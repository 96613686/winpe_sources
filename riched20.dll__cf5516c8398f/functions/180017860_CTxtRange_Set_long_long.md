# CTxtRange::Set(long,long)

- ea: `0x180017860`
- end: `0x180017ee2`
- name: `?Set@CTxtRange@@QEAAHJJ@Z`
- size: `1666`
- prototype: `__int64 __fastcall(CTxtRange *__hidden this, int, int)`
- caller_count: `33`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180002044`
- `0x180005480`
- `0x180016b44`
- `0x18001d0b8`
- `0x18001d24c`
- `0x18001ebcc`
- `0x180026e40`
- `0x18002bfc0`
- `0x1800322bc`
- `0x1800323d8`
- `0x180042de8`
- `0x180043514`
- `0x180044094`
- `0x180045358`
- `0x180049814`
- `0x180049c1c`
- `0x180049cf4`
- `0x180059d40`
- `0x180072e04`
- `0x1800734d4`
- `0x18007eb28`
- `0x18007ef48`
- `0x18007f31c`
- `0x1800804d8`
- `0x1800807d8`
- `0x180080e14`
- `0x1800879a0`
- `0x180087e28`
- `0x180088988`
- `0x180088f24`
- `0x180089be0`
- `0x180089e90`
- `0x180089fe0`

## callees

- `0x1800064d0`
- `0x180017860`
- `0x180017ef0`
- `0x18001d8b0`
- `0x180023ce0`
- `0x180024910`
- `0x18003c4f4`
- `0x180045120`

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
0x180017860  mov     rax, rsp
0x180017863  push    rbx
0x180017864  push    r12
0x180017866  push    r13
0x180017868  sub     rsp, 60h
0x18001786c  mov     r10, [rcx+30h]
0x180017870  xor     r13d, r13d
0x180017873  mov     r12d, [rcx+58h]
0x180017877  mov     rbx, rcx
0x18001787a  mov     [rax+8], rbp
0x18001787e  mov     [rax-28h], rdi
0x180017882  mov     r9d, [r10+110h]
0x180017889  mov     [rax-30h], r14
0x18001788d  mov     [rax-38h], r15
0x180017891  mov     eax, [r10+0B4h]
0x180017898  test    al, 1
0x18001789a  jz      short loc_1800178AB
0x18001789c  bt      eax, 13h
0x1800178a0  mov     eax, r13d
0x1800178a3  setb    al
0x1800178a6  inc     eax
0x1800178a8  sub     r9d, eax
0x1800178ab  mov     r14d, [rcx+28h]
0x1800178af  mov     ecx, edx
0x1800178b1  sub     ecx, r8d
0x1800178b4  test    r10, r10
0x1800178b7  jz      loc_180017D3A
0x1800178bd  mov     rax, [rbx+18h]
0x1800178c1  mov     ebp, [rax+18h]
0x1800178c4  cmp     edx, ebp
0x1800178c6  cmovl   ebp, edx
0x1800178c9  test    ebp, ebp
0x1800178cb  cmovle  ebp, r13d
0x1800178cf  test    r10, r10
0x1800178d2  jz      loc_180017D42
0x1800178d8  mov     rax, [rbx+18h]
0x1800178dc  mov     edx, [rax+18h]
0x1800178df  cmp     ecx, edx
0x1800178e1  mov     r15d, r13d
0x1800178e4  cmovge  ecx, edx
0x1800178e7  test    ecx, ecx
0x1800178e9  cmovg   r15d, ecx
0x1800178ed  cmp     ebp, r15d
0x1800178f0  jnz     short loc_1800178FD
0x1800178f2  cmp     ebp, r9d
0x1800178f5  jle     short loc_1800178FD
0x1800178f7  mov     r15d, r9d
0x1800178fa  mov     ebp, r9d
0x1800178fd  mov     r11d, ebp
0x180017900  mov     [rsp+78h+var_20], rsi
0x180017905  sub     r11d, r14d
0x180017908  jz      loc_180017AF6
0x18001790e  mov     r9, [rbx+18h]
0x180017912  test    r9, r9
0x180017915  jz      loc_180017AF6
0x18001791b  mov     r8d, [r9+8]
0x18001791f  test    r8d, r8d
0x180017922  jz      loc_180017AF6
0x180017928  mov     eax, r14d
0x18001792b  cdq
0x18001792c  sub     eax, edx
0x18001792e  sar     eax, 1
0x180017930  cmp     ebp, eax
0x180017932  jl      loc_180017D09
0x180017938  mov     ecx, r11d
0x18001793b  test    r11d, r11d
0x18001793e  js      loc_180017CA0
0x180017944  mov     r10d, [rbx+20h]
0x180017948  test    r8d, r8d
0x18001794b  jle     loc_180017D5A
0x180017951  cmp     r10d, r8d
0x180017954  jge     loc_180017D5A
0x18001795a  mov     rdx, [r9]
0x18001795d  test    rdx, rdx
0x180017960  jz      loc_180017D5A
0x180017966  test    r10d, r10d
0x180017969  js      loc_180017D5A
0x18001796f  mov     eax, r10d
0x180017972  imul    eax, [r9+10h]
0x180017977  movsxd  r8, eax
0x18001797a  add     r8, rdx
0x18001797d  nop     dword ptr [rax]
0x180017980  test    ecx, ecx
0x180017982  jle     short loc_1800179BA
0x180017984  mov     eax, [r8]
0x180017987  add     [rbx+24h], ecx
0x18001798a  mov     ecx, [rbx+24h]
0x18001798d  cmp     ecx, eax
0x18001798f  jl      short loc_1800179B7
0x180017991  lea     edx, [r10+1]
0x180017995  sub     ecx, eax
0x180017997  mov     [rbx+20h], edx
0x18001799a  cmp     edx, [r9+8]
0x18001799e  jge     loc_180017BB1
0x1800179a4  mov     [rbx+24h], r13d
0x1800179a8  mov     r10d, edx
0x1800179ab  movsxd  rax, dword ptr [r9+10h]
0x1800179af  add     r8, rax
0x1800179b2  jmp     short loc_180017980
0x1800179b4  mov     [rbx+24h], edx
0x1800179b7  mov     ecx, r13d
0x1800179ba  sub     r11d, ecx
0x1800179bd  lea     ecx, [r14+r11]
0x1800179c1  mov     [rbx+28h], ecx
0x1800179c4  sub     ecx, r14d
0x1800179c7  jz      loc_180017A65
0x1800179cd  mov     r10, [rbx+38h]
0x1800179d1  test    r10, r10
0x1800179d4  jz      loc_180017B92
0x1800179da  mov     eax, [r10+8]
0x1800179de  test    eax, eax
0x1800179e0  jz      loc_180017B92
0x1800179e6  mov     edx, ecx
0x1800179e8  test    ecx, ecx
0x1800179ea  js      loc_180017BBD
0x1800179f0  mov     r11d, [rbx+40h]
0x1800179f4  test    eax, eax
0x1800179f6  jle     loc_180017D4A
0x1800179fc  cmp     r11d, eax
0x1800179ff  jge     loc_180017D4A
0x180017a05  mov     r8, [r10]
0x180017a08  test    r8, r8
0x180017a0b  jz      loc_180017D4A
0x180017a11  test    r11d, r11d
0x180017a14  js      loc_180017D4A
0x180017a1a  mov     eax, r11d
0x180017a1d  imul    eax, [r10+10h]
0x180017a22  movsxd  r9, eax
0x180017a25  add     r9, r8
0x180017a28  mov     esi, ecx
0x180017a2a  nop     word ptr [rax+rax+00h]
0x180017a30  test    edx, edx
0x180017a32  jle     short loc_180017A67
0x180017a34  mov     eax, [r9]
0x180017a37  add     [rbx+44h], edx
0x180017a3a  mov     edx, [rbx+44h]
0x180017a3d  cmp     edx, eax
0x180017a3f  jl      short loc_180017A71
0x180017a41  lea     r8d, [r11+1]
0x180017a45  mov     [rbx+40h], r8d
0x180017a49  cmp     r8d, [r10+8]
0x180017a4d  jge     loc_180017BA5
0x180017a53  sub     edx, eax
0x180017a55  mov     [rbx+44h], r13d
0x180017a59  movsxd  rax, dword ptr [r10+10h]
0x180017a5d  mov     r11d, r8d
0x180017a60  add     r9, rax
0x180017a63  jmp     short loc_180017A30
0x180017a65  mov     esi, ecx
0x180017a67  test    esi, esi
0x180017a69  jz      loc_180017AF6
0x180017a6f  mov     ecx, esi
0x180017a71  mov     r9, [rbx+48h]
0x180017a75  test    r9, r9
0x180017a78  jz      short loc_180017AF6
0x180017a7a  mov     eax, [r9+8]
0x180017a7e  test    eax, eax
0x180017a80  jz      short loc_180017AF6
0x180017a82  test    esi, esi
0x180017a84  js      loc_180017C27
0x180017a8a  mov     r10d, [rbx+50h]
0x180017a8e  test    eax, eax
0x180017a90  jle     loc_180017D52
0x180017a96  cmp     r10d, eax
0x180017a99  jge     loc_180017D52
0x180017a9f  mov     rdx, [r9]
0x180017aa2  test    rdx, rdx
0x180017aa5  jz      loc_180017D52
0x180017aab  test    r10d, r10d
0x180017aae  js      loc_180017D52
0x180017ab4  mov     eax, r10d
0x180017ab7  imul    eax, [r9+10h]
0x180017abc  movsxd  r8, eax
0x180017abf  add     r8, rdx
0x180017ac2  test    ecx, ecx
0x180017ac4  jle     short loc_180017AF6
0x180017ac6  mov     eax, [r8]
0x180017ac9  add     [rbx+54h], ecx
0x180017acc  mov     ecx, [rbx+54h]
0x180017acf  cmp     ecx, eax
0x180017ad1  jl      short loc_180017AF6
0x180017ad3  lea     edx, [r10+1]
0x180017ad7  mov     [rbx+50h], edx
0x180017ada  cmp     edx, [r9+8]
0x180017ade  jge     loc_180017B99
0x180017ae4  sub     ecx, eax
0x180017ae6  mov     [rbx+54h], r13d
0x180017aea  movsxd  rax, dword ptr [r9+10h]
0x180017aee  mov     r10d, edx
0x180017af1  add     r8, rax
0x180017af4  jmp     short loc_180017AC2
0x180017af6  mov     rax, [rbx+30h]
0x180017afa  test    dword ptr [rax+0B4h], 80000h
0x180017b04  jnz     loc_180017D7D
0x180017b0a  movzx   r10d, word ptr [rbx+62h]
0x180017b0f  sub     ebp, r15d
0x180017b12  mov     r15, [rsp+78h+var_38]
0x180017b17  mov     [rbx+58h], ebp
0x180017b1a  test    r10b, 2
0x180017b1e  jnz     loc_180017CF3
0x180017b24  cmp     [rbx+28h], r14d
0x180017b28  mov     edx, 40h ; '@'
0x180017b2d  mov     rdi, [rsp+78h+var_28]
0x180017b32  mov     ecx, r13d
0x180017b35  mov     rsi, [rsp+78h+var_20]
0x180017b3a  cmovl   cx, dx
0x180017b3e  mov     rbp, [rsp+78h+arg_0]
0x180017b46  mov     edx, 0FFBFh
0x180017b4b  and     r10w, dx
0x180017b4f  or      cx, r10w
0x180017b53  cmp     r14d, [rbx+28h]
0x180017b57  mov     r14, [rsp+78h+var_30]
0x180017b5c  mov     [rbx+62h], cx
0x180017b60  jz      short loc_180017B87
0x180017b62  test    cl, 2
0x180017b65  jnz     loc_180017ECD
0x180017b6b  mov     edx, 0FFFFFFFFh; int
0x180017b70  mov     rcx, rbx; this
0x180017b73  call    ?Update_iFormat@CTxtRange@@QEAAXJ@Z; CTxtRange::Update_iFormat(long)
0x180017b78  mov     eax, 1
0x180017b7d  add     rsp, 60h
0x180017b81  pop     r13
0x180017b83  pop     r12
0x180017b85  pop     rbx
0x180017b86  retn
0x180017b87  mov     eax, r13d
0x180017b8a  cmp     r12d, [rbx+58h]
0x180017b8e  jz      short loc_180017B7D
0x180017b90  jmp     short loc_180017B62
0x180017b92  mov     esi, ecx
0x180017b94  jmp     loc_180017A71
0x180017b99  mov     [rbx+50h], r10d
0x180017b9d  mov     [rbx+54h], eax
0x180017ba0  jmp     loc_180017AF6
0x180017ba5  mov     [rbx+40h], r11d
0x180017ba9  mov     [rbx+44h], eax
0x180017bac  jmp     loc_180017A71
0x180017bb1  mov     [rbx+20h], r10d
0x180017bb5  mov     [rbx+24h], eax
0x180017bb8  jmp     loc_1800179BA
0x180017bbd  mov     esi, ecx
0x180017bbf  nop
0x180017bc0  test    edx, edx
0x180017bc2  jns     loc_180017A71
0x180017bc8  mov     r8d, [rbx+44h]
0x180017bcc  mov     eax, edx
0x180017bce  neg     eax
0x180017bd0  cmp     eax, r8d
0x180017bd3  jle     loc_180017C85
0x180017bd9  mov     eax, [rbx+40h]
0x180017bdc  test    eax, eax
0x180017bde  jle     loc_180017D6B
0x180017be4  add     edx, r8d
0x180017be7  dec     eax
0x180017be9  mov     [rbx+40h], eax
0x180017bec  mov     r8d, [r10+8]
0x180017bf0  test    r8d, r8d
0x180017bf3  jle     loc_180017D25
0x180017bf9  cmp     eax, r8d
0x180017bfc  jge     loc_180017D25
0x180017c02  mov     r8, [r10]
0x180017c05  test    r8, r8
0x180017c08  jz      loc_180017D25
0x180017c0e  test    eax, eax
0x180017c10  js      loc_180017D25
0x180017c16  imul    eax, [r10+10h]
0x180017c1b  cdqe
0x180017c1d  add     rax, r8
0x180017c20  mov     eax, [rax]
0x180017c22  mov     [rbx+44h], eax
0x180017c25  jmp     short loc_180017BC0
0x180017c27  test    ecx, ecx
0x180017c29  jns     loc_180017AF6
0x180017c2f  mov     edx, [rbx+54h]
0x180017c32  mov     eax, ecx
0x180017c34  neg     eax
0x180017c36  cmp     eax, edx
0x180017c38  jle     short loc_180017C91
0x180017c3a  mov     eax, [rbx+50h]
0x180017c3d  test    eax, eax
0x180017c3f  jle     loc_180017D74
0x180017c45  add     ecx, edx
0x180017c47  dec     eax
0x180017c49  mov     [rbx+50h], eax
0x180017c4c  mov     edx, [r9+8]
0x180017c50  test    edx, edx
0x180017c52  jle     loc_180017D2D
0x180017c58  cmp     eax, edx
0x180017c5a  jge     loc_180017D2D
0x180017c60  mov     rdx, [r9]
0x180017c63  test    rdx, rdx
0x180017c66  jz      loc_180017D2D
0x180017c6c  test    eax, eax
0x180017c6e  js      loc_180017D2D
0x180017c74  imul    eax, [r9+10h]
0x180017c79  cdqe
0x180017c7b  add     rax, rdx
0x180017c7e  mov     eax, [rax]
0x180017c80  mov     [rbx+54h], eax
0x180017c83  jmp     short loc_180017C27
  ... truncated ...
```
