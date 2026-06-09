# RasLineAccept

- ea: `0x1800855e8`
- end: `0x18008580f`
- name: `RasLineAccept`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180025f64`

## callees

- `0x180071cec`
- `0x18008308c`
- `0x180084704`
- `0x1800855e8`
- `0x180088b1c`
- `0x1800895e4`
- `0x18008a408`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x180085694`
- `rtutils!TracePrintfA` at `0x180085727`
- `rtutils!TracePrintfA` at `0x180085694`
- `rtutils!TracePrintfA` at `0x180085727`

## string_xrefs

- `0x180085720`: `RasLineAnswer: GetCallObjWithReadLock failed with error (0x%x)`
- `0x1800856d1`: `RasLineAnswer: GetCallObjWithReadLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineAccept(unsigned int a1, __int64 a2, __int64 a3, int a4, _DWORD *a5)
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
      NDProxyHandle = PrepareAsyncRequest(117637377, v8[1], 24, &lpMem);
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
0x1800855e8  push    rbp
0x1800855ea  push    rbx
0x1800855eb  push    rsi
0x1800855ec  push    rdi
0x1800855ed  push    r14
0x1800855ef  push    r15
0x1800855f1  lea     rbp, [rsp-758h]
0x1800855f9  sub     rsp, 858h
0x180085600  mov     rax, cs:__security_cookie
0x180085607  xor     rax, rsp
0x18008560a  mov     [rbp+780h+var_40], rax
0x180085611  mov     rsi, [rbp+780h+arg_20]
0x180085618  mov     r14d, ecx
0x18008561b  xor     eax, eax
0x18008561d  mov     [rsp+880h+lpMem], 0
0x180085626  lea     rcx, [rsp+880h+var_83C]; void *
0x18008562b  mov     [rsp+880h+var_840], eax
0x18008562f  xor     edx, edx; Val
0x180085631  mov     [rsp+880h+var_860], 0
0x18008563a  mov     r8d, 7FCh; Size
0x180085640  mov     [rsp+880h+var_850], 0
0x180085649  mov     r15, r9
0x18008564c  call    memset_0
0x180085651  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180085658  jz      short loc_180085682
0x18008565a  mov     rdx, qword ptr cs:xmmword_1800C9BE0+8
0x180085661  test    rdx, rdx
0x180085664  jz      short loc_18008569A
0x180085666  mov     rcx, cs:gNdpspEtwContext
0x18008566d  lea     r8, aRaslineanswer_0; "RasLineAnswer..."
0x180085674  mov     rax, cs:gNdpspTemplateFunc
0x18008567b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085680  jmp     short loc_18008569A
0x180085682  mov     ecx, cs:dwTraceId; dwTraceID
0x180085688  cmp     ecx, 0FFFFFFFFh
0x18008568b  jz      short loc_18008569A
0x18008568d  lea     rdx, aRaslineanswer; "RasLineAnswer..."
0x180085694  call    cs:__imp_TracePrintfA
0x18008569a  lea     rdx, [rsp+880h+var_860]
0x18008569f  mov     dword ptr [rsi], 0
0x1800856a5  mov     ecx, r14d
0x1800856a8  call    GetCallObjWithReadLock
0x1800856ad  mov     rdi, [rsp+880h+var_860]
0x1800856b2  mov     ebx, eax
0x1800856b4  test    eax, eax
0x1800856b6  jz      short loc_180085732
0x1800856b8  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x1800856bf  jz      short loc_18008570E
0x1800856c1  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x1800856c9  jz      loc_1800857E1
0x1800856cf  xor     ecx, ecx
0x1800856d1  lea     rdx, aRaslineanswerG_0; "RasLineAnswer: GetCallObjWithReadLock f"...
0x1800856d8  mov     word ptr [rsp+880h+var_840], cx
0x1800856dd  mov     r8d, eax
0x1800856e0  lea     rcx, [rsp+880h+var_840]
0x1800856e5  call    FormatRRASErrorString
0x1800856ea  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x1800856f1  lea     r8, [rsp+880h+var_840]
0x1800856f6  mov     rcx, cs:gNdpspEtwContext
0x1800856fd  mov     rax, cs:gNdpspTemplateFunc
0x180085704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085709  jmp     loc_1800857E1
0x18008570e  mov     ecx, cs:dwTraceId; dwTraceID
0x180085714  cmp     ecx, 0FFFFFFFFh
0x180085717  jz      loc_1800857E1
0x18008571d  mov     r8d, eax
0x180085720  lea     rdx, aRaslineanswerG_2; "RasLineAnswer: GetCallObjWithReadLock f"...
0x180085727  call    cs:__imp_TracePrintfA
0x18008572d  jmp     loc_1800857E1
0x180085732  lea     rdx, [rsp+880h+var_850]
0x180085737  mov     rcx, rdi
0x18008573a  call    GetNDProxyHandle
0x18008573f  mov     ebx, eax
0x180085741  test    eax, eax
0x180085743  jz      short loc_180085789
0x180085745  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x18008574c  jz      short loc_180085772
0x18008574e  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x180085756  jz      loc_1800857E1
0x18008575c  xor     eax, eax
0x18008575e  lea     rdx, aRaslineanswerG; "RasLineAnswer: GetNDProxyHandle failed "...
0x180085765  mov     word ptr [rsp+880h+var_840], ax
0x18008576a  mov     r8d, ebx
0x18008576d  jmp     loc_1800856E0
0x180085772  mov     ecx, cs:dwTraceId
0x180085778  cmp     ecx, 0FFFFFFFFh
0x18008577b  jz      short loc_1800857E1
0x18008577d  mov     r8d, ebx
0x180085780  lea     rdx, aRaslineanswerG_1; "RasLineAnswer: GetNDProxyHandle failed "...
0x180085787  jmp     short loc_180085727
0x180085789  mov     edx, [rdi+4]
0x18008578c  lea     r9, [rsp+880h+lpMem]
0x180085791  mov     r8d, 18h
0x180085797  mov     ecx, 7030101h
0x18008579c  call    PrepareAsyncRequest
0x1800857a1  mov     ebx, eax
0x1800857a3  test    eax, eax
0x1800857a5  jnz     short loc_1800857E1
0x1800857a7  cmp     cs:g_fUseReqId, ebx
0x1800857ad  mov     rdx, [rsp+880h+lpMem]; lpMem
0x1800857b2  mov     rax, [rsp+880h+var_850]
0x1800857b7  mov     [rdx+0A0h], rax
0x1800857be  mov     [rdx+0A8h], ebx
0x1800857c4  jz      short loc_1800857D0
0x1800857c6  mov     eax, [rdx+98h]
0x1800857cc  mov     [rsi], eax
0x1800857ce  jmp     short loc_1800857D7
0x1800857d0  mov     [rdx+98h], r15d
0x1800857d7  mov     ecx, 8FFF23CCh; dwIoControlCode
0x1800857dc  call    AsyncDriverRequest
0x1800857e1  test    rdi, rdi
0x1800857e4  jz      short loc_1800857EE
0x1800857e6  mov     ecx, r14d
0x1800857e9  call    ReleaseObjReadLock
0x1800857ee  mov     eax, ebx
0x1800857f0  mov     rcx, [rbp+780h+var_40]
0x1800857f7  xor     rcx, rsp; StackCookie
0x1800857fa  call    __security_check_cookie
0x1800857ff  add     rsp, 858h
0x180085806  pop     r15
0x180085808  pop     r14
0x18008580a  pop     rdi
0x18008580b  pop     rsi
0x18008580c  pop     rbx
0x18008580d  pop     rbp
0x18008580e  retn
```
