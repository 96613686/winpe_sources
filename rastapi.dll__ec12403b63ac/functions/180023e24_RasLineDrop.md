# RasLineDrop

- ea: `0x180023e24`
- end: `0x1800240a2`
- name: `RasLineDrop`
- size: `638`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x1800023d4`
- `0x180012b00`

## callees

- `0x180020c98`
- `0x180022314`
- `0x180023e24`
- `0x180027270`
- `0x180027d38`
- `0x180028078`
- `0x180028b5c`
- `0x180028c70`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x180023ecd`
- `rtutils!TracePrintfA` at `0x180023f54`
- `rtutils!TracePrintfA` at `0x180023ecd`
- `rtutils!TracePrintfA` at `0x180023f54`

## string_xrefs

- `0x180023fda`: `RasLineCloseCall: AcquireObjWriteLock failed with error (0x%x)`
- `0x180023ff4`: `RasLineCloseCall: AcquireObjWriteLock failed with error (0x%x)`
- `0x180023efe`: `RasLineDrop: GetCallObjWithReadLock failed with error (0x%x)`
- `0x180023f4a`: `RasLineDrop: GetCallObjWithReadLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineDrop(unsigned int a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  unsigned int NDProxyHandle; // eax
  unsigned int v7; // ebx
  const wchar_t *v8; // rdx
  unsigned int *v9; // r14
  char *v10; // rdi
  unsigned int *v12; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v14; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  char v16[2044]; // [rsp+44h] [rbp-BCh] BYREF

  lpMem = 0;
  v12 = 0;
  v14 = 0;
  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( qword_18003EC48 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(
        gNdpspEtwContext,
        qword_18003EC48,
        L"RasLineDrop...");
  }
  else if ( dwTraceId != -1 )
  {
    TracePrintfA(dwTraceId, "RasLineDrop...");
  }
  *a5 = 0;
  NDProxyHandle = GetCallObjWithReadLock(a1, &v12);
  v7 = NDProxyHandle;
  if ( NDProxyHandle )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( qword_18003EC40 )
      {
        v8 = L"RasLineDrop: GetCallObjWithReadLock failed with error (0x%x)";
LABEL_10:
        LOWORD(v15) = 0;
        FormatRRASErrorString(&v15, v8, NDProxyHandle);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v15);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "RasLineDrop: GetCallObjWithReadLock failed with error (0x%x)", NDProxyHandle);
    }
  }
  else
  {
    v9 = v12;
    NDProxyHandle = GetNDProxyHandle(v12, &v14);
    v7 = NDProxyHandle;
    if ( NDProxyHandle )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( !qword_18003EC40 )
          return v7;
        v8 = L"RasLineDrop: GetNDProxyHandle failed with error (0x%x)";
        goto LABEL_10;
      }
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineDrop: GetNDProxyHandle failed with error (0x%x)", NDProxyHandle);
    }
    else
    {
      ReleaseObjReadLock(a1);
      NDProxyHandle = AcquireObjWriteLock(a1);
      v7 = NDProxyHandle;
      if ( NDProxyHandle )
      {
        if ( gIsndpspEtwTracingAvailable )
        {
          if ( !qword_18003EC40 )
            return v7;
          v8 = L"RasLineCloseCall: AcquireObjWriteLock failed with error (0x%x)";
          goto LABEL_10;
        }
        if ( dwTraceId != -1 )
          TracePrintfA(dwTraceId, "RasLineCloseCall: AcquireObjWriteLock failed with error (0x%x)", NDProxyHandle);
      }
      else
      {
        v7 = PrepareAsyncRequest(0x7030109u, v9[1], 0x18u, &lpMem);
        if ( v7 )
        {
          ReleaseObjWriteLock(a1);
        }
        else
        {
          v10 = (char *)lpMem;
          *((_QWORD *)lpMem + 20) = v14;
          v9[17] = 1;
          *((_DWORD *)v10 + 42) = 0;
          ReleaseObjWriteLock(a1);
          if ( g_fUseReqId )
            *a5 = *((_DWORD *)v10 + 38);
          else
            *((_DWORD *)v10 + 38) = 0;
          AsyncDriverRequest(0x8FFF23CC, v10);
        }
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180023e24  mov     [rsp-8+arg_8], rbx
0x180023e29  mov     [rsp-8+arg_10], rsi
0x180023e2e  push    rbp
0x180023e2f  push    rdi
0x180023e30  push    r12
0x180023e32  push    r14
0x180023e34  push    r15
0x180023e36  lea     rbp, [rsp-750h]
0x180023e3e  sub     rsp, 850h
0x180023e45  mov     rax, cs:__security_cookie
0x180023e4c  xor     rax, rsp
0x180023e4f  mov     [rbp+770h+var_30], rax
0x180023e56  mov     r15, [rbp+770h+arg_20]
0x180023e5d  xor     r12d, r12d
0x180023e60  mov     esi, ecx
0x180023e62  mov     [rsp+870h+lpMem], r12
0x180023e67  lea     rcx, [rsp+870h+var_82C]; void *
0x180023e6c  mov     [rsp+870h+var_850], r12
0x180023e71  xor     edx, edx; Val
0x180023e73  mov     [rsp+870h+var_840], r12
0x180023e78  mov     r8d, 7FCh; Size
0x180023e7e  mov     [rsp+870h+var_830], r12d
0x180023e83  call    memset_0
0x180023e88  or      edi, 0FFFFFFFFh
0x180023e8b  cmp     cs:gIsndpspEtwTracingAvailable, r12d
0x180023e92  jz      short loc_180023EBC
0x180023e94  mov     rdx, cs:qword_18003EC48
0x180023e9b  test    rdx, rdx
0x180023e9e  jz      short loc_180023ED3
0x180023ea0  mov     rcx, cs:gNdpspEtwContext
0x180023ea7  lea     r8, aRaslinedrop; "RasLineDrop..."
0x180023eae  mov     rax, cs:gNdpspTemplateFunc
0x180023eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023eba  jmp     short loc_180023ED3
0x180023ebc  mov     ecx, cs:dwTraceId; dwTraceID
0x180023ec2  cmp     ecx, edi
0x180023ec4  jz      short loc_180023ED3
0x180023ec6  lea     rdx, aRaslinedrop_0; "RasLineDrop..."
0x180023ecd  call    cs:__imp_TracePrintfA
0x180023ed3  lea     rdx, [rsp+870h+var_850]
0x180023ed8  mov     [r15], r12d
0x180023edb  mov     ecx, esi
0x180023edd  call    GetCallObjWithReadLock
0x180023ee2  mov     ebx, eax
0x180023ee4  test    eax, eax
0x180023ee6  jz      short loc_180023F5F
0x180023ee8  cmp     cs:gIsndpspEtwTracingAvailable, r12d
0x180023eef  jz      short loc_180023F3C
0x180023ef1  cmp     cs:qword_18003EC40, r12
0x180023ef8  jz      loc_180024075
0x180023efe  lea     rdx, aRaslinedropGet_0; "RasLineDrop: GetCallObjWithReadLock fai"...
0x180023f05  mov     r8d, eax
0x180023f08  mov     word ptr [rsp+870h+var_830], r12w
0x180023f0e  lea     rcx, [rsp+870h+var_830]
0x180023f13  call    FormatRRASErrorString
0x180023f18  mov     rdx, cs:qword_18003EC40
0x180023f1f  lea     r8, [rsp+870h+var_830]
0x180023f24  mov     rcx, cs:gNdpspEtwContext
0x180023f2b  mov     rax, cs:gNdpspTemplateFunc
0x180023f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f37  jmp     loc_180024075
0x180023f3c  mov     ecx, cs:dwTraceId; dwTraceID
0x180023f42  cmp     ecx, edi
0x180023f44  jz      loc_180024075
0x180023f4a  lea     rdx, aRaslinedropGet_1; "RasLineDrop: GetCallObjWithReadLock fai"...
0x180023f51  mov     r8d, eax
0x180023f54  call    cs:__imp_TracePrintfA
0x180023f5a  jmp     loc_180024075
0x180023f5f  mov     r14, [rsp+870h+var_850]
0x180023f64  lea     rdx, [rsp+870h+var_840]
0x180023f69  mov     rcx, r14
0x180023f6c  call    GetNDProxyHandle
0x180023f71  mov     ebx, eax
0x180023f73  test    eax, eax
0x180023f75  jz      short loc_180023FB0
0x180023f77  cmp     cs:gIsndpspEtwTracingAvailable, r12d
0x180023f7e  jz      short loc_180023F99
0x180023f80  cmp     cs:qword_18003EC40, r12
0x180023f87  jz      loc_180024075
0x180023f8d  lea     rdx, aRaslinedropGet; "RasLineDrop: GetNDProxyHandle failed wi"...
0x180023f94  jmp     loc_180023F05
0x180023f99  mov     ecx, cs:dwTraceId
0x180023f9f  cmp     ecx, edi
0x180023fa1  jz      loc_180024075
0x180023fa7  lea     rdx, aRaslinedropGet_2; "RasLineDrop: GetNDProxyHandle failed wi"...
0x180023fae  jmp     short loc_180023F51
0x180023fb0  mov     ecx, esi
0x180023fb2  call    ReleaseObjReadLock
0x180023fb7  mov     ecx, esi
0x180023fb9  call    AcquireObjWriteLock
0x180023fbe  mov     ebx, eax
0x180023fc0  test    eax, eax
0x180023fc2  jz      short loc_180024000
0x180023fc4  cmp     cs:gIsndpspEtwTracingAvailable, r12d
0x180023fcb  jz      short loc_180023FE6
0x180023fcd  cmp     cs:qword_18003EC40, r12
0x180023fd4  jz      loc_180024075
0x180023fda  lea     rdx, aRaslinecloseca_8; "RasLineCloseCall: AcquireObjWriteLock f"...
0x180023fe1  jmp     loc_180023F05
0x180023fe6  mov     ecx, cs:dwTraceId
0x180023fec  cmp     ecx, edi
0x180023fee  jz      loc_180024075
0x180023ff4  lea     rdx, aRaslinecloseca_1; "RasLineCloseCall: AcquireObjWriteLock f"...
0x180023ffb  jmp     loc_180023F51
0x180024000  mov     edx, [r14+4]
0x180024004  lea     r9, [rsp+870h+lpMem]
0x180024009  mov     r8d, 18h
0x18002400f  mov     ecx, 7030109h
0x180024014  call    PrepareAsyncRequest
0x180024019  mov     ebx, eax
0x18002401b  mov     ecx, esi
0x18002401d  test    eax, eax
0x18002401f  jz      short loc_180024028
0x180024021  call    ReleaseObjWriteLock
0x180024026  jmp     short loc_180024075
0x180024028  mov     rdi, [rsp+870h+lpMem]
0x18002402d  mov     rax, [rsp+870h+var_840]
0x180024032  mov     [rdi+0A0h], rax
0x180024039  mov     dword ptr [r14+44h], 1
0x180024041  mov     [rdi+0A8h], r12d
0x180024048  call    ReleaseObjWriteLock
0x18002404d  cmp     cs:g_fUseReqId, r12d
0x180024054  jz      short loc_180024061
0x180024056  mov     eax, [rdi+98h]
0x18002405c  mov     [r15], eax
0x18002405f  jmp     short loc_180024068
0x180024061  mov     [rdi+98h], r12d
0x180024068  mov     rdx, rdi; lpMem
0x18002406b  mov     ecx, 8FFF23CCh; dwIoControlCode
0x180024070  call    AsyncDriverRequest
0x180024075  mov     eax, ebx
0x180024077  mov     rcx, [rbp+770h+var_30]
0x18002407e  xor     rcx, rsp; StackCookie
0x180024081  call    __security_check_cookie
0x180024086  lea     r11, [rsp+870h+var_20]
0x18002408e  mov     rbx, [r11+38h]
0x180024092  mov     rsi, [r11+40h]
0x180024096  mov     rsp, r11
0x180024099  pop     r15
0x18002409b  pop     r14
0x18002409d  pop     r12
0x18002409f  pop     rdi
0x1800240a0  pop     rbp
0x1800240a1  retn
```
