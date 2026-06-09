# AsyncDriverRequest

- ea: `0x180020c98`
- end: `0x180020f6b`
- name: `AsyncDriverRequest`
- size: `723`
- prototype: `void __fastcall(DWORD dwIoControlCode, char *lpMem)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800231f8`
- `0x180023404`
- `0x180023e24`
- `0x1800257e4`

## callees

- `0x180020c98`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020e10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020f23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020e10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020f23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020e1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020f31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020e1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020f31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020db9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020e01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020e28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020f14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020f39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020db9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020e01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020e28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020f14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020f39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020dad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020df2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020f05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020dad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020df2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020f05`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020e0a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020f1d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020e0a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020f1d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180020de7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180020de7`
- `rtutils!TracePrintfA` at `0x180020d9a`
- `rtutils!TracePrintfA` at `0x180020ecc`
- `rtutils!TracePrintfA` at `0x180020d9a`
- `rtutils!TracePrintfA` at `0x180020ecc`

## pseudocode

```c
void __fastcall AsyncDriverRequest(DWORD dwIoControlCode, char *lpMem)
{
  char *lpOverlapped; // rdi
  _DWORD *lpOutBuffer; // rsi
  int v5; // r8d
  __int64 v6; // r9
  DWORD nOutBufferSize; // ebx
  BOOL v8; // ebx
  bool v9; // zf
  struct _RTL_CRITICAL_SECTION *v10; // rcx
  HANDLE ProcessHeap; // rax
  DWORD LastError; // eax
  struct _RTL_CRITICAL_SECTION *v13; // rcx
  HANDLE v14; // rax
  DWORD BytesReturned[4]; // [rsp+40h] [rbp-848h] BYREF
  int v16; // [rsp+50h] [rbp-838h] BYREF
  _BYTE v17[2044]; // [rsp+54h] [rbp-834h] BYREF

  lpOverlapped = lpMem;
  BytesReturned[0] = 0;
  lpOutBuffer = lpMem + 104;
  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( qword_18003EC40 )
    {
      v5 = lpOutBuffer[8];
      v6 = (unsigned int)lpOutBuffer[9];
      LOWORD(v16) = 0;
      FormatRRASErrorString(
        &v16,
        L"AsyncDriverRequest: Oid(%hs), devID(0x%x), reqID(0x%x), hCall(0x%x)",
        off_18002B190[v5 - 117637377],
        v6,
        lpOutBuffer[12],
        lpOutBuffer[13]);
      ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v16);
    }
  }
  else if ( dwTraceId != -1 )
  {
    TracePrintfA(
      dwTraceId,
      "AsyncDriverRequest: Oid(%hs), devID(0x%x), reqID(0x%x), hCall(0x%x)",
      off_18002B190[lpOutBuffer[8] - 117637377],
      lpOutBuffer[9],
      lpOutBuffer[12],
      lpOutBuffer[13]);
  }
  nOutBufferSize = lpOutBuffer[10] + 55;
  EnterCriticalSection((LPCRITICAL_SECTION)(lpOverlapped + 48));
  ++*((_DWORD *)lpOverlapped + 22);
  LeaveCriticalSection((LPCRITICAL_SECTION)(lpOverlapped + 48));
  v8 = DeviceIoControl(
         g_hDriverAsync,
         dwIoControlCode,
         lpOutBuffer,
         nOutBufferSize,
         lpOutBuffer,
         nOutBufferSize,
         BytesReturned,
         (LPOVERLAPPED)lpOverlapped);
  EnterCriticalSection((LPCRITICAL_SECTION)(lpOverlapped + 48));
  v9 = (*((_DWORD *)lpOverlapped + 22))-- == 1;
  v10 = (struct _RTL_CRITICAL_SECTION *)(lpOverlapped + 48);
  if ( v9 )
  {
    LeaveCriticalSection(v10);
    DeleteCriticalSection((LPCRITICAL_SECTION)(lpOverlapped + 48));
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpOverlapped);
    lpOverlapped = 0;
  }
  else
  {
    LeaveCriticalSection(v10);
  }
  if ( !v8 )
  {
    LastError = GetLastError();
    if ( LastError != 997 )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( qword_18003EC40 )
        {
          LOWORD(v16) = 0;
          FormatRRASErrorString(
            &v16,
            L"AsyncDriverRequest: IoCtl (Oid %hs) failed (0x%x)",
            off_18002B190[lpOutBuffer[8] - 117637377],
            LastError);
          ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v16);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(
          dwTraceId,
          "AsyncDriverRequest: IoCtl (Oid %hs) failed (0x%x)",
          off_18002B190[lpOutBuffer[8] - 117637377],
          LastError);
      }
      ((void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD, __int64, _QWORD))g_pfnCallback)(
        0,
        12,
        0,
        (unsigned int)lpOutBuffer[12],
        2147483720LL,
        0);
      EnterCriticalSection((LPCRITICAL_SECTION)(lpOverlapped + 48));
      v9 = (*((_DWORD *)lpOverlapped + 22))-- == 1;
      v13 = (struct _RTL_CRITICAL_SECTION *)(lpOverlapped + 48);
      if ( v9 )
      {
        LeaveCriticalSection(v13);
        DeleteCriticalSection((LPCRITICAL_SECTION)(lpOverlapped + 48));
        v14 = GetProcessHeap();
        HeapFree(v14, 0, lpOverlapped);
      }
      else
      {
        LeaveCriticalSection(v13);
      }
    }
  }
}

```

## disassembly

```asm
0x180020c98  mov     [rsp+arg_10], rbx
0x180020c9d  mov     [rsp+arg_18], rbp
0x180020ca2  push    rsi
0x180020ca3  push    rdi
0x180020ca4  push    r12
0x180020ca6  push    r13
0x180020ca8  push    r14
0x180020caa  sub     rsp, 860h
0x180020cb1  mov     rax, cs:__security_cookie
0x180020cb8  xor     rax, rsp
0x180020cbb  mov     [rsp+888h+var_38], rax
0x180020cc3  mov     rdi, rdx
0x180020cc6  mov     [rsp+888h+BytesReturned], 0
0x180020cce  mov     r14d, ecx
0x180020cd1  lea     rsi, [rdx+68h]
0x180020cd5  xor     eax, eax
0x180020cd7  lea     rcx, [rsp+888h+var_834]; void *
0x180020cdc  xor     edx, edx; Val
0x180020cde  mov     [rsp+888h+var_838], eax
0x180020ce2  mov     r8d, 7FCh; Size
0x180020ce8  call    memset_0
0x180020ced  or      r12d, 0FFFFFFFFh
0x180020cf1  lea     rdx, off_18002B190; "Accept"
0x180020cf8  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180020cff  mov     r13d, 7030101h
0x180020d05  jz      short loc_180020D6B
0x180020d07  cmp     cs:qword_18003EC40, 0
0x180020d0f  jz      loc_180020DA0
0x180020d15  mov     r8d, [rsi+20h]
0x180020d19  lea     rcx, [rsp+888h+var_838]
0x180020d1e  mov     r9d, [rsi+24h]
0x180020d22  xor     eax, eax
0x180020d24  mov     word ptr [rsp+888h+var_838], ax
0x180020d29  sub     r8d, r13d
0x180020d2c  mov     eax, [rsi+34h]
0x180020d2f  mov     [rsp+888h+nOutBufferSize], eax
0x180020d33  mov     eax, [rsi+30h]
0x180020d36  mov     r8, [rdx+r8*8]
0x180020d3a  lea     rdx, aAsyncdriverreq; "AsyncDriverRequest: Oid(%hs), devID(0x%"...
0x180020d41  mov     dword ptr [rsp+888h+lpOutBuffer], eax
0x180020d45  call    FormatRRASErrorString
0x180020d4a  mov     rdx, cs:qword_18003EC40
0x180020d51  lea     r8, [rsp+888h+var_838]
0x180020d56  mov     rcx, cs:gNdpspEtwContext
0x180020d5d  mov     rax, cs:gNdpspTemplateFunc
0x180020d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d69  jmp     short loc_180020DA0
0x180020d6b  mov     ecx, cs:dwTraceId; dwTraceID
0x180020d71  cmp     ecx, r12d
0x180020d74  jz      short loc_180020DA0
0x180020d76  mov     r8d, [rsi+20h]
0x180020d7a  mov     eax, [rsi+34h]
0x180020d7d  sub     r8d, r13d
0x180020d80  mov     r9d, [rsi+24h]
0x180020d84  mov     [rsp+888h+nOutBufferSize], eax
0x180020d88  mov     eax, [rsi+30h]
0x180020d8b  mov     r8, [rdx+r8*8]
0x180020d8f  lea     rdx, aAsyncdriverreq_0; "AsyncDriverRequest: Oid(%hs), devID(0x%"...
0x180020d96  mov     dword ptr [rsp+888h+lpOutBuffer], eax
0x180020d9a  call    cs:__imp_TracePrintfA
0x180020da0  mov     ebx, [rsi+28h]
0x180020da3  lea     rbp, [rdi+30h]
0x180020da7  mov     rcx, rbp; lpCriticalSection
0x180020daa  add     ebx, 37h ; '7'
0x180020dad  call    cs:__imp_EnterCriticalSection
0x180020db3  inc     dword ptr [rdi+58h]
0x180020db6  mov     rcx, rbp; lpCriticalSection
0x180020db9  call    cs:__imp_LeaveCriticalSection
0x180020dbf  mov     rcx, cs:g_hDriverAsync; hDevice
0x180020dc6  lea     rax, [rsp+888h+BytesReturned]
0x180020dcb  mov     [rsp+888h+lpOverlapped], rdi; lpOverlapped
0x180020dd0  mov     r9d, ebx; nInBufferSize
0x180020dd3  mov     [rsp+888h+lpBytesReturned], rax; lpBytesReturned
0x180020dd8  mov     r8, rsi; lpInBuffer
0x180020ddb  mov     [rsp+888h+nOutBufferSize], ebx; nOutBufferSize
0x180020ddf  mov     edx, r14d; dwIoControlCode
0x180020de2  mov     [rsp+888h+lpOutBuffer], rsi; lpOutBuffer
0x180020de7  call    cs:__imp_DeviceIoControl
0x180020ded  mov     rcx, rbp; lpCriticalSection
0x180020df0  mov     ebx, eax
0x180020df2  call    cs:__imp_EnterCriticalSection
0x180020df8  add     [rdi+58h], r12d
0x180020dfc  mov     rcx, rbp; lpCriticalSection
0x180020dff  jnz     short loc_180020E28
0x180020e01  call    cs:__imp_LeaveCriticalSection
0x180020e07  mov     rcx, rbp; lpCriticalSection
0x180020e0a  call    cs:__imp_DeleteCriticalSection
0x180020e10  call    cs:__imp_GetProcessHeap
0x180020e16  mov     r8, rdi; lpMem
0x180020e19  xor     edx, edx; dwFlags
0x180020e1b  mov     rcx, rax; hHeap
0x180020e1e  call    cs:__imp_HeapFree
0x180020e24  xor     edi, edi
0x180020e26  jmp     short loc_180020E2E
0x180020e28  call    cs:__imp_LeaveCriticalSection
0x180020e2e  cmp     ebx, 1
0x180020e31  jz      loc_180020F3F
0x180020e37  call    cs:__imp_GetLastError
0x180020e3d  mov     r9d, eax
0x180020e40  cmp     eax, 3E5h
0x180020e45  jz      loc_180020F3F
0x180020e4b  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180020e52  jz      short loc_180020EA8
0x180020e54  cmp     cs:qword_18003EC40, 0
0x180020e5c  jz      short loc_180020ED2
0x180020e5e  xor     ecx, ecx
0x180020e60  lea     rax, off_18002B190; "Accept"
0x180020e67  mov     word ptr [rsp+888h+var_838], cx
0x180020e6c  lea     rdx, aAsyncdriverreq_1; "AsyncDriverRequest: IoCtl (Oid %hs) fai"...
0x180020e73  mov     ecx, [rsi+20h]
0x180020e76  sub     ecx, r13d
0x180020e79  mov     r8, [rax+rcx*8]
0x180020e7d  lea     rcx, [rsp+888h+var_838]
0x180020e82  call    FormatRRASErrorString
0x180020e87  mov     rdx, cs:qword_18003EC40
0x180020e8e  lea     r8, [rsp+888h+var_838]
0x180020e93  mov     rcx, cs:gNdpspEtwContext
0x180020e9a  mov     rax, cs:gNdpspTemplateFunc
0x180020ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ea6  jmp     short loc_180020ED2
0x180020ea8  mov     ecx, cs:dwTraceId; dwTraceID
0x180020eae  cmp     ecx, r12d
0x180020eb1  jz      short loc_180020ED2
0x180020eb3  mov     r8d, [rsi+20h]
0x180020eb7  lea     rax, off_18002B190; "Accept"
0x180020ebe  sub     r8d, r13d
0x180020ec1  lea     rdx, aAsyncdriverreq_2; "AsyncDriverRequest: IoCtl (Oid %hs) fai"...
0x180020ec8  mov     r8, [rax+r8*8]
0x180020ecc  call    cs:__imp_TracePrintfA
0x180020ed2  mov     r9d, [rsi+30h]
0x180020ed6  xor     r8d, r8d
0x180020ed9  mov     eax, 80000048h
0x180020ede  mov     qword ptr [rsp+888h+nOutBufferSize], 0
0x180020ee7  mov     [rsp+888h+lpOutBuffer], rax
0x180020eec  xor     ecx, ecx
0x180020eee  mov     rax, cs:g_pfnCallback
0x180020ef5  lea     edx, [r8+0Ch]
0x180020ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020efe  lea     rbx, [rdi+30h]
0x180020f02  mov     rcx, rbx; lpCriticalSection
0x180020f05  call    cs:__imp_EnterCriticalSection
0x180020f0b  add     [rdi+58h], r12d
0x180020f0f  mov     rcx, rbx; lpCriticalSection
0x180020f12  jnz     short loc_180020F39
0x180020f14  call    cs:__imp_LeaveCriticalSection
0x180020f1a  mov     rcx, rbx; lpCriticalSection
0x180020f1d  call    cs:__imp_DeleteCriticalSection
0x180020f23  call    cs:__imp_GetProcessHeap
0x180020f29  mov     r8, rdi; lpMem
0x180020f2c  xor     edx, edx; dwFlags
0x180020f2e  mov     rcx, rax; hHeap
0x180020f31  call    cs:__imp_HeapFree
0x180020f37  jmp     short loc_180020F3F
0x180020f39  call    cs:__imp_LeaveCriticalSection
0x180020f3f  mov     rcx, [rsp+888h+var_38]
0x180020f47  xor     rcx, rsp; StackCookie
0x180020f4a  call    __security_check_cookie
0x180020f4f  lea     r11, [rsp+888h+var_28]
0x180020f57  mov     rbx, [r11+40h]
0x180020f5b  mov     rbp, [r11+48h]
0x180020f5f  mov     rsp, r11
0x180020f62  pop     r14
0x180020f64  pop     r13
0x180020f66  pop     r12
0x180020f68  pop     rdi
0x180020f69  pop     rsi
0x180020f6a  retn
```
