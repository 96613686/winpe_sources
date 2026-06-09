# RRasConfigStore::EnumerateRoutingDomains(ulong,ulong *,_MPRI_ROUTING_DOMAIN_INFO_EX * *)

- ea: `0x18003c2e0`
- end: `0x18003c602`
- name: `?EnumerateRoutingDomains@RRasConfigStore@@QEAAKKPEAKPEAPEAU_MPRI_ROUTING_DOMAIN_INFO_EX@@@Z`
- size: `802`
- prototype: `__int64 __fastcall(RRasConfigStore *this, int, unsigned int *, struct _MPRI_ROUTING_DOMAIN_INFO_EX **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x1800357c8`

## callees

- `0x18003c2e0`
- `0x18003d170`
- `0x18004583c`
- `0x180045ad4`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18003c4db`
- `ntdll!RtlReleaseResource` at `0x18003c531`
- `ntdll!RtlReleaseResource` at `0x18003c573`
- `ntdll!RtlReleaseResource` at `0x18003c4db`
- `ntdll!RtlReleaseResource` at `0x18003c531`
- `ntdll!RtlReleaseResource` at `0x18003c573`
- `ntdll!RtlAcquireResourceShared` at `0x18003c3a5`
- `ntdll!RtlAcquireResourceShared` at `0x18003c4aa`
- `ntdll!RtlAcquireResourceShared` at `0x18003c3a5`
- `ntdll!RtlAcquireResourceShared` at `0x18003c4aa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c42c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c42c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c557`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c557`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003c416`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003c416`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c541`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c541`
- `KERNEL32!GetProcessHeap` at `0x18003c41e`
- `KERNEL32!GetProcessHeap` at `0x18003c549`
- `KERNEL32!GetProcessHeap` at `0x18003c41e`
- `KERNEL32!GetProcessHeap` at `0x18003c549`

## string_xrefs

- `0x18003c37c`: `RRasConfigStore::EnumerateRoutingDomains`
- `0x18003c3cb`: `RRasConfigStore::EnumerateRoutingDomains`
- `0x18003c449`: `RRasConfigStore::EnumerateRoutingDomains`
- `0x18003c4f7`: `RRasConfigStore::EnumerateRoutingDomains`
- `0x18003c598`: `RRasConfigStore::EnumerateRoutingDomains`
- `0x18003c3d2`: `%s: No routing domain configured.`

## pseudocode

```c
__int64 __fastcall RRasConfigStore::EnumerateRoutingDomains(
        RRasConfigStore *this,
        int a2,
        unsigned int *a3,
        struct _MPRI_ROUTING_DOMAIN_INFO_EX **a4)
{
  unsigned int v8; // r14d
  void (*v9)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  SIZE_T v10; // rbx
  struct _MPRI_ROUTING_DOMAIN_INFO_EX *v11; // rax
  HANDLE ProcessHeap; // rax
  struct _MPRI_ROUTING_DOMAIN_INFO_EX *v13; // rsi
  _QWORD *v14; // rbx
  __int64 v15; // rdi
  unsigned int Info; // eax
  HANDLE v17; // rax
  unsigned int v18; // ebx
  unsigned int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  unsigned int *v22; // [rsp+28h] [rbp-D8h]
  struct _MPRI_ROUTING_DOMAIN_INFO_EX **v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v25; // [rsp+40h] [rbp-C0h]
  __int128 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+68h] [rbp-98h]
  int v29; // [rsp+6Ch] [rbp-94h]
  int v30; // [rsp+70h] [rbp-90h] BYREF
  char v31[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v23 = a4;
  v22 = a3;
  v21 = a2;
  v8 = 0;
  v20 = 0;
  v30 = 0;
  memset_0(v31, 0, sizeof(v31));
  v25 = 0;
  v24 = 0;
  v26 = 0;
  v27 = 0;
  v28 = -1;
  v29 = 0;
  if ( *((_QWORD *)&xmmword_180071090 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v24,
      L"RRasConfigStore::EnumerateRoutingDomains",
      &v20,
      v9);
  if ( a3 && a4 )
  {
    RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 112), 1u);
    v10 = 540LL * *((_QWORD *)this + 4);
    if ( v10 )
    {
      if ( a2 >= 0 )
      {
        ProcessHeap = GetProcessHeap();
        v11 = (struct _MPRI_ROUTING_DOMAIN_INFO_EX *)HeapAlloc(ProcessHeap, 8u, v10);
      }
      else
      {
        v11 = (struct _MPRI_ROUTING_DOMAIN_INFO_EX *)LocalAlloc(0x40u, 540LL * *((_QWORD *)this + 4));
      }
      v13 = v11;
      if ( v11 )
      {
        v14 = (_QWORD *)*((_QWORD *)this + 3);
        while ( 1 )
        {
          v14 = (_QWORD *)*v14;
          if ( v14 == *((_QWORD **)this + 3) )
          {
            *v22 = v8;
            *v23 = v13;
            goto LABEL_25;
          }
          v15 = v14[4];
          RtlAcquireResourceShared((PRTL_RESOURCE)(v15 + 728), 1u);
          Info = RRasRoutingDomainConfig::GetInfo(
                   (STRSAFE_LPCWSTR)v15,
                   v21 & 0x7FFFFFFF,
                   (struct _MPRI_ROUTING_DOMAIN_INFO_EX *)((char *)v13 + 540 * v8));
          v20 = Info;
          if ( Info )
            break;
          RtlReleaseResource((PRTL_RESOURCE)(v15 + 728));
          ++v8;
        }
        if ( (_QWORD)xmmword_180071090 )
        {
          LOWORD(v30) = 0;
          FormatRRASErrorString(
            &v30,
            L"%s: pRdObject->GetInfo failed: %d.",
            L"RRasConfigStore::EnumerateRoutingDomains",
            Info);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
            gCfgStoreEtwContext,
            xmmword_180071090,
            &v30);
        }
        RtlReleaseResource((PRTL_RESOURCE)(v15 + 728));
        if ( v21 >= 0 )
        {
          v17 = GetProcessHeap();
          HeapFree(v17, 0, v13);
        }
        else
        {
          LocalFree(v13);
        }
      }
      else
      {
        if ( (_QWORD)xmmword_180071090 )
        {
          LOWORD(v30) = 0;
          FormatRRASErrorString(
            &v30,
            L"%s: EnumerateRoutingDomains: Malloc failed.",
            L"RRasConfigStore::EnumerateRoutingDomains");
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
            gCfgStoreEtwContext,
            xmmword_180071090,
            &v30);
        }
        v20 = 8;
      }
    }
    else if ( *((_QWORD *)&xmmword_180071090 + 1) )
    {
      LOWORD(v30) = 0;
      FormatRRASErrorString(&v30, L"%s: No routing domain configured.", L"RRasConfigStore::EnumerateRoutingDomains");
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        *((_QWORD *)&xmmword_180071090 + 1),
        &v30);
    }
LABEL_25:
    RtlReleaseResource((PRTL_RESOURCE)((char *)this + 112));
  }
  else
  {
    v20 = 87;
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v30) = 0;
      FormatRRASErrorString(&v30, L"%hs(Line#%d): Invalid parameter.", "RRasConfigStore::EnumerateRoutingDomains", 358);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v30);
    }
  }
  v18 = v20;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v24);
  return v18;
}

```

## disassembly

```asm
0x18003c2e0  push    rbp
0x18003c2e2  push    rbx
0x18003c2e3  push    rsi
0x18003c2e4  push    rdi
0x18003c2e5  push    r12
0x18003c2e7  push    r13
0x18003c2e9  push    r14
0x18003c2eb  push    r15
0x18003c2ed  lea     rbp, [rsp-788h]
0x18003c2f5  sub     rsp, 888h
0x18003c2fc  mov     rax, cs:__security_cookie
0x18003c303  xor     rax, rsp
0x18003c306  mov     [rbp+7C0h+var_50], rax
0x18003c30d  mov     r12, r9
0x18003c310  mov     [rsp+8C0h+var_890], r9
0x18003c315  mov     rdi, r8
0x18003c318  mov     [rsp+8C0h+var_898], r8
0x18003c31d  mov     esi, edx
0x18003c31f  mov     [rsp+8C0h+var_89C], edx
0x18003c323  mov     r15, rcx
0x18003c326  xor     r14d, r14d
0x18003c329  mov     [rsp+8C0h+var_8A0], r14d
0x18003c32e  mov     [rsp+8C0h+var_850], r14d
0x18003c333  xor     edx, edx; Val
0x18003c335  mov     r8d, 7FCh; Size
0x18003c33b  lea     rcx, [rsp+8C0h+var_84C]; void *
0x18003c340  call    memset_0
0x18003c345  xorps   xmm0, xmm0
0x18003c348  movdqu  [rsp+8C0h+var_880], xmm0
0x18003c34e  mov     [rsp+8C0h+var_888], r14
0x18003c353  xorps   xmm1, xmm1
0x18003c356  movdqu  [rsp+8C0h+var_870], xmm1
0x18003c35c  mov     [rsp+8C0h+var_860], r14
0x18003c361  mov     [rsp+8C0h+var_858], 0FFFFFFFFh
0x18003c369  mov     [rsp+8C0h+var_854], r14d
0x18003c36e  cmp     qword ptr cs:xmmword_180071090+8, r14
0x18003c375  jz      short loc_18003C38D
0x18003c377  lea     r8, [rsp+8C0h+var_8A0]; unsigned int *
0x18003c37c  lea     rdx, aRrasconfigstor_33; "RRasConfigStore::EnumerateRoutingDomain"...
0x18003c383  lea     rcx, [rsp+8C0h+var_888]; this
0x18003c388  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18003c38d  test    rdi, rdi
0x18003c390  jz      loc_18003C57B
0x18003c396  test    r12, r12
0x18003c399  jz      loc_18003C57B
0x18003c39f  mov     dl, 1; Wait
0x18003c3a1  lea     rcx, [r15+70h]; Resource
0x18003c3a5  call    cs:__imp_RtlAcquireResourceShared
0x18003c3ab  imul    rbx, [r15+20h], 21Ch
0x18003c3b3  test    rbx, rbx
0x18003c3b6  jnz     short loc_18003C407
0x18003c3b8  cmp     qword ptr cs:xmmword_180071090+8, r14
0x18003c3bf  jz      loc_18003C56F
0x18003c3c5  mov     word ptr [rsp+8C0h+var_850], r14w
0x18003c3cb  lea     r8, aRrasconfigstor_33; "RRasConfigStore::EnumerateRoutingDomain"...
0x18003c3d2  lea     rdx, aSNoRoutingDoma_1; "%s: No routing domain configured."
0x18003c3d9  lea     rcx, [rsp+8C0h+var_850]
0x18003c3de  call    FormatRRASErrorString
0x18003c3e3  lea     r8, [rsp+8C0h+var_850]
0x18003c3e8  mov     rdx, qword ptr cs:xmmword_180071090+8
0x18003c3ef  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003c3f6  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003c3fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c402  jmp     loc_18003C56F
0x18003c407  mov     edi, 8
0x18003c40c  test    esi, esi
0x18003c40e  jns     short loc_18003C41E
0x18003c410  mov     rdx, rbx; uBytes
0x18003c413  lea     ecx, [rdi+38h]; uFlags
0x18003c416  call    cs:__imp_LocalAlloc
0x18003c41c  jmp     short loc_18003C432
0x18003c41e  call    cs:__imp_GetProcessHeap
0x18003c424  mov     rcx, rax; hHeap
0x18003c427  mov     r8, rbx; dwBytes
0x18003c42a  mov     edx, edi; dwFlags
0x18003c42c  call    cs:__imp_HeapAlloc
0x18003c432  mov     rsi, rax
0x18003c435  test    rax, rax
0x18003c438  jnz     short loc_18003C489
0x18003c43a  cmp     qword ptr cs:xmmword_180071090, r14
0x18003c441  jz      short loc_18003C480
0x18003c443  mov     word ptr [rsp+8C0h+var_850], r14w
0x18003c449  lea     r8, aRrasconfigstor_33; "RRasConfigStore::EnumerateRoutingDomain"...
0x18003c450  lea     rdx, aSEnumeraterout; "%s: EnumerateRoutingDomains: Malloc fai"...
0x18003c457  lea     rcx, [rsp+8C0h+var_850]
0x18003c45c  call    FormatRRASErrorString
0x18003c461  lea     r8, [rsp+8C0h+var_850]
0x18003c466  mov     rdx, qword ptr cs:xmmword_180071090
0x18003c46d  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003c474  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003c47b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c480  mov     [rsp+8C0h+var_8A0], edi
0x18003c484  jmp     loc_18003C56F
0x18003c489  mov     rbx, [r15+18h]
0x18003c48d  mov     rbx, [rbx]
0x18003c490  cmp     rbx, [r15+18h]
0x18003c494  jz      loc_18003C55F
0x18003c49a  mov     rdi, [rbx+20h]
0x18003c49e  lea     r12, [rdi+2D8h]
0x18003c4a5  mov     dl, 1; Wait
0x18003c4a7  mov     rcx, r12; Resource
0x18003c4aa  call    cs:__imp_RtlAcquireResourceShared
0x18003c4b0  mov     eax, r14d
0x18003c4b3  imul    r8, rax, 21Ch
0x18003c4ba  add     r8, rsi; struct _MPRI_ROUTING_DOMAIN_INFO_EX *
0x18003c4bd  mov     edx, [rsp+8C0h+var_89C]
0x18003c4c1  btr     edx, 1Fh; unsigned int
0x18003c4c5  mov     rcx, rdi; pszSrc
0x18003c4c8  call    ?GetInfo@RRasRoutingDomainConfig@@QEAAKKPEAU_MPRI_ROUTING_DOMAIN_INFO_EX@@@Z; RRasRoutingDomainConfig::GetInfo(ulong,_MPRI_ROUTING_DOMAIN_INFO_EX *)
0x18003c4cd  mov     r9d, eax
0x18003c4d0  mov     [rsp+8C0h+var_8A0], eax
0x18003c4d4  test    eax, eax
0x18003c4d6  jnz     short loc_18003C4E6
0x18003c4d8  mov     rcx, r12; Resource
0x18003c4db  call    cs:__imp_RtlReleaseResource
0x18003c4e1  inc     r14d
0x18003c4e4  jmp     short loc_18003C48D
0x18003c4e6  cmp     qword ptr cs:xmmword_180071090, 0
0x18003c4ee  jz      short loc_18003C52E
0x18003c4f0  xor     eax, eax
0x18003c4f2  mov     word ptr [rsp+8C0h+var_850], ax
0x18003c4f7  lea     r8, aRrasconfigstor_33; "RRasConfigStore::EnumerateRoutingDomain"...
0x18003c4fe  lea     rdx, aSPrdobjectGeti; "%s: pRdObject->GetInfo failed: %d."
0x18003c505  lea     rcx, [rsp+8C0h+var_850]
0x18003c50a  call    FormatRRASErrorString
0x18003c50f  lea     r8, [rsp+8C0h+var_850]
0x18003c514  mov     rdx, qword ptr cs:xmmword_180071090
0x18003c51b  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003c522  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003c529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c52e  mov     rcx, r12; Resource
0x18003c531  call    cs:__imp_RtlReleaseResource
0x18003c537  cmp     [rsp+8C0h+var_89C], 0
0x18003c53c  jge     short loc_18003C549
0x18003c53e  mov     rcx, rsi; hMem
0x18003c541  call    cs:__imp_LocalFree
0x18003c547  jmp     short loc_18003C56F
0x18003c549  call    cs:__imp_GetProcessHeap
0x18003c54f  mov     rcx, rax; hHeap
0x18003c552  mov     r8, rsi; lpMem
0x18003c555  xor     edx, edx; dwFlags
0x18003c557  call    cs:__imp_HeapFree
0x18003c55d  jmp     short loc_18003C56F
0x18003c55f  mov     rax, [rsp+8C0h+var_898]
0x18003c564  mov     [rax], r14d
0x18003c567  mov     rax, [rsp+8C0h+var_890]
0x18003c56c  mov     [rax], rsi
0x18003c56f  lea     rcx, [r15+70h]; Resource
0x18003c573  call    cs:__imp_RtlReleaseResource
0x18003c579  jmp     short loc_18003C5CF
0x18003c57b  mov     [rsp+8C0h+var_8A0], 57h ; 'W'
0x18003c583  cmp     qword ptr cs:xmmword_180071090, r14
0x18003c58a  jz      short loc_18003C5CF
0x18003c58c  mov     word ptr [rsp+8C0h+var_850], r14w
0x18003c592  mov     r9d, 166h
0x18003c598  lea     r8, aRrasconfigstor_26; "RRasConfigStore::EnumerateRoutingDomain"...
0x18003c59f  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18003c5a6  lea     rcx, [rsp+8C0h+var_850]
0x18003c5ab  call    FormatRRASErrorString
0x18003c5b0  lea     r8, [rsp+8C0h+var_850]
0x18003c5b5  mov     rdx, qword ptr cs:xmmword_180071090
0x18003c5bc  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003c5c3  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003c5ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5cf  mov     ebx, [rsp+8C0h+var_8A0]
0x18003c5d3  lea     rcx, [rsp+8C0h+var_888]; this
0x18003c5d8  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003c5dd  mov     eax, ebx
0x18003c5df  mov     rcx, [rbp+7C0h+var_50]
0x18003c5e6  xor     rcx, rsp; StackCookie
0x18003c5e9  call    __security_check_cookie
0x18003c5ee  add     rsp, 888h
0x18003c5f5  pop     r15
0x18003c5f7  pop     r14
0x18003c5f9  pop     r13
0x18003c5fb  pop     r12
0x18003c5fd  pop     rdi
0x18003c5fe  pop     rsi
0x18003c5ff  pop     rbx
0x18003c600  pop     rbp
0x18003c601  retn
```
