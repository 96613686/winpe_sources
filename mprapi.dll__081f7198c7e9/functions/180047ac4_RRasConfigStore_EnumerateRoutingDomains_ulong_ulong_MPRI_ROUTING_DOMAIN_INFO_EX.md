# RRasConfigStore::EnumerateRoutingDomains(ulong,ulong *,_MPRI_ROUTING_DOMAIN_INFO_EX * *)

- ea: `0x180047ac4`
- end: `0x180047de6`
- name: `?EnumerateRoutingDomains@RRasConfigStore@@QEAAKKPEAKPEAPEAU_MPRI_ROUTING_DOMAIN_INFO_EX@@@Z`
- size: `802`
- prototype: `__int64 __fastcall(RRasConfigStore *this, int, unsigned int *, struct _MPRI_ROUTING_DOMAIN_INFO_EX **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180041208`

## callees

- `0x180047ac4`
- `0x180048954`
- `0x180050b2c`
- `0x180050cd4`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047bfa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047bfa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047d25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047d25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047c02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047d2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047c02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047d2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180047c10`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180047c10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047d3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047d3b`
- `ntdll!RtlAcquireResourceShared` at `0x180047b89`
- `ntdll!RtlAcquireResourceShared` at `0x180047c8e`
- `ntdll!RtlAcquireResourceShared` at `0x180047b89`
- `ntdll!RtlAcquireResourceShared` at `0x180047c8e`
- `ntdll!RtlReleaseResource` at `0x180047cbf`
- `ntdll!RtlReleaseResource` at `0x180047d15`
- `ntdll!RtlReleaseResource` at `0x180047d57`
- `ntdll!RtlReleaseResource` at `0x180047cbf`
- `ntdll!RtlReleaseResource` at `0x180047d15`
- `ntdll!RtlReleaseResource` at `0x180047d57`

## string_xrefs

- `0x180047b60`: `RRasConfigStore::EnumerateRoutingDomains`
- `0x180047baf`: `RRasConfigStore::EnumerateRoutingDomains`
- `0x180047c2d`: `RRasConfigStore::EnumerateRoutingDomains`
- `0x180047cdb`: `RRasConfigStore::EnumerateRoutingDomains`
- `0x180047d7c`: `RRasConfigStore::EnumerateRoutingDomains`
- `0x180047bb6`: `%s: No routing domain configured.`

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
  if ( *((_QWORD *)&xmmword_180078C50 + 1) )
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
                   (RRasRoutingDomainConfig *)v15,
                   v21 & 0x7FFFFFFF,
                   (struct _MPRI_ROUTING_DOMAIN_INFO_EX *)((char *)v13 + 540 * v8));
          v20 = Info;
          if ( Info )
            break;
          RtlReleaseResource((PRTL_RESOURCE)(v15 + 728));
          ++v8;
        }
        if ( (_QWORD)xmmword_180078C50 )
        {
          LOWORD(v30) = 0;
          FormatRRASErrorString(
            &v30,
            L"%s: pRdObject->GetInfo failed: %d.",
            L"RRasConfigStore::EnumerateRoutingDomains",
            Info);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
            gCfgStoreEtwContext,
            xmmword_180078C50,
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
        if ( (_QWORD)xmmword_180078C50 )
        {
          LOWORD(v30) = 0;
          FormatRRASErrorString(
            &v30,
            L"%s: EnumerateRoutingDomains: Malloc failed.",
            L"RRasConfigStore::EnumerateRoutingDomains");
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
            gCfgStoreEtwContext,
            xmmword_180078C50,
            &v30);
        }
        v20 = 8;
      }
    }
    else if ( *((_QWORD *)&xmmword_180078C50 + 1) )
    {
      LOWORD(v30) = 0;
      FormatRRASErrorString(&v30, L"%s: No routing domain configured.", L"RRasConfigStore::EnumerateRoutingDomains");
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        *((_QWORD *)&xmmword_180078C50 + 1),
        &v30);
    }
LABEL_25:
    RtlReleaseResource((PRTL_RESOURCE)((char *)this + 112));
  }
  else
  {
    v20 = 87;
    if ( (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v30) = 0;
      FormatRRASErrorString(&v30, L"%hs(Line#%d): Invalid parameter.", "RRasConfigStore::EnumerateRoutingDomains", 358);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C50,
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
0x180047ac4  push    rbp
0x180047ac6  push    rbx
0x180047ac7  push    rsi
0x180047ac8  push    rdi
0x180047ac9  push    r12
0x180047acb  push    r13
0x180047acd  push    r14
0x180047acf  push    r15
0x180047ad1  lea     rbp, [rsp-788h]
0x180047ad9  sub     rsp, 888h
0x180047ae0  mov     rax, cs:__security_cookie
0x180047ae7  xor     rax, rsp
0x180047aea  mov     [rbp+7C0h+var_50], rax
0x180047af1  mov     r12, r9
0x180047af4  mov     [rsp+8C0h+var_890], r9
0x180047af9  mov     rdi, r8
0x180047afc  mov     [rsp+8C0h+var_898], r8
0x180047b01  mov     esi, edx
0x180047b03  mov     [rsp+8C0h+var_89C], edx
0x180047b07  mov     r15, rcx
0x180047b0a  xor     r14d, r14d
0x180047b0d  mov     [rsp+8C0h+var_8A0], r14d
0x180047b12  mov     [rsp+8C0h+var_850], r14d
0x180047b17  xor     edx, edx; Val
0x180047b19  mov     r8d, 7FCh; Size
0x180047b1f  lea     rcx, [rsp+8C0h+var_84C]; void *
0x180047b24  call    memset_0
0x180047b29  xorps   xmm0, xmm0
0x180047b2c  movdqu  [rsp+8C0h+var_880], xmm0
0x180047b32  mov     [rsp+8C0h+var_888], r14
0x180047b37  xorps   xmm1, xmm1
0x180047b3a  movdqu  [rsp+8C0h+var_870], xmm1
0x180047b40  mov     [rsp+8C0h+var_860], r14
0x180047b45  mov     [rsp+8C0h+var_858], 0FFFFFFFFh
0x180047b4d  mov     [rsp+8C0h+var_854], r14d
0x180047b52  cmp     qword ptr cs:xmmword_180078C50+8, r14
0x180047b59  jz      short loc_180047B71
0x180047b5b  lea     r8, [rsp+8C0h+var_8A0]; unsigned int *
0x180047b60  lea     rdx, aRrasconfigstor_27; "RRasConfigStore::EnumerateRoutingDomain"...
0x180047b67  lea     rcx, [rsp+8C0h+var_888]; this
0x180047b6c  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180047b71  test    rdi, rdi
0x180047b74  jz      loc_180047D5F
0x180047b7a  test    r12, r12
0x180047b7d  jz      loc_180047D5F
0x180047b83  mov     dl, 1; Wait
0x180047b85  lea     rcx, [r15+70h]; Resource
0x180047b89  call    cs:__imp_RtlAcquireResourceShared
0x180047b8f  imul    rbx, [r15+20h], 21Ch
0x180047b97  test    rbx, rbx
0x180047b9a  jnz     short loc_180047BEB
0x180047b9c  cmp     qword ptr cs:xmmword_180078C50+8, r14
0x180047ba3  jz      loc_180047D53
0x180047ba9  mov     word ptr [rsp+8C0h+var_850], r14w
0x180047baf  lea     r8, aRrasconfigstor_27; "RRasConfigStore::EnumerateRoutingDomain"...
0x180047bb6  lea     rdx, aSNoRoutingDoma_1; "%s: No routing domain configured."
0x180047bbd  lea     rcx, [rsp+8C0h+var_850]
0x180047bc2  call    FormatRRASErrorString
0x180047bc7  lea     r8, [rsp+8C0h+var_850]
0x180047bcc  mov     rdx, qword ptr cs:xmmword_180078C50+8
0x180047bd3  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180047bda  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180047be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047be6  jmp     loc_180047D53
0x180047beb  mov     edi, 8
0x180047bf0  test    esi, esi
0x180047bf2  jns     short loc_180047C02
0x180047bf4  mov     rdx, rbx; uBytes
0x180047bf7  lea     ecx, [rdi+38h]; uFlags
0x180047bfa  call    cs:__imp_LocalAlloc
0x180047c00  jmp     short loc_180047C16
0x180047c02  call    cs:__imp_GetProcessHeap
0x180047c08  mov     rcx, rax; hHeap
0x180047c0b  mov     r8, rbx; dwBytes
0x180047c0e  mov     edx, edi; dwFlags
0x180047c10  call    cs:__imp_HeapAlloc
0x180047c16  mov     rsi, rax
0x180047c19  test    rax, rax
0x180047c1c  jnz     short loc_180047C6D
0x180047c1e  cmp     qword ptr cs:xmmword_180078C50, r14
0x180047c25  jz      short loc_180047C64
0x180047c27  mov     word ptr [rsp+8C0h+var_850], r14w
0x180047c2d  lea     r8, aRrasconfigstor_27; "RRasConfigStore::EnumerateRoutingDomain"...
0x180047c34  lea     rdx, aSEnumeraterout; "%s: EnumerateRoutingDomains: Malloc fai"...
0x180047c3b  lea     rcx, [rsp+8C0h+var_850]
0x180047c40  call    FormatRRASErrorString
0x180047c45  lea     r8, [rsp+8C0h+var_850]
0x180047c4a  mov     rdx, qword ptr cs:xmmword_180078C50
0x180047c51  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180047c58  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180047c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047c64  mov     [rsp+8C0h+var_8A0], edi
0x180047c68  jmp     loc_180047D53
0x180047c6d  mov     rbx, [r15+18h]
0x180047c71  mov     rbx, [rbx]
0x180047c74  cmp     rbx, [r15+18h]
0x180047c78  jz      loc_180047D43
0x180047c7e  mov     rdi, [rbx+20h]
0x180047c82  lea     r12, [rdi+2D8h]
0x180047c89  mov     dl, 1; Wait
0x180047c8b  mov     rcx, r12; Resource
0x180047c8e  call    cs:__imp_RtlAcquireResourceShared
0x180047c94  mov     eax, r14d
0x180047c97  imul    r8, rax, 21Ch
0x180047c9e  add     r8, rsi; struct _MPRI_ROUTING_DOMAIN_INFO_EX *
0x180047ca1  mov     edx, [rsp+8C0h+var_89C]
0x180047ca5  btr     edx, 1Fh; unsigned int
0x180047ca9  mov     rcx, rdi; this
0x180047cac  call    ?GetInfo@RRasRoutingDomainConfig@@QEAAKKPEAU_MPRI_ROUTING_DOMAIN_INFO_EX@@@Z; RRasRoutingDomainConfig::GetInfo(ulong,_MPRI_ROUTING_DOMAIN_INFO_EX *)
0x180047cb1  mov     r9d, eax
0x180047cb4  mov     [rsp+8C0h+var_8A0], eax
0x180047cb8  test    eax, eax
0x180047cba  jnz     short loc_180047CCA
0x180047cbc  mov     rcx, r12; Resource
0x180047cbf  call    cs:__imp_RtlReleaseResource
0x180047cc5  inc     r14d
0x180047cc8  jmp     short loc_180047C71
0x180047cca  cmp     qword ptr cs:xmmword_180078C50, 0
0x180047cd2  jz      short loc_180047D12
0x180047cd4  xor     eax, eax
0x180047cd6  mov     word ptr [rsp+8C0h+var_850], ax
0x180047cdb  lea     r8, aRrasconfigstor_27; "RRasConfigStore::EnumerateRoutingDomain"...
0x180047ce2  lea     rdx, aSPrdobjectGeti; "%s: pRdObject->GetInfo failed: %d."
0x180047ce9  lea     rcx, [rsp+8C0h+var_850]
0x180047cee  call    FormatRRASErrorString
0x180047cf3  lea     r8, [rsp+8C0h+var_850]
0x180047cf8  mov     rdx, qword ptr cs:xmmword_180078C50
0x180047cff  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180047d06  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180047d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d12  mov     rcx, r12; Resource
0x180047d15  call    cs:__imp_RtlReleaseResource
0x180047d1b  cmp     [rsp+8C0h+var_89C], 0
0x180047d20  jge     short loc_180047D2D
0x180047d22  mov     rcx, rsi; hMem
0x180047d25  call    cs:__imp_LocalFree
0x180047d2b  jmp     short loc_180047D53
0x180047d2d  call    cs:__imp_GetProcessHeap
0x180047d33  mov     rcx, rax; hHeap
0x180047d36  mov     r8, rsi; lpMem
0x180047d39  xor     edx, edx; dwFlags
0x180047d3b  call    cs:__imp_HeapFree
0x180047d41  jmp     short loc_180047D53
0x180047d43  mov     rax, [rsp+8C0h+var_898]
0x180047d48  mov     [rax], r14d
0x180047d4b  mov     rax, [rsp+8C0h+var_890]
0x180047d50  mov     [rax], rsi
0x180047d53  lea     rcx, [r15+70h]; Resource
0x180047d57  call    cs:__imp_RtlReleaseResource
0x180047d5d  jmp     short loc_180047DB3
0x180047d5f  mov     [rsp+8C0h+var_8A0], 57h ; 'W'
0x180047d67  cmp     qword ptr cs:xmmword_180078C50, r14
0x180047d6e  jz      short loc_180047DB3
0x180047d70  mov     word ptr [rsp+8C0h+var_850], r14w
0x180047d76  mov     r9d, 166h
0x180047d7c  lea     r8, aRrasconfigstor_21; "RRasConfigStore::EnumerateRoutingDomain"...
0x180047d83  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x180047d8a  lea     rcx, [rsp+8C0h+var_850]
0x180047d8f  call    FormatRRASErrorString
0x180047d94  lea     r8, [rsp+8C0h+var_850]
0x180047d99  mov     rdx, qword ptr cs:xmmword_180078C50
0x180047da0  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180047da7  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180047dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047db3  mov     ebx, [rsp+8C0h+var_8A0]
0x180047db7  lea     rcx, [rsp+8C0h+var_888]; this
0x180047dbc  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180047dc1  mov     eax, ebx
0x180047dc3  mov     rcx, [rbp+7C0h+var_50]
0x180047dca  xor     rcx, rsp; StackCookie
0x180047dcd  call    __security_check_cookie
0x180047dd2  add     rsp, 888h
0x180047dd9  pop     r15
0x180047ddb  pop     r14
0x180047ddd  pop     r13
0x180047ddf  pop     r12
0x180047de1  pop     rdi
0x180047de2  pop     rsi
0x180047de3  pop     rbx
0x180047de4  pop     rbp
0x180047de5  retn
```
