# RealtimeProtection::CRtpDlpEngine::OnLoadModule(PPID const &,wchar_t const *)

- ea: `0x18001a630`
- end: `0x18001ac5a`
- name: `?OnLoadModule@CRtpDlpEngine@RealtimeProtection@@QEAAJAEBUPPID@@PEB_W@Z`
- size: `1578`
- prototype: `int(RealtimeProtection::CRtpDlpEngine *__hidden this, const struct PPID *, const wchar_t *)`
- caller_count: `2`
- callee_count: `19`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180050370`
- `0x1800689f0`

## callees

- `0x18001a630`
- `0x18001ac60`
- `0x18001b220`
- `0x18001b5a0`
- `0x180027ab0`
- `0x180028d80`
- `0x180029590`
- `0x180034420`
- `0x180038450`
- `0x180040920`
- `0x1800809d0`
- `0x18010158c`
- `0x1801015a4`
- `0x180107874`
- `0x18010b558`
- `0x18010b568`
- `0x18010cb40`
- `0x18010ed90`
- `0x180119740`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x18001a6c8`
- `KERNEL32!AcquireSRWLockShared` at `0x18001a720`
- `KERNEL32!AcquireSRWLockShared` at `0x18001a6c8`
- `KERNEL32!AcquireSRWLockShared` at `0x18001a720`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001a7bb`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001a7ee`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001a805`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001a96b`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001a9bf`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001a9e0`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001aa39`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001aa93`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001aab2`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001aaea`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001abfa`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001a7bb`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001a7ee`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001a805`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001a96b`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001a9bf`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001a9e0`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001aa39`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001aa93`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001aab2`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001aaea`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001abfa`
- `KERNEL32!CompareFileTime` at `0x18001a791`
- `KERNEL32!CompareFileTime` at `0x18001a791`

## string_xrefs

- `0x18001a6ac`: `kernel32.dll`
- `0x18001a9ed`: `kernel32.dll`
- `0x18001aa47`: `kernel32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RealtimeProtection::CRtpDlpEngine::OnLoadModule(
        RealtimeProtection::CRtpDlpEngine *this,
        FILETIME *a2,
        const wchar_t *a3)
{
  wchar_t *v6; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  std::_Ref_count_base *v11; // r15
  RTL_SRWLOCK *v12; // r13
  _QWORD *Ptr; // rax
  __int64 v14; // r14
  const wchar_t *v15; // r8
  char v16; // r14
  std::_Ref_count_base *v17; // rcx
  const wchar_t *v18; // rbx
  const struct PPID *v19; // rdx
  bool v20; // r8
  int v21; // eax
  int ApplicationName; // eax
  const wchar_t *v23; // r9
  const struct PPID *v24; // r8
  int v25; // eax
  unsigned int v26; // ebx
  int SystemPath; // eax
  unsigned int v28; // r15d
  int SystemWow64Path; // eax
  struct PPID **v30; // rcx
  __int64 v31; // [rsp+0h] [rbp-F8h] BYREF
  __int16 v32; // [rsp+20h] [rbp-D8h]
  const std::exception *v33[2]; // [rsp+28h] [rbp-D0h] BYREF
  char v34; // [rsp+38h] [rbp-C0h]
  _BYTE v35[32]; // [rsp+40h] [rbp-B8h] BYREF
  std::_Ref_count_base *v36[2]; // [rsp+60h] [rbp-98h] BYREF
  struct PPID *v37[2]; // [rsp+70h] [rbp-88h] BYREF
  __int64 v38; // [rsp+80h] [rbp-78h]
  unsigned __int64 v39; // [rsp+88h] [rbp-70h]
  wchar_t *String1[4]; // [rsp+90h] [rbp-68h] BYREF
  char v41; // [rsp+B0h] [rbp-48h]

  if ( *((_DWORD *)this + 2) != 2 )
    return 0;
  if ( !a3 )
    return 1;
  v6 = wcsrchr(a3, 0x5Cu);
  if ( !v6 || wcsicmp(v6 + 1, L"kernel32.dll") )
    return 0;
  v33[1] = (RealtimeProtection::CRtpDlpEngine *)((char *)this + 16);
  AcquireSRWLockShared((PSRWLOCK)this + 2);
  v34 = 1;
  if ( *((_DWORD *)this + 2) != 2 )
  {
    ReleaseSRWLockShared((PSRWLOCK)this + 2);
    return 0;
  }
  v32 = 0;
  Lock_shared_ptr_spin_lock(v9, v8, v10);
  v11 = qword_180314488;
  if ( qword_180314488 )
  {
    _InterlockedIncrement((volatile signed __int32 *)qword_180314488 + 2);
    v11 = qword_180314488;
  }
  v12 = (RTL_SRWLOCK *)qword_180314480;
  Unlock_shared_ptr_spin_lock();
  if ( !v12 )
  {
    if ( v11 )
      std::_Ref_count_base::_Decref(v11);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 576, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, 2147483662LL);
    ReleaseSRWLockShared((PSRWLOCK)this + 2);
    return 2147483662LL;
  }
  AcquireSRWLockShared(v12 + 58);
  LODWORD(v36[0]) = 0;
  MpHashCrc32(v36, 12);
  Ptr = v12[28].Ptr;
  v14 = Ptr[2 * (LODWORD(v36[0]) & (__int64)v12[31].Ptr) + 1];
  if ( (PVOID)v14 == v12[26].Ptr )
  {
LABEL_24:
    v14 = 0;
  }
  else
  {
    v36[0] = (std::_Ref_count_base *)Ptr[2 * (LODWORD(v36[0]) & (__int64)v12[31].Ptr)];
    while ( a2[1].dwLowDateTime != *(_DWORD *)(v14 + 24) || CompareFileTime(a2, (const FILETIME *)(v14 + 16)) )
    {
      if ( (std::_Ref_count_base *)v14 == v36[0] )
        goto LABEL_24;
      v14 = *(_QWORD *)(v14 + 8);
    }
  }
  if ( !v14 || (PVOID)v14 == v12[26].Ptr )
  {
    ReleaseSRWLockShared(v12 + 58);
    v16 = 0;
  }
  else
  {
    LODWORD(v36[0]) = *(_DWORD *)(v14 + 496);
    ReleaseSRWLockShared(v12 + 58);
    v16 = BYTE3(v36[0]);
    v32 = (__int16)v36[0];
  }
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
  if ( !v16 || v32 )
  {
    ReleaseSRWLockShared((PSRWLOCK)this + 2);
    return 1;
  }
  if ( !*((_QWORD *)this + 16) )
  {
    SystemPath = CommonUtil::UtilGetSystemPath(
                   (RealtimeProtection::CRtpDlpEngine *)((char *)this + 128),
                   (wchar_t **)L"kernel32.dll",
                   v15);
    v28 = SystemPath;
    if ( SystemPath < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          577,
          &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
          (unsigned int)SystemPath);
LABEL_54:
      ReleaseSRWLockShared((PSRWLOCK)this + 2);
      return v28;
    }
  }
  if ( !*((_QWORD *)this + 17) )
  {
    SystemWow64Path = CommonUtil::UtilGetSystemWow64Path(
                        (RealtimeProtection::CRtpDlpEngine *)((char *)this + 136),
                        (wchar_t **)L"kernel32.dll",
                        v15);
    v28 = SystemWow64Path;
    if ( SystemWow64Path < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          578,
          &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
          (unsigned int)SystemWow64Path);
      goto LABEL_54;
    }
  }
  try
  {
    std::wstring::wstring(v35, a3);
    *(_OWORD *)v36 = 0;
    std::atomic_load__anonymous_namespace_::DlpPathCacheImpl_(v36);
  }
  catch ( const std::exception *v33 )
  {
    CommonUtil::HrFromStdException(v33[0], (const struct std::exception *)&v31);
  }
  catch ( ... )
  {
    LODWORD(v36[0]) = -2147467259;
    v26 = (unsigned int)v36[0];
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        582,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        LODWORD(v36[0]));
    return v26;
  }
  if ( !v36[0] )
  {
    v41 = 0;
    v17 = v36[1];
    if ( !v36[1] )
      goto LABEL_32;
    goto LABEL_31;
  }
  anonymous_namespace_::DlpPathCacheImpl::GetDosPathFromFilterPath(v36[0], String1, v35);
  v17 = v36[1];
  if ( v36[1] )
LABEL_31:
    std::_Ref_count_base::_Decref(v17);
LABEL_32:
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v35);
  if ( !v41 )
    goto LABEL_60;
  v18 = (const wchar_t *)String1;
  if ( String1[3] > (wchar_t *)7 )
    v18 = String1[0];
  if ( wcsicmp(v18, *((const wchar_t **)this + 16)) && wcsicmp(v18, *((const wchar_t **)this + 17)) )
  {
LABEL_60:
    std::optional<std::wstring>::~optional<std::wstring>(String1);
    ReleaseSRWLockShared((PSRWLOCK)this + 2);
    return 1;
  }
  else
  {
    v21 = RealtimeProtection::DlpProcessCache::SetProcessInitializationState(
            (RealtimeProtection::DlpProcessCache *)a2,
            v19,
            v20);
    if ( v21 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        579,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)v21);
    *(_OWORD *)v37 = 0;
    v38 = 0;
    v39 = 7;
    LOWORD(v37[0]) = 0;
    ApplicationName = RealtimeProtection::DlpProcessCache::GetApplicationName(a2, v37);
    if ( ApplicationName < 0 )
    {
      v38 = 0;
      v30 = v37;
      if ( v39 > 7 )
        v30 = (struct PPID **)v37[0];
      *(_WORD *)v30 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          580,
          &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
          (unsigned int)ApplicationName);
    }
    v24 = (const struct PPID *)v37;
    if ( v39 > 7 )
      v24 = v37[0];
    v25 = RealtimeProtection::DlpInjection::InjectEnforcementDllAsync(
            (RealtimeProtection::DlpInjection *)*((unsigned int *)this + 14),
            (const struct PPID *)a2,
            v24,
            v23);
    v26 = v25;
    if ( v25 >= 0 )
    {
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v37);
      std::optional<std::wstring>::~optional<std::wstring>(String1);
      ReleaseSRWLockShared((PSRWLOCK)this + 2);
      return v26;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        581,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        (unsigned int)v25);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v37);
    std::optional<std::wstring>::~optional<std::wstring>(String1);
    ReleaseSRWLockShared((PSRWLOCK)this + 2);
    return v26;
  }
}

```

## disassembly

```asm
0x18001a630  push    rbx
0x18001a632  push    rsi
0x18001a633  push    rdi
0x18001a634  push    r12
0x18001a636  push    r13
0x18001a638  push    r14
0x18001a63a  push    r15
0x18001a63c  sub     rsp, 0C0h
0x18001a643  mov     rax, cs:__security_cookie
0x18001a64a  xor     rax, rsp
0x18001a64d  mov     [rsp+0F8h+var_40], rax
0x18001a655  mov     rbx, r8
0x18001a658  mov     rsi, rdx
0x18001a65b  mov     rdi, rcx
0x18001a65e  cmp     dword ptr [rcx+8], 2
0x18001a662  jnz     loc_18001A9CC
0x18001a668  test    rbx, rbx
0x18001a66b  jz      loc_18001A9D3
0x18001a671  mov     edx, 5Ch ; '\'; Ch
0x18001a676  mov     rcx, rbx; Str
0x18001a679  call    wcsrchr
0x18001a67e  test    rax, rax
0x18001a681  jnz     short loc_18001A6A8
0x18001a683  xor     eax, eax
0x18001a685  mov     rcx, [rsp+0F8h+var_40]
0x18001a68d  xor     rcx, rsp; StackCookie
0x18001a690  call    __security_check_cookie
0x18001a695  add     rsp, 0C0h
0x18001a69c  pop     r15
0x18001a69e  pop     r14
0x18001a6a0  pop     r13
0x18001a6a2  pop     r12
0x18001a6a4  pop     rdi
0x18001a6a5  pop     rsi
0x18001a6a6  pop     rbx
0x18001a6a7  retn
0x18001a6a8  lea     rcx, [rax+2]; String1
0x18001a6ac  lea     rdx, aKernel32Dll_0; "kernel32.dll"
0x18001a6b3  call    _wcsicmp
0x18001a6b8  test    eax, eax
0x18001a6ba  jnz     short loc_18001A683
0x18001a6bc  lea     r12, [rdi+10h]
0x18001a6c0  mov     [rsp+0F8h+var_C8], r12
0x18001a6c5  mov     rcx, r12; SRWLock
0x18001a6c8  call    cs:__imp_AcquireSRWLockShared
0x18001a6ce  mov     [rsp+0F8h+var_C0], 1
0x18001a6d3  cmp     dword ptr [rdi+8], 2
0x18001a6d7  jnz     loc_18001A9DD
0x18001a6dd  mov     byte ptr [rsp+0F8h+var_D8], 0
0x18001a6e2  mov     byte ptr [rsp+0F8h+var_D8+1], 0
0x18001a6e7  call    _Lock_shared_ptr_spin_lock
0x18001a6ec  mov     r15, cs:qword_180314488
0x18001a6f3  test    r15, r15
0x18001a6f6  jz      short loc_18001A704
0x18001a6f8  lock inc dword ptr [r15+8]
0x18001a6fd  mov     r15, cs:qword_180314488
0x18001a704  mov     r13, cs:qword_180314480
0x18001a70b  call    _Unlock_shared_ptr_spin_lock
0x18001a710  test    r13, r13
0x18001a713  jz      loc_18001ABB5
0x18001a719  lea     rcx, [r13+1D0h]; SRWLock
0x18001a720  call    cs:__imp_AcquireSRWLockShared
0x18001a726  xor     eax, eax
0x18001a728  mov     dword ptr [rsp+0F8h+var_98], eax
0x18001a72c  mov     r8, rsi
0x18001a72f  mov     edx, 0Ch
0x18001a734  lea     rcx, [rsp+0F8h+var_98]
0x18001a739  call    MpHashCrc32
0x18001a73e  mov     eax, dword ptr [rsp+0F8h+var_98]
0x18001a742  mov     rcx, [r13+0F8h]
0x18001a749  and     rcx, rax
0x18001a74c  add     rcx, rcx
0x18001a74f  mov     rax, [r13+0E0h]
0x18001a756  mov     r14, [rax+rcx*8+8]
0x18001a75b  cmp     r14, [r13+0D0h]
0x18001a762  jz      loc_18001A810
0x18001a768  mov     rax, [rax+rcx*8]
0x18001a76c  mov     [rsp+0F8h+var_98], rax
0x18001a771  lea     rdx, [r14+10h]; lpFileTime2
0x18001a775  mov     eax, [rdx+8]
0x18001a778  cmp     [rsi+8], eax
0x18001a77b  jz      short loc_18001A78E
0x18001a77d  cmp     r14, [rsp+0F8h+var_98]
0x18001a782  jz      loc_18001A810
0x18001a788  mov     r14, [r14+8]
0x18001a78c  jmp     short loc_18001A771
0x18001a78e  mov     rcx, rsi; lpFileTime1
0x18001a791  call    cs:__imp_CompareFileTime
0x18001a797  test    eax, eax
0x18001a799  jnz     short loc_18001A77D
0x18001a79b  test    r14, r14
0x18001a79e  jz      short loc_18001A7FE
0x18001a7a0  cmp     r14, [r13+0D0h]
0x18001a7a7  jz      short loc_18001A7FE
0x18001a7a9  mov     eax, [r14+1F0h]
0x18001a7b0  mov     dword ptr [rsp+0F8h+var_98], eax
0x18001a7b4  lea     rcx, [r13+1D0h]; SRWLock
0x18001a7bb  call    cs:__imp_ReleaseSRWLockShared
0x18001a7c1  movzx   r14d, byte ptr [rsp+0F8h+var_98+3]
0x18001a7c7  movzx   eax, byte ptr [rsp+0F8h+var_98+1]
0x18001a7cc  mov     byte ptr [rsp+0F8h+var_D8+1], al
0x18001a7d0  movzx   eax, byte ptr [rsp+0F8h+var_98]
0x18001a7d5  mov     byte ptr [rsp+0F8h+var_D8], al
0x18001a7d9  test    r15, r15
0x18001a7dc  jz      short loc_18001A7E6
0x18001a7de  mov     rcx, r15; this
0x18001a7e1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001a7e6  test    r14b, r14b
0x18001a7e9  jnz     short loc_18001A815
0x18001a7eb  mov     rcx, r12; SRWLock
0x18001a7ee  call    cs:__imp_ReleaseSRWLockShared
0x18001a7f4  mov     eax, 1
0x18001a7f9  jmp     loc_18001A685
0x18001a7fe  lea     rcx, [r13+1D0h]; SRWLock
0x18001a805  call    cs:__imp_ReleaseSRWLockShared
0x18001a80b  xor     r14b, r14b
0x18001a80e  jmp     short loc_18001A7D9
0x18001a810  xor     r14d, r14d
0x18001a813  jmp     short loc_18001A79B
0x18001a815  cmp     byte ptr [rsp+0F8h+var_D8], 0
0x18001a81a  jnz     short loc_18001A7EB
0x18001a81c  cmp     byte ptr [rsp+0F8h+var_D8+1], 0
0x18001a821  jnz     short loc_18001A7EB
0x18001a823  lea     rcx, [rdi+80h]; this
0x18001a82a  cmp     qword ptr [rcx], 0
0x18001a82e  jz      loc_18001A9ED
0x18001a834  lea     rcx, [rdi+88h]; this
0x18001a83b  cmp     qword ptr [rcx], 0
0x18001a83f  jz      loc_18001AA47
0x18001a845  mov     rdx, rbx
0x18001a848  lea     rcx, [rsp+0F8h+var_B8]
0x18001a84d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001a852  xorps   xmm0, xmm0
0x18001a855  movups  xmmword ptr [rsp+0F8h+var_98], xmm0
0x18001a85a  lea     rcx, [rsp+0F8h+var_98]
0x18001a85f  call    std__atomic_load__anonymous_namespace___DlpPathCacheImpl_
0x18001a864  mov     rcx, [rsp+0F8h+var_98]
0x18001a869  test    rcx, rcx
0x18001a86c  jz      loc_18001A979
0x18001a872  lea     r8, [rsp+0F8h+var_B8]
0x18001a877  lea     rdx, [rsp+0F8h+String1]
0x18001a87f  call    _anonymous_namespace___DlpPathCacheImpl__GetDosPathFromFilterPath
0x18001a884  mov     rcx, [rsp+0F8h+var_98+8]; this
0x18001a889  test    rcx, rcx
0x18001a88c  jz      short loc_18001A893
0x18001a88e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001a893  lea     rcx, [rsp+0F8h+var_B8]; void *
0x18001a898  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18001a89d  cmp     [rsp+0F8h+var_48], 0
0x18001a8a5  jz      loc_18001AAA1
0x18001a8ab  lea     rbx, [rsp+0F8h+String1]
0x18001a8b3  cmp     [rsp+0F8h+var_50], 7
0x18001a8bc  cmova   rbx, [rsp+0F8h+String1]
0x18001a8c5  mov     rdx, [rdi+80h]; String2
0x18001a8cc  mov     rcx, rbx; String1
0x18001a8cf  call    _wcsicmp
0x18001a8d4  test    eax, eax
0x18001a8d6  jnz     loc_18001AAC2
0x18001a8dc  mov     rcx, rsi; this
0x18001a8df  call    ?SetProcessInitializationState@DlpProcessCache@RealtimeProtection@@YAJAEBUPPID@@_N@Z; RealtimeProtection::DlpProcessCache::SetProcessInitializationState(PPID const &,bool)
0x18001a8e4  test    eax, eax
0x18001a8e6  js      loc_18001AAFA
0x18001a8ec  lea     r14, WPP_GLOBAL_Control
0x18001a8f3  xorps   xmm0, xmm0
0x18001a8f6  movups  xmmword ptr [rsp+0F8h+var_88], xmm0
0x18001a8fb  xor     ebx, ebx
0x18001a8fd  mov     [rsp+0F8h+var_78], rbx
0x18001a905  mov     [rsp+0F8h+var_70], 7
0x18001a911  mov     word ptr [rsp+0F8h+var_88], bx
0x18001a916  lea     rdx, [rsp+0F8h+var_88]
0x18001a91b  mov     rcx, rsi
0x18001a91e  call    ?GetApplicationName@DlpProcessCache@RealtimeProtection@@YAJAEBUPPID@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; RealtimeProtection::DlpProcessCache::GetApplicationName(PPID const &,std::wstring &)
0x18001a923  test    eax, eax
0x18001a925  js      loc_18001AB38
0x18001a92b  lea     r8, [rsp+0F8h+var_88]
0x18001a930  cmp     [rsp+0F8h+var_70], 7
0x18001a939  cmova   r8, [rsp+0F8h+var_88]; struct PPID *
0x18001a93f  mov     rdx, rsi; unsigned int
0x18001a942  mov     ecx, [rdi+38h]; this
0x18001a945  call    ?InjectEnforcementDllAsync@DlpInjection@RealtimeProtection@@YAJKAEBUPPID@@QEB_W@Z; RealtimeProtection::DlpInjection::InjectEnforcementDllAsync(ulong,PPID const &,wchar_t const * const)
0x18001a94a  mov     ebx, eax
0x18001a94c  test    eax, eax
0x18001a94e  js      short loc_18001A994
0x18001a950  lea     rcx, [rsp+0F8h+var_88]; void *
0x18001a955  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18001a95a  lea     rcx, [rsp+0F8h+String1]
0x18001a962  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x18001a967  nop
0x18001a968  mov     rcx, r12; SRWLock
0x18001a96b  call    cs:__imp_ReleaseSRWLockShared
0x18001a971  nop
0x18001a972  mov     eax, ebx
0x18001a974  jmp     loc_18001A685
0x18001a979  mov     [rsp+0F8h+var_48], 0
0x18001a981  mov     rcx, [rsp+0F8h+var_98+8]
0x18001a986  test    rcx, rcx
0x18001a989  jnz     loc_18001A88E
0x18001a98f  jmp     loc_18001A893
0x18001a994  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a99b  cmp     rcx, r14
0x18001a99e  jnz     loc_18001AB8E
0x18001a9a4  lea     rcx, [rsp+0F8h+var_88]; void *
0x18001a9a9  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18001a9ae  lea     rcx, [rsp+0F8h+String1]
0x18001a9b6  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x18001a9bb  nop
0x18001a9bc  mov     rcx, r12; SRWLock
0x18001a9bf  call    cs:__imp_ReleaseSRWLockShared
0x18001a9c5  mov     eax, ebx
0x18001a9c7  jmp     loc_18001A685
0x18001a9cc  xor     eax, eax
0x18001a9ce  jmp     loc_18001A685
0x18001a9d3  mov     eax, 1
0x18001a9d8  jmp     loc_18001A685
0x18001a9dd  mov     rcx, r12; SRWLock
0x18001a9e0  call    cs:__imp_ReleaseSRWLockShared
0x18001a9e6  xor     eax, eax
0x18001a9e8  jmp     loc_18001A685
0x18001a9ed  lea     rdx, aKernel32Dll_0; "kernel32.dll"
0x18001a9f4  call    ?UtilGetSystemPath@CommonUtil@@YAJPEAPEA_WPEB_W@Z; CommonUtil::UtilGetSystemPath(wchar_t * *,wchar_t const *)
0x18001a9f9  mov     r15d, eax
0x18001a9fc  test    eax, eax
0x18001a9fe  jns     loc_18001A834
0x18001aa04  lea     r14, WPP_GLOBAL_Control
0x18001aa0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa12  cmp     rcx, r14
0x18001aa15  jz      short loc_18001AA36
0x18001aa17  test    byte ptr [rcx+1Ch], 1
0x18001aa1b  jz      short loc_18001AA36
0x18001aa1d  mov     edx, 241h
0x18001aa22  mov     r9d, eax
0x18001aa25  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x18001aa2c  mov     rcx, [rcx+10h]
0x18001aa30  call    WPP_SF_d
0x18001aa35  nop
0x18001aa36  mov     rcx, r12; SRWLock
0x18001aa39  call    cs:__imp_ReleaseSRWLockShared
0x18001aa3f  mov     eax, r15d
0x18001aa42  jmp     loc_18001A685
0x18001aa47  lea     rdx, aKernel32Dll_0; "kernel32.dll"
0x18001aa4e  call    ?UtilGetSystemWow64Path@CommonUtil@@YAJPEAPEA_WPEB_W@Z; CommonUtil::UtilGetSystemWow64Path(wchar_t * *,wchar_t const *)
0x18001aa53  mov     r15d, eax
0x18001aa56  test    eax, eax
0x18001aa58  jns     loc_18001A845
0x18001aa5e  lea     r14, WPP_GLOBAL_Control
0x18001aa65  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa6c  cmp     rcx, r14
0x18001aa6f  jz      short loc_18001AA90
0x18001aa71  test    byte ptr [rcx+1Ch], 1
0x18001aa75  jz      short loc_18001AA90
0x18001aa77  mov     edx, 242h
0x18001aa7c  mov     r9d, eax
0x18001aa7f  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x18001aa86  mov     rcx, [rcx+10h]
0x18001aa8a  call    WPP_SF_d
0x18001aa8f  nop
0x18001aa90  mov     rcx, r12; SRWLock
0x18001aa93  call    cs:__imp_ReleaseSRWLockShared
0x18001aa99  mov     eax, r15d
0x18001aa9c  jmp     loc_18001A685
0x18001aaa1  lea     rcx, [rsp+0F8h+String1]
0x18001aaa9  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x18001aaae  nop
0x18001aaaf  mov     rcx, r12; SRWLock
0x18001aab2  call    cs:__imp_ReleaseSRWLockShared
0x18001aab8  mov     eax, 1
0x18001aabd  jmp     loc_18001A685
0x18001aac2  mov     rdx, [rdi+88h]; String2
0x18001aac9  mov     rcx, rbx; String1
0x18001aacc  call    _wcsicmp
0x18001aad1  test    eax, eax
0x18001aad3  jz      loc_18001A8DC
0x18001aad9  lea     rcx, [rsp+0F8h+String1]
0x18001aae1  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x18001aae6  nop
0x18001aae7  mov     rcx, r12; SRWLock
0x18001aaea  call    cs:__imp_ReleaseSRWLockShared
0x18001aaf0  mov     eax, 1
0x18001aaf5  jmp     loc_18001A685
0x18001aafa  lea     r14, WPP_GLOBAL_Control
0x18001ab01  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab08  cmp     rcx, r14
0x18001ab0b  jz      loc_18001A8F3
0x18001ab11  test    byte ptr [rcx+1Ch], 2
0x18001ab15  jz      loc_18001A8F3
0x18001ab1b  mov     edx, 243h
0x18001ab20  mov     r9d, eax
0x18001ab23  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x18001ab2a  mov     rcx, [rcx+10h]
0x18001ab2e  call    WPP_SF_d
0x18001ab33  jmp     loc_18001A8F3
0x18001ab38  mov     [rsp+0F8h+var_78], rbx
0x18001ab40  lea     rcx, [rsp+0F8h+var_88]
0x18001ab45  cmp     [rsp+0F8h+var_70], 7
0x18001ab4e  cmova   rcx, [rsp+0F8h+var_88]
0x18001ab54  mov     [rcx], bx
0x18001ab57  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab5e  cmp     rcx, r14
0x18001ab61  jz      loc_18001A92B
0x18001ab67  test    byte ptr [rcx+1Ch], 2
  ... truncated ...
```
