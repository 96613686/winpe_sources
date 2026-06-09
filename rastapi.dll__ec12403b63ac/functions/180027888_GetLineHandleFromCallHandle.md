# GetLineHandleFromCallHandle

- ea: `0x180027888`
- end: `0x180027a07`
- name: `GetLineHandleFromCallHandle`
- size: `383`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180023a14`
- `0x180025e40`

## callees

- `0x180027888`
- `0x180028398`
- `0x180028b5c`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x18002795e`
- `rtutils!TracePrintfA` at `0x1800279c4`
- `rtutils!TracePrintfA` at `0x18002795e`
- `rtutils!TracePrintfA` at `0x1800279c4`

## string_xrefs

- `0x18002790c`: `GetLineHandleFromCallHandle: GetObjWithReadLock failed (0x%x)`
- `0x180027957`: `GetLineHandleFromCallHandle: GetObjWithReadLock failed (0x%x)`

## pseudocode

```c
__int64 __fastcall GetLineHandleFromCallHandle(unsigned int a1, _DWORD *a2)
{
  unsigned int ObjWithReadLock; // eax
  unsigned int *v5; // rbx
  unsigned int v6; // edi
  unsigned int *v8; // [rsp+20h] [rbp-E0h] BYREF
  int v9; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v10[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v8 = 0;
  v9 = 0;
  memset_0(v10, 0, sizeof(v10));
  ObjWithReadLock = GetObjWithReadLock(a1, &v8);
  v5 = v8;
  v6 = ObjWithReadLock;
  if ( ObjWithReadLock )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( !qword_18003EC40 )
        goto LABEL_16;
      LOWORD(v9) = 0;
      FormatRRASErrorString(&v9, L"GetLineHandleFromCallHandle: GetObjWithReadLock failed (0x%x)", ObjWithReadLock);
      goto LABEL_5;
    }
    if ( dwTraceId != -1 )
      TracePrintfA(dwTraceId, "GetLineHandleFromCallHandle: GetObjWithReadLock failed (0x%x)", ObjWithReadLock);
  }
  else if ( *v8 == 1229144396 || *v8 == 1329807692 )
  {
    *a2 = v8[8];
  }
  else if ( gIsndpspEtwTracingAvailable )
  {
    if ( qword_18003EC40 )
    {
      LOWORD(v9) = 0;
      FormatRRASErrorString(&v9, L"GetLineHandleFromCallHandle: Obj (0x%x) has bad key (0x%x)", a1, *v8);
LABEL_5:
      ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v9);
    }
  }
  else if ( dwTraceId != -1 )
  {
    TracePrintfA(dwTraceId, "GetLineHandleFromCallHandle: Obj (0x%x) has bad key (0x%x)", a1, *v8);
  }
LABEL_16:
  if ( v5 )
    ReleaseObjReadLock(a1);
  return v6;
}

```

## disassembly

```asm
0x180027888  mov     [rsp-8+arg_10], rbx
0x18002788d  mov     [rsp-8+arg_18], rsi
0x180027892  push    rbp
0x180027893  push    rdi
0x180027894  push    r14
0x180027896  lea     rbp, [rsp-740h]
0x18002789e  sub     rsp, 840h
0x1800278a5  mov     rax, cs:__security_cookie
0x1800278ac  xor     rax, rsp
0x1800278af  mov     [rbp+750h+var_20], rax
0x1800278b6  mov     r14, rdx
0x1800278b9  mov     [rsp+850h+var_830], 0
0x1800278c2  mov     esi, ecx
0x1800278c4  xor     eax, eax
0x1800278c6  xor     edx, edx; Val
0x1800278c8  mov     [rsp+850h+var_820], eax
0x1800278cc  lea     rcx, [rsp+850h+var_81C]; void *
0x1800278d1  mov     r8d, 7FCh; Size
0x1800278d7  call    memset_0
0x1800278dc  lea     rdx, [rsp+850h+var_830]
0x1800278e1  mov     ecx, esi
0x1800278e3  call    GetObjWithReadLock
0x1800278e8  mov     rbx, [rsp+850h+var_830]
0x1800278ed  mov     edi, eax
0x1800278ef  test    eax, eax
0x1800278f1  jz      short loc_180027966
0x1800278f3  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x1800278fa  jz      short loc_180027949
0x1800278fc  cmp     cs:qword_18003EC40, 0
0x180027904  jz      loc_1800279D2
0x18002790a  xor     ecx, ecx
0x18002790c  lea     rdx, aGetlinehandlef_2; "GetLineHandleFromCallHandle: GetObjWith"...
0x180027913  mov     word ptr [rsp+850h+var_820], cx
0x180027918  mov     r8d, eax
0x18002791b  lea     rcx, [rsp+850h+var_820]
0x180027920  call    FormatRRASErrorString
0x180027925  mov     rdx, cs:qword_18003EC40
0x18002792c  lea     r8, [rsp+850h+var_820]
0x180027931  mov     rcx, cs:gNdpspEtwContext
0x180027938  mov     rax, cs:gNdpspTemplateFunc
0x18002793f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027944  jmp     loc_1800279D2
0x180027949  mov     ecx, cs:dwTraceId; dwTraceID
0x18002794f  cmp     ecx, 0FFFFFFFFh
0x180027952  jz      short loc_1800279D2
0x180027954  mov     r8d, edi
0x180027957  lea     rdx, aGetlinehandlef_1; "GetLineHandleFromCallHandle: GetObjWith"...
0x18002795e  call    cs:__imp_TracePrintfA
0x180027964  jmp     short loc_1800279D2
0x180027966  cmp     dword ptr [rbx], 4943414Ch
0x18002796c  jz      short loc_1800279CC
0x18002796e  cmp     dword ptr [rbx], 4F43414Ch
0x180027974  jz      short loc_1800279CC
0x180027976  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x18002797d  jz      short loc_1800279AC
0x18002797f  cmp     cs:qword_18003EC40, 0
0x180027987  jz      short loc_1800279D2
0x180027989  xor     eax, eax
0x18002798b  lea     rdx, aGetlinehandlef_0; "GetLineHandleFromCallHandle: Obj (0x%x)"...
0x180027992  mov     word ptr [rsp+850h+var_820], ax
0x180027997  lea     rcx, [rsp+850h+var_820]
0x18002799c  mov     r9d, [rbx]
0x18002799f  mov     r8d, esi
0x1800279a2  call    FormatRRASErrorString
0x1800279a7  jmp     loc_180027925
0x1800279ac  mov     ecx, cs:dwTraceId; dwTraceID
0x1800279b2  cmp     ecx, 0FFFFFFFFh
0x1800279b5  jz      short loc_1800279D2
0x1800279b7  mov     r9d, [rbx]
0x1800279ba  lea     rdx, aGetlinehandlef; "GetLineHandleFromCallHandle: Obj (0x%x)"...
0x1800279c1  mov     r8d, esi
0x1800279c4  call    cs:__imp_TracePrintfA
0x1800279ca  jmp     short loc_1800279D2
0x1800279cc  mov     eax, [rbx+20h]
0x1800279cf  mov     [r14], eax
0x1800279d2  test    rbx, rbx
0x1800279d5  jz      short loc_1800279DE
0x1800279d7  mov     ecx, esi
0x1800279d9  call    ReleaseObjReadLock
0x1800279de  mov     eax, edi
0x1800279e0  mov     rcx, [rbp+750h+var_20]
0x1800279e7  xor     rcx, rsp; StackCookie
0x1800279ea  call    __security_check_cookie
0x1800279ef  lea     r11, [rsp+850h+var_10]
0x1800279f7  mov     rbx, [r11+30h]
0x1800279fb  mov     rsi, [r11+38h]
0x1800279ff  mov     rsp, r11
0x180027a02  pop     r14
0x180027a04  pop     rdi
0x180027a05  pop     rbp
0x180027a06  retn
```
