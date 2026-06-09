# RasLineAnswer

- ea: `0x18008b828`
- end: `0x18008ba52`
- name: `RasLineAnswer`
- size: `554`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800283c0`

## callees

- `0x1800755b8`
- `0x180088d74`
- `0x18008a694`
- `0x18008b828`
- `0x18008ed64`
- `0x18008f82c`
- `0x180090714`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x18008b8d3`
- `rtutils!TracePrintfA` at `0x18008b967`
- `rtutils!TracePrintfA` at `0x18008b8d3`
- `rtutils!TracePrintfA` at `0x18008b967`

## string_xrefs

- `0x18008b910`: `RasLineAnswer: GetCallObjWithReadLock failed with error (0x%x)`
- `0x18008b95d`: `RasLineAnswer: GetCallObjWithReadLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineAnswer(unsigned int a1, __int64 a2, __int64 a3, int a4, _DWORD *a5)
{
  unsigned int NDProxyHandle; // eax
  unsigned int *v8; // rdi
  unsigned int v9; // ebx
  const wchar_t *v10; // rdx
  bool v11; // zf
  char *v12; // rdx
  unsigned int *v14; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v16; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+40h] [rbp-C0h] BYREF
  char v18[2044]; // [rsp+44h] [rbp-BCh] BYREF

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
        L"RasLineAnswer...");
  }
  else if ( dwTraceId != -1 )
  {
    TracePrintfA(dwTraceId, "RasLineAnswer...");
  }
  *a5 = 0;
  NDProxyHandle = GetCallObjWithReadLock(a1, &v14);
  v8 = v14;
  v9 = NDProxyHandle;
  if ( NDProxyHandle )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( !(_QWORD)xmmword_1800D0BE0 )
        goto LABEL_25;
      v10 = L"RasLineAnswer: GetCallObjWithReadLock failed with error (0x%x)";
      goto LABEL_10;
    }
    if ( dwTraceId != -1 )
      TracePrintfA(dwTraceId, "RasLineAnswer: GetCallObjWithReadLock failed with error (0x%x)", NDProxyHandle);
  }
  else
  {
    NDProxyHandle = GetNDProxyHandle((__int64)v14, &v16);
    v9 = NDProxyHandle;
    if ( NDProxyHandle )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( (_QWORD)xmmword_1800D0BE0 )
        {
          v10 = L"RasLineAnswer: GetNDProxyHandle failed with error (0x%x)";
LABEL_10:
          LOWORD(v17) = 0;
          FormatRRASErrorString(&v17, v10, NDProxyHandle);
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v17);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "RasLineAnswer: GetNDProxyHandle failed with error (0x%x)", NDProxyHandle);
      }
    }
    else
    {
      v9 = PrepareAsyncRequest(117637378, v8[1], 24, &lpMem);
      if ( !v9 )
      {
        v11 = g_fUseReqId == 0;
        v12 = (char *)lpMem;
        *((_QWORD *)lpMem + 20) = v16;
        *((_DWORD *)v12 + 42) = 0;
        if ( v11 )
          *((_DWORD *)v12 + 38) = a4;
        else
          *a5 = *((_DWORD *)v12 + 38);
        AsyncDriverRequest(0x8FFF23CC, v12);
      }
    }
  }
LABEL_25:
  if ( v8 )
    ReleaseObjReadLock(a1);
  return v9;
}

```

## disassembly

```asm
0x18008b828  mov     [rsp-8+arg_8], rbx
0x18008b82d  mov     [rsp-8+arg_10], rsi
0x18008b832  push    rbp
0x18008b833  push    rdi
0x18008b834  push    r12
0x18008b836  push    r14
0x18008b838  push    r15
0x18008b83a  lea     rbp, [rsp-750h]
0x18008b842  sub     rsp, 850h
0x18008b849  mov     rax, cs:__security_cookie
0x18008b850  xor     rax, rsp
0x18008b853  mov     [rbp+770h+var_30], rax
0x18008b85a  mov     rsi, [rbp+770h+arg_20]
0x18008b861  xor     r12d, r12d
0x18008b864  mov     r14d, ecx
0x18008b867  mov     [rsp+870h+lpMem], r12
0x18008b86c  lea     rcx, [rsp+870h+var_82C]; void *
0x18008b871  mov     [rsp+870h+var_850], r12
0x18008b876  xor     edx, edx; Val
0x18008b878  mov     [rsp+870h+var_840], r12
0x18008b87d  mov     r8d, 7FCh; Size
0x18008b883  mov     [rsp+870h+var_830], r12d
0x18008b888  mov     r15, r9
0x18008b88b  call    memset_0
0x18008b890  cmp     cs:gIsndpspEtwTracingAvailable, r12d
0x18008b897  jz      short loc_18008B8C1
0x18008b899  mov     rdx, qword ptr cs:xmmword_1800D0BE0+8
0x18008b8a0  test    rdx, rdx
0x18008b8a3  jz      short loc_18008B8DF
0x18008b8a5  mov     rcx, cs:gNdpspEtwContext
0x18008b8ac  lea     r8, aRaslineanswer_0; "RasLineAnswer..."
0x18008b8b3  mov     rax, cs:gNdpspTemplateFunc
0x18008b8ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b8bf  jmp     short loc_18008B8DF
0x18008b8c1  mov     ecx, cs:dwTraceId; dwTraceID
0x18008b8c7  cmp     ecx, 0FFFFFFFFh
0x18008b8ca  jz      short loc_18008B8DF
0x18008b8cc  lea     rdx, aRaslineanswer; "RasLineAnswer..."
0x18008b8d3  call    cs:__imp_TracePrintfA
0x18008b8da  nop     dword ptr [rax+rax+00h]
0x18008b8df  lea     rdx, [rsp+870h+var_850]
0x18008b8e4  mov     [rsi], r12d
0x18008b8e7  mov     ecx, r14d
0x18008b8ea  call    GetCallObjWithReadLock
0x18008b8ef  mov     rdi, [rsp+870h+var_850]
0x18008b8f4  mov     ebx, eax
0x18008b8f6  test    eax, eax
0x18008b8f8  jz      short loc_18008B978
0x18008b8fa  cmp     cs:gIsndpspEtwTracingAvailable, r12d
0x18008b901  jz      short loc_18008B94E
0x18008b903  cmp     qword ptr cs:xmmword_1800D0BE0, r12
0x18008b90a  jz      loc_18008BA17
0x18008b910  lea     rdx, aRaslineanswerG_0; "RasLineAnswer: GetCallObjWithReadLock f"...
0x18008b917  mov     r8d, eax
0x18008b91a  mov     word ptr [rsp+870h+var_830], r12w
0x18008b920  lea     rcx, [rsp+870h+var_830]
0x18008b925  call    FormatRRASErrorString
0x18008b92a  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008b931  lea     r8, [rsp+870h+var_830]
0x18008b936  mov     rcx, cs:gNdpspEtwContext
0x18008b93d  mov     rax, cs:gNdpspTemplateFunc
0x18008b944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b949  jmp     loc_18008BA17
0x18008b94e  mov     ecx, cs:dwTraceId; dwTraceID
0x18008b954  cmp     ecx, 0FFFFFFFFh
0x18008b957  jz      loc_18008BA17
0x18008b95d  lea     rdx, aRaslineanswerG_2; "RasLineAnswer: GetCallObjWithReadLock f"...
0x18008b964  mov     r8d, eax
0x18008b967  call    cs:__imp_TracePrintfA
0x18008b96e  nop     dword ptr [rax+rax+00h]
0x18008b973  jmp     loc_18008BA17
0x18008b978  lea     rdx, [rsp+870h+var_840]
0x18008b97d  mov     rcx, rdi
0x18008b980  call    GetNDProxyHandle
0x18008b985  mov     ebx, eax
0x18008b987  test    eax, eax
0x18008b989  jz      short loc_18008B9BD
0x18008b98b  cmp     cs:gIsndpspEtwTracingAvailable, r12d
0x18008b992  jz      short loc_18008B9A9
0x18008b994  cmp     qword ptr cs:xmmword_1800D0BE0, r12
0x18008b99b  jz      short loc_18008BA17
0x18008b99d  lea     rdx, aRaslineanswerG; "RasLineAnswer: GetNDProxyHandle failed "...
0x18008b9a4  jmp     loc_18008B917
0x18008b9a9  mov     ecx, cs:dwTraceId
0x18008b9af  cmp     ecx, 0FFFFFFFFh
0x18008b9b2  jz      short loc_18008BA17
0x18008b9b4  lea     rdx, aRaslineanswerG_1; "RasLineAnswer: GetNDProxyHandle failed "...
0x18008b9bb  jmp     short loc_18008B964
0x18008b9bd  mov     edx, [rdi+4]
0x18008b9c0  lea     r9, [rsp+870h+lpMem]
0x18008b9c5  mov     r8d, 18h
0x18008b9cb  mov     ecx, 7030102h
0x18008b9d0  call    PrepareAsyncRequest
0x18008b9d5  mov     ebx, eax
0x18008b9d7  test    eax, eax
0x18008b9d9  jnz     short loc_18008BA17
0x18008b9db  cmp     cs:g_fUseReqId, r12d
0x18008b9e2  mov     rdx, [rsp+870h+lpMem]; lpMem
0x18008b9e7  mov     rax, [rsp+870h+var_840]
0x18008b9ec  mov     [rdx+0A0h], rax
0x18008b9f3  mov     [rdx+0A8h], r12d
0x18008b9fa  jz      short loc_18008BA06
0x18008b9fc  mov     eax, [rdx+98h]
0x18008ba02  mov     [rsi], eax
0x18008ba04  jmp     short loc_18008BA0D
0x18008ba06  mov     [rdx+98h], r15d
0x18008ba0d  mov     ecx, 8FFF23CCh; dwIoControlCode
0x18008ba12  call    AsyncDriverRequest
0x18008ba17  test    rdi, rdi
0x18008ba1a  jz      short loc_18008BA24
0x18008ba1c  mov     ecx, r14d
0x18008ba1f  call    ReleaseObjReadLock
0x18008ba24  mov     eax, ebx
0x18008ba26  mov     rcx, [rbp+770h+var_30]
0x18008ba2d  xor     rcx, rsp; StackCookie
0x18008ba30  call    __security_check_cookie
0x18008ba35  lea     r11, [rsp+870h+var_20]
0x18008ba3d  mov     rbx, [r11+38h]
0x18008ba41  mov     rsi, [r11+40h]
0x18008ba45  mov     rsp, r11
0x18008ba48  pop     r15
0x18008ba4a  pop     r14
0x18008ba4c  pop     r12
0x18008ba4e  pop     rdi
0x18008ba4f  pop     rbp
0x18008ba50  retn
```
