# RRasConfigStore::EnableRoutingDomainOnRRAS(_GUID *)

- ea: `0x18003bd5c`
- end: `0x18003c2d7`
- name: `?EnableRoutingDomainOnRRAS@RRasConfigStore@@QEAAKPEAU_GUID@@@Z`
- size: `1403`
- prototype: `__int64 __fastcall(RRasConfigStore *this, struct _GUID *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800355d4`

## callees

- `0x18000b604`
- `0x180033e90`
- `0x180038828`
- `0x180038b00`
- `0x18003ae88`
- `0x18003bd5c`
- `0x18003e984`
- `0x18003f104`
- `0x1800416fc`
- `0x180043e34`
- `0x1800445b0`
- `0x1800446c0`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18003c297`
- `ntdll!RtlReleaseResource` at `0x18003c297`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003be8f`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003be8f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c194`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c279`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c194`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c279`
- `KERNEL32!GetProcessHeap` at `0x18003c186`
- `KERNEL32!GetProcessHeap` at `0x18003c26b`
- `KERNEL32!GetProcessHeap` at `0x18003c186`
- `KERNEL32!GetProcessHeap` at `0x18003c26b`

## string_xrefs

- `0x18003bf95`: `%s: Failed to instantiate a Routing Domain config object.`
- `0x18003c001`: `%s: OpenConfigRegKey failed: %d.`
- `0x18003be00`: `RRasConfigStore::EnableRoutingDomainOnRRAS`
- `0x18003be4c`: `RRasConfigStore::EnableRoutingDomainOnRRAS`
- `0x18003bef6`: `%s: Routing domain already configured.`
- `0x18003c05c`: `%s: CreateLoopbackInterface failed: %d.`
- `0x18003c0a3`: `%s: rdConfig->PersistConfig failed for (%ws): %d.`
- `0x18003c142`: `%s: rdConfig->SetConfigParam (ipv4 transport) failed for (%ws): %d.`
- `0x18003c227`: `%s: rdConfig->SetConfigParam (ipv6 transport) failed for (%ws): %d.`

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
  void *v19; // rsi
  HANDLE v20; // rax
  unsigned int v21; // ebx
  struct _GUID *v23; // [rsp+20h] [rbp-E0h]
  struct _GUID *v24; // [rsp+20h] [rbp-E0h]
  struct _GUID *v25; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v26; // [rsp+28h] [rbp-D8h]
  unsigned int v27; // [rsp+30h] [rbp-D0h]
  unsigned int v28; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v29; // [rsp+44h] [rbp-BCh] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-B8h] BYREF
  RRasRoutingDomainConfig *v31; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v32; // [rsp+58h] [rbp-A8h]
  __int64 v33; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v34; // [rsp+68h] [rbp-98h]
  __int128 v35; // [rsp+78h] [rbp-88h]
  __int64 v36; // [rsp+88h] [rbp-78h]
  int v37; // [rsp+90h] [rbp-70h]
  int v38; // [rsp+94h] [rbp-6Ch]
  struct _GUID v39; // [rsp+A0h] [rbp-60h] BYREF
  int v40; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v41; // [rsp+B4h] [rbp-4Ch]
  __int128 v42; // [rsp+C4h] [rbp-3Ch]
  int v43; // [rsp+D4h] [rbp-2Ch]
  _BYTE v44[80]; // [rsp+E0h] [rbp-20h] BYREF
  int v45; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v46[2044]; // [rsp+134h] [rbp+34h] BYREF

  v28 = 0;
  memset_0(v44, 0, sizeof(v44));
  v29 = 0;
  lpMem = 0;
  v45 = 0;
  memset_0(v46, 0, sizeof(v46));
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v34 = 0;
  v33 = 0;
  v35 = 0;
  v36 = 0;
  v37 = -1;
  v38 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v33,
      L"RRasConfigStore::EnableRoutingDomainOnRRAS",
      &v28,
      v4,
      a2,
      v26,
      v27);
  if ( a2 )
  {
    v5 = (struct _RTL_RESOURCE *)((char *)this + 112);
    RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 112), 1u);
    MprConvertGuidToString(a2, 40, v44);
    v6 = (char *)this + 16;
    std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(
      (char *)this + 16,
      &v31,
      a2);
    if ( v31 != *((RRasRoutingDomainConfig **)this + 3) )
    {
      v28 = 183;
      if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
      {
        LOWORD(v45) = 0;
        v39 = GUID_NULL;
        LOWORD(v40) = 0;
        FormatRRASErrorString(
          &v45,
          L"%s: Routing domain already configured.",
          L"RRasConfigStore::EnableRoutingDomainOnRRAS");
        v7 = *((_QWORD *)&xmmword_1800710A0 + 1);
LABEL_9:
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, int *, struct _GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
          gCfgStoreEtwContext,
          v7,
          &v45,
          a2,
          0,
          &v40);
        goto LABEL_40;
      }
      goto LABEL_40;
    }
    v8 = (RRasRoutingDomainConfig *)operator new(0x358u);
    v31 = v8;
    if ( v8 )
    {
      v39 = *a2;
      v9 = RRasRoutingDomainConfig::RRasRoutingDomainConfig(v8, *((HKEY *)this + 1), &v39);
    }
    else
    {
      v9 = 0;
    }
    if ( !v9 )
    {
      if ( (_QWORD)xmmword_1800710A0 )
      {
        LOWORD(v45) = 0;
        v39 = GUID_NULL;
        LOWORD(v40) = 0;
        FormatRRASErrorString(
          &v45,
          L"%s: Failed to instantiate a Routing Domain config object.",
          L"RRasConfigStore::EnableRoutingDomainOnRRAS");
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, struct _GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_1800710A0,
          &v45,
          a2,
          0,
          &v40);
      }
      v28 = 8;
      goto LABEL_40;
    }
    v10 = RRasRoutingDomainConfig::OpenConfigRegKey(v9);
    v11 = v10;
    v28 = v10;
    if ( v10 )
    {
      if ( !(_QWORD)xmmword_180071090 )
        goto LABEL_40;
      v12 = L"%s: OpenConfigRegKey failed: %d.";
    }
    else
    {
      LoopbackInterface = RRasRoutingDomainConfig::CreateLoopbackInterface(v9);
      v11 = LoopbackInterface;
      v28 = LoopbackInterface;
      if ( !LoopbackInterface )
      {
        v14 = RRasRoutingDomainConfig::PersistConfig(v9);
        v28 = v14;
        if ( !v14 )
        {
          CreateIpv4TransportInfo(&v29, (unsigned __int8 **)&lpMem, v15, v16);
          v17 = lpMem;
          if ( lpMem )
          {
            LODWORD(v31) = 33;
            HIDWORD(v31) = v29;
            v32 = lpMem;
            RRasRoutingDomainConfig::SetConfigParam(v9, 32, 1, 16, &v31);
            if ( v28 )
            {
              if ( (_QWORD)xmmword_1800710A0 )
              {
                LOWORD(v45) = 0;
                v39 = GUID_NULL;
                LOWORD(v40) = 0;
                LODWORD(v24) = v28;
                FormatRRASErrorString(
                  &v45,
                  L"%s: rdConfig->SetConfigParam (ipv4 transport) failed for (%ws): %d.",
                  L"RRasConfigStore::EnableRoutingDomainOnRRAS",
                  v44,
                  v24);
                ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, struct _GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
                  gCfgStoreEtwContext,
                  xmmword_1800710A0,
                  &v45,
                  a2,
                  0,
                  &v40);
              }
              v28 = 0;
            }
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v17);
          }
          v29 = 0;
          lpMem = 0;
          CreateIpv6TransportInfo(&v29, (unsigned __int8 **)&lpMem);
          v19 = lpMem;
          if ( lpMem )
          {
            LODWORD(v31) = 87;
            HIDWORD(v31) = v29;
            v32 = lpMem;
            RRasRoutingDomainConfig::SetConfigParam(v9, 128, 1, 16, &v31);
            if ( v28 )
            {
              if ( (_QWORD)xmmword_1800710A0 )
              {
                LOWORD(v45) = 0;
                v39 = GUID_NULL;
                LOWORD(v40) = 0;
                LODWORD(v25) = v28;
                FormatRRASErrorString(
                  &v45,
                  L"%s: rdConfig->SetConfigParam (ipv6 transport) failed for (%ws): %d.",
                  L"RRasConfigStore::EnableRoutingDomainOnRRAS",
                  v44,
                  v25);
                ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, struct _GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
                  gCfgStoreEtwContext,
                  xmmword_1800710A0,
                  &v45,
                  a2,
                  0,
                  &v40);
              }
              v28 = 0;
            }
            v20 = GetProcessHeap();
            HeapFree(v20, 0, v19);
          }
          *((_DWORD *)v9 + 133) |= 2u;
          *(_QWORD *)std::tr1::unordered_map<_GUID,RRasRoutingDomainConfig *,GuidHash,GuidEquality,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>>::operator[](
                       v6,
                       a2) = v9;
          goto LABEL_40;
        }
        if ( (_QWORD)xmmword_1800710A0 )
        {
          LOWORD(v45) = 0;
          v39 = GUID_NULL;
          LOWORD(v40) = 0;
          LODWORD(v23) = v14;
          FormatRRASErrorString(
            &v45,
            L"%s: rdConfig->PersistConfig failed for (%ws): %d.",
            L"RRasConfigStore::EnableRoutingDomainOnRRAS",
            v44,
            v23);
          v7 = xmmword_1800710A0;
          goto LABEL_9;
        }
LABEL_40:
        RtlReleaseResource(v5);
        goto LABEL_41;
      }
      if ( !(_QWORD)xmmword_180071090 )
        goto LABEL_40;
      v12 = L"%s: CreateLoopbackInterface failed: %d.";
    }
    LOWORD(v45) = 0;
    FormatRRASErrorString(&v45, v12, L"RRasConfigStore::EnableRoutingDomainOnRRAS", v11);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180071090,
      &v45);
    goto LABEL_40;
  }
  v28 = 87;
  if ( (_QWORD)xmmword_180071090 )
  {
    LOWORD(v45) = 0;
    FormatRRASErrorString(&v45, L"%hs(Line#%d): Invalid parameter.", "RRasConfigStore::EnableRoutingDomainOnRRAS", 428);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180071090,
      &v45);
  }
LABEL_41:
  v21 = v28;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v33);
  return v21;
}

```

## disassembly

```asm
0x18003bd5c  mov     [rsp-8+arg_10], rbx
0x18003bd61  push    rbp
0x18003bd62  push    rsi
0x18003bd63  push    rdi
0x18003bd64  push    r12
0x18003bd66  push    r13
0x18003bd68  push    r14
0x18003bd6a  push    r15
0x18003bd6c  lea     rbp, [rsp-840h]
0x18003bd74  sub     rsp, 940h
0x18003bd7b  mov     rax, cs:__security_cookie
0x18003bd82  xor     rax, rsp
0x18003bd85  mov     [rbp+870h+var_40], rax
0x18003bd8c  mov     rdi, rdx
0x18003bd8f  mov     rbx, rcx
0x18003bd92  xor     r12d, r12d
0x18003bd95  mov     [rsp+970h+var_930], r12d
0x18003bd9a  xor     edx, edx; Val
0x18003bd9c  lea     r8d, [r12+50h]; Size
0x18003bda1  lea     rcx, [rbp+870h+var_890]; void *
0x18003bda5  call    memset_0
0x18003bdaa  mov     [rsp+970h+var_92C], r12d
0x18003bdaf  mov     [rsp+970h+lpMem], r12
0x18003bdb4  mov     [rbp+870h+var_840], r12d
0x18003bdb8  xor     edx, edx; Val
0x18003bdba  mov     r8d, 7FCh; Size
0x18003bdc0  lea     rcx, [rbp+870h+var_83C]; void *
0x18003bdc4  call    memset_0
0x18003bdc9  mov     [rbp+870h+var_8C0], r12d
0x18003bdcd  xorps   xmm0, xmm0
0x18003bdd0  xor     eax, eax
0x18003bdd2  movups  [rbp+870h+var_8BC], xmm0
0x18003bdd6  movups  [rbp+870h+var_8AC], xmm0
0x18003bdda  mov     [rbp+870h+var_89C], eax
0x18003bddd  movdqu  [rsp+970h+var_908], xmm0
0x18003bde3  mov     [rsp+970h+var_910], r12
0x18003bde8  xorps   xmm1, xmm1
0x18003bdeb  movdqu  [rsp+970h+var_8F8], xmm1
0x18003bdf1  mov     [rbp+870h+var_8E8], r12
0x18003bdf5  mov     [rbp+870h+var_8E0], 0FFFFFFFFh
0x18003bdfc  mov     [rbp+870h+var_8DC], r12d
0x18003be00  lea     r13, aRrasconfigstor_6; "RRasConfigStore::EnableRoutingDomainOnR"...
0x18003be07  cmp     qword ptr cs:xmmword_1800710A0+8, r12
0x18003be0e  jz      short loc_18003BE27
0x18003be10  mov     [rsp+970h+var_950], rdi; struct _GUID *
0x18003be15  lea     r8, [rsp+970h+var_930]; unsigned int *
0x18003be1a  mov     rdx, r13; unsigned __int16 *
0x18003be1d  lea     rcx, [rsp+970h+var_910]; this
0x18003be22  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18003be27  test    rdi, rdi
0x18003be2a  jnz     short loc_18003BE86
0x18003be2c  mov     [rsp+970h+var_930], 57h ; 'W'
0x18003be34  cmp     qword ptr cs:xmmword_180071090, r12
0x18003be3b  jz      loc_18003C29D
0x18003be41  mov     word ptr [rbp+870h+var_840], r12w
0x18003be46  mov     r9d, 1ACh
0x18003be4c  lea     r8, aRrasconfigstor_34; "RRasConfigStore::EnableRoutingDomainOnR"...
0x18003be53  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18003be5a  lea     rcx, [rbp+870h+var_840]
0x18003be5e  call    FormatRRASErrorString
0x18003be63  lea     r8, [rbp+870h+var_840]
0x18003be67  mov     rdx, qword ptr cs:xmmword_180071090
0x18003be6e  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003be75  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003be7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be81  jmp     loc_18003C29D
0x18003be86  lea     r15, [rbx+70h]
0x18003be8a  mov     dl, 1; Wait
0x18003be8c  mov     rcx, r15; Resource
0x18003be8f  call    cs:__imp_RtlAcquireResourceExclusive
0x18003be95  lea     r8, [rbp+870h+var_890]
0x18003be99  mov     edx, 28h ; '('
0x18003be9e  mov     rcx, rdi
0x18003bea1  call    MprConvertGuidToString
0x18003bea6  lea     r14, [rbx+10h]
0x18003beaa  mov     r8, rdi
0x18003bead  lea     rdx, [rsp+970h+var_920]
0x18003beb2  mov     rcx, r14
0x18003beb5  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x18003beba  mov     rax, [rbx+18h]
0x18003bebe  cmp     [rsp+970h+var_920], rax
0x18003bec3  jz      short loc_18003BF3A
0x18003bec5  mov     r9d, 0B7h
0x18003becb  mov     [rsp+970h+var_930], r9d
0x18003bed0  cmp     qword ptr cs:xmmword_1800710A0+8, r12
0x18003bed7  jz      loc_18003C294
0x18003bedd  mov     word ptr [rbp+870h+var_840], r12w
0x18003bee2  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003bee9  movdqu  xmmword ptr [rbp+870h+var_8D0.Data1], xmm0
0x18003beee  mov     word ptr [rbp+870h+var_8C0], r12w
0x18003bef3  mov     r8, r13
0x18003bef6  lea     rdx, aSRoutingDomain; "%s: Routing domain already configured."
0x18003befd  lea     rcx, [rbp+870h+var_840]
0x18003bf01  call    FormatRRASErrorString
0x18003bf06  mov     rdx, qword ptr cs:xmmword_1800710A0+8
0x18003bf0d  lea     rax, [rbp+870h+var_8C0]
0x18003bf11  mov     [rsp+970h+var_948], rax
0x18003bf16  lea     r8, [rbp+870h+var_840]
0x18003bf1a  mov     r9, rdi
0x18003bf1d  mov     [rsp+970h+var_950], r12
0x18003bf22  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003bf29  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003bf30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf35  jmp     loc_18003C294
0x18003bf3a  mov     ecx, 358h; Size
0x18003bf3f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003bf44  mov     [rsp+970h+var_920], rax
0x18003bf49  test    rax, rax
0x18003bf4c  jz      short loc_18003BF6B
0x18003bf4e  movups  xmm0, xmmword ptr [rdi]
0x18003bf51  movdqu  xmmword ptr [rbp+870h+var_8D0.Data1], xmm0
0x18003bf56  lea     r8, [rbp+870h+var_8D0]; struct _GUID
0x18003bf5a  mov     rdx, [rbx+8]; HKEY
0x18003bf5e  mov     rcx, rax; this
0x18003bf61  call    ??0RRasRoutingDomainConfig@@QEAA@PEAUHKEY__@@U_GUID@@@Z; RRasRoutingDomainConfig::RRasRoutingDomainConfig(HKEY__ *,_GUID)
0x18003bf66  mov     rbx, rax
0x18003bf69  jmp     short loc_18003BF6E
0x18003bf6b  mov     rbx, r12
0x18003bf6e  test    rbx, rbx
0x18003bf71  jnz     short loc_18003BFE1
0x18003bf73  cmp     qword ptr cs:xmmword_1800710A0, r12
0x18003bf7a  jz      short loc_18003BFD4
0x18003bf7c  mov     word ptr [rbp+870h+var_840], r12w
0x18003bf81  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003bf88  movdqu  xmmword ptr [rbp+870h+var_8D0.Data1], xmm0
0x18003bf8d  mov     word ptr [rbp+870h+var_8C0], r12w
0x18003bf92  mov     r8, r13
0x18003bf95  lea     rdx, aSFailedToInsta; "%s: Failed to instantiate a Routing Dom"...
0x18003bf9c  lea     rcx, [rbp+870h+var_840]
0x18003bfa0  call    FormatRRASErrorString
0x18003bfa5  lea     rax, [rbp+870h+var_8C0]
0x18003bfa9  mov     [rsp+970h+var_948], rax
0x18003bfae  mov     [rsp+970h+var_950], r12
0x18003bfb3  mov     r9, rdi
0x18003bfb6  lea     r8, [rbp+870h+var_840]
0x18003bfba  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003bfc1  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003bfc8  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003bfcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bfd4  mov     [rsp+970h+var_930], 8
0x18003bfdc  jmp     loc_18003C294
0x18003bfe1  mov     rcx, rbx; this
0x18003bfe4  call    ?OpenConfigRegKey@RRasRoutingDomainConfig@@QEAAKXZ; RRasRoutingDomainConfig::OpenConfigRegKey(void)
0x18003bfe9  mov     r9d, eax
0x18003bfec  mov     [rsp+970h+var_930], eax
0x18003bff0  test    eax, eax
0x18003bff2  jz      short loc_18003C03C
0x18003bff4  cmp     qword ptr cs:xmmword_180071090, r12
0x18003bffb  jz      loc_18003C294
0x18003c001  lea     rdx, aSOpenconfigreg; "%s: OpenConfigRegKey failed: %d."
0x18003c008  mov     r8, r13
0x18003c00b  mov     word ptr [rbp+870h+var_840], r12w
0x18003c010  lea     rcx, [rbp+870h+var_840]
0x18003c014  call    FormatRRASErrorString
0x18003c019  lea     r8, [rbp+870h+var_840]
0x18003c01d  mov     rdx, qword ptr cs:xmmword_180071090
0x18003c024  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003c02b  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003c032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c037  jmp     loc_18003C294
0x18003c03c  mov     rcx, rbx; this
0x18003c03f  call    ?CreateLoopbackInterface@RRasRoutingDomainConfig@@QEAAKXZ; RRasRoutingDomainConfig::CreateLoopbackInterface(void)
0x18003c044  mov     r9d, eax
0x18003c047  mov     [rsp+970h+var_930], eax
0x18003c04b  test    eax, eax
0x18003c04d  jz      short loc_18003C065
0x18003c04f  cmp     qword ptr cs:xmmword_180071090, r12
0x18003c056  jz      loc_18003C294
0x18003c05c  lea     rdx, aSCreateloopbac; "%s: CreateLoopbackInterface failed: %d."
0x18003c063  jmp     short loc_18003C008
0x18003c065  mov     rcx, rbx; this
0x18003c068  call    ?PersistConfig@RRasRoutingDomainConfig@@QEAAKXZ; RRasRoutingDomainConfig::PersistConfig(void)
0x18003c06d  mov     [rsp+970h+var_930], eax
0x18003c071  test    eax, eax
0x18003c073  jz      short loc_18003C0BF
0x18003c075  cmp     qword ptr cs:xmmword_1800710A0, r12
0x18003c07c  jz      loc_18003C294
0x18003c082  mov     word ptr [rbp+870h+var_840], r12w
0x18003c087  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003c08e  movdqu  xmmword ptr [rbp+870h+var_8D0.Data1], xmm0
0x18003c093  mov     word ptr [rbp+870h+var_8C0], r12w
0x18003c098  mov     dword ptr [rsp+970h+var_950], eax
0x18003c09c  lea     r9, [rbp+870h+var_890]
0x18003c0a0  mov     r8, r13
0x18003c0a3  lea     rdx, aSRdconfigPersi; "%s: rdConfig->PersistConfig failed for "...
0x18003c0aa  lea     rcx, [rbp+870h+var_840]
0x18003c0ae  call    FormatRRASErrorString
0x18003c0b3  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003c0ba  jmp     loc_18003BF0D
0x18003c0bf  lea     rdx, [rsp+970h+lpMem]; unsigned __int8 **
0x18003c0c4  lea     rcx, [rsp+970h+var_92C]; unsigned int *
0x18003c0c9  call    ?CreateIpv4TransportInfo@@YAKPEAKPEAPEAE@Z; CreateIpv4TransportInfo(ulong *,uchar * *)
0x18003c0ce  mov     rsi, [rsp+970h+lpMem]
0x18003c0d3  test    rsi, rsi
0x18003c0d6  jz      loc_18003C19A
0x18003c0dc  mov     dword ptr [rsp+970h+var_920], 21h ; '!'
0x18003c0e4  mov     eax, [rsp+970h+var_92C]
0x18003c0e8  mov     dword ptr [rsp+970h+var_920+4], eax
0x18003c0ec  mov     [rsp+970h+var_918], rsi
0x18003c0f1  lea     rax, [rsp+970h+var_920]
0x18003c0f6  mov     [rsp+970h+var_950], rax
0x18003c0fb  mov     edx, 20h ; ' '
0x18003c100  lea     r9d, [rdx-10h]
0x18003c104  lea     r8d, [rdx-1Fh]
0x18003c108  mov     rcx, rbx
0x18003c10b  call    ?SetConfigParam@RRasRoutingDomainConfig@@QEAAKW4_RRAS_RD_CONFIG_TYPE@@HKPEAX@Z; RRasRoutingDomainConfig::SetConfigParam(_RRAS_RD_CONFIG_TYPE,int,ulong,void *)
0x18003c110  mov     ecx, [rsp+970h+var_930]
0x18003c114  test    ecx, ecx
0x18003c116  jz      short loc_18003C186
0x18003c118  cmp     qword ptr cs:xmmword_1800710A0, r12
0x18003c11f  jz      short loc_18003C181
0x18003c121  mov     word ptr [rbp+870h+var_840], r12w
0x18003c126  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003c12d  movdqu  xmmword ptr [rbp+870h+var_8D0.Data1], xmm0
0x18003c132  mov     word ptr [rbp+870h+var_8C0], r12w
0x18003c137  mov     dword ptr [rsp+970h+var_950], ecx
0x18003c13b  lea     r9, [rbp+870h+var_890]
0x18003c13f  mov     r8, r13
0x18003c142  lea     rdx, aSRdconfigSetco_0; "%s: rdConfig->SetConfigParam (ipv4 tran"...
0x18003c149  lea     rcx, [rbp+870h+var_840]
0x18003c14d  call    FormatRRASErrorString
0x18003c152  lea     rax, [rbp+870h+var_8C0]
0x18003c156  mov     [rsp+970h+var_948], rax
0x18003c15b  mov     [rsp+970h+var_950], r12
0x18003c160  mov     r9, rdi
0x18003c163  lea     r8, [rbp+870h+var_840]
0x18003c167  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003c16e  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003c175  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003c17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c181  mov     [rsp+970h+var_930], r12d
0x18003c186  call    cs:__imp_GetProcessHeap
0x18003c18c  mov     r8, rsi; lpMem
0x18003c18f  xor     edx, edx; dwFlags
0x18003c191  mov     rcx, rax; hHeap
0x18003c194  call    cs:__imp_HeapFree
0x18003c19a  mov     [rsp+970h+var_92C], r12d
0x18003c19f  mov     [rsp+970h+lpMem], r12
0x18003c1a4  lea     rdx, [rsp+970h+lpMem]; unsigned __int8 **
0x18003c1a9  lea     rcx, [rsp+970h+var_92C]; unsigned int *
0x18003c1ae  call    ?CreateIpv6TransportInfo@@YAKPEAKPEAPEAE@Z; CreateIpv6TransportInfo(ulong *,uchar * *)
0x18003c1b3  mov     rsi, [rsp+970h+lpMem]
0x18003c1b8  test    rsi, rsi
0x18003c1bb  jz      loc_18003C27F
0x18003c1c1  mov     dword ptr [rsp+970h+var_920], 57h ; 'W'
0x18003c1c9  mov     eax, [rsp+970h+var_92C]
0x18003c1cd  mov     dword ptr [rsp+970h+var_920+4], eax
0x18003c1d1  mov     [rsp+970h+var_918], rsi
0x18003c1d6  lea     rax, [rsp+970h+var_920]
0x18003c1db  mov     [rsp+970h+var_950], rax
0x18003c1e0  mov     edx, 80h
0x18003c1e5  lea     r9d, [rdx-70h]
0x18003c1e9  lea     r8d, [rdx-7Fh]
0x18003c1ed  mov     rcx, rbx
0x18003c1f0  call    ?SetConfigParam@RRasRoutingDomainConfig@@QEAAKW4_RRAS_RD_CONFIG_TYPE@@HKPEAX@Z; RRasRoutingDomainConfig::SetConfigParam(_RRAS_RD_CONFIG_TYPE,int,ulong,void *)
0x18003c1f5  mov     ecx, [rsp+970h+var_930]
0x18003c1f9  test    ecx, ecx
0x18003c1fb  jz      short loc_18003C26B
0x18003c1fd  cmp     qword ptr cs:xmmword_1800710A0, r12
0x18003c204  jz      short loc_18003C266
0x18003c206  mov     word ptr [rbp+870h+var_840], r12w
0x18003c20b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003c212  movdqu  xmmword ptr [rbp+870h+var_8D0.Data1], xmm0
0x18003c217  mov     word ptr [rbp+870h+var_8C0], r12w
0x18003c21c  mov     dword ptr [rsp+970h+var_950], ecx
0x18003c220  lea     r9, [rbp+870h+var_890]
0x18003c224  mov     r8, r13
0x18003c227  lea     rdx, aSRdconfigSetco; "%s: rdConfig->SetConfigParam (ipv6 tran"...
0x18003c22e  lea     rcx, [rbp+870h+var_840]
0x18003c232  call    FormatRRASErrorString
0x18003c237  lea     rax, [rbp+870h+var_8C0]
0x18003c23b  mov     [rsp+970h+var_948], rax
0x18003c240  mov     [rsp+970h+var_950], r12
0x18003c245  mov     r9, rdi
0x18003c248  lea     r8, [rbp+870h+var_840]
0x18003c24c  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003c253  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003c25a  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003c261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c266  mov     [rsp+970h+var_930], r12d
0x18003c26b  call    cs:__imp_GetProcessHeap
0x18003c271  mov     r8, rsi; lpMem
0x18003c274  xor     edx, edx; dwFlags
0x18003c276  mov     rcx, rax; hHeap
0x18003c279  call    cs:__imp_HeapFree
0x18003c27f  or      dword ptr [rbx+214h], 2
0x18003c286  mov     rdx, rdi
0x18003c289  mov     rcx, r14
0x18003c28c  call    ??A?$unordered_map@U_GUID@@PEAVRRasRoutingDomainConfig@@UGuidHash@@UGuidEquality@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@std@@@tr1@std@@QEAAAEAPEAVRRasRoutingDomainConfig@@AEBU_GUID@@@Z; std::tr1::unordered_map<_GUID,RRasRoutingDomainConfig *,GuidHash,GuidEquality,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>>::operator[](_GUID const &)
0x18003c291  mov     [rax], rbx
0x18003c294  mov     rcx, r15; Resource
0x18003c297  call    cs:__imp_RtlReleaseResource
0x18003c29d  mov     ebx, [rsp+970h+var_930]
0x18003c2a1  lea     rcx, [rsp+970h+var_910]; this
0x18003c2a6  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003c2ab  mov     eax, ebx
0x18003c2ad  mov     rcx, [rbp+870h+var_40]
0x18003c2b4  xor     rcx, rsp; StackCookie
0x18003c2b7  call    __security_check_cookie
0x18003c2bc  mov     rbx, [rsp+970h+arg_10]
  ... truncated ...
```
