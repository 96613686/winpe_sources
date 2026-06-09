# CheckHDCPTypeEnforcementSupport(_LUID *,int)

- ea: `0x180188614`
- end: `0x180188dd0`
- name: `?CheckHDCPTypeEnforcementSupport@@YAHPEAU_LUID@@H@Z`
- size: `1980`
- prototype: `__int64 __fastcall(struct _LUID *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18018a190`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18009e6ec`
- `0x1800a0a24`
- `0x1800aeb78`
- `0x180125918`
- `0x1801481e4`
- `0x180174cec`
- `0x180188614`
- `0x18018b8d8`
- `0x18018bca4`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18018871c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18018871c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801886ef`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801886ef`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801886ce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801886ce`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18018893d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180188b50`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180188ba1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18018893d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180188b50`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180188ba1`

## string_xrefs

- `0x1801886c7`: `mfsvr.dll`
- `0x180188712`: `MFCreateHDCPStatus`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_BOOL8 __fastcall CheckHDCPTypeEnforcementSupport(struct _LUID *a1, unsigned int a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rbx
  HMODULE Library; // rdi
  HMODULE v7; // rbx
  FARPROC ProcAddress; // rbx
  int v9; // edi
  CallStackTracing *v10; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 (__fastcall *v13)(_QWORD, GUID *, __int64 *); // rdi
  CallStackTracing *v14; // rcx
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  DWORD TickCount; // ebx
  CallStackTracing *v18; // rcx
  struct CallStackContext *v19; // rax
  CallStackTracing *v20; // rcx
  struct CallStackContext *v21; // rax
  unsigned int v22; // ebx
  __int64 v23; // rdx
  __int64 v24; // r9
  unsigned int v25; // eax
  DWORD v26; // ebx
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  int v30; // ecx
  int v31; // eax
  __int64 v32; // r9
  CallStackTracing *v33; // rcx
  struct CallStackContext *v34; // rax
  CallStackTracing *v35; // rcx
  struct CallStackContext *v36; // rax
  CallStackTracing *v37; // rcx
  struct CallStackContext *v38; // rax
  unsigned int v39; // [rsp+40h] [rbp-20h] BYREF
  __int64 v40; // [rsp+48h] [rbp-18h] BYREF
  wil::last_error_context v41; // [rsp+50h] [rbp-10h] BYREF
  struct _LUID *v42; // [rsp+90h] [rbp+30h] BYREF
  int v43; // [rsp+A0h] [rbp+40h] BYREF
  int v44; // [rsp+A8h] [rbp+48h] BYREF

  v42 = a1;
  v40 = 0;
  v39 = 1;
  v44 = 1;
  dword_1801FD864 = 0;
  dword_1801FD874 = 0;
  v43 = 1;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v42, "CheckHDCPTypeEnforcementSupport", 370);
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 2u )
    WPP_SF_dDD(*((_QWORD *)WPP_GLOBAL_Control + 2), v3, v4, a2, HIDWORD(qword_1801FD888), qword_1801FD888);
  v5 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))qword_1801FCDF8;
  if ( !qword_1801FCDF8 )
  {
    Library = hModule;
    if ( hModule )
      goto LABEL_8;
    Library = LoadLibraryExW(L"mfsvr.dll", 0, 0x800u);
    v7 = hModule;
    if ( hModule )
    {
      wil::last_error_context::last_error_context(&v41);
      FreeLibrary(v7);
      wil::last_error_context::~last_error_context(&v41);
    }
    hModule = Library;
    v5 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))qword_1801FCDF8;
    if ( Library )
    {
LABEL_8:
      ProcAddress = GetProcAddress(Library, "MFCreateHDCPStatus");
      if ( ProcAddress )
      {
        Microsoft::WRL::ComPtr<IMFMediaSource>::InternalRelease(&qword_1801FCDF8);
        ((void (__fastcall *)(__int64 *))ProcAddress)(&qword_1801FCDF8);
      }
      v5 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))qword_1801FCDF8;
    }
  }
  if ( !v5 )
  {
    v9 = MF::OriginateError((MF *)0x80004005LL, v3);
    v10 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v10 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v10->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v10);
      if ( v9 < 0 && ThreadRelativeContext->m_result != v9 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CheckHDCPTypeEnforcementSupport", 390, v9);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_b5a5e24bc53137b87e8c3d8488016309_Traceguids, 0, v9);
LABEL_22:
    if ( !v9 )
      goto LABEL_25;
    goto LABEL_23;
  }
  v13 = **v5;
  Microsoft::WRL::ComPtr<IMFMediaSource>::InternalRelease(&v40);
  v9 = v13(v5, &GUID_259aa8f0_b24f_4fa5_af7d_ae186354d071, &v40);
  if ( v9 < 0 )
  {
    v14 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v14 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v14 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v14->m_fEnabled )
    {
      v15 = CallStackTracing::GetThreadRelativeContext(v14);
      if ( v15->m_result != v9 )
        CallStackContext::TraceFailure(v15, "CheckHDCPTypeEnforcementSupport", 391, v9);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_23;
    v16 = 34;
    goto LABEL_36;
  }
  TickCount = GetTickCount();
  v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *, int *))(*(_QWORD *)qword_1801FCDF8 + 24LL))(
         qword_1801FCDF8,
         &v39,
         &v43);
  if ( v9 < 0 )
  {
    v18 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v18 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v18 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v18->m_fEnabled )
    {
      v19 = CallStackTracing::GetThreadRelativeContext(v18);
      if ( v19->m_result != v9 )
        CallStackContext::TraceFailure(v19, "CheckHDCPTypeEnforcementSupport", 396, v9);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_23;
    v16 = 35;
    goto LABEL_36;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v40 + 32LL))(v40, &v44);
  if ( v9 < 0 )
  {
    v20 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v20 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v20 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v20->m_fEnabled )
    {
      v21 = CallStackTracing::GetThreadRelativeContext(v20);
      if ( v21->m_result != v9 )
        CallStackContext::TraceFailure(v21, "CheckHDCPTypeEnforcementSupport", 397, v9);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_23;
    v16 = 36;
LABEL_36:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_b5a5e24bc53137b87e8c3d8488016309_Traceguids, 0, v9);
    goto LABEL_23;
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 2u )
    WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_b5a5e24bc53137b87e8c3d8488016309_Traceguids, v39, v44, v43);
  if ( v39 != 2 || v43 )
  {
    if ( a2 )
      goto LABEL_68;
    v25 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v40 + 24LL))(v40, 2, &qword_1801FD888);
    v9 = v25;
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM < 2u )
      goto LABEL_68;
    v23 = 39;
    v24 = v25;
  }
  else
  {
    if ( !a2 )
      goto LABEL_68;
    v22 = TickCount - dword_1801FD890;
    dword_1801FD860 = v22;
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM < 2u )
      goto LABEL_68;
    v23 = 38;
    v24 = v22;
  }
  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, &WPP_b5a5e24bc53137b87e8c3d8488016309_Traceguids, v24);
LABEL_68:
  if ( v9 != 881000 )
    goto LABEL_22;
  v26 = GetTickCount();
  dword_1801FD890 = v26;
  do
  {
    v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *, int *))(*(_QWORD *)qword_1801FCDF8 + 24LL))(
           qword_1801FCDF8,
           &v39,
           &v43);
    if ( v9 < 0 )
    {
      v37 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v37 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v37 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v37->m_fEnabled )
      {
        v38 = CallStackTracing::GetThreadRelativeContext(v37);
        if ( v38->m_result != v9 )
          CallStackContext::TraceFailure(v38, "CheckHDCPTypeEnforcementSupport", 424, v9);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v16 = 40;
        goto LABEL_36;
      }
      goto LABEL_23;
    }
    v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v40 + 32LL))(v40, &v44);
    if ( v9 < 0 )
    {
      v35 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v35 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v35 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v35->m_fEnabled )
      {
        v36 = CallStackTracing::GetThreadRelativeContext(v35);
        if ( v36->m_result != v9 )
          CallStackContext::TraceFailure(v36, "CheckHDCPTypeEnforcementSupport", 425, v9);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v16 = 41;
        goto LABEL_36;
      }
      goto LABEL_23;
    }
    v29 = GetTickCount() - v26;
    dword_1801FD874 = v29;
    v30 = v44;
    v31 = v43;
  }
  while ( (unsigned int)v29 < 0x3E8 && v44 == 2 && v43 );
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_b5a5e24bc53137b87e8c3d8488016309_Traceguids, v29);
    v30 = v44;
    v31 = v43;
  }
  v32 = v39;
  if ( !v31 && v39 == 2 )
    goto LABEL_22;
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 2u )
    WPP_SF_DDDD(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, v28, v39, v30, v31);
  v9 = -2147024638;
  v33 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( ((unsigned int (__fastcall *)(CallStackTracing *, __int64, __int64, __int64))stru_1801FC290.CheckVersionMatch)(
           &stru_1801FC290,
           2032,
           v28,
           v32) )
    {
      v33 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v33 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v33->m_fEnabled )
  {
    v34 = CallStackTracing::GetThreadRelativeContext(v33);
    if ( v34->m_result != -2147024638 )
      CallStackContext::TraceFailure(v34, "CheckHDCPTypeEnforcementSupport", 439, -2147024638);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v16 = 44;
    goto LABEL_36;
  }
LABEL_23:
  dword_1801FD864 = v9;
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 2u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      45,
      &WPP_b5a5e24bc53137b87e8c3d8488016309_Traceguids,
      (unsigned int)v9);
LABEL_25:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v42);
  Microsoft::WRL::ComPtr<IMFMediaSource>::InternalRelease(&v40);
  return v9 == 0;
}

```

## disassembly

```asm
0x180188614  mov     [rsp-28h+arg_8], rbx
0x180188619  mov     [rsp-28h+arg_0], rcx
0x18018861e  push    rbp
0x18018861f  push    rsi
0x180188620  push    rdi
0x180188621  push    r12
0x180188623  push    r15
0x180188625  mov     rbp, rsp
0x180188628  sub     rsp, 60h
0x18018862c  mov     esi, edx
0x18018862e  mov     [rbp+var_18], 0
0x180188636  mov     r12d, 1
0x18018863c  mov     [rbp+var_20], r12d
0x180188640  mov     [rbp+arg_18], r12d
0x180188644  mov     cs:dword_1801FD864, 0
0x18018864e  mov     cs:dword_1801FD874, 0
0x180188658  mov     [rbp+arg_10], r12d
0x18018865c  mov     r8d, 172h; int
0x180188662  lea     rdx, aCheckhdcptypee; "CheckHDCPTypeEnforcementSupport"
0x180188669  lea     rcx, [rbp+arg_0]; this
0x18018866d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180188672  nop
0x180188673  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 2; MFWppLevels g_wppLevels
0x18018867a  jb      short loc_1801886A3
0x18018867c  mov     eax, dword ptr cs:qword_1801FD888
0x180188682  mov     [rsp+60h+var_38], eax
0x180188686  mov     eax, dword ptr cs:qword_1801FD888+4
0x18018868c  mov     [rsp+60h+var_40], eax
0x180188690  mov     r9d, esi
0x180188693  mov     rcx, cs:WPP_GLOBAL_Control
0x18018869a  mov     rcx, [rcx+10h]
0x18018869e  call    WPP_SF_dDD
0x1801886a3  mov     rbx, cs:qword_1801FCDF8
0x1801886aa  test    rbx, rbx
0x1801886ad  jnz     loc_18018874C
0x1801886b3  mov     rdi, cs:hModule
0x1801886ba  test    rdi, rdi
0x1801886bd  jnz     short loc_180188712
0x1801886bf  xor     edx, edx; hFile
0x1801886c1  mov     r8d, 800h; dwFlags
0x1801886c7  lea     rcx, aMfsvrDll; "mfsvr.dll"
0x1801886ce  call    cs:__imp_LoadLibraryExW
0x1801886d4  mov     rdi, rax
0x1801886d7  mov     rbx, cs:hModule
0x1801886de  test    rbx, rbx
0x1801886e1  jz      short loc_1801886FF
0x1801886e3  lea     rcx, [rbp+var_10]; this
0x1801886e7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1801886ec  mov     rcx, rbx; hLibModule
0x1801886ef  call    cs:__imp_FreeLibrary
0x1801886f5  lea     rcx, [rbp+var_10]; this
0x1801886f9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1801886fe  nop
0x1801886ff  mov     cs:hModule, rdi
0x180188706  mov     rbx, cs:qword_1801FCDF8
0x18018870d  test    rdi, rdi
0x180188710  jz      short loc_18018874C
0x180188712  lea     rdx, aMfcreatehdcpst; "MFCreateHDCPStatus"
0x180188719  mov     rcx, rdi; hModule
0x18018871c  call    cs:__imp_GetProcAddress
0x180188722  mov     rbx, rax
0x180188725  test    rax, rax
0x180188728  jz      short loc_180188745
0x18018872a  lea     rcx, qword_1801FCDF8
0x180188731  call    ?InternalRelease@?$ComPtr@UIMFMediaSource@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFMediaSource>::InternalRelease(void)
0x180188736  lea     rcx, qword_1801FCDF8
0x18018873d  mov     rax, rbx
0x180188740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188745  mov     rbx, cs:qword_1801FCDF8
0x18018874c  lea     r15, WPP_b5a5e24bc53137b87e8c3d8488016309_Traceguids
0x180188753  test    rbx, rbx
0x180188756  jnz     loc_180188868
0x18018875c  mov     ecx, 80004005h; this
0x180188761  call    ?OriginateError@MF@@YAJJ@Z; MF::OriginateError(long)
0x180188766  mov     edi, eax
0x180188768  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18018876f  test    rcx, rcx
0x180188772  jnz     short loc_1801887B2
0x180188774  lea     rcx, stru_1801FC290
0x18018877b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180188782  mov     rdx, cs:stru_1801FC290.__vftable
0x180188789  mov     rax, [rdx+8]
0x18018878d  mov     edx, 7F0h
0x180188792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188797  test    eax, eax
0x180188799  jnz     short loc_1801887AB
0x18018879b  lea     rcx, stru_1801F8A30
0x1801887a2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801887a9  jmp     short loc_1801887B2
0x1801887ab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801887b2  cmp     byte ptr [rcx+8], 0
0x1801887b6  jz      short loc_1801887E1
0x1801887b8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801887bd  test    edi, edi
0x1801887bf  jns     short loc_1801887E1
0x1801887c1  cmp     [rax+7CCh], edi
0x1801887c7  jz      short loc_1801887E1
0x1801887c9  mov     r9d, edi; int
0x1801887cc  mov     r8d, 186h; int
0x1801887d2  lea     rdx, aCheckhdcptypee; "CheckHDCPTypeEnforcementSupport"
0x1801887d9  mov     rcx, rax; this
0x1801887dc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801887e1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x1801887e8  jb      short loc_180188809
0x1801887ea  mov     edx, 21h ; '!'
0x1801887ef  mov     [rsp+60h+var_40], edi
0x1801887f3  xor     r9d, r9d
0x1801887f6  mov     r8, r15
0x1801887f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180188800  mov     rcx, [rcx+10h]
0x180188804  call    WPP_SF_qD
0x180188809  test    edi, edi
0x18018880b  jz      short loc_180188838
0x18018880d  mov     cs:dword_1801FD864, edi
0x180188813  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 2; MFWppLevels g_wppLevels
0x18018881a  jb      short loc_180188838
0x18018881c  mov     edx, 2Dh ; '-'
0x180188821  mov     r9d, edi
0x180188824  mov     r8, r15
0x180188827  mov     rcx, cs:WPP_GLOBAL_Control
0x18018882e  mov     rcx, [rcx+10h]
0x180188832  call    WPP_SF_d
0x180188837  nop
0x180188838  xor     ebx, ebx
0x18018883a  test    edi, edi
0x18018883c  setz    bl
0x18018883f  lea     rcx, [rbp+arg_0]; this
0x180188843  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180188848  nop
0x180188849  lea     rcx, [rbp+var_18]
0x18018884d  call    ?InternalRelease@?$ComPtr@UIMFMediaSource@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFMediaSource>::InternalRelease(void)
0x180188852  mov     eax, ebx
0x180188854  mov     rbx, [rsp+60h+arg_8]
0x18018885c  add     rsp, 60h
0x180188860  pop     r15
0x180188862  pop     r12
0x180188864  pop     rdi
0x180188865  pop     rsi
0x180188866  pop     rbp
0x180188867  retn
0x180188868  mov     rax, [rbx]
0x18018886b  mov     rdi, [rax]
0x18018886e  lea     rcx, [rbp+var_18]
0x180188872  call    ?InternalRelease@?$ComPtr@UIMFMediaSource@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFMediaSource>::InternalRelease(void)
0x180188877  lea     r8, [rbp+var_18]
0x18018887b  lea     rdx, _GUID_259aa8f0_b24f_4fa5_af7d_ae186354d071
0x180188882  mov     rcx, rbx
0x180188885  mov     rax, rdi
0x180188888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018888d  mov     edi, eax
0x18018888f  test    eax, eax
0x180188891  jns     loc_18018893D
0x180188897  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18018889e  test    rcx, rcx
0x1801888a1  jnz     short loc_1801888E1
0x1801888a3  lea     rcx, stru_1801FC290
0x1801888aa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801888b1  mov     rax, cs:stru_1801FC290.__vftable
0x1801888b8  mov     edx, 7F0h
0x1801888bd  mov     rax, [rax+8]
0x1801888c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801888c6  test    eax, eax
0x1801888c8  jnz     short loc_1801888DA
0x1801888ca  lea     rcx, stru_1801F8A30
0x1801888d1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801888d8  jmp     short loc_1801888E1
0x1801888da  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801888e1  cmp     byte ptr [rcx+8], 0
0x1801888e5  jz      short loc_18018890C
0x1801888e7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801888ec  cmp     [rax+7CCh], edi
0x1801888f2  jz      short loc_18018890C
0x1801888f4  mov     r9d, edi; int
0x1801888f7  mov     r8d, 187h; int
0x1801888fd  lea     rdx, aCheckhdcptypee; "CheckHDCPTypeEnforcementSupport"
0x180188904  mov     rcx, rax; this
0x180188907  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18018890c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180188913  jb      loc_18018880D
0x180188919  mov     edx, 22h ; '"'
0x18018891e  mov     [rsp+60h+var_40], edi
0x180188922  xor     r9d, r9d
0x180188925  mov     r8, r15
0x180188928  mov     rcx, cs:WPP_GLOBAL_Control
0x18018892f  mov     rcx, [rcx+10h]
0x180188933  call    WPP_SF_qD
0x180188938  jmp     loc_18018880D
0x18018893d  call    cs:__imp_GetTickCount
0x180188943  mov     ebx, eax
0x180188945  mov     rcx, cs:qword_1801FCDF8
0x18018894c  mov     rax, [rcx]
0x18018894f  lea     r8, [rbp+arg_10]
0x180188953  lea     rdx, [rbp+var_20]
0x180188957  mov     rax, [rax+18h]
0x18018895b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188960  mov     edi, eax
0x180188962  test    eax, eax
0x180188964  jns     loc_1801889F6
0x18018896a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180188971  test    rcx, rcx
0x180188974  jnz     short loc_1801889B4
0x180188976  lea     rcx, stru_1801FC290
0x18018897d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180188984  mov     rax, cs:stru_1801FC290.__vftable
0x18018898b  mov     edx, 7F0h
0x180188990  mov     rax, [rax+8]
0x180188994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188999  test    eax, eax
0x18018899b  jnz     short loc_1801889AD
0x18018899d  lea     rcx, stru_1801F8A30
0x1801889a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801889ab  jmp     short loc_1801889B4
0x1801889ad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801889b4  cmp     byte ptr [rcx+8], 0
0x1801889b8  jz      short loc_1801889DF
0x1801889ba  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801889bf  cmp     [rax+7CCh], edi
0x1801889c5  jz      short loc_1801889DF
0x1801889c7  mov     r9d, edi; int
0x1801889ca  mov     r8d, 18Ch; int
0x1801889d0  lea     rdx, aCheckhdcptypee; "CheckHDCPTypeEnforcementSupport"
0x1801889d7  mov     rcx, rax; this
0x1801889da  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801889df  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x1801889e6  jb      loc_18018880D
0x1801889ec  mov     edx, 23h ; '#'
0x1801889f1  jmp     loc_18018891E
0x1801889f6  mov     rcx, [rbp+var_18]
0x1801889fa  mov     rax, [rcx]
0x1801889fd  lea     rdx, [rbp+arg_18]
0x180188a01  mov     rax, [rax+20h]
0x180188a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188a0a  mov     edi, eax
0x180188a0c  test    eax, eax
0x180188a0e  jns     loc_180188AA0
0x180188a14  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180188a1b  test    rcx, rcx
0x180188a1e  jnz     short loc_180188A5E
0x180188a20  lea     rcx, stru_1801FC290
0x180188a27  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180188a2e  mov     rax, cs:stru_1801FC290.__vftable
0x180188a35  mov     edx, 7F0h
0x180188a3a  mov     rax, [rax+8]
0x180188a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188a43  test    eax, eax
0x180188a45  jnz     short loc_180188A57
0x180188a47  lea     rcx, stru_1801F8A30
0x180188a4e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180188a55  jmp     short loc_180188A5E
0x180188a57  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180188a5e  cmp     byte ptr [rcx+8], 0
0x180188a62  jz      short loc_180188A89
0x180188a64  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180188a69  cmp     [rax+7CCh], edi
0x180188a6f  jz      short loc_180188A89
0x180188a71  mov     r9d, edi; int
0x180188a74  mov     r8d, 18Dh; int
0x180188a7a  lea     rdx, aCheckhdcptypee; "CheckHDCPTypeEnforcementSupport"
0x180188a81  mov     rcx, rax; this
0x180188a84  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180188a89  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180188a90  jb      loc_18018880D
0x180188a96  mov     edx, 24h ; '$'
0x180188a9b  jmp     loc_18018891E
0x180188aa0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 2; MFWppLevels g_wppLevels
0x180188aa7  jb      short loc_180188AD3
0x180188aa9  mov     edx, 25h ; '%'
0x180188aae  mov     eax, [rbp+arg_10]
0x180188ab1  mov     [rsp+60h+var_38], eax
0x180188ab5  mov     eax, [rbp+arg_18]
0x180188ab8  mov     [rsp+60h+var_40], eax
0x180188abc  mov     r9d, [rbp+var_20]
0x180188ac0  mov     r8, r15
0x180188ac3  mov     rcx, cs:WPP_GLOBAL_Control
0x180188aca  mov     rcx, [rcx+10h]
0x180188ace  call    WPP_SF_DDD
0x180188ad3  cmp     [rbp+var_20], 2
0x180188ad7  jnz     short loc_180188B02
0x180188ad9  cmp     [rbp+arg_10], 0
0x180188add  jnz     short loc_180188B02
0x180188adf  test    esi, esi
0x180188ae1  jz      short loc_180188B44
0x180188ae3  sub     ebx, cs:dword_1801FD890
0x180188ae9  mov     cs:dword_1801FD860, ebx
0x180188aef  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 2; MFWppLevels g_wppLevels
0x180188af6  jb      short loc_180188B44
0x180188af8  mov     edx, 26h ; '&'
0x180188afd  mov     r9d, ebx
0x180188b00  jmp     short loc_180188B31
0x180188b02  test    esi, esi
0x180188b04  jnz     short loc_180188B44
0x180188b06  mov     rcx, [rbp+var_18]
0x180188b0a  mov     rax, [rcx]
0x180188b0d  lea     r8, qword_1801FD888
0x180188b14  lea     edx, [rsi+2]
0x180188b17  mov     rax, [rax+18h]
0x180188b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188b20  mov     edi, eax
0x180188b22  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 2; MFWppLevels g_wppLevels
0x180188b29  jb      short loc_180188B44
  ... truncated ...
```
