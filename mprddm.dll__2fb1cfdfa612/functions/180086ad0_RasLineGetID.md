# RasLineGetID

- ea: `0x180086ad0`
- end: `0x180087068`
- name: `RasLineGetID`
- size: `1432`
- prototype: `__int64 __fastcall(int, int, int, int, wchar_t *String1, void *)`
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x180026e38`
- `0x180041750`

## callees

- `0x180002ba6`
- `0x180071cec`
- `0x18008490c`
- `0x180086ad0`
- `0x1800884f8`
- `0x180088b1c`
- `0x1800892bc`
- `0x1800895e4`
- `0x18008a408`
- `0x18008c5e6`
- `0x18008c5f2`
- `0x18008c60a`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180086e1a`
- `KERNEL32!GetProcessHeap` at `0x180086e1a`
- `KERNEL32!HeapFree` at `0x180086e28`
- `KERNEL32!HeapFree` at `0x180086e28`
- `rtutils!TracePrintfA` at `0x180086bdb`
- `rtutils!TracePrintfA` at `0x180086c48`
- `rtutils!TracePrintfA` at `0x180086d24`
- `rtutils!TracePrintfA` at `0x180086d7b`
- `rtutils!TracePrintfA` at `0x180086e8f`
- `rtutils!TracePrintfA` at `0x180086f26`
- `rtutils!TracePrintfA` at `0x18008705d`
- `rtutils!TracePrintfA` at `0x180086bdb`
- `rtutils!TracePrintfA` at `0x180086c48`
- `rtutils!TracePrintfA` at `0x180086d24`
- `rtutils!TracePrintfA` at `0x180086d7b`
- `rtutils!TracePrintfA` at `0x180086e8f`
- `rtutils!TracePrintfA` at `0x180086f26`
- `rtutils!TracePrintfA` at `0x18008705d`

## string_xrefs

- `0x180086bd4`: `RasLineGetID: GetLineObjWithReadLock failed with error (0x%x)`
- `0x180086b8a`: `RasLineGetID: GetLineObjWithReadLock failed with error (0x%x)`
- `0x180086d1d`: `RasLineGetID: GetCallObjWithReadLock failed with error (0x%x)`
- `0x180086cd3`: `RasLineGetID: GetCallObjWithReadLock failed with error (0x%x)`

## pseudocode

```c
__int64 __fastcall RasLineGetID(
        unsigned int a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        wchar_t *String1,
        unsigned int *a6)
{
  unsigned int v6; // r12d
  wchar_t *v7; // r15
  char *v10; // rbx
  __int64 v11; // rdi
  unsigned int LineObjWithReadLock; // eax
  unsigned int v13; // esi
  __int64 v14; // rdx
  const wchar_t *v15; // r8
  unsigned int *v16; // rbx
  unsigned int v17; // eax
  __int64 v18; // rdx
  const wchar_t *v19; // r8
  unsigned int v20; // eax
  unsigned int v21; // r12d
  unsigned int v22; // eax
  HANDLE ProcessHeap; // rax
  unsigned int NDProxyHandle; // eax
  const wchar_t *v26; // rdx
  unsigned int v27; // ecx
  __int64 v28; // r8
  char *v29; // rdx
  char *v30; // rcx
  LPVOID lpMem; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int *v33; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int *v34; // [rsp+38h] [rbp-C8h] BYREF
  int v35; // [rsp+40h] [rbp-C0h] BYREF
  char v36[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v6 = a1;
  v7 = String1;
  v10 = 0;
  lpMem = 0;
  v34 = 0;
  v11 = -1;
  v33 = 0;
  do
    ++v11;
  while ( String1[v11] );
  v35 = 0;
  memset_0(v36, 0, sizeof(v36));
  if ( a4 != 1 )
  {
    if ( a4 != 4 )
    {
LABEL_71:
      v13 = 87;
      if ( gIsndpspEtwTracingAvailable )
      {
        v14 = *((_QWORD *)&xmmword_1800C9BE0 + 1);
        if ( *((_QWORD *)&xmmword_1800C9BE0 + 1) )
        {
          v15 = L"RasLineGetID: Invalid input parameters";
          goto LABEL_8;
        }
        goto LABEL_44;
      }
      if ( dwTraceId == -1 )
        goto LABEL_44;
      TracePrintfA(dwTraceId, "RasLineGetID: Invalid input parameters");
      goto LABEL_40;
    }
    v17 = GetCallObjWithReadLock(a3, &v33);
    v13 = v17;
    if ( v17 )
    {
      if ( !gIsndpspEtwTracingAvailable )
      {
        if ( dwTraceId != -1 )
          TracePrintfA(dwTraceId, "RasLineGetID: GetCallObjWithReadLock failed with error (0x%x)", v17);
        goto LABEL_42;
      }
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v35) = 0;
        FormatRRASErrorString(&v35, L"RasLineGetID: GetCallObjWithReadLock failed with error (0x%x)", v17);
        v18 = xmmword_1800C9BE0;
        v19 = (const wchar_t *)&v35;
LABEL_24:
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(gNdpspEtwContext, v18, v19);
        goto LABEL_42;
      }
      goto LABEL_42;
    }
    v20 = *a6;
    a6[1] = 28;
    if ( v20 < 0x1C )
    {
      v13 = 122;
      if ( !gIsndpspEtwTracingAvailable )
      {
        if ( dwTraceId != -1 )
          TracePrintfA(dwTraceId, "RasLineGetID: Insufficient buffer passed by caller");
        goto LABEL_42;
      }
      v18 = *((_QWORD *)&xmmword_1800C9BE0 + 1);
      if ( *((_QWORD *)&xmmword_1800C9BE0 + 1) )
      {
        v19 = L"RasLineGetID: Insufficient buffer passed by caller";
        goto LABEL_24;
      }
LABEL_42:
      if ( v33 )
        ReleaseObjReadLock(a3);
      goto LABEL_44;
    }
    if ( !v33 )
      return v13;
    v21 = v11 + 1;
    v22 = PrepareSyncRequest(117637395, v33[1], v20 + 52 + 2 * ((_DWORD)v11 + 1), &lpMem);
    v13 = v22;
    if ( v22 )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( (_QWORD)xmmword_1800C9BE0 )
        {
          LOWORD(v35) = 0;
          FormatRRASErrorString(&v35, L"RasLineGetID: PrepareSyncRequest failed with error (0x%x)", v22);
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v35);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "RasLineGetID: PrepareSyncRequest failed with error (0x%x)", v22);
      }
      v10 = (char *)lpMem;
      goto LABEL_39;
    }
    v10 = (char *)lpMem;
    *((_DWORD *)lpMem + 16) = 0;
    NDProxyHandle = GetNDProxyHandle(v33, v10 + 72);
    v13 = NDProxyHandle;
    if ( NDProxyHandle )
    {
      if ( !gIsndpspEtwTracingAvailable )
      {
        if ( dwTraceId != -1 )
          TracePrintfA(dwTraceId, "RasLineGetID: GetNDProxyHandle failed with error (0x%x)", NDProxyHandle);
        goto LABEL_39;
      }
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        v26 = L"RasLineGetID: GetNDProxyHandle failed with error (0x%x)";
LABEL_53:
        LOWORD(v35) = 0;
        FormatRRASErrorString(&v35, v26, NDProxyHandle);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v35);
      }
    }
    else
    {
      *((_DWORD *)v10 + 21) = v21;
      *((_DWORD *)v10 + 20) = 4;
      v27 = *a6 + 48;
      v28 = v21;
      *((_DWORD *)v10 + 22) = v27;
      *((_DWORD *)v10 + 23) = *a6;
      *((_DWORD *)v10 + 25) = 24;
      *((_DWORD *)v10 + 24) = 24;
      *(_QWORD *)(v10 + 108) = 0;
      *((_DWORD *)v10 + 26) = 0;
      if ( (_DWORD)v11 != -1 )
      {
        v29 = &v10[v27 + 48];
        if ( v21 <= 0x7FFFFFFEuLL )
        {
          do
          {
            if ( !*v7 )
              break;
            *(_WORD *)v29 = *v7++;
            v29 += 2;
            --v28;
          }
          while ( v28 );
          v30 = v29 - 2;
          if ( v28 )
            v30 = v29;
          *(_WORD *)v30 = 0;
        }
        else
        {
          *(_WORD *)v29 = 0;
        }
      }
      NDProxyHandle = SyncDriverRequest(0x8FFF23C8, v10);
      v13 = NDProxyHandle;
      if ( !NDProxyHandle )
      {
        memcpy_0(a6, v10 + 92, *((unsigned int *)v10 + 25));
        goto LABEL_39;
      }
      if ( !gIsndpspEtwTracingAvailable )
      {
        if ( dwTraceId != -1 )
          TracePrintfA(
            dwTraceId,
            "RasLineGetID: SyncDriverRequest(OID_TAPI_GET_ID) failed with error (0x%x)",
            NDProxyHandle);
        goto LABEL_39;
      }
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        v26 = L"RasLineGetID: SyncDriverRequest(OID_TAPI_GET_ID) failed with error (0x%x)";
        goto LABEL_53;
      }
    }
LABEL_39:
    v6 = a1;
LABEL_40:
    if ( v10 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v10);
    }
    goto LABEL_42;
  }
  LineObjWithReadLock = GetLineObjWithReadLock(v6, &v34);
  v13 = LineObjWithReadLock;
  if ( LineObjWithReadLock )
  {
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineGetID: GetLineObjWithReadLock failed with error (0x%x)", LineObjWithReadLock);
      goto LABEL_44;
    }
    if ( (_QWORD)xmmword_1800C9BE0 )
    {
      LOWORD(v35) = 0;
      FormatRRASErrorString(&v35, L"RasLineGetID: GetLineObjWithReadLock failed with error (0x%x)", LineObjWithReadLock);
      v14 = xmmword_1800C9BE0;
      v15 = (const wchar_t *)&v35;
LABEL_8:
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(gNdpspEtwContext, v14, v15);
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  if ( wcscmp_0(String1, L"LineGuid") )
    goto LABEL_71;
  a6[1] = 48;
  if ( *a6 >= 0x30 )
  {
    v16 = v34;
    a6[2] = 48;
    a6[3] = 1;
    a6[4] = 24;
    a6[5] = 24;
    memmove_0(a6 + 6, v16 + 10, 0x10u);
    a6[10] = v16[14];
    *((_BYTE *)a6 + 44) = 0;
  }
  else
  {
    v13 = 122;
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineGetID: Insufficient buffer passed by caller");
      goto LABEL_44;
    }
    v14 = *((_QWORD *)&xmmword_1800C9BE0 + 1);
    if ( *((_QWORD *)&xmmword_1800C9BE0 + 1) )
    {
      v15 = L"RasLineGetID: Insufficient buffer passed by caller";
      goto LABEL_8;
    }
  }
LABEL_44:
  if ( v34 )
    ReleaseObjReadLock(v6);
  return v13;
}

```

## disassembly

```asm
0x180086ad0  mov     [rsp-8+arg_8], rbx
0x180086ad5  push    rbp
0x180086ad6  push    rsi
0x180086ad7  push    rdi
0x180086ad8  push    r12
0x180086ada  push    r13
0x180086adc  push    r14
0x180086ade  push    r15
0x180086ae0  lea     rbp, [rsp-750h]
0x180086ae8  sub     rsp, 850h
0x180086aef  mov     rax, cs:__security_cookie
0x180086af6  xor     rax, rsp
0x180086af9  mov     [rbp+780h+var_40], rax
0x180086b00  mov     r14, [rbp+780h+arg_28]
0x180086b07  mov     r12d, ecx
0x180086b0a  mov     r15, [rbp+780h+String1]
0x180086b11  mov     esi, r9d
0x180086b14  mov     [rsp+880h+var_860], ecx
0x180086b18  mov     r13d, r8d
0x180086b1b  xor     ecx, ecx
0x180086b1d  mov     ebx, ecx
0x180086b1f  mov     [rsp+880h+lpMem], rcx
0x180086b24  mov     [rsp+880h+var_848], rcx
0x180086b29  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180086b2d  mov     [rsp+880h+var_850], rcx
0x180086b32  inc     rdi
0x180086b35  cmp     [r15+rdi*2], cx
0x180086b3a  jnz     short loc_180086B32
0x180086b3c  mov     [rsp+880h+var_840], ecx
0x180086b40  xor     edx, edx; Val
0x180086b42  lea     rcx, [rsp+880h+var_83C]; void *
0x180086b47  mov     r8d, 7FCh; Size
0x180086b4d  call    memset_0
0x180086b52  cmp     esi, 1
0x180086b55  jnz     loc_180086C9B
0x180086b5b  lea     rdx, [rsp+880h+var_848]
0x180086b60  mov     ecx, r12d
0x180086b63  call    GetLineObjWithReadLock
0x180086b68  xor     ecx, ecx
0x180086b6a  mov     esi, eax
0x180086b6c  test    eax, eax
0x180086b6e  jz      short loc_180086BE6
0x180086b70  cmp     cs:gIsndpspEtwTracingAvailable, ecx
0x180086b76  jz      short loc_180086BC2
0x180086b78  cmp     qword ptr cs:xmmword_1800C9BE0, rcx
0x180086b7f  jz      loc_180086E3E
0x180086b85  mov     word ptr [rsp+880h+var_840], cx
0x180086b8a  lea     rdx, aRaslinegetidGe; "RasLineGetID: GetLineObjWithReadLock fa"...
0x180086b91  lea     rcx, [rsp+880h+var_840]
0x180086b96  mov     r8d, eax
0x180086b99  call    FormatRRASErrorString
0x180086b9e  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180086ba5  lea     r8, [rsp+880h+var_840]
0x180086baa  mov     rcx, cs:gNdpspEtwContext
0x180086bb1  mov     rax, cs:gNdpspTemplateFunc
0x180086bb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086bbd  jmp     loc_180086E3E
0x180086bc2  mov     ecx, cs:dwTraceId; dwTraceID
0x180086bc8  cmp     ecx, 0FFFFFFFFh
0x180086bcb  jz      loc_180086E3E
0x180086bd1  mov     r8d, eax
0x180086bd4  lea     rdx, aRaslinegetidGe_3; "RasLineGetID: GetLineObjWithReadLock fa"...
0x180086bdb  call    cs:__imp_TracePrintfA
0x180086be1  jmp     loc_180086E3E
0x180086be6  lea     rdx, aLineguid; "LineGuid"
0x180086bed  mov     rcx, r15; String1
0x180086bf0  call    wcscmp_0
0x180086bf5  xor     ecx, ecx
0x180086bf7  test    eax, eax
0x180086bf9  jnz     loc_18008701E
0x180086bff  lea     eax, [rcx+30h]
0x180086c02  mov     [r14+4], eax
0x180086c06  cmp     [r14], eax
0x180086c09  jnb     short loc_180086C53
0x180086c0b  cmp     cs:gIsndpspEtwTracingAvailable, ecx
0x180086c11  lea     esi, [rcx+7Ah]
0x180086c14  jz      short loc_180086C32
0x180086c16  mov     rdx, qword ptr cs:xmmword_1800C9BE0+8
0x180086c1d  test    rdx, rdx
0x180086c20  jz      loc_180086E3E
0x180086c26  lea     r8, aRaslinegetidIn_0; "RasLineGetID: Insufficient buffer passe"...
0x180086c2d  jmp     loc_180086BAA
0x180086c32  mov     ecx, cs:dwTraceId; dwTraceID
0x180086c38  cmp     ecx, 0FFFFFFFFh
0x180086c3b  jz      loc_180086E3E
0x180086c41  lea     rdx, aRaslinegetidIn; "RasLineGetID: Insufficient buffer passe"...
0x180086c48  call    cs:__imp_TracePrintfA
0x180086c4e  jmp     loc_180086E3E
0x180086c53  mov     rbx, [rsp+880h+var_848]
0x180086c58  lea     rcx, [r14+18h]; void *
0x180086c5c  mov     [r14+8], eax
0x180086c60  mov     r8d, 10h; Size
0x180086c66  lea     eax, [r14+18h]
0x180086c6a  mov     dword ptr [r14+0Ch], 1
0x180086c72  sub     eax, r14d
0x180086c75  mov     dword ptr [r14+10h], 18h
0x180086c7d  lea     rdx, [rbx+28h]; Src
0x180086c81  mov     [r14+14h], eax
0x180086c85  call    memmove_0
0x180086c8a  mov     eax, [rbx+38h]
0x180086c8d  mov     [r14+28h], eax
0x180086c91  mov     byte ptr [r14+2Ch], 0
0x180086c96  jmp     loc_180086E3E
0x180086c9b  cmp     esi, 4
0x180086c9e  jnz     loc_18008701C
0x180086ca4  lea     rdx, [rsp+880h+var_850]
0x180086ca9  mov     ecx, r13d
0x180086cac  call    GetCallObjWithReadLock
0x180086cb1  xor     ecx, ecx
0x180086cb3  mov     esi, eax
0x180086cb5  test    eax, eax
0x180086cb7  jz      short loc_180086D2F
0x180086cb9  cmp     cs:gIsndpspEtwTracingAvailable, ecx
0x180086cbf  jz      short loc_180086D0B
0x180086cc1  cmp     qword ptr cs:xmmword_1800C9BE0, rcx
0x180086cc8  jz      loc_180086E2E
0x180086cce  mov     word ptr [rsp+880h+var_840], cx
0x180086cd3  lea     rdx, aRaslinegetidGe_0; "RasLineGetID: GetCallObjWithReadLock fa"...
0x180086cda  lea     rcx, [rsp+880h+var_840]
0x180086cdf  mov     r8d, eax
0x180086ce2  call    FormatRRASErrorString
0x180086ce7  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180086cee  lea     r8, [rsp+880h+var_840]
0x180086cf3  mov     rcx, cs:gNdpspEtwContext
0x180086cfa  mov     rax, cs:gNdpspTemplateFunc
0x180086d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086d06  jmp     loc_180086E2E
0x180086d0b  mov     ecx, cs:dwTraceId; dwTraceID
0x180086d11  cmp     ecx, 0FFFFFFFFh
0x180086d14  jz      loc_180086E2E
0x180086d1a  mov     r8d, eax
0x180086d1d  lea     rdx, aRaslinegetidGe_2; "RasLineGetID: GetCallObjWithReadLock fa"...
0x180086d24  call    cs:__imp_TracePrintfA
0x180086d2a  jmp     loc_180086E2E
0x180086d2f  mov     eax, [r14]
0x180086d32  mov     dword ptr [r14+4], 1Ch
0x180086d3a  cmp     eax, 1Ch
0x180086d3d  jnb     short loc_180086D86
0x180086d3f  cmp     cs:gIsndpspEtwTracingAvailable, ecx
0x180086d45  mov     esi, 7Ah ; 'z'
0x180086d4a  jz      short loc_180086D65
0x180086d4c  mov     rdx, qword ptr cs:xmmword_1800C9BE0+8
0x180086d53  test    rdx, rdx
0x180086d56  jz      loc_180086E2E
0x180086d5c  lea     r8, aRaslinegetidIn_0; "RasLineGetID: Insufficient buffer passe"...
0x180086d63  jmp     short loc_180086CF3
0x180086d65  mov     ecx, cs:dwTraceId; dwTraceID
0x180086d6b  cmp     ecx, 0FFFFFFFFh
0x180086d6e  jz      loc_180086E2E
0x180086d74  lea     rdx, aRaslinegetidIn; "RasLineGetID: Insufficient buffer passe"...
0x180086d7b  call    cs:__imp_TracePrintfA
0x180086d81  jmp     loc_180086E2E
0x180086d86  mov     rdx, [rsp+880h+var_850]
0x180086d8b  test    rdx, rdx
0x180086d8e  jz      loc_180086E4E
0x180086d94  mov     edx, [rdx+4]
0x180086d97  lea     r8d, [rax+34h]
0x180086d9b  lea     r12d, [rdi+1]
0x180086d9f  mov     ecx, 7030113h
0x180086da4  lea     r8d, [r8+r12*2]
0x180086da8  lea     r9, [rsp+880h+lpMem]
0x180086dad  call    PrepareSyncRequest
0x180086db2  xor     ecx, ecx
0x180086db4  mov     esi, eax
0x180086db6  test    eax, eax
0x180086db8  jz      loc_180086E9A
0x180086dbe  cmp     cs:gIsndpspEtwTracingAvailable, ecx
0x180086dc4  jz      loc_180086E7A
0x180086dca  cmp     qword ptr cs:xmmword_1800C9BE0, rcx
0x180086dd1  jz      short loc_180086E0B
0x180086dd3  mov     word ptr [rsp+880h+var_840], cx
0x180086dd8  lea     rdx, aRaslinegetidPr_0; "RasLineGetID: PrepareSyncRequest failed"...
0x180086ddf  lea     rcx, [rsp+880h+var_840]
0x180086de4  mov     r8d, eax
0x180086de7  call    FormatRRASErrorString
0x180086dec  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180086df3  lea     r8, [rsp+880h+var_840]
0x180086df8  mov     rcx, cs:gNdpspEtwContext
0x180086dff  mov     rax, cs:gNdpspTemplateFunc
0x180086e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086e0b  mov     rbx, [rsp+880h+lpMem]
0x180086e10  mov     r12d, [rsp+880h+var_860]
0x180086e15  test    rbx, rbx
0x180086e18  jz      short loc_180086E2E
0x180086e1a  call    cs:__imp_GetProcessHeap
0x180086e20  mov     r8, rbx; lpMem
0x180086e23  xor     edx, edx; dwFlags
0x180086e25  mov     rcx, rax; hHeap
0x180086e28  call    cs:__imp_HeapFree
0x180086e2e  cmp     [rsp+880h+var_850], 0
0x180086e34  jz      short loc_180086E3E
0x180086e36  mov     ecx, r13d
0x180086e39  call    ReleaseObjReadLock
0x180086e3e  cmp     [rsp+880h+var_848], 0
0x180086e44  jz      short loc_180086E4E
0x180086e46  mov     ecx, r12d
0x180086e49  call    ReleaseObjReadLock
0x180086e4e  mov     eax, esi
0x180086e50  mov     rcx, [rbp+780h+var_40]
0x180086e57  xor     rcx, rsp; StackCookie
0x180086e5a  call    __security_check_cookie
0x180086e5f  mov     rbx, [rsp+880h+arg_8]
0x180086e67  add     rsp, 850h
0x180086e6e  pop     r15
0x180086e70  pop     r14
0x180086e72  pop     r13
0x180086e74  pop     r12
0x180086e76  pop     rdi
0x180086e77  pop     rsi
0x180086e78  pop     rbp
0x180086e79  retn
0x180086e7a  mov     ecx, cs:dwTraceId; dwTraceID
0x180086e80  cmp     ecx, 0FFFFFFFFh
0x180086e83  jz      short loc_180086E0B
0x180086e85  mov     r8d, eax
0x180086e88  lea     rdx, aRaslinegetidPr; "RasLineGetID: PrepareSyncRequest failed"...
0x180086e8f  call    cs:__imp_TracePrintfA
0x180086e95  jmp     loc_180086E0B
0x180086e9a  mov     rbx, [rsp+880h+lpMem]
0x180086e9f  mov     [rbx+40h], ecx
0x180086ea2  lea     rdx, [rbx+48h]
0x180086ea6  mov     rcx, [rsp+880h+var_850]
0x180086eab  call    GetNDProxyHandle
0x180086eb0  mov     esi, eax
0x180086eb2  test    eax, eax
0x180086eb4  jz      short loc_180086F31
0x180086eb6  xor     r12d, r12d
0x180086eb9  cmp     cs:gIsndpspEtwTracingAvailable, r12d
0x180086ec0  jz      short loc_180086F0D
0x180086ec2  cmp     qword ptr cs:xmmword_1800C9BE0, r12
0x180086ec9  jz      loc_180086E10
0x180086ecf  lea     rdx, aRaslinegetidGe_1; "RasLineGetID: GetNDProxyHandle failed w"...
0x180086ed6  mov     r8d, eax
0x180086ed9  mov     word ptr [rsp+880h+var_840], r12w
0x180086edf  lea     rcx, [rsp+880h+var_840]
0x180086ee4  call    FormatRRASErrorString
0x180086ee9  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180086ef0  lea     r8, [rsp+880h+var_840]
0x180086ef5  mov     rcx, cs:gNdpspEtwContext
0x180086efc  mov     rax, cs:gNdpspTemplateFunc
0x180086f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086f08  jmp     loc_180086E10
0x180086f0d  mov     ecx, cs:dwTraceId; dwTraceID
0x180086f13  cmp     ecx, 0FFFFFFFFh
0x180086f16  jz      loc_180086E10
0x180086f1c  lea     rdx, aRaslinegetidGe_4; "RasLineGetID: GetNDProxyHandle failed w"...
0x180086f23  mov     r8d, eax
0x180086f26  call    cs:__imp_TracePrintfA
0x180086f2c  jmp     loc_180086E10
0x180086f31  mov     [rbx+54h], r12d
0x180086f35  mov     dword ptr [rbx+50h], 4
0x180086f3c  mov     ecx, [r14]
0x180086f3f  add     ecx, 30h ; '0'
0x180086f42  mov     r8d, r12d
0x180086f45  mov     [rbx+58h], ecx
0x180086f48  xor     r12d, r12d
0x180086f4b  mov     eax, [r14]
0x180086f4e  mov     [rbx+5Ch], eax
0x180086f51  xor     eax, eax
0x180086f53  mov     dword ptr [rbx+64h], 18h
0x180086f5a  mov     dword ptr [rbx+60h], 18h
0x180086f61  mov     [rbx+6Ch], rax
0x180086f65  mov     [rbx+68h], eax
0x180086f68  test    r8, r8
0x180086f6b  jz      short loc_180086FB7
0x180086f6d  mov     edx, ecx
0x180086f6f  add     rdx, 30h ; '0'
0x180086f73  add     rdx, rbx
0x180086f76  cmp     r8, 7FFFFFFFh
0x180086f7d  ja      short loc_180086F88
0x180086f7f  cmp     r8, 7FFFFFFEh
0x180086f86  jbe     short loc_180086F8E
0x180086f88  mov     [rdx], r12w
0x180086f8c  jmp     short loc_180086FB7
0x180086f8e  movzx   eax, word ptr [r15]
0x180086f92  test    ax, ax
0x180086f95  jz      short loc_180086FA8
0x180086f97  mov     [rdx], ax
0x180086f9a  add     r15, 2
0x180086f9e  add     rdx, 2
0x180086fa2  sub     r8, 1
0x180086fa6  jnz     short loc_180086F8E
0x180086fa8  test    r8, r8
0x180086fab  lea     rcx, [rdx-2]
0x180086faf  cmovnz  rcx, rdx
0x180086fb3  mov     [rcx], r12w
0x180086fb7  mov     rdx, rbx; lpInBuffer
0x180086fba  mov     ecx, 8FFF23C8h; dwIoControlCode
0x180086fbf  call    SyncDriverRequest
0x180086fc4  mov     esi, eax
0x180086fc6  test    eax, eax
0x180086fc8  jz      short loc_180087007
0x180086fca  cmp     cs:gIsndpspEtwTracingAvailable, r12d
0x180086fd1  jz      short loc_180086FEC
0x180086fd3  cmp     qword ptr cs:xmmword_1800C9BE0, r12
0x180086fda  jz      loc_180086E10
0x180086fe0  lea     rdx, aRaslinegetidSy; "RasLineGetID: SyncDriverRequest(OID_TAP"...
0x180086fe7  jmp     loc_180086ED6
0x180086fec  mov     ecx, cs:dwTraceId
0x180086ff2  cmp     ecx, 0FFFFFFFFh
  ... truncated ...
```
