# Dlp::Asimov::InitializeAsimovLogger(void)

- ea: `0x180160a54`
- end: `0x180161210`
- name: `?InitializeAsimovLogger@Asimov@Dlp@@YAJXZ`
- size: `1980`
- prototype: `__int64 __fastcall(Dlp::Asimov *__hidden this)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18015fd3c`

## callees

- `0x1800809d0`
- `0x180089510`
- `0x1800b3710`
- `0x1800b8fcc`
- `0x1800cd824`
- `0x180100c98`
- `0x180101cf4`
- `0x18010cb40`
- `0x18010ce3c`
- `0x18010ce44`
- `0x18010d1e0`
- `0x18010d310`
- `0x18010d380`
- `0x1801449cc`
- `0x180144ba0`
- `0x180145184`
- `0x18014562c`
- `0x180145760`
- `0x180145874`
- `0x1801458c0`
- `0x18014949c`
- `0x1801609b8`
- `0x180160a54`
- `0x1801c39bc`
- `0x1801c39e4`

## import_xrefs

- `MpClient!MpFreeMemory` at `0x180160c08`
- `MpClient!MpFreeMemory` at `0x180160caf`
- `MpClient!MpFreeMemory` at `0x180160d9f`
- `MpClient!MpFreeMemory` at `0x180160dc6`
- `MpClient!MpFreeMemory` at `0x180161111`
- `MpClient!MpFreeMemory` at `0x180161125`
- `MpClient!MpFreeMemory` at `0x180161136`
- `MpClient!MpFreeMemory` at `0x180161145`
- `MpClient!MpFreeMemory` at `0x180161154`
- `MpClient!MpFreeMemory` at `0x18016117c`
- `MpClient!MpFreeMemory` at `0x1801611a4`
- `MpClient!MpFreeMemory` at `0x180160c08`
- `MpClient!MpFreeMemory` at `0x180160caf`
- `MpClient!MpFreeMemory` at `0x180160d9f`
- `MpClient!MpFreeMemory` at `0x180160dc6`
- `MpClient!MpFreeMemory` at `0x180161111`
- `MpClient!MpFreeMemory` at `0x180161125`
- `MpClient!MpFreeMemory` at `0x180161136`
- `MpClient!MpFreeMemory` at `0x180161145`
- `MpClient!MpFreeMemory` at `0x180161154`
- `MpClient!MpFreeMemory` at `0x18016117c`
- `MpClient!MpFreeMemory` at `0x1801611a4`
- `MpClient!MpConfigClose` at `0x180161168`
- `MpClient!MpConfigClose` at `0x180161190`
- `MpClient!MpConfigClose` at `0x180161168`
- `MpClient!MpConfigClose` at `0x180161190`
- `MpClient!MpConfigOpen` at `0x180160b97`
- `MpClient!MpConfigOpen` at `0x180160c98`
- `MpClient!MpConfigOpen` at `0x180160b97`
- `MpClient!MpConfigOpen` at `0x180160c98`

## string_xrefs

- `0x180160d7e`: `MsMpLics.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=16 #try_helpers=1
__int64 __fastcall Dlp::Asimov::InitializeAsimovLogger(Dlp::Asimov *this)
{
  int ValueString; // eax
  int ValueBool; // eax
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  int v6; // eax
  wchar_t **v7; // r9
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  int EngineFilesVersion; // eax
  const wchar_t *v11; // r8
  bool v12; // r9
  wchar_t **v13; // rdx
  int MpFileFullName; // edi
  const wchar_t *v15; // r8
  wchar_t **v16; // rbx
  int PartnerGUID; // eax
  int v18; // r13d
  const wchar_t *v19; // rdx
  __int64 *v20; // rax
  const struct std::nothrow_t *v21; // rdx
  __int64 v22; // rcx
  const wchar_t *v23; // rdx
  const wchar_t *v24; // rsi
  __int64 *v25; // rax
  const struct std::nothrow_t *v26; // rdx
  __int64 v27; // rcx
  wchar_t *v28; // rdx
  wchar_t *v29; // rdi
  __int64 *v30; // rax
  const struct std::nothrow_t *v31; // rdx
  __int64 v32; // rcx
  const wchar_t *v33; // rdx
  __int64 *v34; // rax
  const struct std::nothrow_t *v35; // rdx
  __int64 v36; // rcx
  wchar_t **v37; // rdx
  wchar_t **v38; // rbx
  __int64 *v39; // rax
  const struct std::nothrow_t *v40; // rdx
  __int64 v41; // rcx
  const wchar_t *v42; // rdx
  void **v43; // rax
  const struct std::nothrow_t *v44; // rdx
  void *v45; // rcx
  _QWORD *v46; // rax
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  int v50; // [rsp+20h] [rbp-138h]
  const wchar_t *v51; // [rsp+28h] [rbp-130h] BYREF
  wchar_t **v52; // [rsp+30h] [rbp-128h] BYREF
  void *v53; // [rsp+38h] [rbp-120h] BYREF
  void *v54; // [rsp+40h] [rbp-118h] BYREF
  wchar_t *v55; // [rsp+48h] [rbp-110h] BYREF
  wchar_t *v56; // [rsp+50h] [rbp-108h] BYREF
  __int64 v57; // [rsp+58h] [rbp-100h]
  __int64 v58; // [rsp+60h] [rbp-F8h]
  __int64 v59; // [rsp+68h] [rbp-F0h]
  __int64 v60; // [rsp+70h] [rbp-E8h]
  __int64 v61; // [rsp+78h] [rbp-E0h]
  _BYTE v62[16]; // [rsp+80h] [rbp-D8h] BYREF
  __int64 v63; // [rsp+90h] [rbp-C8h]
  __int64 v64; // [rsp+98h] [rbp-C0h]
  __int64 v65; // [rsp+A0h] [rbp-B8h]
  __int64 v66; // [rsp+A8h] [rbp-B0h]
  __int64 v67; // [rsp+B0h] [rbp-A8h]
  void *v68; // [rsp+B8h] [rbp-A0h]
  const wchar_t *v69; // [rsp+C8h] [rbp-90h] BYREF
  const wchar_t *v70; // [rsp+D0h] [rbp-88h] BYREF
  const wchar_t *v71; // [rsp+D8h] [rbp-80h] BYREF
  __int64 v72; // [rsp+E0h] [rbp-78h] BYREF
  __int64 v73; // [rsp+E8h] [rbp-70h] BYREF
  _QWORD v74[7]; // [rsp+F0h] [rbp-68h] BYREF
  bool v75; // [rsp+128h] [rbp-30h]
  bool v76; // [rsp+129h] [rbp-2Fh]
  bool v77; // [rsp+12Ah] [rbp-2Eh]
  bool v78; // [rsp+12Bh] [rbp-2Dh]
  int v79; // [rsp+12Ch] [rbp-2Ch]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_eb55907698d2371455f751e0d7f04c24_Traceguids);
  if ( dword_180313C70 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 108LL) )
  {
    Init_thread_header(&dword_180313C70);
    if ( dword_180313C70 == -1 )
    {
      CommonUtil::CMpCriticalSection::CMpCriticalSection((CommonUtil::CMpCriticalSection *)&stru_180313C78, 0xFA0u);
      atexit(Dlp::Asimov::InitializeAsimovLogger_::_2_::_dynamic_atexit_destructor_for__s_lock__);
      Init_thread_footer(&dword_180313C70);
    }
  }
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v62);
  if ( byte_180313694 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_eb55907698d2371455f751e0d7f04c24_Traceguids);
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v62);
    return 0;
  }
  v70 = 0;
  v72 = 0;
  v50 = 0;
  LODWORD(v51) = 0;
  ValueString = MpConfigOpen(L".", &v72);
  if ( ValueString < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v5 = 15;
      goto LABEL_28;
    }
  }
  else
  {
    ValueBool = MpConfigGetValueBool(v72, L"BetaPlatform", &v51);
    if ( ValueBool >= 0 )
    {
      v50 = (int)v51;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_eb55907698d2371455f751e0d7f04c24_Traceguids,
          (unsigned int)ValueBool);
      v50 = 0;
    }
    if ( v70 )
    {
      MpFreeMemory(v70);
      v70 = 0;
    }
    ValueString = MpConfigGetValueString(v72, L"ProductGUID", &v70);
    if ( ValueString < 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v5 = 14;
LABEL_28:
        WPP_SF_d(v4[2], v5, WPP_eb55907698d2371455f751e0d7f04c24_Traceguids, (unsigned int)ValueString);
      }
    }
  }
  v69 = 0;
  v73 = 0;
  v6 = MpConfigOpen(L"Features", &v73);
  if ( v6 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v9 = 17;
      goto LABEL_39;
    }
  }
  else
  {
    if ( v69 )
    {
      MpFreeMemory(v69);
      v69 = 0;
    }
    v6 = MpConfigGetValueString(v73, L"SenseOrgId", &v69);
    if ( v6 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v9 = 16;
LABEL_39:
        WPP_SF_d(v8[2], v9, WPP_eb55907698d2371455f751e0d7f04c24_Traceguids, (unsigned int)v6);
      }
    }
  }
  v51 = 0;
  v55 = 0;
  v56 = 0;
  EngineFilesVersion = MpConfigUtils::GetEngineFilesVersion((MpConfigUtils *)&v51, &v55, &v56, v7);
  if ( EngineFilesVersion < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      WPP_eb55907698d2371455f751e0d7f04c24_Traceguids,
      (unsigned int)EngineFilesVersion);
  }
  v71 = 0;
  v52 = 0;
  MpFileFullName = MpConfigUtils::GetMpFileFullName((MpConfigUtils *)&v52, (wchar_t **)L"MsMpLics.dll", v11, v12);
  if ( MpFileFullName >= 0 )
  {
    v16 = v52;
    MpFileFullName = MpConfigUtils::GetFileVersion((MpConfigUtils *)&v71, v52, v15);
    if ( v16 )
      MpFreeMemory(v16);
    if ( MpFileFullName >= 0 )
      goto LABEL_53;
  }
  else if ( v52 )
  {
    MpFreeMemory(v52);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      WPP_eb55907698d2371455f751e0d7f04c24_Traceguids,
      (unsigned int)MpFileFullName);
LABEL_53:
  v52 = 0;
  PartnerGUID = MpConfigUtils::GetPartnerGUID((MpConfigUtils *)&v52, v13);
  v18 = PartnerGUID;
  if ( PartnerGUID < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        WPP_eb55907698d2371455f751e0d7f04c24_Traceguids,
        (unsigned int)PartnerGUID);
    v18 = 0;
  }
  v19 = &qword_18025C818;
  if ( v70 )
    v19 = v70;
  v20 = (__int64 *)CommonUtil::TrDuplicateStringW(&v53, v19);
  v57 = *v20;
  v22 = v57;
  *v20 = 0;
  v63 = v22;
  if ( v53 )
    operator delete(v53, v21);
  v23 = &qword_18025C818;
  v24 = v51;
  if ( v51 )
    v23 = v51;
  v25 = (__int64 *)CommonUtil::TrDuplicateStringW(&v54, v23);
  v58 = *v25;
  v27 = v58;
  *v25 = 0;
  v64 = v27;
  if ( v54 )
    operator delete(v54, v26);
  v28 = (wchar_t *)&qword_18025C818;
  v29 = v55;
  if ( v55 )
    v28 = v55;
  v30 = (__int64 *)CommonUtil::TrDuplicateStringW(&v53, v28);
  v59 = *v30;
  v32 = v59;
  *v30 = 0;
  v65 = v32;
  if ( v53 )
    operator delete(v53, v31);
  v33 = &qword_18025C818;
  if ( v71 )
    v33 = v71;
  v34 = (__int64 *)CommonUtil::TrDuplicateStringW(&v54, v33);
  v60 = *v34;
  v36 = v60;
  *v34 = 0;
  v66 = v36;
  if ( v54 )
    operator delete(v54, v35);
  v37 = (wchar_t **)&qword_18025C818;
  v38 = v52;
  if ( v52 )
    v37 = v52;
  v39 = (__int64 *)CommonUtil::TrDuplicateStringW(&v53, v37);
  v61 = *v39;
  v41 = v61;
  *v39 = 0;
  v67 = v41;
  if ( v53 )
    operator delete(v53, v40);
  v42 = &qword_18025C818;
  if ( v69 )
    v42 = v69;
  v43 = (void **)CommonUtil::TrDuplicateStringW(&v54, v42);
  v53 = *v43;
  v45 = v53;
  *v43 = 0;
  v68 = v45;
  if ( v54 )
    operator delete(v54, v44);
  v46 = operator new(8u);
  *v46 = &CMpAsimovRegisterAggregateEx::`vftable';
  v54 = 0;
  v74[0] = v46;
  CommonUtil::CAutoUniquePtr<RealtimeProtection::CDlpUserCloudQueryManager,void>::~CAutoUniquePtr<RealtimeProtection::CDlpUserCloudQueryManager,void>(&v54);
  v74[1] = v57;
  v74[2] = v58;
  v74[3] = v59;
  v74[4] = v60;
  v74[5] = v61;
  v74[6] = v53;
  v75 = v50 != 0;
  v76 = (unsigned int)IsManagedDefender() != 0;
  v77 = (unsigned int)IsPassiveMode() != 0;
  v78 = (unsigned int)IsSideBySidePassiveMode() != 0;
  v79 = 0;
  InitializeMpAsimov(v74);
  byte_180313694 = 1;
  AsimovDefaultData::~AsimovDefaultData((AsimovDefaultData *)v74);
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_eb55907698d2371455f751e0d7f04c24_Traceguids,
        (unsigned int)v18);
    v18 = 0;
  }
  if ( v38 )
    MpFreeMemory(v38);
  if ( v71 )
    MpFreeMemory(v71);
  if ( v56 )
    MpFreeMemory(v56);
  if ( v29 )
    MpFreeMemory(v29);
  if ( v24 )
    MpFreeMemory(v24);
  if ( v73 )
    MpConfigClose(v73, v47, v48, v49);
  if ( v69 )
    MpFreeMemory(v69);
  if ( v72 )
    MpConfigClose(v72, v47, v48, v49);
  if ( v70 )
    MpFreeMemory(v70);
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v62);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_eb55907698d2371455f751e0d7f04c24_Traceguids);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180160a54  mov     [rsp+arg_0], rbx
0x180160a59  mov     [rsp+arg_8], rsi
0x180160a5e  mov     [rsp+arg_10], rdi
0x180160a63  push    r12
0x180160a65  push    r13
0x180160a67  push    r14
0x180160a69  sub     rsp, 140h
0x180160a70  mov     rax, cs:__security_cookie
0x180160a77  xor     rax, rsp
0x180160a7a  mov     [rsp+158h+var_28], rax
0x180160a82  xor     r14d, r14d
0x180160a85  lea     r12, WPP_GLOBAL_Control
0x180160a8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180160a93  cmp     rcx, r12
0x180160a96  jz      short loc_180160AB2
0x180160a98  test    byte ptr [rcx+1Ch], 8
0x180160a9c  jz      short loc_180160AB2
0x180160a9e  lea     edx, [r14+0Ah]
0x180160aa2  lea     r8, WPP_eb55907698d2371455f751e0d7f04c24_Traceguids
0x180160aa9  mov     rcx, [rcx+10h]
0x180160aad  call    WPP_SF_
0x180160ab2  mov     ecx, cs:_tls_index
0x180160ab8  mov     rax, gs:58h
0x180160ac1  mov     edx, 6Ch ; 'l'
0x180160ac6  mov     rax, [rax+rcx*8]
0x180160aca  mov     eax, [rdx+rax]
0x180160acd  cmp     cs:dword_180313C70, eax
0x180160ad3  jle     short loc_180160B13
0x180160ad5  lea     rcx, dword_180313C70
0x180160adc  call    _Init_thread_header
0x180160ae1  cmp     cs:dword_180313C70, 0FFFFFFFFh
0x180160ae8  jnz     short loc_180160B13
0x180160aea  mov     edx, 0FA0h; unsigned int
0x180160aef  lea     rcx, stru_180313C78; this
0x180160af6  call    ??0CMpCriticalSection@CommonUtil@@QEAA@K@Z; CommonUtil::CMpCriticalSection::CMpCriticalSection(ulong)
0x180160afb  lea     rcx, _Dlp__Asimov__InitializeAsimovLogger____2____dynamic_atexit_destructor_for__s_lock__; void (__cdecl *)()
0x180160b02  call    atexit
0x180160b07  lea     rcx, dword_180313C70
0x180160b0e  call    _Init_thread_footer
0x180160b13  lea     rdx, stru_180313C78
0x180160b1a  lea     rcx, [rsp+158h+var_D8]
0x180160b22  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x180160b27  nop
0x180160b28  cmp     cs:byte_180313694, r14b
0x180160b2f  jz      short loc_180160B6D
0x180160b31  mov     rcx, cs:WPP_GLOBAL_Control
0x180160b38  cmp     rcx, r12
0x180160b3b  jz      short loc_180160B59
0x180160b3d  test    byte ptr [rcx+1Ch], 2
0x180160b41  jz      short loc_180160B59
0x180160b43  mov     edx, 0Ch
0x180160b48  lea     r8, WPP_eb55907698d2371455f751e0d7f04c24_Traceguids
0x180160b4f  mov     rcx, [rcx+10h]
0x180160b53  call    WPP_SF_
0x180160b58  nop
0x180160b59  lea     rcx, [rsp+158h+var_D8]
0x180160b61  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x180160b66  xor     eax, eax
0x180160b68  jmp     loc_1801611E2
0x180160b6d  mov     [rsp+158h+var_88], r14
0x180160b75  mov     [rsp+158h+var_78], r14
0x180160b7d  mov     ebx, r14d
0x180160b80  mov     [rsp+158h+var_138], ebx
0x180160b84  mov     dword ptr [rsp+158h+var_130], ebx
0x180160b88  lea     rdx, [rsp+158h+var_78]
0x180160b90  lea     rcx, asc_18025D638; "."
0x180160b97  call    cs:__imp_MpConfigOpen
0x180160b9d  test    eax, eax
0x180160b9f  js      loc_180160C4F
0x180160ba5  lea     r8, [rsp+158h+var_130]
0x180160baa  lea     rdx, aBetaplatform; "BetaPlatform"
0x180160bb1  mov     rcx, [rsp+158h+var_78]
0x180160bb9  call    MpConfigGetValueBool
0x180160bbe  test    eax, eax
0x180160bc0  jns     short loc_180160BF3
0x180160bc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180160bc9  cmp     rcx, r12
0x180160bcc  jz      short loc_180160BEC
0x180160bce  test    byte ptr [rcx+1Ch], 2
0x180160bd2  jz      short loc_180160BEC
0x180160bd4  mov     edx, 0Dh
0x180160bd9  mov     r9d, eax
0x180160bdc  lea     r8, WPP_eb55907698d2371455f751e0d7f04c24_Traceguids
0x180160be3  mov     rcx, [rcx+10h]
0x180160be7  call    WPP_SF_d
0x180160bec  mov     [rsp+158h+var_138], r14d
0x180160bf1  jmp     short loc_180160BFB
0x180160bf3  mov     eax, dword ptr [rsp+158h+var_130]
0x180160bf7  mov     [rsp+158h+var_138], eax
0x180160bfb  mov     rcx, [rsp+158h+var_88]
0x180160c03  test    rcx, rcx
0x180160c06  jz      short loc_180160C16
0x180160c08  call    cs:__imp_MpFreeMemory
0x180160c0e  mov     [rsp+158h+var_88], r14
0x180160c16  lea     r8, [rsp+158h+var_88]
0x180160c1e  lea     rdx, aProductguid; "ProductGUID"
0x180160c25  mov     rcx, [rsp+158h+var_78]
0x180160c2d  call    MpConfigGetValueString
0x180160c32  test    eax, eax
0x180160c34  jns     short loc_180160C79
0x180160c36  mov     rcx, cs:WPP_GLOBAL_Control
0x180160c3d  cmp     rcx, r12
0x180160c40  jz      short loc_180160C79
0x180160c42  test    byte ptr [rcx+1Ch], 2
0x180160c46  jz      short loc_180160C79
0x180160c48  mov     edx, 0Eh
0x180160c4d  jmp     short loc_180160C66
0x180160c4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180160c56  cmp     rcx, r12
0x180160c59  jz      short loc_180160C79
0x180160c5b  test    byte ptr [rcx+1Ch], 2
0x180160c5f  jz      short loc_180160C79
0x180160c61  mov     edx, 0Fh
0x180160c66  mov     r9d, eax
0x180160c69  lea     r8, WPP_eb55907698d2371455f751e0d7f04c24_Traceguids
0x180160c70  mov     rcx, [rcx+10h]
0x180160c74  call    WPP_SF_d
0x180160c79  mov     [rsp+158h+var_90], r14
0x180160c81  mov     [rsp+158h+var_70], r14
0x180160c89  lea     rdx, [rsp+158h+var_70]
0x180160c91  lea     rcx, aFeatures_0; "Features"
0x180160c98  call    cs:__imp_MpConfigOpen
0x180160c9e  test    eax, eax
0x180160ca0  js      short loc_180160CF6
0x180160ca2  mov     rcx, [rsp+158h+var_90]
0x180160caa  test    rcx, rcx
0x180160cad  jz      short loc_180160CBD
0x180160caf  call    cs:__imp_MpFreeMemory
0x180160cb5  mov     [rsp+158h+var_90], r14
0x180160cbd  lea     r8, [rsp+158h+var_90]
0x180160cc5  lea     rdx, aSenseorgid; "SenseOrgId"
0x180160ccc  mov     rcx, [rsp+158h+var_70]
0x180160cd4  call    MpConfigGetValueString
0x180160cd9  test    eax, eax
0x180160cdb  jns     short loc_180160D20
0x180160cdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180160ce4  cmp     rcx, r12
0x180160ce7  jz      short loc_180160D20
0x180160ce9  test    byte ptr [rcx+1Ch], 2
0x180160ced  jz      short loc_180160D20
0x180160cef  mov     edx, 10h
0x180160cf4  jmp     short loc_180160D0D
0x180160cf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180160cfd  cmp     rcx, r12
0x180160d00  jz      short loc_180160D20
0x180160d02  test    byte ptr [rcx+1Ch], 2
0x180160d06  jz      short loc_180160D20
0x180160d08  mov     edx, 11h
0x180160d0d  mov     r9d, eax
0x180160d10  lea     r8, WPP_eb55907698d2371455f751e0d7f04c24_Traceguids
0x180160d17  mov     rcx, [rcx+10h]
0x180160d1b  call    WPP_SF_d
0x180160d20  mov     [rsp+158h+var_130], r14
0x180160d25  mov     [rsp+158h+var_110], r14
0x180160d2a  mov     [rsp+158h+var_108], r14
0x180160d2f  lea     r8, [rsp+158h+var_108]; wchar_t **
0x180160d34  lea     rdx, [rsp+158h+var_110]; wchar_t **
0x180160d39  lea     rcx, [rsp+158h+var_130]; this
0x180160d3e  call    ?GetEngineFilesVersion@MpConfigUtils@@YAJPEAPEA_W00@Z; MpConfigUtils::GetEngineFilesVersion(wchar_t * *,wchar_t * *,wchar_t * *)
0x180160d43  test    eax, eax
0x180160d45  jns     short loc_180160D71
0x180160d47  mov     rcx, cs:WPP_GLOBAL_Control
0x180160d4e  cmp     rcx, r12
0x180160d51  jz      short loc_180160D71
0x180160d53  test    byte ptr [rcx+1Ch], 2
0x180160d57  jz      short loc_180160D71
0x180160d59  mov     edx, 12h
0x180160d5e  mov     r9d, eax
0x180160d61  lea     r8, WPP_eb55907698d2371455f751e0d7f04c24_Traceguids
0x180160d68  mov     rcx, [rcx+10h]
0x180160d6c  call    WPP_SF_d
0x180160d71  mov     [rsp+158h+var_80], r14
0x180160d79  mov     [rsp+158h+var_128], r14
0x180160d7e  lea     rdx, aMsmplicsDll; "MsMpLics.dll"
0x180160d85  lea     rcx, [rsp+158h+var_128]; this
0x180160d8a  call    ?GetMpFileFullName@MpConfigUtils@@YAJPEAPEA_WPEB_W_N@Z; MpConfigUtils::GetMpFileFullName(wchar_t * *,wchar_t const *,bool)
0x180160d8f  mov     edi, eax
0x180160d91  test    eax, eax
0x180160d93  jns     short loc_180160DA7
0x180160d95  mov     rcx, [rsp+158h+var_128]
0x180160d9a  test    rcx, rcx
0x180160d9d  jz      short loc_180160DD0
0x180160d9f  call    cs:__imp_MpFreeMemory
0x180160da5  jmp     short loc_180160DD0
0x180160da7  mov     rbx, [rsp+158h+var_128]
0x180160dac  mov     rdx, rbx; wchar_t **
0x180160daf  lea     rcx, [rsp+158h+var_80]; this
0x180160db7  call    ?GetFileVersion@MpConfigUtils@@YAJPEAPEA_WPEB_W@Z; MpConfigUtils::GetFileVersion(wchar_t * *,wchar_t const *)
0x180160dbc  mov     edi, eax
0x180160dbe  test    rbx, rbx
0x180160dc1  jz      short loc_180160DCC
0x180160dc3  mov     rcx, rbx
0x180160dc6  call    cs:__imp_MpFreeMemory
0x180160dcc  test    edi, edi
0x180160dce  jns     short loc_180160DFA
0x180160dd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180160dd7  cmp     rcx, r12
0x180160dda  jz      short loc_180160DFA
0x180160ddc  test    byte ptr [rcx+1Ch], 2
0x180160de0  jz      short loc_180160DFA
0x180160de2  mov     edx, 13h
0x180160de7  mov     r9d, edi
0x180160dea  lea     r8, WPP_eb55907698d2371455f751e0d7f04c24_Traceguids
0x180160df1  mov     rcx, [rcx+10h]
0x180160df5  call    WPP_SF_d
0x180160dfa  mov     [rsp+158h+var_128], r14
0x180160dff  lea     rcx, [rsp+158h+var_128]; this
0x180160e04  call    ?GetPartnerGUID@MpConfigUtils@@YAJPEAPEA_W@Z; MpConfigUtils::GetPartnerGUID(wchar_t * *)
0x180160e09  mov     r13d, eax
0x180160e0c  test    eax, eax
0x180160e0e  jns     short loc_180160E3D
0x180160e10  mov     rcx, cs:WPP_GLOBAL_Control
0x180160e17  cmp     rcx, r12
0x180160e1a  jz      short loc_180160E3A
0x180160e1c  test    byte ptr [rcx+1Ch], 2
0x180160e20  jz      short loc_180160E3A
0x180160e22  mov     edx, 14h
0x180160e27  mov     r9d, eax
0x180160e2a  lea     r8, WPP_eb55907698d2371455f751e0d7f04c24_Traceguids
0x180160e31  mov     rcx, [rcx+10h]
0x180160e35  call    WPP_SF_d
0x180160e3a  mov     r13d, r14d
0x180160e3d  lea     rbx, qword_18025C818
0x180160e44  mov     rdx, rbx
0x180160e47  cmp     [rsp+158h+var_88], r14
0x180160e4f  cmovnz  rdx, [rsp+158h+var_88]
0x180160e58  lea     rcx, [rsp+158h+var_120]
0x180160e5d  call    ?TrDuplicateStringW@CommonUtil@@YA?AV?$CReturnHandle@V?$CUniqueHandle@U?$CAutoUniqueArrayPtrDelete2@PEA_W@CommonUtil@@@CommonUtil@@@1@PEB_W@Z; CommonUtil::TrDuplicateStringW(wchar_t const *)
0x180160e62  mov     rcx, [rax]
0x180160e65  mov     [rsp+158h+var_100], rcx
0x180160e6a  mov     [rax], r14
0x180160e6d  mov     [rsp+158h+var_C8], rcx
0x180160e75  mov     rcx, [rsp+158h+var_120]; void *
0x180160e7a  test    rcx, rcx
0x180160e7d  jz      short loc_180160E84
0x180160e7f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180160e84  mov     rdx, rbx
0x180160e87  mov     rsi, [rsp+158h+var_130]
0x180160e8c  test    rsi, rsi
0x180160e8f  cmovnz  rdx, rsi
0x180160e93  lea     rcx, [rsp+158h+var_118]
0x180160e98  call    ?TrDuplicateStringW@CommonUtil@@YA?AV?$CReturnHandle@V?$CUniqueHandle@U?$CAutoUniqueArrayPtrDelete2@PEA_W@CommonUtil@@@CommonUtil@@@1@PEB_W@Z; CommonUtil::TrDuplicateStringW(wchar_t const *)
0x180160e9d  mov     rcx, [rax]
0x180160ea0  mov     [rsp+158h+var_F8], rcx
0x180160ea5  mov     [rax], r14
0x180160ea8  mov     [rsp+158h+var_C0], rcx
0x180160eb0  mov     rcx, [rsp+158h+var_118]; void *
0x180160eb5  test    rcx, rcx
0x180160eb8  jz      short loc_180160EBF
0x180160eba  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180160ebf  mov     rdx, rbx
0x180160ec2  mov     rdi, [rsp+158h+var_110]
0x180160ec7  test    rdi, rdi
0x180160eca  cmovnz  rdx, rdi
0x180160ece  lea     rcx, [rsp+158h+var_120]
0x180160ed3  call    ?TrDuplicateStringW@CommonUtil@@YA?AV?$CReturnHandle@V?$CUniqueHandle@U?$CAutoUniqueArrayPtrDelete2@PEA_W@CommonUtil@@@CommonUtil@@@1@PEB_W@Z; CommonUtil::TrDuplicateStringW(wchar_t const *)
0x180160ed8  mov     rcx, [rax]
0x180160edb  mov     [rsp+158h+var_F0], rcx
0x180160ee0  mov     [rax], r14
0x180160ee3  mov     [rsp+158h+var_B8], rcx
0x180160eeb  mov     rcx, [rsp+158h+var_120]; void *
0x180160ef0  test    rcx, rcx
0x180160ef3  jz      short loc_180160EFA
0x180160ef5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180160efa  mov     rdx, rbx
0x180160efd  cmp     [rsp+158h+var_80], r14
0x180160f05  cmovnz  rdx, [rsp+158h+var_80]
0x180160f0e  lea     rcx, [rsp+158h+var_118]
0x180160f13  call    ?TrDuplicateStringW@CommonUtil@@YA?AV?$CReturnHandle@V?$CUniqueHandle@U?$CAutoUniqueArrayPtrDelete2@PEA_W@CommonUtil@@@CommonUtil@@@1@PEB_W@Z; CommonUtil::TrDuplicateStringW(wchar_t const *)
0x180160f18  mov     rcx, [rax]
0x180160f1b  mov     [rsp+158h+var_E8], rcx
0x180160f20  mov     [rax], r14
0x180160f23  mov     [rsp+158h+var_B0], rcx
0x180160f2b  mov     rcx, [rsp+158h+var_118]; void *
0x180160f30  test    rcx, rcx
0x180160f33  jz      short loc_180160F3A
0x180160f35  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180160f3a  mov     rdx, rbx
0x180160f3d  mov     rbx, [rsp+158h+var_128]
0x180160f42  test    rbx, rbx
0x180160f45  cmovnz  rdx, rbx
0x180160f49  lea     rcx, [rsp+158h+var_120]
0x180160f4e  call    ?TrDuplicateStringW@CommonUtil@@YA?AV?$CReturnHandle@V?$CUniqueHandle@U?$CAutoUniqueArrayPtrDelete2@PEA_W@CommonUtil@@@CommonUtil@@@1@PEB_W@Z; CommonUtil::TrDuplicateStringW(wchar_t const *)
0x180160f53  mov     rcx, [rax]
0x180160f56  mov     [rsp+158h+var_E0], rcx
0x180160f5b  mov     [rax], r14
0x180160f5e  mov     [rsp+158h+var_A8], rcx
0x180160f66  mov     rcx, [rsp+158h+var_120]; void *
0x180160f6b  test    rcx, rcx
0x180160f6e  jz      short loc_180160F75
0x180160f70  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180160f75  cmp     [rsp+158h+var_90], r14
0x180160f7d  lea     rdx, qword_18025C818
0x180160f84  cmovnz  rdx, [rsp+158h+var_90]
0x180160f8d  lea     rcx, [rsp+158h+var_118]
0x180160f92  call    ?TrDuplicateStringW@CommonUtil@@YA?AV?$CReturnHandle@V?$CUniqueHandle@U?$CAutoUniqueArrayPtrDelete2@PEA_W@CommonUtil@@@CommonUtil@@@1@PEB_W@Z; CommonUtil::TrDuplicateStringW(wchar_t const *)
0x180160f97  mov     rcx, [rax]
0x180160f9a  mov     [rsp+158h+var_120], rcx
0x180160f9f  mov     [rax], r14
0x180160fa2  mov     [rsp+158h+var_A0], rcx
  ... truncated ...
```
