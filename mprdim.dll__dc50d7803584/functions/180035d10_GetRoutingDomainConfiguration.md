# GetRoutingDomainConfiguration

- ea: `0x180035d10`
- end: `0x180035f15`
- name: `GetRoutingDomainConfiguration`
- size: `517`
- prototype: `__int64 __usercall@<rax>(struct _GUID *@<rcx>, __int64)`
- caller_count: `13`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180002690`
- `0x180002ddc`
- `0x180003f80`
- `0x180006fac`
- `0x1800091dc`
- `0x18000ad04`
- `0x18000eb60`
- `0x180010e38`
- `0x180013580`
- `0x180014244`
- `0x180016884`
- `0x180016b80`
- `0x18001d870`

## callees

- `0x180035d10`
- `0x18003d380`
- `0x18003d6bc`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## string_xrefs

- `0x180035dea`: `%s: The config store is not available.`
- `0x180035db4`: `GetRoutingDomainConfiguration`
- `0x180035ddf`: `GetRoutingDomainConfiguration`
- `0x180035e84`: `GetRoutingDomainConfiguration`
- `0x180035e92`: `%s: cfgStore->GetRoutingDomainConfiguration failed: %d.`

## pseudocode

```c
__int64 __fastcall GetRoutingDomainConfiguration(
        struct _GUID *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5)
{
  void (*v9)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  struct RRasConfigStore *Instance; // rax
  const struct _GUID *v11; // r9
  unsigned int v12; // ebx
  const struct _GUID *v13; // r9
  unsigned __int16 *v15; // [rsp+28h] [rbp-D8h]
  unsigned int v16; // [rsp+30h] [rbp-D0h]
  unsigned int RoutingDomainConfiguration; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v19; // [rsp+50h] [rbp-B0h]
  __int128 v20; // [rsp+60h] [rbp-A0h]
  __int64 v21; // [rsp+70h] [rbp-90h]
  int v22; // [rsp+78h] [rbp-88h]
  int v23; // [rsp+7Ch] [rbp-84h]
  GUID v24; // [rsp+80h] [rbp-80h] BYREF
  int v25; // [rsp+90h] [rbp-70h] BYREF
  __int128 v26; // [rsp+94h] [rbp-6Ch]
  __int128 v27; // [rsp+A4h] [rbp-5Ch]
  int v28; // [rsp+B4h] [rbp-4Ch]
  int v29; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v30[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  RoutingDomainConfiguration = 0;
  v29 = 0;
  memset_0(v30, 0, sizeof(v30));
  v22 = -1;
  v25 = 0;
  v26 = 0;
  v28 = 0;
  v27 = 0;
  v18 = 0;
  v19 = 0;
  v21 = 0;
  v20 = 0;
  v23 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v18,
      L"GetRoutingDomainConfiguration",
      &RoutingDomainConfiguration,
      v9,
      a1,
      v15,
      v16);
  Instance = RRasConfigStore::GetInstance();
  if ( Instance )
  {
    RoutingDomainConfiguration = RRasConfigStore::GetRoutingDomainConfiguration(Instance, a1, a2, a3, a4, a5);
    v12 = RoutingDomainConfiguration;
    if ( RoutingDomainConfiguration && (_QWORD)xmmword_1800710A0 )
    {
      LOWORD(v29) = 0;
      LOWORD(v25) = 0;
      v24 = GUID_NULL;
      FormatRRASErrorString(
        &v29,
        L"%s: cfgStore->GetRoutingDomainConfiguration failed: %d.",
        L"GetRoutingDomainConfiguration",
        RoutingDomainConfiguration);
      v13 = &v24;
      if ( a1 )
        v13 = a1;
      gCfgStoreParamTemplateFunc(
        gCfgStoreEtwContext,
        (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
        (const unsigned __int16 *)&v29,
        v13,
        0,
        (const unsigned __int16 *)&v25);
      v12 = RoutingDomainConfiguration;
    }
  }
  else
  {
    if ( (_QWORD)xmmword_1800710A0 )
    {
      LOWORD(v29) = 0;
      LOWORD(v25) = 0;
      v24 = GUID_NULL;
      FormatRRASErrorString(&v29, L"%s: The config store is not available.", L"GetRoutingDomainConfiguration");
      v11 = &v24;
      if ( a1 )
        v11 = a1;
      gCfgStoreParamTemplateFunc(
        gCfgStoreEtwContext,
        (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
        (const unsigned __int16 *)&v29,
        v11,
        0,
        (const unsigned __int16 *)&v25);
    }
    v12 = 1003;
    RoutingDomainConfiguration = 1003;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v18);
  return v12;
}

```

## disassembly

```asm
0x180035d10  push    rbp
0x180035d12  push    rbx
0x180035d13  push    rsi
0x180035d14  push    rdi
0x180035d15  push    r14
0x180035d17  push    r15
0x180035d19  lea     rbp, [rsp-7D8h]
0x180035d21  sub     rsp, 8D8h
0x180035d28  mov     rax, cs:__security_cookie
0x180035d2f  xor     rax, rsp
0x180035d32  mov     [rbp+800h+var_40], rax
0x180035d39  mov     r15, [rbp+800h+arg_20]
0x180035d40  mov     esi, r8d
0x180035d43  mov     ebx, edx
0x180035d45  mov     [rsp+900h+var_8C0], 0
0x180035d4d  mov     rdi, rcx
0x180035d50  xor     eax, eax
0x180035d52  xor     edx, edx; Val
0x180035d54  mov     [rbp+800h+var_840], eax
0x180035d57  mov     r8d, 7FCh; Size
0x180035d5d  lea     rcx, [rbp+800h+var_83C]; void *
0x180035d61  mov     r14, r9
0x180035d64  call    memset_0
0x180035d69  xor     eax, eax
0x180035d6b  mov     [rsp+900h+var_888], 0FFFFFFFFh
0x180035d73  cmp     qword ptr cs:xmmword_1800710A0+8, rax
0x180035d7a  xorps   xmm0, xmm0
0x180035d7d  xorps   xmm1, xmm1
0x180035d80  mov     [rbp+800h+var_870], eax
0x180035d83  movups  [rbp+800h+var_86C], xmm0
0x180035d87  mov     [rbp+800h+var_84C], eax
0x180035d8a  movups  [rbp+800h+var_85C], xmm0
0x180035d8e  mov     [rsp+900h+var_8B8], rax
0x180035d93  movdqu  [rsp+900h+var_8B0], xmm0
0x180035d99  mov     [rsp+900h+var_890], rax
0x180035d9e  movdqu  [rsp+900h+var_8A0], xmm1
0x180035da4  mov     [rsp+900h+var_884], eax
0x180035da8  jz      short loc_180035DC5
0x180035daa  lea     r8, [rsp+900h+var_8C0]; unsigned int *
0x180035daf  mov     [rsp+900h+var_8E0], rdi; struct _GUID *
0x180035db4  lea     rdx, aGetroutingdoma_2; "GetRoutingDomainConfiguration"
0x180035dbb  lea     rcx, [rsp+900h+var_8B8]; this
0x180035dc0  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180035dc5  call    ?GetInstance@RRasConfigStore@@SAPEAV1@XZ; RRasConfigStore::GetInstance(void)
0x180035dca  test    rax, rax
0x180035dcd  jnz     short loc_180035E4C
0x180035dcf  cmp     qword ptr cs:xmmword_1800710A0, rax
0x180035dd6  jz      short loc_180035E3E
0x180035dd8  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180035ddf  lea     r8, aGetroutingdoma_2; "GetRoutingDomainConfiguration"
0x180035de6  mov     word ptr [rbp+800h+var_840], ax
0x180035dea  lea     rdx, aSTheConfigStor_0; "%s: The config store is not available."
0x180035df1  mov     word ptr [rbp+800h+var_870], ax
0x180035df5  lea     rcx, [rbp+800h+var_840]
0x180035df9  movdqu  [rbp+800h+var_880], xmm0
0x180035dfe  call    FormatRRASErrorString
0x180035e03  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180035e0a  lea     rax, [rbp+800h+var_870]
0x180035e0e  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180035e15  lea     r9, [rbp+800h+var_880]
0x180035e19  mov     [rsp+900h+var_8D8], rax
0x180035e1e  lea     r8, [rbp+800h+var_840]
0x180035e22  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180035e29  test    rdi, rdi
0x180035e2c  mov     [rsp+900h+var_8E0], 0
0x180035e35  cmovnz  r9, rdi
0x180035e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035e3e  mov     ebx, 3EBh
0x180035e43  mov     [rsp+900h+var_8C0], ebx
0x180035e47  jmp     loc_180035EEA
0x180035e4c  mov     [rsp+900h+var_8D8], r15
0x180035e51  mov     r9d, esi
0x180035e54  mov     r8d, ebx
0x180035e57  mov     [rsp+900h+var_8E0], r14
0x180035e5c  mov     rdx, rdi
0x180035e5f  mov     rcx, rax
0x180035e62  call    ?GetRoutingDomainConfiguration@RRasConfigStore@@QEAAKPEAU_GUID@@W4_RRAS_RD_CONFIG_TYPE@@HPEAKPEAX@Z; RRasConfigStore::GetRoutingDomainConfiguration(_GUID *,_RRAS_RD_CONFIG_TYPE,int,ulong *,void *)
0x180035e67  mov     [rsp+900h+var_8C0], eax
0x180035e6b  mov     ebx, eax
0x180035e6d  test    eax, eax
0x180035e6f  jz      short loc_180035EEA
0x180035e71  cmp     qword ptr cs:xmmword_1800710A0, 0
0x180035e79  jz      short loc_180035EEA
0x180035e7b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180035e82  xor     eax, eax
0x180035e84  lea     r8, aGetroutingdoma_2; "GetRoutingDomainConfiguration"
0x180035e8b  mov     r9d, ebx
0x180035e8e  mov     word ptr [rbp+800h+var_840], ax
0x180035e92  lea     rdx, aSCfgstoreGetro_1; "%s: cfgStore->GetRoutingDomainConfigura"...
0x180035e99  mov     word ptr [rbp+800h+var_870], ax
0x180035e9d  lea     rcx, [rbp+800h+var_840]
0x180035ea1  movdqu  [rbp+800h+var_880], xmm0
0x180035ea6  call    FormatRRASErrorString
0x180035eab  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180035eb2  lea     rax, [rbp+800h+var_870]
0x180035eb6  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180035ebd  lea     r9, [rbp+800h+var_880]
0x180035ec1  mov     [rsp+900h+var_8D8], rax
0x180035ec6  lea     r8, [rbp+800h+var_840]
0x180035eca  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180035ed1  test    rdi, rdi
0x180035ed4  mov     [rsp+900h+var_8E0], 0
0x180035edd  cmovnz  r9, rdi
0x180035ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ee6  mov     ebx, [rsp+900h+var_8C0]
0x180035eea  lea     rcx, [rsp+900h+var_8B8]; this
0x180035eef  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180035ef4  mov     eax, ebx
0x180035ef6  mov     rcx, [rbp+800h+var_40]
0x180035efd  xor     rcx, rsp; StackCookie
0x180035f00  call    __security_check_cookie
0x180035f05  add     rsp, 8D8h
0x180035f0c  pop     r15
0x180035f0e  pop     r14
0x180035f10  pop     rdi
0x180035f11  pop     rsi
0x180035f12  pop     rbx
0x180035f13  pop     rbp
0x180035f14  retn
```
