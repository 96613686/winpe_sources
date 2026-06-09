# CleanupNdproxyIoControl

- ea: `0x180083c10`
- end: `0x180083f7d`
- name: `CleanupNdproxyIoControl`
- size: `877`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001f8e0`
- `0x180083f84`

## callees

- `0x180071cec`
- `0x180083c10`
- `0x18008a694`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180083f18`
- `KERNEL32!DeleteCriticalSection` at `0x180083f18`
- `KERNEL32!DeviceIoControl` at `0x180083cd7`
- `KERNEL32!DeviceIoControl` at `0x180083cd7`
- `KERNEL32!GetProcessHeap` at `0x180083eac`
- `KERNEL32!GetProcessHeap` at `0x180083ec0`
- `KERNEL32!GetProcessHeap` at `0x180083f46`
- `KERNEL32!GetProcessHeap` at `0x180083eac`
- `KERNEL32!GetProcessHeap` at `0x180083ec0`
- `KERNEL32!GetProcessHeap` at `0x180083f46`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180083e00`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180083e00`
- `KERNEL32!CloseHandle` at `0x180083d62`
- `KERNEL32!CloseHandle` at `0x180083e96`
- `KERNEL32!CloseHandle` at `0x180083edf`
- `KERNEL32!CloseHandle` at `0x180083eec`
- `KERNEL32!CloseHandle` at `0x180083f2a`
- `KERNEL32!CloseHandle` at `0x180083d62`
- `KERNEL32!CloseHandle` at `0x180083e96`
- `KERNEL32!CloseHandle` at `0x180083edf`
- `KERNEL32!CloseHandle` at `0x180083eec`
- `KERNEL32!CloseHandle` at `0x180083f2a`
- `KERNEL32!GetLastError` at `0x180083ce1`
- `KERNEL32!GetLastError` at `0x180083ce1`
- `KERNEL32!WaitForSingleObject` at `0x180083e60`
- `KERNEL32!WaitForSingleObject` at `0x180083e86`
- `KERNEL32!WaitForSingleObject` at `0x180083e60`
- `KERNEL32!WaitForSingleObject` at `0x180083e86`
- `KERNEL32!HeapFree` at `0x180083eba`
- `KERNEL32!HeapFree` at `0x180083ed2`
- `KERNEL32!HeapFree` at `0x180083f54`
- `KERNEL32!HeapFree` at `0x180083eba`
- `KERNEL32!HeapFree` at `0x180083ed2`
- `KERNEL32!HeapFree` at `0x180083f54`
- `rtutils!TracePrintfA` at `0x180083c9d`
- `rtutils!TracePrintfA` at `0x180083d48`
- `rtutils!TracePrintfA` at `0x180083de7`
- `rtutils!TracePrintfA` at `0x180083e4b`
- `rtutils!TracePrintfA` at `0x180083c9d`
- `rtutils!TracePrintfA` at `0x180083d48`
- `rtutils!TracePrintfA` at `0x180083de7`
- `rtutils!TracePrintfA` at `0x180083e4b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180083e72`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180083e72`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180083d55`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180083d79`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180083d55`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180083d79`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x180083f03`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x180083f03`

## string_xrefs

- `0x180083de0`: `CleanupNdproxyIoControl: Posting exit message to completion port`
- `0x180083dc1`: `CleanupNdproxyIoControl: Posting exit message to completion port`
- `0x180083e44`: `CleanupNdproxyIoControl: PostQueuedCompletionStatus failed`
- `0x180083e25`: `CleanupNdproxyIoControl: PostQueuedCompletionStatus failed`

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
  wchar_t DeviceName[12]; // [rsp+48h] [rbp-850h] BYREF
  int v12; // [rsp+60h] [rbp-838h] BYREF
  _BYTE v13[2044]; // [rsp+64h] [rbp-834h] BYREF

  BytesReturned = 0;
  v12 = 0;
  wcscpy(DeviceName, L"NDPROXY");
  v0 = 0;
  memset_0(v13, 0, sizeof(v13));
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( *((_QWORD *)&xmmword_1800C9BE0 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
        gNdpspEtwContext,
        *((_QWORD *)&xmmword_1800C9BE0 + 1),
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
        if ( (_QWORD)xmmword_1800C9BE0 )
        {
          LOWORD(v12) = 0;
          FormatRRASErrorString(&v12, L"CleanupNdproxyIoControl: DISCONNECT failed(0x%x)", LastError);
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v12);
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
            if ( *((_QWORD *)&xmmword_1800C9BE0 + 1) )
              ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
                gNdpspEtwContext,
                *((_QWORD *)&xmmword_1800C9BE0 + 1),
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
              if ( *((_QWORD *)&xmmword_1800C9BE0 + 1) )
                ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
                  gNdpspEtwContext,
                  *((_QWORD *)&xmmword_1800C9BE0 + 1),
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
0x180083c10  push    rbx
0x180083c12  push    rbp
0x180083c13  push    rsi
0x180083c14  push    rdi
0x180083c15  sub     rsp, 878h
0x180083c1c  mov     rax, cs:__security_cookie
0x180083c23  xor     rax, rsp
0x180083c26  mov     [rsp+898h+var_38], rax
0x180083c2e  movups  xmm0, xmmword ptr cs:aNdproxy_0; "NDPROXY"
0x180083c35  xor     ebp, ebp
0x180083c37  lea     rcx, [rsp+898h+var_834]; void *
0x180083c3c  xor     edx, edx; Val
0x180083c3e  mov     [rsp+898h+BytesReturned], ebp
0x180083c42  mov     r8d, 7FCh; Size
0x180083c48  mov     [rsp+898h+var_838], ebp
0x180083c4c  movdqu  xmmword ptr [rsp+898h+DeviceName], xmm0
0x180083c52  mov     esi, ebp
0x180083c54  call    memset_0
0x180083c59  or      ebx, 0FFFFFFFFh
0x180083c5c  cmp     cs:gIsndpspEtwTracingAvailable, ebp
0x180083c62  jz      short loc_180083C8C
0x180083c64  mov     rdx, qword ptr cs:xmmword_1800C9BE0+8
0x180083c6b  test    rdx, rdx
0x180083c6e  jz      short loc_180083CA3
0x180083c70  mov     rcx, cs:gNdpspEtwContext
0x180083c77  lea     r8, aCleanupndproxy_2; "CleanupNdproxyIoControl"
0x180083c7e  mov     rax, cs:gNdpspTemplateFunc
0x180083c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083c8a  jmp     short loc_180083CA3
0x180083c8c  mov     ecx, cs:dwTraceId; dwTraceID
0x180083c92  cmp     ecx, ebx
0x180083c94  jz      short loc_180083CA3
0x180083c96  lea     rdx, aCleanupndproxy_5; "CleanupNdproxyIoControl"
0x180083c9d  call    cs:__imp_TracePrintfA
0x180083ca3  mov     rcx, cs:g_hDriverSync; hDevice
0x180083caa  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180083cae  jz      loc_180083D68
0x180083cb4  mov     [rsp+898h+lpOverlapped], rbp; lpOverlapped
0x180083cb9  lea     rax, [rsp+898h+BytesReturned]
0x180083cbe  mov     [rsp+898h+lpBytesReturned], rax; lpBytesReturned
0x180083cc3  xor     r9d, r9d; nInBufferSize
0x180083cc6  mov     [rsp+898h+nOutBufferSize], ebp; nOutBufferSize
0x180083cca  xor     r8d, r8d; lpInBuffer
0x180083ccd  mov     edx, 8FFF23C4h; dwIoControlCode
0x180083cd2  mov     [rsp+898h+lpOutBuffer], rbp; lpOutBuffer
0x180083cd7  call    cs:__imp_DeviceIoControl
0x180083cdd  test    eax, eax
0x180083cdf  jnz     short loc_180083D4E
0x180083ce1  call    cs:__imp_GetLastError
0x180083ce7  cmp     cs:gIsndpspEtwTracingAvailable, ebp
0x180083ced  mov     esi, eax
0x180083cef  jz      short loc_180083D34
0x180083cf1  cmp     qword ptr cs:xmmword_1800C9BE0, rbp
0x180083cf8  jz      short loc_180083D4E
0x180083cfa  mov     r8d, eax
0x180083cfd  mov     word ptr [rsp+898h+var_838], bp
0x180083d02  lea     rdx, aCleanupndproxy_1; "CleanupNdproxyIoControl: DISCONNECT fai"...
0x180083d09  lea     rcx, [rsp+898h+var_838]
0x180083d0e  call    FormatRRASErrorString
0x180083d13  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180083d1a  lea     r8, [rsp+898h+var_838]
0x180083d1f  mov     rcx, cs:gNdpspEtwContext
0x180083d26  mov     rax, cs:gNdpspTemplateFunc
0x180083d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083d32  jmp     short loc_180083D4E
0x180083d34  mov     ecx, cs:dwTraceId; dwTraceID
0x180083d3a  cmp     ecx, ebx
0x180083d3c  jz      short loc_180083D4E
0x180083d3e  mov     r8d, eax
0x180083d41  lea     rdx, aCleanupndproxy; "CleanupNdproxyIoControl: DISCONNECT fai"...
0x180083d48  call    cs:__imp_TracePrintfA
0x180083d4e  mov     rcx, cs:g_hDriverSync; hFile
0x180083d55  call    cs:__imp_CancelIo
0x180083d5b  mov     rcx, cs:g_hDriverSync; hObject
0x180083d62  call    cs:__imp_CloseHandle
0x180083d68  mov     rcx, cs:g_hDriverAsync; hFile
0x180083d6f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180083d73  jz      loc_180083EF2
0x180083d79  call    cs:__imp_CancelIo
0x180083d7f  cmp     cs:g_hAsyncIoCompletionPort, 0FFFFFFFFFFFFFFFFh
0x180083d87  jz      loc_180083EE5
0x180083d8d  mov     rax, cs:g_pAsyncEventsThreadInfo
0x180083d94  test    rax, rax
0x180083d97  jz      loc_180083ED8
0x180083d9d  cmp     [rax], rbp
0x180083da0  jz      loc_180083EA3
0x180083da6  cmp     cs:gIsndpspEtwTracingAvailable, ebp
0x180083dac  jz      short loc_180083DD6
0x180083dae  mov     rdx, qword ptr cs:xmmword_1800C9BE0+8
0x180083db5  test    rdx, rdx
0x180083db8  jz      short loc_180083DED
0x180083dba  mov     rcx, cs:gNdpspEtwContext
0x180083dc1  lea     r8, aCleanupndproxy_0; "CleanupNdproxyIoControl: Posting exit m"...
0x180083dc8  mov     rax, cs:gNdpspTemplateFunc
0x180083dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083dd4  jmp     short loc_180083DED
0x180083dd6  mov     ecx, cs:dwTraceId; dwTraceID
0x180083ddc  cmp     ecx, ebx
0x180083dde  jz      short loc_180083DED
0x180083de0  lea     rdx, aCleanupndproxy_4; "CleanupNdproxyIoControl: Posting exit m"...
0x180083de7  call    cs:__imp_TracePrintfA
0x180083ded  mov     rcx, cs:g_hAsyncIoCompletionPort; CompletionPort
0x180083df4  lea     r9, g_OverlappedTerminate; lpOverlapped
0x180083dfb  xor     r8d, r8d; dwCompletionKey
0x180083dfe  xor     edx, edx; dwNumberOfBytesTransferred
0x180083e00  call    cs:__imp_PostQueuedCompletionStatus
0x180083e06  test    eax, eax
0x180083e08  jnz     short loc_180083E7A
0x180083e0a  cmp     cs:gIsndpspEtwTracingAvailable, ebp
0x180083e10  jz      short loc_180083E3A
0x180083e12  mov     rdx, qword ptr cs:xmmword_1800C9BE0+8
0x180083e19  test    rdx, rdx
0x180083e1c  jz      short loc_180083E51
0x180083e1e  mov     rcx, cs:gNdpspEtwContext
0x180083e25  lea     r8, aCleanupndproxy_6; "CleanupNdproxyIoControl: PostQueuedComp"...
0x180083e2c  mov     rax, cs:gNdpspTemplateFunc
0x180083e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083e38  jmp     short loc_180083E51
0x180083e3a  mov     ecx, cs:dwTraceId; dwTraceID
0x180083e40  cmp     ecx, ebx
0x180083e42  jz      short loc_180083E51
0x180083e44  lea     rdx, aCleanupndproxy_3; "CleanupNdproxyIoControl: PostQueuedComp"...
0x180083e4b  call    cs:__imp_TracePrintfA
0x180083e51  mov     rcx, cs:g_pAsyncEventsThreadInfo
0x180083e58  mov     edx, 1388h; dwMilliseconds
0x180083e5d  mov     rcx, [rcx]; hHandle
0x180083e60  call    cs:__imp_WaitForSingleObject
0x180083e66  mov     rcx, cs:g_pAsyncEventsThreadInfo
0x180083e6d  xor     edx, edx; dwExitCode
0x180083e6f  mov     rcx, [rcx]; hThread
0x180083e72  call    cs:__imp_TerminateThread
0x180083e78  jmp     short loc_180083E8C
0x180083e7a  mov     rcx, cs:g_pAsyncEventsThreadInfo
0x180083e81  mov     edx, ebx; dwMilliseconds
0x180083e83  mov     rcx, [rcx]; hHandle
0x180083e86  call    cs:__imp_WaitForSingleObject
0x180083e8c  mov     rcx, cs:g_pAsyncEventsThreadInfo
0x180083e93  mov     rcx, [rcx]; hObject
0x180083e96  call    cs:__imp_CloseHandle
0x180083e9c  mov     rax, cs:g_pAsyncEventsThreadInfo
0x180083ea3  mov     rbx, [rax+8]
0x180083ea7  test    rbx, rbx
0x180083eaa  jz      short loc_180083EC0
0x180083eac  call    cs:__imp_GetProcessHeap
0x180083eb2  mov     r8, rbx; lpMem
0x180083eb5  xor     edx, edx; dwFlags
0x180083eb7  mov     rcx, rax; hHeap
0x180083eba  call    cs:__imp_HeapFree
0x180083ec0  call    cs:__imp_GetProcessHeap
0x180083ec6  mov     r8, cs:g_pAsyncEventsThreadInfo; lpMem
0x180083ecd  xor     edx, edx; dwFlags
0x180083ecf  mov     rcx, rax; hHeap
0x180083ed2  call    cs:__imp_HeapFree
0x180083ed8  mov     rcx, cs:g_hAsyncIoCompletionPort; hObject
0x180083edf  call    cs:__imp_CloseHandle
0x180083ee5  mov     rcx, cs:g_hDriverAsync; hObject
0x180083eec  call    cs:__imp_CloseHandle
0x180083ef2  call    UninitializeMapper
0x180083ef7  xor     r8d, r8d; lpTargetPath
0x180083efa  lea     rdx, [rsp+898h+DeviceName]; lpDeviceName
0x180083eff  lea     ecx, [r8+2]; dwFlags
0x180083f03  call    cs:__imp_DefineDosDeviceW
0x180083f09  cmp     cs:g_dwRequestID, ebp
0x180083f0f  jz      short loc_180083F1E
0x180083f11  lea     rcx, g_RequestIDCritSec; lpCriticalSection
0x180083f18  call    cs:__imp_DeleteCriticalSection
0x180083f1e  mov     rcx, cs:g_hRasOpenLinesMutex; hObject
0x180083f25  test    rcx, rcx
0x180083f28  jz      short loc_180083F37
0x180083f2a  call    cs:__imp_CloseHandle
0x180083f30  mov     cs:g_hRasOpenLinesMutex, rbp
0x180083f37  mov     rdi, cs:g_pRasOpenLines
0x180083f3e  jmp     short loc_180083F5A
0x180083f40  mov     rbx, rdi
0x180083f43  mov     rdi, [rdi]
0x180083f46  call    cs:__imp_GetProcessHeap
0x180083f4c  mov     r8, rbx; lpMem
0x180083f4f  xor     edx, edx; dwFlags
0x180083f51  mov     rcx, rax; hHeap
0x180083f54  call    cs:__imp_HeapFree
0x180083f5a  test    rdi, rdi
0x180083f5d  jnz     short loc_180083F40
0x180083f5f  mov     eax, esi
0x180083f61  mov     rcx, [rsp+898h+var_38]
0x180083f69  xor     rcx, rsp; StackCookie
0x180083f6c  call    __security_check_cookie
0x180083f71  add     rsp, 878h
0x180083f78  pop     rdi
0x180083f79  pop     rsi
0x180083f7a  pop     rbp
0x180083f7b  pop     rbx
0x180083f7c  retn
```
