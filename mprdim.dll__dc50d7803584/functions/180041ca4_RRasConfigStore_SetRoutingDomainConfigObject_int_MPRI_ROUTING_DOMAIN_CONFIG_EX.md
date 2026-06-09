# RRasConfigStore::SetRoutingDomainConfigObject(int,_MPRI_ROUTING_DOMAIN_CONFIG_EX *)

- ea: `0x180041ca4`
- end: `0x180041ed5`
- name: `?SetRoutingDomainConfigObject@RRasConfigStore@@QEAAKHPEAU_MPRI_ROUTING_DOMAIN_CONFIG_EX@@@Z`
- size: `561`
- prototype: `__int64 __fastcall(RRasConfigStore *this, __int64, struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180037820`

## callees

- `0x180041494`
- `0x180041ca4`
- `0x180043e34`
- `0x18004583c`
- `0x180045ad4`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180041e90`
- `ntdll!RtlReleaseResource` at `0x180041e99`
- `ntdll!RtlReleaseResource` at `0x180041e90`
- `ntdll!RtlReleaseResource` at `0x180041e99`
- `ntdll!RtlAcquireResourceExclusive` at `0x180041dff`
- `ntdll!RtlAcquireResourceExclusive` at `0x180041dff`
- `ntdll!RtlAcquireResourceShared` at `0x180041dc2`
- `ntdll!RtlAcquireResourceShared` at `0x180041dc2`

## string_xrefs

- `0x180041d3a`: `RRasConfigStore::SetRoutingDomainConfigObject`
- `0x180041e3b`: `RRasConfigStore::SetRoutingDomainConfigObject`
- `0x180041d71`: `RRasConfigStore::SetRoutingDomainConfigObject`
- `0x180041e42`: `%s: pRdObject->SetConfig failed: %d.`

## pseudocode

```c
__int64 __fastcall RRasConfigStore::SetRoutingDomainConfigObject(
        RRasConfigStore *this,
        __int64 a2,
        struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *a3)
{
  void (*v5)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  GUID *v6; // rsi
  struct _RTL_RESOURCE *v7; // r14
  __int64 v8; // rbx
  unsigned int v9; // eax
  GUID *v10; // r9
  unsigned int v11; // ebx
  unsigned int v13; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v15; // [rsp+50h] [rbp-B0h]
  __int128 v16; // [rsp+60h] [rbp-A0h]
  __int64 v17; // [rsp+70h] [rbp-90h]
  int v18; // [rsp+78h] [rbp-88h]
  int v19; // [rsp+7Ch] [rbp-84h]
  GUID v20; // [rsp+80h] [rbp-80h] BYREF
  int v21; // [rsp+90h] [rbp-70h] BYREF
  __int128 v22; // [rsp+94h] [rbp-6Ch]
  __int128 v23; // [rsp+A4h] [rbp-5Ch]
  int v24; // [rsp+B4h] [rbp-4Ch]
  int v25; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v26[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v13 = 0;
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v15 = 0;
  v14 = 0;
  v16 = 0;
  v17 = 0;
  v18 = -1;
  v19 = 0;
  if ( *((_QWORD *)&xmmword_180071090 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v14,
      L"RRasConfigStore::SetRoutingDomainConfigObject",
      &v13,
      v5);
  if ( a3 )
  {
    v6 = 0;
    if ( *(_BYTE *)a3 == 1 )
      v6 = (GUID *)((char *)a3 + 524);
    v7 = (struct _RTL_RESOURCE *)((char *)this + 112);
    RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 112), 1u);
    std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(
      (char *)this + 16,
      &v20,
      v6);
    if ( *(_QWORD *)&v20.Data1 == *((_QWORD *)this + 3) )
    {
      v13 = 1168;
    }
    else
    {
      v8 = *(_QWORD *)(*(_QWORD *)&v20.Data1 + 32LL);
      RtlAcquireResourceExclusive((PRTL_RESOURCE)(v8 + 728), 1u);
      v9 = RRasRoutingDomainConfig::SetConfig((RRasRoutingDomainConfig *)v8, a3);
      v13 = v9;
      if ( v9 && (_QWORD)xmmword_1800710A0 )
      {
        LOWORD(v25) = 0;
        v20 = GUID_NULL;
        LOWORD(v21) = 0;
        FormatRRASErrorString(
          &v25,
          L"%s: pRdObject->SetConfig failed: %d.",
          L"RRasConfigStore::SetRoutingDomainConfigObject",
          v9);
        v10 = &v20;
        if ( v6 )
          v10 = v6;
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_1800710A0,
          &v25,
          v10,
          0,
          &v21);
      }
      RtlReleaseResource((PRTL_RESOURCE)(v8 + 728));
    }
    RtlReleaseResource(v7);
  }
  else
  {
    v13 = 87;
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v25) = 0;
      FormatRRASErrorString(
        &v25,
        L"%hs(Line#%d): Invalid parameter.",
        "RRasConfigStore::SetRoutingDomainConfigObject",
        1217);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v25);
    }
  }
  v11 = v13;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v14);
  return v11;
}

```

## disassembly

```asm
0x180041ca4  mov     [rsp-8+arg_8], rbx
0x180041ca9  push    rbp
0x180041caa  push    rsi
0x180041cab  push    rdi
0x180041cac  push    r14
0x180041cae  push    r15
0x180041cb0  lea     rbp, [rsp-7D0h]
0x180041cb8  sub     rsp, 8D0h
0x180041cbf  mov     rax, cs:__security_cookie
0x180041cc6  xor     rax, rsp
0x180041cc9  mov     [rbp+7F0h+var_30], rax
0x180041cd0  mov     rdi, r8
0x180041cd3  mov     rbx, rcx
0x180041cd6  mov     [rsp+8F0h+var_8B0], 0
0x180041cde  xor     eax, eax
0x180041ce0  mov     [rbp+7F0h+var_830], eax
0x180041ce3  xor     edx, edx; Val
0x180041ce5  mov     r8d, 7FCh; Size
0x180041ceb  lea     rcx, [rbp+7F0h+var_82C]; void *
0x180041cef  call    memset_0
0x180041cf4  xor     eax, eax
0x180041cf6  mov     [rbp+7F0h+var_860], eax
0x180041cf9  xorps   xmm0, xmm0
0x180041cfc  movups  [rbp+7F0h+var_85C], xmm0
0x180041d00  movups  [rbp+7F0h+var_84C], xmm0
0x180041d04  mov     [rbp+7F0h+var_83C], eax
0x180041d07  movdqu  [rsp+8F0h+var_8A0], xmm0
0x180041d0d  mov     [rsp+8F0h+var_8A8], rax
0x180041d12  xorps   xmm1, xmm1
0x180041d15  movdqu  [rsp+8F0h+var_890], xmm1
0x180041d1b  mov     [rsp+8F0h+var_880], rax
0x180041d20  mov     [rsp+8F0h+var_878], 0FFFFFFFFh
0x180041d28  mov     [rsp+8F0h+var_874], eax
0x180041d2c  cmp     qword ptr cs:xmmword_180071090+8, rax
0x180041d33  jz      short loc_180041D4B
0x180041d35  lea     r8, [rsp+8F0h+var_8B0]; unsigned int *
0x180041d3a  lea     rdx, aRrasconfigstor_1; "RRasConfigStore::SetRoutingDomainConfig"...
0x180041d41  lea     rcx, [rsp+8F0h+var_8A8]; this
0x180041d46  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180041d4b  test    rdi, rdi
0x180041d4e  jnz     short loc_180041DAB
0x180041d50  mov     [rsp+8F0h+var_8B0], 57h ; 'W'
0x180041d58  cmp     qword ptr cs:xmmword_180071090, rdi
0x180041d5f  jz      loc_180041E9F
0x180041d65  xor     eax, eax
0x180041d67  mov     word ptr [rbp+7F0h+var_830], ax
0x180041d6b  mov     r9d, 4C1h
0x180041d71  lea     r8, aRrasconfigstor_15; "RRasConfigStore::SetRoutingDomainConfig"...
0x180041d78  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x180041d7f  lea     rcx, [rbp+7F0h+var_830]
0x180041d83  call    FormatRRASErrorString
0x180041d88  lea     r8, [rbp+7F0h+var_830]
0x180041d8c  mov     rdx, qword ptr cs:xmmword_180071090
0x180041d93  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180041d9a  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180041da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041da6  jmp     loc_180041E9F
0x180041dab  xor     esi, esi
0x180041dad  cmp     byte ptr [rdi], 1
0x180041db0  jnz     short loc_180041DB9
0x180041db2  lea     rsi, [rdi+20Ch]
0x180041db9  lea     r14, [rbx+70h]
0x180041dbd  mov     dl, 1; Wait
0x180041dbf  mov     rcx, r14; Resource
0x180041dc2  call    cs:__imp_RtlAcquireResourceShared
0x180041dc8  lea     rcx, [rbx+10h]
0x180041dcc  mov     r8, rsi
0x180041dcf  lea     rdx, [rbp+7F0h+var_870]
0x180041dd3  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x180041dd8  mov     rax, qword ptr [rbp+7F0h+var_870]
0x180041ddc  cmp     rax, [rbx+18h]
0x180041de0  jnz     short loc_180041DEF
0x180041de2  mov     [rsp+8F0h+var_8B0], 490h
0x180041dea  jmp     loc_180041E96
0x180041def  mov     rbx, [rax+20h]
0x180041df3  lea     r15, [rbx+2D8h]
0x180041dfa  mov     dl, 1; Wait
0x180041dfc  mov     rcx, r15; Resource
0x180041dff  call    cs:__imp_RtlAcquireResourceExclusive
0x180041e05  mov     rdx, rdi; struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *
0x180041e08  mov     rcx, rbx; this
0x180041e0b  call    ?SetConfig@RRasRoutingDomainConfig@@QEAAKPEAU_MPRI_ROUTING_DOMAIN_CONFIG_EX@@@Z; RRasRoutingDomainConfig::SetConfig(_MPRI_ROUTING_DOMAIN_CONFIG_EX *)
0x180041e10  mov     r9d, eax
0x180041e13  mov     [rsp+8F0h+var_8B0], eax
0x180041e17  test    eax, eax
0x180041e19  jz      short loc_180041E8D
0x180041e1b  cmp     qword ptr cs:xmmword_1800710A0, 0
0x180041e23  jz      short loc_180041E8D
0x180041e25  xor     eax, eax
0x180041e27  mov     word ptr [rbp+7F0h+var_830], ax
0x180041e2b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180041e32  movdqu  [rbp+7F0h+var_870], xmm0
0x180041e37  mov     word ptr [rbp+7F0h+var_860], ax
0x180041e3b  lea     r8, aRrasconfigstor_1; "RRasConfigStore::SetRoutingDomainConfig"...
0x180041e42  lea     rdx, aSPrdobjectSetc; "%s: pRdObject->SetConfig failed: %d."
0x180041e49  lea     rcx, [rbp+7F0h+var_830]
0x180041e4d  call    FormatRRASErrorString
0x180041e52  lea     r9, [rbp+7F0h+var_870]
0x180041e56  test    rsi, rsi
0x180041e59  cmovnz  r9, rsi
0x180041e5d  lea     rax, [rbp+7F0h+var_860]
0x180041e61  mov     [rsp+8F0h+var_8C8], rax
0x180041e66  mov     [rsp+8F0h+var_8D0], 0
0x180041e6f  lea     r8, [rbp+7F0h+var_830]
0x180041e73  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180041e7a  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180041e81  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180041e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e8d  mov     rcx, r15; Resource
0x180041e90  call    cs:__imp_RtlReleaseResource
0x180041e96  mov     rcx, r14; Resource
0x180041e99  call    cs:__imp_RtlReleaseResource
0x180041e9f  mov     ebx, [rsp+8F0h+var_8B0]
0x180041ea3  lea     rcx, [rsp+8F0h+var_8A8]; this
0x180041ea8  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180041ead  mov     eax, ebx
0x180041eaf  mov     rcx, [rbp+7F0h+var_30]
0x180041eb6  xor     rcx, rsp; StackCookie
0x180041eb9  call    __security_check_cookie
0x180041ebe  mov     rbx, [rsp+8F0h+arg_8]
0x180041ec6  add     rsp, 8D0h
0x180041ecd  pop     r15
0x180041ecf  pop     r14
0x180041ed1  pop     rdi
0x180041ed2  pop     rsi
0x180041ed3  pop     rbp
0x180041ed4  retn
```
