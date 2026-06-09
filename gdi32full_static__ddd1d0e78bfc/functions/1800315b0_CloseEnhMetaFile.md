# CloseEnhMetaFile

- ea: `0x1800315b0`
- end: `0x180031939`
- name: `CloseEnhMetaFile`
- size: `905`
- prototype: `HENHMETAFILE __stdcall(HDC hdc)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180035440`

## callees

- `0x18002c5a0`
- `0x18002c7b8`
- `0x18002ca14`
- `0x18002cfe8`
- `0x18002fda0`
- `0x1800315b0`
- `0x180031940`
- `0x180031ca0`
- `0x180031e74`
- `0x180031f30`
- `0x180031fa4`
- `0x18003261c`
- `0x1800524d0`
- `0x180052630`
- `0x180085b80`
- `0x1800939d0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800318cd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800318cd`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800318a3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800318a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800318f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800318f0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180031682`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18003169c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800316b6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800316d0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180031682`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18003169c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800316b6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800316d0`
- `GDI32!RestoreDC` at `0x180031636`
- `GDI32!RestoreDC` at `0x180031636`
- `GDI32!pldcGet` at `0x1800315bc`
- `GDI32!pldcGet` at `0x1800315bc`
- `GDI32!GdiSetLastError` at `0x1800317f0`
- `GDI32!GdiSetLastError` at `0x1800317f0`
- `GDI32!DeleteObject` at `0x180031846`
- `GDI32!DeleteObject` at `0x18003185e`
- `GDI32!DeleteObject` at `0x180031846`
- `GDI32!DeleteObject` at `0x18003185e`

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
0x1800315b0  push    rbx
0x1800315b2  push    rbp
0x1800315b3  push    rsi
0x1800315b4  push    rdi
0x1800315b5  sub     rsp, 38h
0x1800315b9  mov     rsi, rcx
0x1800315bc  call    cs:__imp_pldcGet
0x1800315c3  nop     dword ptr [rax+rax+00h]
0x1800315c8  mov     rbx, rax
0x1800315cb  test    rax, rax
0x1800315ce  jz      loc_1800317EB
0x1800315d4  mov     edx, esi
0x1800315d6  and     edx, 7F0000h
0x1800315dc  cmp     edx, 660000h
0x1800315e2  jz      loc_1800317EB
0x1800315e8  cmp     dword ptr [rax+0Ch], 2
0x1800315ec  jnz     loc_1800317FC
0x1800315f2  mov     rcx, [rax+130h]; ho
0x1800315f9  xor     ebp, ebp
0x1800315fb  test    rcx, rcx
0x1800315fe  jnz     loc_180031846
0x180031604  mov     rcx, [rbx+138h]; ho
0x18003160b  test    rcx, rcx
0x18003160e  jnz     loc_18003185E
0x180031614  mov     rbx, [rbx+10h]
0x180031618  cmp     [rbx+84h], ebp
0x18003161e  jnz     loc_180031876
0x180031624  test    byte ptr [rbx+20h], 2
0x180031628  jnz     loc_1800317AB
0x18003162e  mov     edx, 1; nSavedDC
0x180031633  mov     rcx, rsi; hdc
0x180031636  call    cs:__imp_RestoreDC
0x18003163d  nop     dword ptr [rax+rax+00h]
0x180031642  mov     edx, [rbx+0A4h]
0x180031648  mov     rcx, rsi
0x18003164b  mov     r8, [rbx+0A8h]
0x180031652  mov     [rbx+68h], edx
0x180031655  call    MF_EOF
0x18003165a  test    eax, eax
0x18003165c  jz      loc_1800317AB
0x180031662  mov     rcx, rbx; this
0x180031665  call    ?vFlushBounds@MDC@@QEAAXXZ; MDC::vFlushBounds(void)
0x18003166a  lea     rcx, [rbx+3Ch]; this
0x18003166e  call    ?bEmpty@ERECTL@@QEAAHXZ; ERECTL::bEmpty(void)
0x180031673  test    eax, eax
0x180031675  jz      short loc_1800316DF
0x180031677  imul    ecx, [rbx+2Ch], 64h ; 'd'; nNumber
0x18003167b  mov     r8d, [rbx+6Ch]; nDenominator
0x18003167f  mov     edx, [rbx+74h]; nNumerator
0x180031682  call    cs:__imp_MulDiv
0x180031689  nop     dword ptr [rax+rax+00h]
0x18003168e  imul    ecx, [rbx+34h], 64h ; 'd'; nNumber
0x180031692  mov     r8d, [rbx+6Ch]; nDenominator
0x180031696  mov     edx, [rbx+74h]; nNumerator
0x180031699  mov     [rbx+3Ch], eax
0x18003169c  call    cs:__imp_MulDiv
0x1800316a3  nop     dword ptr [rax+rax+00h]
0x1800316a8  imul    ecx, [rbx+30h], 64h ; 'd'; nNumber
0x1800316ac  mov     r8d, [rbx+70h]; nDenominator
0x1800316b0  mov     edx, [rbx+78h]; nNumerator
0x1800316b3  mov     [rbx+44h], eax
0x1800316b6  call    cs:__imp_MulDiv
0x1800316bd  nop     dword ptr [rax+rax+00h]
0x1800316c2  imul    ecx, [rbx+38h], 64h ; 'd'; nNumber
0x1800316c6  mov     r8d, [rbx+70h]; nDenominator
0x1800316ca  mov     edx, [rbx+78h]; nNumerator
0x1800316cd  mov     [rbx+40h], eax
0x1800316d0  call    cs:__imp_MulDiv
0x1800316d7  nop     dword ptr [rax+rax+00h]
0x1800316dc  mov     [rbx+48h], eax
0x1800316df  test    byte ptr [rbx+20h], 1
0x1800316e3  jnz     loc_180031883
0x1800316e9  test    byte ptr [rbx+20h], 80h
0x1800316ed  mov     rax, [rbx+10h]
0x1800316f1  jnz     loc_180031909
0x1800316f7  test    rax, rax
0x1800316fa  jz      loc_1800317AB
0x180031700  movups  xmm0, xmmword ptr [rbx+24h]
0x180031704  movups  xmmword ptr [rax], xmm0
0x180031707  movups  xmm1, xmmword ptr [rbx+34h]
0x18003170b  movups  xmmword ptr [rax+10h], xmm1
0x18003170f  movups  xmm0, xmmword ptr [rbx+44h]
0x180031713  movups  xmmword ptr [rax+20h], xmm0
0x180031717  movups  xmm1, xmmword ptr [rbx+54h]
0x18003171b  movups  xmmword ptr [rax+30h], xmm1
0x18003171f  movups  xmm0, xmmword ptr [rbx+64h]
0x180031723  movups  xmmword ptr [rax+40h], xmm0
0x180031727  movups  xmm1, xmmword ptr [rbx+74h]
0x18003172b  movups  xmmword ptr [rax+50h], xmm1
0x18003172f  movups  xmm0, xmmword ptr [rbx+80h]
0x180031736  movups  xmmword ptr [rax+5Ch], xmm0
0x18003173a  test    byte ptr [rbx+20h], 80h
0x18003173e  jz      short loc_180031747
0x180031740  mov     rax, [rbx+10h]
0x180031744  dec     dword ptr [rax+50h]
0x180031747  mov     edx, [rbx+1Ch]; unsigned int
0x18003174a  mov     rcx, rbx; this
0x18003174d  call    ?ReallocMem@MDC@@QEAAHK@Z; MDC::ReallocMem(ulong)
0x180031752  mov     eax, [rbx+20h]
0x180031755  test    al, 8
0x180031757  jnz     short loc_18003179A
0x180031759  test    al, 1
0x18003175b  jnz     loc_180031800
0x180031761  test    al, al
0x180031763  js      short loc_1800317D9
0x180031765  mov     rcx, [rbx+10h]; unsigned int *
0x180031769  test    rcx, rcx
0x18003176c  jz      short loc_1800317AB
0x18003176e  xor     r9d, r9d
0x180031771  xor     r8d, r8d
0x180031774  xor     edx, edx
0x180031776  call    SetEnhMetaFileBitsAlt
0x18003177b  test    byte ptr [rbx+20h], 80h
0x18003177f  mov     rbp, rax
0x180031782  jz      short loc_18003178B
0x180031784  mov     rax, [rbx+10h]
0x180031788  dec     dword ptr [rax+50h]
0x18003178b  test    rbp, rbp
0x18003178e  jz      short loc_1800317AB
0x180031790  mov     qword ptr [rbx+10h], 0
0x180031798  jmp     short loc_1800317AF
0x18003179a  mov     r9, [rbx+10h]
0x18003179e  test    al, al
0x1800317a0  js      loc_180031920
0x1800317a6  test    r9, r9
0x1800317a9  jnz     short loc_180031816
0x1800317ab  or      dword ptr [rbx+20h], 2
0x1800317af  mov     rcx, rbx; this
0x1800317b2  call    ?vFreeMDC@@YAXPEAVMDC@@@Z; vFreeMDC(MDC *)
0x1800317b7  mov     rcx, rsi; HDC
0x1800317ba  call    InternalDeleteDC
0x1800317bf  mov     rcx, rsi; void *
0x1800317c2  call    GdiTrackHDelete
0x1800317c7  mov     rcx, rbp
0x1800317ca  call    GdiTrackHCreate
0x1800317cf  add     rsp, 38h
0x1800317d3  pop     rdi
0x1800317d4  pop     rsi
0x1800317d5  pop     rbp
0x1800317d6  pop     rbx
0x1800317d7  retn
0x1800317d9  mov     edx, 1; int
0x1800317de  mov     rcx, rbx; this
0x1800317e1  call    ?CompleteEMFData@MDC@@QEAAPEAXH@Z; MDC::CompleteEMFData(int)
0x1800317e6  mov     rbp, rax
0x1800317e9  jmp     short loc_18003178B
0x1800317eb  mov     ecx, 6
0x1800317f0  call    cs:__imp_GdiSetLastError
0x1800317f7  nop     dword ptr [rax+rax+00h]
0x1800317fc  xor     eax, eax
0x1800317fe  jmp     short loc_1800317CF
0x180031800  lea     rcx, [rbx+0D8h]; lpName
0x180031807  call    GetEnhMetaFileW
0x18003180c  mov     rbp, rax
0x18003180f  test    rax, rax
0x180031812  jnz     short loc_1800317AF
0x180031814  jmp     short loc_1800317AB
0x180031816  mov     ecx, [rbx+1Ch]; unsigned int
0x180031819  mov     rdx, r9; unsigned int *
0x18003181c  call    ?GetDWordCheckSum@@YAKIPEAK@Z; GetDWordCheckSum(uint,ulong *)
0x180031821  mov     ecx, [r9+4]
0x180031825  neg     eax
0x180031827  mov     [rcx+r9+18h], eax
0x18003182c  mov     eax, [rbx+20h]
0x18003182f  test    al, al
0x180031831  jns     loc_180031759
0x180031837  mov     rax, [rbx+10h]
0x18003183b  dec     dword ptr [rax+50h]
0x18003183e  mov     eax, [rbx+20h]
0x180031841  jmp     loc_180031759
0x180031846  call    cs:__imp_DeleteObject
0x18003184d  nop     dword ptr [rax+rax+00h]
0x180031852  mov     [rbx+130h], rbp
0x180031859  jmp     loc_180031604
0x18003185e  call    cs:__imp_DeleteObject
0x180031865  nop     dword ptr [rax+rax+00h]
0x18003186a  mov     [rbx+138h], rbp
0x180031871  jmp     loc_180031614
0x180031876  mov     rcx, rsi
0x180031879  call    GlmfCloseMetaFile
0x18003187e  jmp     loc_180031624
0x180031883  mov     rcx, rbx; this
0x180031886  mov     [rsp+58h+NumberOfBytesWritten], ebp
0x18003188a  call    ?bFlush@MDC@@QEAAHXZ; MDC::bFlush(void)
0x18003188f  test    eax, eax
0x180031891  jz      loc_1800317AB
0x180031897  mov     rcx, [rbx+8]; hFile
0x18003189b  xor     r9d, r9d; dwMoveMethod
0x18003189e  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800318a1  xor     edx, edx; lDistanceToMove
0x1800318a3  call    cs:__imp_SetFilePointer
0x1800318aa  nop     dword ptr [rax+rax+00h]
0x1800318af  test    eax, eax
0x1800318b1  jnz     loc_1800317AB
0x1800318b7  mov     rcx, [rbx+8]; hFile
0x1800318bb  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800318c0  lea     r8d, [rax+6Ch]; nNumberOfBytesToWrite
0x1800318c4  mov     [rsp+58h+lpOverlapped], rbp; lpOverlapped
0x1800318c9  lea     rdx, [rbx+24h]; lpBuffer
0x1800318cd  call    cs:__imp_WriteFile
0x1800318d4  nop     dword ptr [rax+rax+00h]
0x1800318d9  test    eax, eax
0x1800318db  jz      loc_1800317AB
0x1800318e1  cmp     [rsp+58h+NumberOfBytesWritten], 6Ch ; 'l'
0x1800318e6  jnz     loc_1800317AB
0x1800318ec  mov     rcx, [rbx+8]; hObject
0x1800318f0  call    cs:__imp_CloseHandle
0x1800318f7  nop     dword ptr [rax+rax+00h]
0x1800318fc  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x180031904  jmp     loc_180031752
0x180031909  mov     edx, [rax+3Ch]; unsigned int
0x18003190c  lea     rcx, [rax+50h]; this
0x180031910  mov     r8d, 6Ch ; 'l'; unsigned int
0x180031916  call    ?ObtainPtr@EMFContainer@@QEAAPEAXII@Z; EMFContainer::ObtainPtr(uint,uint)
0x18003191b  jmp     loc_1800316F7
0x180031920  mov     r8d, [rbx+1Ch]; unsigned int
0x180031924  lea     rcx, [r9+50h]; this
0x180031928  mov     edx, [r9+3Ch]; unsigned int
0x18003192c  call    ?ObtainPtr@EMFContainer@@QEAAPEAXII@Z; EMFContainer::ObtainPtr(uint,uint)
0x180031931  mov     r9, rax
0x180031934  jmp     loc_1800317A6
```
