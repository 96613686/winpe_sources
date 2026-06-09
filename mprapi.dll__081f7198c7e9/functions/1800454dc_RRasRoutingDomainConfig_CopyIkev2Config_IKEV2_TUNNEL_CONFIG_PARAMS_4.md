# RRasRoutingDomainConfig::CopyIkev2Config(_IKEV2_TUNNEL_CONFIG_PARAMS_4 *)

- ea: `0x1800454dc`
- end: `0x180045662`
- name: `?CopyIkev2Config@RRasRoutingDomainConfig@@AEAAKPEAU_IKEV2_TUNNEL_CONFIG_PARAMS_4@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180044888`
- `0x180047ff4`

## callees

- `0x18002efac`
- `0x1800454dc`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004562d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004562d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045561`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045561`

## string_xrefs

- `0x1800455bd`: `RRasRoutingDomainConfig::CopyIkev2Config`
- `0x18004557b`: `%s: Failed to open ikev2 config reg key. error %d`
- `0x1800455ad`: `%s: GetIkev2ConfigParams: Failed. error %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
    if ( !(_QWORD)xmmword_180078C60 )
      goto LABEL_10;
    v5 = L"%s: Failed to open ikev2 config reg key. error %d";
  }
  else
  {
    Ikev2ConfigParams = GetIkev2ConfigParams(hKey);
    if ( !Ikev2ConfigParams || !(_QWORD)xmmword_180078C60 )
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
    (const struct _EVENT_DESCRIPTOR *)xmmword_180078C60,
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
0x1800454dc  mov     [rsp-8+arg_10], rbx
0x1800454e1  push    rbp
0x1800454e2  push    rsi
0x1800454e3  push    rdi
0x1800454e4  lea     rbp, [rsp-790h]
0x1800454ec  sub     rsp, 890h
0x1800454f3  mov     rax, cs:__security_cookie
0x1800454fa  xor     rax, rsp
0x1800454fd  mov     [rbp+7A0h+var_20], rax
0x180045504  mov     rdi, rdx
0x180045507  mov     [rsp+8A0h+hKey], 0
0x180045510  mov     rsi, rcx
0x180045513  xor     eax, eax
0x180045515  xor     edx, edx; Val
0x180045517  mov     [rbp+7A0h+var_820], eax
0x18004551a  lea     rcx, [rbp+7A0h+var_81C]; void *
0x18004551e  mov     r8d, 7FCh; Size
0x180045524  call    memset_0
0x180045529  mov     rcx, [rsi+338h]; hKey
0x180045530  lea     rdx, aIkev2; "IKEv2"
0x180045537  xor     eax, eax
0x180045539  xorps   xmm0, xmm0
0x18004553c  mov     [rsp+8A0h+var_848], eax
0x180045540  mov     r9d, 20019h; samDesired
0x180045546  mov     [rsp+8A0h+var_824], eax
0x18004554a  xor     r8d, r8d; ulOptions
0x18004554d  lea     rax, [rsp+8A0h+hKey]
0x180045552  mov     [rsp+8A0h+phkResult], rax; phkResult
0x180045557  movups  [rsp+8A0h+var_844], xmm0
0x18004555c  movups  [rsp+8A0h+var_834], xmm0
0x180045561  call    cs:__imp_RegOpenKeyExW
0x180045567  mov     ebx, eax
0x180045569  test    eax, eax
0x18004556b  jz      short loc_180045584
0x18004556d  cmp     qword ptr cs:xmmword_180078C60, 0
0x180045575  jz      loc_180045623
0x18004557b  lea     rdx, aSFailedToOpenI; "%s: Failed to open ikev2 config reg key"...
0x180045582  jmp     short loc_1800455B4
0x180045584  mov     rcx, [rsp+8A0h+hKey]; hkey
0x180045589  mov     r9d, 68h ; 'h'
0x18004558f  mov     r8, rdi
0x180045592  mov     dl, 5
0x180045594  call    GetIkev2ConfigParams
0x180045599  mov     ebx, eax
0x18004559b  test    eax, eax
0x18004559d  jz      loc_180045623
0x1800455a3  cmp     qword ptr cs:xmmword_180078C60, 0
0x1800455ab  jz      short loc_180045623
0x1800455ad  lea     rdx, aSGetikev2confi; "%s: GetIkev2ConfigParams: Failed. error"...
0x1800455b4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800455bb  xor     eax, eax
0x1800455bd  lea     r8, aRrasroutingdom_10; "RRasRoutingDomainConfig::CopyIkev2Confi"...
0x1800455c4  mov     r9d, ebx
0x1800455c7  mov     word ptr [rbp+7A0h+var_820], ax
0x1800455cb  lea     rcx, [rbp+7A0h+var_820]
0x1800455cf  mov     word ptr [rsp+8A0h+var_848], ax
0x1800455d4  movdqu  [rsp+8A0h+var_858], xmm0
0x1800455da  call    FormatRRASErrorString
0x1800455df  mov     rdx, qword ptr cs:xmmword_180078C60
0x1800455e6  lea     rcx, [rsi+204h]
0x1800455ed  test    rcx, rcx
0x1800455f0  lea     rax, [rsp+8A0h+var_848]
0x1800455f5  mov     [rsp+8A0h+var_878], rax
0x1800455fa  lea     r9, [rsp+8A0h+var_858]
0x1800455ff  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180045606  lea     r8, [rbp+7A0h+var_820]
0x18004560a  cmovnz  r9, rcx
0x18004560e  mov     [rsp+8A0h+phkResult], 0
0x180045617  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004561e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045623  mov     rcx, [rsp+8A0h+hKey]; hKey
0x180045628  test    rcx, rcx
0x18004562b  jz      short loc_180045633
0x18004562d  call    cs:__imp_RegCloseKey
0x180045633  mov     eax, 490h
0x180045638  cmp     ebx, 2
0x18004563b  cmovz   ebx, eax
0x18004563e  mov     eax, ebx
0x180045640  mov     rcx, [rbp+7A0h+var_20]
0x180045647  xor     rcx, rsp; StackCookie
0x18004564a  call    __security_check_cookie
0x18004564f  mov     rbx, [rsp+8A0h+arg_10]
0x180045657  add     rsp, 890h
0x18004565e  pop     rdi
0x18004565f  pop     rsi
0x180045660  pop     rbp
0x180045661  retn
```
