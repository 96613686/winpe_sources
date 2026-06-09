# GetLineObjWithWriteLock

- ea: `0x180027ba4`
- end: `0x180027d31`
- name: `GetLineObjWithWriteLock`
- size: `397`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x1800226f0`
- `0x180023610`
- `0x180023a14`

## callees

- `0x180027ba4`
- `0x1800284fc`
- `0x180028c70`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x180027c73`
- `rtutils!TracePrintfA` at `0x180027cf6`
- `rtutils!TracePrintfA` at `0x180027c73`
- `rtutils!TracePrintfA` at `0x180027cf6`

## string_xrefs

- `0x180027c1d`: `GetLineObjWithWriteLock: GetObjWithWriteLock failed (0x%x)`
- `0x180027c6c`: `GetLineObjWithWriteLock: GetObjWithWriteLock failed (0x%x)`
- `0x180027ca4`: `GetLineObjWithWriteLock: RasTapi line handle (0x%x) has bad key (0x%x)`
- `0x180027cef`: `GetLineObjWithWriteLock: RasTapi line handle (0x%x) has bad key (0x%x)`

## pseudocode

```c
__int64 __fastcall GetLineObjWithWriteLock(unsigned int a1, unsigned int **a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  unsigned int *v7; // [rsp+20h] [rbp-E0h] BYREF
  int v8; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v9[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v7 = 0;
  v8 = 0;
  memset_0(v9, 0, sizeof(v9));
  v4 = GetObjWithWriteLock(a1, &v7);
  v5 = v4;
  if ( v4 )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( qword_18003EC40 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"GetLineObjWithWriteLock: GetObjWithWriteLock failed (0x%x)", v4);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v8);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "GetLineObjWithWriteLock: GetObjWithWriteLock failed (0x%x)", v4);
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
        FormatRRASErrorString(&v8, L"GetLineObjWithWriteLock: RasTapi line handle (0x%x) has bad key (0x%x)", a1, *v7);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v8);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "GetLineObjWithWriteLock: RasTapi line handle (0x%x) has bad key (0x%x)", a1, *v7);
    }
    v5 = 6;
    ReleaseObjWriteLock(a1);
  }
  return v5;
}

```

## disassembly

```asm
0x180027ba4  mov     [rsp-8+arg_10], rbx
0x180027ba9  push    rbp
0x180027baa  push    rsi
0x180027bab  push    rdi
0x180027bac  lea     rbp, [rsp-740h]
0x180027bb4  sub     rsp, 840h
0x180027bbb  mov     rax, cs:__security_cookie
0x180027bc2  xor     rax, rsp
0x180027bc5  mov     [rbp+750h+var_20], rax
0x180027bcc  mov     rsi, rdx
0x180027bcf  mov     [rsp+850h+var_830], 0
0x180027bd8  mov     edi, ecx
0x180027bda  xor     eax, eax
0x180027bdc  xor     edx, edx; Val
0x180027bde  mov     [rsp+850h+var_820], eax
0x180027be2  lea     rcx, [rsp+850h+var_81C]; void *
0x180027be7  mov     r8d, 7FCh; Size
0x180027bed  call    memset_0
0x180027bf2  lea     rdx, [rsp+850h+var_830]
0x180027bf7  mov     ecx, edi
0x180027bf9  call    GetObjWithWriteLock
0x180027bfe  mov     ebx, eax
0x180027c00  test    eax, eax
0x180027c02  jz      short loc_180027C7E
0x180027c04  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180027c0b  jz      short loc_180027C5A
0x180027c0d  cmp     cs:qword_18003EC40, 0
0x180027c15  jz      loc_180027D0D
0x180027c1b  xor     ecx, ecx
0x180027c1d  lea     rdx, aGetlineobjwith_4; "GetLineObjWithWriteLock: GetObjWithWrit"...
0x180027c24  mov     word ptr [rsp+850h+var_820], cx
0x180027c29  mov     r8d, eax
0x180027c2c  lea     rcx, [rsp+850h+var_820]
0x180027c31  call    FormatRRASErrorString
0x180027c36  mov     rdx, cs:qword_18003EC40
0x180027c3d  lea     r8, [rsp+850h+var_820]
0x180027c42  mov     rcx, cs:gNdpspEtwContext
0x180027c49  mov     rax, cs:gNdpspTemplateFunc
0x180027c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c55  jmp     loc_180027D0D
0x180027c5a  mov     ecx, cs:dwTraceId; dwTraceID
0x180027c60  cmp     ecx, 0FFFFFFFFh
0x180027c63  jz      loc_180027D0D
0x180027c69  mov     r8d, eax
0x180027c6c  lea     rdx, aGetlineobjwith_1; "GetLineObjWithWriteLock: GetObjWithWrit"...
0x180027c73  call    cs:__imp_TracePrintfA
0x180027c79  jmp     loc_180027D0D
0x180027c7e  mov     rcx, [rsp+850h+var_830]
0x180027c83  mov     r9d, [rcx]
0x180027c86  cmp     r9d, 4B4C494Eh
0x180027c8d  jz      short loc_180027D0A
0x180027c8f  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180027c96  jz      short loc_180027CE1
0x180027c98  cmp     cs:qword_18003EC40, 0
0x180027ca0  jz      short loc_180027CFC
0x180027ca2  xor     eax, eax
0x180027ca4  lea     rdx, aGetlineobjwith_0; "GetLineObjWithWriteLock: RasTapi line h"...
0x180027cab  mov     word ptr [rsp+850h+var_820], ax
0x180027cb0  mov     r8d, edi
0x180027cb3  mov     r9d, [rcx]
0x180027cb6  lea     rcx, [rsp+850h+var_820]
0x180027cbb  call    FormatRRASErrorString
0x180027cc0  mov     rdx, cs:qword_18003EC40
0x180027cc7  lea     r8, [rsp+850h+var_820]
0x180027ccc  mov     rcx, cs:gNdpspEtwContext
0x180027cd3  mov     rax, cs:gNdpspTemplateFunc
0x180027cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027cdf  jmp     short loc_180027CFC
0x180027ce1  mov     ecx, cs:dwTraceId; dwTraceID
0x180027ce7  cmp     ecx, 0FFFFFFFFh
0x180027cea  jz      short loc_180027CFC
0x180027cec  mov     r8d, edi
0x180027cef  lea     rdx, aGetlineobjwith_3; "GetLineObjWithWriteLock: RasTapi line h"...
0x180027cf6  call    cs:__imp_TracePrintfA
0x180027cfc  mov     ecx, edi
0x180027cfe  mov     ebx, 6
0x180027d03  call    ReleaseObjWriteLock
0x180027d08  jmp     short loc_180027D0D
0x180027d0a  mov     [rsi], rcx
0x180027d0d  mov     eax, ebx
0x180027d0f  mov     rcx, [rbp+750h+var_20]
0x180027d16  xor     rcx, rsp; StackCookie
0x180027d19  call    __security_check_cookie
0x180027d1e  mov     rbx, [rsp+850h+arg_10]
0x180027d26  add     rsp, 840h
0x180027d2d  pop     rdi
0x180027d2e  pop     rsi
0x180027d2f  pop     rbp
0x180027d30  retn
```
