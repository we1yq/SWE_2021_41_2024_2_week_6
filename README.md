# SWE_2021_41_2024_2_week_6
---
## Week 4 Assignment
* Github link: [we1yq/SWE_2021_41_2024_2_week_4](https://github.com/we1yq/SWE_2021_41_2024_2_week_4)
```python
def isHappy(n):
  while n >= 10:
    sum = 0
    while n > 0:
      digit = n % 10
      sum += digit ** 2
      n //= 10
    n = sum
  if n != 1:
    return False
  else:
    return True

num = input("Input: ")
print("Output:", isHappy(int(num)))
```
* The function ``isHappy(n)`` determines whether a given number is a "happy number."
* A ``happy number`` is defined as follows:

  > Starting with any positive integer, replace the number by the sum of the squares of its digits.
  > Repeat the process until the number equals 1 (where it will stay), or it ``loops endlessly in a cycle`` which does not include 1.
  > Those numbers for which this process ``ends in 1`` are happy.

* Input:
 
  > The number is taken from the user as input using the ``input()`` function and is converted into an integer with ``int()``.

* isHappy(n):
  
  > The outer loop ``(while n >= 10)`` keeps running as long as the number is 10 or bigger. It calculates the sum of the squares of the digits and updates n with that sum until n becomes a single digit.\
  > 
  > The inner loop ``(while n > 0)`` breaks the number into its digits, squares each digit, and adds those squares together.\
  > 
  > After loop, when ``n != 1``, return ``False``. Else, return ``True``.

* Output:

   > After getting the input from the user and passing it to ``isHappy``, the program prints whether the number is happy (``True``) or not (``False``).
  


---
## Week 5 Assignment
> ```bash
> docker exec <your container> cat /etc/os-release
> ```
> * This command runs the ``cat /etc/os-release`` command inside the Docker container named ``ossp-container``. It reads and displays the contents of the ``/etc/os-release`` file.
>> **Output**
>> ```bash
>> PRETTY_NAME="Ubuntu 24.04.1 LTS"
>> NAME="Ubuntu"
>> VERSION_ID="24.04"
>> VERSION="24.04.1 LTS (Noble Numbat) "
>> VERSION_CODENAME=noble
>> ID=ubuntu
>> ID_LIKE=debian
>> HOME_URL= "https://www.ubuntu.com/"
>> SUPPORT_URL="https://help.ubuntu.com/"
>> BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
>> PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
>> UBUNTU_CODENAME=noble
>> LOGO=ubuntu-logo
>> ```
>> * The output shows that the container is running ``Ubuntu 24.04.1 LTS (Noble Numbat)``. It provides details such as the ``version number``, ``codename``, ``support URLs``, and other metadata about the OS.
<br>
<br>

> ```bash
> docker exec ossp-container git --version
> ```
> * This runs the ``git --version`` command inside the ``ossp-container`` Docker container to check the version of Git installed.
>> **Output**
>> ```bash
>> git version 2.43.0
>> ```
>> * The output shows that ``Git version 2.43.0`` is installed in the container.
<br>
<br>

> ```bash
> docker exec ossp-container python3 --version
> ```
> *  This runs the ``python3 --version`` command inside the ``ossp-container`` Docker container to check the version of Python installed.
>> **Output**
>> ```bash
>> Python 3.12.3
>> ```
>> * The output shows that ``Python 3.12.3`` is installed in the container.
<br>
<br>

> ```bash
> docker inspect --format="{{ .HostConfig.Binds }}" ossp-container
> ```
> * This runs a Docker inspection command on the ``ossp-container`` to view the bind mount configuration using the ``--format`` option to display the ``.HostConfig.Binds`` field.
>> **Output**
>> ```bash
>> [/Users/weiyiqin/ossp_host_dir:/mnt/ossp_container_dir]
>> ```
>> * The output shows that there is a bind mount set up between ``/Users/weiyiqin/ossp_host_dir`` on the host machine and ``/mnt/ossp_container_dir`` inside the container. 
