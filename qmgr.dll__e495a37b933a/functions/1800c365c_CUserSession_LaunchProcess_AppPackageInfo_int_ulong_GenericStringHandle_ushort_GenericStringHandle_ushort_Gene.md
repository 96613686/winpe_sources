# CUserSession::LaunchProcess(AppPackageInfo *,int,ulong,GenericStringHandle<ushort>,GenericStringHandle<ushort>,GenericStringHandle<ushort>,ulong *)

- ea: `0x1800c365c`
- end: `0x1800c3c02`
- name: `?LaunchProcess@CUserSession@@QEAAJPEAUAppPackageInfo@@HKV?$GenericStringHandle@G@@11PEAK@Z`
- size: `1446`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned int, int, _DWORD *, __int64, unsigned __int16 **, LPDWORD lpExitCode)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800765dc`

## callees

- `0x180006640`
- `0x180008b70`
- `0x18000f5f0`
- `0x180014310`
- `0x18001a6fc`
- `0x18001d7f0`
- `0x18001d830`
- `0x18005579c`
- `0x18009e9c8`
- `0x1800a3de8`
- `0x1800b1160`
- `0x1800c365c`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800c3a51`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800c3a51`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800c3926`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800c3926`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c384d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c385f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3930`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c393a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3942`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c39dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c39e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c39ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3a5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3a65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3a6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c384d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c385f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3930`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c393a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3942`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c39dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c39e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c39ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3a5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3a65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3a6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c3adc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c3af0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c3adc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c3af0`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800c39c9`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800c39c9`
- `USERENV!DestroyEnvironmentBlock` at `0x1800c3ac8`
- `USERENV!DestroyEnvironmentBlock` at `0x1800c3ac8`
- `USERENV!CreateEnvironmentBlock` at `0x1800c3843`
- `USERENV!CreateEnvironmentBlock` at `0x1800c3843`

## pseudocode

```c
__int64 __fastcall CUserSession::LaunchProcess(
        _QWORD *a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        _DWORD *a5,
        __int64 a6,
        unsigned __int16 **a7,
        LPDWORD lpExitCode)
{
  char v12; // al
  WCHAR *lpDesktop; // rcx
  unsigned __int16 **v14; // r15
  int v15; // eax
  __int64 v16; // rsi
  unsigned __int16 *v17; // rax
  WCHAR *v18; // rbx
  __int64 v19; // rdi
  unsigned int LastError; // eax
  unsigned int v21; // eax
  DWORD v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  __int64 result; // rax
  const ComError *v26; // rbx
  LPVOID Environment; // [rsp+60h] [rbp-388h] BYREF
  unsigned __int16 *v28; // [rsp+68h] [rbp-380h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-378h] BYREF
  const ComError *v30; // [rsp+88h] [rbp-360h] BYREF
  __int64 v31; // [rsp+90h] [rbp-358h] BYREF
  volatile signed __int32 *v32; // [rsp+98h] [rbp-350h]
  HANDLE Handles[4]; // [rsp+A0h] [rbp-348h] BYREF
  void **pExceptionObject; // [rsp+C0h] [rbp-328h] BYREF
  __int128 v35; // [rsp+C8h] [rbp-320h]
  int v36; // [rsp+D8h] [rbp-310h]
  int v37; // [rsp+DCh] [rbp-30Ch]
  int v38; // [rsp+E0h] [rbp-308h]
  void **v39; // [rsp+120h] [rbp-2C8h] BYREF
  __int128 v40; // [rsp+128h] [rbp-2C0h]
  unsigned int v41; // [rsp+138h] [rbp-2B0h]
  int v42; // [rsp+13Ch] [rbp-2ACh]
  int v43; // [rsp+140h] [rbp-2A8h]
  void **v44; // [rsp+180h] [rbp-268h] BYREF
  __int128 v45; // [rsp+188h] [rbp-260h]
  unsigned int v46; // [rsp+198h] [rbp-250h]
  int v47; // [rsp+19Ch] [rbp-24Ch]
  int v48; // [rsp+1A0h] [rbp-248h]
  void **v49; // [rsp+1E0h] [rbp-208h] BYREF
  __int128 v50; // [rsp+1E8h] [rbp-200h]
  unsigned int v51; // [rsp+1F8h] [rbp-1F0h]
  int v52; // [rsp+1FCh] [rbp-1ECh]
  int v53; // [rsp+200h] [rbp-1E8h]
  void **v54; // [rsp+240h] [rbp-1A8h] BYREF
  __int128 v55; // [rsp+248h] [rbp-1A0h]
  unsigned int v56; // [rsp+258h] [rbp-190h]
  int v57; // [rsp+25Ch] [rbp-18Ch]
  int v58; // [rsp+260h] [rbp-188h]
  void **v59; // [rsp+2A0h] [rbp-148h] BYREF
  __int128 v60; // [rsp+2A8h] [rbp-140h]
  int v61; // [rsp+2B8h] [rbp-130h]
  int v62; // [rsp+2BCh] [rbp-12Ch]
  int v63; // [rsp+2C0h] [rbp-128h]
  struct _STARTUPINFOW StartupInfo; // [rsp+300h] [rbp-E8h] BYREF
  _BYTE v65[120]; // [rsp+370h] [rbp-78h] BYREF
  _DWORD *v66; // [rsp+3F0h] [rbp+8h] BYREF

  Environment = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  try
  {
    StartupInfo.cb = 104;
    v12 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
    lpDesktop = L"winsta0\\default";
    if ( !v12 )
      lpDesktop = StartupInfo.lpDesktop;
    StartupInfo.lpDesktop = lpDesktop;
    v66 = operator new(0x10u);
    v66[2] = 1;
    *(_QWORD *)v66 = 0;
    v14 = a7;
    _InterlockedAdd((volatile signed __int32 *)*a7 + 2, 1u);
    v28 = *v14;
    v31 = a1[5];
    v32 = (volatile signed __int32 *)a1[6];
    _InterlockedAdd(v32, 1u);
    v15 = CJobManager::CloneUserToken(g_Manager, &v31, a2, a3, a4, 0, &v28, &v66);
    if ( v15 < 0 )
    {
      v35 = 0;
      pExceptionObject = &ComError::`vftable';
      v36 = v15;
      v37 = 1734;
      v38 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v16 = a6;
    v17 = CopyString((const unsigned __int16 *)(*(_QWORD *)a6 + 12LL), 0xFFFFFFFFFFFFFFFFuLL);
    v18 = v17;
    v28 = v17;
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      v19 = (__int64)a5;
    }
    else
    {
      v19 = (__int64)a5;
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        95,
        (unsigned int)&WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids,
        *a5 + 12,
        (__int64)v17);
    }
    if ( !CreateEnvironmentBlock(&Environment, *(HANDLE *)v66, 0) )
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0x80070000;
      else
        LastError = GetLastError();
      v40 = 0;
      v39 = &ComError::`vftable';
      v41 = LastError;
      v42 = 1748;
      v43 = 1;
      throw (ComError *)&v39;
    }
    CNestedImpersonation::CNestedImpersonation((CNestedImpersonation *)v65, (const struct TokenHandle *)&v66);
    if ( !CreateProcessAsUserW(
            *(HANDLE *)v66,
            (LPCWSTR)(*(_QWORD *)v19 + 12LL),
            v18,
            0,
            0,
            0,
            0x420u,
            Environment,
            0,
            &StartupInfo,
            &ProcessInformation) )
    {
      if ( (int)GetLastError() > 0 )
        v21 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v21 = GetLastError();
      v45 = 0;
      v44 = &ComError::`vftable';
      v46 = v21;
      v47 = 1771;
      v48 = 1;
      throw (ComError *)&v44;
    }
    Handles[0] = ProcessInformation.hProcess;
    Handles[1] = g_hServiceStopEvent;
    v22 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    if ( v22 == 1 )
    {
      v60 = 0;
      v59 = &ComError::`vftable';
      v61 = -2147467259;
      v62 = 1785;
      v63 = 1;
      throw (ComError *)&v59;
    }
    if ( v22 == -1 )
    {
      if ( (int)GetLastError() > 0 )
        v23 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v23 = GetLastError();
      v50 = 0;
      v49 = &ComError::`vftable';
      v51 = v23;
      v52 = 1788;
      v53 = 1;
      throw (ComError *)&v49;
    }
    if ( !GetExitCodeProcess(ProcessInformation.hProcess, lpExitCode) )
    {
      if ( (int)GetLastError() > 0 )
        v24 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v24 = GetLastError();
      v55 = 0;
      v54 = &ComError::`vftable';
      v56 = v24;
      v57 = 1797;
      v58 = 1;
      throw (ComError *)&v54;
    }
    DestroyEnvironmentBlock(Environment);
    Environment = 0;
    CloseHandle(ProcessInformation.hThread);
    ProcessInformation.hThread = 0;
    CloseHandle(ProcessInformation.hProcess);
    ProcessInformation.hProcess = 0;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        96,
        &WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids,
        ProcessInformation.dwProcessId);
    CNestedImpersonation::~CNestedImpersonation((CNestedImpersonation *)v65);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v28);
    TokenHandle::Decrement((TokenHandle *)&v66);
    GenericStringHandle<unsigned short>::FreeIt(v19);
    GenericStringHandle<unsigned short>::FreeIt(v16);
    GenericStringHandle<unsigned short>::FreeIt(v14);
    result = 0;
  }
  catch ( const ComError *v30 )
  {
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      v26 = v30;
    }
    else
    {
      v26 = v30;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        97,
        &WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids,
        *((unsigned int *)v30 + 6));
    }
    if ( Environment )
      DestroyEnvironmentBlock(Environment);
    if ( ProcessInformation.hThread )
    {
      CloseHandle(ProcessInformation.hThread);
      ProcessInformation.hThread = 0;
    }
    if ( ProcessInformation.hProcess )
    {
      CloseHandle(ProcessInformation.hProcess);
      ProcessInformation.hProcess = 0;
    }
    LODWORD(v66) = *((_DWORD *)v26 + 6);
    GenericStringHandle<unsigned short>::FreeIt(a5);
    GenericStringHandle<unsigned short>::FreeIt(a6);
    GenericStringHandle<unsigned short>::FreeIt(a7);
    return (unsigned int)v66;
  }
  StartupInfo.cb = 104;
}

```

## disassembly

```asm
0x1800c365c  push    rbx
0x1800c365e  push    rsi
0x1800c365f  push    rdi
0x1800c3660  push    r13
0x1800c3662  push    r14
0x1800c3664  push    r15
0x1800c3666  sub     rsp, 3B8h
0x1800c366d  mov     edi, r9d
0x1800c3670  mov     esi, r8d
0x1800c3673  mov     r14, rdx
0x1800c3676  mov     rbx, rcx
0x1800c3679  mov     [rsp+3E8h+Environment], 0
0x1800c3682  xorps   xmm0, xmm0
0x1800c3685  xor     eax, eax
0x1800c3687  movups  xmmword ptr [rsp+3E8h+ProcessInformation.hProcess], xmm0
0x1800c368c  mov     qword ptr [rsp+3E8h+ProcessInformation.dwProcessId], rax
0x1800c3694  xor     edx, edx; Val
0x1800c3696  lea     r8d, [rax+64h]; Size
0x1800c369a  lea     rcx, [rsp+3E8h+StartupInfo+4]; void *
0x1800c36a2  call    memset_0
0x1800c36a7  mov     [rsp+3E8h+StartupInfo.cb], 68h ; 'h'
0x1800c36b2  mov     rax, [rbx]
0x1800c36b5  mov     rcx, rbx
0x1800c36b8  mov     rax, [rax+8]
0x1800c36bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c36c1  lea     rcx, aWinsta0Default; "winsta0\\default"
0x1800c36c8  test    al, al
0x1800c36ca  cmovz   rcx, [rsp+3E8h+StartupInfo.lpDesktop]
0x1800c36d3  mov     [rsp+3E8h+StartupInfo.lpDesktop], rcx
0x1800c36db  mov     ecx, 10h; dwBytes
0x1800c36e0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c36e5  mov     [rsp+3E8h+arg_0], rax
0x1800c36ed  mov     r13d, 1
0x1800c36f3  mov     [rax+8], r13d
0x1800c36f7  mov     rax, [rsp+3E8h+arg_0]
0x1800c36ff  mov     qword ptr [rax], 0
0x1800c3706  mov     r15, [rsp+3E8h+arg_30]
0x1800c370e  mov     rax, [r15]
0x1800c3711  lock add [rax+8], r13d
0x1800c3716  mov     rax, [r15]
0x1800c3719  mov     [rsp+3E8h+var_380], rax
0x1800c371e  mov     rax, [rbx+28h]
0x1800c3722  mov     [rsp+3E8h+var_358], rax
0x1800c372a  mov     rax, [rbx+30h]
0x1800c372e  mov     [rsp+3E8h+var_350], rax
0x1800c3736  lock add [rax], r13d
0x1800c373a  lea     rax, [rsp+3E8h+arg_0]
0x1800c3742  mov     [rsp+3E8h+lpEnvironment], rax
0x1800c3747  lea     rax, [rsp+3E8h+var_380]
0x1800c374c  mov     qword ptr [rsp+3E8h+dwCreationFlags], rax
0x1800c3751  mov     qword ptr [rsp+3E8h+bInheritHandles], 0
0x1800c375a  mov     dword ptr [rsp+3E8h+lpThreadAttributes], edi
0x1800c375e  mov     r9d, esi
0x1800c3761  mov     r8, r14
0x1800c3764  lea     rdx, [rsp+3E8h+var_358]
0x1800c376c  mov     rcx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x1800c3773  call    ?CloneUserToken@CJobManager@@QEAAJVSidHandle@@PEAUAppPackageInfo@@HKPEA_KV?$GenericStringHandle@G@@PEAVTokenHandle@@@Z; CJobManager::CloneUserToken(SidHandle,AppPackageInfo *,int,ulong,unsigned __int64 *,GenericStringHandle<ushort>,TokenHandle *)
0x1800c3778  test    eax, eax
0x1800c377a  jns     short loc_1800C37C4
0x1800c377c  xorps   xmm0, xmm0
0x1800c377f  movups  [rsp+3E8h+var_320], xmm0
0x1800c3787  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800c378e  mov     [rsp+3E8h+pExceptionObject], rcx
0x1800c3796  mov     [rsp+3E8h+var_310], eax
0x1800c379d  mov     [rsp+3E8h+var_30C], 6C6h
0x1800c37a8  mov     [rsp+3E8h+var_308], r13d
0x1800c37b0  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800c37b7  lea     rcx, [rsp+3E8h+pExceptionObject]; pExceptionObject
0x1800c37bf  call    _CxxThrowException_0
0x1800c37c4  mov     rsi, [rsp+3E8h+arg_28]
0x1800c37cc  mov     rcx, [rsi]
0x1800c37cf  add     rcx, 0Ch; unsigned __int16 *
0x1800c37d3  or      rdx, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x1800c37d7  call    ?CopyString@@YAPEAGPEBG_K@Z; CopyString(ushort const *,unsigned __int64)
0x1800c37dc  mov     rbx, rax
0x1800c37df  mov     [rsp+3E8h+var_380], rax
0x1800c37e4  lea     r14, WPP_GLOBAL_Control
0x1800c37eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c37f2  cmp     rcx, r14
0x1800c37f5  jz      short loc_1800C3828
0x1800c37f7  test    [rcx+1Ch], r13b
0x1800c37fb  jz      short loc_1800C3828
0x1800c37fd  mov     rdi, [rsp+3E8h+arg_20]
0x1800c3805  mov     r9, [rdi]
0x1800c3808  add     r9, 0Ch
0x1800c380c  mov     edx, 5Fh ; '_'
0x1800c3811  mov     [rsp+3E8h+lpThreadAttributes], rax
0x1800c3816  lea     r8, WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids
0x1800c381d  mov     rcx, [rcx+10h]
0x1800c3821  call    WPP_SF_SS
0x1800c3826  jmp     short loc_1800C3830
0x1800c3828  mov     rdi, [rsp+3E8h+arg_20]
0x1800c3830  xor     r8d, r8d; bInherit
0x1800c3833  mov     rdx, [rsp+3E8h+arg_0]
0x1800c383b  mov     rdx, [rdx]; hToken
0x1800c383e  lea     rcx, [rsp+3E8h+Environment]; lpEnvironment
0x1800c3843  call    cs:__imp_CreateEnvironmentBlock
0x1800c3849  test    eax, eax
0x1800c384b  jnz     short loc_1800C38B5
0x1800c384d  call    cs:__imp_GetLastError
0x1800c3853  test    eax, eax
0x1800c3855  jg      short loc_1800C385F
0x1800c3857  call    cs:__imp_GetLastError
0x1800c385d  jmp     short loc_1800C386D
0x1800c385f  call    cs:__imp_GetLastError
0x1800c3865  movzx   eax, ax
0x1800c3868  or      eax, 80070000h
0x1800c386d  xorps   xmm0, xmm0
0x1800c3870  movups  [rsp+3E8h+var_2C0], xmm0
0x1800c3878  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800c387f  mov     [rsp+3E8h+var_2C8], rcx
0x1800c3887  mov     [rsp+3E8h+var_2B0], eax
0x1800c388e  mov     [rsp+3E8h+var_2AC], 6D4h
0x1800c3899  mov     [rsp+3E8h+var_2A8], r13d
0x1800c38a1  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800c38a8  lea     rcx, [rsp+3E8h+var_2C8]; pExceptionObject
0x1800c38b0  call    _CxxThrowException_0
0x1800c38b5  lea     rdx, [rsp+3E8h+arg_0]; struct TokenHandle *
0x1800c38bd  lea     rcx, [rsp+3E8h+var_78]; this
0x1800c38c5  call    ??0CNestedImpersonation@@QEAA@AEBVTokenHandle@@@Z; CNestedImpersonation::CNestedImpersonation(TokenHandle const &)
0x1800c38ca  nop
0x1800c38cb  mov     rax, [rsp+3E8h+Environment]
0x1800c38d0  mov     rdx, [rdi]
0x1800c38d3  add     rdx, 0Ch; lpApplicationName
0x1800c38d7  lea     rcx, [rsp+3E8h+ProcessInformation]
0x1800c38dc  mov     [rsp+3E8h+lpProcessInformation], rcx; lpProcessInformation
0x1800c38e1  lea     rcx, [rsp+3E8h+StartupInfo]
0x1800c38e9  mov     [rsp+3E8h+lpStartupInfo], rcx; lpStartupInfo
0x1800c38ee  mov     [rsp+3E8h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1800c38f7  mov     [rsp+3E8h+lpEnvironment], rax; lpEnvironment
0x1800c38fc  mov     [rsp+3E8h+dwCreationFlags], 420h; dwCreationFlags
0x1800c3904  mov     [rsp+3E8h+bInheritHandles], 0; bInheritHandles
0x1800c390c  mov     [rsp+3E8h+lpThreadAttributes], 0; lpThreadAttributes
0x1800c3915  xor     r9d, r9d; lpProcessAttributes
0x1800c3918  mov     r8, rbx; lpCommandLine
0x1800c391b  mov     rcx, [rsp+3E8h+arg_0]
0x1800c3923  mov     rcx, [rcx]; hToken
0x1800c3926  call    cs:__imp_CreateProcessAsUserW
0x1800c392c  test    eax, eax
0x1800c392e  jnz     short loc_1800C3998
0x1800c3930  call    cs:__imp_GetLastError
0x1800c3936  test    eax, eax
0x1800c3938  jg      short loc_1800C3942
0x1800c393a  call    cs:__imp_GetLastError
0x1800c3940  jmp     short loc_1800C3950
0x1800c3942  call    cs:__imp_GetLastError
0x1800c3948  movzx   eax, ax
0x1800c394b  or      eax, 80070000h
0x1800c3950  xorps   xmm0, xmm0
0x1800c3953  movups  [rsp+3E8h+var_260], xmm0
0x1800c395b  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800c3962  mov     [rsp+3E8h+var_268], rcx
0x1800c396a  mov     [rsp+3E8h+var_250], eax
0x1800c3971  mov     [rsp+3E8h+var_24C], 6EBh
0x1800c397c  mov     [rsp+3E8h+var_248], r13d
0x1800c3984  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800c398b  lea     rcx, [rsp+3E8h+var_268]; pExceptionObject
0x1800c3993  call    _CxxThrowException_0
0x1800c3998  mov     rax, [rsp+3E8h+ProcessInformation.hProcess]
0x1800c399d  mov     [rsp+3E8h+Handles], rax
0x1800c39a5  mov     rax, cs:?g_hServiceStopEvent@@3V?$auto_HANDLE@$0A@@@A; auto_HANDLE<0> g_hServiceStopEvent
0x1800c39ac  mov     [rsp+3E8h+var_340], rax
0x1800c39b4  or      ebx, 0FFFFFFFFh
0x1800c39b7  mov     r9d, ebx; dwMilliseconds
0x1800c39ba  xor     r8d, r8d; bWaitAll
0x1800c39bd  lea     rdx, [rsp+3E8h+Handles]; lpHandles
0x1800c39c5  lea     ecx, [r8+2]; nCount
0x1800c39c9  call    cs:__imp_WaitForMultipleObjects
0x1800c39cf  cmp     eax, r13d
0x1800c39d2  jz      loc_1800C3B74
0x1800c39d8  cmp     eax, ebx
0x1800c39da  jnz     short loc_1800C3A44
0x1800c39dc  call    cs:__imp_GetLastError
0x1800c39e2  test    eax, eax
0x1800c39e4  jg      short loc_1800C39EE
0x1800c39e6  call    cs:__imp_GetLastError
0x1800c39ec  jmp     short loc_1800C39FC
0x1800c39ee  call    cs:__imp_GetLastError
0x1800c39f4  movzx   eax, ax
0x1800c39f7  or      eax, 80070000h
0x1800c39fc  xorps   xmm0, xmm0
0x1800c39ff  movups  [rsp+3E8h+var_200], xmm0
0x1800c3a07  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800c3a0e  mov     [rsp+3E8h+var_208], rcx
0x1800c3a16  mov     [rsp+3E8h+var_1F0], eax
0x1800c3a1d  mov     [rsp+3E8h+var_1EC], 6FCh
0x1800c3a28  mov     [rsp+3E8h+var_1E8], r13d
0x1800c3a30  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800c3a37  lea     rcx, [rsp+3E8h+var_208]; pExceptionObject
0x1800c3a3f  call    _CxxThrowException_0
0x1800c3a44  mov     rdx, [rsp+3E8h+lpExitCode]; lpExitCode
0x1800c3a4c  mov     rcx, [rsp+3E8h+ProcessInformation.hProcess]; hProcess
0x1800c3a51  call    cs:__imp_GetExitCodeProcess
0x1800c3a57  test    eax, eax
0x1800c3a59  jnz     short loc_1800C3AC3
0x1800c3a5b  call    cs:__imp_GetLastError
0x1800c3a61  test    eax, eax
0x1800c3a63  jg      short loc_1800C3A6D
0x1800c3a65  call    cs:__imp_GetLastError
0x1800c3a6b  jmp     short loc_1800C3A7B
0x1800c3a6d  call    cs:__imp_GetLastError
0x1800c3a73  movzx   eax, ax
0x1800c3a76  or      eax, 80070000h
0x1800c3a7b  xorps   xmm0, xmm0
0x1800c3a7e  movups  [rsp+3E8h+var_1A0], xmm0
0x1800c3a86  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800c3a8d  mov     [rsp+3E8h+var_1A8], rcx
0x1800c3a95  mov     [rsp+3E8h+var_190], eax
0x1800c3a9c  mov     [rsp+3E8h+var_18C], 705h
0x1800c3aa7  mov     [rsp+3E8h+var_188], r13d
0x1800c3aaf  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800c3ab6  lea     rcx, [rsp+3E8h+var_1A8]; pExceptionObject
0x1800c3abe  call    _CxxThrowException_0
0x1800c3ac3  mov     rcx, [rsp+3E8h+Environment]; lpEnvironment
0x1800c3ac8  call    cs:__imp_DestroyEnvironmentBlock
0x1800c3ace  mov     [rsp+3E8h+Environment], 0
0x1800c3ad7  mov     rcx, [rsp+3E8h+ProcessInformation.hThread]; hObject
0x1800c3adc  call    cs:__imp_CloseHandle
0x1800c3ae2  mov     [rsp+3E8h+ProcessInformation.hThread], 0
0x1800c3aeb  mov     rcx, [rsp+3E8h+ProcessInformation.hProcess]; hObject
0x1800c3af0  call    cs:__imp_CloseHandle
0x1800c3af6  mov     [rsp+3E8h+ProcessInformation.hProcess], 0
0x1800c3aff  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3b06  cmp     rcx, r14
0x1800c3b09  jz      short loc_1800C3B2F
0x1800c3b0b  test    [rcx+1Ch], r13b
0x1800c3b0f  jz      short loc_1800C3B2F
0x1800c3b11  mov     edx, 60h ; '`'
0x1800c3b16  mov     r9d, [rsp+3E8h+ProcessInformation.dwProcessId]
0x1800c3b1e  lea     r8, WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids
0x1800c3b25  mov     rcx, [rcx+10h]
0x1800c3b29  call    WPP_SF_d
0x1800c3b2e  nop
0x1800c3b2f  lea     rcx, [rsp+3E8h+var_78]; this
0x1800c3b37  call    ??1CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::~CNestedImpersonation(void)
0x1800c3b3c  nop
0x1800c3b3d  lea     rcx, [rsp+3E8h+var_380]; void *
0x1800c3b42  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800c3b47  nop
0x1800c3b48  lea     rcx, [rsp+3E8h+arg_0]; this
0x1800c3b50  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x1800c3b55  nop
0x1800c3b56  mov     rcx, rdi
0x1800c3b59  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x1800c3b5e  nop
0x1800c3b5f  mov     rcx, rsi
0x1800c3b62  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x1800c3b67  nop
0x1800c3b68  mov     rcx, r15
0x1800c3b6b  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x1800c3b70  xor     eax, eax
0x1800c3b72  jmp     short loc_1800C3BF1
0x1800c3b74  xorps   xmm0, xmm0
0x1800c3b77  movups  [rsp+3E8h+var_140], xmm0
0x1800c3b7f  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800c3b86  mov     [rsp+3E8h+var_148], rcx
0x1800c3b8e  mov     [rsp+3E8h+var_130], 80004005h
0x1800c3b99  mov     [rsp+3E8h+var_12C], 6F9h
0x1800c3ba4  mov     [rsp+3E8h+var_128], r13d
0x1800c3bac  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800c3bb3  lea     rcx, [rsp+3E8h+var_148]; pExceptionObject
0x1800c3bbb  call    _CxxThrowException_0
0x1800c3bc1  mov     rcx, [rsp+3E8h+arg_20]
0x1800c3bc9  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x1800c3bce  nop
0x1800c3bcf  mov     rcx, [rsp+3E8h+arg_28]
0x1800c3bd7  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x1800c3bdc  nop
0x1800c3bdd  mov     rcx, [rsp+3E8h+arg_30]
0x1800c3be5  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x1800c3bea  mov     eax, dword ptr [rsp+3E8h+arg_0]
0x1800c3bf1  add     rsp, 3B8h
0x1800c3bf8  pop     r15
0x1800c3bfa  pop     r14
0x1800c3bfc  pop     r13
0x1800c3bfe  pop     rdi
0x1800c3bff  pop     rsi
0x1800c3c00  pop     rbx
0x1800c3c01  retn
```
