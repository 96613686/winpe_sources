# RtlpConvertAclToAutoInherit

- ea: `0x180123664`
- end: `0x180123e7f`
- name: `RtlpConvertAclToAutoInherit`
- size: `2075`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18013d0dc`

## callees

- `0x180015b30`
- `0x18001861c`
- `0x18001b984`
- `0x180039da0`
- `0x18003c6a0`
- `0x18004d900`
- `0x1800c8080`
- `0x180123664`
- `0x180162810`
- `0x180164280`

## pseudocode

```c
__int64 __fastcall RtlpConvertAclToAutoInherit(
        __int64 a1,
        unsigned __int16 *a2,
        __int64 a3,
        char a4,
        __int64 a5,
        __int64 a6,
        _DWORD *a7,
        __int64 *a8,
        _DWORD *a9)
{
  unsigned __int16 *v9; // r13
  _DWORD *v10; // r14
  __int64 *v11; // rsi
  _DWORD *v12; // rdi
  unsigned __int8 *v13; // r15
  void *ProcessHeap; // r12
  int v15; // ebx
  __int64 v16; // rbx
  int v17; // r9d
  __int64 v18; // r12
  __int64 v19; // r11
  int v20; // ebx
  unsigned __int16 *v21; // r10
  int v22; // ecx
  int v23; // r9d
  char v24; // r8
  __int64 v25; // rdx
  char v26; // al
  int v27; // ecx
  int v28; // ecx
  int v29; // eax
  __int64 v30; // rax
  int v31; // r10d
  unsigned __int16 *v32; // r9
  __int64 v33; // rsi
  int v34; // eax
  int v35; // ecx
  int v36; // ecx
  int v37; // eax
  char v38; // dl
  int v39; // r13d
  unsigned __int16 *v40; // r15
  int v41; // r8d
  int v42; // r12d
  int v43; // ebx
  unsigned __int16 *v44; // r14
  int v45; // edi
  __int64 v46; // r11
  __int64 v47; // rcx
  char v48; // dl
  unsigned __int8 *v49; // r9
  char v50; // r11
  int v51; // esi
  int i; // r10d
  char v53; // r8
  unsigned __int16 *v54; // rcx
  int v55; // eax
  __int64 v56; // r8
  __int64 v57; // rax
  __int64 *v58; // rbx
  __int64 v59; // r9
  unsigned __int8 v60; // al
  int v61; // r12d
  _BYTE *v62; // rsi
  __int64 v63; // rdi
  unsigned __int16 *v64; // r9
  unsigned __int16 *v65; // r15
  int v66; // ebx
  _BYTE *v67; // r8
  int v68; // ecx
  int j; // edx
  int v70; // eax
  int v71; // eax
  int v72; // eax
  void *Heap_0; // rax
  __int64 v74; // r8
  char v76; // [rsp+90h] [rbp-80h] BYREF
  char v77; // [rsp+91h] [rbp-7Fh]
  int v78; // [rsp+94h] [rbp-7Ch] BYREF
  __int16 v79; // [rsp+98h] [rbp-78h]
  __int64 *v80; // [rsp+A0h] [rbp-70h]
  int v81; // [rsp+A8h] [rbp-68h]
  __int64 v82; // [rsp+B0h] [rbp-60h]
  unsigned __int16 *v83; // [rsp+B8h] [rbp-58h]
  char *v84; // [rsp+C0h] [rbp-50h]
  __int64 v85; // [rsp+C8h] [rbp-48h] BYREF
  int v86; // [rsp+D0h] [rbp-40h]
  int v87; // [rsp+D4h] [rbp-3Ch] BYREF
  void *v88; // [rsp+D8h] [rbp-38h]
  __int64 v89; // [rsp+E0h] [rbp-30h] BYREF
  int v90; // [rsp+E8h] [rbp-28h]
  int v91; // [rsp+ECh] [rbp-24h]
  unsigned __int16 *v92; // [rsp+F0h] [rbp-20h]
  char *v93; // [rsp+F8h] [rbp-18h] BYREF
  __int64 v94; // [rsp+100h] [rbp-10h]
  __int64 v95; // [rsp+108h] [rbp-8h]
  __int64 v96; // [rsp+110h] [rbp+0h]
  _DWORD *v97; // [rsp+118h] [rbp+8h]
  _DWORD *v98; // [rsp+120h] [rbp+10h]
  int v99; // [rsp+128h] [rbp+18h] BYREF
  __int64 v100; // [rsp+12Ch] [rbp+1Ch]
  char v101[8]; // [rsp+158h] [rbp+48h] BYREF
  int v102; // [rsp+160h] [rbp+50h]

  v9 = a2;
  v10 = a7;
  v11 = a8;
  v12 = a9;
  v89 = a3;
  v95 = a5;
  v96 = a1;
  v94 = a6;
  v13 = 0;
  v83 = a2;
  v85 = 0;
  v84 = 0;
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  v93 = 0;
  v76 = 0;
  v87 = 0;
  v78 = 0;
  v88 = ProcessHeap;
  v77 = a4;
  v98 = a7;
  v80 = a8;
  v97 = a9;
  v79 = 768;
  v99 = 257;
  v100 = 50331648;
  v15 = RtlInitializeSid(v101, &v78, 1);
  if ( v15 < 0 )
    return (unsigned int)v15;
  v16 = v96;
  *a9 = 1024;
  v102 = 1;
  *a8 = 0;
  if ( v16 && !(unsigned __int8)RtlValidAcl(v16) || !(unsigned __int8)RtlValidAcl(v9) )
    return (unsigned int)-1073741705;
  LOBYTE(v17) = v77;
  v15 = RtlpInheritAcl(
          v16,
          0,
          0,
          v17,
          1,
          0,
          (__int64)&v99,
          (__int64)v101,
          (__int64)&v99,
          (__int64)v101,
          (__int64)a7,
          2,
          (unsigned __int64)&v89 & -(__int64)(v89 != 0),
          v89 != 0,
          (__int64)&v85,
          (__int64)&v76,
          (__int64)&v87);
  if ( v15 == -2147483637 )
  {
    v18 = 0;
    *a9 |= 0x1000u;
LABEL_99:
    v15 = 0;
    if ( (*v12 & 0x1000) != 0 )
    {
      if ( *v11 )
      {
        RtlFreeHeap_0(v88, 0, *v11);
        *v11 = 0;
      }
      Heap_0 = (void *)RtlAllocateHeap_0(v88, (unsigned int)(NtdllBaseTag + 1310720), v9[1]);
      *v11 = (__int64)Heap_0;
      if ( Heap_0 )
        memmove(Heap_0, v9, v9[1]);
      else
        v15 = -1073741801;
    }
    if ( !v18 )
    {
      ProcessHeap = v88;
      goto LABEL_108;
    }
    goto LABEL_106;
  }
  if ( v15 >= 0 )
  {
    v82 = RtlAllocateHeap_0(ProcessHeap, (unsigned int)(NtdllBaseTag + 1310720), 24LL * v9[2]);
    v19 = v82;
    if ( v82 )
    {
      v20 = 0;
      v92 = v9 + 4;
      v21 = v9 + 4;
      while ( v20 < v9[2] )
      {
        if ( *(_BYTE *)v21 > 8u || *(_BYTE *)v21 == 4 )
        {
          *a9 |= 0x1000u;
          v18 = v19;
          goto LABEL_99;
        }
        v22 = *((_DWORD *)v21 + 1);
        if ( v22 < 0 )
          v22 |= *a7;
        if ( (v22 & 0x40000000) != 0 )
          v22 |= a7[1];
        if ( (v22 & 0x20000000) != 0 )
          v22 |= a7[2];
        if ( (v22 & 0x10000000) != 0 )
          v22 |= a7[3];
        if ( (unsigned __int8)(*(_BYTE *)v21 - 2) <= 2u || *(_BYTE *)v21 >= 7u )
          v23 = v22 & (a7[3] & 0xEFFFFFF | 0x1000000);
        else
          v23 = v22 & a7[3] & 0xFFFFFFF;
        v24 = *((_BYTE *)v21 + 1) & 3 | ~*((_BYTE *)v21 + 1) & 8;
        v25 = 3LL * v20;
        v26 = *((_BYTE *)v21 + 1) & 1;
        v27 = (*((_BYTE *)v21 + 1) & 2) != 0 ? v23 : 0;
        *(_DWORD *)(v19 + 8 * v25) = v27;
        *(_DWORD *)(v19 + 8 * v25 + 12) = v27;
        v28 = v26 != 0 ? v23 : 0;
        *(_DWORD *)(v19 + 8 * v25 + 4) = v28;
        *(_DWORD *)(v19 + 8 * v25 + 16) = v28;
        ++v20;
        v29 = (v24 & 8) != 0 ? v23 : 0;
        *(_DWORD *)(v19 + 8 * v25 + 8) = v29;
        *(_DWORD *)(v19 + 8 * v25 + 20) = v29;
        v21 = (unsigned __int16 *)((char *)v21 + v21[1]);
      }
      v30 = v85;
      v31 = 0;
      v32 = v9;
      v33 = v85 + 8;
      while ( 1 )
      {
        v34 = *(unsigned __int16 *)(v30 + 4);
        v86 = v31;
        if ( v31 >= v34 )
          break;
        if ( *(_BYTE *)v33 > 8u || *(_BYTE *)v33 == 4 )
          goto LABEL_55;
        v35 = *(_DWORD *)(v33 + 4);
        if ( v35 < 0 )
          v35 |= *v10;
        if ( (v35 & 0x40000000) != 0 )
          v35 |= v10[1];
        if ( (v35 & 0x20000000) != 0 )
          v35 |= v10[2];
        if ( (v35 & 0x10000000) != 0 )
          v35 |= v10[3];
        v36 = (unsigned __int8)(*(_BYTE *)v33 - 2) <= 2u || *(_BYTE *)v33 >= 7u
            ? (v10[3] & 0xEFFFFFF | 0x1000000) & v35
            : v10[3] & v35 & 0xFFFFFFF;
        if ( v36 )
        {
          v37 = *(_BYTE *)(v33 + 1) & 3;
          v38 = v37 | ~*(_BYTE *)(v33 + 1) & 8;
          if ( v37 | ~*(_BYTE *)(v33 + 1) & 8 )
          {
            v39 = (*(_BYTE *)(v33 + 1) & 2) != 0 ? v36 : 0;
            v40 = v32 + 4;
            v91 = v39;
            v41 = (v38 & 1) != 0 ? v36 : 0;
            v78 = v41;
            v42 = 0;
            v43 = (v38 & 8) != 0 ? v36 : 0;
            v90 = v43;
            if ( v32[2] )
            {
              v44 = v83;
              v45 = (v38 & 1) != 0 ? v36 : 0;
              do
              {
                if ( (unsigned __int8)RtlpCompareAces(v33, v40, v95, v94) )
                {
                  v46 = v82;
                  v47 = 3LL * v42;
                  v43 &= ~*(_DWORD *)(v82 + 24LL * v42 + 8);
                  v39 &= ~*(_DWORD *)(v82 + 24LL * v42);
                  v45 &= ~*(_DWORD *)(v82 + 24LL * v42 + 4);
                  *(_DWORD *)(v82 + 8 * v47 + 20) &= ~v90;
                  *(_DWORD *)(v46 + 8 * v47 + 12) &= ~v91;
                  *(_DWORD *)(v46 + 8 * v47 + 16) &= ~v78;
                }
                ++v42;
                v40 = (unsigned __int16 *)((char *)v40 + v40[1]);
              }
              while ( v42 < v44[2] );
              v10 = v98;
              v32 = v83;
              v31 = v86;
              v81 = v45;
              v41 = v45;
              v12 = v97;
            }
            if ( v39 | v41 | v43 )
            {
LABEL_55:
              *v12 |= 0x1000u;
              v9 = v83;
              v13 = (unsigned __int8 *)v84;
              v11 = v80;
LABEL_98:
              v18 = v82;
              goto LABEL_99;
            }
          }
        }
        ++v31;
        v33 += *(unsigned __int16 *)(v33 + 2);
        v30 = v85;
      }
      v9 = v83;
      v48 = 0;
      v49 = (unsigned __int8 *)v92;
      v50 = 0;
      v18 = v82;
      v51 = 0;
      for ( i = 0; i < v83[2]; ++i )
      {
        v53 = *((_BYTE *)RtlBaseAceType + *v49);
        if ( *(_DWORD *)(v82 + 24LL * i + 12) | *(_DWORD *)(v82 + 24LL * i + 16) | *(_DWORD *)(v82 + 24LL * i + 20) )
        {
          if ( !v53 && v50
            || (v54 = (unsigned __int16 *)(v49 + 2), v51 += *((unsigned __int16 *)v49 + 1), v53 == 1) && v48 )
          {
            v13 = (unsigned __int8 *)v84;
LABEL_70:
            *v12 |= 0x1000u;
            v11 = v80;
            goto LABEL_99;
          }
        }
        else
        {
          if ( v53 )
          {
            if ( v53 == 1 )
              v50 = 1;
          }
          else
          {
            v48 = 1;
          }
          v54 = (unsigned __int16 *)(v49 + 2);
        }
        v49 += *v54;
      }
      LOBYTE(v49) = v77;
      v55 = RtlpInheritAcl(
              v96,
              0,
              0,
              (_DWORD)v49,
              1,
              0,
              v95,
              v94,
              v95,
              v94,
              (__int64)v10,
              2,
              (unsigned __int64)&v89 & -(__int64)(v89 != 0),
              v89 != 0,
              (__int64)&v93,
              (__int64)&v76,
              (__int64)&v87);
      v13 = (unsigned __int8 *)v93;
      v15 = v55;
      if ( v55 >= 0 )
      {
        v56 = v51 + (unsigned int)*((unsigned __int16 *)v93 + 1);
        v84 = v93;
        v57 = RtlAllocateHeap_0(v88, (unsigned int)(NtdllBaseTag + 1310720), v56);
        v58 = v80;
        v59 = v57;
        *v80 = v57;
        if ( !v57 )
        {
          v15 = -1073741801;
          goto LABEL_106;
        }
        v60 = *v13;
        if ( *v13 <= *(_BYTE *)v9 )
          v60 = *(_BYTE *)v9;
        if ( (int)RtlCreateAcl(v59, v51 + (unsigned int)*((unsigned __int16 *)v13 + 1), v60) < 0 )
          goto LABEL_70;
        v61 = 0;
        v62 = (_BYTE *)(*v58 + 8);
        if ( v9[2] )
        {
          v63 = v82;
          v64 = v9 + 4;
          do
          {
            v65 = v64 + 1;
            v66 = *(_DWORD *)(v63 + 24LL * v61 + 12)
                | *(_DWORD *)(v63 + 24LL * v61 + 16)
                | *(_DWORD *)(v63 + 24LL * v61 + 20);
            if ( v66 )
            {
              memmove(v62, v64, *v65);
              v62[1] &= ~0x10u;
              v67 = v62;
              v64 = v92;
              v62 += *v65;
              ++*(_WORD *)(*v80 + 4);
              v68 = 0x80000000;
              *((_DWORD *)v67 + 1) = *((_DWORD *)v64 + 1) & v66;
              for ( j = v66 & ~*((_DWORD *)v64 + 1); j; v68 = (unsigned int)v68 >> 1 )
              {
                if ( (unsigned int)v68 < 0x10000000 )
                  break;
                if ( (v68 & *((_DWORD *)v64 + 1)) != 0 )
                {
                  v70 = v68;
                  if ( v68 < 0 )
                    v70 = *v10 | v68;
                  if ( (v70 & 0x40000000) != 0 )
                    v70 |= v10[1];
                  if ( (v70 & 0x20000000) != 0 )
                    v70 |= v10[2];
                  if ( (v70 & 0x10000000) != 0 )
                    v70 |= v10[3];
                  v71 = v70 & 0xFFFFFFF;
                  if ( (v71 & j) != 0 )
                  {
                    *((_DWORD *)v67 + 1) |= v68;
                    j &= ~v71;
                  }
                }
              }
              *((_DWORD *)v67 + 1) |= j;
            }
            ++v61;
            v64 = (unsigned __int16 *)((char *)v64 + *v65);
            v72 = v9[2];
            v92 = v64;
          }
          while ( v61 < v72 );
          v12 = v97;
          v13 = (unsigned __int8 *)v84;
        }
        memmove(v62, v13 + 8, (unsigned int)*((unsigned __int16 *)v13 + 1) - 8);
        v11 = v80;
        *(_WORD *)(*v80 + 4) += *((_WORD *)v13 + 2);
        goto LABEL_98;
      }
LABEL_106:
      v74 = v18;
      ProcessHeap = v88;
      RtlFreeHeap_0(v88, 0, v74);
      goto LABEL_108;
    }
    v15 = -1073741801;
  }
LABEL_108:
  if ( v85 )
    RtlFreeHeap_0(ProcessHeap, 0, v85);
  if ( v13 )
    RtlFreeHeap_0(ProcessHeap, 0, v13);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180123664  mov     [rsp-8+arg_18], rbx
0x180123669  push    rbp
0x18012366a  push    rsi
0x18012366b  push    rdi
0x18012366c  push    r12
0x18012366e  push    r13
0x180123670  push    r14
0x180123672  push    r15
0x180123674  lea     rbp, [rsp-80h]
0x180123679  sub     rsp, 190h
0x180123680  mov     rax, cs:__security_cookie
0x180123687  xor     rax, rsp
0x18012368a  mov     [rbp+0B0h+var_38], rax
0x18012368e  mov     rax, [rbp+0B0h+arg_20]
0x180123695  mov     r13, rdx
0x180123698  mov     r14, [rbp+0B0h+arg_30]
0x18012369f  mov     rsi, [rbp+0B0h+arg_38]
0x1801236a6  mov     rdi, [rbp+0B0h+arg_40]
0x1801236ad  mov     [rbp+0B0h+var_E0], r8
0x1801236b1  mov     [rbp+0B0h+var_B8], rax
0x1801236b5  mov     rax, [rbp+0B0h+arg_28]
0x1801236bc  mov     [rbp+0B0h+var_B0], rcx
0x1801236c0  xor     ecx, ecx
0x1801236c2  mov     [rbp+0B0h+var_C0], rax
0x1801236c6  mov     r15d, ecx
0x1801236c9  mov     rax, gs:60h
0x1801236d2  mov     [rbp+0B0h+var_108], rdx
0x1801236d6  lea     rdx, [rbp+0B0h+var_12C]
0x1801236da  mov     [rbp+0B0h+var_F8], rcx
0x1801236de  lea     r8d, [rcx+1]
0x1801236e2  mov     [rbp+0B0h+var_100], rcx
0x1801236e6  mov     r12, [rax+30h]
0x1801236ea  mov     [rbp+0B0h+var_C8], rcx
0x1801236ee  mov     [rbp+0B0h+var_130], cl
0x1801236f1  mov     [rbp+0B0h+var_EC], ecx
0x1801236f4  mov     [rbp+0B0h+var_12C], ecx
0x1801236f7  lea     rcx, [rbp+0B0h+var_68]
0x1801236fb  mov     [rbp+0B0h+var_E8], r12
0x1801236ff  mov     [rbp+0B0h+var_12F], r9b
0x180123703  mov     [rbp+0B0h+var_A0], r14
0x180123707  mov     [rbp+0B0h+var_120], rsi
0x18012370b  mov     [rbp+0B0h+var_A8], rdi
0x18012370f  mov     [rbp+0B0h+var_128], 300h
0x180123715  mov     [rbp+0B0h+var_98], 101h
0x18012371c  mov     [rbp+0B0h+var_94], 3000000h
0x180123724  call    RtlInitializeSid
0x180123729  mov     ebx, eax
0x18012372b  test    eax, eax
0x18012372d  js      loc_180123E55
0x180123733  mov     rbx, [rbp+0B0h+var_B0]
0x180123737  lea     ecx, [r15+1]
0x18012373b  mov     dword ptr [rdi], 400h
0x180123741  mov     [rbp+0B0h+var_60], ecx
0x180123744  mov     [rsi], r15
0x180123747  test    rbx, rbx
0x18012374a  jz      short loc_180123762
0x18012374c  mov     rcx, rbx
0x18012374f  call    RtlValidAcl
0x180123754  test    al, al
0x180123756  jnz     short loc_180123762
0x180123758  mov     ebx, 0C0000077h
0x18012375d  jmp     loc_180123E55
0x180123762  mov     rcx, r13
0x180123765  call    RtlValidAcl
0x18012376a  test    al, al
0x18012376c  jz      short loc_180123758
0x18012376e  mov     rax, [rbp+0B0h+var_E0]
0x180123772  xor     edx, edx
0x180123774  mov     r9b, [rbp+0B0h+var_12F]
0x180123778  test    rax, rax
0x18012377b  setnz   dl
0x18012377e  neg     rax
0x180123781  lea     rax, [rbp+0B0h+var_E0]
0x180123785  sbb     rcx, rcx
0x180123788  xor     r8d, r8d
0x18012378b  and     rcx, rax
0x18012378e  lea     rax, [rbp+0B0h+var_EC]
0x180123792  mov     [rsp+1C0h+var_140], rax
0x18012379a  lea     rax, [rbp+0B0h+var_130]
0x18012379e  mov     [rsp+1C0h+var_148], rax
0x1801237a3  lea     rax, [rbp+0B0h+var_F8]
0x1801237a7  mov     [rsp+1C0h+var_150], rax
0x1801237ac  lea     rax, [rbp+0B0h+var_68]
0x1801237b0  mov     [rsp+1C0h+var_158], edx
0x1801237b4  xor     edx, edx
0x1801237b6  mov     [rsp+1C0h+var_160], rcx
0x1801237bb  mov     rcx, rbx
0x1801237be  mov     [rsp+1C0h+var_168], 2
0x1801237c6  mov     [rsp+1C0h+var_170], r14
0x1801237cb  mov     [rsp+1C0h+var_178], rax
0x1801237d0  lea     rax, [rbp+0B0h+var_98]
0x1801237d4  mov     [rsp+1C0h+var_180], rax
0x1801237d9  lea     rax, [rbp+0B0h+var_68]
0x1801237dd  mov     [rsp+1C0h+var_188], rax
0x1801237e2  lea     rax, [rbp+0B0h+var_98]
0x1801237e6  mov     [rsp+1C0h+var_190], rax
0x1801237eb  mov     [rsp+1C0h+var_198], r15b
0x1801237f0  mov     [rsp+1C0h+var_1A0], 1
0x1801237f5  call    RtlpInheritAcl
0x1801237fa  mov     ebx, eax
0x1801237fc  mov     rax, [rbp+0B0h+var_F8]
0x180123800  mov     [rbp+0B0h+var_F8], rax
0x180123804  cmp     ebx, 8000000Bh
0x18012380a  jnz     short loc_180123818
0x18012380c  xor     r12d, r12d
0x18012380f  bts     dword ptr [rdi], 0Ch
0x180123813  jmp     loc_180123DB8
0x180123818  test    ebx, ebx
0x18012381a  js      loc_180123E2D
0x180123820  movzx   eax, word ptr [r13+4]
0x180123825  mov     rcx, r12
0x180123828  mov     edx, cs:NtdllBaseTag
0x18012382e  add     edx, 140000h
0x180123834  lea     r8, [rax+rax*2]
0x180123838  shl     r8, 3
0x18012383c  call    RtlAllocateHeap_0
0x180123841  mov     [rbp+0B0h+var_110], rax
0x180123845  mov     r11, rax
0x180123848  test    rax, rax
0x18012384b  jnz     short loc_180123857
0x18012384d  mov     ebx, 0C0000017h
0x180123852  jmp     loc_180123E2D
0x180123857  lea     rcx, [r13+8]
0x18012385b  xor     ebx, ebx
0x18012385d  mov     [rbp+0B0h+var_D0], rcx
0x180123861  mov     r10, rcx
0x180123864  lea     r12d, [rbx+1]
0x180123868  movzx   eax, word ptr [r13+4]
0x18012386d  cmp     ebx, eax
0x18012386f  jge     loc_18012395E
0x180123875  cmp     byte ptr [r10], 8
0x180123879  ja      loc_180123952
0x18012387f  cmp     byte ptr [r10], 4
0x180123883  jz      loc_180123952
0x180123889  mov     ecx, [r10+4]
0x18012388d  test    ecx, ecx
0x18012388f  jns     short loc_180123894
0x180123891  or      ecx, [r14]
0x180123894  bt      ecx, 1Eh
0x180123898  jnb     short loc_18012389E
0x18012389a  or      ecx, [r14+4]
0x18012389e  bt      ecx, 1Dh
0x1801238a2  jnb     short loc_1801238A8
0x1801238a4  or      ecx, [r14+8]
0x1801238a8  bt      ecx, 1Ch
0x1801238ac  jnb     short loc_1801238B2
0x1801238ae  or      ecx, [r14+0Ch]
0x1801238b2  mov     al, [r10]
0x1801238b5  sub     al, 2
0x1801238b7  cmp     al, 2
0x1801238b9  jbe     short loc_1801238D1
0x1801238bb  cmp     byte ptr [r10], 7
0x1801238bf  jnb     short loc_1801238D1
0x1801238c1  mov     r9d, [r14+0Ch]
0x1801238c5  and     r9d, ecx
0x1801238c8  and     r9d, 0FFFFFFFh
0x1801238cf  jmp     short loc_1801238E4
0x1801238d1  mov     r9d, [r14+0Ch]
0x1801238d5  and     r9d, 0EFFFFFFh
0x1801238dc  bts     r9d, 18h
0x1801238e1  and     r9d, ecx
0x1801238e4  movzx   eax, byte ptr [r10+1]
0x1801238e9  mov     r8d, eax
0x1801238ec  and     eax, 3
0x1801238ef  not     r8d
0x1801238f2  and     r8d, 8
0x1801238f6  or      r8d, eax
0x1801238f9  movsxd  rax, ebx
0x1801238fc  lea     rdx, [rax+rax*2]
0x180123900  mov     eax, r8d
0x180123903  and     al, 2
0x180123905  neg     al
0x180123907  mov     al, r8b
0x18012390a  sbb     ecx, ecx
0x18012390c  and     al, r12b
0x18012390f  and     ecx, r9d
0x180123912  mov     [r11+rdx*8], ecx
0x180123916  neg     al
0x180123918  mov     [r11+rdx*8+0Ch], ecx
0x18012391d  sbb     ecx, ecx
0x18012391f  and     r8b, 8
0x180123923  and     ecx, r9d
0x180123926  mov     [r11+rdx*8+4], ecx
0x18012392b  neg     r8b
0x18012392e  mov     [r11+rdx*8+10h], ecx
0x180123933  sbb     eax, eax
0x180123935  add     ebx, r12d
0x180123938  and     eax, r9d
0x18012393b  mov     [r11+rdx*8+8], eax
0x180123940  mov     [r11+rdx*8+14h], eax
0x180123945  movzx   eax, word ptr [r10+2]
0x18012394a  add     r10, rax
0x18012394d  jmp     loc_180123868
0x180123952  bts     dword ptr [rdi], 0Ch
0x180123956  mov     r12, r11
0x180123959  jmp     loc_180123DB8
0x18012395e  mov     rax, [rbp+0B0h+var_F8]
0x180123962  xor     r10d, r10d
0x180123965  mov     r9, r13
0x180123968  mov     r15d, r12d
0x18012396b  lea     rsi, [rax+8]
0x18012396f  movzx   eax, word ptr [rax+4]
0x180123973  mov     [rbp+0B0h+var_F0], r10d
0x180123977  cmp     r10d, eax
0x18012397a  jge     loc_180123B03
0x180123980  cmp     byte ptr [rsi], 8
0x180123983  ja      loc_180123AEE
0x180123989  cmp     byte ptr [rsi], 4
0x18012398c  jz      loc_180123AEE
0x180123992  mov     ecx, [rsi+4]
0x180123995  test    ecx, ecx
0x180123997  jns     short loc_18012399C
0x180123999  or      ecx, [r14]
0x18012399c  bt      ecx, 1Eh
0x1801239a0  jnb     short loc_1801239A6
0x1801239a2  or      ecx, [r14+4]
0x1801239a6  bt      ecx, 1Dh
0x1801239aa  jnb     short loc_1801239B0
0x1801239ac  or      ecx, [r14+8]
0x1801239b0  bt      ecx, 1Ch
0x1801239b4  jnb     short loc_1801239BA
0x1801239b6  or      ecx, [r14+0Ch]
0x1801239ba  mov     al, [rsi]
0x1801239bc  sub     al, 2
0x1801239be  cmp     al, 2
0x1801239c0  jbe     short loc_1801239D3
0x1801239c2  cmp     byte ptr [rsi], 7
0x1801239c5  jnb     short loc_1801239D3
0x1801239c7  and     ecx, [r14+0Ch]
0x1801239cb  and     ecx, 0FFFFFFFh
0x1801239d1  jmp     short loc_1801239E2
0x1801239d3  mov     eax, [r14+0Ch]
0x1801239d7  and     eax, 0EFFFFFFh
0x1801239dc  bts     eax, 18h
0x1801239e0  and     ecx, eax
0x1801239e2  test    ecx, ecx
0x1801239e4  jz      loc_180123ADB
0x1801239ea  movzx   eax, byte ptr [rsi+1]
0x1801239ee  mov     edx, eax
0x1801239f0  and     eax, 3
0x1801239f3  not     edx
0x1801239f5  and     edx, 8
0x1801239f8  or      edx, eax
0x1801239fa  jz      loc_180123ADB
0x180123a00  mov     al, dl
0x180123a02  and     al, 2
0x180123a04  neg     al
0x180123a06  mov     al, dl
0x180123a08  sbb     r13d, r13d
0x180123a0b  and     al, r15b
0x180123a0e  and     r13d, ecx
0x180123a11  lea     r15, [r9+8]
0x180123a15  neg     al
0x180123a17  mov     [rbp+0B0h+var_D4], r13d
0x180123a1b  sbb     r8d, r8d
0x180123a1e  and     dl, 8
0x180123a21  and     r8d, ecx
0x180123a24  neg     dl
0x180123a26  mov     [rbp+0B0h+var_12C], r8d
0x180123a2a  sbb     ebx, ebx
0x180123a2c  xor     r12d, r12d
0x180123a2f  and     ebx, ecx
0x180123a31  xor     eax, eax
0x180123a33  mov     [rbp+0B0h+var_D8], ebx
0x180123a36  cmp     ax, [r9+4]
0x180123a3b  jnb     loc_180123ACF
0x180123a41  mov     r14, [rbp+0B0h+var_108]
0x180123a45  mov     edi, r8d
0x180123a48  mov     r9, [rbp+0B0h+var_C0]
0x180123a4c  mov     rdx, r15
0x180123a4f  mov     r8, [rbp+0B0h+var_B8]
0x180123a53  mov     rcx, rsi
0x180123a56  call    RtlpCompareAces
0x180123a5b  test    al, al
0x180123a5d  jz      short loc_180123AA3
0x180123a5f  mov     r11, [rbp+0B0h+var_110]
0x180123a63  movsxd  rax, r12d
0x180123a66  lea     rcx, [rax+rax*2]
0x180123a6a  mov     eax, [r11+rcx*8+8]
0x180123a6f  not     eax
0x180123a71  and     ebx, eax
0x180123a73  mov     eax, [r11+rcx*8]
0x180123a77  not     eax
0x180123a79  and     r13d, eax
0x180123a7c  mov     eax, [r11+rcx*8+4]
0x180123a81  not     eax
0x180123a83  and     edi, eax
0x180123a85  mov     eax, [rbp+0B0h+var_D8]
0x180123a88  not     eax
0x180123a8a  and     [r11+rcx*8+14h], eax
0x180123a8f  mov     eax, [rbp+0B0h+var_D4]
0x180123a92  not     eax
0x180123a94  and     [r11+rcx*8+0Ch], eax
0x180123a99  mov     eax, [rbp+0B0h+var_12C]
0x180123a9c  not     eax
0x180123a9e  and     [r11+rcx*8+10h], eax
0x180123aa3  movzx   eax, word ptr [r15+2]
0x180123aa8  inc     r12d
0x180123aab  add     r15, rax
0x180123aae  movzx   eax, word ptr [r14+4]
  ... truncated ...
```
