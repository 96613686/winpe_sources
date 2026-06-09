# RRasRoutingDomainConfig::CopyIkev2Config(_IKEV2_TUNNEL_CONFIG_PARAMS_4 *)

- ea: `0x180039b4c`
- end: `0x180039cd2`
- name: `?CopyIkev2Config@RRasRoutingDomainConfig@@AEAAKPEAU_IKEV2_TUNNEL_CONFIG_PARAMS_4@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180038f98`
- `0x18003c810`

## callees

- `0x180032e84`
- `0x180039b4c`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180039bd1`
- `ADVAPI32!RegOpenKeyExW` at `0x180039bd1`
- `ADVAPI32!RegCloseKey` at `0x180039c9d`
- `ADVAPI32!RegCloseKey` at `0x180039c9d`

## string_xrefs

- `0x180039c2d`: `RRasRoutingDomainConfig::CopyIkev2Config`
- `0x180039beb`: `%s: Failed to open ikev2 config reg key. error %d`
- `0x180039c1d`: `%s: GetIkev2ConfigParams: Failed. error %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RRasRoutingDomainConfig::CopyIkev2Config(
        RRasRoutingDomainConfig *this,
        struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *a2)
{
  HKEY v3; // rcx
  unsigned int Ikev2ConfigParams; // ebx
  const wchar_t *v5; // rdx
  const struct _GUID *v6; // r9
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  GUID v9; // [rsp+48h] [rbp-B8h] BYREF
  int v10; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v11; // [rsp+5Ch] [rbp-A4h]
  __int128 v12; // [rsp+6Ch] [rbp-94h]
  int v13; // [rsp+7Ch] [rbp-84h]
  int v14; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v15[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  hKey = 0;
  v14 = 0;
  memset_0(v15, 0, sizeof(v15));
  v3 = (HKEY)*((_QWORD *)this + 103);
  v10 = 0;
  v13 = 0;
  v11 = 0;
  v12 = 0;
  Ikev2ConfigParams = RegOpenKeyExW(v3, L"IKEv2", 0, 0x20019u, &hKey);
  if ( Ikev2ConfigParams )
  {
    if ( !(_QWORD)xmmword_1800710A0 )
      goto LABEL_10;
    v5 = L"%s: Failed to open ikev2 config reg key. error %d";
  }
  else
  {
    Ikev2ConfigParams = GetIkev2ConfigParams(hKey);
    if ( !Ikev2ConfigParams || !(_QWORD)xmmword_1800710A0 )
      goto LABEL_10;
    v5 = L"%s: GetIkev2ConfigParams: Failed. error %d";
  }
  LOWORD(v14) = 0;
  LOWORD(v10) = 0;
  v9 = GUID_NULL;
  FormatRRASErrorString(&v14, v5, L"RRasRoutingDomainConfig::CopyIkev2Config", Ikev2ConfigParams);
  v6 = &v9;
  if ( this != (RRasRoutingDomainConfig *)-516LL )
    v6 = (const struct _GUID *)((char *)this + 516);
  gCfgStoreParamTemplateFunc(
    gCfgStoreEtwContext,
    (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
    (const unsigned __int16 *)&v14,
    v6,
    0,
    (const unsigned __int16 *)&v10);
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
  if ( Ikev2ConfigParams == 2 )
    return 1168;
  return Ikev2ConfigParams;
}

```

## disassembly

```asm
0x180039b4c  mov     [rsp-8+arg_10], rbx
0x180039b51  push    rbp
0x180039b52  push    rsi
0x180039b53  push    rdi
0x180039b54  lea     rbp, [rsp-790h]
0x180039b5c  sub     rsp, 890h
0x180039b63  mov     rax, cs:__security_cookie
0x180039b6a  xor     rax, rsp
0x180039b6d  mov     [rbp+7A0h+var_20], rax
0x180039b74  mov     rdi, rdx
0x180039b77  mov     [rsp+8A0h+hKey], 0
0x180039b80  mov     rsi, rcx
0x180039b83  xor     eax, eax
0x180039b85  xor     edx, edx; Val
0x180039b87  mov     [rbp+7A0h+var_820], eax
0x180039b8a  lea     rcx, [rbp+7A0h+var_81C]; void *
0x180039b8e  mov     r8d, 7FCh; Size
0x180039b94  call    memset_0
0x180039b99  mov     rcx, [rsi+338h]; hKey
0x180039ba0  lea     rdx, aIkev2; "IKEv2"
0x180039ba7  xor     eax, eax
0x180039ba9  xorps   xmm0, xmm0
0x180039bac  mov     [rsp+8A0h+var_848], eax
0x180039bb0  mov     r9d, 20019h; samDesired
0x180039bb6  mov     [rsp+8A0h+var_824], eax
0x180039bba  xor     r8d, r8d; ulOptions
0x180039bbd  lea     rax, [rsp+8A0h+hKey]
0x180039bc2  mov     [rsp+8A0h+phkResult], rax; phkResult
0x180039bc7  movups  [rsp+8A0h+var_844], xmm0
0x180039bcc  movups  [rsp+8A0h+var_834], xmm0
0x180039bd1  call    cs:__imp_RegOpenKeyExW
0x180039bd7  mov     ebx, eax
0x180039bd9  test    eax, eax
0x180039bdb  jz      short loc_180039BF4
0x180039bdd  cmp     qword ptr cs:xmmword_1800710A0, 0
0x180039be5  jz      loc_180039C93
0x180039beb  lea     rdx, aSFailedToOpenI; "%s: Failed to open ikev2 config reg key"...
0x180039bf2  jmp     short loc_180039C24
0x180039bf4  mov     rcx, [rsp+8A0h+hKey]; hkey
0x180039bf9  mov     r9d, 68h ; 'h'
0x180039bff  mov     r8, rdi
0x180039c02  mov     dl, 5
0x180039c04  call    GetIkev2ConfigParams
0x180039c09  mov     ebx, eax
0x180039c0b  test    eax, eax
0x180039c0d  jz      loc_180039C93
0x180039c13  cmp     qword ptr cs:xmmword_1800710A0, 0
0x180039c1b  jz      short loc_180039C93
0x180039c1d  lea     rdx, aSGetikev2confi; "%s: GetIkev2ConfigParams: Failed. error"...
0x180039c24  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180039c2b  xor     eax, eax
0x180039c2d  lea     r8, aRrasroutingdom_10; "RRasRoutingDomainConfig::CopyIkev2Confi"...
0x180039c34  mov     r9d, ebx
0x180039c37  mov     word ptr [rbp+7A0h+var_820], ax
0x180039c3b  lea     rcx, [rbp+7A0h+var_820]
0x180039c3f  mov     word ptr [rsp+8A0h+var_848], ax
0x180039c44  movdqu  [rsp+8A0h+var_858], xmm0
0x180039c4a  call    FormatRRASErrorString
0x180039c4f  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180039c56  lea     rcx, [rsi+204h]
0x180039c5d  test    rcx, rcx
0x180039c60  lea     rax, [rsp+8A0h+var_848]
0x180039c65  mov     [rsp+8A0h+var_878], rax
0x180039c6a  lea     r9, [rsp+8A0h+var_858]
0x180039c6f  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180039c76  lea     r8, [rbp+7A0h+var_820]
0x180039c7a  cmovnz  r9, rcx
0x180039c7e  mov     [rsp+8A0h+phkResult], 0
0x180039c87  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180039c8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c93  mov     rcx, [rsp+8A0h+hKey]; hKey
0x180039c98  test    rcx, rcx
0x180039c9b  jz      short loc_180039CA3
0x180039c9d  call    cs:__imp_RegCloseKey
0x180039ca3  mov     eax, 490h
0x180039ca8  cmp     ebx, 2
0x180039cab  cmovz   ebx, eax
0x180039cae  mov     eax, ebx
0x180039cb0  mov     rcx, [rbp+7A0h+var_20]
0x180039cb7  xor     rcx, rsp; StackCookie
0x180039cba  call    __security_check_cookie
0x180039cbf  mov     rbx, [rsp+8A0h+arg_10]
0x180039cc7  add     rsp, 890h
0x180039cce  pop     rdi
0x180039ccf  pop     rsi
0x180039cd0  pop     rbp
0x180039cd1  retn
```
