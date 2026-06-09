# RasLineSetDefaultMediaDetection

- ea: `0x18008e4b0`
- end: `0x18008e6ee`
- name: `RasLineSetDefaultMediaDetection`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18008db88`

## callees

- `0x1800755b8`
- `0x18008a88c`
- `0x18008e4b0`
- `0x18008e6f4`
- `0x18008f50c`
- `0x180090714`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18008e692`
- `KERNEL32!GetProcessHeap` at `0x18008e692`
- `KERNEL32!HeapFree` at `0x18008e6a6`
- `KERNEL32!HeapFree` at `0x18008e6a6`
- `rtutils!TracePrintfA` at `0x18008e58f`
- `rtutils!TracePrintfA` at `0x18008e681`
- `rtutils!TracePrintfA` at `0x18008e58f`
- `rtutils!TracePrintfA` at `0x18008e681`

## string_xrefs

- `0x18008e541`: `RasLineSetDefaultMediaDetection: GetLineObjWithReadLock failed with error (0x%x)`
- `0x18008e588`: `RasLineSetDefaultMediaDetection: GetLineObjWithReadLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineSetDefaultMediaDetection(unsigned int a1)
{
  unsigned int LineObjWithReadLock; // eax
  unsigned int *v3; // rsi
  unsigned int v4; // ebx
  unsigned int v5; // eax
  _DWORD *v6; // rdi
  const wchar_t *v7; // rdx
  void *v8; // rdx
  HANDLE ProcessHeap; // rax
  unsigned int *v11; // [rsp+28h] [rbp-E0h] BYREF
  LPVOID lpMem; // [rsp+30h] [rbp-D8h] BYREF
  int v13; // [rsp+38h] [rbp-D0h] BYREF
  _BYTE v14[2044]; // [rsp+3Ch] [rbp-CCh] BYREF

  lpMem = 0;
  v11 = 0;
  v13 = 0;
  memset_0(v14, 0, sizeof(v14));
  LineObjWithReadLock = GetLineObjWithReadLock(a1, &v11);
  v3 = v11;
  v4 = LineObjWithReadLock;
  if ( LineObjWithReadLock )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        LOWORD(v13) = 0;
        FormatRRASErrorString(
          &v13,
          L"RasLineSetDefaultMediaDetection: GetLineObjWithReadLock failed with error (0x%x)",
          LineObjWithReadLock);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v13);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(
        dwTraceId,
        "RasLineSetDefaultMediaDetection: GetLineObjWithReadLock failed with error (0x%x)",
        LineObjWithReadLock);
    }
    goto LABEL_22;
  }
  v5 = PrepareSyncRequest(117637407, v11[1], 24, &lpMem);
  v6 = lpMem;
  v4 = v5;
  if ( v5 )
  {
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineSetDefaultMediaDetection: PrepareSyncRequest failed with error (0x%x)", v5);
      goto LABEL_20;
    }
    if ( (_QWORD)xmmword_1800D0BE0 )
    {
      v7 = L"RasLineSetDefaultMediaDetection: PrepareSyncRequest failed with error (0x%x)";
LABEL_17:
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v13, v7, v5);
      ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v13);
    }
  }
  else
  {
    v8 = lpMem;
    *((_QWORD *)lpMem + 7) = *((_QWORD *)v3 + 2);
    v6[16] = 258;
    v5 = SyncDriverRequest(0x8FFF23C8, v8);
    v4 = v5;
    if ( v5 )
    {
      if ( !gIsndpspEtwTracingAvailable )
      {
        if ( dwTraceId != -1 )
          TracePrintfA(
            dwTraceId,
            "RasLineSetDefaultMediaDetection: SyncDriverRequest(OID_TAPI_SET_DEFAULT_MEDIA_DETECTION) failed with error (0x%x)",
            v5);
        goto LABEL_20;
      }
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        v7 = L"RasLineSetDefaultMediaDetection: SyncDriverRequest(OID_TAPI_SET_DEFAULT_MEDIA_DETECTION) failed with error (0x%x)";
        goto LABEL_17;
      }
    }
  }
LABEL_20:
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
LABEL_22:
  if ( v3 )
    ReleaseObjReadLock(a1);
  return v4;
}

```

## disassembly

```asm
0x18008e4b0  mov     rax, rsp
0x18008e4b3  mov     [rax+10h], rbx
0x18008e4b7  mov     [rax+18h], rsi
0x18008e4bb  mov     [rax+20h], rdi
0x18008e4bf  push    rbp
0x18008e4c0  push    r14
0x18008e4c2  push    r15
0x18008e4c4  lea     rbp, [rax-758h]
0x18008e4cb  sub     rsp, 840h
0x18008e4d2  mov     rax, cs:__security_cookie
0x18008e4d9  xor     rax, rsp
0x18008e4dc  mov     [rbp+750h+var_20], rax
0x18008e4e3  xor     r15d, r15d
0x18008e4e6  mov     r14d, ecx
0x18008e4e9  lea     rcx, [rsp+850h+var_81C]; void *
0x18008e4ee  mov     [rsp+850h+lpMem], r15
0x18008e4f3  xor     edx, edx; Val
0x18008e4f5  mov     [rsp+850h+var_830], r15
0x18008e4fa  mov     r8d, 7FCh; Size
0x18008e500  mov     [rsp+850h+var_820], r15d
0x18008e505  call    memset_0
0x18008e50a  lea     rdx, [rsp+850h+var_830]
0x18008e50f  mov     ecx, r14d
0x18008e512  call    GetLineObjWithReadLock
0x18008e517  mov     rsi, [rsp+850h+var_830]
0x18008e51c  mov     ebx, eax
0x18008e51e  test    eax, eax
0x18008e520  jz      short loc_18008E5A0
0x18008e522  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x18008e529  jz      short loc_18008E576
0x18008e52b  cmp     qword ptr cs:xmmword_1800D0BE0, r15
0x18008e532  jz      loc_18008E6B2
0x18008e538  mov     r8d, eax
0x18008e53b  mov     word ptr [rsp+850h+var_820], r15w
0x18008e541  lea     rdx, aRaslinesetdefa_1; "RasLineSetDefaultMediaDetection: GetLin"...
0x18008e548  lea     rcx, [rsp+850h+var_820]
0x18008e54d  call    FormatRRASErrorString
0x18008e552  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008e559  lea     r8, [rsp+850h+var_820]
0x18008e55e  mov     rcx, cs:gNdpspEtwContext
0x18008e565  mov     rax, cs:gNdpspTemplateFunc
0x18008e56c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e571  jmp     loc_18008E6B2
0x18008e576  mov     ecx, cs:dwTraceId; dwTraceID
0x18008e57c  cmp     ecx, 0FFFFFFFFh
0x18008e57f  jz      loc_18008E6B2
0x18008e585  mov     r8d, eax
0x18008e588  lea     rdx, aRaslinesetdefa_3; "RasLineSetDefaultMediaDetection: GetLin"...
0x18008e58f  call    cs:__imp_TracePrintfA
0x18008e596  nop     dword ptr [rax+rax+00h]
0x18008e59b  jmp     loc_18008E6B2
0x18008e5a0  mov     edx, [rsi+4]
0x18008e5a3  lea     r9, [rsp+850h+lpMem]
0x18008e5a8  mov     r8d, 18h
0x18008e5ae  mov     ecx, 703011Fh
0x18008e5b3  call    PrepareSyncRequest
0x18008e5b8  mov     rdi, [rsp+850h+lpMem]
0x18008e5bd  mov     ebx, eax
0x18008e5bf  test    eax, eax
0x18008e5c1  jz      short loc_18008E5FD
0x18008e5c3  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x18008e5ca  jz      short loc_18008E5E2
0x18008e5cc  cmp     qword ptr cs:xmmword_1800D0BE0, r15
0x18008e5d3  jz      loc_18008E68D
0x18008e5d9  lea     rdx, aRaslinesetdefa_4; "RasLineSetDefaultMediaDetection: Prepar"...
0x18008e5e0  jmp     short loc_18008E638
0x18008e5e2  mov     ecx, cs:dwTraceId
0x18008e5e8  cmp     ecx, 0FFFFFFFFh
0x18008e5eb  jz      loc_18008E68D
0x18008e5f1  lea     rdx, aRaslinesetdefa_2; "RasLineSetDefaultMediaDetection: Prepar"...
0x18008e5f8  jmp     loc_18008E67E
0x18008e5fd  mov     rax, [rsi+10h]
0x18008e601  mov     rdx, rdi; lpInBuffer
0x18008e604  mov     ecx, 8FFF23C8h; dwIoControlCode
0x18008e609  mov     [rdi+38h], rax
0x18008e60d  mov     dword ptr [rdi+40h], 102h
0x18008e614  call    SyncDriverRequest
0x18008e619  mov     ebx, eax
0x18008e61b  test    eax, eax
0x18008e61d  jz      short loc_18008E68D
0x18008e61f  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x18008e626  jz      short loc_18008E66C
0x18008e628  cmp     qword ptr cs:xmmword_1800D0BE0, r15
0x18008e62f  jz      short loc_18008E68D
0x18008e631  lea     rdx, aRaslinesetdefa_0; "RasLineSetDefaultMediaDetection: SyncDr"...
0x18008e638  mov     r8d, eax
0x18008e63b  mov     word ptr [rsp+850h+var_820], r15w
0x18008e641  lea     rcx, [rsp+850h+var_820]
0x18008e646  call    FormatRRASErrorString
0x18008e64b  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008e652  lea     r8, [rsp+850h+var_820]
0x18008e657  mov     rcx, cs:gNdpspEtwContext
0x18008e65e  mov     rax, cs:gNdpspTemplateFunc
0x18008e665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e66a  jmp     short loc_18008E68D
0x18008e66c  mov     ecx, cs:dwTraceId; dwTraceID
0x18008e672  cmp     ecx, 0FFFFFFFFh
0x18008e675  jz      short loc_18008E68D
0x18008e677  lea     rdx, aRaslinesetdefa; "RasLineSetDefaultMediaDetection: SyncDr"...
0x18008e67e  mov     r8d, eax
0x18008e681  call    cs:__imp_TracePrintfA
0x18008e688  nop     dword ptr [rax+rax+00h]
0x18008e68d  test    rdi, rdi
0x18008e690  jz      short loc_18008E6B2
0x18008e692  call    cs:__imp_GetProcessHeap
0x18008e699  nop     dword ptr [rax+rax+00h]
0x18008e69e  mov     r8, rdi; lpMem
0x18008e6a1  xor     edx, edx; dwFlags
0x18008e6a3  mov     rcx, rax; hHeap
0x18008e6a6  call    cs:__imp_HeapFree
0x18008e6ad  nop     dword ptr [rax+rax+00h]
0x18008e6b2  test    rsi, rsi
0x18008e6b5  jz      short loc_18008E6BF
0x18008e6b7  mov     ecx, r14d
0x18008e6ba  call    ReleaseObjReadLock
0x18008e6bf  mov     eax, ebx
0x18008e6c1  mov     rcx, [rbp+750h+var_20]
0x18008e6c8  xor     rcx, rsp; StackCookie
0x18008e6cb  call    __security_check_cookie
0x18008e6d0  lea     r11, [rsp+850h+var_10]
0x18008e6d8  mov     rbx, [r11+28h]
0x18008e6dc  mov     rsi, [r11+30h]
0x18008e6e0  mov     rdi, [r11+38h]
0x18008e6e4  mov     rsp, r11
0x18008e6e7  pop     r15
0x18008e6e9  pop     r14
0x18008e6eb  pop     rbp
0x18008e6ec  retn
```
