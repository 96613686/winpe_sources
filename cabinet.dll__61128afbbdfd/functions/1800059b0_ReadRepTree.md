# ReadRepTree

- ea: `0x1800059b0`
- end: `0x180006269`
- name: `ReadRepTree`
- size: `2233`
- prototype: `_BOOL8 __fastcall(__int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004750`

## callees

- `0x1800059b0`
- `0x180006270`
- `0x180006910`
- `0x180014dc0`
- `0x18001562a`

## pseudocode

```c
_BOOL8 __fastcall ReadRepTree(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  __int64 v7; // rdi
  __int64 i; // r9
  unsigned __int64 *v9; // r13
  unsigned int v10; // r10d
  char v11; // al
  int v12; // edx
  unsigned int v13; // r10d
  int v14; // r8d
  char v15; // r8
  unsigned int v16; // r10d
  int v17; // edx
  unsigned int v18; // r10d
  unsigned int v19; // edx
  char v20; // r8
  unsigned int v21; // r10d
  int v22; // edx
  unsigned int v23; // r10d
  char v24; // r8
  unsigned int v25; // r11d
  int v26; // r10d
  unsigned int v27; // r11d
  int v28; // edx
  char v29; // dl
  unsigned int v30; // r10d
  int v31; // r8d
  unsigned int v32; // r10d
  int v33; // ebx
  unsigned int v34; // r8d
  unsigned __int16 v35; // ax
  int v36; // r8d
  char v37; // cl
  unsigned __int64 v39; // r11
  unsigned __int16 *v40; // rdx
  int v41; // r10d
  unsigned __int16 *v42; // r8
  int v43; // edx
  unsigned int v44; // ecx
  __int16 v45; // bp
  int v46; // r11d
  int j; // ecx
  __int64 v48; // rax
  int v49; // r14d
  int v50; // r14d
  unsigned __int64 v51; // rbp
  unsigned __int8 *v52; // rbx
  int v53; // eax
  int v54; // r11d
  unsigned __int16 *v55; // rbx
  int v56; // r11d
  int v57; // r11d
  unsigned __int64 v58; // rbp
  unsigned __int8 *v59; // r11
  int v60; // ebx
  int v61; // eax
  unsigned __int16 *v62; // r11
  int v63; // ebx
  unsigned __int64 v64; // rbp
  unsigned __int8 *v65; // r11
  int v66; // ebx
  int v67; // eax
  unsigned __int16 *v68; // r11
  int v69; // ebx
  unsigned __int64 v70; // rbp
  unsigned __int16 *v71; // r8
  int v72; // ebx
  unsigned __int16 *v73; // r10
  unsigned __int64 v74; // rbp
  unsigned __int8 *v75; // rbx
  int v76; // r11d
  int v77; // eax
  unsigned __int16 *v78; // rbx
  char v79; // dl
  int v80; // r11d
  int v81; // r14d
  int v82; // r14d
  unsigned int v83; // edx
  int v84; // ecx
  unsigned int v85; // r8d
  int v86; // edx
  _BYTE v87[32]; // [rsp+30h] [rbp-328h] BYREF
  _WORD v88[96]; // [rsp+50h] [rbp-308h] BYREF
  _WORD v89[256]; // [rsp+110h] [rbp-248h] BYREF

  v7 = a1;
  for ( i = 0; i != 20; i += 5 )
  {
    v9 = (unsigned __int64 *)(v7 + 11016);
    v10 = *(_DWORD *)(v7 + 11968);
    v11 = *(_BYTE *)(v7 + 11972) - 4;
    v12 = 16 * v10;
    v13 = v10 >> 28;
    v14 = v11;
    *(_BYTE *)(v7 + 11972) = v11;
    *(_DWORD *)(v7 + 11968) = v12;
    if ( v11 > 0 )
      goto LABEL_3;
    v51 = *(_QWORD *)(v7 + 11024);
    v52 = (unsigned __int8 *)*v9;
    if ( *v9 >= v51 )
    {
      *(_DWORD *)(v7 + 11980) = 1;
    }
    else
    {
      v53 = *v52;
      a1 = (unsigned int)-v14;
      v54 = v52[1] << 8;
      v55 = (unsigned __int16 *)(v52 + 2);
      *v9 = (unsigned __int64)v55;
      v56 = (v53 | v54) << -(char)v14;
      LOBYTE(v14) = v14 + 16;
      v57 = v12 | v56;
      *(_BYTE *)(v7 + 11972) = v14;
      *(_DWORD *)(v7 + 11968) = v57;
      if ( (char)v14 > 0 )
        goto LABEL_40;
      if ( (unsigned __int64)v55 >= v51 )
      {
        *(_DWORD *)(v7 + 11980) = 1;
LABEL_40:
        v12 = v57;
        goto LABEL_3;
      }
      a1 = (unsigned int)-(char)v14;
      v12 = v57 | (*v55 << -(char)v14);
      *v9 = (unsigned __int64)(v55 + 1);
      LOBYTE(v14) = v14 + 16;
    }
LABEL_3:
    v87[i] = v13;
    v15 = v14 - 4;
    v16 = v12;
    *(_BYTE *)(v7 + 11972) = v15;
    v17 = 16 * v12;
    v18 = v16 >> 28;
    *(_DWORD *)(v7 + 11968) = v17;
    if ( v15 <= 0 )
    {
      v58 = *(_QWORD *)(v7 + 11024);
      v59 = (unsigned __int8 *)*v9;
      if ( *v9 >= v58 )
      {
        *(_DWORD *)(v7 + 11980) = 1;
      }
      else
      {
        v60 = v59[1];
        v61 = *v59;
        v62 = (unsigned __int16 *)(v59 + 2);
        a1 = (unsigned int)-v15;
        v15 += 16;
        v63 = v17 | ((v61 | (v60 << 8)) << a1);
        *(_DWORD *)(v7 + 11968) = v63;
        *v9 = (unsigned __int64)v62;
        *(_BYTE *)(v7 + 11972) = v15;
        if ( v15 <= 0 )
        {
          if ( (unsigned __int64)v62 >= v58 )
          {
            *(_DWORD *)(v7 + 11980) = 1;
          }
          else
          {
            a1 = (unsigned int)-v15;
            *(_DWORD *)(v7 + 11968) = v63 | (*v62 << -v15);
            v15 += 16;
            *v9 = (unsigned __int64)(v62 + 1);
          }
        }
      }
    }
    v19 = *(_DWORD *)(v7 + 11968);
    v20 = v15 - 4;
    v87[i + 1] = v18;
    v21 = v19;
    v22 = 16 * v19;
    v23 = v21 >> 28;
    *(_DWORD *)(v7 + 11968) = v22;
    *(_BYTE *)(v7 + 11972) = v20;
    if ( v20 <= 0 )
    {
      v64 = *(_QWORD *)(v7 + 11024);
      v65 = (unsigned __int8 *)*v9;
      if ( *v9 >= v64 )
      {
        *(_DWORD *)(v7 + 11980) = 1;
      }
      else
      {
        v66 = v65[1];
        v67 = *v65;
        v68 = (unsigned __int16 *)(v65 + 2);
        a1 = (unsigned int)-v20;
        v20 += 16;
        v69 = v22 | ((v67 | (v66 << 8)) << a1);
        *(_DWORD *)(v7 + 11968) = v69;
        *v9 = (unsigned __int64)v68;
        *(_BYTE *)(v7 + 11972) = v20;
        if ( v20 <= 0 )
        {
          if ( (unsigned __int64)v68 >= v64 )
          {
            *(_DWORD *)(v7 + 11980) = 1;
          }
          else
          {
            a1 = (unsigned int)-v20;
            *(_DWORD *)(v7 + 11968) = v69 | (*v68 << -v20);
            v20 += 16;
            *v9 = (unsigned __int64)(v68 + 1);
          }
        }
      }
    }
    v87[i + 2] = v23;
    v24 = v20 - 4;
    v25 = *(_DWORD *)(v7 + 11968);
    v26 = 16 * v25;
    v27 = v25 >> 28;
    v28 = v24;
    *(_DWORD *)(v7 + 11968) = v26;
    *(_BYTE *)(v7 + 11972) = v24;
    if ( v24 <= 0 )
    {
      v70 = *(_QWORD *)(v7 + 11024);
      v71 = (unsigned __int16 *)*v9;
      if ( *v9 >= v70 )
      {
        *(_DWORD *)(v7 + 11980) = 1;
      }
      else
      {
        a1 = (unsigned int)-v28;
        LOBYTE(v28) = v28 + 16;
        v72 = v26 | (*v71 << a1);
        v73 = v71 + 1;
        *(_DWORD *)(v7 + 11968) = v72;
        *v9 = (unsigned __int64)(v71 + 1);
        *(_BYTE *)(v7 + 11972) = v28;
        if ( (char)v28 <= 0 )
        {
          if ( (unsigned __int64)v73 >= v70 )
          {
            *(_DWORD *)(v7 + 11980) = 1;
          }
          else
          {
            a1 = (unsigned int)-(char)v28;
            *(_DWORD *)(v7 + 11968) = v72 | (*v73 << -(char)v28);
            LOBYTE(v28) = v28 + 16;
            *v9 = (unsigned __int64)(v71 + 2);
          }
        }
      }
    }
    v29 = v28 - 4;
    v30 = *(_DWORD *)(v7 + 11968);
    v87[i + 3] = v27;
    v31 = 16 * v30;
    v32 = v30 >> 28;
    *(_DWORD *)(v7 + 11968) = v31;
    *(_BYTE *)(v7 + 11972) = v29;
    if ( v29 <= 0 )
    {
      v74 = *(_QWORD *)(v7 + 11024);
      v75 = (unsigned __int8 *)*v9;
      if ( *v9 >= v74 )
        goto LABEL_75;
      v76 = v75[1];
      v77 = *v75;
      v78 = (unsigned __int16 *)(v75 + 2);
      a1 = (unsigned int)-v29;
      v79 = v29 + 16;
      v80 = v31 | ((v77 | (v76 << 8)) << a1);
      *(_DWORD *)(v7 + 11968) = v80;
      *v9 = (unsigned __int64)v78;
      *(_BYTE *)(v7 + 11972) = v79;
      if ( v79 > 0 )
        goto LABEL_7;
      if ( (unsigned __int64)v78 >= v74 )
      {
LABEL_75:
        *(_DWORD *)(v7 + 11980) = 1;
      }
      else
      {
        a1 = (unsigned int)-v79;
        *(_DWORD *)(v7 + 11968) = v80 | (*v78 << -v79);
        *v9 = (unsigned __int64)(v78 + 1);
        *(_BYTE *)(v7 + 11972) = v79 + 16;
      }
    }
LABEL_7:
    v87[i + 4] = v32;
  }
  if ( *(_DWORD *)(v7 + 11980) )
    return 0;
  make_table(a1, 0x14u, (__int64)v87, 8u, (char *)v89, (__int64)v88);
  v33 = 0;
LABEL_10:
  if ( v33 < a2 )
  {
    v34 = *(_DWORD *)(v7 + 11968);
    v35 = v89[(unsigned __int64)v34 >> 24];
    if ( (v35 & 0x8000u) == 0 )
      goto LABEL_12;
    v83 = 0x800000;
    while ( 1 )
    {
      v84 = 2 * (__int16)-v35;
      if ( (v34 & v83) != 0 )
      {
        if ( (unsigned int)(v84 + 1) >= 0x5E )
        {
          v35 = 0;
          *(_DWORD *)(v7 + 11980) = 1;
        }
        else
        {
          v35 = v88[v84 + 1];
        }
      }
      else
      {
        if ( (unsigned int)v84 >= 0x5E )
        {
          v35 = 0;
          *(_DWORD *)(v7 + 11980) = 1;
LABEL_12:
          if ( v35 >= 0x18u )
            goto LABEL_20;
          if ( *(_DWORD *)(v7 + 11980) )
            return 0;
          v36 = v34 << v87[v35];
          v37 = *(_BYTE *)(v7 + 11972) - v87[v35];
          *(_DWORD *)(v7 + 11968) = v36;
          *(_BYTE *)(v7 + 11972) = v37;
          if ( v37 > 0 )
            goto LABEL_15;
          v39 = *(_QWORD *)(v7 + 11024);
          v40 = (unsigned __int16 *)*v9;
          if ( *v9 >= v39 )
            goto LABEL_20;
          v41 = v36 | (*v40 << -v37);
          *(_BYTE *)(v7 + 11972) = v37 + 16;
          *(_DWORD *)(v7 + 11968) = v41;
          v42 = v40 + 1;
          *v9 = (unsigned __int64)(v40 + 1);
          if ( (char)(v37 + 16) > 0 )
            goto LABEL_15;
          if ( (unsigned __int64)v42 >= v39 )
          {
LABEL_20:
            *(_DWORD *)(v7 + 11980) = 1;
            return 0;
          }
          v43 = v41 | (*v42 << -(char)(v37 + 16));
          *v9 = (unsigned __int64)(v42 + 1);
          *(_DWORD *)(v7 + 11968) = v43;
          *(_BYTE *)(v7 + 11972) = v37 + 32;
LABEL_15:
          switch ( v35 )
          {
            case 0x11u:
              v49 = *(_DWORD *)(v7 + 11968) >> 28;
              fillbuf(v7, 4);
              v50 = v49 + 4;
              if ( v50 + v33 >= a2 )
                v50 = a2 - v33;
              if ( v50 <= 0 )
                goto LABEL_10;
              memset_0((void *)(a4 + v33), 0, v50);
              do
              {
                --v50;
                ++v33;
              }
              while ( v50 > 0 );
              --v33;
              break;
            case 0x12u:
              v81 = *(_DWORD *)(v7 + 11968) >> 27;
              fillbuf(v7, 5);
              v82 = v81 + 20;
              if ( v82 + v33 >= a2 )
                v82 = a2 - v33;
              if ( v82 <= 0 )
                goto LABEL_10;
              memset_0((void *)(a4 + v33), 0, v82);
              do
              {
                --v82;
                ++v33;
              }
              while ( v82 > 0 );
              --v33;
              break;
            case 0x13u:
              fillbuf(v7, 1);
              v44 = *(_DWORD *)(v7 + 11968);
              v45 = v89[(unsigned __int64)v44 >> 24];
              if ( v45 >= 0 )
                goto LABEL_27;
              v85 = 0x800000;
              while ( 2 )
              {
                v86 = 2 * (__int16)-v45;
                if ( (v44 & v85) != 0 )
                {
                  if ( (unsigned int)(v86 + 1) >= 0x5E )
                  {
                    v45 = 0;
                    *(_DWORD *)(v7 + 11980) = 1;
                  }
                  else
                  {
                    v45 = v88[v86 + 1];
                  }
LABEL_84:
                  v85 >>= 1;
                  if ( v45 >= 0 )
                    goto LABEL_27;
                  continue;
                }
                break;
              }
              if ( (unsigned int)v86 < 0x5E )
              {
                v45 = v88[v86];
                goto LABEL_84;
              }
              *(_DWORD *)(v7 + 11980) = 1;
              v45 = 0;
LABEL_27:
              if ( (unsigned __int16)v45 >= 0x18u )
                goto LABEL_20;
              if ( *(_DWORD *)(v7 + 11980) )
                return 0;
              fillbuf(v7, (unsigned __int8)v87[(unsigned __int16)v45]);
              if ( *(_DWORD *)(v7 + 11980) )
                return 0;
              for ( j = (*(unsigned __int8 *)(v33 + a3) - (unsigned __int16)v45 + 17) % 17;
                    v46 > 0;
                    *(_BYTE *)(v48 + a4) = j )
              {
                if ( v33 >= a2 )
                  break;
                v48 = v33;
                --v46;
                ++v33;
              }
              goto LABEL_10;
            default:
              *(_BYTE *)(v33 + a4) = (*(unsigned __int8 *)(v33 + a3) - v35 + 17) % 17;
              break;
          }
          ++v33;
          goto LABEL_10;
        }
        v35 = v88[v84];
      }
      v83 >>= 1;
      if ( (v35 & 0x8000u) == 0 )
        goto LABEL_12;
    }
  }
  return *(_DWORD *)(v7 + 11980) == 0;
}

```

## disassembly

```asm
0x1800059b0  mov     r11, rsp
0x1800059b3  push    rsi
0x1800059b4  push    rdi
0x1800059b5  push    r12
0x1800059b7  push    r15
0x1800059b9  sub     rsp, 338h
0x1800059c0  mov     rax, cs:__security_cookie
0x1800059c7  xor     rax, rsp
0x1800059ca  mov     [rsp+358h+var_48], rax
0x1800059d2  mov     [r11+10h], rbx
0x1800059d6  mov     r15, r9
0x1800059d9  mov     [r11-28h], rbp
0x1800059dd  mov     r12, r8
0x1800059e0  mov     [r11-30h], r13
0x1800059e4  mov     esi, edx
0x1800059e6  mov     rdi, rcx
0x1800059e9  xor     r9d, r9d
0x1800059ec  nop     dword ptr [rax+00h]
0x1800059f0  mov     edx, [rdi+2EC0h]
0x1800059f6  lea     r13, [rdi+2B08h]
0x1800059fd  movzx   eax, byte ptr [rdi+2EC4h]
0x180005a04  mov     r10d, edx
0x180005a07  sub     al, 4
0x180005a09  shl     edx, 4
0x180005a0c  shr     r10d, 1Ch
0x180005a10  movsx   r8d, al
0x180005a14  mov     [rdi+2EC4h], r8b
0x180005a1b  mov     [rdi+2EC0h], edx
0x180005a21  test    al, al
0x180005a23  jle     loc_180005DC9
0x180005a29  mov     byte ptr [rsp+r9+358h+var_328], r10b
0x180005a2e  sub     r8b, 4
0x180005a32  mov     r10d, edx
0x180005a35  mov     [rdi+2EC4h], r8b
0x180005a3c  shl     edx, 4
0x180005a3f  shr     r10d, 1Ch
0x180005a43  mov     [rdi+2EC0h], edx
0x180005a49  test    r8b, r8b
0x180005a4c  jle     loc_180005E22
0x180005a52  mov     edx, [rdi+2EC0h]
0x180005a58  sub     r8b, 4
0x180005a5c  mov     byte ptr [rsp+r9+358h+var_328+1], r10b
0x180005a61  mov     r10d, edx
0x180005a64  shl     edx, 4
0x180005a67  shr     r10d, 1Ch
0x180005a6b  mov     [rdi+2EC0h], edx
0x180005a71  mov     [rdi+2EC4h], r8b
0x180005a78  test    r8b, r8b
0x180005a7b  jle     loc_180005EA8
0x180005a81  mov     byte ptr [rsp+r9+358h+var_328+2], r10b
0x180005a86  sub     r8b, 4
0x180005a8a  mov     r10d, [rdi+2EC0h]
0x180005a91  mov     r11d, r10d
0x180005a94  shl     r10d, 4
0x180005a98  shr     r11d, 1Ch
0x180005a9c  movsx   edx, r8b
0x180005aa0  mov     [rdi+2EC0h], r10d
0x180005aa7  mov     [rdi+2EC4h], dl
0x180005aad  test    r8b, r8b
0x180005ab0  jle     loc_180005F2E
0x180005ab6  mov     r8d, [rdi+2EC0h]
0x180005abd  sub     dl, 4
0x180005ac0  mov     r10d, r8d
0x180005ac3  mov     byte ptr [rsp+r9+358h+var_328+3], r11b
0x180005ac8  shl     r8d, 4
0x180005acc  shr     r10d, 1Ch
0x180005ad0  mov     [rdi+2EC0h], r8d
0x180005ad7  mov     [rdi+2EC4h], dl
0x180005add  test    dl, dl
0x180005adf  jle     loc_180005F86
0x180005ae5  mov     [rsp+r9+358h+var_324], r10b
0x180005aea  add     r9, 5
0x180005aee  cmp     r9, 14h
0x180005af2  jnz     loc_1800059F0
0x180005af8  cmp     dword ptr [rdi+2ECCh], 0
0x180005aff  mov     [rsp+358h+var_38], r14
0x180005b07  jnz     loc_180005C03
0x180005b0d  lea     rax, [rsp+358h+var_308]
0x180005b12  mov     r9b, 8; int
0x180005b15  mov     [rsp+358h+var_330], rax; __int64
0x180005b1a  lea     r8, [rsp+358h+var_328]; int
0x180005b1f  lea     rax, [rsp+358h+var_248]
0x180005b27  mov     edx, 14h; int
0x180005b2c  mov     [rsp+358h+var_338], rax; void *
0x180005b31  call    make_table
0x180005b36  xor     ebx, ebx
0x180005b38  cmp     ebx, esi
0x180005b3a  jge     loc_18000606A
0x180005b40  mov     r8d, [rdi+2EC0h]
0x180005b47  mov     eax, r8d
0x180005b4a  shr     rax, 18h
0x180005b4e  movzx   eax, [rsp+rax*2+358h+var_248]
0x180005b56  test    ax, ax
0x180005b59  js      loc_18000607A
0x180005b5f  cmp     ax, 18h
0x180005b63  jnb     loc_180005BF9
0x180005b69  cmp     dword ptr [rdi+2ECCh], 0
0x180005b70  jnz     loc_180005C03
0x180005b76  movzx   ecx, ax
0x180005b79  movzx   edx, byte ptr [rsp+rcx+358h+var_328]
0x180005b7e  movzx   ecx, dl
0x180005b81  shl     r8d, cl
0x180005b84  movzx   ecx, byte ptr [rdi+2EC4h]
0x180005b8b  sub     cl, dl
0x180005b8d  mov     [rdi+2EC0h], r8d
0x180005b94  movsx   r9d, cl
0x180005b98  mov     [rdi+2EC4h], cl
0x180005b9e  test    cl, cl
0x180005ba0  jle     loc_180005C43
0x180005ba6  cmp     ax, 11h
0x180005baa  jz      loc_180005D8D
0x180005bb0  cmp     ax, 12h
0x180005bb4  jz      loc_180006016
0x180005bba  cmp     ax, 13h
0x180005bbe  jz      loc_180005CD0
0x180005bc4  movzx   ecx, ax
0x180005bc7  mov     eax, 78787879h
0x180005bcc  movsxd  r9, ebx
0x180005bcf  movzx   r8d, byte ptr [r9+r12]
0x180005bd4  sub     r8d, ecx
0x180005bd7  add     r8d, 11h
0x180005bdb  imul    r8d
0x180005bde  sar     edx, 3
0x180005be1  mov     eax, edx
0x180005be3  shr     eax, 1Fh
0x180005be6  add     edx, eax
0x180005be8  imul    eax, edx, 11h
0x180005beb  sub     r8d, eax
0x180005bee  mov     [r9+r15], r8b
0x180005bf2  inc     ebx
0x180005bf4  jmp     loc_180005B38
0x180005bf9  mov     dword ptr [rdi+2ECCh], 1
0x180005c03  xor     eax, eax
0x180005c05  mov     r14, [rsp+358h+var_38]
0x180005c0d  mov     r13, [rsp+358h+var_30]
0x180005c15  mov     rbp, [rsp+358h+var_28]
0x180005c1d  mov     rbx, [rsp+358h+arg_8]
0x180005c25  mov     rcx, [rsp+358h+var_48]
0x180005c2d  xor     rcx, rsp; StackCookie
0x180005c30  call    __security_check_cookie
0x180005c35  add     rsp, 338h
0x180005c3c  pop     r15
0x180005c3e  pop     r12
0x180005c40  pop     rdi
0x180005c41  pop     rsi
0x180005c42  retn
0x180005c43  mov     r11, [rdi+2B10h]
0x180005c4a  mov     rdx, [r13+0]
0x180005c4e  cmp     rdx, r11
0x180005c51  jnb     short loc_180005BF9
0x180005c53  movzx   ecx, byte ptr [rdx]
0x180005c56  movzx   r10d, byte ptr [rdx+1]
0x180005c5b  shl     r10d, 8
0x180005c5f  or      r10d, ecx
0x180005c62  mov     ecx, r9d
0x180005c65  neg     ecx
0x180005c67  add     r9b, 10h
0x180005c6b  shl     r10d, cl
0x180005c6e  or      r10d, r8d
0x180005c71  mov     [rdi+2EC4h], r9b
0x180005c78  mov     [rdi+2EC0h], r10d
0x180005c7f  lea     r8, [rdx+2]
0x180005c83  mov     [r13+0], r8
0x180005c87  test    r9b, r9b
0x180005c8a  jg      loc_180005BA6
0x180005c90  cmp     r8, r11
0x180005c93  jnb     loc_180005BF9
0x180005c99  movzx   ecx, byte ptr [r8]
0x180005c9d  movzx   edx, byte ptr [r8+1]
0x180005ca2  shl     edx, 8
0x180005ca5  or      edx, ecx
0x180005ca7  movsx   ecx, r9b
0x180005cab  neg     ecx
0x180005cad  shl     edx, cl
0x180005caf  lea     rcx, [r8+2]
0x180005cb3  or      edx, r10d
0x180005cb6  mov     [r13+0], rcx
0x180005cba  add     r9b, 10h
0x180005cbe  mov     [rdi+2EC0h], edx
0x180005cc4  mov     [rdi+2EC4h], r9b
0x180005ccb  jmp     loc_180005BA6
0x180005cd0  mov     r11d, [rdi+2EC0h]
0x180005cd7  mov     edx, 1
0x180005cdc  mov     rcx, rdi
0x180005cdf  shr     r11d, 1Fh
0x180005ce3  call    fillbuf
0x180005ce8  add     r11d, 4
0x180005cec  mov     ecx, esi
0x180005cee  sub     ecx, ebx
0x180005cf0  lea     eax, [r11+rbx]
0x180005cf4  cmp     eax, esi
0x180005cf6  cmovge  r11d, ecx
0x180005cfa  mov     ecx, [rdi+2EC0h]
0x180005d00  mov     eax, ecx
0x180005d02  shr     rax, 18h
0x180005d06  movzx   ebp, [rsp+rax*2+358h+var_248]
0x180005d0e  test    bp, bp
0x180005d11  js      loc_180006173
0x180005d17  cmp     bp, 18h
0x180005d1b  jnb     loc_180005BF9
0x180005d21  cmp     dword ptr [rdi+2ECCh], 0
0x180005d28  jnz     loc_180005C03
0x180005d2e  movzx   eax, bp
0x180005d31  mov     rcx, rdi
0x180005d34  movzx   edx, byte ptr [rsp+rax+358h+var_328]
0x180005d39  call    fillbuf
0x180005d3e  cmp     dword ptr [rdi+2ECCh], 0
0x180005d45  jnz     loc_180005C03
0x180005d4b  movsxd  rax, ebx
0x180005d4e  movzx   ecx, byte ptr [rax+r12]
0x180005d53  movzx   eax, bp
0x180005d56  sub     ecx, eax
0x180005d58  mov     eax, 78787879h
0x180005d5d  add     ecx, 11h
0x180005d60  imul    ecx
0x180005d62  sar     edx, 3
0x180005d65  mov     eax, edx
0x180005d67  shr     eax, 1Fh
0x180005d6a  add     edx, eax
0x180005d6c  imul    eax, edx, 11h
0x180005d6f  sub     ecx, eax
0x180005d71  test    r11d, r11d
0x180005d74  jle     short loc_180005DC0
0x180005d76  cmp     ebx, esi
0x180005d78  jge     short loc_180005DC0
0x180005d7a  movsxd  rax, ebx
0x180005d7d  dec     r11d
0x180005d80  inc     ebx
0x180005d82  mov     [rax+r15], cl
0x180005d86  test    r11d, r11d
0x180005d89  jg      short loc_180005D76
0x180005d8b  jmp     short loc_180005DC0
0x180005d8d  mov     r14d, [rdi+2EC0h]
0x180005d94  mov     edx, 4
0x180005d99  mov     rcx, rdi
0x180005d9c  shr     r14d, 1Ch
0x180005da0  call    fillbuf
0x180005da5  add     r14d, 4
0x180005da9  mov     ecx, esi
0x180005dab  sub     ecx, ebx
0x180005dad  lea     eax, [r14+rbx]
0x180005db1  cmp     eax, esi
0x180005db3  cmovge  r14d, ecx
0x180005db7  test    r14d, r14d
0x180005dba  jg      loc_18000620E
0x180005dc0  dec     ebx
0x180005dc2  inc     ebx
0x180005dc4  jmp     loc_180005B38
0x180005dc9  mov     rbp, [rdi+2B10h]
0x180005dd0  mov     rbx, [r13+0]
0x180005dd4  cmp     rbx, rbp
0x180005dd7  jnb     loc_1800060C0
0x180005ddd  movzx   r11d, byte ptr [rbx+1]
0x180005de2  mov     ecx, r8d
0x180005de5  movzx   eax, byte ptr [rbx]
0x180005de8  neg     ecx
0x180005dea  shl     r11d, 8
0x180005dee  add     rbx, 2
0x180005df2  or      r11d, eax
0x180005df5  mov     [r13+0], rbx
0x180005df9  shl     r11d, cl
0x180005dfc  add     r8b, 10h
0x180005e00  or      r11d, edx
0x180005e03  mov     [rdi+2EC4h], r8b
0x180005e0a  mov     [rdi+2EC0h], r11d
0x180005e11  test    r8b, r8b
0x180005e14  jle     loc_18000610B
0x180005e1a  mov     edx, r11d
0x180005e1d  jmp     loc_180005A29
0x180005e22  mov     rbp, [rdi+2B10h]
0x180005e29  mov     r11, [r13+0]
0x180005e2d  cmp     r11, rbp
0x180005e30  jnb     loc_1800060CF
0x180005e36  movzx   ebx, byte ptr [r11+1]
0x180005e3b  movzx   eax, byte ptr [r11]
0x180005e3f  add     r11, 2
0x180005e43  shl     ebx, 8
0x180005e46  or      ebx, eax
0x180005e48  movsx   ecx, r8b
0x180005e4c  neg     ecx
0x180005e4e  add     r8b, 10h
0x180005e52  shl     ebx, cl
0x180005e54  or      ebx, edx
0x180005e56  mov     [rdi+2EC0h], ebx
0x180005e5c  mov     [r13+0], r11
0x180005e60  mov     [rdi+2EC4h], r8b
0x180005e67  test    r8b, r8b
0x180005e6a  jg      loc_180005A52
0x180005e70  cmp     r11, rbp
0x180005e73  jnb     loc_1800061BF
0x180005e79  movzx   eax, byte ptr [r11]
0x180005e7d  movzx   edx, byte ptr [r11+1]
0x180005e82  shl     edx, 8
0x180005e85  or      edx, eax
0x180005e87  movsx   ecx, r8b
0x180005e8b  neg     ecx
0x180005e8d  lea     rax, [r11+2]
0x180005e91  shl     edx, cl
0x180005e93  or      edx, ebx
0x180005e95  mov     [rdi+2EC0h], edx
  ... truncated ...
```
