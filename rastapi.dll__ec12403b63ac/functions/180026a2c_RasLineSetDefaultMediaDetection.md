# RasLineSetDefaultMediaDetection

- ea: `0x180026a2c`
- end: `0x180026c45`
- name: `RasLineSetDefaultMediaDetection`
- size: `537`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002619c`

## callees

- `0x18002251c`
- `0x180026a2c`
- `0x180026c4c`
- `0x180027a10`
- `0x180028b5c`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026c03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026c03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026c11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026c11`
- `rtutils!TracePrintfA` at `0x180026b0c`
- `rtutils!TracePrintfA` at `0x180026bf8`
- `rtutils!TracePrintfA` at `0x180026b0c`
- `rtutils!TracePrintfA` at `0x180026bf8`

## string_xrefs

- `0x180026ab6`: `RasLineSetDefaultMediaDetection: GetLineObjWithReadLock failed with error (0x%x)`
- `0x180026b05`: `RasLineSetDefaultMediaDetection: GetLineObjWithReadLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineSetDefaultMediaDetection(unsigned int a1, int a2)
{
  unsigned int LineObjWithReadLock; // eax
  unsigned int *v5; // rsi
  unsigned int v6; // ebx
  unsigned int v7; // eax
  _DWORD *v8; // rdi
  const wchar_t *v9; // rdx
  _DWORD *v10; // rdx
  HANDLE ProcessHeap; // rax
  unsigned int *v13; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-D8h] BYREF
  int v15; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v16[2044]; // [rsp+34h] [rbp-CCh] BYREF

  lpMem = 0;
  v13 = 0;
  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  LineObjWithReadLock = GetLineObjWithReadLock(a1, &v13);
  v5 = v13;
  v6 = LineObjWithReadLock;
  if ( LineObjWithReadLock )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( qword_18003EC40 )
      {
        LOWORD(v15) = 0;
        FormatRRASErrorString(
          &v15,
          L"RasLineSetDefaultMediaDetection: GetLineObjWithReadLock failed with error (0x%x)",
          LineObjWithReadLock);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v15);
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
  v7 = PrepareSyncRequest(0x703011Fu, v13[1], 0x18u, &lpMem);
  v8 = lpMem;
  v6 = v7;
  if ( v7 )
  {
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineSetDefaultMediaDetection: PrepareSyncRequest failed with error (0x%x)", v7);
      goto LABEL_20;
    }
    if ( qword_18003EC40 )
    {
      v9 = L"RasLineSetDefaultMediaDetection: PrepareSyncRequest failed with error (0x%x)";
LABEL_17:
      LOWORD(v15) = 0;
      FormatRRASErrorString(&v15, v9, v6);
      ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v15);
    }
  }
  else
  {
    v10 = lpMem;
    *((_QWORD *)lpMem + 7) = *((_QWORD *)v5 + 2);
    v8[16] = a2;
    v6 = SyncDriverRequest(0x8FFF23C8, v10);
    if ( v6 )
    {
      if ( !gIsndpspEtwTracingAvailable )
      {
        if ( dwTraceId != -1 )
          TracePrintfA(
            dwTraceId,
            "RasLineSetDefaultMediaDetection: SyncDriverRequest(OID_TAPI_SET_DEFAULT_MEDIA_DETECTION) failed with error (0x%x)",
            v6);
        goto LABEL_20;
      }
      if ( qword_18003EC40 )
      {
        v9 = L"RasLineSetDefaultMediaDetection: SyncDriverRequest(OID_TAPI_SET_DEFAULT_MEDIA_DETECTION) failed with error (0x%x)";
        goto LABEL_17;
      }
    }
  }
LABEL_20:
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
  }
LABEL_22:
  if ( v5 )
    ReleaseObjReadLock(a1);
  return v6;
}

```

## disassembly

```asm
0x180026a2c  push    rbp
0x180026a2e  push    rbx
0x180026a2f  push    rsi
0x180026a30  push    rdi
0x180026a31  push    r14
0x180026a33  push    r15
0x180026a35  lea     rbp, [rsp-748h]
0x180026a3d  sub     rsp, 848h
0x180026a44  mov     rax, cs:__security_cookie
0x180026a4b  xor     rax, rsp
0x180026a4e  mov     [rbp+770h+var_40], rax
0x180026a55  mov     r14d, edx
0x180026a58  mov     [rsp+870h+lpMem], 0
0x180026a61  mov     r15d, ecx
0x180026a64  mov     [rsp+870h+var_850], 0
0x180026a6d  xor     eax, eax
0x180026a6f  lea     rcx, [rsp+870h+var_83C]; void *
0x180026a74  xor     edx, edx; Val
0x180026a76  mov     [rsp+870h+var_840], eax
0x180026a7a  mov     r8d, 7FCh; Size
0x180026a80  call    memset_0
0x180026a85  lea     rdx, [rsp+870h+var_850]
0x180026a8a  mov     ecx, r15d
0x180026a8d  call    GetLineObjWithReadLock
0x180026a92  mov     rsi, [rsp+870h+var_850]
0x180026a97  mov     ebx, eax
0x180026a99  test    eax, eax
0x180026a9b  jz      short loc_180026B17
0x180026a9d  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180026aa4  jz      short loc_180026AF3
0x180026aa6  cmp     cs:qword_18003EC40, 0
0x180026aae  jz      loc_180026C17
0x180026ab4  xor     ecx, ecx
0x180026ab6  lea     rdx, aRaslinesetdefa_1; "RasLineSetDefaultMediaDetection: GetLin"...
0x180026abd  mov     word ptr [rsp+870h+var_840], cx
0x180026ac2  mov     r8d, eax
0x180026ac5  lea     rcx, [rsp+870h+var_840]
0x180026aca  call    FormatRRASErrorString
0x180026acf  mov     rdx, cs:qword_18003EC40
0x180026ad6  lea     r8, [rsp+870h+var_840]
0x180026adb  mov     rcx, cs:gNdpspEtwContext
0x180026ae2  mov     rax, cs:gNdpspTemplateFunc
0x180026ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026aee  jmp     loc_180026C17
0x180026af3  mov     ecx, cs:dwTraceId; dwTraceID
0x180026af9  cmp     ecx, 0FFFFFFFFh
0x180026afc  jz      loc_180026C17
0x180026b02  mov     r8d, eax
0x180026b05  lea     rdx, aRaslinesetdefa_3; "RasLineSetDefaultMediaDetection: GetLin"...
0x180026b0c  call    cs:__imp_TracePrintfA
0x180026b12  jmp     loc_180026C17
0x180026b17  mov     edx, [rsi+4]
0x180026b1a  lea     r9, [rsp+870h+lpMem]
0x180026b1f  mov     r8d, 18h
0x180026b25  mov     ecx, 703011Fh
0x180026b2a  call    PrepareSyncRequest
0x180026b2f  mov     rdi, [rsp+870h+lpMem]
0x180026b34  mov     ebx, eax
0x180026b36  test    eax, eax
0x180026b38  jz      short loc_180026B75
0x180026b3a  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180026b41  jz      short loc_180026B5A
0x180026b43  cmp     cs:qword_18003EC40, 0
0x180026b4b  jz      loc_180026BFE
0x180026b51  lea     rdx, aRaslinesetdefa_4; "RasLineSetDefaultMediaDetection: Prepar"...
0x180026b58  jmp     short loc_180026BAE
0x180026b5a  mov     ecx, cs:dwTraceId
0x180026b60  cmp     ecx, 0FFFFFFFFh
0x180026b63  jz      loc_180026BFE
0x180026b69  lea     rdx, aRaslinesetdefa_2; "RasLineSetDefaultMediaDetection: Prepar"...
0x180026b70  jmp     loc_180026BF5
0x180026b75  mov     rax, [rsi+10h]
0x180026b79  mov     rdx, rdi; lpInBuffer
0x180026b7c  mov     ecx, 8FFF23C8h; dwIoControlCode
0x180026b81  mov     [rdi+38h], rax
0x180026b85  mov     [rdi+40h], r14d
0x180026b89  call    SyncDriverRequest
0x180026b8e  mov     ebx, eax
0x180026b90  test    eax, eax
0x180026b92  jz      short loc_180026BFE
0x180026b94  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180026b9b  jz      short loc_180026BE3
0x180026b9d  cmp     cs:qword_18003EC40, 0
0x180026ba5  jz      short loc_180026BFE
0x180026ba7  lea     rdx, aRaslinesetdefa_0; "RasLineSetDefaultMediaDetection: SyncDr"...
0x180026bae  xor     eax, eax
0x180026bb0  lea     rcx, [rsp+870h+var_840]
0x180026bb5  mov     r8d, ebx
0x180026bb8  mov     word ptr [rsp+870h+var_840], ax
0x180026bbd  call    FormatRRASErrorString
0x180026bc2  mov     rdx, cs:qword_18003EC40
0x180026bc9  lea     r8, [rsp+870h+var_840]
0x180026bce  mov     rcx, cs:gNdpspEtwContext
0x180026bd5  mov     rax, cs:gNdpspTemplateFunc
0x180026bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026be1  jmp     short loc_180026BFE
0x180026be3  mov     ecx, cs:dwTraceId; dwTraceID
0x180026be9  cmp     ecx, 0FFFFFFFFh
0x180026bec  jz      short loc_180026BFE
0x180026bee  lea     rdx, aRaslinesetdefa; "RasLineSetDefaultMediaDetection: SyncDr"...
0x180026bf5  mov     r8d, ebx
0x180026bf8  call    cs:__imp_TracePrintfA
0x180026bfe  test    rdi, rdi
0x180026c01  jz      short loc_180026C17
0x180026c03  call    cs:__imp_GetProcessHeap
0x180026c09  mov     r8, rdi; lpMem
0x180026c0c  xor     edx, edx; dwFlags
0x180026c0e  mov     rcx, rax; hHeap
0x180026c11  call    cs:__imp_HeapFree
0x180026c17  test    rsi, rsi
0x180026c1a  jz      short loc_180026C24
0x180026c1c  mov     ecx, r15d
0x180026c1f  call    ReleaseObjReadLock
0x180026c24  mov     eax, ebx
0x180026c26  mov     rcx, [rbp+770h+var_40]
0x180026c2d  xor     rcx, rsp; StackCookie
0x180026c30  call    __security_check_cookie
0x180026c35  add     rsp, 848h
0x180026c3c  pop     r15
0x180026c3e  pop     r14
0x180026c40  pop     rdi
0x180026c41  pop     rsi
0x180026c42  pop     rbx
0x180026c43  pop     rbp
0x180026c44  retn
```
