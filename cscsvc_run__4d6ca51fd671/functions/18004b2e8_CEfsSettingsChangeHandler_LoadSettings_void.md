# CEfsSettingsChangeHandler::LoadSettings(void)

- ea: `0x18004b2e8`
- end: `0x18004b3ac`
- name: `?LoadSettings@CEfsSettingsChangeHandler@@UEAAJXZ`
- size: `196`
- prototype: `__int64 __fastcall(CEfsSettingsChangeHandler *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005ddb0`

## callees

- `0x18004b2e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b325`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b325`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b362`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b362`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b38a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b38a`

## string_xrefs

- `0x18004b33c`: `EfsConfiguration`

## pseudocode

```c
__int64 __fastcall CEfsSettingsChangeHandler::LoadSettings(CEfsSettingsChangeHandler *this)
{
  unsigned int v2; // ebx
  __int64 result; // rax
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  int Data; // [rsp+58h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  *((_DWORD *)this + 2) = 1;
  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Windows NT\\CurrentVersion\\EFS",
         0,
         1u,
         &hKey);
  if ( !v2 )
  {
    Data = 0;
    Type = 0;
    cbData = 4;
    v2 = RegQueryValueExW(hKey, L"EfsConfiguration", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v2 )
    {
      if ( Type == 4 )
        *((_DWORD *)this + 2) = (Data & 1) == 0;
      else
        v2 = 13;
    }
    RegCloseKey(hKey);
  }
  result = 0;
  if ( v2 != 2 )
    result = v2;
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18004b2e8  push    rbp
0x18004b2ea  push    rbx
0x18004b2eb  push    rdi
0x18004b2ec  mov     rbp, rsp
0x18004b2ef  sub     rsp, 30h
0x18004b2f3  mov     rdi, rcx
0x18004b2f6  mov     dword ptr [rcx+8], 1
0x18004b2fd  lea     rax, [rbp+hKey]
0x18004b301  mov     [rbp+hKey], 0
0x18004b309  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004b310  mov     [rsp+30h+phkResult], rax; phkResult
0x18004b315  mov     r9d, 1; samDesired
0x18004b31b  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x18004b322  xor     r8d, r8d; ulOptions
0x18004b325  call    cs:__imp_RegOpenKeyExW
0x18004b32b  mov     ebx, eax
0x18004b32d  test    eax, eax
0x18004b32f  jnz     short loc_18004B390
0x18004b331  mov     rcx, [rbp+hKey]; hKey
0x18004b335  lea     r9, [rbp+Type]; lpType
0x18004b339  mov     [rbp+Data], eax
0x18004b33c  lea     rdx, aEfsconfigurati; "EfsConfiguration"
0x18004b343  mov     [rbp+Type], eax
0x18004b346  xor     r8d, r8d; lpReserved
0x18004b349  lea     rax, [rbp+cbData]
0x18004b34d  mov     [rbp+cbData], 4
0x18004b354  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18004b359  lea     rax, [rbp+Data]
0x18004b35d  mov     [rsp+30h+phkResult], rax; lpData
0x18004b362  call    cs:__imp_RegQueryValueExW
0x18004b368  mov     ebx, eax
0x18004b36a  test    eax, eax
0x18004b36c  jnz     short loc_18004B386
0x18004b36e  cmp     [rbp+Type], 4
0x18004b372  jnz     short loc_18004B381
0x18004b374  mov     eax, [rbp+Data]
0x18004b377  not     eax
0x18004b379  and     eax, 1
0x18004b37c  mov     [rdi+8], eax
0x18004b37f  jmp     short loc_18004B386
0x18004b381  mov     ebx, 0Dh
0x18004b386  mov     rcx, [rbp+hKey]; hKey
0x18004b38a  call    cs:__imp_RegCloseKey
0x18004b390  xor     eax, eax
0x18004b392  cmp     ebx, 2
0x18004b395  cmovnz  eax, ebx
0x18004b398  test    eax, eax
0x18004b39a  jle     short loc_18004B3A4
0x18004b39c  movzx   eax, ax
0x18004b39f  or      eax, 80070000h
0x18004b3a4  add     rsp, 30h
0x18004b3a8  pop     rdi
0x18004b3a9  pop     rbx
0x18004b3aa  pop     rbp
0x18004b3ab  retn
```
