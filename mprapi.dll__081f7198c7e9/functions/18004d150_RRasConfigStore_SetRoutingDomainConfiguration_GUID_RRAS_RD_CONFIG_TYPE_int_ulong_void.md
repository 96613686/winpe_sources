# RRasConfigStore::SetRoutingDomainConfiguration(_GUID *,_RRAS_RD_CONFIG_TYPE,int,ulong,void *)

- ea: `0x18004d150`
- end: `0x18004d2fe`
- name: `?SetRoutingDomainConfiguration@RRasConfigStore@@QEAAKPEAU_GUID@@W4_RRAS_RD_CONFIG_TYPE@@HKPEAX@Z`
- size: `430`
- prototype: `__int64 __fastcall(__int64, struct _GUID *, int, int, unsigned int, struct _MPRI_IPV4_CONFIG_1 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180043060`

## callees

- `0x18004c944`
- `0x18004d150`
- `0x18004f0ec`
- `0x180050b2c`
- `0x180050be8`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x18004d209`
- `ntdll!RtlAcquireResourceShared` at `0x18004d209`
- `ntdll!RtlReleaseResource` at `0x18004d26c`
- `ntdll!RtlReleaseResource` at `0x18004d275`
- `ntdll!RtlReleaseResource` at `0x18004d26c`
- `ntdll!RtlReleaseResource` at `0x18004d275`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004d245`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004d245`

## string_xrefs

- `0x18004d1e1`: `RRasConfigStore::SetRoutingDomainConfiguration`
- `0x18004d298`: `RRasConfigStore::SetRoutingDomainConfiguration`

## pseudocode

```c
__int64 __fastcall RRasConfigStore::SetRoutingDomainConfiguration(
        __int64 a1,
        struct _GUID *a2,
        int a3,
        int a4,
        unsigned int a5,
        struct _MPRI_IPV4_CONFIG_1 *a6)
{
  void (*v10)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  __int64 v11; // rbx
  unsigned int v12; // ebx
  unsigned int v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v17; // [rsp+58h] [rbp-A8h]
  __int128 v18; // [rsp+68h] [rbp-98h]
  __int64 v19; // [rsp+78h] [rbp-88h]
  int v20; // [rsp+80h] [rbp-80h]
  int v21; // [rsp+84h] [rbp-7Ch]
  int v22; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v23[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v14 = 0;
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  v17 = 0;
  v16 = 0;
  v18 = 0;
  v19 = 0;
  v20 = -1;
  v21 = 0;
  if ( *((_QWORD *)&xmmword_180078C60 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v16,
      L"RRasConfigStore::SetRoutingDomainConfiguration",
      &v14,
      v10,
      a2);
  if ( a2 && a6 )
  {
    RtlAcquireResourceShared((PRTL_RESOURCE)(a1 + 112), 1u);
    std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(
      (_QWORD *)(a1 + 16),
      &v15,
      (__int64)a2);
    if ( v15 == *(_QWORD *)(a1 + 24) )
    {
      v14 = 1168;
    }
    else
    {
      v11 = *(_QWORD *)(v15 + 32);
      RtlAcquireResourceExclusive((PRTL_RESOURCE)(v11 + 728), 1u);
      v14 = RRasRoutingDomainConfig::SetConfigParam(v11, a3, a4, a5, a6);
      RtlReleaseResource((PRTL_RESOURCE)(v11 + 728));
    }
    RtlReleaseResource((PRTL_RESOURCE)(a1 + 112));
  }
  else
  {
    v14 = 87;
    if ( (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v22) = 0;
      FormatRRASErrorString(
        &v22,
        L"%hs(Line#%d): Invalid parameter.",
        "RRasConfigStore::SetRoutingDomainConfiguration",
        1017);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C50,
        &v22);
    }
  }
  v12 = v14;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v16);
  return v12;
}

```

## disassembly

```asm
0x18004d150  push    rbp
0x18004d152  push    rbx
0x18004d153  push    rsi
0x18004d154  push    rdi
0x18004d155  push    r12
0x18004d157  push    r14
0x18004d159  push    r15
0x18004d15b  lea     rbp, [rsp-7A0h]
0x18004d163  sub     rsp, 8A0h
0x18004d16a  mov     rax, cs:__security_cookie
0x18004d171  xor     rax, rsp
0x18004d174  mov     [rbp+7D0h+var_40], rax
0x18004d17b  mov     r12d, r9d
0x18004d17e  mov     r15d, r8d
0x18004d181  mov     rbx, rdx
0x18004d184  mov     rdi, rcx
0x18004d187  mov     r14, [rbp+7D0h+arg_28]
0x18004d18e  xor     esi, esi
0x18004d190  mov     [rsp+8D0h+var_890], esi
0x18004d194  mov     [rbp+7D0h+var_840], esi
0x18004d197  xor     edx, edx; Val
0x18004d199  mov     r8d, 7FCh; Size
0x18004d19f  lea     rcx, [rbp+7D0h+var_83C]; void *
0x18004d1a3  call    memset_0
0x18004d1a8  xorps   xmm0, xmm0
0x18004d1ab  movdqu  [rsp+8D0h+var_878], xmm0
0x18004d1b1  mov     [rsp+8D0h+var_880], rsi
0x18004d1b6  xorps   xmm1, xmm1
0x18004d1b9  movdqu  [rsp+8D0h+var_868], xmm1
0x18004d1bf  mov     [rsp+8D0h+var_858], rsi
0x18004d1c4  mov     [rbp+7D0h+var_850], 0FFFFFFFFh
0x18004d1cb  mov     [rbp+7D0h+var_84C], esi
0x18004d1ce  cmp     qword ptr cs:xmmword_180078C60+8, rsi
0x18004d1d5  jz      short loc_18004D1F2
0x18004d1d7  mov     [rsp+8D0h+var_8B0], rbx; struct _GUID *
0x18004d1dc  lea     r8, [rsp+8D0h+var_890]; unsigned int *
0x18004d1e1  lea     rdx, aRrasconfigstor_10; "RRasConfigStore::SetRoutingDomainConfig"...
0x18004d1e8  lea     rcx, [rsp+8D0h+var_880]; this
0x18004d1ed  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18004d1f2  test    rbx, rbx
0x18004d1f5  jz      loc_18004D27D
0x18004d1fb  test    r14, r14
0x18004d1fe  jz      short loc_18004D27D
0x18004d200  lea     rsi, [rdi+70h]
0x18004d204  mov     dl, 1; Wait
0x18004d206  mov     rcx, rsi; Resource
0x18004d209  call    cs:__imp_RtlAcquireResourceShared
0x18004d20f  lea     rcx, [rdi+10h]
0x18004d213  mov     r8, rbx
0x18004d216  lea     rdx, [rsp+8D0h+var_888]
0x18004d21b  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x18004d220  mov     rax, [rsp+8D0h+var_888]
0x18004d225  cmp     rax, [rdi+18h]
0x18004d229  jnz     short loc_18004D235
0x18004d22b  mov     [rsp+8D0h+var_890], 490h
0x18004d233  jmp     short loc_18004D272
0x18004d235  mov     rbx, [rax+20h]
0x18004d239  lea     rdi, [rbx+2D8h]
0x18004d240  mov     dl, 1; Wait
0x18004d242  mov     rcx, rdi; Resource
0x18004d245  call    cs:__imp_RtlAcquireResourceExclusive
0x18004d24b  mov     [rsp+8D0h+var_8B0], r14
0x18004d250  mov     r9d, [rbp+7D0h+arg_20]
0x18004d257  mov     r8d, r12d
0x18004d25a  mov     edx, r15d
0x18004d25d  mov     rcx, rbx
0x18004d260  call    ?SetConfigParam@RRasRoutingDomainConfig@@QEAAKW4_RRAS_RD_CONFIG_TYPE@@HKPEAX@Z; RRasRoutingDomainConfig::SetConfigParam(_RRAS_RD_CONFIG_TYPE,int,ulong,void *)
0x18004d265  mov     [rsp+8D0h+var_890], eax
0x18004d269  mov     rcx, rdi; Resource
0x18004d26c  call    cs:__imp_RtlReleaseResource
0x18004d272  mov     rcx, rsi; Resource
0x18004d275  call    cs:__imp_RtlReleaseResource
0x18004d27b  jmp     short loc_18004D2CD
0x18004d27d  mov     [rsp+8D0h+var_890], 57h ; 'W'
0x18004d285  cmp     qword ptr cs:xmmword_180078C50, rsi
0x18004d28c  jz      short loc_18004D2CD
0x18004d28e  mov     word ptr [rbp+7D0h+var_840], si
0x18004d292  mov     r9d, 3F9h
0x18004d298  lea     r8, aRrasconfigstor_13; "RRasConfigStore::SetRoutingDomainConfig"...
0x18004d29f  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18004d2a6  lea     rcx, [rbp+7D0h+var_840]
0x18004d2aa  call    FormatRRASErrorString
0x18004d2af  lea     r8, [rbp+7D0h+var_840]
0x18004d2b3  mov     rdx, qword ptr cs:xmmword_180078C50
0x18004d2ba  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004d2c1  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004d2c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d2cd  mov     ebx, [rsp+8D0h+var_890]
0x18004d2d1  lea     rcx, [rsp+8D0h+var_880]; this
0x18004d2d6  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18004d2db  mov     eax, ebx
0x18004d2dd  mov     rcx, [rbp+7D0h+var_40]
0x18004d2e4  xor     rcx, rsp; StackCookie
0x18004d2e7  call    __security_check_cookie
0x18004d2ec  add     rsp, 8A0h
0x18004d2f3  pop     r15
0x18004d2f5  pop     r14
0x18004d2f7  pop     r12
0x18004d2f9  pop     rdi
0x18004d2fa  pop     rsi
0x18004d2fb  pop     rbx
0x18004d2fc  pop     rbp
0x18004d2fd  retn
```
