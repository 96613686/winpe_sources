# DeleteAllInterfaces

- ea: `0x1800017a0`
- end: `0x180001acd`
- name: `DeleteAllInterfaces`
- size: `813`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c054`
- `0x18002bdb8`

## callees

- `0x1800017a0`
- `0x180002eb8`
- `0x180003b00`
- `0x18000ac60`
- `0x180016734`
- `0x180055118`
- `0x1800551c4`
- `0x180055fc8`
- `0x180057bac`
- `0x180057dd0`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180001864`
- `ntdll!RtlAcquireResourceExclusive` at `0x180001864`
- `ntdll!RtlReleaseResource` at `0x180001918`
- `ntdll!RtlReleaseResource` at `0x1800019b9`
- `ntdll!RtlReleaseResource` at `0x180001a97`
- `ntdll!RtlReleaseResource` at `0x180001918`
- `ntdll!RtlReleaseResource` at `0x1800019b9`
- `ntdll!RtlReleaseResource` at `0x180001a97`
- `ntdll!RtlAcquireResourceShared` at `0x180001905`
- `ntdll!RtlAcquireResourceShared` at `0x180001905`
- `KERNEL32!HeapFree` at `0x180001a6a`
- `KERNEL32!HeapFree` at `0x180001a8a`
- `KERNEL32!HeapFree` at `0x180001a6a`
- `KERNEL32!HeapFree` at `0x180001a8a`
- `KERNEL32!HeapAlloc` at `0x180001977`
- `KERNEL32!HeapAlloc` at `0x180001977`

## string_xrefs

- `0x1800017fa`: `DeleteAllInterfaces`
- `0x180001821`: `DeleteAllInterface for Tranport %d`
- `0x1800018cf`: `GetInstance: failed to instantiate RtMgrRdConfigStore object.`

## pseudocode

```c
void __fastcall DeleteAllInterfaces(unsigned int a1)
{
  int v2; // r13d
  char v3; // al
  RtMgrRdConfigStore *v4; // rdi
  RtMgrRdConfigStore *v5; // rax
  struct _GUID *v6; // r14
  __int64 *v7; // rdi
  _QWORD **v8; // rcx
  unsigned int v9; // r15d
  _QWORD *v10; // rax
  struct _GUID *v11; // rax
  __int64 *v12; // rbx
  struct _GUID *i; // r15
  __int64 v14; // rdx
  unsigned int j; // ebx
  _QWORD *InternalInterfaceForRoutingDomain; // rax
  __int64 v17; // rdx
  _QWORD *v18; // r8
  __int64 *v19; // rbx
  unsigned int v20; // [rsp+20h] [rbp-848h]
  int v21; // [rsp+30h] [rbp-838h] BYREF
  char v22[2044]; // [rsp+34h] [rbp-834h] BYREF

  v2 = a1 == 33;
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  v3 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"DeleteAllInterfaces");
    v3 = Microsoft_Windows_RRASEnableBits;
  }
  if ( v3 < 0 )
  {
    LOWORD(v21) = 0;
    FormatRRASErrorString(&v21, L"DeleteAllInterface for Tranport %d", a1);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v21);
  }
  RtlAcquireResourceExclusive(&Resource, 1u);
  v4 = RtMgrRdConfigStore::pInstance;
  if ( !RtMgrRdConfigStore::pInstance )
  {
    v5 = (RtMgrRdConfigStore *)operator new(0x118u);
    v4 = v5;
    if ( v5 )
    {
      std::tr1::unordered_map<_GUID,RtMgrRoutingDomainConfig *,GuidHash,GuidEquality,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>>::unordered_map<_GUID,RtMgrRoutingDomainConfig *,GuidHash,GuidEquality,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>>((char *)v5 + 8);
      std::tr1::unordered_map<void *,RtMgrRoutingDomainConfig *,std::hash<void *>,std::equal_to<void *>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>>::unordered_map<void *,RtMgrRoutingDomainConfig *,std::hash<void *>,std::equal_to<void *>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>>((char *)v4 + 96);
      *(_DWORD *)v4 = 0;
      RtMgrRdConfigStore::pInstance = v4;
    }
    else
    {
      v4 = 0;
      RtMgrRdConfigStore::pInstance = 0;
      if ( (_QWORD)xmmword_18008B440 )
      {
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRdMgrTemplateFunc)(
          gRdMgrEtwContext,
          xmmword_18008B440,
          L"GetInstance: failed to instantiate RtMgrRdConfigStore object.");
        v4 = RtMgrRdConfigStore::pInstance;
      }
    }
  }
  v6 = 0;
  RtlAcquireResourceShared((PRTL_RESOURCE)((char *)v4 + 184), 1u);
  if ( *((_QWORD *)v4 + 3) )
  {
    v8 = (_QWORD **)*((_QWORD *)v4 + 2);
    v9 = 0;
    v10 = *v8;
    while ( v10 != v8 )
    {
      v10 = (_QWORD *)*v10;
      ++v9;
    }
    v20 = v9;
    v11 = (struct _GUID *)HeapAlloc(IPRouterHeap, 0, 16LL * v9);
    if ( v11 )
    {
      v12 = (__int64 *)*((_QWORD *)v4 + 2);
      for ( i = v11; ; RtMgrRoutingDomainConfig::GetRoutingDomainId((RtMgrRoutingDomainConfig *)v12[4], &i[v14]) )
      {
        v12 = (__int64 *)*v12;
        if ( v12 == *((__int64 **)v4 + 2) )
          break;
        v14 = (unsigned int)v6;
        LODWORD(v6) = (_DWORD)v6 + 1;
      }
      v6 = i;
      v9 = v20;
    }
    RtlReleaseResource((PRTL_RESOURCE)((char *)v4 + 184));
    for ( j = 0; j < v9; ++j )
    {
      InternalInterfaceForRoutingDomain = (_QWORD *)GetInternalInterfaceForRoutingDomain(&v6[j], a1);
      if ( InternalInterfaceForRoutingDomain )
      {
        v17 = *InternalInterfaceForRoutingDomain;
        if ( *(_QWORD **)(*InternalInterfaceForRoutingDomain + 8LL) != InternalInterfaceForRoutingDomain
          || (v18 = (_QWORD *)InternalInterfaceForRoutingDomain[1], (_QWORD *)*v18 != InternalInterfaceForRoutingDomain) )
        {
          __fastfail(3u);
        }
        *v18 = v17;
        *(_QWORD *)(v17 + 8) = v18;
        _InterlockedDecrement(&g_ulNumInterfaces);
      }
      SetLoopbackInterfaceForRoutingDomain(&v6[j], a1, 0);
    }
  }
  else
  {
    RtlReleaseResource((PRTL_RESOURCE)((char *)v4 + 184));
  }
  v7 = (__int64 *)lpMem;
  if ( lpMem != &ICBList )
  {
    do
    {
      if ( *((_DWORD *)v7 + 129) == v2 )
      {
        if ( *((_DWORD *)v7 + 42) == 4 && (unsigned int)(*((_DWORD *)v7 + 36) - 1) <= 1 )
        {
          *((_DWORD *)v7 + 45) |= 4u;
          v7 = (__int64 *)v7[1];
        }
        else
        {
          v19 = v7;
          v7 = (__int64 *)v7[1];
          RemoveInterfaceFromLists(v19);
          DeleteSingleInterface((__int64)v19);
          HeapFree(IPRouterHeap, 0, v19);
        }
      }
      else
      {
        v7 = (__int64 *)v7[1];
      }
    }
    while ( v7 != &ICBList );
  }
  if ( v6 )
    HeapFree(IPRouterHeap, 0, v6);
  RtlReleaseResource(&Resource);
}

```

## disassembly

```asm
0x1800017a0  push    rsi
0x1800017a2  push    rdi
0x1800017a3  push    r12
0x1800017a5  push    r13
0x1800017a7  push    r14
0x1800017a9  sub     rsp, 840h
0x1800017b0  mov     rax, cs:__security_cookie
0x1800017b7  xor     rax, rsp
0x1800017ba  mov     [rsp+868h+var_38], rax
0x1800017c2  xor     r13d, r13d
0x1800017c5  mov     r12d, ecx
0x1800017c8  cmp     ecx, 21h ; '!'
0x1800017cb  mov     r8d, 7FCh; Size
0x1800017d1  lea     rcx, [rsp+868h+var_834]; void *
0x1800017d6  setz    r13b
0x1800017da  xor     eax, eax
0x1800017dc  xor     edx, edx; Val
0x1800017de  mov     [rsp+868h+var_838], eax
0x1800017e2  call    memset_0
0x1800017e7  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800017ee  movzx   ecx, al
0x1800017f1  and     cl, 80h
0x1800017f4  mov     byte ptr [rsp+868h+var_848], cl
0x1800017f8  jz      short loc_18000181B
0x1800017fa  lea     r8, aDeleteallinter_4; "DeleteAllInterfaces"
0x180001801  lea     rdx, RasRtrmgrTraceInfo
0x180001808  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000180f  call    McTemplateU0z_EventWriteTransfer
0x180001814  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18000181b  test    al, al
0x18000181d  jns     short loc_18000185B
0x18000181f  xor     eax, eax
0x180001821  lea     rdx, aDeleteallinter_2; "DeleteAllInterface for Tranport %d"
0x180001828  mov     r8d, r12d
0x18000182b  mov     word ptr [rsp+868h+var_838], ax
0x180001830  lea     rcx, [rsp+868h+var_838]
0x180001835  call    FormatRRASErrorString
0x18000183a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180001841  jge     short loc_18000185B
0x180001843  lea     r8, [rsp+868h+var_838]
0x180001848  lea     rdx, RasRtrmgrTraceInfo
0x18000184f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180001856  call    McTemplateU0z_EventWriteTransfer
0x18000185b  mov     dl, 1; Wait
0x18000185d  lea     rcx, Resource; Resource
0x180001864  call    cs:__imp_RtlAcquireResourceExclusive
0x18000186a  mov     rdi, cs:?pInstance@RtMgrRdConfigStore@@0PEAV1@EA; RtMgrRdConfigStore * RtMgrRdConfigStore::pInstance
0x180001871  test    rdi, rdi
0x180001874  jnz     short loc_1800018E9
0x180001876  mov     ecx, 118h; Size
0x18000187b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001880  mov     [rsp+868h+var_840], rax
0x180001885  mov     rdi, rax
0x180001888  test    rax, rax
0x18000188b  jz      short loc_1800018B3
0x18000188d  lea     rcx, [rax+8]
0x180001891  call    ??0?$unordered_map@U_GUID@@PEAVRtMgrRoutingDomainConfig@@UGuidHash@@UGuidEquality@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@@std@@@tr1@std@@QEAA@XZ; std::tr1::unordered_map<_GUID,RtMgrRoutingDomainConfig *,GuidHash,GuidEquality,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>>::unordered_map<_GUID,RtMgrRoutingDomainConfig *,GuidHash,GuidEquality,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>>(void)
0x180001896  lea     rcx, [rdi+60h]
0x18000189a  call    ??0?$unordered_map@PEAXPEAVRtMgrRoutingDomainConfig@@V?$hash@PEAX@std@@U?$equal_to@PEAX@3@V?$allocator@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@@3@@tr1@std@@QEAA@XZ; std::tr1::unordered_map<void *,RtMgrRoutingDomainConfig *,std::hash<void *>,std::equal_to<void *>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>>::unordered_map<void *,RtMgrRoutingDomainConfig *,std::hash<void *>,std::equal_to<void *>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>>(void)
0x18000189f  mov     dword ptr [rdi], 0
0x1800018a5  mov     cs:?pInstance@RtMgrRdConfigStore@@0PEAV1@EA, rdi; RtMgrRdConfigStore * RtMgrRdConfigStore::pInstance
0x1800018ac  test    rdi, rdi
0x1800018af  jz      short loc_1800018BC
0x1800018b1  jmp     short loc_1800018E9
0x1800018b3  xor     edi, edi
0x1800018b5  mov     cs:?pInstance@RtMgrRdConfigStore@@0PEAV1@EA, rdi; RtMgrRdConfigStore * RtMgrRdConfigStore::pInstance
0x1800018bc  mov     rdx, qword ptr cs:xmmword_18008B440
0x1800018c3  test    rdx, rdx
0x1800018c6  jz      short loc_1800018E9
0x1800018c8  mov     rcx, cs:?gRdMgrEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRdMgrEtwContext
0x1800018cf  lea     r8, aGetinstanceFai; "GetInstance: failed to instantiate RtMg"...
0x1800018d6  mov     rax, cs:?gRdMgrTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRdMgrTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800018dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018e2  mov     rdi, cs:?pInstance@RtMgrRdConfigStore@@0PEAV1@EA; RtMgrRdConfigStore * RtMgrRdConfigStore::pInstance
0x1800018e9  mov     [rsp+868h+arg_8], rbx
0x1800018f1  lea     rcx, [rdi+0B8h]; Resource
0x1800018f8  mov     dl, 1; Wait
0x1800018fa  mov     [rsp+868h+arg_10], r15
0x180001902  xor     r14d, r14d
0x180001905  call    cs:__imp_RtlAcquireResourceShared
0x18000190b  cmp     [rdi+18h], r14
0x18000190f  jnz     short loc_18000194B
0x180001911  lea     rcx, [rdi+0B8h]; Resource
0x180001918  call    cs:__imp_RtlReleaseResource
0x18000191e  mov     rdi, cs:lpMem
0x180001925  lea     rsi, ICBList
0x18000192c  cmp     rdi, rsi
0x18000192f  jz      loc_180001A79
0x180001935  cmp     [rdi+204h], r13d
0x18000193c  jz      loc_180001A24
0x180001942  mov     rdi, [rdi+8]
0x180001946  jmp     loc_180001A70
0x18000194b  mov     rcx, [rdi+10h]
0x18000194f  xor     r15d, r15d
0x180001952  mov     rax, [rcx]
0x180001955  cmp     rax, rcx
0x180001958  jz      short loc_180001962
0x18000195a  mov     rax, [rax]
0x18000195d  inc     r15d
0x180001960  jmp     short loc_180001955
0x180001962  mov     rcx, cs:?IPRouterHeap@@3PEAXEA; hHeap
0x180001969  xor     edx, edx; dwFlags
0x18000196b  mov     r8d, r15d
0x18000196e  shl     r8, 4; dwBytes
0x180001972  mov     [rsp+868h+var_848], r15d
0x180001977  call    cs:__imp_HeapAlloc
0x18000197d  test    rax, rax
0x180001980  jz      short loc_1800019B2
0x180001982  mov     rbx, [rdi+10h]
0x180001986  mov     r15, rax
0x180001989  mov     rbx, [rbx]
0x18000198c  cmp     rbx, [rdi+10h]
0x180001990  jz      short loc_1800019AA
0x180001992  mov     rcx, [rbx+20h]; this
0x180001996  mov     edx, r14d
0x180001999  inc     r14d
0x18000199c  shl     rdx, 4
0x1800019a0  add     rdx, r15; struct _GUID *
0x1800019a3  call    ?GetRoutingDomainId@RtMgrRoutingDomainConfig@@QEAAXPEAU_GUID@@@Z; RtMgrRoutingDomainConfig::GetRoutingDomainId(_GUID *)
0x1800019a8  jmp     short loc_180001989
0x1800019aa  mov     r14, r15
0x1800019ad  mov     r15d, [rsp+868h+var_848]
0x1800019b2  lea     rcx, [rdi+0B8h]; Resource
0x1800019b9  call    cs:__imp_RtlReleaseResource
0x1800019bf  xor     ebx, ebx
0x1800019c1  test    r15d, r15d
0x1800019c4  jz      loc_18000191E
0x1800019ca  mov     edi, ebx
0x1800019cc  mov     edx, r12d; unsigned int
0x1800019cf  shl     rdi, 4
0x1800019d3  add     rdi, r14
0x1800019d6  mov     rcx, rdi; struct _GUID *
0x1800019d9  call    GetInternalInterfaceForRoutingDomain
0x1800019de  test    rax, rax
0x1800019e1  jz      short loc_180001A03
0x1800019e3  mov     rdx, [rax]
0x1800019e6  cmp     [rdx+8], rax
0x1800019ea  jnz     short loc_180001A1D
0x1800019ec  mov     r8, [rax+8]
0x1800019f0  cmp     [r8], rax
0x1800019f3  jnz     short loc_180001A1D
0x1800019f5  mov     [r8], rdx
0x1800019f8  mov     [rdx+8], r8
0x1800019fc  lock dec cs:g_ulNumInterfaces
0x180001a03  xor     r8d, r8d; struct _ICB *
0x180001a06  mov     edx, r12d; unsigned int
0x180001a09  mov     rcx, rdi; struct _GUID *
0x180001a0c  call    SetLoopbackInterfaceForRoutingDomain
0x180001a11  inc     ebx
0x180001a13  cmp     ebx, r15d
0x180001a16  jb      short loc_1800019CA
0x180001a18  jmp     loc_18000191E
0x180001a1d  mov     ecx, 3
0x180001a22  int     29h; Win8: RtlFailFast(ecx)
0x180001a24  cmp     dword ptr [rdi+0A8h], 4
0x180001a2b  jnz     short loc_180001A47
0x180001a2d  mov     eax, [rdi+90h]
0x180001a33  dec     eax
0x180001a35  cmp     eax, 1
0x180001a38  ja      short loc_180001A47
0x180001a3a  or      dword ptr [rdi+0B4h], 4
0x180001a41  mov     rdi, [rdi+8]
0x180001a45  jmp     short loc_180001A70
0x180001a47  mov     rbx, rdi
0x180001a4a  mov     rdi, [rdi+8]
0x180001a4e  mov     rcx, rbx
0x180001a51  call    RemoveInterfaceFromLists
0x180001a56  mov     rcx, rbx
0x180001a59  call    DeleteSingleInterface
0x180001a5e  mov     rcx, cs:IPRouterHeap; hHeap
0x180001a65  mov     r8, rbx; lpMem
0x180001a68  xor     edx, edx; dwFlags
0x180001a6a  call    cs:__imp_HeapFree
0x180001a70  cmp     rdi, rsi
0x180001a73  jnz     loc_180001935
0x180001a79  test    r14, r14
0x180001a7c  jz      short loc_180001A90
0x180001a7e  mov     rcx, cs:IPRouterHeap; hHeap
0x180001a85  mov     r8, r14; lpMem
0x180001a88  xor     edx, edx; dwFlags
0x180001a8a  call    cs:__imp_HeapFree
0x180001a90  lea     rcx, Resource; Resource
0x180001a97  call    cs:__imp_RtlReleaseResource
0x180001a9d  mov     r15, [rsp+868h+arg_10]
0x180001aa5  mov     rbx, [rsp+868h+arg_8]
0x180001aad  mov     rcx, [rsp+868h+var_38]
0x180001ab5  xor     rcx, rsp; StackCookie
0x180001ab8  call    __security_check_cookie
0x180001abd  add     rsp, 840h
0x180001ac4  pop     r14
0x180001ac6  pop     r13
0x180001ac8  pop     r12
0x180001aca  pop     rdi
0x180001acb  pop     rsi
0x180001acc  retn
```
