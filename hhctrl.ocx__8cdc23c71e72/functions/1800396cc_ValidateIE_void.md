# ValidateIE(void)

- ea: `0x1800396cc`
- end: `0x180039814`
- name: `?ValidateIE@@YAHXZ`
- size: `328`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180038640`

## callees

- `0x1800396cc`
- `0x180075c90`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800397ec`
- `ADVAPI32!RegCloseKey` at `0x1800397ec`
- `ADVAPI32!RegQueryValueExA` at `0x18003975c`
- `ADVAPI32!RegQueryValueExA` at `0x180039794`
- `ADVAPI32!RegQueryValueExA` at `0x1800397d3`
- `ADVAPI32!RegQueryValueExA` at `0x18003975c`
- `ADVAPI32!RegQueryValueExA` at `0x180039794`
- `ADVAPI32!RegQueryValueExA` at `0x1800397d3`
- `ADVAPI32!RegOpenKeyExA` at `0x18003971a`
- `ADVAPI32!RegOpenKeyExA` at `0x18003971a`

## pseudocode

```c
_BOOL8 ValidateIE(void)
{
  BOOL v0; // ebx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[2096]; // [rsp+40h] [rbp-C0h] BYREF

  v0 = 0;
  hKey = 0;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SOFTWARE\\Microsoft\\Internet Explorer", 0, 0x20019u, &hKey) )
  {
    cbData = 2084;
    Data[2084] = 0;
    if ( RegQueryValueExA(hKey, "Version", 0, 0, Data, &cbData)
      && (cbData = 2084, RegQueryValueExA(hKey, "IVer", 0, 0, Data, &cbData)) )
    {
      cbData = 2084;
      v0 = RegQueryValueExA(hKey, "Build", 0, 0, Data, &cbData) == 0;
    }
    else
    {
      v0 = 1;
    }
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x1800396cc  mov     [rsp-8+arg_0], rbx
0x1800396d1  push    rbp
0x1800396d2  lea     rbp, [rsp-780h]
0x1800396da  sub     rsp, 880h
0x1800396e1  mov     rax, cs:__security_cookie
0x1800396e8  xor     rax, rsp
0x1800396eb  mov     [rbp+780h+var_10], rax
0x1800396f2  lea     rax, [rsp+880h+hKey]
0x1800396f7  xor     ebx, ebx
0x1800396f9  mov     r9d, 20019h; samDesired
0x1800396ff  mov     [rsp+880h+hKey], rbx
0x180039704  xor     r8d, r8d; ulOptions
0x180039707  mov     [rsp+880h+phkResult], rax; phkResult
0x18003970c  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Internet Explorer"
0x180039713  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003971a  call    cs:__imp_RegOpenKeyExA
0x180039720  test    eax, eax
0x180039722  jnz     loc_1800397F2
0x180039728  mov     rcx, [rsp+880h+hKey]; hKey
0x18003972d  lea     rax, [rsp+880h+cbData]
0x180039732  mov     [rsp+880h+lpcbData], rax; lpcbData
0x180039737  lea     rdx, aVersion; "Version"
0x18003973e  lea     rax, [rsp+880h+Data]
0x180039743  mov     [rsp+880h+cbData], 824h
0x18003974b  xor     r9d, r9d; lpType
0x18003974e  mov     [rsp+880h+phkResult], rax; lpData
0x180039753  xor     r8d, r8d; lpReserved
0x180039756  mov     [rbp+780h+var_1C], bl
0x18003975c  call    cs:__imp_RegQueryValueExA
0x180039762  test    eax, eax
0x180039764  jz      short loc_18003979E
0x180039766  mov     rcx, [rsp+880h+hKey]; hKey
0x18003976b  lea     rax, [rsp+880h+cbData]
0x180039770  mov     [rsp+880h+lpcbData], rax; lpcbData
0x180039775  lea     rdx, aIver; "IVer"
0x18003977c  lea     rax, [rsp+880h+Data]
0x180039781  mov     [rsp+880h+cbData], 824h
0x180039789  xor     r9d, r9d; lpType
0x18003978c  mov     [rsp+880h+phkResult], rax; lpData
0x180039791  xor     r8d, r8d; lpReserved
0x180039794  call    cs:__imp_RegQueryValueExA
0x18003979a  test    eax, eax
0x18003979c  jnz     short loc_1800397A5
0x18003979e  mov     ebx, 1
0x1800397a3  jmp     short loc_1800397E7
0x1800397a5  mov     rcx, [rsp+880h+hKey]; hKey
0x1800397aa  lea     rax, [rsp+880h+cbData]
0x1800397af  mov     [rsp+880h+lpcbData], rax; lpcbData
0x1800397b4  lea     rdx, aBuild; "Build"
0x1800397bb  lea     rax, [rsp+880h+Data]
0x1800397c0  mov     [rsp+880h+cbData], 824h
0x1800397c8  xor     r9d, r9d; lpType
0x1800397cb  mov     [rsp+880h+phkResult], rax; lpData
0x1800397d0  xor     r8d, r8d; lpReserved
0x1800397d3  call    cs:__imp_RegQueryValueExA
0x1800397d9  mov     ecx, ebx
0x1800397db  mov     ebx, 1
0x1800397e0  test    eax, eax
0x1800397e2  cmovz   ecx, ebx
0x1800397e5  mov     ebx, ecx
0x1800397e7  mov     rcx, [rsp+880h+hKey]; hKey
0x1800397ec  call    cs:__imp_RegCloseKey
0x1800397f2  mov     eax, ebx
0x1800397f4  mov     rcx, [rbp+780h+var_10]
0x1800397fb  xor     rcx, rsp; StackCookie
0x1800397fe  call    __security_check_cookie
0x180039803  mov     rbx, [rsp+880h+arg_0]
0x18003980b  add     rsp, 880h
0x180039812  pop     rbp
0x180039813  retn
```
