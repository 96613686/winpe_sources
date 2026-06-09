# GetLineObjWithReadLock

- ea: `0x1800892bc`
- end: `0x180089449`
- name: `GetLineObjWithReadLock`
- size: `397`
- prototype: ``
- caller_count: `7`
- callee_count: `7`
- tags: ``

## callers

- `0x180083370`
- `0x180084ae0`
- `0x180086ad0`
- `0x180087070`
- `0x1800876d0`
- `0x1800882cc`
- `0x180088e64`

## callees

- `0x180071cec`
- `0x1800892bc`
- `0x180089c44`
- `0x18008a408`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x18008938b`
- `rtutils!TracePrintfA` at `0x18008940e`
- `rtutils!TracePrintfA` at `0x18008938b`
- `rtutils!TracePrintfA` at `0x18008940e`

## string_xrefs

- `0x180089384`: `GetLineObjWithReadLock: GetObjWithReadLock failed (0x%x)`
- `0x180089335`: `GetLineObjWithReadLock: GetObjWithReadLock failed (0x%x)`
- `0x180089407`: `GetLineObjWithReadLock: RasTapi line handle (0x%x) has bad key (0x%x)`
- `0x1800893bc`: `GetLineObjWithReadLock: RasTapi line handle (0x%x) has bad key (0x%x)`

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
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"GetLineObjWithReadLock: GetObjWithReadLock failed (0x%x)", ObjWithReadLock);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v8);
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
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"GetLineObjWithReadLock: RasTapi line handle (0x%x) has bad key (0x%x)", a1, *v7);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v8);
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
0x1800892bc  mov     [rsp-8+arg_10], rbx
0x1800892c1  push    rbp
0x1800892c2  push    rsi
0x1800892c3  push    rdi
0x1800892c4  lea     rbp, [rsp-740h]
0x1800892cc  sub     rsp, 840h
0x1800892d3  mov     rax, cs:__security_cookie
0x1800892da  xor     rax, rsp
0x1800892dd  mov     [rbp+750h+var_20], rax
0x1800892e4  mov     rsi, rdx
0x1800892e7  mov     [rsp+850h+var_830], 0
0x1800892f0  mov     edi, ecx
0x1800892f2  xor     eax, eax
0x1800892f4  xor     edx, edx; Val
0x1800892f6  mov     [rsp+850h+var_820], eax
0x1800892fa  lea     rcx, [rsp+850h+var_81C]; void *
0x1800892ff  mov     r8d, 7FCh; Size
0x180089305  call    memset_0
0x18008930a  lea     rdx, [rsp+850h+var_830]
0x18008930f  mov     ecx, edi
0x180089311  call    GetObjWithReadLock
0x180089316  mov     ebx, eax
0x180089318  test    eax, eax
0x18008931a  jz      short loc_180089396
0x18008931c  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180089323  jz      short loc_180089372
0x180089325  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x18008932d  jz      loc_180089425
0x180089333  xor     ecx, ecx
0x180089335  lea     rdx, aGetlineobjwith; "GetLineObjWithReadLock: GetObjWithReadL"...
0x18008933c  mov     word ptr [rsp+850h+var_820], cx
0x180089341  mov     r8d, eax
0x180089344  lea     rcx, [rsp+850h+var_820]
0x180089349  call    FormatRRASErrorString
0x18008934e  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180089355  lea     r8, [rsp+850h+var_820]
0x18008935a  mov     rcx, cs:gNdpspEtwContext
0x180089361  mov     rax, cs:gNdpspTemplateFunc
0x180089368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008936d  jmp     loc_180089425
0x180089372  mov     ecx, cs:dwTraceId; dwTraceID
0x180089378  cmp     ecx, 0FFFFFFFFh
0x18008937b  jz      loc_180089425
0x180089381  mov     r8d, eax
0x180089384  lea     rdx, aGetlineobjwith_6; "GetLineObjWithReadLock: GetObjWithReadL"...
0x18008938b  call    cs:__imp_TracePrintfA
0x180089391  jmp     loc_180089425
0x180089396  mov     rcx, [rsp+850h+var_830]
0x18008939b  mov     r9d, [rcx]
0x18008939e  cmp     r9d, 4B4C494Eh
0x1800893a5  jz      short loc_180089422
0x1800893a7  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x1800893ae  jz      short loc_1800893F9
0x1800893b0  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x1800893b8  jz      short loc_180089414
0x1800893ba  xor     eax, eax
0x1800893bc  lea     rdx, aGetlineobjwith_5; "GetLineObjWithReadLock: RasTapi line ha"...
0x1800893c3  mov     word ptr [rsp+850h+var_820], ax
0x1800893c8  mov     r8d, edi
0x1800893cb  mov     r9d, [rcx]
0x1800893ce  lea     rcx, [rsp+850h+var_820]
0x1800893d3  call    FormatRRASErrorString
0x1800893d8  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x1800893df  lea     r8, [rsp+850h+var_820]
0x1800893e4  mov     rcx, cs:gNdpspEtwContext
0x1800893eb  mov     rax, cs:gNdpspTemplateFunc
0x1800893f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800893f7  jmp     short loc_180089414
0x1800893f9  mov     ecx, cs:dwTraceId; dwTraceID
0x1800893ff  cmp     ecx, 0FFFFFFFFh
0x180089402  jz      short loc_180089414
0x180089404  mov     r8d, edi
0x180089407  lea     rdx, aGetlineobjwith_2; "GetLineObjWithReadLock: RasTapi line ha"...
0x18008940e  call    cs:__imp_TracePrintfA
0x180089414  mov     ecx, edi
0x180089416  mov     ebx, 6
0x18008941b  call    ReleaseObjReadLock
0x180089420  jmp     short loc_180089425
0x180089422  mov     [rsi], rcx
0x180089425  mov     eax, ebx
0x180089427  mov     rcx, [rbp+750h+var_20]
0x18008942e  xor     rcx, rsp; StackCookie
0x180089431  call    __security_check_cookie
0x180089436  mov     rbx, [rsp+850h+arg_10]
0x18008943e  add     rsp, 840h
0x180089445  pop     rdi
0x180089446  pop     rsi
0x180089447  pop     rbp
0x180089448  retn
```
