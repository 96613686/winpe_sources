# GetLineObjWithWriteLock

- ea: `0x18008f69c`
- end: `0x18008f824`
- name: `GetLineObjWithWriteLock`
- size: `392`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x18008aa50`
- `0x18008ba58`
- `0x18008beac`

## callees

- `0x1800755b8`
- `0x18008f69c`
- `0x180090048`
- `0x180090834`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x18008f75c`
- `rtutils!TracePrintfA` at `0x18008f7e6`
- `rtutils!TracePrintfA` at `0x18008f75c`
- `rtutils!TracePrintfA` at `0x18008f7e6`

## string_xrefs

- `0x18008f755`: `GetLineObjWithWriteLock: GetObjWithWriteLock failed (0x%x)`
- `0x18008f70e`: `GetLineObjWithWriteLock: GetObjWithWriteLock failed (0x%x)`
- `0x18008f7df`: `GetLineObjWithWriteLock: RasTapi line handle (0x%x) has bad key (0x%x)`
- `0x18008f799`: `GetLineObjWithWriteLock: RasTapi line handle (0x%x) has bad key (0x%x)`

## pseudocode

```c
__int64 __fastcall GetLineObjWithWriteLock(unsigned int a1, unsigned int **a2)
{
  unsigned int v4; // eax
  __int64 v5; // rdx
  unsigned int v6; // ebx
  unsigned int *v8; // [rsp+20h] [rbp-838h] BYREF
  int v9; // [rsp+30h] [rbp-828h] BYREF
  _BYTE v10[2044]; // [rsp+34h] [rbp-824h] BYREF

  v8 = 0;
  v9 = 0;
  memset_0(v10, 0, sizeof(v10));
  v4 = GetObjWithWriteLock(a1, &v8);
  v6 = v4;
  if ( v4 )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        LOWORD(v9) = 0;
        FormatRRASErrorString(&v9, L"GetLineObjWithWriteLock: GetObjWithWriteLock failed (0x%x)", v4);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v9);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "GetLineObjWithWriteLock: GetObjWithWriteLock failed (0x%x)", v4);
    }
  }
  else if ( *v8 == 1263290702 )
  {
    *a2 = v8;
  }
  else
  {
    v6 = 6;
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        LOWORD(v9) = 0;
        FormatRRASErrorString(&v9, L"GetLineObjWithWriteLock: RasTapi line handle (0x%x) has bad key (0x%x)", a1, *v8);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v9);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "GetLineObjWithWriteLock: RasTapi line handle (0x%x) has bad key (0x%x)", a1, *v8);
    }
    ReleaseObjWriteLock(a1, v5);
  }
  return v6;
}

```

## disassembly

```asm
0x18008f69c  mov     [rsp+arg_10], rbx
0x18008f6a1  push    rbp
0x18008f6a2  push    rsi
0x18008f6a3  push    rdi
0x18008f6a4  sub     rsp, 840h
0x18008f6ab  mov     rax, cs:__security_cookie
0x18008f6b2  xor     rax, rsp
0x18008f6b5  mov     [rsp+858h+var_28], rax
0x18008f6bd  mov     rsi, rdx
0x18008f6c0  mov     edi, ecx
0x18008f6c2  xor     ebp, ebp
0x18008f6c4  lea     rcx, [rsp+858h+var_824]; void *
0x18008f6c9  xor     edx, edx; Val
0x18008f6cb  mov     [rsp+858h+var_838], rbp
0x18008f6d0  mov     r8d, 7FCh; Size
0x18008f6d6  mov     [rsp+858h+var_828], ebp
0x18008f6da  call    memset_0
0x18008f6df  lea     rdx, [rsp+858h+var_838]
0x18008f6e4  mov     ecx, edi
0x18008f6e6  call    GetObjWithWriteLock
0x18008f6eb  mov     ebx, eax
0x18008f6ed  test    eax, eax
0x18008f6ef  jz      short loc_18008F76D
0x18008f6f1  cmp     cs:gIsndpspEtwTracingAvailable, ebp
0x18008f6f7  jz      short loc_18008F743
0x18008f6f9  cmp     qword ptr cs:xmmword_1800D0BE0, rbp
0x18008f700  jz      loc_18008F7FE
0x18008f706  mov     r8d, eax
0x18008f709  mov     word ptr [rsp+858h+var_828], bp
0x18008f70e  lea     rdx, aGetlineobjwith_4; "GetLineObjWithWriteLock: GetObjWithWrit"...
0x18008f715  lea     rcx, [rsp+858h+var_828]
0x18008f71a  call    FormatRRASErrorString
0x18008f71f  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008f726  lea     r8, [rsp+858h+var_828]
0x18008f72b  mov     rcx, cs:gNdpspEtwContext
0x18008f732  mov     rax, cs:gNdpspTemplateFunc
0x18008f739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f73e  jmp     loc_18008F7FE
0x18008f743  mov     ecx, cs:dwTraceId; dwTraceID
0x18008f749  cmp     ecx, 0FFFFFFFFh
0x18008f74c  jz      loc_18008F7FE
0x18008f752  mov     r8d, eax
0x18008f755  lea     rdx, aGetlineobjwith_1; "GetLineObjWithWriteLock: GetObjWithWrit"...
0x18008f75c  call    cs:__imp_TracePrintfA
0x18008f763  nop     dword ptr [rax+rax+00h]
0x18008f768  jmp     loc_18008F7FE
0x18008f76d  mov     rax, [rsp+858h+var_838]
0x18008f772  mov     r9d, [rax]
0x18008f775  cmp     r9d, 4B4C494Eh
0x18008f77c  jz      short loc_18008F7FB
0x18008f77e  cmp     cs:gIsndpspEtwTracingAvailable, ebp
0x18008f784  mov     ebx, 6
0x18008f789  jz      short loc_18008F7D1
0x18008f78b  cmp     qword ptr cs:xmmword_1800D0BE0, rbp
0x18008f792  jz      short loc_18008F7F2
0x18008f794  mov     word ptr [rsp+858h+var_828], bp
0x18008f799  lea     rdx, aGetlineobjwith_0; "GetLineObjWithWriteLock: RasTapi line h"...
0x18008f7a0  mov     r9d, [rax]
0x18008f7a3  lea     rcx, [rsp+858h+var_828]
0x18008f7a8  mov     r8d, edi
0x18008f7ab  call    FormatRRASErrorString
0x18008f7b0  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008f7b7  lea     r8, [rsp+858h+var_828]
0x18008f7bc  mov     rcx, cs:gNdpspEtwContext
0x18008f7c3  mov     rax, cs:gNdpspTemplateFunc
0x18008f7ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f7cf  jmp     short loc_18008F7F2
0x18008f7d1  mov     ecx, cs:dwTraceId; dwTraceID
0x18008f7d7  cmp     ecx, 0FFFFFFFFh
0x18008f7da  jz      short loc_18008F7F2
0x18008f7dc  mov     r8d, edi
0x18008f7df  lea     rdx, aGetlineobjwith_3; "GetLineObjWithWriteLock: RasTapi line h"...
0x18008f7e6  call    cs:__imp_TracePrintfA
0x18008f7ed  nop     dword ptr [rax+rax+00h]
0x18008f7f2  mov     ecx, edi
0x18008f7f4  call    ReleaseObjWriteLock
0x18008f7f9  jmp     short loc_18008F7FE
0x18008f7fb  mov     [rsi], rax
0x18008f7fe  mov     eax, ebx
0x18008f800  mov     rcx, [rsp+858h+var_28]
0x18008f808  xor     rcx, rsp; StackCookie
0x18008f80b  call    __security_check_cookie
0x18008f810  mov     rbx, [rsp+858h+arg_10]
0x18008f818  add     rsp, 840h
0x18008f81f  pop     rdi
0x18008f820  pop     rsi
0x18008f821  pop     rbp
0x18008f822  retn
```
