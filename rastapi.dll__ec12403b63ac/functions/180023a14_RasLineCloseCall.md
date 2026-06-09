# RasLineCloseCall

- ea: `0x180023a14`
- end: `0x180023e1b`
- name: `RasLineCloseCall`
- size: `1031`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: ``

## callers

- `0x1800023d4`
- `0x18000cb80`
- `0x180012b00`

## callees

- `0x18002251c`
- `0x180023a14`
- `0x180026c4c`
- `0x180027270`
- `0x180027888`
- `0x180027ba4`
- `0x180027d38`
- `0x180028078`
- `0x1800281f0`
- `0x180028b5c`
- `0x180028c70`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023dda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023dda`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023de8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023de8`
- `rtutils!TracePrintfA` at `0x180023afa`
- `rtutils!TracePrintfA` at `0x180023cef`
- `rtutils!TracePrintfA` at `0x180023d7e`
- `rtutils!TracePrintfA` at `0x180023afa`
- `rtutils!TracePrintfA` at `0x180023cef`
- `rtutils!TracePrintfA` at `0x180023d7e`

## string_xrefs

- `0x180023b2d`: `RasLineCloseCall: GetCallObjWithReadLock failed with error (0x%x)`
- `0x180023b48`: `RasLineCloseCall: GetCallObjWithReadLock failed with error (0x%x)`
- `0x180023bd3`: `RasLineCloseCall: AcquireObjWriteLock failed with error (0x%x)`
- `0x180023bee`: `RasLineCloseCall: AcquireObjWriteLock failed with error (0x%x)`
- `0x180023c24`: `RasLineClose: GetLineObjWithWriteLock failed with error (0x%x)`
- `0x180023c3f`: `RasLineClose: GetLineObjWithWriteLock failed with error (0x%x)`

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
  _QWORD *v8; // r14
  __int64 v9; // rax
  _DWORD *v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  HANDLE ProcessHeap; // rax
  unsigned int v16; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD *v17; // [rsp+28h] [rbp-D8h] BYREF
  LPVOID lpMem; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[2044]; // [rsp+54h] [rbp-ACh] BYREF

  lpMem = 0;
  v19 = 0;
  v17 = 0;
  v20 = 0;
  v16 = 0;
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  NDProxyHandle = GetLineHandleFromCallHandle(a1, &v16);
  v3 = NDProxyHandle;
  if ( NDProxyHandle )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( qword_18003EC40 )
      {
        v4 = L"RasLineCloseCall: GetLineHandleFromCallHandle failed with error (0x%x)";
LABEL_5:
        LOWORD(v21) = 0;
        FormatRRASErrorString(&v21, v4, NDProxyHandle);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v21);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "RasLineCloseCall: GetLineHandleFromCallHandle failed with error (0x%x)", NDProxyHandle);
    }
  }
  else
  {
    NDProxyHandle = GetCallObjWithReadLock(a1, &v17);
    v3 = NDProxyHandle;
    if ( NDProxyHandle )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( !qword_18003EC40 )
          return v3;
        v4 = L"RasLineCloseCall: GetCallObjWithReadLock failed with error (0x%x)";
        goto LABEL_5;
      }
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineCloseCall: GetCallObjWithReadLock failed with error (0x%x)", NDProxyHandle);
    }
    else
    {
      v5 = v17;
      v6 = *v17;
      NDProxyHandle = GetNDProxyHandle(v17, &v19);
      v3 = NDProxyHandle;
      if ( NDProxyHandle )
      {
        if ( gIsndpspEtwTracingAvailable )
        {
          if ( !qword_18003EC40 )
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
            if ( !qword_18003EC40 )
              return v3;
            v4 = L"RasLineCloseCall: AcquireObjWriteLock failed with error (0x%x)";
            goto LABEL_5;
          }
          if ( dwTraceId != -1 )
            TracePrintfA(dwTraceId, "RasLineCloseCall: AcquireObjWriteLock failed with error (0x%x)", NDProxyHandle);
        }
        else
        {
          NDProxyHandle = GetLineObjWithWriteLock(v16, &v20);
          v3 = NDProxyHandle;
          if ( NDProxyHandle )
          {
            if ( gIsndpspEtwTracingAvailable )
            {
              if ( !qword_18003EC40 )
                return v3;
              v4 = L"RasLineClose: GetLineObjWithWriteLock failed with error (0x%x)";
              goto LABEL_5;
            }
            if ( dwTraceId != -1 )
              TracePrintfA(dwTraceId, "RasLineClose: GetLineObjWithWriteLock failed with error (0x%x)", NDProxyHandle);
          }
          else
          {
            v7 = PrepareSyncRequest(0x7030104u, v5[1], 0x10u, &lpMem);
            v8 = lpMem;
            v3 = v7;
            if ( v7 )
            {
              ReleaseObjWriteLock(a1);
              ReleaseObjWriteLock(v16);
              if ( gIsndpspEtwTracingAvailable )
              {
                if ( qword_18003EC40 )
                {
                  LOWORD(v21) = 0;
                  FormatRRASErrorString(&v21, L"RasLineCloseCall: PrepareSyncRequest failed with error (0x%x)", v3);
                  ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(
                    gNdpspEtwContext,
                    qword_18003EC40,
                    &v21);
                }
              }
              else if ( dwTraceId != -1 )
              {
                TracePrintfA(dwTraceId, "RasLineCloseCall: PrepareSyncRequest failed with error (0x%x)", v3);
              }
            }
            else
            {
              v9 = v19;
              v10 = lpMem;
              *v5 = 1482184792;
              v8[7] = v9;
              v11 = SyncDriverRequest(0x8FFF23CC, v10);
              v3 = v11;
              if ( v11 )
              {
                if ( gIsndpspEtwTracingAvailable )
                {
                  if ( qword_18003EC40 )
                  {
                    LOWORD(v21) = 0;
                    FormatRRASErrorString(
                      &v21,
                      L"RasLineClose: SyncDriverRequest(OID_TAPI_CLOSE_CALL) failed with error (0x%x)",
                      v11);
                    ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(
                      gNdpspEtwContext,
                      qword_18003EC40,
                      &v21);
                  }
                }
                else if ( dwTraceId != -1 )
                {
                  TracePrintfA(
                    dwTraceId,
                    "RasLineClose: SyncDriverRequest(OID_TAPI_CLOSE_CALL) failed with error (0x%x)",
                    v11);
                }
              }
              if ( v6 == 1229144396 )
              {
                v12 = *((_QWORD *)v5 + 7);
                if ( v12 )
                  *(_QWORD *)(v12 + 48) = *((_QWORD *)v5 + 6);
                v13 = *((_QWORD *)v5 + 6);
                if ( v13 )
                  *(_QWORD *)(v13 + 56) = *((_QWORD *)v5 + 7);
                else
                  *(_QWORD *)(v20 + 24) = *((_QWORD *)v5 + 7);
              }
              ReleaseObjWriteLock(a1);
              ReleaseObjWriteLock(v16);
              CloseObjHandle(a1);
            }
            if ( v8 )
            {
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, v8);
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
0x180023a14  mov     [rsp-8+arg_8], rbx
0x180023a19  mov     [rsp-8+arg_10], rsi
0x180023a1e  push    rbp
0x180023a1f  push    rdi
0x180023a20  push    r12
0x180023a22  push    r13
0x180023a24  push    r14
0x180023a26  lea     rbp, [rsp-760h]
0x180023a2e  sub     rsp, 860h
0x180023a35  mov     rax, cs:__security_cookie
0x180023a3c  xor     rax, rsp
0x180023a3f  mov     [rbp+780h+var_30], rax
0x180023a46  xor     r13d, r13d
0x180023a49  mov     esi, ecx
0x180023a4b  lea     rcx, [rsp+880h+var_82C]; void *
0x180023a50  mov     [rsp+880h+lpMem], r13
0x180023a55  xor     edx, edx; Val
0x180023a57  mov     [rsp+880h+var_848], r13
0x180023a5c  mov     r8d, 7FCh; Size
0x180023a62  mov     [rsp+880h+var_858], r13
0x180023a67  mov     [rsp+880h+var_840], r13
0x180023a6c  mov     [rsp+880h+var_860], r13d
0x180023a71  mov     [rsp+880h+var_830], r13d
0x180023a76  call    memset_0
0x180023a7b  lea     rdx, [rsp+880h+var_860]
0x180023a80  mov     ecx, esi
0x180023a82  call    GetLineHandleFromCallHandle
0x180023a87  mov     ebx, eax
0x180023a89  test    eax, eax
0x180023a8b  jz      short loc_180023B05
0x180023a8d  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180023a94  jz      short loc_180023AE1
0x180023a96  cmp     cs:qword_18003EC40, r13
0x180023a9d  jz      loc_180023DEE
0x180023aa3  lea     rdx, aRaslinecloseca_7; "RasLineCloseCall: GetLineHandleFromCall"...
0x180023aaa  mov     r8d, eax
0x180023aad  mov     word ptr [rsp+880h+var_830], r13w
0x180023ab3  lea     rcx, [rsp+880h+var_830]
0x180023ab8  call    FormatRRASErrorString
0x180023abd  mov     rdx, cs:qword_18003EC40
0x180023ac4  lea     r8, [rsp+880h+var_830]
0x180023ac9  mov     rcx, cs:gNdpspEtwContext
0x180023ad0  mov     rax, cs:gNdpspTemplateFunc
0x180023ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023adc  jmp     loc_180023DEE
0x180023ae1  mov     ecx, cs:dwTraceId; dwTraceID
0x180023ae7  cmp     ecx, 0FFFFFFFFh
0x180023aea  jz      loc_180023DEE
0x180023af0  lea     rdx, aRaslinecloseca_3; "RasLineCloseCall: GetLineHandleFromCall"...
0x180023af7  mov     r8d, eax
0x180023afa  call    cs:__imp_TracePrintfA
0x180023b00  jmp     loc_180023DEE
0x180023b05  lea     rdx, [rsp+880h+var_858]
0x180023b0a  mov     ecx, esi
0x180023b0c  call    GetCallObjWithReadLock
0x180023b11  mov     ebx, eax
0x180023b13  test    eax, eax
0x180023b15  jz      short loc_180023B51
0x180023b17  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180023b1e  jz      short loc_180023B39
0x180023b20  cmp     cs:qword_18003EC40, r13
0x180023b27  jz      loc_180023DEE
0x180023b2d  lea     rdx, aRaslinecloseca_6; "RasLineCloseCall: GetCallObjWithReadLoc"...
0x180023b34  jmp     loc_180023AAA
0x180023b39  mov     ecx, cs:dwTraceId
0x180023b3f  cmp     ecx, 0FFFFFFFFh
0x180023b42  jz      loc_180023DEE
0x180023b48  lea     rdx, aRaslinecloseca; "RasLineCloseCall: GetCallObjWithReadLoc"...
0x180023b4f  jmp     short loc_180023AF7
0x180023b51  mov     rdi, [rsp+880h+var_858]
0x180023b56  lea     rdx, [rsp+880h+var_848]
0x180023b5b  mov     rcx, rdi
0x180023b5e  mov     r12d, [rdi]
0x180023b61  call    GetNDProxyHandle
0x180023b66  mov     ebx, eax
0x180023b68  test    eax, eax
0x180023b6a  jz      short loc_180023BA9
0x180023b6c  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180023b73  jz      short loc_180023B8E
0x180023b75  cmp     cs:qword_18003EC40, r13
0x180023b7c  jz      loc_180023DEE
0x180023b82  lea     rdx, aRaslinecloseca_2; "RasLineCloseCall: GetNDProxyHandle fail"...
0x180023b89  jmp     loc_180023AAA
0x180023b8e  mov     ecx, cs:dwTraceId
0x180023b94  cmp     ecx, 0FFFFFFFFh
0x180023b97  jz      loc_180023DEE
0x180023b9d  lea     rdx, aRaslinecloseca_4; "RasLineCloseCall: GetNDProxyHandle fail"...
0x180023ba4  jmp     loc_180023AF7
0x180023ba9  mov     ecx, esi
0x180023bab  call    ReleaseObjReadLock
0x180023bb0  mov     ecx, esi
0x180023bb2  call    AcquireObjWriteLock
0x180023bb7  mov     ebx, eax
0x180023bb9  test    eax, eax
0x180023bbb  jz      short loc_180023BFA
0x180023bbd  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180023bc4  jz      short loc_180023BDF
0x180023bc6  cmp     cs:qword_18003EC40, r13
0x180023bcd  jz      loc_180023DEE
0x180023bd3  lea     rdx, aRaslinecloseca_8; "RasLineCloseCall: AcquireObjWriteLock f"...
0x180023bda  jmp     loc_180023AAA
0x180023bdf  mov     ecx, cs:dwTraceId
0x180023be5  cmp     ecx, 0FFFFFFFFh
0x180023be8  jz      loc_180023DEE
0x180023bee  lea     rdx, aRaslinecloseca_1; "RasLineCloseCall: AcquireObjWriteLock f"...
0x180023bf5  jmp     loc_180023AF7
0x180023bfa  mov     ecx, [rsp+880h+var_860]
0x180023bfe  lea     rdx, [rsp+880h+var_840]
0x180023c03  call    GetLineObjWithWriteLock
0x180023c08  mov     ebx, eax
0x180023c0a  test    eax, eax
0x180023c0c  jz      short loc_180023C4B
0x180023c0e  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180023c15  jz      short loc_180023C30
0x180023c17  cmp     cs:qword_18003EC40, r13
0x180023c1e  jz      loc_180023DEE
0x180023c24  lea     rdx, aRaslinecloseGe_0; "RasLineClose: GetLineObjWithWriteLock f"...
0x180023c2b  jmp     loc_180023AAA
0x180023c30  mov     ecx, cs:dwTraceId
0x180023c36  cmp     ecx, 0FFFFFFFFh
0x180023c39  jz      loc_180023DEE
0x180023c3f  lea     rdx, aRaslinecloseGe; "RasLineClose: GetLineObjWithWriteLock f"...
0x180023c46  jmp     loc_180023AF7
0x180023c4b  mov     edx, [rdi+4]
0x180023c4e  lea     r9, [rsp+880h+lpMem]
0x180023c53  mov     r8d, 10h
0x180023c59  mov     ecx, 7030104h
0x180023c5e  call    PrepareSyncRequest
0x180023c63  mov     r14, [rsp+880h+lpMem]
0x180023c68  mov     ebx, eax
0x180023c6a  test    eax, eax
0x180023c6c  jz      loc_180023CFA
0x180023c72  mov     ecx, esi
0x180023c74  call    ReleaseObjWriteLock
0x180023c79  mov     ecx, [rsp+880h+var_860]
0x180023c7d  call    ReleaseObjWriteLock
0x180023c82  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180023c89  jz      short loc_180023CD6
0x180023c8b  cmp     cs:qword_18003EC40, r13
0x180023c92  jz      loc_180023DD5
0x180023c98  mov     r8d, ebx
0x180023c9b  mov     word ptr [rsp+880h+var_830], r13w
0x180023ca1  lea     rdx, aRaslinecloseca_0; "RasLineCloseCall: PrepareSyncRequest fa"...
0x180023ca8  lea     rcx, [rsp+880h+var_830]
0x180023cad  call    FormatRRASErrorString
0x180023cb2  mov     rdx, cs:qword_18003EC40
0x180023cb9  lea     r8, [rsp+880h+var_830]
0x180023cbe  mov     rcx, cs:gNdpspEtwContext
0x180023cc5  mov     rax, cs:gNdpspTemplateFunc
0x180023ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cd1  jmp     loc_180023DD5
0x180023cd6  mov     ecx, cs:dwTraceId; dwTraceID
0x180023cdc  cmp     ecx, 0FFFFFFFFh
0x180023cdf  jz      loc_180023DD5
0x180023ce5  mov     r8d, ebx
0x180023ce8  lea     rdx, aRaslinecloseca_5; "RasLineCloseCall: PrepareSyncRequest fa"...
0x180023cef  call    cs:__imp_TracePrintfA
0x180023cf5  jmp     loc_180023DD5
0x180023cfa  mov     rax, [rsp+880h+var_848]
0x180023cff  mov     rdx, r14; lpInBuffer
0x180023d02  mov     dword ptr [rdi], 58585858h
0x180023d08  mov     ecx, 8FFF23CCh; dwIoControlCode
0x180023d0d  mov     [r14+38h], rax
0x180023d11  call    SyncDriverRequest
0x180023d16  mov     ebx, eax
0x180023d18  test    eax, eax
0x180023d1a  jz      short loc_180023D84
0x180023d1c  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180023d23  jz      short loc_180023D69
0x180023d25  cmp     cs:qword_18003EC40, r13
0x180023d2c  jz      short loc_180023D84
0x180023d2e  mov     r8d, eax
0x180023d31  mov     word ptr [rsp+880h+var_830], r13w
0x180023d37  lea     rdx, aRaslinecloseSy_1; "RasLineClose: SyncDriverRequest(OID_TAP"...
0x180023d3e  lea     rcx, [rsp+880h+var_830]
0x180023d43  call    FormatRRASErrorString
0x180023d48  mov     rdx, cs:qword_18003EC40
0x180023d4f  lea     r8, [rsp+880h+var_830]
0x180023d54  mov     rcx, cs:gNdpspEtwContext
0x180023d5b  mov     rax, cs:gNdpspTemplateFunc
0x180023d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d67  jmp     short loc_180023D84
0x180023d69  mov     ecx, cs:dwTraceId; dwTraceID
0x180023d6f  cmp     ecx, 0FFFFFFFFh
0x180023d72  jz      short loc_180023D84
0x180023d74  mov     r8d, eax
0x180023d77  lea     rdx, aRaslinecloseSy_2; "RasLineClose: SyncDriverRequest(OID_TAP"...
0x180023d7e  call    cs:__imp_TracePrintfA
0x180023d84  cmp     r12d, 4943414Ch
0x180023d8b  jnz     short loc_180023DBE
0x180023d8d  mov     rcx, [rdi+38h]
0x180023d91  test    rcx, rcx
0x180023d94  jz      short loc_180023D9E
0x180023d96  mov     rax, [rdi+30h]
0x180023d9a  mov     [rcx+30h], rax
0x180023d9e  mov     rcx, [rdi+30h]
0x180023da2  test    rcx, rcx
0x180023da5  jz      short loc_180023DB1
0x180023da7  mov     rax, [rdi+38h]
0x180023dab  mov     [rcx+38h], rax
0x180023daf  jmp     short loc_180023DBE
0x180023db1  mov     rax, [rsp+880h+var_840]
0x180023db6  mov     rcx, [rdi+38h]
0x180023dba  mov     [rax+18h], rcx
0x180023dbe  mov     ecx, esi
0x180023dc0  call    ReleaseObjWriteLock
0x180023dc5  mov     ecx, [rsp+880h+var_860]
0x180023dc9  call    ReleaseObjWriteLock
0x180023dce  mov     ecx, esi
0x180023dd0  call    CloseObjHandle
0x180023dd5  test    r14, r14
0x180023dd8  jz      short loc_180023DEE
0x180023dda  call    cs:__imp_GetProcessHeap
0x180023de0  mov     r8, r14; lpMem
0x180023de3  xor     edx, edx; dwFlags
0x180023de5  mov     rcx, rax; hHeap
0x180023de8  call    cs:__imp_HeapFree
0x180023dee  mov     eax, ebx
0x180023df0  mov     rcx, [rbp+780h+var_30]
0x180023df7  xor     rcx, rsp; StackCookie
0x180023dfa  call    __security_check_cookie
0x180023dff  lea     r11, [rsp+880h+var_20]
0x180023e07  mov     rbx, [r11+38h]
0x180023e0b  mov     rsi, [r11+40h]
0x180023e0f  mov     rsp, r11
0x180023e12  pop     r14
0x180023e14  pop     r13
0x180023e16  pop     r12
0x180023e18  pop     rdi
0x180023e19  pop     rbp
0x180023e1a  retn
```
