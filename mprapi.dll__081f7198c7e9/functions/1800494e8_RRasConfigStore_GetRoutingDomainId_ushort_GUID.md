# RRasConfigStore::GetRoutingDomainId(ushort *,_GUID *)

- ea: `0x1800494e8`
- end: `0x180049722`
- name: `?GetRoutingDomainId@RRasConfigStore@@QEAAKPEAGPEAU_GUID@@@Z`
- size: `570`
- prototype: `__int64 __fastcall(RRasConfigStore *this, unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180041af0`

## callees

- `0x1800492a8`
- `0x1800494e8`
- `0x180050b2c`
- `0x180050cd4`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800495cb`
- `msvcrt!_wcsicmp` at `0x1800495cb`
- `ntdll!RtlAcquireResourceShared` at `0x1800495ae`
- `ntdll!RtlAcquireResourceShared` at `0x1800495ae`
- `ntdll!RtlReleaseResource` at `0x180049693`
- `ntdll!RtlReleaseResource` at `0x180049693`

## string_xrefs

- `0x18004957f`: `RRasConfigStore::GetRoutingDomainId`
- `0x1800495fa`: `RRasConfigStore::GetRoutingDomainId`
- `0x180049658`: `RRasConfigStore::GetRoutingDomainId`
- `0x1800496ba`: `RRasConfigStore::GetRoutingDomainId`
- `0x180049601`: `%s: No Routing Domain object with name '%ws' is configured for RRAS. Trying to get it from Network stack`

## pseudocode

```c
__int64 __fastcall RRasConfigStore::GetRoutingDomainId(RRasConfigStore *this, unsigned __int16 *a2, struct _GUID *a3)
{
  void (*v6)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  RRasConfigStore *v7; // rcx
  _QWORD *v8; // rbx
  __int64 v9; // r14
  unsigned int v10; // ebx
  unsigned int RoutingDomainIDFromStack; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v13; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v14; // [rsp+30h] [rbp-D0h]
  __int128 v15; // [rsp+40h] [rbp-C0h]
  __int64 v16; // [rsp+50h] [rbp-B0h]
  int v17; // [rsp+58h] [rbp-A8h]
  int v18; // [rsp+5Ch] [rbp-A4h]
  int v19; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  RoutingDomainIDFromStack = 0;
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  v14 = 0;
  v13 = 0;
  v15 = 0;
  v16 = 0;
  v17 = -1;
  v18 = 0;
  if ( *((_QWORD *)&xmmword_180078C50 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v13,
      L"RRasConfigStore::GetRoutingDomainId",
      &RoutingDomainIDFromStack,
      v6);
  if ( a3 && a2 )
  {
    *a3 = 0;
    RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 112), 1u);
    v8 = (_QWORD *)*((_QWORD *)this + 3);
    while ( 1 )
    {
      v8 = (_QWORD *)*v8;
      if ( v8 == *((_QWORD **)this + 3) )
        break;
      v9 = v8[4];
      if ( !_wcsicmp((const wchar_t *)v9, a2) )
      {
        *a3 = *(struct _GUID *)(v9 + 516);
        goto LABEL_14;
      }
    }
    if ( *((_QWORD *)&xmmword_180078C50 + 1) )
    {
      LOWORD(v19) = 0;
      FormatRRASErrorString(
        &v19,
        L"%s: No Routing Domain object with name '%ws' is configured for RRAS. Trying to get it from Network stack",
        L"RRasConfigStore::GetRoutingDomainId",
        a2);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        *((_QWORD *)&xmmword_180078C50 + 1),
        &v19);
    }
    RoutingDomainIDFromStack = RRasConfigStore::GetRoutingDomainIDFromStack(v7, a2, a3);
    if ( RoutingDomainIDFromStack && (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v19) = 0;
      FormatRRASErrorString(
        &v19,
        L"%s: No Routing Domain object found with name '%ws'",
        L"RRasConfigStore::GetRoutingDomainId",
        a2);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C50,
        &v19);
    }
LABEL_14:
    RtlReleaseResource((PRTL_RESOURCE)((char *)this + 112));
  }
  else
  {
    RoutingDomainIDFromStack = 87;
    if ( (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v19) = 0;
      FormatRRASErrorString(&v19, L"%hs(Line#%d): Invalid parameter.", "RRasConfigStore::GetRoutingDomainId", 787);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C50,
        &v19);
    }
  }
  v10 = RoutingDomainIDFromStack;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v13);
  return v10;
}

```

## disassembly

```asm
0x1800494e8  push    rbp
0x1800494ea  push    rbx
0x1800494eb  push    rsi
0x1800494ec  push    rdi
0x1800494ed  push    r12
0x1800494ef  push    r14
0x1800494f1  push    r15
0x1800494f3  lea     rbp, [rsp-770h]
0x1800494fb  sub     rsp, 870h
0x180049502  mov     rax, cs:__security_cookie
0x180049509  xor     rax, rsp
0x18004950c  mov     [rbp+7A0h+var_40], rax
0x180049513  mov     rsi, r8
0x180049516  mov     rdi, rdx
0x180049519  mov     r15, rcx
0x18004951c  mov     [rsp+8A0h+var_880], 0
0x180049524  xor     eax, eax
0x180049526  mov     [rsp+8A0h+var_840], eax
0x18004952a  xor     edx, edx; Val
0x18004952c  mov     r8d, 7FCh; Size
0x180049532  lea     rcx, [rsp+8A0h+var_83C]; void *
0x180049537  call    memset_0
0x18004953c  xorps   xmm0, xmm0
0x18004953f  movdqu  [rsp+8A0h+var_870], xmm0
0x180049545  mov     [rsp+8A0h+var_878], 0
0x18004954e  xorps   xmm1, xmm1
0x180049551  movdqu  [rsp+8A0h+var_860], xmm1
0x180049557  mov     [rsp+8A0h+var_850], 0
0x180049560  mov     [rsp+8A0h+var_848], 0FFFFFFFFh
0x180049568  mov     [rsp+8A0h+var_844], 0
0x180049570  cmp     qword ptr cs:xmmword_180078C50+8, 0
0x180049578  jz      short loc_180049590
0x18004957a  lea     r8, [rsp+8A0h+var_880]; unsigned int *
0x18004957f  lea     rdx, aRrasconfigstor_26; "RRasConfigStore::GetRoutingDomainId"
0x180049586  lea     rcx, [rsp+8A0h+var_878]; this
0x18004958b  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180049590  test    rsi, rsi
0x180049593  jz      loc_18004969B
0x180049599  test    rdi, rdi
0x18004959c  jz      loc_18004969B
0x1800495a2  xorps   xmm0, xmm0
0x1800495a5  movups  xmmword ptr [rsi], xmm0
0x1800495a8  mov     dl, 1; Wait
0x1800495aa  lea     rcx, [r15+70h]; Resource
0x1800495ae  call    cs:__imp_RtlAcquireResourceShared
0x1800495b4  mov     rbx, [r15+18h]
0x1800495b8  mov     rbx, [rbx]
0x1800495bb  cmp     rbx, [r15+18h]
0x1800495bf  jz      short loc_1800495E6
0x1800495c1  mov     r14, [rbx+20h]
0x1800495c5  mov     rdx, rdi; String2
0x1800495c8  mov     rcx, r14; String1
0x1800495cb  call    cs:__imp__wcsicmp
0x1800495d1  test    eax, eax
0x1800495d3  jnz     short loc_1800495B8
0x1800495d5  movups  xmm0, xmmword ptr [r14+204h]
0x1800495dd  movdqu  xmmword ptr [rsi], xmm0
0x1800495e1  jmp     loc_18004968F
0x1800495e6  cmp     qword ptr cs:xmmword_180078C50+8, 0
0x1800495ee  jz      short loc_180049631
0x1800495f0  xor     eax, eax
0x1800495f2  mov     word ptr [rsp+8A0h+var_840], ax
0x1800495f7  mov     r9, rdi
0x1800495fa  lea     r8, aRrasconfigstor_26; "RRasConfigStore::GetRoutingDomainId"
0x180049601  lea     rdx, aSNoRoutingDoma; "%s: No Routing Domain object with name "...
0x180049608  lea     rcx, [rsp+8A0h+var_840]
0x18004960d  call    FormatRRASErrorString
0x180049612  lea     r8, [rsp+8A0h+var_840]
0x180049617  mov     rdx, qword ptr cs:xmmword_180078C50+8
0x18004961e  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180049625  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004962c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049631  mov     r8, rsi; struct _GUID *
0x180049634  mov     rdx, rdi; unsigned __int16 *
0x180049637  call    ?GetRoutingDomainIDFromStack@RRasConfigStore@@AEAAKPEAGPEAU_GUID@@@Z; RRasConfigStore::GetRoutingDomainIDFromStack(ushort *,_GUID *)
0x18004963c  mov     [rsp+8A0h+var_880], eax
0x180049640  test    eax, eax
0x180049642  jz      short loc_18004968F
0x180049644  cmp     qword ptr cs:xmmword_180078C50, 0
0x18004964c  jz      short loc_18004968F
0x18004964e  xor     eax, eax
0x180049650  mov     word ptr [rsp+8A0h+var_840], ax
0x180049655  mov     r9, rdi
0x180049658  lea     r8, aRrasconfigstor_26; "RRasConfigStore::GetRoutingDomainId"
0x18004965f  lea     rdx, aSNoRoutingDoma_0; "%s: No Routing Domain object found with"...
0x180049666  lea     rcx, [rsp+8A0h+var_840]
0x18004966b  call    FormatRRASErrorString
0x180049670  lea     r8, [rsp+8A0h+var_840]
0x180049675  mov     rdx, qword ptr cs:xmmword_180078C50
0x18004967c  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180049683  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004968a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004968f  lea     rcx, [r15+70h]; Resource
0x180049693  call    cs:__imp_RtlReleaseResource
0x180049699  jmp     short loc_1800496F1
0x18004969b  mov     [rsp+8A0h+var_880], 57h ; 'W'
0x1800496a3  cmp     qword ptr cs:xmmword_180078C50, 0
0x1800496ab  jz      short loc_1800496F1
0x1800496ad  xor     eax, eax
0x1800496af  mov     word ptr [rsp+8A0h+var_840], ax
0x1800496b4  mov     r9d, 313h
0x1800496ba  lea     r8, aRrasconfigstor_11; "RRasConfigStore::GetRoutingDomainId"
0x1800496c1  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x1800496c8  lea     rcx, [rsp+8A0h+var_840]
0x1800496cd  call    FormatRRASErrorString
0x1800496d2  lea     r8, [rsp+8A0h+var_840]
0x1800496d7  mov     rdx, qword ptr cs:xmmword_180078C50
0x1800496de  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x1800496e5  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800496ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800496f1  mov     ebx, [rsp+8A0h+var_880]
0x1800496f5  lea     rcx, [rsp+8A0h+var_878]; this
0x1800496fa  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800496ff  mov     eax, ebx
0x180049701  mov     rcx, [rbp+7A0h+var_40]
0x180049708  xor     rcx, rsp; StackCookie
0x18004970b  call    __security_check_cookie
0x180049710  add     rsp, 870h
0x180049717  pop     r15
0x180049719  pop     r14
0x18004971b  pop     r12
0x18004971d  pop     rdi
0x18004971e  pop     rsi
0x18004971f  pop     rbx
0x180049720  pop     rbp
0x180049721  retn
```
