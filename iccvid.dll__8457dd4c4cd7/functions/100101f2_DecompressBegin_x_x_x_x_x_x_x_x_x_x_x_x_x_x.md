# DecompressBegin(x,x,x,x,x,x,x,x,x,x,x,x,x,x)

- ea: `0x100101f2`
- end: `0x1001051a`
- name: `_DecompressBegin@56`
- size: `808`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x100093a0`
- `0x10010520`

## callees

- `0x1000422a`
- `0x100053b2`
- `0x1000552a`
- `0x10005598`
- `0x1000f82f`
- `0x1000ff0e`
- `0x100101f2`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x100103c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1001041b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10010422`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1001045a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10010461`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x100103c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1001041b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10010422`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1001045a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10010461`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x10010405`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x10010405`

## pseudocode

```c
int __userpurge DecompressBegin@<eax>(
        int a1@<ecx>,
        ULONG a2@<esi>,
        int a3,
        int a4,
        int a5,
        int a6,
        unsigned int a7,
        unsigned int a8,
        int a9,
        int a10,
        int a11,
        int a12,
        int a13,
        int a14)
{
  int v14; // ebx
  int result; // eax
  unsigned int v17; // ebx
  unsigned __int16 v18; // ax
  unsigned __int16 v19; // si
  bool v20; // zf
  int v21; // esi
  unsigned int *v22; // edx
  unsigned __int16 v23; // cx
  int v24; // esi
  unsigned __int16 v25; // ax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  unsigned int *v29; // esi
  int v30; // eax
  unsigned int v31; // ecx
  SIZE_T v32; // esi
  HLOCAL v33; // eax
  HLOCAL *v34; // esi
  __int16 v35; // cx
  _DWORD *v36; // eax
  __int16 v37; // cx
  HLOCAL *v38; // esi
  void *v39; // ecx
  int v40; // eax
  int v41; // eax
  int v42; // eax
  int v43; // [esp-14h] [ebp-38h]
  int v44; // [esp-10h] [ebp-34h]
  int v45; // [esp-Ch] [ebp-30h]
  int v46; // [esp-8h] [ebp-2Ch]
  ULONG v47; // [esp-4h] [ebp-28h]
  ULONG *v48; // [esp+0h] [ebp-24h]
  ULONG *v49; // [esp+0h] [ebp-24h]
  __int16 v50; // [esp+8h] [ebp-1Ch]
  unsigned __int16 v51; // [esp+Ch] [ebp-18h]
  ULONG ulMultiplicand; // [esp+10h] [ebp-14h] BYREF
  int v53; // [esp+14h] [ebp-10h]
  int v54; // [esp+18h] [ebp-Ch]
  int v55; // [esp+1Ch] [ebp-8h]
  int v56; // [esp+20h] [ebp-4h]

  v14 = a9;
  result = DecompressQueryIndirect(a3, a1, a5, a6, &a7, &a8, a9, v43, v44, v45, &a13, &a14);
  if ( !result )
  {
    v56 = DecompressedDibType(v14);
    v17 = a8;
    v50 = word_10003CE4[v56];
    v53 = a13 / (int)a7;
    if ( (((unsigned __int8)a8 | (unsigned __int8)a7) & 3) != 0 )
    {
      if ( a7 + 3 >= a7 )
      {
        ulMultiplicand = (a7 + 3) & 0xFFFFFFFC;
        if ( ULongMult((ULONG)&ulMultiplicand, a2, v48) >= 0 && ulMultiplicand <= 0xFFFF )
        {
          v18 = ulMultiplicand;
          if ( v17 + 3 >= v17 )
          {
            v19 = ulMultiplicand;
            ulMultiplicand = v17 + 3;
            v54 = v18;
            if ( ULongMult((ULONG)&ulMultiplicand, v47, v49) >= 0 && ulMultiplicand <= 0xFFFF )
            {
              v55 = (unsigned __int16)ulMultiplicand;
              v51 = v19;
              if ( *(_DWORD *)(a1 + 92) )
              {
                v20 = *(_WORD *)(a1 + 124) == v19;
                v21 = v56;
                if ( v20 && *(_WORD *)(a1 + 126) == (_WORD)ulMultiplicand && *(_DWORD *)(a1 + 112) == v56 )
                {
                  v20 = (*(_BYTE *)(a1 + 104) & 1) == 0;
                  ulMultiplicand = a1 + 104;
                  if ( !v20 )
                  {
                    v22 = (unsigned int *)(a1 + 140);
                    ulMultiplicand = a1 + 104;
                    v23 = v55;
                    v54 = v51;
                    v24 = v56;
                    v53 = (unsigned __int16)v55;
                    v25 = v51;
                    if ( !*(_DWORD *)(a1 + 128) )
                    {
LABEL_25:
                      v29 = v22;
                      v54 = v25;
                      v55 = v23;
                      if ( *(_DWORD *)(a1 + 128) )
                      {
                        LocalFree(*(HLOCAL *)(a1 + 128));
                        v23 = v53;
                        *(_DWORD *)(a1 + 128) = 0;
                        *(_DWORD *)(a1 + 132) = 0;
                        *(_DWORD *)(a1 + 136) = 0;
                      }
                      v30 = (__int16)v23;
                      v31 = *v29;
                      v32 = v30 * *v29;
                      if ( v31 && v32 / v31 != v30 || v32 > 0x7FFFFFFF )
                      {
                        v38 = *(HLOCAL **)(a1 + 92);
                        LocalFree(v38[7]);
                        LocalFree(v38);
                        v46 = -100;
                        goto LABEL_34;
                      }
                      v33 = LocalAlloc(0x40u, v32);
                      *(_DWORD *)(a1 + 128) = v33;
                      if ( !v33 )
                      {
                        v34 = *(HLOCAL **)(a1 + 92);
                        LocalFree(v34[7]);
                        LocalFree(v34);
                        v46 = -3;
LABEL_34:
                        result = v46;
                        *(_DWORD *)(a1 + 92) = 0;
                        return result;
                      }
                      v35 = v54;
                      *(_DWORD *)(a1 + 132) = v33;
                      v36 = (_DWORD *)ulMultiplicand;
                      *(_WORD *)(a1 + 124) = v35;
                      v37 = v55;
                      *(_DWORD *)(a1 + 136) = v32;
                      *v36 |= 1u;
                      v24 = v56;
                      *(_WORD *)(a1 + 126) = v37;
                    }
LABEL_50:
                    *(_WORD *)(a1 + 120) = a13;
                    *(_WORD *)(a1 + 122) = a14;
                    *(_WORD *)(a1 + 108) = *(_WORD *)(a9 + 14);
                    *(_WORD *)(a1 + 110) = v50;
                    result = 0;
                    *(_DWORD *)(a1 + 112) = v24;
                    *(_DWORD *)(a1 + 148) = 0;
                    return result;
                  }
                }
                if ( *(int *)(a1 + 96) <= 0 )
                  v26 = 0;
                else
                  v26 = *(_DWORD *)(a1 + 100);
                v27 = CVDecompressEnd(*(HLOCAL *)(a1 + 92), v26);
                *(_DWORD *)(a1 + 92) = 0;
              }
              else
              {
                v21 = v56;
                v27 = 0;
              }
              v28 = CVDecompressBegin(v21, v53, v27);
              *(_DWORD *)(a1 + 92) = v28;
              if ( v28 )
              {
                if ( !v21 )
                  CVDecompressSetPalette(*(_DWORD *)(a1 + 96));
                v22 = (unsigned int *)(a1 + 140);
                ulMultiplicand = a1 + 104;
                v25 = v54;
                *(_DWORD *)(a1 + 140) = v50 * (__int16)v54;
                v23 = v55;
                v53 = (unsigned __int16)v55;
                goto LABEL_25;
              }
            }
          }
        }
      }
      return -3;
    }
    v39 = *(void **)(a1 + 92);
    v24 = v56;
    if ( v39 )
    {
      if ( *(__int16 *)(a1 + 120) == a13
        && *(__int16 *)(a1 + 122) == a14
        && *(_DWORD *)(a1 + 112) == v56
        && (*(_BYTE *)(a1 + 104) & 1) == 0 )
      {
        goto LABEL_49;
      }
      if ( *(int *)(a1 + 96) <= 0 )
        v40 = 0;
      else
        v40 = *(_DWORD *)(a1 + 100);
      v41 = CVDecompressEnd(v39, v40);
      *(_DWORD *)(a1 + 92) = 0;
    }
    else
    {
      v41 = 0;
    }
    v42 = CVDecompressBegin(v24, v53, v41);
    *(_DWORD *)(a1 + 92) = v42;
    if ( !v42 )
      return -3;
    if ( !v24 )
      CVDecompressSetPalette(*(_DWORD *)(a1 + 96));
LABEL_49:
    *(_DWORD *)(a1 + 104) &= ~1u;
    goto LABEL_50;
  }
  return result;
}

```

## disassembly

```asm
0x100101f2  mov     edi, edi
0x100101f4  push    ebp
0x100101f5  mov     ebp, esp
0x100101f7  sub     esp, 1Ch
0x100101fa  lea     eax, [ebp+arg_2C]
0x100101fd  push    ebx
0x100101fe  mov     ebx, [ebp+arg_18]
0x10010201  push    edi; pulResult
0x10010202  push    eax
0x10010203  lea     eax, [ebp+arg_28]
0x10010206  mov     edi, ecx
0x10010208  push    eax
0x10010209  sub     esp, 0Ch
0x1001020c  lea     eax, [ebp+arg_14]
0x1001020f  push    ebx
0x10010210  push    eax
0x10010211  lea     eax, [ebp+arg_10]
0x10010214  push    eax
0x10010215  push    [ebp+arg_C]
0x10010218  push    [ebp+arg_8]
0x1001021b  push    ecx
0x1001021c  push    [ebp+arg_0]
0x1001021f  call    _DecompressQueryIndirect@56; DecompressQueryIndirect(x,x,x,x,x,x,x,x,x,x,x,x,x,x)
0x10010224  test    eax, eax
0x10010226  jnz     loc_10010514
0x1001022c  push    esi; ulMultiplier
0x1001022d  mov     ecx, ebx
0x1001022f  call    _DecompressedDibType@4; DecompressedDibType(x)
0x10010234  mov     esi, [ebp+arg_10]
0x10010237  mov     ecx, esi
0x10010239  mov     [ebp+var_4], eax
0x1001023c  mov     ebx, [ebp+arg_14]
0x1001023f  or      ecx, ebx
0x10010241  movzx   eax, ds:word_10003CE4[eax*2]
0x10010249  mov     [ebp+var_1C], eax
0x1001024c  mov     eax, [ebp+arg_28]
0x1001024f  cdq
0x10010250  idiv    esi
0x10010252  mov     [ebp+var_10], eax
0x10010255  test    cl, 3
0x10010258  jz      loc_10010472
0x1001025e  lea     ecx, [esi+3]
0x10010261  cmp     ecx, esi
0x10010263  jb      loc_100104CE
0x10010269  lea     edx, [ebp+ulMultiplicand]
0x1001026c  and     ecx, 0FFFFFFFCh
0x1001026f  push    edx; ulMultiplicand
0x10010270  mov     edx, eax
0x10010272  mov     [ebp+ulMultiplicand], ecx
0x10010275  call    _ULongMult@12; ULongMult(x,x,x)
0x1001027a  test    eax, eax
0x1001027c  js      loc_100104CE
0x10010282  mov     eax, [ebp+ulMultiplicand]
0x10010285  cmp     eax, 0FFFFh
0x1001028a  ja      loc_100104CE
0x10010290  lea     ecx, [ebx+3]
0x10010293  movzx   eax, ax
0x10010296  cmp     ecx, ebx
0x10010298  jb      loc_100104CE
0x1001029e  mov     edx, [ebp+var_10]
0x100102a1  mov     esi, eax
0x100102a3  lea     eax, [ebp+ulMultiplicand]
0x100102a6  mov     [ebp+ulMultiplicand], ecx
0x100102a9  push    eax; ulMultiplicand
0x100102aa  mov     [ebp+var_C], esi
0x100102ad  call    _ULongMult@12; ULongMult(x,x,x)
0x100102b2  test    eax, eax
0x100102b4  js      loc_100104CE
0x100102ba  mov     eax, [ebp+ulMultiplicand]
0x100102bd  cmp     eax, 0FFFFh
0x100102c2  ja      loc_100104CE
0x100102c8  movzx   edx, ax
0x100102cb  xor     ebx, ebx
0x100102cd  movzx   eax, si
0x100102d0  mov     [ebp+var_8], edx
0x100102d3  mov     [ebp+var_18], eax
0x100102d6  movzx   ecx, dx
0x100102d9  cmp     [edi+5Ch], ebx
0x100102dc  jz      short loc_10010352
0x100102de  cmp     [edi+7Ch], si
0x100102e2  mov     esi, [ebp+var_4]
0x100102e5  jnz     short loc_10010332
0x100102e7  cmp     [edi+7Eh], dx
0x100102eb  jnz     short loc_10010332
0x100102ed  cmp     [edi+70h], esi
0x100102f0  jnz     short loc_10010332
0x100102f2  lea     eax, [edi+68h]
0x100102f5  test    byte ptr [eax], 1
0x100102f8  mov     [ebp+ulMultiplicand], eax
0x100102fb  jz      short loc_10010332
0x100102fd  lea     edx, [edi+8Ch]
0x10010303  mov     esi, [ebp+var_18]
0x10010306  mov     [ebp+var_10], ecx
0x10010309  mov     ecx, [ebp+var_8]
0x1001030c  movzx   esi, si
0x1001030f  mov     [ebp+ulMultiplicand], eax
0x10010312  mov     eax, [ebp+var_18]
0x10010315  movzx   ecx, cx
0x10010318  mov     [ebp+var_C], esi
0x1001031b  mov     esi, [ebp+var_4]
0x1001031e  mov     [ebp+var_10], ecx
0x10010321  movzx   eax, ax
0x10010324  cmp     [edi+80h], ebx
0x1001032a  jnz     loc_100104E8
0x10010330  jmp     short loc_100103AA
0x10010332  cmp     [edi+60h], ebx
0x10010335  jle     short loc_1001033C
0x10010337  mov     eax, [edi+64h]
0x1001033a  jmp     short loc_1001033E
0x1001033c  mov     eax, ebx
0x1001033e  mov     ecx, [edi+5Ch]; hMem
0x10010341  xor     edx, edx
0x10010343  push    eax; int
0x10010344  inc     edx
0x10010345  call    _CVDecompressEnd@12; CVDecompressEnd(x,x,x)
0x1001034a  mov     edx, [ebp+var_8]
0x1001034d  mov     [edi+5Ch], ebx
0x10010350  jmp     short loc_10010357
0x10010352  mov     esi, [ebp+var_4]
0x10010355  mov     eax, ebx
0x10010357  mov     ecx, [ebp+var_C]
0x1001035a  push    eax
0x1001035b  push    [ebp+var_10]
0x1001035e  push    esi
0x1001035f  call    _CVDecompressBegin@20; CVDecompressBegin(x,x,x,x,x)
0x10010364  mov     [edi+5Ch], eax
0x10010367  test    eax, eax
0x10010369  jz      loc_100104CE
0x1001036f  test    esi, esi
0x10010371  jnz     short loc_10010380
0x10010373  push    dword ptr [edi+60h]
0x10010376  mov     edx, [edi+64h]
0x10010379  mov     ecx, eax
0x1001037b  call    _CVDecompressSetPalette@12; CVDecompressSetPalette(x,x,x)
0x10010380  mov     eax, [ebp+var_C]
0x10010383  lea     edx, [edi+8Ch]
0x10010389  movsx   ecx, ax
0x1001038c  mov     eax, [ebp+var_1C]
0x1001038f  cwde
0x10010390  imul    ecx, eax
0x10010393  lea     eax, [edi+68h]
0x10010396  mov     [ebp+ulMultiplicand], eax
0x10010399  mov     eax, [ebp+var_C]
0x1001039c  movzx   eax, ax
0x1001039f  mov     [edx], ecx
0x100103a1  mov     ecx, [ebp+var_8]
0x100103a4  movzx   ecx, cx
0x100103a7  mov     [ebp+var_10], ecx
0x100103aa  movzx   eax, ax
0x100103ad  mov     esi, edx
0x100103af  mov     [ebp+var_C], eax
0x100103b2  movzx   eax, cx
0x100103b5  mov     [ebp+var_8], eax
0x100103b8  mov     eax, [edi+80h]
0x100103be  test    eax, eax
0x100103c0  jz      short loc_100103DE
0x100103c2  push    eax; hMem
0x100103c3  call    ds:__imp__LocalFree@4; LocalFree(x)
0x100103c9  mov     ecx, [ebp+var_10]
0x100103cc  mov     [edi+80h], ebx
0x100103d2  mov     [edi+84h], ebx
0x100103d8  mov     [edi+88h], ebx
0x100103de  movsx   eax, cx
0x100103e1  mov     ecx, [esi]
0x100103e3  mov     esi, ecx
0x100103e5  imul    esi, eax
0x100103e8  mov     [ebp+var_18], eax
0x100103eb  test    ecx, ecx
0x100103ed  jz      short loc_100103FA
0x100103ef  xor     edx, edx
0x100103f1  mov     eax, esi
0x100103f3  div     ecx
0x100103f5  cmp     eax, [ebp+var_18]
0x100103f8  jnz     short loc_10010454
0x100103fa  cmp     esi, 7FFFFFFFh
0x10010400  ja      short loc_10010454
0x10010402  push    esi; uBytes
0x10010403  push    40h ; '@'; uFlags
0x10010405  call    ds:__imp__LocalAlloc@8; LocalAlloc(x,x)
0x1001040b  mov     [edi+80h], eax
0x10010411  test    eax, eax
0x10010413  jnz     short loc_1001042C
0x10010415  mov     esi, [edi+5Ch]
0x10010418  push    dword ptr [esi+1Ch]; hMem
0x1001041b  call    ds:__imp__LocalFree@4; LocalFree(x)
0x10010421  push    esi; hMem
0x10010422  call    ds:__imp__LocalFree@4; LocalFree(x)
0x10010428  push    0FFFFFFFDh
0x1001042a  jmp     short loc_10010469
0x1001042c  mov     ecx, [ebp+var_C]
0x1001042f  mov     [edi+84h], eax
0x10010435  mov     eax, [ebp+ulMultiplicand]
0x10010438  mov     [edi+7Ch], cx
0x1001043c  mov     ecx, [ebp+var_8]
0x1001043f  mov     [edi+88h], esi
0x10010445  or      dword ptr [eax], 1
0x10010448  mov     esi, [ebp+var_4]
0x1001044b  mov     [edi+7Eh], cx
0x1001044f  jmp     loc_100104E8
0x10010454  mov     esi, [edi+5Ch]
0x10010457  push    dword ptr [esi+1Ch]; hMem
0x1001045a  call    ds:__imp__LocalFree@4; LocalFree(x)
0x10010460  push    esi; hMem
0x10010461  call    ds:__imp__LocalFree@4; LocalFree(x)
0x10010467  push    0FFFFFF9Ch
0x10010469  pop     eax
0x1001046a  mov     [edi+5Ch], ebx
0x1001046d  jmp     loc_10010513
0x10010472  mov     ecx, [edi+5Ch]; hMem
0x10010475  xor     ebx, ebx
0x10010477  mov     esi, [ebp+var_4]
0x1001047a  test    ecx, ecx
0x1001047c  jz      short loc_100104B5
0x1001047e  movsx   eax, word ptr [edi+78h]
0x10010482  cmp     eax, [ebp+arg_28]
0x10010485  jnz     short loc_1001049B
0x10010487  movsx   eax, word ptr [edi+7Ah]
0x1001048b  cmp     eax, [ebp+arg_2C]
0x1001048e  jnz     short loc_1001049B
0x10010490  cmp     [edi+70h], esi
0x10010493  jnz     short loc_1001049B
0x10010495  test    byte ptr [edi+68h], 1
0x10010499  jz      short loc_100104E4
0x1001049b  cmp     [edi+60h], ebx
0x1001049e  jle     short loc_100104A5
0x100104a0  mov     eax, [edi+64h]
0x100104a3  jmp     short loc_100104A7
0x100104a5  mov     eax, ebx
0x100104a7  xor     edx, edx
0x100104a9  push    eax; int
0x100104aa  inc     edx
0x100104ab  call    _CVDecompressEnd@12; CVDecompressEnd(x,x,x)
0x100104b0  mov     [edi+5Ch], ebx
0x100104b3  jmp     short loc_100104B7
0x100104b5  mov     eax, ebx
0x100104b7  mov     edx, [ebp+arg_2C]
0x100104ba  mov     ecx, [ebp+arg_28]
0x100104bd  push    eax
0x100104be  push    [ebp+var_10]
0x100104c1  push    esi
0x100104c2  call    _CVDecompressBegin@20; CVDecompressBegin(x,x,x,x,x)
0x100104c7  mov     [edi+5Ch], eax
0x100104ca  test    eax, eax
0x100104cc  jnz     short loc_100104D3
0x100104ce  push    0FFFFFFFDh
0x100104d0  pop     eax
0x100104d1  jmp     short loc_10010513
0x100104d3  test    esi, esi
0x100104d5  jnz     short loc_100104E4
0x100104d7  push    dword ptr [edi+60h]
0x100104da  mov     edx, [edi+64h]
0x100104dd  mov     ecx, eax
0x100104df  call    _CVDecompressSetPalette@12; CVDecompressSetPalette(x,x,x)
0x100104e4  and     dword ptr [edi+68h], 0FFFFFFFEh
0x100104e8  mov     eax, [ebp+arg_28]
0x100104eb  mov     [edi+78h], ax
0x100104ef  mov     eax, [ebp+arg_2C]
0x100104f2  mov     [edi+7Ah], ax
0x100104f6  mov     eax, [ebp+arg_18]
0x100104f9  mov     ax, [eax+0Eh]
0x100104fd  mov     [edi+6Ch], ax
0x10010501  mov     eax, [ebp+var_1C]
0x10010504  mov     [edi+6Eh], ax
0x10010508  xor     eax, eax
0x1001050a  mov     [edi+70h], esi
0x1001050d  mov     [edi+94h], ebx
0x10010513  pop     esi
0x10010514  pop     edi
0x10010515  pop     ebx
0x10010516  leave
0x10010517  retn    30h ; '0'
```
