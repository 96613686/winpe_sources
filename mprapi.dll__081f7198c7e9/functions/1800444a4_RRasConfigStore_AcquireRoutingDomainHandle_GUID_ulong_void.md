# RRasConfigStore::AcquireRoutingDomainHandle(_GUID *,ulong,void * *)

- ea: `0x1800444a4`
- end: `0x180044675`
- name: `?AcquireRoutingDomainHandle@RRasConfigStore@@QEAAKPEAU_GUID@@KPEAPEAX@Z`
- size: `465`
- prototype: `__int64 __fastcall(RRasConfigStore *this, struct _GUID *, char, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180040920`

## callees

- `0x1800444a4`
- `0x18004f0ec`
- `0x180050b2c`
- `0x180050be8`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x1800445ca`
- `ntdll!RtlAcquireResourceShared` at `0x180044617`
- `ntdll!RtlAcquireResourceShared` at `0x1800445ca`
- `ntdll!RtlAcquireResourceShared` at `0x180044617`
- `ntdll!RtlReleaseResource` at `0x180044639`
- `ntdll!RtlReleaseResource` at `0x180044639`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800445ff`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800445ff`

## string_xrefs

- `0x180044540`: `RRasConfigStore::AcquireRoutingDomainHandle`
- `0x18004457e`: `RRasConfigStore::AcquireRoutingDomainHandle`

## pseudocode

```c
__int64 __fastcall RRasConfigStore::AcquireRoutingDomainHandle(
        RRasConfigStore *this,
        struct _GUID *a2,
        char a3,
        void **a4)
{
  void (*v8)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  int v9; // edi
  __int64 v10; // rsi
  unsigned int v11; // ebx
  unsigned __int16 *v13; // [rsp+28h] [rbp-D8h]
  unsigned int v14; // [rsp+30h] [rbp-D0h]
  unsigned int v15; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v17; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v18; // [rsp+58h] [rbp-A8h]
  __int128 v19; // [rsp+68h] [rbp-98h]
  __int64 v20; // [rsp+78h] [rbp-88h]
  int v21; // [rsp+80h] [rbp-80h]
  int v22; // [rsp+84h] [rbp-7Ch]
  int v23; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v24[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v15 = 0;
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v18 = 0;
  v17 = 0;
  v19 = 0;
  v20 = 0;
  v21 = -1;
  v22 = 0;
  if ( *((_QWORD *)&xmmword_180078C60 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v17,
      L"RRasConfigStore::AcquireRoutingDomainHandle",
      &v15,
      v8,
      a2,
      v13,
      v14);
  if ( a4 || a2 || (a3 & 3) != 0 )
  {
    *a4 = 0;
    v9 = 1;
    RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 112), 1u);
    std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(
      (char *)this + 16,
      &v16,
      a2);
    if ( v16 == *((_QWORD *)this + 3) )
    {
      v15 = 1168;
    }
    else
    {
      v10 = *(_QWORD *)(v16 + 32);
      if ( (a3 & 1) != 0 )
      {
        RtlAcquireResourceExclusive((PRTL_RESOURCE)(v10 + 728), 1u);
      }
      else if ( (a3 & 2) != 0 )
      {
        RtlAcquireResourceShared((PRTL_RESOURCE)(v10 + 728), 1u);
      }
      *a4 = (void *)v10;
    }
  }
  else
  {
    v15 = 87;
    if ( (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(
        &v23,
        L"%hs(Line#%d): Invalid parameter.",
        "RRasConfigStore::AcquireRoutingDomainHandle",
        854);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C50,
        &v23);
    }
    v9 = 0;
  }
  if ( v15 && v9 )
    RtlReleaseResource((PRTL_RESOURCE)((char *)this + 112));
  v11 = v15;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v17);
  return v11;
}

```

## disassembly

```asm
0x1800444a4  mov     [rsp-8+arg_10], rbx
0x1800444a9  push    rbp
0x1800444aa  push    rsi
0x1800444ab  push    rdi
0x1800444ac  push    r14
0x1800444ae  push    r15
0x1800444b0  lea     rbp, [rsp-7A0h]
0x1800444b8  sub     rsp, 8A0h
0x1800444bf  mov     rax, cs:__security_cookie
0x1800444c6  xor     rax, rsp
0x1800444c9  mov     [rbp+7C0h+var_30], rax
0x1800444d0  mov     r15, r9
0x1800444d3  mov     r14d, r8d
0x1800444d6  mov     rsi, rdx
0x1800444d9  mov     rbx, rcx
0x1800444dc  mov     [rsp+8C0h+var_880], 0
0x1800444e4  xor     eax, eax
0x1800444e6  mov     [rbp+7C0h+var_830], eax
0x1800444e9  xor     edx, edx; Val
0x1800444eb  mov     r8d, 7FCh; Size
0x1800444f1  lea     rcx, [rbp+7C0h+var_82C]; void *
0x1800444f5  call    memset_0
0x1800444fa  xorps   xmm0, xmm0
0x1800444fd  movdqu  [rsp+8C0h+var_868], xmm0
0x180044503  mov     [rsp+8C0h+var_870], 0
0x18004450c  xorps   xmm1, xmm1
0x18004450f  movdqu  [rsp+8C0h+var_858], xmm1
0x180044515  mov     [rsp+8C0h+var_848], 0
0x18004451e  mov     [rbp+7C0h+var_840], 0FFFFFFFFh
0x180044525  mov     [rbp+7C0h+var_83C], 0
0x18004452c  cmp     qword ptr cs:xmmword_180078C60+8, 0
0x180044534  jz      short loc_180044551
0x180044536  mov     [rsp+8C0h+var_8A0], rsi; struct _GUID *
0x18004453b  lea     r8, [rsp+8C0h+var_880]; unsigned int *
0x180044540  lea     rdx, aRrasconfigstor_18; "RRasConfigStore::AcquireRoutingDomainHa"...
0x180044547  lea     rcx, [rsp+8C0h+var_870]; this
0x18004454c  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180044551  test    r15, r15
0x180044554  jnz     short loc_1800445B7
0x180044556  test    rsi, rsi
0x180044559  jnz     short loc_1800445B7
0x18004455b  test    r14b, 3
0x18004455f  jnz     short loc_1800445B7
0x180044561  mov     [rsp+8C0h+var_880], 57h ; 'W'
0x180044569  cmp     qword ptr cs:xmmword_180078C50, rsi
0x180044570  jz      short loc_1800445B3
0x180044572  xor     eax, eax
0x180044574  mov     word ptr [rbp+7C0h+var_830], ax
0x180044578  mov     r9d, 356h
0x18004457e  lea     r8, aRrasconfigstor_29; "RRasConfigStore::AcquireRoutingDomainHa"...
0x180044585  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18004458c  lea     rcx, [rbp+7C0h+var_830]
0x180044590  call    FormatRRASErrorString
0x180044595  lea     r8, [rbp+7C0h+var_830]
0x180044599  mov     rdx, qword ptr cs:xmmword_180078C50
0x1800445a0  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x1800445a7  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800445ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445b3  xor     edi, edi
0x1800445b5  jmp     short loc_18004462A
0x1800445b7  mov     qword ptr [r15], 0
0x1800445be  lea     rcx, [rbx+70h]; Resource
0x1800445c2  mov     edi, 1
0x1800445c7  mov     dl, dil; Wait
0x1800445ca  call    cs:__imp_RtlAcquireResourceShared
0x1800445d0  lea     rcx, [rbx+10h]
0x1800445d4  mov     r8, rsi
0x1800445d7  lea     rdx, [rsp+8C0h+var_878]
0x1800445dc  call    ?lower_bound@?$_Hash@V?$_Umap_traits@U_GUID@@PEAVRRasRoutingDomainConfig@@V?$_Hash_compare@U_GUID@@UGuidHash@@UGuidEquality@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVRRasRoutingDomainConfig@@@std@@@2@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::tr1::_Umap_traits<_GUID,RRasRoutingDomainConfig *,std::_Hash_compare<_GUID,GuidHash,GuidEquality>,std::allocator<std::pair<_GUID const,RRasRoutingDomainConfig *>>,0>>::lower_bound(_GUID const &)
0x1800445e1  mov     rax, [rsp+8C0h+var_878]
0x1800445e6  cmp     rax, [rbx+18h]
0x1800445ea  jz      short loc_180044622
0x1800445ec  mov     rsi, [rax+20h]
0x1800445f0  test    dil, r14b
0x1800445f3  jz      short loc_180044607
0x1800445f5  lea     rcx, [rsi+2D8h]; Resource
0x1800445fc  mov     dl, dil; Wait
0x1800445ff  call    cs:__imp_RtlAcquireResourceExclusive
0x180044605  jmp     short loc_18004461D
0x180044607  test    r14b, 2
0x18004460b  jz      short loc_18004461D
0x18004460d  lea     rcx, [rsi+2D8h]; Resource
0x180044614  mov     dl, dil; Wait
0x180044617  call    cs:__imp_RtlAcquireResourceShared
0x18004461d  mov     [r15], rsi
0x180044620  jmp     short loc_18004462A
0x180044622  mov     [rsp+8C0h+var_880], 490h
0x18004462a  cmp     [rsp+8C0h+var_880], 0
0x18004462f  jz      short loc_18004463F
0x180044631  test    edi, edi
0x180044633  jz      short loc_18004463F
0x180044635  lea     rcx, [rbx+70h]; Resource
0x180044639  call    cs:__imp_RtlReleaseResource
0x18004463f  mov     ebx, [rsp+8C0h+var_880]
0x180044643  lea     rcx, [rsp+8C0h+var_870]; this
0x180044648  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18004464d  mov     eax, ebx
0x18004464f  mov     rcx, [rbp+7C0h+var_30]
0x180044656  xor     rcx, rsp; StackCookie
0x180044659  call    __security_check_cookie
0x18004465e  mov     rbx, [rsp+8C0h+arg_10]
0x180044666  add     rsp, 8A0h
0x18004466d  pop     r15
0x18004466f  pop     r14
0x180044671  pop     rdi
0x180044672  pop     rsi
0x180044673  pop     rbp
0x180044674  retn
```
