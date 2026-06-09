# RunAction(ushort const *,ushort const *,void *,ushort const *,ulong,void *)

- ea: `0x1800259d8`
- end: `0x180025de4`
- name: `?RunAction@@YAXPEBG0PEAX0K1@Z`
- size: `1036`
- prototype: `void __fastcall(unsigned __int16 *lpApplicationName, const unsigned __int16 *, WCHAR *, unsigned __int16 *, unsigned int, HANDLE hToken)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180019cb8`
- `0x180025dec`

## callees

- `0x180005878`
- `0x18002354c`
- `0x1800259d8`
- `0x18006101a`
- `0x180061060`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180025a75`
- `ntdll!RtlInitUnicodeString` at `0x180025a75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d07`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180025cb9`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180025cb9`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180025cf9`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180025cf9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025d8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025d98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025d8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025d98`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180025da8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180025da8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180025db7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180025db7`
- `iisutil!PuDbgPrint` at `0x180025c1a`
- `iisutil!PuDbgPrint` at `0x180025c1a`
- `iisutil!PuDbgPrintError` at `0x180025aca`
- `iisutil!PuDbgPrintError` at `0x180025d50`
- `iisutil!PuDbgPrintError` at `0x180025aca`
- `iisutil!PuDbgPrintError` at `0x180025d50`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180025a19`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180025a19`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180025a86`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180025a86`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180025adc`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180025b0f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180025b41`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180025adc`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180025b0f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180025b41`

## string_xrefs

- `0x180025abf`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x180025bfc`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`
- `0x180025d49`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\worker_process.cxx`

## pseudocode

```c
void __fastcall RunAction(
        unsigned __int16 *lpApplicationName,
        const unsigned __int16 *a2,
        WCHAR *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        HANDLE hToken)
{
  unsigned __int16 v10; // ax
  LPCWSTR v11; // rcx
  signed int v12; // ebx
  struct _STARTUPINFOW *p_StartupInfo; // rax
  __int64 v14; // rcx
  struct _PROCESS_INFORMATION *p_ProcessInformation; // rax
  __int64 v16; // rcx
  unsigned __int16 *v17; // rcx
  unsigned __int16 **v18; // r9
  unsigned int v19; // edx
  BOOL v20; // eax
  signed int LastError; // eax
  PWSTR Buffer; // rcx
  unsigned int lpThreadAttributes; // [rsp+20h] [rbp-E0h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v26[2]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v27[3]; // [rsp+98h] [rbp-68h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v29[32]; // [rsp+120h] [rbp+20h] BYREF
  PCWSTR SourceString; // [rsp+140h] [rbp+40h]

  STRU::STRU((STRU *)v29);
  DestinationString = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !lpApplicationName )
    goto LABEL_49;
  v10 = *lpApplicationName;
  v11 = lpApplicationName;
  while ( v10 == 32 )
    v10 = *++v11;
  if ( !v10 )
    goto LABEL_49;
  RtlInitUnicodeString(&DestinationString, 0);
  v12 = STRU::Copy((STRU *)v29, L"\"");
  if ( v12 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
        9178,
        "RunAction",
        v12,
        "Adding first quote on action failed.\n");
LABEL_43:
    Buffer = (PWSTR)&::SourceString;
    v19 = a5;
    v18 = (unsigned __int16 **)v27;
    v27[0] = a4;
    lpThreadAttributes = v12;
    if ( DestinationString.Buffer )
      Buffer = DestinationString.Buffer;
    v27[1] = Buffer;
LABEL_34:
    WEB_ADMIN_SERVICE::LogEvent(g_pWebAdminService, v19, 2u, (const unsigned __int16 **const)v18, lpThreadAttributes);
    goto LABEL_47;
  }
  v12 = STRU::Append((STRU *)v29, lpApplicationName);
  if ( v12 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
        9190,
        "RunAction",
        v12,
        "Adding executable to action failed\n");
    goto LABEL_43;
  }
  v12 = STRU::Append((STRU *)v29, L"\" ");
  if ( v12 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
        9202,
        "RunAction",
        v12,
        "Adding second quote on action failed\n");
    goto LABEL_43;
  }
  v12 = STRU::Append((STRU *)v29, a2);
  if ( v12 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
        9214,
        "RunAction",
        v12,
        "Adding parameters to orphan action failed\n");
    goto LABEL_43;
  }
  v12 = ExpandCommandLinePiece(SourceString, &DestinationString, a3);
  if ( v12 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
        9230,
        "RunAction",
        v12,
        "Expanding the string failed\n");
    goto LABEL_43;
  }
  p_StartupInfo = &StartupInfo;
  v14 = 104;
  do
  {
    LOBYTE(p_StartupInfo->cb) = 0;
    p_StartupInfo = (struct _STARTUPINFOW *)((char *)p_StartupInfo + 1);
    --v14;
  }
  while ( v14 );
  StartupInfo.cb = 104;
  p_ProcessInformation = &ProcessInformation;
  v16 = 24;
  do
  {
    LOBYTE(p_ProcessInformation->hProcess) = 0;
    p_ProcessInformation = (struct _PROCESS_INFORMATION *)((char *)p_ProcessInformation + 1);
    --v16;
  }
  while ( v16 );
  if ( (g_dwDebugFlags & 0x410000) != 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
      9248,
      "RunAction",
      "Running action '%S'\n",
      DestinationString.Buffer);
  if ( APP_POOL::sm_dwIdentitiesAllowedValue == -1 || (APP_POOL::sm_dwIdentitiesAllowedValue & 1) != 0 )
  {
    v20 = CreateProcessW(
            lpApplicationName,
            DestinationString.Buffer,
            0,
            0,
            0,
            0x10u,
            0,
            0,
            &StartupInfo,
            &ProcessInformation);
  }
  else
  {
    if ( !hToken )
    {
      v17 = (unsigned __int16 *)&::SourceString;
      v26[1] = a4;
      lpThreadAttributes = 0;
      v18 = v26;
      if ( DestinationString.Buffer )
        v17 = DestinationString.Buffer;
      v19 = -1073736624;
      v26[0] = v17;
      goto LABEL_34;
    }
    v20 = CreateProcessAsUserW(
            hToken,
            lpApplicationName,
            DestinationString.Buffer,
            0,
            0,
            0,
            0x10u,
            0,
            0,
            &StartupInfo,
            &ProcessInformation);
  }
  if ( !v20 )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\worker_process.cxx",
        9343,
        "RunAction",
        v12,
        "Could not run orphan action\n");
    if ( v12 >= 0 )
      goto LABEL_47;
    goto LABEL_43;
  }
  CloseHandle(ProcessInformation.hThread);
  CloseHandle(ProcessInformation.hProcess);
LABEL_47:
  if ( DestinationString.Buffer )
  {
    GlobalFree(DestinationString.Buffer);
    DestinationString.Buffer = 0;
  }
LABEL_49:
  STRU::~STRU((STRU *)v29);
}

```

## disassembly

```asm
0x1800259d8  mov     [rsp-8+arg_18], rbx
0x1800259dd  push    rbp
0x1800259de  push    rsi
0x1800259df  push    rdi
0x1800259e0  push    r12
0x1800259e2  push    r13
0x1800259e4  push    r14
0x1800259e6  push    r15
0x1800259e8  lea     rbp, [rsp-60h]
0x1800259ed  sub     rsp, 160h
0x1800259f4  mov     rax, cs:__security_cookie
0x1800259fb  xor     rax, rsp
0x1800259fe  mov     [rbp+90h+var_38], rax
0x180025a02  mov     r15, [rbp+90h+hToken]
0x180025a09  mov     rdi, rcx
0x180025a0c  lea     rcx, [rbp+90h+var_70]
0x180025a10  mov     r12, r9
0x180025a13  mov     r14, r8
0x180025a16  mov     rsi, rdx
0x180025a19  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180025a1f  xor     edx, edx; Val
0x180025a21  lea     rcx, [rbp+90h+StartupInfo]; void *
0x180025a25  xorps   xmm0, xmm0
0x180025a28  movups  xmmword ptr [rsp+190h+DestinationString.Length], xmm0
0x180025a2d  lea     r8d, [rdx+68h]; Size
0x180025a31  call    memset_0
0x180025a36  xor     eax, eax
0x180025a38  xor     r13d, r13d
0x180025a3b  mov     qword ptr [rbp+90h+ProcessInformation.dwProcessId], rax
0x180025a3f  xorps   xmm0, xmm0
0x180025a42  movups  xmmword ptr [rsp+190h+ProcessInformation.hProcess], xmm0
0x180025a47  test    rdi, rdi
0x180025a4a  jz      loc_180025DB3
0x180025a50  movzx   eax, word ptr [rdi]
0x180025a53  mov     rcx, rdi
0x180025a56  jmp     short loc_180025A5F
0x180025a58  lea     rcx, [rcx+2]
0x180025a5c  movzx   eax, word ptr [rcx]
0x180025a5f  cmp     ax, 20h ; ' '
0x180025a63  jz      short loc_180025A58
0x180025a65  test    ax, ax
0x180025a68  jz      loc_180025DB3
0x180025a6e  xor     edx, edx; SourceString
0x180025a70  lea     rcx, [rsp+190h+DestinationString]; DestinationString
0x180025a75  call    cs:__imp_RtlInitUnicodeString
0x180025a7b  lea     rdx, asc_18006EF8C; "\""
0x180025a82  lea     rcx, [rbp+90h+var_70]
0x180025a86  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180025a8c  mov     ebx, eax
0x180025a8e  test    eax, eax
0x180025a90  jns     short loc_180025AD5
0x180025a92  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180025a99  jz      loc_180025D5A
0x180025a9f  lea     rax, aAddingFirstQuo; "Adding first quote on action failed.\n"
0x180025aa6  mov     r8d, 23DAh
0x180025aac  mov     rcx, cs:g_pDebug
0x180025ab3  lea     r9, aRunaction; "RunAction"
0x180025aba  mov     qword ptr [rsp+190h+bInheritHandles], rax
0x180025abf  lea     rdx, aServercommonIn_24; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180025ac6  mov     dword ptr [rsp+190h+lpThreadAttributes], ebx
0x180025aca  call    cs:__imp_PuDbgPrintError
0x180025ad0  jmp     loc_180025D5A
0x180025ad5  mov     rdx, rdi
0x180025ad8  lea     rcx, [rbp+90h+var_70]
0x180025adc  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180025ae2  mov     ebx, eax
0x180025ae4  test    eax, eax
0x180025ae6  jns     short loc_180025B04
0x180025ae8  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180025aef  jz      loc_180025D5A
0x180025af5  lea     rax, aAddingExecutab; "Adding executable to action failed\n"
0x180025afc  mov     r8d, 23E6h
0x180025b02  jmp     short loc_180025AAC
0x180025b04  lea     rdx, asc_1800704EC; "\" "
0x180025b0b  lea     rcx, [rbp+90h+var_70]
0x180025b0f  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180025b15  mov     ebx, eax
0x180025b17  test    eax, eax
0x180025b19  jns     short loc_180025B3A
0x180025b1b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180025b22  jz      loc_180025D5A
0x180025b28  lea     rax, aAddingSecondQu; "Adding second quote on action failed\n"
0x180025b2f  mov     r8d, 23F2h
0x180025b35  jmp     loc_180025AAC
0x180025b3a  mov     rdx, rsi
0x180025b3d  lea     rcx, [rbp+90h+var_70]
0x180025b41  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180025b47  mov     ebx, eax
0x180025b49  test    eax, eax
0x180025b4b  jns     short loc_180025B6C
0x180025b4d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180025b54  jz      loc_180025D5A
0x180025b5a  lea     rax, aAddingParamete; "Adding parameters to orphan action fail"...
0x180025b61  mov     r8d, 23FEh
0x180025b67  jmp     loc_180025AAC
0x180025b6c  mov     rcx, [rbp+90h+SourceString]; SourceString
0x180025b70  lea     rdx, [rsp+190h+DestinationString]; Destination
0x180025b75  mov     r8, r14; Environment
0x180025b78  call    ?ExpandCommandLinePiece@@YAJPEAGPEAU_UNICODE_STRING@@PEAX@Z; ExpandCommandLinePiece(ushort *,_UNICODE_STRING *,void *)
0x180025b7d  mov     ebx, eax
0x180025b7f  test    eax, eax
0x180025b81  jns     short loc_180025BA2
0x180025b83  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180025b8a  jz      loc_180025D5A
0x180025b90  lea     rax, aExpandingTheSt; "Expanding the string failed\n"
0x180025b97  mov     r8d, 240Eh
0x180025b9d  jmp     loc_180025AAC
0x180025ba2  mov     edx, 68h ; 'h'
0x180025ba7  lea     rax, [rbp+90h+StartupInfo]
0x180025bab  mov     ecx, edx
0x180025bad  mov     [rax], r13b
0x180025bb0  inc     rax
0x180025bb3  sub     rcx, 1
0x180025bb7  jnz     short loc_180025BAD
0x180025bb9  mov     [rbp+90h+StartupInfo.cb], edx
0x180025bbc  lea     rax, [rsp+190h+ProcessInformation]
0x180025bc1  mov     ecx, 18h
0x180025bc6  mov     [rax], r13b
0x180025bc9  inc     rax
0x180025bcc  sub     rcx, 1
0x180025bd0  jnz     short loc_180025BC6
0x180025bd2  mov     eax, cs:g_dwDebugFlags
0x180025bd8  test    eax, 410000h
0x180025bdd  setnz   cl
0x180025be0  test    al, 3
0x180025be2  setnz   al
0x180025be5  test    al, cl
0x180025be7  jz      short loc_180025C20
0x180025be9  mov     rax, [rsp+190h+DestinationString.Buffer]
0x180025bee  lea     r9, aRunaction; "RunAction"
0x180025bf5  mov     rcx, cs:g_pDebug
0x180025bfc  lea     rdx, aServercommonIn_24; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180025c03  mov     qword ptr [rsp+190h+bInheritHandles], rax
0x180025c08  mov     r8d, 2420h
0x180025c0e  lea     rax, aRunningActionS; "Running action '%S'\n"
0x180025c15  mov     [rsp+190h+lpThreadAttributes], rax
0x180025c1a  call    cs:__imp_PuDbgPrint
0x180025c20  mov     eax, cs:?sm_dwIdentitiesAllowedValue@APP_POOL@@0KA; ulong APP_POOL::sm_dwIdentitiesAllowedValue
0x180025c26  cmp     eax, 0FFFFFFFFh
0x180025c29  jz      loc_180025CC1
0x180025c2f  test    al, 1
0x180025c31  jnz     loc_180025CC1
0x180025c37  test    r15, r15
0x180025c3a  jnz     short loc_180025C7C
0x180025c3c  mov     rax, [rsp+190h+DestinationString.Buffer]
0x180025c41  lea     rcx, SourceString
0x180025c48  test    rax, rax
0x180025c4b  mov     [rbp+90h+var_100], r12
0x180025c4f  mov     dword ptr [rsp+190h+lpThreadAttributes], r13d; unsigned int
0x180025c54  lea     r9, [rbp+90h+var_108]; unsigned __int16 **
0x180025c58  cmovnz  rcx, rax
0x180025c5c  mov     edx, 0C0001450h; unsigned int
0x180025c61  mov     [rbp+90h+var_108], rcx
0x180025c65  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x180025c6c  mov     r8d, 2; unsigned __int16
0x180025c72  call    ?LogEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180025c77  jmp     loc_180025D9E
0x180025c7c  mov     r8, [rsp+190h+DestinationString.Buffer]; lpCommandLine
0x180025c81  lea     rax, [rsp+190h+ProcessInformation]
0x180025c86  mov     [rsp+190h+lpProcessInformation], rax; lpProcessInformation
0x180025c8b  xor     r9d, r9d; lpProcessAttributes
0x180025c8e  lea     rax, [rbp+90h+StartupInfo]
0x180025c92  mov     rdx, rdi; lpApplicationName
0x180025c95  mov     [rsp+190h+lpStartupInfo], rax; lpStartupInfo
0x180025c9a  mov     rcx, r15; hToken
0x180025c9d  mov     [rsp+190h+lpCurrentDirectory], r13; lpCurrentDirectory
0x180025ca2  mov     [rsp+190h+lpEnvironment], r13; lpEnvironment
0x180025ca7  mov     [rsp+190h+dwCreationFlags], 10h; dwCreationFlags
0x180025caf  mov     [rsp+190h+bInheritHandles], r13d; bInheritHandles
0x180025cb4  mov     [rsp+190h+lpThreadAttributes], r13; lpThreadAttributes
0x180025cb9  call    cs:__imp_CreateProcessAsUserW
0x180025cbf  jmp     short loc_180025CFF
0x180025cc1  mov     rdx, [rsp+190h+DestinationString.Buffer]; lpCommandLine
0x180025cc6  lea     rax, [rsp+190h+ProcessInformation]
0x180025ccb  mov     [rsp+190h+lpStartupInfo], rax; lpProcessInformation
0x180025cd0  xor     r9d, r9d; lpThreadAttributes
0x180025cd3  lea     rax, [rbp+90h+StartupInfo]
0x180025cd7  xor     r8d, r8d; lpProcessAttributes
0x180025cda  mov     [rsp+190h+lpCurrentDirectory], rax; lpStartupInfo
0x180025cdf  mov     rcx, rdi; lpApplicationName
0x180025ce2  mov     [rsp+190h+lpEnvironment], r13; lpCurrentDirectory
0x180025ce7  mov     qword ptr [rsp+190h+dwCreationFlags], r13; lpEnvironment
0x180025cec  mov     [rsp+190h+bInheritHandles], 10h; dwCreationFlags
0x180025cf4  mov     dword ptr [rsp+190h+lpThreadAttributes], r13d; bInheritHandles
0x180025cf9  call    cs:__imp_CreateProcessW
0x180025cff  test    eax, eax
0x180025d01  jnz     loc_180025D88
0x180025d07  call    cs:__imp_GetLastError
0x180025d0d  mov     ebx, eax
0x180025d0f  test    eax, eax
0x180025d11  jle     short loc_180025D1C
0x180025d13  movzx   ebx, ax
0x180025d16  or      ebx, 80070000h
0x180025d1c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180025d23  jz      short loc_180025D56
0x180025d25  mov     rcx, cs:g_pDebug
0x180025d2c  lea     rax, aCouldNotRunOrp; "Could not run orphan action\n"
0x180025d33  mov     qword ptr [rsp+190h+bInheritHandles], rax
0x180025d38  lea     r9, aRunaction; "RunAction"
0x180025d3f  mov     r8d, 247Fh
0x180025d45  mov     dword ptr [rsp+190h+lpThreadAttributes], ebx
0x180025d49  lea     rdx, aServercommonIn_24; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180025d50  call    cs:__imp_PuDbgPrintError
0x180025d56  test    ebx, ebx
0x180025d58  jns     short loc_180025D9E
0x180025d5a  mov     rax, [rsp+190h+DestinationString.Buffer]
0x180025d5f  lea     rcx, SourceString
0x180025d66  mov     edx, [rbp+90h+arg_20]
0x180025d6c  lea     r9, [rbp+90h+var_F8]
0x180025d70  test    rax, rax
0x180025d73  mov     [rbp+90h+var_F8], r12
0x180025d77  mov     dword ptr [rsp+190h+lpThreadAttributes], ebx
0x180025d7b  cmovnz  rcx, rax
0x180025d7f  mov     [rbp+90h+var_F0], rcx
0x180025d83  jmp     loc_180025C65
0x180025d88  mov     rcx, [rsp+190h+ProcessInformation.hThread]; hObject
0x180025d8d  call    cs:__imp_CloseHandle
0x180025d93  mov     rcx, [rsp+190h+ProcessInformation.hProcess]; hObject
0x180025d98  call    cs:__imp_CloseHandle
0x180025d9e  mov     rcx, [rsp+190h+DestinationString.Buffer]; hMem
0x180025da3  test    rcx, rcx
0x180025da6  jz      short loc_180025DB3
0x180025da8  call    cs:__imp_GlobalFree
0x180025dae  mov     [rsp+190h+DestinationString.Buffer], r13
0x180025db3  lea     rcx, [rbp+90h+var_70]
0x180025db7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180025dbd  mov     rcx, [rbp+90h+var_38]
0x180025dc1  xor     rcx, rsp; StackCookie
0x180025dc4  call    __security_check_cookie
0x180025dc9  mov     rbx, [rsp+190h+arg_18]
0x180025dd1  add     rsp, 160h
0x180025dd8  pop     r15
0x180025dda  pop     r14
0x180025ddc  pop     r13
0x180025dde  pop     r12
0x180025de0  pop     rdi
0x180025de1  pop     rsi
0x180025de2  pop     rbp
0x180025de3  retn
```
