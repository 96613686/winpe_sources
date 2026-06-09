# RasLineMakeCall

- ea: `0x180087070`
- end: `0x1800876c4`
- name: `RasLineMakeCall`
- size: `1620`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1800265e0`

## callees

- `0x180002ba6`
- `0x180071cec`
- `0x18008308c`
- `0x180084704`
- `0x180087070`
- `0x1800892bc`
- `0x1800897d8`
- `0x180089a9c`
- `0x18008a084`
- `0x18008a408`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!mbstowcs_s` at `0x1800872b1`
- `msvcrt!mbstowcs_s` at `0x1800872b1`
- `KERNEL32!DeleteCriticalSection` at `0x1800874ae`
- `KERNEL32!DeleteCriticalSection` at `0x1800874ae`
- `KERNEL32!GetProcessHeap` at `0x1800871db`
- `KERNEL32!GetProcessHeap` at `0x1800874b4`
- `KERNEL32!GetProcessHeap` at `0x1800874e0`
- `KERNEL32!GetProcessHeap` at `0x1800871db`
- `KERNEL32!GetProcessHeap` at `0x1800874b4`
- `KERNEL32!GetProcessHeap` at `0x1800874e0`
- `KERNEL32!HeapAlloc` at `0x1800871ed`
- `KERNEL32!HeapAlloc` at `0x1800871ed`
- `KERNEL32!LeaveCriticalSection` at `0x1800874a5`
- `KERNEL32!LeaveCriticalSection` at `0x1800874ca`
- `KERNEL32!LeaveCriticalSection` at `0x1800874a5`
- `KERNEL32!LeaveCriticalSection` at `0x1800874ca`
- `KERNEL32!EnterCriticalSection` at `0x180087496`
- `KERNEL32!EnterCriticalSection` at `0x180087496`
- `KERNEL32!HeapFree` at `0x1800874c2`
- `KERNEL32!HeapFree` at `0x1800874ee`
- `KERNEL32!HeapFree` at `0x1800874c2`
- `KERNEL32!HeapFree` at `0x1800874ee`
- `KERNEL32!WideCharToMultiByte` at `0x180087639`
- `KERNEL32!WideCharToMultiByte` at `0x180087639`
- `rtutils!TracePrintfA` at `0x180087152`
- `rtutils!TracePrintfA` at `0x1800871cd`
- `rtutils!TracePrintfA` at `0x180087254`
- `rtutils!TracePrintfA` at `0x18008736a`
- `rtutils!TracePrintfA` at `0x180087424`
- `rtutils!TracePrintfA` at `0x18008747f`
- `rtutils!TracePrintfA` at `0x180087152`
- `rtutils!TracePrintfA` at `0x1800871cd`
- `rtutils!TracePrintfA` at `0x180087254`
- `rtutils!TracePrintfA` at `0x18008736a`
- `rtutils!TracePrintfA` at `0x180087424`
- `rtutils!TracePrintfA` at `0x18008747f`

## string_xrefs

- `0x1800871c6`: `RasLineMakeCall: GetLineObjWithReadLock failed with error (0x%x)`
- `0x180087188`: `RasLineMakeCall: GetLineObjWithReadLock failed with error (0x%x)`
- `0x18008724d`: `RasLineMakeCall: Failed to create call obj`
- `0x180087226`: `RasLineMakeCall: Failed to create call obj`
- `0x180087478`: `RasLineMakeCall: Failed to reacquire read lock for obj (%p)`
- `0x180087458`: `RasLineMakeCall: Failed to reacquire read lock for obj (%p)`

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
  __int64 v53; // [rsp+88h] [rbp-78h]
  wchar_t DstBuf[104]; // [rsp+90h] [rbp-70h] BYREF
  int v55; // [rsp+160h] [rbp+60h] BYREF
  char v56[2044]; // [rsp+164h] [rbp+64h] BYREF

  v49 = a2;
  Src = a7;
  v52 = a5;
  v51 = a6;
  lpMem = 0;
  v45 = 0;
  v44 = 0;
  PtNumOfCharConverted = 0;
  v53 = a4;
  memset_0(DstBuf, 0, 0xC8u);
  v55 = 0;
  memset_0(v56, 0, sizeof(v56));
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( *((_QWORD *)&xmmword_1800C9BE0 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
        gNdpspEtwContext,
        *((_QWORD *)&xmmword_1800C9BE0 + 1),
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
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v55) = 0;
        FormatRRASErrorString(
          &v55,
          L"RasLineMakeCall: GetLineObjWithReadLock failed with error (0x%x)",
          LineObjWithReadLock);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v55);
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
      if ( *((_QWORD *)&xmmword_1800C9BE0 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
          gNdpspEtwContext,
          *((_QWORD *)&xmmword_1800C9BE0 + 1),
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
    if ( !*((_QWORD *)&xmmword_1800C9BE0 + 1) )
    {
LABEL_33:
      v14 = v45;
      goto LABEL_34;
    }
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
      gNdpspEtwContext,
      *((_QWORD *)&xmmword_1800C9BE0 + 1),
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
  Lock = PrepareAsyncRequest(117637397, *(unsigned int *)(v14 + 4), v21 + v15 + 232, &lpMem);
  if ( Lock )
  {
    ReleaseObjReadLock(a1);
    goto LABEL_55;
  }
  ReleaseObjReadLock(a1);
  Lock = OpenObjHandle((__int64)v11, &v44);
  if ( Lock )
  {
    if ( !gIsndpspEtwTracingAvailable )
    {
      if ( dwTraceId != -1 )
        TracePrintfA(dwTraceId, "RasLineMakeCall: Failed to map call object (%p) to handle", v11);
      goto LABEL_55;
    }
    if ( (_QWORD)xmmword_1800C9BE0 )
    {
      LOWORD(v55) = 0;
      FormatRRASErrorString(&v55, L"RasLineMakeCall: Failed to map call object (%p) to handle", v11);
LABEL_46:
      ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v55);
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
    if ( (_QWORD)xmmword_1800C9BE0 )
    {
      LOWORD(v55) = 0;
      FormatRRASErrorString(&v55, L"RasLineMakeCall: Failed to reacquire read lock for obj (%p)", a1);
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
    *(_DWORD *)v30 = v53;
  else
    *v52 = *(_DWORD *)v30;
  ReleaseObjReadLock(a1);
  AsyncDriverRequest(0x8FFF23C8, v28);
  return Lock;
}

```

## disassembly

```asm
0x180087070  mov     [rsp-8+arg_10], rbx
0x180087075  push    rbp
0x180087076  push    rsi
0x180087077  push    rdi
0x180087078  push    r12
0x18008707a  push    r13
0x18008707c  push    r14
0x18008707e  push    r15
0x180087080  lea     rbp, [rsp-870h]
0x180087088  sub     rsp, 970h
0x18008708f  mov     rax, cs:__security_cookie
0x180087096  xor     rax, rsp
0x180087099  mov     [rbp+8A0h+var_40], rax
0x1800870a0  mov     rax, [rbp+8A0h+arg_28]
0x1800870a7  xor     r13d, r13d
0x1800870aa  mov     r15, [rbp+8A0h+arg_30]
0x1800870b1  mov     rdi, rdx
0x1800870b4  mov     rbx, [rbp+8A0h+arg_20]
0x1800870bb  mov     r14d, ecx
0x1800870be  mov     [rsp+9A0h+var_938], rdx
0x1800870c3  lea     rcx, [rbp+8A0h+DstBuf]; void *
0x1800870c7  xor     edx, edx; Val
0x1800870c9  mov     [rsp+9A0h+Src], r15
0x1800870ce  mov     r8d, 0C8h; Size
0x1800870d4  mov     [rbp+8A0h+var_920], rbx
0x1800870d8  mov     [rsp+9A0h+var_928], rax
0x1800870dd  mov     [rsp+9A0h+lpMem], r13
0x1800870e2  mov     [rsp+9A0h+var_958], r13
0x1800870e7  mov     [rsp+9A0h+var_95C], r13d
0x1800870ec  mov     [rsp+9A0h+PtNumOfCharConverted], r13
0x1800870f1  mov     [rbp+8A0h+var_918], r9
0x1800870f5  call    memset_0
0x1800870fa  xor     edx, edx; Val
0x1800870fc  mov     [rbp+8A0h+var_840], r13d
0x180087100  mov     r8d, 7FCh; Size
0x180087106  lea     rcx, [rbp+8A0h+var_83C]; void *
0x18008710a  call    memset_0
0x18008710f  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180087116  jz      short loc_180087140
0x180087118  mov     rdx, qword ptr cs:xmmword_1800C9BE0+8
0x18008711f  test    rdx, rdx
0x180087122  jz      short loc_180087158
0x180087124  mov     rcx, cs:gNdpspEtwContext
0x18008712b  lea     r8, aRaslinemakecal; "RasLineMakeCall..."
0x180087132  mov     rax, cs:gNdpspTemplateFunc
0x180087139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008713e  jmp     short loc_180087158
0x180087140  mov     ecx, cs:dwTraceId; dwTraceID
0x180087146  cmp     ecx, 0FFFFFFFFh
0x180087149  jz      short loc_180087158
0x18008714b  lea     rdx, aRaslinemakecal_13; "RasLineMakeCall..."
0x180087152  call    cs:__imp_TracePrintfA
0x180087158  lea     rdx, [rsp+9A0h+var_958]
0x18008715d  mov     [rbx], r13d
0x180087160  mov     ecx, r14d
0x180087163  call    GetLineObjWithReadLock
0x180087168  mov     ebx, eax
0x18008716a  test    eax, eax
0x18008716c  jz      short loc_1800871DB
0x18008716e  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180087175  jz      short loc_1800871B8
0x180087177  cmp     qword ptr cs:xmmword_1800C9BE0, r13
0x18008717e  jz      short loc_1800871D3
0x180087180  mov     r8d, eax
0x180087183  mov     word ptr [rbp+8A0h+var_840], r13w
0x180087188  lea     rdx, aRaslinemakecal_0; "RasLineMakeCall: GetLineObjWithReadLock"...
0x18008718f  lea     rcx, [rbp+8A0h+var_840]
0x180087193  call    FormatRRASErrorString
0x180087198  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x18008719f  lea     r8, [rbp+8A0h+var_840]
0x1800871a3  mov     rcx, cs:gNdpspEtwContext
0x1800871aa  mov     rax, cs:gNdpspTemplateFunc
0x1800871b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800871b6  jmp     short loc_1800871D3
0x1800871b8  mov     ecx, cs:dwTraceId; dwTraceID
0x1800871be  cmp     ecx, 0FFFFFFFFh
0x1800871c1  jz      short loc_1800871D3
0x1800871c3  mov     r8d, eax
0x1800871c6  lea     rdx, aRaslinemakecal_14; "RasLineMakeCall: GetLineObjWithReadLock"...
0x1800871cd  call    cs:__imp_TracePrintfA
0x1800871d3  mov     rsi, r13
0x1800871d6  jmp     loc_180087485
0x1800871db  call    cs:__imp_GetProcessHeap
0x1800871e1  mov     edx, 8; dwFlags
0x1800871e6  mov     rcx, rax; hHeap
0x1800871e9  lea     r8d, [rdx+40h]; dwBytes
0x1800871ed  call    cs:__imp_HeapAlloc
0x1800871f3  mov     rsi, rax
0x1800871f6  test    rax, rax
0x1800871f9  jnz     short loc_18008725F
0x1800871fb  mov     ecx, r14d
0x1800871fe  lea     ebx, [rax+0Eh]
0x180087201  call    ReleaseObjReadLock
0x180087206  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008720d  jz      short loc_18008723E
0x18008720f  mov     rdx, qword ptr cs:xmmword_1800C9BE0+8
0x180087216  test    rdx, rdx
0x180087219  jz      loc_180087698
0x18008721f  mov     rcx, cs:gNdpspEtwContext
0x180087226  lea     r8, aRaslinemakecal_4; "RasLineMakeCall: Failed to create call "...
0x18008722d  mov     rax, cs:gNdpspTemplateFunc
0x180087234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087239  jmp     loc_180087698
0x18008723e  mov     ecx, cs:dwTraceId; dwTraceID
0x180087244  cmp     ecx, 0FFFFFFFFh
0x180087247  jz      loc_180087698
0x18008724d  lea     rdx, aRaslinemakecal_5; "RasLineMakeCall: Failed to create call "...
0x180087254  call    cs:__imp_TracePrintfA
0x18008725a  jmp     loc_180087698
0x18008725f  mov     rdx, [rsp+9A0h+var_958]
0x180087264  mov     ecx, r13d
0x180087267  mov     dword ptr [rax], 4F43414Ch
0x18008726d  mov     r12d, r13d
0x180087270  mov     [rsp+9A0h+var_960], ecx
0x180087274  mov     eax, [rdx+4]
0x180087277  mov     [rsi+4], eax
0x18008727a  mov     [rsi+20h], r14d
0x18008727e  mov     dword ptr [rsi+40h], 1
0x180087285  mov     eax, [rdx+38h]
0x180087288  mov     [rsp+9A0h+var_950], eax
0x18008728c  test    rdi, rdi
0x18008728f  jz      short loc_180087310
0x180087291  cmp     eax, 0Ch
0x180087294  jz      short loc_1800872D2
0x180087296  mov     r9, rdi; SrcBuf
0x180087299  mov     [rsp+9A0h+MaxCount], 63h ; 'c'; MaxCount
0x1800872a2  mov     r8d, 64h ; 'd'; SizeInWords
0x1800872a8  lea     rdx, [rbp+8A0h+DstBuf]; DstBuf
0x1800872ac  lea     rcx, [rsp+9A0h+PtNumOfCharConverted]; PtNumOfCharConverted
0x1800872b1  call    cs:__imp_mbstowcs_s
0x1800872b7  mov     rax, [rsp+9A0h+PtNumOfCharConverted]
0x1800872bc  mov     rdx, [rsp+9A0h+var_958]
0x1800872c1  test    rax, rax
0x1800872c4  jz      loc_180087372
0x1800872ca  mov     r12d, eax
0x1800872cd  lea     ecx, [rax+rax]
0x1800872d0  jmp     short loc_18008730A
0x1800872d2  mov     edx, 7FFFFFFFh
0x1800872d7  mov     rax, rdi
0x1800872da  mov     ecx, edx
0x1800872dc  cmp     [rax], r13b
0x1800872df  jz      short loc_1800872EA
0x1800872e1  inc     rax
0x1800872e4  sub     rcx, 1
0x1800872e8  jnz     short loc_1800872DC
0x1800872ea  sub     rdx, rcx
0x1800872ed  mov     rax, rcx
0x1800872f0  neg     rax
0x1800872f3  sbb     r8, r8
0x1800872f6  and     r8, rdx
0x1800872f9  mov     rdx, [rsp+9A0h+var_958]
0x1800872fe  test    rcx, rcx
0x180087301  jz      short loc_180087372
0x180087303  lea     r12d, [r8+1]
0x180087307  mov     ecx, r12d
0x18008730a  mov     [rsp+9A0h+var_960], ecx
0x18008730e  jmp     short loc_180087347
0x180087310  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180087317  jz      short loc_180087358
0x180087319  mov     rdx, qword ptr cs:xmmword_1800C9BE0+8
0x180087320  test    rdx, rdx
0x180087323  jz      short loc_180087342
0x180087325  mov     rcx, cs:gNdpspEtwContext
0x18008732c  lea     r8, aRaslinemakecal_11; "RasLineMakeCall: Destination address is"...
0x180087333  mov     rax, cs:gNdpspTemplateFunc
0x18008733a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008733f  mov     ecx, r13d
0x180087342  mov     rdx, [rsp+9A0h+var_958]
0x180087347  test    r15, r15
0x18008734a  jz      short loc_180087377
0x18008734c  mov     r15d, [r15]
0x18008734f  sub     r15d, 0B4h
0x180087356  jmp     short loc_18008737A
0x180087358  mov     ecx, cs:dwTraceId; dwTraceID
0x18008735e  cmp     ecx, 0FFFFFFFFh
0x180087361  jz      short loc_180087372
0x180087363  lea     rdx, aRaslinemakecal_17; "RasLineMakeCall: Destination address is"...
0x18008736a  call    cs:__imp_TracePrintfA
0x180087370  jmp     short loc_18008733F
0x180087372  mov     ecx, r13d
0x180087375  jmp     short loc_180087347
0x180087377  mov     r15d, r13d
0x18008737a  mov     edx, [rdx+4]
0x18008737d  lea     r8d, [rcx+0E8h]
0x180087384  add     r8d, r15d
0x180087387  lea     r9, [rsp+9A0h+lpMem]
0x18008738c  mov     ecx, 7030115h
0x180087391  call    PrepareAsyncRequest
0x180087396  mov     ebx, eax
0x180087398  mov     ecx, r14d
0x18008739b  test    eax, eax
0x18008739d  jz      short loc_1800873A9
0x18008739f  call    ReleaseObjReadLock
0x1800873a4  jmp     loc_180087485
0x1800873a9  call    ReleaseObjReadLock
0x1800873ae  lea     rdx, [rsp+9A0h+var_95C]
0x1800873b3  mov     rcx, rsi
0x1800873b6  call    OpenObjHandle
0x1800873bb  mov     ebx, eax
0x1800873bd  test    eax, eax
0x1800873bf  jz      short loc_18008742C
0x1800873c1  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x1800873c8  jz      short loc_18008740F
0x1800873ca  cmp     qword ptr cs:xmmword_1800C9BE0, r13
0x1800873d1  jz      loc_180087485
0x1800873d7  mov     r8, rsi
0x1800873da  mov     word ptr [rbp+8A0h+var_840], r13w
0x1800873df  lea     rdx, aRaslinemakecal_20; "RasLineMakeCall: Failed to map call obj"...
0x1800873e6  lea     rcx, [rbp+8A0h+var_840]
0x1800873ea  call    FormatRRASErrorString
0x1800873ef  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x1800873f6  lea     r8, [rbp+8A0h+var_840]
0x1800873fa  mov     rcx, cs:gNdpspEtwContext
0x180087401  mov     rax, cs:gNdpspTemplateFunc
0x180087408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008740d  jmp     short loc_180087485
0x18008740f  mov     ecx, cs:dwTraceId; dwTraceID
0x180087415  cmp     ecx, 0FFFFFFFFh
0x180087418  jz      short loc_180087485
0x18008741a  mov     r8, rsi
0x18008741d  lea     rdx, aRaslinemakecal_8; "RasLineMakeCall: Failed to map call obj"...
0x180087424  call    cs:__imp_TracePrintfA
0x18008742a  jmp     short loc_180087485
0x18008742c  mov     ecx, r14d
0x18008742f  call    AcquireObjReadLock
0x180087434  mov     ebx, eax
0x180087436  test    eax, eax
0x180087438  jz      loc_180087507
0x18008743e  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180087445  jz      short loc_18008746A
0x180087447  cmp     qword ptr cs:xmmword_1800C9BE0, r13
0x18008744e  jz      short loc_180087485
0x180087450  mov     r8d, r14d
0x180087453  mov     word ptr [rbp+8A0h+var_840], r13w
0x180087458  lea     rdx, aRaslinemakecal_19; "RasLineMakeCall: Failed to reacquire re"...
0x18008745f  lea     rcx, [rbp+8A0h+var_840]
0x180087463  call    FormatRRASErrorString
0x180087468  jmp     short loc_1800873EF
0x18008746a  mov     ecx, cs:dwTraceId; dwTraceID
0x180087470  cmp     ecx, 0FFFFFFFFh
0x180087473  jz      short loc_180087485
0x180087475  mov     r8d, r14d
0x180087478  lea     rdx, aRaslinemakecal_12; "RasLineMakeCall: Failed to reacquire re"...
0x18008747f  call    cs:__imp_TracePrintfA
0x180087485  mov     rdi, [rsp+9A0h+lpMem]
0x18008748a  test    rdi, rdi
0x18008748d  jz      short loc_1800874D0
0x18008748f  lea     r14, [rdi+30h]
0x180087493  mov     rcx, r14; lpCriticalSection
0x180087496  call    cs:__imp_EnterCriticalSection
0x18008749c  add     dword ptr [rdi+58h], 0FFFFFFFFh
0x1800874a0  mov     rcx, r14; lpCriticalSection
0x1800874a3  jnz     short loc_1800874CA
0x1800874a5  call    cs:__imp_LeaveCriticalSection
0x1800874ab  mov     rcx, r14; lpCriticalSection
0x1800874ae  call    cs:__imp_DeleteCriticalSection
0x1800874b4  call    cs:__imp_GetProcessHeap
0x1800874ba  mov     r8, rdi; lpMem
0x1800874bd  xor     edx, edx; dwFlags
0x1800874bf  mov     rcx, rax; hHeap
0x1800874c2  call    cs:__imp_HeapFree
0x1800874c8  jmp     short loc_1800874D0
0x1800874ca  call    cs:__imp_LeaveCriticalSection
0x1800874d0  cmp     [rsp+9A0h+var_95C], r13d
0x1800874d5  jnz     short loc_1800874F9
0x1800874d7  test    rsi, rsi
0x1800874da  jz      loc_180087698
0x1800874e0  call    cs:__imp_GetProcessHeap
0x1800874e6  mov     r8, rsi; lpMem
0x1800874e9  xor     edx, edx; dwFlags
0x1800874eb  mov     rcx, rax; hHeap
0x1800874ee  call    cs:__imp_HeapFree
0x1800874f4  jmp     loc_180087698
0x1800874f9  mov     ecx, [rsp+9A0h+var_95C]
0x1800874fd  call    CloseObjHandle
0x180087502  jmp     loc_180087698
0x180087507  mov     ecx, [rsp+9A0h+var_95C]
0x18008750b  xor     r10d, r10d
0x18008750e  mov     r13, [rsp+9A0h+lpMem]
0x180087513  mov     rax, [rsp+9A0h+var_958]
0x180087518  mov     [rsi+8], ecx
0x18008751b  mov     [rsp+9A0h+lpMem], rcx
0x180087520  lea     rdi, [r13+98h]
0x180087527  mov     rax, [rax+10h]
0x18008752b  mov     [rdi+10h], rcx
0x18008752f  mov     ecx, [rsp+9A0h+var_960]
0x180087533  mov     [rdi+8], rax
0x180087537  mov     [rdi+20h], ecx
0x18008753a  test    ecx, ecx
0x18008753c  jz      loc_1800875E0
0x180087542  mov     edx, r15d
0x180087545  add     rdx, 0E8h
0x18008754c  add     rdx, rdi
0x18008754f  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180087553  mov     eax, edx
0x180087555  sub     eax, edi
0x180087557  cmp     [rsp+9A0h+var_950], 0Ch
0x18008755c  mov     [rdi+24h], eax
0x18008755f  jnz     short loc_180087599
0x180087561  cmp     rcx, 7FFFFFFEh
  ... truncated ...
```
