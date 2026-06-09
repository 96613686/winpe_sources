# GetLineObjWithWriteLock

- ea: `0x180089450`
- end: `0x1800895dd`
- name: `GetLineObjWithWriteLock`
- size: `397`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180084ae0`
- `0x180085a48`
- `0x180085e4c`

## callees

- `0x180071cec`
- `0x180089450`
- `0x180089da8`
- `0x18008a51c`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x18008951f`
- `rtutils!TracePrintfA` at `0x1800895a2`
- `rtutils!TracePrintfA` at `0x18008951f`
- `rtutils!TracePrintfA` at `0x1800895a2`

## string_xrefs

- `0x180089518`: `GetLineObjWithWriteLock: GetObjWithWriteLock failed (0x%x)`
- `0x1800894c9`: `GetLineObjWithWriteLock: GetObjWithWriteLock failed (0x%x)`
- `0x18008959b`: `GetLineObjWithWriteLock: RasTapi line handle (0x%x) has bad key (0x%x)`
- `0x180089550`: `GetLineObjWithWriteLock: RasTapi line handle (0x%x) has bad key (0x%x)`

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
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"GetLineObjWithWriteLock: GetObjWithWriteLock failed (0x%x)", v4);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v8);
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
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"GetLineObjWithWriteLock: RasTapi line handle (0x%x) has bad key (0x%x)", a1, *v7);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v8);
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
0x180089450  mov     [rsp-8+arg_10], rbx
0x180089455  push    rbp
0x180089456  push    rsi
0x180089457  push    rdi
0x180089458  lea     rbp, [rsp-740h]
0x180089460  sub     rsp, 840h
0x180089467  mov     rax, cs:__security_cookie
0x18008946e  xor     rax, rsp
0x180089471  mov     [rbp+750h+var_20], rax
0x180089478  mov     rsi, rdx
0x18008947b  mov     [rsp+850h+var_830], 0
0x180089484  mov     edi, ecx
0x180089486  xor     eax, eax
0x180089488  xor     edx, edx; Val
0x18008948a  mov     [rsp+850h+var_820], eax
0x18008948e  lea     rcx, [rsp+850h+var_81C]; void *
0x180089493  mov     r8d, 7FCh; Size
0x180089499  call    memset_0
0x18008949e  lea     rdx, [rsp+850h+var_830]
0x1800894a3  mov     ecx, edi
0x1800894a5  call    GetObjWithWriteLock
0x1800894aa  mov     ebx, eax
0x1800894ac  test    eax, eax
0x1800894ae  jz      short loc_18008952A
0x1800894b0  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x1800894b7  jz      short loc_180089506
0x1800894b9  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x1800894c1  jz      loc_1800895B9
0x1800894c7  xor     ecx, ecx
0x1800894c9  lea     rdx, aGetlineobjwith_4; "GetLineObjWithWriteLock: GetObjWithWrit"...
0x1800894d0  mov     word ptr [rsp+850h+var_820], cx
0x1800894d5  mov     r8d, eax
0x1800894d8  lea     rcx, [rsp+850h+var_820]
0x1800894dd  call    FormatRRASErrorString
0x1800894e2  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x1800894e9  lea     r8, [rsp+850h+var_820]
0x1800894ee  mov     rcx, cs:gNdpspEtwContext
0x1800894f5  mov     rax, cs:gNdpspTemplateFunc
0x1800894fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089501  jmp     loc_1800895B9
0x180089506  mov     ecx, cs:dwTraceId; dwTraceID
0x18008950c  cmp     ecx, 0FFFFFFFFh
0x18008950f  jz      loc_1800895B9
0x180089515  mov     r8d, eax
0x180089518  lea     rdx, aGetlineobjwith_1; "GetLineObjWithWriteLock: GetObjWithWrit"...
0x18008951f  call    cs:__imp_TracePrintfA
0x180089525  jmp     loc_1800895B9
0x18008952a  mov     rcx, [rsp+850h+var_830]
0x18008952f  mov     r9d, [rcx]
0x180089532  cmp     r9d, 4B4C494Eh
0x180089539  jz      short loc_1800895B6
0x18008953b  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180089542  jz      short loc_18008958D
0x180089544  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x18008954c  jz      short loc_1800895A8
0x18008954e  xor     eax, eax
0x180089550  lea     rdx, aGetlineobjwith_0; "GetLineObjWithWriteLock: RasTapi line h"...
0x180089557  mov     word ptr [rsp+850h+var_820], ax
0x18008955c  mov     r8d, edi
0x18008955f  mov     r9d, [rcx]
0x180089562  lea     rcx, [rsp+850h+var_820]
0x180089567  call    FormatRRASErrorString
0x18008956c  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180089573  lea     r8, [rsp+850h+var_820]
0x180089578  mov     rcx, cs:gNdpspEtwContext
0x18008957f  mov     rax, cs:gNdpspTemplateFunc
0x180089586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008958b  jmp     short loc_1800895A8
0x18008958d  mov     ecx, cs:dwTraceId; dwTraceID
0x180089593  cmp     ecx, 0FFFFFFFFh
0x180089596  jz      short loc_1800895A8
0x180089598  mov     r8d, edi
0x18008959b  lea     rdx, aGetlineobjwith_3; "GetLineObjWithWriteLock: RasTapi line h"...
0x1800895a2  call    cs:__imp_TracePrintfA
0x1800895a8  mov     ecx, edi
0x1800895aa  mov     ebx, 6
0x1800895af  call    ReleaseObjWriteLock
0x1800895b4  jmp     short loc_1800895B9
0x1800895b6  mov     [rsi], rcx
0x1800895b9  mov     eax, ebx
0x1800895bb  mov     rcx, [rbp+750h+var_20]
0x1800895c2  xor     rcx, rsp; StackCookie
0x1800895c5  call    __security_check_cookie
0x1800895ca  mov     rbx, [rsp+850h+arg_10]
0x1800895d2  add     rsp, 840h
0x1800895d9  pop     rdi
0x1800895da  pop     rsi
0x1800895db  pop     rbp
0x1800895dc  retn
```
