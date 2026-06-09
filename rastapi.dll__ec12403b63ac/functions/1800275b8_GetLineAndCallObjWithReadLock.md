# GetLineAndCallObjWithReadLock

- ea: `0x1800275b8`
- end: `0x180027880`
- name: `GetLineAndCallObjWithReadLock`
- size: `712`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800226f0`

## callees

- `0x180027270`
- `0x1800275b8`
- `0x180027a10`
- `0x180027f2c`
- `0x180028b5c`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x18002769a`
- `rtutils!TracePrintfA` at `0x1800277a2`
- `rtutils!TracePrintfA` at `0x18002782b`
- `rtutils!TracePrintfA` at `0x18002769a`
- `rtutils!TracePrintfA` at `0x1800277a2`
- `rtutils!TracePrintfA` at `0x18002782b`

## string_xrefs

- `0x180027649`: `GetLineAndCallObjWithReadLock: GetLineObjWithReadLock failed with error (0x%x)`
- `0x180027693`: `GetLineAndCallObjWithReadLock: GetLineObjWithReadLock failed with error (0x%x)`
- `0x1800276f1`: `GetLineAndCallObjWithReadLock: Inbound ht_call(%p) closed already`
- `0x18002779b`: `GetLineAndCallObjWithReadLock: Inbound ht_call(%p) closed already`
- `0x180027759`: `GetLineAndCallObjWithReadLock: Failed to reacquire read lock for obj (%p)`
- `0x180027781`: `GetLineAndCallObjWithReadLock: Failed to reacquire read lock for obj (%p)`
- `0x1800277dc`: `GetLineAndCallObjWithReadLock: GetCallObjWithReadLock failed with error (0x%x)`
- `0x180027824`: `GetLineAndCallObjWithReadLock: GetCallObjWithReadLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall GetLineAndCallObjWithReadLock(unsigned int a1, const void *a2, _QWORD *a3, _QWORD *a4)
{
  _DWORD *v7; // rbx
  unsigned int LineObjWithReadLock; // eax
  __int64 v10; // r15
  unsigned int Lock; // edi
  _DWORD *v12; // rsi
  unsigned int v13; // eax
  _DWORD *v15; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v16; // [rsp+28h] [rbp-D8h] BYREF
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v7 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  LineObjWithReadLock = GetLineObjWithReadLock(a1, &v16);
  v10 = v16;
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
    if ( qword_18003EC40 )
    {
      LOWORD(v17) = 0;
      FormatRRASErrorString(
        &v17,
        L"GetLineAndCallObjWithReadLock: GetLineObjWithReadLock failed with error (0x%x)",
        LineObjWithReadLock);
LABEL_5:
      ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v17);
      goto LABEL_34;
    }
    goto LABEL_34;
  }
  *a3 = v16;
  if ( ((unsigned __int8)a2 & 1) == 0 )
  {
    v13 = GetCallObjWithReadLock((unsigned int)a2, &v15);
    Lock = v13;
    if ( v13 )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( qword_18003EC40 )
        {
          LOWORD(v17) = 0;
          FormatRRASErrorString(
            &v17,
            L"GetLineAndCallObjWithReadLock: GetCallObjWithReadLock failed with error (0x%x)",
            v13);
          ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v17);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "GetLineAndCallObjWithReadLock: GetCallObjWithReadLock failed with error (0x%x)", v13);
      }
      v7 = v15;
      goto LABEL_34;
    }
    v7 = v15;
    goto LABEL_39;
  }
  v7 = *(_DWORD **)(v10 + 24);
  if ( !v7 )
    goto LABEL_14;
  v12 = *(_DWORD **)(v10 + 24);
  while ( *((const void **)v12 + 2) != a2 )
  {
    v7 = (_DWORD *)*((_QWORD *)v12 + 7);
    v12 = v7;
    if ( !v7 )
      goto LABEL_14;
  }
  if ( *v7 != 1229144396 )
  {
LABEL_14:
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( qword_18003EC40 )
      {
        LOWORD(v17) = 0;
        FormatRRASErrorString(&v17, L"GetLineAndCallObjWithReadLock: Inbound ht_call(%p) closed already", a2);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v17);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "GetLineAndCallObjWithReadLock: Inbound ht_call(%p) closed already", a2);
    }
    Lock = -2147483624;
    goto LABEL_34;
  }
  Lock = AcquireObjReadLock((unsigned int)v12[2]);
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
        (unsigned int)v12[2]);
    goto LABEL_34;
  }
  if ( qword_18003EC40 )
  {
    LOWORD(v17) = 0;
    FormatRRASErrorString(
      &v17,
      L"GetLineAndCallObjWithReadLock: Failed to reacquire read lock for obj (%p)",
      (unsigned int)v12[2]);
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
0x1800275b8  push    rbp
0x1800275ba  push    rbx
0x1800275bb  push    rsi
0x1800275bc  push    rdi
0x1800275bd  push    r12
0x1800275bf  push    r13
0x1800275c1  push    r14
0x1800275c3  push    r15
0x1800275c5  lea     rbp, [rsp-748h]
0x1800275cd  sub     rsp, 848h
0x1800275d4  mov     rax, cs:__security_cookie
0x1800275db  xor     rax, rsp
0x1800275de  mov     [rbp+780h+var_50], rax
0x1800275e5  mov     rsi, r8
0x1800275e8  mov     r14, rdx
0x1800275eb  mov     r13d, ecx
0x1800275ee  xor     ebx, ebx
0x1800275f0  xor     eax, eax
0x1800275f2  mov     [rsp+880h+var_860], rbx
0x1800275f7  xor     edx, edx; Val
0x1800275f9  mov     [rsp+880h+var_858], rbx
0x1800275fe  mov     r8d, 7FCh; Size
0x180027604  mov     [rsp+880h+var_850], eax
0x180027608  lea     rcx, [rsp+880h+var_84C]; void *
0x18002760d  mov     r12, r9
0x180027610  call    memset_0
0x180027615  lea     rdx, [rsp+880h+var_858]
0x18002761a  mov     ecx, r13d
0x18002761d  call    GetLineObjWithReadLock
0x180027622  mov     r15, [rsp+880h+var_858]
0x180027627  mov     edi, eax
0x180027629  xor     eax, eax
0x18002762b  test    edi, edi
0x18002762d  jz      short loc_1800276A5
0x18002762f  cmp     cs:gIsndpspEtwTracingAvailable, eax
0x180027635  jz      short loc_180027681
0x180027637  cmp     cs:qword_18003EC40, rax
0x18002763e  jz      loc_180027836
0x180027644  mov     word ptr [rsp+880h+var_850], ax
0x180027649  lea     rdx, aGetlineandcall_0; "GetLineAndCallObjWithReadLock: GetLineO"...
0x180027650  mov     r8d, edi
0x180027653  lea     rcx, [rsp+880h+var_850]
0x180027658  call    FormatRRASErrorString
0x18002765d  mov     rdx, cs:qword_18003EC40
0x180027664  lea     r8, [rsp+880h+var_850]
0x180027669  mov     rcx, cs:gNdpspEtwContext
0x180027670  mov     rax, cs:gNdpspTemplateFunc
0x180027677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002767c  jmp     loc_180027836
0x180027681  mov     ecx, cs:dwTraceId; dwTraceID
0x180027687  cmp     ecx, 0FFFFFFFFh
0x18002768a  jz      loc_180027836
0x180027690  mov     r8d, edi
0x180027693  lea     rdx, aGetlineandcall_2; "GetLineAndCallObjWithReadLock: GetLineO"...
0x18002769a  call    cs:__imp_TracePrintfA
0x1800276a0  jmp     loc_180027836
0x1800276a5  mov     [rsi], r15
0x1800276a8  test    r14b, 1
0x1800276ac  jz      loc_1800277B2
0x1800276b2  mov     rbx, [r15+18h]
0x1800276b6  test    rbx, rbx
0x1800276b9  jz      short loc_1800276D0
0x1800276bb  mov     rsi, rbx
0x1800276be  cmp     [rsi+10h], r14
0x1800276c2  jz      short loc_180027726
0x1800276c4  mov     rbx, [rsi+38h]
0x1800276c8  mov     rsi, rbx
0x1800276cb  test    rbx, rbx
0x1800276ce  jnz     short loc_1800276BE
0x1800276d0  cmp     cs:gIsndpspEtwTracingAvailable, eax
0x1800276d6  jz      loc_18002778D
0x1800276dc  cmp     cs:qword_18003EC40, rax
0x1800276e3  jz      loc_1800277A8
0x1800276e9  mov     r8, r14
0x1800276ec  mov     word ptr [rsp+880h+var_850], ax
0x1800276f1  lea     rdx, aGetlineandcall_6; "GetLineAndCallObjWithReadLock: Inbound "...
0x1800276f8  lea     rcx, [rsp+880h+var_850]
0x1800276fd  call    FormatRRASErrorString
0x180027702  mov     rdx, cs:qword_18003EC40
0x180027709  lea     r8, [rsp+880h+var_850]
0x18002770e  mov     rcx, cs:gNdpspEtwContext
0x180027715  mov     rax, cs:gNdpspTemplateFunc
0x18002771c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027721  jmp     loc_1800277A8
0x180027726  cmp     dword ptr [rbx], 4943414Ch
0x18002772c  jnz     short loc_1800276D0
0x18002772e  mov     ecx, [rsi+8]
0x180027731  call    AcquireObjReadLock
0x180027736  mov     edi, eax
0x180027738  test    eax, eax
0x18002773a  jz      loc_180027857
0x180027740  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180027747  jz      short loc_18002776E
0x180027749  cmp     cs:qword_18003EC40, 0
0x180027751  jz      loc_180027836
0x180027757  xor     eax, eax
0x180027759  lea     rdx, aGetlineandcall; "GetLineAndCallObjWithReadLock: Failed t"...
0x180027760  mov     word ptr [rsp+880h+var_850], ax
0x180027765  mov     r8d, [rsi+8]
0x180027769  jmp     loc_180027653
0x18002776e  mov     ecx, cs:dwTraceId
0x180027774  cmp     ecx, 0FFFFFFFFh
0x180027777  jz      loc_180027836
0x18002777d  mov     r8d, [rsi+8]
0x180027781  lea     rdx, aGetlineandcall_3; "GetLineAndCallObjWithReadLock: Failed t"...
0x180027788  jmp     loc_18002769A
0x18002778d  mov     ecx, cs:dwTraceId; dwTraceID
0x180027793  cmp     ecx, 0FFFFFFFFh
0x180027796  jz      short loc_1800277A8
0x180027798  mov     r8, r14
0x18002779b  lea     rdx, aGetlineandcall_4; "GetLineAndCallObjWithReadLock: Inbound "...
0x1800277a2  call    cs:__imp_TracePrintfA
0x1800277a8  mov     edi, 80000018h
0x1800277ad  jmp     loc_180027836
0x1800277b2  mov     ecx, r14d
0x1800277b5  lea     rdx, [rsp+880h+var_860]
0x1800277ba  call    GetCallObjWithReadLock
0x1800277bf  mov     edi, eax
0x1800277c1  test    eax, eax
0x1800277c3  jz      loc_180027852
0x1800277c9  cmp     cs:gIsndpspEtwTracingAvailable, ebx
0x1800277cf  jz      short loc_180027816
0x1800277d1  cmp     cs:qword_18003EC40, rbx
0x1800277d8  jz      short loc_180027831
0x1800277da  xor     eax, eax
0x1800277dc  lea     rdx, aGetlineandcall_1; "GetLineAndCallObjWithReadLock: GetCallO"...
0x1800277e3  mov     r8d, edi
0x1800277e6  mov     word ptr [rsp+880h+var_850], ax
0x1800277eb  lea     rcx, [rsp+880h+var_850]
0x1800277f0  call    FormatRRASErrorString
0x1800277f5  mov     rdx, cs:qword_18003EC40
0x1800277fc  lea     r8, [rsp+880h+var_850]
0x180027801  mov     rcx, cs:gNdpspEtwContext
0x180027808  mov     rax, cs:gNdpspTemplateFunc
0x18002780f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027814  jmp     short loc_180027831
0x180027816  mov     ecx, cs:dwTraceId; dwTraceID
0x18002781c  cmp     ecx, 0FFFFFFFFh
0x18002781f  jz      short loc_180027831
0x180027821  mov     r8d, edi
0x180027824  lea     rdx, aGetlineandcall_5; "GetLineAndCallObjWithReadLock: GetCallO"...
0x18002782b  call    cs:__imp_TracePrintfA
0x180027831  mov     rbx, [rsp+880h+var_860]
0x180027836  test    r15, r15
0x180027839  jz      short loc_180027843
0x18002783b  mov     ecx, r13d
0x18002783e  call    ReleaseObjReadLock
0x180027843  test    rbx, rbx
0x180027846  jz      short loc_18002785B
0x180027848  mov     ecx, [rbx+8]
0x18002784b  call    ReleaseObjReadLock
0x180027850  jmp     short loc_18002785B
0x180027852  mov     rbx, [rsp+880h+var_860]
0x180027857  mov     [r12], rbx
0x18002785b  mov     eax, edi
0x18002785d  mov     rcx, [rbp+780h+var_50]
0x180027864  xor     rcx, rsp; StackCookie
0x180027867  call    __security_check_cookie
0x18002786c  add     rsp, 848h
0x180027873  pop     r15
0x180027875  pop     r14
0x180027877  pop     r13
0x180027879  pop     r12
0x18002787b  pop     rdi
0x18002787c  pop     rsi
0x18002787d  pop     rbx
0x18002787e  pop     rbp
0x18002787f  retn
```
