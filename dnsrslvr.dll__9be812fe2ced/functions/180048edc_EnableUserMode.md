# EnableUserMode

- ea: `0x180048edc`
- end: `0x180049067`
- name: `EnableUserMode`
- size: `395`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1800494f8`

## callees

- `0x180046ec0`
- `0x180048edc`
- `0x18007b294`
- `0x180085e68`
- `0x180086ab0`
- `0x180086fe4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048fb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048fb7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180048f39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180048f39`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180048fab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180048fab`

## string_xrefs

- `0x180048f1d`: `system\currentcontrolset\services\Lmhosts\Parameters`
- `0x180048f5e`: `system\currentcontrolset\services\Lmhosts\Parameters`
- `0x180048fe5`: `system\currentcontrolset\services\Lmhosts\Parameters`
- `0x180049018`: `system\currentcontrolset\services\Lmhosts\Parameters`

## pseudocode

```c
bool EnableUserMode()
{
  LSTATUS v0; // eax
  LSTATUS v1; // ebx
  LPDWORD lpcbData; // [rsp+28h] [rbp-28h]
  HKEY hKey; // [rsp+30h] [rbp-20h] BYREF
  DWORD Type; // [rsp+38h] [rbp-18h] BYREF
  BYTE Data[4]; // [rsp+3Ch] [rbp-14h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-10h] BYREF

  hKey = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  Type = 0;
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"system\\currentcontrolset\\services\\Lmhosts\\Parameters",
         0,
         0x20019u,
         &hKey);
  if ( v0 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_Sd(
        1035,
        23,
        (unsigned int)WPP_baf6623f38bf314eb96485734268b87e_Traceguids,
        (unsigned int)L"system\\currentcontrolset\\services\\Lmhosts\\Parameters",
        v0);
    return 0;
  }
  Type = 4;
  cbData = 4;
  v1 = RegQueryValueExW(hKey, L"EnableUserMode", 0, &Type, Data, &cbData);
  RegCloseKey(hKey);
  hKey = 0;
  if ( v1 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      LODWORD(lpcbData) = v1;
      WPP_SF_SSd(
        1035,
        24,
        (unsigned int)WPP_baf6623f38bf314eb96485734268b87e_Traceguids,
        (unsigned int)L"system\\currentcontrolset\\services\\Lmhosts\\Parameters",
        (__int64)L"EnableUserMode",
        lpcbData,
        hKey);
    }
    return 0;
  }
  if ( Type != 4 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_SS(
        1035,
        25,
        (unsigned int)WPP_baf6623f38bf314eb96485734268b87e_Traceguids,
        (unsigned int)L"system\\currentcontrolset\\services\\Lmhosts\\Parameters",
        (__int64)L"EnableUserMode");
    return 0;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_SSL();
  return *(_DWORD *)Data != 0;
}

```

## disassembly

```asm
0x180048edc  mov     [rsp-8+arg_0], rbx
0x180048ee1  mov     [rsp-8+arg_8], r15
0x180048ee6  push    rbp
0x180048ee7  mov     rbp, rsp
0x180048eea  sub     rsp, 50h
0x180048eee  mov     rax, cs:__security_cookie
0x180048ef5  xor     rax, rsp
0x180048ef8  mov     [rbp+var_8], rax
0x180048efc  lea     rax, [rbp+hKey]
0x180048f00  mov     [rbp+hKey], 0
0x180048f08  mov     r9d, 20019h; samDesired
0x180048f0e  mov     [rsp+50h+phkResult], rax; phkResult
0x180048f13  xor     r8d, r8d; ulOptions
0x180048f16  mov     dword ptr [rbp+Data], 0
0x180048f1d  lea     rdx, aSystemCurrentc_2; "system\\currentcontrolset\\services\\Lm"...
0x180048f24  mov     [rbp+cbData], 0
0x180048f2b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180048f32  mov     [rbp+Type], 0
0x180048f39  call    cs:__imp_RegOpenKeyExW
0x180048f3f  test    eax, eax
0x180048f41  jz      short loc_180048F76
0x180048f43  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180048f4a  jz      loc_18004902B
0x180048f50  mov     edx, 17h
0x180048f55  mov     dword ptr [rsp+50h+phkResult], eax
0x180048f59  mov     ecx, 40Bh
0x180048f5e  lea     r9, aSystemCurrentc_2; "system\\currentcontrolset\\services\\Lm"...
0x180048f65  lea     r8, WPP_baf6623f38bf314eb96485734268b87e_Traceguids
0x180048f6c  call    WPP_SF_Sd
0x180048f71  jmp     loc_18004902B
0x180048f76  mov     rcx, [rbp+hKey]; hKey
0x180048f7a  lea     rax, [rbp+cbData]
0x180048f7e  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180048f83  lea     r15, aEnableusermode; "EnableUserMode"
0x180048f8a  lea     rax, [rbp+Data]
0x180048f8e  mov     [rbp+Type], 4
0x180048f95  lea     r9, [rbp+Type]; lpType
0x180048f99  mov     [rsp+50h+phkResult], rax; lpData
0x180048f9e  xor     r8d, r8d; lpReserved
0x180048fa1  mov     [rbp+cbData], 4
0x180048fa8  mov     rdx, r15; lpValueName
0x180048fab  call    cs:__imp_RegQueryValueExW
0x180048fb1  mov     rcx, [rbp+hKey]; hKey
0x180048fb5  mov     ebx, eax
0x180048fb7  call    cs:__imp_RegCloseKey
0x180048fbd  mov     [rbp+hKey], 0
0x180048fc5  test    ebx, ebx
0x180048fc7  jz      short loc_180048FFA
0x180048fc9  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180048fd0  jz      short loc_18004902B
0x180048fd2  mov     edx, 18h
0x180048fd7  mov     dword ptr [rsp+50h+lpcbData], ebx
0x180048fdb  mov     ecx, 40Bh
0x180048fe0  mov     [rsp+50h+phkResult], r15
0x180048fe5  lea     r9, aSystemCurrentc_2; "system\\currentcontrolset\\services\\Lm"...
0x180048fec  lea     r8, WPP_baf6623f38bf314eb96485734268b87e_Traceguids
0x180048ff3  call    WPP_SF_SSd
0x180048ff8  jmp     short loc_18004902B
0x180048ffa  cmp     [rbp+Type], 4
0x180048ffe  jz      short loc_18004902F
0x180049000  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180049007  jz      short loc_18004902B
0x180049009  mov     edx, 19h
0x18004900e  mov     [rsp+50h+phkResult], r15
0x180049013  mov     ecx, 40Bh
0x180049018  lea     r9, aSystemCurrentc_2; "system\\currentcontrolset\\services\\Lm"...
0x18004901f  lea     r8, WPP_baf6623f38bf314eb96485734268b87e_Traceguids
0x180049026  call    WPP_SF_SS
0x18004902b  xor     al, al
0x18004902d  jmp     short loc_18004904B
0x18004902f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180049036  jz      short loc_180049044
0x180049038  mov     eax, dword ptr [rbp+Data]
0x18004903b  mov     dword ptr [rsp+50h+lpcbData], eax
0x18004903f  call    WPP_SF_SSL
0x180049044  cmp     dword ptr [rbp+Data], 0
0x180049048  setnz   al
0x18004904b  mov     rcx, [rbp+var_8]
0x18004904f  xor     rcx, rsp; StackCookie
0x180049052  call    __security_check_cookie
0x180049057  mov     rbx, [rsp+50h+arg_0]
0x18004905c  mov     r15, [rsp+50h+arg_8]
0x180049061  add     rsp, 50h
0x180049065  pop     rbp
0x180049066  retn
```
