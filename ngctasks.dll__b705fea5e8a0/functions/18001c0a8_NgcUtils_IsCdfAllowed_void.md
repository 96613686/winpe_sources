# NgcUtils::IsCdfAllowed(void)

- ea: `0x18001c0a8`
- end: `0x18001c1f0`
- name: `?IsCdfAllowed@NgcUtils@@YA_NXZ`
- size: `328`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001bdbc`

## callees

- `0x18000714c`
- `0x18000ebc0`
- `0x180018d20`
- `0x18001c0a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c0f5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c1b7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c0f5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c1b7`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18001c14b`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18001c14b`

## string_xrefs

- `0x18001c115`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x18001c159`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x18001c1d5`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
        (int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\velocityutils.cpp",
        (const char *)(unsigned int)PolicyInt);
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
0x18001c0a8  push    rbp
0x18001c0aa  mov     rbp, rsp
0x18001c0ad  sub     rsp, 40h
0x18001c0b1  lea     rax, [rbp+arg_8]
0x18001c0b5  mov     [rbp+arg_0], 1
0x18001c0bc  mov     [rsp+40h+pcbData], rax; pcbData
0x18001c0c1  lea     r8, aDisabled; "Disabled"
0x18001c0c8  lea     rax, [rbp+arg_0]
0x18001c0cc  mov     [rbp+arg_8], 4
0x18001c0d3  mov     [rsp+40h+pvData], rax; pvData
0x18001c0d8  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001c0df  mov     r9d, 10h; dwFlags
0x18001c0e5  mov     [rsp+40h+pdwType], 0; int
0x18001c0ee  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001c0f5  call    cs:__imp_RegGetValueW
0x18001c0fb  cmp     eax, 2
0x18001c0fe  jz      short loc_18001C109
0x18001c100  test    eax, eax
0x18001c102  jnz     short loc_18001C111
0x18001c104  cmp     [rbp+arg_0], eax
0x18001c107  jnz     short loc_18001C129
0x18001c109  mov     al, 1
0x18001c10b  add     rsp, 40h
0x18001c10f  pop     rbp
0x18001c110  retn
0x18001c111  mov     rcx, [rbp+8]; this
0x18001c115  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001c11c  mov     r9d, eax; char *
0x18001c11f  mov     edx, 37h ; '7'; void *
0x18001c124  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18001c129  call    IsPolicyManager_GetPolicyIntPresent
0x18001c12e  test    al, al
0x18001c130  jz      short loc_18001C173
0x18001c132  lea     r8, [rbp+arg_10]
0x18001c136  mov     [rbp+arg_10], 0
0x18001c13d  lea     rdx, aAllowsecondary; "AllowSecondaryAuthenticationDevice"
0x18001c144  lea     rcx, aAuthentication; "Authentication"
0x18001c14b  call    cs:__imp_PolicyManager_GetPolicyInt
0x18001c151  test    eax, eax
0x18001c153  jns     short loc_18001C16D
0x18001c155  mov     rcx, [rbp+8]; this
0x18001c159  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001c160  mov     r9d, eax; char *
0x18001c163  mov     edx, 41h ; 'A'; void *
0x18001c168  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c16d  cmp     [rbp+arg_10], 0
0x18001c171  jnz     short loc_18001C109
0x18001c173  lea     rax, [rbp+arg_8]
0x18001c177  mov     [rbp+arg_0], 0
0x18001c17e  mov     [rsp+40h+pcbData], rax; pcbData
0x18001c183  lea     r8, aAllowsecondary; "AllowSecondaryAuthenticationDevice"
0x18001c18a  lea     rax, [rbp+arg_0]
0x18001c18e  mov     [rbp+arg_8], 4
0x18001c195  mov     [rsp+40h+pvData], rax; pvData
0x18001c19a  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Secondar"...
0x18001c1a1  mov     r9d, 10h; dwFlags
0x18001c1a7  mov     [rsp+40h+pdwType], 0; unsigned int
0x18001c1b0  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001c1b7  call    cs:__imp_RegGetValueW
0x18001c1bd  test    eax, eax
0x18001c1bf  jnz     short loc_18001C1CC
0x18001c1c1  cmp     [rbp+arg_0], eax
0x18001c1c4  setnz   al
0x18001c1c7  jmp     loc_18001C10B
0x18001c1cc  cmp     eax, 2
0x18001c1cf  jz      short loc_18001C1E9
0x18001c1d1  mov     rcx, [rbp+8]; this
0x18001c1d5  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001c1dc  mov     r9d, eax; char *
0x18001c1df  mov     edx, 5Dh ; ']'; void *
0x18001c1e4  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18001c1e9  xor     al, al
0x18001c1eb  jmp     loc_18001C10B
```
