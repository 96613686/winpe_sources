# GetLineObjWithReadLock

- ea: `0x180027a10`
- end: `0x180027b9d`
- name: `GetLineObjWithReadLock`
- size: `397`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `7`
- tags: ``

## callers

- `0x180020f80`
- `0x1800226f0`
- `0x180025244`
- `0x1800257e4`
- `0x180025e40`
- `0x180026a2c`
- `0x1800275b8`

## callees

- `0x180027a10`
- `0x180028398`
- `0x180028b5c`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x180027adf`
- `rtutils!TracePrintfA` at `0x180027b62`
- `rtutils!TracePrintfA` at `0x180027adf`
- `rtutils!TracePrintfA` at `0x180027b62`

## string_xrefs

- `0x180027a89`: `GetLineObjWithReadLock: GetObjWithReadLock failed (0x%x)`
- `0x180027ad8`: `GetLineObjWithReadLock: GetObjWithReadLock failed (0x%x)`
- `0x180027b10`: `GetLineObjWithReadLock: RasTapi line handle (0x%x) has bad key (0x%x)`
- `0x180027b5b`: `GetLineObjWithReadLock: RasTapi line handle (0x%x) has bad key (0x%x)`

## pseudocode

```c
__int64 __fastcall GetLineObjWithReadLock(unsigned int a1, unsigned int **a2)
{
  unsigned int ObjWithReadLock; // eax
  unsigned int v5; // ebx
  unsigned int *v7; // [rsp+20h] [rbp-E0h] BYREF
  int v8; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v9[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v7 = 0;
  v8 = 0;
  memset_0(v9, 0, sizeof(v9));
  ObjWithReadLock = GetObjWithReadLock(a1, &v7);
  v5 = ObjWithReadLock;
  if ( ObjWithReadLock )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( qword_18003EC40 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"GetLineObjWithReadLock: GetObjWithReadLock failed (0x%x)", ObjWithReadLock);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v8);
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
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( qword_18003EC40 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"GetLineObjWithReadLock: RasTapi line handle (0x%x) has bad key (0x%x)", a1, *v7);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v8);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "GetLineObjWithReadLock: RasTapi line handle (0x%x) has bad key (0x%x)", a1, *v7);
    }
    v5 = 6;
    ReleaseObjReadLock(a1);
  }
  return v5;
}

```

## disassembly

```asm
0x180027a10  mov     [rsp-8+arg_10], rbx
0x180027a15  push    rbp
0x180027a16  push    rsi
0x180027a17  push    rdi
0x180027a18  lea     rbp, [rsp-740h]
0x180027a20  sub     rsp, 840h
0x180027a27  mov     rax, cs:__security_cookie
0x180027a2e  xor     rax, rsp
0x180027a31  mov     [rbp+750h+var_20], rax
0x180027a38  mov     rsi, rdx
0x180027a3b  mov     [rsp+850h+var_830], 0
0x180027a44  mov     edi, ecx
0x180027a46  xor     eax, eax
0x180027a48  xor     edx, edx; Val
0x180027a4a  mov     [rsp+850h+var_820], eax
0x180027a4e  lea     rcx, [rsp+850h+var_81C]; void *
0x180027a53  mov     r8d, 7FCh; Size
0x180027a59  call    memset_0
0x180027a5e  lea     rdx, [rsp+850h+var_830]
0x180027a63  mov     ecx, edi
0x180027a65  call    GetObjWithReadLock
0x180027a6a  mov     ebx, eax
0x180027a6c  test    eax, eax
0x180027a6e  jz      short loc_180027AEA
0x180027a70  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180027a77  jz      short loc_180027AC6
0x180027a79  cmp     cs:qword_18003EC40, 0
0x180027a81  jz      loc_180027B79
0x180027a87  xor     ecx, ecx
0x180027a89  lea     rdx, aGetlineobjwith; "GetLineObjWithReadLock: GetObjWithReadL"...
0x180027a90  mov     word ptr [rsp+850h+var_820], cx
0x180027a95  mov     r8d, eax
0x180027a98  lea     rcx, [rsp+850h+var_820]
0x180027a9d  call    FormatRRASErrorString
0x180027aa2  mov     rdx, cs:qword_18003EC40
0x180027aa9  lea     r8, [rsp+850h+var_820]
0x180027aae  mov     rcx, cs:gNdpspEtwContext
0x180027ab5  mov     rax, cs:gNdpspTemplateFunc
0x180027abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ac1  jmp     loc_180027B79
0x180027ac6  mov     ecx, cs:dwTraceId; dwTraceID
0x180027acc  cmp     ecx, 0FFFFFFFFh
0x180027acf  jz      loc_180027B79
0x180027ad5  mov     r8d, eax
0x180027ad8  lea     rdx, aGetlineobjwith_6; "GetLineObjWithReadLock: GetObjWithReadL"...
0x180027adf  call    cs:__imp_TracePrintfA
0x180027ae5  jmp     loc_180027B79
0x180027aea  mov     rcx, [rsp+850h+var_830]
0x180027aef  mov     r9d, [rcx]
0x180027af2  cmp     r9d, 4B4C494Eh
0x180027af9  jz      short loc_180027B76
0x180027afb  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180027b02  jz      short loc_180027B4D
0x180027b04  cmp     cs:qword_18003EC40, 0
0x180027b0c  jz      short loc_180027B68
0x180027b0e  xor     eax, eax
0x180027b10  lea     rdx, aGetlineobjwith_5; "GetLineObjWithReadLock: RasTapi line ha"...
0x180027b17  mov     word ptr [rsp+850h+var_820], ax
0x180027b1c  mov     r8d, edi
0x180027b1f  mov     r9d, [rcx]
0x180027b22  lea     rcx, [rsp+850h+var_820]
0x180027b27  call    FormatRRASErrorString
0x180027b2c  mov     rdx, cs:qword_18003EC40
0x180027b33  lea     r8, [rsp+850h+var_820]
0x180027b38  mov     rcx, cs:gNdpspEtwContext
0x180027b3f  mov     rax, cs:gNdpspTemplateFunc
0x180027b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b4b  jmp     short loc_180027B68
0x180027b4d  mov     ecx, cs:dwTraceId; dwTraceID
0x180027b53  cmp     ecx, 0FFFFFFFFh
0x180027b56  jz      short loc_180027B68
0x180027b58  mov     r8d, edi
0x180027b5b  lea     rdx, aGetlineobjwith_2; "GetLineObjWithReadLock: RasTapi line ha"...
0x180027b62  call    cs:__imp_TracePrintfA
0x180027b68  mov     ecx, edi
0x180027b6a  mov     ebx, 6
0x180027b6f  call    ReleaseObjReadLock
0x180027b74  jmp     short loc_180027B79
0x180027b76  mov     [rsi], rcx
0x180027b79  mov     eax, ebx
0x180027b7b  mov     rcx, [rbp+750h+var_20]
0x180027b82  xor     rcx, rsp; StackCookie
0x180027b85  call    __security_check_cookie
0x180027b8a  mov     rbx, [rsp+850h+arg_10]
0x180027b92  add     rsp, 840h
0x180027b99  pop     rdi
0x180027b9a  pop     rsi
0x180027b9b  pop     rbp
0x180027b9c  retn
```
