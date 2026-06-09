# RRasRoutingDomainConfig::UpdateCompartmentIdAndName(void)

- ea: `0x1800421f4`
- end: `0x180042392`
- name: `?UpdateCompartmentIdAndName@RRasRoutingDomainConfig@@QEAAKXZ`
- size: `414`
- prototype: `unsigned int __fastcall(RRasRoutingDomainConfig *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180038828`
- `0x180040eb0`

## callees

- `0x1800421f4`
- `0x180045430`
- `0x180045748`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## string_xrefs

- `0x18004229b`: `RRasRoutingDomainConfig::UpdateCompartmentIdAndName`
- `0x1800422fc`: `RRasRoutingDomainConfig::UpdateCompartmentIdAndName`
- `0x180042281`: `%s: NsiGetCompartmentIdForRoutingDomain failed while finding compartment Id for routing domain.`
- `0x1800422d4`: `%s: NsiGetRoutingDomainNameFromCompartmentId failed while finding friendly name for routing domain.`
- `0x180042307`: `%s: Friendly name : %ws , compartment Id : %d`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::UpdateCompartmentIdAndName(RRasRoutingDomainConfig *this)
{
  unsigned int *v2; // r14
  unsigned int CompartmentIdForRoutingDomain; // eax
  __int64 v4; // rdx
  unsigned int RoutingDomainNameFromCompartmentId; // ebx
  const wchar_t *v6; // rdx
  __int64 v7; // r9
  int v8; // eax
  const struct _GUID *v9; // r9
  GUID v11; // [rsp+40h] [rbp-C0h] BYREF
  int v12; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v13; // [rsp+54h] [rbp-ACh]
  __int128 v14; // [rsp+64h] [rbp-9Ch]
  int v15; // [rsp+74h] [rbp-8Ch]
  int v16; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v17[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  v12 = 0;
  v2 = (unsigned int *)((char *)this + 540);
  v15 = 0;
  v13 = 0;
  v14 = 0;
  CompartmentIdForRoutingDomain = NsiGetCompartmentIdForRoutingDomain((char *)this + 516, (char *)this + 540);
  RoutingDomainNameFromCompartmentId = CompartmentIdForRoutingDomain;
  if ( CompartmentIdForRoutingDomain )
  {
    if ( !(_QWORD)xmmword_1800710A0 )
      return RoutingDomainNameFromCompartmentId;
    v6 = L"%s: NsiGetCompartmentIdForRoutingDomain failed while finding compartment Id for routing domain.";
    LOWORD(v16) = 0;
    v7 = CompartmentIdForRoutingDomain;
    LOWORD(v12) = 0;
  }
  else
  {
    RoutingDomainNameFromCompartmentId = NsiGetRoutingDomainNameFromCompartmentId(*v2, v4, this);
    if ( !RoutingDomainNameFromCompartmentId )
    {
      if ( !(_QWORD)xmmword_1800710A0 )
        return RoutingDomainNameFromCompartmentId;
      LOWORD(v16) = 0;
      LOWORD(v12) = 0;
      v8 = *v2;
      v11 = GUID_NULL;
      FormatRRASErrorString(
        &v16,
        L"%s: Friendly name : %ws , compartment Id : %d",
        L"RRasRoutingDomainConfig::UpdateCompartmentIdAndName",
        this,
        v8);
      goto LABEL_10;
    }
    if ( !(_QWORD)xmmword_1800710A0 )
      return RoutingDomainNameFromCompartmentId;
    v6 = L"%s: NsiGetRoutingDomainNameFromCompartmentId failed while finding friendly name for routing domain.";
    LOWORD(v16) = 0;
    v7 = RoutingDomainNameFromCompartmentId;
    LOWORD(v12) = 0;
  }
  v11 = GUID_NULL;
  FormatRRASErrorString(&v16, v6, L"RRasRoutingDomainConfig::UpdateCompartmentIdAndName", v7);
LABEL_10:
  v9 = &v11;
  if ( this != (RRasRoutingDomainConfig *)-516LL )
    v9 = (const struct _GUID *)((char *)this + 516);
  gCfgStoreParamTemplateFunc(
    gCfgStoreEtwContext,
    (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
    (const unsigned __int16 *)&v16,
    v9,
    0,
    (const unsigned __int16 *)&v12);
  return RoutingDomainNameFromCompartmentId;
}

```

## disassembly

```asm
0x1800421f4  mov     [rsp-8+arg_8], rbx
0x1800421f9  mov     [rsp-8+arg_10], rsi
0x1800421fe  push    rbp
0x1800421ff  push    rdi
0x180042200  push    r14
0x180042202  lea     rbp, [rsp-790h]
0x18004220a  sub     rsp, 890h
0x180042211  mov     rax, cs:__security_cookie
0x180042218  xor     rax, rsp
0x18004221b  mov     [rbp+7A0h+var_20], rax
0x180042222  mov     rdi, rcx
0x180042225  xor     eax, eax
0x180042227  lea     rcx, [rbp+7A0h+var_81C]; void *
0x18004222b  mov     [rbp+7A0h+var_820], eax
0x18004222e  xor     edx, edx; Val
0x180042230  mov     r8d, 7FCh; Size
0x180042236  call    memset_0
0x18004223b  xor     eax, eax
0x18004223d  lea     rsi, [rdi+204h]
0x180042244  xorps   xmm0, xmm0
0x180042247  mov     [rsp+8A0h+var_850], eax
0x18004224b  lea     r14, [rdi+21Ch]
0x180042252  mov     [rsp+8A0h+var_82C], eax
0x180042256  mov     rdx, r14
0x180042259  mov     rcx, rsi
0x18004225c  movups  [rsp+8A0h+var_84C], xmm0
0x180042261  movups  [rsp+8A0h+var_83C], xmm0
0x180042266  call    NsiGetCompartmentIdForRoutingDomain
0x18004226b  mov     ebx, eax
0x18004226d  test    eax, eax
0x18004226f  jz      short loc_1800422B3
0x180042271  cmp     qword ptr cs:xmmword_1800710A0, 0
0x180042279  jz      loc_180042369
0x18004227f  xor     ecx, ecx
0x180042281  lea     rdx, aSNsigetcompart; "%s: NsiGetCompartmentIdForRoutingDomain"...
0x180042288  mov     word ptr [rbp+7A0h+var_820], cx
0x18004228c  mov     r9d, eax
0x18004228f  mov     word ptr [rsp+8A0h+var_850], cx
0x180042294  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004229b  lea     r8, aRrasroutingdom_28; "RRasRoutingDomainConfig::UpdateCompartm"...
0x1800422a2  lea     rcx, [rbp+7A0h+var_820]
0x1800422a6  movdqu  [rsp+8A0h+var_860], xmm0
0x1800422ac  call    FormatRRASErrorString
0x1800422b1  jmp     short loc_18004232C
0x1800422b3  mov     ecx, [r14]
0x1800422b6  mov     r8, rdi
0x1800422b9  call    NsiGetRoutingDomainNameFromCompartmentId
0x1800422be  mov     ebx, eax
0x1800422c0  test    eax, eax
0x1800422c2  jz      short loc_1800422E9
0x1800422c4  cmp     qword ptr cs:xmmword_1800710A0, 0
0x1800422cc  jz      loc_180042369
0x1800422d2  xor     eax, eax
0x1800422d4  lea     rdx, aSNsigetrouting; "%s: NsiGetRoutingDomainNameFromCompartm"...
0x1800422db  mov     word ptr [rbp+7A0h+var_820], ax
0x1800422df  mov     r9d, ebx
0x1800422e2  mov     word ptr [rsp+8A0h+var_850], ax
0x1800422e7  jmp     short loc_180042294
0x1800422e9  cmp     qword ptr cs:xmmword_1800710A0, 0
0x1800422f1  jz      short loc_180042369
0x1800422f3  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800422fa  xor     eax, eax
0x1800422fc  lea     r8, aRrasroutingdom_28; "RRasRoutingDomainConfig::UpdateCompartm"...
0x180042303  mov     word ptr [rbp+7A0h+var_820], ax
0x180042307  lea     rdx, aSFriendlyNameW; "%s: Friendly name : %ws , compartment I"...
0x18004230e  mov     word ptr [rsp+8A0h+var_850], ax
0x180042313  lea     rcx, [rbp+7A0h+var_820]
0x180042317  mov     eax, [r14]
0x18004231a  mov     r9, rdi
0x18004231d  movdqu  [rsp+8A0h+var_860], xmm0
0x180042323  mov     dword ptr [rsp+8A0h+var_880], eax
0x180042327  call    FormatRRASErrorString
0x18004232c  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180042333  lea     rax, [rsp+8A0h+var_850]
0x180042338  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004233f  lea     r9, [rsp+8A0h+var_860]
0x180042344  mov     [rsp+8A0h+var_878], rax
0x180042349  lea     r8, [rbp+7A0h+var_820]
0x18004234d  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180042354  test    rsi, rsi
0x180042357  mov     [rsp+8A0h+var_880], 0
0x180042360  cmovnz  r9, rsi
0x180042364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042369  mov     eax, ebx
0x18004236b  mov     rcx, [rbp+7A0h+var_20]
0x180042372  xor     rcx, rsp; StackCookie
0x180042375  call    __security_check_cookie
0x18004237a  lea     r11, [rsp+8A0h+var_10]
0x180042382  mov     rbx, [r11+28h]
0x180042386  mov     rsi, [r11+30h]
0x18004238a  mov     rsp, r11
0x18004238d  pop     r14
0x18004238f  pop     rdi
0x180042390  pop     rbp
0x180042391  retn
```
