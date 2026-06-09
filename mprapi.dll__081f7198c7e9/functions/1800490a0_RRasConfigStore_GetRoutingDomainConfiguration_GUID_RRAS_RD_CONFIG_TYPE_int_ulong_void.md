# RRasConfigStore::GetRoutingDomainConfiguration(_GUID *,_RRAS_RD_CONFIG_TYPE,int,ulong *,void *)

- ea: `0x1800490a0`
- end: `0x1800492a1`
- name: `?GetRoutingDomainConfiguration@RRasConfigStore@@QEAAKPEAU_GUID@@W4_RRAS_RD_CONFIG_TYPE@@HPEAKPEAX@Z`
- size: `513`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, int, int, __int64, char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800418e0`

## callees

- `0x180047ff4`
- `0x1800490a0`
- `0x18004f0ec`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x180049134`
- `ntdll!RtlAcquireResourceShared` at `0x18004917a`
- `ntdll!RtlAcquireResourceShared` at `0x180049134`
- `ntdll!RtlAcquireResourceShared` at `0x18004917a`
- `ntdll!RtlReleaseResource` at `0x18004919d`
- `ntdll!RtlReleaseResource` at `0x1800491a6`
- `ntdll!RtlReleaseResource` at `0x18004919d`
- `ntdll!RtlReleaseResource` at `0x1800491a6`
- `ntdll!RtlAcquireResourceExclusive` at `0x180049172`
- `ntdll!RtlAcquireResourceExclusive` at `0x180049172`

## string_xrefs

- `0x1800491ce`: `RRasConfigStore::GetRoutingDomainConfiguration`
- `0x180049216`: `RRasConfigStore::GetRoutingDomainConfiguration`

## pseudocode

```c
__int64 __fastcall RRasConfigStore::GetRoutingDomainConfiguration(
        __int64 a1,
        const struct _GUID *a2,
        int a3,
        int a4,
        __int64 a5,
        char *a6)
{
  struct _RTL_RESOURCE *v10; // rsi
  unsigned int v11; // ebx
  __int64 v12; // rbx
  struct _RTL_RESOURCE *v13; // rcx
  unsigned int ConfigParam; // eax
  struct _RTL_RESOURCE *v15; // rcx
  const struct _GUID *v16; // r9
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  GUID v19; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v21; // [rsp+5Ch] [rbp-A4h]
  __int128 v22; // [rsp+6Ch] [rbp-94h]
  int v23; // [rsp+7Ch] [rbp-84h]
  int v24; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v25[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  *(_QWORD *)&v19.Data1 = a5;
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v20 = 0;
  v23 = 0;
  v21 = 0;
  v22 = 0;
  if ( a2 && a6 )
  {
    v10 = (struct _RTL_RESOURCE *)(a1 + 112);
    RtlAcquireResourceShared((PRTL_RESOURCE)(a1 + 112), 1u);
    std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(
      a1 + 16,
      &v18,
      a2);
    if ( v18 == *(_QWORD *)(a1 + 24) )
    {
      v11 = 1168;
    }
    else
    {
      v12 = *(_QWORD *)(v18 + 32);
      v13 = (struct _RTL_RESOURCE *)(v12 + 728);
      if ( a4 )
        RtlAcquireResourceExclusive(v13, 1u);
      else
        RtlAcquireResourceShared(v13, 1u);
      ConfigParam = RRasRoutingDomainConfig::GetConfigParam(v12, a3, a4, *(unsigned int **)&v19.Data1, a6);
      v15 = (struct _RTL_RESOURCE *)(v12 + 728);
      v11 = ConfigParam;
      RtlReleaseResource(v15);
    }
    RtlReleaseResource(v10);
    if ( !v11 )
      return v11;
  }
  else
  {
    v11 = 87;
    if ( (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(
        &v24,
        L"%hs(Line#%d): Invalid parameter.",
        "RRasConfigStore::GetRoutingDomainConfiguration",
        949);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C50,
        &v24);
    }
  }
  if ( (_QWORD)xmmword_180078C60 )
  {
    LOWORD(v24) = 0;
    LOWORD(v20) = 0;
    v19 = GUID_NULL;
    FormatRRASErrorString(&v24, L"%s: failed: %d.", L"RRasConfigStore::GetRoutingDomainConfiguration", v11);
    v16 = &v19;
    if ( a2 )
      v16 = a2;
    gCfgStoreParamTemplateFunc(
      gCfgStoreEtwContext,
      (const struct _EVENT_DESCRIPTOR *)xmmword_180078C60,
      (const unsigned __int16 *)&v24,
      v16,
      0,
      (const unsigned __int16 *)&v20);
  }
  return v11;
}

```

## disassembly

```asm
0x1800490a0  push    rbp
0x1800490a2  push    rbx
0x1800490a3  push    rsi
0x1800490a4  push    rdi
0x1800490a5  push    r12
0x1800490a7  push    r13
0x1800490a9  push    r14
0x1800490ab  push    r15
0x1800490ad  lea     rbp, [rsp-798h]
0x1800490b5  sub     rsp, 898h
0x1800490bc  mov     rax, cs:__security_cookie
0x1800490c3  xor     rax, rsp
0x1800490c6  mov     [rbp+7D0h+var_50], rax
0x1800490cd  mov     rax, [rbp+7D0h+arg_20]
0x1800490d4  mov     r13d, r8d
0x1800490d7  mov     r14, [rbp+7D0h+arg_28]
0x1800490de  mov     r12, rdx
0x1800490e1  mov     qword ptr [rsp+8D0h+var_888], rax
0x1800490e6  mov     rbx, rcx
0x1800490e9  xor     eax, eax
0x1800490eb  lea     rcx, [rbp+7D0h+var_84C]; void *
0x1800490ef  xor     edx, edx; Val
0x1800490f1  mov     [rbp+7D0h+var_850], eax
0x1800490f4  mov     r8d, 7FCh; Size
0x1800490fa  mov     r15d, r9d
0x1800490fd  call    memset_0
0x180049102  xor     eax, eax
0x180049104  xorps   xmm0, xmm0
0x180049107  mov     [rsp+8D0h+var_878], eax
0x18004910b  mov     [rsp+8D0h+var_854], eax
0x18004910f  movups  [rsp+8D0h+var_874], xmm0
0x180049114  movups  [rsp+8D0h+var_864], xmm0
0x180049119  test    r12, r12
0x18004911c  jz      loc_1800491B6
0x180049122  test    r14, r14
0x180049125  jz      loc_1800491B6
0x18004912b  lea     rsi, [rbx+70h]
0x18004912f  mov     dl, 1; Wait
0x180049131  mov     rcx, rsi; Resource
0x180049134  call    cs:__imp_RtlAcquireResourceShared
0x18004913a  lea     rcx, [rbx+10h]
0x18004913e  mov     r8, r12
0x180049141  lea     rdx, [rsp+8D0h+var_890]
0x180049146  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x18004914b  mov     rax, [rsp+8D0h+var_890]
0x180049150  cmp     rax, [rbx+18h]
0x180049154  jnz     short loc_18004915D
0x180049156  mov     ebx, 490h
0x18004915b  jmp     short loc_1800491A3
0x18004915d  mov     rbx, [rax+20h]
0x180049161  mov     dl, 1; Wait
0x180049163  lea     rdi, [rbx+2D8h]
0x18004916a  mov     rcx, rdi; Resource
0x18004916d  test    r15d, r15d
0x180049170  jz      short loc_18004917A
0x180049172  call    cs:__imp_RtlAcquireResourceExclusive
0x180049178  jmp     short loc_180049180
0x18004917a  call    cs:__imp_RtlAcquireResourceShared
0x180049180  mov     r9, qword ptr [rsp+8D0h+var_888]
0x180049185  mov     r8d, r15d
0x180049188  mov     edx, r13d
0x18004918b  mov     [rsp+8D0h+var_8B0], r14
0x180049190  mov     rcx, rbx
0x180049193  call    ?GetConfigParam@RRasRoutingDomainConfig@@QEAAKW4_RRAS_RD_CONFIG_TYPE@@HPEAKPEAX@Z; RRasRoutingDomainConfig::GetConfigParam(_RRAS_RD_CONFIG_TYPE,int,ulong *,void *)
0x180049198  mov     rcx, rdi; Resource
0x18004919b  mov     ebx, eax
0x18004919d  call    cs:__imp_RtlReleaseResource
0x1800491a3  mov     rcx, rsi; Resource
0x1800491a6  call    cs:__imp_RtlReleaseResource
0x1800491ac  test    ebx, ebx
0x1800491ae  jz      loc_18004927C
0x1800491b4  jmp     short loc_180049203
0x1800491b6  cmp     qword ptr cs:xmmword_180078C50, rax
0x1800491bd  mov     ebx, 57h ; 'W'
0x1800491c2  jz      short loc_180049203
0x1800491c4  mov     r9d, 3B5h
0x1800491ca  mov     word ptr [rbp+7D0h+var_850], ax
0x1800491ce  lea     r8, aRrasconfigstor_3; "RRasConfigStore::GetRoutingDomainConfig"...
0x1800491d5  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x1800491dc  lea     rcx, [rbp+7D0h+var_850]
0x1800491e0  call    FormatRRASErrorString
0x1800491e5  mov     rdx, qword ptr cs:xmmword_180078C50
0x1800491ec  lea     r8, [rbp+7D0h+var_850]
0x1800491f0  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x1800491f7  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800491fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049203  cmp     qword ptr cs:xmmword_180078C60, 0
0x18004920b  jz      short loc_18004927C
0x18004920d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180049214  xor     eax, eax
0x180049216  lea     r8, aRrasconfigstor_6; "RRasConfigStore::GetRoutingDomainConfig"...
0x18004921d  mov     r9d, ebx
0x180049220  mov     word ptr [rbp+7D0h+var_850], ax
0x180049224  lea     rdx, aSFailedD; "%s: failed: %d."
0x18004922b  mov     word ptr [rsp+8D0h+var_878], ax
0x180049230  lea     rcx, [rbp+7D0h+var_850]
0x180049234  movdqu  [rsp+8D0h+var_888], xmm0
0x18004923a  call    FormatRRASErrorString
0x18004923f  mov     rdx, qword ptr cs:xmmword_180078C60
0x180049246  lea     rax, [rsp+8D0h+var_878]
0x18004924b  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180049252  lea     r9, [rsp+8D0h+var_888]
0x180049257  mov     [rsp+8D0h+var_8A8], rax
0x18004925c  lea     r8, [rbp+7D0h+var_850]
0x180049260  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180049267  test    r12, r12
0x18004926a  mov     [rsp+8D0h+var_8B0], 0
0x180049273  cmovnz  r9, r12
0x180049277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004927c  mov     eax, ebx
0x18004927e  mov     rcx, [rbp+7D0h+var_50]
0x180049285  xor     rcx, rsp; StackCookie
0x180049288  call    __security_check_cookie
0x18004928d  add     rsp, 898h
0x180049294  pop     r15
0x180049296  pop     r14
0x180049298  pop     r13
0x18004929a  pop     r12
0x18004929c  pop     rdi
0x18004929d  pop     rsi
0x18004929e  pop     rbx
0x18004929f  pop     rbp
0x1800492a0  retn
```
