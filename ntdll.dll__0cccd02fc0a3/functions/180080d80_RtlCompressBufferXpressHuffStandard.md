# RtlCompressBufferXpressHuffStandard

- ea: `0x180080d80`
- end: `0x1800815e3`
- name: `RtlCompressBufferXpressHuffStandard`
- size: `2147`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18007fcd0`

## callees

- `0x180080d80`
- `0x1800815f0`
- `0x180081640`
- `0x180081b80`
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
0x180080d80  mov     r11, rsp
0x180080d83  mov     [r11+10h], rbx
0x180080d87  mov     [r11+18h], r8
0x180080d8b  mov     [r11+8], rcx
0x180080d8f  push    rbp
0x180080d90  push    rsi
0x180080d91  push    rdi
0x180080d92  push    r12
0x180080d94  push    r13
0x180080d96  push    r14
0x180080d98  push    r15
0x180080d9a  sub     rsp, 0A0h
0x180080da1  xor     r10d, r10d
0x180080da4  mov     r13, rcx
0x180080da7  mov     [r11-44h], r10d
0x180080dab  cmp     r9d, 12Ch
0x180080db2  jb      loc_180080FC9
0x180080db8  mov     r12, [rsp+0D8h+arg_28]
0x180080dc0  mov     eax, edx
0x180080dc2  mov     rdi, r12
0x180080dc5  mov     [rsp+0D8h+var_80], rax
0x180080dca  mov     [rsp+0D8h+var_88], r8
0x180080dcf  mov     [r11-58h], r10
0x180080dd3  lea     rbx, [rax+rcx]
0x180080dd7  mov     [r11-50h], r10
0x180080ddb  mov     eax, r9d
0x180080dde  add     rax, r8
0x180080de1  mov     [rsp+0D8h+var_90], rbx
0x180080de6  mov     [rsp+0D8h+var_60], rax
0x180080deb  mov     rax, rcx
0x180080dee  mov     ecx, 0AF6h
0x180080df3  mov     [r11-48h], edx
0x180080df7  rep stosq
0x180080dfa  lea     rdi, [r12+57B0h]
0x180080e02  mov     ecx, 12EEh
0x180080e07  rep stosq
0x180080e0a  mov     rdi, rax
0x180080e0d  lea     rax, [r12+16140h]
0x180080e15  xor     edx, edx; Val
0x180080e17  mov     [rsp+0D8h+var_A0], r10
0x180080e1c  mov     r8d, 800h; Size
0x180080e22  mov     [rsp+0D8h+var_98], r10
0x180080e27  mov     rcx, rax; void *
0x180080e2a  lea     r14, [r12+16A44h]
0x180080e32  mov     r15, r10
0x180080e35  mov     rsi, r10
0x180080e38  call    memset$thunk$772440563353939046
0x180080e3d  mov     r8, [rsp+0D8h+var_80]
0x180080e42  lea     rcx, [rdi+10000h]
0x180080e49  cmp     rcx, rbx
0x180080e4c  cmova   rcx, rbx
0x180080e50  add     r8, rdi
0x180080e53  lea     rbx, [r12+16A40h]
0x180080e5b  mov     [rsp+0D8h+var_68], rcx
0x180080e60  mov     [rsp+0D8h+arg_30], rbx
0x180080e68  lea     rbp, [rcx-28h]
0x180080e6c  cmp     rbp, r8
0x180080e6f  mov     [rsp+0D8h+var_A8], rbp
0x180080e74  cmovb   r8, rbp
0x180080e78  mov     [rsp+0D8h+arg_38], r8
0x180080e80  cmp     rdi, r13
0x180080e83  jnz     loc_1800815D8
0x180080e89  movzx   eax, byte ptr [rdi]
0x180080e8c  mov     r13d, 2
0x180080e92  inc     dword ptr [r12+rax*4+16140h]
0x180080e9a  movzx   eax, byte ptr [rdi]
0x180080e9d  inc     rdi
0x180080ea0  mov     [r14], al
0x180080ea3  inc     r14
0x180080ea6  mov     [rsp+0D8h+arg_28], r14
0x180080eae  cmp     rdi, rbp
0x180080eb1  jb      loc_180080FF0
0x180080eb7  cmp     rdi, rcx
0x180080eba  jnb     short loc_180080EEC
0x180080ebc  movzx   eax, byte ptr [rdi]
0x180080ebf  inc     dword ptr [r12+rax*4+16140h]
0x180080ec7  movzx   eax, byte ptr [rdi]
0x180080eca  inc     rdi
0x180080ecd  mov     [r14], al
0x180080ed0  inc     r14
0x180080ed3  lea     eax, ds:0[r13*2]
0x180080edb  test    r13d, r13d
0x180080ede  js      loc_180080FD7
0x180080ee4  mov     r13d, eax
0x180080ee7  cmp     rdi, rcx
0x180080eea  jb      short loc_180080EBC
0x180080eec  test    r13d, r13d
0x180080eef  js      short loc_180080EFA
0x180080ef1  add     r13d, r13d
0x180080ef4  or      r13d, 1
0x180080ef8  jge     short loc_180080EF1
0x180080efa  lea     eax, ds:0[r13*2]
0x180080f02  or      eax, 1
0x180080f05  mov     [rbx], eax
0x180080f07  cmp     rdi, [rsp+0D8h+var_90]
0x180080f0c  jb      loc_180080FD0
0x180080f12  inc     dword ptr [r12+16540h]
0x180080f1a  mov     ebx, 1
0x180080f1f  lea     rcx, [r12+0EF20h]
0x180080f27  call    XpressBuildHuffmanEncodings
0x180080f2c  mov     r9, [rsp+0D8h+var_88]
0x180080f31  lea     rcx, [rax+1Fh]
0x180080f35  add     rcx, r15
0x180080f38  shr     rcx, 5
0x180080f3c  lea     rax, [rsi+rcx*4]
0x180080f40  lea     rcx, [r9+102h]
0x180080f47  add     rcx, rax
0x180080f4a  cmp     rcx, [rsp+0D8h+var_60]
0x180080f4f  jnb     short loc_180080FC9
0x180080f51  mov     r8, r14
0x180080f54  mov     [rsp+0D8h+var_B8], ebx
0x180080f58  lea     rdx, [r12+16A40h]
0x180080f60  lea     rcx, [r12+0EF20h]
0x180080f68  call    XpressDoHuffmanPass
0x180080f6d  mov     r13, [rsp+0D8h+arg_0]
0x180080f75  mov     r14, rax
0x180080f78  mov     [rsp+0D8h+var_88], rax
0x180080f7d  test    ebx, ebx
0x180080f7f  mov     rbx, [rsp+0D8h+var_90]
0x180080f84  lea     rax, [r12+16140h]
0x180080f8c  mov     r10d, 0
0x180080f92  jz      loc_180080E15
0x180080f98  mov     rax, [rsp+0D8h+arg_20]
0x180080fa0  sub     r14d, [rsp+0D8h+arg_10]
0x180080fa8  mov     [rax], r14d
0x180080fab  xor     eax, eax
0x180080fad  mov     rbx, [rsp+0D8h+arg_8]
0x180080fb5  add     rsp, 0A0h
0x180080fbc  pop     r15
0x180080fbe  pop     r14
0x180080fc0  pop     r13
0x180080fc2  pop     r12
0x180080fc4  pop     rdi
0x180080fc5  pop     rsi
0x180080fc6  pop     rbp
0x180080fc7  retn
0x180080fc9  mov     eax, 0C0000023h
0x180080fce  jmp     short loc_180080FAD
0x180080fd0  xor     ebx, ebx
0x180080fd2  jmp     loc_180080F1F
0x180080fd7  mov     [rbx], eax
0x180080fd9  mov     r13d, 1
0x180080fdf  mov     rbx, r14
0x180080fe2  add     r14, 4
0x180080fe6  jmp     loc_180080EE7
0x180080ff0  movzx   ecx, byte ptr [rdi+1]
0x180080ff4  lea     r10, [rdi+1]
0x180080ff8  movzx   eax, byte ptr [rdi+2]
0x180080ffc  mov     r11, rdi
0x180080fff  lea     rdx, [rax+rcx*4]
0x180081003  movzx   eax, byte ptr [rdi]
0x180081006  lea     rcx, [rax+rdx*2]
0x18008100a  mov     r9, [r12+rcx*8]
0x18008100e  mov     [r12+rcx*8], rdi
0x180081012  movzx   ecx, byte ptr [rdi]
0x180081015  cmp     [r9], cl
0x180081018  jnz     loc_1800811C9
0x18008101e  movzx   eax, byte ptr [r10]
0x180081022  cmp     [r9+1], al
0x180081026  jnz     loc_1800811C9
0x18008102c  movzx   eax, byte ptr [rdi+2]
0x180081030  cmp     [r9+2], al
0x180081034  jnz     loc_1800811C9
0x18008103a  mov     rax, rdi
0x18008103d  sub     rax, r9
0x180081040  cmp     rax, 10000h
0x180081046  jge     loc_1800811C9
0x18008104c  movzx   ebx, byte ptr [rdi+3]
0x180081050  lea     rbp, [rdi+3]
0x180081054  movzx   r8d, byte ptr [r9+3]
0x180081059  mov     [rsp+0D8h+var_78], rbp
0x18008105e  cmp     bl, r8b
0x180081061  jnz     loc_18008121E
0x180081067  movzx   ebx, byte ptr [r9+4]
0x18008106c  movzx   esi, byte ptr [rdi+4]
0x180081070  cmp     sil, bl
0x180081073  jnz     loc_1800812E3
0x180081079  movzx   ebp, byte ptr [r9+5]
0x18008107e  movzx   r14d, byte ptr [rdi+5]
0x180081083  cmp     r14b, bpl
0x180081086  jnz     loc_18008137E
0x18008108c  add     rdi, 6
0x180081090  add     r9, 6
0x180081094  mov     rcx, [rsp+0D8h+var_90]
0x180081099  lea     rax, [rcx-28h]
0x18008109d  cmp     rdi, rax
0x1800810a0  jnb     loc_18008157E
0x1800810a6  mov     ecx, [r9]
0x1800810a9  mov     eax, [rdi]
0x1800810ab  cmp     eax, ecx
0x1800810ad  jz      loc_18008126D
0x1800810b3  cmp     al, cl
0x1800810b5  jnz     short loc_1800810CB
0x1800810b7  movzx   eax, byte ptr [r9+1]
0x1800810bc  cmp     [rdi+1], al
0x1800810bf  jz      loc_180081424
0x1800810c5  inc     rdi
0x1800810c8  inc     r9
0x1800810cb  mov     r14, [rsp+0D8h+arg_28]
0x1800810d3  mov     r8, rdi
0x1800810d6  mov     rdx, rdi
0x1800810d9  sub     r8, r11
0x1800810dc  sub     rdx, r9
0x1800810df  cmp     r8, 3
0x1800810e3  jz      loc_180081447
0x1800810e9  cmp     rdx, 100h
0x1800810f0  jnb     loc_180081203
0x1800810f6  lea     rax, XpressHighBitIndexTable
0x1800810fd  movzx   ecx, byte ptr [rdx+rax]
0x180081101  mov     r15, [rsp+0D8h+var_A0]
0x180081106  mov     eax, 1
0x18008110b  shl     rax, cl
0x18008110e  add     r15, rcx
0x180081111  sub     rdx, rax
0x180081114  shl     cl, 4
0x180081117  add     r8, 0FFFFFFFFFFFFFFFDh
0x18008111b  mov     [rsp+0D8h+var_A0], r15
0x180081120  cmp     r8, 0Fh
0x180081124  jnb     loc_1800814C8
0x18008112a  add     r8b, cl
0x18008112d  lea     r9, [r14+1]
0x180081131  movzx   ecx, r8b
0x180081135  mov     [r14], r8b
0x180081138  movzx   eax, cl
0x18008113b  lea     r14, [r9+2]
0x18008113f  mov     [rsp+0D8h+arg_28], r14
0x180081147  inc     dword ptr [r12+rax*4+16540h]
0x18008114f  lea     eax, ds:0[r13*2]
0x180081157  or      eax, 1
0x18008115a  mov     [r9], dx
0x18008115e  test    r13d, r13d
0x180081161  js      loc_18008149F
0x180081167  mov     r13d, eax
0x18008116a  mov     r8, [rsp+0D8h+arg_38]
0x180081172  mov     rbx, [rsp+0D8h+arg_30]
0x18008117a  mov     rbp, [rsp+0D8h+var_A8]
0x18008117f  cmp     rdi, r8
0x180081182  jb      loc_180080FF0
0x180081188  cmp     rdi, rbp
0x18008118b  jnb     loc_1800815C9
0x180081191  mov     r8, rdi
0x180081194  mov     rdx, rbp
0x180081197  lea     rcx, [rsp+0D8h+var_58]
0x18008119f  call    RtlpMakeXpressCallback
0x1800811a4  mov     r8, rax
0x1800811a7  mov     [rsp+0D8h+arg_38], rax
0x1800811af  jmp     loc_180080FF0
0x1800811b4  mov     r8, [rsp+0D8h+arg_38]
0x1800811bc  mov     rbx, [rsp+0D8h+arg_30]
0x1800811c4  mov     rbp, [rsp+0D8h+var_A8]
0x1800811c9  movzx   eax, byte ptr [r11]
0x1800811cd  mov     rdi, r10
0x1800811d0  inc     dword ptr [r12+rax*4+16140h]
0x1800811d8  movzx   eax, byte ptr [r11]
0x1800811dc  mov     [r14], al
0x1800811df  inc     r14
0x1800811e2  mov     [rsp+0D8h+arg_28], r14
0x1800811ea  lea     eax, ds:0[r13*2]
0x1800811f2  test    r13d, r13d
0x1800811f5  js      loc_180081466
0x1800811fb  mov     r13d, eax
0x1800811fe  jmp     loc_180080FF0
0x180081203  mov     rax, rdx
0x180081206  lea     rcx, XpressHighBitIndexTable
0x18008120d  shr     rax, 8
0x180081211  movzx   ecx, byte ptr [rax+rcx]
0x180081215  add     rcx, 8
0x180081219  jmp     loc_180081101
0x18008121e  lea     rdx, [rcx+rdx*2]
0x180081222  lea     rax, [rdx+rbx]
0x180081226  mov     rcx, [r12+rax*8+57B0h]
0x18008122e  lea     rax, [rdx+r8]
0x180081232  mov     [r12+rax*8+57B0h], r9
0x18008123a  mov     rax, rdi
0x18008123d  sub     rax, rcx
0x180081240  cmp     rax, 10000h
0x180081246  jge     loc_180081372
0x18008124c  mov     eax, [rdi]
0x18008124e  cmp     eax, [rcx]
0x180081250  jnz     loc_180081372
0x180081256  shr     rax, 18h
0x18008125a  mov     r9, rcx
0x18008125d  add     rax, rdx
0x180081260  mov     [r12+rax*8+57B0h], rdi
0x180081268  jmp     loc_180081067
0x18008126d  mov     ecx, [r9+4]
0x180081271  mov     eax, [rdi+4]
0x180081274  cmp     eax, ecx
0x180081276  jnz     loc_1800814FE
0x18008127c  mov     ecx, [r9+8]
0x180081280  mov     eax, [rdi+8]
0x180081283  cmp     eax, ecx
0x180081285  jnz     loc_1800814F1
0x18008128b  mov     ecx, [r9+0Ch]
0x18008128f  mov     eax, [rdi+0Ch]
0x180081292  cmp     eax, ecx
0x180081294  jnz     loc_180081518
0x18008129a  mov     ecx, [r9+10h]
0x18008129e  mov     eax, [rdi+10h]
0x1800812a1  cmp     eax, ecx
  ... truncated ...
```
