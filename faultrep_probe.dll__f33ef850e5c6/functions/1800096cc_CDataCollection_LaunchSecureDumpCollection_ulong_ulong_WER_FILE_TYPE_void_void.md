# CDataCollection::LaunchSecureDumpCollection(ulong,ulong,_WER_FILE_TYPE,void *,void *)

- ea: `0x1800096cc`
- end: `0x180009ad6`
- name: `?LaunchSecureDumpCollection@CDataCollection@@AEAAJKKW4_WER_FILE_TYPE@@PEAX1@Z`
- size: `1034`
- prototype: `__int64 __fastcall(CDataCollection *__hidden this, unsigned int, unsigned int, enum _WER_FILE_TYPE, void *, HANDLE hSourceHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008be4`

## callees

- `0x180002890`
- `0x180003474`
- `0x180006684`
- `0x180007704`
- `0x1800096cc`
- `0x180009ed8`
- `0x180009f00`
- `0x18003e5a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009755`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000975e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009755`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000975e`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180009912`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180009912`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800099f0`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800099f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009792`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000991c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009792`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000991c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099fa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009997`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009997`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800098ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800098bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009aa4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800098ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800098bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009aa4`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180009788`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180009788`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDataCollection::LaunchSecureDumpCollection(
        CDataCollection *this,
        unsigned int a2,
        int a3,
        enum _WER_FILE_TYPE a4,
        void *a5,
        HANDLE hSourceHandle)
{
  HANDLE *v9; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v11; // rax
  signed int LastError; // eax
  unsigned int v13; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  int v17; // eax
  signed int v18; // eax
  signed int v19; // eax
  signed int v20; // eax
  _QWORD *v21; // rcx
  __int64 dwDesiredAccess; // [rsp+20h] [rbp-E0h]
  __int64 bInheritHandle; // [rsp+28h] [rbp-D8h]
  DWORD ExitCode; // [rsp+50h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION hObject; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v27[2]; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  __int128 v29; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v30; // [rsp+100h] [rbp+0h]
  __int128 v31; // [rsp+110h] [rbp+10h]
  __int128 v32; // [rsp+120h] [rbp+20h]
  __int128 v33; // [rsp+130h] [rbp+30h]
  __int128 v34; // [rsp+140h] [rbp+40h]
  void *v35; // [rsp+150h] [rbp+50h]
  WCHAR CommandLine[264]; // [rsp+160h] [rbp+60h] BYREF

  ExitCode = 0;
  v27[0] = 0;
  if ( a5 == (void *)-1LL )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( !hSourceHandle )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  memset(&hObject, 0, sizeof(hObject));
  v9 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(v27);
  CurrentProcess = GetCurrentProcess();
  v11 = GetCurrentProcess();
  if ( !DuplicateHandle(v11, hSourceHandle, CurrentProcess, v9, 0, 1, 2u) )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 53;
LABEL_11:
      v16 = v13;
LABEL_12:
      WPP_SF_d(v14[2], v15, &WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids, v16);
      goto LABEL_47;
    }
    goto LABEL_47;
  }
  LODWORD(bInheritHandle) = a4;
  LODWORD(dwDesiredAccess) = a3;
  v17 = StringCchPrintfW(
          CommandLine,
          0x104u,
          L"werfaultsecure.exe /h /s /pid %u /tid %u /type %u /encfile %I64d /cancel %I64d",
          a2,
          dwDesiredAccess,
          bInheritHandle,
          a5,
          v27[0]);
  v13 = v17;
  if ( v17 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 54;
      v16 = (unsigned int)v17;
      goto LABEL_12;
    }
    goto LABEL_47;
  }
  memset_0(&v29, 0, 0x68u);
  *(_OWORD *)&StartupInfo.cb = v29;
  StartupInfo.lpTitle = (LPWSTR)*((_QWORD *)&v30 + 1);
  *(_OWORD *)&StartupInfo.dwX = v31;
  *(_OWORD *)&StartupInfo.dwXCountChars = v32;
  *(_OWORD *)&StartupInfo.wShowWindow = v33;
  *(_OWORD *)&StartupInfo.hStdInput = v34;
  StartupInfo.hStdError = v35;
  StartupInfo.cb = 104;
  StartupInfo.lpDesktop = (LPWSTR)&unk_18004FE4C;
  if ( hObject.hProcess )
    CloseHandle(hObject.hProcess);
  if ( hObject.hThread )
    CloseHandle(hObject.hThread);
  memset(&hObject, 0, sizeof(hObject));
  if ( CreateProcessW(0, CommandLine, 0, 0, 1, 0x40000u, 0, 0, &StartupInfo, &hObject) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        56,
        &WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids,
        hObject.dwProcessId);
    if ( WaitForSingleObject(hObject.hProcess, 0xFFFFFFFF) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids);
      v19 = GetLastError();
      v13 = v19;
      if ( v19 > 0 )
        v13 = (unsigned __int16)v19 | 0x80070000;
      goto LABEL_47;
    }
    if ( !GetExitCodeProcess(hObject.hProcess, &ExitCode) )
    {
      v20 = GetLastError();
      if ( v20 > 0 )
        v20 = (unsigned __int16)v20 | 0x80070000;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_46;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_43:
        if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 8) != 0 )
          WPP_SF_d(v21[2], 59, &WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids, ExitCode);
LABEL_46:
        v13 = ExitCode;
        goto LABEL_47;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        &WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids,
        (unsigned int)v20);
    }
    v21 = WPP_GLOBAL_Control;
    goto LABEL_43;
  }
  v18 = GetLastError();
  v13 = v18;
  if ( v18 > 0 )
    v13 = (unsigned __int16)v18 | 0x80070000;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v15 = 55;
    goto LABEL_11;
  }
LABEL_47:
  if ( hObject.hProcess )
    CloseHandle(hObject.hProcess);
  if ( hObject.hThread )
    CloseHandle(hObject.hThread);
  memset(&hObject, 0, sizeof(hObject));
  if ( (unsigned __int64)v27[0] + 1 > 1 )
    CloseHandle(v27[0]);
  return v13;
}

```

## disassembly

```asm
0x1800096cc  mov     [rsp-8+arg_0], rbx
0x1800096d1  push    rbp
0x1800096d2  push    rsi
0x1800096d3  push    rdi
0x1800096d4  push    r12
0x1800096d6  push    r13
0x1800096d8  push    r14
0x1800096da  push    r15
0x1800096dc  lea     rbp, [rsp-280h]
0x1800096e4  sub     rsp, 380h
0x1800096eb  mov     rax, cs:__security_cookie
0x1800096f2  xor     rax, rsp
0x1800096f5  mov     [rbp+2B0h+var_40], rax
0x1800096fc  mov     r13d, r9d
0x1800096ff  mov     r12d, r8d
0x180009702  mov     r15d, edx
0x180009705  mov     r14, [rbp+2B0h+arg_20]
0x18000970c  mov     rsi, [rbp+2B0h+hSourceHandle]
0x180009713  mov     [rsp+3B0h+ExitCode], 0
0x18000971b  mov     [rsp+3B0h+var_340], 0
0x180009724  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180009728  jnz     short loc_18000972F
0x18000972a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000972f  test    rsi, rsi
0x180009732  jnz     short loc_180009739
0x180009734  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009739  xorps   xmm0, xmm0
0x18000973c  xor     eax, eax
0x18000973e  movups  xmmword ptr [rsp+3B0h+hObject], xmm0
0x180009743  mov     [rsp+3B0h+var_348], rax
0x180009748  lea     rcx, [rsp+3B0h+var_340]
0x18000974d  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180009752  mov     rdi, rax
0x180009755  call    cs:__imp_GetCurrentProcess
0x18000975b  mov     rbx, rax
0x18000975e  call    cs:__imp_GetCurrentProcess
0x180009764  mov     [rsp+3B0h+dwOptions], 2; dwOptions
0x18000976c  mov     dword ptr [rsp+3B0h+bInheritHandle], 1; bInheritHandle
0x180009774  mov     dword ptr [rsp+3B0h+dwDesiredAccess], 0; dwDesiredAccess
0x18000977c  mov     r9, rdi; lpTargetHandle
0x18000977f  mov     r8, rbx; hTargetProcessHandle
0x180009782  mov     rdx, rsi; hSourceHandle
0x180009785  mov     rcx, rax; hSourceProcessHandle
0x180009788  call    cs:__imp_DuplicateHandle
0x18000978e  test    eax, eax
0x180009790  jnz     short loc_1800097E5
0x180009792  call    cs:__imp_GetLastError
0x180009798  mov     ebx, eax
0x18000979a  test    eax, eax
0x18000979c  jle     short loc_1800097A7
0x18000979e  movzx   ebx, ax
0x1800097a1  or      ebx, 80070000h
0x1800097a7  lea     rdi, WPP_GLOBAL_Control
0x1800097ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097b5  cmp     rcx, rdi
0x1800097b8  jz      loc_180009A66
0x1800097be  test    byte ptr [rcx+1Ch], 1
0x1800097c2  jz      loc_180009A66
0x1800097c8  mov     edx, 35h ; '5'
0x1800097cd  mov     r9d, ebx
0x1800097d0  lea     r8, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids
0x1800097d7  mov     rcx, [rcx+10h]
0x1800097db  call    WPP_SF_d
0x1800097e0  jmp     loc_180009A66
0x1800097e5  mov     rax, [rsp+3B0h+var_340]
0x1800097ea  mov     [rsp+3B0h+lpCurrentDirectory], rax
0x1800097ef  mov     qword ptr [rsp+3B0h+dwOptions], r14
0x1800097f4  mov     dword ptr [rsp+3B0h+bInheritHandle], r13d
0x1800097f9  mov     dword ptr [rsp+3B0h+dwDesiredAccess], r12d
0x1800097fe  mov     r9d, r15d
0x180009801  lea     r8, aWerfaultsecure_0; "werfaultsecure.exe /h /s /pid %u /tid %"...
0x180009808  mov     edx, 104h; unsigned __int64
0x18000980d  lea     rcx, [rbp+2B0h+CommandLine]; wchar_t *
0x180009811  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180009816  mov     ebx, eax
0x180009818  test    eax, eax
0x18000981a  jns     short loc_180009847
0x18000981c  lea     rdi, WPP_GLOBAL_Control
0x180009823  mov     rcx, cs:WPP_GLOBAL_Control
0x18000982a  cmp     rcx, rdi
0x18000982d  jz      loc_180009A66
0x180009833  test    byte ptr [rcx+1Ch], 1
0x180009837  jz      loc_180009A66
0x18000983d  mov     edx, 36h ; '6'
0x180009842  mov     r9d, eax
0x180009845  jmp     short loc_1800097D0
0x180009847  mov     ebx, 68h ; 'h'
0x18000984c  mov     r8d, ebx; Size
0x18000984f  xor     edx, edx; Val
0x180009851  lea     rcx, [rbp+2B0h+var_2C0]; void *
0x180009855  call    memset_0
0x18000985a  movups  xmm0, [rbp+2B0h+var_2C0]
0x18000985e  movaps  xmmword ptr [rbp+2B0h+StartupInfo.cb], xmm0
0x180009862  movups  xmm1, [rbp+2B0h+var_2B0]
0x180009866  movaps  xmmword ptr [rbp+2B0h+StartupInfo.lpDesktop], xmm1
0x18000986a  movups  xmm0, [rbp+2B0h+var_2A0]
0x18000986e  movaps  xmmword ptr [rbp+2B0h+StartupInfo.dwX], xmm0
0x180009872  movups  xmm1, [rbp+2B0h+var_290]
0x180009876  movaps  xmmword ptr [rbp+2B0h+StartupInfo.dwXCountChars], xmm1
0x18000987a  movups  xmm0, [rbp+2B0h+var_280]
0x18000987e  movaps  xmmword ptr [rbp+2B0h+StartupInfo.wShowWindow], xmm0
0x180009882  movups  xmm1, [rbp+2B0h+var_270]
0x180009886  movaps  xmmword ptr [rbp+2B0h+StartupInfo.hStdInput], xmm1
0x18000988a  movsd   xmm0, [rbp+2B0h+var_260]
0x18000988f  movsd   [rbp+2B0h+StartupInfo.hStdError], xmm0
0x180009894  mov     [rbp+2B0h+StartupInfo.cb], ebx
0x180009897  lea     rax, unk_18004FE4C
0x18000989e  mov     [rbp+2B0h+StartupInfo.lpDesktop], rax
0x1800098a2  mov     rcx, [rsp+3B0h+hObject]; hObject
0x1800098a7  test    rcx, rcx
0x1800098aa  jz      short loc_1800098B2
0x1800098ac  call    cs:__imp_CloseHandle
0x1800098b2  mov     rcx, [rsp+3B0h+hObject+8]; hObject
0x1800098b7  test    rcx, rcx
0x1800098ba  jz      short loc_1800098C2
0x1800098bc  call    cs:__imp_CloseHandle
0x1800098c2  xorps   xmm0, xmm0
0x1800098c5  xor     eax, eax
0x1800098c7  movups  xmmword ptr [rsp+3B0h+hObject], xmm0
0x1800098cc  mov     [rsp+3B0h+var_348], rax
0x1800098d1  lea     rax, [rsp+3B0h+hObject]
0x1800098d6  mov     [rsp+3B0h+lpProcessInformation], rax; lpProcessInformation
0x1800098db  lea     rax, [rbp+2B0h+StartupInfo]
0x1800098df  mov     [rsp+3B0h+lpStartupInfo], rax; lpStartupInfo
0x1800098e4  mov     [rsp+3B0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1800098ed  mov     qword ptr [rsp+3B0h+dwOptions], 0; lpEnvironment
0x1800098f6  mov     dword ptr [rsp+3B0h+bInheritHandle], 40000h; dwCreationFlags
0x1800098fe  mov     dword ptr [rsp+3B0h+dwDesiredAccess], 1; bInheritHandles
0x180009906  xor     r9d, r9d; lpThreadAttributes
0x180009909  xor     r8d, r8d; lpProcessAttributes
0x18000990c  lea     rdx, [rbp+2B0h+CommandLine]; lpCommandLine
0x180009910  xor     ecx, ecx; lpApplicationName
0x180009912  call    cs:__imp_CreateProcessW
0x180009918  test    eax, eax
0x18000991a  jnz     short loc_18000995C
0x18000991c  call    cs:__imp_GetLastError
0x180009922  mov     ebx, eax
0x180009924  test    eax, eax
0x180009926  jle     short loc_180009931
0x180009928  movzx   ebx, ax
0x18000992b  or      ebx, 80070000h
0x180009931  lea     rdi, WPP_GLOBAL_Control
0x180009938  mov     rcx, cs:WPP_GLOBAL_Control
0x18000993f  cmp     rcx, rdi
0x180009942  jz      loc_180009A66
0x180009948  test    byte ptr [rcx+1Ch], 1
0x18000994c  jz      loc_180009A66
0x180009952  mov     edx, 37h ; '7'
0x180009957  jmp     loc_1800097CD
0x18000995c  lea     rdi, WPP_GLOBAL_Control
0x180009963  mov     rcx, cs:WPP_GLOBAL_Control
0x18000996a  cmp     rcx, rdi
0x18000996d  jz      short loc_18000998F
0x18000996f  test    byte ptr [rcx+1Ch], 8
0x180009973  jz      short loc_18000998F
0x180009975  mov     edx, 38h ; '8'
0x18000997a  mov     r9d, dword ptr [rsp+3B0h+var_348]
0x18000997f  lea     r8, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids
0x180009986  mov     rcx, [rcx+10h]
0x18000998a  call    WPP_SF_d
0x18000998f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009992  mov     rcx, [rsp+3B0h+hObject]; hHandle
0x180009997  call    cs:__imp_WaitForSingleObject
0x18000999d  test    eax, eax
0x18000999f  jz      short loc_1800099E6
0x1800099a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099a8  cmp     rcx, rdi
0x1800099ab  jz      short loc_1800099C8
0x1800099ad  test    byte ptr [rcx+1Ch], 1
0x1800099b1  jz      short loc_1800099C8
0x1800099b3  mov     edx, 39h ; '9'
0x1800099b8  lea     r8, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids
0x1800099bf  mov     rcx, [rcx+10h]
0x1800099c3  call    WPP_SF_
0x1800099c8  call    cs:__imp_GetLastError
0x1800099ce  mov     ebx, eax
0x1800099d0  test    eax, eax
0x1800099d2  jle     loc_180009A66
0x1800099d8  movzx   ebx, ax
0x1800099db  or      ebx, 80070000h
0x1800099e1  jmp     loc_180009A66
0x1800099e6  lea     rdx, [rsp+3B0h+ExitCode]; lpExitCode
0x1800099eb  mov     rcx, [rsp+3B0h+hObject]; hProcess
0x1800099f0  call    cs:__imp_GetExitCodeProcess
0x1800099f6  test    eax, eax
0x1800099f8  jnz     short loc_180009A36
0x1800099fa  call    cs:__imp_GetLastError
0x180009a00  test    eax, eax
0x180009a02  jle     short loc_180009A0C
0x180009a04  movzx   eax, ax
0x180009a07  or      eax, 80070000h
0x180009a0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a13  cmp     rcx, rdi
0x180009a16  jz      short loc_180009A62
0x180009a18  test    byte ptr [rcx+1Ch], 1
0x180009a1c  jz      short loc_180009A3D
0x180009a1e  mov     edx, 3Ah ; ':'
0x180009a23  mov     r9d, eax
0x180009a26  lea     r8, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids
0x180009a2d  mov     rcx, [rcx+10h]
0x180009a31  call    WPP_SF_d
0x180009a36  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a3d  cmp     rcx, rdi
0x180009a40  jz      short loc_180009A62
0x180009a42  test    byte ptr [rcx+1Ch], 8
0x180009a46  jz      short loc_180009A62
0x180009a48  mov     edx, 3Bh ; ';'
0x180009a4d  mov     r9d, [rsp+3B0h+ExitCode]
0x180009a52  lea     r8, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids
0x180009a59  mov     rcx, [rcx+10h]
0x180009a5d  call    WPP_SF_d
0x180009a62  mov     ebx, [rsp+3B0h+ExitCode]
0x180009a66  mov     rcx, [rsp+3B0h+hObject]; hObject
0x180009a6b  test    rcx, rcx
0x180009a6e  jz      short loc_180009A76
0x180009a70  call    cs:__imp_CloseHandle
0x180009a76  mov     rcx, [rsp+3B0h+hObject+8]; hObject
0x180009a7b  test    rcx, rcx
0x180009a7e  jz      short loc_180009A86
0x180009a80  call    cs:__imp_CloseHandle
0x180009a86  xorps   xmm0, xmm0
0x180009a89  xor     eax, eax
0x180009a8b  movups  xmmword ptr [rsp+3B0h+hObject], xmm0
0x180009a90  mov     [rsp+3B0h+var_348], rax
0x180009a95  mov     rcx, [rsp+3B0h+var_340]; hObject
0x180009a9a  lea     rax, [rcx+1]
0x180009a9e  cmp     rax, 1
0x180009aa2  jbe     short loc_180009AAA
0x180009aa4  call    cs:__imp_CloseHandle
0x180009aaa  mov     eax, ebx
0x180009aac  mov     rcx, [rbp+2B0h+var_40]
0x180009ab3  xor     rcx, rsp; StackCookie
0x180009ab6  call    __security_check_cookie
0x180009abb  mov     rbx, [rsp+3B0h+arg_0]
0x180009ac3  add     rsp, 380h
0x180009aca  pop     r15
0x180009acc  pop     r14
0x180009ace  pop     r13
0x180009ad0  pop     r12
0x180009ad2  pop     rdi
0x180009ad3  pop     rsi
0x180009ad4  pop     rbp
0x180009ad5  retn
```
