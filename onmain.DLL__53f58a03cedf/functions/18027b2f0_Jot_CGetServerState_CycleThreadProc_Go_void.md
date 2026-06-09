# Jot::CGetServerState::CycleThreadProc_Go(void)

- ea: `0x18027b2f0`
- end: `0x18027baf4`
- name: `?CycleThreadProc_Go@CGetServerState@Jot@@MEAAXXZ`
- size: `2052`
- prototype: `void __fastcall(Jot::CGetServerState *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180067080`
- `0x1801c3df4`
- `0x1801ee3ac`
- `0x1801efea0`
- `0x18027b2f0`
- `0x180284f0c`
- `0x180284f60`
- `0x18029ced0`
- `0x1802b0fdc`
- `0x1802e2190`
- `0x1802e5170`
- `0x1802e5190`
- `0x180688538`
- `0x18072ef78`

## import_xrefs

- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18027b9f1`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18027b9f1`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18027b780`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18027ba17`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18027b780`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18027ba17`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18027b9fc`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18027b9fc`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18027b46b`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18027b46b`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x18027b452`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x18027b6ca`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x18027b6f8`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x18027b452`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x18027b6ca`
- `Mso20Win32Client!__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z` at `0x18027b6f8`
- `Mso20Win32Client!__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z` at `0x18027b731`
- `Mso20Win32Client!__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z` at `0x18027b731`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x18027b4f8`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x18027b540`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x18027b598`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x18027b5ec`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x18027b640`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x18027b4f8`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x18027b540`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x18027b598`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x18027b5ec`
- `Mso20Win32Client!__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z` at `0x18027b640`
- `Mso20Win32Client!__imp_?MsoFRegGetDw@@YAHPEBU_msoreg@@PEAK@Z` at `0x18027b750`
- `Mso20Win32Client!__imp_?MsoFRegGetDw@@YAHPEBU_msoreg@@PEAK@Z` at `0x18027b750`
- `Mso20Win32Client!__imp_?IsDomainNetwork@NetStatus@Mso@@YA_NXZ` at `0x18027b964`
- `Mso20Win32Client!__imp_?IsDomainNetwork@NetStatus@Mso@@YA_NXZ` at `0x18027b964`

## string_xrefs

- `0x18027b6b3`: `Common`

## pseudocode

```c
void __fastcall Jot::CGetServerState::CycleThreadProc_Go(Jot::CGetServerState *this)
{
  __int64 v2; // rcx
  __int64 v3; // rdx
  _QWORD *v4; // r14
  char v5; // cl
  void (__fastcall *v6)(Jot::CGetServerState *, __int128 *); // rbx
  __int64 v7; // rax
  __int128 *v8; // rdx
  char v9; // r15
  unsigned int v10; // r8d
  __int64 v11; // rdx
  void (__fastcall *v12)(Jot::CGetServerState *, __int64); // rbx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  const wchar_t *v16; // r8
  Mso::NetStatus *v17; // rcx
  char v18; // bl
  void (__fastcall *v19)(Jot::CGetServerState *, __int128 *); // rbx
  __int64 v20; // rax
  unsigned int v21; // r8d
  unsigned int v22; // r8d
  __int128 v23; // [rsp+38h] [rbp-1F0h] BYREF
  unsigned int v24; // [rsp+48h] [rbp-1E0h] BYREF
  Jot::CGetServerState *v25; // [rsp+50h] [rbp-1D8h] BYREF
  __int128 v26; // [rsp+60h] [rbp-1C8h] BYREF
  __int64 v27; // [rsp+70h] [rbp-1B8h]
  __int128 v28; // [rsp+78h] [rbp-1B0h] BYREF
  __int128 v29; // [rsp+88h] [rbp-1A0h]
  char v30; // [rsp+98h] [rbp-190h]
  __int128 v31; // [rsp+A0h] [rbp-188h] BYREF
  __int64 v32; // [rsp+B0h] [rbp-178h]
  __int128 v33; // [rsp+B8h] [rbp-170h] BYREF
  __int128 v34; // [rsp+C8h] [rbp-160h]
  char v35; // [rsp+D8h] [rbp-150h]
  __int128 v36; // [rsp+E0h] [rbp-148h] BYREF
  __int64 v37; // [rsp+F0h] [rbp-138h]
  __int128 v38; // [rsp+F8h] [rbp-130h] BYREF
  __int128 v39; // [rsp+108h] [rbp-120h]
  char v40; // [rsp+118h] [rbp-110h]
  __int128 v41; // [rsp+120h] [rbp-108h] BYREF
  __int64 v42; // [rsp+130h] [rbp-F8h]
  __int128 v43; // [rsp+138h] [rbp-F0h] BYREF
  __int128 v44; // [rsp+148h] [rbp-E0h]
  char v45; // [rsp+158h] [rbp-D0h]
  __int128 v46; // [rsp+160h] [rbp-C8h] BYREF
  __int64 v47; // [rsp+170h] [rbp-B8h]
  __int128 v48; // [rsp+178h] [rbp-B0h] BYREF
  __int128 v49; // [rsp+188h] [rbp-A0h]
  char v50; // [rsp+198h] [rbp-90h]
  _QWORD v51[9]; // [rsp+1A0h] [rbp-88h] BYREF
  _BYTE v52[32]; // [rsp+1E8h] [rbp-40h] BYREF

  v25 = this;
  v24 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  *(_QWORD *)&v49 = &v46;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  *(_QWORD *)&v44 = &v41;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  *(_QWORD *)&v39 = &v36;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  *(_QWORD *)&v34 = &v31;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  *(_QWORD *)&v29 = &v26;
  DynamicMsorid::InitForKey((DynamicMsorid *)&v41, (const struct _msoreg *)&vmsoridCUOffice, L"16.0", 4u);
  if ( !v45 || (DynamicMsorid::InitForKey((DynamicMsorid *)&v36, (const struct _msoreg *)&v43, L"Common", 6u), !v40) )
  {
    v2 = 508048475;
LABEL_3:
    MsoShipAssertTagProc(v2);
    goto LABEL_4;
  }
  DynamicMsorid::InitForKey((DynamicMsorid *)&v31, (const struct _msoreg *)&v38, L"FileIO", 6u);
  if ( !v35 )
  {
    v2 = 508048472;
    goto LABEL_3;
  }
  DynamicMsorid::InitForValue(&v26, &v33, L"SyncOnlyOnDomainNetwork", 23, 4);
  if ( !MsoFRegGetDw((const struct _msoreg *)((unsigned __int64)&v28 & -(__int64)(v30 != 0)), &v24) )
    v24 = 0;
LABEL_4:
  if ( v24
    && !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 192LL))(*((_QWORD *)this + 50))
    && !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 224LL))(*((_QWORD *)this + 50)) )
  {
    v15 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 50) + 152LL))(*((_QWORD *)this + 50), v52);
    if ( *(_QWORD *)(v15 + 24) > 7u )
      v15 = *(_QWORD *)v15;
    if ( MsoCF::Strings::IsWzPrefixOfWz_IgnoreCase((MsoCF::Strings *)L"https", (const wchar_t *)v15, v16)
      || (v18 = 1, Mso::NetStatus::IsDomainNetwork(v17)) )
    {
      v18 = 0;
    }
    std::wstring::~wstring(v52);
    if ( v18 )
    {
      *((_BYTE *)this + 408) = 0;
      Jot::ExceptionWithErrorCode::ExceptionWithErrorCode(v51, 17129795);
      v51[0] = &Jot::ErrDisconnectedFromDomain::`vftable';
      std::exception_ptr::_Copy_exception(&v23, v51, &TI3_AUErrDisconnectedFromDomain_Jot__);
      v51[0] = &Jot::ErrStorageUrl::`vftable';
      Jot::Exception::~Exception((Jot::Exception *)v51);
      __ExceptionPtrAssign((char *)this + 416, &v23);
      __ExceptionPtrDestroy(&v23);
      v19 = *(void (__fastcall **)(Jot::CGetServerState *, __int128 *))(*(_QWORD *)this + 96LL);
      v23 = 0;
      __ExceptionPtrCreate(&v23);
      v19(this, &v23);
LABEL_41:
      DynamicMsorid::~DynamicMsorid((DynamicMsorid *)&v26);
      DynamicMsorid::~DynamicMsorid((DynamicMsorid *)&v31);
      DynamicMsorid::~DynamicMsorid((DynamicMsorid *)&v36);
      DynamicMsorid::~DynamicMsorid((DynamicMsorid *)&v41);
      DynamicMsorid::~DynamicMsorid((DynamicMsorid *)&v46);
      return;
    }
  }
  v4 = (_QWORD *)((char *)this + 400);
  *(_QWORD *)&v23 = (char *)this + 400;
  LOBYTE(v3) = 1;
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 50) + 80LL))(
         *((_QWORD *)this + 50),
         v3,
         600000000);
  if ( !*((_BYTE *)this + 177) )
  {
    if ( v5 || (*((_BYTE *)this + 408) = 0, (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 208LL))(*v4)) )
    {
LABEL_24:
      v6 = *(void (__fastcall **)(Jot::CGetServerState *, __int128 *))(*(_QWORD *)this + 96LL);
      v23 = 0;
      __ExceptionPtrCreate(&v23);
      v8 = &v23;
      goto LABEL_7;
    }
    v9 = 0;
    (*(void (__fastcall **)(_QWORD, Jot::CGetServerState **))(*(_QWORD *)*v4 + 232LL))(*v4, &v25);
    if ( v25 )
    {
      v20 = (*(__int64 (__fastcall **)(Jot::CGetServerState *))(*(_QWORD *)v25 + 24LL))(v25);
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v20 + 80LL))(v20, 0, 600000000);
    }
    if ( *((_BYTE *)this + 177) )
    {
      v11 = 17129797;
    }
    else
    {
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 192LL))(*v4) )
      {
        if ( v9 )
          *((_BYTE *)this + 409) = 1;
LABEL_32:
        if ( v25 )
          (*(void (__fastcall **)(Jot::CGetServerState *))(*(_QWORD *)v25 + 16LL))(v25);
        goto LABEL_24;
      }
      if ( v9
        && (Jot::IsWin32Error((Jot::CGetServerState *)((char *)this + 416), (const struct std::exception_ptr *)3, v10)
         || Jot::IsWin32Error((Jot::CGetServerState *)((char *)this + 416), (const struct std::exception_ptr *)2, v21)
         || Jot::IsWin32Error(
              (Jot::CGetServerState *)((char *)this + 416),
              (const struct std::exception_ptr *)0x35,
              v22)) )
      {
        *((_BYTE *)this + 409) = 1;
      }
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD, __int64))(*(_QWORD *)*v4 + 80LL))(*v4, 0, 600000000) )
      {
        *((_WORD *)this + 204) = 1;
        std::exception_ptr::operator=((char *)this + 416);
      }
      if ( !*((_BYTE *)this + 177) )
        goto LABEL_32;
      v11 = 17129798;
    }
    v12 = *(void (__fastcall **)(Jot::CGetServerState *, __int64))(*(_QWORD *)this + 96LL);
    v13 = Jot::ErrAbortedCurrentOperation::ErrAbortedCurrentOperation(v51, v11);
    v14 = std::make_exception_ptr<Jot::ErrAbortedCurrentOperation>(v52, v13);
    v12(this, v14);
    if ( v25 )
      (*(void (__fastcall **)(Jot::CGetServerState *))(*(_QWORD *)v25 + 16LL))(v25);
    goto LABEL_41;
  }
  v6 = *(void (__fastcall **)(Jot::CGetServerState *, __int128 *))(*(_QWORD *)this + 96LL);
  v7 = Jot::ErrAbortedCurrentOperation::ErrAbortedCurrentOperation(v51, 17129796);
  v8 = (__int128 *)std::make_exception_ptr<Jot::ErrAbortedCurrentOperation>(v52, v7);
LABEL_7:
  v6(this, v8);
  if ( v30 )
  {
    MsoOrapiDeleteFromCache((const struct _msoreg *)&v28);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v26);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v28);
    v30 = 0;
  }
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v28);
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v26);
  if ( v35 )
  {
    MsoOrapiDeleteFromCache((const struct _msoreg *)&v33);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v31);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v33);
    v35 = 0;
  }
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v33);
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v31);
  if ( v40 )
  {
    MsoOrapiDeleteFromCache((const struct _msoreg *)&v38);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v36);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v38);
    v40 = 0;
  }
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v38);
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v36);
  if ( v45 )
  {
    MsoOrapiDeleteFromCache((const struct _msoreg *)&v43);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v41);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v43);
    v45 = 0;
  }
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v43);
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v41);
  if ( v50 )
  {
    MsoOrapiDeleteFromCache((const struct _msoreg *)&v48);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v46);
    DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v48);
    v50 = 0;
  }
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v48);
  DynamicMsorid::MsoridOwner::Free((DynamicMsorid::MsoridOwner *)&v46);
}

```

## disassembly

```asm
0x18027b2f0  mov     r11, rsp
0x18027b2f3  mov     [r11+10h], rbx
0x18027b2f7  mov     [r11+18h], rsi
0x18027b2fb  push    rdi
0x18027b2fc  push    r14
0x18027b2fe  push    r15
0x18027b300  sub     rsp, 210h
0x18027b307  mov     rax, cs:__security_cookie
0x18027b30e  xor     rax, rsp
0x18027b311  mov     [rsp+228h+var_20], rax
0x18027b319  mov     rsi, rcx
0x18027b31c  mov     [rsp+228h+var_1D8], rcx
0x18027b321  xor     edi, edi
0x18027b323  mov     [rsp+228h+var_1E0], edi
0x18027b327  xorps   xmm0, xmm0
0x18027b32a  xor     eax, eax
0x18027b32c  movups  [rsp+228h+var_C8], xmm0
0x18027b334  mov     [r11-0B8h], rax
0x18027b33b  xorps   xmm1, xmm1
0x18027b33e  movups  [rsp+228h+var_B0], xmm1
0x18027b346  movups  [rsp+228h+var_A0], xmm1
0x18027b34e  mov     [rsp+228h+var_90], dil
0x18027b356  lea     rax, [r11-0C8h]
0x18027b35d  mov     [r11-0A0h], rax
0x18027b364  xor     eax, eax
0x18027b366  movups  [rsp+228h+var_108], xmm0
0x18027b36e  mov     [r11-0F8h], rax
0x18027b375  movups  [rsp+228h+var_F0], xmm1
0x18027b37d  movups  [rsp+228h+var_E0], xmm1
0x18027b385  mov     [rsp+228h+var_D0], dil
0x18027b38d  lea     rax, [r11-108h]
0x18027b394  mov     [r11-0E0h], rax
0x18027b39b  xor     eax, eax
0x18027b39d  movups  [rsp+228h+var_148], xmm0
0x18027b3a5  mov     [r11-138h], rax
0x18027b3ac  movups  [rsp+228h+var_130], xmm1
0x18027b3b4  movups  [rsp+228h+var_120], xmm1
0x18027b3bc  mov     [rsp+228h+var_110], dil
0x18027b3c4  lea     rax, [r11-148h]
0x18027b3cb  mov     [r11-120h], rax
0x18027b3d2  xor     eax, eax
0x18027b3d4  movups  [rsp+228h+var_188], xmm0
0x18027b3dc  mov     [r11-178h], rax
0x18027b3e3  movups  [rsp+228h+var_170], xmm1
0x18027b3eb  movups  [rsp+228h+var_160], xmm1
0x18027b3f3  mov     [rsp+228h+var_150], dil
0x18027b3fb  lea     rax, [r11-188h]
0x18027b402  mov     [r11-160h], rax
0x18027b409  xor     eax, eax
0x18027b40b  movups  [rsp+228h+var_1C8], xmm0
0x18027b410  mov     [rsp+228h+var_1B8], rax
0x18027b415  movups  [rsp+228h+var_1B0], xmm1
0x18027b41a  movups  [rsp+228h+var_1A0], xmm1
0x18027b422  mov     [rsp+228h+var_190], dil
0x18027b42a  lea     rax, [rsp+228h+var_1C8]
0x18027b42f  mov     [r11-1A0h], rax
0x18027b436  lea     r14d, [rdi+4]
0x18027b43a  mov     r9d, r14d
0x18027b43d  lea     r8, a160; "16.0"
0x18027b444  lea     rdx, ?vmsoridCUOffice@@3U_msoreg@@B; _msoreg const vmsoridCUOffice
0x18027b44b  lea     rcx, [r11-108h]
0x18027b452  call    cs:__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z; DynamicMsorid::InitForKey(_msoreg const &,wchar_t const *,unsigned __int64)
0x18027b458  cmp     [rsp+228h+var_D0], dil
0x18027b460  jnz     loc_18027B6AB
0x18027b466  mov     ecx, 1E48345Bh
0x18027b46b  call    cs:__imp_MsoShipAssertTagProc
0x18027b471  cmp     [rsp+228h+var_1E0], edi
0x18027b475  jnz     loc_18027B8EA
0x18027b47b  lea     r14, [rsi+190h]
0x18027b482  mov     qword ptr [rsp+228h+var_1F0], r14
0x18027b487  mov     rcx, [r14]
0x18027b48a  mov     rax, [rcx]
0x18027b48d  mov     ebx, 23C34600h
0x18027b492  mov     r8d, ebx
0x18027b495  mov     dl, 1
0x18027b497  mov     rax, [rax+50h]
0x18027b49b  call    cs:__guard_dispatch_icall_fptr
0x18027b4a1  mov     cl, al
0x18027b4a3  mov     al, [rsi+0B1h]
0x18027b4a9  test    al, al
0x18027b4ab  jz      loc_18027B767
0x18027b4b1  mov     rax, [rsi]
0x18027b4b4  mov     rbx, [rax+60h]
0x18027b4b8  mov     edx, 1056144h
0x18027b4bd  lea     rcx, [rsp+228h+var_88]
0x18027b4c5  call    ??0ErrAbortedCurrentOperation@Jot@@QEAA@VExceptionTag@1@@Z; Jot::ErrAbortedCurrentOperation::ErrAbortedCurrentOperation(Jot::ExceptionTag)
0x18027b4ca  mov     rdx, rax
0x18027b4cd  lea     rcx, [rsp+228h+var_40]
0x18027b4d5  call    ??$make_exception_ptr@UErrAbortedCurrentOperation@Jot@@@std@@YA?AVexception_ptr@0@UErrAbortedCurrentOperation@Jot@@@Z; std::make_exception_ptr<Jot::ErrAbortedCurrentOperation>(Jot::ErrAbortedCurrentOperation)
0x18027b4da  mov     rdx, rax
0x18027b4dd  mov     rcx, rsi
0x18027b4e0  mov     rax, rbx
0x18027b4e3  call    cs:__guard_dispatch_icall_fptr
0x18027b4e9  cmp     [rsp+228h+var_190], dil
0x18027b4f1  jz      short loc_18027B51A
0x18027b4f3  lea     rcx, [rsp+228h+var_1B0]
0x18027b4f8  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x18027b4fe  lea     rcx, [rsp+228h+var_1C8]; this
0x18027b503  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18027b508  lea     rcx, [rsp+228h+var_1B0]; this
0x18027b50d  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18027b512  mov     [rsp+228h+var_190], dil
0x18027b51a  lea     rcx, [rsp+228h+var_1B0]; this
0x18027b51f  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18027b524  lea     rcx, [rsp+228h+var_1C8]; this
0x18027b529  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18027b52e  cmp     [rsp+228h+var_150], dil
0x18027b536  jz      short loc_18027B568
0x18027b538  lea     rcx, [rsp+228h+var_170]
0x18027b540  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x18027b546  lea     rcx, [rsp+228h+var_188]; this
0x18027b54e  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18027b553  lea     rcx, [rsp+228h+var_170]; this
0x18027b55b  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18027b560  mov     [rsp+228h+var_150], dil
0x18027b568  lea     rcx, [rsp+228h+var_170]; this
0x18027b570  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18027b575  lea     rcx, [rsp+228h+var_188]; this
0x18027b57d  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18027b582  cmp     [rsp+228h+var_110], dil
0x18027b58a  jz      short loc_18027B5C0
0x18027b58c  nop     dword ptr [rax+00h]
0x18027b590  lea     rcx, [rsp+228h+var_130]
0x18027b598  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x18027b59e  lea     rcx, [rsp+228h+var_148]; this
0x18027b5a6  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18027b5ab  lea     rcx, [rsp+228h+var_130]; this
0x18027b5b3  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18027b5b8  mov     [rsp+228h+var_110], dil
0x18027b5c0  lea     rcx, [rsp+228h+var_130]; this
0x18027b5c8  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18027b5cd  lea     rcx, [rsp+228h+var_148]; this
0x18027b5d5  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18027b5da  cmp     [rsp+228h+var_D0], dil
0x18027b5e2  jz      short loc_18027B614
0x18027b5e4  lea     rcx, [rsp+228h+var_F0]
0x18027b5ec  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x18027b5f2  lea     rcx, [rsp+228h+var_108]; this
0x18027b5fa  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18027b5ff  lea     rcx, [rsp+228h+var_F0]; this
0x18027b607  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18027b60c  mov     [rsp+228h+var_D0], dil
0x18027b614  lea     rcx, [rsp+228h+var_F0]; this
0x18027b61c  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18027b621  lea     rcx, [rsp+228h+var_108]; this
0x18027b629  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18027b62e  cmp     [rsp+228h+var_90], dil
0x18027b636  jz      short loc_18027B668
0x18027b638  lea     rcx, [rsp+228h+var_B0]
0x18027b640  call    cs:__imp_?MsoOrapiDeleteFromCache@@YAXPEBU_msoreg@@@Z; MsoOrapiDeleteFromCache(_msoreg const *)
0x18027b646  lea     rcx, [rsp+228h+var_C8]; this
0x18027b64e  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18027b653  lea     rcx, [rsp+228h+var_B0]; this
0x18027b65b  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18027b660  mov     [rsp+228h+var_90], dil
0x18027b668  lea     rcx, [rsp+228h+var_B0]; this
0x18027b670  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18027b675  lea     rcx, [rsp+228h+var_C8]; this
0x18027b67d  call    ?Free@MsoridOwner@DynamicMsorid@@QEAAXXZ; DynamicMsorid::MsoridOwner::Free(void)
0x18027b682  mov     rcx, [rsp+228h+var_20]
0x18027b68a  xor     rcx, rsp; StackCookie
0x18027b68d  call    __security_check_cookie
0x18027b692  lea     r11, [rsp+228h+var_18]
0x18027b69a  mov     rbx, [r11+28h]
0x18027b69e  mov     rsi, [r11+30h]
0x18027b6a2  mov     rsp, r11
0x18027b6a5  pop     r15
0x18027b6a7  pop     r14
0x18027b6a9  pop     rdi
0x18027b6aa  retn
0x18027b6ab  mov     ebx, 6
0x18027b6b0  mov     r9d, ebx
0x18027b6b3  lea     r8, aCommon; "Common"
0x18027b6ba  lea     rdx, [rsp+228h+var_F0]
0x18027b6c2  lea     rcx, [rsp+228h+var_148]
0x18027b6ca  call    cs:__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z; DynamicMsorid::InitForKey(_msoreg const &,wchar_t const *,unsigned __int64)
0x18027b6d0  cmp     [rsp+228h+var_110], dil
0x18027b6d8  jz      loc_18027B466
0x18027b6de  mov     r9d, ebx
0x18027b6e1  lea     r8, aFileio; "FileIO"
0x18027b6e8  lea     rdx, [rsp+228h+var_130]
0x18027b6f0  lea     rcx, [rsp+228h+var_188]
0x18027b6f8  call    cs:__imp_?InitForKey@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_K@Z; DynamicMsorid::InitForKey(_msoreg const &,wchar_t const *,unsigned __int64)
0x18027b6fe  cmp     [rsp+228h+var_150], dil
0x18027b706  jnz     short loc_18027B712
0x18027b708  mov     ecx, 1E483458h
0x18027b70d  jmp     loc_18027B46B
0x18027b712  mov     [rsp+228h+var_208], r14d
0x18027b717  mov     r9d, 17h
0x18027b71d  lea     r8, aSynconlyondoma; "SyncOnlyOnDomainNetwork"
0x18027b724  lea     rdx, [rsp+228h+var_170]
0x18027b72c  lea     rcx, [rsp+228h+var_1C8]
0x18027b731  call    cs:__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z; DynamicMsorid::InitForValue(_msoreg const &,wchar_t const *,unsigned __int64,RegValueType)
0x18027b737  mov     al, [rsp+228h+var_190]
0x18027b73e  neg     al
0x18027b740  sbb     rcx, rcx
0x18027b743  lea     rax, [rsp+228h+var_1B0]
0x18027b748  and     rcx, rax
0x18027b74b  lea     rdx, [rsp+228h+var_1E0]
0x18027b750  call    cs:__imp_?MsoFRegGetDw@@YAHPEBU_msoreg@@PEAK@Z; MsoFRegGetDw(_msoreg const *,ulong *)
0x18027b756  test    eax, eax
0x18027b758  jnz     loc_18027B471
0x18027b75e  mov     [rsp+228h+var_1E0], edi
0x18027b762  jmp     loc_18027B471
0x18027b767  test    cl, cl
0x18027b769  jz      short loc_18027B790
0x18027b76b  mov     rax, [rsi]
0x18027b76e  mov     rbx, [rax+60h]
0x18027b772  xorps   xmm0, xmm0
0x18027b775  movdqu  [rsp+228h+var_1F0], xmm0
0x18027b77b  lea     rcx, [rsp+228h+var_1F0]
0x18027b780  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18027b786  lea     rdx, [rsp+228h+var_1F0]
0x18027b78b  jmp     loc_18027B4DD
0x18027b790  mov     [rsi+198h], dil
0x18027b797  mov     rcx, [r14]
0x18027b79a  mov     rax, [rcx]
0x18027b79d  mov     rax, [rax+0D0h]
0x18027b7a4  call    cs:__guard_dispatch_icall_fptr
0x18027b7aa  test    al, al
0x18027b7ac  jnz     short loc_18027B76B
0x18027b7ae  mov     r15b, dil
0x18027b7b1  mov     rcx, [r14]
0x18027b7b4  mov     rax, [rcx]
0x18027b7b7  lea     rdx, [rsp+228h+var_1D8]
0x18027b7bc  mov     rax, [rax+0E8h]
0x18027b7c3  call    cs:__guard_dispatch_icall_fptr
0x18027b7c9  nop
0x18027b7ca  mov     rcx, [rsp+228h+var_1D8]
0x18027b7cf  test    rcx, rcx
0x18027b7d2  jnz     loc_18027BA4C
0x18027b7d8  mov     cl, [rsi+0B1h]
0x18027b7de  test    cl, cl
0x18027b7e0  jnz     loc_18027BA79
0x18027b7e6  mov     rcx, [r14]
0x18027b7e9  mov     rax, [rcx]
0x18027b7ec  mov     rax, [rax+0C0h]
0x18027b7f3  call    cs:__guard_dispatch_icall_fptr
0x18027b7f9  test    al, al
0x18027b7fb  jz      short loc_18027B826
0x18027b7fd  test    r15b, r15b
0x18027b800  jnz     loc_18027BA83
0x18027b806  mov     rcx, [rsp+228h+var_1D8]
0x18027b80b  test    rcx, rcx
0x18027b80e  jz      loc_18027B76B
0x18027b814  mov     rax, [rcx]
0x18027b817  mov     rax, [rax+10h]
0x18027b81b  call    cs:__guard_dispatch_icall_fptr
0x18027b821  jmp     loc_18027B76B
0x18027b826  test    r15b, r15b
0x18027b829  jnz     loc_18027BA8F
0x18027b82f  mov     rcx, [r14]
0x18027b832  mov     rax, [rcx]
0x18027b835  mov     r8, rbx
0x18027b838  xor     edx, edx
0x18027b83a  mov     rax, [rax+50h]
0x18027b83e  call    cs:__guard_dispatch_icall_fptr
0x18027b844  test    al, al
0x18027b846  jnz     loc_18027BAD9
0x18027b84c  mov     al, [rsi+0B1h]
0x18027b852  test    al, al
0x18027b854  jz      short loc_18027B806
0x18027b856  mov     edx, 1056146h
0x18027b85b  mov     rax, [rsi]
0x18027b85e  mov     rbx, [rax+60h]
0x18027b862  lea     rcx, [rsp+228h+var_88]
0x18027b86a  call    ??0ErrAbortedCurrentOperation@Jot@@QEAA@VExceptionTag@1@@Z; Jot::ErrAbortedCurrentOperation::ErrAbortedCurrentOperation(Jot::ExceptionTag)
0x18027b86f  mov     rdx, rax
0x18027b872  lea     rcx, [rsp+228h+var_40]
0x18027b87a  call    ??$make_exception_ptr@UErrAbortedCurrentOperation@Jot@@@std@@YA?AVexception_ptr@0@UErrAbortedCurrentOperation@Jot@@@Z; std::make_exception_ptr<Jot::ErrAbortedCurrentOperation>(Jot::ErrAbortedCurrentOperation)
0x18027b87f  mov     rdx, rax
0x18027b882  mov     rcx, rsi
0x18027b885  mov     rax, rbx
0x18027b888  call    cs:__guard_dispatch_icall_fptr
0x18027b88e  nop
0x18027b88f  mov     rcx, [rsp+228h+var_1D8]
0x18027b894  test    rcx, rcx
0x18027b897  jz      short loc_18027B8A7
0x18027b899  mov     rax, [rcx]
0x18027b89c  mov     rax, [rax+10h]
0x18027b8a0  call    cs:__guard_dispatch_icall_fptr
0x18027b8a6  nop
0x18027b8a7  lea     rcx, [rsp+228h+var_1C8]; this
0x18027b8ac  call    ??1DynamicMsorid@@QEAA@XZ; DynamicMsorid::~DynamicMsorid(void)
0x18027b8b1  lea     rcx, [rsp+228h+var_188]; this
0x18027b8b9  call    ??1DynamicMsorid@@QEAA@XZ; DynamicMsorid::~DynamicMsorid(void)
0x18027b8be  lea     rcx, [rsp+228h+var_148]; this
0x18027b8c6  call    ??1DynamicMsorid@@QEAA@XZ; DynamicMsorid::~DynamicMsorid(void)
0x18027b8cb  lea     rcx, [rsp+228h+var_108]; this
0x18027b8d3  call    ??1DynamicMsorid@@QEAA@XZ; DynamicMsorid::~DynamicMsorid(void)
0x18027b8d8  lea     rcx, [rsp+228h+var_C8]; this
0x18027b8e0  call    ??1DynamicMsorid@@QEAA@XZ; DynamicMsorid::~DynamicMsorid(void)
0x18027b8e5  jmp     loc_18027B682
0x18027b8ea  mov     rcx, [rsi+190h]
0x18027b8f1  mov     rax, [rcx]
0x18027b8f4  mov     rax, [rax+0C0h]
0x18027b8fb  call    cs:__guard_dispatch_icall_fptr
0x18027b901  test    al, al
0x18027b903  jnz     loc_18027B47B
0x18027b909  mov     rcx, [rsi+190h]
  ... truncated ...
```
