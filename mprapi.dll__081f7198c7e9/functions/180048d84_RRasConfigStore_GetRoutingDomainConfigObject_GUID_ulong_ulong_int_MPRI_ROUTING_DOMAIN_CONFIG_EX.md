# RRasConfigStore::GetRoutingDomainConfigObject(_GUID *,ulong,ulong,int,_MPRI_ROUTING_DOMAIN_CONFIG_EX * *)

- ea: `0x180048d84`
- end: `0x18004909a`
- name: `?GetRoutingDomainConfigObject@RRasConfigStore@@QEAAKPEAU_GUID@@KKHPEAPEAU_MPRI_ROUTING_DOMAIN_CONFIG_EX@@@Z`
- size: `790`
- prototype: `__int64 __fastcall(RRasConfigStore *this, struct _GUID *, int, unsigned int, int, struct _MPRI_ROUTING_DOMAIN_CONFIG_EX **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800416e0`

## callees

- `0x180047dec`
- `0x180048d84`
- `0x18004b3ac`
- `0x18004f0ec`
- `0x18004f89c`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180048efd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180048efd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180048f05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180048f05`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180048f19`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180048f19`
- `ntdll!RtlAcquireResourceShared` at `0x180048e19`
- `ntdll!RtlAcquireResourceShared` at `0x180048e19`
- `ntdll!RtlReleaseResource` at `0x180048edc`
- `ntdll!RtlReleaseResource` at `0x180048f92`
- `ntdll!RtlReleaseResource` at `0x180049020`
- `ntdll!RtlReleaseResource` at `0x180048edc`
- `ntdll!RtlReleaseResource` at `0x180048f92`
- `ntdll!RtlReleaseResource` at `0x180049020`
- `ntdll!RtlAcquireResourceExclusive` at `0x180048e55`
- `ntdll!RtlAcquireResourceExclusive` at `0x180048e55`

## string_xrefs

- `0x180049040`: `RRasConfigStore::GetRoutingDomainConfigObject`
- `0x180048e7c`: `RRasConfigStore::GetRoutingDomainConfigObject`
- `0x180048f3c`: `RRasConfigStore::GetRoutingDomainConfigObject`
- `0x180048faf`: `RRasConfigStore::GetRoutingDomainConfigObject`
- `0x180048e87`: `%s: pRdObject->PopulateFromRegistry failed: %d.`
- `0x180048fbd`: `%s: pRdObject->GetConfig failed: %d.`

## pseudocode

```c
__int64 __fastcall RRasConfigStore::GetRoutingDomainConfigObject(
        RRasConfigStore *this,
        struct _GUID *a2,
        int a3,
        unsigned int a4,
        int a5,
        struct _MPRI_ROUTING_DOMAIN_CONFIG_EX **a6)
{
  struct _RTL_RESOURCE *v9; // r12
  unsigned int Config; // ebx
  __int64 v11; // r13
  unsigned int v12; // eax
  struct _GUID *v13; // r9
  struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *v14; // rax
  HANDLE ProcessHeap; // rax
  struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *v16; // rdi
  _OWORD v21[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v22; // [rsp+70h] [rbp-90h] BYREF
  __int128 v23; // [rsp+74h] [rbp-8Ch]
  __int128 v24; // [rsp+84h] [rbp-7Ch]
  int v25; // [rsp+94h] [rbp-6Ch]
  int v26; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v27[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v22 = 0;
  v25 = 0;
  v23 = 0;
  v24 = 0;
  if ( a2 && a6 )
  {
    v9 = (struct _RTL_RESOURCE *)((char *)this + 112);
    *a6 = 0;
    RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 112), 1u);
    std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(
      (char *)this + 16,
      v21,
      a2);
    if ( *(_QWORD *)&v21[0] == *((_QWORD *)this + 3) )
    {
      Config = 1168;
LABEL_21:
      RtlReleaseResource(v9);
      return Config;
    }
    v11 = *(_QWORD *)(*(_QWORD *)&v21[0] + 32LL);
    RtlAcquireResourceExclusive((PRTL_RESOURCE)(v11 + 728), 1u);
    v12 = RRasRoutingDomainConfig::PopulateFromRegistry((RRasRoutingDomainConfig *)v11);
    Config = v12;
    if ( v12 )
    {
      if ( !(_QWORD)xmmword_180078C60 )
      {
LABEL_9:
        RtlReleaseResource((PRTL_RESOURCE)(v11 + 728));
        goto LABEL_21;
      }
      LOWORD(v26) = 0;
      LOWORD(v22) = 0;
      v21[0] = GUID_NULL;
      FormatRRASErrorString(
        &v26,
        L"%s: pRdObject->PopulateFromRegistry failed: %d.",
        L"RRasConfigStore::GetRoutingDomainConfigObject",
        v12);
      v13 = a2;
    }
    else
    {
      Config = 8;
      if ( a3 >= 0 )
      {
        ProcessHeap = GetProcessHeap();
        v14 = (struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *)HeapAlloc(ProcessHeap, 8u, 0x368u);
      }
      else
      {
        v14 = (struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *)LocalAlloc(0x40u, 0x368u);
      }
      *(_QWORD *)&v21[0] = v14;
      v16 = v14;
      if ( v14 )
      {
        memset_0(v14, 0, 0x368u);
        Config = RRasRoutingDomainConfig::GetConfig((RRasRoutingDomainConfig *)v11, a3, a4, v16);
        RtlReleaseResource((PRTL_RESOURCE)(v11 + 728));
        if ( Config )
        {
          if ( (_QWORD)xmmword_180078C60 )
          {
            LOWORD(v26) = 0;
            LOWORD(v22) = 0;
            v21[1] = GUID_NULL;
            FormatRRASErrorString(
              &v26,
              L"%s: pRdObject->GetConfig failed: %d.",
              L"RRasConfigStore::GetRoutingDomainConfigObject",
              Config);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, struct _GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
              gCfgStoreEtwContext,
              xmmword_180078C60,
              &v26,
              a2,
              0,
              &v22);
          }
          FreeRoutingDomainConfigObject(v21);
        }
        else
        {
          *a6 = v16;
        }
        goto LABEL_21;
      }
      if ( !(_QWORD)xmmword_180078C60 )
        goto LABEL_9;
      LOWORD(v26) = 0;
      LOWORD(v22) = 0;
      v21[0] = GUID_NULL;
      FormatRRASErrorString(&v26, L"%s: Malloc failed.", L"RRasConfigStore::GetRoutingDomainConfigObject");
      v13 = a2;
    }
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, struct _GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180078C60,
      &v26,
      v13,
      0,
      &v22);
    goto LABEL_9;
  }
  Config = 87;
  if ( (_QWORD)xmmword_180078C50 )
  {
    LOWORD(v26) = 0;
    FormatRRASErrorString(
      &v26,
      L"%hs(Line#%d): Invalid parameter.",
      "RRasConfigStore::GetRoutingDomainConfigObject",
      1129);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180078C50,
      &v26);
  }
  return Config;
}

```

## disassembly

```asm
0x180048d84  push    rbp
0x180048d86  push    rbx
0x180048d87  push    rsi
0x180048d88  push    rdi
0x180048d89  push    r12
0x180048d8b  push    r13
0x180048d8d  push    r14
0x180048d8f  push    r15
0x180048d91  lea     rbp, [rsp-7B8h]
0x180048d99  sub     rsp, 8B8h
0x180048da0  mov     rax, cs:__security_cookie
0x180048da7  xor     rax, rsp
0x180048daa  mov     [rbp+7F0h+var_50], rax
0x180048db1  mov     r15, [rbp+7F0h+arg_28]
0x180048db8  mov     r14d, r8d
0x180048dbb  mov     [rsp+8F0h+var_8AC], r8d
0x180048dc0  mov     rdi, rdx
0x180048dc3  mov     [rsp+8F0h+var_8A8], rdx
0x180048dc8  mov     rbx, rcx
0x180048dcb  xor     eax, eax
0x180048dcd  mov     [rsp+8F0h+var_8B0], r9d
0x180048dd2  xor     edx, edx; Val
0x180048dd4  mov     [rbp+7F0h+var_850], eax
0x180048dd7  mov     r8d, 7FCh; Size
0x180048ddd  lea     rcx, [rbp+7F0h+var_84C]; void *
0x180048de1  call    memset_0
0x180048de6  xor     eax, eax
0x180048de8  xorps   xmm0, xmm0
0x180048deb  mov     [rsp+8F0h+var_880], eax
0x180048def  mov     [rbp+7F0h+var_85C], eax
0x180048df2  movups  [rsp+8F0h+var_87C], xmm0
0x180048df7  movups  [rbp+7F0h+var_86C], xmm0
0x180048dfb  test    rdi, rdi
0x180048dfe  jz      loc_180049028
0x180048e04  test    r15, r15
0x180048e07  jz      loc_180049028
0x180048e0d  lea     r12, [rbx+70h]
0x180048e11  mov     [r15], rax
0x180048e14  mov     rcx, r12; Resource
0x180048e17  mov     dl, 1; Wait
0x180048e19  call    cs:__imp_RtlAcquireResourceShared
0x180048e1f  lea     rcx, [rbx+10h]
0x180048e23  mov     r8, rdi
0x180048e26  lea     rdx, [rsp+8F0h+var_8A0]
0x180048e2b  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x180048e30  mov     rax, qword ptr [rsp+8F0h+var_8A0]
0x180048e35  cmp     rax, [rbx+18h]
0x180048e39  jnz     short loc_180048E45
0x180048e3b  mov     ebx, 490h
0x180048e40  jmp     loc_18004901D
0x180048e45  mov     r13, [rax+20h]
0x180048e49  mov     dl, 1; Wait
0x180048e4b  lea     rsi, [r13+2D8h]
0x180048e52  mov     rcx, rsi; Resource
0x180048e55  call    cs:__imp_RtlAcquireResourceExclusive
0x180048e5b  mov     rcx, r13; this
0x180048e5e  call    ?PopulateFromRegistry@RRasRoutingDomainConfig@@QEAAKXZ; RRasRoutingDomainConfig::PopulateFromRegistry(void)
0x180048e63  mov     ebx, eax
0x180048e65  test    eax, eax
0x180048e67  jz      short loc_180048EE7
0x180048e69  cmp     qword ptr cs:xmmword_180078C60, 0
0x180048e71  jz      short loc_180048ED9
0x180048e73  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180048e7a  xor     ecx, ecx
0x180048e7c  lea     r8, aRrasconfigstor_23; "RRasConfigStore::GetRoutingDomainConfig"...
0x180048e83  mov     word ptr [rbp+7F0h+var_850], cx
0x180048e87  lea     rdx, aSPrdobjectPopu; "%s: pRdObject->PopulateFromRegistry fai"...
0x180048e8e  mov     word ptr [rsp+8F0h+var_880], cx
0x180048e93  mov     r9d, eax
0x180048e96  lea     rcx, [rbp+7F0h+var_850]
0x180048e9a  movdqu  [rsp+8F0h+var_8A0], xmm0
0x180048ea0  call    FormatRRASErrorString
0x180048ea5  mov     r9, rdi
0x180048ea8  mov     rdx, qword ptr cs:xmmword_180078C60
0x180048eaf  lea     rax, [rsp+8F0h+var_880]
0x180048eb4  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180048ebb  lea     r8, [rbp+7F0h+var_850]
0x180048ebf  mov     [rsp+8F0h+var_8C8], rax
0x180048ec4  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180048ecb  mov     [rsp+8F0h+var_8D0], 0
0x180048ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ed9  mov     rcx, rsi; Resource
0x180048edc  call    cs:__imp_RtlReleaseResource
0x180048ee2  jmp     loc_18004901D
0x180048ee7  mov     ebx, 8
0x180048eec  test    r14d, r14d
0x180048eef  jns     short loc_180048F05
0x180048ef1  mov     r14d, 368h
0x180048ef7  lea     ecx, [rbx+38h]; uFlags
0x180048efa  mov     edx, r14d; uBytes
0x180048efd  call    cs:__imp_LocalAlloc
0x180048f03  jmp     short loc_180048F1F
0x180048f05  call    cs:__imp_GetProcessHeap
0x180048f0b  mov     r14d, 368h
0x180048f11  mov     edx, ebx; dwFlags
0x180048f13  mov     rcx, rax; hHeap
0x180048f16  mov     r8d, r14d; dwBytes
0x180048f19  call    cs:__imp_HeapAlloc
0x180048f1f  mov     qword ptr [rsp+8F0h+var_8A0], rax
0x180048f24  mov     rdi, rax
0x180048f27  test    rax, rax
0x180048f2a  jnz     short loc_180048F6C
0x180048f2c  cmp     qword ptr cs:xmmword_180078C60, rax
0x180048f33  jz      short loc_180048ED9
0x180048f35  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180048f3c  lea     r8, aRrasconfigstor_23; "RRasConfigStore::GetRoutingDomainConfig"...
0x180048f43  mov     word ptr [rbp+7F0h+var_850], ax
0x180048f47  lea     rdx, aSMallocFailed; "%s: Malloc failed."
0x180048f4e  mov     word ptr [rsp+8F0h+var_880], ax
0x180048f53  lea     rcx, [rbp+7F0h+var_850]
0x180048f57  movdqu  [rsp+8F0h+var_8A0], xmm0
0x180048f5d  call    FormatRRASErrorString
0x180048f62  mov     r9, [rsp+8F0h+var_8A8]
0x180048f67  jmp     loc_180048EA8
0x180048f6c  mov     r8, r14; Size
0x180048f6f  xor     edx, edx; Val
0x180048f71  mov     rcx, rdi; void *
0x180048f74  call    memset_0
0x180048f79  mov     r8d, [rsp+8F0h+var_8B0]; unsigned int
0x180048f7e  mov     r9, rdi; struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *
0x180048f81  mov     edx, [rsp+8F0h+var_8AC]; unsigned int
0x180048f85  mov     rcx, r13; this
0x180048f88  call    ?GetConfig@RRasRoutingDomainConfig@@QEAAKKKPEAU_MPRI_ROUTING_DOMAIN_CONFIG_EX@@@Z; RRasRoutingDomainConfig::GetConfig(ulong,ulong,_MPRI_ROUTING_DOMAIN_CONFIG_EX *)
0x180048f8d  mov     rcx, rsi; Resource
0x180048f90  mov     ebx, eax
0x180048f92  call    cs:__imp_RtlReleaseResource
0x180048f98  test    ebx, ebx
0x180048f9a  jz      short loc_18004901A
0x180048f9c  cmp     qword ptr cs:xmmword_180078C60, 0
0x180048fa4  jz      short loc_18004900E
0x180048fa6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180048fad  xor     eax, eax
0x180048faf  lea     r8, aRrasconfigstor_23; "RRasConfigStore::GetRoutingDomainConfig"...
0x180048fb6  mov     r9d, ebx
0x180048fb9  mov     word ptr [rbp+7F0h+var_850], ax
0x180048fbd  lea     rdx, aSPrdobjectGetc; "%s: pRdObject->GetConfig failed: %d."
0x180048fc4  mov     word ptr [rsp+8F0h+var_880], ax
0x180048fc9  lea     rcx, [rbp+7F0h+var_850]
0x180048fcd  movdqu  [rsp+8F0h+var_890], xmm0
0x180048fd3  call    FormatRRASErrorString
0x180048fd8  mov     r9, [rsp+8F0h+var_8A8]
0x180048fdd  lea     rax, [rsp+8F0h+var_880]
0x180048fe2  mov     rdx, qword ptr cs:xmmword_180078C60
0x180048fe9  lea     r8, [rbp+7F0h+var_850]
0x180048fed  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180048ff4  mov     [rsp+8F0h+var_8C8], rax
0x180048ff9  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180049000  mov     [rsp+8F0h+var_8D0], 0
0x180049009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004900e  lea     rcx, [rsp+8F0h+var_8A0]
0x180049013  call    FreeRoutingDomainConfigObject
0x180049018  jmp     short loc_18004901D
0x18004901a  mov     [r15], rdi
0x18004901d  mov     rcx, r12; Resource
0x180049020  call    cs:__imp_RtlReleaseResource
0x180049026  jmp     short loc_180049075
0x180049028  cmp     qword ptr cs:xmmword_180078C50, rax
0x18004902f  mov     ebx, 57h ; 'W'
0x180049034  jz      short loc_180049075
0x180049036  mov     r9d, 469h
0x18004903c  mov     word ptr [rbp+7F0h+var_850], ax
0x180049040  lea     r8, aRrasconfigstor_0; "RRasConfigStore::GetRoutingDomainConfig"...
0x180049047  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18004904e  lea     rcx, [rbp+7F0h+var_850]
0x180049052  call    FormatRRASErrorString
0x180049057  mov     rdx, qword ptr cs:xmmword_180078C50
0x18004905e  lea     r8, [rbp+7F0h+var_850]
0x180049062  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180049069  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180049070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049075  mov     eax, ebx
0x180049077  mov     rcx, [rbp+7F0h+var_50]
0x18004907e  xor     rcx, rsp; StackCookie
0x180049081  call    __security_check_cookie
0x180049086  add     rsp, 8B8h
0x18004908d  pop     r15
0x18004908f  pop     r14
0x180049091  pop     r13
0x180049093  pop     r12
0x180049095  pop     rdi
0x180049096  pop     rsi
0x180049097  pop     rbx
0x180049098  pop     rbp
0x180049099  retn
```
