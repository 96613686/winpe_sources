# RRasConfigStore::EnableRoutingDomainOnRRAS(_GUID *)

- ea: `0x180047508`
- end: `0x180047abd`
- name: `?EnableRoutingDomainOnRRAS@RRasConfigStore@@QEAAKPEAU_GUID@@@Z`
- size: `1461`
- prototype: `__int64 __fastcall(RRasConfigStore *this, struct _GUID *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180041014`

## callees

- `0x180002718`
- `0x1800302d0`
- `0x180043e78`
- `0x180044384`
- `0x180046644`
- `0x180047508`
- `0x180049f28`
- `0x18004a6c0`
- `0x18004c944`
- `0x18004f0ec`
- `0x18004fd28`
- `0x180050b2c`
- `0x180050be8`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047932`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047946`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047a51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047932`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047946`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047a51`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180047958`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180047958`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047940`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047a5f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047940`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047a5f`
- `ntdll!RtlReleaseResource` at `0x180047a7d`
- `ntdll!RtlReleaseResource` at `0x180047a7d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004763b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004763b`

## string_xrefs

- `0x180047741`: `%s: Failed to instantiate a Routing Domain config object.`
- `0x1800477ad`: `%s: OpenConfigRegKey failed: %d.`
- `0x1800475ac`: `RRasConfigStore::EnableRoutingDomainOnRRAS`
- `0x1800475f8`: `RRasConfigStore::EnableRoutingDomainOnRRAS`
- `0x1800476a2`: `%s: Routing domain already configured.`
- `0x180047808`: `%s: CreateLoopbackInterface failed: %d.`
- `0x18004784f`: `%s: rdConfig->PersistConfig failed for (%ws): %d.`
- `0x1800478ee`: `%s: rdConfig->SetConfigParam (ipv4 transport) failed for (%ws): %d.`
- `0x180047a0d`: `%s: rdConfig->SetConfigParam (ipv6 transport) failed for (%ws): %d.`

## pseudocode

```c
__int64 __fastcall RRasConfigStore::EnableRoutingDomainOnRRAS(RRasConfigStore *this, struct _GUID *a2)
{
  void (*v4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  struct _RTL_RESOURCE *v5; // r15
  char *v6; // r14
  __int64 v7; // rdx
  RRasRoutingDomainConfig *v8; // rax
  RRasRoutingDomainConfig *v9; // rbx
  unsigned int v10; // eax
  __int64 v11; // r9
  const wchar_t *v12; // rdx
  unsigned int LoopbackInterface; // eax
  unsigned int v14; // eax
  __int64 v15; // r8
  void (*v16)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  void *v17; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v19; // rax
  char *v20; // rax
  void *v21; // rsi
  _DWORD *v22; // rcx
  HANDLE v23; // rax
  unsigned int v24; // ebx
  struct _GUID *v26; // [rsp+20h] [rbp-E0h]
  struct _GUID *v27; // [rsp+20h] [rbp-E0h]
  struct _GUID *v28; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v29; // [rsp+28h] [rbp-D8h]
  unsigned int v30; // [rsp+30h] [rbp-D0h]
  unsigned int v31; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v32; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v33; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v34; // [rsp+50h] [rbp-B0h]
  LPVOID lpMem; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v37; // [rsp+68h] [rbp-98h]
  __int128 v38; // [rsp+78h] [rbp-88h]
  __int64 v39; // [rsp+88h] [rbp-78h]
  int v40; // [rsp+90h] [rbp-70h]
  int v41; // [rsp+94h] [rbp-6Ch]
  struct _GUID v42; // [rsp+A0h] [rbp-60h] BYREF
  int v43; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v44; // [rsp+B4h] [rbp-4Ch]
  __int128 v45; // [rsp+C4h] [rbp-3Ch]
  int v46; // [rsp+D4h] [rbp-2Ch]
  _BYTE v47[80]; // [rsp+E0h] [rbp-20h] BYREF
  int v48; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v49[2044]; // [rsp+134h] [rbp+34h] BYREF

  v31 = 0;
  memset_0(v47, 0, sizeof(v47));
  v32 = 0;
  lpMem = 0;
  v48 = 0;
  memset_0(v49, 0, sizeof(v49));
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v37 = 0;
  v36 = 0;
  v38 = 0;
  v39 = 0;
  v40 = -1;
  v41 = 0;
  if ( *((_QWORD *)&xmmword_180078C60 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v36,
      L"RRasConfigStore::EnableRoutingDomainOnRRAS",
      &v31,
      v4,
      a2,
      v29,
      v30);
  if ( a2 )
  {
    v5 = (struct _RTL_RESOURCE *)((char *)this + 112);
    RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 112), 1u);
    MprConvertGuidToString(a2, 40, v47);
    v6 = (char *)this + 16;
    std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(
      (char *)this + 16,
      &v33,
      a2);
    if ( v33 != *((_QWORD *)this + 3) )
    {
      v31 = 183;
      if ( *((_QWORD *)&xmmword_180078C60 + 1) )
      {
        LOWORD(v48) = 0;
        v42 = GUID_NULL;
        LOWORD(v43) = 0;
        FormatRRASErrorString(
          &v48,
          L"%s: Routing domain already configured.",
          L"RRasConfigStore::EnableRoutingDomainOnRRAS");
        v7 = *((_QWORD *)&xmmword_180078C60 + 1);
LABEL_9:
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, int *, struct _GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
          gCfgStoreEtwContext,
          v7,
          &v48,
          a2,
          0,
          &v43);
        goto LABEL_40;
      }
      goto LABEL_40;
    }
    v8 = (RRasRoutingDomainConfig *)operator new(0x358u);
    v33 = (__int64)v8;
    if ( v8 )
    {
      v42 = *a2;
      v9 = RRasRoutingDomainConfig::RRasRoutingDomainConfig(v8, *((HKEY *)this + 1), &v42);
    }
    else
    {
      v9 = 0;
    }
    if ( !v9 )
    {
      if ( (_QWORD)xmmword_180078C60 )
      {
        LOWORD(v48) = 0;
        v42 = GUID_NULL;
        LOWORD(v43) = 0;
        FormatRRASErrorString(
          &v48,
          L"%s: Failed to instantiate a Routing Domain config object.",
          L"RRasConfigStore::EnableRoutingDomainOnRRAS");
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, struct _GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_180078C60,
          &v48,
          a2,
          0,
          &v43);
      }
      v31 = 8;
      goto LABEL_40;
    }
    v10 = RRasRoutingDomainConfig::OpenConfigRegKey(v9);
    v11 = v10;
    v31 = v10;
    if ( v10 )
    {
      if ( !(_QWORD)xmmword_180078C50 )
        goto LABEL_40;
      v12 = L"%s: OpenConfigRegKey failed: %d.";
    }
    else
    {
      LoopbackInterface = RRasRoutingDomainConfig::CreateLoopbackInterface(v9);
      v11 = LoopbackInterface;
      v31 = LoopbackInterface;
      if ( !LoopbackInterface )
      {
        v14 = RRasRoutingDomainConfig::PersistConfig(v9);
        v31 = v14;
        if ( !v14 )
        {
          CreateIpv4TransportInfo(&v32, (unsigned __int8 **)&lpMem, v15, v16);
          v17 = lpMem;
          if ( lpMem )
          {
            LODWORD(v33) = 33;
            HIDWORD(v33) = v32;
            v34 = lpMem;
            RRasRoutingDomainConfig::SetConfigParam(v9, 32, 1, 16, &v33);
            if ( v31 )
            {
              if ( (_QWORD)xmmword_180078C60 )
              {
                LOWORD(v48) = 0;
                v42 = GUID_NULL;
                LOWORD(v43) = 0;
                LODWORD(v27) = v31;
                FormatRRASErrorString(
                  &v48,
                  L"%s: rdConfig->SetConfigParam (ipv4 transport) failed for (%ws): %d.",
                  L"RRasConfigStore::EnableRoutingDomainOnRRAS",
                  v47,
                  v27);
                ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, struct _GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
                  gCfgStoreEtwContext,
                  xmmword_180078C60,
                  &v48,
                  a2,
                  0,
                  &v43);
              }
              v31 = 0;
            }
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v17);
          }
          v19 = GetProcessHeap();
          v20 = (char *)HeapAlloc(v19, 8u, 0x2Cu);
          v21 = v20;
          if ( v20 )
          {
            *(_QWORD *)(v20 + 28) = 0;
            *(_QWORD *)(v20 + 36) = 0;
            *(_DWORD *)v20 = 1;
            *((_DWORD *)v20 + 1) = 44;
            *((_DWORD *)v20 + 2) = 1;
            v22 = (_DWORD *)((unsigned __int64)(v20 + 35) & 0xFFFFFFFFFFFFFFF8uLL);
            *((_DWORD *)v20 + 3) = -65521;
            *((_DWORD *)v20 + 4) = 8;
            *((_DWORD *)v20 + 5) = 1;
            *((_DWORD *)v20 + 6) = (((_DWORD)v20 + 35) & 0xFFFFFFF8) - (_DWORD)v20;
            *v22 = 0;
            v22[1] = 1;
            v33 = 0x2C00000057LL;
            v34 = v20;
            RRasRoutingDomainConfig::SetConfigParam(v9, 128, 1, 16, &v33);
            if ( v31 )
            {
              if ( (_QWORD)xmmword_180078C60 )
              {
                LOWORD(v48) = 0;
                v42 = GUID_NULL;
                LOWORD(v43) = 0;
                LODWORD(v28) = v31;
                FormatRRASErrorString(
                  &v48,
                  L"%s: rdConfig->SetConfigParam (ipv6 transport) failed for (%ws): %d.",
                  L"RRasConfigStore::EnableRoutingDomainOnRRAS",
                  v47,
                  v28);
                ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, struct _GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
                  gCfgStoreEtwContext,
                  xmmword_180078C60,
                  &v48,
                  a2,
                  0,
                  &v43);
              }
              v31 = 0;
            }
            v23 = GetProcessHeap();
            HeapFree(v23, 0, v21);
          }
          *((_DWORD *)v9 + 133) |= 2u;
          *(_QWORD *)std::tr1::unordered_map<_GUID,RRasRoutingDomainConfig *,GuidHash,GuidEquality,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>>::operator[](
                       (__int64)v6,
                       (__int128 *)a2) = v9;
          goto LABEL_40;
        }
        if ( (_QWORD)xmmword_180078C60 )
        {
          LOWORD(v48) = 0;
          v42 = GUID_NULL;
          LOWORD(v43) = 0;
          LODWORD(v26) = v14;
          FormatRRASErrorString(
            &v48,
            L"%s: rdConfig->PersistConfig failed for (%ws): %d.",
            L"RRasConfigStore::EnableRoutingDomainOnRRAS",
            v47,
            v26);
          v7 = xmmword_180078C60;
          goto LABEL_9;
        }
LABEL_40:
        RtlReleaseResource(v5);
        goto LABEL_41;
      }
      if ( !(_QWORD)xmmword_180078C50 )
        goto LABEL_40;
      v12 = L"%s: CreateLoopbackInterface failed: %d.";
    }
    LOWORD(v48) = 0;
    FormatRRASErrorString(&v48, v12, L"RRasConfigStore::EnableRoutingDomainOnRRAS", v11);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180078C50,
      &v48);
    goto LABEL_40;
  }
  v31 = 87;
  if ( (_QWORD)xmmword_180078C50 )
  {
    LOWORD(v48) = 0;
    FormatRRASErrorString(&v48, L"%hs(Line#%d): Invalid parameter.", "RRasConfigStore::EnableRoutingDomainOnRRAS", 428);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180078C50,
      &v48);
  }
LABEL_41:
  v24 = v31;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v36);
  return v24;
}

```

## disassembly

```asm
0x180047508  mov     [rsp-8+arg_10], rbx
0x18004750d  push    rbp
0x18004750e  push    rsi
0x18004750f  push    rdi
0x180047510  push    r12
0x180047512  push    r13
0x180047514  push    r14
0x180047516  push    r15
0x180047518  lea     rbp, [rsp-840h]
0x180047520  sub     rsp, 940h
0x180047527  mov     rax, cs:__security_cookie
0x18004752e  xor     rax, rsp
0x180047531  mov     [rbp+870h+var_40], rax
0x180047538  mov     rdi, rdx
0x18004753b  mov     rbx, rcx
0x18004753e  xor     r12d, r12d
0x180047541  mov     [rsp+970h+var_930], r12d
0x180047546  xor     edx, edx; Val
0x180047548  lea     r8d, [r12+50h]; Size
0x18004754d  lea     rcx, [rbp+870h+var_890]; void *
0x180047551  call    memset_0
0x180047556  mov     [rsp+970h+var_92C], r12d
0x18004755b  mov     [rsp+970h+lpMem], r12
0x180047560  mov     [rbp+870h+var_840], r12d
0x180047564  xor     edx, edx; Val
0x180047566  mov     r8d, 7FCh; Size
0x18004756c  lea     rcx, [rbp+870h+var_83C]; void *
0x180047570  call    memset_0
0x180047575  mov     [rbp+870h+var_8C0], r12d
0x180047579  xorps   xmm0, xmm0
0x18004757c  xor     eax, eax
0x18004757e  movups  [rbp+870h+var_8BC], xmm0
0x180047582  movups  [rbp+870h+var_8AC], xmm0
0x180047586  mov     [rbp+870h+var_89C], eax
0x180047589  movdqu  [rsp+970h+var_908], xmm0
0x18004758f  mov     [rsp+970h+var_910], r12
0x180047594  xorps   xmm1, xmm1
0x180047597  movdqu  [rsp+970h+var_8F8], xmm1
0x18004759d  mov     [rbp+870h+var_8E8], r12
0x1800475a1  mov     [rbp+870h+var_8E0], 0FFFFFFFFh
0x1800475a8  mov     [rbp+870h+var_8DC], r12d
0x1800475ac  lea     r13, aRrasconfigstor_5; "RRasConfigStore::EnableRoutingDomainOnR"...
0x1800475b3  cmp     qword ptr cs:xmmword_180078C60+8, r12
0x1800475ba  jz      short loc_1800475D3
0x1800475bc  mov     [rsp+970h+var_950], rdi; struct _GUID *
0x1800475c1  lea     r8, [rsp+970h+var_930]; unsigned int *
0x1800475c6  mov     rdx, r13; unsigned __int16 *
0x1800475c9  lea     rcx, [rsp+970h+var_910]; this
0x1800475ce  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x1800475d3  test    rdi, rdi
0x1800475d6  jnz     short loc_180047632
0x1800475d8  mov     [rsp+970h+var_930], 57h ; 'W'
0x1800475e0  cmp     qword ptr cs:xmmword_180078C50, r12
0x1800475e7  jz      loc_180047A83
0x1800475ed  mov     word ptr [rbp+870h+var_840], r12w
0x1800475f2  mov     r9d, 1ACh
0x1800475f8  lea     r8, aRrasconfigstor_28; "RRasConfigStore::EnableRoutingDomainOnR"...
0x1800475ff  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x180047606  lea     rcx, [rbp+870h+var_840]
0x18004760a  call    FormatRRASErrorString
0x18004760f  lea     r8, [rbp+870h+var_840]
0x180047613  mov     rdx, qword ptr cs:xmmword_180078C50
0x18004761a  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180047621  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180047628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004762d  jmp     loc_180047A83
0x180047632  lea     r15, [rbx+70h]
0x180047636  mov     dl, 1; Wait
0x180047638  mov     rcx, r15; Resource
0x18004763b  call    cs:__imp_RtlAcquireResourceExclusive
0x180047641  lea     r8, [rbp+870h+var_890]
0x180047645  mov     edx, 28h ; '('
0x18004764a  mov     rcx, rdi
0x18004764d  call    MprConvertGuidToString
0x180047652  lea     r14, [rbx+10h]
0x180047656  mov     r8, rdi
0x180047659  lea     rdx, [rsp+970h+var_928]
0x18004765e  mov     rcx, r14
0x180047661  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x180047666  mov     rax, [rbx+18h]
0x18004766a  cmp     [rsp+970h+var_928], rax
0x18004766f  jz      short loc_1800476E6
0x180047671  mov     r9d, 0B7h
0x180047677  mov     [rsp+970h+var_930], r9d
0x18004767c  cmp     qword ptr cs:xmmword_180078C60+8, r12
0x180047683  jz      loc_180047A7A
0x180047689  mov     word ptr [rbp+870h+var_840], r12w
0x18004768e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180047695  movdqu  xmmword ptr [rbp+870h+var_8D0.Data1], xmm0
0x18004769a  mov     word ptr [rbp+870h+var_8C0], r12w
0x18004769f  mov     r8, r13
0x1800476a2  lea     rdx, aSRoutingDomain; "%s: Routing domain already configured."
0x1800476a9  lea     rcx, [rbp+870h+var_840]
0x1800476ad  call    FormatRRASErrorString
0x1800476b2  mov     rdx, qword ptr cs:xmmword_180078C60+8
0x1800476b9  lea     rax, [rbp+870h+var_8C0]
0x1800476bd  mov     [rsp+970h+var_948], rax
0x1800476c2  lea     r8, [rbp+870h+var_840]
0x1800476c6  mov     r9, rdi
0x1800476c9  mov     [rsp+970h+var_950], r12
0x1800476ce  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x1800476d5  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x1800476dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800476e1  jmp     loc_180047A7A
0x1800476e6  mov     ecx, 358h; Size
0x1800476eb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800476f0  mov     [rsp+970h+var_928], rax
0x1800476f5  test    rax, rax
0x1800476f8  jz      short loc_180047717
0x1800476fa  movups  xmm0, xmmword ptr [rdi]
0x1800476fd  movdqu  xmmword ptr [rbp+870h+var_8D0.Data1], xmm0
0x180047702  lea     r8, [rbp+870h+var_8D0]; struct _GUID
0x180047706  mov     rdx, [rbx+8]; HKEY
0x18004770a  mov     rcx, rax; this
0x18004770d  call    ??0RRasRoutingDomainConfig@@QEAA@PEAUHKEY__@@U_GUID@@@Z; RRasRoutingDomainConfig::RRasRoutingDomainConfig(HKEY__ *,_GUID)
0x180047712  mov     rbx, rax
0x180047715  jmp     short loc_18004771A
0x180047717  mov     rbx, r12
0x18004771a  test    rbx, rbx
0x18004771d  jnz     short loc_18004778D
0x18004771f  cmp     qword ptr cs:xmmword_180078C60, r12
0x180047726  jz      short loc_180047780
0x180047728  mov     word ptr [rbp+870h+var_840], r12w
0x18004772d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180047734  movdqu  xmmword ptr [rbp+870h+var_8D0.Data1], xmm0
0x180047739  mov     word ptr [rbp+870h+var_8C0], r12w
0x18004773e  mov     r8, r13
0x180047741  lea     rdx, aSFailedToInsta; "%s: Failed to instantiate a Routing Dom"...
0x180047748  lea     rcx, [rbp+870h+var_840]
0x18004774c  call    FormatRRASErrorString
0x180047751  lea     rax, [rbp+870h+var_8C0]
0x180047755  mov     [rsp+970h+var_948], rax
0x18004775a  mov     [rsp+970h+var_950], r12
0x18004775f  mov     r9, rdi
0x180047762  lea     r8, [rbp+870h+var_840]
0x180047766  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004776d  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180047774  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004777b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047780  mov     [rsp+970h+var_930], 8
0x180047788  jmp     loc_180047A7A
0x18004778d  mov     rcx, rbx; this
0x180047790  call    ?OpenConfigRegKey@RRasRoutingDomainConfig@@QEAAKXZ; RRasRoutingDomainConfig::OpenConfigRegKey(void)
0x180047795  mov     r9d, eax
0x180047798  mov     [rsp+970h+var_930], eax
0x18004779c  test    eax, eax
0x18004779e  jz      short loc_1800477E8
0x1800477a0  cmp     qword ptr cs:xmmword_180078C50, r12
0x1800477a7  jz      loc_180047A7A
0x1800477ad  lea     rdx, aSOpenconfigreg; "%s: OpenConfigRegKey failed: %d."
0x1800477b4  mov     r8, r13
0x1800477b7  mov     word ptr [rbp+870h+var_840], r12w
0x1800477bc  lea     rcx, [rbp+870h+var_840]
0x1800477c0  call    FormatRRASErrorString
0x1800477c5  lea     r8, [rbp+870h+var_840]
0x1800477c9  mov     rdx, qword ptr cs:xmmword_180078C50
0x1800477d0  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x1800477d7  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800477de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800477e3  jmp     loc_180047A7A
0x1800477e8  mov     rcx, rbx; this
0x1800477eb  call    ?CreateLoopbackInterface@RRasRoutingDomainConfig@@QEAAKXZ; RRasRoutingDomainConfig::CreateLoopbackInterface(void)
0x1800477f0  mov     r9d, eax
0x1800477f3  mov     [rsp+970h+var_930], eax
0x1800477f7  test    eax, eax
0x1800477f9  jz      short loc_180047811
0x1800477fb  cmp     qword ptr cs:xmmword_180078C50, r12
0x180047802  jz      loc_180047A7A
0x180047808  lea     rdx, aSCreateloopbac; "%s: CreateLoopbackInterface failed: %d."
0x18004780f  jmp     short loc_1800477B4
0x180047811  mov     rcx, rbx; this
0x180047814  call    ?PersistConfig@RRasRoutingDomainConfig@@QEAAKXZ; RRasRoutingDomainConfig::PersistConfig(void)
0x180047819  mov     [rsp+970h+var_930], eax
0x18004781d  test    eax, eax
0x18004781f  jz      short loc_18004786B
0x180047821  cmp     qword ptr cs:xmmword_180078C60, r12
0x180047828  jz      loc_180047A7A
0x18004782e  mov     word ptr [rbp+870h+var_840], r12w
0x180047833  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004783a  movdqu  xmmword ptr [rbp+870h+var_8D0.Data1], xmm0
0x18004783f  mov     word ptr [rbp+870h+var_8C0], r12w
0x180047844  mov     dword ptr [rsp+970h+var_950], eax
0x180047848  lea     r9, [rbp+870h+var_890]
0x18004784c  mov     r8, r13
0x18004784f  lea     rdx, aSRdconfigPersi; "%s: rdConfig->PersistConfig failed for "...
0x180047856  lea     rcx, [rbp+870h+var_840]
0x18004785a  call    FormatRRASErrorString
0x18004785f  mov     rdx, qword ptr cs:xmmword_180078C60
0x180047866  jmp     loc_1800476B9
0x18004786b  lea     rdx, [rsp+970h+lpMem]; unsigned __int8 **
0x180047870  lea     rcx, [rsp+970h+var_92C]; unsigned int *
0x180047875  call    ?CreateIpv4TransportInfo@@YAKPEAKPEAPEAE@Z; CreateIpv4TransportInfo(ulong *,uchar * *)
0x18004787a  mov     rsi, [rsp+970h+lpMem]
0x18004787f  test    rsi, rsi
0x180047882  jz      loc_180047946
0x180047888  mov     dword ptr [rsp+970h+var_928], 21h ; '!'
0x180047890  mov     eax, [rsp+970h+var_92C]
0x180047894  mov     dword ptr [rsp+970h+var_928+4], eax
0x180047898  mov     [rsp+970h+var_920], rsi
0x18004789d  lea     rax, [rsp+970h+var_928]
0x1800478a2  mov     [rsp+970h+var_950], rax
0x1800478a7  mov     edx, 20h ; ' '
0x1800478ac  lea     r9d, [rdx-10h]
0x1800478b0  lea     r8d, [rdx-1Fh]
0x1800478b4  mov     rcx, rbx
0x1800478b7  call    ?SetConfigParam@RRasRoutingDomainConfig@@QEAAKW4_RRAS_RD_CONFIG_TYPE@@HKPEAX@Z; RRasRoutingDomainConfig::SetConfigParam(_RRAS_RD_CONFIG_TYPE,int,ulong,void *)
0x1800478bc  mov     ecx, [rsp+970h+var_930]
0x1800478c0  test    ecx, ecx
0x1800478c2  jz      short loc_180047932
0x1800478c4  cmp     qword ptr cs:xmmword_180078C60, r12
0x1800478cb  jz      short loc_18004792D
0x1800478cd  mov     word ptr [rbp+870h+var_840], r12w
0x1800478d2  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800478d9  movdqu  xmmword ptr [rbp+870h+var_8D0.Data1], xmm0
0x1800478de  mov     word ptr [rbp+870h+var_8C0], r12w
0x1800478e3  mov     dword ptr [rsp+970h+var_950], ecx
0x1800478e7  lea     r9, [rbp+870h+var_890]
0x1800478eb  mov     r8, r13
0x1800478ee  lea     rdx, aSRdconfigSetco_0; "%s: rdConfig->SetConfigParam (ipv4 tran"...
0x1800478f5  lea     rcx, [rbp+870h+var_840]
0x1800478f9  call    FormatRRASErrorString
0x1800478fe  lea     rax, [rbp+870h+var_8C0]
0x180047902  mov     [rsp+970h+var_948], rax
0x180047907  mov     [rsp+970h+var_950], r12
0x18004790c  mov     r9, rdi
0x18004790f  lea     r8, [rbp+870h+var_840]
0x180047913  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004791a  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180047921  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180047928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004792d  mov     [rsp+970h+var_930], r12d
0x180047932  call    cs:__imp_GetProcessHeap
0x180047938  mov     r8, rsi; lpMem
0x18004793b  xor     edx, edx; dwFlags
0x18004793d  mov     rcx, rax; hHeap
0x180047940  call    cs:__imp_HeapFree
0x180047946  call    cs:__imp_GetProcessHeap
0x18004794c  mov     rcx, rax; hHeap
0x18004794f  mov     edx, 8; dwFlags
0x180047954  lea     r8d, [rdx+24h]; dwBytes
0x180047958  call    cs:__imp_HeapAlloc
0x18004795e  mov     rsi, rax
0x180047961  test    rax, rax
0x180047964  jz      loc_180047A65
0x18004796a  mov     [rax+1Ch], r12
0x18004796e  mov     [rax+24h], r12
0x180047972  mov     edx, 1
0x180047977  mov     [rax], edx
0x180047979  mov     dword ptr [rax+4], 2Ch ; ','
0x180047980  mov     [rax+8], edx
0x180047983  lea     rcx, [rax+23h]
0x180047987  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18004798b  mov     dword ptr [rax+0Ch], 0FFFF000Fh
0x180047992  mov     dword ptr [rax+10h], 8
0x180047999  mov     [rax+14h], edx
0x18004799c  mov     eax, ecx
0x18004799e  sub     eax, esi
0x1800479a0  mov     [rsi+18h], eax
0x1800479a3  mov     [rcx], r12d
0x1800479a6  mov     [rcx+4], edx
0x1800479a9  mov     dword ptr [rsp+970h+var_928], 57h ; 'W'
0x1800479b1  mov     dword ptr [rsp+970h+var_928+4], 2Ch ; ','
0x1800479b9  mov     [rsp+970h+var_920], rsi
0x1800479be  lea     rax, [rsp+970h+var_928]
0x1800479c3  mov     [rsp+970h+var_950], rax
0x1800479c8  lea     r9d, [rdx+0Fh]
0x1800479cc  mov     r8d, edx
0x1800479cf  lea     edx, [r8+7Fh]
0x1800479d3  mov     rcx, rbx
0x1800479d6  call    ?SetConfigParam@RRasRoutingDomainConfig@@QEAAKW4_RRAS_RD_CONFIG_TYPE@@HKPEAX@Z; RRasRoutingDomainConfig::SetConfigParam(_RRAS_RD_CONFIG_TYPE,int,ulong,void *)
0x1800479db  mov     ecx, [rsp+970h+var_930]
0x1800479df  test    ecx, ecx
0x1800479e1  jz      short loc_180047A51
0x1800479e3  cmp     qword ptr cs:xmmword_180078C60, r12
0x1800479ea  jz      short loc_180047A4C
0x1800479ec  mov     word ptr [rbp+870h+var_840], r12w
0x1800479f1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800479f8  movdqu  xmmword ptr [rbp+870h+var_8D0.Data1], xmm0
0x1800479fd  mov     word ptr [rbp+870h+var_8C0], r12w
0x180047a02  mov     dword ptr [rsp+970h+var_950], ecx
0x180047a06  lea     r9, [rbp+870h+var_890]
0x180047a0a  mov     r8, r13
0x180047a0d  lea     rdx, aSRdconfigSetco; "%s: rdConfig->SetConfigParam (ipv6 tran"...
0x180047a14  lea     rcx, [rbp+870h+var_840]
0x180047a18  call    FormatRRASErrorString
0x180047a1d  lea     rax, [rbp+870h+var_8C0]
0x180047a21  mov     [rsp+970h+var_948], rax
0x180047a26  mov     [rsp+970h+var_950], r12
0x180047a2b  mov     r9, rdi
0x180047a2e  lea     r8, [rbp+870h+var_840]
0x180047a32  mov     rdx, qword ptr cs:xmmword_180078C60
0x180047a39  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180047a40  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180047a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047a4c  mov     [rsp+970h+var_930], r12d
0x180047a51  call    cs:__imp_GetProcessHeap
0x180047a57  mov     r8, rsi; lpMem
0x180047a5a  xor     edx, edx; dwFlags
0x180047a5c  mov     rcx, rax; hHeap
0x180047a5f  call    cs:__imp_HeapFree
  ... truncated ...
```
