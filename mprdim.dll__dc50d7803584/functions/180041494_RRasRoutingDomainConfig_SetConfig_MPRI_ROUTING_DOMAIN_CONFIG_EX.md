# RRasRoutingDomainConfig::SetConfig(_MPRI_ROUTING_DOMAIN_CONFIG_EX *)

- ea: `0x180041494`
- end: `0x1800416f4`
- name: `?SetConfig@RRasRoutingDomainConfig@@QEAAKPEAU_MPRI_ROUTING_DOMAIN_CONFIG_EX@@@Z`
- size: `608`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *, __int64, void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x180041ca4`

## callees

- `0x180041494`
- `0x180042398`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## string_xrefs

- `0x180041519`: `RRasRoutingDomainConfig::SetConfig`
- `0x1800415d7`: `RRasRoutingDomainConfig::SetConfig`
- `0x180041670`: `RRasRoutingDomainConfig::SetConfig`
- `0x180041576`: `RRasRoutingDomainConfig::SetConfig`
- `0x180041677`: `%s: UpdateConfigEx1Data failed: %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RRasRoutingDomainConfig::SetConfig(
        RRasRoutingDomainConfig *this,
        struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *a2,
        __int64 a3,
        void (*a4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))
{
  GUID *v6; // rdi
  unsigned int updated; // ebx
  GUID *v8; // r9
  GUID *v9; // r9
  unsigned __int16 *v11; // [rsp+28h] [rbp-D8h]
  unsigned int v12; // [rsp+30h] [rbp-D0h]
  unsigned int v13; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v15; // [rsp+50h] [rbp-B0h]
  __int128 v16; // [rsp+60h] [rbp-A0h]
  __int64 v17; // [rsp+70h] [rbp-90h]
  int v18; // [rsp+78h] [rbp-88h]
  int v19; // [rsp+7Ch] [rbp-84h]
  GUID v20; // [rsp+80h] [rbp-80h] BYREF
  int v21; // [rsp+90h] [rbp-70h] BYREF
  __int128 v22; // [rsp+94h] [rbp-6Ch]
  __int128 v23; // [rsp+A4h] [rbp-5Ch]
  int v24; // [rsp+B4h] [rbp-4Ch]
  int v25; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v26[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v13 = 0;
  v15 = 0;
  v14 = 0;
  v16 = 0;
  v17 = 0;
  v18 = -1;
  v19 = 0;
  v6 = (GUID *)((char *)this + 516);
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v14,
      L"RRasRoutingDomainConfig::SetConfig",
      &v13,
      a4,
      (struct _GUID *)((char *)this + 516),
      v11,
      v12);
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  if ( a2 )
  {
    if ( *(_BYTE *)a2 == 1 )
    {
      updated = RRasRoutingDomainConfig::UpdateConfigEx1Data(
                  this,
                  (struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *)((char *)a2 + 8));
      v13 = updated;
      if ( updated && (_QWORD)xmmword_1800710A0 )
      {
        LOWORD(v25) = 0;
        v20 = GUID_NULL;
        LOWORD(v21) = 0;
        FormatRRASErrorString(
          &v25,
          L"%s: UpdateConfigEx1Data failed: %d.",
          L"RRasRoutingDomainConfig::SetConfig",
          updated);
        v9 = &v20;
        if ( v6 )
          v9 = v6;
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_1800710A0,
          &v25,
          v9,
          0,
          &v21);
        goto LABEL_17;
      }
    }
    else
    {
      if ( (_QWORD)xmmword_1800710A0 )
      {
        LOWORD(v25) = 0;
        v20 = GUID_NULL;
        LOWORD(v21) = 0;
        FormatRRASErrorString(&v25, L"%s: Un-supported revision (%d).", L"RRasRoutingDomainConfig::SetConfig");
        v8 = &v20;
        if ( v6 )
          v8 = v6;
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_1800710A0,
          &v25,
          v8,
          0,
          &v21);
      }
      updated = 50;
      v13 = 50;
    }
  }
  else
  {
    updated = 87;
    v13 = 87;
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v25) = 0;
      FormatRRASErrorString(&v25, L"%hs(Line#%d): Invalid parameter.", "RRasRoutingDomainConfig::SetConfig", 1925);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v25);
LABEL_17:
      updated = v13;
    }
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v14);
  return updated;
}

```

## disassembly

```asm
0x180041494  mov     [rsp-8+arg_10], rbx
0x180041499  push    rbp
0x18004149a  push    rsi
0x18004149b  push    rdi
0x18004149c  lea     rbp, [rsp-7D0h]
0x1800414a4  sub     rsp, 8D0h
0x1800414ab  mov     rax, cs:__security_cookie
0x1800414b2  xor     rax, rsp
0x1800414b5  mov     [rbp+7E0h+var_20], rax
0x1800414bc  mov     rbx, rdx
0x1800414bf  mov     rsi, rcx
0x1800414c2  mov     [rsp+8E0h+var_8A0], 0
0x1800414ca  xorps   xmm0, xmm0
0x1800414cd  movdqu  [rsp+8E0h+var_890], xmm0
0x1800414d3  mov     [rsp+8E0h+var_898], 0
0x1800414dc  xorps   xmm1, xmm1
0x1800414df  movdqu  [rsp+8E0h+var_880], xmm1
0x1800414e5  mov     [rsp+8E0h+var_870], 0
0x1800414ee  mov     [rsp+8E0h+var_868], 0FFFFFFFFh
0x1800414f6  mov     [rsp+8E0h+var_864], 0
0x1800414fe  lea     rdi, [rcx+204h]
0x180041505  cmp     qword ptr cs:xmmword_1800710A0+8, 0
0x18004150d  jz      short loc_18004152A
0x18004150f  mov     [rsp+8E0h+var_8C0], rdi; struct _GUID *
0x180041514  lea     r8, [rsp+8E0h+var_8A0]; unsigned int *
0x180041519  lea     rdx, aRrasroutingdom_17; "RRasRoutingDomainConfig::SetConfig"
0x180041520  lea     rcx, [rsp+8E0h+var_898]; this
0x180041525  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18004152a  xor     eax, eax
0x18004152c  mov     [rbp+7E0h+var_820], eax
0x18004152f  xor     edx, edx; Val
0x180041531  mov     r8d, 7FCh; Size
0x180041537  lea     rcx, [rbp+7E0h+var_81C]; void *
0x18004153b  call    memset_0
0x180041540  xor     eax, eax
0x180041542  mov     [rbp+7E0h+var_850], eax
0x180041545  xorps   xmm0, xmm0
0x180041548  movups  [rbp+7E0h+var_84C], xmm0
0x18004154c  movups  [rbp+7E0h+var_83C], xmm0
0x180041550  mov     [rbp+7E0h+var_82C], eax
0x180041553  test    rbx, rbx
0x180041556  jnz     short loc_1800415B0
0x180041558  lea     ebx, [rax+57h]
0x18004155b  mov     [rsp+8E0h+var_8A0], ebx
0x18004155f  cmp     qword ptr cs:xmmword_180071090, rax
0x180041566  jz      loc_1800416C6
0x18004156c  mov     word ptr [rbp+7E0h+var_820], ax
0x180041570  mov     r9d, 785h
0x180041576  lea     r8, aRrasroutingdom_49; "RRasRoutingDomainConfig::SetConfig"
0x18004157d  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x180041584  lea     rcx, [rbp+7E0h+var_820]
0x180041588  call    FormatRRASErrorString
0x18004158d  lea     r8, [rbp+7E0h+var_820]
0x180041591  mov     rdx, qword ptr cs:xmmword_180071090
0x180041598  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004159f  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800415a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800415ab  jmp     loc_1800416C2
0x1800415b0  movzx   r9d, byte ptr [rbx]
0x1800415b4  cmp     r9d, 1
0x1800415b8  jz      short loc_180041637
0x1800415ba  cmp     qword ptr cs:xmmword_1800710A0, rax
0x1800415c1  jz      short loc_180041629
0x1800415c3  mov     word ptr [rbp+7E0h+var_820], ax
0x1800415c7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800415ce  movdqu  [rbp+7E0h+var_860], xmm0
0x1800415d3  mov     word ptr [rbp+7E0h+var_850], ax
0x1800415d7  lea     r8, aRrasroutingdom_17; "RRasRoutingDomainConfig::SetConfig"
0x1800415de  lea     rdx, aSUnSupportedRe; "%s: Un-supported revision (%d)."
0x1800415e5  lea     rcx, [rbp+7E0h+var_820]
0x1800415e9  call    FormatRRASErrorString
0x1800415ee  lea     r9, [rbp+7E0h+var_860]
0x1800415f2  test    rdi, rdi
0x1800415f5  cmovnz  r9, rdi
0x1800415f9  lea     rax, [rbp+7E0h+var_850]
0x1800415fd  mov     [rsp+8E0h+var_8B8], rax
0x180041602  mov     [rsp+8E0h+var_8C0], 0
0x18004160b  lea     r8, [rbp+7E0h+var_820]
0x18004160f  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180041616  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004161d  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180041624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041629  mov     ebx, 32h ; '2'
0x18004162e  mov     [rsp+8E0h+var_8A0], ebx
0x180041632  jmp     loc_1800416C6
0x180041637  lea     rdx, [rbx+8]; struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *
0x18004163b  mov     rcx, rsi; this
0x18004163e  call    ?UpdateConfigEx1Data@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_ROUTING_DOMAIN_CONFIG_EX1@@@Z; RRasRoutingDomainConfig::UpdateConfigEx1Data(_MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)
0x180041643  mov     ebx, eax
0x180041645  mov     [rsp+8E0h+var_8A0], eax
0x180041649  test    eax, eax
0x18004164b  jz      short loc_1800416C6
0x18004164d  cmp     qword ptr cs:xmmword_1800710A0, 0
0x180041655  jz      short loc_1800416C6
0x180041657  xor     eax, eax
0x180041659  mov     word ptr [rbp+7E0h+var_820], ax
0x18004165d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180041664  movdqu  [rbp+7E0h+var_860], xmm0
0x180041669  mov     word ptr [rbp+7E0h+var_850], ax
0x18004166d  mov     r9d, ebx
0x180041670  lea     r8, aRrasroutingdom_17; "RRasRoutingDomainConfig::SetConfig"
0x180041677  lea     rdx, aSUpdateconfige; "%s: UpdateConfigEx1Data failed: %d."
0x18004167e  lea     rcx, [rbp+7E0h+var_820]
0x180041682  call    FormatRRASErrorString
0x180041687  lea     r9, [rbp+7E0h+var_860]
0x18004168b  test    rdi, rdi
0x18004168e  cmovnz  r9, rdi
0x180041692  lea     rax, [rbp+7E0h+var_850]
0x180041696  mov     [rsp+8E0h+var_8B8], rax
0x18004169b  mov     [rsp+8E0h+var_8C0], 0
0x1800416a4  lea     r8, [rbp+7E0h+var_820]
0x1800416a8  mov     rdx, qword ptr cs:xmmword_1800710A0
0x1800416af  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x1800416b6  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x1800416bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416c2  mov     ebx, [rsp+8E0h+var_8A0]
0x1800416c6  lea     rcx, [rsp+8E0h+var_898]; this
0x1800416cb  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800416d0  mov     eax, ebx
0x1800416d2  mov     rcx, [rbp+7E0h+var_20]
0x1800416d9  xor     rcx, rsp; StackCookie
0x1800416dc  call    __security_check_cookie
0x1800416e1  mov     rbx, [rsp+8E0h+arg_10]
0x1800416e9  add     rsp, 8D0h
0x1800416f0  pop     rdi
0x1800416f1  pop     rsi
0x1800416f2  pop     rbp
0x1800416f3  retn
```
