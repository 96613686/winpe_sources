# RasLineAnswer

- ea: `0x180023404`
- end: `0x180023609`
- name: `RasLineAnswer`
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
- `0x180023404`
- `0x180027270`
- `0x180027d38`
- `0x180028b5c`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x1800234a3`
- `rtutils!TracePrintfA` at `0x180023531`
- `rtutils!TracePrintfA` at `0x1800234a3`
- `rtutils!TracePrintfA` at `0x180023531`

## string_xrefs

- `0x1800234da`: `RasLineAnswer: GetCallObjWithReadLock failed with error (0x%x)`
- `0x180023527`: `RasLineAnswer: GetCallObjWithReadLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineAnswer(unsigned int a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5)
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
      v8 = PrepareAsyncRequest(0x7030102u, v7[1], 0x18u, &lpMem);
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
0x180023404  push    rbp
0x180023406  push    rbx
0x180023407  push    rsi
0x180023408  push    rdi
0x180023409  push    r14
0x18002340b  push    r15
0x18002340d  lea     rbp, [rsp-758h]
0x180023415  sub     rsp, 858h
0x18002341c  mov     rax, cs:__security_cookie
0x180023423  xor     rax, rsp
0x180023426  mov     [rbp+780h+var_40], rax
0x18002342d  mov     rsi, [rbp+780h+arg_20]
0x180023434  xor     r15d, r15d
0x180023437  mov     r14d, ecx
0x18002343a  mov     [rsp+880h+lpMem], r15
0x18002343f  lea     rcx, [rsp+880h+var_83C]; void *
0x180023444  mov     [rsp+880h+var_860], r15
0x180023449  xor     edx, edx; Val
0x18002344b  mov     [rsp+880h+var_850], r15
0x180023450  mov     r8d, 7FCh; Size
0x180023456  mov     [rsp+880h+var_840], r15d
0x18002345b  call    memset_0
0x180023460  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x180023467  jz      short loc_180023491
0x180023469  mov     rdx, cs:qword_18003EC48
0x180023470  test    rdx, rdx
0x180023473  jz      short loc_1800234A9
0x180023475  mov     rcx, cs:gNdpspEtwContext
0x18002347c  lea     r8, aRaslineanswer_0; "RasLineAnswer..."
0x180023483  mov     rax, cs:gNdpspTemplateFunc
0x18002348a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002348f  jmp     short loc_1800234A9
0x180023491  mov     ecx, cs:dwTraceId; dwTraceID
0x180023497  cmp     ecx, 0FFFFFFFFh
0x18002349a  jz      short loc_1800234A9
0x18002349c  lea     rdx, aRaslineanswer; "RasLineAnswer..."
0x1800234a3  call    cs:__imp_TracePrintfA
0x1800234a9  lea     rdx, [rsp+880h+var_860]
0x1800234ae  mov     [rsi], r15d
0x1800234b1  mov     ecx, r14d
0x1800234b4  call    GetCallObjWithReadLock
0x1800234b9  mov     rdi, [rsp+880h+var_860]
0x1800234be  mov     ebx, eax
0x1800234c0  test    eax, eax
0x1800234c2  jz      short loc_18002353C
0x1800234c4  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x1800234cb  jz      short loc_180023518
0x1800234cd  cmp     cs:qword_18003EC40, r15
0x1800234d4  jz      loc_1800235DB
0x1800234da  lea     rdx, aRaslineanswerG_0; "RasLineAnswer: GetCallObjWithReadLock f"...
0x1800234e1  mov     r8d, eax
0x1800234e4  mov     word ptr [rsp+880h+var_840], r15w
0x1800234ea  lea     rcx, [rsp+880h+var_840]
0x1800234ef  call    FormatRRASErrorString
0x1800234f4  mov     rdx, cs:qword_18003EC40
0x1800234fb  lea     r8, [rsp+880h+var_840]
0x180023500  mov     rcx, cs:gNdpspEtwContext
0x180023507  mov     rax, cs:gNdpspTemplateFunc
0x18002350e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023513  jmp     loc_1800235DB
0x180023518  mov     ecx, cs:dwTraceId; dwTraceID
0x18002351e  cmp     ecx, 0FFFFFFFFh
0x180023521  jz      loc_1800235DB
0x180023527  lea     rdx, aRaslineanswerG_2; "RasLineAnswer: GetCallObjWithReadLock f"...
0x18002352e  mov     r8d, eax
0x180023531  call    cs:__imp_TracePrintfA
0x180023537  jmp     loc_1800235DB
0x18002353c  lea     rdx, [rsp+880h+var_850]
0x180023541  mov     rcx, rdi
0x180023544  call    GetNDProxyHandle
0x180023549  mov     ebx, eax
0x18002354b  test    eax, eax
0x18002354d  jz      short loc_180023581
0x18002354f  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x180023556  jz      short loc_18002356D
0x180023558  cmp     cs:qword_18003EC40, r15
0x18002355f  jz      short loc_1800235DB
0x180023561  lea     rdx, aRaslineanswerG; "RasLineAnswer: GetNDProxyHandle failed "...
0x180023568  jmp     loc_1800234E1
0x18002356d  mov     ecx, cs:dwTraceId
0x180023573  cmp     ecx, 0FFFFFFFFh
0x180023576  jz      short loc_1800235DB
0x180023578  lea     rdx, aRaslineanswerG_1; "RasLineAnswer: GetNDProxyHandle failed "...
0x18002357f  jmp     short loc_18002352E
0x180023581  mov     edx, [rdi+4]
0x180023584  lea     r9, [rsp+880h+lpMem]
0x180023589  mov     r8d, 18h
0x18002358f  mov     ecx, 7030102h
0x180023594  call    PrepareAsyncRequest
0x180023599  mov     ebx, eax
0x18002359b  test    eax, eax
0x18002359d  jnz     short loc_1800235DB
0x18002359f  cmp     cs:g_fUseReqId, r15d
0x1800235a6  mov     rdx, [rsp+880h+lpMem]; lpMem
0x1800235ab  mov     rax, [rsp+880h+var_850]
0x1800235b0  mov     [rdx+0A0h], rax
0x1800235b7  mov     [rdx+0A8h], r15d
0x1800235be  jz      short loc_1800235CA
0x1800235c0  mov     eax, [rdx+98h]
0x1800235c6  mov     [rsi], eax
0x1800235c8  jmp     short loc_1800235D1
0x1800235ca  mov     [rdx+98h], r15d
0x1800235d1  mov     ecx, 8FFF23CCh; dwIoControlCode
0x1800235d6  call    AsyncDriverRequest
0x1800235db  test    rdi, rdi
0x1800235de  jz      short loc_1800235E8
0x1800235e0  mov     ecx, r14d
0x1800235e3  call    ReleaseObjReadLock
0x1800235e8  mov     eax, ebx
0x1800235ea  mov     rcx, [rbp+780h+var_40]
0x1800235f1  xor     rcx, rsp; StackCookie
0x1800235f4  call    __security_check_cookie
0x1800235f9  add     rsp, 858h
0x180023600  pop     r15
0x180023602  pop     r14
0x180023604  pop     rdi
0x180023605  pop     rsi
0x180023606  pop     rbx
0x180023607  pop     rbp
0x180023608  retn
```
