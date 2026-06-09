# CTxtRange::Set(long,long)

- ea: `0x180016700`
- end: `0x180016d82`
- name: `?Set@CTxtRange@@QEAAHJJ@Z`
- size: `1666`
- prototype: `__int64 __fastcall(CTxtRange *__hidden this, int, int)`
- caller_count: `33`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1800020c4`
- `0x180005510`
- `0x1800159d8`
- `0x180019e4c`
- `0x18001eb2c`
- `0x1800238dc`
- `0x18002cf2c`
- `0x18002d048`
- `0x180031ffc`
- `0x180035230`
- `0x180043e88`
- `0x1800445b4`
- `0x180045164`
- `0x180046484`
- `0x18004a97c`
- `0x18004ad84`
- `0x18004ae60`
- `0x18005b350`
- `0x180074d50`
- `0x180075420`
- `0x180080f88`
- `0x1800813b8`
- `0x18008178c`
- `0x180082964`
- `0x180082c68`
- `0x1800832a8`
- `0x180089fe0`
- `0x18008a468`
- `0x18008afec`
- `0x18008b588`
- `0x18008c240`
- `0x18008c4f0`
- `0x18008c640`

## callees

- `0x180006570`
- `0x180016700`
- `0x180016d90`
- `0x18001f230`
- `0x18002f560`
- `0x1800301a0`
- `0x18003cc90`
- `0x180045230`

## pseudocode

```c
__int64 __fastcall CTxtRange::Set(CTxtRange *this, int a2, int a3)
{
  __int64 v3; // r10
  int v4; // r12d
  int v6; // r9d
  int v7; // eax
  int v8; // r14d
  int v9; // ecx
  int v10; // ebp
  int v11; // edx
  int v12; // r15d
  __int64 v13; // r9
  int v14; // r8d
  int v15; // ecx
  int v16; // r10d
  int *v17; // r8
  int v18; // eax
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  __int64 v22; // r10
  int v23; // eax
  int v24; // edx
  int v25; // r11d
  int *v26; // r9
  int v27; // esi
  int v28; // eax
  int v29; // edx
  __int64 v30; // r9
  int v31; // eax
  int v32; // r10d
  int *v33; // r8
  int v34; // eax
  int v35; // ecx
  __int16 v36; // r10
  int v37; // ebp
  __int16 v38; // cx
  __int16 v39; // cx
  bool v40; // zf
  __int64 result; // rax
  int v42; // r8d
  int v43; // eax
  int v44; // eax
  int v45; // r8d
  _DWORD *v46; // rax
  int v47; // edx
  int v48; // eax
  int v49; // eax
  int v50; // edx
  _DWORD *v51; // rax
  int v52; // eax
  int v53; // edx
  int v54; // eax
  int v55; // eax
  int v56; // edx
  _DWORD *v57; // rax
  int v58; // edx
  int v59; // eax
  int v60; // esi
  __m128i v61; // xmm1
  int v62; // esi
  int v63; // ebp
  int v64; // edx
  int v65; // ecx
  __m128i v66; // xmm1
  __int128 v67; // xmm0
  __int128 v68; // [rsp+20h] [rbp-58h] BYREF
  __m128i v69; // [rsp+30h] [rbp-48h]
  int v70; // [rsp+88h] [rbp+10h] BYREF
  int v71; // [rsp+90h] [rbp+18h] BYREF

  v3 = *((_QWORD *)this + 6);
  v4 = *((_DWORD *)this + 22);
  v6 = *(_DWORD *)(v3 + 272);
  v7 = *(_DWORD *)(v3 + 180);
  if ( (v7 & 1) != 0 )
    v6 -= ((v7 & 0x80000) != 0) + 1;
  v8 = *((_DWORD *)this + 10);
  v9 = a2 - a3;
  if ( v3 )
    v10 = *(_DWORD *)(*((_QWORD *)this + 3) + 24LL);
  else
    v10 = 0;
  if ( a2 < v10 )
    v10 = a2;
  if ( v10 <= 0 )
    v10 = 0;
  if ( v3 )
    v11 = *(_DWORD *)(*((_QWORD *)this + 3) + 24LL);
  else
    v11 = 0;
  v12 = 0;
  if ( v9 >= v11 )
    v9 = v11;
  if ( v9 > 0 )
    v12 = v9;
  if ( v10 == v12 && v10 > v6 )
  {
    v12 = v6;
    v10 = v6;
  }
  if ( v10 == v8 )
    goto LABEL_64;
  v13 = *((_QWORD *)this + 3);
  if ( !v13 )
    goto LABEL_64;
  v14 = *(_DWORD *)(v13 + 8);
  if ( !v14 )
    goto LABEL_64;
  if ( v10 < v8 / 2 )
  {
    *((_QWORD *)this + 4) = 0;
    v58 = 0;
    if ( v10 > 0 )
      v58 = v10;
    v20 = CRunPtrBase::AdvanceCp((CTxtRange *)((char *)this + 24), v58);
  }
  else
  {
    v15 = v10 - v8;
    if ( v10 - v8 < 0 )
    {
      while ( v15 < 0 )
      {
        v52 = *((_DWORD *)this + 9);
        v53 = v52 + v15;
        if ( -v15 <= v52 )
        {
          *((_DWORD *)this + 9) = v53;
LABEL_33:
          v15 = 0;
          break;
        }
        v54 = *((_DWORD *)this + 8);
        v15 = v53;
        if ( v54 <= 0 )
        {
          *((_QWORD *)this + 4) = 0;
          break;
        }
        v55 = v54 - 1;
        *((_DWORD *)this + 8) = v55;
        v56 = *(_DWORD *)(v13 + 8);
        if ( v56 > 0 && v55 < v56 && *(_QWORD *)v13 && v55 >= 0 )
          v57 = (_DWORD *)(*(_QWORD *)v13 + *(_DWORD *)(v13 + 16) * v55);
        else
          v57 = 0;
        *((_DWORD *)this + 9) = *v57;
      }
    }
    else
    {
      v16 = *((_DWORD *)this + 8);
      if ( v14 > 0 && v16 < v14 && *(_QWORD *)v13 && v16 >= 0 )
        v17 = (int *)(*(_QWORD *)v13 + *(_DWORD *)(v13 + 16) * v16);
      else
        v17 = 0;
      while ( v15 > 0 )
      {
        v18 = *v17;
        *((_DWORD *)this + 9) += v15;
        v19 = *((_DWORD *)this + 9);
        if ( v19 < v18 )
          goto LABEL_33;
        v15 = v19 - v18;
        *((_DWORD *)this + 8) = v16 + 1;
        if ( v16 + 1 >= *(_DWORD *)(v13 + 8) )
        {
          *((_DWORD *)this + 8) = v16;
          *((_DWORD *)this + 9) = v18;
          break;
        }
        *((_DWORD *)this + 9) = 0;
        ++v16;
        v17 = (int *)((char *)v17 + *(int *)(v13 + 16));
      }
    }
    v20 = v10 - v15;
  }
  *((_DWORD *)this + 10) = v20;
  v21 = v20 - v8;
  if ( !v21 )
  {
    v27 = 0;
LABEL_50:
    if ( !v27 )
      goto LABEL_64;
    v21 = v27;
    goto LABEL_52;
  }
  v22 = *((_QWORD *)this + 7);
  if ( v22 && (v23 = *(_DWORD *)(v22 + 8)) != 0 )
  {
    v24 = v21;
    if ( v21 >= 0 )
    {
      v25 = *((_DWORD *)this + 16);
      if ( v23 > 0 && v25 < v23 && *(_QWORD *)v22 && v25 >= 0 )
        v26 = (int *)(*(_QWORD *)v22 + *(_DWORD *)(v22 + 16) * v25);
      else
        v26 = 0;
      v27 = v21;
      while ( v24 > 0 )
      {
        v28 = *v26;
        *((_DWORD *)this + 17) += v24;
        v29 = *((_DWORD *)this + 17);
        if ( v29 < v28 )
          goto LABEL_52;
        *((_DWORD *)this + 16) = v25 + 1;
        if ( v25 + 1 >= *(_DWORD *)(v22 + 8) )
        {
          *((_DWORD *)this + 16) = v25;
          *((_DWORD *)this + 17) = v28;
          goto LABEL_52;
        }
        v24 = v29 - v28;
        *((_DWORD *)this + 17) = 0;
        ++v25;
        v26 = (int *)((char *)v26 + *(int *)(v22 + 16));
      }
      goto LABEL_50;
    }
    v27 = v21;
    while ( v24 < 0 )
    {
      v42 = *((_DWORD *)this + 17);
      if ( -v24 <= v42 )
      {
        *((_DWORD *)this + 17) = v42 + v24;
        break;
      }
      v43 = *((_DWORD *)this + 16);
      if ( v43 <= 0 )
      {
        *((_QWORD *)this + 8) = 0;
        break;
      }
      v24 += v42;
      v44 = v43 - 1;
      *((_DWORD *)this + 16) = v44;
      v45 = *(_DWORD *)(v22 + 8);
      if ( v45 > 0 && v44 < v45 && *(_QWORD *)v22 && v44 >= 0 )
        v46 = (_DWORD *)(*(_QWORD *)v22 + *(_DWORD *)(v22 + 16) * v44);
      else
        v46 = 0;
      *((_DWORD *)this + 17) = *v46;
    }
  }
  else
  {
    v27 = v21;
  }
LABEL_52:
  v30 = *((_QWORD *)this + 9);
  if ( v30 )
  {
    v31 = *(_DWORD *)(v30 + 8);
    if ( v31 )
    {
      if ( v27 < 0 )
      {
        while ( v21 < 0 )
        {
          v47 = *((_DWORD *)this + 21);
          if ( -v21 <= v47 )
          {
            *((_DWORD *)this + 21) = v47 + v21;
            break;
          }
          v48 = *((_DWORD *)this + 20);
          if ( v48 <= 0 )
          {
            *((_QWORD *)this + 10) = 0;
            break;
          }
          v21 += v47;
          v49 = v48 - 1;
          *((_DWORD *)this + 20) = v49;
          v50 = *(_DWORD *)(v30 + 8);
          if ( v50 > 0 && v49 < v50 && *(_QWORD *)v30 && v49 >= 0 )
            v51 = (_DWORD *)(*(_QWORD *)v30 + *(_DWORD *)(v30 + 16) * v49);
          else
            v51 = 0;
          *((_DWORD *)this + 21) = *v51;
        }
      }
      else
      {
        v32 = *((_DWORD *)this + 20);
        if ( v31 > 0 && v32 < v31 && *(_QWORD *)v30 && v32 >= 0 )
          v33 = (int *)(*(_QWORD *)v30 + *(_DWORD *)(v30 + 16) * v32);
        else
          v33 = 0;
        while ( v21 > 0 )
        {
          v34 = *v33;
          *((_DWORD *)this + 21) += v21;
          v35 = *((_DWORD *)this + 21);
          if ( v35 < v34 )
            break;
          *((_DWORD *)this + 20) = v32 + 1;
          if ( v32 + 1 >= *(_DWORD *)(v30 + 8) )
          {
            *((_DWORD *)this + 20) = v32;
            *((_DWORD *)this + 21) = v34;
            break;
          }
          v21 = v35 - v34;
          *((_DWORD *)this + 21) = 0;
          ++v32;
          v33 = (int *)((char *)v33 + *(int *)(v30 + 16));
        }
      }
    }
  }
LABEL_64:
  if ( (*(_DWORD *)(*((_QWORD *)this + 6) + 180LL) & 0x80000) != 0 )
  {
    v59 = CTxtPtr::AdjustCpCRLF((CTxtRange *)((char *)this + 24));
    v60 = v59;
    if ( v59 )
    {
      CRunPtrBase::AdvanceCp((CTxtRange *)((char *)this + 56), v59);
      CRunPtrBase::AdvanceCp((CTxtRange *)((char *)this + 72), v60);
      v10 = *((_DWORD *)this + 10);
    }
    if ( v12 != v10 )
    {
      v61 = *(__m128i *)((char *)this + 40);
      v68 = *(_OWORD *)((char *)this + 24);
      v69 = v61;
      CTxtPtr::AdvanceCp((CTxtPtr *)&v68, v12 - v10);
      v12 += CTxtPtr::AdjustCpCRLF((CTxtPtr *)&v68);
    }
  }
  v36 = *((_WORD *)this + 49);
  v37 = v10 - v12;
  *((_DWORD *)this + 22) = v37;
  if ( (v36 & 2) != 0 )
  {
    if ( !v37 )
    {
      v36 &= 0xFE7Fu;
      goto LABEL_66;
    }
    v71 = 0;
    v70 = 0;
    CTxtRange::GetRange(this, &v71, &v70);
    v62 = v70;
    v63 = v71;
    if ( v8 != -1 )
    {
      if ( v4 <= 0 )
      {
        v65 = v8;
        v64 = v8 - v4;
      }
      else
      {
        v64 = v8;
        v65 = v8 - v4;
      }
      if ( (v36 & 0x80u) != 0 )
      {
        if ( v71 <= v65 && v70 >= v64 )
          goto LABEL_66;
      }
      else if ( v71 >= v65 && v70 <= v64 )
      {
        goto LABEL_66;
      }
    }
    v66 = *(__m128i *)((char *)this + 40);
    v67 = *(_OWORD *)((char *)this + 24);
    v70 = 0;
    v68 = v67;
    v69 = v66;
    CTxtPtr::AdvanceCp((CTxtPtr *)&v68, v71 - _mm_cvtsi128_si32(v66));
    CTxtPtr::FindEOP((CTxtPtr *)&v68, v62 - v63, (unsigned __int64)&v70);
    v36 = *((_WORD *)this + 49) & 0xFE7F | v70 & 0x100 | ((unsigned int)v70 >> 2) & 0x80;
  }
LABEL_66:
  v38 = 0;
  if ( *((_DWORD *)this + 10) < v8 )
    v38 = 64;
  v39 = v36 & 0xFFBF | v38;
  v40 = v8 == *((_DWORD *)this + 10);
  *((_WORD *)this + 49) = v39;
  if ( !v40 || (result = 0, v4 != *((_DWORD *)this + 22)) )
  {
    if ( (v39 & 2) != 0 )
      CCallMgr::SetSelectionChanged(*(CCallMgr **)(*((_QWORD *)this + 6) + 144LL));
    CTxtRange::Update_iFormat(this, -1);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180016700  mov     rax, rsp
0x180016703  push    rbx
0x180016704  push    r12
0x180016706  push    r13
0x180016708  sub     rsp, 60h
0x18001670c  mov     r10, [rcx+30h]
0x180016710  xor     r13d, r13d
0x180016713  mov     r12d, [rcx+58h]
0x180016717  mov     rbx, rcx
0x18001671a  mov     [rax+8], rbp
0x18001671e  mov     [rax-28h], rdi
0x180016722  mov     r9d, [r10+110h]
0x180016729  mov     [rax-30h], r14
0x18001672d  mov     [rax-38h], r15
0x180016731  mov     eax, [r10+0B4h]
0x180016738  test    al, 1
0x18001673a  jz      short loc_18001674B
0x18001673c  bt      eax, 13h
0x180016740  mov     eax, r13d
0x180016743  setb    al
0x180016746  inc     eax
0x180016748  sub     r9d, eax
0x18001674b  mov     r14d, [rcx+28h]
0x18001674f  mov     ecx, edx
0x180016751  sub     ecx, r8d
0x180016754  test    r10, r10
0x180016757  jz      loc_180016BDA
0x18001675d  mov     rax, [rbx+18h]
0x180016761  mov     ebp, [rax+18h]
0x180016764  cmp     edx, ebp
0x180016766  cmovl   ebp, edx
0x180016769  test    ebp, ebp
0x18001676b  cmovle  ebp, r13d
0x18001676f  test    r10, r10
0x180016772  jz      loc_180016BE2
0x180016778  mov     rax, [rbx+18h]
0x18001677c  mov     edx, [rax+18h]
0x18001677f  cmp     ecx, edx
0x180016781  mov     r15d, r13d
0x180016784  cmovge  ecx, edx
0x180016787  test    ecx, ecx
0x180016789  cmovg   r15d, ecx
0x18001678d  cmp     ebp, r15d
0x180016790  jnz     short loc_18001679D
0x180016792  cmp     ebp, r9d
0x180016795  jle     short loc_18001679D
0x180016797  mov     r15d, r9d
0x18001679a  mov     ebp, r9d
0x18001679d  mov     r11d, ebp
0x1800167a0  mov     [rsp+78h+var_20], rsi
0x1800167a5  sub     r11d, r14d
0x1800167a8  jz      loc_180016996
0x1800167ae  mov     r9, [rbx+18h]
0x1800167b2  test    r9, r9
0x1800167b5  jz      loc_180016996
0x1800167bb  mov     r8d, [r9+8]
0x1800167bf  test    r8d, r8d
0x1800167c2  jz      loc_180016996
0x1800167c8  mov     eax, r14d
0x1800167cb  cdq
0x1800167cc  sub     eax, edx
0x1800167ce  sar     eax, 1
0x1800167d0  cmp     ebp, eax
0x1800167d2  jl      loc_180016BA9
0x1800167d8  mov     ecx, r11d
0x1800167db  test    r11d, r11d
0x1800167de  js      loc_180016B40
0x1800167e4  mov     r10d, [rbx+20h]
0x1800167e8  test    r8d, r8d
0x1800167eb  jle     loc_180016BFA
0x1800167f1  cmp     r10d, r8d
0x1800167f4  jge     loc_180016BFA
0x1800167fa  mov     rdx, [r9]
0x1800167fd  test    rdx, rdx
0x180016800  jz      loc_180016BFA
0x180016806  test    r10d, r10d
0x180016809  js      loc_180016BFA
0x18001680f  mov     eax, r10d
0x180016812  imul    eax, [r9+10h]
0x180016817  movsxd  r8, eax
0x18001681a  add     r8, rdx
0x18001681d  nop     dword ptr [rax]
0x180016820  test    ecx, ecx
0x180016822  jle     short loc_18001685A
0x180016824  mov     eax, [r8]
0x180016827  add     [rbx+24h], ecx
0x18001682a  mov     ecx, [rbx+24h]
0x18001682d  cmp     ecx, eax
0x18001682f  jl      short loc_180016857
0x180016831  lea     edx, [r10+1]
0x180016835  sub     ecx, eax
0x180016837  mov     [rbx+20h], edx
0x18001683a  cmp     edx, [r9+8]
0x18001683e  jge     loc_180016A52
0x180016844  mov     [rbx+24h], r13d
0x180016848  mov     r10d, edx
0x18001684b  movsxd  rax, dword ptr [r9+10h]
0x18001684f  add     r8, rax
0x180016852  jmp     short loc_180016820
0x180016854  mov     [rbx+24h], edx
0x180016857  mov     ecx, r13d
0x18001685a  sub     r11d, ecx
0x18001685d  lea     ecx, [r14+r11]
0x180016861  mov     [rbx+28h], ecx
0x180016864  sub     ecx, r14d
0x180016867  jz      loc_180016905
0x18001686d  mov     r10, [rbx+38h]
0x180016871  test    r10, r10
0x180016874  jz      loc_180016A33
0x18001687a  mov     eax, [r10+8]
0x18001687e  test    eax, eax
0x180016880  jz      loc_180016A33
0x180016886  mov     edx, ecx
0x180016888  test    ecx, ecx
0x18001688a  js      loc_180016A5E
0x180016890  mov     r11d, [rbx+40h]
0x180016894  test    eax, eax
0x180016896  jle     loc_180016BEA
0x18001689c  cmp     r11d, eax
0x18001689f  jge     loc_180016BEA
0x1800168a5  mov     r8, [r10]
0x1800168a8  test    r8, r8
0x1800168ab  jz      loc_180016BEA
0x1800168b1  test    r11d, r11d
0x1800168b4  js      loc_180016BEA
0x1800168ba  mov     eax, r11d
0x1800168bd  imul    eax, [r10+10h]
0x1800168c2  movsxd  r9, eax
0x1800168c5  add     r9, r8
0x1800168c8  mov     esi, ecx
0x1800168ca  nop     word ptr [rax+rax+00h]
0x1800168d0  test    edx, edx
0x1800168d2  jle     short loc_180016907
0x1800168d4  mov     eax, [r9]
0x1800168d7  add     [rbx+44h], edx
0x1800168da  mov     edx, [rbx+44h]
0x1800168dd  cmp     edx, eax
0x1800168df  jl      short loc_180016911
0x1800168e1  lea     r8d, [r11+1]
0x1800168e5  mov     [rbx+40h], r8d
0x1800168e9  cmp     r8d, [r10+8]
0x1800168ed  jge     loc_180016A46
0x1800168f3  sub     edx, eax
0x1800168f5  mov     [rbx+44h], r13d
0x1800168f9  movsxd  rax, dword ptr [r10+10h]
0x1800168fd  mov     r11d, r8d
0x180016900  add     r9, rax
0x180016903  jmp     short loc_1800168D0
0x180016905  mov     esi, ecx
0x180016907  test    esi, esi
0x180016909  jz      loc_180016996
0x18001690f  mov     ecx, esi
0x180016911  mov     r9, [rbx+48h]
0x180016915  test    r9, r9
0x180016918  jz      short loc_180016996
0x18001691a  mov     eax, [r9+8]
0x18001691e  test    eax, eax
0x180016920  jz      short loc_180016996
0x180016922  test    esi, esi
0x180016924  js      loc_180016AC7
0x18001692a  mov     r10d, [rbx+50h]
0x18001692e  test    eax, eax
0x180016930  jle     loc_180016BF2
0x180016936  cmp     r10d, eax
0x180016939  jge     loc_180016BF2
0x18001693f  mov     rdx, [r9]
0x180016942  test    rdx, rdx
0x180016945  jz      loc_180016BF2
0x18001694b  test    r10d, r10d
0x18001694e  js      loc_180016BF2
0x180016954  mov     eax, r10d
0x180016957  imul    eax, [r9+10h]
0x18001695c  movsxd  r8, eax
0x18001695f  add     r8, rdx
0x180016962  test    ecx, ecx
0x180016964  jle     short loc_180016996
0x180016966  mov     eax, [r8]
0x180016969  add     [rbx+54h], ecx
0x18001696c  mov     ecx, [rbx+54h]
0x18001696f  cmp     ecx, eax
0x180016971  jl      short loc_180016996
0x180016973  lea     edx, [r10+1]
0x180016977  mov     [rbx+50h], edx
0x18001697a  cmp     edx, [r9+8]
0x18001697e  jge     loc_180016A3A
0x180016984  sub     ecx, eax
0x180016986  mov     [rbx+54h], r13d
0x18001698a  movsxd  rax, dword ptr [r9+10h]
0x18001698e  mov     r10d, edx
0x180016991  add     r8, rax
0x180016994  jmp     short loc_180016962
0x180016996  mov     rax, [rbx+30h]
0x18001699a  test    dword ptr [rax+0B4h], 80000h
0x1800169a4  jnz     loc_180016C1D
0x1800169aa  movzx   r10d, word ptr [rbx+62h]
0x1800169af  sub     ebp, r15d
0x1800169b2  mov     r15, [rsp+78h+var_38]
0x1800169b7  mov     [rbx+58h], ebp
0x1800169ba  test    r10b, 2
0x1800169be  jnz     loc_180016B93
0x1800169c4  cmp     [rbx+28h], r14d
0x1800169c8  mov     edx, 40h ; '@'
0x1800169cd  mov     rdi, [rsp+78h+var_28]
0x1800169d2  mov     ecx, r13d
0x1800169d5  mov     rsi, [rsp+78h+var_20]
0x1800169da  cmovl   cx, dx
0x1800169de  mov     rbp, [rsp+78h+arg_0]
0x1800169e6  mov     edx, 0FFBFh
0x1800169eb  and     r10w, dx
0x1800169ef  or      cx, r10w
0x1800169f3  cmp     r14d, [rbx+28h]
0x1800169f7  mov     r14, [rsp+78h+var_30]
0x1800169fc  mov     [rbx+62h], cx
0x180016a00  jz      short loc_180016A28
0x180016a02  test    cl, 2
0x180016a05  jnz     loc_180016D6D
0x180016a0b  mov     edx, 0FFFFFFFFh; int
0x180016a10  mov     rcx, rbx; this
0x180016a13  call    ?Update_iFormat@CTxtRange@@QEAAXJ@Z; CTxtRange::Update_iFormat(long)
0x180016a18  mov     eax, 1
0x180016a1d  add     rsp, 60h
0x180016a21  pop     r13
0x180016a23  pop     r12
0x180016a25  pop     rbx
0x180016a26  retn
0x180016a28  mov     eax, r13d
0x180016a2b  cmp     r12d, [rbx+58h]
0x180016a2f  jz      short loc_180016A1D
0x180016a31  jmp     short loc_180016A02
0x180016a33  mov     esi, ecx
0x180016a35  jmp     loc_180016911
0x180016a3a  mov     [rbx+50h], r10d
0x180016a3e  mov     [rbx+54h], eax
0x180016a41  jmp     loc_180016996
0x180016a46  mov     [rbx+40h], r11d
0x180016a4a  mov     [rbx+44h], eax
0x180016a4d  jmp     loc_180016911
0x180016a52  mov     [rbx+20h], r10d
0x180016a56  mov     [rbx+24h], eax
0x180016a59  jmp     loc_18001685A
0x180016a5e  mov     esi, ecx
0x180016a60  test    edx, edx
0x180016a62  jns     loc_180016911
0x180016a68  mov     r8d, [rbx+44h]
0x180016a6c  mov     eax, edx
0x180016a6e  neg     eax
0x180016a70  cmp     eax, r8d
0x180016a73  jle     loc_180016B25
0x180016a79  mov     eax, [rbx+40h]
0x180016a7c  test    eax, eax
0x180016a7e  jle     loc_180016C0B
0x180016a84  add     edx, r8d
0x180016a87  dec     eax
0x180016a89  mov     [rbx+40h], eax
0x180016a8c  mov     r8d, [r10+8]
0x180016a90  test    r8d, r8d
0x180016a93  jle     loc_180016BC5
0x180016a99  cmp     eax, r8d
0x180016a9c  jge     loc_180016BC5
0x180016aa2  mov     r8, [r10]
0x180016aa5  test    r8, r8
0x180016aa8  jz      loc_180016BC5
0x180016aae  test    eax, eax
0x180016ab0  js      loc_180016BC5
0x180016ab6  imul    eax, [r10+10h]
0x180016abb  cdqe
0x180016abd  add     rax, r8
0x180016ac0  mov     eax, [rax]
0x180016ac2  mov     [rbx+44h], eax
0x180016ac5  jmp     short loc_180016A60
0x180016ac7  test    ecx, ecx
0x180016ac9  jns     loc_180016996
0x180016acf  mov     edx, [rbx+54h]
0x180016ad2  mov     eax, ecx
0x180016ad4  neg     eax
0x180016ad6  cmp     eax, edx
0x180016ad8  jle     short loc_180016B31
0x180016ada  mov     eax, [rbx+50h]
0x180016add  test    eax, eax
0x180016adf  jle     loc_180016C14
0x180016ae5  add     ecx, edx
0x180016ae7  dec     eax
0x180016ae9  mov     [rbx+50h], eax
0x180016aec  mov     edx, [r9+8]
0x180016af0  test    edx, edx
0x180016af2  jle     loc_180016BCD
0x180016af8  cmp     eax, edx
0x180016afa  jge     loc_180016BCD
0x180016b00  mov     rdx, [r9]
0x180016b03  test    rdx, rdx
0x180016b06  jz      loc_180016BCD
0x180016b0c  test    eax, eax
0x180016b0e  js      loc_180016BCD
0x180016b14  imul    eax, [r9+10h]
0x180016b19  cdqe
0x180016b1b  add     rax, rdx
0x180016b1e  mov     eax, [rax]
0x180016b20  mov     [rbx+54h], eax
0x180016b23  jmp     short loc_180016AC7
0x180016b25  lea     eax, [r8+rdx]
  ... truncated ...
```
