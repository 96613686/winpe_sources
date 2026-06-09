# GetLineAndCallObjWithReadLock

- ea: `0x18008f0a4`
- end: `0x18008f382`
- name: `GetLineAndCallObjWithReadLock`
- size: `734`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18008aa50`

## callees

- `0x1800755b8`
- `0x18008ed64`
- `0x18008f0a4`
- `0x18008f50c`
- `0x18008fa60`
- `0x180090714`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x18008f186`
- `rtutils!TracePrintfA` at `0x18008f298`
- `rtutils!TracePrintfA` at `0x18008f326`
- `rtutils!TracePrintfA` at `0x18008f186`
- `rtutils!TracePrintfA` at `0x18008f298`
- `rtutils!TracePrintfA` at `0x18008f326`

## string_xrefs

- `0x18008f17f`: `GetLineAndCallObjWithReadLock: GetLineObjWithReadLock failed with error (0x%x)`
- `0x18008f138`: `GetLineAndCallObjWithReadLock: GetLineObjWithReadLock failed with error (0x%x)`
- `0x18008f291`: `GetLineAndCallObjWithReadLock: Inbound ht_call(%p) closed already`
- `0x18008f1eb`: `GetLineAndCallObjWithReadLock: Inbound ht_call(%p) closed already`
- `0x18008f277`: `GetLineAndCallObjWithReadLock: Failed to reacquire read lock for obj (%p)`
- `0x18008f254`: `GetLineAndCallObjWithReadLock: Failed to reacquire read lock for obj (%p)`
- `0x18008f31f`: `GetLineAndCallObjWithReadLock: GetCallObjWithReadLock failed with error (0x%x)`
- `0x18008f2df`: `GetLineAndCallObjWithReadLock: GetCallObjWithReadLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall GetLineAndCallObjWithReadLock(unsigned int a1, const void *a2, _QWORD *a3, _QWORD *a4)
{
  _DWORD *v7; // rbx
  unsigned int LineObjWithReadLock; // eax
  __int64 v10; // r14
  unsigned int Lock; // edi
  _DWORD *v12; // rax
  _DWORD *v13; // rcx
  unsigned int v14; // eax
  _DWORD *v16; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+28h] [rbp-D8h] BYREF
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v16 = 0;
  v17 = 0;
  v18 = 0;
  v7 = 0;
  memset_0(v19, 0, sizeof(v19));
  LineObjWithReadLock = GetLineObjWithReadLock(a1, &v17);
  v10 = v17;
  Lock = LineObjWithReadLock;
  if ( LineObjWithReadLock )
  {
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(
          dwTraceId,
          "GetLineAndCallObjWithReadLock: GetLineObjWithReadLock failed with error (0x%x)",
          LineObjWithReadLock);
      goto LABEL_34;
    }
    if ( (_QWORD)xmmword_1800D0BE0 )
    {
      LOWORD(v18) = 0;
      FormatRRASErrorString(
        &v18,
        L"GetLineAndCallObjWithReadLock: GetLineObjWithReadLock failed with error (0x%x)",
        LineObjWithReadLock);
LABEL_5:
      ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v18);
      goto LABEL_34;
    }
    goto LABEL_34;
  }
  *a3 = v17;
  if ( ((unsigned __int8)a2 & 1) == 0 )
  {
    v14 = GetCallObjWithReadLock((unsigned int)a2, &v16);
    Lock = v14;
    if ( v14 )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( (_QWORD)xmmword_1800D0BE0 )
        {
          LOWORD(v18) = 0;
          FormatRRASErrorString(
            &v18,
            L"GetLineAndCallObjWithReadLock: GetCallObjWithReadLock failed with error (0x%x)",
            v14);
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v18);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "GetLineAndCallObjWithReadLock: GetCallObjWithReadLock failed with error (0x%x)", v14);
      }
      v7 = v16;
      goto LABEL_34;
    }
    v7 = v16;
    goto LABEL_39;
  }
  v7 = *(_DWORD **)(v10 + 24);
  if ( !v7 )
    goto LABEL_14;
  v12 = *(_DWORD **)(v10 + 24);
  v13 = v12;
  while ( *((const void **)v12 + 2) != a2 )
  {
    v7 = (_DWORD *)*((_QWORD *)v13 + 7);
    v12 = v7;
    v13 = v7;
    if ( !v7 )
      goto LABEL_14;
  }
  if ( *v7 != 1229144396 )
  {
LABEL_14:
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        LOWORD(v18) = 0;
        FormatRRASErrorString(&v18, L"GetLineAndCallObjWithReadLock: Inbound ht_call(%p) closed already", a2);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v18);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "GetLineAndCallObjWithReadLock: Inbound ht_call(%p) closed already", a2);
    }
    Lock = -2147483624;
    goto LABEL_34;
  }
  Lock = AcquireObjReadLock((unsigned int)v7[2]);
  if ( !Lock )
  {
LABEL_39:
    *a4 = v7;
    return Lock;
  }
  if ( !gIsndpspEtwTracingAvailable )
  {
    if ( dwTraceId != -1 )
      TracePrintfA(
        dwTraceId,
        "GetLineAndCallObjWithReadLock: Failed to reacquire read lock for obj (%p)",
        (unsigned int)v7[2]);
    goto LABEL_34;
  }
  if ( (_QWORD)xmmword_1800D0BE0 )
  {
    LOWORD(v18) = 0;
    FormatRRASErrorString(
      &v18,
      L"GetLineAndCallObjWithReadLock: Failed to reacquire read lock for obj (%p)",
      (unsigned int)v7[2]);
    goto LABEL_5;
  }
LABEL_34:
  if ( v10 )
    ReleaseObjReadLock(a1);
  if ( v7 )
    ReleaseObjReadLock((unsigned int)v7[2]);
  return Lock;
}

```

## disassembly

```asm
0x18008f0a4  push    rbp
0x18008f0a6  push    rbx
0x18008f0a7  push    rsi
0x18008f0a8  push    rdi
0x18008f0a9  push    r12
0x18008f0ab  push    r13
0x18008f0ad  push    r14
0x18008f0af  push    r15
0x18008f0b1  lea     rbp, [rsp-748h]
0x18008f0b9  sub     rsp, 848h
0x18008f0c0  mov     rax, cs:__security_cookie
0x18008f0c7  xor     rax, rsp
0x18008f0ca  mov     [rbp+780h+var_50], rax
0x18008f0d1  xor     eax, eax
0x18008f0d3  mov     r15, r8
0x18008f0d6  mov     rsi, rdx
0x18008f0d9  mov     [rsp+880h+var_860], rax
0x18008f0de  mov     r13d, ecx
0x18008f0e1  mov     [rsp+880h+var_858], rax
0x18008f0e6  xor     edx, edx; Val
0x18008f0e8  mov     [rsp+880h+var_850], eax
0x18008f0ec  mov     r8d, 7FCh; Size
0x18008f0f2  lea     rcx, [rsp+880h+var_84C]; void *
0x18008f0f7  mov     ebx, eax
0x18008f0f9  mov     r12, r9
0x18008f0fc  call    memset_0
0x18008f101  lea     rdx, [rsp+880h+var_858]
0x18008f106  mov     ecx, r13d
0x18008f109  call    GetLineObjWithReadLock
0x18008f10e  mov     r14, [rsp+880h+var_858]
0x18008f113  xor     edx, edx
0x18008f115  mov     edi, eax
0x18008f117  test    eax, eax
0x18008f119  jz      short loc_18008F197
0x18008f11b  cmp     cs:gIsndpspEtwTracingAvailable, edx
0x18008f121  jz      short loc_18008F16D
0x18008f123  cmp     qword ptr cs:xmmword_1800D0BE0, rdx
0x18008f12a  jz      loc_18008F337
0x18008f130  mov     word ptr [rsp+880h+var_850], dx
0x18008f135  mov     r8d, eax
0x18008f138  lea     rdx, aGetlineandcall_0; "GetLineAndCallObjWithReadLock: GetLineO"...
0x18008f13f  lea     rcx, [rsp+880h+var_850]
0x18008f144  call    FormatRRASErrorString
0x18008f149  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008f150  lea     r8, [rsp+880h+var_850]
0x18008f155  mov     rcx, cs:gNdpspEtwContext
0x18008f15c  mov     rax, cs:gNdpspTemplateFunc
0x18008f163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f168  jmp     loc_18008F337
0x18008f16d  mov     ecx, cs:dwTraceId; dwTraceID
0x18008f173  cmp     ecx, 0FFFFFFFFh
0x18008f176  jz      loc_18008F337
0x18008f17c  mov     r8d, eax
0x18008f17f  lea     rdx, aGetlineandcall_2; "GetLineAndCallObjWithReadLock: GetLineO"...
0x18008f186  call    cs:__imp_TracePrintfA
0x18008f18d  nop     dword ptr [rax+rax+00h]
0x18008f192  jmp     loc_18008F337
0x18008f197  mov     [r15], r14
0x18008f19a  test    sil, 1
0x18008f19e  jz      loc_18008F2AE
0x18008f1a4  mov     rbx, [r14+18h]
0x18008f1a8  test    rbx, rbx
0x18008f1ab  jz      short loc_18008F1C8
0x18008f1ad  mov     rax, rbx
0x18008f1b0  mov     rcx, rbx
0x18008f1b3  cmp     [rax+10h], rsi
0x18008f1b7  jz      short loc_18008F21E
0x18008f1b9  mov     rbx, [rcx+38h]
0x18008f1bd  mov     rax, rbx
0x18008f1c0  mov     rcx, rbx
0x18008f1c3  test    rbx, rbx
0x18008f1c6  jnz     short loc_18008F1B3
0x18008f1c8  cmp     cs:gIsndpspEtwTracingAvailable, edx
0x18008f1ce  jz      loc_18008F283
0x18008f1d4  cmp     qword ptr cs:xmmword_1800D0BE0, rdx
0x18008f1db  jz      loc_18008F2A4
0x18008f1e1  mov     word ptr [rsp+880h+var_850], dx
0x18008f1e6  lea     rcx, [rsp+880h+var_850]
0x18008f1eb  lea     rdx, aGetlineandcall_6; "GetLineAndCallObjWithReadLock: Inbound "...
0x18008f1f2  mov     r8, rsi
0x18008f1f5  call    FormatRRASErrorString
0x18008f1fa  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008f201  lea     r8, [rsp+880h+var_850]
0x18008f206  mov     rcx, cs:gNdpspEtwContext
0x18008f20d  mov     rax, cs:gNdpspTemplateFunc
0x18008f214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f219  jmp     loc_18008F2A4
0x18008f21e  cmp     dword ptr [rbx], 4943414Ch
0x18008f224  jnz     short loc_18008F1C8
0x18008f226  mov     ecx, [rbx+8]
0x18008f229  call    AcquireObjReadLock
0x18008f22e  xor     esi, esi
0x18008f230  mov     edi, eax
0x18008f232  test    eax, eax
0x18008f234  jz      loc_18008F358
0x18008f23a  cmp     cs:gIsndpspEtwTracingAvailable, esi
0x18008f240  jz      short loc_18008F264
0x18008f242  cmp     qword ptr cs:xmmword_1800D0BE0, rsi
0x18008f249  jz      loc_18008F337
0x18008f24f  mov     word ptr [rsp+880h+var_850], si
0x18008f254  lea     rdx, aGetlineandcall; "GetLineAndCallObjWithReadLock: Failed t"...
0x18008f25b  mov     r8d, [rbx+8]
0x18008f25f  jmp     loc_18008F13F
0x18008f264  mov     ecx, cs:dwTraceId
0x18008f26a  cmp     ecx, 0FFFFFFFFh
0x18008f26d  jz      loc_18008F337
0x18008f273  mov     r8d, [rbx+8]
0x18008f277  lea     rdx, aGetlineandcall_3; "GetLineAndCallObjWithReadLock: Failed t"...
0x18008f27e  jmp     loc_18008F186
0x18008f283  mov     ecx, cs:dwTraceId; dwTraceID
0x18008f289  cmp     ecx, 0FFFFFFFFh
0x18008f28c  jz      short loc_18008F2A4
0x18008f28e  mov     r8, rsi
0x18008f291  lea     rdx, aGetlineandcall_4; "GetLineAndCallObjWithReadLock: Inbound "...
0x18008f298  call    cs:__imp_TracePrintfA
0x18008f29f  nop     dword ptr [rax+rax+00h]
0x18008f2a4  mov     edi, 80000018h
0x18008f2a9  jmp     loc_18008F337
0x18008f2ae  lea     rdx, [rsp+880h+var_860]
0x18008f2b3  mov     ecx, esi
0x18008f2b5  call    GetCallObjWithReadLock
0x18008f2ba  xor     esi, esi
0x18008f2bc  mov     edi, eax
0x18008f2be  test    eax, eax
0x18008f2c0  jz      loc_18008F353
0x18008f2c6  cmp     cs:gIsndpspEtwTracingAvailable, esi
0x18008f2cc  jz      short loc_18008F311
0x18008f2ce  cmp     qword ptr cs:xmmword_1800D0BE0, rsi
0x18008f2d5  jz      short loc_18008F332
0x18008f2d7  mov     r8d, eax
0x18008f2da  mov     word ptr [rsp+880h+var_850], si
0x18008f2df  lea     rdx, aGetlineandcall_1; "GetLineAndCallObjWithReadLock: GetCallO"...
0x18008f2e6  lea     rcx, [rsp+880h+var_850]
0x18008f2eb  call    FormatRRASErrorString
0x18008f2f0  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008f2f7  lea     r8, [rsp+880h+var_850]
0x18008f2fc  mov     rcx, cs:gNdpspEtwContext
0x18008f303  mov     rax, cs:gNdpspTemplateFunc
0x18008f30a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f30f  jmp     short loc_18008F332
0x18008f311  mov     ecx, cs:dwTraceId; dwTraceID
0x18008f317  cmp     ecx, 0FFFFFFFFh
0x18008f31a  jz      short loc_18008F332
0x18008f31c  mov     r8d, eax
0x18008f31f  lea     rdx, aGetlineandcall_5; "GetLineAndCallObjWithReadLock: GetCallO"...
0x18008f326  call    cs:__imp_TracePrintfA
0x18008f32d  nop     dword ptr [rax+rax+00h]
0x18008f332  mov     rbx, [rsp+880h+var_860]
0x18008f337  test    r14, r14
0x18008f33a  jz      short loc_18008F344
0x18008f33c  mov     ecx, r13d
0x18008f33f  call    ReleaseObjReadLock
0x18008f344  test    rbx, rbx
0x18008f347  jz      short loc_18008F35C
0x18008f349  mov     ecx, [rbx+8]
0x18008f34c  call    ReleaseObjReadLock
0x18008f351  jmp     short loc_18008F35C
0x18008f353  mov     rbx, [rsp+880h+var_860]
0x18008f358  mov     [r12], rbx
0x18008f35c  mov     eax, edi
0x18008f35e  mov     rcx, [rbp+780h+var_50]
0x18008f365  xor     rcx, rsp; StackCookie
0x18008f368  call    __security_check_cookie
0x18008f36d  add     rsp, 848h
0x18008f374  pop     r15
0x18008f376  pop     r14
0x18008f378  pop     r13
0x18008f37a  pop     r12
0x18008f37c  pop     rdi
0x18008f37d  pop     rsi
0x18008f37e  pop     rbx
0x18008f37f  pop     rbp
0x18008f380  retn
```
