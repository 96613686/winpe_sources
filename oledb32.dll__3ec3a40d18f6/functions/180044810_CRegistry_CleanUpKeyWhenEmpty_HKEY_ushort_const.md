# CRegistry::CleanUpKeyWhenEmpty(HKEY__ *,ushort const *)

- ea: `0x180044810`
- end: `0x18004489f`
- name: `?CleanUpKeyWhenEmpty@CRegistry@@AEAAXPEAUHKEY__@@PEBG@Z`
- size: `143`
- prototype: `void(CRegistry *__hidden this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180044aa4`

## callees

- `0x180044810`
- `0x18007e700`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x180044865`
- `ADVAPI32!RegEnumValueW` at `0x180044865`
- `ADVAPI32!RegDeleteKeyW` at `0x180044878`
- `ADVAPI32!RegDeleteKeyW` at `0x180044878`

## pseudocode

```c
void __fastcall CRegistry::CleanUpKeyWhenEmpty(HKEY *this, HKEY a2, const unsigned __int16 *a3)
{
  DWORD cchValueName[4]; // [rsp+40h] [rbp-238h] BYREF
  WCHAR ValueName[264]; // [rsp+50h] [rbp-228h] BYREF

  cchValueName[0] = 261;
  if ( RegEnumValueW(a2, 0, ValueName, cchValueName, 0, 0, 0, 0) == 259 )
    RegDeleteKeyW(*this, a3);
}

```

## disassembly

```asm
0x180044810  mov     [rsp+arg_18], rbx
0x180044815  push    rdi
0x180044816  sub     rsp, 270h
0x18004481d  mov     rax, cs:__security_cookie
0x180044824  xor     rax, rsp
0x180044827  mov     [rsp+278h+var_18], rax
0x18004482f  mov     rbx, rcx
0x180044832  mov     [rsp+278h+cchValueName], 105h
0x18004483a  xor     ecx, ecx
0x18004483c  lea     r9, [rsp+278h+cchValueName]; lpcchValueName
0x180044841  mov     [rsp+278h+lpcbData], rcx; lpcbData
0x180044846  mov     rax, rdx
0x180044849  mov     [rsp+278h+lpData], rcx; lpData
0x18004484e  mov     rdi, r8
0x180044851  mov     [rsp+278h+lpType], rcx; lpType
0x180044856  lea     r8, [rsp+278h+ValueName]; lpValueName
0x18004485b  mov     [rsp+278h+lpReserved], rcx; lpReserved
0x180044860  xor     edx, edx; dwIndex
0x180044862  mov     rcx, rax; hKey
0x180044865  call    cs:__imp_RegEnumValueW
0x18004486b  cmp     eax, 103h
0x180044870  jnz     short loc_18004487E
0x180044872  mov     rcx, [rbx]; hKey
0x180044875  mov     rdx, rdi; lpSubKey
0x180044878  call    cs:__imp_RegDeleteKeyW
0x18004487e  mov     rcx, [rsp+278h+var_18]
0x180044886  xor     rcx, rsp; StackCookie
0x180044889  call    __security_check_cookie
0x18004488e  mov     rbx, [rsp+278h+arg_18]
0x180044896  add     rsp, 270h
0x18004489d  pop     rdi
0x18004489e  retn
```
