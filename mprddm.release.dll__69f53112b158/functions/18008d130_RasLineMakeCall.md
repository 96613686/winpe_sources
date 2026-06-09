# RasLineMakeCall

- ea: `0x18008d130`
- end: `0x18008d7ff`
- name: `RasLineMakeCall`
- size: `1743`
- prototype: `__int64 __fastcall(unsigned int, char *, __int64, __int64, _DWORD *, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180028968`

## callees

- `0x180002be6`
- `0x1800755b8`
- `0x180088d74`
- `0x18008a694`
- `0x18008d130`
- `0x18008f50c`
- `0x18008fa60`
- `0x18008fd44`
- `0x180090344`
- `0x180090714`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `msvcrt!mbstowcs_s` at `0x18008d399`
- `msvcrt!mbstowcs_s` at `0x18008d399`
- `KERNEL32!DeleteCriticalSection` at `0x18008d5a7`
- `KERNEL32!DeleteCriticalSection` at `0x18008d5a7`
- `KERNEL32!GetProcessHeap` at `0x18008d2ac`
- `KERNEL32!GetProcessHeap` at `0x18008d5b3`
- `KERNEL32!GetProcessHeap` at `0x18008d5f4`
- `KERNEL32!GetProcessHeap` at `0x18008d2ac`
- `KERNEL32!GetProcessHeap` at `0x18008d5b3`
- `KERNEL32!GetProcessHeap` at `0x18008d5f4`
- `KERNEL32!HeapAlloc` at `0x18008d2c4`
- `KERNEL32!HeapAlloc` at `0x18008d2c4`
- `KERNEL32!LeaveCriticalSection` at `0x18008d598`
- `KERNEL32!LeaveCriticalSection` at `0x18008d5d5`
- `KERNEL32!LeaveCriticalSection` at `0x18008d598`
- `KERNEL32!LeaveCriticalSection` at `0x18008d5d5`
- `KERNEL32!EnterCriticalSection` at `0x18008d583`
- `KERNEL32!EnterCriticalSection` at `0x18008d583`
- `KERNEL32!HeapFree` at `0x18008d5c7`
- `KERNEL32!HeapFree` at `0x18008d608`
- `KERNEL32!HeapFree` at `0x18008d5c7`
- `KERNEL32!HeapFree` at `0x18008d608`
- `KERNEL32!WideCharToMultiByte` at `0x18008d76d`
- `KERNEL32!WideCharToMultiByte` at `0x18008d76d`
- `rtutils!TracePrintfA` at `0x18008d217`
- `rtutils!TracePrintfA` at `0x18008d331`
- `rtutils!TracePrintfA` at `0x18008d443`
- `rtutils!TracePrintfA` at `0x18008d50e`
- `rtutils!TracePrintfA` at `0x18008d568`
- `rtutils!TracePrintfA` at `0x18008d217`
- `rtutils!TracePrintfA` at `0x18008d331`
- `rtutils!TracePrintfA` at `0x18008d443`
- `rtutils!TracePrintfA` at `0x18008d50e`
- `rtutils!TracePrintfA` at `0x18008d568`

## string_xrefs

- `0x18008d256`: `RasLineMakeCall: GetLineObjWithReadLock failed with error (0x%x)`
- `0x18008d303`: `RasLineMakeCall: Failed to create call obj`
- `0x18008d2a0`: `RasLineMakeCall: GetLineObjWithReadLock failed with error (0x%x)`
- `0x18008d32a`: `RasLineMakeCall: Failed to create call obj`
- `0x18008d547`: `RasLineMakeCall: Failed to reacquire read lock for obj (%p)`
- `0x18008d561`: `RasLineMakeCall: Failed to reacquire read lock for obj (%p)`

## pseudocode

```c
__int64 __fastcall RasLineMakeCall(
        unsigned int a1,
        char *a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5,
        __int64 a6,
        _DWORD *a7)
{
  char *v8; // rbx
  _DWORD *v9; // rsi
  unsigned int v10; // r12d
  int v11; // edi
  unsigned int LineObjWithReadLock; // eax
  unsigned int Lock; // r14d
  __int64 v14; // r8
  const wchar_t *v15; // rdx
  HANDLE ProcessHeap; // rax
  _DWORD *v17; // rax
  __int64 v18; // rcx
  char *v19; // rax
  int v20; // edx
  __int64 v21; // rdx
  __int64 v22; // r8
  unsigned int v23; // r13d
  char *v24; // rdi
  bool v25; // zf
  struct _RTL_CRITICAL_SECTION *v26; // rcx
  HANDLE v27; // rax
  HANDLE v28; // rax
  unsigned __int64 v29; // rcx
  unsigned int v30; // r8d
  __int64 v31; // rax
  unsigned __int64 v32; // rcx
  __int64 v33; // rdx
  char *v34; // rdi
  char v35; // al
  _BYTE *v36; // rax
  __int64 v37; // rdx
  char *v38; // rax
  __int16 v39; // r8
  _WORD *v40; // rax
  unsigned int *v41; // rsi
  unsigned int cbMultiByte; // edx
  _DWORD *v43; // rcx
  unsigned int v45; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v46; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v47; // [rsp+50h] [rbp-B0h]
  LPVOID lpMem; // [rsp+58h] [rbp-A8h] BYREF
  int v49; // [rsp+60h] [rbp-A0h]
  size_t PtNumOfCharConverted; // [rsp+68h] [rbp-98h] BYREF
  char *SrcBuf; // [rsp+70h] [rbp-90h]
  void *Src; // [rsp+78h] [rbp-88h]
  __int64 v53; // [rsp+80h] [rbp-80h]
  _DWORD *v54; // [rsp+88h] [rbp-78h]
  __int64 v55; // [rsp+90h] [rbp-70h]
  wchar_t DstBuf[104]; // [rsp+A0h] [rbp-60h] BYREF
  int v57; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v58[2044]; // [rsp+174h] [rbp+74h] BYREF

  v53 = a6;
  SrcBuf = a2;
  v8 = 0;
  lpMem = 0;
  v46 = 0;
  v9 = 0;
  v45 = 0;
  v10 = 0;
  v11 = 0;
  v47 = 0;
  PtNumOfCharConverted = 0;
  v55 = a4;
  v54 = a5;
  Src = a7;
  memset_0(DstBuf, 0, 0xC8u);
  v57 = 0;
  memset_0(v58, 0, sizeof(v58));
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( *((_QWORD *)&xmmword_1800D0BE0 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
        gNdpspEtwContext,
        *((_QWORD *)&xmmword_1800D0BE0 + 1),
        L"RasLineMakeCall...");
  }
  else if ( dwTraceId != -1 )
  {
    TracePrintfA(dwTraceId, "RasLineMakeCall...");
  }
  *a5 = 0;
  LineObjWithReadLock = GetLineObjWithReadLock(a1, &v46);
  Lock = LineObjWithReadLock;
  if ( LineObjWithReadLock )
  {
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineMakeCall: GetLineObjWithReadLock failed with error (0x%x)", LineObjWithReadLock);
      goto LABEL_52;
    }
    if ( (_QWORD)xmmword_1800D0BE0 )
    {
      v14 = LineObjWithReadLock;
      v15 = L"RasLineMakeCall: GetLineObjWithReadLock failed with error (0x%x)";
LABEL_10:
      LOWORD(v57) = 0;
      FormatRRASErrorString(&v57, v15, v14);
LABEL_11:
      ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v57);
      goto LABEL_52;
    }
    goto LABEL_52;
  }
  ProcessHeap = GetProcessHeap();
  v17 = HeapAlloc(ProcessHeap, 8u, 0x48u);
  v9 = v17;
  if ( !v17 )
  {
    Lock = 14;
    ReleaseObjReadLock(a1);
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( *((_QWORD *)&xmmword_1800D0BE0 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
          gNdpspEtwContext,
          *((_QWORD *)&xmmword_1800D0BE0 + 1),
          L"RasLineMakeCall: Failed to create call obj");
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "RasLineMakeCall: Failed to create call obj");
    }
    return Lock;
  }
  v18 = v46;
  *v17 = 1329807692;
  v17[1] = *(_DWORD *)(v18 + 4);
  v19 = SrcBuf;
  v9[8] = a1;
  v9[16] = 1;
  v20 = *(_DWORD *)(v18 + 56);
  v49 = v20;
  if ( v19 )
  {
    if ( v20 == 12 )
    {
      v21 = 0x7FFFFFFF;
      do
      {
        if ( !*v19 )
          break;
        ++v19;
        --v21;
      }
      while ( v21 );
      v22 = (0x7FFFFFFF - v21) & -(__int64)(v21 != 0);
      v18 = v46;
      if ( v21 )
      {
        v10 = v22 + 1;
        v11 = v22 + 1;
        v47 = v22 + 1;
      }
    }
    else
    {
      mbstowcs_s(&PtNumOfCharConverted, DstBuf, 0x64u, v19, 0x63u);
      v18 = v46;
      if ( PtNumOfCharConverted )
      {
        v11 = 2 * PtNumOfCharConverted;
        v10 = PtNumOfCharConverted;
        v47 = 2 * PtNumOfCharConverted;
      }
    }
    goto LABEL_35;
  }
  if ( !gIsndpspEtwTracingAvailable )
  {
    if ( dwTraceId != -1 )
      TracePrintfA(dwTraceId, "RasLineMakeCall: Destination address is NULL.", 0x7FFFFFFF);
    goto LABEL_34;
  }
  if ( *((_QWORD *)&xmmword_1800D0BE0 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
      gNdpspEtwContext,
      *((_QWORD *)&xmmword_1800D0BE0 + 1),
      L"RasLineMakeCall: Destination address is NULL.");
LABEL_34:
    v18 = v46;
  }
LABEL_35:
  if ( a7 )
    v23 = *a7 - 180;
  else
    v23 = 0;
  Lock = PrepareAsyncRequest(117637397, *(unsigned int *)(v18 + 4), v11 + v23 + 232, &lpMem);
  if ( Lock )
  {
    ReleaseObjReadLock(a1);
    v8 = (char *)lpMem;
    goto LABEL_52;
  }
  v8 = (char *)lpMem;
  v24 = (char *)lpMem + 152;
  ReleaseObjReadLock(a1);
  Lock = OpenObjHandle(v9, &v45);
  if ( Lock )
  {
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineMakeCall: Failed to map call object (%p) to handle", v9);
      goto LABEL_52;
    }
    if ( (_QWORD)xmmword_1800D0BE0 )
    {
      LOWORD(v57) = 0;
      FormatRRASErrorString(&v57, L"RasLineMakeCall: Failed to map call object (%p) to handle", v9);
      goto LABEL_11;
    }
    goto LABEL_52;
  }
  Lock = AcquireObjReadLock(a1);
  if ( Lock )
  {
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineMakeCall: Failed to reacquire read lock for obj (%p)", a1);
      goto LABEL_52;
    }
    if ( (_QWORD)xmmword_1800D0BE0 )
    {
      v14 = a1;
      v15 = L"RasLineMakeCall: Failed to reacquire read lock for obj (%p)";
      goto LABEL_10;
    }
LABEL_52:
    if ( v8 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 48));
      v25 = (*((_DWORD *)v8 + 22))-- == 1;
      v26 = (struct _RTL_CRITICAL_SECTION *)(v8 + 48);
      if ( v25 )
      {
        LeaveCriticalSection(v26);
        DeleteCriticalSection((LPCRITICAL_SECTION)(v8 + 48));
        v27 = GetProcessHeap();
        HeapFree(v27, 0, v8);
      }
      else
      {
        LeaveCriticalSection(v26);
      }
    }
    if ( v45 )
    {
      CloseObjHandle(v45);
    }
    else if ( v9 )
    {
      v28 = GetProcessHeap();
      HeapFree(v28, 0, v9);
    }
    return Lock;
  }
  v29 = v45;
  v30 = v47;
  v31 = v46;
  v9[2] = v45;
  lpMem = (LPVOID)v29;
  *((_QWORD *)v24 + 1) = *(_QWORD *)(v31 + 16);
  *((_QWORD *)v24 + 2) = v29;
  *((_DWORD *)v24 + 8) = v30;
  if ( v30 )
  {
    v32 = (unsigned __int64)&v24[v23 + 232] & 0xFFFFFFFFFFFFFFF8uLL;
    v25 = v49 == 12;
    *((_DWORD *)v24 + 9) = (((_DWORD)v24 + v23 + 232) & 0xFFFFFFF8) - (_DWORD)v24;
    if ( v25 )
    {
      v33 = v30;
      if ( v30 <= 0x7FFFFFFE )
      {
        v34 = &SrcBuf[-v32];
        do
        {
          v35 = v34[v32];
          if ( !v35 )
            break;
          *(_BYTE *)v32++ = v35;
          --v33;
        }
        while ( v33 );
        v36 = (_BYTE *)(v32 - 1);
        v24 = v8 + 152;
        if ( v33 )
          v36 = (_BYTE *)v32;
        *v36 = 0;
      }
      else
      {
        *(_BYTE *)v32 = 0;
      }
    }
    else
    {
      v37 = v10;
      if ( v10 )
      {
        if ( v10 <= 0x7FFFFFFE )
        {
          v38 = (char *)DstBuf - v32;
          do
          {
            v39 = *(_WORD *)&v38[v32];
            if ( !v39 )
              break;
            *(_WORD *)v32 = v39;
            v32 += 2LL;
            --v37;
          }
          while ( v37 );
          v40 = (_WORD *)(v32 - 2);
          if ( v37 )
            v40 = (_WORD *)v32;
          *v40 = 0;
        }
        else
        {
          *(_WORD *)v32 = 0;
        }
      }
    }
  }
  else
  {
    *((_DWORD *)v24 + 9) = 0;
  }
  v41 = (unsigned int *)Src;
  if ( Src )
  {
    v24[40] = 0;
    memcpy_0(v24 + 44, v41, *v41);
    cbMultiByte = v41[12];
    if ( cbMultiByte )
    {
      WideCharToMultiByte(
        0,
        0x400u,
        (LPCWCH)((char *)v41 + v41[13]),
        cbMultiByte >> 1,
        &v24[v41[13] + 44],
        cbMultiByte,
        0,
        0);
      *((_DWORD *)v24 + 23) >>= 1;
    }
  }
  else
  {
    v24[40] = 1;
  }
  v25 = g_fUseReqId == 0;
  v43 = (_DWORD *)v53;
  *((_QWORD *)v8 + 12) = lpMem;
  *((_QWORD *)v8 + 5) = RasLineMakeCall_postProcess;
  *v43 = v45;
  if ( v25 )
    *(_DWORD *)v24 = v55;
  else
    *v54 = *(_DWORD *)v24;
  ReleaseObjReadLock(a1);
  AsyncDriverRequest(0x8FFF23C8, v8);
  return Lock;
}

```

## disassembly

```asm
0x18008d130  mov     [rsp-8+arg_10], rbx
0x18008d135  push    rbp
0x18008d136  push    rsi
0x18008d137  push    rdi
0x18008d138  push    r12
0x18008d13a  push    r13
0x18008d13c  push    r14
0x18008d13e  push    r15
0x18008d140  lea     rbp, [rsp-880h]
0x18008d148  sub     rsp, 980h
0x18008d14f  mov     rax, cs:__security_cookie
0x18008d156  xor     rax, rsp
0x18008d159  mov     [rbp+8B0h+var_40], rax
0x18008d160  mov     rax, [rbp+8B0h+arg_28]
0x18008d167  mov     r15d, ecx
0x18008d16a  mov     r14, [rbp+8B0h+arg_20]
0x18008d171  lea     rcx, [rbp+8B0h+DstBuf]; void *
0x18008d175  mov     r13, [rbp+8B0h+arg_30]
0x18008d17c  mov     r8d, 0C8h; Size
0x18008d182  mov     [rbp+8B0h+var_930], rax
0x18008d186  xor     eax, eax
0x18008d188  mov     [rsp+9B0h+SrcBuf], rdx
0x18008d18d  mov     ebx, eax
0x18008d18f  xor     edx, edx; Val
0x18008d191  mov     [rsp+9B0h+lpMem], rax
0x18008d196  mov     [rsp+9B0h+var_968], rax
0x18008d19b  mov     esi, eax
0x18008d19d  mov     [rsp+9B0h+var_970], eax
0x18008d1a1  mov     r12d, eax
0x18008d1a4  mov     edi, eax
0x18008d1a6  mov     [rsp+9B0h+var_960], eax
0x18008d1aa  mov     [rsp+9B0h+PtNumOfCharConverted], rax
0x18008d1af  mov     [rbp+8B0h+var_920], r9
0x18008d1b3  mov     [rbp+8B0h+var_928], r14
0x18008d1b7  mov     [rsp+9B0h+Src], r13
0x18008d1bc  call    memset_0
0x18008d1c1  and     [rbp+8B0h+var_840], ebx
0x18008d1c4  lea     rcx, [rbp+8B0h+var_83C]; void *
0x18008d1c8  xor     edx, edx; Val
0x18008d1ca  mov     r8d, 7FCh; Size
0x18008d1d0  call    memset_0
0x18008d1d5  cmp     cs:gIsndpspEtwTracingAvailable, ebx
0x18008d1db  jz      short loc_18008D205
0x18008d1dd  mov     rdx, qword ptr cs:xmmword_1800D0BE0+8
0x18008d1e4  test    rdx, rdx
0x18008d1e7  jz      short loc_18008D223
0x18008d1e9  mov     rcx, cs:gNdpspEtwContext
0x18008d1f0  lea     r8, aRaslinemakecal; "RasLineMakeCall..."
0x18008d1f7  mov     rax, cs:gNdpspTemplateFunc
0x18008d1fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d203  jmp     short loc_18008D223
0x18008d205  mov     ecx, cs:dwTraceId; dwTraceID
0x18008d20b  cmp     ecx, 0FFFFFFFFh
0x18008d20e  jz      short loc_18008D223
0x18008d210  lea     rdx, aRaslinemakecal_13; "RasLineMakeCall..."
0x18008d217  call    cs:__imp_TracePrintfA
0x18008d21e  nop     dword ptr [rax+rax+00h]
0x18008d223  and     [r14], ebx
0x18008d226  lea     rdx, [rsp+9B0h+var_968]
0x18008d22b  mov     ecx, r15d
0x18008d22e  call    GetLineObjWithReadLock
0x18008d233  xor     r10d, r10d
0x18008d236  mov     r14d, eax
0x18008d239  test    eax, eax
0x18008d23b  jz      short loc_18008D2AC
0x18008d23d  cmp     cs:gIsndpspEtwTracingAvailable, r10d
0x18008d244  jz      short loc_18008D28E
0x18008d246  cmp     qword ptr cs:xmmword_1800D0BE0, r10
0x18008d24d  jz      loc_18008D577
0x18008d253  mov     r8d, eax
0x18008d256  lea     rdx, aRaslinemakecal_0; "RasLineMakeCall: GetLineObjWithReadLock"...
0x18008d25d  lea     rcx, [rbp+8B0h+var_840]
0x18008d261  mov     word ptr [rbp+8B0h+var_840], r10w
0x18008d266  call    FormatRRASErrorString
0x18008d26b  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008d272  lea     r8, [rbp+8B0h+var_840]
0x18008d276  mov     rcx, cs:gNdpspEtwContext
0x18008d27d  mov     rax, cs:gNdpspTemplateFunc
0x18008d284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d289  jmp     loc_18008D574
0x18008d28e  mov     ecx, cs:dwTraceId
0x18008d294  cmp     ecx, 0FFFFFFFFh
0x18008d297  jz      loc_18008D577
0x18008d29d  mov     r8d, eax
0x18008d2a0  lea     rdx, aRaslinemakecal_14; "RasLineMakeCall: GetLineObjWithReadLock"...
0x18008d2a7  jmp     loc_18008D568
0x18008d2ac  call    cs:__imp_GetProcessHeap
0x18008d2b3  nop     dword ptr [rax+rax+00h]
0x18008d2b8  mov     edx, 8; dwFlags
0x18008d2bd  mov     rcx, rax; hHeap
0x18008d2c0  lea     r8d, [rdx+40h]; dwBytes
0x18008d2c4  call    cs:__imp_HeapAlloc
0x18008d2cb  nop     dword ptr [rax+rax+00h]
0x18008d2d0  mov     rsi, rax
0x18008d2d3  test    rax, rax
0x18008d2d6  jnz     short loc_18008D342
0x18008d2d8  mov     ecx, r15d
0x18008d2db  lea     r14d, [rax+0Eh]
0x18008d2df  call    ReleaseObjReadLock
0x18008d2e4  cmp     cs:gIsndpspEtwTracingAvailable, ebx
0x18008d2ea  jz      short loc_18008D31B
0x18008d2ec  mov     rdx, qword ptr cs:xmmword_1800D0BE0+8
0x18008d2f3  test    rdx, rdx
0x18008d2f6  jz      loc_18008D7D1
0x18008d2fc  mov     rcx, cs:gNdpspEtwContext
0x18008d303  lea     r8, aRaslinemakecal_4; "RasLineMakeCall: Failed to create call "...
0x18008d30a  mov     rax, cs:gNdpspTemplateFunc
0x18008d311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d316  jmp     loc_18008D7D1
0x18008d31b  mov     ecx, cs:dwTraceId; dwTraceID
0x18008d321  cmp     ecx, 0FFFFFFFFh
0x18008d324  jz      loc_18008D7D1
0x18008d32a  lea     rdx, aRaslinemakecal_5; "RasLineMakeCall: Failed to create call "...
0x18008d331  call    cs:__imp_TracePrintfA
0x18008d338  nop     dword ptr [rax+rax+00h]
0x18008d33d  jmp     loc_18008D7D1
0x18008d342  mov     rcx, [rsp+9B0h+var_968]
0x18008d347  mov     r8d, 7FFFFFFFh
0x18008d34d  mov     dword ptr [rax], 4F43414Ch
0x18008d353  mov     eax, [rcx+4]
0x18008d356  mov     [rsi+4], eax
0x18008d359  mov     rax, [rsp+9B0h+SrcBuf]
0x18008d35e  mov     [rsi+20h], r15d
0x18008d362  mov     dword ptr [rsi+40h], 1
0x18008d369  mov     edx, [rcx+38h]
0x18008d36c  mov     [rsp+9B0h+var_950], edx
0x18008d370  test    rax, rax
0x18008d373  jz      loc_18008D401
0x18008d379  cmp     edx, 0Ch
0x18008d37c  jz      short loc_18008D3C7
0x18008d37e  mov     r9, rax; SrcBuf
0x18008d381  mov     [rsp+9B0h+MaxCount], 63h ; 'c'; MaxCount
0x18008d38a  mov     r8d, 64h ; 'd'; SizeInWords
0x18008d390  lea     rdx, [rbp+8B0h+DstBuf]; DstBuf
0x18008d394  lea     rcx, [rsp+9B0h+PtNumOfCharConverted]; PtNumOfCharConverted
0x18008d399  call    cs:__imp_mbstowcs_s
0x18008d3a0  nop     dword ptr [rax+rax+00h]
0x18008d3a5  mov     rax, [rsp+9B0h+PtNumOfCharConverted]
0x18008d3aa  mov     rcx, [rsp+9B0h+var_968]
0x18008d3af  test    rax, rax
0x18008d3b2  jz      loc_18008D454
0x18008d3b8  lea     edi, [rax+rax]
0x18008d3bb  mov     r12d, eax
0x18008d3be  mov     [rsp+9B0h+var_960], edi
0x18008d3c2  jmp     loc_18008D454
0x18008d3c7  mov     rdx, r8
0x18008d3ca  cmp     [rax], bl
0x18008d3cc  jz      short loc_18008D3D7
0x18008d3ce  inc     rax
0x18008d3d1  sub     rdx, 1
0x18008d3d5  jnz     short loc_18008D3CA
0x18008d3d7  mov     rcx, r8
0x18008d3da  mov     rax, rdx
0x18008d3dd  sub     rcx, rdx
0x18008d3e0  neg     rax
0x18008d3e3  sbb     r8, r8
0x18008d3e6  and     r8, rcx
0x18008d3e9  mov     rcx, [rsp+9B0h+var_968]
0x18008d3ee  test    rdx, rdx
0x18008d3f1  jz      short loc_18008D454
0x18008d3f3  lea     r12d, [r8+1]
0x18008d3f7  mov     edi, r12d
0x18008d3fa  mov     [rsp+9B0h+var_960], r12d
0x18008d3ff  jmp     short loc_18008D454
0x18008d401  cmp     cs:gIsndpspEtwTracingAvailable, ebx
0x18008d407  jz      short loc_18008D431
0x18008d409  mov     rdx, qword ptr cs:xmmword_1800D0BE0+8
0x18008d410  test    rdx, rdx
0x18008d413  jz      short loc_18008D454
0x18008d415  mov     rcx, cs:gNdpspEtwContext
0x18008d41c  lea     r8, aRaslinemakecal_11; "RasLineMakeCall: Destination address is"...
0x18008d423  mov     rax, cs:gNdpspTemplateFunc
0x18008d42a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d42f  jmp     short loc_18008D44F
0x18008d431  mov     ecx, cs:dwTraceId; dwTraceID
0x18008d437  cmp     ecx, 0FFFFFFFFh
0x18008d43a  jz      short loc_18008D44F
0x18008d43c  lea     rdx, aRaslinemakecal_17; "RasLineMakeCall: Destination address is"...
0x18008d443  call    cs:__imp_TracePrintfA
0x18008d44a  nop     dword ptr [rax+rax+00h]
0x18008d44f  mov     rcx, [rsp+9B0h+var_968]
0x18008d454  test    r13, r13
0x18008d457  jz      short loc_18008D466
0x18008d459  mov     r13d, [r13+0]
0x18008d45d  sub     r13d, 0B4h
0x18008d464  jmp     short loc_18008D469
0x18008d466  mov     r13d, ebx
0x18008d469  mov     edx, [rcx+4]
0x18008d46c  lea     r8d, [r13+0E8h]
0x18008d473  add     r8d, edi
0x18008d476  lea     r9, [rsp+9B0h+lpMem]
0x18008d47b  mov     ecx, 7030115h
0x18008d480  call    PrepareAsyncRequest
0x18008d485  mov     r14d, eax
0x18008d488  mov     ecx, r15d
0x18008d48b  test    eax, eax
0x18008d48d  jz      short loc_18008D49E
0x18008d48f  call    ReleaseObjReadLock
0x18008d494  mov     rbx, [rsp+9B0h+lpMem]
0x18008d499  jmp     loc_18008D574
0x18008d49e  mov     rbx, [rsp+9B0h+lpMem]
0x18008d4a3  lea     rdi, [rbx+98h]
0x18008d4aa  call    ReleaseObjReadLock
0x18008d4af  lea     rdx, [rsp+9B0h+var_970]
0x18008d4b4  mov     rcx, rsi
0x18008d4b7  call    OpenObjHandle
0x18008d4bc  xor     r10d, r10d
0x18008d4bf  mov     r14d, eax
0x18008d4c2  test    eax, eax
0x18008d4c4  jz      short loc_18008D51C
0x18008d4c6  cmp     cs:gIsndpspEtwTracingAvailable, r10d
0x18008d4cd  jz      short loc_18008D4F9
0x18008d4cf  cmp     qword ptr cs:xmmword_1800D0BE0, r10
0x18008d4d6  jz      loc_18008D577
0x18008d4dc  mov     r8, rsi
0x18008d4df  mov     word ptr [rbp+8B0h+var_840], r10w
0x18008d4e4  lea     rdx, aRaslinemakecal_20; "RasLineMakeCall: Failed to map call obj"...
0x18008d4eb  lea     rcx, [rbp+8B0h+var_840]
0x18008d4ef  call    FormatRRASErrorString
0x18008d4f4  jmp     loc_18008D26B
0x18008d4f9  mov     ecx, cs:dwTraceId; dwTraceID
0x18008d4ff  cmp     ecx, 0FFFFFFFFh
0x18008d502  jz      short loc_18008D577
0x18008d504  mov     r8, rsi
0x18008d507  lea     rdx, aRaslinemakecal_8; "RasLineMakeCall: Failed to map call obj"...
0x18008d50e  call    cs:__imp_TracePrintfA
0x18008d515  nop     dword ptr [rax+rax+00h]
0x18008d51a  jmp     short loc_18008D574
0x18008d51c  mov     ecx, r15d
0x18008d51f  call    AcquireObjReadLock
0x18008d524  xor     r10d, r10d
0x18008d527  mov     r14d, eax
0x18008d52a  test    eax, eax
0x18008d52c  jz      loc_18008D627
0x18008d532  cmp     cs:gIsndpspEtwTracingAvailable, r10d
0x18008d539  jz      short loc_18008D553
0x18008d53b  cmp     qword ptr cs:xmmword_1800D0BE0, r10
0x18008d542  jz      short loc_18008D577
0x18008d544  mov     r8d, r15d
0x18008d547  lea     rdx, aRaslinemakecal_19; "RasLineMakeCall: Failed to reacquire re"...
0x18008d54e  jmp     loc_18008D25D
0x18008d553  mov     ecx, cs:dwTraceId; dwTraceID
0x18008d559  cmp     ecx, 0FFFFFFFFh
0x18008d55c  jz      short loc_18008D577
0x18008d55e  mov     r8d, r15d
0x18008d561  lea     rdx, aRaslinemakecal_12; "RasLineMakeCall: Failed to reacquire re"...
0x18008d568  call    cs:__imp_TracePrintfA
0x18008d56f  nop     dword ptr [rax+rax+00h]
0x18008d574  xor     r10d, r10d
0x18008d577  test    rbx, rbx
0x18008d57a  jz      short loc_18008D5E4
0x18008d57c  lea     rdi, [rbx+30h]
0x18008d580  mov     rcx, rdi; lpCriticalSection
0x18008d583  call    cs:__imp_EnterCriticalSection
0x18008d58a  nop     dword ptr [rax+rax+00h]
0x18008d58f  add     dword ptr [rbx+58h], 0FFFFFFFFh
0x18008d593  mov     rcx, rdi; lpCriticalSection
0x18008d596  jnz     short loc_18008D5D5
0x18008d598  call    cs:__imp_LeaveCriticalSection
0x18008d59f  nop     dword ptr [rax+rax+00h]
0x18008d5a4  mov     rcx, rdi; lpCriticalSection
0x18008d5a7  call    cs:__imp_DeleteCriticalSection
0x18008d5ae  nop     dword ptr [rax+rax+00h]
0x18008d5b3  call    cs:__imp_GetProcessHeap
0x18008d5ba  nop     dword ptr [rax+rax+00h]
0x18008d5bf  mov     r8, rbx; lpMem
0x18008d5c2  xor     edx, edx; dwFlags
0x18008d5c4  mov     rcx, rax; hHeap
0x18008d5c7  call    cs:__imp_HeapFree
0x18008d5ce  nop     dword ptr [rax+rax+00h]
0x18008d5d3  jmp     short loc_18008D5E1
0x18008d5d5  call    cs:__imp_LeaveCriticalSection
0x18008d5dc  nop     dword ptr [rax+rax+00h]
0x18008d5e1  xor     r10d, r10d
0x18008d5e4  cmp     [rsp+9B0h+var_970], r10d
0x18008d5e9  jnz     short loc_18008D619
0x18008d5eb  test    rsi, rsi
0x18008d5ee  jz      loc_18008D7D1
0x18008d5f4  call    cs:__imp_GetProcessHeap
0x18008d5fb  nop     dword ptr [rax+rax+00h]
0x18008d600  mov     r8, rsi; lpMem
0x18008d603  xor     edx, edx; dwFlags
0x18008d605  mov     rcx, rax; hHeap
0x18008d608  call    cs:__imp_HeapFree
0x18008d60f  nop     dword ptr [rax+rax+00h]
0x18008d614  jmp     loc_18008D7D1
0x18008d619  mov     ecx, [rsp+9B0h+var_970]
0x18008d61d  call    CloseObjHandle
0x18008d622  jmp     loc_18008D7D1
0x18008d627  mov     ecx, [rsp+9B0h+var_970]
0x18008d62b  mov     r8d, [rsp+9B0h+var_960]
0x18008d630  mov     rax, [rsp+9B0h+var_968]
0x18008d635  mov     [rsi+8], ecx
0x18008d638  mov     [rsp+9B0h+lpMem], rcx
0x18008d63d  mov     rax, [rax+10h]
0x18008d641  mov     [rdi+8], rax
0x18008d645  mov     [rdi+10h], rcx
0x18008d649  mov     [rdi+20h], r8d
0x18008d64d  test    r8d, r8d
0x18008d650  jz      loc_18008D714
  ... truncated ...
```
