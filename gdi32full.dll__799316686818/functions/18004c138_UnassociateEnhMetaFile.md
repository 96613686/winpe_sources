# UnassociateEnhMetaFile

- ea: `0x18004c138`
- end: `0x18004c3f9`
- name: `UnassociateEnhMetaFile`
- size: `705`
- prototype: `__int64 __fastcall(HDC hdc, int)`
- caller_count: `5`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18004bf80`
- `0x180070308`
- `0x180091f40`
- `0x180094054`
- `0x180094e5c`

## callees

- `0x180023650`
- `0x180023858`
- `0x180023aa4`
- `0x180024010`
- `0x180028a24`
- `0x180028b54`
- `0x18004c138`
- `0x18004c8fc`
- `0x18004ca5c`
- `0x180080c34`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18004c260`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18004c274`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18004c288`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18004c29c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18004c260`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18004c274`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18004c288`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18004c29c`
- `GDI32!SetICMMode` at `0x18004c1ee`
- `GDI32!SetICMMode` at `0x18004c1ff`
- `GDI32!SetICMMode` at `0x18004c3c5`
- `GDI32!SetICMMode` at `0x18004c1ee`
- `GDI32!SetICMMode` at `0x18004c1ff`
- `GDI32!SetICMMode` at `0x18004c3c5`
- `GDI32!pldcGet` at `0x18004c14d`
- `GDI32!pldcGet` at `0x18004c14d`
- `GDI32!GdiSetLastError` at `0x18004c3e2`
- `GDI32!GdiSetLastError` at `0x18004c3e2`
- `GDI32!DeleteObject` at `0x18004c18c`
- `GDI32!DeleteObject` at `0x18004c1a9`
- `GDI32!DeleteObject` at `0x18004c18c`
- `GDI32!DeleteObject` at `0x18004c1a9`
- `win32u!NtGdiMakeInfoDC` at `0x18004c210`
- `win32u!NtGdiMakeInfoDC` at `0x18004c3d5`
- `win32u!NtGdiMakeInfoDC` at `0x18004c210`
- `win32u!NtGdiMakeInfoDC` at `0x18004c3d5`

## pseudocode

```c
void *__fastcall UnassociateEnhMetaFile(HDC hdc, int a2)
{
  __int64 v4; // rax
  __int64 v5; // rdi
  void *v6; // rcx
  void *v7; // rcx
  __int64 v8; // rbx
  void *v9; // rbp
  int v10; // r15d
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // eax
  int v14; // ecx
  int v15; // r8d
  int v16; // edx
  int v17; // eax
  int v18; // ecx
  int v19; // r8d
  int v20; // edx
  int v21; // eax
  int v22; // ecx
  int v23; // r8d
  int v24; // edx
  char *v25; // rax
  unsigned int *v26; // r9
  unsigned int v27; // eax
  __int64 v28; // r9

  v4 = pldcGet(hdc);
  v5 = v4;
  if ( !v4 || ((unsigned int)hdc & 0x7F0000) == 0x660000 )
  {
    GdiSetLastError(6);
    return 0;
  }
  if ( *(_DWORD *)(v4 + 12) != 2 )
    return 0;
  v6 = *(void **)(v4 + 304);
  if ( v6 )
  {
    DeleteObject(v6);
    *(_QWORD *)(v5 + 304) = 0;
  }
  v7 = *(void **)(v5 + 312);
  if ( v7 )
  {
    DeleteObject(v7);
    *(_QWORD *)(v5 + 312) = 0;
  }
  v8 = *(_QWORD *)(v5 + 16);
  if ( !v8 || *(char *)(v8 + 32) >= 0 )
  {
    NtGdiMakeInfoDC(hdc, 0);
    return 0;
  }
  v9 = 0;
  v10 = 0;
  if ( *(_DWORD *)(v8 + 132) )
    GlmfCloseMetaFile(hdc);
  if ( SetICMMode(hdc, 3) == 2 )
  {
    SetICMMode(hdc, 1);
    v10 = 1;
  }
  NtGdiMakeInfoDC(hdc, 0);
  if ( (*(_BYTE *)(v8 + 32) & 2) != 0 )
    goto LABEL_32;
  v11 = *(unsigned int *)(v8 + 164);
  v12 = *(_QWORD *)(v8 + 168);
  *(_DWORD *)(v8 + 104) = v11;
  if ( !(unsigned int)MF_EOF(hdc, v11, v12) )
    goto LABEL_32;
  MDC::vFlushBounds((MDC *)v8);
  if ( (unsigned int)ERECTL::bEmpty((ERECTL *)(v8 + 60)) )
  {
    v13 = MulDiv(100 * *(_DWORD *)(v8 + 44), *(_DWORD *)(v8 + 116), *(_DWORD *)(v8 + 108));
    v14 = 100 * *(_DWORD *)(v8 + 52);
    v15 = *(_DWORD *)(v8 + 108);
    v16 = *(_DWORD *)(v8 + 116);
    *(_DWORD *)(v8 + 60) = v13;
    v17 = MulDiv(v14, v16, v15);
    v18 = 100 * *(_DWORD *)(v8 + 48);
    v19 = *(_DWORD *)(v8 + 112);
    v20 = *(_DWORD *)(v8 + 120);
    *(_DWORD *)(v8 + 68) = v17;
    v21 = MulDiv(v18, v20, v19);
    v22 = 100 * *(_DWORD *)(v8 + 56);
    v23 = *(_DWORD *)(v8 + 112);
    v24 = *(_DWORD *)(v8 + 120);
    *(_DWORD *)(v8 + 64) = v21;
    *(_DWORD *)(v8 + 72) = MulDiv(v22, v24, v23);
  }
  v25 = *(char **)(v8 + 16);
  if ( *(char *)(v8 + 32) < 0 )
    v25 = (char *)EMFContainer::ObtainPtr((EMFContainer *)(v25 + 80), *((_DWORD *)v25 + 15), 0x6Cu);
  if ( !v25 )
    goto LABEL_32;
  *(_OWORD *)v25 = *(_OWORD *)(v8 + 36);
  *((_OWORD *)v25 + 1) = *(_OWORD *)(v8 + 52);
  *((_OWORD *)v25 + 2) = *(_OWORD *)(v8 + 68);
  *((_OWORD *)v25 + 3) = *(_OWORD *)(v8 + 84);
  *((_OWORD *)v25 + 4) = *(_OWORD *)(v8 + 100);
  *((_OWORD *)v25 + 5) = *(_OWORD *)(v8 + 116);
  *(_OWORD *)(v25 + 92) = *(_OWORD *)(v8 + 128);
  if ( (*(_BYTE *)(v8 + 32) & 0x80) != 0 )
    --*(_DWORD *)(*(_QWORD *)(v8 + 16) + 80LL);
  MDC::ReallocMem((MDC *)v8, *(_DWORD *)(v8 + 28));
  if ( (*(_BYTE *)(v8 + 32) & 8) != 0 )
  {
    v26 = *(unsigned int **)(v8 + 16);
    if ( (*(_BYTE *)(v8 + 32) & 0x80) != 0 )
      v26 = (unsigned int *)EMFContainer::ObtainPtr((EMFContainer *)(v26 + 20), v26[15], *(_DWORD *)(v8 + 28));
    if ( !v26 )
    {
      *(_DWORD *)(v5 + 12) = 1;
LABEL_33:
      *(_DWORD *)(v8 + 32) |= 2u;
      goto LABEL_34;
    }
    v27 = GetDWordCheckSum(*(_DWORD *)(v8 + 28), v26);
    *(_DWORD *)(*(unsigned int *)(v28 + 4) + v28 + 24) = -v27;
    if ( (*(_BYTE *)(v8 + 32) & 0x80) != 0 )
      --*(_DWORD *)(*(_QWORD *)(v8 + 16) + 80LL);
  }
  v9 = MDC::CompleteEMFData((MDC *)v8, a2);
  if ( !v9 )
  {
LABEL_32:
    *(_DWORD *)(v5 + 12) = 1;
    goto LABEL_33;
  }
  *(_QWORD *)(v8 + 16) = 0;
  *(_DWORD *)(v5 + 12) = 1;
LABEL_34:
  vFreeMDC((struct MDC *)v8);
  *(_QWORD *)(v5 + 16) = 0;
  if ( v10 )
    SetICMMode(hdc, 2);
  return v9;
}

```

## disassembly

```asm
0x18004c138  push    rbx
0x18004c13a  push    rbp
0x18004c13b  push    rsi
0x18004c13c  push    rdi
0x18004c13d  push    r12
0x18004c13f  push    r14
0x18004c141  push    r15
0x18004c143  sub     rsp, 20h
0x18004c147  mov     r12d, edx
0x18004c14a  mov     rsi, rcx
0x18004c14d  call    cs:__imp_pldcGet
0x18004c153  mov     rdi, rax
0x18004c156  test    rax, rax
0x18004c159  jz      loc_18004C3DD
0x18004c15f  mov     r8d, esi
0x18004c162  and     r8d, 7F0000h
0x18004c169  cmp     r8d, 660000h
0x18004c170  jz      loc_18004C3DD
0x18004c176  cmp     dword ptr [rax+0Ch], 2
0x18004c17a  jnz     loc_18004C3E8
0x18004c180  mov     rcx, [rax+130h]; ho
0x18004c187  test    rcx, rcx
0x18004c18a  jz      short loc_18004C19D
0x18004c18c  call    cs:__imp_DeleteObject
0x18004c192  mov     qword ptr [rdi+130h], 0
0x18004c19d  mov     rcx, [rdi+138h]; ho
0x18004c1a4  test    rcx, rcx
0x18004c1a7  jz      short loc_18004C1BA
0x18004c1a9  call    cs:__imp_DeleteObject
0x18004c1af  mov     qword ptr [rdi+138h], 0
0x18004c1ba  mov     rbx, [rdi+10h]
0x18004c1be  test    rbx, rbx
0x18004c1c1  jz      loc_18004C3D0
0x18004c1c7  test    byte ptr [rbx+20h], 80h
0x18004c1cb  jz      loc_18004C3D0
0x18004c1d1  xor     ebp, ebp
0x18004c1d3  xor     r15d, r15d
0x18004c1d6  cmp     [rbx+84h], ebp
0x18004c1dc  jz      short loc_18004C1E6
0x18004c1de  mov     rcx, rsi
0x18004c1e1  call    GlmfCloseMetaFile
0x18004c1e6  mov     edx, 3; mode
0x18004c1eb  mov     rcx, rsi; hdc
0x18004c1ee  call    cs:__imp_SetICMMode
0x18004c1f4  cmp     eax, 2
0x18004c1f7  jnz     short loc_18004C20B
0x18004c1f9  lea     edx, [rax-1]; mode
0x18004c1fc  mov     rcx, rsi; hdc
0x18004c1ff  call    cs:__imp_SetICMMode
0x18004c205  mov     r15d, 1
0x18004c20b  xor     edx, edx
0x18004c20d  mov     rcx, rsi
0x18004c210  call    cs:__imp_NtGdiMakeInfoDC
0x18004c216  test    byte ptr [rbx+20h], 2
0x18004c21a  jnz     loc_18004C398
0x18004c220  mov     edx, [rbx+0A4h]
0x18004c226  mov     rcx, rsi
0x18004c229  mov     r8, [rbx+0A8h]
0x18004c230  mov     [rbx+68h], edx
0x18004c233  call    MF_EOF
0x18004c238  test    eax, eax
0x18004c23a  jz      loc_18004C398
0x18004c240  mov     rcx, rbx; this
0x18004c243  call    ?vFlushBounds@MDC@@QEAAXXZ; MDC::vFlushBounds(void)
0x18004c248  lea     rcx, [rbx+3Ch]; this
0x18004c24c  call    ?bEmpty@ERECTL@@QEAAHXZ; ERECTL::bEmpty(void)
0x18004c251  test    eax, eax
0x18004c253  jz      short loc_18004C2A5
0x18004c255  imul    ecx, [rbx+2Ch], 64h ; 'd'; nNumber
0x18004c259  mov     r8d, [rbx+6Ch]; nDenominator
0x18004c25d  mov     edx, [rbx+74h]; nNumerator
0x18004c260  call    cs:__imp_MulDiv
0x18004c266  imul    ecx, [rbx+34h], 64h ; 'd'; nNumber
0x18004c26a  mov     r8d, [rbx+6Ch]; nDenominator
0x18004c26e  mov     edx, [rbx+74h]; nNumerator
0x18004c271  mov     [rbx+3Ch], eax
0x18004c274  call    cs:__imp_MulDiv
0x18004c27a  imul    ecx, [rbx+30h], 64h ; 'd'; nNumber
0x18004c27e  mov     r8d, [rbx+70h]; nDenominator
0x18004c282  mov     edx, [rbx+78h]; nNumerator
0x18004c285  mov     [rbx+44h], eax
0x18004c288  call    cs:__imp_MulDiv
0x18004c28e  imul    ecx, [rbx+38h], 64h ; 'd'; nNumber
0x18004c292  mov     r8d, [rbx+70h]; nDenominator
0x18004c296  mov     edx, [rbx+78h]; nNumerator
0x18004c299  mov     [rbx+40h], eax
0x18004c29c  call    cs:__imp_MulDiv
0x18004c2a2  mov     [rbx+48h], eax
0x18004c2a5  mov     rax, [rbx+10h]
0x18004c2a9  mov     r14b, 80h
0x18004c2ac  test    [rbx+20h], r14b
0x18004c2b0  jz      short loc_18004C2C4
0x18004c2b2  mov     edx, [rax+3Ch]; unsigned int
0x18004c2b5  lea     rcx, [rax+50h]; this
0x18004c2b9  mov     r8d, 6Ch ; 'l'; unsigned int
0x18004c2bf  call    ?ObtainPtr@EMFContainer@@QEAAPEAXII@Z; EMFContainer::ObtainPtr(uint,uint)
0x18004c2c4  test    rax, rax
0x18004c2c7  jz      loc_18004C398
0x18004c2cd  movups  xmm0, xmmword ptr [rbx+24h]
0x18004c2d1  movups  xmmword ptr [rax], xmm0
0x18004c2d4  movups  xmm1, xmmword ptr [rbx+34h]
0x18004c2d8  movups  xmmword ptr [rax+10h], xmm1
0x18004c2dc  movups  xmm0, xmmword ptr [rbx+44h]
0x18004c2e0  movups  xmmword ptr [rax+20h], xmm0
0x18004c2e4  movups  xmm1, xmmword ptr [rbx+54h]
0x18004c2e8  movups  xmmword ptr [rax+30h], xmm1
0x18004c2ec  movups  xmm0, xmmword ptr [rbx+64h]
0x18004c2f0  movups  xmmword ptr [rax+40h], xmm0
0x18004c2f4  movups  xmm1, xmmword ptr [rbx+74h]
0x18004c2f8  movups  xmmword ptr [rax+50h], xmm1
0x18004c2fc  movups  xmm0, xmmword ptr [rbx+80h]
0x18004c303  movups  xmmword ptr [rax+5Ch], xmm0
0x18004c307  test    [rbx+20h], r14b
0x18004c30b  jz      short loc_18004C314
0x18004c30d  mov     rax, [rbx+10h]
0x18004c311  dec     dword ptr [rax+50h]
0x18004c314  mov     edx, [rbx+1Ch]; unsigned int
0x18004c317  mov     rcx, rbx; this
0x18004c31a  call    ?ReallocMem@MDC@@QEAAHK@Z; MDC::ReallocMem(ulong)
0x18004c31f  test    byte ptr [rbx+20h], 8
0x18004c323  jz      short loc_18004C36B
0x18004c325  mov     r9, [rbx+10h]
0x18004c329  test    [rbx+20h], r14b
0x18004c32d  jz      short loc_18004C343
0x18004c32f  mov     r8d, [rbx+1Ch]; unsigned int
0x18004c333  lea     rcx, [r9+50h]; this
0x18004c337  mov     edx, [r9+3Ch]; unsigned int
0x18004c33b  call    ?ObtainPtr@EMFContainer@@QEAAPEAXII@Z; EMFContainer::ObtainPtr(uint,uint)
0x18004c340  mov     r9, rax
0x18004c343  test    r9, r9
0x18004c346  jz      short loc_18004C38F
0x18004c348  mov     ecx, [rbx+1Ch]; unsigned int
0x18004c34b  mov     rdx, r9; unsigned int *
0x18004c34e  call    ?GetDWordCheckSum@@YAKIPEAK@Z; GetDWordCheckSum(uint,ulong *)
0x18004c353  mov     ecx, [r9+4]
0x18004c357  neg     eax
0x18004c359  mov     [rcx+r9+18h], eax
0x18004c35e  test    [rbx+20h], r14b
0x18004c362  jz      short loc_18004C36B
0x18004c364  mov     rax, [rbx+10h]
0x18004c368  dec     dword ptr [rax+50h]
0x18004c36b  mov     edx, r12d; int
0x18004c36e  mov     rcx, rbx; this
0x18004c371  call    ?CompleteEMFData@MDC@@QEAAPEAXH@Z; MDC::CompleteEMFData(int)
0x18004c376  mov     rbp, rax
0x18004c379  test    rax, rax
0x18004c37c  jz      short loc_18004C398
0x18004c37e  mov     qword ptr [rbx+10h], 0
0x18004c386  mov     dword ptr [rdi+0Ch], 1
0x18004c38d  jmp     short loc_18004C3A8
0x18004c38f  mov     dword ptr [rdi+0Ch], 1
0x18004c396  jmp     short loc_18004C3A4
0x18004c398  mov     dword ptr [rdi+0Ch], 1
0x18004c39f  test    rbp, rbp
0x18004c3a2  jnz     short loc_18004C3A8
0x18004c3a4  or      dword ptr [rbx+20h], 2
0x18004c3a8  mov     rcx, rbx; this
0x18004c3ab  call    ?vFreeMDC@@YAXPEAVMDC@@@Z; vFreeMDC(MDC *)
0x18004c3b0  mov     qword ptr [rdi+10h], 0
0x18004c3b8  test    r15d, r15d
0x18004c3bb  jz      short loc_18004C3CB
0x18004c3bd  mov     edx, 2; mode
0x18004c3c2  mov     rcx, rsi; hdc
0x18004c3c5  call    cs:__imp_SetICMMode
0x18004c3cb  mov     rax, rbp
0x18004c3ce  jmp     short loc_18004C3EA
0x18004c3d0  xor     edx, edx
0x18004c3d2  mov     rcx, rsi
0x18004c3d5  call    cs:__imp_NtGdiMakeInfoDC
0x18004c3db  jmp     short loc_18004C3E8
0x18004c3dd  mov     ecx, 6
0x18004c3e2  call    cs:__imp_GdiSetLastError
0x18004c3e8  xor     eax, eax
0x18004c3ea  add     rsp, 20h
0x18004c3ee  pop     r15
0x18004c3f0  pop     r14
0x18004c3f2  pop     r12
0x18004c3f4  pop     rdi
0x18004c3f5  pop     rsi
0x18004c3f6  pop     rbp
0x18004c3f7  pop     rbx
0x18004c3f8  retn
```
