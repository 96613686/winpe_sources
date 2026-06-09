# GetLineObjWithReadLock

- ea: `0x18008f50c`
- end: `0x18008f694`
- name: `GetLineObjWithReadLock`
- size: `392`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `7`
- tags: ``

## callers

- `0x1800890b0`
- `0x18008aa50`
- `0x18008cb84`
- `0x18008d130`
- `0x18008d810`
- `0x18008e4b0`
- `0x18008f0a4`

## callees

- `0x1800755b8`
- `0x18008f50c`
- `0x18008ff04`
- `0x180090714`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x18008f5cc`
- `rtutils!TracePrintfA` at `0x18008f656`
- `rtutils!TracePrintfA` at `0x18008f5cc`
- `rtutils!TracePrintfA` at `0x18008f656`

## string_xrefs

- `0x18008f5c5`: `GetLineObjWithReadLock: GetObjWithReadLock failed (0x%x)`
- `0x18008f57e`: `GetLineObjWithReadLock: GetObjWithReadLock failed (0x%x)`
- `0x18008f64f`: `GetLineObjWithReadLock: RasTapi line handle (0x%x) has bad key (0x%x)`
- `0x18008f609`: `GetLineObjWithReadLock: RasTapi line handle (0x%x) has bad key (0x%x)`

## pseudocode

```c
__int64 __fastcall GetLineObjWithReadLock(unsigned int a1, unsigned int **a2)
{
  unsigned int ObjWithReadLock; // eax
  unsigned int v5; // ebx
  unsigned int *v7; // [rsp+20h] [rbp-838h] BYREF
  int v8; // [rsp+30h] [rbp-828h] BYREF
  _BYTE v9[2044]; // [rsp+34h] [rbp-824h] BYREF

  v7 = 0;
  v8 = 0;
  memset_0(v9, 0, sizeof(v9));
  ObjWithReadLock = GetObjWithReadLock(a1, &v7);
  v5 = ObjWithReadLock;
  if ( ObjWithReadLock )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"GetLineObjWithReadLock: GetObjWithReadLock failed (0x%x)", ObjWithReadLock);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v8);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "GetLineObjWithReadLock: GetObjWithReadLock failed (0x%x)", ObjWithReadLock);
    }
  }
  else if ( *v7 == 1263290702 )
  {
    *a2 = v7;
  }
  else
  {
    v5 = 6;
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"GetLineObjWithReadLock: RasTapi line handle (0x%x) has bad key (0x%x)", a1, *v7);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v8);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "GetLineObjWithReadLock: RasTapi line handle (0x%x) has bad key (0x%x)", a1, *v7);
    }
    ReleaseObjReadLock(a1);
  }
  return v5;
}

```

## disassembly

```asm
0x18008f50c  mov     [rsp+arg_10], rbx
0x18008f511  push    rbp
0x18008f512  push    rsi
0x18008f513  push    rdi
0x18008f514  sub     rsp, 840h
0x18008f51b  mov     rax, cs:__security_cookie
0x18008f522  xor     rax, rsp
0x18008f525  mov     [rsp+858h+var_28], rax
0x18008f52d  mov     rsi, rdx
0x18008f530  mov     edi, ecx
0x18008f532  xor     ebp, ebp
0x18008f534  lea     rcx, [rsp+858h+var_824]; void *
0x18008f539  xor     edx, edx; Val
0x18008f53b  mov     [rsp+858h+var_838], rbp
0x18008f540  mov     r8d, 7FCh; Size
0x18008f546  mov     [rsp+858h+var_828], ebp
0x18008f54a  call    memset_0
0x18008f54f  lea     rdx, [rsp+858h+var_838]
0x18008f554  mov     ecx, edi
0x18008f556  call    GetObjWithReadLock
0x18008f55b  mov     ebx, eax
0x18008f55d  test    eax, eax
0x18008f55f  jz      short loc_18008F5DD
0x18008f561  cmp     cs:gIsndpspEtwTracingAvailable, ebp
0x18008f567  jz      short loc_18008F5B3
0x18008f569  cmp     qword ptr cs:xmmword_1800D0BE0, rbp
0x18008f570  jz      loc_18008F66E
0x18008f576  mov     r8d, eax
0x18008f579  mov     word ptr [rsp+858h+var_828], bp
0x18008f57e  lea     rdx, aGetlineobjwith; "GetLineObjWithReadLock: GetObjWithReadL"...
0x18008f585  lea     rcx, [rsp+858h+var_828]
0x18008f58a  call    FormatRRASErrorString
0x18008f58f  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008f596  lea     r8, [rsp+858h+var_828]
0x18008f59b  mov     rcx, cs:gNdpspEtwContext
0x18008f5a2  mov     rax, cs:gNdpspTemplateFunc
0x18008f5a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f5ae  jmp     loc_18008F66E
0x18008f5b3  mov     ecx, cs:dwTraceId; dwTraceID
0x18008f5b9  cmp     ecx, 0FFFFFFFFh
0x18008f5bc  jz      loc_18008F66E
0x18008f5c2  mov     r8d, eax
0x18008f5c5  lea     rdx, aGetlineobjwith_6; "GetLineObjWithReadLock: GetObjWithReadL"...
0x18008f5cc  call    cs:__imp_TracePrintfA
0x18008f5d3  nop     dword ptr [rax+rax+00h]
0x18008f5d8  jmp     loc_18008F66E
0x18008f5dd  mov     rax, [rsp+858h+var_838]
0x18008f5e2  mov     r9d, [rax]
0x18008f5e5  cmp     r9d, 4B4C494Eh
0x18008f5ec  jz      short loc_18008F66B
0x18008f5ee  cmp     cs:gIsndpspEtwTracingAvailable, ebp
0x18008f5f4  mov     ebx, 6
0x18008f5f9  jz      short loc_18008F641
0x18008f5fb  cmp     qword ptr cs:xmmword_1800D0BE0, rbp
0x18008f602  jz      short loc_18008F662
0x18008f604  mov     word ptr [rsp+858h+var_828], bp
0x18008f609  lea     rdx, aGetlineobjwith_5; "GetLineObjWithReadLock: RasTapi line ha"...
0x18008f610  mov     r9d, [rax]
0x18008f613  lea     rcx, [rsp+858h+var_828]
0x18008f618  mov     r8d, edi
0x18008f61b  call    FormatRRASErrorString
0x18008f620  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008f627  lea     r8, [rsp+858h+var_828]
0x18008f62c  mov     rcx, cs:gNdpspEtwContext
0x18008f633  mov     rax, cs:gNdpspTemplateFunc
0x18008f63a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f63f  jmp     short loc_18008F662
0x18008f641  mov     ecx, cs:dwTraceId; dwTraceID
0x18008f647  cmp     ecx, 0FFFFFFFFh
0x18008f64a  jz      short loc_18008F662
0x18008f64c  mov     r8d, edi
0x18008f64f  lea     rdx, aGetlineobjwith_2; "GetLineObjWithReadLock: RasTapi line ha"...
0x18008f656  call    cs:__imp_TracePrintfA
0x18008f65d  nop     dword ptr [rax+rax+00h]
0x18008f662  mov     ecx, edi
0x18008f664  call    ReleaseObjReadLock
0x18008f669  jmp     short loc_18008F66E
0x18008f66b  mov     [rsi], rax
0x18008f66e  mov     eax, ebx
0x18008f670  mov     rcx, [rsp+858h+var_28]
0x18008f678  xor     rcx, rsp; StackCookie
0x18008f67b  call    __security_check_cookie
0x18008f680  mov     rbx, [rsp+858h+arg_10]
0x18008f688  add     rsp, 840h
0x18008f68f  pop     rdi
0x18008f690  pop     rsi
0x18008f691  pop     rbp
0x18008f692  retn
```
