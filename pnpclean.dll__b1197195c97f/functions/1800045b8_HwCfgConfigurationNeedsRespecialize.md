# HwCfgConfigurationNeedsRespecialize

- ea: `0x1800045b8`
- end: `0x180004689`
- name: `HwCfgConfigurationNeedsRespecialize`
- size: `209`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004e74`

## callees

- `0x1800045b8`
- `0x18000474c`
- `0x18000480c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000460a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000460a`
- `ADVAPI32!RegCloseKey` at `0x180004665`
- `ADVAPI32!RegCloseKey` at `0x180004674`
- `ADVAPI32!RegCloseKey` at `0x180004665`
- `ADVAPI32!RegCloseKey` at `0x180004674`
- `ADVAPI32!RegSetValueExW` at `0x180004655`
- `ADVAPI32!RegSetValueExW` at `0x180004655`

## pseudocode

```c
__int64 __fastcall HwCfgConfigurationNeedsRespecialize(LPCWSTR lpSubKey)
{
  HKEY v1; // rbx
  unsigned int RootKey; // eax
  unsigned int CurrentKey; // edi
  int Data; // [rsp+50h] [rbp+20h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+30h]

  v1 = 0;
  hKey = 0;
  phkResult = 0;
  Data = 0;
  if ( !lpSubKey )
  {
    CurrentKey = HwCfgGetCurrentKey(2u);
    if ( CurrentKey )
      goto LABEL_9;
    goto LABEL_6;
  }
  RootKey = HwCfgGetRootKey(0x20019u);
  v1 = hKey;
  CurrentKey = RootKey;
  if ( !RootKey )
  {
    CurrentKey = RegOpenKeyExW(hKey, lpSubKey, 0, 2u, &phkResult);
    if ( !CurrentKey )
    {
LABEL_6:
      Data = 1;
      CurrentKey = RegSetValueExW(phkResult, L"Respecialize", 0, 4u, (const BYTE *)&Data, 4u);
    }
  }
  if ( v1 )
    RegCloseKey(v1);
LABEL_9:
  if ( phkResult )
    RegCloseKey(phkResult);
  return CurrentKey;
}

```

## disassembly

```asm
0x1800045b8  mov     [rsp-18h+arg_18], rbx
0x1800045bd  push    rbp
0x1800045be  push    rsi
0x1800045bf  push    rdi
0x1800045c0  mov     rbp, rsp
0x1800045c3  sub     rsp, 30h
0x1800045c7  xor     ebx, ebx
0x1800045c9  mov     rsi, rcx
0x1800045cc  mov     [rbp+hKey], rbx
0x1800045d0  mov     [rbp+arg_8], rbx
0x1800045d4  mov     [rbp+Data], ebx
0x1800045d7  test    rcx, rcx
0x1800045da  jz      short loc_180004618
0x1800045dc  lea     rdx, [rbp+hKey]
0x1800045e0  mov     ecx, 20019h; samDesired
0x1800045e5  call    HwCfgGetRootKey
0x1800045ea  mov     rbx, [rbp+hKey]
0x1800045ee  mov     edi, eax
0x1800045f0  test    eax, eax
0x1800045f2  jnz     short loc_18000465D
0x1800045f4  lea     rax, [rbp+arg_8]
0x1800045f8  xor     r8d, r8d; ulOptions
0x1800045fb  lea     r9d, [rdi+2]; samDesired
0x1800045ff  mov     [rsp+30h+phkResult], rax; phkResult
0x180004604  mov     rdx, rsi; lpSubKey
0x180004607  mov     rcx, rbx; hKey
0x18000460a  call    cs:__imp_RegOpenKeyExW
0x180004610  mov     edi, eax
0x180004612  test    eax, eax
0x180004614  jnz     short loc_18000465D
0x180004616  jmp     short loc_18000462C
0x180004618  lea     rdx, [rbp+arg_8]
0x18000461c  mov     ecx, 2; samDesired
0x180004621  call    HwCfgGetCurrentKey
0x180004626  mov     edi, eax
0x180004628  test    eax, eax
0x18000462a  jnz     short loc_18000466B
0x18000462c  mov     rcx, [rbp+arg_8]; hKey
0x180004630  lea     rax, [rbp+Data]
0x180004634  mov     r9d, 4; dwType
0x18000463a  mov     [rbp+Data], 1
0x180004641  mov     [rsp+30h+cbData], r9d; cbData
0x180004646  lea     rdx, ValueName; "Respecialize"
0x18000464d  xor     r8d, r8d; Reserved
0x180004650  mov     [rsp+30h+phkResult], rax; lpData
0x180004655  call    cs:__imp_RegSetValueExW
0x18000465b  mov     edi, eax
0x18000465d  test    rbx, rbx
0x180004660  jz      short loc_18000466B
0x180004662  mov     rcx, rbx; hKey
0x180004665  call    cs:__imp_RegCloseKey
0x18000466b  mov     rcx, [rbp+arg_8]; hKey
0x18000466f  test    rcx, rcx
0x180004672  jz      short loc_18000467A
0x180004674  call    cs:__imp_RegCloseKey
0x18000467a  mov     rbx, [rsp+30h+arg_18]
0x18000467f  mov     eax, edi
0x180004681  add     rsp, 30h
0x180004685  pop     rdi
0x180004686  pop     rsi
0x180004687  pop     rbp
0x180004688  retn
```
