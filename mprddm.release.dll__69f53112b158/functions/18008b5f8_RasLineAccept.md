# RasLineAccept

- ea: `0x18008b5f8`
- end: `0x18008b822`
- name: `RasLineAccept`
- size: `554`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800281a0`

## callees

- `0x1800755b8`
- `0x180088d74`
- `0x18008a694`
- `0x18008b5f8`
- `0x18008ed64`
- `0x18008f82c`
- `0x180090714`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `rtutils!TracePrintfA` at `0x18008b6a3`
- `rtutils!TracePrintfA` at `0x18008b737`
- `rtutils!TracePrintfA` at `0x18008b6a3`
- `rtutils!TracePrintfA` at `0x18008b737`

## string_xrefs

- `0x18008b6e0`: `RasLineAnswer: GetCallObjWithReadLock failed with error (0x%x)`
- `0x18008b72d`: `RasLineAnswer: GetCallObjWithReadLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineAccept(unsigned int a1, __int64 a2, __int64 a3, int a4, _DWORD *a5)
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
      v9 = PrepareAsyncRequest(117637377, v8[1], 24, &lpMem);
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
0x18008b5f8  mov     [rsp-8+arg_8], rbx
0x18008b5fd  mov     [rsp-8+arg_10], rsi
0x18008b602  push    rbp
0x18008b603  push    rdi
0x18008b604  push    r12
0x18008b606  push    r14
0x18008b608  push    r15
0x18008b60a  lea     rbp, [rsp-750h]
0x18008b612  sub     rsp, 850h
0x18008b619  mov     rax, cs:__security_cookie
0x18008b620  xor     rax, rsp
0x18008b623  mov     [rbp+770h+var_30], rax
0x18008b62a  mov     rsi, [rbp+770h+arg_20]
0x18008b631  xor     r12d, r12d
0x18008b634  mov     r14d, ecx
0x18008b637  mov     [rsp+870h+lpMem], r12
0x18008b63c  lea     rcx, [rsp+870h+var_82C]; void *
0x18008b641  mov     [rsp+870h+var_850], r12
0x18008b646  xor     edx, edx; Val
0x18008b648  mov     [rsp+870h+var_840], r12
0x18008b64d  mov     r8d, 7FCh; Size
0x18008b653  mov     [rsp+870h+var_830], r12d
0x18008b658  mov     r15, r9
0x18008b65b  call    memset_0
0x18008b660  cmp     cs:gIsndpspEtwTracingAvailable, r12d
0x18008b667  jz      short loc_18008B691
0x18008b669  mov     rdx, qword ptr cs:xmmword_1800D0BE0+8
0x18008b670  test    rdx, rdx
0x18008b673  jz      short loc_18008B6AF
0x18008b675  mov     rcx, cs:gNdpspEtwContext
0x18008b67c  lea     r8, aRaslineanswer_0; "RasLineAnswer..."
0x18008b683  mov     rax, cs:gNdpspTemplateFunc
0x18008b68a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b68f  jmp     short loc_18008B6AF
0x18008b691  mov     ecx, cs:dwTraceId; dwTraceID
0x18008b697  cmp     ecx, 0FFFFFFFFh
0x18008b69a  jz      short loc_18008B6AF
0x18008b69c  lea     rdx, aRaslineanswer; "RasLineAnswer..."
0x18008b6a3  call    cs:__imp_TracePrintfA
0x18008b6aa  nop     dword ptr [rax+rax+00h]
0x18008b6af  lea     rdx, [rsp+870h+var_850]
0x18008b6b4  mov     [rsi], r12d
0x18008b6b7  mov     ecx, r14d
0x18008b6ba  call    GetCallObjWithReadLock
0x18008b6bf  mov     rdi, [rsp+870h+var_850]
0x18008b6c4  mov     ebx, eax
0x18008b6c6  test    eax, eax
0x18008b6c8  jz      short loc_18008B748
0x18008b6ca  cmp     cs:gIsndpspEtwTracingAvailable, r12d
0x18008b6d1  jz      short loc_18008B71E
0x18008b6d3  cmp     qword ptr cs:xmmword_1800D0BE0, r12
0x18008b6da  jz      loc_18008B7E7
0x18008b6e0  lea     rdx, aRaslineanswerG_0; "RasLineAnswer: GetCallObjWithReadLock f"...
0x18008b6e7  mov     r8d, eax
0x18008b6ea  mov     word ptr [rsp+870h+var_830], r12w
0x18008b6f0  lea     rcx, [rsp+870h+var_830]
0x18008b6f5  call    FormatRRASErrorString
0x18008b6fa  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008b701  lea     r8, [rsp+870h+var_830]
0x18008b706  mov     rcx, cs:gNdpspEtwContext
0x18008b70d  mov     rax, cs:gNdpspTemplateFunc
0x18008b714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b719  jmp     loc_18008B7E7
0x18008b71e  mov     ecx, cs:dwTraceId; dwTraceID
0x18008b724  cmp     ecx, 0FFFFFFFFh
0x18008b727  jz      loc_18008B7E7
0x18008b72d  lea     rdx, aRaslineanswerG_2; "RasLineAnswer: GetCallObjWithReadLock f"...
0x18008b734  mov     r8d, eax
0x18008b737  call    cs:__imp_TracePrintfA
0x18008b73e  nop     dword ptr [rax+rax+00h]
0x18008b743  jmp     loc_18008B7E7
0x18008b748  lea     rdx, [rsp+870h+var_840]
0x18008b74d  mov     rcx, rdi
0x18008b750  call    GetNDProxyHandle
0x18008b755  mov     ebx, eax
0x18008b757  test    eax, eax
0x18008b759  jz      short loc_18008B78D
0x18008b75b  cmp     cs:gIsndpspEtwTracingAvailable, r12d
0x18008b762  jz      short loc_18008B779
0x18008b764  cmp     qword ptr cs:xmmword_1800D0BE0, r12
0x18008b76b  jz      short loc_18008B7E7
0x18008b76d  lea     rdx, aRaslineanswerG; "RasLineAnswer: GetNDProxyHandle failed "...
0x18008b774  jmp     loc_18008B6E7
0x18008b779  mov     ecx, cs:dwTraceId
0x18008b77f  cmp     ecx, 0FFFFFFFFh
0x18008b782  jz      short loc_18008B7E7
0x18008b784  lea     rdx, aRaslineanswerG_1; "RasLineAnswer: GetNDProxyHandle failed "...
0x18008b78b  jmp     short loc_18008B734
0x18008b78d  mov     edx, [rdi+4]
0x18008b790  lea     r9, [rsp+870h+lpMem]
0x18008b795  mov     r8d, 18h
0x18008b79b  mov     ecx, 7030101h
0x18008b7a0  call    PrepareAsyncRequest
0x18008b7a5  mov     ebx, eax
0x18008b7a7  test    eax, eax
0x18008b7a9  jnz     short loc_18008B7E7
0x18008b7ab  cmp     cs:g_fUseReqId, r12d
0x18008b7b2  mov     rdx, [rsp+870h+lpMem]; lpMem
0x18008b7b7  mov     rax, [rsp+870h+var_840]
0x18008b7bc  mov     [rdx+0A0h], rax
0x18008b7c3  mov     [rdx+0A8h], r12d
0x18008b7ca  jz      short loc_18008B7D6
0x18008b7cc  mov     eax, [rdx+98h]
0x18008b7d2  mov     [rsi], eax
0x18008b7d4  jmp     short loc_18008B7DD
0x18008b7d6  mov     [rdx+98h], r15d
0x18008b7dd  mov     ecx, 8FFF23CCh; dwIoControlCode
0x18008b7e2  call    AsyncDriverRequest
0x18008b7e7  test    rdi, rdi
0x18008b7ea  jz      short loc_18008B7F4
0x18008b7ec  mov     ecx, r14d
0x18008b7ef  call    ReleaseObjReadLock
0x18008b7f4  mov     eax, ebx
0x18008b7f6  mov     rcx, [rbp+770h+var_30]
0x18008b7fd  xor     rcx, rsp; StackCookie
0x18008b800  call    __security_check_cookie
0x18008b805  lea     r11, [rsp+870h+var_20]
0x18008b80d  mov     rbx, [r11+38h]
0x18008b811  mov     rsi, [r11+40h]
0x18008b815  mov     rsp, r11
0x18008b818  pop     r15
0x18008b81a  pop     r14
0x18008b81c  pop     r12
0x18008b81e  pop     rdi
0x18008b81f  pop     rbp
0x18008b820  retn
```
