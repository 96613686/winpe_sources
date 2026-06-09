# RasLineMakeCall

- ea: `0x1800257e4`
- end: `0x180025e31`
- name: `RasLineMakeCall`
- size: `1613`
- prototype: `__int64 __fastcall(unsigned int, const char *, __int64, __int64, _DWORD *, unsigned int *, _DWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18000f810`

## callees

- `0x180020c98`
- `0x180022314`
- `0x1800257e4`
- `0x180027a10`
- `0x180027f2c`
- `0x1800281f0`
- `0x1800287d8`
- `0x180028b5c`
- `0x180029130`
- `0x180029266`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `msvcrt!mbstowcs_s` at `0x180025a21`
- `msvcrt!mbstowcs_s` at `0x180025a21`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002595d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002595d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002594b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025c24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025c50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002594b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025c24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025c50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025c32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025c5e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025c32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025c5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025c15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025c3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025c15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025c3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025c06`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025c06`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025c1e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025c1e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180025da9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180025da9`
- `rtutils!TracePrintfA` at `0x1800258c2`
- `rtutils!TracePrintfA` at `0x18002593d`
- `rtutils!TracePrintfA` at `0x1800259c4`
- `rtutils!TracePrintfA` at `0x180025ada`
- `rtutils!TracePrintfA` at `0x180025b94`
- `rtutils!TracePrintfA` at `0x180025bef`
- `rtutils!TracePrintfA` at `0x1800258c2`
- `rtutils!TracePrintfA` at `0x18002593d`
- `rtutils!TracePrintfA` at `0x1800259c4`
- `rtutils!TracePrintfA` at `0x180025ada`
- `rtutils!TracePrintfA` at `0x180025b94`
- `rtutils!TracePrintfA` at `0x180025bef`

## string_xrefs

- `0x1800258f8`: `RasLineMakeCall: GetLineObjWithReadLock failed with error (0x%x)`
- `0x180025936`: `RasLineMakeCall: GetLineObjWithReadLock failed with error (0x%x)`
- `0x180025996`: `RasLineMakeCall: Failed to create call obj`
- `0x1800259bd`: `RasLineMakeCall: Failed to create call obj`
- `0x180025bc8`: `RasLineMakeCall: Failed to reacquire read lock for obj (%p)`
- `0x180025be8`: `RasLineMakeCall: Failed to reacquire read lock for obj (%p)`

## pseudocode

```c
__int64 __fastcall RasLineMakeCall(
        unsigned int a1,
        const char *a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5,
        unsigned int *a6,
        _DWORD *a7)
{
  unsigned int LineObjWithReadLock; // eax
  unsigned int Lock; // ebx
  _DWORD *v11; // rsi
  HANDLE ProcessHeap; // rax
  _DWORD *v13; // rax
  __int64 v14; // rdx
  unsigned int v15; // ecx
  unsigned int v16; // r12d
  int v17; // eax
  const char *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // r8
  unsigned int v21; // r15d
  char *v22; // rdi
  bool v23; // zf
  struct _RTL_CRITICAL_SECTION *v24; // rcx
  HANDLE v25; // rax
  HANDLE v26; // rax
  unsigned __int64 v27; // rcx
  char *v28; // r13
  __int64 v29; // rax
  CHAR *v30; // rdi
  __int64 v31; // rax
  __int64 v32; // rcx
  _BYTE *v33; // rdx
  const char *v34; // r8
  _BYTE *v35; // rax
  __int64 v36; // rax
  wchar_t *v37; // rcx
  _WORD *v38; // rcx
  unsigned int *v39; // rsi
  unsigned int cbMultiByte; // edx
  unsigned int *v41; // rcx
  unsigned int v43; // [rsp+40h] [rbp-C0h]
  unsigned int v44; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v45; // [rsp+48h] [rbp-B8h] BYREF
  int v46; // [rsp+50h] [rbp-B0h]
  LPVOID lpMem; // [rsp+58h] [rbp-A8h] BYREF
  size_t PtNumOfCharConverted; // [rsp+60h] [rbp-A0h] BYREF
  const char *v49; // [rsp+68h] [rbp-98h]
  void *Src; // [rsp+70h] [rbp-90h]
  unsigned int *v51; // [rsp+78h] [rbp-88h]
  _DWORD *v52; // [rsp+80h] [rbp-80h]
  wchar_t DstBuf[104]; // [rsp+90h] [rbp-70h] BYREF
  int v54; // [rsp+160h] [rbp+60h] BYREF
  char v55[2044]; // [rsp+164h] [rbp+64h] BYREF

  v49 = a2;
  Src = a7;
  v52 = a5;
  v51 = a6;
  lpMem = 0;
  v45 = 0;
  v44 = 0;
  PtNumOfCharConverted = 0;
  memset_0(DstBuf, 0, 0xC8u);
  v54 = 0;
  memset_0(v55, 0, sizeof(v55));
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( qword_18003EC48 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(
        gNdpspEtwContext,
        qword_18003EC48,
        L"RasLineMakeCall...");
  }
  else if ( dwTraceId != -1 )
  {
    TracePrintfA(dwTraceId, "RasLineMakeCall...");
  }
  *a5 = 0;
  LineObjWithReadLock = GetLineObjWithReadLock(a1, &v45);
  Lock = LineObjWithReadLock;
  if ( LineObjWithReadLock )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( qword_18003EC40 )
      {
        LOWORD(v54) = 0;
        FormatRRASErrorString(
          &v54,
          L"RasLineMakeCall: GetLineObjWithReadLock failed with error (0x%x)",
          LineObjWithReadLock);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v54);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "RasLineMakeCall: GetLineObjWithReadLock failed with error (0x%x)", LineObjWithReadLock);
    }
    v11 = 0;
    goto LABEL_55;
  }
  ProcessHeap = GetProcessHeap();
  v13 = HeapAlloc(ProcessHeap, 8u, 0x48u);
  v11 = v13;
  if ( !v13 )
  {
    Lock = 14;
    ReleaseObjReadLock(a1);
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( qword_18003EC48 )
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(
          gNdpspEtwContext,
          qword_18003EC48,
          L"RasLineMakeCall: Failed to create call obj");
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "RasLineMakeCall: Failed to create call obj");
    }
    return Lock;
  }
  v14 = v45;
  v15 = 0;
  *v13 = 1329807692;
  v16 = 0;
  v43 = 0;
  v13[1] = *(_DWORD *)(v14 + 4);
  v13[8] = a1;
  v13[16] = 1;
  v17 = *(_DWORD *)(v14 + 56);
  v46 = v17;
  if ( a2 )
  {
    if ( v17 == 12 )
    {
      v18 = a2;
      v19 = 0x7FFFFFFF;
      do
      {
        if ( !*v18 )
          break;
        ++v18;
        --v19;
      }
      while ( v19 );
      v20 = (0x7FFFFFFF - v19) & -(__int64)(v19 != 0);
      v14 = v45;
      if ( v19 )
      {
        v16 = v20 + 1;
        v15 = v20 + 1;
        goto LABEL_28;
      }
    }
    else
    {
      mbstowcs_s(&PtNumOfCharConverted, DstBuf, 0x64u, a2, 0x63u);
      v14 = v45;
      if ( PtNumOfCharConverted )
      {
        v16 = PtNumOfCharConverted;
        v15 = 2 * PtNumOfCharConverted;
LABEL_28:
        v43 = v15;
        goto LABEL_34;
      }
    }
    goto LABEL_38;
  }
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( !qword_18003EC48 )
    {
LABEL_33:
      v14 = v45;
      goto LABEL_34;
    }
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(
      gNdpspEtwContext,
      qword_18003EC48,
      L"RasLineMakeCall: Destination address is NULL.");
LABEL_32:
    v15 = 0;
    goto LABEL_33;
  }
  if ( dwTraceId != -1 )
  {
    TracePrintfA(dwTraceId, "RasLineMakeCall: Destination address is NULL.");
    goto LABEL_32;
  }
LABEL_38:
  v15 = 0;
LABEL_34:
  if ( a7 )
    v21 = *a7 - 180;
  else
    v21 = 0;
  Lock = PrepareAsyncRequest(0x7030115u, *(_DWORD *)(v14 + 4), v21 + v15 + 232, &lpMem);
  if ( Lock )
  {
    ReleaseObjReadLock(a1);
    goto LABEL_55;
  }
  ReleaseObjReadLock(a1);
  Lock = OpenObjHandle(v11, &v44);
  if ( Lock )
  {
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineMakeCall: Failed to map call object (%p) to handle", v11);
      goto LABEL_55;
    }
    if ( qword_18003EC40 )
    {
      LOWORD(v54) = 0;
      FormatRRASErrorString(&v54, L"RasLineMakeCall: Failed to map call object (%p) to handle", v11);
LABEL_46:
      ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v54);
      goto LABEL_55;
    }
    goto LABEL_55;
  }
  Lock = AcquireObjReadLock(a1);
  if ( Lock )
  {
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineMakeCall: Failed to reacquire read lock for obj (%p)", (const void *)a1);
      goto LABEL_55;
    }
    if ( qword_18003EC40 )
    {
      LOWORD(v54) = 0;
      FormatRRASErrorString(&v54, L"RasLineMakeCall: Failed to reacquire read lock for obj (%p)", a1);
      goto LABEL_46;
    }
LABEL_55:
    v22 = (char *)lpMem;
    if ( lpMem )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)lpMem + 48));
      v23 = (*((_DWORD *)v22 + 22))-- == 1;
      v24 = (struct _RTL_CRITICAL_SECTION *)(v22 + 48);
      if ( v23 )
      {
        LeaveCriticalSection(v24);
        DeleteCriticalSection((LPCRITICAL_SECTION)(v22 + 48));
        v25 = GetProcessHeap();
        HeapFree(v25, 0, v22);
      }
      else
      {
        LeaveCriticalSection(v24);
      }
    }
    if ( v44 )
    {
      CloseObjHandle(v44);
    }
    else if ( v11 )
    {
      v26 = GetProcessHeap();
      HeapFree(v26, 0, v11);
    }
    return Lock;
  }
  v27 = v44;
  v28 = (char *)lpMem;
  v29 = v45;
  v11[2] = v44;
  lpMem = (LPVOID)v27;
  v30 = v28 + 152;
  v31 = *(_QWORD *)(v29 + 16);
  *((_QWORD *)v28 + 21) = v27;
  v32 = v43;
  *((_QWORD *)v28 + 20) = v31;
  *((_DWORD *)v28 + 46) = v43;
  if ( v43 )
  {
    v33 = (_BYTE *)((unsigned __int64)&v30[v21 + 232] & 0xFFFFFFFFFFFFFFF8uLL);
    v23 = v46 == 12;
    *((_DWORD *)v28 + 47) = (((_DWORD)v30 + v21 + 232) & 0xFFFFFFF8) - (_DWORD)v30;
    if ( v23 )
    {
      if ( v43 > 0x7FFFFFFEuLL )
      {
        *v33 = 0;
      }
      else
      {
        v34 = v49;
        do
        {
          if ( !*v34 )
            break;
          *v33++ = *v34++;
          --v32;
        }
        while ( v32 );
        v35 = v33 - 1;
        if ( v32 )
          v35 = v33;
        *v35 = 0;
      }
    }
    else
    {
      v36 = v16;
      if ( v16 )
      {
        if ( v16 > 0x7FFFFFFEuLL )
        {
          *(_WORD *)v33 = 0;
        }
        else
        {
          v37 = DstBuf;
          do
          {
            if ( !*v37 )
              break;
            *(_WORD *)v33 = *v37++;
            v33 += 2;
            --v36;
          }
          while ( v36 );
          v38 = v33 - 2;
          if ( v36 )
            v38 = v33;
          *v38 = 0;
        }
      }
    }
  }
  else
  {
    *((_DWORD *)v28 + 47) = 0;
  }
  v39 = (unsigned int *)Src;
  if ( Src )
  {
    v28[192] = 0;
    memcpy_0(v28 + 196, v39, *v39);
    cbMultiByte = v39[12];
    if ( cbMultiByte )
    {
      WideCharToMultiByte(
        0,
        0x400u,
        (LPCWCH)((char *)v39 + v39[13]),
        cbMultiByte >> 1,
        &v30[v39[13] + 44],
        cbMultiByte,
        0,
        0);
      *((_DWORD *)v28 + 61) >>= 1;
    }
  }
  else
  {
    v28[192] = 1;
  }
  v23 = g_fUseReqId == 0;
  v41 = v51;
  *((_QWORD *)v28 + 12) = lpMem;
  *((_QWORD *)v28 + 5) = RasLineMakeCall_postProcess;
  *v41 = v44;
  if ( v23 )
    *(_DWORD *)v30 = 0;
  else
    *v52 = *(_DWORD *)v30;
  ReleaseObjReadLock(a1);
  AsyncDriverRequest(0x8FFF23C8, v28);
  return Lock;
}

```

## disassembly

```asm
0x1800257e4  mov     [rsp-8+arg_10], rbx
0x1800257e9  push    rbp
0x1800257ea  push    rsi
0x1800257eb  push    rdi
0x1800257ec  push    r12
0x1800257ee  push    r13
0x1800257f0  push    r14
0x1800257f2  push    r15
0x1800257f4  lea     rbp, [rsp-870h]
0x1800257fc  sub     rsp, 970h
0x180025803  mov     rax, cs:__security_cookie
0x18002580a  xor     rax, rsp
0x18002580d  mov     [rbp+8A0h+var_40], rax
0x180025814  mov     rax, [rbp+8A0h+arg_28]
0x18002581b  xor     r13d, r13d
0x18002581e  mov     r15, [rbp+8A0h+arg_30]
0x180025825  mov     rdi, rdx
0x180025828  mov     rbx, [rbp+8A0h+arg_20]
0x18002582f  mov     r14d, ecx
0x180025832  mov     [rsp+9A0h+var_938], rdx
0x180025837  lea     rcx, [rbp+8A0h+DstBuf]; void *
0x18002583b  xor     edx, edx; Val
0x18002583d  mov     [rsp+9A0h+Src], r15
0x180025842  mov     r8d, 0C8h; Size
0x180025848  mov     [rbp+8A0h+var_920], rbx
0x18002584c  mov     [rsp+9A0h+var_928], rax
0x180025851  mov     [rsp+9A0h+lpMem], r13
0x180025856  mov     [rsp+9A0h+var_958], r13
0x18002585b  mov     [rsp+9A0h+var_95C], r13d
0x180025860  mov     [rsp+9A0h+PtNumOfCharConverted], r13
0x180025865  call    memset_0
0x18002586a  xor     edx, edx; Val
0x18002586c  mov     [rbp+8A0h+var_840], r13d
0x180025870  mov     r8d, 7FCh; Size
0x180025876  lea     rcx, [rbp+8A0h+var_83C]; void *
0x18002587a  call    memset_0
0x18002587f  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180025886  jz      short loc_1800258B0
0x180025888  mov     rdx, cs:qword_18003EC48
0x18002588f  test    rdx, rdx
0x180025892  jz      short loc_1800258C8
0x180025894  mov     rcx, cs:gNdpspEtwContext
0x18002589b  lea     r8, aRaslinemakecal; "RasLineMakeCall..."
0x1800258a2  mov     rax, cs:gNdpspTemplateFunc
0x1800258a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258ae  jmp     short loc_1800258C8
0x1800258b0  mov     ecx, cs:dwTraceId; dwTraceID
0x1800258b6  cmp     ecx, 0FFFFFFFFh
0x1800258b9  jz      short loc_1800258C8
0x1800258bb  lea     rdx, aRaslinemakecal_13; "RasLineMakeCall..."
0x1800258c2  call    cs:__imp_TracePrintfA
0x1800258c8  lea     rdx, [rsp+9A0h+var_958]
0x1800258cd  mov     [rbx], r13d
0x1800258d0  mov     ecx, r14d
0x1800258d3  call    GetLineObjWithReadLock
0x1800258d8  mov     ebx, eax
0x1800258da  test    eax, eax
0x1800258dc  jz      short loc_18002594B
0x1800258de  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x1800258e5  jz      short loc_180025928
0x1800258e7  cmp     cs:qword_18003EC40, r13
0x1800258ee  jz      short loc_180025943
0x1800258f0  mov     r8d, eax
0x1800258f3  mov     word ptr [rbp+8A0h+var_840], r13w
0x1800258f8  lea     rdx, aRaslinemakecal_0; "RasLineMakeCall: GetLineObjWithReadLock"...
0x1800258ff  lea     rcx, [rbp+8A0h+var_840]
0x180025903  call    FormatRRASErrorString
0x180025908  mov     rdx, cs:qword_18003EC40
0x18002590f  lea     r8, [rbp+8A0h+var_840]
0x180025913  mov     rcx, cs:gNdpspEtwContext
0x18002591a  mov     rax, cs:gNdpspTemplateFunc
0x180025921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025926  jmp     short loc_180025943
0x180025928  mov     ecx, cs:dwTraceId; dwTraceID
0x18002592e  cmp     ecx, 0FFFFFFFFh
0x180025931  jz      short loc_180025943
0x180025933  mov     r8d, eax
0x180025936  lea     rdx, aRaslinemakecal_14; "RasLineMakeCall: GetLineObjWithReadLock"...
0x18002593d  call    cs:__imp_TracePrintfA
0x180025943  mov     rsi, r13
0x180025946  jmp     loc_180025BF5
0x18002594b  call    cs:__imp_GetProcessHeap
0x180025951  mov     edx, 8; dwFlags
0x180025956  mov     rcx, rax; hHeap
0x180025959  lea     r8d, [rdx+40h]; dwBytes
0x18002595d  call    cs:__imp_HeapAlloc
0x180025963  mov     rsi, rax
0x180025966  test    rax, rax
0x180025969  jnz     short loc_1800259CF
0x18002596b  mov     ecx, r14d
0x18002596e  lea     ebx, [rax+0Eh]
0x180025971  call    ReleaseObjReadLock
0x180025976  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18002597d  jz      short loc_1800259AE
0x18002597f  mov     rdx, cs:qword_18003EC48
0x180025986  test    rdx, rdx
0x180025989  jz      loc_180025E05
0x18002598f  mov     rcx, cs:gNdpspEtwContext
0x180025996  lea     r8, aRaslinemakecal_4; "RasLineMakeCall: Failed to create call "...
0x18002599d  mov     rax, cs:gNdpspTemplateFunc
0x1800259a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259a9  jmp     loc_180025E05
0x1800259ae  mov     ecx, cs:dwTraceId; dwTraceID
0x1800259b4  cmp     ecx, 0FFFFFFFFh
0x1800259b7  jz      loc_180025E05
0x1800259bd  lea     rdx, aRaslinemakecal_5; "RasLineMakeCall: Failed to create call "...
0x1800259c4  call    cs:__imp_TracePrintfA
0x1800259ca  jmp     loc_180025E05
0x1800259cf  mov     rdx, [rsp+9A0h+var_958]
0x1800259d4  mov     ecx, r13d
0x1800259d7  mov     dword ptr [rax], 4F43414Ch
0x1800259dd  mov     r12d, r13d
0x1800259e0  mov     [rsp+9A0h+var_960], ecx
0x1800259e4  mov     eax, [rdx+4]
0x1800259e7  mov     [rsi+4], eax
0x1800259ea  mov     [rsi+20h], r14d
0x1800259ee  mov     dword ptr [rsi+40h], 1
0x1800259f5  mov     eax, [rdx+38h]
0x1800259f8  mov     [rsp+9A0h+var_950], eax
0x1800259fc  test    rdi, rdi
0x1800259ff  jz      short loc_180025A80
0x180025a01  cmp     eax, 0Ch
0x180025a04  jz      short loc_180025A42
0x180025a06  mov     r9, rdi; SrcBuf
0x180025a09  mov     [rsp+9A0h+MaxCount], 63h ; 'c'; MaxCount
0x180025a12  mov     r8d, 64h ; 'd'; SizeInWords
0x180025a18  lea     rdx, [rbp+8A0h+DstBuf]; DstBuf
0x180025a1c  lea     rcx, [rsp+9A0h+PtNumOfCharConverted]; PtNumOfCharConverted
0x180025a21  call    cs:__imp_mbstowcs_s
0x180025a27  mov     rax, [rsp+9A0h+PtNumOfCharConverted]
0x180025a2c  mov     rdx, [rsp+9A0h+var_958]
0x180025a31  test    rax, rax
0x180025a34  jz      loc_180025AE2
0x180025a3a  mov     r12d, eax
0x180025a3d  lea     ecx, [rax+rax]
0x180025a40  jmp     short loc_180025A7A
0x180025a42  mov     edx, 7FFFFFFFh
0x180025a47  mov     rax, rdi
0x180025a4a  mov     ecx, edx
0x180025a4c  cmp     [rax], r13b
0x180025a4f  jz      short loc_180025A5A
0x180025a51  inc     rax
0x180025a54  sub     rcx, 1
0x180025a58  jnz     short loc_180025A4C
0x180025a5a  sub     rdx, rcx
0x180025a5d  mov     rax, rcx
0x180025a60  neg     rax
0x180025a63  sbb     r8, r8
0x180025a66  and     r8, rdx
0x180025a69  mov     rdx, [rsp+9A0h+var_958]
0x180025a6e  test    rcx, rcx
0x180025a71  jz      short loc_180025AE2
0x180025a73  lea     r12d, [r8+1]
0x180025a77  mov     ecx, r12d
0x180025a7a  mov     [rsp+9A0h+var_960], ecx
0x180025a7e  jmp     short loc_180025AB7
0x180025a80  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180025a87  jz      short loc_180025AC8
0x180025a89  mov     rdx, cs:qword_18003EC48
0x180025a90  test    rdx, rdx
0x180025a93  jz      short loc_180025AB2
0x180025a95  mov     rcx, cs:gNdpspEtwContext
0x180025a9c  lea     r8, aRaslinemakecal_11; "RasLineMakeCall: Destination address is"...
0x180025aa3  mov     rax, cs:gNdpspTemplateFunc
0x180025aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025aaf  mov     ecx, r13d
0x180025ab2  mov     rdx, [rsp+9A0h+var_958]
0x180025ab7  test    r15, r15
0x180025aba  jz      short loc_180025AE7
0x180025abc  mov     r15d, [r15]
0x180025abf  sub     r15d, 0B4h
0x180025ac6  jmp     short loc_180025AEA
0x180025ac8  mov     ecx, cs:dwTraceId; dwTraceID
0x180025ace  cmp     ecx, 0FFFFFFFFh
0x180025ad1  jz      short loc_180025AE2
0x180025ad3  lea     rdx, aRaslinemakecal_17; "RasLineMakeCall: Destination address is"...
0x180025ada  call    cs:__imp_TracePrintfA
0x180025ae0  jmp     short loc_180025AAF
0x180025ae2  mov     ecx, r13d
0x180025ae5  jmp     short loc_180025AB7
0x180025ae7  mov     r15d, r13d
0x180025aea  mov     edx, [rdx+4]
0x180025aed  lea     r8d, [rcx+0E8h]
0x180025af4  add     r8d, r15d
0x180025af7  lea     r9, [rsp+9A0h+lpMem]
0x180025afc  mov     ecx, 7030115h
0x180025b01  call    PrepareAsyncRequest
0x180025b06  mov     ebx, eax
0x180025b08  mov     ecx, r14d
0x180025b0b  test    eax, eax
0x180025b0d  jz      short loc_180025B19
0x180025b0f  call    ReleaseObjReadLock
0x180025b14  jmp     loc_180025BF5
0x180025b19  call    ReleaseObjReadLock
0x180025b1e  lea     rdx, [rsp+9A0h+var_95C]
0x180025b23  mov     rcx, rsi
0x180025b26  call    OpenObjHandle
0x180025b2b  mov     ebx, eax
0x180025b2d  test    eax, eax
0x180025b2f  jz      short loc_180025B9C
0x180025b31  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180025b38  jz      short loc_180025B7F
0x180025b3a  cmp     cs:qword_18003EC40, r13
0x180025b41  jz      loc_180025BF5
0x180025b47  mov     r8, rsi
0x180025b4a  mov     word ptr [rbp+8A0h+var_840], r13w
0x180025b4f  lea     rdx, aRaslinemakecal_20; "RasLineMakeCall: Failed to map call obj"...
0x180025b56  lea     rcx, [rbp+8A0h+var_840]
0x180025b5a  call    FormatRRASErrorString
0x180025b5f  mov     rdx, cs:qword_18003EC40
0x180025b66  lea     r8, [rbp+8A0h+var_840]
0x180025b6a  mov     rcx, cs:gNdpspEtwContext
0x180025b71  mov     rax, cs:gNdpspTemplateFunc
0x180025b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b7d  jmp     short loc_180025BF5
0x180025b7f  mov     ecx, cs:dwTraceId; dwTraceID
0x180025b85  cmp     ecx, 0FFFFFFFFh
0x180025b88  jz      short loc_180025BF5
0x180025b8a  mov     r8, rsi
0x180025b8d  lea     rdx, aRaslinemakecal_8; "RasLineMakeCall: Failed to map call obj"...
0x180025b94  call    cs:__imp_TracePrintfA
0x180025b9a  jmp     short loc_180025BF5
0x180025b9c  mov     ecx, r14d
0x180025b9f  call    AcquireObjReadLock
0x180025ba4  mov     ebx, eax
0x180025ba6  test    eax, eax
0x180025ba8  jz      loc_180025C77
0x180025bae  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180025bb5  jz      short loc_180025BDA
0x180025bb7  cmp     cs:qword_18003EC40, r13
0x180025bbe  jz      short loc_180025BF5
0x180025bc0  mov     r8d, r14d
0x180025bc3  mov     word ptr [rbp+8A0h+var_840], r13w
0x180025bc8  lea     rdx, aRaslinemakecal_19; "RasLineMakeCall: Failed to reacquire re"...
0x180025bcf  lea     rcx, [rbp+8A0h+var_840]
0x180025bd3  call    FormatRRASErrorString
0x180025bd8  jmp     short loc_180025B5F
0x180025bda  mov     ecx, cs:dwTraceId; dwTraceID
0x180025be0  cmp     ecx, 0FFFFFFFFh
0x180025be3  jz      short loc_180025BF5
0x180025be5  mov     r8d, r14d
0x180025be8  lea     rdx, aRaslinemakecal_12; "RasLineMakeCall: Failed to reacquire re"...
0x180025bef  call    cs:__imp_TracePrintfA
0x180025bf5  mov     rdi, [rsp+9A0h+lpMem]
0x180025bfa  test    rdi, rdi
0x180025bfd  jz      short loc_180025C40
0x180025bff  lea     r14, [rdi+30h]
0x180025c03  mov     rcx, r14; lpCriticalSection
0x180025c06  call    cs:__imp_EnterCriticalSection
0x180025c0c  add     dword ptr [rdi+58h], 0FFFFFFFFh
0x180025c10  mov     rcx, r14; lpCriticalSection
0x180025c13  jnz     short loc_180025C3A
0x180025c15  call    cs:__imp_LeaveCriticalSection
0x180025c1b  mov     rcx, r14; lpCriticalSection
0x180025c1e  call    cs:__imp_DeleteCriticalSection
0x180025c24  call    cs:__imp_GetProcessHeap
0x180025c2a  mov     r8, rdi; lpMem
0x180025c2d  xor     edx, edx; dwFlags
0x180025c2f  mov     rcx, rax; hHeap
0x180025c32  call    cs:__imp_HeapFree
0x180025c38  jmp     short loc_180025C40
0x180025c3a  call    cs:__imp_LeaveCriticalSection
0x180025c40  cmp     [rsp+9A0h+var_95C], r13d
0x180025c45  jnz     short loc_180025C69
0x180025c47  test    rsi, rsi
0x180025c4a  jz      loc_180025E05
0x180025c50  call    cs:__imp_GetProcessHeap
0x180025c56  mov     r8, rsi; lpMem
0x180025c59  xor     edx, edx; dwFlags
0x180025c5b  mov     rcx, rax; hHeap
0x180025c5e  call    cs:__imp_HeapFree
0x180025c64  jmp     loc_180025E05
0x180025c69  mov     ecx, [rsp+9A0h+var_95C]
0x180025c6d  call    CloseObjHandle
0x180025c72  jmp     loc_180025E05
0x180025c77  mov     ecx, [rsp+9A0h+var_95C]
0x180025c7b  xor     r10d, r10d
0x180025c7e  mov     r13, [rsp+9A0h+lpMem]
0x180025c83  mov     rax, [rsp+9A0h+var_958]
0x180025c88  mov     [rsi+8], ecx
0x180025c8b  mov     [rsp+9A0h+lpMem], rcx
0x180025c90  lea     rdi, [r13+98h]
0x180025c97  mov     rax, [rax+10h]
0x180025c9b  mov     [rdi+10h], rcx
0x180025c9f  mov     ecx, [rsp+9A0h+var_960]
0x180025ca3  mov     [rdi+8], rax
0x180025ca7  mov     [rdi+20h], ecx
0x180025caa  test    ecx, ecx
0x180025cac  jz      loc_180025D50
0x180025cb2  mov     edx, r15d
0x180025cb5  add     rdx, 0E8h
0x180025cbc  add     rdx, rdi
0x180025cbf  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180025cc3  mov     eax, edx
0x180025cc5  sub     eax, edi
0x180025cc7  cmp     [rsp+9A0h+var_950], 0Ch
0x180025ccc  mov     [rdi+24h], eax
0x180025ccf  jnz     short loc_180025D09
0x180025cd1  cmp     rcx, 7FFFFFFEh
0x180025cd8  ja      short loc_180025D04
  ... truncated ...
```
