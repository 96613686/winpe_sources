# TrustScannerThreadProc(void *)

- ea: `0x1800325c0`
- end: `0x1800328b2`
- name: `?TrustScannerThreadProc@@YAKPEAX@Z`
- size: `754`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x18000fd18`
- `0x18000fd40`
- `0x18002f62c`
- `0x180030710`
- `0x180030784`
- `0x180031d70`
- `0x18003219c`
- `0x1800321b0`
- `0x1800325c0`
- `0x180032958`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800325f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800325f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800325f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800325f8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800328a4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800328a4`

## pseudocode

```c
void __fastcall __noreturn TrustScannerThreadProc(HMODULE Parameter)
{
  unsigned int v2; // edi
  DWORD CurrentThreadId; // ebx
  DWORD v4; // eax
  __int64 v5; // r8
  int v6; // eax
  struct _SCANNER_REQUEST *v7; // rbx
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  struct _LIST_ENTRY *v10; // rcx
  __int64 v11; // rax
  struct _LIST_ENTRY *Blink; // rdx
  struct _LIST_ENTRY v13; // [rsp+30h] [rbp-18h] BYREF
  int v14; // [rsp+80h] [rbp+38h] BYREF

  v14 = 0;
  v13 = 0;
  v2 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = GetCurrentThreadId();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, v5, v4, CurrentThreadId);
  }
  v13.Blink = &v13;
  v13.Flink = &v13;
  v6 = RunningOnPDC(&v14);
  if ( v6 < 0 )
  {
LABEL_35:
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        61,
        &WPP_844d483327f83d00fc717282eb3891a9_Traceguids,
        (unsigned int)v6);
LABEL_37:
    FreeScannerRequestList(&v13);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_844d483327f83d00fc717282eb3891a9_Traceguids);
    FreeLibraryAndExitThread(Parameter, 0);
  }
  while ( 1 )
  {
    AcquireTrustScannerLock();
    if ( !v14 )
      break;
    if ( !LsaDbEnablePDCTrustScanner )
    {
      v9 = WPP_GLOBAL_Control;
      goto LABEL_16;
    }
    v7 = (struct _SCANNER_REQUEST *)gScannerRequests;
    if ( gScannerRequests != &gScannerRequests )
    {
      if ( *((HLOCAL **)gScannerRequests + 1) != &gScannerRequests )
        goto LABEL_40;
      v8 = *(_QWORD **)gScannerRequests;
      if ( *(HLOCAL *)(*(_QWORD *)gScannerRequests + 8LL) != gScannerRequests )
        goto LABEL_40;
      --gcScannerRequests;
      gScannerRequests = v8;
      v8[1] = &gScannerRequests;
      *((_QWORD *)v7 + 1) = v7;
      *(_QWORD *)v7 = v7;
      goto LABEL_29;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_844d483327f83d00fc717282eb3891a9_Traceguids, v2);
LABEL_28:
    v7 = 0;
    gfTrustScannerThreadRunning = 0;
LABEL_29:
    ReleaseTrustScannerLock();
    if ( !v7 )
      goto LABEL_37;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_844d483327f83d00fc717282eb3891a9_Traceguids, v2);
    ProcessScannerRequest(v7);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_844d483327f83d00fc717282eb3891a9_Traceguids);
    FreeScannerRequest(v7);
    ++v2;
    v6 = RunningOnPDC(&v14);
    if ( v6 < 0 )
      goto LABEL_35;
  }
  v9 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_844d483327f83d00fc717282eb3891a9_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  if ( !LsaDbEnablePDCTrustScanner )
  {
LABEL_16:
    if ( (*((_BYTE *)v9 + 28) & 0x10) != 0 )
    {
      WPP_SF_(v9[2], 63, &WPP_844d483327f83d00fc717282eb3891a9_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
  }
  v10 = (struct _LIST_ENTRY *)gScannerRequests;
  if ( gScannerRequests != &gScannerRequests )
  {
    if ( (*((_BYTE *)v9 + 28) & 0x10) != 0 )
    {
      WPP_SF_d(v9[2], 64, &WPP_844d483327f83d00fc717282eb3891a9_Traceguids, gcScannerRequests);
      v10 = (struct _LIST_ENTRY *)gScannerRequests;
    }
    if ( (HLOCAL *)v10->Blink != &gScannerRequests
      || (v11 = qword_1800481C8, *(HLOCAL **)qword_1800481C8 != &gScannerRequests)
      || (*(_QWORD *)qword_1800481C8 = v10,
          v10->Blink = (struct _LIST_ENTRY *)v11,
          qword_1800481C8 = (__int64)&gScannerRequests,
          gScannerRequests = &gScannerRequests,
          gcScannerRequests = 0,
          v13.Flink->Blink != &v13)
      || (Blink = v13.Blink, v13.Blink->Flink != &v13)
      || v10->Flink->Blink != v10
      || v10->Blink->Flink != v10 )
    {
LABEL_40:
      __fastfail(3u);
    }
    v13.Blink->Flink = v10;
    v13.Blink = v10->Blink;
    v10->Blink->Flink = &v13;
    v10->Blink = Blink;
  }
  goto LABEL_28;
}

```

## disassembly

```asm
0x1800325c0  push    rbp
0x1800325c2  push    rbx
0x1800325c3  push    rsi
0x1800325c4  push    rdi
0x1800325c5  push    r12
0x1800325c7  push    r13
0x1800325c9  mov     rbp, rsp
0x1800325cc  sub     rsp, 48h
0x1800325d0  xorps   xmm0, xmm0
0x1800325d3  mov     [rbp+arg_0], 0
0x1800325da  movups  xmmword ptr [rbp+var_18.Flink], xmm0
0x1800325de  mov     rsi, rcx
0x1800325e1  xor     edi, edi
0x1800325e3  mov     rax, cs:WPP_GLOBAL_Control
0x1800325ea  test    byte ptr [rax+1Ch], 10h
0x1800325ee  jz      short loc_180032618
0x1800325f0  call    cs:__imp_GetCurrentThreadId
0x1800325f6  mov     ebx, eax
0x1800325f8  call    cs:__imp_GetCurrentThreadId
0x1800325fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180032605  lea     edx, [rdi+3Ch]
0x180032608  mov     r9d, eax
0x18003260b  mov     [rsp+48h+var_28], ebx
0x18003260f  mov     rcx, [rcx+10h]
0x180032613  call    WPP_SF_Dd
0x180032618  lea     rax, [rbp+var_18]
0x18003261c  mov     [rbp+var_18.Blink], rax
0x180032620  lea     rcx, [rbp+arg_0]; int *
0x180032624  lea     rax, [rbp+var_18]
0x180032628  mov     [rbp+var_18.Flink], rax
0x18003262c  call    ?RunningOnPDC@@YAJPEAH@Z; RunningOnPDC(int *)
0x180032631  lea     r13, WPP_844d483327f83d00fc717282eb3891a9_Traceguids
0x180032638  test    eax, eax
0x18003263a  js      loc_180032857
0x180032640  lea     r12, ?gScannerRequests@@3U_LIST_ENTRY@@A; _LIST_ENTRY gScannerRequests
0x180032647  call    ?AcquireTrustScannerLock@@YAXXZ; AcquireTrustScannerLock(void)
0x18003264c  cmp     [rbp+arg_0], 0
0x180032650  jz      short loc_1800326CE
0x180032652  cmp     cs:?LsaDbEnablePDCTrustScanner@@3KA, 0; ulong LsaDbEnablePDCTrustScanner
0x180032659  jz      short loc_1800326C5
0x18003265b  mov     rbx, cs:?gScannerRequests@@3U_LIST_ENTRY@@A; _LIST_ENTRY gScannerRequests
0x180032662  cmp     rbx, r12
0x180032665  jnz     short loc_180032691
0x180032667  mov     rcx, cs:WPP_GLOBAL_Control
0x18003266e  test    byte ptr [rcx+1Ch], 10h
0x180032672  jz      loc_1800327DF
0x180032678  mov     rcx, [rcx+10h]
0x18003267c  mov     edx, 41h ; 'A'
0x180032681  mov     r9d, edi
0x180032684  mov     r8, r13
0x180032687  call    WPP_SF_d
0x18003268c  jmp     loc_1800327DF
0x180032691  cmp     [rbx+8], r12
0x180032695  jnz     loc_1800328AB
0x18003269b  mov     rax, [rbx]
0x18003269e  cmp     [rax+8], rbx
0x1800326a2  jnz     loc_1800328AB
0x1800326a8  dec     cs:?gcScannerRequests@@3KA; ulong gcScannerRequests
0x1800326ae  mov     cs:?gScannerRequests@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY gScannerRequests
0x1800326b5  mov     [rax+8], r12
0x1800326b9  mov     [rbx+8], rbx
0x1800326bd  mov     [rbx], rbx
0x1800326c0  jmp     loc_1800327E7
0x1800326c5  mov     rax, cs:WPP_GLOBAL_Control
0x1800326cc  jmp     short loc_1800326FC
0x1800326ce  mov     rax, cs:WPP_GLOBAL_Control
0x1800326d5  test    byte ptr [rax+1Ch], 10h
0x1800326d9  jz      short loc_1800326F3
0x1800326db  mov     rcx, [rax+10h]
0x1800326df  mov     edx, 3Eh ; '>'
0x1800326e4  mov     r8, r13
0x1800326e7  call    WPP_SF_
0x1800326ec  mov     rax, cs:WPP_GLOBAL_Control
0x1800326f3  cmp     cs:?LsaDbEnablePDCTrustScanner@@3KA, 0; ulong LsaDbEnablePDCTrustScanner
0x1800326fa  jnz     short loc_18003271A
0x1800326fc  test    byte ptr [rax+1Ch], 10h
0x180032700  jz      short loc_18003271A
0x180032702  mov     rcx, [rax+10h]
0x180032706  mov     edx, 3Fh ; '?'
0x18003270b  mov     r8, r13
0x18003270e  call    WPP_SF_
0x180032713  mov     rax, cs:WPP_GLOBAL_Control
0x18003271a  mov     rcx, cs:?gScannerRequests@@3U_LIST_ENTRY@@A; _LIST_ENTRY gScannerRequests
0x180032721  cmp     rcx, r12
0x180032724  jz      loc_1800327DF
0x18003272a  test    byte ptr [rax+1Ch], 10h
0x18003272e  jz      short loc_18003274F
0x180032730  mov     r9d, cs:?gcScannerRequests@@3KA; ulong gcScannerRequests
0x180032737  mov     edx, 40h ; '@'
0x18003273c  mov     rcx, [rax+10h]
0x180032740  mov     r8, r13
0x180032743  call    WPP_SF_d
0x180032748  mov     rcx, cs:?gScannerRequests@@3U_LIST_ENTRY@@A; _LIST_ENTRY gScannerRequests
0x18003274f  cmp     [rcx+8], r12
0x180032753  jnz     loc_1800328AB
0x180032759  mov     rax, cs:qword_1800481C8
0x180032760  cmp     [rax], r12
0x180032763  jnz     loc_1800328AB
0x180032769  mov     [rax], rcx
0x18003276c  lea     rdx, [rbp+var_18]
0x180032770  mov     [rcx+8], rax
0x180032774  mov     rax, [rbp+var_18.Flink]
0x180032778  mov     cs:qword_1800481C8, r12
0x18003277f  mov     cs:?gScannerRequests@@3U_LIST_ENTRY@@A, r12; _LIST_ENTRY gScannerRequests
0x180032786  mov     cs:?gcScannerRequests@@3KA, 0; ulong gcScannerRequests
0x180032790  cmp     [rax+8], rdx
0x180032794  jnz     loc_1800328AB
0x18003279a  mov     rdx, [rbp+var_18.Blink]
0x18003279e  lea     rax, [rbp+var_18]
0x1800327a2  cmp     [rdx], rax
0x1800327a5  jnz     loc_1800328AB
0x1800327ab  mov     rax, [rcx]
0x1800327ae  cmp     [rax+8], rcx
0x1800327b2  jnz     loc_1800328AB
0x1800327b8  mov     rax, [rcx+8]
0x1800327bc  cmp     [rax], rcx
0x1800327bf  jnz     loc_1800328AB
0x1800327c5  mov     [rdx], rcx
0x1800327c8  lea     r8, [rbp+var_18]
0x1800327cc  mov     rax, [rcx+8]
0x1800327d0  mov     [rbp+var_18.Blink], rax
0x1800327d4  mov     rax, [rcx+8]
0x1800327d8  mov     [rax], r8
0x1800327db  mov     [rcx+8], rdx
0x1800327df  xor     ebx, ebx
0x1800327e1  mov     cs:?gfTrustScannerThreadRunning@@3HA, ebx; int gfTrustScannerThreadRunning
0x1800327e7  call    ?ReleaseTrustScannerLock@@YAXXZ; ReleaseTrustScannerLock(void)
0x1800327ec  test    rbx, rbx
0x1800327ef  jz      loc_180032878
0x1800327f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800327fc  test    byte ptr [rcx+1Ch], 10h
0x180032800  jz      short loc_180032816
0x180032802  mov     rcx, [rcx+10h]
0x180032806  mov     edx, 42h ; 'B'
0x18003280b  mov     r9d, edi
0x18003280e  mov     r8, r13
0x180032811  call    WPP_SF_d
0x180032816  mov     rcx, rbx; struct _SCANNER_REQUEST *
0x180032819  call    ?ProcessScannerRequest@@YAXPEAU_SCANNER_REQUEST@@@Z; ProcessScannerRequest(_SCANNER_REQUEST *)
0x18003281e  mov     rcx, cs:WPP_GLOBAL_Control
0x180032825  test    byte ptr [rcx+1Ch], 10h
0x180032829  jz      short loc_18003283C
0x18003282b  mov     rcx, [rcx+10h]
0x18003282f  mov     edx, 43h ; 'C'
0x180032834  mov     r8, r13
0x180032837  call    WPP_SF_
0x18003283c  mov     rcx, rbx; hMem
0x18003283f  call    ?FreeScannerRequest@@YAXPEAU_SCANNER_REQUEST@@@Z; FreeScannerRequest(_SCANNER_REQUEST *)
0x180032844  lea     rcx, [rbp+arg_0]; int *
0x180032848  inc     edi
0x18003284a  call    ?RunningOnPDC@@YAJPEAH@Z; RunningOnPDC(int *)
0x18003284f  test    eax, eax
0x180032851  jns     loc_180032647
0x180032857  mov     rcx, cs:WPP_GLOBAL_Control
0x18003285e  test    byte ptr [rcx+1Ch], 10h
0x180032862  jz      short loc_180032878
0x180032864  mov     rcx, [rcx+10h]
0x180032868  mov     edx, 3Dh ; '='
0x18003286d  mov     r9d, eax
0x180032870  mov     r8, r13
0x180032873  call    WPP_SF_d
0x180032878  lea     rcx, [rbp+var_18]; struct _LIST_ENTRY *
0x18003287c  call    ?FreeScannerRequestList@@YAXPEAU_LIST_ENTRY@@@Z; FreeScannerRequestList(_LIST_ENTRY *)
0x180032881  mov     rcx, cs:WPP_GLOBAL_Control
0x180032888  test    byte ptr [rcx+1Ch], 10h
0x18003288c  jz      short loc_18003289F
0x18003288e  mov     rcx, [rcx+10h]
0x180032892  mov     edx, 44h ; 'D'
0x180032897  mov     r8, r13
0x18003289a  call    WPP_SF_
0x18003289f  xor     edx, edx; dwExitCode
0x1800328a1  mov     rcx, rsi; hLibModule
0x1800328a4  call    cs:__imp_FreeLibraryAndExitThread
0x1800328aa  int     3; Trap to Debugger
0x1800328ab  mov     ecx, 3
0x1800328b0  int     29h; Win8: RtlFailFast(ecx)
```
