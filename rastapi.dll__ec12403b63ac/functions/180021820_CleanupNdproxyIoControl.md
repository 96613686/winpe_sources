# CleanupNdproxyIoControl

- ea: `0x180021820`
- end: `0x180021b8d`
- name: `CleanupNdproxyIoControl`
- size: `877`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800022a0`
- `0x180021b94`

## callees

- `0x180021820`
- `0x180028de8`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800218f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800218f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021abc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021ad0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021b56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021abc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021ad0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021b56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021aca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021ae2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021b64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021aca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021ae2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021b64`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180021a70`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180021a96`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180021a70`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180021a96`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021b28`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021b28`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800218e7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800218e7`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180021a10`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180021a10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021972`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021aa6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021aef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021afc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021b3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021972`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021aa6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021aef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021afc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021b3a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180021a82`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180021a82`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x180021b13`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x180021b13`
- `rtutils!TracePrintfA` at `0x1800218ad`
- `rtutils!TracePrintfA` at `0x180021958`
- `rtutils!TracePrintfA` at `0x1800219f7`
- `rtutils!TracePrintfA` at `0x180021a5b`
- `rtutils!TracePrintfA` at `0x1800218ad`
- `rtutils!TracePrintfA` at `0x180021958`
- `rtutils!TracePrintfA` at `0x1800219f7`
- `rtutils!TracePrintfA` at `0x180021a5b`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180021965`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180021989`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180021965`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180021989`

## string_xrefs

- `0x1800219d1`: `CleanupNdproxyIoControl: Posting exit message to completion port`
- `0x1800219f0`: `CleanupNdproxyIoControl: Posting exit message to completion port`
- `0x180021a35`: `CleanupNdproxyIoControl: PostQueuedCompletionStatus failed`
- `0x180021a54`: `CleanupNdproxyIoControl: PostQueuedCompletionStatus failed`

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
  DWORD BytesReturned; // [rsp+40h] [rbp-858h] BYREF
  WCHAR DeviceName[12]; // [rsp+48h] [rbp-850h] BYREF
  int v12; // [rsp+60h] [rbp-838h] BYREF
  _BYTE v13[2044]; // [rsp+64h] [rbp-834h] BYREF

  BytesReturned = 0;
  v12 = 0;
  wcscpy(DeviceName, L"NDPROXY");
  v0 = 0;
  memset_0(v13, 0, sizeof(v13));
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( qword_18003EC48 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(
        gNdpspEtwContext,
        qword_18003EC48,
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
        if ( qword_18003EC40 )
        {
          LOWORD(v12) = 0;
          FormatRRASErrorString(&v12, L"CleanupNdproxyIoControl: DISCONNECT failed(0x%x)", LastError);
          ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v12);
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
            if ( qword_18003EC48 )
              ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(
                gNdpspEtwContext,
                qword_18003EC48,
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
              if ( qword_18003EC48 )
                ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(
                  gNdpspEtwContext,
                  qword_18003EC48,
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
0x180021820  push    rbx
0x180021822  push    rbp
0x180021823  push    rsi
0x180021824  push    rdi
0x180021825  sub     rsp, 878h
0x18002182c  mov     rax, cs:__security_cookie
0x180021833  xor     rax, rsp
0x180021836  mov     [rsp+898h+var_38], rax
0x18002183e  movups  xmm0, xmmword ptr cs:aNdproxy_0; "NDPROXY"
0x180021845  xor     ebp, ebp
0x180021847  lea     rcx, [rsp+898h+var_834]; void *
0x18002184c  xor     edx, edx; Val
0x18002184e  mov     [rsp+898h+BytesReturned], ebp
0x180021852  mov     r8d, 7FCh; Size
0x180021858  mov     [rsp+898h+var_838], ebp
0x18002185c  movdqu  xmmword ptr [rsp+898h+DeviceName], xmm0
0x180021862  mov     esi, ebp
0x180021864  call    memset_0
0x180021869  or      ebx, 0FFFFFFFFh
0x18002186c  cmp     cs:gIsndpspEtwTracingAvailable, ebp
0x180021872  jz      short loc_18002189C
0x180021874  mov     rdx, cs:qword_18003EC48
0x18002187b  test    rdx, rdx
0x18002187e  jz      short loc_1800218B3
0x180021880  mov     rcx, cs:gNdpspEtwContext
0x180021887  lea     r8, aCleanupndproxy_2; "CleanupNdproxyIoControl"
0x18002188e  mov     rax, cs:gNdpspTemplateFunc
0x180021895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002189a  jmp     short loc_1800218B3
0x18002189c  mov     ecx, cs:dwTraceId; dwTraceID
0x1800218a2  cmp     ecx, ebx
0x1800218a4  jz      short loc_1800218B3
0x1800218a6  lea     rdx, aCleanupndproxy_5; "CleanupNdproxyIoControl"
0x1800218ad  call    cs:__imp_TracePrintfA
0x1800218b3  mov     rcx, cs:g_hDriverSync; hDevice
0x1800218ba  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800218be  jz      loc_180021978
0x1800218c4  mov     [rsp+898h+lpOverlapped], rbp; lpOverlapped
0x1800218c9  lea     rax, [rsp+898h+BytesReturned]
0x1800218ce  mov     [rsp+898h+lpBytesReturned], rax; lpBytesReturned
0x1800218d3  xor     r9d, r9d; nInBufferSize
0x1800218d6  mov     [rsp+898h+nOutBufferSize], ebp; nOutBufferSize
0x1800218da  xor     r8d, r8d; lpInBuffer
0x1800218dd  mov     edx, 8FFF23C4h; dwIoControlCode
0x1800218e2  mov     [rsp+898h+lpOutBuffer], rbp; lpOutBuffer
0x1800218e7  call    cs:__imp_DeviceIoControl
0x1800218ed  test    eax, eax
0x1800218ef  jnz     short loc_18002195E
0x1800218f1  call    cs:__imp_GetLastError
0x1800218f7  cmp     cs:gIsndpspEtwTracingAvailable, ebp
0x1800218fd  mov     esi, eax
0x1800218ff  jz      short loc_180021944
0x180021901  cmp     cs:qword_18003EC40, rbp
0x180021908  jz      short loc_18002195E
0x18002190a  mov     r8d, eax
0x18002190d  mov     word ptr [rsp+898h+var_838], bp
0x180021912  lea     rdx, aCleanupndproxy_1; "CleanupNdproxyIoControl: DISCONNECT fai"...
0x180021919  lea     rcx, [rsp+898h+var_838]
0x18002191e  call    FormatRRASErrorString
0x180021923  mov     rdx, cs:qword_18003EC40
0x18002192a  lea     r8, [rsp+898h+var_838]
0x18002192f  mov     rcx, cs:gNdpspEtwContext
0x180021936  mov     rax, cs:gNdpspTemplateFunc
0x18002193d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021942  jmp     short loc_18002195E
0x180021944  mov     ecx, cs:dwTraceId; dwTraceID
0x18002194a  cmp     ecx, ebx
0x18002194c  jz      short loc_18002195E
0x18002194e  mov     r8d, eax
0x180021951  lea     rdx, aCleanupndproxy; "CleanupNdproxyIoControl: DISCONNECT fai"...
0x180021958  call    cs:__imp_TracePrintfA
0x18002195e  mov     rcx, cs:g_hDriverSync; hFile
0x180021965  call    cs:__imp_CancelIo
0x18002196b  mov     rcx, cs:g_hDriverSync; hObject
0x180021972  call    cs:__imp_CloseHandle
0x180021978  mov     rcx, cs:g_hDriverAsync; hFile
0x18002197f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180021983  jz      loc_180021B02
0x180021989  call    cs:__imp_CancelIo
0x18002198f  cmp     cs:g_hAsyncIoCompletionPort, 0FFFFFFFFFFFFFFFFh
0x180021997  jz      loc_180021AF5
0x18002199d  mov     rax, cs:g_pAsyncEventsThreadInfo
0x1800219a4  test    rax, rax
0x1800219a7  jz      loc_180021AE8
0x1800219ad  cmp     [rax], rbp
0x1800219b0  jz      loc_180021AB3
0x1800219b6  cmp     cs:gIsndpspEtwTracingAvailable, ebp
0x1800219bc  jz      short loc_1800219E6
0x1800219be  mov     rdx, cs:qword_18003EC48
0x1800219c5  test    rdx, rdx
0x1800219c8  jz      short loc_1800219FD
0x1800219ca  mov     rcx, cs:gNdpspEtwContext
0x1800219d1  lea     r8, aCleanupndproxy_0; "CleanupNdproxyIoControl: Posting exit m"...
0x1800219d8  mov     rax, cs:gNdpspTemplateFunc
0x1800219df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219e4  jmp     short loc_1800219FD
0x1800219e6  mov     ecx, cs:dwTraceId; dwTraceID
0x1800219ec  cmp     ecx, ebx
0x1800219ee  jz      short loc_1800219FD
0x1800219f0  lea     rdx, aCleanupndproxy_4; "CleanupNdproxyIoControl: Posting exit m"...
0x1800219f7  call    cs:__imp_TracePrintfA
0x1800219fd  mov     rcx, cs:g_hAsyncIoCompletionPort; CompletionPort
0x180021a04  lea     r9, g_OverlappedTerminate; lpOverlapped
0x180021a0b  xor     r8d, r8d; dwCompletionKey
0x180021a0e  xor     edx, edx; dwNumberOfBytesTransferred
0x180021a10  call    cs:__imp_PostQueuedCompletionStatus
0x180021a16  test    eax, eax
0x180021a18  jnz     short loc_180021A8A
0x180021a1a  cmp     cs:gIsndpspEtwTracingAvailable, ebp
0x180021a20  jz      short loc_180021A4A
0x180021a22  mov     rdx, cs:qword_18003EC48
0x180021a29  test    rdx, rdx
0x180021a2c  jz      short loc_180021A61
0x180021a2e  mov     rcx, cs:gNdpspEtwContext
0x180021a35  lea     r8, aCleanupndproxy_6; "CleanupNdproxyIoControl: PostQueuedComp"...
0x180021a3c  mov     rax, cs:gNdpspTemplateFunc
0x180021a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a48  jmp     short loc_180021A61
0x180021a4a  mov     ecx, cs:dwTraceId; dwTraceID
0x180021a50  cmp     ecx, ebx
0x180021a52  jz      short loc_180021A61
0x180021a54  lea     rdx, aCleanupndproxy_3; "CleanupNdproxyIoControl: PostQueuedComp"...
0x180021a5b  call    cs:__imp_TracePrintfA
0x180021a61  mov     rcx, cs:g_pAsyncEventsThreadInfo
0x180021a68  mov     edx, 1388h; dwMilliseconds
0x180021a6d  mov     rcx, [rcx]; hHandle
0x180021a70  call    cs:__imp_WaitForSingleObject
0x180021a76  mov     rcx, cs:g_pAsyncEventsThreadInfo
0x180021a7d  xor     edx, edx; dwExitCode
0x180021a7f  mov     rcx, [rcx]; hThread
0x180021a82  call    cs:__imp_TerminateThread
0x180021a88  jmp     short loc_180021A9C
0x180021a8a  mov     rcx, cs:g_pAsyncEventsThreadInfo
0x180021a91  mov     edx, ebx; dwMilliseconds
0x180021a93  mov     rcx, [rcx]; hHandle
0x180021a96  call    cs:__imp_WaitForSingleObject
0x180021a9c  mov     rcx, cs:g_pAsyncEventsThreadInfo
0x180021aa3  mov     rcx, [rcx]; hObject
0x180021aa6  call    cs:__imp_CloseHandle
0x180021aac  mov     rax, cs:g_pAsyncEventsThreadInfo
0x180021ab3  mov     rbx, [rax+8]
0x180021ab7  test    rbx, rbx
0x180021aba  jz      short loc_180021AD0
0x180021abc  call    cs:__imp_GetProcessHeap
0x180021ac2  mov     r8, rbx; lpMem
0x180021ac5  xor     edx, edx; dwFlags
0x180021ac7  mov     rcx, rax; hHeap
0x180021aca  call    cs:__imp_HeapFree
0x180021ad0  call    cs:__imp_GetProcessHeap
0x180021ad6  mov     r8, cs:g_pAsyncEventsThreadInfo; lpMem
0x180021add  xor     edx, edx; dwFlags
0x180021adf  mov     rcx, rax; hHeap
0x180021ae2  call    cs:__imp_HeapFree
0x180021ae8  mov     rcx, cs:g_hAsyncIoCompletionPort; hObject
0x180021aef  call    cs:__imp_CloseHandle
0x180021af5  mov     rcx, cs:g_hDriverAsync; hObject
0x180021afc  call    cs:__imp_CloseHandle
0x180021b02  call    UninitializeMapper
0x180021b07  xor     r8d, r8d; lpTargetPath
0x180021b0a  lea     rdx, [rsp+898h+DeviceName]; lpDeviceName
0x180021b0f  lea     ecx, [r8+2]; dwFlags
0x180021b13  call    cs:__imp_DefineDosDeviceW
0x180021b19  cmp     cs:g_dwRequestID, ebp
0x180021b1f  jz      short loc_180021B2E
0x180021b21  lea     rcx, g_RequestIDCritSec; lpCriticalSection
0x180021b28  call    cs:__imp_DeleteCriticalSection
0x180021b2e  mov     rcx, cs:g_hRasOpenLinesMutex; hObject
0x180021b35  test    rcx, rcx
0x180021b38  jz      short loc_180021B47
0x180021b3a  call    cs:__imp_CloseHandle
0x180021b40  mov     cs:g_hRasOpenLinesMutex, rbp
0x180021b47  mov     rdi, cs:g_pRasOpenLines
0x180021b4e  jmp     short loc_180021B6A
0x180021b50  mov     rbx, rdi
0x180021b53  mov     rdi, [rdi]
0x180021b56  call    cs:__imp_GetProcessHeap
0x180021b5c  mov     r8, rbx; lpMem
0x180021b5f  xor     edx, edx; dwFlags
0x180021b61  mov     rcx, rax; hHeap
0x180021b64  call    cs:__imp_HeapFree
0x180021b6a  test    rdi, rdi
0x180021b6d  jnz     short loc_180021B50
0x180021b6f  mov     eax, esi
0x180021b71  mov     rcx, [rsp+898h+var_38]
0x180021b79  xor     rcx, rsp; StackCookie
0x180021b7c  call    __security_check_cookie
0x180021b81  add     rsp, 878h
0x180021b88  pop     rdi
0x180021b89  pop     rsi
0x180021b8a  pop     rbp
0x180021b8b  pop     rbx
0x180021b8c  retn
```
