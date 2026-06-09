# AsyncDriverRequest

- ea: `0x18008308c`
- end: `0x18008335f`
- name: `AsyncDriverRequest`
- size: `723`
- prototype: `__int64 __fastcall(DWORD dwIoControlCode, LPVOID lpMem)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800855e8`
- `0x180085818`
- `0x18008625c`
- `0x180087070`

## callees

- `0x180071cec`
- `0x18008308c`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800831fe`
- `KERNEL32!DeleteCriticalSection` at `0x180083311`
- `KERNEL32!DeleteCriticalSection` at `0x1800831fe`
- `KERNEL32!DeleteCriticalSection` at `0x180083311`
- `KERNEL32!DeviceIoControl` at `0x1800831db`
- `KERNEL32!DeviceIoControl` at `0x1800831db`
- `KERNEL32!GetProcessHeap` at `0x180083204`
- `KERNEL32!GetProcessHeap` at `0x180083317`
- `KERNEL32!GetProcessHeap` at `0x180083204`
- `KERNEL32!GetProcessHeap` at `0x180083317`
- `KERNEL32!GetLastError` at `0x18008322b`
- `KERNEL32!GetLastError` at `0x18008322b`
- `KERNEL32!LeaveCriticalSection` at `0x1800831ad`
- `KERNEL32!LeaveCriticalSection` at `0x1800831f5`
- `KERNEL32!LeaveCriticalSection` at `0x18008321c`
- `KERNEL32!LeaveCriticalSection` at `0x180083308`
- `KERNEL32!LeaveCriticalSection` at `0x18008332d`
- `KERNEL32!LeaveCriticalSection` at `0x1800831ad`
- `KERNEL32!LeaveCriticalSection` at `0x1800831f5`
- `KERNEL32!LeaveCriticalSection` at `0x18008321c`
- `KERNEL32!LeaveCriticalSection` at `0x180083308`
- `KERNEL32!LeaveCriticalSection` at `0x18008332d`
- `KERNEL32!EnterCriticalSection` at `0x1800831a1`
- `KERNEL32!EnterCriticalSection` at `0x1800831e6`
- `KERNEL32!EnterCriticalSection` at `0x1800832f9`
- `KERNEL32!EnterCriticalSection` at `0x1800831a1`
- `KERNEL32!EnterCriticalSection` at `0x1800831e6`
- `KERNEL32!EnterCriticalSection` at `0x1800832f9`
- `KERNEL32!HeapFree` at `0x180083212`
- `KERNEL32!HeapFree` at `0x180083325`
- `KERNEL32!HeapFree` at `0x180083212`
- `KERNEL32!HeapFree` at `0x180083325`
- `rtutils!TracePrintfA` at `0x18008318e`
- `rtutils!TracePrintfA` at `0x1800832c0`
- `rtutils!TracePrintfA` at `0x18008318e`
- `rtutils!TracePrintfA` at `0x1800832c0`

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
    if ( (_QWORD)xmmword_1800C9BE0 )
    {
      v5 = lpOutBuffer[8];
      v6 = (unsigned int)lpOutBuffer[9];
      LOWORD(v16) = 0;
      FormatRRASErrorString(
        &v16,
        L"AsyncDriverRequest: Oid(%hs), devID(0x%x), reqID(0x%x), hCall(0x%x)",
        off_18008FDC0[v5 - 117637377],
        v6,
        lpOutBuffer[12],
        lpOutBuffer[13]);
      ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v16);
    }
  }
  else if ( dwTraceId != -1 )
  {
    TracePrintfA(
      dwTraceId,
      "AsyncDriverRequest: Oid(%hs), devID(0x%x), reqID(0x%x), hCall(0x%x)",
      off_18008FDC0[lpOutBuffer[8] - 117637377],
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
        if ( (_QWORD)xmmword_1800C9BE0 )
        {
          LOWORD(v16) = 0;
          FormatRRASErrorString(
            &v16,
            L"AsyncDriverRequest: IoCtl (Oid %hs) failed (0x%x)",
            off_18008FDC0[lpOutBuffer[8] - 117637377],
            LastError);
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v16);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(
          dwTraceId,
          "AsyncDriverRequest: IoCtl (Oid %hs) failed (0x%x)",
          off_18008FDC0[lpOutBuffer[8] - 117637377],
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
0x18008308c  mov     [rsp+arg_10], rbx
0x180083091  mov     [rsp+arg_18], rbp
0x180083096  push    rsi
0x180083097  push    rdi
0x180083098  push    r12
0x18008309a  push    r13
0x18008309c  push    r14
0x18008309e  sub     rsp, 860h
0x1800830a5  mov     rax, cs:__security_cookie
0x1800830ac  xor     rax, rsp
0x1800830af  mov     [rsp+888h+var_38], rax
0x1800830b7  mov     rdi, rdx
0x1800830ba  mov     [rsp+888h+BytesReturned], 0
0x1800830c2  mov     r14d, ecx
0x1800830c5  lea     rsi, [rdx+68h]
0x1800830c9  xor     eax, eax
0x1800830cb  lea     rcx, [rsp+888h+var_834]; void *
0x1800830d0  xor     edx, edx; Val
0x1800830d2  mov     [rsp+888h+var_838], eax
0x1800830d6  mov     r8d, 7FCh; Size
0x1800830dc  call    memset_0
0x1800830e1  or      r12d, 0FFFFFFFFh
0x1800830e5  lea     rdx, off_18008FDC0; "Accept"
0x1800830ec  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x1800830f3  mov     r13d, 7030101h
0x1800830f9  jz      short loc_18008315F
0x1800830fb  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x180083103  jz      loc_180083194
0x180083109  mov     r8d, [rsi+20h]
0x18008310d  lea     rcx, [rsp+888h+var_838]
0x180083112  mov     r9d, [rsi+24h]
0x180083116  xor     eax, eax
0x180083118  mov     word ptr [rsp+888h+var_838], ax
0x18008311d  sub     r8d, r13d
0x180083120  mov     eax, [rsi+34h]
0x180083123  mov     [rsp+888h+nOutBufferSize], eax
0x180083127  mov     eax, [rsi+30h]
0x18008312a  mov     r8, [rdx+r8*8]
0x18008312e  lea     rdx, aAsyncdriverreq; "AsyncDriverRequest: Oid(%hs), devID(0x%"...
0x180083135  mov     dword ptr [rsp+888h+lpOutBuffer], eax
0x180083139  call    FormatRRASErrorString
0x18008313e  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180083145  lea     r8, [rsp+888h+var_838]
0x18008314a  mov     rcx, cs:gNdpspEtwContext
0x180083151  mov     rax, cs:gNdpspTemplateFunc
0x180083158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008315d  jmp     short loc_180083194
0x18008315f  mov     ecx, cs:dwTraceId; dwTraceID
0x180083165  cmp     ecx, r12d
0x180083168  jz      short loc_180083194
0x18008316a  mov     r8d, [rsi+20h]
0x18008316e  mov     eax, [rsi+34h]
0x180083171  sub     r8d, r13d
0x180083174  mov     r9d, [rsi+24h]
0x180083178  mov     [rsp+888h+nOutBufferSize], eax
0x18008317c  mov     eax, [rsi+30h]
0x18008317f  mov     r8, [rdx+r8*8]
0x180083183  lea     rdx, szFormat; "AsyncDriverRequest: Oid(%hs), devID(0x%"...
0x18008318a  mov     dword ptr [rsp+888h+lpOutBuffer], eax
0x18008318e  call    cs:__imp_TracePrintfA
0x180083194  mov     ebx, [rsi+28h]
0x180083197  lea     rbp, [rdi+30h]
0x18008319b  mov     rcx, rbp; lpCriticalSection
0x18008319e  add     ebx, 37h ; '7'
0x1800831a1  call    cs:__imp_EnterCriticalSection
0x1800831a7  inc     dword ptr [rdi+58h]
0x1800831aa  mov     rcx, rbp; lpCriticalSection
0x1800831ad  call    cs:__imp_LeaveCriticalSection
0x1800831b3  mov     rcx, cs:g_hDriverAsync; hDevice
0x1800831ba  lea     rax, [rsp+888h+BytesReturned]
0x1800831bf  mov     [rsp+888h+lpOverlapped], rdi; lpOverlapped
0x1800831c4  mov     r9d, ebx; nInBufferSize
0x1800831c7  mov     [rsp+888h+lpBytesReturned], rax; lpBytesReturned
0x1800831cc  mov     r8, rsi; lpInBuffer
0x1800831cf  mov     [rsp+888h+nOutBufferSize], ebx; nOutBufferSize
0x1800831d3  mov     edx, r14d; dwIoControlCode
0x1800831d6  mov     [rsp+888h+lpOutBuffer], rsi; lpOutBuffer
0x1800831db  call    cs:__imp_DeviceIoControl
0x1800831e1  mov     rcx, rbp; lpCriticalSection
0x1800831e4  mov     ebx, eax
0x1800831e6  call    cs:__imp_EnterCriticalSection
0x1800831ec  add     [rdi+58h], r12d
0x1800831f0  mov     rcx, rbp; lpCriticalSection
0x1800831f3  jnz     short loc_18008321C
0x1800831f5  call    cs:__imp_LeaveCriticalSection
0x1800831fb  mov     rcx, rbp; lpCriticalSection
0x1800831fe  call    cs:__imp_DeleteCriticalSection
0x180083204  call    cs:__imp_GetProcessHeap
0x18008320a  mov     r8, rdi; lpMem
0x18008320d  xor     edx, edx; dwFlags
0x18008320f  mov     rcx, rax; hHeap
0x180083212  call    cs:__imp_HeapFree
0x180083218  xor     edi, edi
0x18008321a  jmp     short loc_180083222
0x18008321c  call    cs:__imp_LeaveCriticalSection
0x180083222  cmp     ebx, 1
0x180083225  jz      loc_180083333
0x18008322b  call    cs:__imp_GetLastError
0x180083231  mov     r9d, eax
0x180083234  cmp     eax, 3E5h
0x180083239  jz      loc_180083333
0x18008323f  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180083246  jz      short loc_18008329C
0x180083248  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x180083250  jz      short loc_1800832C6
0x180083252  xor     ecx, ecx
0x180083254  lea     rax, off_18008FDC0; "Accept"
0x18008325b  mov     word ptr [rsp+888h+var_838], cx
0x180083260  lea     rdx, aAsyncdriverreq_1; "AsyncDriverRequest: IoCtl (Oid %hs) fai"...
0x180083267  mov     ecx, [rsi+20h]
0x18008326a  sub     ecx, r13d
0x18008326d  mov     r8, [rax+rcx*8]
0x180083271  lea     rcx, [rsp+888h+var_838]
0x180083276  call    FormatRRASErrorString
0x18008327b  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180083282  lea     r8, [rsp+888h+var_838]
0x180083287  mov     rcx, cs:gNdpspEtwContext
0x18008328e  mov     rax, cs:gNdpspTemplateFunc
0x180083295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008329a  jmp     short loc_1800832C6
0x18008329c  mov     ecx, cs:dwTraceId; dwTraceID
0x1800832a2  cmp     ecx, r12d
0x1800832a5  jz      short loc_1800832C6
0x1800832a7  mov     r8d, [rsi+20h]
0x1800832ab  lea     rax, off_18008FDC0; "Accept"
0x1800832b2  sub     r8d, r13d
0x1800832b5  lea     rdx, aAsyncdriverreq_2; "AsyncDriverRequest: IoCtl (Oid %hs) fai"...
0x1800832bc  mov     r8, [rax+r8*8]
0x1800832c0  call    cs:__imp_TracePrintfA
0x1800832c6  mov     r9d, [rsi+30h]
0x1800832ca  xor     r8d, r8d
0x1800832cd  mov     eax, 80000048h
0x1800832d2  mov     qword ptr [rsp+888h+nOutBufferSize], 0
0x1800832db  mov     [rsp+888h+lpOutBuffer], rax
0x1800832e0  xor     ecx, ecx
0x1800832e2  mov     rax, cs:g_pfnCallback
0x1800832e9  lea     edx, [r8+0Ch]
0x1800832ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800832f2  lea     rbx, [rdi+30h]
0x1800832f6  mov     rcx, rbx; lpCriticalSection
0x1800832f9  call    cs:__imp_EnterCriticalSection
0x1800832ff  add     [rdi+58h], r12d
0x180083303  mov     rcx, rbx; lpCriticalSection
0x180083306  jnz     short loc_18008332D
0x180083308  call    cs:__imp_LeaveCriticalSection
0x18008330e  mov     rcx, rbx; lpCriticalSection
0x180083311  call    cs:__imp_DeleteCriticalSection
0x180083317  call    cs:__imp_GetProcessHeap
0x18008331d  mov     r8, rdi; lpMem
0x180083320  xor     edx, edx; dwFlags
0x180083322  mov     rcx, rax; hHeap
0x180083325  call    cs:__imp_HeapFree
0x18008332b  jmp     short loc_180083333
0x18008332d  call    cs:__imp_LeaveCriticalSection
0x180083333  mov     rcx, [rsp+888h+var_38]
0x18008333b  xor     rcx, rsp; StackCookie
0x18008333e  call    __security_check_cookie
0x180083343  lea     r11, [rsp+888h+var_28]
0x18008334b  mov     rbx, [r11+40h]
0x18008334f  mov     rbp, [r11+48h]
0x180083353  mov     rsp, r11
0x180083356  pop     r14
0x180083358  pop     r13
0x18008335a  pop     r12
0x18008335c  pop     rdi
0x18008335d  pop     rsi
0x18008335e  retn
```
