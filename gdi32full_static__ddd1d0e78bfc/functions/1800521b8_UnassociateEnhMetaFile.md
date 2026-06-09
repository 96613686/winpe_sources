# UnassociateEnhMetaFile

- ea: `0x1800521b8`
- end: `0x1800524c8`
- name: `UnassociateEnhMetaFile`
- size: `784`
- prototype: `__int64 __fastcall(HDC hdc, int)`
- caller_count: `5`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180051fb8`
- `0x1800748a4`
- `0x180097b10`
- `0x180099e04`
- `0x18009ace0`

## callees

- `0x18002c5a0`
- `0x18002c7b8`
- `0x18002ca14`
- `0x18002cfe8`
- `0x180031e74`
- `0x180031fa4`
- `0x1800521b8`
- `0x1800524d0`
- `0x180052630`
- `0x180085b80`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180052304`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18005231e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180052338`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180052352`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180052304`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18005231e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180052338`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180052352`
- `GDI32!SetICMMode` at `0x180052280`
- `GDI32!SetICMMode` at `0x180052297`
- `GDI32!SetICMMode` at `0x180052481`
- `GDI32!SetICMMode` at `0x180052280`
- `GDI32!SetICMMode` at `0x180052297`
- `GDI32!SetICMMode` at `0x180052481`
- `GDI32!pldcGet` at `0x1800521cd`
- `GDI32!pldcGet` at `0x1800521cd`
- `GDI32!GdiSetLastError` at `0x1800524aa`
- `GDI32!GdiSetLastError` at `0x1800524aa`
- `GDI32!DeleteObject` at `0x180052212`
- `GDI32!DeleteObject` at `0x180052235`
- `GDI32!DeleteObject` at `0x180052212`
- `GDI32!DeleteObject` at `0x180052235`
- `win32u!NtGdiMakeInfoDC` at `0x1800522ae`
- `win32u!NtGdiMakeInfoDC` at `0x180052497`
- `win32u!NtGdiMakeInfoDC` at `0x1800522ae`
- `win32u!NtGdiMakeInfoDC` at `0x180052497`

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
0x1800521b8  push    rbx
0x1800521ba  push    rbp
0x1800521bb  push    rsi
0x1800521bc  push    rdi
0x1800521bd  push    r12
0x1800521bf  push    r14
0x1800521c1  push    r15
0x1800521c3  sub     rsp, 20h
0x1800521c7  mov     r12d, edx
0x1800521ca  mov     rsi, rcx
0x1800521cd  call    cs:__imp_pldcGet
0x1800521d4  nop     dword ptr [rax+rax+00h]
0x1800521d9  mov     rdi, rax
0x1800521dc  test    rax, rax
0x1800521df  jz      loc_1800524A5
0x1800521e5  mov     r8d, esi
0x1800521e8  and     r8d, 7F0000h
0x1800521ef  cmp     r8d, 660000h
0x1800521f6  jz      loc_1800524A5
0x1800521fc  cmp     dword ptr [rax+0Ch], 2
0x180052200  jnz     loc_1800524B6
0x180052206  mov     rcx, [rax+130h]; ho
0x18005220d  test    rcx, rcx
0x180052210  jz      short loc_180052229
0x180052212  call    cs:__imp_DeleteObject
0x180052219  nop     dword ptr [rax+rax+00h]
0x18005221e  mov     qword ptr [rdi+130h], 0
0x180052229  mov     rcx, [rdi+138h]; ho
0x180052230  test    rcx, rcx
0x180052233  jz      short loc_18005224C
0x180052235  call    cs:__imp_DeleteObject
0x18005223c  nop     dword ptr [rax+rax+00h]
0x180052241  mov     qword ptr [rdi+138h], 0
0x18005224c  mov     rbx, [rdi+10h]
0x180052250  test    rbx, rbx
0x180052253  jz      loc_180052492
0x180052259  test    byte ptr [rbx+20h], 80h
0x18005225d  jz      loc_180052492
0x180052263  xor     ebp, ebp
0x180052265  xor     r15d, r15d
0x180052268  cmp     [rbx+84h], ebp
0x18005226e  jz      short loc_180052278
0x180052270  mov     rcx, rsi
0x180052273  call    GlmfCloseMetaFile
0x180052278  mov     edx, 3; mode
0x18005227d  mov     rcx, rsi; hdc
0x180052280  call    cs:__imp_SetICMMode
0x180052287  nop     dword ptr [rax+rax+00h]
0x18005228c  cmp     eax, 2
0x18005228f  jnz     short loc_1800522A9
0x180052291  lea     edx, [rax-1]; mode
0x180052294  mov     rcx, rsi; hdc
0x180052297  call    cs:__imp_SetICMMode
0x18005229e  nop     dword ptr [rax+rax+00h]
0x1800522a3  mov     r15d, 1
0x1800522a9  xor     edx, edx
0x1800522ab  mov     rcx, rsi
0x1800522ae  call    cs:__imp_NtGdiMakeInfoDC
0x1800522b5  nop     dword ptr [rax+rax+00h]
0x1800522ba  test    byte ptr [rbx+20h], 2
0x1800522be  jnz     loc_180052454
0x1800522c4  mov     edx, [rbx+0A4h]
0x1800522ca  mov     rcx, rsi
0x1800522cd  mov     r8, [rbx+0A8h]
0x1800522d4  mov     [rbx+68h], edx
0x1800522d7  call    MF_EOF
0x1800522dc  test    eax, eax
0x1800522de  jz      loc_180052454
0x1800522e4  mov     rcx, rbx; this
0x1800522e7  call    ?vFlushBounds@MDC@@QEAAXXZ; MDC::vFlushBounds(void)
0x1800522ec  lea     rcx, [rbx+3Ch]; this
0x1800522f0  call    ?bEmpty@ERECTL@@QEAAHXZ; ERECTL::bEmpty(void)
0x1800522f5  test    eax, eax
0x1800522f7  jz      short loc_180052361
0x1800522f9  imul    ecx, [rbx+2Ch], 64h ; 'd'; nNumber
0x1800522fd  mov     r8d, [rbx+6Ch]; nDenominator
0x180052301  mov     edx, [rbx+74h]; nNumerator
0x180052304  call    cs:__imp_MulDiv
0x18005230b  nop     dword ptr [rax+rax+00h]
0x180052310  imul    ecx, [rbx+34h], 64h ; 'd'; nNumber
0x180052314  mov     r8d, [rbx+6Ch]; nDenominator
0x180052318  mov     edx, [rbx+74h]; nNumerator
0x18005231b  mov     [rbx+3Ch], eax
0x18005231e  call    cs:__imp_MulDiv
0x180052325  nop     dword ptr [rax+rax+00h]
0x18005232a  imul    ecx, [rbx+30h], 64h ; 'd'; nNumber
0x18005232e  mov     r8d, [rbx+70h]; nDenominator
0x180052332  mov     edx, [rbx+78h]; nNumerator
0x180052335  mov     [rbx+44h], eax
0x180052338  call    cs:__imp_MulDiv
0x18005233f  nop     dword ptr [rax+rax+00h]
0x180052344  imul    ecx, [rbx+38h], 64h ; 'd'; nNumber
0x180052348  mov     r8d, [rbx+70h]; nDenominator
0x18005234c  mov     edx, [rbx+78h]; nNumerator
0x18005234f  mov     [rbx+40h], eax
0x180052352  call    cs:__imp_MulDiv
0x180052359  nop     dword ptr [rax+rax+00h]
0x18005235e  mov     [rbx+48h], eax
0x180052361  mov     rax, [rbx+10h]
0x180052365  mov     r14b, 80h
0x180052368  test    [rbx+20h], r14b
0x18005236c  jz      short loc_180052380
0x18005236e  mov     edx, [rax+3Ch]; unsigned int
0x180052371  lea     rcx, [rax+50h]; this
0x180052375  mov     r8d, 6Ch ; 'l'; unsigned int
0x18005237b  call    ?ObtainPtr@EMFContainer@@QEAAPEAXII@Z; EMFContainer::ObtainPtr(uint,uint)
0x180052380  test    rax, rax
0x180052383  jz      loc_180052454
0x180052389  movups  xmm0, xmmword ptr [rbx+24h]
0x18005238d  movups  xmmword ptr [rax], xmm0
0x180052390  movups  xmm1, xmmword ptr [rbx+34h]
0x180052394  movups  xmmword ptr [rax+10h], xmm1
0x180052398  movups  xmm0, xmmword ptr [rbx+44h]
0x18005239c  movups  xmmword ptr [rax+20h], xmm0
0x1800523a0  movups  xmm1, xmmword ptr [rbx+54h]
0x1800523a4  movups  xmmword ptr [rax+30h], xmm1
0x1800523a8  movups  xmm0, xmmword ptr [rbx+64h]
0x1800523ac  movups  xmmword ptr [rax+40h], xmm0
0x1800523b0  movups  xmm1, xmmword ptr [rbx+74h]
0x1800523b4  movups  xmmword ptr [rax+50h], xmm1
0x1800523b8  movups  xmm0, xmmword ptr [rbx+80h]
0x1800523bf  movups  xmmword ptr [rax+5Ch], xmm0
0x1800523c3  test    [rbx+20h], r14b
0x1800523c7  jz      short loc_1800523D0
0x1800523c9  mov     rax, [rbx+10h]
0x1800523cd  dec     dword ptr [rax+50h]
0x1800523d0  mov     edx, [rbx+1Ch]; unsigned int
0x1800523d3  mov     rcx, rbx; this
0x1800523d6  call    ?ReallocMem@MDC@@QEAAHK@Z; MDC::ReallocMem(ulong)
0x1800523db  test    byte ptr [rbx+20h], 8
0x1800523df  jz      short loc_180052427
0x1800523e1  mov     r9, [rbx+10h]
0x1800523e5  test    [rbx+20h], r14b
0x1800523e9  jz      short loc_1800523FF
0x1800523eb  mov     r8d, [rbx+1Ch]; unsigned int
0x1800523ef  lea     rcx, [r9+50h]; this
0x1800523f3  mov     edx, [r9+3Ch]; unsigned int
0x1800523f7  call    ?ObtainPtr@EMFContainer@@QEAAPEAXII@Z; EMFContainer::ObtainPtr(uint,uint)
0x1800523fc  mov     r9, rax
0x1800523ff  test    r9, r9
0x180052402  jz      short loc_18005244B
0x180052404  mov     ecx, [rbx+1Ch]; unsigned int
0x180052407  mov     rdx, r9; unsigned int *
0x18005240a  call    ?GetDWordCheckSum@@YAKIPEAK@Z; GetDWordCheckSum(uint,ulong *)
0x18005240f  mov     ecx, [r9+4]
0x180052413  neg     eax
0x180052415  mov     [rcx+r9+18h], eax
0x18005241a  test    [rbx+20h], r14b
0x18005241e  jz      short loc_180052427
0x180052420  mov     rax, [rbx+10h]
0x180052424  dec     dword ptr [rax+50h]
0x180052427  mov     edx, r12d; int
0x18005242a  mov     rcx, rbx; this
0x18005242d  call    ?CompleteEMFData@MDC@@QEAAPEAXH@Z; MDC::CompleteEMFData(int)
0x180052432  mov     rbp, rax
0x180052435  test    rax, rax
0x180052438  jz      short loc_180052454
0x18005243a  mov     qword ptr [rbx+10h], 0
0x180052442  mov     dword ptr [rdi+0Ch], 1
0x180052449  jmp     short loc_180052464
0x18005244b  mov     dword ptr [rdi+0Ch], 1
0x180052452  jmp     short loc_180052460
0x180052454  mov     dword ptr [rdi+0Ch], 1
0x18005245b  test    rbp, rbp
0x18005245e  jnz     short loc_180052464
0x180052460  or      dword ptr [rbx+20h], 2
0x180052464  mov     rcx, rbx; this
0x180052467  call    ?vFreeMDC@@YAXPEAVMDC@@@Z; vFreeMDC(MDC *)
0x18005246c  mov     qword ptr [rdi+10h], 0
0x180052474  test    r15d, r15d
0x180052477  jz      short loc_18005248D
0x180052479  mov     edx, 2; mode
0x18005247e  mov     rcx, rsi; hdc
0x180052481  call    cs:__imp_SetICMMode
0x180052488  nop     dword ptr [rax+rax+00h]
0x18005248d  mov     rax, rbp
0x180052490  jmp     short loc_1800524B8
0x180052492  xor     edx, edx
0x180052494  mov     rcx, rsi
0x180052497  call    cs:__imp_NtGdiMakeInfoDC
0x18005249e  nop     dword ptr [rax+rax+00h]
0x1800524a3  jmp     short loc_1800524B6
0x1800524a5  mov     ecx, 6
0x1800524aa  call    cs:__imp_GdiSetLastError
0x1800524b1  nop     dword ptr [rax+rax+00h]
0x1800524b6  xor     eax, eax
0x1800524b8  add     rsp, 20h
0x1800524bc  pop     r15
0x1800524be  pop     r14
0x1800524c0  pop     r12
0x1800524c2  pop     rdi
0x1800524c3  pop     rsi
0x1800524c4  pop     rbp
0x1800524c5  pop     rbx
0x1800524c6  retn
```
