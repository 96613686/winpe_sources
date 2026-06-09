# RasLineDrop

- ea: `0x18008c2d8`
- end: `0x18008c570`
- name: `RasLineDrop`
- size: `664`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x1800285b8`
- `0x18002a7b0`

## callees

- `0x1800755b8`
- `0x180088d74`
- `0x18008a694`
- `0x18008c2d8`
- `0x18008ed64`
- `0x18008f82c`
- `0x18008fb8c`
- `0x180090714`
- `0x180090834`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x18008c389`
- `rtutils!TracePrintfA` at `0x18008c416`
- `rtutils!TracePrintfA` at `0x18008c389`
- `rtutils!TracePrintfA` at `0x18008c416`

## string_xrefs

- `0x18008c4a2`: `RasLineCloseCall: AcquireObjWriteLock failed with error (0x%x)`
- `0x18008c4bc`: `RasLineCloseCall: AcquireObjWriteLock failed with error (0x%x)`
- `0x18008c3c0`: `RasLineDrop: GetCallObjWithReadLock failed with error (0x%x)`
- `0x18008c40c`: `RasLineDrop: GetCallObjWithReadLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineDrop(unsigned int a1, __int64 a2, __int64 a3, int a4, _DWORD *a5)
{
  unsigned int NDProxyHandle; // eax
  unsigned int v8; // ebx
  const wchar_t *v9; // rdx
  unsigned int *v10; // r14
  __int64 v11; // rdx
  char *v12; // rdi
  unsigned int *v14; // [rsp+28h] [rbp-E0h] BYREF
  LPVOID lpMem; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v16; // [rsp+38h] [rbp-D0h] BYREF
  int v17; // [rsp+48h] [rbp-C0h] BYREF
  char v18[2044]; // [rsp+4Ch] [rbp-BCh] BYREF

  lpMem = 0;
  v14 = 0;
  v16 = 0;
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( *((_QWORD *)&xmmword_1800D0BE0 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
        gNdpspEtwContext,
        *((_QWORD *)&xmmword_1800D0BE0 + 1),
        L"RasLineDrop...");
  }
  else if ( dwTraceId != -1 )
  {
    TracePrintfA(dwTraceId, "RasLineDrop...");
  }
  *a5 = 0;
  NDProxyHandle = GetCallObjWithReadLock(a1, &v14);
  v8 = NDProxyHandle;
  if ( NDProxyHandle )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        v9 = L"RasLineDrop: GetCallObjWithReadLock failed with error (0x%x)";
LABEL_10:
        LOWORD(v17) = 0;
        FormatRRASErrorString(&v17, v9, NDProxyHandle);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v17);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "RasLineDrop: GetCallObjWithReadLock failed with error (0x%x)", NDProxyHandle);
    }
  }
  else
  {
    v10 = v14;
    NDProxyHandle = GetNDProxyHandle((__int64)v14, &v16);
    v8 = NDProxyHandle;
    if ( NDProxyHandle )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( !(_QWORD)xmmword_1800D0BE0 )
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
          if ( !(_QWORD)xmmword_1800D0BE0 )
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
          ReleaseObjWriteLock(a1, v11);
        }
        else
        {
          v12 = (char *)lpMem;
          *((_QWORD *)lpMem + 20) = v16;
          v10[17] = 1;
          *((_DWORD *)v12 + 42) = 0;
          ReleaseObjWriteLock(a1, v11);
          if ( g_fUseReqId )
            *a5 = *((_DWORD *)v12 + 38);
          else
            *((_DWORD *)v12 + 38) = a4;
          AsyncDriverRequest(0x8FFF23CC, v12);
        }
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18008c2d8  mov     rax, rsp
0x18008c2db  mov     [rax+10h], rbx
0x18008c2df  mov     [rax+18h], rsi
0x18008c2e3  mov     [rax+20h], rdi
0x18008c2e7  push    rbp
0x18008c2e8  push    r12
0x18008c2ea  push    r13
0x18008c2ec  push    r14
0x18008c2ee  push    r15
0x18008c2f0  lea     rbp, [rax-778h]
0x18008c2f7  sub     rsp, 850h
0x18008c2fe  mov     rax, cs:__security_cookie
0x18008c305  xor     rax, rsp
0x18008c308  mov     [rbp+770h+var_30], rax
0x18008c30f  mov     r15, [rbp+770h+arg_20]
0x18008c316  xor     r13d, r13d
0x18008c319  mov     esi, ecx
0x18008c31b  mov     [rsp+870h+lpMem], r13
0x18008c320  lea     rcx, [rsp+870h+var_82C]; void *
0x18008c325  mov     [rsp+870h+var_850], r13
0x18008c32a  xor     edx, edx; Val
0x18008c32c  mov     [rsp+870h+var_840], r13
0x18008c331  mov     r8d, 7FCh; Size
0x18008c337  mov     [rsp+870h+var_830], r13d
0x18008c33c  mov     r12, r9
0x18008c33f  call    memset_0
0x18008c344  or      edi, 0FFFFFFFFh
0x18008c347  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008c34e  jz      short loc_18008C378
0x18008c350  mov     rdx, qword ptr cs:xmmword_1800D0BE0+8
0x18008c357  test    rdx, rdx
0x18008c35a  jz      short loc_18008C395
0x18008c35c  mov     rcx, cs:gNdpspEtwContext
0x18008c363  lea     r8, aRaslinedrop; "RasLineDrop..."
0x18008c36a  mov     rax, cs:gNdpspTemplateFunc
0x18008c371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c376  jmp     short loc_18008C395
0x18008c378  mov     ecx, cs:dwTraceId; dwTraceID
0x18008c37e  cmp     ecx, edi
0x18008c380  jz      short loc_18008C395
0x18008c382  lea     rdx, aRaslinedrop_0; "RasLineDrop..."
0x18008c389  call    cs:__imp_TracePrintfA
0x18008c390  nop     dword ptr [rax+rax+00h]
0x18008c395  lea     rdx, [rsp+870h+var_850]
0x18008c39a  mov     [r15], r13d
0x18008c39d  mov     ecx, esi
0x18008c39f  call    GetCallObjWithReadLock
0x18008c3a4  mov     ebx, eax
0x18008c3a6  test    eax, eax
0x18008c3a8  jz      short loc_18008C427
0x18008c3aa  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008c3b1  jz      short loc_18008C3FE
0x18008c3b3  cmp     qword ptr cs:xmmword_1800D0BE0, r13
0x18008c3ba  jz      loc_18008C53D
0x18008c3c0  lea     rdx, aRaslinedropGet_0; "RasLineDrop: GetCallObjWithReadLock fai"...
0x18008c3c7  mov     r8d, eax
0x18008c3ca  mov     word ptr [rsp+870h+var_830], r13w
0x18008c3d0  lea     rcx, [rsp+870h+var_830]
0x18008c3d5  call    FormatRRASErrorString
0x18008c3da  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008c3e1  lea     r8, [rsp+870h+var_830]
0x18008c3e6  mov     rcx, cs:gNdpspEtwContext
0x18008c3ed  mov     rax, cs:gNdpspTemplateFunc
0x18008c3f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c3f9  jmp     loc_18008C53D
0x18008c3fe  mov     ecx, cs:dwTraceId; dwTraceID
0x18008c404  cmp     ecx, edi
0x18008c406  jz      loc_18008C53D
0x18008c40c  lea     rdx, aRaslinedropGet_1; "RasLineDrop: GetCallObjWithReadLock fai"...
0x18008c413  mov     r8d, eax
0x18008c416  call    cs:__imp_TracePrintfA
0x18008c41d  nop     dword ptr [rax+rax+00h]
0x18008c422  jmp     loc_18008C53D
0x18008c427  mov     r14, [rsp+870h+var_850]
0x18008c42c  lea     rdx, [rsp+870h+var_840]
0x18008c431  mov     rcx, r14
0x18008c434  call    GetNDProxyHandle
0x18008c439  mov     ebx, eax
0x18008c43b  test    eax, eax
0x18008c43d  jz      short loc_18008C478
0x18008c43f  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008c446  jz      short loc_18008C461
0x18008c448  cmp     qword ptr cs:xmmword_1800D0BE0, r13
0x18008c44f  jz      loc_18008C53D
0x18008c455  lea     rdx, aRaslinedropGet; "RasLineDrop: GetNDProxyHandle failed wi"...
0x18008c45c  jmp     loc_18008C3C7
0x18008c461  mov     ecx, cs:dwTraceId
0x18008c467  cmp     ecx, edi
0x18008c469  jz      loc_18008C53D
0x18008c46f  lea     rdx, aRaslinedropGet_2; "RasLineDrop: GetNDProxyHandle failed wi"...
0x18008c476  jmp     short loc_18008C413
0x18008c478  mov     ecx, esi
0x18008c47a  call    ReleaseObjReadLock
0x18008c47f  mov     ecx, esi
0x18008c481  call    AcquireObjWriteLock
0x18008c486  mov     ebx, eax
0x18008c488  test    eax, eax
0x18008c48a  jz      short loc_18008C4C8
0x18008c48c  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008c493  jz      short loc_18008C4AE
0x18008c495  cmp     qword ptr cs:xmmword_1800D0BE0, r13
0x18008c49c  jz      loc_18008C53D
0x18008c4a2  lea     rdx, aRaslinecloseca_8; "RasLineCloseCall: AcquireObjWriteLock f"...
0x18008c4a9  jmp     loc_18008C3C7
0x18008c4ae  mov     ecx, cs:dwTraceId
0x18008c4b4  cmp     ecx, edi
0x18008c4b6  jz      loc_18008C53D
0x18008c4bc  lea     rdx, aRaslinecloseca_1; "RasLineCloseCall: AcquireObjWriteLock f"...
0x18008c4c3  jmp     loc_18008C413
0x18008c4c8  mov     edx, [r14+4]
0x18008c4cc  lea     r9, [rsp+870h+lpMem]
0x18008c4d1  mov     r8d, 18h
0x18008c4d7  mov     ecx, 7030109h
0x18008c4dc  call    PrepareAsyncRequest
0x18008c4e1  mov     ebx, eax
0x18008c4e3  mov     ecx, esi
0x18008c4e5  test    eax, eax
0x18008c4e7  jz      short loc_18008C4F0
0x18008c4e9  call    ReleaseObjWriteLock
0x18008c4ee  jmp     short loc_18008C53D
0x18008c4f0  mov     rdi, [rsp+870h+lpMem]
0x18008c4f5  mov     rax, [rsp+870h+var_840]
0x18008c4fa  mov     [rdi+0A0h], rax
0x18008c501  mov     dword ptr [r14+44h], 1
0x18008c509  mov     [rdi+0A8h], r13d
0x18008c510  call    ReleaseObjWriteLock
0x18008c515  cmp     cs:g_fUseReqId, r13d
0x18008c51c  jz      short loc_18008C529
0x18008c51e  mov     eax, [rdi+98h]
0x18008c524  mov     [r15], eax
0x18008c527  jmp     short loc_18008C530
0x18008c529  mov     [rdi+98h], r12d
0x18008c530  mov     rdx, rdi; lpMem
0x18008c533  mov     ecx, 8FFF23CCh; dwIoControlCode
0x18008c538  call    AsyncDriverRequest
0x18008c53d  mov     eax, ebx
0x18008c53f  mov     rcx, [rbp+770h+var_30]
0x18008c546  xor     rcx, rsp; StackCookie
0x18008c549  call    __security_check_cookie
0x18008c54e  lea     r11, [rsp+870h+var_20]
0x18008c556  mov     rbx, [r11+38h]
0x18008c55a  mov     rsi, [r11+40h]
0x18008c55e  mov     rdi, [r11+48h]
0x18008c562  mov     rsp, r11
0x18008c565  pop     r15
0x18008c567  pop     r14
0x18008c569  pop     r13
0x18008c56b  pop     r12
0x18008c56d  pop     rbp
0x18008c56e  retn
```
