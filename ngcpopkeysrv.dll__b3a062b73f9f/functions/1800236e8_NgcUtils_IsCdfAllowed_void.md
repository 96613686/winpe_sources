# NgcUtils::IsCdfAllowed(void)

- ea: `0x1800236e8`
- end: `0x180023830`
- name: `?IsCdfAllowed@NgcUtils@@YA_NXZ`
- size: `328`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023454`

## callees

- `0x180006514`
- `0x18001069c`
- `0x180022d28`
- `0x1800236e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023735`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800237f7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023735`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800237f7`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18002378b`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18002378b`

## string_xrefs

- `0x180023755`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x180023799`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x180023815`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`

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
  if ( (unsigned __int8)IsPolicyManager_GetPolicyIntPresent() )
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
0x1800236e8  push    rbp
0x1800236ea  mov     rbp, rsp
0x1800236ed  sub     rsp, 40h
0x1800236f1  lea     rax, [rbp+arg_8]
0x1800236f5  mov     [rbp+arg_0], 1
0x1800236fc  mov     [rsp+40h+pcbData], rax; pcbData
0x180023701  lea     r8, aDisabled; "Disabled"
0x180023708  lea     rax, [rbp+arg_0]
0x18002370c  mov     [rbp+arg_8], 4
0x180023713  mov     [rsp+40h+pvData], rax; pvData
0x180023718  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002371f  mov     r9d, 10h; dwFlags
0x180023725  mov     [rsp+40h+pdwType], 0; int
0x18002372e  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180023735  call    cs:__imp_RegGetValueW
0x18002373b  cmp     eax, 2
0x18002373e  jz      short loc_180023749
0x180023740  test    eax, eax
0x180023742  jnz     short loc_180023751
0x180023744  cmp     [rbp+arg_0], eax
0x180023747  jnz     short loc_180023769
0x180023749  mov     al, 1
0x18002374b  add     rsp, 40h
0x18002374f  pop     rbp
0x180023750  retn
0x180023751  mov     rcx, [rbp+8]; this
0x180023755  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18002375c  mov     r9d, eax; char *
0x18002375f  mov     edx, 37h ; '7'; void *
0x180023764  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180023769  call    IsPolicyManager_GetPolicyIntPresent
0x18002376e  test    al, al
0x180023770  jz      short loc_1800237B3
0x180023772  lea     r8, [rbp+arg_10]
0x180023776  mov     [rbp+arg_10], 0
0x18002377d  lea     rdx, aAllowsecondary; "AllowSecondaryAuthenticationDevice"
0x180023784  lea     rcx, aAuthentication; "Authentication"
0x18002378b  call    cs:__imp_PolicyManager_GetPolicyInt
0x180023791  test    eax, eax
0x180023793  jns     short loc_1800237AD
0x180023795  mov     rcx, [rbp+8]; this
0x180023799  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800237a0  mov     r9d, eax; char *
0x1800237a3  mov     edx, 41h ; 'A'; void *
0x1800237a8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800237ad  cmp     [rbp+arg_10], 0
0x1800237b1  jnz     short loc_180023749
0x1800237b3  lea     rax, [rbp+arg_8]
0x1800237b7  mov     [rbp+arg_0], 0
0x1800237be  mov     [rsp+40h+pcbData], rax; pcbData
0x1800237c3  lea     r8, aAllowsecondary; "AllowSecondaryAuthenticationDevice"
0x1800237ca  lea     rax, [rbp+arg_0]
0x1800237ce  mov     [rbp+arg_8], 4
0x1800237d5  mov     [rsp+40h+pvData], rax; pvData
0x1800237da  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Secondar"...
0x1800237e1  mov     r9d, 10h; dwFlags
0x1800237e7  mov     [rsp+40h+pdwType], 0; unsigned int
0x1800237f0  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800237f7  call    cs:__imp_RegGetValueW
0x1800237fd  test    eax, eax
0x1800237ff  jnz     short loc_18002380C
0x180023801  cmp     [rbp+arg_0], eax
0x180023804  setnz   al
0x180023807  jmp     loc_18002374B
0x18002380c  cmp     eax, 2
0x18002380f  jz      short loc_180023829
0x180023811  mov     rcx, [rbp+8]; this
0x180023815  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18002381c  mov     r9d, eax; char *
0x18002381f  mov     edx, 5Dh ; ']'; void *
0x180023824  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180023829  xor     al, al
0x18002382b  jmp     loc_18002374B
```
