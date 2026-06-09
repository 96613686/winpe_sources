# DsrCmdJoinHelper::GetCloudKerbToken(CLI_EXTENSIONS const &,ushort const *,ushort const *,ushort * *,int *)

- ea: `0x1800ae4a0`
- end: `0x1800ae7cb`
- name: `?GetCloudKerbToken@DsrCmdJoinHelper@@AEAAJAEBUCLI_EXTENSIONS@@PEBG1PEAPEAGPEAH@Z`
- size: `811`
- prototype: `__int64 __fastcall(DsrCmdJoinHelper *__hidden this, const struct CLI_EXTENSIONS *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180027a74`
- `0x1800aee10`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x1800ae4a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800ae748`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800ae748`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800ae6a7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800ae6a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae5d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae631`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae66f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae6b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae713`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae752`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae771`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae5d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae631`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae66f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae6b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae713`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae752`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae771`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800ae660`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800ae660`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ae539`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ae539`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae57e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae627`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae767`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae57e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae627`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ae767`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800ae6f0`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800ae6f0`

## string_xrefs

- `0x1800ae5fb`: `%s: WaitForSingleObject timed out for GetCloudKerbTokenThreadProc`
- `0x1800ae528`: `%s: Check and wait for previous GetCloudKerbTokenThreadProc call to finish...`
- `0x1800ae618`: `%s: Previous GetCloudKerbTokenThreadProc call finished`
- `0x1800ae553`: `%s: WaitForSingleObject returned unexpected wait status 0x%08x for GetCloudKerbTokenThreadProc`
- `0x1800ae4bf`: `DsrCmdJoinHelper::GetCloudKerbToken`
- `0x1800ae6bb`: `%s: CreateThread failed with error code: 0x%08x`
- `0x1800ae6c7`: `%s: Waiting for GetCloudKerbTokenThreadProc to finish...`
- `0x1800ae63a`: `%s: CloseHandle(thread) failed with error code: 0x%08x`
- `0x1800ae77a`: `%s: CloseHandle(thread) failed with error code: 0x%08x`
- `0x1800ae675`: `%s: CreateEventExW failed with error code: 0x%08x`
- `0x1800ae7a5`: `%s: GetCloudKerbTokenThreadProc succeeded`
- `0x1800ae730`: `%s: WaitForMultipleObjects timed out for GetCloudKerbTokenThreadProc`
- `0x1800ae758`: `%s: GetExitCodeThread failed with error code: 0x%08x`
- `0x1800ae799`: `%s: GetCloudKerbTokenThreadProc failed with error code 0x%08x`
- `0x1800ae707`: `%s: WaitForMultipleObjects returned unexpected wait status 0x%08x for GetCloudKerbTokenThreadProc`

## pseudocode

```c
__int64 __fastcall DsrCmdJoinHelper::GetCloudKerbToken(
        HANDLE *this,
        const struct CLI_EXTENSIONS *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 **a5,
        int *a6)
{
  int v10; // r14d
  DWORD v11; // eax
  const unsigned __int16 *v12; // rcx
  DWORD v13; // ebx
  DWORD v14; // eax
  DWORD v16; // eax
  const wchar_t *v17; // r8
  const unsigned __int16 *v18; // rcx
  DWORD LastError; // eax
  DWORD v20; // eax
  const unsigned __int16 *v21; // rcx
  HANDLE Thread; // rax
  DWORD v23; // eax
  HANDLE Handles[2]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD Parameter[6]; // [rsp+40h] [rbp-40h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-10h]
  DWORD v27; // [rsp+B0h] [rbp+30h] BYREF
  DWORD ExitCode; // [rsp+B8h] [rbp+38h] BYREF

  Logger::TraceVerbose((wchar_t *)L"%s started", L"DsrCmdJoinHelper::GetCloudKerbToken");
  v10 = 0;
  Parameter[3] = a5;
  Parameter[1] = a3;
  Parameter[4] = &v27;
  Parameter[2] = a4;
  Parameter[5] = a6;
  v27 = 0;
  ExitCode = 0;
  Parameter[0] = a2;
  hObject = 0;
  if ( !*this )
    goto LABEL_21;
  Logger::TraceVerbose(
    (wchar_t *)L"%s: Check and wait for previous GetCloudKerbTokenThreadProc call to finish...",
    L"DsrCmdJoinHelper::GetCloudKerbToken");
  v11 = WaitForSingleObject(*this, 0xFFFFFFFF);
  switch ( v11 )
  {
    case 0u:
      Logger::TraceVerbose(
        (wchar_t *)L"%s: Previous GetCloudKerbTokenThreadProc call finished",
        L"DsrCmdJoinHelper::GetCloudKerbToken");
LABEL_18:
      if ( !CloseHandle(*this) )
      {
        LastError = GetLastError();
        Logger::TraceWarning(
          (wchar_t *)L"%s: CloseHandle(thread) failed with error code: 0x%08x",
          L"DsrCmdJoinHelper::GetCloudKerbToken",
          LastError);
      }
      *this = 0;
LABEL_21:
      v13 = 0;
      hObject = CreateEventExW(0, 0, 1u, 0x1F0003u);
      if ( !hObject )
      {
        v20 = GetLastError();
        v21 = L"%s: CreateEventExW failed with error code: 0x%08x";
LABEL_23:
        v10 = v20;
        Logger::TraceError(v21, L"DsrCmdJoinHelper::GetCloudKerbToken", v20);
        goto LABEL_44;
      }
      Thread = CreateThread(0, 0, GetCloudKerbTokenThreadProc, Parameter, 0, 0);
      *this = Thread;
      if ( !Thread )
      {
        v20 = GetLastError();
        v21 = L"%s: CreateThread failed with error code: 0x%08x";
        goto LABEL_23;
      }
      Logger::TraceVerbose(
        (wchar_t *)L"%s: Waiting for GetCloudKerbTokenThreadProc to finish...",
        L"DsrCmdJoinHelper::GetCloudKerbToken");
      Handles[0] = *this;
      Handles[1] = hObject;
      v11 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
      if ( v11 )
      {
        if ( v11 != 1 )
        {
          if ( v11 != 258 )
          {
            if ( v11 != -1 )
            {
              v12 = L"%s: WaitForMultipleObjects returned unexpected wait status 0x%08x for GetCloudKerbTokenThreadProc";
              goto LABEL_6;
            }
            v16 = GetLastError();
            v10 = v16;
            if ( !v16 )
              goto LABEL_8;
            v17 = L"WaitForMultipleObjects";
            goto LABEL_14;
          }
          v18 = L"%s: WaitForMultipleObjects timed out for GetCloudKerbTokenThreadProc";
LABEL_16:
          LOWORD(v10) = 1460;
          Logger::TraceError(v18, L"DsrCmdJoinHelper::GetCloudKerbToken");
          goto LABEL_7;
        }
        v13 = v27;
      }
      else
      {
        if ( !GetExitCodeThread(*this, &ExitCode) )
        {
          v20 = GetLastError();
          v21 = L"%s: GetExitCodeThread failed with error code: 0x%08x";
          goto LABEL_23;
        }
        if ( CloseHandle(*this) )
        {
          v23 = GetLastError();
          Logger::TraceWarning(
            (wchar_t *)L"%s: CloseHandle(thread) failed with error code: 0x%08x",
            L"DsrCmdJoinHelper::GetCloudKerbToken",
            v23);
        }
        *this = 0;
        v13 = ExitCode;
      }
      if ( (v13 & 0x80000000) == 0 )
        Logger::TraceVerbose(
          (wchar_t *)L"%s: GetCloudKerbTokenThreadProc succeeded",
          L"DsrCmdJoinHelper::GetCloudKerbToken");
      else
        Logger::TraceError(
          L"%s: GetCloudKerbTokenThreadProc failed with error code 0x%08x",
          L"DsrCmdJoinHelper::GetCloudKerbToken",
          v13);
LABEL_44:
      if ( !v10 )
        goto LABEL_8;
      goto LABEL_45;
    case 0x102u:
      v18 = L"%s: WaitForSingleObject timed out for GetCloudKerbTokenThreadProc";
      goto LABEL_16;
    case 0xFFFFFFFF:
      v16 = GetLastError();
      v10 = v16;
      if ( v16 )
      {
        v17 = L"WaitForSingleObject";
LABEL_14:
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"DsrCmdJoinHelper::GetCloudKerbToken",
          v17,
          v16);
LABEL_45:
        if ( v10 <= 0 )
        {
          v13 = v10;
          goto LABEL_8;
        }
        goto LABEL_7;
      }
      goto LABEL_18;
  }
  v12 = L"%s: WaitForSingleObject returned unexpected wait status 0x%08x for GetCloudKerbTokenThreadProc";
LABEL_6:
  LOWORD(v10) = 1460;
  Logger::TraceError(v12, L"DsrCmdJoinHelper::GetCloudKerbToken", v11);
LABEL_7:
  v13 = (unsigned __int16)v10 | 0x80070000;
LABEL_8:
  if ( hObject && !CloseHandle(hObject) )
  {
    v14 = GetLastError();
    Logger::TraceWarning(
      (wchar_t *)L"%s: CloseHandle(event) failed with error code: 0x%08x",
      L"DsrCmdJoinHelper::GetCloudKerbToken",
      v14);
  }
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"DsrCmdJoinHelper::GetCloudKerbToken", v13);
  return v13;
}

```

## disassembly

```asm
0x1800ae4a0  mov     [rsp-28h+arg_10], rbx
0x1800ae4a5  mov     [rsp-28h+arg_18], rsi
0x1800ae4aa  push    rbp
0x1800ae4ab  push    rdi
0x1800ae4ac  push    r13
0x1800ae4ae  push    r14
0x1800ae4b0  push    r15
0x1800ae4b2  mov     rbp, rsp
0x1800ae4b5  sub     rsp, 80h
0x1800ae4bc  mov     rbx, rdx
0x1800ae4bf  lea     r13, aDsrcmdjoinhelp_0; "DsrCmdJoinHelper::GetCloudKerbToken"
0x1800ae4c6  mov     r15, rcx
0x1800ae4c9  mov     rdx, r13
0x1800ae4cc  lea     rcx, aSStarted; "%s started"
0x1800ae4d3  mov     rsi, r9
0x1800ae4d6  mov     rdi, r8
0x1800ae4d9  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800ae4de  mov     rax, [rbp+arg_20]
0x1800ae4e2  xor     r14d, r14d
0x1800ae4e5  mov     [rbp+var_28], rax
0x1800ae4e9  lea     rax, [rbp+arg_0]
0x1800ae4ed  mov     [rbp+var_38], rdi
0x1800ae4f1  or      edi, 0FFFFFFFFh
0x1800ae4f4  mov     [rbp+var_20], rax
0x1800ae4f8  mov     rax, [rbp+arg_28]
0x1800ae4fc  mov     [rbp+var_30], rsi
0x1800ae500  mov     esi, 102h
0x1800ae505  mov     [rbp+var_18], rax
0x1800ae509  mov     [rbp+arg_0], 0
0x1800ae510  mov     [rbp+ExitCode], r14d
0x1800ae514  mov     [rbp+Parameter], rbx
0x1800ae518  mov     [rbp+hObject], r14
0x1800ae51c  cmp     [r15], r14
0x1800ae51f  jz      loc_1800AE650
0x1800ae525  mov     rdx, r13
0x1800ae528  lea     rcx, aSCheckAndWaitF; "%s: Check and wait for previous GetClou"...
0x1800ae52f  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800ae534  mov     rcx, [r15]; hHandle
0x1800ae537  mov     edx, edi; dwMilliseconds
0x1800ae539  call    cs:__imp_WaitForSingleObject
0x1800ae53f  test    eax, eax
0x1800ae541  jz      loc_1800AE615
0x1800ae547  cmp     eax, esi
0x1800ae549  jz      loc_1800AE5FB
0x1800ae54f  cmp     eax, edi
0x1800ae551  jz      short loc_1800AE5D0
0x1800ae553  lea     rcx, aSWaitforsingle_12; "%s: WaitForSingleObject returned unexpe"...
0x1800ae55a  mov     rdx, r13
0x1800ae55d  mov     r8d, eax
0x1800ae560  mov     r14d, 5B4h
0x1800ae566  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800ae56b  movzx   ebx, r14w
0x1800ae56f  or      ebx, 80070000h
0x1800ae575  mov     rcx, [rbp+hObject]; hObject
0x1800ae579  test    rcx, rcx
0x1800ae57c  jz      short loc_1800AE5A0
0x1800ae57e  call    cs:__imp_CloseHandle
0x1800ae584  test    eax, eax
0x1800ae586  jnz     short loc_1800AE5A0
0x1800ae588  call    cs:__imp_GetLastError
0x1800ae58e  mov     rdx, r13
0x1800ae591  lea     rcx, aSClosehandleEv; "%s: CloseHandle(event) failed with erro"...
0x1800ae598  mov     r8d, eax
0x1800ae59b  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800ae5a0  mov     r8d, ebx
0x1800ae5a3  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x1800ae5aa  mov     rdx, r13
0x1800ae5ad  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800ae5b2  lea     r11, [rsp+80h+var_s0]
0x1800ae5ba  mov     eax, ebx
0x1800ae5bc  mov     rbx, [r11+40h]
0x1800ae5c0  mov     rsi, [r11+48h]
0x1800ae5c4  mov     rsp, r11
0x1800ae5c7  pop     r15
0x1800ae5c9  pop     r14
0x1800ae5cb  pop     r13
0x1800ae5cd  pop     rdi
0x1800ae5ce  pop     rbp
0x1800ae5cf  retn
0x1800ae5d0  call    cs:__imp_GetLastError
0x1800ae5d6  mov     r14d, eax
0x1800ae5d9  test    eax, eax
0x1800ae5db  jz      short loc_1800AE624
0x1800ae5dd  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800ae5e4  mov     r9d, eax
0x1800ae5e7  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x1800ae5ee  mov     rdx, r13
0x1800ae5f1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800ae5f6  jmp     loc_1800AE7BA
0x1800ae5fb  lea     rcx, aSWaitforsingle; "%s: WaitForSingleObject timed out for G"...
0x1800ae602  mov     rdx, r13
0x1800ae605  mov     r14d, 5B4h
0x1800ae60b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800ae610  jmp     loc_1800AE56B
0x1800ae615  mov     rdx, r13
0x1800ae618  lea     rcx, aSPreviousGetcl; "%s: Previous GetCloudKerbTokenThreadPro"...
0x1800ae61f  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800ae624  mov     rcx, [r15]; hObject
0x1800ae627  call    cs:__imp_CloseHandle
0x1800ae62d  test    eax, eax
0x1800ae62f  jnz     short loc_1800AE649
0x1800ae631  call    cs:__imp_GetLastError
0x1800ae637  mov     rdx, r13
0x1800ae63a  lea     rcx, aSClosehandleTh; "%s: CloseHandle(thread) failed with err"...
0x1800ae641  mov     r8d, eax
0x1800ae644  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800ae649  mov     qword ptr [r15], 0
0x1800ae650  xor     ebx, ebx
0x1800ae652  xor     edx, edx; lpName
0x1800ae654  xor     ecx, ecx; lpEventAttributes
0x1800ae656  mov     r9d, 1F0003h; dwDesiredAccess
0x1800ae65c  lea     r8d, [rbx+1]; dwFlags
0x1800ae660  call    cs:__imp_CreateEventExW
0x1800ae666  mov     [rbp+hObject], rax
0x1800ae66a  test    rax, rax
0x1800ae66d  jnz     short loc_1800AE68F
0x1800ae66f  call    cs:__imp_GetLastError
0x1800ae675  lea     rcx, aSCreateeventex; "%s: CreateEventExW failed with error co"...
0x1800ae67c  mov     r14d, eax
0x1800ae67f  mov     r8d, eax
0x1800ae682  mov     rdx, r13
0x1800ae685  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800ae68a  jmp     loc_1800AE7B1
0x1800ae68f  mov     [rsp+80h+lpThreadId], rbx; lpThreadId
0x1800ae694  lea     r9, [rbp+Parameter]; lpParameter
0x1800ae698  lea     r8, ?GetCloudKerbTokenThreadProc@@YAKPEAX@Z; lpStartAddress
0x1800ae69f  mov     [rsp+80h+dwCreationFlags], ebx; dwCreationFlags
0x1800ae6a3  xor     edx, edx; dwStackSize
0x1800ae6a5  xor     ecx, ecx; lpThreadAttributes
0x1800ae6a7  call    cs:__imp_CreateThread
0x1800ae6ad  mov     [r15], rax
0x1800ae6b0  test    rax, rax
0x1800ae6b3  jnz     short loc_1800AE6C4
0x1800ae6b5  call    cs:__imp_GetLastError
0x1800ae6bb  lea     rcx, aSCreatethreadF; "%s: CreateThread failed with error code"...
0x1800ae6c2  jmp     short loc_1800AE67C
0x1800ae6c4  mov     rdx, r13
0x1800ae6c7  lea     rcx, aSWaitingForGet; "%s: Waiting for GetCloudKerbTokenThread"...
0x1800ae6ce  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800ae6d3  mov     rax, [r15]
0x1800ae6d6  lea     rdx, [rbp+Handles]; lpHandles
0x1800ae6da  xor     r8d, r8d; bWaitAll
0x1800ae6dd  mov     [rbp+Handles], rax
0x1800ae6e1  mov     rax, [rbp+hObject]
0x1800ae6e5  mov     r9d, edi; dwMilliseconds
0x1800ae6e8  mov     [rbp+var_48], rax
0x1800ae6ec  lea     ecx, [r8+2]; nCount
0x1800ae6f0  call    cs:__imp_WaitForMultipleObjects
0x1800ae6f6  test    eax, eax
0x1800ae6f8  jz      short loc_1800AE741
0x1800ae6fa  cmp     eax, 1
0x1800ae6fd  jz      short loc_1800AE73C
0x1800ae6ff  cmp     eax, esi
0x1800ae701  jz      short loc_1800AE730
0x1800ae703  cmp     eax, edi
0x1800ae705  jz      short loc_1800AE713
0x1800ae707  lea     rcx, aSWaitformultip_0; "%s: WaitForMultipleObjects returned une"...
0x1800ae70e  jmp     loc_1800AE55A
0x1800ae713  call    cs:__imp_GetLastError
0x1800ae719  mov     r14d, eax
0x1800ae71c  test    eax, eax
0x1800ae71e  jz      loc_1800AE575
0x1800ae724  lea     r8, aWaitformultipl; "WaitForMultipleObjects"
0x1800ae72b  jmp     loc_1800AE5E4
0x1800ae730  lea     rcx, aSWaitformultip; "%s: WaitForMultipleObjects timed out fo"...
0x1800ae737  jmp     loc_1800AE602
0x1800ae73c  mov     ebx, [rbp+arg_0]
0x1800ae73f  jmp     short loc_1800AE78F
0x1800ae741  mov     rcx, [r15]; hThread
0x1800ae744  lea     rdx, [rbp+ExitCode]; lpExitCode
0x1800ae748  call    cs:__imp_GetExitCodeThread
0x1800ae74e  test    eax, eax
0x1800ae750  jnz     short loc_1800AE764
0x1800ae752  call    cs:__imp_GetLastError
0x1800ae758  lea     rcx, aSGetexitcodeth; "%s: GetExitCodeThread failed with error"...
0x1800ae75f  jmp     loc_1800AE67C
0x1800ae764  mov     rcx, [r15]; hObject
0x1800ae767  call    cs:__imp_CloseHandle
0x1800ae76d  test    eax, eax
0x1800ae76f  jz      short loc_1800AE789
0x1800ae771  call    cs:__imp_GetLastError
0x1800ae777  mov     rdx, r13
0x1800ae77a  lea     rcx, aSClosehandleTh; "%s: CloseHandle(thread) failed with err"...
0x1800ae781  mov     r8d, eax
0x1800ae784  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800ae789  mov     [r15], rbx
0x1800ae78c  mov     ebx, [rbp+ExitCode]
0x1800ae78f  mov     rdx, r13
0x1800ae792  test    ebx, ebx
0x1800ae794  jns     short loc_1800AE7A5
0x1800ae796  mov     r8d, ebx
0x1800ae799  lea     rcx, aSGetcloudkerbt_0; "%s: GetCloudKerbTokenThreadProc failed "...
0x1800ae7a0  jmp     loc_1800AE685
0x1800ae7a5  lea     rcx, aSGetcloudkerbt; "%s: GetCloudKerbTokenThreadProc succeed"...
0x1800ae7ac  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800ae7b1  test    r14d, r14d
0x1800ae7b4  jz      loc_1800AE575
0x1800ae7ba  test    r14d, r14d
0x1800ae7bd  jg      loc_1800AE56B
0x1800ae7c3  mov     ebx, r14d
0x1800ae7c6  jmp     loc_1800AE575
```
