# AggregatedTokenRequest::ParseMexToRealmInfo(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,AggregatedTokenRequest::RealmInfo &)

- ea: `0x14000b0fc`
- end: `0x14000b3f0`
- name: `?ParseMexToRealmInfo@AggregatedTokenRequest@@AEAAXV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAURealmInfo@1@@Z`
- size: `756`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x14000ab04`
- `0x14000b7e0`

## callees

- `0x140005458`
- `0x140007bf8`
- `0x140008644`
- `0x14000b0fc`
- `0x14000c384`
- `0x14000caac`
- `0x14000f208`
- `0x14001920c`
- `0x140019e24`
- `0x14001bd58`
- `0x14002c3e8`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall AggregatedTokenRequest::ParseMexToRealmInfo(__int64 a1, __int64 *a2, __int64 a3)
{
  __int64 v6; // rax
  _QWORD *v7; // rdi
  volatile signed __int32 *v8; // rdx
  _QWORD *v9; // rdx
  __int64 v10; // rdi
  _QWORD *v11; // rdx
  volatile signed __int32 *v12; // rdx
  __int64 result; // rax
  ResourceId *v14; // rax
  __int64 v15; // rdx
  _QWORD v16[4]; // [rsp+30h] [rbp-88h] BYREF
  _BYTE pExceptionObject[16]; // [rsp+50h] [rbp-68h] BYREF
  __int64 v18; // [rsp+60h] [rbp-58h] BYREF
  __int64 v19; // [rsp+68h] [rbp-50h]
  __int64 v20; // [rsp+70h] [rbp-48h]
  __int64 v21; // [rsp+78h] [rbp-40h]
  _QWORD v22[7]; // [rsp+80h] [rbp-38h] BYREF
  __int64 v24; // [rsp+D8h] [rbp+20h] BYREF

  v18 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v19 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v20 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v21 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v6 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  try
  {
    v22[0] = v6 + 24;
    v22[1] = a1;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      (_QWORD *)(a3 + 8),
      a2);
    v16[1] = &v24;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v24,
      (__int64 *)(*(_QWORD *)(a1 + 8) + 40LL));
    v16[2] = &v24;
    v7 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
           v16,
           (__int64 *)(a3 + 8));
    v16[3] = v7;
    Log::InfoInternal(a1, 0x4AA90010u, 0x4AAE0005u, *v7, v24);
    v8 = (volatile signed __int32 *)(*v7 - 24LL);
    if ( _InterlockedDecrement(v8 + 4) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v8 + 8LL))(*(_QWORD *)v8);
    v9 = (_QWORD *)(v24 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v24 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 8LL))(*v9);
    v10 = *(_QWORD *)(a1 + 8);
    if ( !(unsigned __int8)Url::IsValidAndSecure(a2) )
    {
      Exception::Exception((Exception *)pExceptionObject, -894894048);
      throw (Exception *)pExceptionObject;
    }
    WSTrustMEX::SendRequest(&v24, a2, v10);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      v22,
      &v24);
    WSTrustMEX::ParseResponse(&v18);
    v11 = (_QWORD *)(v24 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v24 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
    if ( *(_DWORD *)(v18 - 16) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        a3 + 24,
        (__int64)L"%s%s",
        L"v13:");
    }
    else if ( *(_DWORD *)(v19 - 16) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        a3 + 24,
        (__int64)L"%s%s",
        L"v2005:");
    }
    if ( *(_DWORD *)(v20 - 16) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        a3 + 16,
        (__int64)L"%s%s",
        L"v13:");
    }
    else if ( *(_DWORD *)(v21 - 16) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        a3 + 16,
        (__int64)L"%s%s",
        L"v2005:");
    }
  }
  catch ( ... )
  {
    if ( !(unsigned __int8)ATL::CSimpleStringT<unsigned short,0>::IsEmpty(v22) )
      std::unique_ptr<WebRequest>::operator->((__int64)v22);
    v14 = ResourceId::ResourceId((ResourceId *)&v24, 0x4AAE001Au);
    Log::Error<unsigned short const *>(a1, v15, *(unsigned int *)v14);
    throw;
  }
  WSTrustMEX::~WSTrustMEX((WSTrustMEX *)&v18);
  v12 = (volatile signed __int32 *)(*a2 - 24);
  result = (unsigned int)_InterlockedDecrement(v12 + 4);
  if ( (int)result <= 0 )
    return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v12 + 8LL))(*(_QWORD *)v12);
  return result;
}

```

## disassembly

```asm
0x14000b0fc  mov     [rsp+arg_8], rdx
0x14000b101  mov     [rsp+arg_0], rcx
0x14000b106  push    rbx
0x14000b107  push    rsi
0x14000b108  push    rdi
0x14000b109  push    r12
0x14000b10b  push    r14
0x14000b10d  sub     rsp, 90h
0x14000b114  mov     rbx, r8
0x14000b117  mov     rsi, rdx
0x14000b11a  mov     r14, rcx
0x14000b11d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000b124  lea     rdi, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000b12b  mov     rcx, rdi
0x14000b12e  mov     rax, [rax+18h]
0x14000b132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b137  add     rax, 18h
0x14000b13b  mov     [rsp+0B8h+var_58], rax
0x14000b140  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000b147  mov     rcx, rdi
0x14000b14a  mov     rax, [rax+18h]
0x14000b14e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b153  add     rax, 18h
0x14000b157  mov     [rsp+0B8h+var_50], rax
0x14000b15c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000b163  mov     rcx, rdi
0x14000b166  mov     rax, [rax+18h]
0x14000b16a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b16f  add     rax, 18h
0x14000b173  mov     [rsp+0B8h+var_48], rax
0x14000b178  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000b17f  mov     rcx, rdi
0x14000b182  mov     rax, [rax+18h]
0x14000b186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b18b  add     rax, 18h
0x14000b18f  mov     [rsp+0B8h+var_40], rax
0x14000b194  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000b19b  mov     rcx, rdi
0x14000b19e  mov     rax, [rax+18h]
0x14000b1a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b1a7  add     rax, 18h
0x14000b1ab  mov     [rsp+0B8h+var_38], rax
0x14000b1b3  mov     [rsp+0B8h+var_30], r14
0x14000b1bb  mov     rdx, rsi
0x14000b1be  lea     rcx, [rbx+8]
0x14000b1c2  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000b1c7  lea     rax, [rsp+0B8h+arg_18]
0x14000b1cf  mov     [rsp+0B8h+var_80], rax
0x14000b1d4  mov     rdx, [r14+8]
0x14000b1d8  add     rdx, 28h ; '('
0x14000b1dc  lea     rcx, [rsp+0B8h+arg_18]
0x14000b1e4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000b1e9  lea     rax, [rsp+0B8h+arg_18]
0x14000b1f1  mov     [rsp+0B8h+var_78], rax
0x14000b1f6  lea     rdx, [rbx+8]
0x14000b1fa  lea     rcx, [rsp+0B8h+var_88]
0x14000b1ff  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000b204  mov     rdi, rax
0x14000b207  mov     [rsp+0B8h+var_70], rax
0x14000b20c  mov     rcx, [rsp+0B8h+arg_18]
0x14000b214  mov     [rsp+0B8h+var_98], rcx
0x14000b219  mov     r9, [rax]
0x14000b21c  mov     edx, 4AA90010h
0x14000b221  mov     r8d, 4AAE0005h
0x14000b227  mov     rcx, r14
0x14000b22a  call    ?InfoInternal@Log@@CAXPEBVILogContext@@KVResourceId@@ZZ; Log::InfoInternal(ILogContext const *,ulong,ResourceId,...)
0x14000b22f  nop
0x14000b230  mov     rdx, [rdi]
0x14000b233  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000b237  or      r12d, 0FFFFFFFFh
0x14000b23b  mov     eax, r12d
0x14000b23e  lock xadd [rdx+10h], eax
0x14000b243  add     eax, r12d
0x14000b246  test    eax, eax
0x14000b248  jg      short loc_14000B25A
0x14000b24a  mov     rcx, [rdx]
0x14000b24d  mov     rax, [rcx]
0x14000b250  mov     rax, [rax+8]
0x14000b254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b259  nop
0x14000b25a  mov     rdx, [rsp+0B8h+arg_18]
0x14000b262  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000b266  mov     eax, r12d
0x14000b269  lock xadd [rdx+10h], eax
0x14000b26e  add     eax, r12d
0x14000b271  test    eax, eax
0x14000b273  jg      short loc_14000B284
0x14000b275  mov     rcx, [rdx]
0x14000b278  mov     rax, [rcx]
0x14000b27b  mov     rax, [rax+8]
0x14000b27f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b284  mov     rdi, [r14+8]
0x14000b288  mov     rcx, rsi
0x14000b28b  call    ?IsValidAndSecure@Url@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Url::IsValidAndSecure(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000b290  test    al, al
0x14000b292  jz      loc_14000B3CE
0x14000b298  mov     r8, rdi
0x14000b29b  mov     rdx, rsi
0x14000b29e  lea     rcx, [rsp+0B8h+arg_18]
0x14000b2a6  call    ?SendRequest@WSTrustMEX@@CA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@AEBVAuthenticationContext@@@Z; WSTrustMEX::SendRequest(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,AuthenticationContext const &)
0x14000b2ab  nop
0x14000b2ac  lea     rdx, [rsp+0B8h+arg_18]
0x14000b2b4  lea     rcx, [rsp+0B8h+var_38]
0x14000b2bc  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000b2c1  lea     rdx, [rsp+0B8h+arg_18]
0x14000b2c9  lea     rcx, [rsp+0B8h+var_58]
0x14000b2ce  call    ?ParseResponse@WSTrustMEX@@AEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WSTrustMEX::ParseResponse(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000b2d3  nop
0x14000b2d4  mov     rdx, [rsp+0B8h+arg_18]
0x14000b2dc  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000b2e0  mov     eax, r12d
0x14000b2e3  lock xadd [rdx+10h], eax
0x14000b2e8  add     eax, r12d
0x14000b2eb  test    eax, eax
0x14000b2ed  jg      short loc_14000B2FE
0x14000b2ef  mov     rcx, [rdx]
0x14000b2f2  mov     rax, [rcx]
0x14000b2f5  mov     rax, [rax+8]
0x14000b2f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b2fe  mov     r9, [rsp+0B8h+var_58]
0x14000b303  cmp     dword ptr [r9-10h], 0
0x14000b308  jz      short loc_14000B323
0x14000b30a  lea     rcx, [rbx+18h]
0x14000b30e  lea     r8, aV13; "v13:"
0x14000b315  lea     rdx, aSS_0; "%s%s"
0x14000b31c  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x14000b321  jmp     short loc_14000B346
0x14000b323  mov     r9, [rsp+0B8h+var_50]
0x14000b328  cmp     dword ptr [r9-10h], 0
0x14000b32d  jz      short loc_14000B346
0x14000b32f  lea     rcx, [rbx+18h]
0x14000b333  lea     r8, aV2005; "v2005:"
0x14000b33a  lea     rdx, aSS_0; "%s%s"
0x14000b341  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x14000b346  mov     r9, [rsp+0B8h+var_48]
0x14000b34b  cmp     dword ptr [r9-10h], 0
0x14000b350  jz      short loc_14000B36B
0x14000b352  lea     rcx, [rbx+10h]
0x14000b356  lea     r8, aV13; "v13:"
0x14000b35d  lea     rdx, aSS_0; "%s%s"
0x14000b364  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x14000b369  jmp     short loc_14000B38F
0x14000b36b  mov     r9, [rsp+0B8h+var_40]
0x14000b370  cmp     dword ptr [r9-10h], 0
0x14000b375  jz      short loc_14000B38F
0x14000b377  lea     rcx, [rbx+10h]
0x14000b37b  lea     r8, aV2005; "v2005:"
0x14000b382  lea     rdx, aSS_0; "%s%s"
0x14000b389  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x14000b38e  nop
0x14000b38f  lea     rcx, [rsp+0B8h+var_58]; this
0x14000b394  call    ??1WSTrustMEX@@QEAA@XZ; WSTrustMEX::~WSTrustMEX(void)
0x14000b399  nop
0x14000b39a  mov     rdx, [rsi]
0x14000b39d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000b3a1  mov     eax, r12d
0x14000b3a4  lock xadd [rdx+10h], eax
0x14000b3a9  add     eax, r12d
0x14000b3ac  test    eax, eax
0x14000b3ae  jg      short loc_14000B3BF
0x14000b3b0  mov     rcx, [rdx]
0x14000b3b3  mov     rax, [rcx]
0x14000b3b6  mov     rax, [rax+8]
0x14000b3ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b3bf  add     rsp, 90h
0x14000b3c6  pop     r14
0x14000b3c8  pop     r12
0x14000b3ca  pop     rdi
0x14000b3cb  pop     rsi
0x14000b3cc  pop     rbx
0x14000b3cd  retn
0x14000b3ce  mov     edx, 0CAA90020h; unsigned int
0x14000b3d3  lea     rcx, [rsp+0B8h+pExceptionObject]; this
0x14000b3d8  call    ??0Exception@@QEAA@K@Z; Exception::Exception(ulong)
0x14000b3dd  lea     rdx, _TI1?AVException@@; pThrowInfo
0x14000b3e4  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x14000b3e9  call    _CxxThrowException_0
```
