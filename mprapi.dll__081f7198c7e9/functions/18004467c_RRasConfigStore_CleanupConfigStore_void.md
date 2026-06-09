# RRasConfigStore::CleanupConfigStore(void)

- ea: `0x18004467c`
- end: `0x18004478c`
- name: `?CleanupConfigStore@RRasConfigStore@@QEAAKXZ`
- size: `272`
- prototype: `__int64 __fastcall(RRasConfigStore *this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180040b1c`
- `0x1800442cc`

## callees

- `0x1800442f8`
- `0x18004467c`
- `0x18004ee0c`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180044747`
- `msvcrt!??3@YAXPEAX@Z` at `0x180044747`
- `ntdll!RtlReleaseResource` at `0x18004475c`
- `ntdll!RtlReleaseResource` at `0x18004475c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180044719`
- `ntdll!RtlAcquireResourceExclusive` at `0x180044719`

## string_xrefs

- `0x1800446d5`: `RRasConfigStore::CleanupConfigStore`

## pseudocode

```c
__int64 __fastcall RRasConfigStore::CleanupConfigStore(RRasConfigStore *this)
{
  __int64 *v2; // rbx
  void *v3; // rsi
  _WORD v5[2]; // [rsp+20h] [rbp-828h] BYREF
  _BYTE v6[2044]; // [rsp+24h] [rbp-824h] BYREF

  v5[1] = 0;
  memset_0(v6, 0, sizeof(v6));
  if ( *((_DWORD *)this + 26) )
  {
    RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 112), 1u);
    if ( *((_QWORD *)this + 4) )
    {
      v2 = (__int64 *)*((_QWORD *)this + 3);
      while ( 1 )
      {
        v2 = (__int64 *)*v2;
        if ( v2 == *((__int64 **)this + 3) )
          break;
        v3 = (void *)v2[4];
        if ( v3 )
        {
          RRasRoutingDomainConfig::~RRasRoutingDomainConfig((RRasRoutingDomainConfig *)v2[4]);
          operator delete(v3);
        }
      }
      std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::clear((char *)this + 16);
    }
    RtlReleaseResource((PRTL_RESOURCE)((char *)this + 112));
  }
  else if ( (_QWORD)xmmword_180078C50 )
  {
    v5[0] = 0;
    FormatRRASErrorString(v5, L"%s: Not initialized yet.", L"RRasConfigStore::CleanupConfigStore");
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, _WORD *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180078C50,
      v5);
  }
  return 0;
}

```

## disassembly

```asm
0x18004467c  mov     [rsp+arg_8], rbx
0x180044681  mov     [rsp+arg_10], rbp
0x180044686  push    rsi
0x180044687  push    rdi
0x180044688  push    r14
0x18004468a  sub     rsp, 830h
0x180044691  mov     rax, cs:__security_cookie
0x180044698  xor     rax, rsp
0x18004469b  mov     [rsp+848h+var_28], rax
0x1800446a3  mov     rdi, rcx
0x1800446a6  xor     eax, eax
0x1800446a8  lea     rcx, [rsp+848h+var_824]; void *
0x1800446ad  mov     [rsp+848h+var_826], ax
0x1800446b2  xor     edx, edx; Val
0x1800446b4  mov     r8d, 7FCh; Size
0x1800446ba  call    memset_0
0x1800446bf  cmp     dword ptr [rdi+68h], 0
0x1800446c3  jnz     short loc_180044713
0x1800446c5  cmp     qword ptr cs:xmmword_180078C50, 0
0x1800446cd  jz      loc_180044762
0x1800446d3  xor     eax, eax
0x1800446d5  lea     r8, aRrasconfigstor_17; "RRasConfigStore::CleanupConfigStore"
0x1800446dc  lea     rdx, aSNotInitialize; "%s: Not initialized yet."
0x1800446e3  mov     [rsp+848h+var_828], ax
0x1800446e8  lea     rcx, [rsp+848h+var_828]
0x1800446ed  call    FormatRRASErrorString
0x1800446f2  mov     rdx, qword ptr cs:xmmword_180078C50
0x1800446f9  lea     r8, [rsp+848h+var_828]
0x1800446fe  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180044705  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004470c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044711  jmp     short loc_180044762
0x180044713  mov     dl, 1; Wait
0x180044715  lea     rcx, [rdi+70h]; Resource
0x180044719  call    cs:__imp_RtlAcquireResourceExclusive
0x18004471f  cmp     qword ptr [rdi+20h], 0
0x180044724  jz      short loc_180044758
0x180044726  mov     rbx, [rdi+18h]
0x18004472a  mov     rbx, [rbx]
0x18004472d  cmp     rbx, [rdi+18h]
0x180044731  jz      short loc_18004474F
0x180044733  mov     rsi, [rbx+20h]
0x180044737  test    rsi, rsi
0x18004473a  jz      short loc_18004472A
0x18004473c  mov     rcx, rsi; this
0x18004473f  call    ??1RRasRoutingDomainConfig@@QEAA@XZ; RRasRoutingDomainConfig::~RRasRoutingDomainConfig(void)
0x180044744  mov     rcx, rsi
0x180044747  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004474d  jmp     short loc_18004472A
0x18004474f  lea     rcx, [rdi+10h]
0x180044753  call    ?clear@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAAXXZ; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::clear(void)
0x180044758  lea     rcx, [rdi+70h]; Resource
0x18004475c  call    cs:__imp_RtlReleaseResource
0x180044762  xor     eax, eax
0x180044764  mov     rcx, [rsp+848h+var_28]
0x18004476c  xor     rcx, rsp; StackCookie
0x18004476f  call    __security_check_cookie
0x180044774  lea     r11, [rsp+848h+var_18]
0x18004477c  mov     rbx, [r11+28h]
0x180044780  mov     rbp, [r11+30h]
0x180044784  mov     rsp, r11
0x180044787  pop     r14
0x180044789  pop     rdi
0x18004478a  pop     rsi
0x18004478b  retn
```
