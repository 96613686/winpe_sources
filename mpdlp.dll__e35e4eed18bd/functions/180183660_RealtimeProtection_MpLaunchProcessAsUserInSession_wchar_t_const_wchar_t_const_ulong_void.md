# RealtimeProtection::MpLaunchProcessAsUserInSession(wchar_t const *,wchar_t const *,ulong,void * *)

- ea: `0x180183660`
- end: `0x180183927`
- name: `?MpLaunchProcessAsUserInSession@RealtimeProtection@@YAJPEB_W0KPEAPEAX@Z`
- size: `711`
- prototype: `__int64 __fastcall(wchar_t **this, const wchar_t *, const wchar_t *, unsigned int, void **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801f66e4`
- `0x18022bc00`

## callees

- `0x18007f2f8`
- `0x1800809d0`
- `0x1800c8f68`
- `0x180104674`
- `0x180106620`
- `0x18010cb40`
- `0x18010ce3c`
- `0x180183660`
- `0x18023a310`

## import_xrefs

- `MpClient!MpFreeMemory` at `0x1801836e2`
- `MpClient!MpFreeMemory` at `0x18018375c`
- `MpClient!MpFreeMemory` at `0x1801838a8`
- `MpClient!MpFreeMemory` at `0x180183903`
- `MpClient!MpFreeMemory` at `0x1801836e2`
- `MpClient!MpFreeMemory` at `0x18018375c`
- `MpClient!MpFreeMemory` at `0x1801838a8`
- `MpClient!MpFreeMemory` at `0x180183903`
- `KERNEL32!CloseHandle` at `0x1801837bf`
- `KERNEL32!CloseHandle` at `0x18018388d`
- `KERNEL32!CloseHandle` at `0x1801838e8`
- `KERNEL32!CloseHandle` at `0x1801837bf`
- `KERNEL32!CloseHandle` at `0x18018388d`
- `KERNEL32!CloseHandle` at `0x1801838e8`
- `ADVAPI32!CreateProcessAsUserW` at `0x18018383e`
- `ADVAPI32!CreateProcessAsUserW` at `0x18018383e`
- `WTSAPI32!WTSQueryUserToken` at `0x180183773`
- `WTSAPI32!WTSQueryUserToken` at `0x180183773`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::MpLaunchProcessAsUserInSession(
        wchar_t **this,
        const wchar_t *a2,
        const wchar_t *a3,
        HANDLE *a4)
{
  ULONG v6; // esi
  int MpFileFullNameFromService; // eax
  unsigned int v8; // ebx
  wchar_t *v10; // rbx
  int v11; // eax
  const struct std::nothrow_t *v12; // rdx
  unsigned int v13; // edi
  unsigned int LastError; // eax
  LPWSTR v15; // rdi
  void *v16; // rdx
  int v17; // esi
  wchar_t *v18; // [rsp+60h] [rbp-A0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-98h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  void *phToken; // [rsp+F0h] [rbp-10h] BYREF
  LPWSTR lpCommandLine; // [rsp+F8h] [rbp-8h] BYREF

  v18 = 0;
  v6 = (unsigned int)a3;
  MpFileFullNameFromService = MpConfigUtils::GetMpFileFullNameFromService((MpConfigUtils *)&v18, this, a3, (bool)a4);
  v8 = MpFileFullNameFromService;
  if ( MpFileFullNameFromService < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids,
        (unsigned int)MpFileFullNameFromService);
    if ( v18 )
      MpFreeMemory(v18);
    return v8;
  }
  v10 = v18;
  lpCommandLine = 0;
  v11 = CommonUtil::NewSprintfW((CommonUtil *)&lpCommandLine, (wchar_t **)L"\"%ls\" %ls", v18, a2);
  v13 = v11;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        51,
        WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids,
        (unsigned int)v11);
LABEL_12:
    if ( lpCommandLine )
      operator delete(lpCommandLine, v12);
    if ( v10 )
      MpFreeMemory(v10);
    return v13;
  }
  phToken = 0;
  if ( !WTSQueryUserToken(v6, &phToken) )
  {
    LastError = HrGetLastError();
    v13 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids, LastError);
    if ( phToken )
      CloseHandle(phToken);
    goto LABEL_12;
  }
  memset(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.lpDesktop = L"winsta0\\default";
  StartupInfo.cb = 104;
  v15 = lpCommandLine;
  StartupInfo.wShowWindow = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( CreateProcessAsUserW(phToken, 0, lpCommandLine, 0, 0, 0, 0x1000428u, 0, 0, &StartupInfo, &ProcessInformation)
    || (v17 = HrGetLastError(), v17 >= 0) )
  {
    if ( ProcessInformation.hThread )
      CommonUtil::UtilCloseHandle((CommonUtil *)ProcessInformation.hThread, v16);
    if ( a4 )
    {
      *a4 = ProcessInformation.hProcess;
    }
    else if ( ProcessInformation.hProcess )
    {
      CommonUtil::UtilCloseHandle((CommonUtil *)ProcessInformation.hProcess, v16);
    }
    if ( phToken )
      CloseHandle(phToken);
    if ( v15 )
      operator delete(v15, (const struct std::nothrow_t *)v16);
    if ( v10 )
      MpFreeMemory(v10);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids,
        (unsigned int)v17);
    if ( phToken )
      CloseHandle(phToken);
    if ( v15 )
      operator delete(v15, (const struct std::nothrow_t *)v16);
    if ( v10 )
      MpFreeMemory(v10);
    return (unsigned int)v17;
  }
}

```

## disassembly

```asm
0x180183660  push    rbp
0x180183662  push    rbx
0x180183663  push    rsi
0x180183664  push    rdi
0x180183665  push    r14
0x180183667  push    r15
0x180183669  lea     rbp, [rsp-18h]
0x18018366e  sub     rsp, 118h
0x180183675  mov     rax, cs:__security_cookie
0x18018367c  xor     rax, rsp
0x18018367f  mov     [rbp+40h+var_40], rax
0x180183683  mov     rdi, rdx
0x180183686  xor     r15d, r15d
0x180183689  mov     rdx, rcx; wchar_t **
0x18018368c  mov     [rsp+140h+var_E0], r15
0x180183691  lea     rcx, [rsp+140h+var_E0]; this
0x180183696  mov     r14, r9
0x180183699  mov     esi, r8d
0x18018369c  call    ?GetMpFileFullNameFromService@MpConfigUtils@@YAJPEAPEA_WPEB_W_N@Z; MpConfigUtils::GetMpFileFullNameFromService(wchar_t * *,wchar_t const *,bool)
0x1801836a1  mov     ebx, eax
0x1801836a3  test    eax, eax
0x1801836a5  jns     short loc_1801836EF
0x1801836a7  mov     r10, cs:WPP_GLOBAL_Control
0x1801836ae  lea     rcx, WPP_GLOBAL_Control
0x1801836b5  cmp     r10, rcx
0x1801836b8  jz      short loc_1801836D8
0x1801836ba  test    byte ptr [r10+1Ch], 1
0x1801836bf  jz      short loc_1801836D8
0x1801836c1  mov     rcx, [r10+10h]
0x1801836c5  lea     edx, [r15+32h]
0x1801836c9  mov     r9d, eax
0x1801836cc  lea     r8, WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids
0x1801836d3  call    WPP_SF_d
0x1801836d8  mov     rcx, [rsp+140h+var_E0]
0x1801836dd  test    rcx, rcx
0x1801836e0  jz      short loc_1801836E8
0x1801836e2  call    cs:__imp_MpFreeMemory
0x1801836e8  mov     eax, ebx
0x1801836ea  jmp     loc_18018390B
0x1801836ef  mov     rbx, [rsp+140h+var_E0]
0x1801836f4  lea     rdx, aLsLs; "\"%ls\" %ls"
0x1801836fb  mov     r8, rbx; wchar_t *
0x1801836fe  mov     [rbp+40h+lpCommandLine], r15
0x180183702  mov     r9, rdi
0x180183705  lea     rcx, [rbp+40h+lpCommandLine]; this
0x180183709  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x18018370e  mov     edi, eax
0x180183710  test    eax, eax
0x180183712  jns     short loc_180183769
0x180183714  mov     r10, cs:WPP_GLOBAL_Control
0x18018371b  lea     rcx, WPP_GLOBAL_Control
0x180183722  cmp     r10, rcx
0x180183725  jz      short loc_180183746
0x180183727  test    byte ptr [r10+1Ch], 1
0x18018372c  jz      short loc_180183746
0x18018372e  mov     rcx, [r10+10h]
0x180183732  lea     r8, WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids
0x180183739  mov     edx, 33h ; '3'
0x18018373e  mov     r9d, eax
0x180183741  call    WPP_SF_d
0x180183746  mov     rcx, [rbp+40h+lpCommandLine]; void *
0x18018374a  test    rcx, rcx
0x18018374d  jz      short loc_180183754
0x18018374f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180183754  test    rbx, rbx
0x180183757  jz      short loc_180183762
0x180183759  mov     rcx, rbx
0x18018375c  call    cs:__imp_MpFreeMemory
0x180183762  mov     eax, edi
0x180183764  jmp     loc_18018390B
0x180183769  lea     rdx, [rbp+40h+phToken]; phToken
0x18018376d  mov     [rbp+40h+phToken], r15
0x180183771  mov     ecx, esi; SessionId
0x180183773  call    cs:__imp_WTSQueryUserToken
0x180183779  test    eax, eax
0x18018377b  jnz     short loc_1801837CA
0x18018377d  call    HrGetLastError
0x180183782  mov     edi, eax
0x180183784  mov     r10, cs:WPP_GLOBAL_Control
0x18018378b  lea     rcx, WPP_GLOBAL_Control
0x180183792  cmp     r10, rcx
0x180183795  jz      short loc_1801837B6
0x180183797  test    byte ptr [r10+1Ch], 1
0x18018379c  jz      short loc_1801837B6
0x18018379e  mov     rcx, [r10+10h]
0x1801837a2  lea     r8, WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids
0x1801837a9  mov     edx, 34h ; '4'
0x1801837ae  mov     r9d, eax
0x1801837b1  call    WPP_SF_d
0x1801837b6  mov     rcx, [rbp+40h+phToken]; hObject
0x1801837ba  test    rcx, rcx
0x1801837bd  jz      short loc_180183746
0x1801837bf  call    cs:__imp_CloseHandle
0x1801837c5  jmp     loc_180183746
0x1801837ca  mov     edi, 68h ; 'h'
0x1801837cf  lea     rcx, [rbp+40h+StartupInfo]; void *
0x1801837d3  mov     r8d, edi; Size
0x1801837d6  xor     edx, edx; Val
0x1801837d8  call    memset
0x1801837dd  mov     rcx, [rbp+40h+phToken]; hToken
0x1801837e1  lea     rax, aWinsta0Default; "winsta0\\default"
0x1801837e8  mov     [rbp+40h+StartupInfo.lpDesktop], rax
0x1801837ec  xorps   xmm0, xmm0
0x1801837ef  xor     eax, eax
0x1801837f1  mov     [rbp+40h+StartupInfo.cb], edi
0x1801837f4  mov     rdi, [rbp+40h+lpCommandLine]
0x1801837f8  xor     r9d, r9d; lpProcessAttributes
0x1801837fb  mov     qword ptr [rsp+140h+ProcessInformation.dwProcessId], rax
0x180183800  mov     r8, rdi; lpCommandLine
0x180183803  lea     rax, [rsp+140h+ProcessInformation]
0x180183808  mov     [rbp+40h+StartupInfo.wShowWindow], r15w
0x18018380d  mov     [rsp+140h+lpProcessInformation], rax; lpProcessInformation
0x180183812  xor     edx, edx; lpApplicationName
0x180183814  lea     rax, [rbp+40h+StartupInfo]
0x180183818  mov     [rsp+140h+lpStartupInfo], rax; lpStartupInfo
0x18018381d  mov     [rsp+140h+lpCurrentDirectory], r15; lpCurrentDirectory
0x180183822  mov     [rsp+140h+lpEnvironment], r15; lpEnvironment
0x180183827  mov     [rsp+140h+dwCreationFlags], 1000428h; dwCreationFlags
0x18018382f  mov     [rsp+140h+bInheritHandles], r15d; bInheritHandles
0x180183834  mov     [rsp+140h+lpThreadAttributes], r15; lpThreadAttributes
0x180183839  movups  xmmword ptr [rsp+140h+ProcessInformation.hProcess], xmm0
0x18018383e  call    cs:__imp_CreateProcessAsUserW
0x180183844  test    eax, eax
0x180183846  jnz     short loc_1801838B2
0x180183848  call    HrGetLastError
0x18018384d  mov     esi, eax
0x18018384f  test    eax, eax
0x180183851  jns     short loc_1801838B2
0x180183853  mov     rax, cs:WPP_GLOBAL_Control
0x18018385a  lea     rcx, WPP_GLOBAL_Control
0x180183861  cmp     rax, rcx
0x180183864  jz      short loc_180183884
0x180183866  test    byte ptr [rax+1Ch], 1
0x18018386a  jz      short loc_180183884
0x18018386c  mov     rcx, [rax+10h]
0x180183870  lea     r8, WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids
0x180183877  mov     edx, 35h ; '5'
0x18018387c  mov     r9d, esi
0x18018387f  call    WPP_SF_d
0x180183884  mov     rcx, [rbp+40h+phToken]; hObject
0x180183888  test    rcx, rcx
0x18018388b  jz      short loc_180183893
0x18018388d  call    cs:__imp_CloseHandle
0x180183893  test    rdi, rdi
0x180183896  jz      short loc_1801838A0
0x180183898  mov     rcx, rdi; void *
0x18018389b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801838a0  test    rbx, rbx
0x1801838a3  jz      short loc_1801838AE
0x1801838a5  mov     rcx, rbx
0x1801838a8  call    cs:__imp_MpFreeMemory
0x1801838ae  mov     eax, esi
0x1801838b0  jmp     short loc_18018390B
0x1801838b2  mov     rcx, [rsp+140h+ProcessInformation.hThread]; this
0x1801838b7  test    rcx, rcx
0x1801838ba  jz      short loc_1801838C1
0x1801838bc  call    ?UtilCloseHandle@CommonUtil@@YAXPEAX@Z; CommonUtil::UtilCloseHandle(void *)
0x1801838c1  test    r14, r14
0x1801838c4  jz      short loc_1801838D0
0x1801838c6  mov     rax, [rsp+140h+ProcessInformation.hProcess]
0x1801838cb  mov     [r14], rax
0x1801838ce  jmp     short loc_1801838DF
0x1801838d0  mov     rcx, [rsp+140h+ProcessInformation.hProcess]; this
0x1801838d5  test    rcx, rcx
0x1801838d8  jz      short loc_1801838DF
0x1801838da  call    ?UtilCloseHandle@CommonUtil@@YAXPEAX@Z; CommonUtil::UtilCloseHandle(void *)
0x1801838df  mov     rcx, [rbp+40h+phToken]; hObject
0x1801838e3  test    rcx, rcx
0x1801838e6  jz      short loc_1801838EE
0x1801838e8  call    cs:__imp_CloseHandle
0x1801838ee  test    rdi, rdi
0x1801838f1  jz      short loc_1801838FB
0x1801838f3  mov     rcx, rdi; void *
0x1801838f6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801838fb  test    rbx, rbx
0x1801838fe  jz      short loc_180183909
0x180183900  mov     rcx, rbx
0x180183903  call    cs:__imp_MpFreeMemory
0x180183909  xor     eax, eax
0x18018390b  mov     rcx, [rbp+40h+var_40]
0x18018390f  xor     rcx, rsp; StackCookie
0x180183912  call    __security_check_cookie
0x180183917  add     rsp, 118h
0x18018391e  pop     r15
0x180183920  pop     r14
0x180183922  pop     rdi
0x180183923  pop     rsi
0x180183924  pop     rbx
0x180183925  pop     rbp
0x180183926  retn
```
