# CFvePolicyReader::ResetRootPolicyKeys(void)

- ea: `0x18002af80`
- end: `0x18002b061`
- name: `?ResetRootPolicyKeys@CFvePolicyReader@@AEAAJXZ`
- size: `225`
- prototype: `__int64 __fastcall(CFvePolicyReader *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002b0b0`

## callees

- `0x18002a940`
- `0x18002af80`
- `0x18002b068`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18002b03e`
- `ADVAPI32!RegCloseKey` at `0x18002b04e`
- `ADVAPI32!RegCloseKey` at `0x18002b03e`
- `ADVAPI32!RegCloseKey` at `0x18002b04e`
- `ADVAPI32!RegOpenKeyExW` at `0x18002afcd`
- `ADVAPI32!RegOpenKeyExW` at `0x18002b007`
- `ADVAPI32!RegOpenKeyExW` at `0x18002afcd`
- `ADVAPI32!RegOpenKeyExW` at `0x18002b007`

## pseudocode

```c
__int64 __fastcall CFvePolicyReader::ResetRootPolicyKeys(CFvePolicyReader *this)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  LSTATUS v4; // eax
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  phkResult = 0;
  CFvePolicyReader::CloseRootPolicyKeys(this);
  CFvePolicyReader::UnloadVolumePolicy(this);
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software", 0, 0x20019u, &hKey);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 < 0 )
    goto LABEL_8;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System", 0, 0x20019u, &phkResult);
  v3 = v4;
  if ( v4 > 0 )
    v3 = (unsigned __int16)v4 | 0x80070000;
  if ( v3 < 0 )
  {
LABEL_8:
    if ( hKey )
      RegCloseKey(hKey);
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  else
  {
    *((_QWORD *)this + 2) = hKey;
    *((_QWORD *)this + 3) = phkResult;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002af80  mov     [rsp+arg_0], rbx
0x18002af85  push    rdi
0x18002af86  sub     rsp, 30h
0x18002af8a  mov     rdi, rcx
0x18002af8d  mov     [rsp+38h+hKey], 0
0x18002af96  mov     [rsp+38h+arg_10], 0
0x18002af9f  call    ?CloseRootPolicyKeys@CFvePolicyReader@@AEAAXXZ; CFvePolicyReader::CloseRootPolicyKeys(void)
0x18002afa4  mov     rcx, rdi; this
0x18002afa7  call    ?UnloadVolumePolicy@CFvePolicyReader@@AEAAXXZ; CFvePolicyReader::UnloadVolumePolicy(void)
0x18002afac  lea     rax, [rsp+38h+hKey]
0x18002afb1  mov     r9d, 20019h; samDesired
0x18002afb7  xor     r8d, r8d; ulOptions
0x18002afba  mov     [rsp+38h+phkResult], rax; phkResult
0x18002afbf  lea     rdx, aSoftware; "Software"
0x18002afc6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002afcd  call    cs:__imp_RegOpenKeyExW
0x18002afd3  mov     ebx, eax
0x18002afd5  test    eax, eax
0x18002afd7  jle     short loc_18002AFE2
0x18002afd9  movzx   ebx, ax
0x18002afdc  or      ebx, 80070000h
0x18002afe2  test    ebx, ebx
0x18002afe4  js      short loc_18002B034
0x18002afe6  lea     rax, [rsp+38h+arg_10]
0x18002afeb  mov     r9d, 20019h; samDesired
0x18002aff1  xor     r8d, r8d; ulOptions
0x18002aff4  mov     [rsp+38h+phkResult], rax; phkResult
0x18002aff9  lea     rdx, aSystem; "System"
0x18002b000  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b007  call    cs:__imp_RegOpenKeyExW
0x18002b00d  mov     ebx, eax
0x18002b00f  test    eax, eax
0x18002b011  jle     short loc_18002B01C
0x18002b013  movzx   ebx, ax
0x18002b016  or      ebx, 80070000h
0x18002b01c  test    ebx, ebx
0x18002b01e  js      short loc_18002B034
0x18002b020  mov     rax, [rsp+38h+hKey]
0x18002b025  mov     [rdi+10h], rax
0x18002b029  mov     rax, [rsp+38h+arg_10]
0x18002b02e  mov     [rdi+18h], rax
0x18002b032  jmp     short loc_18002B054
0x18002b034  mov     rcx, [rsp+38h+hKey]; hKey
0x18002b039  test    rcx, rcx
0x18002b03c  jz      short loc_18002B044
0x18002b03e  call    cs:__imp_RegCloseKey
0x18002b044  mov     rcx, [rsp+38h+arg_10]; hKey
0x18002b049  test    rcx, rcx
0x18002b04c  jz      short loc_18002B054
0x18002b04e  call    cs:__imp_RegCloseKey
0x18002b054  mov     eax, ebx
0x18002b056  mov     rbx, [rsp+38h+arg_0]
0x18002b05b  add     rsp, 30h
0x18002b05f  pop     rdi
0x18002b060  retn
```
