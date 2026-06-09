# CPkgDefCache::CPkgDefCache(ulong,ushort const *,ulong,CTokenMapCache &,IRegistryFilter *,void *,HKEY__ *)

- ea: `0x14002a1b0`
- end: `0x14002a5aa`
- name: `??0CPkgDefCache@@IEAA@KPEBGKAEAVCTokenMapCache@@PEAUIRegistryFilter@@PEAXPEAUHKEY__@@@Z`
- size: `1018`
- prototype: `CPkgDefCache *__fastcall(CPkgDefCache *__hidden this, unsigned int, const unsigned __int16 *, unsigned int, struct CTokenMapCache *, struct IRegistryFilter *, void *, HKEY)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x14001d17c`
- `0x14002a020`

## callees

- `0x140002c10`
- `0x140003160`
- `0x140004950`
- `0x1400095f4`
- `0x140022db0`
- `0x14002a1b0`
- `0x14002a5b0`
- `0x140033ab0`

## import_xrefs

- `SHLWAPI!PathIsDirectoryW` at `0x14002a467`
- `SHLWAPI!PathIsDirectoryW` at `0x14002a499`
- `SHLWAPI!PathIsDirectoryW` at `0x14002a467`
- `SHLWAPI!PathIsDirectoryW` at `0x14002a499`

## string_xrefs

- `0x14002a458`: `PkgDefCache flags`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
CPkgDefCache *__fastcall CPkgDefCache::CPkgDefCache(
        CPkgDefCache *this,
        int a2,
        const unsigned __int16 *a3,
        int a4,
        struct CTokenMapCache *a5,
        struct IRegistryFilter *a6,
        void *a7,
        HKEY a8)
{
  LPCWSTR *v10; // rdi
  struct ATL::IAtlStringMgr *Instance; // rax
  struct ATL::IAtlStringMgr *v12; // rax
  struct ATL::IAtlStringMgr *v13; // rax
  struct ATL::IAtlStringMgr *v14; // rax
  struct ATL::IAtlStringMgr *v15; // rax
  struct ATL::IAtlStringMgr *v16; // rax
  struct ATL::IAtlStringMgr *v17; // rax
  struct ATL::IAtlStringMgr *v18; // rax
  struct ATL::IAtlStringMgr *v19; // rax
  struct ATL::IAtlStringMgr *v20; // rax
  struct ATL::IAtlStringMgr *v21; // rax
  struct ATL::IAtlStringMgr *v22; // rax
  struct ATL::IAtlStringMgr *v23; // rax
  struct ATL::IAtlStringMgr *v24; // rax
  struct ATL::IAtlStringMgr *v25; // rax
  struct ATL::IAtlStringMgr *v26; // rax

  *(_QWORD *)this = &CPkgDefCache::`vftable';
  *((_DWORD *)this + 2) = a2;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 10) = 0;
  *((_DWORD *)this + 11) = a4;
  *((_DWORD *)this + 12) = 0;
  v10 = (LPCWSTR *)((char *)this + 64);
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  *v10 = (LPCWSTR)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (char *)this + 72,
    a3);
  v12 = ATL::CAtlStringMgr::GetInstance();
  if ( !v12 )
    ATL::AtlThrowImpl(-2147467259);
  *((_QWORD *)this + 10) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v12 + 24LL))(v12) + 24;
  v13 = ATL::CAtlStringMgr::GetInstance();
  if ( !v13 )
    ATL::AtlThrowImpl(-2147467259);
  *((_QWORD *)this + 11) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v13 + 24LL))(v13) + 24;
  v14 = ATL::CAtlStringMgr::GetInstance();
  if ( !v14 )
    ATL::AtlThrowImpl(-2147467259);
  *((_QWORD *)this + 12) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v14 + 24LL))(v14) + 24;
  v15 = ATL::CAtlStringMgr::GetInstance();
  if ( !v15 )
    ATL::AtlThrowImpl(-2147467259);
  *((_QWORD *)this + 13) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v15 + 24LL))(v15) + 24;
  v16 = ATL::CAtlStringMgr::GetInstance();
  if ( !v16 )
    ATL::AtlThrowImpl(-2147467259);
  *((_QWORD *)this + 14) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v16 + 24LL))(v16) + 24;
  v17 = ATL::CAtlStringMgr::GetInstance();
  if ( !v17 )
    ATL::AtlThrowImpl(-2147467259);
  *((_QWORD *)this + 15) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v17 + 24LL))(v17) + 24;
  v18 = ATL::CAtlStringMgr::GetInstance();
  if ( !v18 )
    ATL::AtlThrowImpl(-2147467259);
  *((_QWORD *)this + 16) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v18 + 24LL))(v18) + 24;
  v19 = ATL::CAtlStringMgr::GetInstance();
  if ( !v19 )
    ATL::AtlThrowImpl(-2147467259);
  *((_QWORD *)this + 17) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v19 + 24LL))(v19) + 24;
  v20 = ATL::CAtlStringMgr::GetInstance();
  if ( !v20 )
    ATL::AtlThrowImpl(-2147467259);
  *((_QWORD *)this + 18) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v20 + 24LL))(v20) + 24;
  v21 = ATL::CAtlStringMgr::GetInstance();
  if ( !v21 )
    ATL::AtlThrowImpl(-2147467259);
  *((_QWORD *)this + 19) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v21 + 24LL))(v21) + 24;
  v22 = ATL::CAtlStringMgr::GetInstance();
  if ( !v22 )
    ATL::AtlThrowImpl(-2147467259);
  *((_QWORD *)this + 20) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v22 + 24LL))(v22) + 24;
  *((_QWORD *)this + 21) = a5;
  v23 = ATL::CAtlStringMgr::GetInstance();
  if ( !v23 )
    ATL::AtlThrowImpl(-2147467259);
  *((_QWORD *)this + 22) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v23 + 24LL))(v23) + 24;
  v24 = ATL::CAtlStringMgr::GetInstance();
  if ( !v24 )
    ATL::AtlThrowImpl(-2147467259);
  *((_QWORD *)this + 23) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v24 + 24LL))(v24) + 24;
  v25 = ATL::CAtlStringMgr::GetInstance();
  if ( !v25 )
    ATL::AtlThrowImpl(-2147467259);
  *((_QWORD *)this + 24) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v25 + 24LL))(v25) + 24;
  v26 = ATL::CAtlStringMgr::GetInstance();
  if ( !v26 )
    ATL::AtlThrowImpl(-2147467259);
  *((_QWORD *)this + 25) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v26 + 24LL))(v26) + 24;
  *((_QWORD *)this + 26) = a6;
  *((_BYTE *)this + 217) = 0;
  *((_QWORD *)this + 28) = a7;
  *((_QWORD *)this + 29) = a8;
  CLogger::LogInfo(L"PkgDefCache flags", *((_DWORD *)this + 2), 0);
  if ( !PathIsDirectoryW(*((LPCWSTR *)this + 9)) )
  {
    ATL::CSimpleStringT<unsigned short,0>::operator=((char *)this + 96, (char *)this + 72);
    ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::RenameExtension(
      (char *)this + 96,
      L".User.PkgDef");
  }
  ATL::CSimpleStringT<unsigned short,0>::operator=(v10, (char *)this + 72);
  if ( !PathIsDirectoryW(*v10) )
    ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::RemoveFileSpec(v10);
  *((_DWORD *)this + 13) = 0;
  *((_DWORD *)this + 14) = 0;
  return this;
}

```

## disassembly

```asm
0x14002a1b0  mov     rax, rsp
0x14002a1b3  mov     [rax+10h], rbx
0x14002a1b7  mov     [rax+18h], rsi
0x14002a1bb  mov     [rax+20h], rdi
0x14002a1bf  mov     [rax+8], rcx
0x14002a1c3  push    r14
0x14002a1c5  sub     rsp, 30h
0x14002a1c9  mov     rsi, r8
0x14002a1cc  mov     rbx, rcx
0x14002a1cf  lea     rax, ??_7CPkgDefCache@@6B@; const CPkgDefCache::`vftable'
0x14002a1d6  mov     [rcx], rax
0x14002a1d9  mov     [rcx+8], edx
0x14002a1dc  and     qword ptr [rcx+10h], 0
0x14002a1e1  and     dword ptr [rcx+18h], 0
0x14002a1e5  and     qword ptr [rcx+20h], 0
0x14002a1ea  and     dword ptr [rcx+28h], 0
0x14002a1ee  mov     [rcx+2Ch], r9d
0x14002a1f2  and     dword ptr [rcx+30h], 0
0x14002a1f6  lea     rdi, [rcx+40h]
0x14002a1fa  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002a1ff  mov     rcx, rax
0x14002a202  test    rax, rax
0x14002a205  jz      loc_14002A4DA
0x14002a20b  mov     rax, [rax]
0x14002a20e  call    qword ptr [rax+18h]
0x14002a211  add     rax, 18h
0x14002a215  mov     [rdi], rax
0x14002a218  lea     r14, [rbx+48h]
0x14002a21c  mov     [rsp+38h+var_18], r14
0x14002a221  mov     rdx, rsi
0x14002a224  mov     rcx, r14
0x14002a227  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14002a22c  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002a231  mov     rcx, rax
0x14002a234  test    rax, rax
0x14002a237  jz      loc_14002A4E9
0x14002a23d  mov     rax, [rax]
0x14002a240  call    qword ptr [rax+18h]
0x14002a243  add     rax, 18h
0x14002a247  mov     [rbx+50h], rax
0x14002a24b  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002a250  mov     rcx, rax
0x14002a253  test    rax, rax
0x14002a256  jz      loc_14002A4F7
0x14002a25c  mov     rax, [rax]
0x14002a25f  call    qword ptr [rax+18h]
0x14002a262  add     rax, 18h
0x14002a266  mov     [rbx+58h], rax
0x14002a26a  lea     rsi, [rbx+60h]
0x14002a26e  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002a273  mov     rcx, rax
0x14002a276  test    rax, rax
0x14002a279  jz      loc_14002A505
0x14002a27f  mov     rax, [rax]
0x14002a282  call    qword ptr [rax+18h]
0x14002a285  add     rax, 18h
0x14002a289  mov     [rsi], rax
0x14002a28c  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002a291  mov     rcx, rax
0x14002a294  test    rax, rax
0x14002a297  jz      loc_14002A513
0x14002a29d  mov     rax, [rax]
0x14002a2a0  call    qword ptr [rax+18h]
0x14002a2a3  add     rax, 18h
0x14002a2a7  mov     [rbx+68h], rax
0x14002a2ab  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002a2b0  mov     rcx, rax
0x14002a2b3  test    rax, rax
0x14002a2b6  jz      loc_14002A521
0x14002a2bc  mov     rax, [rax]
0x14002a2bf  call    qword ptr [rax+18h]
0x14002a2c2  add     rax, 18h
0x14002a2c6  mov     [rbx+70h], rax
0x14002a2ca  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002a2cf  mov     rcx, rax
0x14002a2d2  test    rax, rax
0x14002a2d5  jz      loc_14002A52F
0x14002a2db  mov     rax, [rax]
0x14002a2de  call    qword ptr [rax+18h]
0x14002a2e1  add     rax, 18h
0x14002a2e5  mov     [rbx+78h], rax
0x14002a2e9  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002a2ee  mov     rcx, rax
0x14002a2f1  test    rax, rax
0x14002a2f4  jz      loc_14002A53D
0x14002a2fa  mov     rax, [rax]
0x14002a2fd  call    qword ptr [rax+18h]
0x14002a300  add     rax, 18h
0x14002a304  mov     [rbx+80h], rax
0x14002a30b  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002a310  mov     rcx, rax
0x14002a313  test    rax, rax
0x14002a316  jz      loc_14002A54B
0x14002a31c  mov     rax, [rax]
0x14002a31f  call    qword ptr [rax+18h]
0x14002a322  add     rax, 18h
0x14002a326  mov     [rbx+88h], rax
0x14002a32d  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002a332  mov     rcx, rax
0x14002a335  test    rax, rax
0x14002a338  jz      loc_14002A559
0x14002a33e  mov     rax, [rax]
0x14002a341  call    qword ptr [rax+18h]
0x14002a344  add     rax, 18h
0x14002a348  mov     [rbx+90h], rax
0x14002a34f  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002a354  mov     rcx, rax
0x14002a357  test    rax, rax
0x14002a35a  jz      loc_14002A567
0x14002a360  mov     rax, [rax]
0x14002a363  call    qword ptr [rax+18h]
0x14002a366  add     rax, 18h
0x14002a36a  mov     [rbx+98h], rax
0x14002a371  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002a376  mov     rcx, rax
0x14002a379  test    rax, rax
0x14002a37c  jz      loc_14002A575
0x14002a382  mov     rax, [rax]
0x14002a385  call    qword ptr [rax+18h]
0x14002a388  add     rax, 18h
0x14002a38c  mov     [rbx+0A0h], rax
0x14002a393  mov     rax, [rsp+38h+arg_20]
0x14002a398  mov     [rbx+0A8h], rax
0x14002a39f  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002a3a4  mov     rcx, rax
0x14002a3a7  test    rax, rax
0x14002a3aa  jz      loc_14002A583
0x14002a3b0  mov     rax, [rax]
0x14002a3b3  call    qword ptr [rax+18h]
0x14002a3b6  add     rax, 18h
0x14002a3ba  mov     [rbx+0B0h], rax
0x14002a3c1  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002a3c6  mov     rcx, rax
0x14002a3c9  test    rax, rax
0x14002a3cc  jz      loc_14002A591
0x14002a3d2  mov     rax, [rax]
0x14002a3d5  call    qword ptr [rax+18h]
0x14002a3d8  add     rax, 18h
0x14002a3dc  mov     [rbx+0B8h], rax
0x14002a3e3  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002a3e8  mov     rcx, rax
0x14002a3eb  test    rax, rax
0x14002a3ee  jz      loc_14002A59F
0x14002a3f4  mov     rax, [rax]
0x14002a3f7  call    qword ptr [rax+18h]
0x14002a3fa  add     rax, 18h
0x14002a3fe  mov     [rbx+0C0h], rax
0x14002a405  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002a40a  mov     rcx, rax
0x14002a40d  test    rax, rax
0x14002a410  jz      loc_14002A4CC
0x14002a416  mov     rax, [rax]
0x14002a419  call    qword ptr [rax+18h]
0x14002a41c  add     rax, 18h
0x14002a420  mov     [rbx+0C8h], rax
0x14002a427  mov     rax, [rsp+38h+arg_28]
0x14002a42c  mov     [rbx+0D0h], rax
0x14002a433  mov     byte ptr [rbx+0D9h], 0
0x14002a43a  mov     rax, [rsp+38h+arg_30]
0x14002a43f  mov     [rbx+0E0h], rax
0x14002a446  mov     rax, [rsp+38h+arg_38]
0x14002a44b  mov     [rbx+0E8h], rax
0x14002a452  xor     r8d, r8d; unsigned __int16 *
0x14002a455  mov     edx, [rbx+8]; int
0x14002a458  lea     rcx, aPkgdefcacheFla; "PkgDefCache flags"
0x14002a45f  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x14002a464  mov     rcx, [r14]; pszPath
0x14002a467  call    cs:__imp_PathIsDirectoryW
0x14002a46d  test    eax, eax
0x14002a46f  jnz     short loc_14002A48B
0x14002a471  mov     rdx, r14
0x14002a474  mov     rcx, rsi
0x14002a477  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14002a47c  lea     rdx, aUserPkgdef; ".User.PkgDef"
0x14002a483  mov     rcx, rsi
0x14002a486  call    ?RenameExtension@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::RenameExtension(ushort const *)
0x14002a48b  mov     rdx, r14
0x14002a48e  mov     rcx, rdi
0x14002a491  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14002a496  mov     rcx, [rdi]; pszPath
0x14002a499  call    cs:__imp_PathIsDirectoryW
0x14002a49f  test    eax, eax
0x14002a4a1  jnz     short loc_14002A4AB
0x14002a4a3  mov     rcx, rdi
0x14002a4a6  call    ?RemoveFileSpec@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHXZ; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::RemoveFileSpec(void)
0x14002a4ab  and     dword ptr [rbx+34h], 0
0x14002a4af  and     dword ptr [rbx+38h], 0
0x14002a4b3  mov     rax, rbx
0x14002a4b6  mov     rbx, [rsp+38h+arg_8]
0x14002a4bb  mov     rsi, [rsp+38h+arg_10]
0x14002a4c0  mov     rdi, [rsp+38h+arg_18]
0x14002a4c5  add     rsp, 30h
0x14002a4c9  pop     r14
0x14002a4cb  retn
0x14002a4cc  mov     ecx, 80004005h; int
0x14002a4d1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002a4d7  jmp     short $+2
0x14002a4d9  nop
0x14002a4da  mov     ecx, 80004005h; int
0x14002a4df  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002a4e5  jmp     short loc_14002A4E8
0x14002a4e8  nop
0x14002a4e9  mov     ecx, 80004005h; int
0x14002a4ee  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002a4f4  jmp     short $+2
0x14002a4f6  nop
0x14002a4f7  mov     ecx, 80004005h; int
0x14002a4fc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002a502  jmp     short $+2
0x14002a504  nop
0x14002a505  mov     ecx, 80004005h; int
0x14002a50a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002a510  jmp     short $+2
0x14002a512  nop
0x14002a513  mov     ecx, 80004005h; int
0x14002a518  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002a51e  jmp     short $+2
0x14002a520  nop
0x14002a521  mov     ecx, 80004005h; int
0x14002a526  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002a52c  jmp     short $+2
0x14002a52e  nop
0x14002a52f  mov     ecx, 80004005h; int
0x14002a534  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002a53a  jmp     short $+2
0x14002a53c  nop
0x14002a53d  mov     ecx, 80004005h; int
0x14002a542  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002a548  jmp     short $+2
0x14002a54a  nop
0x14002a54b  mov     ecx, 80004005h; int
0x14002a550  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002a556  jmp     short $+2
0x14002a558  nop
0x14002a559  mov     ecx, 80004005h; int
0x14002a55e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002a564  jmp     short $+2
0x14002a566  nop
0x14002a567  mov     ecx, 80004005h; int
0x14002a56c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002a572  jmp     short $+2
0x14002a574  nop
0x14002a575  mov     ecx, 80004005h; int
0x14002a57a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002a580  jmp     short $+2
0x14002a582  nop
0x14002a583  mov     ecx, 80004005h; int
0x14002a588  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002a58e  jmp     short $+2
0x14002a590  nop
0x14002a591  mov     ecx, 80004005h; int
0x14002a596  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002a59c  jmp     short $+2
0x14002a59e  nop
0x14002a59f  mov     ecx, 80004005h; int
0x14002a5a4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
