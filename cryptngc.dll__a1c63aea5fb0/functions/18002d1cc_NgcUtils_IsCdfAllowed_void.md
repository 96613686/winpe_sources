# NgcUtils::IsCdfAllowed(void)

- ea: `0x18002d1cc`
- end: `0x18002d314`
- name: `?IsCdfAllowed@NgcUtils@@YA_NXZ`
- size: `328`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800433ec`

## callees

- `0x18002d1cc`
- `0x18002f150`
- `0x180032fcc`
- `0x180042304`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002d219`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002d2db`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002d219`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002d2db`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18002d26f`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18002d26f`

## string_xrefs

- `0x18002d239`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x18002d27d`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x18002d2f9`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`

## pseudocode

```c
bool __fastcall NgcUtils::IsCdfAllowed(NgcUtils *this)
{
  unsigned int ValueW; // eax
  int PolicyInt; // eax
  unsigned int v4; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-20h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  int pvData; // [rsp+50h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+18h] BYREF
  int v10; // [rsp+60h] [rbp+20h] BYREF

  pvData = 1;
  pcbData = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Providers\\{48B4E58D-2791-456C-9091-D524C6C706F2}",
             L"Disabled",
             0x10u,
             0,
             &pvData,
             &pcbData);
  if ( ValueW == 2 )
    return 1;
  if ( ValueW )
  {
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\velocityutils.cpp",
      (const char *)ValueW,
      pdwType);
  }
  else if ( !pvData )
  {
    return 1;
  }
  if ( (unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent() )
  {
    v10 = 0;
    PolicyInt = PolicyManager_GetPolicyInt(L"Authentication", L"AllowSecondaryAuthenticationDevice", &v10);
    if ( PolicyInt < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\velocityutils.cpp",
        (const char *)(unsigned int)PolicyInt,
        pdwType);
    if ( v10 )
      return 1;
  }
  pvData = 0;
  pcbData = 4;
  v4 = RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\SecondaryAuthenticationFactor",
         L"AllowSecondaryAuthenticationDevice",
         0x10u,
         0,
         &pvData,
         &pcbData);
  if ( !v4 )
    return pvData != 0;
  if ( v4 != 2 )
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\velocityutils.cpp",
      (const char *)v4,
      pdwTypea);
  return 0;
}

```

## disassembly

```asm
0x18002d1cc  push    rbp
0x18002d1ce  mov     rbp, rsp
0x18002d1d1  sub     rsp, 40h
0x18002d1d5  lea     rax, [rbp+arg_8]
0x18002d1d9  mov     [rbp+arg_0], 1
0x18002d1e0  mov     [rsp+40h+pcbData], rax; pcbData
0x18002d1e5  lea     r8, aDisabled; "Disabled"
0x18002d1ec  lea     rax, [rbp+arg_0]
0x18002d1f0  mov     [rbp+arg_8], 4
0x18002d1f7  mov     [rsp+40h+pvData], rax; pvData
0x18002d1fc  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002d203  mov     r9d, 10h; dwFlags
0x18002d209  mov     [rsp+40h+pdwType], 0; int
0x18002d212  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002d219  call    cs:__imp_RegGetValueW
0x18002d21f  cmp     eax, 2
0x18002d222  jz      short loc_18002D22D
0x18002d224  test    eax, eax
0x18002d226  jnz     short loc_18002D235
0x18002d228  cmp     [rbp+arg_0], eax
0x18002d22b  jnz     short loc_18002D24D
0x18002d22d  mov     al, 1
0x18002d22f  add     rsp, 40h
0x18002d233  pop     rbp
0x18002d234  retn
0x18002d235  mov     rcx, [rbp+8]; this
0x18002d239  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18002d240  mov     r9d, eax; char *
0x18002d243  mov     edx, 37h ; '7'; void *
0x18002d248  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18002d24d  call    IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent
0x18002d252  test    al, al
0x18002d254  jz      short loc_18002D297
0x18002d256  lea     r8, [rbp+arg_10]
0x18002d25a  mov     [rbp+arg_10], 0
0x18002d261  lea     rdx, aAllowsecondary; "AllowSecondaryAuthenticationDevice"
0x18002d268  lea     rcx, aAuthentication; "Authentication"
0x18002d26f  call    cs:__imp_PolicyManager_GetPolicyInt
0x18002d275  test    eax, eax
0x18002d277  jns     short loc_18002D291
0x18002d279  mov     rcx, [rbp+8]; this
0x18002d27d  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18002d284  mov     r9d, eax; char *
0x18002d287  mov     edx, 41h ; 'A'; void *
0x18002d28c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002d291  cmp     [rbp+arg_10], 0
0x18002d295  jnz     short loc_18002D22D
0x18002d297  lea     rax, [rbp+arg_8]
0x18002d29b  mov     [rbp+arg_0], 0
0x18002d2a2  mov     [rsp+40h+pcbData], rax; pcbData
0x18002d2a7  lea     r8, aAllowsecondary; "AllowSecondaryAuthenticationDevice"
0x18002d2ae  lea     rax, [rbp+arg_0]
0x18002d2b2  mov     [rbp+arg_8], 4
0x18002d2b9  mov     [rsp+40h+pvData], rax; pvData
0x18002d2be  lea     rdx, aSoftwarePolici_2; "SOFTWARE\\Policies\\Microsoft\\Secondar"...
0x18002d2c5  mov     r9d, 10h; dwFlags
0x18002d2cb  mov     [rsp+40h+pdwType], 0; unsigned int
0x18002d2d4  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002d2db  call    cs:__imp_RegGetValueW
0x18002d2e1  test    eax, eax
0x18002d2e3  jnz     short loc_18002D2F0
0x18002d2e5  cmp     [rbp+arg_0], eax
0x18002d2e8  setnz   al
0x18002d2eb  jmp     loc_18002D22F
0x18002d2f0  cmp     eax, 2
0x18002d2f3  jz      short loc_18002D30D
0x18002d2f5  mov     rcx, [rbp+8]; this
0x18002d2f9  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18002d300  mov     r9d, eax; char *
0x18002d303  mov     edx, 5Dh ; ']'; void *
0x18002d308  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18002d30d  xor     al, al
0x18002d30f  jmp     loc_18002D22F
```
