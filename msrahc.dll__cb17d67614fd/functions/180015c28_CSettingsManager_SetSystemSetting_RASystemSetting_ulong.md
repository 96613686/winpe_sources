# CSettingsManager::SetSystemSetting(_RASystemSetting,ulong)

- ea: `0x180015c28`
- end: `0x180015d0a`
- name: `?SetSystemSetting@CSettingsManager@@QEAAJW4_RASystemSetting@@K@Z`
- size: `226`
- prototype: `__int64 __fastcall(HANDLE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180011af8`

## callees

- `0x180015c28`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180015cc6`
- `ADVAPI32!RegSetValueExW` at `0x180015cc6`
- `ADVAPI32!RegOpenKeyExW` at `0x180015c98`
- `ADVAPI32!RegOpenKeyExW` at `0x180015c98`
- `ADVAPI32!RegCloseKey` at `0x180015ce2`
- `ADVAPI32!RegCloseKey` at `0x180015ce2`
- `KERNEL32!ReleaseMutex` at `0x180015cf9`
- `KERNEL32!ReleaseMutex` at `0x180015cf9`
- `KERNEL32!WaitForSingleObject` at `0x180015c5c`
- `KERNEL32!WaitForSingleObject` at `0x180015c5c`

## pseudocode

```c
__int64 __fastcall CSettingsManager::SetSystemSetting(HANDLE *a1)
{
  HANDLE v2; // rcx
  unsigned int v3; // edi
  int v4; // ebp
  int v5; // ebx
  BYTE Data[56]; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF

  *(_DWORD *)Data = 1;
  v2 = *a1;
  hKey = 0;
  if ( !v2 )
    return (unsigned int)-2147418113;
  if ( WaitForSingleObject(v2, 0x64u) == 258 )
  {
    v4 = 0;
  }
  else
  {
    v4 = 1;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Control\\Remote Assistance",
            0,
            0x20006u,
            &hKey) )
    {
      v5 = 0;
      if ( RegSetValueExW(hKey, RA_SYSTEM_SETTINGS, 0, 4u, Data, 4u) )
        v5 = -2147467259;
      v3 = v5;
      goto LABEL_10;
    }
  }
  v3 = -2147467259;
LABEL_10:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v4 == 1 )
    ReleaseMutex(*a1);
  return v3;
}

```

## disassembly

```asm
0x180015c28  push    rbx
0x180015c2a  push    rbp
0x180015c2b  push    rsi
0x180015c2c  push    rdi
0x180015c2d  sub     rsp, 48h
0x180015c31  mov     rsi, rcx
0x180015c34  mov     dword ptr [rsp+68h+Data], 1
0x180015c3c  mov     rcx, [rcx]; hHandle
0x180015c3f  mov     [rsp+68h+hKey], 0
0x180015c48  test    rcx, rcx
0x180015c4b  jnz     short loc_180015C57
0x180015c4d  mov     edi, 8000FFFFh
0x180015c52  jmp     loc_180015CFF
0x180015c57  mov     edx, 64h ; 'd'; dwMilliseconds
0x180015c5c  call    cs:__imp_WaitForSingleObject
0x180015c62  cmp     eax, 102h
0x180015c67  jnz     short loc_180015C72
0x180015c69  xor     ebp, ebp
0x180015c6b  mov     edi, 80004005h
0x180015c70  jmp     short loc_180015CD8
0x180015c72  lea     rax, [rsp+68h+hKey]
0x180015c77  mov     r9d, 20006h; samDesired
0x180015c7d  xor     r8d, r8d; ulOptions
0x180015c80  mov     [rsp+68h+phkResult], rax; phkResult
0x180015c85  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Rem"...
0x180015c8c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015c93  mov     ebp, 1
0x180015c98  call    cs:__imp_RegOpenKeyExW
0x180015c9e  test    eax, eax
0x180015ca0  jnz     short loc_180015C6B
0x180015ca2  mov     rdx, cs:?RA_SYSTEM_SETTINGS@@3PAPEBGA; lpValueName
0x180015ca9  lea     r9d, [rbp+3]; dwType
0x180015cad  mov     rcx, [rsp+68h+hKey]; hKey
0x180015cb2  lea     rax, [rsp+68h+Data]
0x180015cb7  mov     [rsp+68h+cbData], r9d; cbData
0x180015cbc  xor     r8d, r8d; Reserved
0x180015cbf  mov     [rsp+68h+phkResult], rax; lpData
0x180015cc4  xor     ebx, ebx
0x180015cc6  call    cs:__imp_RegSetValueExW
0x180015ccc  mov     edi, 80004005h
0x180015cd1  test    eax, eax
0x180015cd3  cmovnz  ebx, edi
0x180015cd6  mov     edi, ebx
0x180015cd8  mov     rcx, [rsp+68h+hKey]; hKey
0x180015cdd  test    rcx, rcx
0x180015ce0  jz      short loc_180015CF1
0x180015ce2  call    cs:__imp_RegCloseKey
0x180015ce8  mov     [rsp+68h+hKey], 0
0x180015cf1  cmp     ebp, 1
0x180015cf4  jnz     short loc_180015CFF
0x180015cf6  mov     rcx, [rsi]; hMutex
0x180015cf9  call    cs:__imp_ReleaseMutex
0x180015cff  mov     eax, edi
0x180015d01  add     rsp, 48h
0x180015d05  pop     rdi
0x180015d06  pop     rsi
0x180015d07  pop     rbp
0x180015d08  pop     rbx
0x180015d09  retn
```
