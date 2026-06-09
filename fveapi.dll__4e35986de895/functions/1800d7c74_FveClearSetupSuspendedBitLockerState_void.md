# FveClearSetupSuspendedBitLockerState(void)

- ea: `0x1800d7c74`
- end: `0x1800d7dc3`
- name: `?FveClearSetupSuspendedBitLockerState@@YAXXZ`
- size: `335`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180058cdc`

## callees

- `0x180019128`
- `0x1800d7c74`
- `0x1800d7fb4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d7d6c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d7d6c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800d7d00`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800d7d00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d7db0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d7db0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d7cb9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d7cb9`

## pseudocode

```c
void FveClearSetupSuspendedBitLockerState(void)
{
  unsigned int v0; // eax
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  unsigned int v3; // eax
  int Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  Data = 0;
  hKey = 0;
  if ( !FveDidSetupSuspendBitLocker() )
    goto LABEL_15;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup", 0, 2u, &hKey);
  if ( v0 )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_15;
    v2 = 55;
    goto LABEL_14;
  }
  v3 = RegDeleteValueW(hKey, L"BitLockerSuspended");
  if ( (v3 & 0xFFFFFFFD) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, v3);
    v0 = RegSetValueExW(hKey, L"BitLockerSuspended", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v0 )
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v2 = 57;
LABEL_14:
        WPP_SF_D(v1[2], v2, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, v0);
      }
    }
  }
LABEL_15:
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x1800d7c74  push    rbx
0x1800d7c76  sub     rsp, 30h
0x1800d7c7a  mov     [rsp+38h+Data], 0
0x1800d7c82  mov     [rsp+38h+hKey], 0
0x1800d7c8b  call    ?FveDidSetupSuspendBitLocker@@YA_NXZ; FveDidSetupSuspendBitLocker(void)
0x1800d7c90  test    al, al
0x1800d7c92  jz      loc_1800D7DA6
0x1800d7c98  lea     rax, [rsp+38h+hKey]
0x1800d7c9d  mov     r9d, 2; samDesired
0x1800d7ca3  xor     r8d, r8d; ulOptions
0x1800d7ca6  mov     [rsp+38h+phkResult], rax; phkResult
0x1800d7cab  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x1800d7cb2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d7cb9  call    cs:__imp_RegOpenKeyExW
0x1800d7cc0  nop     dword ptr [rax+rax+00h]
0x1800d7cc5  test    eax, eax
0x1800d7cc7  jz      short loc_1800D7CF4
0x1800d7cc9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d7cd0  lea     rbx, WPP_GLOBAL_Control
0x1800d7cd7  cmp     rcx, rbx
0x1800d7cda  jz      loc_1800D7DA6
0x1800d7ce0  test    byte ptr [rcx+1Ch], 2
0x1800d7ce4  jz      loc_1800D7DA6
0x1800d7cea  mov     edx, 37h ; '7'
0x1800d7cef  jmp     loc_1800D7D93
0x1800d7cf4  mov     rcx, [rsp+38h+hKey]; hKey
0x1800d7cf9  lea     rdx, aBitlockersuspe; "BitLockerSuspended"
0x1800d7d00  call    cs:__imp_RegDeleteValueW
0x1800d7d07  nop     dword ptr [rax+rax+00h]
0x1800d7d0c  test    eax, 0FFFFFFFDh
0x1800d7d11  jz      loc_1800D7DA6
0x1800d7d17  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d7d1e  lea     rbx, WPP_GLOBAL_Control
0x1800d7d25  cmp     rcx, rbx
0x1800d7d28  jz      short loc_1800D7D48
0x1800d7d2a  test    byte ptr [rcx+1Ch], 2
0x1800d7d2e  jz      short loc_1800D7D48
0x1800d7d30  mov     rcx, [rcx+10h]
0x1800d7d34  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x1800d7d3b  mov     edx, 38h ; '8'
0x1800d7d40  mov     r9d, eax
0x1800d7d43  call    WPP_SF_D
0x1800d7d48  mov     rcx, [rsp+38h+hKey]; hKey
0x1800d7d4d  lea     rax, [rsp+38h+Data]
0x1800d7d52  mov     r9d, 4; dwType
0x1800d7d58  lea     rdx, aBitlockersuspe; "BitLockerSuspended"
0x1800d7d5f  mov     [rsp+38h+cbData], r9d; cbData
0x1800d7d64  xor     r8d, r8d; Reserved
0x1800d7d67  mov     [rsp+38h+phkResult], rax; lpData
0x1800d7d6c  call    cs:__imp_RegSetValueExW
0x1800d7d73  nop     dword ptr [rax+rax+00h]
0x1800d7d78  test    eax, eax
0x1800d7d7a  jz      short loc_1800D7DA6
0x1800d7d7c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d7d83  cmp     rcx, rbx
0x1800d7d86  jz      short loc_1800D7DA6
0x1800d7d88  test    byte ptr [rcx+1Ch], 2
0x1800d7d8c  jz      short loc_1800D7DA6
0x1800d7d8e  mov     edx, 39h ; '9'
0x1800d7d93  mov     rcx, [rcx+10h]
0x1800d7d97  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x1800d7d9e  mov     r9d, eax
0x1800d7da1  call    WPP_SF_D
0x1800d7da6  mov     rcx, [rsp+38h+hKey]; hKey
0x1800d7dab  test    rcx, rcx
0x1800d7dae  jz      short loc_1800D7DBC
0x1800d7db0  call    cs:__imp_RegCloseKey
0x1800d7db7  nop     dword ptr [rax+rax+00h]
0x1800d7dbc  add     rsp, 30h
0x1800d7dc0  pop     rbx
0x1800d7dc1  retn
```
