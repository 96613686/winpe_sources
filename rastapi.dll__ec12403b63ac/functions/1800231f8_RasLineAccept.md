# RasLineAccept

- ea: `0x1800231f8`
- end: `0x1800233fd`
- name: `RasLineAccept`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180010330`

## callees

- `0x180020c98`
- `0x180022314`
- `0x1800231f8`
- `0x180027270`
- `0x180027d38`
- `0x180028b5c`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x180023297`
- `rtutils!TracePrintfA` at `0x180023325`
- `rtutils!TracePrintfA` at `0x180023297`
- `rtutils!TracePrintfA` at `0x180023325`

## string_xrefs

- `0x1800232ce`: `RasLineAnswer: GetCallObjWithReadLock failed with error (0x%x)`
- `0x18002331b`: `RasLineAnswer: GetCallObjWithReadLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineAccept(unsigned int a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  unsigned int NDProxyHandle; // eax
  unsigned int *v7; // rdi
  unsigned int v8; // ebx
  const wchar_t *v9; // rdx
  bool v10; // zf
  char *v11; // rdx
  unsigned int *v13; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v15; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+40h] [rbp-C0h] BYREF
  char v17[2044]; // [rsp+44h] [rbp-BCh] BYREF

  lpMem = 0;
  v13 = 0;
  v15 = 0;
  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( qword_18003EC48 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(
        gNdpspEtwContext,
        qword_18003EC48,
        L"RasLineAnswer...");
  }
  else if ( dwTraceId != -1 )
  {
    TracePrintfA(dwTraceId, "RasLineAnswer...");
  }
  *a5 = 0;
  NDProxyHandle = GetCallObjWithReadLock(a1, &v13);
  v7 = v13;
  v8 = NDProxyHandle;
  if ( NDProxyHandle )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( !qword_18003EC40 )
        goto LABEL_25;
      v9 = L"RasLineAnswer: GetCallObjWithReadLock failed with error (0x%x)";
      goto LABEL_10;
    }
    if ( dwTraceId != -1 )
      TracePrintfA(dwTraceId, "RasLineAnswer: GetCallObjWithReadLock failed with error (0x%x)", NDProxyHandle);
  }
  else
  {
    NDProxyHandle = GetNDProxyHandle(v13, &v15);
    v8 = NDProxyHandle;
    if ( NDProxyHandle )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( qword_18003EC40 )
        {
          v9 = L"RasLineAnswer: GetNDProxyHandle failed with error (0x%x)";
LABEL_10:
          LOWORD(v16) = 0;
          FormatRRASErrorString(&v16, v9, NDProxyHandle);
          ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v16);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "RasLineAnswer: GetNDProxyHandle failed with error (0x%x)", NDProxyHandle);
      }
    }
    else
    {
      v8 = PrepareAsyncRequest(0x7030101u, v7[1], 0x18u, &lpMem);
      if ( !v8 )
      {
        v10 = g_fUseReqId == 0;
        v11 = (char *)lpMem;
        *((_QWORD *)lpMem + 20) = v15;
        *((_DWORD *)v11 + 42) = 0;
        if ( v10 )
          *((_DWORD *)v11 + 38) = 0;
        else
          *a5 = *((_DWORD *)v11 + 38);
        AsyncDriverRequest(0x8FFF23CC, v11);
      }
    }
  }
LABEL_25:
  if ( v7 )
    ReleaseObjReadLock(a1);
  return v8;
}

```

## disassembly

```asm
0x1800231f8  push    rbp
0x1800231fa  push    rbx
0x1800231fb  push    rsi
0x1800231fc  push    rdi
0x1800231fd  push    r14
0x1800231ff  push    r15
0x180023201  lea     rbp, [rsp-758h]
0x180023209  sub     rsp, 858h
0x180023210  mov     rax, cs:__security_cookie
0x180023217  xor     rax, rsp
0x18002321a  mov     [rbp+780h+var_40], rax
0x180023221  mov     rsi, [rbp+780h+arg_20]
0x180023228  xor     r15d, r15d
0x18002322b  mov     r14d, ecx
0x18002322e  mov     [rsp+880h+lpMem], r15
0x180023233  lea     rcx, [rsp+880h+var_83C]; void *
0x180023238  mov     [rsp+880h+var_860], r15
0x18002323d  xor     edx, edx; Val
0x18002323f  mov     [rsp+880h+var_850], r15
0x180023244  mov     r8d, 7FCh; Size
0x18002324a  mov     [rsp+880h+var_840], r15d
0x18002324f  call    memset_0
0x180023254  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x18002325b  jz      short loc_180023285
0x18002325d  mov     rdx, cs:qword_18003EC48
0x180023264  test    rdx, rdx
0x180023267  jz      short loc_18002329D
0x180023269  mov     rcx, cs:gNdpspEtwContext
0x180023270  lea     r8, aRaslineanswer_0; "RasLineAnswer..."
0x180023277  mov     rax, cs:gNdpspTemplateFunc
0x18002327e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023283  jmp     short loc_18002329D
0x180023285  mov     ecx, cs:dwTraceId; dwTraceID
0x18002328b  cmp     ecx, 0FFFFFFFFh
0x18002328e  jz      short loc_18002329D
0x180023290  lea     rdx, aRaslineanswer; "RasLineAnswer..."
0x180023297  call    cs:__imp_TracePrintfA
0x18002329d  lea     rdx, [rsp+880h+var_860]
0x1800232a2  mov     [rsi], r15d
0x1800232a5  mov     ecx, r14d
0x1800232a8  call    GetCallObjWithReadLock
0x1800232ad  mov     rdi, [rsp+880h+var_860]
0x1800232b2  mov     ebx, eax
0x1800232b4  test    eax, eax
0x1800232b6  jz      short loc_180023330
0x1800232b8  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x1800232bf  jz      short loc_18002330C
0x1800232c1  cmp     cs:qword_18003EC40, r15
0x1800232c8  jz      loc_1800233CF
0x1800232ce  lea     rdx, aRaslineanswerG_0; "RasLineAnswer: GetCallObjWithReadLock f"...
0x1800232d5  mov     r8d, eax
0x1800232d8  mov     word ptr [rsp+880h+var_840], r15w
0x1800232de  lea     rcx, [rsp+880h+var_840]
0x1800232e3  call    FormatRRASErrorString
0x1800232e8  mov     rdx, cs:qword_18003EC40
0x1800232ef  lea     r8, [rsp+880h+var_840]
0x1800232f4  mov     rcx, cs:gNdpspEtwContext
0x1800232fb  mov     rax, cs:gNdpspTemplateFunc
0x180023302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023307  jmp     loc_1800233CF
0x18002330c  mov     ecx, cs:dwTraceId; dwTraceID
0x180023312  cmp     ecx, 0FFFFFFFFh
0x180023315  jz      loc_1800233CF
0x18002331b  lea     rdx, aRaslineanswerG_2; "RasLineAnswer: GetCallObjWithReadLock f"...
0x180023322  mov     r8d, eax
0x180023325  call    cs:__imp_TracePrintfA
0x18002332b  jmp     loc_1800233CF
0x180023330  lea     rdx, [rsp+880h+var_850]
0x180023335  mov     rcx, rdi
0x180023338  call    GetNDProxyHandle
0x18002333d  mov     ebx, eax
0x18002333f  test    eax, eax
0x180023341  jz      short loc_180023375
0x180023343  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x18002334a  jz      short loc_180023361
0x18002334c  cmp     cs:qword_18003EC40, r15
0x180023353  jz      short loc_1800233CF
0x180023355  lea     rdx, aRaslineanswerG; "RasLineAnswer: GetNDProxyHandle failed "...
0x18002335c  jmp     loc_1800232D5
0x180023361  mov     ecx, cs:dwTraceId
0x180023367  cmp     ecx, 0FFFFFFFFh
0x18002336a  jz      short loc_1800233CF
0x18002336c  lea     rdx, aRaslineanswerG_1; "RasLineAnswer: GetNDProxyHandle failed "...
0x180023373  jmp     short loc_180023322
0x180023375  mov     edx, [rdi+4]
0x180023378  lea     r9, [rsp+880h+lpMem]
0x18002337d  mov     r8d, 18h
0x180023383  mov     ecx, 7030101h
0x180023388  call    PrepareAsyncRequest
0x18002338d  mov     ebx, eax
0x18002338f  test    eax, eax
0x180023391  jnz     short loc_1800233CF
0x180023393  cmp     cs:g_fUseReqId, r15d
0x18002339a  mov     rdx, [rsp+880h+lpMem]; lpMem
0x18002339f  mov     rax, [rsp+880h+var_850]
0x1800233a4  mov     [rdx+0A0h], rax
0x1800233ab  mov     [rdx+0A8h], r15d
0x1800233b2  jz      short loc_1800233BE
0x1800233b4  mov     eax, [rdx+98h]
0x1800233ba  mov     [rsi], eax
0x1800233bc  jmp     short loc_1800233C5
0x1800233be  mov     [rdx+98h], r15d
0x1800233c5  mov     ecx, 8FFF23CCh; dwIoControlCode
0x1800233ca  call    AsyncDriverRequest
0x1800233cf  test    rdi, rdi
0x1800233d2  jz      short loc_1800233DC
0x1800233d4  mov     ecx, r14d
0x1800233d7  call    ReleaseObjReadLock
0x1800233dc  mov     eax, ebx
0x1800233de  mov     rcx, [rbp+780h+var_40]
0x1800233e5  xor     rcx, rsp; StackCookie
0x1800233e8  call    __security_check_cookie
0x1800233ed  add     rsp, 858h
0x1800233f4  pop     r15
0x1800233f6  pop     r14
0x1800233f8  pop     rdi
0x1800233f9  pop     rsi
0x1800233fa  pop     rbx
0x1800233fb  pop     rbp
0x1800233fc  retn
```
