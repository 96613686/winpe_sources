# CleanupNdproxyIoControl

- ea: `0x180089a14`
- end: `0x180089e34`
- name: `CleanupNdproxyIoControl`
- size: `1056`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800205b0`
- `0x180089e3c`

## callees

- `0x1800755b8`
- `0x180089a14`
- `0x1800909d4`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180089da9`
- `KERNEL32!DeleteCriticalSection` at `0x180089da9`
- `KERNEL32!DeviceIoControl` at `0x180089aec`
- `KERNEL32!DeviceIoControl` at `0x180089aec`
- `KERNEL32!GetProcessHeap` at `0x180089d13`
- `KERNEL32!GetProcessHeap` at `0x180089d33`
- `KERNEL32!GetProcessHeap` at `0x180089de3`
- `KERNEL32!GetProcessHeap` at `0x180089d13`
- `KERNEL32!GetProcessHeap` at `0x180089d33`
- `KERNEL32!GetProcessHeap` at `0x180089de3`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180089c3f`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180089c3f`
- `KERNEL32!CloseHandle` at `0x180089b8f`
- `KERNEL32!CloseHandle` at `0x180089cf7`
- `KERNEL32!CloseHandle` at `0x180089d5e`
- `KERNEL32!CloseHandle` at `0x180089d71`
- `KERNEL32!CloseHandle` at `0x180089dc1`
- `KERNEL32!CloseHandle` at `0x180089b8f`
- `KERNEL32!CloseHandle` at `0x180089cf7`
- `KERNEL32!CloseHandle` at `0x180089d5e`
- `KERNEL32!CloseHandle` at `0x180089d71`
- `KERNEL32!CloseHandle` at `0x180089dc1`
- `KERNEL32!GetLastError` at `0x180089afc`
- `KERNEL32!GetLastError` at `0x180089afc`
- `KERNEL32!WaitForSingleObject` at `0x180089caf`
- `KERNEL32!WaitForSingleObject` at `0x180089ce1`
- `KERNEL32!WaitForSingleObject` at `0x180089caf`
- `KERNEL32!WaitForSingleObject` at `0x180089ce1`
- `KERNEL32!HeapFree` at `0x180089d27`
- `KERNEL32!HeapFree` at `0x180089d4b`
- `KERNEL32!HeapFree` at `0x180089df7`
- `KERNEL32!HeapFree` at `0x180089d27`
- `KERNEL32!HeapFree` at `0x180089d4b`
- `KERNEL32!HeapFree` at `0x180089df7`
- `rtutils!TracePrintfA` at `0x180089aac`
- `rtutils!TracePrintfA` at `0x180089b69`
- `rtutils!TracePrintfA` at `0x180089c20`
- `rtutils!TracePrintfA` at `0x180089c94`
- `rtutils!TracePrintfA` at `0x180089aac`
- `rtutils!TracePrintfA` at `0x180089b69`
- `rtutils!TracePrintfA` at `0x180089c20`
- `rtutils!TracePrintfA` at `0x180089c94`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180089cc7`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180089cc7`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180089b7c`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180089bac`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180089b7c`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180089bac`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x180089d8e`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x180089d8e`

## string_xrefs

- `0x180089bfa`: `CleanupNdproxyIoControl: Posting exit message to completion port`
- `0x180089c6e`: `CleanupNdproxyIoControl: PostQueuedCompletionStatus failed`
- `0x180089c19`: `CleanupNdproxyIoControl: Posting exit message to completion port`
- `0x180089c8d`: `CleanupNdproxyIoControl: PostQueuedCompletionStatus failed`

## pseudocode

```c
__int64 CleanupNdproxyIoControl()
{
  DWORD v0; // esi
  DWORD LastError; // eax
  _QWORD *v2; // rax
  void *v3; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v5; // rax
  _QWORD *v6; // rdi
  void *v7; // rbx
  HANDLE v8; // rax
  DWORD BytesReturned; // [rsp+40h] [rbp-838h] BYREF
  wchar_t DeviceName[12]; // [rsp+48h] [rbp-830h] BYREF
  int v12; // [rsp+60h] [rbp-818h] BYREF
  _BYTE v13[2044]; // [rsp+64h] [rbp-814h] BYREF

  BytesReturned = 0;
  v12 = 0;
  wcscpy(DeviceName, L"NDPROXY");
  v0 = 0;
  memset_0(v13, 0, sizeof(v13));
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( *((_QWORD *)&xmmword_1800D0BE0 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
        gNdpspEtwContext,
        *((_QWORD *)&xmmword_1800D0BE0 + 1),
        L"CleanupNdproxyIoControl");
  }
  else if ( dwTraceId != -1 )
  {
    TracePrintfA(dwTraceId, "CleanupNdproxyIoControl");
  }
  if ( g_hDriverSync != (HANDLE)-1LL )
  {
    if ( !DeviceIoControl(g_hDriverSync, 0x8FFF23C4, 0, 0, 0, 0, &BytesReturned, 0) )
    {
      LastError = GetLastError();
      v0 = LastError;
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( (_QWORD)xmmword_1800D0BE0 )
        {
          LOWORD(v12) = 0;
          FormatRRASErrorString(&v12, L"CleanupNdproxyIoControl: DISCONNECT failed(0x%x)", LastError);
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v12);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "CleanupNdproxyIoControl: DISCONNECT failed(0x%x)", LastError);
      }
    }
    CancelIo(g_hDriverSync);
    CloseHandle(g_hDriverSync);
  }
  if ( g_hDriverAsync != (HANDLE)-1LL )
  {
    CancelIo(g_hDriverAsync);
    if ( g_hAsyncIoCompletionPort != (HANDLE)-1LL )
    {
      v2 = g_pAsyncEventsThreadInfo;
      if ( g_pAsyncEventsThreadInfo )
      {
        if ( *(_QWORD *)g_pAsyncEventsThreadInfo )
        {
          if ( gIsndpspEtwTracingAvailable )
          {
            if ( *((_QWORD *)&xmmword_1800D0BE0 + 1) )
              ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
                gNdpspEtwContext,
                *((_QWORD *)&xmmword_1800D0BE0 + 1),
                L"CleanupNdproxyIoControl: Posting exit message to completion port");
          }
          else if ( dwTraceId != -1 )
          {
            TracePrintfA(dwTraceId, "CleanupNdproxyIoControl: Posting exit message to completion port");
          }
          if ( PostQueuedCompletionStatus(g_hAsyncIoCompletionPort, 0, 0, &g_OverlappedTerminate) )
          {
            WaitForSingleObject(*(HANDLE *)g_pAsyncEventsThreadInfo, 0xFFFFFFFF);
          }
          else
          {
            if ( gIsndpspEtwTracingAvailable )
            {
              if ( *((_QWORD *)&xmmword_1800D0BE0 + 1) )
                ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
                  gNdpspEtwContext,
                  *((_QWORD *)&xmmword_1800D0BE0 + 1),
                  L"CleanupNdproxyIoControl: PostQueuedCompletionStatus failed");
            }
            else if ( dwTraceId != -1 )
            {
              TracePrintfA(dwTraceId, "CleanupNdproxyIoControl: PostQueuedCompletionStatus failed");
            }
            WaitForSingleObject(*(HANDLE *)g_pAsyncEventsThreadInfo, 0x1388u);
            TerminateThread(*(HANDLE *)g_pAsyncEventsThreadInfo, 0);
          }
          CloseHandle(*(HANDLE *)g_pAsyncEventsThreadInfo);
          v2 = g_pAsyncEventsThreadInfo;
        }
        v3 = (void *)v2[1];
        if ( v3 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v3);
        }
        v5 = GetProcessHeap();
        HeapFree(v5, 0, g_pAsyncEventsThreadInfo);
      }
      CloseHandle(g_hAsyncIoCompletionPort);
    }
    CloseHandle(g_hDriverAsync);
  }
  UninitializeMapper();
  DefineDosDeviceW(2u, DeviceName, 0);
  if ( g_dwRequestID )
    DeleteCriticalSection(&g_RequestIDCritSec);
  if ( g_hRasOpenLinesMutex )
  {
    CloseHandle(g_hRasOpenLinesMutex);
    g_hRasOpenLinesMutex = 0;
  }
  v6 = g_pRasOpenLines;
  while ( v6 )
  {
    v7 = v6;
    v6 = (_QWORD *)*v6;
    v8 = GetProcessHeap();
    HeapFree(v8, 0, v7);
  }
  return v0;
}

```

## disassembly

```asm
0x180089a14  mov     [rsp+arg_0], rbx
0x180089a19  mov     [rsp+arg_8], rbp
0x180089a1e  mov     [rsp+arg_10], rsi
0x180089a23  push    rdi
0x180089a24  sub     rsp, 870h
0x180089a2b  mov     rax, cs:__security_cookie
0x180089a32  xor     rax, rsp
0x180089a35  mov     [rsp+878h+var_18], rax
0x180089a3d  movups  xmm0, xmmword ptr cs:aNdproxy_0; "NDPROXY"
0x180089a44  xor     ebp, ebp
0x180089a46  lea     rcx, [rsp+878h+var_814]; void *
0x180089a4b  xor     edx, edx; Val
0x180089a4d  mov     [rsp+878h+BytesReturned], ebp
0x180089a51  mov     r8d, 7FCh; Size
0x180089a57  mov     [rsp+878h+var_818], ebp
0x180089a5b  movdqu  xmmword ptr [rsp+878h+DeviceName], xmm0
0x180089a61  mov     esi, ebp
0x180089a63  call    memset_0
0x180089a68  or      ebx, 0FFFFFFFFh
0x180089a6b  cmp     cs:gIsndpspEtwTracingAvailable, ebp
0x180089a71  jz      short loc_180089A9B
0x180089a73  mov     rdx, qword ptr cs:xmmword_1800D0BE0+8
0x180089a7a  test    rdx, rdx
0x180089a7d  jz      short loc_180089AB8
0x180089a7f  mov     rcx, cs:gNdpspEtwContext
0x180089a86  lea     r8, aCleanupndproxy_2; "CleanupNdproxyIoControl"
0x180089a8d  mov     rax, cs:gNdpspTemplateFunc
0x180089a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089a99  jmp     short loc_180089AB8
0x180089a9b  mov     ecx, cs:dwTraceId; dwTraceID
0x180089aa1  cmp     ecx, ebx
0x180089aa3  jz      short loc_180089AB8
0x180089aa5  lea     rdx, aCleanupndproxy_5; "CleanupNdproxyIoControl"
0x180089aac  call    cs:__imp_TracePrintfA
0x180089ab3  nop     dword ptr [rax+rax+00h]
0x180089ab8  mov     rcx, cs:g_hDriverSync; hDevice
0x180089abf  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180089ac3  jz      loc_180089B9B
0x180089ac9  mov     [rsp+878h+lpOverlapped], rbp; lpOverlapped
0x180089ace  lea     rax, [rsp+878h+BytesReturned]
0x180089ad3  mov     [rsp+878h+lpBytesReturned], rax; lpBytesReturned
0x180089ad8  xor     r9d, r9d; nInBufferSize
0x180089adb  mov     [rsp+878h+nOutBufferSize], ebp; nOutBufferSize
0x180089adf  xor     r8d, r8d; lpInBuffer
0x180089ae2  mov     edx, 8FFF23C4h; dwIoControlCode
0x180089ae7  mov     [rsp+878h+lpOutBuffer], rbp; lpOutBuffer
0x180089aec  call    cs:__imp_DeviceIoControl
0x180089af3  nop     dword ptr [rax+rax+00h]
0x180089af8  test    eax, eax
0x180089afa  jnz     short loc_180089B75
0x180089afc  call    cs:__imp_GetLastError
0x180089b03  nop     dword ptr [rax+rax+00h]
0x180089b08  cmp     cs:gIsndpspEtwTracingAvailable, ebp
0x180089b0e  mov     esi, eax
0x180089b10  jz      short loc_180089B55
0x180089b12  cmp     qword ptr cs:xmmword_1800D0BE0, rbp
0x180089b19  jz      short loc_180089B75
0x180089b1b  mov     r8d, eax
0x180089b1e  mov     word ptr [rsp+878h+var_818], bp
0x180089b23  lea     rdx, aCleanupndproxy_1; "CleanupNdproxyIoControl: DISCONNECT fai"...
0x180089b2a  lea     rcx, [rsp+878h+var_818]
0x180089b2f  call    FormatRRASErrorString
0x180089b34  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x180089b3b  lea     r8, [rsp+878h+var_818]
0x180089b40  mov     rcx, cs:gNdpspEtwContext
0x180089b47  mov     rax, cs:gNdpspTemplateFunc
0x180089b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089b53  jmp     short loc_180089B75
0x180089b55  mov     ecx, cs:dwTraceId; dwTraceID
0x180089b5b  cmp     ecx, ebx
0x180089b5d  jz      short loc_180089B75
0x180089b5f  mov     r8d, eax
0x180089b62  lea     rdx, aCleanupndproxy; "CleanupNdproxyIoControl: DISCONNECT fai"...
0x180089b69  call    cs:__imp_TracePrintfA
0x180089b70  nop     dword ptr [rax+rax+00h]
0x180089b75  mov     rcx, cs:g_hDriverSync; hFile
0x180089b7c  call    cs:__imp_CancelIo
0x180089b83  nop     dword ptr [rax+rax+00h]
0x180089b88  mov     rcx, cs:g_hDriverSync; hObject
0x180089b8f  call    cs:__imp_CloseHandle
0x180089b96  nop     dword ptr [rax+rax+00h]
0x180089b9b  mov     rcx, cs:g_hDriverAsync; hFile
0x180089ba2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180089ba6  jz      loc_180089D7D
0x180089bac  call    cs:__imp_CancelIo
0x180089bb3  nop     dword ptr [rax+rax+00h]
0x180089bb8  cmp     cs:g_hAsyncIoCompletionPort, 0FFFFFFFFFFFFFFFFh
0x180089bc0  jz      loc_180089D6A
0x180089bc6  mov     rax, cs:g_pAsyncEventsThreadInfo
0x180089bcd  test    rax, rax
0x180089bd0  jz      loc_180089D57
0x180089bd6  cmp     [rax], rbp
0x180089bd9  jz      loc_180089D0A
0x180089bdf  cmp     cs:gIsndpspEtwTracingAvailable, ebp
0x180089be5  jz      short loc_180089C0F
0x180089be7  mov     rdx, qword ptr cs:xmmword_1800D0BE0+8
0x180089bee  test    rdx, rdx
0x180089bf1  jz      short loc_180089C2C
0x180089bf3  mov     rcx, cs:gNdpspEtwContext
0x180089bfa  lea     r8, aCleanupndproxy_0; "CleanupNdproxyIoControl: Posting exit m"...
0x180089c01  mov     rax, cs:gNdpspTemplateFunc
0x180089c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089c0d  jmp     short loc_180089C2C
0x180089c0f  mov     ecx, cs:dwTraceId; dwTraceID
0x180089c15  cmp     ecx, ebx
0x180089c17  jz      short loc_180089C2C
0x180089c19  lea     rdx, aCleanupndproxy_4; "CleanupNdproxyIoControl: Posting exit m"...
0x180089c20  call    cs:__imp_TracePrintfA
0x180089c27  nop     dword ptr [rax+rax+00h]
0x180089c2c  mov     rcx, cs:g_hAsyncIoCompletionPort; CompletionPort
0x180089c33  lea     r9, g_OverlappedTerminate; lpOverlapped
0x180089c3a  xor     r8d, r8d; dwCompletionKey
0x180089c3d  xor     edx, edx; dwNumberOfBytesTransferred
0x180089c3f  call    cs:__imp_PostQueuedCompletionStatus
0x180089c46  nop     dword ptr [rax+rax+00h]
0x180089c4b  test    eax, eax
0x180089c4d  jnz     loc_180089CD5
0x180089c53  cmp     cs:gIsndpspEtwTracingAvailable, ebp
0x180089c59  jz      short loc_180089C83
0x180089c5b  mov     rdx, qword ptr cs:xmmword_1800D0BE0+8
0x180089c62  test    rdx, rdx
0x180089c65  jz      short loc_180089CA0
0x180089c67  mov     rcx, cs:gNdpspEtwContext
0x180089c6e  lea     r8, aCleanupndproxy_6; "CleanupNdproxyIoControl: PostQueuedComp"...
0x180089c75  mov     rax, cs:gNdpspTemplateFunc
0x180089c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089c81  jmp     short loc_180089CA0
0x180089c83  mov     ecx, cs:dwTraceId; dwTraceID
0x180089c89  cmp     ecx, ebx
0x180089c8b  jz      short loc_180089CA0
0x180089c8d  lea     rdx, aCleanupndproxy_3; "CleanupNdproxyIoControl: PostQueuedComp"...
0x180089c94  call    cs:__imp_TracePrintfA
0x180089c9b  nop     dword ptr [rax+rax+00h]
0x180089ca0  mov     rcx, cs:g_pAsyncEventsThreadInfo
0x180089ca7  mov     edx, 1388h; dwMilliseconds
0x180089cac  mov     rcx, [rcx]; hHandle
0x180089caf  call    cs:__imp_WaitForSingleObject
0x180089cb6  nop     dword ptr [rax+rax+00h]
0x180089cbb  mov     rcx, cs:g_pAsyncEventsThreadInfo
0x180089cc2  xor     edx, edx; dwExitCode
0x180089cc4  mov     rcx, [rcx]; hThread
0x180089cc7  call    cs:__imp_TerminateThread
0x180089cce  nop     dword ptr [rax+rax+00h]
0x180089cd3  jmp     short loc_180089CED
0x180089cd5  mov     rcx, cs:g_pAsyncEventsThreadInfo
0x180089cdc  mov     edx, ebx; dwMilliseconds
0x180089cde  mov     rcx, [rcx]; hHandle
0x180089ce1  call    cs:__imp_WaitForSingleObject
0x180089ce8  nop     dword ptr [rax+rax+00h]
0x180089ced  mov     rcx, cs:g_pAsyncEventsThreadInfo
0x180089cf4  mov     rcx, [rcx]; hObject
0x180089cf7  call    cs:__imp_CloseHandle
0x180089cfe  nop     dword ptr [rax+rax+00h]
0x180089d03  mov     rax, cs:g_pAsyncEventsThreadInfo
0x180089d0a  mov     rbx, [rax+8]
0x180089d0e  test    rbx, rbx
0x180089d11  jz      short loc_180089D33
0x180089d13  call    cs:__imp_GetProcessHeap
0x180089d1a  nop     dword ptr [rax+rax+00h]
0x180089d1f  mov     r8, rbx; lpMem
0x180089d22  xor     edx, edx; dwFlags
0x180089d24  mov     rcx, rax; hHeap
0x180089d27  call    cs:__imp_HeapFree
0x180089d2e  nop     dword ptr [rax+rax+00h]
0x180089d33  call    cs:__imp_GetProcessHeap
0x180089d3a  nop     dword ptr [rax+rax+00h]
0x180089d3f  mov     r8, cs:g_pAsyncEventsThreadInfo; lpMem
0x180089d46  xor     edx, edx; dwFlags
0x180089d48  mov     rcx, rax; hHeap
0x180089d4b  call    cs:__imp_HeapFree
0x180089d52  nop     dword ptr [rax+rax+00h]
0x180089d57  mov     rcx, cs:g_hAsyncIoCompletionPort; hObject
0x180089d5e  call    cs:__imp_CloseHandle
0x180089d65  nop     dword ptr [rax+rax+00h]
0x180089d6a  mov     rcx, cs:g_hDriverAsync; hObject
0x180089d71  call    cs:__imp_CloseHandle
0x180089d78  nop     dword ptr [rax+rax+00h]
0x180089d7d  call    UninitializeMapper
0x180089d82  xor     r8d, r8d; lpTargetPath
0x180089d85  lea     rdx, [rsp+878h+DeviceName]; lpDeviceName
0x180089d8a  lea     ecx, [r8+2]; dwFlags
0x180089d8e  call    cs:__imp_DefineDosDeviceW
0x180089d95  nop     dword ptr [rax+rax+00h]
0x180089d9a  cmp     cs:g_dwRequestID, ebp
0x180089da0  jz      short loc_180089DB5
0x180089da2  lea     rcx, g_RequestIDCritSec; lpCriticalSection
0x180089da9  call    cs:__imp_DeleteCriticalSection
0x180089db0  nop     dword ptr [rax+rax+00h]
0x180089db5  mov     rcx, cs:g_hRasOpenLinesMutex; hObject
0x180089dbc  test    rcx, rcx
0x180089dbf  jz      short loc_180089DD4
0x180089dc1  call    cs:__imp_CloseHandle
0x180089dc8  nop     dword ptr [rax+rax+00h]
0x180089dcd  mov     cs:g_hRasOpenLinesMutex, rbp
0x180089dd4  mov     rdi, cs:g_pRasOpenLines
0x180089ddb  jmp     short loc_180089E03
0x180089ddd  mov     rbx, rdi
0x180089de0  mov     rdi, [rdi]
0x180089de3  call    cs:__imp_GetProcessHeap
0x180089dea  nop     dword ptr [rax+rax+00h]
0x180089def  mov     r8, rbx; lpMem
0x180089df2  xor     edx, edx; dwFlags
0x180089df4  mov     rcx, rax; hHeap
0x180089df7  call    cs:__imp_HeapFree
0x180089dfe  nop     dword ptr [rax+rax+00h]
0x180089e03  test    rdi, rdi
0x180089e06  jnz     short loc_180089DDD
0x180089e08  mov     eax, esi
0x180089e0a  mov     rcx, [rsp+878h+var_18]
0x180089e12  xor     rcx, rsp; StackCookie
0x180089e15  call    __security_check_cookie
0x180089e1a  lea     r11, [rsp+878h+var_8]
0x180089e22  mov     rbx, [r11+10h]
0x180089e26  mov     rbp, [r11+18h]
0x180089e2a  mov     rsi, [r11+20h]
0x180089e2e  mov     rsp, r11
0x180089e31  pop     rdi
0x180089e32  retn
```
