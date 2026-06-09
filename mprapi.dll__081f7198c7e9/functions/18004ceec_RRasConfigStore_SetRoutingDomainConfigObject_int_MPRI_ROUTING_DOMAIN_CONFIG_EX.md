# RRasConfigStore::SetRoutingDomainConfigObject(int,_MPRI_ROUTING_DOMAIN_CONFIG_EX *)

- ea: `0x18004ceec`
- end: `0x18004d147`
- name: `?SetRoutingDomainConfigObject@RRasConfigStore@@QEAAKHPEAU_MPRI_ROUTING_DOMAIN_CONFIG_EX@@@Z`
- size: `603`
- prototype: `__int64 __fastcall(RRasConfigStore *this, __int64, struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180042ed0`

## callees

- `0x18004a6c0`
- `0x18004c6dc`
- `0x18004ceec`
- `0x18004f0ec`
- `0x180050b2c`
- `0x180050cd4`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x18004d00a`
- `ntdll!RtlAcquireResourceShared` at `0x18004d00a`
- `ntdll!RtlReleaseResource` at `0x18004d102`
- `ntdll!RtlReleaseResource` at `0x18004d10b`
- `ntdll!RtlReleaseResource` at `0x18004d102`
- `ntdll!RtlReleaseResource` at `0x18004d10b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004d047`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004d047`

## string_xrefs

- `0x18004cf82`: `RRasConfigStore::SetRoutingDomainConfigObject`
- `0x18004d0b4`: `RRasConfigStore::SetRoutingDomainConfigObject`
- `0x18004cfb9`: `RRasConfigStore::SetRoutingDomainConfigObject`
- `0x18004d071`: `%s: pRdObject->SetConfig failed: %d.`
- `0x18004d097`: `%s: pRdObject->PersistConfig failed: %d.`

## pseudocode

```c
__int64 __fastcall RRasConfigStore::SetRoutingDomainConfigObject(
        RRasConfigStore *this,
        __int64 a2,
        struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *a3)
{
  void (*v5)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  GUID *v6; // rdi
  struct _RTL_RESOURCE *v7; // r14
  __int64 v8; // rsi
  __int64 v9; // r8
  void (*v10)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int v11; // eax
  __int64 v12; // r9
  const wchar_t *v13; // rdx
  unsigned int v14; // eax
  GUID *v15; // r9
  unsigned int v16; // ebx
  unsigned int v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v20; // [rsp+50h] [rbp-B0h]
  __int128 v21; // [rsp+60h] [rbp-A0h]
  __int64 v22; // [rsp+70h] [rbp-90h]
  int v23; // [rsp+78h] [rbp-88h]
  int v24; // [rsp+7Ch] [rbp-84h]
  GUID v25; // [rsp+80h] [rbp-80h] BYREF
  int v26; // [rsp+90h] [rbp-70h] BYREF
  __int128 v27; // [rsp+94h] [rbp-6Ch]
  __int128 v28; // [rsp+A4h] [rbp-5Ch]
  int v29; // [rsp+B4h] [rbp-4Ch]
  int v30; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v31[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v18 = 0;
  v30 = 0;
  memset_0(v31, 0, sizeof(v31));
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v20 = 0;
  v19 = 0;
  v21 = 0;
  v22 = 0;
  v23 = -1;
  v24 = 0;
  if ( *((_QWORD *)&xmmword_180078C50 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v19,
      L"RRasConfigStore::SetRoutingDomainConfigObject",
      &v18,
      v5);
  if ( a3 )
  {
    v6 = 0;
    if ( *(_BYTE *)a3 == 1 )
      v6 = (GUID *)((char *)a3 + 524);
    v7 = (struct _RTL_RESOURCE *)((char *)this + 112);
    RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 112), 1u);
    std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(
      (_QWORD *)this + 2,
      &v25,
      (__int64)v6);
    if ( *(_QWORD *)&v25.Data1 == *((_QWORD *)this + 3) )
    {
      v18 = 1168;
LABEL_20:
      RtlReleaseResource(v7);
      goto LABEL_21;
    }
    v8 = *(_QWORD *)(*(_QWORD *)&v25.Data1 + 32LL);
    RtlAcquireResourceExclusive((PRTL_RESOURCE)(v8 + 728), 1u);
    v11 = RRasRoutingDomainConfig::SetConfig((RRasRoutingDomainConfig *)v8, a3, v9, v10);
    v12 = v11;
    v18 = v11;
    if ( v11 )
    {
      if ( (_QWORD)xmmword_180078C60 )
      {
        v13 = L"%s: pRdObject->SetConfig failed: %d.";
LABEL_16:
        LOWORD(v30) = 0;
        v25 = GUID_NULL;
        LOWORD(v26) = 0;
        FormatRRASErrorString(&v30, v13, L"RRasConfigStore::SetRoutingDomainConfigObject", v12);
        v15 = &v25;
        if ( v6 )
          v15 = v6;
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_180078C60,
          &v30,
          v15,
          0,
          &v26);
      }
    }
    else
    {
      v14 = RRasRoutingDomainConfig::PersistConfig((RRasRoutingDomainConfig *)v8);
      v12 = v14;
      v18 = v14;
      if ( v14 && (_QWORD)xmmword_180078C60 )
      {
        v13 = L"%s: pRdObject->PersistConfig failed: %d.";
        goto LABEL_16;
      }
    }
    RtlReleaseResource((PRTL_RESOURCE)(v8 + 728));
    goto LABEL_20;
  }
  v18 = 87;
  if ( (_QWORD)xmmword_180078C50 )
  {
    LOWORD(v30) = 0;
    FormatRRASErrorString(
      &v30,
      L"%hs(Line#%d): Invalid parameter.",
      "RRasConfigStore::SetRoutingDomainConfigObject",
      1217);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180078C50,
      &v30);
  }
LABEL_21:
  v16 = v18;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v19);
  return v16;
}

```

## disassembly

```asm
0x18004ceec  mov     [rsp-8+arg_8], rbx
0x18004cef1  push    rbp
0x18004cef2  push    rsi
0x18004cef3  push    rdi
0x18004cef4  push    r14
0x18004cef6  push    r15
0x18004cef8  lea     rbp, [rsp-7D0h]
0x18004cf00  sub     rsp, 8D0h
0x18004cf07  mov     rax, cs:__security_cookie
0x18004cf0e  xor     rax, rsp
0x18004cf11  mov     [rbp+7F0h+var_30], rax
0x18004cf18  mov     rbx, r8
0x18004cf1b  mov     rsi, rcx
0x18004cf1e  mov     [rsp+8F0h+var_8B0], 0
0x18004cf26  xor     eax, eax
0x18004cf28  mov     [rbp+7F0h+var_830], eax
0x18004cf2b  xor     edx, edx; Val
0x18004cf2d  mov     r8d, 7FCh; Size
0x18004cf33  lea     rcx, [rbp+7F0h+var_82C]; void *
0x18004cf37  call    memset_0
0x18004cf3c  xor     eax, eax
0x18004cf3e  mov     [rbp+7F0h+var_860], eax
0x18004cf41  xorps   xmm0, xmm0
0x18004cf44  movups  [rbp+7F0h+var_85C], xmm0
0x18004cf48  movups  [rbp+7F0h+var_84C], xmm0
0x18004cf4c  mov     [rbp+7F0h+var_83C], eax
0x18004cf4f  movdqu  [rsp+8F0h+var_8A0], xmm0
0x18004cf55  mov     [rsp+8F0h+var_8A8], rax
0x18004cf5a  xorps   xmm1, xmm1
0x18004cf5d  movdqu  [rsp+8F0h+var_890], xmm1
0x18004cf63  mov     [rsp+8F0h+var_880], rax
0x18004cf68  mov     [rsp+8F0h+var_878], 0FFFFFFFFh
0x18004cf70  mov     [rsp+8F0h+var_874], eax
0x18004cf74  cmp     qword ptr cs:xmmword_180078C50+8, rax
0x18004cf7b  jz      short loc_18004CF93
0x18004cf7d  lea     r8, [rsp+8F0h+var_8B0]; unsigned int *
0x18004cf82  lea     rdx, aRrasconfigstor_1; "RRasConfigStore::SetRoutingDomainConfig"...
0x18004cf89  lea     rcx, [rsp+8F0h+var_8A8]; this
0x18004cf8e  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18004cf93  test    rbx, rbx
0x18004cf96  jnz     short loc_18004CFF3
0x18004cf98  mov     [rsp+8F0h+var_8B0], 57h ; 'W'
0x18004cfa0  cmp     qword ptr cs:xmmword_180078C50, rbx
0x18004cfa7  jz      loc_18004D111
0x18004cfad  xor     eax, eax
0x18004cfaf  mov     word ptr [rbp+7F0h+var_830], ax
0x18004cfb3  mov     r9d, 4C1h
0x18004cfb9  lea     r8, aRrasconfigstor_12; "RRasConfigStore::SetRoutingDomainConfig"...
0x18004cfc0  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18004cfc7  lea     rcx, [rbp+7F0h+var_830]
0x18004cfcb  call    FormatRRASErrorString
0x18004cfd0  lea     r8, [rbp+7F0h+var_830]
0x18004cfd4  mov     rdx, qword ptr cs:xmmword_180078C50
0x18004cfdb  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004cfe2  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004cfe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cfee  jmp     loc_18004D111
0x18004cff3  xor     edi, edi
0x18004cff5  cmp     byte ptr [rbx], 1
0x18004cff8  jnz     short loc_18004D001
0x18004cffa  lea     rdi, [rbx+20Ch]
0x18004d001  lea     r14, [rsi+70h]
0x18004d005  mov     dl, 1; Wait
0x18004d007  mov     rcx, r14; Resource
0x18004d00a  call    cs:__imp_RtlAcquireResourceShared
0x18004d010  lea     rcx, [rsi+10h]
0x18004d014  mov     r8, rdi
0x18004d017  lea     rdx, [rbp+7F0h+var_870]
0x18004d01b  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x18004d020  mov     rax, qword ptr [rbp+7F0h+var_870]
0x18004d024  cmp     rax, [rsi+18h]
0x18004d028  jnz     short loc_18004D037
0x18004d02a  mov     [rsp+8F0h+var_8B0], 490h
0x18004d032  jmp     loc_18004D108
0x18004d037  mov     rsi, [rax+20h]
0x18004d03b  lea     r15, [rsi+2D8h]
0x18004d042  mov     dl, 1; Wait
0x18004d044  mov     rcx, r15; Resource
0x18004d047  call    cs:__imp_RtlAcquireResourceExclusive
0x18004d04d  mov     rdx, rbx; struct _MPRI_ROUTING_DOMAIN_CONFIG_EX *
0x18004d050  mov     rcx, rsi; this
0x18004d053  call    ?SetConfig@RRasRoutingDomainConfig@@QEAAKPEAU_MPRI_ROUTING_DOMAIN_CONFIG_EX@@@Z; RRasRoutingDomainConfig::SetConfig(_MPRI_ROUTING_DOMAIN_CONFIG_EX *)
0x18004d058  mov     r9d, eax
0x18004d05b  mov     [rsp+8F0h+var_8B0], eax
0x18004d05f  test    eax, eax
0x18004d061  jz      short loc_18004D07A
0x18004d063  cmp     qword ptr cs:xmmword_180078C60, 0
0x18004d06b  jz      loc_18004D0FF
0x18004d071  lea     rdx, aSPrdobjectSetc; "%s: pRdObject->SetConfig failed: %d."
0x18004d078  jmp     short loc_18004D09E
0x18004d07a  mov     rcx, rsi; this
0x18004d07d  call    ?PersistConfig@RRasRoutingDomainConfig@@QEAAKXZ; RRasRoutingDomainConfig::PersistConfig(void)
0x18004d082  mov     r9d, eax
0x18004d085  mov     [rsp+8F0h+var_8B0], eax
0x18004d089  test    eax, eax
0x18004d08b  jz      short loc_18004D0FF
0x18004d08d  cmp     qword ptr cs:xmmword_180078C60, 0
0x18004d095  jz      short loc_18004D0FF
0x18004d097  lea     rdx, aSPrdobjectPers; "%s: pRdObject->PersistConfig failed: %d"...
0x18004d09e  xor     eax, eax
0x18004d0a0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004d0a7  mov     word ptr [rbp+7F0h+var_830], ax
0x18004d0ab  movdqu  [rbp+7F0h+var_870], xmm0
0x18004d0b0  mov     word ptr [rbp+7F0h+var_860], ax
0x18004d0b4  lea     r8, aRrasconfigstor_1; "RRasConfigStore::SetRoutingDomainConfig"...
0x18004d0bb  lea     rcx, [rbp+7F0h+var_830]
0x18004d0bf  call    FormatRRASErrorString
0x18004d0c4  lea     rax, [rbp+7F0h+var_860]
0x18004d0c8  mov     [rsp+8F0h+var_8C8], rax
0x18004d0cd  lea     r9, [rbp+7F0h+var_870]
0x18004d0d1  test    rdi, rdi
0x18004d0d4  mov     [rsp+8F0h+var_8D0], 0
0x18004d0dd  cmovnz  r9, rdi
0x18004d0e1  lea     r8, [rbp+7F0h+var_830]
0x18004d0e5  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004d0ec  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004d0f3  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004d0fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0ff  mov     rcx, r15; Resource
0x18004d102  call    cs:__imp_RtlReleaseResource
0x18004d108  mov     rcx, r14; Resource
0x18004d10b  call    cs:__imp_RtlReleaseResource
0x18004d111  mov     ebx, [rsp+8F0h+var_8B0]
0x18004d115  lea     rcx, [rsp+8F0h+var_8A8]; this
0x18004d11a  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18004d11f  mov     eax, ebx
0x18004d121  mov     rcx, [rbp+7F0h+var_30]
0x18004d128  xor     rcx, rsp; StackCookie
0x18004d12b  call    __security_check_cookie
0x18004d130  mov     rbx, [rsp+8F0h+arg_8]
0x18004d138  add     rsp, 8D0h
0x18004d13f  pop     r15
0x18004d141  pop     r14
0x18004d143  pop     rdi
0x18004d144  pop     rsi
0x18004d145  pop     rbp
0x18004d146  retn
```
