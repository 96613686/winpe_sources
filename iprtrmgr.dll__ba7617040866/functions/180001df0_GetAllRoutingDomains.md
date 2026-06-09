# GetAllRoutingDomains

- ea: `0x180001df0`
- end: `0x180001f23`
- name: `GetAllRoutingDomains`
- size: `307`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18000bdbc`
- `0x18000be58`
- `0x180050b74`

## callees

- `0x180001df0`
- `0x180003b00`
- `0x180055118`
- `0x1800551c4`
- `0x180055fc8`
- `0x180059010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180001f1c`
- `ntdll!RtlAcquireResourceShared` at `0x180001e8e`
- `ntdll!RtlAcquireResourceShared` at `0x180001e8e`
- `KERNEL32!HeapAlloc` at `0x180001ec7`
- `KERNEL32!HeapAlloc` at `0x180001ec7`

## string_xrefs

- `0x180001e65`: `GetInstance: failed to instantiate RtMgrRdConfigStore object.`

## pseudocode

```c
void __fastcall GetAllRoutingDomains(struct _GUID **a1, unsigned int *a2)
{
  RtMgrRdConfigStore *v2; // rdi
  unsigned int v3; // r15d
  RtMgrRdConfigStore *v6; // rax
  _QWORD **v7; // rcx
  unsigned int v8; // edx
  _QWORD *v9; // rax
  HANDLE v10; // rcx
  struct _GUID *v11; // rbp
  __int64 *i; // rbx
  __int64 v13; // rdx

  v2 = RtMgrRdConfigStore::pInstance;
  v3 = 0;
  if ( !RtMgrRdConfigStore::pInstance )
  {
    v6 = (RtMgrRdConfigStore *)operator new(0x118u);
    v2 = v6;
    if ( v6 )
    {
      std::tr1::unordered_map<_GUID,RtMgrRoutingDomainConfig *,GuidHash,GuidEquality,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>>::unordered_map<_GUID,RtMgrRoutingDomainConfig *,GuidHash,GuidEquality,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>>((char *)v6 + 8);
      std::tr1::unordered_map<void *,RtMgrRoutingDomainConfig *,std::hash<void *>,std::equal_to<void *>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>>::unordered_map<void *,RtMgrRoutingDomainConfig *,std::hash<void *>,std::equal_to<void *>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>>((char *)v2 + 96);
      *(_DWORD *)v2 = 0;
      RtMgrRdConfigStore::pInstance = v2;
    }
    else
    {
      v2 = 0;
      RtMgrRdConfigStore::pInstance = 0;
      if ( (_QWORD)xmmword_18008B440 )
      {
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRdMgrTemplateFunc)(
          gRdMgrEtwContext,
          xmmword_18008B440,
          L"GetInstance: failed to instantiate RtMgrRdConfigStore object.");
        v2 = RtMgrRdConfigStore::pInstance;
      }
    }
  }
  *a2 = 0;
  *a1 = 0;
  RtlAcquireResourceShared((PRTL_RESOURCE)((char *)v2 + 184), 1u);
  if ( *((_QWORD *)v2 + 3) )
  {
    v7 = (_QWORD **)*((_QWORD *)v2 + 2);
    v8 = 0;
    v9 = *v7;
    while ( v9 != v7 )
    {
      v9 = (_QWORD *)*v9;
      ++v8;
    }
    v10 = IPRouterHeap;
    *a2 = v8;
    v11 = (struct _GUID *)HeapAlloc(v10, 0, 16LL * v8);
    if ( v11 )
    {
      for ( i = (__int64 *)*((_QWORD *)v2 + 2);
            ;
            RtMgrRoutingDomainConfig::GetRoutingDomainId((RtMgrRoutingDomainConfig *)i[4], &v11[v13]) )
      {
        i = (__int64 *)*i;
        if ( i == *((__int64 **)v2 + 2) )
          break;
        v13 = v3++;
      }
      *a1 = v11;
    }
  }
  RtlReleaseResource((PRTL_RESOURCE)((char *)v2 + 184));
}

```

## disassembly

```asm
0x180001df0  mov     [rsp+arg_8], rbx
0x180001df5  mov     [rsp+arg_10], rsi
0x180001dfa  push    rdi
0x180001dfb  push    r14
0x180001dfd  push    r15
0x180001dff  sub     rsp, 20h
0x180001e03  mov     rdi, cs:?pInstance@RtMgrRdConfigStore@@0PEAV1@EA; RtMgrRdConfigStore * RtMgrRdConfigStore::pInstance
0x180001e0a  xor     r15d, r15d
0x180001e0d  mov     rbx, rdx
0x180001e10  mov     r14, rcx
0x180001e13  test    rdi, rdi
0x180001e16  jnz     short loc_180001E7F
0x180001e18  mov     ecx, 118h; Size
0x180001e1d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001e22  mov     rdi, rax
0x180001e25  test    rax, rax
0x180001e28  jz      short loc_180001E48
0x180001e2a  lea     rcx, [rax+8]
0x180001e2e  call    ??0?$unordered_map@U_GUID@@PEAVRtMgrRoutingDomainConfig@@UGuidHash@@UGuidEquality@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRtMgrRoutingDomainConfig@@@std@@@std@@@tr1@std@@QEAA@XZ; std::tr1::unordered_map<_GUID,RtMgrRoutingDomainConfig *,GuidHash,GuidEquality,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>>::unordered_map<_GUID,RtMgrRoutingDomainConfig *,GuidHash,GuidEquality,std::allocator<std::pair<_GUID const,RtMgrRoutingDomainConfig *>>>(void)
0x180001e33  lea     rcx, [rdi+60h]
0x180001e37  call    ??0?$unordered_map@PEAXPEAVRtMgrRoutingDomainConfig@@V?$hash@PEAX@std@@U?$equal_to@PEAX@3@V?$allocator@U?$pair@QEAXPEAVRtMgrRoutingDomainConfig@@@std@@@3@@tr1@std@@QEAA@XZ; std::tr1::unordered_map<void *,RtMgrRoutingDomainConfig *,std::hash<void *>,std::equal_to<void *>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>>::unordered_map<void *,RtMgrRoutingDomainConfig *,std::hash<void *>,std::equal_to<void *>,std::allocator<std::pair<void * const,RtMgrRoutingDomainConfig *>>>(void)
0x180001e3c  mov     [rdi], r15d
0x180001e3f  mov     cs:?pInstance@RtMgrRdConfigStore@@0PEAV1@EA, rdi; RtMgrRdConfigStore * RtMgrRdConfigStore::pInstance
0x180001e46  jmp     short loc_180001E7F
0x180001e48  mov     rdx, qword ptr cs:xmmword_18008B440
0x180001e4f  mov     rdi, r15
0x180001e52  mov     cs:?pInstance@RtMgrRdConfigStore@@0PEAV1@EA, r15; RtMgrRdConfigStore * RtMgrRdConfigStore::pInstance
0x180001e59  test    rdx, rdx
0x180001e5c  jz      short loc_180001E7F
0x180001e5e  mov     rcx, cs:?gRdMgrEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRdMgrEtwContext
0x180001e65  lea     r8, aGetinstanceFai; "GetInstance: failed to instantiate RtMg"...
0x180001e6c  mov     rax, cs:?gRdMgrTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRdMgrTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180001e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e78  mov     rdi, cs:?pInstance@RtMgrRdConfigStore@@0PEAV1@EA; RtMgrRdConfigStore * RtMgrRdConfigStore::pInstance
0x180001e7f  mov     dl, 1; Wait
0x180001e81  mov     [rbx], r15d
0x180001e84  lea     rcx, [rdi+0B8h]; Resource
0x180001e8b  mov     [r14], r15
0x180001e8e  call    cs:__imp_RtlAcquireResourceShared
0x180001e94  cmp     [rdi+18h], r15
0x180001e98  jz      short loc_180001F02
0x180001e9a  mov     rcx, [rdi+10h]
0x180001e9e  mov     edx, r15d
0x180001ea1  mov     [rsp+38h+arg_0], rbp
0x180001ea6  mov     rax, [rcx]
0x180001ea9  cmp     rax, rcx
0x180001eac  jz      short loc_180001EB5
0x180001eae  mov     rax, [rax]
0x180001eb1  inc     edx
0x180001eb3  jmp     short loc_180001EA9
0x180001eb5  mov     rcx, cs:?IPRouterHeap@@3PEAXEA; hHeap
0x180001ebc  mov     r8d, edx
0x180001ebf  mov     [rbx], edx
0x180001ec1  xor     edx, edx; dwFlags
0x180001ec3  shl     r8, 4; dwBytes
0x180001ec7  call    cs:__imp_HeapAlloc
0x180001ecd  mov     rbp, rax
0x180001ed0  test    rax, rax
0x180001ed3  jz      short loc_180001EFD
0x180001ed5  mov     rbx, [rdi+10h]
0x180001ed9  mov     rbx, [rbx]
0x180001edc  cmp     rbx, [rdi+10h]
0x180001ee0  jz      short loc_180001EFA
0x180001ee2  mov     rcx, [rbx+20h]; this
0x180001ee6  mov     edx, r15d
0x180001ee9  inc     r15d
0x180001eec  shl     rdx, 4
0x180001ef0  add     rdx, rbp; struct _GUID *
0x180001ef3  call    ?GetRoutingDomainId@RtMgrRoutingDomainConfig@@QEAAXPEAU_GUID@@@Z; RtMgrRoutingDomainConfig::GetRoutingDomainId(_GUID *)
0x180001ef8  jmp     short loc_180001ED9
0x180001efa  mov     [r14], rbp
0x180001efd  mov     rbp, [rsp+38h+arg_0]
0x180001f02  lea     rcx, [rdi+0B8h]
0x180001f09  mov     rbx, [rsp+38h+arg_8]
0x180001f0e  mov     rsi, [rsp+38h+arg_10]
0x180001f13  add     rsp, 20h
0x180001f17  pop     r15
0x180001f19  pop     r14
0x180001f1b  pop     rdi
0x180001f1c  jmp     cs:__imp_RtlReleaseResource
```
