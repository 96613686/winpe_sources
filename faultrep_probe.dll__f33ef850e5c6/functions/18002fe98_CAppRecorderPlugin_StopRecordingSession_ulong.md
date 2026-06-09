# CAppRecorderPlugin::StopRecordingSession(ulong)

- ea: `0x18002fe98`
- end: `0x1800302b0`
- name: `?StopRecordingSession@CAppRecorderPlugin@@AEAAJK@Z`
- size: `1048`
- prototype: `__int64 __fastcall(CAppRecorderPlugin *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002f330`

## callees

- `0x1800028b4`
- `0x180003474`
- `0x180006b50`
- `0x180009ed8`
- `0x180009f00`
- `0x180016414`
- `0x180016f80`
- `0x18002fe98`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800301ee`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800301ee`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180030214`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180030214`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18003011a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18003011a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003005d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003005d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030124`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18003004b`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18003004b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003016e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800301b5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003016e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800301b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800300b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800300c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003024d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003028c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003029c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800300b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800300c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003024d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003028c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003029c`
- `wer!WerpAddTerminationReason` at `0x180030207`
- `wer!WerpAddTerminationReason` at `0x180030207`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CAppRecorderPlugin::StopRecordingSession(CAppRecorderPlugin *this, unsigned int a2)
{
  char *v3; // rsi
  int SystemDirectory2; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  signed int LastError; // eax
  signed int v10; // eax
  DWORD ProcessId; // eax
  struct _PROCESS_INFORMATION hObject; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpApplicationName[2]; // [rsp+68h] [rbp-98h] BYREF
  _WORD v15[8]; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpName[2]; // [rsp+88h] [rbp-78h] BYREF
  _WORD v17[8]; // [rsp+98h] [rbp-68h] BYREF
  LPWSTR lpCommandLine[2]; // [rsp+A8h] [rbp-58h] BYREF
  _WORD v19[12]; // [rsp+B8h] [rbp-48h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+D0h] [rbp-30h] BYREF

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&hObject, 0, sizeof(hObject));
  lpCommandLine[0] = v19;
  lpCommandLine[1] = v19;
  v19[0] = 0;
  lpApplicationName[0] = v15;
  lpApplicationName[1] = v15;
  v15[0] = 0;
  v3 = 0;
  lpName[0] = v17;
  lpName[1] = v17;
  v17[0] = 0;
  SystemDirectory2 = UtilGetSystemDirectory2(lpApplicationName, 0);
  v5 = SystemDirectory2;
  if ( SystemDirectory2 >= 0 )
  {
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                            lpApplicationName,
                            L"psr.exe") )
    {
      SystemDirectory2 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                           lpCommandLine,
                           L"%s /stop",
                           lpApplicationName[0]);
      v5 = SystemDirectory2;
      if ( SystemDirectory2 >= 0 )
      {
        SystemDirectory2 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                             lpName,
                             L"%d-AppRecorderEnabled",
                             a2);
        v5 = SystemDirectory2;
        if ( SystemDirectory2 >= 0 )
        {
          v3 = (char *)OpenEventW(0x100000u, 0, lpName[0]);
          if ( v3 == (char *)-1LL || v3 + 1 == (char *)1 )
          {
            LastError = GetLastError();
            v5 = LastError;
            if ( LastError > 0 )
              v5 = (unsigned __int16)LastError | 0x80070000;
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_47;
            v7 = 37;
          }
          else
          {
            StartupInfo.cb = 104;
            if ( hObject.hProcess )
              CloseHandle(hObject.hProcess);
            if ( hObject.hThread )
              CloseHandle(hObject.hThread);
            memset(&hObject, 0, sizeof(hObject));
            if ( CreateProcessW(lpApplicationName[0], lpCommandLine[0], 0, 0, 0, 0, 0, 0, &StartupInfo, &hObject) )
            {
              if ( WaitForSingleObject(v3, 0x4E20u) == 258
                && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids);
              }
              if ( hObject.hProcess && WaitForSingleObject(hObject.hProcess, 0x4E20u) == 258 )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids);
                }
                ProcessId = GetProcessId(hObject.hProcess);
                WerpAddTerminationReason(ProcessId, 2, L"WerAppRecorderNonResponsive");
                TerminateProcess(hObject.hProcess, 0);
                v5 = -2147467259;
              }
              else
              {
                v5 = 0;
              }
              goto LABEL_47;
            }
            v10 = GetLastError();
            v5 = v10;
            if ( v10 > 0 )
              v5 = (unsigned __int16)v10 | 0x80070000;
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_47;
            v7 = 38;
          }
          v8 = v5;
          goto LABEL_6;
        }
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = 36;
          goto LABEL_5;
        }
      }
      else
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = 35;
          goto LABEL_5;
        }
      }
    }
    else
    {
      v5 = -2147024882;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 34;
        v8 = 2147942414LL;
        goto LABEL_6;
      }
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 33;
LABEL_5:
      v8 = (unsigned int)SystemDirectory2;
LABEL_6:
      WPP_SF_d(v6[2], v7, &WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids, v8);
    }
  }
LABEL_47:
  if ( lpName[0] != v17 )
    operator delete((void *)lpName[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( (unsigned __int64)(v3 + 1) > 1 )
    CloseHandle(v3);
  if ( lpApplicationName[0] != v15 )
    operator delete((void *)lpApplicationName[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( lpCommandLine[0] != v19 )
    operator delete(lpCommandLine[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( hObject.hProcess )
    CloseHandle(hObject.hProcess);
  if ( hObject.hThread )
    CloseHandle(hObject.hThread);
  return v5;
}

```

## disassembly

```asm
0x18002fe98  mov     [rsp-8+arg_0], rcx
0x18002fe9d  push    rbp
0x18002fe9e  push    rbx
0x18002fe9f  push    rsi
0x18002fea0  push    rdi
0x18002fea1  lea     rbp, [rsp-48h]
0x18002fea6  sub     rsp, 148h
0x18002fead  mov     edi, edx
0x18002feaf  xor     edx, edx; Val
0x18002feb1  lea     r8d, [rdx+68h]; Size
0x18002feb5  lea     rcx, [rbp+60h+StartupInfo]; void *
0x18002feb9  call    memset_0
0x18002febe  xorps   xmm0, xmm0
0x18002fec1  xor     eax, eax
0x18002fec3  movups  xmmword ptr [rsp+160h+hObject], xmm0
0x18002fec8  mov     [rsp+160h+var_100], rax
0x18002fecd  lea     rax, [rbp+60h+var_A8]
0x18002fed1  mov     [rbp+60h+lpCommandLine], rax
0x18002fed5  lea     rax, [rbp+60h+var_A8]
0x18002fed9  mov     [rbp+60h+var_B0], rax
0x18002fedd  xor     eax, eax
0x18002fedf  mov     [rbp+60h+var_A8], ax
0x18002fee3  lea     rax, [rsp+160h+var_E8]
0x18002fee8  mov     [rsp+160h+lpApplicationName], rax
0x18002feed  lea     rax, [rsp+160h+var_E8]
0x18002fef2  mov     [rsp+160h+var_F0], rax
0x18002fef7  xor     eax, eax
0x18002fef9  mov     [rsp+160h+var_E8], ax
0x18002fefe  xor     esi, esi
0x18002ff00  mov     [rbp+60h+arg_0], rsi
0x18002ff04  lea     rax, [rbp+60h+var_C8]
0x18002ff08  mov     [rbp+60h+lpName], rax
0x18002ff0c  lea     rax, [rbp+60h+var_C8]
0x18002ff10  mov     [rbp+60h+var_D0], rax
0x18002ff14  xor     eax, eax
0x18002ff16  mov     [rbp+60h+var_C8], ax
0x18002ff1a  xor     edx, edx
0x18002ff1c  lea     rcx, [rsp+160h+lpApplicationName]
0x18002ff21  call    ?UtilGetSystemDirectory2@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@G_N@Z; UtilGetSystemDirectory2(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ushort,bool)
0x18002ff26  mov     ebx, eax
0x18002ff28  test    eax, eax
0x18002ff2a  jns     short loc_18002FF68
0x18002ff2c  lea     rdi, WPP_GLOBAL_Control
0x18002ff33  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ff3a  cmp     rcx, rdi
0x18002ff3d  jz      loc_180030223
0x18002ff43  test    byte ptr [rcx+1Ch], 1
0x18002ff47  jz      loc_180030223
0x18002ff4d  lea     edx, [rsi+21h]
0x18002ff50  mov     r9d, eax
0x18002ff53  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x18002ff5a  mov     rcx, [rcx+10h]
0x18002ff5e  call    WPP_SF_d
0x18002ff63  jmp     loc_180030223
0x18002ff68  mov     r8d, 7
0x18002ff6e  lea     rdx, aPsrExe; "psr.exe"
0x18002ff75  lea     rcx, [rsp+160h+lpApplicationName]
0x18002ff7a  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18002ff7f  test    al, al
0x18002ff81  jnz     short loc_18002FFB6
0x18002ff83  mov     ebx, 8007000Eh
0x18002ff88  lea     rdi, WPP_GLOBAL_Control
0x18002ff8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ff96  cmp     rcx, rdi
0x18002ff99  jz      loc_180030223
0x18002ff9f  test    byte ptr [rcx+1Ch], 1
0x18002ffa3  jz      loc_180030223
0x18002ffa9  mov     edx, 22h ; '"'
0x18002ffae  mov     r9d, 8007000Eh
0x18002ffb4  jmp     short loc_18002FF53
0x18002ffb6  mov     r8, [rsp+160h+lpApplicationName]
0x18002ffbb  lea     rdx, aSStop; "%s /stop"
0x18002ffc2  lea     rcx, [rbp+60h+lpCommandLine]
0x18002ffc6  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18002ffcb  mov     ebx, eax
0x18002ffcd  test    eax, eax
0x18002ffcf  jns     short loc_18002FFFC
0x18002ffd1  lea     rdi, WPP_GLOBAL_Control
0x18002ffd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ffdf  cmp     rcx, rdi
0x18002ffe2  jz      loc_180030223
0x18002ffe8  test    byte ptr [rcx+1Ch], 1
0x18002ffec  jz      loc_180030223
0x18002fff2  mov     edx, 23h ; '#'
0x18002fff7  jmp     loc_18002FF50
0x18002fffc  mov     r8d, edi
0x18002ffff  lea     rdx, aDApprecorderen; "%d-AppRecorderEnabled"
0x180030006  lea     rcx, [rbp+60h+lpName]
0x18003000a  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18003000f  mov     ebx, eax
0x180030011  test    eax, eax
0x180030013  jns     short loc_180030040
0x180030015  lea     rdi, WPP_GLOBAL_Control
0x18003001c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030023  cmp     rcx, rdi
0x180030026  jz      loc_180030223
0x18003002c  test    byte ptr [rcx+1Ch], 1
0x180030030  jz      loc_180030223
0x180030036  mov     edx, 24h ; '$'
0x18003003b  jmp     loc_18002FF50
0x180030040  mov     r8, [rbp+60h+lpName]; lpName
0x180030044  xor     edx, edx; bInheritHandle
0x180030046  mov     ecx, 100000h; dwDesiredAccess
0x18003004b  call    cs:__imp_OpenEventW
0x180030051  mov     rsi, rax
0x180030054  inc     rax
0x180030057  cmp     rax, 1
0x18003005b  ja      short loc_1800300A0
0x18003005d  call    cs:__imp_GetLastError
0x180030063  mov     ebx, eax
0x180030065  test    eax, eax
0x180030067  jle     short loc_180030072
0x180030069  movzx   ebx, ax
0x18003006c  or      ebx, 80070000h
0x180030072  lea     rdi, WPP_GLOBAL_Control
0x180030079  mov     rcx, cs:WPP_GLOBAL_Control
0x180030080  cmp     rcx, rdi
0x180030083  jz      loc_180030223
0x180030089  test    byte ptr [rcx+1Ch], 1
0x18003008d  jz      loc_180030223
0x180030093  mov     edx, 25h ; '%'
0x180030098  mov     r9d, ebx
0x18003009b  jmp     loc_18002FF53
0x1800300a0  mov     [rbp+60h+StartupInfo.cb], 68h ; 'h'
0x1800300a7  mov     rcx, [rsp+160h+hObject]; hObject
0x1800300ac  test    rcx, rcx
0x1800300af  jz      short loc_1800300B7
0x1800300b1  call    cs:__imp_CloseHandle
0x1800300b7  mov     rcx, [rsp+160h+hObject+8]; hObject
0x1800300bc  test    rcx, rcx
0x1800300bf  jz      short loc_1800300C7
0x1800300c1  call    cs:__imp_CloseHandle
0x1800300c7  xorps   xmm0, xmm0
0x1800300ca  xor     eax, eax
0x1800300cc  movups  xmmword ptr [rsp+160h+hObject], xmm0
0x1800300d1  mov     [rsp+160h+var_100], rax
0x1800300d6  lea     rax, [rsp+160h+hObject]
0x1800300db  mov     [rsp+160h+lpProcessInformation], rax; lpProcessInformation
0x1800300e0  lea     rax, [rbp+60h+StartupInfo]
0x1800300e4  mov     [rsp+160h+lpStartupInfo], rax; lpStartupInfo
0x1800300e9  mov     [rsp+160h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1800300f2  mov     [rsp+160h+lpEnvironment], 0; lpEnvironment
0x1800300fb  mov     [rsp+160h+dwCreationFlags], 0; dwCreationFlags
0x180030103  mov     [rsp+160h+bInheritHandles], 0; bInheritHandles
0x18003010b  xor     r9d, r9d; lpThreadAttributes
0x18003010e  xor     r8d, r8d; lpProcessAttributes
0x180030111  mov     rdx, [rbp+60h+lpCommandLine]; lpCommandLine
0x180030115  mov     rcx, [rsp+160h+lpApplicationName]; lpApplicationName
0x18003011a  call    cs:__imp_CreateProcessW
0x180030120  test    eax, eax
0x180030122  jnz     short loc_180030164
0x180030124  call    cs:__imp_GetLastError
0x18003012a  mov     ebx, eax
0x18003012c  test    eax, eax
0x18003012e  jle     short loc_180030139
0x180030130  movzx   ebx, ax
0x180030133  or      ebx, 80070000h
0x180030139  lea     rdi, WPP_GLOBAL_Control
0x180030140  mov     rcx, cs:WPP_GLOBAL_Control
0x180030147  cmp     rcx, rdi
0x18003014a  jz      loc_180030223
0x180030150  test    byte ptr [rcx+1Ch], 1
0x180030154  jz      loc_180030223
0x18003015a  mov     edx, 26h ; '&'
0x18003015f  jmp     loc_180030098
0x180030164  mov     ebx, 4E20h
0x180030169  mov     edx, ebx; dwMilliseconds
0x18003016b  mov     rcx, rsi; hHandle
0x18003016e  call    cs:__imp_WaitForSingleObject
0x180030174  lea     rdi, WPP_GLOBAL_Control
0x18003017b  cmp     eax, 102h
0x180030180  jnz     short loc_1800301A9
0x180030182  mov     rcx, cs:WPP_GLOBAL_Control
0x180030189  cmp     rcx, rdi
0x18003018c  jz      short loc_1800301A9
0x18003018e  test    byte ptr [rcx+1Ch], 2
0x180030192  jz      short loc_1800301A9
0x180030194  mov     edx, 27h ; '''
0x180030199  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x1800301a0  mov     rcx, [rcx+10h]
0x1800301a4  call    WPP_SF_
0x1800301a9  mov     rcx, [rsp+160h+hObject]; hHandle
0x1800301ae  test    rcx, rcx
0x1800301b1  jz      short loc_180030221
0x1800301b3  mov     edx, ebx; dwMilliseconds
0x1800301b5  call    cs:__imp_WaitForSingleObject
0x1800301bb  cmp     eax, 102h
0x1800301c0  jnz     short loc_180030221
0x1800301c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800301c9  cmp     rcx, rdi
0x1800301cc  jz      short loc_1800301E9
0x1800301ce  test    byte ptr [rcx+1Ch], 1
0x1800301d2  jz      short loc_1800301E9
0x1800301d4  mov     edx, 28h ; '('
0x1800301d9  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x1800301e0  mov     rcx, [rcx+10h]
0x1800301e4  call    WPP_SF_
0x1800301e9  mov     rcx, [rsp+160h+hObject]; Process
0x1800301ee  call    cs:__imp_GetProcessId
0x1800301f4  mov     ecx, eax
0x1800301f6  mov     r9d, 1
0x1800301fc  lea     r8, aWerapprecorder; "WerAppRecorderNonResponsive"
0x180030203  lea     edx, [r9+1]
0x180030207  call    cs:__imp_WerpAddTerminationReason
0x18003020d  xor     edx, edx; uExitCode
0x18003020f  mov     rcx, [rsp+160h+hObject]; hProcess
0x180030214  call    cs:__imp_TerminateProcess
0x18003021a  mov     ebx, 80004005h
0x18003021f  jmp     short loc_180030223
0x180030221  xor     ebx, ebx
0x180030223  lea     rax, [rbp+60h+var_C8]
0x180030227  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18003022e  mov     rcx, [rbp+60h+lpName]; void *
0x180030232  cmp     rcx, rax
0x180030235  jz      short loc_180030240
0x180030237  mov     rdx, rdi; struct std::nothrow_t *
0x18003023a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003023f  nop
0x180030240  lea     rax, [rsi+1]
0x180030244  cmp     rax, 1
0x180030248  jbe     short loc_180030254
0x18003024a  mov     rcx, rsi; hObject
0x18003024d  call    cs:__imp_CloseHandle
0x180030253  nop
0x180030254  lea     rax, [rsp+160h+var_E8]
0x180030259  mov     rcx, [rsp+160h+lpApplicationName]; void *
0x18003025e  cmp     rcx, rax
0x180030261  jz      short loc_18003026C
0x180030263  mov     rdx, rdi; struct std::nothrow_t *
0x180030266  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003026b  nop
0x18003026c  lea     rax, [rbp+60h+var_A8]
0x180030270  mov     rcx, [rbp+60h+lpCommandLine]; void *
0x180030274  cmp     rcx, rax
0x180030277  jz      short loc_180030282
0x180030279  mov     rdx, rdi; struct std::nothrow_t *
0x18003027c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180030281  nop
0x180030282  mov     rcx, [rsp+160h+hObject]; hObject
0x180030287  test    rcx, rcx
0x18003028a  jz      short loc_180030292
0x18003028c  call    cs:__imp_CloseHandle
0x180030292  mov     rcx, [rsp+160h+hObject+8]; hObject
0x180030297  test    rcx, rcx
0x18003029a  jz      short loc_1800302A2
0x18003029c  call    cs:__imp_CloseHandle
0x1800302a2  mov     eax, ebx
0x1800302a4  add     rsp, 148h
0x1800302ab  pop     rdi
0x1800302ac  pop     rsi
0x1800302ad  pop     rbx
0x1800302ae  pop     rbp
0x1800302af  retn
```
