# InitializeNdproxyIoControl

- ea: `0x180083f84`
- end: `0x1800846fd`
- name: `InitializeNdproxyIoControl`
- size: `1913`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800275e0`

## callees

- `0x180071cec`
- `0x180083c10`
- `0x180083f84`
- `0x180089ef4`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x180084294`
- `KERNEL32!DeviceIoControl` at `0x180084367`
- `KERNEL32!DeviceIoControl` at `0x1800843ff`
- `KERNEL32!DeviceIoControl` at `0x1800844b1`
- `KERNEL32!DeviceIoControl` at `0x180084294`
- `KERNEL32!DeviceIoControl` at `0x180084367`
- `KERNEL32!DeviceIoControl` at `0x1800843ff`
- `KERNEL32!DeviceIoControl` at `0x1800844b1`
- `KERNEL32!Sleep` at `0x180084332`
- `KERNEL32!Sleep` at `0x180084332`
- `KERNEL32!InitializeCriticalSection` at `0x1800840a0`
- `KERNEL32!InitializeCriticalSection` at `0x1800840a0`
- `KERNEL32!CreateThread` at `0x18008462a`
- `KERNEL32!CreateThread` at `0x18008462a`
- `KERNEL32!GetProcessHeap` at `0x180084568`
- `KERNEL32!GetProcessHeap` at `0x1800845f4`
- `KERNEL32!GetProcessHeap` at `0x180084568`
- `KERNEL32!GetProcessHeap` at `0x1800845f4`
- `KERNEL32!CreateIoCompletionPort` at `0x1800841f9`
- `KERNEL32!CreateIoCompletionPort` at `0x1800841f9`
- `KERNEL32!CreateFileA` at `0x1800840f8`
- `KERNEL32!CreateFileA` at `0x180084194`
- `KERNEL32!CreateFileA` at `0x1800840f8`
- `KERNEL32!CreateFileA` at `0x180084194`
- `KERNEL32!HeapAlloc` at `0x18008457a`
- `KERNEL32!HeapAlloc` at `0x180084603`
- `KERNEL32!HeapAlloc` at `0x18008457a`
- `KERNEL32!HeapAlloc` at `0x180084603`
- `KERNEL32!GetLastError` at `0x180084052`
- `KERNEL32!GetLastError` at `0x18008410b`
- `KERNEL32!GetLastError` at `0x1800841a7`
- `KERNEL32!GetLastError` at `0x18008420c`
- `KERNEL32!GetLastError` at `0x180084375`
- `KERNEL32!GetLastError` at `0x1800844bb`
- `KERNEL32!GetLastError` at `0x180084643`
- `KERNEL32!GetLastError` at `0x18008467c`
- `KERNEL32!GetLastError` at `0x180084052`
- `KERNEL32!GetLastError` at `0x18008410b`
- `KERNEL32!GetLastError` at `0x1800841a7`
- `KERNEL32!GetLastError` at `0x18008420c`
- `KERNEL32!GetLastError` at `0x180084375`
- `KERNEL32!GetLastError` at `0x1800844bb`
- `KERNEL32!GetLastError` at `0x180084643`
- `KERNEL32!GetLastError` at `0x18008467c`
- `rtutils!TracePrintfA` at `0x18008416b`
- `rtutils!TracePrintfA` at `0x180084313`
- `rtutils!TracePrintfA` at `0x18008447e`
- `rtutils!TracePrintfA` at `0x18008455d`
- `rtutils!TracePrintfA` at `0x1800845df`
- `rtutils!TracePrintfA` at `0x1800846c9`
- `rtutils!TracePrintfA` at `0x18008416b`
- `rtutils!TracePrintfA` at `0x180084313`
- `rtutils!TracePrintfA` at `0x18008447e`
- `rtutils!TracePrintfA` at `0x18008455d`
- `rtutils!TracePrintfA` at `0x1800845df`
- `rtutils!TracePrintfA` at `0x1800846c9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x180084040`
- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x180084040`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x1800840b8`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x1800840ca`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x1800840b8`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x1800840ca`

## string_xrefs

- `0x180084070`: `InitializeNdproxyIoControl: CreateMutex failed (0x%x)`
- `0x180084129`: `InitializeNdproxyIoControl: CreateFile(%hs, sync) failed (0x%x)`
- `0x18008408d`: `InitializeNdproxyIoControl: CreateMutex failed (0x%x)`
- `0x1800841c5`: `InitializeNdproxyIoControl: CreateFile(%hs, async) failed (0x%x)`
- `0x18008415c`: `InitializeNdproxyIoControl: CreateFile(%hs, sync) failed (0x%x)`
- `0x18008422a`: `InitializeNdproxyIoControl: CreateIoCompletionPort failed (0x%x)`
- `0x1800841e2`: `InitializeNdproxyIoControl: CreateFile(%hs, async) failed (0x%x)`
- `0x180084247`: `InitializeNdproxyIoControl: CreateIoCompletionPort failed (0x%x)`
- `0x1800845ab`: `InitializeNdproxyIoControl: Failed to allocate thread info`
- `0x1800845d8`: `InitializeNdproxyIoControl: Failed to allocate thread info`
- `0x18008465d`: `InitializeNdproxyIoControl: CreateThread failed (0x%x)`
- `0x180084673`: `InitializeNdproxyIoControl: CreateThread failed (0x%x)`

## pseudocode

```c
__int64 __fastcall InitializeNdproxyIoControl(__int64 a1, __int64 a2, unsigned int a3)
{
  DWORD LastError; // eax
  unsigned int v5; // ebx
  const wchar_t *v6; // rdx
  DWORD v7; // eax
  const wchar_t *v8; // rdx
  HANDLE FileA; // rax
  int v10; // ebx
  BOOL i; // eax
  unsigned int v12; // eax
  __int64 v13; // rdx
  const wchar_t *v14; // r8
  HANDLE ProcessHeap; // rax
  _DWORD *v16; // rax
  _DWORD *v17; // rsi
  HANDLE v18; // rax
  HANDLE v19; // rax
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD InBuffer[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  DWORD ThreadId; // [rsp+54h] [rbp-ACh] BYREF
  CHAR FileName[16]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR DeviceName[8]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR TargetPath[20]; // [rsp+78h] [rbp-88h] BYREF
  int v28; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v29[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  wcscpy(DeviceName, L"NDProxy");
  InBuffer[0] = 1;
  wcscpy(TargetPath, L"\\Device\\NDProxy");
  InBuffer[1] = 1;
  BytesReturned = 0;
  ThreadId = 0;
  v23 = 0;
  strcpy(FileName, "\\\\.\\NDProxy");
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  g_fUseReqId = 0;
  g_pfnCallback = (__int64)NdproxyCallback;
  g_hRasOpenLinesMutex = CreateMutexA(0, 0, 0);
  if ( !g_hRasOpenLinesMutex )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        v6 = L"InitializeNdproxyIoControl: CreateMutex failed (0x%x)";
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
  DefineDosDeviceW(2u, DeviceName, 0);
  DefineDosDeviceW(1u, DeviceName, TargetPath);
  g_hDriverSync = CreateFileA(FileName, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
  if ( g_hDriverSync == (HANDLE)-1LL )
  {
    v7 = GetLastError();
    v5 = v7;
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "InitializeNdproxyIoControl: CreateFile(%hs, sync) failed (0x%x)", FileName, v7);
      goto LABEL_82;
    }
    if ( !(_QWORD)xmmword_1800C9BE0 )
      goto LABEL_82;
    v8 = L"InitializeNdproxyIoControl: CreateFile(%hs, sync) failed (0x%x)";
    goto LABEL_11;
  }
  FileA = CreateFileA(FileName, 0xC0000000, 3u, 0, 3u, 0x40000080u, 0);
  g_hDriverAsync = FileA;
  if ( FileA == (HANDLE)-1LL )
  {
    v7 = GetLastError();
    v5 = v7;
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "InitializeNdproxyIoControl: CreateFile(%hs, async) failed (0x%x)", FileName, v7);
      goto LABEL_82;
    }
    if ( !(_QWORD)xmmword_1800C9BE0 )
      goto LABEL_82;
    v8 = L"InitializeNdproxyIoControl: CreateFile(%hs, async) failed (0x%x)";
LABEL_11:
    LOWORD(v28) = 0;
    FormatRRASErrorString(&v28, v8, FileName, v7);
    goto LABEL_42;
  }
  g_hAsyncIoCompletionPort = CreateIoCompletionPort(FileA, 0, 0, 0);
  if ( g_hAsyncIoCompletionPort == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        v6 = L"InitializeNdproxyIoControl: CreateIoCompletionPort failed (0x%x)";
        goto LABEL_41;
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "InitializeNdproxyIoControl: CreateIoCompletionPort failed (0x%x)", LastError);
    }
    goto LABEL_82;
  }
  v10 = 10;
  for ( i = DeviceIoControl(g_hDriverSync, 0x8FFF23DC, InBuffer, 8u, &g_dwNumNDProxyLines, 4u, &BytesReturned, 0);
        ;
        i = DeviceIoControl(g_hDriverSync, 0x8FFF23DC, InBuffer, 8u, &g_dwNumNDProxyLines, 4u, &BytesReturned, 0) )
  {
    if ( !i || BytesReturned < 4 )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( !(_QWORD)xmmword_1800C9BE0 )
          goto LABEL_82;
        v6 = L"InitializeNdproxyIoControl: GET_NUM_LINES failed (0x%x)";
        goto LABEL_41;
      }
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "InitializeNdproxyIoControl: GET_NUM_LINES failed (0x%x)", LastError);
      goto LABEL_82;
    }
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v28) = 0;
        FormatRRASErrorString(
          &v28,
          L"InitializeNdproxyIoControl: GET_NUM_LINES returned 0x%x lines",
          (unsigned int)g_dwNumNDProxyLines);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v28);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "InitializeNdproxyIoControl: GET_NUM_LINES returned 0x%x lines", g_dwNumNDProxyLines);
    }
    if ( g_dwNumNDProxyLines >= a3 || !v10 )
      break;
    Sleep(0x1F4u);
    --v10;
  }
  if ( !DeviceIoControl(g_hDriverSync, 0x8FFF23C0, InBuffer, 8u, &g_dwNumNDProxyLines, 4u, &BytesReturned, 0)
    || BytesReturned < 4 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        v6 = L"InitializeNdproxyIoControl: CONNECT failed (0x%x)";
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
    if ( (_QWORD)xmmword_1800C9BE0 )
    {
      LOWORD(v28) = 0;
      FormatRRASErrorString(
        &v28,
        L"InitializeNdproxyIoControl: NDProxy has 0x%x lines",
        (unsigned int)g_dwNumNDProxyLines);
      ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v28);
    }
  }
  else if ( dwTraceId != -1 )
  {
    TracePrintfA(dwTraceId, "InitializeNdproxyIoControl: NDProxy has 0x%x lines", g_dwNumNDProxyLines);
  }
  if ( DeviceIoControl(g_hDriverSync, 0x8FFF23D4, &v23, 4u, 0, 0, &BytesReturned, 0) )
  {
    v12 = InitializeMapper();
    v5 = v12;
    if ( v12 )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( !(_QWORD)xmmword_1800C9BE0 )
          goto LABEL_83;
        LOWORD(v28) = 0;
        FormatRRASErrorString(&v28, L"InitializeNdproxyIoControl: InitializeMapper failed (0x%x)", v12);
        v13 = xmmword_1800C9BE0;
        v14 = (const wchar_t *)&v28;
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
      v17 = v16;
      if ( v16 )
      {
        v16[4] = 1024;
        v18 = GetProcessHeap();
        *((_QWORD *)v17 + 1) = HeapAlloc(v18, 8u, 0x400u);
        v19 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)AsyncEventsThread, 0, 0, &ThreadId);
        *(_QWORD *)g_pAsyncEventsThreadInfo = v19;
        if ( !v19 )
        {
          LastError = GetLastError();
          v5 = LastError;
          if ( gIsndpspEtwTracingAvailable )
          {
            if ( (_QWORD)xmmword_1800C9BE0 )
            {
              v6 = L"InitializeNdproxyIoControl: CreateThread failed (0x%x)";
              goto LABEL_41;
            }
          }
          else if ( dwTraceId != -1 )
          {
            TracePrintfA(dwTraceId, "InitializeNdproxyIoControl: CreateThread failed (0x%x)", LastError);
          }
          goto LABEL_82;
        }
        return v5;
      }
      v5 = 14;
      if ( gIsndpspEtwTracingAvailable )
      {
        v13 = *((_QWORD *)&xmmword_1800C9BE0 + 1);
        if ( !*((_QWORD *)&xmmword_1800C9BE0 + 1) )
          goto LABEL_83;
        v14 = L"InitializeNdproxyIoControl: Failed to allocate thread info";
        goto LABEL_66;
      }
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "InitializeNdproxyIoControl: Failed to allocate thread info");
    }
LABEL_83:
    CleanupNdproxyIoControl();
    return v5;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( !(_QWORD)xmmword_1800C9BE0 )
      goto LABEL_82;
    v6 = L"InitializeNdproxyIoControl: SET_DEVICEID_BASE failed (0x%x)";
LABEL_41:
    LOWORD(v28) = 0;
    FormatRRASErrorString(&v28, v6, LastError);
LABEL_42:
    ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v28);
  }
  else if ( dwTraceId != -1 )
  {
    TracePrintfA(dwTraceId, "InitializeNdproxyIoControl: SET_DEVICEID_BASE failed (0x%x)", LastError);
  }
LABEL_82:
  if ( v5 )
    goto LABEL_83;
  return v5;
}

```

## disassembly

```asm
0x180083f84  push    rbp
0x180083f86  push    rbx
0x180083f87  push    rsi
0x180083f88  push    rdi
0x180083f89  push    r12
0x180083f8b  push    r13
0x180083f8d  push    r14
0x180083f8f  push    r15
0x180083f91  lea     rbp, [rsp-7B8h]
0x180083f99  sub     rsp, 8B8h
0x180083fa0  mov     rax, cs:__security_cookie
0x180083fa7  xor     rax, rsp
0x180083faa  mov     [rbp+7F0h+var_50], rax
0x180083fb1  movups  xmm0, xmmword ptr cs:aNdproxy_1; "NDProxy"
0x180083fb8  mov     eax, dword ptr cs:aNdproxy+8; "oxy"
0x180083fbe  xor     r15d, r15d
0x180083fc1  movups  xmm1, xmmword ptr cs:aDeviceNdproxy; "\\Device\\NDProxy"
0x180083fc8  mov     esi, r8d
0x180083fcb  mov     ebx, 1
0x180083fd0  movdqu  xmmword ptr [rsp+8F0h+DeviceName], xmm0
0x180083fd6  xor     edx, edx; Val
0x180083fd8  mov     r8d, 7FCh; Size
0x180083fde  movups  xmm0, xmmword ptr cs:aDeviceNdproxy+10h; "NDProxy"
0x180083fe5  lea     rcx, [rbp+7F0h+var_84C]; void *
0x180083fe9  mov     [rsp+8F0h+InBuffer], ebx
0x180083fed  movups  xmmword ptr [rsp+8F0h+TargetPath], xmm1
0x180083ff2  mov     [rsp+8F0h+var_8A4], ebx
0x180083ff6  movsd   xmm1, qword ptr cs:aNdproxy; "\\\\.\\NDProxy"
0x180083ffe  movups  [rbp+7F0h+var_868], xmm0
0x180084002  mov     [rsp+8F0h+BytesReturned], r15d
0x180084007  mov     [rsp+8F0h+ThreadId], r15d
0x18008400c  mov     [rsp+8F0h+var_8A0], r15d
0x180084011  movsd   qword ptr [rsp+8F0h+FileName], xmm1
0x180084017  mov     [rsp+8F0h+var_890], eax
0x18008401b  mov     [rbp+7F0h+var_850], r15d
0x18008401f  call    memset_0
0x180084024  lea     rax, ?NdproxyCallback@@YAXPEAXK_K111@Z; NdproxyCallback(void *,ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64)
0x18008402b  mov     cs:g_fUseReqId, r15d
0x180084032  xor     r8d, r8d; lpName
0x180084035  mov     cs:g_pfnCallback, rax
0x18008403c  xor     edx, edx; bInitialOwner
0x18008403e  xor     ecx, ecx; lpMutexAttributes
0x180084040  call    cs:__imp_CreateMutexA
0x180084046  mov     cs:g_hRasOpenLinesMutex, rax
0x18008404d  test    rax, rax
0x180084050  jnz     short loc_180084099
0x180084052  call    cs:__imp_GetLastError
0x180084058  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x18008405f  mov     ebx, eax
0x180084061  jz      short loc_18008407C
0x180084063  cmp     qword ptr cs:xmmword_1800C9BE0, r15
0x18008406a  jz      loc_1800846CF
0x180084070  lea     rdx, aInitializendpr_20; "InitializeNdproxyIoControl: CreateMutex"...
0x180084077  jmp     loc_18008439E
0x18008407c  mov     ecx, cs:dwTraceId
0x180084082  or      edi, 0FFFFFFFFh
0x180084085  cmp     ecx, edi
0x180084087  jz      loc_1800846CF
0x18008408d  lea     rdx, aInitializendpr_6; "InitializeNdproxyIoControl: CreateMutex"...
0x180084094  jmp     loc_1800846C6
0x180084099  lea     rcx, g_RequestIDCritSec; lpCriticalSection
0x1800840a0  call    cs:__imp_InitializeCriticalSection
0x1800840a6  xor     r8d, r8d; lpTargetPath
0x1800840a9  mov     cs:g_dwRequestID, ebx
0x1800840af  lea     rdx, [rsp+8F0h+DeviceName]; lpDeviceName
0x1800840b4  lea     ecx, [r8+2]; dwFlags
0x1800840b8  call    cs:__imp_DefineDosDeviceW
0x1800840be  lea     r8, [rsp+8F0h+TargetPath]; lpTargetPath
0x1800840c3  mov     ecx, ebx; dwFlags
0x1800840c5  lea     rdx, [rsp+8F0h+DeviceName]; lpDeviceName
0x1800840ca  call    cs:__imp_DefineDosDeviceW
0x1800840d0  mov     ebx, 3
0x1800840d5  mov     [rsp+8F0h+hTemplateFile], r15; hTemplateFile
0x1800840da  mov     edi, 0C0000000h
0x1800840df  mov     [rsp+8F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800840e7  mov     r8d, ebx; dwShareMode
0x1800840ea  mov     [rsp+8F0h+dwCreationDisposition], ebx; dwCreationDisposition
0x1800840ee  mov     edx, edi; dwDesiredAccess
0x1800840f0  lea     rcx, [rsp+8F0h+FileName]; lpFileName
0x1800840f5  xor     r9d, r9d; lpSecurityAttributes
0x1800840f8  call    cs:__imp_CreateFileA
0x1800840fe  mov     cs:g_hDriverSync, rax
0x180084105  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180084109  jnz     short loc_180084176
0x18008410b  call    cs:__imp_GetLastError
0x180084111  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x180084118  mov     ebx, eax
0x18008411a  jz      short loc_18008414B
0x18008411c  cmp     qword ptr cs:xmmword_1800C9BE0, r15
0x180084123  jz      loc_1800846CF
0x180084129  lea     rdx, aInitializendpr_22; "InitializeNdproxyIoControl: CreateFile("...
0x180084130  lea     r8, [rsp+8F0h+FileName]
0x180084135  mov     word ptr [rbp+7F0h+var_850], r15w
0x18008413a  mov     r9d, eax
0x18008413d  lea     rcx, [rbp+7F0h+var_850]
0x180084141  call    FormatRRASErrorString
0x180084146  jmp     loc_1800843AF
0x18008414b  mov     ecx, cs:dwTraceId; dwTraceID
0x180084151  or      edi, 0FFFFFFFFh
0x180084154  cmp     ecx, edi
0x180084156  jz      loc_1800846CF
0x18008415c  lea     rdx, aInitializendpr_21; "InitializeNdproxyIoControl: CreateFile("...
0x180084163  lea     r8, [rsp+8F0h+FileName]
0x180084168  mov     r9d, eax
0x18008416b  call    cs:__imp_TracePrintfA
0x180084171  jmp     loc_1800846CF
0x180084176  mov     [rsp+8F0h+hTemplateFile], r15; hTemplateFile
0x18008417b  lea     rcx, [rsp+8F0h+FileName]; lpFileName
0x180084180  mov     [rsp+8F0h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x180084188  xor     r9d, r9d; lpSecurityAttributes
0x18008418b  mov     r8d, ebx; dwShareMode
0x18008418e  mov     [rsp+8F0h+dwCreationDisposition], ebx; dwCreationDisposition
0x180084192  mov     edx, edi; dwDesiredAccess
0x180084194  call    cs:__imp_CreateFileA
0x18008419a  mov     cs:g_hDriverAsync, rax
0x1800841a1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800841a5  jnz     short loc_1800841EE
0x1800841a7  call    cs:__imp_GetLastError
0x1800841ad  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x1800841b4  mov     ebx, eax
0x1800841b6  jz      short loc_1800841D1
0x1800841b8  cmp     qword ptr cs:xmmword_1800C9BE0, r15
0x1800841bf  jz      loc_1800846CF
0x1800841c5  lea     rdx, aInitializendpr_8; "InitializeNdproxyIoControl: CreateFile("...
0x1800841cc  jmp     loc_180084130
0x1800841d1  mov     ecx, cs:dwTraceId
0x1800841d7  or      edi, 0FFFFFFFFh
0x1800841da  cmp     ecx, edi
0x1800841dc  jz      loc_1800846CF
0x1800841e2  lea     rdx, aInitializendpr_14; "InitializeNdproxyIoControl: CreateFile("...
0x1800841e9  jmp     loc_180084163
0x1800841ee  xor     r9d, r9d; NumberOfConcurrentThreads
0x1800841f1  xor     r8d, r8d; CompletionKey
0x1800841f4  xor     edx, edx; ExistingCompletionPort
0x1800841f6  mov     rcx, rax; FileHandle
0x1800841f9  call    cs:__imp_CreateIoCompletionPort
0x1800841ff  mov     cs:g_hAsyncIoCompletionPort, rax
0x180084206  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008420a  jnz     short loc_180084253
0x18008420c  call    cs:__imp_GetLastError
0x180084212  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x180084219  mov     ebx, eax
0x18008421b  jz      short loc_180084236
0x18008421d  cmp     qword ptr cs:xmmword_1800C9BE0, r15
0x180084224  jz      loc_1800846CF
0x18008422a  lea     rdx, aInitializendpr_16; "InitializeNdproxyIoControl: CreateIoCom"...
0x180084231  jmp     loc_18008439E
0x180084236  mov     ecx, cs:dwTraceId
0x18008423c  or      edi, 0FFFFFFFFh
0x18008423f  cmp     ecx, edi
0x180084241  jz      loc_1800846CF
0x180084247  lea     rdx, aInitializendpr_17; "InitializeNdproxyIoControl: CreateIoCom"...
0x18008424e  jmp     loc_1800846C6
0x180084253  mov     rcx, cs:g_hDriverSync; hDevice
0x18008425a  lea     rax, [rsp+8F0h+BytesReturned]
0x18008425f  mov     [rsp+8F0h+lpOverlapped], r15; lpOverlapped
0x180084264  lea     r13, g_dwNumNDProxyLines
0x18008426b  mov     [rsp+8F0h+hTemplateFile], rax; lpBytesReturned
0x180084270  lea     r8, [rsp+8F0h+InBuffer]; lpInBuffer
0x180084275  mov     ebx, 0Ah
0x18008427a  mov     edx, 8FFF23DCh; dwIoControlCode
0x18008427f  lea     r14d, [rbx-6]
0x180084283  lea     r12d, [rbx-2]
0x180084287  mov     [rsp+8F0h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x18008428c  mov     r9d, r12d; nInBufferSize
0x18008428f  mov     qword ptr [rsp+8F0h+dwCreationDisposition], r13; lpOutBuffer
0x180084294  call    cs:__imp_DeviceIoControl
0x18008429a  or      edi, 0FFFFFFFFh
0x18008429d  jmp     loc_18008436D
0x1800842a2  cmp     [rsp+8F0h+BytesReturned], r14d
0x1800842a7  jb      loc_180084375
0x1800842ad  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x1800842b4  jz      short loc_1800842FB
0x1800842b6  cmp     qword ptr cs:xmmword_1800C9BE0, r15
0x1800842bd  jz      short loc_180084319
0x1800842bf  mov     r8d, cs:g_dwNumNDProxyLines
0x1800842c6  lea     rdx, aInitializendpr_0; "InitializeNdproxyIoControl: GET_NUM_LIN"...
0x1800842cd  lea     rcx, [rbp+7F0h+var_850]
0x1800842d1  mov     word ptr [rbp+7F0h+var_850], r15w
0x1800842d6  call    FormatRRASErrorString
0x1800842db  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x1800842e2  lea     r8, [rbp+7F0h+var_850]
0x1800842e6  mov     rcx, cs:gNdpspEtwContext
0x1800842ed  mov     rax, cs:gNdpspTemplateFunc
0x1800842f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800842f9  jmp     short loc_180084319
0x1800842fb  mov     ecx, cs:dwTraceId; dwTraceID
0x180084301  cmp     ecx, edi
0x180084303  jz      short loc_180084319
0x180084305  mov     r8d, cs:g_dwNumNDProxyLines
0x18008430c  lea     rdx, aInitializendpr_19; "InitializeNdproxyIoControl: GET_NUM_LIN"...
0x180084313  call    cs:__imp_TracePrintfA
0x180084319  cmp     cs:g_dwNumNDProxyLines, esi
0x18008431f  jnb     loc_1800843D2
0x180084325  test    ebx, ebx
0x180084327  jz      loc_1800843D2
0x18008432d  mov     ecx, 1F4h; dwMilliseconds
0x180084332  call    cs:__imp_Sleep
0x180084338  mov     rcx, cs:g_hDriverSync; hDevice
0x18008433f  lea     rax, [rsp+8F0h+BytesReturned]
0x180084344  mov     [rsp+8F0h+lpOverlapped], r15; lpOverlapped
0x180084349  lea     r8, [rsp+8F0h+InBuffer]; lpInBuffer
0x18008434e  mov     [rsp+8F0h+hTemplateFile], rax; lpBytesReturned
0x180084353  add     ebx, edi
0x180084355  mov     [rsp+8F0h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x18008435a  mov     r9d, r12d; nInBufferSize
0x18008435d  mov     edx, 8FFF23DCh; dwIoControlCode
0x180084362  mov     qword ptr [rsp+8F0h+dwCreationDisposition], r13; lpOutBuffer
0x180084367  call    cs:__imp_DeviceIoControl
0x18008436d  test    eax, eax
0x18008436f  jnz     loc_1800842A2
0x180084375  call    cs:__imp_GetLastError
0x18008437b  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x180084382  mov     ebx, eax
0x180084384  jz      loc_1800846B5
0x18008438a  cmp     qword ptr cs:xmmword_1800C9BE0, r15
0x180084391  jz      loc_1800846CF
0x180084397  lea     rdx, aInitializendpr_12; "InitializeNdproxyIoControl: GET_NUM_LIN"...
0x18008439e  mov     r8d, eax
0x1800843a1  mov     word ptr [rbp+7F0h+var_850], r15w
0x1800843a6  lea     rcx, [rbp+7F0h+var_850]
0x1800843aa  call    FormatRRASErrorString
0x1800843af  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x1800843b6  lea     r8, [rbp+7F0h+var_850]
0x1800843ba  mov     rcx, cs:gNdpspEtwContext
0x1800843c1  mov     rax, cs:gNdpspTemplateFunc
0x1800843c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800843cd  jmp     loc_1800846CF
0x1800843d2  mov     rcx, cs:g_hDriverSync; hDevice
0x1800843d9  lea     rax, [rsp+8F0h+BytesReturned]
0x1800843de  mov     [rsp+8F0h+lpOverlapped], r15; lpOverlapped
0x1800843e3  lea     r8, [rsp+8F0h+InBuffer]; lpInBuffer
0x1800843e8  mov     [rsp+8F0h+hTemplateFile], rax; lpBytesReturned
0x1800843ed  mov     r9d, r12d; nInBufferSize
0x1800843f0  mov     [rsp+8F0h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x1800843f5  mov     edx, 8FFF23C0h; dwIoControlCode
0x1800843fa  mov     qword ptr [rsp+8F0h+dwCreationDisposition], r13; lpOutBuffer
0x1800843ff  call    cs:__imp_DeviceIoControl
0x180084405  test    eax, eax
0x180084407  jz      loc_18008467C
0x18008440d  cmp     [rsp+8F0h+BytesReturned], r14d
0x180084412  jb      loc_18008467C
0x180084418  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x18008441f  jz      short loc_180084466
0x180084421  cmp     qword ptr cs:xmmword_1800C9BE0, r15
0x180084428  jz      short loc_180084484
0x18008442a  mov     r8d, cs:g_dwNumNDProxyLines
0x180084431  lea     rdx, aInitializendpr_15; "InitializeNdproxyIoControl: NDProxy has"...
0x180084438  lea     rcx, [rbp+7F0h+var_850]
0x18008443c  mov     word ptr [rbp+7F0h+var_850], r15w
0x180084441  call    FormatRRASErrorString
0x180084446  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x18008444d  lea     r8, [rbp+7F0h+var_850]
0x180084451  mov     rcx, cs:gNdpspEtwContext
0x180084458  mov     rax, cs:gNdpspTemplateFunc
0x18008445f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084464  jmp     short loc_180084484
0x180084466  mov     ecx, cs:dwTraceId; dwTraceID
0x18008446c  cmp     ecx, edi
0x18008446e  jz      short loc_180084484
0x180084470  mov     r8d, cs:g_dwNumNDProxyLines
0x180084477  lea     rdx, aInitializendpr_3; "InitializeNdproxyIoControl: NDProxy has"...
0x18008447e  call    cs:__imp_TracePrintfA
0x180084484  mov     rcx, cs:g_hDriverSync; hDevice
0x18008448b  lea     rax, [rsp+8F0h+BytesReturned]
0x180084490  mov     [rsp+8F0h+lpOverlapped], r15; lpOverlapped
0x180084495  lea     r8, [rsp+8F0h+var_8A0]; lpInBuffer
0x18008449a  mov     [rsp+8F0h+hTemplateFile], rax; lpBytesReturned
0x18008449f  mov     r9d, r14d; nInBufferSize
0x1800844a2  mov     [rsp+8F0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x1800844a7  mov     edx, 8FFF23D4h; dwIoControlCode
0x1800844ac  mov     qword ptr [rsp+8F0h+dwCreationDisposition], r15; lpOutBuffer
0x1800844b1  call    cs:__imp_DeviceIoControl
0x1800844b7  test    eax, eax
0x1800844b9  jnz     short loc_1800844FF
0x1800844bb  call    cs:__imp_GetLastError
0x1800844c1  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x1800844c8  mov     ebx, eax
0x1800844ca  jz      short loc_1800844E5
0x1800844cc  cmp     qword ptr cs:xmmword_1800C9BE0, r15
0x1800844d3  jz      loc_1800846CF
0x1800844d9  lea     rdx, aInitializendpr; "InitializeNdproxyIoControl: SET_DEVICEI"...
0x1800844e0  jmp     loc_18008439E
0x1800844e5  mov     ecx, cs:dwTraceId
0x1800844eb  cmp     ecx, edi
0x1800844ed  jz      loc_1800846CF
0x1800844f3  lea     rdx, aInitializendpr_11; "InitializeNdproxyIoControl: SET_DEVICEI"...
0x1800844fa  jmp     loc_1800846C6
0x1800844ff  call    InitializeMapper
0x180084504  mov     ebx, eax
0x180084506  test    eax, eax
0x180084508  jz      short loc_180084568
0x18008450a  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x180084511  jz      short loc_180084545
0x180084513  cmp     qword ptr cs:xmmword_1800C9BE0, r15
0x18008451a  jz      loc_1800846D3
0x180084520  mov     r8d, eax
0x180084523  mov     word ptr [rbp+7F0h+var_850], r15w
0x180084528  lea     rdx, aInitializendpr_9; "InitializeNdproxyIoControl: InitializeM"...
0x18008452f  lea     rcx, [rbp+7F0h+var_850]
  ... truncated ...
```
