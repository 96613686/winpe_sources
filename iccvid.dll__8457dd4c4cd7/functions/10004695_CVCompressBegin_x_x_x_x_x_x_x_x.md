# CVCompressBegin(x,x,x,x,x,x,x,x)

- ea: `0x10004695`
- end: `0x10004a61`
- name: `_CVCompressBegin@32`
- size: `972`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1000fbcc`

## callees

- `0x1000422a`
- `0x10004695`
- `0x10004a67`
- `0x10004fa4`
- `0x10004fcb`
- `0x10006841`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x100046ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x100047c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1000487f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x10004897`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x100048af`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1000492e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x10004944`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1000495b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x10004971`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1000498b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x100049a4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x100046ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x100047c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1000487f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x10004897`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x100048af`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1000492e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x10004944`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1000495b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x10004971`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1000498b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x100049a4`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntA` at `0x10004a0a`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntA` at `0x10004a2a`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntA` at `0x10004a40`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntA` at `0x10004a0a`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntA` at `0x10004a2a`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileIntA` at `0x10004a40`

## pseudocode

```c
HLOCAL __fastcall CVCompressBegin(__int16 a1, __int16 a2, int a3, int a4, int a5, int a6, int a7, __int16 a8)
{
  HLOCAL result; // eax
  ULONG v11; // esi
  int v12; // eax
  ULONG v13; // eax
  int v14; // edi
  __int16 v15; // cx
  __int16 v16; // cx
  __int16 v17; // ax
  __int16 v18; // bx
  _DWORD *v19; // eax
  _DWORD *v20; // edi
  unsigned __int16 v21; // dx
  bool v22; // cc
  unsigned __int16 v23; // cx
  unsigned __int16 v24; // dx
  signed __int16 v25; // cx
  HLOCAL v26; // eax
  HLOCAL v27; // eax
  HLOCAL v28; // eax
  int v29; // edi
  HLOCAL v30; // eax
  HLOCAL v31; // eax
  HLOCAL v32; // eax
  HLOCAL v33; // eax
  HLOCAL v34; // eax
  HLOCAL v35; // eax
  ULONG v36; // [esp+0h] [ebp-20h]
  ULONG v37; // [esp+0h] [ebp-20h]
  ULONG v38; // [esp+0h] [ebp-20h]
  ULONG *v39; // [esp+4h] [ebp-1Ch]
  ULONG *v40; // [esp+4h] [ebp-1Ch]
  ULONG *v41; // [esp+4h] [ebp-1Ch]
  signed __int16 v42; // [esp+Ch] [ebp-14h]
  __int16 v43; // [esp+10h] [ebp-10h]
  ULONG uBytes; // [esp+14h] [ebp-Ch] BYREF
  ULONG v45; // [esp+18h] [ebp-8h] BYREF
  ULONG ulMultiplicand; // [esp+1Ch] [ebp-4h] BYREF

  result = LocalAlloc(0x40u, 0x41Cu);
  v11 = (ULONG)result;
  v45 = (ULONG)result;
  if ( result )
  {
    v12 = 3;
    do
    {
      --v12;
      *(_DWORD *)(v11 + 4 * v12 + 196) = 0;
    }
    while ( v12 );
    *(_DWORD *)(v11 + 108) = 0;
    *(_DWORD *)(v11 + 112) = 0;
    *(_DWORD *)(v11 + 124) = 0;
    *(_DWORD *)(v11 + 128) = 0;
    *(_DWORD *)(v11 + 148) = 0;
    *(_DWORD *)(v11 + 152) = 0;
    *(_DWORD *)(v11 + 64) = a3;
    v43 = a2;
    *(_DWORD *)(v11 + 72) = a4;
    *(_WORD *)(v11 + 70) = a2;
    v13 = (a2 + 3) & 0xFFFC;
    uBytes = v13;
    *(_WORD *)(v11 + 80) = v13;
    *(_DWORD *)(v11 + 84) = a2 * a1;
    v14 = (__int16)v13;
    v15 = (a1 + 3) & 0xFFFC;
    *(_WORD *)(v11 + 78) = v15;
    *(_WORD *)(v11 + 68) = a1;
    v16 = ((((__int16)v13 * v15) >> 4) + 1200) / 2400;
    v17 = 1;
    if ( v16 >= 1 )
    {
      v17 = v16;
      if ( v16 > 3 )
        v17 = 3;
    }
    v42 = ((v17 + v14 - 1) / v17 + 3) & 0xFFFC;
    *(_WORD *)(v11 + 208) = (v42 + v14 - 1) / v42;
    CVSetStatusProc(v11, a7);
    *(_WORD *)(v11 + 1050) = 16 * *(_WORD *)(v11 + 208);
    CVCompressFramesInfo();
    v18 = 0;
    if ( *(__int16 *)(v11 + 208) > 0 )
    {
      while ( 1 )
      {
        v19 = LocalAlloc(0x40u, 0x24u);
        v20 = v19;
        *(_DWORD *)(v11 + 4 * v18 + 196) = v19;
        if ( !v19 )
          break;
        if ( v18 )
          **(_DWORD **)(v11 + 4 * v18 + 192) = v19;
        v21 = uBytes;
        v22 = v42 < (signed __int16)uBytes;
        v19[4] = 0;
        v19[5] = 0;
        v19[7] = 0;
        v23 = v21;
        if ( v22 )
          v23 = v42;
        *((_WORD *)v19 + 2) = v18;
        v24 = v23;
        uBytes -= v23;
        v11 = v45;
        v25 = v43;
        if ( v42 < v43 )
          v25 = v42;
        *((_WORD *)v19 + 3) = v24;
        v43 -= v25;
        *((_WORD *)v19 + 4) = v25;
        v19[3] = ((__int16)v24 * *(__int16 *)(v11 + 78)) >> 4;
        if ( v18 )
          *((_BYTE *)v19 + 10) = 17;
        if ( ULongMult((ULONG)&ulMultiplicand, v36, v39) < 0 )
          break;
        v26 = LocalAlloc(0x40u, ulMultiplicand);
        v20[4] = v26;
        if ( !v26 )
          break;
        v27 = LocalAlloc(0x40u, 0x800u);
        v20[5] = v27;
        if ( !v27 )
          break;
        v28 = LocalAlloc(0x40u, 0x800u);
        v20[7] = v28;
        if ( !v28 )
          break;
        if ( ++v18 >= *(__int16 *)(v11 + 208) )
          goto LABEL_22;
      }
      return (HLOCAL)UnwindCompressBegin((HLOCAL)v11);
    }
LABEL_22:
    if ( !*(_DWORD *)(v11 + 196) )
      return (HLOCAL)UnwindCompressBegin((HLOCAL)v11);
    if ( ULongMult((ULONG)&ulMultiplicand, v36, v39) < 0 )
      return (HLOCAL)UnwindCompressBegin((HLOCAL)v11);
    if ( ULongMult((ULONG)&uBytes, v37, v40) < 0 )
      return (HLOCAL)UnwindCompressBegin((HLOCAL)v11);
    v29 = 8;
    if ( ULongMult((ULONG)&v45, v38, v41) < 0 )
      return (HLOCAL)UnwindCompressBegin((HLOCAL)v11);
    v30 = LocalAlloc(0x40u, uBytes);
    *(_DWORD *)(v11 + 108) = v30;
    if ( !v30 )
      return (HLOCAL)UnwindCompressBegin((HLOCAL)v11);
    v31 = LocalAlloc(0x40u, uBytes);
    *(_DWORD *)(v11 + 112) = v31;
    if ( !v31 )
      return (HLOCAL)UnwindCompressBegin((HLOCAL)v11);
    v32 = LocalAlloc(0x40u, 0x1CC00u);
    *(_DWORD *)(v11 + 124) = v32;
    if ( !v32 )
      return (HLOCAL)UnwindCompressBegin((HLOCAL)v11);
    v33 = LocalAlloc(0x40u, ulMultiplicand);
    *(_DWORD *)(v11 + 128) = v33;
    if ( !v33 )
      return (HLOCAL)UnwindCompressBegin((HLOCAL)v11);
    v34 = LocalAlloc(0x40u, 0x1CC00u);
    *(_DWORD *)(v11 + 148) = v34;
    if ( !v34 )
      return (HLOCAL)UnwindCompressBegin((HLOCAL)v11);
    v35 = LocalAlloc(0x40u, v45);
    *(_DWORD *)(v11 + 152) = v35;
    if ( !v35 || !DIBToYUVBegin(v11, a5) )
      return (HLOCAL)UnwindCompressBegin((HLOCAL)v11);
    *(_DWORD *)(v11 + 140) = 200;
    *(_DWORD *)(v11 + 164) = 2000;
    *(_DWORD *)(v11 + 92) = -1;
    *(_WORD *)(v11 + 106) = a8;
    do
    {
      --v29;
      *(_WORD *)(v11 + 2 * v29 + 172) = GetPrivateProfileIntA(
                                          szIniSection,
                                          (&off_1001400C)[4 * v29],
                                          dword_10014008[4 * v29],
                                          szIniFile);
    }
    while ( v29 );
    *(_WORD *)(v11 + 188) = GetPrivateProfileIntA(szIniSection, "NeighborsMethod", 1, szIniFile);
    *(_WORD *)(v11 + 190) = GetPrivateProfileIntA(szIniSection, "NeighborsRounds", 14, szIniFile);
    return (HLOCAL)v11;
  }
  return result;
}

```

## disassembly

```asm
0x10004695  mov     edi, edi
0x10004697  push    ebp
0x10004698  mov     ebp, esp
0x1000469a  and     esp, 0FFFFFFF8h
0x1000469d  sub     esp, 14h
0x100046a0  push    ebx
0x100046a1  push    esi; pulResult
0x100046a2  push    edi; ulMultiplier
0x100046a3  push    41Ch; uBytes
0x100046a8  push    40h ; '@'; uFlags
0x100046aa  mov     edi, edx
0x100046ac  mov     ebx, ecx
0x100046ae  call    ds:__imp__LocalAlloc@8; LocalAlloc(x,x)
0x100046b4  mov     esi, eax
0x100046b6  mov     [esp+20h+var_8], esi
0x100046ba  test    esi, esi
0x100046bc  jz      loc_10004A58
0x100046c2  push    3
0x100046c4  pop     eax
0x100046c5  xor     ecx, ecx
0x100046c7  sub     eax, 1
0x100046ca  mov     [esi+eax*4+0C4h], ecx
0x100046d1  jnz     short loc_100046C7
0x100046d3  mov     eax, [ebp+arg_0]
0x100046d6  mov     [esi+6Ch], ecx
0x100046d9  mov     [esi+70h], ecx
0x100046dc  mov     [esi+7Ch], ecx
0x100046df  mov     [esi+80h], ecx
0x100046e5  mov     [esi+94h], ecx
0x100046eb  mov     [esi+98h], ecx
0x100046f1  mov     [esi+40h], eax
0x100046f4  movzx   eax, di
0x100046f7  mov     [esp+20h+var_10], eax
0x100046fb  mov     eax, [ebp+arg_4]
0x100046fe  mov     [esi+48h], eax
0x10004701  movsx   eax, di
0x10004704  movsx   ecx, bx
0x10004707  imul    ecx, eax
0x1000470a  lea     eax, [edi+3]
0x1000470d  and     eax, 0FFFFFFFCh
0x10004710  mov     [esi+46h], di
0x10004714  movzx   eax, ax
0x10004717  mov     [esp+20h+uBytes], eax
0x1000471b  mov     [esi+50h], ax
0x1000471f  mov     [esi+54h], ecx
0x10004722  lea     ecx, [ebx+3]
0x10004725  movsx   edi, ax
0x10004728  and     ecx, 0FFFFFFFCh
0x1000472b  movsx   eax, cx
0x1000472e  imul    eax, edi
0x10004731  mov     [esi+4Eh], cx
0x10004735  mov     ecx, 960h
0x1000473a  push    3
0x1000473c  mov     [esi+44h], bx
0x10004740  pop     ebx
0x10004741  sar     eax, 4
0x10004744  add     eax, 4B0h
0x10004749  cdq
0x1000474a  idiv    ecx
0x1000474c  movzx   ecx, ax
0x1000474f  xor     eax, eax
0x10004751  inc     eax
0x10004752  cmp     cx, ax
0x10004755  jl      short loc_1000475F
0x10004757  cmp     cx, bx
0x1000475a  mov     eax, ecx
0x1000475c  cmovg   eax, ebx
0x1000475f  movsx   ecx, ax
0x10004762  lea     eax, [edi-1]
0x10004765  add     eax, ecx
0x10004767  cdq
0x10004768  idiv    ecx
0x1000476a  add     eax, ebx
0x1000476c  and     eax, 0FFFFFFFCh
0x1000476f  movzx   eax, ax
0x10004772  movsx   ecx, ax
0x10004775  mov     [esp+20h+var_14], eax
0x10004779  lea     eax, [edi-1]
0x1000477c  add     eax, ecx
0x1000477e  cdq
0x1000477f  idiv    ecx
0x10004781  mov     edx, [ebp+arg_10]
0x10004784  mov     ecx, esi
0x10004786  mov     [esi+0D0h], ax
0x1000478d  call    _CVSetStatusProc@8; CVSetStatusProc(x,x)
0x10004792  mov     ax, [esi+0D0h]
0x10004799  mov     edx, [ebp+arg_C]
0x1000479c  shl     ax, 4
0x100047a0  mov     [esi+41Ah], ax
0x100047a7  call    _CVCompressFramesInfo@8; CVCompressFramesInfo(x,x)
0x100047ac  xor     eax, eax
0x100047ae  xor     ebx, ebx
0x100047b0  cmp     ax, [esi+0D0h]
0x100047b7  jge     loc_100048CE
0x100047bd  push    24h ; '$'; uBytes
0x100047bf  push    40h ; '@'; uFlags
0x100047c1  call    ds:__imp__LocalAlloc@8; LocalAlloc(x,x)
0x100047c7  movsx   ecx, bx
0x100047ca  mov     edi, eax
0x100047cc  mov     [esi+ecx*4+0C4h], edi
0x100047d3  test    edi, edi
0x100047d5  jz      loc_10004A51
0x100047db  test    bx, bx
0x100047de  jz      short loc_100047E9
0x100047e0  mov     ecx, [esi+ecx*4+0C0h]
0x100047e7  mov     [ecx], edi
0x100047e9  mov     edx, [esp+20h+uBytes]
0x100047ed  xor     eax, eax
0x100047ef  cmp     word ptr [esp+20h+var_14], dx
0x100047f4  mov     esi, [esp+20h+var_10]
0x100047f8  mov     [edi+10h], eax
0x100047fb  mov     [edi+14h], eax
0x100047fe  mov     [edi+1Ch], eax
0x10004801  mov     eax, [esp+20h+var_14]
0x10004805  movzx   eax, ax
0x10004808  movzx   ecx, dx
0x1000480b  cmovl   ecx, eax
0x1000480e  mov     [edi+4], bx
0x10004812  mov     eax, [esp+20h+var_10]
0x10004816  movzx   edx, cx
0x10004819  sub     [esp+20h+uBytes], edx
0x1000481d  cmp     word ptr [esp+20h+var_14], si
0x10004822  mov     esi, [esp+20h+var_8]
0x10004826  movzx   ecx, ax
0x10004829  mov     eax, [esp+20h+var_14]
0x1000482d  movzx   eax, ax
0x10004830  cmovl   ecx, eax
0x10004833  mov     [edi+6], dx
0x10004837  movzx   eax, cx
0x1000483a  sub     [esp+20h+var_10], eax
0x1000483e  mov     [edi+8], ax
0x10004842  movsx   ecx, word ptr [esi+4Eh]
0x10004846  movsx   eax, dx
0x10004849  imul    ecx, eax
0x1000484c  sar     ecx, 4
0x1000484f  mov     [edi+0Ch], ecx
0x10004852  test    bx, bx
0x10004855  jz      short loc_1000485B
0x10004857  mov     byte ptr [edi+0Ah], 11h
0x1000485b  mov     ecx, [esi+0C4h]
0x10004861  lea     eax, [esp+20h+ulMultiplicand]
0x10004865  push    eax; ulMultiplicand
0x10004866  push    20h ; ' '
0x10004868  pop     edx
0x10004869  mov     ecx, [ecx+0Ch]
0x1000486c  call    _ULongMult@12; ULongMult(x,x,x)
0x10004871  test    eax, eax
0x10004873  js      loc_10004A51
0x10004879  push    [esp+20h+ulMultiplicand]; uBytes
0x1000487d  push    40h ; '@'; uFlags
0x1000487f  call    ds:__imp__LocalAlloc@8; LocalAlloc(x,x)
0x10004885  mov     [edi+10h], eax
0x10004888  test    eax, eax
0x1000488a  jz      loc_10004A51
0x10004890  push    800h; uBytes
0x10004895  push    40h ; '@'; uFlags
0x10004897  call    ds:__imp__LocalAlloc@8; LocalAlloc(x,x)
0x1000489d  mov     [edi+14h], eax
0x100048a0  test    eax, eax
0x100048a2  jz      loc_10004A51
0x100048a8  push    800h; uBytes
0x100048ad  push    40h ; '@'; uFlags
0x100048af  call    ds:__imp__LocalAlloc@8; LocalAlloc(x,x)
0x100048b5  mov     [edi+1Ch], eax
0x100048b8  test    eax, eax
0x100048ba  jz      loc_10004A51
0x100048c0  inc     ebx
0x100048c1  cmp     bx, [esi+0D0h]
0x100048c8  jl      loc_100047BD
0x100048ce  mov     ebx, [esi+0C4h]
0x100048d4  test    ebx, ebx
0x100048d6  jz      loc_10004A51
0x100048dc  mov     ecx, [ebx+0Ch]
0x100048df  lea     eax, [esp+20h+ulMultiplicand]
0x100048e3  push    eax; ulMultiplicand
0x100048e4  push    20h ; ' '
0x100048e6  pop     edx
0x100048e7  call    _ULongMult@12; ULongMult(x,x,x)
0x100048ec  test    eax, eax
0x100048ee  js      loc_10004A51
0x100048f4  mov     ecx, [ebx+0Ch]
0x100048f7  lea     eax, [esp+20h+uBytes]
0x100048fb  push    eax; ulMultiplicand
0x100048fc  push    2
0x100048fe  pop     edx
0x100048ff  call    _ULongMult@12; ULongMult(x,x,x)
0x10004904  test    eax, eax
0x10004906  js      loc_10004A51
0x1000490c  mov     ecx, [ebx+0Ch]
0x1000490f  lea     eax, [esp+20h+var_8]
0x10004913  push    eax; ulMultiplicand
0x10004914  push    8
0x10004916  pop     edi
0x10004917  mov     edx, edi
0x10004919  call    _ULongMult@12; ULongMult(x,x,x)
0x1000491e  test    eax, eax
0x10004920  js      loc_10004A51
0x10004926  push    [esp+20h+uBytes]; uBytes
0x1000492a  push    40h ; '@'
0x1000492c  pop     ebx
0x1000492d  push    ebx; uFlags
0x1000492e  call    ds:__imp__LocalAlloc@8; LocalAlloc(x,x)
0x10004934  mov     [esi+6Ch], eax
0x10004937  test    eax, eax
0x10004939  jz      loc_10004A51
0x1000493f  push    [esp+20h+uBytes]; uBytes
0x10004943  push    ebx; uFlags
0x10004944  call    ds:__imp__LocalAlloc@8; LocalAlloc(x,x)
0x1000494a  mov     [esi+70h], eax
0x1000494d  test    eax, eax
0x1000494f  jz      loc_10004A51
0x10004955  push    1CC00h; uBytes
0x1000495a  push    ebx; uFlags
0x1000495b  call    ds:__imp__LocalAlloc@8; LocalAlloc(x,x)
0x10004961  mov     [esi+7Ch], eax
0x10004964  test    eax, eax
0x10004966  jz      loc_10004A51
0x1000496c  push    [esp+20h+ulMultiplicand]; uBytes
0x10004970  push    ebx; uFlags
0x10004971  call    ds:__imp__LocalAlloc@8; LocalAlloc(x,x)
0x10004977  mov     [esi+80h], eax
0x1000497d  test    eax, eax
0x1000497f  jz      loc_10004A51
0x10004985  push    1CC00h; uBytes
0x1000498a  push    ebx; uFlags
0x1000498b  call    ds:__imp__LocalAlloc@8; LocalAlloc(x,x)
0x10004991  mov     [esi+94h], eax
0x10004997  test    eax, eax
0x10004999  jz      loc_10004A51
0x1000499f  push    [esp+20h+var_8]; uBytes
0x100049a3  push    ebx; uFlags
0x100049a4  call    ds:__imp__LocalAlloc@8; LocalAlloc(x,x)
0x100049aa  mov     [esi+98h], eax
0x100049b0  test    eax, eax
0x100049b2  jz      loc_10004A51
0x100049b8  mov     edx, [ebp+arg_8]
0x100049bb  mov     ecx, esi
0x100049bd  call    _DIBToYUVBegin@8; DIBToYUVBegin(x,x)
0x100049c2  test    eax, eax
0x100049c4  jz      loc_10004A51
0x100049ca  mov     ax, [ebp+arg_14]
0x100049ce  mov     ebx, offset _szIniFile
0x100049d3  mov     dword ptr [esi+8Ch], 0C8h
0x100049dd  mov     dword ptr [esi+0A4h], 7D0h
0x100049e7  mov     dword ptr [esi+5Ch], 0FFFFFFFFh
0x100049ee  mov     [esi+6Ah], ax
0x100049f2  dec     edi
0x100049f3  mov     eax, edi
0x100049f5  shl     eax, 4
0x100049f8  push    ebx; lpFileName
0x100049f9  push    dword_10014008[eax]; nDefault
0x100049ff  push    off_1001400C[eax]; lpKeyName
0x10004a05  push    offset _szIniSection; "ICCVID.drv"
0x10004a0a  call    ds:__imp__GetPrivateProfileIntA@16; GetPrivateProfileIntA(x,x,x,x)
0x10004a10  mov     [esi+edi*2+0ACh], ax
0x10004a18  test    edi, edi
0x10004a1a  jnz     short loc_100049F2
0x10004a1c  push    ebx; lpFileName
0x10004a1d  push    1; nDefault
0x10004a1f  push    offset KeyName; "NeighborsMethod"
0x10004a24  mov     edi, offset _szIniSection; "ICCVID.drv"
0x10004a29  push    edi; lpAppName
0x10004a2a  call    ds:__imp__GetPrivateProfileIntA@16; GetPrivateProfileIntA(x,x,x,x)
0x10004a30  push    ebx; lpFileName
0x10004a31  push    0Eh; nDefault
0x10004a33  push    offset aNeighborsround; "NeighborsRounds"
0x10004a38  push    edi; lpAppName
0x10004a39  mov     [esi+0BCh], ax
0x10004a40  call    ds:__imp__GetPrivateProfileIntA@16; GetPrivateProfileIntA(x,x,x,x)
0x10004a46  mov     [esi+0BEh], ax
0x10004a4d  mov     eax, esi
0x10004a4f  jmp     short loc_10004A58
0x10004a51  mov     ecx, esi; hMem
0x10004a53  call    _UnwindCompressBegin@4; UnwindCompressBegin(x)
0x10004a58  pop     edi
0x10004a59  pop     esi
0x10004a5a  pop     ebx
0x10004a5b  mov     esp, ebp
0x10004a5d  pop     ebp
0x10004a5e  retn    18h
```
