# PrepareAsyncRequest

- ea: `0x180022314`
- end: `0x180022514`
- name: `PrepareAsyncRequest`
- size: `512`
- prototype: `__int64 __fastcall(unsigned int, int, unsigned int, _QWORD *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800231f8`
- `0x180023404`
- `0x180023e24`
- `0x1800257e4`

## callees

- `0x180022314`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800223ed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800223ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800223dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800223dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800224e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800224e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800224af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800224af`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022480`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022480`
- `rtutils!TracePrintfA` at `0x1800223ca`
- `rtutils!TracePrintfA` at `0x18002245b`
- `rtutils!TracePrintfA` at `0x1800223ca`
- `rtutils!TracePrintfA` at `0x18002245b`

## pseudocode

```c
__int64 __fastcall PrepareAsyncRequest(unsigned int a1, int a2, unsigned int a3, _QWORD *a4)
{
  unsigned int v8; // edi
  HANDLE ProcessHeap; // rax
  char *v10; // rax
  _DWORD *v11; // rbx
  bool v12; // zf
  unsigned int v13; // edx
  int v15; // [rsp+20h] [rbp-838h] BYREF
  _BYTE v16[2044]; // [rsp+24h] [rbp-834h] BYREF

  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  if ( a3 + 160 >= a3 )
  {
    ProcessHeap = GetProcessHeap();
    v10 = (char *)HeapAlloc(ProcessHeap, 8u, a3 + 160);
    v11 = v10;
    if ( v10 )
    {
      v8 = 0;
      *((_DWORD *)v10 + 8) = 1095915339;
      *((_QWORD *)v10 + 3) = 0;
      *((_QWORD *)v10 + 5) = 0;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v10 + 48));
      v12 = g_fUseReqId == 0;
      v11[22] = 1;
      v11[34] = a1;
      v11[35] = a2;
      v11[36] = a3;
      if ( !v12 )
      {
        EnterCriticalSection(&g_RequestIDCritSec);
        v13 = g_dwRequestID + 1;
        g_dwRequestID = v13;
        v11[38] = v13;
        if ( v13 >= 0x7FFFFFFF )
          g_dwRequestID = 1;
        LeaveCriticalSection(&g_RequestIDCritSec);
      }
      *a4 = v11;
    }
    else
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( qword_18003EC40 )
        {
          LOWORD(v15) = 0;
          FormatRRASErrorString(&v15, L"PrepareAsyncRequest: failed to allocate async request for oid (%x)", a1);
          ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v15);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "PrepareAsyncRequest: failed to allocate async request for oid (%x)", a1);
      }
      return 14;
    }
  }
  else
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( qword_18003EC40 )
      {
        LOWORD(v15) = 0;
        FormatRRASErrorString(
          &v15,
          L"PrepareAsyncRequest: Arithmetic Overflow error. Failed to allocate async request for oid (%x)",
          a1);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v15);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(
        dwTraceId,
        "PrepareAsyncRequest: Arithmetic Overflow error. Failed to allocate async request for oid (%x)",
        a1);
    }
    return 534;
  }
  return v8;
}

```

## disassembly

```asm
0x180022314  mov     [rsp+arg_8], rbx
0x180022319  push    rbp
0x18002231a  push    rsi
0x18002231b  push    rdi
0x18002231c  push    r14
0x18002231e  push    r15
0x180022320  sub     rsp, 830h
0x180022327  mov     rax, cs:__security_cookie
0x18002232e  xor     rax, rsp
0x180022331  mov     [rsp+858h+var_38], rax
0x180022339  mov     ebp, r8d
0x18002233c  mov     r15d, edx
0x18002233f  mov     esi, ecx
0x180022341  xor     eax, eax
0x180022343  xor     edx, edx; Val
0x180022345  mov     [rsp+858h+var_838], eax
0x180022349  mov     r8d, 7FCh; Size
0x18002234f  lea     rcx, [rsp+858h+var_834]; void *
0x180022354  mov     r14, r9
0x180022357  call    memset_0
0x18002235c  lea     eax, [rbp+0A0h]
0x180022362  cmp     eax, ebp
0x180022364  jnb     short loc_1800223DA
0x180022366  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x18002236d  jz      short loc_1800223B5
0x18002236f  cmp     cs:qword_18003EC40, 0
0x180022377  jz      short loc_1800223D0
0x180022379  xor     eax, eax
0x18002237b  lea     rdx, aPrepareasyncre_2; "PrepareAsyncRequest: Arithmetic Overflo"...
0x180022382  mov     r8d, esi
0x180022385  mov     word ptr [rsp+858h+var_838], ax
0x18002238a  lea     rcx, [rsp+858h+var_838]
0x18002238f  call    FormatRRASErrorString
0x180022394  mov     rdx, cs:qword_18003EC40
0x18002239b  lea     r8, [rsp+858h+var_838]
0x1800223a0  mov     rcx, cs:gNdpspEtwContext
0x1800223a7  mov     rax, cs:gNdpspTemplateFunc
0x1800223ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223b3  jmp     short loc_1800223D0
0x1800223b5  mov     ecx, cs:dwTraceId; dwTraceID
0x1800223bb  cmp     ecx, 0FFFFFFFFh
0x1800223be  jz      short loc_1800223D0
0x1800223c0  mov     r8d, esi
0x1800223c3  lea     rdx, aPrepareasyncre; "PrepareAsyncRequest: Arithmetic Overflo"...
0x1800223ca  call    cs:__imp_TracePrintfA
0x1800223d0  mov     edi, 216h
0x1800223d5  jmp     loc_1800224EB
0x1800223da  mov     ebx, eax
0x1800223dc  call    cs:__imp_GetProcessHeap
0x1800223e2  mov     r8d, ebx; dwBytes
0x1800223e5  mov     edx, 8; dwFlags
0x1800223ea  mov     rcx, rax; hHeap
0x1800223ed  call    cs:__imp_HeapAlloc
0x1800223f3  mov     rbx, rax
0x1800223f6  test    rax, rax
0x1800223f9  jnz     short loc_18002246B
0x1800223fb  cmp     cs:gIsndpspEtwTracingAvailable, eax
0x180022401  jz      short loc_180022446
0x180022403  cmp     cs:qword_18003EC40, rax
0x18002240a  jz      short loc_180022461
0x18002240c  mov     r8d, esi
0x18002240f  mov     word ptr [rsp+858h+var_838], ax
0x180022414  lea     rdx, aPrepareasyncre_1; "PrepareAsyncRequest: failed to allocate"...
0x18002241b  lea     rcx, [rsp+858h+var_838]
0x180022420  call    FormatRRASErrorString
0x180022425  mov     rdx, cs:qword_18003EC40
0x18002242c  lea     r8, [rsp+858h+var_838]
0x180022431  mov     rcx, cs:gNdpspEtwContext
0x180022438  mov     rax, cs:gNdpspTemplateFunc
0x18002243f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022444  jmp     short loc_180022461
0x180022446  mov     ecx, cs:dwTraceId; dwTraceID
0x18002244c  cmp     ecx, 0FFFFFFFFh
0x18002244f  jz      short loc_180022461
0x180022451  mov     r8d, esi
0x180022454  lea     rdx, aPrepareasyncre_0; "PrepareAsyncRequest: failed to allocate"...
0x18002245b  call    cs:__imp_TracePrintfA
0x180022461  mov     edi, 0Eh
0x180022466  jmp     loc_1800224EB
0x18002246b  xor     edi, edi
0x18002246d  mov     dword ptr [rax+20h], 4152574Bh
0x180022474  lea     rcx, [rax+30h]; lpCriticalSection
0x180022478  mov     [rax+18h], rdi
0x18002247c  mov     [rax+28h], rdi
0x180022480  call    cs:__imp_InitializeCriticalSection
0x180022486  cmp     cs:g_fUseReqId, edi
0x18002248c  mov     dword ptr [rbx+58h], 1
0x180022493  mov     [rbx+88h], esi
0x180022499  mov     [rbx+8Ch], r15d
0x1800224a0  mov     [rbx+90h], ebp
0x1800224a6  jz      short loc_1800224E8
0x1800224a8  lea     rcx, g_RequestIDCritSec; lpCriticalSection
0x1800224af  call    cs:__imp_EnterCriticalSection
0x1800224b5  mov     edx, cs:g_dwRequestID
0x1800224bb  inc     edx
0x1800224bd  mov     cs:g_dwRequestID, edx
0x1800224c3  mov     [rbx+98h], edx
0x1800224c9  cmp     edx, 7FFFFFFFh
0x1800224cf  jb      short loc_1800224DB
0x1800224d1  mov     cs:g_dwRequestID, 1
0x1800224db  lea     rcx, g_RequestIDCritSec; lpCriticalSection
0x1800224e2  call    cs:__imp_LeaveCriticalSection
0x1800224e8  mov     [r14], rbx
0x1800224eb  mov     eax, edi
0x1800224ed  mov     rcx, [rsp+858h+var_38]
0x1800224f5  xor     rcx, rsp; StackCookie
0x1800224f8  call    __security_check_cookie
0x1800224fd  mov     rbx, [rsp+858h+arg_8]
0x180022505  add     rsp, 830h
0x18002250c  pop     r15
0x18002250e  pop     r14
0x180022510  pop     rdi
0x180022511  pop     rsi
0x180022512  pop     rbp
0x180022513  retn
```
