# RRasConfigStore::DisableRoutingDomainOnRRAS(_GUID *)

- ea: `0x180046ea8`
- end: `0x1800470ca`
- name: `?DisableRoutingDomainOnRRAS@RRasConfigStore@@QEAAKPEAU_GUID@@@Z`
- size: `546`
- prototype: `__int64 __fastcall(RRasConfigStore *this, struct _GUID *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180040e20`

## callees

- `0x1800442f8`
- `0x180046ea8`
- `0x18004c448`
- `0x18004efb0`
- `0x18004f0ec`
- `0x180050b2c`
- `0x180050be8`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180047084`
- `msvcrt!??3@YAXPEAX@Z` at `0x180047084`
- `ntdll!RtlReleaseResource` at `0x18004708d`
- `ntdll!RtlReleaseResource` at `0x18004708d`
- `ntdll!RtlAcquireResourceExclusive` at `0x180046fbf`
- `ntdll!RtlAcquireResourceExclusive` at `0x180046fbf`

## string_xrefs

- `0x180046f45`: `RRasConfigStore::DisableRoutingDomainOnRRAS`
- `0x180047011`: `RRasConfigStore::DisableRoutingDomainOnRRAS`
- `0x180046f7c`: `RRasConfigStore::DisableRoutingDomainOnRRAS`
- `0x180047018`: `%s: Routing domain not configured.`

## pseudocode

```c
__int64 __fastcall RRasConfigStore::DisableRoutingDomainOnRRAS(RRasConfigStore *this, struct _GUID *a2)
{
  void (*v4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  struct _RTL_RESOURCE *v5; // rsi
  char *v6; // r14
  RRasRoutingDomainConfig *v7; // rbx
  unsigned int v8; // ebx
  unsigned __int16 *v10; // [rsp+28h] [rbp-D8h]
  unsigned int v11; // [rsp+30h] [rbp-D0h]
  unsigned int v12; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v14; // [rsp+50h] [rbp-B0h]
  __int128 v15; // [rsp+60h] [rbp-A0h]
  __int64 v16; // [rsp+70h] [rbp-90h]
  int v17; // [rsp+78h] [rbp-88h]
  int v18; // [rsp+7Ch] [rbp-84h]
  GUID v19; // [rsp+80h] [rbp-80h] BYREF
  int v20; // [rsp+90h] [rbp-70h] BYREF
  __int128 v21; // [rsp+94h] [rbp-6Ch]
  __int128 v22; // [rsp+A4h] [rbp-5Ch]
  int v23; // [rsp+B4h] [rbp-4Ch]
  int v24; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v25[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v12 = 0;
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v14 = 0;
  v13 = 0;
  v15 = 0;
  v16 = 0;
  v17 = -1;
  v18 = 0;
  if ( *((_QWORD *)&xmmword_180078C60 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v13,
      L"RRasConfigStore::DisableRoutingDomainOnRRAS",
      &v12,
      v4,
      a2,
      v10,
      v11);
  if ( a2 )
  {
    v5 = (struct _RTL_RESOURCE *)((char *)this + 112);
    RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 112), 1u);
    v6 = (char *)this + 16;
    std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(
      (char *)this + 16,
      &v19,
      a2);
    if ( *(_QWORD *)&v19.Data1 == *((_QWORD *)this + 3) )
    {
      v12 = 1168;
      if ( (_QWORD)xmmword_180078C60 )
      {
        LOWORD(v24) = 0;
        v19 = GUID_NULL;
        LOWORD(v20) = 0;
        FormatRRASErrorString(
          &v24,
          L"%s: Routing domain not configured.",
          L"RRasConfigStore::DisableRoutingDomainOnRRAS");
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, struct _GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_180078C60,
          &v24,
          a2,
          0,
          &v20);
      }
    }
    else
    {
      v7 = *(RRasRoutingDomainConfig **)(*(_QWORD *)&v19.Data1 + 32LL);
      RRasRoutingDomainConfig::RemoveConfigurationFromRegistry(v7);
      std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::erase(
        v6,
        a2);
      if ( v7 )
      {
        RRasRoutingDomainConfig::~RRasRoutingDomainConfig(v7);
        operator delete(v7);
      }
    }
    RtlReleaseResource(v5);
  }
  else
  {
    v12 = 87;
    if ( (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(
        &v24,
        L"%hs(Line#%d): Invalid parameter.",
        "RRasConfigStore::DisableRoutingDomainOnRRAS",
        556);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C50,
        &v24);
    }
  }
  v8 = v12;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v13);
  return v8;
}

```

## disassembly

```asm
0x180046ea8  mov     [rsp-8+arg_10], rbx
0x180046ead  mov     [rsp-8+arg_18], rsi
0x180046eb2  push    rbp
0x180046eb3  push    rdi
0x180046eb4  push    r14
0x180046eb6  lea     rbp, [rsp-7D0h]
0x180046ebe  sub     rsp, 8D0h
0x180046ec5  mov     rax, cs:__security_cookie
0x180046ecc  xor     rax, rsp
0x180046ecf  mov     [rbp+7E0h+var_20], rax
0x180046ed6  mov     rdi, rdx
0x180046ed9  mov     rbx, rcx
0x180046edc  mov     [rsp+8E0h+var_8A0], 0
0x180046ee4  xor     eax, eax
0x180046ee6  mov     [rbp+7E0h+var_820], eax
0x180046ee9  xor     edx, edx; Val
0x180046eeb  mov     r8d, 7FCh; Size
0x180046ef1  lea     rcx, [rbp+7E0h+var_81C]; void *
0x180046ef5  call    memset_0
0x180046efa  xor     eax, eax
0x180046efc  mov     [rbp+7E0h+var_850], eax
0x180046eff  xorps   xmm0, xmm0
0x180046f02  movups  [rbp+7E0h+var_84C], xmm0
0x180046f06  movups  [rbp+7E0h+var_83C], xmm0
0x180046f0a  mov     [rbp+7E0h+var_82C], eax
0x180046f0d  movdqu  [rsp+8E0h+var_890], xmm0
0x180046f13  mov     [rsp+8E0h+var_898], rax
0x180046f18  xorps   xmm1, xmm1
0x180046f1b  movdqu  [rsp+8E0h+var_880], xmm1
0x180046f21  mov     [rsp+8E0h+var_870], rax
0x180046f26  mov     [rsp+8E0h+var_868], 0FFFFFFFFh
0x180046f2e  mov     [rsp+8E0h+var_864], eax
0x180046f32  cmp     qword ptr cs:xmmword_180078C60+8, rax
0x180046f39  jz      short loc_180046F56
0x180046f3b  mov     [rsp+8E0h+var_8C0], rdi; struct _GUID *
0x180046f40  lea     r8, [rsp+8E0h+var_8A0]; unsigned int *
0x180046f45  lea     rdx, aRrasconfigstor_9; "RRasConfigStore::DisableRoutingDomainOn"...
0x180046f4c  lea     rcx, [rsp+8E0h+var_898]; this
0x180046f51  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180046f56  test    rdi, rdi
0x180046f59  jnz     short loc_180046FB6
0x180046f5b  mov     [rsp+8E0h+var_8A0], 57h ; 'W'
0x180046f63  cmp     qword ptr cs:xmmword_180078C50, rdi
0x180046f6a  jz      loc_180047093
0x180046f70  xor     eax, eax
0x180046f72  mov     word ptr [rbp+7E0h+var_820], ax
0x180046f76  mov     r9d, 22Ch
0x180046f7c  lea     r8, aRrasconfigstor_25; "RRasConfigStore::DisableRoutingDomainOn"...
0x180046f83  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x180046f8a  lea     rcx, [rbp+7E0h+var_820]
0x180046f8e  call    FormatRRASErrorString
0x180046f93  lea     r8, [rbp+7E0h+var_820]
0x180046f97  mov     rdx, qword ptr cs:xmmword_180078C50
0x180046f9e  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180046fa5  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180046fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046fb1  jmp     loc_180047093
0x180046fb6  lea     rsi, [rbx+70h]
0x180046fba  mov     dl, 1; Wait
0x180046fbc  mov     rcx, rsi; Resource
0x180046fbf  call    cs:__imp_RtlAcquireResourceExclusive
0x180046fc5  lea     r14, [rbx+10h]
0x180046fc9  mov     r8, rdi
0x180046fcc  lea     rdx, [rbp+7E0h+var_860]
0x180046fd0  mov     rcx, r14
0x180046fd3  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x180046fd8  mov     rax, qword ptr [rbp+7E0h+var_860]
0x180046fdc  cmp     rax, [rbx+18h]
0x180046fe0  jnz     short loc_18004705D
0x180046fe2  mov     r9d, 490h
0x180046fe8  mov     [rsp+8E0h+var_8A0], r9d
0x180046fed  cmp     qword ptr cs:xmmword_180078C60, 0
0x180046ff5  jz      loc_18004708A
0x180046ffb  xor     eax, eax
0x180046ffd  mov     word ptr [rbp+7E0h+var_820], ax
0x180047001  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180047008  movdqu  [rbp+7E0h+var_860], xmm0
0x18004700d  mov     word ptr [rbp+7E0h+var_850], ax
0x180047011  lea     r8, aRrasconfigstor_9; "RRasConfigStore::DisableRoutingDomainOn"...
0x180047018  lea     rdx, aSRoutingDomain_1; "%s: Routing domain not configured."
0x18004701f  lea     rcx, [rbp+7E0h+var_820]
0x180047023  call    FormatRRASErrorString
0x180047028  lea     rax, [rbp+7E0h+var_850]
0x18004702c  mov     [rsp+8E0h+var_8B8], rax
0x180047031  mov     [rsp+8E0h+var_8C0], 0
0x18004703a  mov     r9, rdi
0x18004703d  lea     r8, [rbp+7E0h+var_820]
0x180047041  mov     rdx, qword ptr cs:xmmword_180078C60
0x180047048  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004704f  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180047056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004705b  jmp     short loc_18004708A
0x18004705d  mov     rbx, [rax+20h]
0x180047061  mov     rcx, rbx; this
0x180047064  call    ?RemoveConfigurationFromRegistry@RRasRoutingDomainConfig@@QEAAKXZ; RRasRoutingDomainConfig::RemoveConfigurationFromRegistry(void)
0x180047069  mov     rdx, rdi
0x18004706c  mov     rcx, r14
0x18004706f  call    ?erase@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA_KAEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::erase(_GUID const &)
0x180047074  test    rbx, rbx
0x180047077  jz      short loc_18004708A
0x180047079  mov     rcx, rbx; this
0x18004707c  call    ??1RRasRoutingDomainConfig@@QEAA@XZ; RRasRoutingDomainConfig::~RRasRoutingDomainConfig(void)
0x180047081  mov     rcx, rbx
0x180047084  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004708a  mov     rcx, rsi; Resource
0x18004708d  call    cs:__imp_RtlReleaseResource
0x180047093  mov     ebx, [rsp+8E0h+var_8A0]
0x180047097  lea     rcx, [rsp+8E0h+var_898]; this
0x18004709c  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800470a1  mov     eax, ebx
0x1800470a3  mov     rcx, [rbp+7E0h+var_20]
0x1800470aa  xor     rcx, rsp; StackCookie
0x1800470ad  call    __security_check_cookie
0x1800470b2  lea     r11, [rsp+8E0h+var_10]
0x1800470ba  mov     rbx, [r11+30h]
0x1800470be  mov     rsi, [r11+38h]
0x1800470c2  mov     rsp, r11
0x1800470c5  pop     r14
0x1800470c7  pop     rdi
0x1800470c8  pop     rbp
0x1800470c9  retn
```
