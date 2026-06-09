# RasLineSetDefaultMediaDetection

- ea: `0x1800882cc`
- end: `0x1800884f2`
- name: `RasLineSetDefaultMediaDetection`
- size: `550`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180087a2c`

## callees

- `0x180071cec`
- `0x18008490c`
- `0x1800882cc`
- `0x1800884f8`
- `0x1800892bc`
- `0x18008a408`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800884a8`
- `KERNEL32!GetProcessHeap` at `0x1800884a8`
- `KERNEL32!HeapFree` at `0x1800884b6`
- `KERNEL32!HeapFree` at `0x1800884b6`
- `rtutils!TracePrintfA` at `0x1800883ae`
- `rtutils!TracePrintfA` at `0x18008849d`
- `rtutils!TracePrintfA` at `0x1800883ae`
- `rtutils!TracePrintfA` at `0x18008849d`

## string_xrefs

- `0x1800883a7`: `RasLineSetDefaultMediaDetection: GetLineObjWithReadLock failed with error (0x%x)`
- `0x180088358`: `RasLineSetDefaultMediaDetection: GetLineObjWithReadLock failed with error (0x%x)`

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
  unsigned int *v11; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-D8h] BYREF
  int v13; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[2044]; // [rsp+34h] [rbp-CCh] BYREF

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
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v13) = 0;
        FormatRRASErrorString(
          &v13,
          L"RasLineSetDefaultMediaDetection: GetLineObjWithReadLock failed with error (0x%x)",
          LineObjWithReadLock);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v13);
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
    if ( (_QWORD)xmmword_1800C9BE0 )
    {
      v7 = L"RasLineSetDefaultMediaDetection: PrepareSyncRequest failed with error (0x%x)";
LABEL_17:
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v13, v7, v4);
      ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v13);
    }
  }
  else
  {
    v8 = lpMem;
    *((_QWORD *)lpMem + 7) = *((_QWORD *)v3 + 2);
    v6[16] = 258;
    v4 = SyncDriverRequest(0x8FFF23C8, v8);
    if ( v4 )
    {
      if ( !gIsndpspEtwTracingAvailable )
      {
        if ( dwTraceId != -1 )
          TracePrintfA(
            dwTraceId,
            "RasLineSetDefaultMediaDetection: SyncDriverRequest(OID_TAPI_SET_DEFAULT_MEDIA_DETECTION) failed with error (0x%x)",
            v4);
        goto LABEL_20;
      }
      if ( (_QWORD)xmmword_1800C9BE0 )
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
0x1800882cc  mov     [rsp-8+arg_8], rbx
0x1800882d1  mov     [rsp-8+arg_10], rsi
0x1800882d6  push    rbp
0x1800882d7  push    rdi
0x1800882d8  push    r14
0x1800882da  lea     rbp, [rsp-740h]
0x1800882e2  sub     rsp, 840h
0x1800882e9  mov     rax, cs:__security_cookie
0x1800882f0  xor     rax, rsp
0x1800882f3  mov     [rbp+750h+var_20], rax
0x1800882fa  mov     r14d, ecx
0x1800882fd  mov     [rsp+850h+lpMem], 0
0x180088306  xor     eax, eax
0x180088308  mov     [rsp+850h+var_830], 0
0x180088311  lea     rcx, [rsp+850h+var_81C]; void *
0x180088316  mov     [rsp+850h+var_820], eax
0x18008831a  xor     edx, edx; Val
0x18008831c  mov     r8d, 7FCh; Size
0x180088322  call    memset_0
0x180088327  lea     rdx, [rsp+850h+var_830]
0x18008832c  mov     ecx, r14d
0x18008832f  call    GetLineObjWithReadLock
0x180088334  mov     rsi, [rsp+850h+var_830]
0x180088339  mov     ebx, eax
0x18008833b  test    eax, eax
0x18008833d  jz      short loc_1800883B9
0x18008833f  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180088346  jz      short loc_180088395
0x180088348  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x180088350  jz      loc_1800884BC
0x180088356  xor     ecx, ecx
0x180088358  lea     rdx, aRaslinesetdefa_1; "RasLineSetDefaultMediaDetection: GetLin"...
0x18008835f  mov     word ptr [rsp+850h+var_820], cx
0x180088364  mov     r8d, eax
0x180088367  lea     rcx, [rsp+850h+var_820]
0x18008836c  call    FormatRRASErrorString
0x180088371  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180088378  lea     r8, [rsp+850h+var_820]
0x18008837d  mov     rcx, cs:gNdpspEtwContext
0x180088384  mov     rax, cs:gNdpspTemplateFunc
0x18008838b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088390  jmp     loc_1800884BC
0x180088395  mov     ecx, cs:dwTraceId; dwTraceID
0x18008839b  cmp     ecx, 0FFFFFFFFh
0x18008839e  jz      loc_1800884BC
0x1800883a4  mov     r8d, eax
0x1800883a7  lea     rdx, aRaslinesetdefa_3; "RasLineSetDefaultMediaDetection: GetLin"...
0x1800883ae  call    cs:__imp_TracePrintfA
0x1800883b4  jmp     loc_1800884BC
0x1800883b9  mov     edx, [rsi+4]
0x1800883bc  lea     r9, [rsp+850h+lpMem]
0x1800883c1  mov     r8d, 18h
0x1800883c7  mov     ecx, 703011Fh
0x1800883cc  call    PrepareSyncRequest
0x1800883d1  mov     rdi, [rsp+850h+lpMem]
0x1800883d6  mov     ebx, eax
0x1800883d8  test    eax, eax
0x1800883da  jz      short loc_180088417
0x1800883dc  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x1800883e3  jz      short loc_1800883FC
0x1800883e5  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x1800883ed  jz      loc_1800884A3
0x1800883f3  lea     rdx, aRaslinesetdefa_4; "RasLineSetDefaultMediaDetection: Prepar"...
0x1800883fa  jmp     short loc_180088453
0x1800883fc  mov     ecx, cs:dwTraceId
0x180088402  cmp     ecx, 0FFFFFFFFh
0x180088405  jz      loc_1800884A3
0x18008840b  lea     rdx, aRaslinesetdefa_2; "RasLineSetDefaultMediaDetection: Prepar"...
0x180088412  jmp     loc_18008849A
0x180088417  mov     rax, [rsi+10h]
0x18008841b  mov     rdx, rdi; lpInBuffer
0x18008841e  mov     ecx, 8FFF23C8h; dwIoControlCode
0x180088423  mov     [rdi+38h], rax
0x180088427  mov     dword ptr [rdi+40h], 102h
0x18008842e  call    SyncDriverRequest
0x180088433  mov     ebx, eax
0x180088435  test    eax, eax
0x180088437  jz      short loc_1800884A3
0x180088439  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180088440  jz      short loc_180088488
0x180088442  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x18008844a  jz      short loc_1800884A3
0x18008844c  lea     rdx, aRaslinesetdefa_0; "RasLineSetDefaultMediaDetection: SyncDr"...
0x180088453  xor     eax, eax
0x180088455  lea     rcx, [rsp+850h+var_820]
0x18008845a  mov     r8d, ebx
0x18008845d  mov     word ptr [rsp+850h+var_820], ax
0x180088462  call    FormatRRASErrorString
0x180088467  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x18008846e  lea     r8, [rsp+850h+var_820]
0x180088473  mov     rcx, cs:gNdpspEtwContext
0x18008847a  mov     rax, cs:gNdpspTemplateFunc
0x180088481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088486  jmp     short loc_1800884A3
0x180088488  mov     ecx, cs:dwTraceId; dwTraceID
0x18008848e  cmp     ecx, 0FFFFFFFFh
0x180088491  jz      short loc_1800884A3
0x180088493  lea     rdx, aRaslinesetdefa; "RasLineSetDefaultMediaDetection: SyncDr"...
0x18008849a  mov     r8d, ebx
0x18008849d  call    cs:__imp_TracePrintfA
0x1800884a3  test    rdi, rdi
0x1800884a6  jz      short loc_1800884BC
0x1800884a8  call    cs:__imp_GetProcessHeap
0x1800884ae  mov     r8, rdi; lpMem
0x1800884b1  xor     edx, edx; dwFlags
0x1800884b3  mov     rcx, rax; hHeap
0x1800884b6  call    cs:__imp_HeapFree
0x1800884bc  test    rsi, rsi
0x1800884bf  jz      short loc_1800884C9
0x1800884c1  mov     ecx, r14d
0x1800884c4  call    ReleaseObjReadLock
0x1800884c9  mov     eax, ebx
0x1800884cb  mov     rcx, [rbp+750h+var_20]
0x1800884d2  xor     rcx, rsp; StackCookie
0x1800884d5  call    __security_check_cookie
0x1800884da  lea     r11, [rsp+850h+var_10]
0x1800884e2  mov     rbx, [r11+28h]
0x1800884e6  mov     rsi, [r11+30h]
0x1800884ea  mov     rsp, r11
0x1800884ed  pop     r14
0x1800884ef  pop     rdi
0x1800884f0  pop     rbp
0x1800884f1  retn
```
