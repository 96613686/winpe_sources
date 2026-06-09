# RasLineDrop

- ea: `0x18008625c`
- end: `0x1800864d0`
- name: `RasLineDrop`
- size: `628`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x1800263c4`
- `0x180028570`

## callees

- `0x180071cec`
- `0x18008308c`
- `0x180084704`
- `0x18008625c`
- `0x180088b1c`
- `0x1800895e4`
- `0x180089924`
- `0x18008a408`
- `0x18008a51c`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x180086303`
- `rtutils!TracePrintfA` at `0x18008638a`
- `rtutils!TracePrintfA` at `0x180086303`
- `rtutils!TracePrintfA` at `0x18008638a`

## string_xrefs

- `0x18008642a`: `RasLineCloseCall: AcquireObjWriteLock failed with error (0x%x)`
- `0x180086410`: `RasLineCloseCall: AcquireObjWriteLock failed with error (0x%x)`
- `0x180086380`: `RasLineDrop: GetCallObjWithReadLock failed with error (0x%x)`
- `0x180086334`: `RasLineDrop: GetCallObjWithReadLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineDrop(unsigned int a1, __int64 a2, __int64 a3, int a4, _DWORD *a5)
{
  unsigned int NDProxyHandle; // eax
  unsigned int v8; // ebx
  const wchar_t *v9; // rdx
  unsigned int *v10; // r14
  char *v11; // rdi
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
    if ( *((_QWORD *)&xmmword_1800C9BE0 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
        gNdpspEtwContext,
        *((_QWORD *)&xmmword_1800C9BE0 + 1),
        L"RasLineDrop...");
  }
  else if ( dwTraceId != -1 )
  {
    TracePrintfA(dwTraceId, "RasLineDrop...");
  }
  *a5 = 0;
  NDProxyHandle = GetCallObjWithReadLock(a1, &v13);
  v8 = NDProxyHandle;
  if ( NDProxyHandle )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        v9 = L"RasLineDrop: GetCallObjWithReadLock failed with error (0x%x)";
LABEL_10:
        LOWORD(v16) = 0;
        FormatRRASErrorString(&v16, v9, NDProxyHandle);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v16);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "RasLineDrop: GetCallObjWithReadLock failed with error (0x%x)", NDProxyHandle);
    }
  }
  else
  {
    v10 = v13;
    NDProxyHandle = GetNDProxyHandle(v13, &v15);
    v8 = NDProxyHandle;
    if ( NDProxyHandle )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( !(_QWORD)xmmword_1800C9BE0 )
          return v8;
        v9 = L"RasLineDrop: GetNDProxyHandle failed with error (0x%x)";
        goto LABEL_10;
      }
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineDrop: GetNDProxyHandle failed with error (0x%x)", NDProxyHandle);
    }
    else
    {
      ReleaseObjReadLock(a1);
      NDProxyHandle = AcquireObjWriteLock(a1);
      v8 = NDProxyHandle;
      if ( NDProxyHandle )
      {
        if ( gIsndpspEtwTracingAvailable )
        {
          if ( !(_QWORD)xmmword_1800C9BE0 )
            return v8;
          v9 = L"RasLineCloseCall: AcquireObjWriteLock failed with error (0x%x)";
          goto LABEL_10;
        }
        if ( dwTraceId != -1 )
          TracePrintfA(dwTraceId, "RasLineCloseCall: AcquireObjWriteLock failed with error (0x%x)", NDProxyHandle);
      }
      else
      {
        v8 = PrepareAsyncRequest(117637385, v10[1], 24, &lpMem);
        if ( v8 )
        {
          ReleaseObjWriteLock(a1);
        }
        else
        {
          v11 = (char *)lpMem;
          *((_QWORD *)lpMem + 20) = v15;
          v10[17] = 1;
          *((_DWORD *)v11 + 42) = 0;
          ReleaseObjWriteLock(a1);
          if ( g_fUseReqId )
            *a5 = *((_DWORD *)v11 + 38);
          else
            *((_DWORD *)v11 + 38) = a4;
          AsyncDriverRequest(0x8FFF23CC, v11);
        }
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18008625c  push    rbp
0x18008625e  push    rbx
0x18008625f  push    rsi
0x180086260  push    rdi
0x180086261  push    r12
0x180086263  push    r13
0x180086265  push    r14
0x180086267  push    r15
0x180086269  lea     rbp, [rsp-758h]
0x180086271  sub     rsp, 858h
0x180086278  mov     rax, cs:__security_cookie
0x18008627f  xor     rax, rsp
0x180086282  mov     [rbp+790h+var_50], rax
0x180086289  mov     r15, [rbp+790h+arg_20]
0x180086290  xor     r13d, r13d
0x180086293  mov     esi, ecx
0x180086295  mov     [rsp+890h+lpMem], r13
0x18008629a  lea     rcx, [rsp+890h+var_84C]; void *
0x18008629f  mov     [rsp+890h+var_870], r13
0x1800862a4  xor     edx, edx; Val
0x1800862a6  mov     [rsp+890h+var_860], r13
0x1800862ab  mov     r8d, 7FCh; Size
0x1800862b1  mov     [rsp+890h+var_850], r13d
0x1800862b6  mov     r12, r9
0x1800862b9  call    memset_0
0x1800862be  or      edi, 0FFFFFFFFh
0x1800862c1  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x1800862c8  jz      short loc_1800862F2
0x1800862ca  mov     rdx, qword ptr cs:xmmword_1800C9BE0+8
0x1800862d1  test    rdx, rdx
0x1800862d4  jz      short loc_180086309
0x1800862d6  mov     rcx, cs:gNdpspEtwContext
0x1800862dd  lea     r8, aRaslinedrop; "RasLineDrop..."
0x1800862e4  mov     rax, cs:gNdpspTemplateFunc
0x1800862eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800862f0  jmp     short loc_180086309
0x1800862f2  mov     ecx, cs:dwTraceId; dwTraceID
0x1800862f8  cmp     ecx, edi
0x1800862fa  jz      short loc_180086309
0x1800862fc  lea     rdx, aRaslinedrop_0; "RasLineDrop..."
0x180086303  call    cs:__imp_TracePrintfA
0x180086309  lea     rdx, [rsp+890h+var_870]
0x18008630e  mov     [r15], r13d
0x180086311  mov     ecx, esi
0x180086313  call    GetCallObjWithReadLock
0x180086318  mov     ebx, eax
0x18008631a  test    eax, eax
0x18008631c  jz      short loc_180086395
0x18008631e  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180086325  jz      short loc_180086372
0x180086327  cmp     qword ptr cs:xmmword_1800C9BE0, r13
0x18008632e  jz      loc_1800864AB
0x180086334  lea     rdx, aRaslinedropGet_0; "RasLineDrop: GetCallObjWithReadLock fai"...
0x18008633b  mov     r8d, eax
0x18008633e  mov     word ptr [rsp+890h+var_850], r13w
0x180086344  lea     rcx, [rsp+890h+var_850]
0x180086349  call    FormatRRASErrorString
0x18008634e  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180086355  lea     r8, [rsp+890h+var_850]
0x18008635a  mov     rcx, cs:gNdpspEtwContext
0x180086361  mov     rax, cs:gNdpspTemplateFunc
0x180086368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008636d  jmp     loc_1800864AB
0x180086372  mov     ecx, cs:dwTraceId; dwTraceID
0x180086378  cmp     ecx, edi
0x18008637a  jz      loc_1800864AB
0x180086380  lea     rdx, aRaslinedropGet_1; "RasLineDrop: GetCallObjWithReadLock fai"...
0x180086387  mov     r8d, eax
0x18008638a  call    cs:__imp_TracePrintfA
0x180086390  jmp     loc_1800864AB
0x180086395  mov     r14, [rsp+890h+var_870]
0x18008639a  lea     rdx, [rsp+890h+var_860]
0x18008639f  mov     rcx, r14
0x1800863a2  call    GetNDProxyHandle
0x1800863a7  mov     ebx, eax
0x1800863a9  test    eax, eax
0x1800863ab  jz      short loc_1800863E6
0x1800863ad  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x1800863b4  jz      short loc_1800863CF
0x1800863b6  cmp     qword ptr cs:xmmword_1800C9BE0, r13
0x1800863bd  jz      loc_1800864AB
0x1800863c3  lea     rdx, aRaslinedropGet; "RasLineDrop: GetNDProxyHandle failed wi"...
0x1800863ca  jmp     loc_18008633B
0x1800863cf  mov     ecx, cs:dwTraceId
0x1800863d5  cmp     ecx, edi
0x1800863d7  jz      loc_1800864AB
0x1800863dd  lea     rdx, aRaslinedropGet_2; "RasLineDrop: GetNDProxyHandle failed wi"...
0x1800863e4  jmp     short loc_180086387
0x1800863e6  mov     ecx, esi
0x1800863e8  call    ReleaseObjReadLock
0x1800863ed  mov     ecx, esi
0x1800863ef  call    AcquireObjWriteLock
0x1800863f4  mov     ebx, eax
0x1800863f6  test    eax, eax
0x1800863f8  jz      short loc_180086436
0x1800863fa  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180086401  jz      short loc_18008641C
0x180086403  cmp     qword ptr cs:xmmword_1800C9BE0, r13
0x18008640a  jz      loc_1800864AB
0x180086410  lea     rdx, aRaslinecloseca_8; "RasLineCloseCall: AcquireObjWriteLock f"...
0x180086417  jmp     loc_18008633B
0x18008641c  mov     ecx, cs:dwTraceId
0x180086422  cmp     ecx, edi
0x180086424  jz      loc_1800864AB
0x18008642a  lea     rdx, aRaslinecloseca_1; "RasLineCloseCall: AcquireObjWriteLock f"...
0x180086431  jmp     loc_180086387
0x180086436  mov     edx, [r14+4]
0x18008643a  lea     r9, [rsp+890h+lpMem]
0x18008643f  mov     r8d, 18h
0x180086445  mov     ecx, 7030109h
0x18008644a  call    PrepareAsyncRequest
0x18008644f  mov     ebx, eax
0x180086451  mov     ecx, esi
0x180086453  test    eax, eax
0x180086455  jz      short loc_18008645E
0x180086457  call    ReleaseObjWriteLock
0x18008645c  jmp     short loc_1800864AB
0x18008645e  mov     rdi, [rsp+890h+lpMem]
0x180086463  mov     rax, [rsp+890h+var_860]
0x180086468  mov     [rdi+0A0h], rax
0x18008646f  mov     dword ptr [r14+44h], 1
0x180086477  mov     [rdi+0A8h], r13d
0x18008647e  call    ReleaseObjWriteLock
0x180086483  cmp     cs:g_fUseReqId, r13d
0x18008648a  jz      short loc_180086497
0x18008648c  mov     eax, [rdi+98h]
0x180086492  mov     [r15], eax
0x180086495  jmp     short loc_18008649E
0x180086497  mov     [rdi+98h], r12d
0x18008649e  mov     rdx, rdi; lpMem
0x1800864a1  mov     ecx, 8FFF23CCh; dwIoControlCode
0x1800864a6  call    AsyncDriverRequest
0x1800864ab  mov     eax, ebx
0x1800864ad  mov     rcx, [rbp+790h+var_50]
0x1800864b4  xor     rcx, rsp; StackCookie
0x1800864b7  call    __security_check_cookie
0x1800864bc  add     rsp, 858h
0x1800864c3  pop     r15
0x1800864c5  pop     r14
0x1800864c7  pop     r13
0x1800864c9  pop     r12
0x1800864cb  pop     rdi
0x1800864cc  pop     rsi
0x1800864cd  pop     rbx
0x1800864ce  pop     rbp
0x1800864cf  retn
```
