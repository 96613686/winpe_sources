# RasLineAnswer

- ea: `0x180085818`
- end: `0x180085a3f`
- name: `RasLineAnswer`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800261a4`

## callees

- `0x180071cec`
- `0x18008308c`
- `0x180084704`
- `0x180085818`
- `0x180088b1c`
- `0x1800895e4`
- `0x18008a408`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x1800858c4`
- `rtutils!TracePrintfA` at `0x180085957`
- `rtutils!TracePrintfA` at `0x1800858c4`
- `rtutils!TracePrintfA` at `0x180085957`

## string_xrefs

- `0x180085950`: `RasLineAnswer: GetCallObjWithReadLock failed with error (0x%x)`
- `0x180085901`: `RasLineAnswer: GetCallObjWithReadLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineAnswer(unsigned int a1, __int64 a2, __int64 a3, int a4, _DWORD *a5)
{
  unsigned int v7; // eax
  unsigned int *v8; // rdi
  unsigned int NDProxyHandle; // ebx
  bool v10; // zf
  char *v11; // rdx
  unsigned int *v13; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v15; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+40h] [rbp-C0h] BYREF
  char v17[2044]; // [rsp+44h] [rbp-BCh] BYREF

  lpMem = 0;
  v16 = 0;
  v13 = 0;
  v15 = 0;
  memset_0(v17, 0, sizeof(v17));
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( *((_QWORD *)&xmmword_1800C9BE0 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
        gNdpspEtwContext,
        *((_QWORD *)&xmmword_1800C9BE0 + 1),
        L"RasLineAnswer...");
  }
  else if ( dwTraceId != -1 )
  {
    TracePrintfA(dwTraceId, "RasLineAnswer...");
  }
  *a5 = 0;
  v7 = GetCallObjWithReadLock(a1, &v13);
  v8 = v13;
  NDProxyHandle = v7;
  if ( v7 )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( !(_QWORD)xmmword_1800C9BE0 )
        goto LABEL_25;
      LOWORD(v16) = 0;
      FormatRRASErrorString(&v16, L"RasLineAnswer: GetCallObjWithReadLock failed with error (0x%x)", v7);
      goto LABEL_10;
    }
    if ( dwTraceId != -1 )
      TracePrintfA(dwTraceId, "RasLineAnswer: GetCallObjWithReadLock failed with error (0x%x)", v7);
  }
  else
  {
    NDProxyHandle = GetNDProxyHandle(v13, &v15);
    if ( NDProxyHandle )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( (_QWORD)xmmword_1800C9BE0 )
        {
          LOWORD(v16) = 0;
          FormatRRASErrorString(&v16, L"RasLineAnswer: GetNDProxyHandle failed with error (0x%x)", NDProxyHandle);
LABEL_10:
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v16);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "RasLineAnswer: GetNDProxyHandle failed with error (0x%x)", NDProxyHandle);
      }
    }
    else
    {
      NDProxyHandle = PrepareAsyncRequest(117637378, v8[1], 24, &lpMem);
      if ( !NDProxyHandle )
      {
        v10 = g_fUseReqId == 0;
        v11 = (char *)lpMem;
        *((_QWORD *)lpMem + 20) = v15;
        *((_DWORD *)v11 + 42) = 0;
        if ( v10 )
          *((_DWORD *)v11 + 38) = a4;
        else
          *a5 = *((_DWORD *)v11 + 38);
        AsyncDriverRequest(0x8FFF23CC, v11);
      }
    }
  }
LABEL_25:
  if ( v8 )
    ReleaseObjReadLock(a1);
  return NDProxyHandle;
}

```

## disassembly

```asm
0x180085818  push    rbp
0x18008581a  push    rbx
0x18008581b  push    rsi
0x18008581c  push    rdi
0x18008581d  push    r14
0x18008581f  push    r15
0x180085821  lea     rbp, [rsp-758h]
0x180085829  sub     rsp, 858h
0x180085830  mov     rax, cs:__security_cookie
0x180085837  xor     rax, rsp
0x18008583a  mov     [rbp+780h+var_40], rax
0x180085841  mov     rsi, [rbp+780h+arg_20]
0x180085848  mov     r14d, ecx
0x18008584b  xor     eax, eax
0x18008584d  mov     [rsp+880h+lpMem], 0
0x180085856  lea     rcx, [rsp+880h+var_83C]; void *
0x18008585b  mov     [rsp+880h+var_840], eax
0x18008585f  xor     edx, edx; Val
0x180085861  mov     [rsp+880h+var_860], 0
0x18008586a  mov     r8d, 7FCh; Size
0x180085870  mov     [rsp+880h+var_850], 0
0x180085879  mov     r15, r9
0x18008587c  call    memset_0
0x180085881  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180085888  jz      short loc_1800858B2
0x18008588a  mov     rdx, qword ptr cs:xmmword_1800C9BE0+8
0x180085891  test    rdx, rdx
0x180085894  jz      short loc_1800858CA
0x180085896  mov     rcx, cs:gNdpspEtwContext
0x18008589d  lea     r8, aRaslineanswer_0; "RasLineAnswer..."
0x1800858a4  mov     rax, cs:gNdpspTemplateFunc
0x1800858ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800858b0  jmp     short loc_1800858CA
0x1800858b2  mov     ecx, cs:dwTraceId; dwTraceID
0x1800858b8  cmp     ecx, 0FFFFFFFFh
0x1800858bb  jz      short loc_1800858CA
0x1800858bd  lea     rdx, aRaslineanswer; "RasLineAnswer..."
0x1800858c4  call    cs:__imp_TracePrintfA
0x1800858ca  lea     rdx, [rsp+880h+var_860]
0x1800858cf  mov     dword ptr [rsi], 0
0x1800858d5  mov     ecx, r14d
0x1800858d8  call    GetCallObjWithReadLock
0x1800858dd  mov     rdi, [rsp+880h+var_860]
0x1800858e2  mov     ebx, eax
0x1800858e4  test    eax, eax
0x1800858e6  jz      short loc_180085962
0x1800858e8  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x1800858ef  jz      short loc_18008593E
0x1800858f1  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x1800858f9  jz      loc_180085A11
0x1800858ff  xor     ecx, ecx
0x180085901  lea     rdx, aRaslineanswerG_0; "RasLineAnswer: GetCallObjWithReadLock f"...
0x180085908  mov     word ptr [rsp+880h+var_840], cx
0x18008590d  mov     r8d, eax
0x180085910  lea     rcx, [rsp+880h+var_840]
0x180085915  call    FormatRRASErrorString
0x18008591a  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180085921  lea     r8, [rsp+880h+var_840]
0x180085926  mov     rcx, cs:gNdpspEtwContext
0x18008592d  mov     rax, cs:gNdpspTemplateFunc
0x180085934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085939  jmp     loc_180085A11
0x18008593e  mov     ecx, cs:dwTraceId; dwTraceID
0x180085944  cmp     ecx, 0FFFFFFFFh
0x180085947  jz      loc_180085A11
0x18008594d  mov     r8d, eax
0x180085950  lea     rdx, aRaslineanswerG_2; "RasLineAnswer: GetCallObjWithReadLock f"...
0x180085957  call    cs:__imp_TracePrintfA
0x18008595d  jmp     loc_180085A11
0x180085962  lea     rdx, [rsp+880h+var_850]
0x180085967  mov     rcx, rdi
0x18008596a  call    GetNDProxyHandle
0x18008596f  mov     ebx, eax
0x180085971  test    eax, eax
0x180085973  jz      short loc_1800859B9
0x180085975  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x18008597c  jz      short loc_1800859A2
0x18008597e  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x180085986  jz      loc_180085A11
0x18008598c  xor     eax, eax
0x18008598e  lea     rdx, aRaslineanswerG; "RasLineAnswer: GetNDProxyHandle failed "...
0x180085995  mov     word ptr [rsp+880h+var_840], ax
0x18008599a  mov     r8d, ebx
0x18008599d  jmp     loc_180085910
0x1800859a2  mov     ecx, cs:dwTraceId
0x1800859a8  cmp     ecx, 0FFFFFFFFh
0x1800859ab  jz      short loc_180085A11
0x1800859ad  mov     r8d, ebx
0x1800859b0  lea     rdx, aRaslineanswerG_1; "RasLineAnswer: GetNDProxyHandle failed "...
0x1800859b7  jmp     short loc_180085957
0x1800859b9  mov     edx, [rdi+4]
0x1800859bc  lea     r9, [rsp+880h+lpMem]
0x1800859c1  mov     r8d, 18h
0x1800859c7  mov     ecx, 7030102h
0x1800859cc  call    PrepareAsyncRequest
0x1800859d1  mov     ebx, eax
0x1800859d3  test    eax, eax
0x1800859d5  jnz     short loc_180085A11
0x1800859d7  cmp     cs:g_fUseReqId, ebx
0x1800859dd  mov     rdx, [rsp+880h+lpMem]; lpMem
0x1800859e2  mov     rax, [rsp+880h+var_850]
0x1800859e7  mov     [rdx+0A0h], rax
0x1800859ee  mov     [rdx+0A8h], ebx
0x1800859f4  jz      short loc_180085A00
0x1800859f6  mov     eax, [rdx+98h]
0x1800859fc  mov     [rsi], eax
0x1800859fe  jmp     short loc_180085A07
0x180085a00  mov     [rdx+98h], r15d
0x180085a07  mov     ecx, 8FFF23CCh; dwIoControlCode
0x180085a0c  call    AsyncDriverRequest
0x180085a11  test    rdi, rdi
0x180085a14  jz      short loc_180085A1E
0x180085a16  mov     ecx, r14d
0x180085a19  call    ReleaseObjReadLock
0x180085a1e  mov     eax, ebx
0x180085a20  mov     rcx, [rbp+780h+var_40]
0x180085a27  xor     rcx, rsp; StackCookie
0x180085a2a  call    __security_check_cookie
0x180085a2f  add     rsp, 858h
0x180085a36  pop     r15
0x180085a38  pop     r14
0x180085a3a  pop     rdi
0x180085a3b  pop     rsi
0x180085a3c  pop     rbx
0x180085a3d  pop     rbp
0x180085a3e  retn
```
