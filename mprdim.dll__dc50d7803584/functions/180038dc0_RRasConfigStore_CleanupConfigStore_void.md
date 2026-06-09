# RRasConfigStore::CleanupConfigStore(void)

- ea: `0x180038dc0`
- end: `0x180038eaf`
- name: `?CleanupConfigStore@RRasConfigStore@@QEAAKXZ`
- size: `239`
- prototype: `__int64 __fastcall(RRasConfigStore *this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034eec`
- `0x180038a78`

## callees

- `0x180038bc0`
- `0x180038dc0`
- `0x180043c28`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180038e8b`
- `ntdll!RtlReleaseResource` at `0x180038e8b`
- `ntdll!RtlAcquireResourceExclusive` at `0x180038e54`
- `ntdll!RtlAcquireResourceExclusive` at `0x180038e54`

## string_xrefs

- `0x180038e10`: `RRasConfigStore::CleanupConfigStore`

## pseudocode

```c
__int64 __fastcall RRasConfigStore::CleanupConfigStore(RRasConfigStore *this)
{
  _QWORD *v2; // rbx
  RRasRoutingDomainConfig *v3; // rcx
  _WORD v5[2]; // [rsp+20h] [rbp-838h] BYREF
  _BYTE v6[2044]; // [rsp+24h] [rbp-834h] BYREF

  v5[1] = 0;
  memset_0(v6, 0, sizeof(v6));
  if ( *((_DWORD *)this + 26) )
  {
    RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 112), 1u);
    if ( *((_QWORD *)this + 4) )
    {
      v2 = (_QWORD *)*((_QWORD *)this + 3);
      while ( 1 )
      {
        v2 = (_QWORD *)*v2;
        if ( v2 == *((_QWORD **)this + 3) )
          break;
        v3 = (RRasRoutingDomainConfig *)v2[4];
        if ( v3 )
          RRasRoutingDomainConfig::`scalar deleting destructor'(v3);
      }
      std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::clear((char *)this + 16);
    }
    RtlReleaseResource((PRTL_RESOURCE)((char *)this + 112));
  }
  else if ( (_QWORD)xmmword_180071090 )
  {
    v5[0] = 0;
    FormatRRASErrorString(v5, L"%s: Not initialized yet.", L"RRasConfigStore::CleanupConfigStore");
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, _WORD *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180071090,
      v5);
  }
  return 0;
}

```

## disassembly

```asm
0x180038dc0  push    rbx
0x180038dc2  push    rbp
0x180038dc3  push    rsi
0x180038dc4  push    rdi
0x180038dc5  sub     rsp, 838h
0x180038dcc  mov     rax, cs:__security_cookie
0x180038dd3  xor     rax, rsp
0x180038dd6  mov     [rsp+858h+var_38], rax
0x180038dde  mov     rdi, rcx
0x180038de1  xor     eax, eax
0x180038de3  lea     rcx, [rsp+858h+var_834]; void *
0x180038de8  mov     [rsp+858h+var_836], ax
0x180038ded  xor     edx, edx; Val
0x180038def  mov     r8d, 7FCh; Size
0x180038df5  call    memset_0
0x180038dfa  cmp     dword ptr [rdi+68h], 0
0x180038dfe  jnz     short loc_180038E4E
0x180038e00  cmp     qword ptr cs:xmmword_180071090, 0
0x180038e08  jz      loc_180038E91
0x180038e0e  xor     eax, eax
0x180038e10  lea     r8, aRrasconfigstor_21; "RRasConfigStore::CleanupConfigStore"
0x180038e17  lea     rdx, aSNotInitialize; "%s: Not initialized yet."
0x180038e1e  mov     [rsp+858h+var_838], ax
0x180038e23  lea     rcx, [rsp+858h+var_838]
0x180038e28  call    FormatRRASErrorString
0x180038e2d  mov     rdx, qword ptr cs:xmmword_180071090
0x180038e34  lea     r8, [rsp+858h+var_838]
0x180038e39  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180038e40  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180038e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e4c  jmp     short loc_180038E91
0x180038e4e  mov     dl, 1; Wait
0x180038e50  lea     rcx, [rdi+70h]; Resource
0x180038e54  call    cs:__imp_RtlAcquireResourceExclusive
0x180038e5a  cmp     qword ptr [rdi+20h], 0
0x180038e5f  jz      short loc_180038E87
0x180038e61  mov     rbx, [rdi+18h]
0x180038e65  mov     rbx, [rbx]
0x180038e68  cmp     rbx, [rdi+18h]
0x180038e6c  jz      short loc_180038E7E
0x180038e6e  mov     rcx, [rbx+20h]; this
0x180038e72  test    rcx, rcx
0x180038e75  jz      short loc_180038E65
0x180038e77  call    ??_GRRasRoutingDomainConfig@@QEAAPEAXI@Z; RRasRoutingDomainConfig::`scalar deleting destructor'(uint)
0x180038e7c  jmp     short loc_180038E65
0x180038e7e  lea     rcx, [rdi+10h]
0x180038e82  call    ?clear@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAAXXZ; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::clear(void)
0x180038e87  lea     rcx, [rdi+70h]; Resource
0x180038e8b  call    cs:__imp_RtlReleaseResource
0x180038e91  xor     eax, eax
0x180038e93  mov     rcx, [rsp+858h+var_38]
0x180038e9b  xor     rcx, rsp; StackCookie
0x180038e9e  call    __security_check_cookie
0x180038ea3  add     rsp, 838h
0x180038eaa  pop     rdi
0x180038eab  pop     rsi
0x180038eac  pop     rbp
0x180038ead  pop     rbx
0x180038eae  retn
```
