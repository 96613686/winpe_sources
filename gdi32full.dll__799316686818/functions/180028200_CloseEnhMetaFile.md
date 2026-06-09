# CloseEnhMetaFile

- ea: `0x180028200`
- end: `0x180028540`
- name: `CloseEnhMetaFile`
- size: `832`
- prototype: `HENHMETAFILE __stdcall(HDC hdc)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002b5a0`

## callees

- `0x180023650`
- `0x180023858`
- `0x180023aa4`
- `0x180024010`
- `0x180026cf0`
- `0x180028200`
- `0x180028550`
- `0x180028860`
- `0x180028a24`
- `0x180028ae0`
- `0x180028b54`
- `0x180028f18`
- `0x18004c8fc`
- `0x18004ca5c`
- `0x180080c34`
- `0x18008e090`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800284e0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800284e0`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800284bc`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800284bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800284fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800284fd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800282c6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800282da`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800282ee`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180028302`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800282c6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800282da`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800282ee`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180028302`
- `GDI32!RestoreDC` at `0x180028280`
- `GDI32!RestoreDC` at `0x180028280`
- `GDI32!pldcGet` at `0x18002820c`
- `GDI32!pldcGet` at `0x18002820c`
- `GDI32!GdiSetLastError` at `0x18002841b`
- `GDI32!GdiSetLastError` at `0x18002841b`
- `GDI32!DeleteObject` at `0x18002846b`
- `GDI32!DeleteObject` at `0x18002847d`
- `GDI32!DeleteObject` at `0x18002846b`
- `GDI32!DeleteObject` at `0x18002847d`

## pseudocode

```c
HENHMETAFILE __stdcall CloseEnhMetaFile(HDC hdc)
{
  __int64 v2; // rax
  _QWORD *v3; // rbx
  void *v4; // rcx
  HENHMETAFILE EnhMetaFileW; // rbp
  void *v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // eax
  int v11; // ecx
  int v12; // r8d
  int v13; // edx
  int v14; // eax
  int v15; // ecx
  int v16; // r8d
  int v17; // edx
  int v18; // eax
  int v19; // ecx
  int v20; // r8d
  int v21; // edx
  char *v22; // rax
  int v23; // eax
  unsigned int *v24; // rcx
  unsigned int *v25; // r9
  unsigned int v27; // eax
  __int64 v28; // r9
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp+10h] BYREF

  v2 = pldcGet(hdc);
  v3 = (_QWORD *)v2;
  if ( !v2 || ((unsigned int)hdc & 0x7F0000) == 0x660000 )
  {
    GdiSetLastError(6);
  }
  else if ( *(_DWORD *)(v2 + 12) == 2 )
  {
    v4 = *(void **)(v2 + 304);
    EnhMetaFileW = 0;
    if ( v4 )
    {
      DeleteObject(v4);
      v3[38] = 0;
    }
    v6 = (void *)v3[39];
    if ( v6 )
    {
      DeleteObject(v6);
      v3[39] = 0;
    }
    v7 = v3[2];
    if ( *(_DWORD *)(v7 + 132) )
      GlmfCloseMetaFile(hdc);
    if ( (*(_BYTE *)(v7 + 32) & 2) != 0 )
      goto LABEL_32;
    RestoreDC(hdc, 1);
    v8 = *(unsigned int *)(v7 + 164);
    v9 = *(_QWORD *)(v7 + 168);
    *(_DWORD *)(v7 + 104) = v8;
    if ( !(unsigned int)MF_EOF(hdc, v8, v9) )
      goto LABEL_32;
    MDC::vFlushBounds((MDC *)v7);
    if ( (unsigned int)ERECTL::bEmpty((ERECTL *)(v7 + 60)) )
    {
      v10 = MulDiv(100 * *(_DWORD *)(v7 + 44), *(_DWORD *)(v7 + 116), *(_DWORD *)(v7 + 108));
      v11 = 100 * *(_DWORD *)(v7 + 52);
      v12 = *(_DWORD *)(v7 + 108);
      v13 = *(_DWORD *)(v7 + 116);
      *(_DWORD *)(v7 + 60) = v10;
      v14 = MulDiv(v11, v13, v12);
      v15 = 100 * *(_DWORD *)(v7 + 48);
      v16 = *(_DWORD *)(v7 + 112);
      v17 = *(_DWORD *)(v7 + 120);
      *(_DWORD *)(v7 + 68) = v14;
      v18 = MulDiv(v15, v17, v16);
      v19 = 100 * *(_DWORD *)(v7 + 56);
      v20 = *(_DWORD *)(v7 + 112);
      v21 = *(_DWORD *)(v7 + 120);
      *(_DWORD *)(v7 + 64) = v18;
      *(_DWORD *)(v7 + 72) = MulDiv(v19, v21, v20);
    }
    if ( (*(_BYTE *)(v7 + 32) & 1) != 0 )
    {
      NumberOfBytesWritten = 0;
      if ( !(unsigned int)MDC::bFlush((MDC *)v7)
        || SetFilePointer(*(HANDLE *)(v7 + 8), 0, 0, 0)
        || !WriteFile(*(HANDLE *)(v7 + 8), (LPCVOID)(v7 + 36), 0x6Cu, &NumberOfBytesWritten, 0)
        || NumberOfBytesWritten != 108 )
      {
        goto LABEL_32;
      }
      CloseHandle(*(HANDLE *)(v7 + 8));
      *(_QWORD *)(v7 + 8) = -1;
    }
    else
    {
      v22 = *(char **)(v7 + 16);
      if ( *(char *)(v7 + 32) < 0 )
        v22 = (char *)EMFContainer::ObtainPtr((EMFContainer *)(v22 + 80), *((_DWORD *)v22 + 15), 0x6Cu);
      if ( !v22 )
        goto LABEL_32;
      *(_OWORD *)v22 = *(_OWORD *)(v7 + 36);
      *((_OWORD *)v22 + 1) = *(_OWORD *)(v7 + 52);
      *((_OWORD *)v22 + 2) = *(_OWORD *)(v7 + 68);
      *((_OWORD *)v22 + 3) = *(_OWORD *)(v7 + 84);
      *((_OWORD *)v22 + 4) = *(_OWORD *)(v7 + 100);
      *((_OWORD *)v22 + 5) = *(_OWORD *)(v7 + 116);
      *(_OWORD *)(v22 + 92) = *(_OWORD *)(v7 + 128);
      if ( *(char *)(v7 + 32) < 0 )
        --*(_DWORD *)(*(_QWORD *)(v7 + 16) + 80LL);
      MDC::ReallocMem((MDC *)v7, *(_DWORD *)(v7 + 28));
    }
    v23 = *(_DWORD *)(v7 + 32);
    if ( (v23 & 8) != 0 )
    {
      v25 = *(unsigned int **)(v7 + 16);
      if ( (v23 & 0x80u) != 0 )
        v25 = (unsigned int *)EMFContainer::ObtainPtr((EMFContainer *)(v25 + 20), v25[15], *(_DWORD *)(v7 + 28));
      if ( !v25 )
        goto LABEL_32;
      v27 = GetDWordCheckSum(*(_DWORD *)(v7 + 28), v25);
      *(_DWORD *)(*(unsigned int *)(v28 + 4) + v28 + 24) = -v27;
      v23 = *(_DWORD *)(v7 + 32);
      if ( (v23 & 0x80u) != 0 )
      {
        --*(_DWORD *)(*(_QWORD *)(v7 + 16) + 80LL);
        v23 = *(_DWORD *)(v7 + 32);
      }
    }
    if ( (v23 & 1) != 0 )
    {
      EnhMetaFileW = GetEnhMetaFileW((LPCWSTR)(v7 + 216));
      if ( EnhMetaFileW )
        goto LABEL_33;
      goto LABEL_32;
    }
    if ( (v23 & 0x80u) != 0 )
    {
      EnhMetaFileW = (HENHMETAFILE)MDC::CompleteEMFData((MDC *)v7, 1);
    }
    else
    {
      v24 = *(unsigned int **)(v7 + 16);
      if ( !v24 )
        goto LABEL_32;
      EnhMetaFileW = (HENHMETAFILE)SetEnhMetaFileBitsAlt(v24);
      if ( *(char *)(v7 + 32) < 0 )
        --*(_DWORD *)(*(_QWORD *)(v7 + 16) + 80LL);
    }
    if ( EnhMetaFileW )
    {
      *(_QWORD *)(v7 + 16) = 0;
LABEL_33:
      vFreeMDC((struct MDC *)v7);
      InternalDeleteDC(hdc);
      GdiTrackHDelete(hdc);
      return (HENHMETAFILE)GdiTrackHCreate(EnhMetaFileW);
    }
LABEL_32:
    *(_DWORD *)(v7 + 32) |= 2u;
    goto LABEL_33;
  }
  return 0;
}

```

## disassembly

```asm
0x180028200  push    rbx
0x180028202  push    rbp
0x180028203  push    rsi
0x180028204  push    rdi
0x180028205  sub     rsp, 38h
0x180028209  mov     rsi, rcx
0x18002820c  call    cs:__imp_pldcGet
0x180028212  mov     rbx, rax
0x180028215  test    rax, rax
0x180028218  jz      loc_180028416
0x18002821e  mov     edx, esi
0x180028220  and     edx, 7F0000h
0x180028226  cmp     edx, 660000h
0x18002822c  jz      loc_180028416
0x180028232  cmp     dword ptr [rax+0Ch], 2
0x180028236  jnz     loc_180028421
0x18002823c  mov     rcx, [rax+130h]; ho
0x180028243  xor     ebp, ebp
0x180028245  test    rcx, rcx
0x180028248  jnz     loc_18002846B
0x18002824e  mov     rcx, [rbx+138h]; ho
0x180028255  test    rcx, rcx
0x180028258  jnz     loc_18002847D
0x18002825e  mov     rbx, [rbx+10h]
0x180028262  cmp     [rbx+84h], ebp
0x180028268  jnz     loc_18002848F
0x18002826e  test    byte ptr [rbx+20h], 2
0x180028272  jnz     loc_1800283D7
0x180028278  mov     edx, 1; nSavedDC
0x18002827d  mov     rcx, rsi; hdc
0x180028280  call    cs:__imp_RestoreDC
0x180028286  mov     edx, [rbx+0A4h]
0x18002828c  mov     rcx, rsi
0x18002828f  mov     r8, [rbx+0A8h]
0x180028296  mov     [rbx+68h], edx
0x180028299  call    MF_EOF
0x18002829e  test    eax, eax
0x1800282a0  jz      loc_1800283D7
0x1800282a6  mov     rcx, rbx; this
0x1800282a9  call    ?vFlushBounds@MDC@@QEAAXXZ; MDC::vFlushBounds(void)
0x1800282ae  lea     rcx, [rbx+3Ch]; this
0x1800282b2  call    ?bEmpty@ERECTL@@QEAAHXZ; ERECTL::bEmpty(void)
0x1800282b7  test    eax, eax
0x1800282b9  jz      short loc_18002830B
0x1800282bb  imul    ecx, [rbx+2Ch], 64h ; 'd'; nNumber
0x1800282bf  mov     r8d, [rbx+6Ch]; nDenominator
0x1800282c3  mov     edx, [rbx+74h]; nNumerator
0x1800282c6  call    cs:__imp_MulDiv
0x1800282cc  imul    ecx, [rbx+34h], 64h ; 'd'; nNumber
0x1800282d0  mov     r8d, [rbx+6Ch]; nDenominator
0x1800282d4  mov     edx, [rbx+74h]; nNumerator
0x1800282d7  mov     [rbx+3Ch], eax
0x1800282da  call    cs:__imp_MulDiv
0x1800282e0  imul    ecx, [rbx+30h], 64h ; 'd'; nNumber
0x1800282e4  mov     r8d, [rbx+70h]; nDenominator
0x1800282e8  mov     edx, [rbx+78h]; nNumerator
0x1800282eb  mov     [rbx+44h], eax
0x1800282ee  call    cs:__imp_MulDiv
0x1800282f4  imul    ecx, [rbx+38h], 64h ; 'd'; nNumber
0x1800282f8  mov     r8d, [rbx+70h]; nDenominator
0x1800282fc  mov     edx, [rbx+78h]; nNumerator
0x1800282ff  mov     [rbx+40h], eax
0x180028302  call    cs:__imp_MulDiv
0x180028308  mov     [rbx+48h], eax
0x18002830b  test    byte ptr [rbx+20h], 1
0x18002830f  jnz     loc_18002849C
0x180028315  test    byte ptr [rbx+20h], 80h
0x180028319  mov     rax, [rbx+10h]
0x18002831d  jnz     loc_180028510
0x180028323  test    rax, rax
0x180028326  jz      loc_1800283D7
0x18002832c  movups  xmm0, xmmword ptr [rbx+24h]
0x180028330  movups  xmmword ptr [rax], xmm0
0x180028333  movups  xmm1, xmmword ptr [rbx+34h]
0x180028337  movups  xmmword ptr [rax+10h], xmm1
0x18002833b  movups  xmm0, xmmword ptr [rbx+44h]
0x18002833f  movups  xmmword ptr [rax+20h], xmm0
0x180028343  movups  xmm1, xmmword ptr [rbx+54h]
0x180028347  movups  xmmword ptr [rax+30h], xmm1
0x18002834b  movups  xmm0, xmmword ptr [rbx+64h]
0x18002834f  movups  xmmword ptr [rax+40h], xmm0
0x180028353  movups  xmm1, xmmword ptr [rbx+74h]
0x180028357  movups  xmmword ptr [rax+50h], xmm1
0x18002835b  movups  xmm0, xmmword ptr [rbx+80h]
0x180028362  movups  xmmword ptr [rax+5Ch], xmm0
0x180028366  test    byte ptr [rbx+20h], 80h
0x18002836a  jz      short loc_180028373
0x18002836c  mov     rax, [rbx+10h]
0x180028370  dec     dword ptr [rax+50h]
0x180028373  mov     edx, [rbx+1Ch]; unsigned int
0x180028376  mov     rcx, rbx; this
0x180028379  call    ?ReallocMem@MDC@@QEAAHK@Z; MDC::ReallocMem(ulong)
0x18002837e  mov     eax, [rbx+20h]
0x180028381  test    al, 8
0x180028383  jnz     short loc_1800283C6
0x180028385  test    al, 1
0x180028387  jnz     loc_180028425
0x18002838d  test    al, al
0x18002838f  js      short loc_180028404
0x180028391  mov     rcx, [rbx+10h]; unsigned int *
0x180028395  test    rcx, rcx
0x180028398  jz      short loc_1800283D7
0x18002839a  xor     r9d, r9d
0x18002839d  xor     r8d, r8d
0x1800283a0  xor     edx, edx
0x1800283a2  call    SetEnhMetaFileBitsAlt
0x1800283a7  test    byte ptr [rbx+20h], 80h
0x1800283ab  mov     rbp, rax
0x1800283ae  jz      short loc_1800283B7
0x1800283b0  mov     rax, [rbx+10h]
0x1800283b4  dec     dword ptr [rax+50h]
0x1800283b7  test    rbp, rbp
0x1800283ba  jz      short loc_1800283D7
0x1800283bc  mov     qword ptr [rbx+10h], 0
0x1800283c4  jmp     short loc_1800283DB
0x1800283c6  mov     r9, [rbx+10h]
0x1800283ca  test    al, al
0x1800283cc  js      loc_180028527
0x1800283d2  test    r9, r9
0x1800283d5  jnz     short loc_18002843B
0x1800283d7  or      dword ptr [rbx+20h], 2
0x1800283db  mov     rcx, rbx; this
0x1800283de  call    ?vFreeMDC@@YAXPEAVMDC@@@Z; vFreeMDC(MDC *)
0x1800283e3  mov     rcx, rsi; HDC
0x1800283e6  call    InternalDeleteDC
0x1800283eb  mov     rcx, rsi; void *
0x1800283ee  call    GdiTrackHDelete
0x1800283f3  mov     rcx, rbp
0x1800283f6  call    GdiTrackHCreate
0x1800283fb  add     rsp, 38h
0x1800283ff  pop     rdi
0x180028400  pop     rsi
0x180028401  pop     rbp
0x180028402  pop     rbx
0x180028403  retn
0x180028404  mov     edx, 1; int
0x180028409  mov     rcx, rbx; this
0x18002840c  call    ?CompleteEMFData@MDC@@QEAAPEAXH@Z; MDC::CompleteEMFData(int)
0x180028411  mov     rbp, rax
0x180028414  jmp     short loc_1800283B7
0x180028416  mov     ecx, 6
0x18002841b  call    cs:__imp_GdiSetLastError
0x180028421  xor     eax, eax
0x180028423  jmp     short loc_1800283FB
0x180028425  lea     rcx, [rbx+0D8h]; lpName
0x18002842c  call    GetEnhMetaFileW
0x180028431  mov     rbp, rax
0x180028434  test    rax, rax
0x180028437  jnz     short loc_1800283DB
0x180028439  jmp     short loc_1800283D7
0x18002843b  mov     ecx, [rbx+1Ch]; unsigned int
0x18002843e  mov     rdx, r9; unsigned int *
0x180028441  call    ?GetDWordCheckSum@@YAKIPEAK@Z; GetDWordCheckSum(uint,ulong *)
0x180028446  mov     ecx, [r9+4]
0x18002844a  neg     eax
0x18002844c  mov     [rcx+r9+18h], eax
0x180028451  mov     eax, [rbx+20h]
0x180028454  test    al, al
0x180028456  jns     loc_180028385
0x18002845c  mov     rax, [rbx+10h]
0x180028460  dec     dword ptr [rax+50h]
0x180028463  mov     eax, [rbx+20h]
0x180028466  jmp     loc_180028385
0x18002846b  call    cs:__imp_DeleteObject
0x180028471  mov     [rbx+130h], rbp
0x180028478  jmp     loc_18002824E
0x18002847d  call    cs:__imp_DeleteObject
0x180028483  mov     [rbx+138h], rbp
0x18002848a  jmp     loc_18002825E
0x18002848f  mov     rcx, rsi
0x180028492  call    GlmfCloseMetaFile
0x180028497  jmp     loc_18002826E
0x18002849c  mov     rcx, rbx; this
0x18002849f  mov     [rsp+58h+NumberOfBytesWritten], ebp
0x1800284a3  call    ?bFlush@MDC@@QEAAHXZ; MDC::bFlush(void)
0x1800284a8  test    eax, eax
0x1800284aa  jz      loc_1800283D7
0x1800284b0  mov     rcx, [rbx+8]; hFile
0x1800284b4  xor     r9d, r9d; dwMoveMethod
0x1800284b7  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800284ba  xor     edx, edx; lDistanceToMove
0x1800284bc  call    cs:__imp_SetFilePointer
0x1800284c2  test    eax, eax
0x1800284c4  jnz     loc_1800283D7
0x1800284ca  mov     rcx, [rbx+8]; hFile
0x1800284ce  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800284d3  lea     r8d, [rax+6Ch]; nNumberOfBytesToWrite
0x1800284d7  mov     [rsp+58h+lpOverlapped], rbp; lpOverlapped
0x1800284dc  lea     rdx, [rbx+24h]; lpBuffer
0x1800284e0  call    cs:__imp_WriteFile
0x1800284e6  test    eax, eax
0x1800284e8  jz      loc_1800283D7
0x1800284ee  cmp     [rsp+58h+NumberOfBytesWritten], 6Ch ; 'l'
0x1800284f3  jnz     loc_1800283D7
0x1800284f9  mov     rcx, [rbx+8]; hObject
0x1800284fd  call    cs:__imp_CloseHandle
0x180028503  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x18002850b  jmp     loc_18002837E
0x180028510  mov     edx, [rax+3Ch]; unsigned int
0x180028513  lea     rcx, [rax+50h]; this
0x180028517  mov     r8d, 6Ch ; 'l'; unsigned int
0x18002851d  call    ?ObtainPtr@EMFContainer@@QEAAPEAXII@Z; EMFContainer::ObtainPtr(uint,uint)
0x180028522  jmp     loc_180028323
0x180028527  mov     r8d, [rbx+1Ch]; unsigned int
0x18002852b  lea     rcx, [r9+50h]; this
0x18002852f  mov     edx, [r9+3Ch]; unsigned int
0x180028533  call    ?ObtainPtr@EMFContainer@@QEAAPEAXII@Z; EMFContainer::ObtainPtr(uint,uint)
0x180028538  mov     r9, rax
0x18002853b  jmp     loc_1800283D2
```
