# InitializeNdproxyIoControl

- ea: `0x180089e3c`
- end: `0x18008a68c`
- name: `InitializeNdproxyIoControl`
- size: `2128`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800298e4`

## callees

- `0x1800755b8`
- `0x180089a14`
- `0x180089e3c`
- `0x18009018c`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x18008a1a1`
- `KERNEL32!DeviceIoControl` at `0x18008a286`
- `KERNEL32!DeviceIoControl` at `0x18008a32a`
- `KERNEL32!DeviceIoControl` at `0x18008a3e8`
- `KERNEL32!DeviceIoControl` at `0x18008a1a1`
- `KERNEL32!DeviceIoControl` at `0x18008a286`
- `KERNEL32!DeviceIoControl` at `0x18008a32a`
- `KERNEL32!DeviceIoControl` at `0x18008a3e8`
- `KERNEL32!Sleep` at `0x18008a24b`
- `KERNEL32!Sleep` at `0x18008a24b`
- `KERNEL32!InitializeCriticalSection` at `0x180089f71`
- `KERNEL32!InitializeCriticalSection` at `0x180089f71`
- `KERNEL32!CreateThread` at `0x18008a593`
- `KERNEL32!CreateThread` at `0x18008a593`
- `KERNEL32!GetProcessHeap` at `0x18008a4b1`
- `KERNEL32!GetProcessHeap` at `0x18008a54a`
- `KERNEL32!GetProcessHeap` at `0x18008a4b1`
- `KERNEL32!GetProcessHeap` at `0x18008a54a`
- `KERNEL32!CreateIoCompletionPort` at `0x18008a0fd`
- `KERNEL32!CreateIoCompletionPort` at `0x18008a0fd`
- `KERNEL32!CreateFileA` at `0x180089fdd`
- `KERNEL32!CreateFileA` at `0x18008a08c`
- `KERNEL32!CreateFileA` at `0x180089fdd`
- `KERNEL32!CreateFileA` at `0x18008a08c`
- `KERNEL32!HeapAlloc` at `0x18008a4c9`
- `KERNEL32!HeapAlloc` at `0x18008a55f`
- `KERNEL32!HeapAlloc` at `0x18008a4c9`
- `KERNEL32!HeapAlloc` at `0x18008a55f`
- `KERNEL32!GetLastError` at `0x180089f1d`
- `KERNEL32!GetLastError` at `0x180089ff6`
- `KERNEL32!GetLastError` at `0x18008a0a5`
- `KERNEL32!GetLastError` at `0x18008a116`
- `KERNEL32!GetLastError` at `0x18008a29a`
- `KERNEL32!GetLastError` at `0x18008a3f8`
- `KERNEL32!GetLastError` at `0x18008a5b2`
- `KERNEL32!GetLastError` at `0x18008a5f1`
- `KERNEL32!GetLastError` at `0x180089f1d`
- `KERNEL32!GetLastError` at `0x180089ff6`
- `KERNEL32!GetLastError` at `0x18008a0a5`
- `KERNEL32!GetLastError` at `0x18008a116`
- `KERNEL32!GetLastError` at `0x18008a29a`
- `KERNEL32!GetLastError` at `0x18008a3f8`
- `KERNEL32!GetLastError` at `0x18008a5b2`
- `KERNEL32!GetLastError` at `0x18008a5f1`
- `rtutils!TracePrintfA` at `0x18008a05c`
- `rtutils!TracePrintfA` at `0x18008a226`
- `rtutils!TracePrintfA` at `0x18008a3af`
- `rtutils!TracePrintfA` at `0x18008a4a0`
- `rtutils!TracePrintfA` at `0x18008a531`
- `rtutils!TracePrintfA` at `0x18008a644`
- `rtutils!TracePrintfA` at `0x18008a05c`
- `rtutils!TracePrintfA` at `0x18008a226`
- `rtutils!TracePrintfA` at `0x18008a3af`
- `rtutils!TracePrintfA` at `0x18008a4a0`
- `rtutils!TracePrintfA` at `0x18008a531`
- `rtutils!TracePrintfA` at `0x18008a644`
- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x180089f05`
- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x180089f05`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x180089f8f`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x180089fa7`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x180089f8f`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x180089fa7`

## string_xrefs

- `0x180089f5e`: `InitializeNdproxyIoControl: CreateMutex failed (0x%x)`
- `0x180089f41`: `InitializeNdproxyIoControl: CreateMutex failed (0x%x)`
- `0x18008a04d`: `InitializeNdproxyIoControl: CreateFile(%hs, sync) failed (0x%x)`
- `0x18008a01a`: `InitializeNdproxyIoControl: CreateFile(%hs, sync) failed (0x%x)`
- `0x18008a0e6`: `InitializeNdproxyIoControl: CreateFile(%hs, async) failed (0x%x)`
- `0x18008a0c9`: `InitializeNdproxyIoControl: CreateFile(%hs, async) failed (0x%x)`
- `0x18008a157`: `InitializeNdproxyIoControl: CreateIoCompletionPort failed (0x%x)`
- `0x18008a13a`: `InitializeNdproxyIoControl: CreateIoCompletionPort failed (0x%x)`
- `0x18008a52a`: `InitializeNdproxyIoControl: Failed to allocate thread info`
- `0x18008a4fd`: `InitializeNdproxyIoControl: Failed to allocate thread info`
- `0x18008a5e8`: `InitializeNdproxyIoControl: CreateThread failed (0x%x)`
- `0x18008a5d2`: `InitializeNdproxyIoControl: CreateThread failed (0x%x)`

## pseudocode

```c
__int64 __fastcall InitializeNdproxyIoControl(__int64 a1, __int64 a2, unsigned int a3)
{
  int v4; // ebx
  DWORD LastError; // eax
  unsigned int v6; // ebx
  const wchar_t *v7; // rdx
  DWORD v8; // eax
  const wchar_t *v9; // rdx
  HANDLE FileA; // rax
  BOOL i; // eax
  unsigned int v12; // eax
  __int64 v13; // rdx
  const wchar_t *v14; // r8
  HANDLE ProcessHeap; // rax
  _DWORD *v16; // rax
  HANDLE v17; // rax
  HANDLE Thread; // rax
  DWORD BytesReturned; // [rsp+48h] [rbp-C0h] BYREF
  _DWORD InBuffer[2]; // [rsp+50h] [rbp-B8h] BYREF
  DWORD ThreadId[2]; // [rsp+58h] [rbp-B0h] BYREF
  CHAR FileName[16]; // [rsp+60h] [rbp-A8h] BYREF
  wchar_t DeviceName_8[8]; // [rsp+70h] [rbp-98h] BYREF
  _OWORD TargetPath_8[2]; // [rsp+80h] [rbp-88h] BYREF
  int v26; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v27[2044]; // [rsp+ACh] [rbp-5Ch] BYREF

  wcscpy(DeviceName_8, L"NDProxy");
  InBuffer[0] = 1;
  InBuffer[1] = 1;
  v4 = 10;
  BytesReturned = 0;
  strcpy(FileName, "\\\\.\\NDProxy");
  ThreadId[1] = 0;
  ThreadId[0] = 0;
  wcscpy((wchar_t *)TargetPath_8, L"\\Device\\NDProxy");
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  g_fUseReqId = 0;
  g_pfnCallback = (__int64)NdproxyCallback;
  g_hRasOpenLinesMutex = CreateMutexA(0, 0, 0);
  if ( !g_hRasOpenLinesMutex )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        v7 = L"InitializeNdproxyIoControl: CreateMutex failed (0x%x)";
        goto LABEL_41;
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "InitializeNdproxyIoControl: CreateMutex failed (0x%x)", LastError);
    }
    goto LABEL_82;
  }
  InitializeCriticalSection(&g_RequestIDCritSec);
  g_dwRequestID = 1;
  DefineDosDeviceW(2u, DeviceName_8, 0);
  DefineDosDeviceW(1u, DeviceName_8, (LPCWSTR)TargetPath_8);
  g_hDriverSync = CreateFileA(FileName, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
  if ( g_hDriverSync == (HANDLE)-1LL )
  {
    v8 = GetLastError();
    v6 = v8;
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "InitializeNdproxyIoControl: CreateFile(%hs, sync) failed (0x%x)", FileName, v8);
      goto LABEL_82;
    }
    if ( !(_QWORD)xmmword_1800D0BE0 )
      goto LABEL_82;
    v9 = L"InitializeNdproxyIoControl: CreateFile(%hs, sync) failed (0x%x)";
    goto LABEL_11;
  }
  FileA = CreateFileA(FileName, 0xC0000000, 3u, 0, 3u, 0x40000080u, 0);
  g_hDriverAsync = FileA;
  if ( FileA == (HANDLE)-1LL )
  {
    v8 = GetLastError();
    v6 = v8;
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "InitializeNdproxyIoControl: CreateFile(%hs, async) failed (0x%x)", FileName, v8);
      goto LABEL_82;
    }
    if ( !(_QWORD)xmmword_1800D0BE0 )
      goto LABEL_82;
    v9 = L"InitializeNdproxyIoControl: CreateFile(%hs, async) failed (0x%x)";
LABEL_11:
    LOWORD(v26) = 0;
    FormatRRASErrorString(&v26, v9, FileName, v8);
    goto LABEL_42;
  }
  g_hAsyncIoCompletionPort = CreateIoCompletionPort(FileA, 0, 0, 0);
  if ( g_hAsyncIoCompletionPort == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        v7 = L"InitializeNdproxyIoControl: CreateIoCompletionPort failed (0x%x)";
        goto LABEL_41;
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "InitializeNdproxyIoControl: CreateIoCompletionPort failed (0x%x)", LastError);
    }
    goto LABEL_82;
  }
  for ( i = DeviceIoControl(g_hDriverSync, 0x8FFF23DC, InBuffer, 8u, &g_dwNumNDProxyLines, 4u, &BytesReturned, 0);
        ;
        i = DeviceIoControl(g_hDriverSync, 0x8FFF23DC, InBuffer, 8u, &g_dwNumNDProxyLines, 4u, &BytesReturned, 0) )
  {
    if ( !i || BytesReturned < 4 )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( !(_QWORD)xmmword_1800D0BE0 )
          goto LABEL_82;
        v7 = L"InitializeNdproxyIoControl: GET_NUM_LINES failed (0x%x)";
        goto LABEL_41;
      }
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "InitializeNdproxyIoControl: GET_NUM_LINES failed (0x%x)", LastError);
      goto LABEL_82;
    }
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        LOWORD(v26) = 0;
        FormatRRASErrorString(
          &v26,
          L"InitializeNdproxyIoControl: GET_NUM_LINES returned 0x%x lines",
          (unsigned int)g_dwNumNDProxyLines);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v26);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "InitializeNdproxyIoControl: GET_NUM_LINES returned 0x%x lines", g_dwNumNDProxyLines);
    }
    if ( g_dwNumNDProxyLines >= a3 || !v4 )
      break;
    Sleep(0x1F4u);
    --v4;
  }
  if ( !DeviceIoControl(g_hDriverSync, 0x8FFF23C0, InBuffer, 8u, &g_dwNumNDProxyLines, 4u, &BytesReturned, 0)
    || BytesReturned < 4 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        v7 = L"InitializeNdproxyIoControl: CONNECT failed (0x%x)";
        goto LABEL_41;
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "InitializeNdproxyIoControl: CONNECT failed (0x%x)", LastError);
    }
    goto LABEL_82;
  }
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( (_QWORD)xmmword_1800D0BE0 )
    {
      LOWORD(v26) = 0;
      FormatRRASErrorString(
        &v26,
        L"InitializeNdproxyIoControl: NDProxy has 0x%x lines",
        (unsigned int)g_dwNumNDProxyLines);
      ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v26);
    }
  }
  else if ( dwTraceId != -1 )
  {
    TracePrintfA(dwTraceId, "InitializeNdproxyIoControl: NDProxy has 0x%x lines", g_dwNumNDProxyLines);
  }
  if ( DeviceIoControl(g_hDriverSync, 0x8FFF23D4, ThreadId, 4u, 0, 0, &BytesReturned, 0) )
  {
    v12 = InitializeMapper();
    v6 = v12;
    if ( v12 )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( !(_QWORD)xmmword_1800D0BE0 )
          goto LABEL_83;
        LOWORD(v26) = 0;
        FormatRRASErrorString(&v26, L"InitializeNdproxyIoControl: InitializeMapper failed (0x%x)", v12);
        v13 = xmmword_1800D0BE0;
        v14 = (const wchar_t *)&v26;
LABEL_66:
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(gNdpspEtwContext, v13, v14);
        goto LABEL_83;
      }
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "InitializeNdproxyIoControl: InitializeMapper failed (0x%x)", v12);
    }
    else
    {
      ProcessHeap = GetProcessHeap();
      v16 = HeapAlloc(ProcessHeap, 8u, 0x18u);
      g_pAsyncEventsThreadInfo = v16;
      if ( v16 )
      {
        v16[4] = 1024;
        v17 = GetProcessHeap();
        *((_QWORD *)g_pAsyncEventsThreadInfo + 1) = HeapAlloc(v17, 8u, 0x400u);
        Thread = CreateThread(0, 0, AsyncEventsThread, 0, 0, &ThreadId[1]);
        *(_QWORD *)g_pAsyncEventsThreadInfo = Thread;
        if ( !Thread )
        {
          LastError = GetLastError();
          v6 = LastError;
          if ( gIsndpspEtwTracingAvailable )
          {
            if ( (_QWORD)xmmword_1800D0BE0 )
            {
              v7 = L"InitializeNdproxyIoControl: CreateThread failed (0x%x)";
              goto LABEL_41;
            }
          }
          else if ( dwTraceId != -1 )
          {
            TracePrintfA(dwTraceId, "InitializeNdproxyIoControl: CreateThread failed (0x%x)", LastError);
          }
          goto LABEL_82;
        }
        return v6;
      }
      v6 = 14;
      if ( gIsndpspEtwTracingAvailable )
      {
        v13 = *((_QWORD *)&xmmword_1800D0BE0 + 1);
        if ( !*((_QWORD *)&xmmword_1800D0BE0 + 1) )
          goto LABEL_83;
        v14 = L"InitializeNdproxyIoControl: Failed to allocate thread info";
        goto LABEL_66;
      }
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "InitializeNdproxyIoControl: Failed to allocate thread info");
    }
LABEL_83:
    CleanupNdproxyIoControl();
    return v6;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( !(_QWORD)xmmword_1800D0BE0 )
      goto LABEL_82;
    v7 = L"InitializeNdproxyIoControl: SET_DEVICEID_BASE failed (0x%x)";
LABEL_41:
    LOWORD(v26) = 0;
    FormatRRASErrorString(&v26, v7, LastError);
LABEL_42:
    ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v26);
  }
  else if ( dwTraceId != -1 )
  {
    TracePrintfA(dwTraceId, "InitializeNdproxyIoControl: SET_DEVICEID_BASE failed (0x%x)", LastError);
  }
LABEL_82:
  if ( v6 )
    goto LABEL_83;
  return v6;
}

```

## disassembly

```asm
0x180089e3c  mov     rax, rsp
0x180089e3f  mov     [rax+8], rbx
0x180089e43  mov     [rax+10h], rsi
0x180089e47  mov     [rax+18h], rdi
0x180089e4b  push    rbp
0x180089e4c  push    r12
0x180089e4e  push    r13
0x180089e50  push    r14
0x180089e52  push    r15
0x180089e54  lea     rbp, [rax-7D8h]
0x180089e5b  sub     rsp, 8B0h
0x180089e62  mov     rax, cs:__security_cookie
0x180089e69  xor     rax, rsp
0x180089e6c  mov     [rbp+7D0h+var_30], rax
0x180089e73  movups  xmm0, xmmword ptr cs:aNdproxy_1; "NDProxy"
0x180089e7a  mov     eax, dword ptr cs:aNdproxy+8; "oxy"
0x180089e80  xor     r14d, r14d
0x180089e83  movups  xmm1, xmmword ptr cs:aDeviceNdproxy; "\\Device\\NDProxy"
0x180089e8a  mov     edi, 1
0x180089e8f  mov     esi, r8d
0x180089e92  movdqu  xmmword ptr [rsp+8D0h+DeviceName+8], xmm0
0x180089e98  xor     edx, edx; Val
0x180089e9a  mov     r8d, 7FCh; Size
0x180089ea0  movups  xmm0, xmmword ptr cs:aDeviceNdproxy+10h; "NDProxy"
0x180089ea7  lea     rcx, [rbp+7D0h+var_82C]; void *
0x180089eab  mov     [rsp+8D0h+InBuffer], edi
0x180089eaf  mov     [rsp+8D0h+var_884], edi
0x180089eb3  lea     ebx, [rdi+9]
0x180089eb6  movups  [rbp+7D0h+var_848], xmm0
0x180089eba  mov     [rsp+8D0h+BytesReturned], r14d
0x180089ebf  movsd   xmm0, qword ptr cs:aNdproxy; "\\\\.\\NDProxy"
0x180089ec7  movsd   qword ptr [rsp+8D0h+FileName], xmm0
0x180089ecd  mov     [rsp+8D0h+ThreadId+4], r14d
0x180089ed2  mov     [rsp+8D0h+ThreadId], r14d
0x180089ed7  movups  xmmword ptr [rsp+8D0h+TargetPath+8], xmm1
0x180089edc  mov     dword ptr [rsp+8D0h+DeviceName], eax
0x180089ee0  mov     [rbp+7D0h+var_830], r14d
0x180089ee4  call    memset_0
0x180089ee9  lea     rax, ?NdproxyCallback@@YAXPEAXK_K111@Z; NdproxyCallback(void *,ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64)
0x180089ef0  mov     cs:g_fUseReqId, r14d
0x180089ef7  xor     r8d, r8d; lpName
0x180089efa  mov     cs:g_pfnCallback, rax
0x180089f01  xor     edx, edx; bInitialOwner
0x180089f03  xor     ecx, ecx; lpMutexAttributes
0x180089f05  call    cs:__imp_CreateMutexA
0x180089f0c  nop     dword ptr [rax+rax+00h]
0x180089f11  mov     cs:g_hRasOpenLinesMutex, rax
0x180089f18  test    rax, rax
0x180089f1b  jnz     short loc_180089F6A
0x180089f1d  call    cs:__imp_GetLastError
0x180089f24  nop     dword ptr [rax+rax+00h]
0x180089f29  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x180089f30  mov     ebx, eax
0x180089f32  jz      short loc_180089F4D
0x180089f34  cmp     qword ptr cs:xmmword_1800D0BE0, r14
0x180089f3b  jz      loc_18008A650
0x180089f41  lea     rdx, aInitializendpr_20; "InitializeNdproxyIoControl: CreateMutex"...
0x180089f48  jmp     loc_18008A2C9
0x180089f4d  mov     ecx, cs:dwTraceId
0x180089f53  or      edi, 0FFFFFFFFh
0x180089f56  cmp     ecx, edi
0x180089f58  jz      loc_18008A650
0x180089f5e  lea     rdx, aInitializendpr_6; "InitializeNdproxyIoControl: CreateMutex"...
0x180089f65  jmp     loc_18008A641
0x180089f6a  lea     rcx, g_RequestIDCritSec; lpCriticalSection
0x180089f71  call    cs:__imp_InitializeCriticalSection
0x180089f78  nop     dword ptr [rax+rax+00h]
0x180089f7d  xor     r8d, r8d; lpTargetPath
0x180089f80  mov     cs:g_dwRequestID, edi
0x180089f86  lea     rdx, [rsp+8D0h+DeviceName+8]; lpDeviceName
0x180089f8b  lea     ecx, [r8+2]; dwFlags
0x180089f8f  call    cs:__imp_DefineDosDeviceW
0x180089f96  nop     dword ptr [rax+rax+00h]
0x180089f9b  lea     r8, [rsp+8D0h+TargetPath+8]; lpTargetPath
0x180089fa0  mov     ecx, edi; dwFlags
0x180089fa2  lea     rdx, [rsp+8D0h+DeviceName+8]; lpDeviceName
0x180089fa7  call    cs:__imp_DefineDosDeviceW
0x180089fae  nop     dword ptr [rax+rax+00h]
0x180089fb3  mov     edi, 3
0x180089fb8  mov     [rsp+8D0h+hTemplateFile], r14; hTemplateFile
0x180089fbd  mov     r15d, 0C0000000h
0x180089fc3  mov     [rsp+8D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180089fcb  mov     r8d, edi; dwShareMode
0x180089fce  mov     [rsp+8D0h+dwCreationDisposition], edi; dwCreationDisposition
0x180089fd2  mov     edx, r15d; dwDesiredAccess
0x180089fd5  lea     rcx, [rsp+8D0h+FileName]; lpFileName
0x180089fda  xor     r9d, r9d; lpSecurityAttributes
0x180089fdd  call    cs:__imp_CreateFileA
0x180089fe4  nop     dword ptr [rax+rax+00h]
0x180089fe9  mov     cs:g_hDriverSync, rax
0x180089ff0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180089ff4  jnz     short loc_18008A06D
0x180089ff6  call    cs:__imp_GetLastError
0x180089ffd  nop     dword ptr [rax+rax+00h]
0x18008a002  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x18008a009  mov     ebx, eax
0x18008a00b  jz      short loc_18008A03C
0x18008a00d  cmp     qword ptr cs:xmmword_1800D0BE0, r14
0x18008a014  jz      loc_18008A650
0x18008a01a  lea     rdx, aInitializendpr_22; "InitializeNdproxyIoControl: CreateFile("...
0x18008a021  lea     r8, [rsp+8D0h+FileName]
0x18008a026  mov     word ptr [rbp+7D0h+var_830], r14w
0x18008a02b  mov     r9d, eax
0x18008a02e  lea     rcx, [rbp+7D0h+var_830]
0x18008a032  call    FormatRRASErrorString
0x18008a037  jmp     loc_18008A2DA
0x18008a03c  mov     ecx, cs:dwTraceId; dwTraceID
0x18008a042  or      edi, 0FFFFFFFFh
0x18008a045  cmp     ecx, edi
0x18008a047  jz      loc_18008A650
0x18008a04d  lea     rdx, aInitializendpr_21; "InitializeNdproxyIoControl: CreateFile("...
0x18008a054  lea     r8, [rsp+8D0h+FileName]
0x18008a059  mov     r9d, eax
0x18008a05c  call    cs:__imp_TracePrintfA
0x18008a063  nop     dword ptr [rax+rax+00h]
0x18008a068  jmp     loc_18008A650
0x18008a06d  mov     [rsp+8D0h+hTemplateFile], r14; hTemplateFile
0x18008a072  lea     rcx, [rsp+8D0h+FileName]; lpFileName
0x18008a077  mov     [rsp+8D0h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x18008a07f  xor     r9d, r9d; lpSecurityAttributes
0x18008a082  mov     r8d, edi; dwShareMode
0x18008a085  mov     [rsp+8D0h+dwCreationDisposition], edi; dwCreationDisposition
0x18008a089  mov     edx, r15d; dwDesiredAccess
0x18008a08c  call    cs:__imp_CreateFileA
0x18008a093  nop     dword ptr [rax+rax+00h]
0x18008a098  mov     cs:g_hDriverAsync, rax
0x18008a09f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008a0a3  jnz     short loc_18008A0F2
0x18008a0a5  call    cs:__imp_GetLastError
0x18008a0ac  nop     dword ptr [rax+rax+00h]
0x18008a0b1  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x18008a0b8  mov     ebx, eax
0x18008a0ba  jz      short loc_18008A0D5
0x18008a0bc  cmp     qword ptr cs:xmmword_1800D0BE0, r14
0x18008a0c3  jz      loc_18008A650
0x18008a0c9  lea     rdx, aInitializendpr_8; "InitializeNdproxyIoControl: CreateFile("...
0x18008a0d0  jmp     loc_18008A021
0x18008a0d5  mov     ecx, cs:dwTraceId
0x18008a0db  or      edi, 0FFFFFFFFh
0x18008a0de  cmp     ecx, edi
0x18008a0e0  jz      loc_18008A650
0x18008a0e6  lea     rdx, aInitializendpr_14; "InitializeNdproxyIoControl: CreateFile("...
0x18008a0ed  jmp     loc_18008A054
0x18008a0f2  xor     r9d, r9d; NumberOfConcurrentThreads
0x18008a0f5  xor     r8d, r8d; CompletionKey
0x18008a0f8  xor     edx, edx; ExistingCompletionPort
0x18008a0fa  mov     rcx, rax; FileHandle
0x18008a0fd  call    cs:__imp_CreateIoCompletionPort
0x18008a104  nop     dword ptr [rax+rax+00h]
0x18008a109  mov     cs:g_hAsyncIoCompletionPort, rax
0x18008a110  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008a114  jnz     short loc_18008A163
0x18008a116  call    cs:__imp_GetLastError
0x18008a11d  nop     dword ptr [rax+rax+00h]
0x18008a122  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x18008a129  mov     ebx, eax
0x18008a12b  jz      short loc_18008A146
0x18008a12d  cmp     qword ptr cs:xmmword_1800D0BE0, r14
0x18008a134  jz      loc_18008A650
0x18008a13a  lea     rdx, aInitializendpr_16; "InitializeNdproxyIoControl: CreateIoCom"...
0x18008a141  jmp     loc_18008A2C9
0x18008a146  mov     ecx, cs:dwTraceId
0x18008a14c  or      edi, 0FFFFFFFFh
0x18008a14f  cmp     ecx, edi
0x18008a151  jz      loc_18008A650
0x18008a157  lea     rdx, aInitializendpr_17; "InitializeNdproxyIoControl: CreateIoCom"...
0x18008a15e  jmp     loc_18008A641
0x18008a163  mov     rcx, cs:g_hDriverSync; hDevice
0x18008a16a  lea     rax, [rsp+8D0h+BytesReturned]
0x18008a16f  mov     [rsp+8D0h+lpOverlapped], r14; lpOverlapped
0x18008a174  lea     r13, g_dwNumNDProxyLines
0x18008a17b  mov     [rsp+8D0h+hTemplateFile], rax; lpBytesReturned
0x18008a180  lea     r8, [rsp+8D0h+InBuffer]; lpInBuffer
0x18008a185  mov     r15d, 4
0x18008a18b  mov     edx, 8FFF23DCh; dwIoControlCode
0x18008a190  mov     [rsp+8D0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x18008a195  mov     qword ptr [rsp+8D0h+dwCreationDisposition], r13; lpOutBuffer
0x18008a19a  lea     r12d, [r15+4]
0x18008a19e  mov     r9d, r12d; nInBufferSize
0x18008a1a1  call    cs:__imp_DeviceIoControl
0x18008a1a8  nop     dword ptr [rax+rax+00h]
0x18008a1ad  or      edi, 0FFFFFFFFh
0x18008a1b0  jmp     loc_18008A292
0x18008a1b5  cmp     [rsp+8D0h+BytesReturned], r15d
0x18008a1ba  jb      loc_18008A29A
0x18008a1c0  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x18008a1c7  jz      short loc_18008A20E
0x18008a1c9  cmp     qword ptr cs:xmmword_1800D0BE0, r14
0x18008a1d0  jz      short loc_18008A232
0x18008a1d2  mov     r8d, cs:g_dwNumNDProxyLines
0x18008a1d9  lea     rdx, aInitializendpr_0; "InitializeNdproxyIoControl: GET_NUM_LIN"...
0x18008a1e0  lea     rcx, [rbp+7D0h+var_830]
0x18008a1e4  mov     word ptr [rbp+7D0h+var_830], r14w
0x18008a1e9  call    FormatRRASErrorString
0x18008a1ee  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008a1f5  lea     r8, [rbp+7D0h+var_830]
0x18008a1f9  mov     rcx, cs:gNdpspEtwContext
0x18008a200  mov     rax, cs:gNdpspTemplateFunc
0x18008a207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a20c  jmp     short loc_18008A232
0x18008a20e  mov     ecx, cs:dwTraceId; dwTraceID
0x18008a214  cmp     ecx, edi
0x18008a216  jz      short loc_18008A232
0x18008a218  mov     r8d, cs:g_dwNumNDProxyLines
0x18008a21f  lea     rdx, aInitializendpr_19; "InitializeNdproxyIoControl: GET_NUM_LIN"...
0x18008a226  call    cs:__imp_TracePrintfA
0x18008a22d  nop     dword ptr [rax+rax+00h]
0x18008a232  cmp     cs:g_dwNumNDProxyLines, esi
0x18008a238  jnb     loc_18008A2FD
0x18008a23e  test    ebx, ebx
0x18008a240  jz      loc_18008A2FD
0x18008a246  mov     ecx, 1F4h; dwMilliseconds
0x18008a24b  call    cs:__imp_Sleep
0x18008a252  nop     dword ptr [rax+rax+00h]
0x18008a257  mov     rcx, cs:g_hDriverSync; hDevice
0x18008a25e  lea     rax, [rsp+8D0h+BytesReturned]
0x18008a263  mov     [rsp+8D0h+lpOverlapped], r14; lpOverlapped
0x18008a268  lea     r8, [rsp+8D0h+InBuffer]; lpInBuffer
0x18008a26d  mov     [rsp+8D0h+hTemplateFile], rax; lpBytesReturned
0x18008a272  add     ebx, edi
0x18008a274  mov     [rsp+8D0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x18008a279  mov     r9d, r12d; nInBufferSize
0x18008a27c  mov     edx, 8FFF23DCh; dwIoControlCode
0x18008a281  mov     qword ptr [rsp+8D0h+dwCreationDisposition], r13; lpOutBuffer
0x18008a286  call    cs:__imp_DeviceIoControl
0x18008a28d  nop     dword ptr [rax+rax+00h]
0x18008a292  test    eax, eax
0x18008a294  jnz     loc_18008A1B5
0x18008a29a  call    cs:__imp_GetLastError
0x18008a2a1  nop     dword ptr [rax+rax+00h]
0x18008a2a6  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x18008a2ad  mov     ebx, eax
0x18008a2af  jz      loc_18008A630
0x18008a2b5  cmp     qword ptr cs:xmmword_1800D0BE0, r14
0x18008a2bc  jz      loc_18008A650
0x18008a2c2  lea     rdx, aInitializendpr_12; "InitializeNdproxyIoControl: GET_NUM_LIN"...
0x18008a2c9  mov     r8d, eax
0x18008a2cc  mov     word ptr [rbp+7D0h+var_830], r14w
0x18008a2d1  lea     rcx, [rbp+7D0h+var_830]
0x18008a2d5  call    FormatRRASErrorString
0x18008a2da  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008a2e1  lea     r8, [rbp+7D0h+var_830]
0x18008a2e5  mov     rcx, cs:gNdpspEtwContext
0x18008a2ec  mov     rax, cs:gNdpspTemplateFunc
0x18008a2f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a2f8  jmp     loc_18008A650
0x18008a2fd  mov     rcx, cs:g_hDriverSync; hDevice
0x18008a304  lea     rax, [rsp+8D0h+BytesReturned]
0x18008a309  mov     [rsp+8D0h+lpOverlapped], r14; lpOverlapped
0x18008a30e  lea     r8, [rsp+8D0h+InBuffer]; lpInBuffer
0x18008a313  mov     [rsp+8D0h+hTemplateFile], rax; lpBytesReturned
0x18008a318  mov     r9d, r12d; nInBufferSize
0x18008a31b  mov     [rsp+8D0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x18008a320  mov     edx, 8FFF23C0h; dwIoControlCode
0x18008a325  mov     qword ptr [rsp+8D0h+dwCreationDisposition], r13; lpOutBuffer
0x18008a32a  call    cs:__imp_DeviceIoControl
0x18008a331  nop     dword ptr [rax+rax+00h]
0x18008a336  test    eax, eax
0x18008a338  jz      loc_18008A5F1
0x18008a33e  cmp     [rsp+8D0h+BytesReturned], r15d
0x18008a343  jb      loc_18008A5F1
0x18008a349  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x18008a350  jz      short loc_18008A397
0x18008a352  cmp     qword ptr cs:xmmword_1800D0BE0, r14
0x18008a359  jz      short loc_18008A3BB
0x18008a35b  mov     r8d, cs:g_dwNumNDProxyLines
0x18008a362  lea     rdx, aInitializendpr_15; "InitializeNdproxyIoControl: NDProxy has"...
0x18008a369  lea     rcx, [rbp+7D0h+var_830]
0x18008a36d  mov     word ptr [rbp+7D0h+var_830], r14w
0x18008a372  call    FormatRRASErrorString
0x18008a377  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008a37e  lea     r8, [rbp+7D0h+var_830]
0x18008a382  mov     rcx, cs:gNdpspEtwContext
0x18008a389  mov     rax, cs:gNdpspTemplateFunc
0x18008a390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a395  jmp     short loc_18008A3BB
0x18008a397  mov     ecx, cs:dwTraceId; dwTraceID
0x18008a39d  cmp     ecx, edi
0x18008a39f  jz      short loc_18008A3BB
0x18008a3a1  mov     r8d, cs:g_dwNumNDProxyLines
0x18008a3a8  lea     rdx, aInitializendpr_3; "InitializeNdproxyIoControl: NDProxy has"...
0x18008a3af  call    cs:__imp_TracePrintfA
0x18008a3b6  nop     dword ptr [rax+rax+00h]
0x18008a3bb  mov     rcx, cs:g_hDriverSync; hDevice
0x18008a3c2  lea     rax, [rsp+8D0h+BytesReturned]
0x18008a3c7  mov     [rsp+8D0h+lpOverlapped], r14; lpOverlapped
0x18008a3cc  lea     r8, [rsp+8D0h+ThreadId]; lpInBuffer
0x18008a3d1  mov     [rsp+8D0h+hTemplateFile], rax; lpBytesReturned
0x18008a3d6  mov     r9d, r15d; nInBufferSize
0x18008a3d9  mov     [rsp+8D0h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x18008a3de  mov     edx, 8FFF23D4h; dwIoControlCode
0x18008a3e3  mov     qword ptr [rsp+8D0h+dwCreationDisposition], r14; lpOutBuffer
0x18008a3e8  call    cs:__imp_DeviceIoControl
0x18008a3ef  nop     dword ptr [rax+rax+00h]
0x18008a3f4  test    eax, eax
0x18008a3f6  jnz     short loc_18008A442
0x18008a3f8  call    cs:__imp_GetLastError
0x18008a3ff  nop     dword ptr [rax+rax+00h]
0x18008a404  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x18008a40b  mov     ebx, eax
  ... truncated ...
```
