# RasLineCloseCall

- ea: `0x18008beac`
- end: `0x18008c2d2`
- name: `RasLineCloseCall`
- size: `1062`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `15`
- tags: ``

## callers

- `0x1800285b8`
- `0x18002a000`
- `0x18002a7b0`

## callees

- `0x1800755b8`
- `0x18008a88c`
- `0x18008beac`
- `0x18008e6f4`
- `0x18008ed64`
- `0x18008f388`
- `0x18008f69c`
- `0x18008f82c`
- `0x18008fb8c`
- `0x18008fd44`
- `0x180090714`
- `0x180090834`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18008c284`
- `KERNEL32!GetProcessHeap` at `0x18008c284`
- `KERNEL32!HeapFree` at `0x18008c298`
- `KERNEL32!HeapFree` at `0x18008c298`
- `rtutils!TracePrintfA` at `0x18008bf92`
- `rtutils!TracePrintfA` at `0x18008c18d`
- `rtutils!TracePrintfA` at `0x18008c222`
- `rtutils!TracePrintfA` at `0x18008bf92`
- `rtutils!TracePrintfA` at `0x18008c18d`
- `rtutils!TracePrintfA` at `0x18008c222`

## string_xrefs

- `0x18008bfcb`: `RasLineCloseCall: GetCallObjWithReadLock failed with error (0x%x)`
- `0x18008bfe6`: `RasLineCloseCall: GetCallObjWithReadLock failed with error (0x%x)`
- `0x18008c071`: `RasLineCloseCall: AcquireObjWriteLock failed with error (0x%x)`
- `0x18008c0c2`: `RasLineClose: GetLineObjWithWriteLock failed with error (0x%x)`
- `0x18008c08c`: `RasLineCloseCall: AcquireObjWriteLock failed with error (0x%x)`
- `0x18008c0dd`: `RasLineClose: GetLineObjWithWriteLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineCloseCall(unsigned int a1)
{
  unsigned int NDProxyHandle; // eax
  unsigned int v3; // ebx
  const wchar_t *v4; // rdx
  _DWORD *v5; // rdi
  int v6; // r12d
  unsigned int v7; // eax
  __int64 v8; // rdx
  _QWORD *v9; // r14
  __int64 v10; // rdx
  __int64 v11; // rax
  void *v12; // rdx
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rdx
  HANDLE ProcessHeap; // rax
  unsigned int v20; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD *v21; // [rsp+28h] [rbp-D8h] BYREF
  LPVOID lpMem; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  int v25; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[2044]; // [rsp+54h] [rbp-ACh] BYREF

  lpMem = 0;
  v23 = 0;
  v21 = 0;
  v24 = 0;
  v20 = 0;
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  NDProxyHandle = GetLineHandleFromCallHandle(a1, &v20);
  v3 = NDProxyHandle;
  if ( NDProxyHandle )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800D0BE0 )
      {
        v4 = L"RasLineCloseCall: GetLineHandleFromCallHandle failed with error (0x%x)";
LABEL_5:
        LOWORD(v25) = 0;
        FormatRRASErrorString(&v25, v4, NDProxyHandle);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v25);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "RasLineCloseCall: GetLineHandleFromCallHandle failed with error (0x%x)", NDProxyHandle);
    }
  }
  else
  {
    NDProxyHandle = GetCallObjWithReadLock(a1, &v21);
    v3 = NDProxyHandle;
    if ( NDProxyHandle )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( !(_QWORD)xmmword_1800D0BE0 )
          return v3;
        v4 = L"RasLineCloseCall: GetCallObjWithReadLock failed with error (0x%x)";
        goto LABEL_5;
      }
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineCloseCall: GetCallObjWithReadLock failed with error (0x%x)", NDProxyHandle);
    }
    else
    {
      v5 = v21;
      v6 = *v21;
      NDProxyHandle = GetNDProxyHandle((__int64)v21, &v23);
      v3 = NDProxyHandle;
      if ( NDProxyHandle )
      {
        if ( gIsndpspEtwTracingAvailable )
        {
          if ( !(_QWORD)xmmword_1800D0BE0 )
            return v3;
          v4 = L"RasLineCloseCall: GetNDProxyHandle failed with error (0x%x)";
          goto LABEL_5;
        }
        if ( dwTraceId != -1 )
          TracePrintfA(dwTraceId, "RasLineCloseCall: GetNDProxyHandle failed with error (0x%x)", NDProxyHandle);
      }
      else
      {
        ReleaseObjReadLock(a1);
        NDProxyHandle = AcquireObjWriteLock(a1);
        v3 = NDProxyHandle;
        if ( NDProxyHandle )
        {
          if ( gIsndpspEtwTracingAvailable )
          {
            if ( !(_QWORD)xmmword_1800D0BE0 )
              return v3;
            v4 = L"RasLineCloseCall: AcquireObjWriteLock failed with error (0x%x)";
            goto LABEL_5;
          }
          if ( dwTraceId != -1 )
            TracePrintfA(dwTraceId, "RasLineCloseCall: AcquireObjWriteLock failed with error (0x%x)", NDProxyHandle);
        }
        else
        {
          NDProxyHandle = GetLineObjWithWriteLock(v20, &v24);
          v3 = NDProxyHandle;
          if ( NDProxyHandle )
          {
            if ( gIsndpspEtwTracingAvailable )
            {
              if ( !(_QWORD)xmmword_1800D0BE0 )
                return v3;
              v4 = L"RasLineClose: GetLineObjWithWriteLock failed with error (0x%x)";
              goto LABEL_5;
            }
            if ( dwTraceId != -1 )
              TracePrintfA(dwTraceId, "RasLineClose: GetLineObjWithWriteLock failed with error (0x%x)", NDProxyHandle);
          }
          else
          {
            v7 = PrepareSyncRequest(117637380, (unsigned int)v5[1], 16, &lpMem);
            v9 = lpMem;
            v3 = v7;
            if ( v7 )
            {
              ReleaseObjWriteLock(a1, v8);
              ReleaseObjWriteLock(v20, v10);
              if ( gIsndpspEtwTracingAvailable )
              {
                if ( (_QWORD)xmmword_1800D0BE0 )
                {
                  LOWORD(v25) = 0;
                  FormatRRASErrorString(&v25, L"RasLineCloseCall: PrepareSyncRequest failed with error (0x%x)", v3);
                  ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(
                    gNdpspEtwContext,
                    xmmword_1800D0BE0,
                    &v25);
                }
              }
              else if ( dwTraceId != -1 )
              {
                TracePrintfA(dwTraceId, "RasLineCloseCall: PrepareSyncRequest failed with error (0x%x)", v3);
              }
            }
            else
            {
              v11 = v23;
              v12 = lpMem;
              *v5 = 1482184792;
              v9[7] = v11;
              v13 = SyncDriverRequest(0x8FFF23CC, v12);
              v3 = v13;
              if ( v13 )
              {
                if ( gIsndpspEtwTracingAvailable )
                {
                  if ( (_QWORD)xmmword_1800D0BE0 )
                  {
                    LOWORD(v25) = 0;
                    FormatRRASErrorString(
                      &v25,
                      L"RasLineClose: SyncDriverRequest(OID_TAPI_CLOSE_CALL) failed with error (0x%x)",
                      v13);
                    ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(
                      gNdpspEtwContext,
                      xmmword_1800D0BE0,
                      &v25);
                  }
                }
                else if ( dwTraceId != -1 )
                {
                  TracePrintfA(
                    dwTraceId,
                    "RasLineClose: SyncDriverRequest(OID_TAPI_CLOSE_CALL) failed with error (0x%x)",
                    v13);
                }
              }
              if ( v6 == 1229144396 )
              {
                v15 = *((_QWORD *)v5 + 7);
                if ( v15 )
                  *(_QWORD *)(v15 + 48) = *((_QWORD *)v5 + 6);
                v16 = *((_QWORD *)v5 + 6);
                if ( v16 )
                  *(_QWORD *)(v16 + 56) = *((_QWORD *)v5 + 7);
                else
                  *(_QWORD *)(v24 + 24) = *((_QWORD *)v5 + 7);
              }
              ReleaseObjWriteLock(a1, v14);
              ReleaseObjWriteLock(v20, v17);
              CloseObjHandle(a1);
            }
            if ( v9 )
            {
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, v9);
            }
          }
        }
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18008beac  mov     [rsp-8+arg_8], rbx
0x18008beb1  mov     [rsp-8+arg_10], rsi
0x18008beb6  push    rbp
0x18008beb7  push    rdi
0x18008beb8  push    r12
0x18008beba  push    r13
0x18008bebc  push    r14
0x18008bebe  lea     rbp, [rsp-760h]
0x18008bec6  sub     rsp, 860h
0x18008becd  mov     rax, cs:__security_cookie
0x18008bed4  xor     rax, rsp
0x18008bed7  mov     [rbp+780h+var_30], rax
0x18008bede  xor     r13d, r13d
0x18008bee1  mov     esi, ecx
0x18008bee3  lea     rcx, [rsp+880h+var_82C]; void *
0x18008bee8  mov     [rsp+880h+lpMem], r13
0x18008beed  xor     edx, edx; Val
0x18008beef  mov     [rsp+880h+var_848], r13
0x18008bef4  mov     r8d, 7FCh; Size
0x18008befa  mov     [rsp+880h+var_858], r13
0x18008beff  mov     [rsp+880h+var_840], r13
0x18008bf04  mov     [rsp+880h+var_860], r13d
0x18008bf09  mov     [rsp+880h+var_830], r13d
0x18008bf0e  call    memset_0
0x18008bf13  lea     rdx, [rsp+880h+var_860]
0x18008bf18  mov     ecx, esi
0x18008bf1a  call    GetLineHandleFromCallHandle
0x18008bf1f  mov     ebx, eax
0x18008bf21  test    eax, eax
0x18008bf23  jz      short loc_18008BFA3
0x18008bf25  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008bf2c  jz      short loc_18008BF79
0x18008bf2e  cmp     qword ptr cs:xmmword_1800D0BE0, r13
0x18008bf35  jz      loc_18008C2A4
0x18008bf3b  lea     rdx, aRaslinecloseca_7; "RasLineCloseCall: GetLineHandleFromCall"...
0x18008bf42  mov     r8d, eax
0x18008bf45  mov     word ptr [rsp+880h+var_830], r13w
0x18008bf4b  lea     rcx, [rsp+880h+var_830]
0x18008bf50  call    FormatRRASErrorString
0x18008bf55  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008bf5c  lea     r8, [rsp+880h+var_830]
0x18008bf61  mov     rcx, cs:gNdpspEtwContext
0x18008bf68  mov     rax, cs:gNdpspTemplateFunc
0x18008bf6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bf74  jmp     loc_18008C2A4
0x18008bf79  mov     ecx, cs:dwTraceId; dwTraceID
0x18008bf7f  cmp     ecx, 0FFFFFFFFh
0x18008bf82  jz      loc_18008C2A4
0x18008bf88  lea     rdx, aRaslinecloseca_3; "RasLineCloseCall: GetLineHandleFromCall"...
0x18008bf8f  mov     r8d, eax
0x18008bf92  call    cs:__imp_TracePrintfA
0x18008bf99  nop     dword ptr [rax+rax+00h]
0x18008bf9e  jmp     loc_18008C2A4
0x18008bfa3  lea     rdx, [rsp+880h+var_858]
0x18008bfa8  mov     ecx, esi
0x18008bfaa  call    GetCallObjWithReadLock
0x18008bfaf  mov     ebx, eax
0x18008bfb1  test    eax, eax
0x18008bfb3  jz      short loc_18008BFEF
0x18008bfb5  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008bfbc  jz      short loc_18008BFD7
0x18008bfbe  cmp     qword ptr cs:xmmword_1800D0BE0, r13
0x18008bfc5  jz      loc_18008C2A4
0x18008bfcb  lea     rdx, aRaslinecloseca_6; "RasLineCloseCall: GetCallObjWithReadLoc"...
0x18008bfd2  jmp     loc_18008BF42
0x18008bfd7  mov     ecx, cs:dwTraceId
0x18008bfdd  cmp     ecx, 0FFFFFFFFh
0x18008bfe0  jz      loc_18008C2A4
0x18008bfe6  lea     rdx, aRaslinecloseca; "RasLineCloseCall: GetCallObjWithReadLoc"...
0x18008bfed  jmp     short loc_18008BF8F
0x18008bfef  mov     rdi, [rsp+880h+var_858]
0x18008bff4  lea     rdx, [rsp+880h+var_848]
0x18008bff9  mov     rcx, rdi
0x18008bffc  mov     r12d, [rdi]
0x18008bfff  call    GetNDProxyHandle
0x18008c004  mov     ebx, eax
0x18008c006  test    eax, eax
0x18008c008  jz      short loc_18008C047
0x18008c00a  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008c011  jz      short loc_18008C02C
0x18008c013  cmp     qword ptr cs:xmmword_1800D0BE0, r13
0x18008c01a  jz      loc_18008C2A4
0x18008c020  lea     rdx, aRaslinecloseca_2; "RasLineCloseCall: GetNDProxyHandle fail"...
0x18008c027  jmp     loc_18008BF42
0x18008c02c  mov     ecx, cs:dwTraceId
0x18008c032  cmp     ecx, 0FFFFFFFFh
0x18008c035  jz      loc_18008C2A4
0x18008c03b  lea     rdx, aRaslinecloseca_4; "RasLineCloseCall: GetNDProxyHandle fail"...
0x18008c042  jmp     loc_18008BF8F
0x18008c047  mov     ecx, esi
0x18008c049  call    ReleaseObjReadLock
0x18008c04e  mov     ecx, esi
0x18008c050  call    AcquireObjWriteLock
0x18008c055  mov     ebx, eax
0x18008c057  test    eax, eax
0x18008c059  jz      short loc_18008C098
0x18008c05b  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008c062  jz      short loc_18008C07D
0x18008c064  cmp     qword ptr cs:xmmword_1800D0BE0, r13
0x18008c06b  jz      loc_18008C2A4
0x18008c071  lea     rdx, aRaslinecloseca_8; "RasLineCloseCall: AcquireObjWriteLock f"...
0x18008c078  jmp     loc_18008BF42
0x18008c07d  mov     ecx, cs:dwTraceId
0x18008c083  cmp     ecx, 0FFFFFFFFh
0x18008c086  jz      loc_18008C2A4
0x18008c08c  lea     rdx, aRaslinecloseca_1; "RasLineCloseCall: AcquireObjWriteLock f"...
0x18008c093  jmp     loc_18008BF8F
0x18008c098  mov     ecx, [rsp+880h+var_860]
0x18008c09c  lea     rdx, [rsp+880h+var_840]
0x18008c0a1  call    GetLineObjWithWriteLock
0x18008c0a6  mov     ebx, eax
0x18008c0a8  test    eax, eax
0x18008c0aa  jz      short loc_18008C0E9
0x18008c0ac  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008c0b3  jz      short loc_18008C0CE
0x18008c0b5  cmp     qword ptr cs:xmmword_1800D0BE0, r13
0x18008c0bc  jz      loc_18008C2A4
0x18008c0c2  lea     rdx, aRaslinecloseGe_0; "RasLineClose: GetLineObjWithWriteLock f"...
0x18008c0c9  jmp     loc_18008BF42
0x18008c0ce  mov     ecx, cs:dwTraceId
0x18008c0d4  cmp     ecx, 0FFFFFFFFh
0x18008c0d7  jz      loc_18008C2A4
0x18008c0dd  lea     rdx, aRaslinecloseGe; "RasLineClose: GetLineObjWithWriteLock f"...
0x18008c0e4  jmp     loc_18008BF8F
0x18008c0e9  mov     edx, [rdi+4]
0x18008c0ec  lea     r9, [rsp+880h+lpMem]
0x18008c0f1  mov     r8d, 10h
0x18008c0f7  mov     ecx, 7030104h
0x18008c0fc  call    PrepareSyncRequest
0x18008c101  mov     r14, [rsp+880h+lpMem]
0x18008c106  mov     ebx, eax
0x18008c108  test    eax, eax
0x18008c10a  jz      loc_18008C19E
0x18008c110  mov     ecx, esi
0x18008c112  call    ReleaseObjWriteLock
0x18008c117  mov     ecx, [rsp+880h+var_860]
0x18008c11b  call    ReleaseObjWriteLock
0x18008c120  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008c127  jz      short loc_18008C174
0x18008c129  cmp     qword ptr cs:xmmword_1800D0BE0, r13
0x18008c130  jz      loc_18008C27F
0x18008c136  mov     r8d, ebx
0x18008c139  mov     word ptr [rsp+880h+var_830], r13w
0x18008c13f  lea     rdx, aRaslinecloseca_0; "RasLineCloseCall: PrepareSyncRequest fa"...
0x18008c146  lea     rcx, [rsp+880h+var_830]
0x18008c14b  call    FormatRRASErrorString
0x18008c150  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008c157  lea     r8, [rsp+880h+var_830]
0x18008c15c  mov     rcx, cs:gNdpspEtwContext
0x18008c163  mov     rax, cs:gNdpspTemplateFunc
0x18008c16a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c16f  jmp     loc_18008C27F
0x18008c174  mov     ecx, cs:dwTraceId; dwTraceID
0x18008c17a  cmp     ecx, 0FFFFFFFFh
0x18008c17d  jz      loc_18008C27F
0x18008c183  mov     r8d, ebx
0x18008c186  lea     rdx, aRaslinecloseca_5; "RasLineCloseCall: PrepareSyncRequest fa"...
0x18008c18d  call    cs:__imp_TracePrintfA
0x18008c194  nop     dword ptr [rax+rax+00h]
0x18008c199  jmp     loc_18008C27F
0x18008c19e  mov     rax, [rsp+880h+var_848]
0x18008c1a3  mov     rdx, r14; lpInBuffer
0x18008c1a6  mov     dword ptr [rdi], 58585858h
0x18008c1ac  mov     ecx, 8FFF23CCh; dwIoControlCode
0x18008c1b1  mov     [r14+38h], rax
0x18008c1b5  call    SyncDriverRequest
0x18008c1ba  mov     ebx, eax
0x18008c1bc  test    eax, eax
0x18008c1be  jz      short loc_18008C22E
0x18008c1c0  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008c1c7  jz      short loc_18008C20D
0x18008c1c9  cmp     qword ptr cs:xmmword_1800D0BE0, r13
0x18008c1d0  jz      short loc_18008C22E
0x18008c1d2  mov     r8d, eax
0x18008c1d5  mov     word ptr [rsp+880h+var_830], r13w
0x18008c1db  lea     rdx, aRaslinecloseSy_1; "RasLineClose: SyncDriverRequest(OID_TAP"...
0x18008c1e2  lea     rcx, [rsp+880h+var_830]
0x18008c1e7  call    FormatRRASErrorString
0x18008c1ec  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008c1f3  lea     r8, [rsp+880h+var_830]
0x18008c1f8  mov     rcx, cs:gNdpspEtwContext
0x18008c1ff  mov     rax, cs:gNdpspTemplateFunc
0x18008c206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c20b  jmp     short loc_18008C22E
0x18008c20d  mov     ecx, cs:dwTraceId; dwTraceID
0x18008c213  cmp     ecx, 0FFFFFFFFh
0x18008c216  jz      short loc_18008C22E
0x18008c218  mov     r8d, eax
0x18008c21b  lea     rdx, aRaslinecloseSy_2; "RasLineClose: SyncDriverRequest(OID_TAP"...
0x18008c222  call    cs:__imp_TracePrintfA
0x18008c229  nop     dword ptr [rax+rax+00h]
0x18008c22e  cmp     r12d, 4943414Ch
0x18008c235  jnz     short loc_18008C268
0x18008c237  mov     rcx, [rdi+38h]
0x18008c23b  test    rcx, rcx
0x18008c23e  jz      short loc_18008C248
0x18008c240  mov     rax, [rdi+30h]
0x18008c244  mov     [rcx+30h], rax
0x18008c248  mov     rcx, [rdi+30h]
0x18008c24c  test    rcx, rcx
0x18008c24f  jz      short loc_18008C25B
0x18008c251  mov     rax, [rdi+38h]
0x18008c255  mov     [rcx+38h], rax
0x18008c259  jmp     short loc_18008C268
0x18008c25b  mov     rax, [rsp+880h+var_840]
0x18008c260  mov     rcx, [rdi+38h]
0x18008c264  mov     [rax+18h], rcx
0x18008c268  mov     ecx, esi
0x18008c26a  call    ReleaseObjWriteLock
0x18008c26f  mov     ecx, [rsp+880h+var_860]
0x18008c273  call    ReleaseObjWriteLock
0x18008c278  mov     ecx, esi
0x18008c27a  call    CloseObjHandle
0x18008c27f  test    r14, r14
0x18008c282  jz      short loc_18008C2A4
0x18008c284  call    cs:__imp_GetProcessHeap
0x18008c28b  nop     dword ptr [rax+rax+00h]
0x18008c290  mov     r8, r14; lpMem
0x18008c293  xor     edx, edx; dwFlags
0x18008c295  mov     rcx, rax; hHeap
0x18008c298  call    cs:__imp_HeapFree
0x18008c29f  nop     dword ptr [rax+rax+00h]
0x18008c2a4  mov     eax, ebx
0x18008c2a6  mov     rcx, [rbp+780h+var_30]
0x18008c2ad  xor     rcx, rsp; StackCookie
0x18008c2b0  call    __security_check_cookie
0x18008c2b5  lea     r11, [rsp+880h+var_20]
0x18008c2bd  mov     rbx, [r11+38h]
0x18008c2c1  mov     rsi, [r11+40h]
0x18008c2c5  mov     rsp, r11
0x18008c2c8  pop     r14
0x18008c2ca  pop     r13
0x18008c2cc  pop     r12
0x18008c2ce  pop     rdi
0x18008c2cf  pop     rbp
0x18008c2d0  retn
```
