# RealtimeProtection::MpLaunchProcessAsUserProcessToken(wchar_t const *,wchar_t const *,ulong,void * *)

- ea: `0x180183928`
- end: `0x180183c66`
- name: `?MpLaunchProcessAsUserProcessToken@RealtimeProtection@@YAJPEB_W0KPEAPEAX@Z`
- size: `830`
- prototype: `__int64 __fastcall(wchar_t **this, const wchar_t *, const wchar_t *, unsigned int, void **)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180075250`
- `0x1801f66e4`

## callees

- `0x18007f2f8`
- `0x1800809d0`
- `0x1800c8f68`
- `0x1801019bc`
- `0x180104674`
- `0x1801051e8`
- `0x180106620`
- `0x18010cb40`
- `0x18010ce3c`
- `0x180183928`
- `0x18023a310`

## import_xrefs

- `MpClient!MpFreeMemory` at `0x1801839a9`
- `MpClient!MpFreeMemory` at `0x180183a22`
- `MpClient!MpFreeMemory` at `0x180183bd8`
- `MpClient!MpFreeMemory` at `0x180183c42`
- `MpClient!MpFreeMemory` at `0x1801839a9`
- `MpClient!MpFreeMemory` at `0x180183a22`
- `MpClient!MpFreeMemory` at `0x180183bd8`
- `MpClient!MpFreeMemory` at `0x180183c42`
- `KERNEL32!CloseHandle` at `0x180183a84`
- `KERNEL32!CloseHandle` at `0x180183ae3`
- `KERNEL32!CloseHandle` at `0x180183bae`
- `KERNEL32!CloseHandle` at `0x180183bbd`
- `KERNEL32!CloseHandle` at `0x180183c18`
- `KERNEL32!CloseHandle` at `0x180183c27`
- `KERNEL32!CloseHandle` at `0x180183a84`
- `KERNEL32!CloseHandle` at `0x180183ae3`
- `KERNEL32!CloseHandle` at `0x180183bae`
- `KERNEL32!CloseHandle` at `0x180183bbd`
- `KERNEL32!CloseHandle` at `0x180183c18`
- `KERNEL32!CloseHandle` at `0x180183c27`
- `ADVAPI32!CreateProcessAsUserW` at `0x180183b5f`
- `ADVAPI32!CreateProcessAsUserW` at `0x180183b5f`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::MpLaunchProcessAsUserProcessToken(
        wchar_t **this,
        const wchar_t *a2,
        const wchar_t *a3,
        HANDLE *a4)
{
  unsigned int v6; // esi
  int MpFileFullNameFromService; // eax
  unsigned int v8; // ebx
  wchar_t *v10; // rbx
  int v11; // eax
  unsigned int v12; // r9d
  unsigned int v13; // edi
  const struct std::nothrow_t *v14; // rdx
  int v15; // eax
  unsigned int v16; // r9d
  int v17; // eax
  LPWSTR v18; // rdi
  void *v19; // rdx
  int LastError; // eax
  unsigned int v21; // esi
  const struct std::nothrow_t *v22; // rdx
  wchar_t *v23; // [rsp+60h] [rbp-A0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-98h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  HANDLE hObject; // [rsp+F0h] [rbp-10h] BYREF
  LPWSTR lpCommandLine; // [rsp+F8h] [rbp-8h] BYREF
  HANDLE hToken; // [rsp+100h] [rbp+0h] BYREF

  v23 = 0;
  v6 = (unsigned int)a3;
  MpFileFullNameFromService = MpConfigUtils::GetMpFileFullNameFromService((MpConfigUtils *)&v23, this, a3, (bool)a4);
  v8 = MpFileFullNameFromService;
  if ( MpFileFullNameFromService < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids,
        (unsigned int)MpFileFullNameFromService);
    if ( v23 )
      MpFreeMemory(v23);
    return v8;
  }
  v10 = v23;
  lpCommandLine = 0;
  v11 = CommonUtil::NewSprintfW((CommonUtil *)&lpCommandLine, (wchar_t **)L"\"%ls\" %ls", v23, a2);
  v13 = v11;
  if ( v11 < 0 )
  {
    v14 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids,
        (unsigned int)v11);
LABEL_12:
    if ( lpCommandLine )
      operator delete(lpCommandLine, v14);
    if ( v10 )
      MpFreeMemory(v10);
    return v13;
  }
  hObject = 0;
  v15 = CommonUtil::UtilOpenProcess((CommonUtil *)&hObject, (void **)v6, 0x400u, v12);
  v13 = v15;
  if ( v15 < 0 )
  {
    v14 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids,
        (unsigned int)v15);
LABEL_21:
    if ( hObject )
      CloseHandle(hObject);
    goto LABEL_12;
  }
  hToken = 0;
  v17 = CommonUtil::UtilOpenProcessToken((CommonUtil *)&hToken, (void **)hObject, (void *)0xF, v16);
  v13 = v17;
  if ( v17 < 0 )
  {
    v14 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids,
        (unsigned int)v17);
    if ( hToken )
      CloseHandle(hToken);
    goto LABEL_21;
  }
  memset(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.lpDesktop = L"winsta0\\default";
  StartupInfo.cb = 104;
  v18 = lpCommandLine;
  StartupInfo.wShowWindow = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( CreateProcessAsUserW(hToken, 0, lpCommandLine, 0, 0, 0, 0x1000428u, 0, 0, &StartupInfo, &ProcessInformation)
    || (LastError = HrGetLastError(), v21 = LastError, LastError >= 0) )
  {
    if ( ProcessInformation.hThread )
      CommonUtil::UtilCloseHandle((CommonUtil *)ProcessInformation.hThread, v19);
    if ( a4 )
    {
      *a4 = ProcessInformation.hProcess;
    }
    else if ( ProcessInformation.hProcess )
    {
      CommonUtil::UtilCloseHandle((CommonUtil *)ProcessInformation.hProcess, v19);
    }
    if ( hToken )
      CloseHandle(hToken);
    if ( hObject )
      CloseHandle(hObject);
    if ( v18 )
      operator delete(v18, (const struct std::nothrow_t *)v19);
    if ( v10 )
      MpFreeMemory(v10);
    return 0;
  }
  else
  {
    v22 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids,
        (unsigned int)LastError);
    if ( hToken )
      CloseHandle(hToken);
    if ( hObject )
      CloseHandle(hObject);
    if ( v18 )
      operator delete(v18, v22);
    if ( v10 )
      MpFreeMemory(v10);
    return v21;
  }
}

```

## disassembly

```asm
0x180183928  push    rbp
0x18018392a  push    rbx
0x18018392b  push    rsi
0x18018392c  push    rdi
0x18018392d  push    r14
0x18018392f  push    r15
0x180183931  lea     rbp, [rsp-18h]
0x180183936  sub     rsp, 118h
0x18018393d  mov     rax, cs:__security_cookie
0x180183944  xor     rax, rsp
0x180183947  mov     [rbp+40h+var_38], rax
0x18018394b  mov     rdi, rdx
0x18018394e  xor     r15d, r15d
0x180183951  mov     rdx, rcx; wchar_t **
0x180183954  mov     [rsp+140h+var_E0], r15
0x180183959  lea     rcx, [rsp+140h+var_E0]; this
0x18018395e  mov     r14, r9
0x180183961  mov     esi, r8d
0x180183964  call    ?GetMpFileFullNameFromService@MpConfigUtils@@YAJPEAPEA_WPEB_W_N@Z; MpConfigUtils::GetMpFileFullNameFromService(wchar_t * *,wchar_t const *,bool)
0x180183969  mov     ebx, eax
0x18018396b  test    eax, eax
0x18018396d  jns     short loc_1801839B6
0x18018396f  mov     rcx, cs:WPP_GLOBAL_Control
0x180183976  lea     rdx, WPP_GLOBAL_Control
0x18018397d  cmp     rcx, rdx
0x180183980  jz      short loc_18018399F
0x180183982  test    byte ptr [rcx+1Ch], 1
0x180183986  jz      short loc_18018399F
0x180183988  mov     rcx, [rcx+10h]
0x18018398c  lea     edx, [r15+2Dh]
0x180183990  mov     r9d, eax
0x180183993  lea     r8, WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids
0x18018399a  call    WPP_SF_d
0x18018399f  mov     rcx, [rsp+140h+var_E0]
0x1801839a4  test    rcx, rcx
0x1801839a7  jz      short loc_1801839AF
0x1801839a9  call    cs:__imp_MpFreeMemory
0x1801839af  mov     eax, ebx
0x1801839b1  jmp     loc_180183C4A
0x1801839b6  mov     rbx, [rsp+140h+var_E0]
0x1801839bb  lea     rdx, aLsLs; "\"%ls\" %ls"
0x1801839c2  mov     r8, rbx; wchar_t *
0x1801839c5  mov     [rbp+40h+lpCommandLine], r15
0x1801839c9  mov     r9, rdi
0x1801839cc  lea     rcx, [rbp+40h+lpCommandLine]; this
0x1801839d0  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x1801839d5  mov     edi, eax
0x1801839d7  test    eax, eax
0x1801839d9  jns     short loc_180183A2F
0x1801839db  mov     rcx, cs:WPP_GLOBAL_Control
0x1801839e2  lea     rdx, WPP_GLOBAL_Control
0x1801839e9  cmp     rcx, rdx
0x1801839ec  jz      short loc_180183A0C
0x1801839ee  test    byte ptr [rcx+1Ch], 1
0x1801839f2  jz      short loc_180183A0C
0x1801839f4  mov     rcx, [rcx+10h]
0x1801839f8  lea     r8, WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids
0x1801839ff  mov     edx, 2Eh ; '.'
0x180183a04  mov     r9d, eax
0x180183a07  call    WPP_SF_d
0x180183a0c  mov     rcx, [rbp+40h+lpCommandLine]; void *
0x180183a10  test    rcx, rcx
0x180183a13  jz      short loc_180183A1A
0x180183a15  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180183a1a  test    rbx, rbx
0x180183a1d  jz      short loc_180183A28
0x180183a1f  mov     rcx, rbx
0x180183a22  call    cs:__imp_MpFreeMemory
0x180183a28  mov     eax, edi
0x180183a2a  jmp     loc_180183C4A
0x180183a2f  mov     r8d, 400h; unsigned int
0x180183a35  mov     [rbp+40h+hObject], r15
0x180183a39  mov     edx, esi; void **
0x180183a3b  lea     rcx, [rbp+40h+hObject]; this
0x180183a3f  call    ?UtilOpenProcess@CommonUtil@@YAJPEAPEAXKK@Z; CommonUtil::UtilOpenProcess(void * *,ulong,ulong)
0x180183a44  mov     edi, eax
0x180183a46  test    eax, eax
0x180183a48  jns     short loc_180183A8C
0x180183a4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180183a51  lea     rdx, WPP_GLOBAL_Control
0x180183a58  cmp     rcx, rdx
0x180183a5b  jz      short loc_180183A7B
0x180183a5d  test    byte ptr [rcx+1Ch], 1
0x180183a61  jz      short loc_180183A7B
0x180183a63  mov     rcx, [rcx+10h]
0x180183a67  lea     r8, WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids
0x180183a6e  mov     edx, 2Fh ; '/'
0x180183a73  mov     r9d, eax
0x180183a76  call    WPP_SF_d
0x180183a7b  mov     rcx, [rbp+40h+hObject]; hObject
0x180183a7f  test    rcx, rcx
0x180183a82  jz      short loc_180183A0C
0x180183a84  call    cs:__imp_CloseHandle
0x180183a8a  jmp     short loc_180183A0C
0x180183a8c  mov     rdx, [rbp+40h+hObject]; void **
0x180183a90  lea     rcx, [rbp+40h+hToken]; this
0x180183a94  mov     r8d, 0Fh; void *
0x180183a9a  mov     [rbp+40h+hToken], r15
0x180183a9e  call    ?UtilOpenProcessToken@CommonUtil@@YAJPEAPEAXPEAXK@Z; CommonUtil::UtilOpenProcessToken(void * *,void *,ulong)
0x180183aa3  mov     edi, eax
0x180183aa5  test    eax, eax
0x180183aa7  jns     short loc_180183AEB
0x180183aa9  mov     rcx, cs:WPP_GLOBAL_Control
0x180183ab0  lea     rdx, WPP_GLOBAL_Control
0x180183ab7  cmp     rcx, rdx
0x180183aba  jz      short loc_180183ADA
0x180183abc  test    byte ptr [rcx+1Ch], 1
0x180183ac0  jz      short loc_180183ADA
0x180183ac2  mov     rcx, [rcx+10h]
0x180183ac6  lea     r8, WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids
0x180183acd  mov     edx, 30h ; '0'
0x180183ad2  mov     r9d, eax
0x180183ad5  call    WPP_SF_d
0x180183ada  mov     rcx, [rbp+40h+hToken]; hObject
0x180183ade  test    rcx, rcx
0x180183ae1  jz      short loc_180183A7B
0x180183ae3  call    cs:__imp_CloseHandle
0x180183ae9  jmp     short loc_180183A7B
0x180183aeb  mov     edi, 68h ; 'h'
0x180183af0  lea     rcx, [rbp+40h+StartupInfo]; void *
0x180183af4  mov     r8d, edi; Size
0x180183af7  xor     edx, edx; Val
0x180183af9  call    memset
0x180183afe  mov     rcx, [rbp+40h+hToken]; hToken
0x180183b02  lea     rax, aWinsta0Default; "winsta0\\default"
0x180183b09  mov     [rbp+40h+StartupInfo.lpDesktop], rax
0x180183b0d  xorps   xmm0, xmm0
0x180183b10  xor     eax, eax
0x180183b12  mov     [rbp+40h+StartupInfo.cb], edi
0x180183b15  mov     rdi, [rbp+40h+lpCommandLine]
0x180183b19  xor     r9d, r9d; lpProcessAttributes
0x180183b1c  mov     qword ptr [rsp+140h+ProcessInformation.dwProcessId], rax
0x180183b21  mov     r8, rdi; lpCommandLine
0x180183b24  lea     rax, [rsp+140h+ProcessInformation]
0x180183b29  mov     [rbp+40h+StartupInfo.wShowWindow], r15w
0x180183b2e  mov     [rsp+140h+lpProcessInformation], rax; lpProcessInformation
0x180183b33  xor     edx, edx; lpApplicationName
0x180183b35  lea     rax, [rbp+40h+StartupInfo]
0x180183b39  mov     [rsp+140h+lpStartupInfo], rax; lpStartupInfo
0x180183b3e  mov     [rsp+140h+lpCurrentDirectory], r15; lpCurrentDirectory
0x180183b43  mov     [rsp+140h+lpEnvironment], r15; lpEnvironment
0x180183b48  mov     [rsp+140h+dwCreationFlags], 1000428h; dwCreationFlags
0x180183b50  mov     [rsp+140h+bInheritHandles], r15d; bInheritHandles
0x180183b55  mov     [rsp+140h+lpThreadAttributes], r15; lpThreadAttributes
0x180183b5a  movups  xmmword ptr [rsp+140h+ProcessInformation.hProcess], xmm0
0x180183b5f  call    cs:__imp_CreateProcessAsUserW
0x180183b65  test    eax, eax
0x180183b67  jnz     short loc_180183BE2
0x180183b69  call    HrGetLastError
0x180183b6e  mov     esi, eax
0x180183b70  test    eax, eax
0x180183b72  jns     short loc_180183BE2
0x180183b74  mov     rcx, cs:WPP_GLOBAL_Control
0x180183b7b  lea     rdx, WPP_GLOBAL_Control
0x180183b82  cmp     rcx, rdx
0x180183b85  jz      short loc_180183BA5
0x180183b87  test    byte ptr [rcx+1Ch], 1
0x180183b8b  jz      short loc_180183BA5
0x180183b8d  mov     rcx, [rcx+10h]
0x180183b91  lea     r8, WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids
0x180183b98  mov     edx, 31h ; '1'
0x180183b9d  mov     r9d, eax
0x180183ba0  call    WPP_SF_d
0x180183ba5  mov     rcx, [rbp+40h+hToken]; hObject
0x180183ba9  test    rcx, rcx
0x180183bac  jz      short loc_180183BB4
0x180183bae  call    cs:__imp_CloseHandle
0x180183bb4  mov     rcx, [rbp+40h+hObject]; hObject
0x180183bb8  test    rcx, rcx
0x180183bbb  jz      short loc_180183BC3
0x180183bbd  call    cs:__imp_CloseHandle
0x180183bc3  test    rdi, rdi
0x180183bc6  jz      short loc_180183BD0
0x180183bc8  mov     rcx, rdi; void *
0x180183bcb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180183bd0  test    rbx, rbx
0x180183bd3  jz      short loc_180183BDE
0x180183bd5  mov     rcx, rbx
0x180183bd8  call    cs:__imp_MpFreeMemory
0x180183bde  mov     eax, esi
0x180183be0  jmp     short loc_180183C4A
0x180183be2  mov     rcx, [rsp+140h+ProcessInformation.hThread]; this
0x180183be7  test    rcx, rcx
0x180183bea  jz      short loc_180183BF1
0x180183bec  call    ?UtilCloseHandle@CommonUtil@@YAXPEAX@Z; CommonUtil::UtilCloseHandle(void *)
0x180183bf1  test    r14, r14
0x180183bf4  jz      short loc_180183C00
0x180183bf6  mov     rax, [rsp+140h+ProcessInformation.hProcess]
0x180183bfb  mov     [r14], rax
0x180183bfe  jmp     short loc_180183C0F
0x180183c00  mov     rcx, [rsp+140h+ProcessInformation.hProcess]; this
0x180183c05  test    rcx, rcx
0x180183c08  jz      short loc_180183C0F
0x180183c0a  call    ?UtilCloseHandle@CommonUtil@@YAXPEAX@Z; CommonUtil::UtilCloseHandle(void *)
0x180183c0f  mov     rcx, [rbp+40h+hToken]; hObject
0x180183c13  test    rcx, rcx
0x180183c16  jz      short loc_180183C1E
0x180183c18  call    cs:__imp_CloseHandle
0x180183c1e  mov     rcx, [rbp+40h+hObject]; hObject
0x180183c22  test    rcx, rcx
0x180183c25  jz      short loc_180183C2D
0x180183c27  call    cs:__imp_CloseHandle
0x180183c2d  test    rdi, rdi
0x180183c30  jz      short loc_180183C3A
0x180183c32  mov     rcx, rdi; void *
0x180183c35  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180183c3a  test    rbx, rbx
0x180183c3d  jz      short loc_180183C48
0x180183c3f  mov     rcx, rbx
0x180183c42  call    cs:__imp_MpFreeMemory
0x180183c48  xor     eax, eax
0x180183c4a  mov     rcx, [rbp+40h+var_38]
0x180183c4e  xor     rcx, rsp; StackCookie
0x180183c51  call    __security_check_cookie
0x180183c56  add     rsp, 118h
0x180183c5d  pop     r15
0x180183c5f  pop     r14
0x180183c61  pop     rdi
0x180183c62  pop     rsi
0x180183c63  pop     rbx
0x180183c64  pop     rbp
0x180183c65  retn
```
