# RtlCompressBufferXpressHuffStandard

- ea: `0x1800b5e50`
- end: `0x1800b66b3`
- name: `RtlCompressBufferXpressHuffStandard`
- size: `2147`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800b4da0`

## callees

- `0x1800b5e50`
- `0x1800b66c0`
- `0x1800b6710`
- `0x1800b6c50`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall RtlCompressBufferXpressHuffStandard(
        unsigned __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        _DWORD *a5,
        _DWORD *a6)
{
  unsigned __int8 *v6; // r13
  unsigned __int64 v8; // rbx
  unsigned __int8 *v9; // rdi
  void *v10; // rax
  unsigned __int8 *v11; // r14
  __int64 v12; // r15
  __int64 v13; // rsi
  unsigned __int8 *v14; // rcx
  unsigned __int64 XpressCallback; // r8
  int *v16; // rbx
  unsigned __int64 v17; // rbp
  int v18; // r13d
  unsigned __int8 v19; // al
  unsigned __int8 v20; // al
  int v21; // ebx
  __int64 v22; // rax
  int v23; // r14d
  bool v24; // zf
  unsigned __int8 *v26; // r10
  unsigned __int8 *v27; // r11
  __int64 v28; // rdx
  __int64 v29; // rcx
  unsigned __int8 *v30; // r9
  __int64 v31; // rcx
  __int64 v32; // rbx
  __int64 v33; // r8
  __int64 v34; // rbx
  __int64 v35; // rsi
  __int64 v36; // rbp
  __int64 v37; // r14
  _BYTE *i; // r9
  int v39; // ecx
  int v40; // eax
  unsigned __int64 v41; // rdx
  __int64 v42; // rcx
  unsigned __int64 v43; // rdx
  char v44; // cl
  unsigned __int64 v45; // r8
  _WORD *v46; // r9
  unsigned __int8 v47; // cl
  int v48; // eax
  unsigned __int8 *v49; // r8
  __int64 v50; // rdx
  unsigned __int8 *v51; // rcx
  unsigned __int64 v52; // rax
  __int64 v53; // rdx
  unsigned __int8 *v54; // rcx
  __int64 v55; // rax
  unsigned __int64 v56; // r8
  unsigned __int8 *v57; // rcx
  __int64 v58; // rax
  int *v59; // rcx
  __int64 v60; // rax
  unsigned __int64 v61; // [rsp+30h] [rbp-A8h]
  __int64 v62; // [rsp+38h] [rbp-A0h]
  __int64 v63; // [rsp+40h] [rbp-98h]
  unsigned __int64 v64; // [rsp+48h] [rbp-90h]
  __int64 v65; // [rsp+50h] [rbp-88h]
  __int64 v66; // [rsp+58h] [rbp-80h]
  unsigned __int8 *v67; // [rsp+70h] [rbp-68h]
  unsigned __int64 v68; // [rsp+78h] [rbp-60h]
  _QWORD v69[2]; // [rsp+80h] [rbp-58h] BYREF
  unsigned int v70; // [rsp+90h] [rbp-48h]
  int v71; // [rsp+94h] [rbp-44h]
  int v73; // [rsp+F0h] [rbp+18h]
  unsigned __int8 *v74; // [rsp+108h] [rbp+30h]
  int *v76; // [rsp+110h] [rbp+38h]
  unsigned __int64 v78; // [rsp+118h] [rbp+40h]

  v73 = a3;
  v6 = (unsigned __int8 *)a1;
  v71 = 0;
  if ( a4 < 0x12C )
    return 3221225507LL;
  v66 = a2;
  v65 = a3;
  v69[0] = 0;
  v8 = a2 + a1;
  v69[1] = 0;
  v64 = v8;
  v68 = a3 + a4;
  v70 = a2;
  memset64(a6, a1, 0xAF6u);
  memset64(a6 + 5612, a1, 0x12EEu);
  v9 = (unsigned __int8 *)a1;
  v10 = a6 + 22608;
  while ( 2 )
  {
    v62 = 0;
    v63 = 0;
    v11 = (unsigned __int8 *)(a6 + 23185);
    v12 = 0;
    v13 = 0;
    memset_thunk_772440563353939046(v10, 0, 0x800u);
    v14 = v9 + 0x10000;
    if ( (unsigned __int64)(v9 + 0x10000) > v8 )
      v14 = (unsigned __int8 *)v8;
    XpressCallback = (unsigned __int64)&v9[v66];
    v16 = a6 + 23184;
    v67 = v14;
    v76 = a6 + 23184;
    v17 = (unsigned __int64)(v14 - 40);
    v61 = (unsigned __int64)(v14 - 40);
    if ( v14 - 40 < &v9[v66] )
      XpressCallback = (unsigned __int64)(v14 - 40);
    v78 = XpressCallback;
    if ( v9 == v6 )
    {
      v18 = 2;
      ++a6[*v9 + 22608];
      v19 = *v9++;
      *v11 = v19;
      v11 = (unsigned __int8 *)a6 + 92741;
    }
    else
    {
      v18 = 1;
    }
    v74 = v11;
    if ( (unsigned __int64)v9 >= v17 )
      goto LABEL_10;
    do
    {
      while ( 1 )
      {
        while ( 1 )
        {
          v26 = v9 + 1;
          v27 = v9;
          v28 = v9[2] + 4LL * v9[1];
          v29 = *v9 + 2 * v28;
          v30 = *(unsigned __int8 **)&a6[2 * v29];
          *(_QWORD *)&a6[2 * v29] = v9;
          v31 = *v9;
          if ( *v30 != (_BYTE)v31 || v30[1] != *v26 || v30[2] != v9[2] || v9 - v30 >= 0x10000 )
            break;
          v32 = v9[3];
          v33 = v30[3];
          if ( (_BYTE)v32 != (_BYTE)v33 )
          {
            v50 = v31 + 2 * v28;
            v51 = *(unsigned __int8 **)&a6[2 * v50 + 5612 + 2 * v32];
            *(_QWORD *)&a6[2 * v50 + 5612 + 2 * v33] = v30;
            if ( v9 - v51 >= 0x10000 || (v52 = *(unsigned int *)v9, (_DWORD)v52 != *(_DWORD *)v51) )
            {
              v9 += 3;
              i = v30 + 3;
              goto LABEL_38;
            }
            v30 = v51;
            *(_QWORD *)&a6[2 * v50 + 5612 + 2 * (v52 >> 24)] = v9;
          }
          v34 = v30[4];
          v35 = v9[4];
          if ( (_BYTE)v35 != (_BYTE)v34 )
          {
            v53 = 2
                * ((unsigned __int8)__ROR1__(*v26 ^ __ROL1__(v9[3] + *v9, 3), 1)
                 + 4LL * (unsigned __int8)__ROL1__(*v9 ^ __ROR1__(v9[2] + *v26 + 97, 1), 3));
            v54 = *(unsigned __int8 **)&a6[2 * v53 + 5612 + 2 * v35];
            *(_QWORD *)&a6[2 * v53 + 5612 + 2 * v34] = v30;
            if ( v9 - v54 >= 0x10000
              || *(_DWORD *)v9 != *(_DWORD *)v54
              || (v55 = v9[4], (_BYTE)v55 != v54[4])
              || v9 == v54 )
            {
              v9 += 4;
              i = v30 + 4;
LABEL_37:
              v11 = v74;
              goto LABEL_38;
            }
            v30 = v54;
            *(_QWORD *)&a6[2 * v53 + 5612 + 2 * v55] = v9;
          }
          v36 = v30[5];
          v37 = v9[5];
          if ( (_BYTE)v37 != (_BYTE)v36 )
          {
            v56 = 2
                * ((v9[2] ^ (unsigned __int64)(unsigned __int8)__ROL1__(*v9, v9[4]))
                 + 4
                 * ((unsigned __int8)__ROR1__(*v26 ^ __ROL1__(v9[3], 3), 1)
                  + (unsigned __int64)(unsigned __int8)__ROL1__(v9[4] ^ (__ROR1__(*v9, 1) + 69), 3)));
            v57 = *(unsigned __int8 **)&a6[2 * v56 + 5612 + 2 * v37];
            *(_QWORD *)&a6[2 * v56 + 5612 + 2 * v36] = v30;
            if ( v9 - v57 >= 0x10000
              || *(_DWORD *)v9 != *(_DWORD *)v57
              || v9[4] != v57[4]
              || (v58 = v9[5], (_BYTE)v58 != v57[5])
              || v9 == v57 )
            {
              v9 += 5;
              i = v30 + 5;
              goto LABEL_37;
            }
            v30 = v57;
            *(_QWORD *)&a6[2 * v56 + 5612 + 2 * v58] = v9;
          }
          v9 += 6;
          for ( i = v30 + 6; ; i += 32 )
          {
            if ( (unsigned __int64)v9 >= v64 - 40 )
            {
              for ( ; (unsigned __int64)v9 < v64; ++i )
              {
                if ( *v9 != *i )
                  break;
                ++v9;
              }
              goto LABEL_37;
            }
            v39 = *(_DWORD *)i;
            v40 = *(_DWORD *)v9;
            if ( *(_DWORD *)v9 != *(_DWORD *)i )
              break;
            v39 = *((_DWORD *)i + 1);
            v40 = *((_DWORD *)v9 + 1);
            if ( v40 != v39 )
            {
              v9 += 4;
              i += 4;
              break;
            }
            v39 = *((_DWORD *)i + 2);
            v40 = *((_DWORD *)v9 + 2);
            if ( v40 != v39 )
            {
              v9 += 8;
              i += 8;
              break;
            }
            v39 = *((_DWORD *)i + 3);
            v40 = *((_DWORD *)v9 + 3);
            if ( v40 != v39 )
            {
              v9 += 12;
              i += 12;
              break;
            }
            v39 = *((_DWORD *)i + 4);
            v40 = *((_DWORD *)v9 + 4);
            if ( v40 != v39 )
            {
              v9 += 16;
              i += 16;
              break;
            }
            v39 = *((_DWORD *)i + 5);
            v40 = *((_DWORD *)v9 + 5);
            if ( v40 != v39 )
            {
              v9 += 20;
              i += 20;
              break;
            }
            v39 = *((_DWORD *)i + 6);
            v40 = *((_DWORD *)v9 + 6);
            if ( v40 != v39 )
            {
              v9 += 24;
              i += 24;
              break;
            }
            v39 = *((_DWORD *)i + 7);
            v40 = *((_DWORD *)v9 + 7);
            if ( v40 != v39 )
            {
              v9 += 28;
              i += 28;
              break;
            }
            v9 += 32;
          }
          if ( (_BYTE)v40 != (_BYTE)v39 )
            goto LABEL_37;
          if ( v9[1] != i[1] )
          {
            ++v9;
            ++i;
            goto LABEL_37;
          }
          v11 = v74;
          if ( v9[2] == i[2] )
          {
            v9 += 3;
            i += 3;
          }
          else
          {
            v9 += 2;
            i += 2;
          }
LABEL_38:
          v41 = v9 - i;
          if ( v9 - v27 == 3 && v41 > 0x1000 )
          {
            XpressCallback = v78;
            v16 = v76;
            v17 = v61;
            break;
          }
          if ( v41 >= 0x100 )
            v42 = *((unsigned __int8 *)XpressHighBitIndexTable + (v41 >> 8)) + 8LL;
          else
            v42 = *((unsigned __int8 *)XpressHighBitIndexTable + v41);
          v12 = v42 + v62;
          v43 = v41 - (1LL << v42);
          v44 = 16 * v42;
          v45 = v9 - v27 - 3;
          v62 = v12;
          if ( v45 >= 0xF )
          {
            v47 = v44 + 15;
            *v11 = v47;
            v46 = v11 + 2;
            if ( (unsigned __int64)(v9 - v27 - 18) >= 0xFF )
            {
              v11[1] = -1;
              if ( v45 < 0x10000 )
              {
                *v46 = v45;
                v63 += 3;
                v46 = v11 + 4;
                goto LABEL_43;
              }
              *((_DWORD *)v11 + 1) = v45;
              *v46 = 0;
              v46 = v11 + 8;
              v60 = 7;
            }
            else
            {
              v11[1] = (_BYTE)v9 - (_BYTE)v27 - 18;
              v60 = 1;
            }
            v63 += v60;
          }
          else
          {
            v46 = v11 + 1;
            v47 = v44 + v45;
            *v11 = v47;
          }
LABEL_43:
          v11 = (unsigned __int8 *)(v46 + 1);
          v74 = (unsigned __int8 *)(v46 + 1);
          ++a6[v47 + 22864];
          v48 = (2 * v18) | 1;
          *v46 = v43;
          if ( v18 < 0 )
          {
            v59 = v76;
            v18 = 1;
            v76 = (int *)(v46 + 1);
            v11 = (unsigned __int8 *)(v46 + 3);
            v74 = (unsigned __int8 *)(v46 + 3);
            *v59 = v48;
          }
          else
          {
            v18 = (2 * v18) | 1;
          }
          XpressCallback = v78;
          v16 = v76;
          v17 = v61;
          if ( (unsigned __int64)v9 >= v78 )
          {
            if ( (unsigned __int64)v9 >= v61 )
              goto LABEL_104;
            v49 = v9;
LABEL_48:
            XpressCallback = RtlpMakeXpressCallback(v69, v17, v49);
            v78 = XpressCallback;
          }
        }
        v9 = v26;
        ++a6[*v27 + 22608];
        *v11++ = *v27;
        v74 = v11;
        if ( v18 < 0 )
          break;
        v18 *= 2;
      }
      *v16 = 2 * v18;
      v18 = 1;
      v16 = (int *)v11;
      v11 += 4;
      v76 = v16;
      v74 = v11;
    }
    while ( (unsigned __int64)v26 < XpressCallback );
    if ( (unsigned __int64)v26 < v17 )
    {
      v49 = v26;
      goto LABEL_48;
    }
    v12 = v62;
LABEL_104:
    v13 = v63;
    v14 = v67;
LABEL_10:
    while ( v9 < v14 )
    {
      ++a6[*v9 + 22608];
      v20 = *v9++;
      *v11++ = v20;
      if ( v18 < 0 )
      {
        *v16 = 2 * v18;
        v18 = 1;
        v16 = (int *)v11;
        v11 += 4;
      }
      else
      {
        v18 *= 2;
      }
    }
    for ( ; v18 >= 0; v18 = (2 * v18) | 1 )
      ;
    *v16 = (2 * v18) | 1;
    if ( (unsigned __int64)v9 < v64 )
    {
      v21 = 0;
    }
    else
    {
      ++a6[22864];
      v21 = 1;
    }
    if ( v13 + 4 * ((unsigned __int64)(v12 + XpressBuildHuffmanEncodings(a6 + 15304) + 31) >> 5) + v65 + 258 < v68 )
    {
      v22 = XpressDoHuffmanPass((int)a6 + 61216, (int)a6 + 92736, (_DWORD)v11, v65, v21);
      v6 = (unsigned __int8 *)a1;
      v23 = v22;
      v65 = v22;
      v24 = v21 == 0;
      v8 = v64;
      v10 = a6 + 22608;
      if ( !v24 )
      {
        *a5 = v23 - v73;
        return 0;
      }
      continue;
    }
    return 3221225507LL;
  }
}

```

## disassembly

```asm
0x1800b5e50  mov     r11, rsp
0x1800b5e53  mov     [r11+10h], rbx
0x1800b5e57  mov     [r11+18h], r8
0x1800b5e5b  mov     [r11+8], rcx
0x1800b5e5f  push    rbp
0x1800b5e60  push    rsi
0x1800b5e61  push    rdi
0x1800b5e62  push    r12
0x1800b5e64  push    r13
0x1800b5e66  push    r14
0x1800b5e68  push    r15
0x1800b5e6a  sub     rsp, 0A0h
0x1800b5e71  xor     r10d, r10d
0x1800b5e74  mov     r13, rcx
0x1800b5e77  mov     [r11-44h], r10d
0x1800b5e7b  cmp     r9d, 12Ch
0x1800b5e82  jb      loc_1800B6099
0x1800b5e88  mov     r12, [rsp+0D8h+arg_28]
0x1800b5e90  mov     eax, edx
0x1800b5e92  mov     rdi, r12
0x1800b5e95  mov     [rsp+0D8h+var_80], rax
0x1800b5e9a  mov     [rsp+0D8h+var_88], r8
0x1800b5e9f  mov     [r11-58h], r10
0x1800b5ea3  lea     rbx, [rax+rcx]
0x1800b5ea7  mov     [r11-50h], r10
0x1800b5eab  mov     eax, r9d
0x1800b5eae  add     rax, r8
0x1800b5eb1  mov     [rsp+0D8h+var_90], rbx
0x1800b5eb6  mov     [rsp+0D8h+var_60], rax
0x1800b5ebb  mov     rax, rcx
0x1800b5ebe  mov     ecx, 0AF6h
0x1800b5ec3  mov     [r11-48h], edx
0x1800b5ec7  rep stosq
0x1800b5eca  lea     rdi, [r12+57B0h]
0x1800b5ed2  mov     ecx, 12EEh
0x1800b5ed7  rep stosq
0x1800b5eda  mov     rdi, rax
0x1800b5edd  lea     rax, [r12+16140h]
0x1800b5ee5  xor     edx, edx; Val
0x1800b5ee7  mov     [rsp+0D8h+var_A0], r10
0x1800b5eec  mov     r8d, 800h; Size
0x1800b5ef2  mov     [rsp+0D8h+var_98], r10
0x1800b5ef7  mov     rcx, rax; void *
0x1800b5efa  lea     r14, [r12+16A44h]
0x1800b5f02  mov     r15, r10
0x1800b5f05  mov     rsi, r10
0x1800b5f08  call    memset$thunk$772440563353939046
0x1800b5f0d  mov     r8, [rsp+0D8h+var_80]
0x1800b5f12  lea     rcx, [rdi+10000h]
0x1800b5f19  cmp     rcx, rbx
0x1800b5f1c  cmova   rcx, rbx
0x1800b5f20  add     r8, rdi
0x1800b5f23  lea     rbx, [r12+16A40h]
0x1800b5f2b  mov     [rsp+0D8h+var_68], rcx
0x1800b5f30  mov     [rsp+0D8h+arg_30], rbx
0x1800b5f38  lea     rbp, [rcx-28h]
0x1800b5f3c  cmp     rbp, r8
0x1800b5f3f  mov     [rsp+0D8h+var_A8], rbp
0x1800b5f44  cmovb   r8, rbp
0x1800b5f48  mov     [rsp+0D8h+arg_38], r8
0x1800b5f50  cmp     rdi, r13
0x1800b5f53  jnz     loc_1800B66A8
0x1800b5f59  movzx   eax, byte ptr [rdi]
0x1800b5f5c  mov     r13d, 2
0x1800b5f62  inc     dword ptr [r12+rax*4+16140h]
0x1800b5f6a  movzx   eax, byte ptr [rdi]
0x1800b5f6d  inc     rdi
0x1800b5f70  mov     [r14], al
0x1800b5f73  inc     r14
0x1800b5f76  mov     [rsp+0D8h+arg_28], r14
0x1800b5f7e  cmp     rdi, rbp
0x1800b5f81  jb      loc_1800B60C0
0x1800b5f87  cmp     rdi, rcx
0x1800b5f8a  jnb     short loc_1800B5FBC
0x1800b5f8c  movzx   eax, byte ptr [rdi]
0x1800b5f8f  inc     dword ptr [r12+rax*4+16140h]
0x1800b5f97  movzx   eax, byte ptr [rdi]
0x1800b5f9a  inc     rdi
0x1800b5f9d  mov     [r14], al
0x1800b5fa0  inc     r14
0x1800b5fa3  lea     eax, ds:0[r13*2]
0x1800b5fab  test    r13d, r13d
0x1800b5fae  js      loc_1800B60A7
0x1800b5fb4  mov     r13d, eax
0x1800b5fb7  cmp     rdi, rcx
0x1800b5fba  jb      short loc_1800B5F8C
0x1800b5fbc  test    r13d, r13d
0x1800b5fbf  js      short loc_1800B5FCA
0x1800b5fc1  add     r13d, r13d
0x1800b5fc4  or      r13d, 1
0x1800b5fc8  jge     short loc_1800B5FC1
0x1800b5fca  lea     eax, ds:0[r13*2]
0x1800b5fd2  or      eax, 1
0x1800b5fd5  mov     [rbx], eax
0x1800b5fd7  cmp     rdi, [rsp+0D8h+var_90]
0x1800b5fdc  jb      loc_1800B60A0
0x1800b5fe2  inc     dword ptr [r12+16540h]
0x1800b5fea  mov     ebx, 1
0x1800b5fef  lea     rcx, [r12+0EF20h]
0x1800b5ff7  call    XpressBuildHuffmanEncodings
0x1800b5ffc  mov     r9, [rsp+0D8h+var_88]
0x1800b6001  lea     rcx, [rax+1Fh]
0x1800b6005  add     rcx, r15
0x1800b6008  shr     rcx, 5
0x1800b600c  lea     rax, [rsi+rcx*4]
0x1800b6010  lea     rcx, [r9+102h]
0x1800b6017  add     rcx, rax
0x1800b601a  cmp     rcx, [rsp+0D8h+var_60]
0x1800b601f  jnb     short loc_1800B6099
0x1800b6021  mov     r8, r14
0x1800b6024  mov     [rsp+0D8h+var_B8], ebx
0x1800b6028  lea     rdx, [r12+16A40h]
0x1800b6030  lea     rcx, [r12+0EF20h]
0x1800b6038  call    XpressDoHuffmanPass
0x1800b603d  mov     r13, [rsp+0D8h+arg_0]
0x1800b6045  mov     r14, rax
0x1800b6048  mov     [rsp+0D8h+var_88], rax
0x1800b604d  test    ebx, ebx
0x1800b604f  mov     rbx, [rsp+0D8h+var_90]
0x1800b6054  lea     rax, [r12+16140h]
0x1800b605c  mov     r10d, 0
0x1800b6062  jz      loc_1800B5EE5
0x1800b6068  mov     rax, [rsp+0D8h+arg_20]
0x1800b6070  sub     r14d, [rsp+0D8h+arg_10]
0x1800b6078  mov     [rax], r14d
0x1800b607b  xor     eax, eax
0x1800b607d  mov     rbx, [rsp+0D8h+arg_8]
0x1800b6085  add     rsp, 0A0h
0x1800b608c  pop     r15
0x1800b608e  pop     r14
0x1800b6090  pop     r13
0x1800b6092  pop     r12
0x1800b6094  pop     rdi
0x1800b6095  pop     rsi
0x1800b6096  pop     rbp
0x1800b6097  retn
0x1800b6099  mov     eax, 0C0000023h
0x1800b609e  jmp     short loc_1800B607D
0x1800b60a0  xor     ebx, ebx
0x1800b60a2  jmp     loc_1800B5FEF
0x1800b60a7  mov     [rbx], eax
0x1800b60a9  mov     r13d, 1
0x1800b60af  mov     rbx, r14
0x1800b60b2  add     r14, 4
0x1800b60b6  jmp     loc_1800B5FB7
0x1800b60c0  movzx   ecx, byte ptr [rdi+1]
0x1800b60c4  lea     r10, [rdi+1]
0x1800b60c8  movzx   eax, byte ptr [rdi+2]
0x1800b60cc  mov     r11, rdi
0x1800b60cf  lea     rdx, [rax+rcx*4]
0x1800b60d3  movzx   eax, byte ptr [rdi]
0x1800b60d6  lea     rcx, [rax+rdx*2]
0x1800b60da  mov     r9, [r12+rcx*8]
0x1800b60de  mov     [r12+rcx*8], rdi
0x1800b60e2  movzx   ecx, byte ptr [rdi]
0x1800b60e5  cmp     [r9], cl
0x1800b60e8  jnz     loc_1800B6299
0x1800b60ee  movzx   eax, byte ptr [r10]
0x1800b60f2  cmp     [r9+1], al
0x1800b60f6  jnz     loc_1800B6299
0x1800b60fc  movzx   eax, byte ptr [rdi+2]
0x1800b6100  cmp     [r9+2], al
0x1800b6104  jnz     loc_1800B6299
0x1800b610a  mov     rax, rdi
0x1800b610d  sub     rax, r9
0x1800b6110  cmp     rax, 10000h
0x1800b6116  jge     loc_1800B6299
0x1800b611c  movzx   ebx, byte ptr [rdi+3]
0x1800b6120  lea     rbp, [rdi+3]
0x1800b6124  movzx   r8d, byte ptr [r9+3]
0x1800b6129  mov     [rsp+0D8h+var_78], rbp
0x1800b612e  cmp     bl, r8b
0x1800b6131  jnz     loc_1800B62EE
0x1800b6137  movzx   ebx, byte ptr [r9+4]
0x1800b613c  movzx   esi, byte ptr [rdi+4]
0x1800b6140  cmp     sil, bl
0x1800b6143  jnz     loc_1800B63B3
0x1800b6149  movzx   ebp, byte ptr [r9+5]
0x1800b614e  movzx   r14d, byte ptr [rdi+5]
0x1800b6153  cmp     r14b, bpl
0x1800b6156  jnz     loc_1800B644E
0x1800b615c  add     rdi, 6
0x1800b6160  add     r9, 6
0x1800b6164  mov     rcx, [rsp+0D8h+var_90]
0x1800b6169  lea     rax, [rcx-28h]
0x1800b616d  cmp     rdi, rax
0x1800b6170  jnb     loc_1800B664E
0x1800b6176  mov     ecx, [r9]
0x1800b6179  mov     eax, [rdi]
0x1800b617b  cmp     eax, ecx
0x1800b617d  jz      loc_1800B633D
0x1800b6183  cmp     al, cl
0x1800b6185  jnz     short loc_1800B619B
0x1800b6187  movzx   eax, byte ptr [r9+1]
0x1800b618c  cmp     [rdi+1], al
0x1800b618f  jz      loc_1800B64F4
0x1800b6195  inc     rdi
0x1800b6198  inc     r9
0x1800b619b  mov     r14, [rsp+0D8h+arg_28]
0x1800b61a3  mov     r8, rdi
0x1800b61a6  mov     rdx, rdi
0x1800b61a9  sub     r8, r11
0x1800b61ac  sub     rdx, r9
0x1800b61af  cmp     r8, 3
0x1800b61b3  jz      loc_1800B6517
0x1800b61b9  cmp     rdx, 100h
0x1800b61c0  jnb     loc_1800B62D3
0x1800b61c6  lea     rax, XpressHighBitIndexTable
0x1800b61cd  movzx   ecx, byte ptr [rdx+rax]
0x1800b61d1  mov     r15, [rsp+0D8h+var_A0]
0x1800b61d6  mov     eax, 1
0x1800b61db  shl     rax, cl
0x1800b61de  add     r15, rcx
0x1800b61e1  sub     rdx, rax
0x1800b61e4  shl     cl, 4
0x1800b61e7  add     r8, 0FFFFFFFFFFFFFFFDh
0x1800b61eb  mov     [rsp+0D8h+var_A0], r15
0x1800b61f0  cmp     r8, 0Fh
0x1800b61f4  jnb     loc_1800B6598
0x1800b61fa  add     r8b, cl
0x1800b61fd  lea     r9, [r14+1]
0x1800b6201  movzx   ecx, r8b
0x1800b6205  mov     [r14], r8b
0x1800b6208  movzx   eax, cl
0x1800b620b  lea     r14, [r9+2]
0x1800b620f  mov     [rsp+0D8h+arg_28], r14
0x1800b6217  inc     dword ptr [r12+rax*4+16540h]
0x1800b621f  lea     eax, ds:0[r13*2]
0x1800b6227  or      eax, 1
0x1800b622a  mov     [r9], dx
0x1800b622e  test    r13d, r13d
0x1800b6231  js      loc_1800B656F
0x1800b6237  mov     r13d, eax
0x1800b623a  mov     r8, [rsp+0D8h+arg_38]
0x1800b6242  mov     rbx, [rsp+0D8h+arg_30]
0x1800b624a  mov     rbp, [rsp+0D8h+var_A8]
0x1800b624f  cmp     rdi, r8
0x1800b6252  jb      loc_1800B60C0
0x1800b6258  cmp     rdi, rbp
0x1800b625b  jnb     loc_1800B6699
0x1800b6261  mov     r8, rdi
0x1800b6264  mov     rdx, rbp
0x1800b6267  lea     rcx, [rsp+0D8h+var_58]
0x1800b626f  call    RtlpMakeXpressCallback
0x1800b6274  mov     r8, rax
0x1800b6277  mov     [rsp+0D8h+arg_38], rax
0x1800b627f  jmp     loc_1800B60C0
0x1800b6284  mov     r8, [rsp+0D8h+arg_38]
0x1800b628c  mov     rbx, [rsp+0D8h+arg_30]
0x1800b6294  mov     rbp, [rsp+0D8h+var_A8]
0x1800b6299  movzx   eax, byte ptr [r11]
0x1800b629d  mov     rdi, r10
0x1800b62a0  inc     dword ptr [r12+rax*4+16140h]
0x1800b62a8  movzx   eax, byte ptr [r11]
0x1800b62ac  mov     [r14], al
0x1800b62af  inc     r14
0x1800b62b2  mov     [rsp+0D8h+arg_28], r14
0x1800b62ba  lea     eax, ds:0[r13*2]
0x1800b62c2  test    r13d, r13d
0x1800b62c5  js      loc_1800B6536
0x1800b62cb  mov     r13d, eax
0x1800b62ce  jmp     loc_1800B60C0
0x1800b62d3  mov     rax, rdx
0x1800b62d6  lea     rcx, XpressHighBitIndexTable
0x1800b62dd  shr     rax, 8
0x1800b62e1  movzx   ecx, byte ptr [rax+rcx]
0x1800b62e5  add     rcx, 8
0x1800b62e9  jmp     loc_1800B61D1
0x1800b62ee  lea     rdx, [rcx+rdx*2]
0x1800b62f2  lea     rax, [rdx+rbx]
0x1800b62f6  mov     rcx, [r12+rax*8+57B0h]
0x1800b62fe  lea     rax, [rdx+r8]
0x1800b6302  mov     [r12+rax*8+57B0h], r9
0x1800b630a  mov     rax, rdi
0x1800b630d  sub     rax, rcx
0x1800b6310  cmp     rax, 10000h
0x1800b6316  jge     loc_1800B6442
0x1800b631c  mov     eax, [rdi]
0x1800b631e  cmp     eax, [rcx]
0x1800b6320  jnz     loc_1800B6442
0x1800b6326  shr     rax, 18h
0x1800b632a  mov     r9, rcx
0x1800b632d  add     rax, rdx
0x1800b6330  mov     [r12+rax*8+57B0h], rdi
0x1800b6338  jmp     loc_1800B6137
0x1800b633d  mov     ecx, [r9+4]
0x1800b6341  mov     eax, [rdi+4]
0x1800b6344  cmp     eax, ecx
0x1800b6346  jnz     loc_1800B65CE
0x1800b634c  mov     ecx, [r9+8]
0x1800b6350  mov     eax, [rdi+8]
0x1800b6353  cmp     eax, ecx
0x1800b6355  jnz     loc_1800B65C1
0x1800b635b  mov     ecx, [r9+0Ch]
0x1800b635f  mov     eax, [rdi+0Ch]
0x1800b6362  cmp     eax, ecx
0x1800b6364  jnz     loc_1800B65E8
0x1800b636a  mov     ecx, [r9+10h]
0x1800b636e  mov     eax, [rdi+10h]
0x1800b6371  cmp     eax, ecx
  ... truncated ...
```
