# GetLineHandleFromCallHandle

- ea: `0x180089134`
- end: `0x1800892b3`
- name: `GetLineHandleFromCallHandle`
- size: `383`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180085e4c`
- `0x1800876d0`

## callees

- `0x180071cec`
- `0x180089134`
- `0x180089c44`
- `0x18008a408`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x18008920a`
- `rtutils!TracePrintfA` at `0x180089270`
- `rtutils!TracePrintfA` at `0x18008920a`
- `rtutils!TracePrintfA` at `0x180089270`

## string_xrefs

- `0x180089203`: `GetLineHandleFromCallHandle: GetObjWithReadLock failed (0x%x)`
- `0x1800891b8`: `GetLineHandleFromCallHandle: GetObjWithReadLock failed (0x%x)`

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
      if ( !(_QWORD)xmmword_1800C9BE0 )
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
    if ( (_QWORD)xmmword_1800C9BE0 )
    {
      LOWORD(v9) = 0;
      FormatRRASErrorString(&v9, L"GetLineHandleFromCallHandle: Obj (0x%x) has bad key (0x%x)", a1, *v8);
LABEL_5:
      ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v9);
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
0x180089134  mov     [rsp-8+arg_10], rbx
0x180089139  mov     [rsp-8+arg_18], rsi
0x18008913e  push    rbp
0x18008913f  push    rdi
0x180089140  push    r14
0x180089142  lea     rbp, [rsp-740h]
0x18008914a  sub     rsp, 840h
0x180089151  mov     rax, cs:__security_cookie
0x180089158  xor     rax, rsp
0x18008915b  mov     [rbp+750h+var_20], rax
0x180089162  mov     r14, rdx
0x180089165  mov     [rsp+850h+var_830], 0
0x18008916e  mov     esi, ecx
0x180089170  xor     eax, eax
0x180089172  xor     edx, edx; Val
0x180089174  mov     [rsp+850h+var_820], eax
0x180089178  lea     rcx, [rsp+850h+var_81C]; void *
0x18008917d  mov     r8d, 7FCh; Size
0x180089183  call    memset_0
0x180089188  lea     rdx, [rsp+850h+var_830]
0x18008918d  mov     ecx, esi
0x18008918f  call    GetObjWithReadLock
0x180089194  mov     rbx, [rsp+850h+var_830]
0x180089199  mov     edi, eax
0x18008919b  test    eax, eax
0x18008919d  jz      short loc_180089212
0x18008919f  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x1800891a6  jz      short loc_1800891F5
0x1800891a8  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x1800891b0  jz      loc_18008927E
0x1800891b6  xor     ecx, ecx
0x1800891b8  lea     rdx, aGetlinehandlef_2; "GetLineHandleFromCallHandle: GetObjWith"...
0x1800891bf  mov     word ptr [rsp+850h+var_820], cx
0x1800891c4  mov     r8d, eax
0x1800891c7  lea     rcx, [rsp+850h+var_820]
0x1800891cc  call    FormatRRASErrorString
0x1800891d1  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x1800891d8  lea     r8, [rsp+850h+var_820]
0x1800891dd  mov     rcx, cs:gNdpspEtwContext
0x1800891e4  mov     rax, cs:gNdpspTemplateFunc
0x1800891eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800891f0  jmp     loc_18008927E
0x1800891f5  mov     ecx, cs:dwTraceId; dwTraceID
0x1800891fb  cmp     ecx, 0FFFFFFFFh
0x1800891fe  jz      short loc_18008927E
0x180089200  mov     r8d, edi
0x180089203  lea     rdx, aGetlinehandlef_1; "GetLineHandleFromCallHandle: GetObjWith"...
0x18008920a  call    cs:__imp_TracePrintfA
0x180089210  jmp     short loc_18008927E
0x180089212  cmp     dword ptr [rbx], 4943414Ch
0x180089218  jz      short loc_180089278
0x18008921a  cmp     dword ptr [rbx], 4F43414Ch
0x180089220  jz      short loc_180089278
0x180089222  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180089229  jz      short loc_180089258
0x18008922b  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x180089233  jz      short loc_18008927E
0x180089235  xor     eax, eax
0x180089237  lea     rdx, aGetlinehandlef_0; "GetLineHandleFromCallHandle: Obj (0x%x)"...
0x18008923e  mov     word ptr [rsp+850h+var_820], ax
0x180089243  lea     rcx, [rsp+850h+var_820]
0x180089248  mov     r9d, [rbx]
0x18008924b  mov     r8d, esi
0x18008924e  call    FormatRRASErrorString
0x180089253  jmp     loc_1800891D1
0x180089258  mov     ecx, cs:dwTraceId; dwTraceID
0x18008925e  cmp     ecx, 0FFFFFFFFh
0x180089261  jz      short loc_18008927E
0x180089263  mov     r9d, [rbx]
0x180089266  lea     rdx, aGetlinehandlef; "GetLineHandleFromCallHandle: Obj (0x%x)"...
0x18008926d  mov     r8d, esi
0x180089270  call    cs:__imp_TracePrintfA
0x180089276  jmp     short loc_18008927E
0x180089278  mov     eax, [rbx+20h]
0x18008927b  mov     [r14], eax
0x18008927e  test    rbx, rbx
0x180089281  jz      short loc_18008928A
0x180089283  mov     ecx, esi
0x180089285  call    ReleaseObjReadLock
0x18008928a  mov     eax, edi
0x18008928c  mov     rcx, [rbp+750h+var_20]
0x180089293  xor     rcx, rsp; StackCookie
0x180089296  call    __security_check_cookie
0x18008929b  lea     r11, [rsp+850h+var_10]
0x1800892a3  mov     rbx, [r11+30h]
0x1800892a7  mov     rsi, [r11+38h]
0x1800892ab  mov     rsp, r11
0x1800892ae  pop     r14
0x1800892b0  pop     rdi
0x1800892b1  pop     rbp
0x1800892b2  retn
```
