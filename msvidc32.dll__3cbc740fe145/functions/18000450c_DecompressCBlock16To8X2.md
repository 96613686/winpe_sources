# DecompressCBlock16To8X2

- ea: `0x18000450c`
- end: `0x180004afc`
- name: `DecompressCBlock16To8X2`
- size: `1520`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005860`

## callees

- `0x18000450c`

## pseudocode

```c
unsigned __int16 *__fastcall DecompressCBlock16To8X2(int *a1, unsigned __int16 *a2, unsigned int *a3, int a4, int *a5)
{
  __int64 v5; // rdi
  unsigned int *v6; // r11
  unsigned __int16 *v7; // r10
  int *v8; // rsi
  unsigned int v9; // edx
  unsigned __int16 v10; // bx
  __int16 v11; // ax
  __int64 v12; // r8
  unsigned __int16 v13; // cx
  unsigned __int16 v14; // r8
  __int64 v15; // rbx
  unsigned int v16; // r11d
  int v17; // r9d
  char v18; // dl
  __int64 v19; // rdx
  int v20; // r8d
  __int64 v21; // r12
  unsigned int v22; // r14d
  char v23; // r15
  unsigned int v24; // edx
  __int16 v25; // ax
  __int16 v26; // ax
  __int16 v27; // ax
  unsigned __int16 v28; // cx
  __int64 v29; // r12
  int *v30; // rdi
  int *v31; // r11
  unsigned int v32; // ebx
  int *v33; // r9
  __int64 v34; // rcx
  __int64 v35; // rax
  int v36; // r13d
  int v37; // edx
  int v38; // eax
  int *v39; // rsi
  unsigned int v40; // r14d
  __int64 v41; // rbp
  __int64 v42; // rcx
  __int64 v43; // rax
  int v44; // r13d
  int v45; // edx
  int v46; // eax
  __int64 v47; // r15
  unsigned int v48; // r9d
  int v49; // eax
  __int64 v50; // rdi
  unsigned int v51; // r11d
  int *v52; // r8
  int *v53; // r12
  int *v54; // r13
  __int64 v55; // rcx
  __int64 v56; // rax
  int v57; // edx
  int v58; // eax
  int v60; // [rsp+0h] [rbp-78h]
  int v61; // [rsp+0h] [rbp-78h]
  int v62; // [rsp+0h] [rbp-78h]
  int v63; // [rsp+4h] [rbp-74h]
  int v64; // [rsp+4h] [rbp-74h]
  int v65; // [rsp+8h] [rbp-70h]
  int v66; // [rsp+8h] [rbp-70h]
  unsigned __int16 v67; // [rsp+Ch] [rbp-6Ch]
  unsigned __int16 v68; // [rsp+10h] [rbp-68h]
  int v69; // [rsp+10h] [rbp-68h]
  unsigned __int16 v70; // [rsp+14h] [rbp-64h]
  unsigned __int16 v71; // [rsp+14h] [rbp-64h]
  unsigned __int16 v72; // [rsp+18h] [rbp-60h]
  __int64 v73; // [rsp+20h] [rbp-58h]
  __int64 v74; // [rsp+20h] [rbp-58h]
  __int64 v75; // [rsp+28h] [rbp-50h]
  int *v76; // [rsp+30h] [rbp-48h]
  int *v77; // [rsp+80h] [rbp+8h]
  unsigned __int16 *v78; // [rsp+88h] [rbp+10h]
  unsigned __int16 v80; // [rsp+A0h] [rbp+28h]
  unsigned int v81; // [rsp+A0h] [rbp+28h]

  v78 = a2;
  v77 = a1;
  v5 = a4;
  v6 = a3;
  v7 = a2;
  v8 = a1;
  if ( *a5 > 0 )
  {
    --*a5;
    return v7;
  }
  v9 = *a3;
  if ( *a3 <= 1 )
  {
    v10 = 0;
LABEL_5:
    v11 = 0;
    goto LABEL_6;
  }
  v14 = *v7;
  v9 -= 2;
  ++v7;
  *v6 = v9;
  v78 = v7;
  if ( (v14 & 0x8000u) != 0 )
  {
    if ( (v14 & 0xFC00) == 0x8400 )
    {
      *a5 = (v14 & 0x3FF) - 1;
    }
    else
    {
      v15 = lpLookup;
      v16 = 0;
      v17 = *(unsigned __int16 *)(lpScale + 2LL * (v14 & 0x7FFF));
      do
      {
        v18 = v16++;
        v19 = 2LL * (v18 & 3);
        v20 = *(unsigned __int8 *)(v17 + ditherr[2 * v19] + v15)
            | ((*(unsigned __int8 *)(v17 + ditherr[2 * v19 + 1] + v15)
              | ((*(unsigned __int8 *)(v17 + ditherr[2 * v19 + 2] + v15)
                | (*(unsigned __int8 *)(v17 + ditherr[2 * v19 + 3] + v15) << 8)) << 8)) << 8);
        *v8 = v20;
        v8[1] = v20;
        v8 = (int *)((char *)v8 + v5);
      }
      while ( v16 < 8 );
    }
    return v7;
  }
  v10 = v14;
  if ( v9 <= 1 )
    goto LABEL_5;
  if ( (*v7 & 0x8000u) == 0 )
  {
    v11 = *v7++;
    v9 -= 2;
    v78 = v7;
    *v6 = v9;
LABEL_6:
    v12 = lpScale;
    v80 = *(_WORD *)(lpScale + 2LL * (v11 & 0x7FFF));
    if ( v9 > 1 )
    {
      v13 = *v7;
      *v6 = v9 - 2;
      v78 = v7 + 1;
    }
    else
    {
      v13 = 0;
    }
    v47 = a4;
    v48 = 0;
    v71 = *(_WORD *)(v12 + 2LL * (v13 & 0x7FFF));
    v49 = 2 * v5;
    v50 = lpLookup;
    v74 = v49;
    do
    {
      v51 = 0;
      v52 = v8;
      v53 = &ditherr[4 * (v48 & 3)];
      v54 = &ditherr[4 * (((_BYTE)v48 + 1) & 3)];
      do
      {
        v55 = v51 & 3;
        v56 = ((_BYTE)v51 + 1) & 3;
        v69 = v54[v55];
        v57 = v53[v56];
        v62 = v54[v56];
        if ( (v10 & 1) != 0 )
        {
          *(_BYTE *)v52 = *(_BYTE *)(v80 + v53[v55] + v50);
          *((_BYTE *)v52 + v47) = *(_BYTE *)(v80 + v69 + v50);
          *((_BYTE *)v52 + 1) = *(_BYTE *)(v80 + v57 + v50);
          v58 = v80 + v62;
        }
        else
        {
          *(_BYTE *)v52 = *(_BYTE *)(v71 + v53[v55] + v50);
          *((_BYTE *)v52 + v47) = *(_BYTE *)(v71 + v69 + v50);
          *((_BYTE *)v52 + 1) = *(_BYTE *)(v57 + v71 + v50);
          v58 = v71 + v62;
        }
        v51 += 2;
        v10 >>= 1;
        *((_BYTE *)v52 + v47 + 1) = *(_BYTE *)(v58 + v50);
        v52 = (int *)((char *)v52 + 2);
      }
      while ( v51 < 8 );
      v8 = (int *)((char *)v8 + v74);
      v48 += 2;
    }
    while ( v48 < 8 );
    return v78;
  }
  v21 = lpScale;
  v73 = 2 * a4;
  v22 = 0;
  v72 = 0;
  v70 = 0;
  v68 = 0;
  v67 = 0;
  v81 = 0;
  v75 = a4;
  do
  {
    v23 = v22;
    if ( (v22 & 0xFFFFFFFB) == 0 )
    {
      v24 = *v6;
      if ( *v6 > 1 )
      {
        v25 = *v7++;
        v24 -= 2;
        *v6 = v24;
      }
      else
      {
        v25 = 0;
      }
      v72 = *(_WORD *)(v21 + 2LL * (v25 & 0x7FFF));
      if ( v24 > 1 )
      {
        v26 = *v7++;
        v24 -= 2;
        *v6 = v24;
      }
      else
      {
        v26 = 0;
      }
      v70 = *(_WORD *)(v21 + 2LL * (v26 & 0x7FFF));
      if ( v24 > 1 )
      {
        v27 = *v7++;
        v24 -= 2;
        *v6 = v24;
      }
      else
      {
        v27 = 0;
      }
      v68 = *(_WORD *)(v21 + 2LL * (v27 & 0x7FFF));
      if ( v24 > 1 )
      {
        v28 = *v7;
        *v6 = v24 - 2;
        ++v7;
      }
      else
      {
        v28 = 0;
      }
      v67 = *(_WORD *)(v21 + 2LL * (v28 & 0x7FFF));
    }
    v29 = lpLookup;
    v30 = v8;
    v31 = &ditherr[4 * (v22 & 3)];
    v32 = 0;
    v33 = &ditherr[4 * (((_BYTE)v22 + 1) & 3)];
    do
    {
      v34 = v32 & 3;
      v35 = ((_BYTE)v32 + 1) & 3;
      v36 = v31[v34];
      v65 = v33[v34];
      v60 = v33[v35];
      v63 = v31[v35];
      if ( (v14 & 1) != 0 )
      {
        v37 = v72;
        v38 = v72 + v36;
      }
      else
      {
        v37 = v70;
        v38 = v70 + v36;
      }
      v32 += 2;
      v14 >>= 1;
      *(_BYTE *)v30 = *(_BYTE *)(v38 + v29);
      *((_BYTE *)v30 + v75) = *(_BYTE *)(v37 + v65 + v29);
      *((_BYTE *)v30 + 1) = *(_BYTE *)(v37 + v63 + v29);
      *((_BYTE *)v30 + v75 + 1) = *(_BYTE *)(v37 + v60 + v29);
      v30 = (int *)((char *)v30 + 2);
    }
    while ( v32 < 4 );
    v6 = a3;
    v39 = v77;
    v40 = v81;
    v21 = lpScale;
    if ( v32 < 8 )
    {
      v76 = &ditherr[4 * (v23 & 3)];
      v41 = lpLookup;
      do
      {
        v42 = v32 & 3;
        v43 = ((_BYTE)v32 + 1) & 3;
        v44 = v76[v42];
        v61 = v33[v42];
        v66 = v33[v43];
        v64 = v76[v43];
        if ( (v14 & 1) != 0 )
        {
          v45 = v68;
          v46 = v68 + v44;
        }
        else
        {
          v45 = v67;
          v46 = v67 + v44;
        }
        v32 += 2;
        v14 >>= 1;
        *(_BYTE *)v30 = *(_BYTE *)(v46 + v41);
        *((_BYTE *)v30 + v75) = *(_BYTE *)(v45 + v61 + v41);
        *((_BYTE *)v30 + 1) = *(_BYTE *)(v45 + v64 + v41);
        *((_BYTE *)v30 + v75 + 1) = *(_BYTE *)(v45 + v66 + v41);
        v30 = (int *)((char *)v30 + 2);
      }
      while ( v32 < 8 );
      v6 = a3;
      v39 = v77;
      v40 = v81;
      v21 = lpScale;
    }
    v8 = (int *)((char *)v39 + v73);
    v22 = v40 + 2;
    v77 = v8;
    v81 = v22;
  }
  while ( v22 < 8 );
  return v7;
}

```

## disassembly

```asm
0x18000450c  mov     rax, rsp
0x18000450f  mov     [rax+20h], rbx
0x180004513  mov     [rax+18h], r8
0x180004517  mov     [rax+10h], rdx
0x18000451b  mov     [rax+8], rcx
0x18000451f  push    rbp
0x180004520  push    rsi
0x180004521  push    rdi
0x180004522  push    r12
0x180004524  push    r13
0x180004526  push    r14
0x180004528  push    r15
0x18000452a  sub     rsp, 40h
0x18000452e  mov     rbx, [rsp+78h+arg_20]
0x180004536  xor     r13d, r13d
0x180004539  movsxd  rdi, r9d
0x18000453c  mov     r11, r8
0x18000453f  mov     r10, rdx
0x180004542  mov     rsi, rcx
0x180004545  mov     eax, [rbx]
0x180004547  test    eax, eax
0x180004549  jle     short loc_180004554
0x18000454b  dec     eax
0x18000454d  mov     [rbx], eax
0x18000454f  jmp     loc_180004AE1
0x180004554  mov     edx, [r8]
0x180004557  cmp     edx, 1
0x18000455a  ja      short loc_180004593
0x18000455c  mov     ebx, r13d
0x18000455f  mov     eax, r13d
0x180004562  mov     r8, cs:lpScale
0x180004569  mov     r9d, 7FFFh
0x18000456f  movzx   eax, ax
0x180004572  and     rax, r9
0x180004575  movzx   eax, word ptr [r8+rax*2]
0x18000457a  mov     word ptr [rsp+78h+arg_20], ax
0x180004582  cmp     edx, 1
0x180004585  ja      loc_18000498D
0x18000458b  mov     ecx, r13d
0x18000458e  jmp     loc_1800049A3
0x180004593  movzx   r8d, word ptr [r10]
0x180004597  add     edx, 0FFFFFFFEh
0x18000459a  add     r10, 2
0x18000459e  mov     [r11], edx
0x1800045a1  mov     [rsp+78h+arg_8], r10
0x1800045a9  test    r8w, r8w
0x1800045ad  jns     loc_180004666
0x1800045b3  movzx   ecx, r8w
0x1800045b7  mov     eax, ecx
0x1800045b9  and     eax, 0FFFFFC00h
0x1800045be  cmp     eax, 8400h
0x1800045c3  jnz     short loc_1800045D4
0x1800045c5  and     ecx, 3FFh
0x1800045cb  dec     ecx
0x1800045cd  mov     [rbx], ecx
0x1800045cf  jmp     loc_180004AE1
0x1800045d4  mov     rax, cs:lpScale
0x1800045db  lea     rbp, ditherr
0x1800045e2  mov     rbx, cs:lpLookup
0x1800045e9  mov     r9d, 7FFFh
0x1800045ef  and     r8, r9
0x1800045f2  mov     r11d, r13d
0x1800045f5  movzx   r9d, word ptr [rax+r8*2]
0x1800045fa  mov     edx, r11d
0x1800045fd  inc     r11d
0x180004600  and     edx, 3
0x180004603  add     rdx, rdx
0x180004606  mov     eax, [rbp+rdx*8+0Ch]
0x18000460a  add     eax, r9d
0x18000460d  cdqe
0x18000460f  movzx   r8d, byte ptr [rax+rbx]
0x180004614  mov     eax, [rbp+rdx*8+8]
0x180004618  shl     r8d, 8
0x18000461c  add     eax, r9d
0x18000461f  cdqe
0x180004621  movzx   ecx, byte ptr [rax+rbx]
0x180004625  mov     eax, [rbp+rdx*8+4]
0x180004629  or      r8d, ecx
0x18000462c  shl     r8d, 8
0x180004630  add     eax, r9d
0x180004633  cdqe
0x180004635  movzx   ecx, byte ptr [rax+rbx]
0x180004639  or      r8d, ecx
0x18000463c  mov     ecx, [rbp+rdx*8+0]
0x180004640  add     ecx, r9d
0x180004643  shl     r8d, 8
0x180004647  movsxd  rcx, ecx
0x18000464a  movzx   edx, byte ptr [rcx+rbx]
0x18000464e  or      r8d, edx
0x180004651  mov     [rsi], r8d
0x180004654  mov     [rsi+4], r8d
0x180004658  add     rsi, rdi
0x18000465b  cmp     r11d, 8
0x18000465f  jb      short loc_1800045FA
0x180004661  jmp     loc_180004AE1
0x180004666  mov     rcx, r10
0x180004669  movzx   ebx, r8w
0x18000466d  cmp     edx, 1
0x180004670  jbe     loc_18000455F
0x180004676  cmp     [r10], r13w
0x18000467a  jge     loc_180004973
0x180004680  mov     r12, cs:lpScale
0x180004687  lea     eax, [rdi+rdi]
0x18000468a  cdqe
0x18000468c  lea     rbp, ditherr
0x180004693  mov     [rsp+78h+var_58], rax
0x180004698  mov     r14d, r13d
0x18000469b  mov     dword ptr [rsp+78h+var_60], r13d
0x1800046a0  mov     r9d, 7FFFh
0x1800046a6  mov     [rsp+78h+var_64], r13d
0x1800046ab  mov     [rsp+78h+var_68], r13d
0x1800046b0  mov     [rsp+78h+var_6C], r13d
0x1800046b5  mov     dword ptr [rsp+78h+arg_20], r13d
0x1800046bd  mov     [rsp+78h+var_50], rdi
0x1800046c2  mov     r15d, r14d
0x1800046c5  test    r14d, 0FFFFFFFBh
0x1800046cc  jnz     loc_180004771
0x1800046d2  mov     edx, [r11]
0x1800046d5  cmp     edx, 1
0x1800046d8  ja      short loc_1800046DF
0x1800046da  mov     eax, r13d
0x1800046dd  jmp     short loc_1800046ED
0x1800046df  movzx   eax, word ptr [r10]
0x1800046e3  add     r10, 2
0x1800046e7  add     edx, 0FFFFFFFEh
0x1800046ea  mov     [r11], edx
0x1800046ed  movzx   eax, ax
0x1800046f0  and     rax, r9
0x1800046f3  movzx   eax, word ptr [r12+rax*2]
0x1800046f8  mov     dword ptr [rsp+78h+var_60], eax
0x1800046fc  cmp     edx, 1
0x1800046ff  ja      short loc_180004706
0x180004701  mov     eax, r13d
0x180004704  jmp     short loc_180004714
0x180004706  movzx   eax, word ptr [r10]
0x18000470a  add     r10, 2
0x18000470e  add     edx, 0FFFFFFFEh
0x180004711  mov     [r11], edx
0x180004714  movzx   eax, ax
0x180004717  and     rax, r9
0x18000471a  movzx   eax, word ptr [r12+rax*2]
0x18000471f  mov     [rsp+78h+var_64], eax
0x180004723  cmp     edx, 1
0x180004726  ja      short loc_18000472D
0x180004728  mov     eax, r13d
0x18000472b  jmp     short loc_18000473B
0x18000472d  movzx   eax, word ptr [r10]
0x180004731  add     r10, 2
0x180004735  add     edx, 0FFFFFFFEh
0x180004738  mov     [r11], edx
0x18000473b  movzx   eax, ax
0x18000473e  and     rax, r9
0x180004741  movzx   eax, word ptr [r12+rax*2]
0x180004746  mov     [rsp+78h+var_68], eax
0x18000474a  cmp     edx, 1
0x18000474d  ja      short loc_180004754
0x18000474f  mov     ecx, r13d
0x180004752  jmp     short loc_180004762
0x180004754  movzx   ecx, word ptr [r10]
0x180004758  lea     eax, [rdx-2]
0x18000475b  mov     [r11], eax
0x18000475e  add     r10, 2
0x180004762  movzx   eax, cx
0x180004765  and     rax, r9
0x180004768  movzx   eax, word ptr [r12+rax*2]
0x18000476d  mov     [rsp+78h+var_6C], eax
0x180004771  mov     r12, cs:lpLookup
0x180004778  lea     r9d, [r14+1]
0x18000477c  mov     r14d, [rsp+78h+var_64]
0x180004781  mov     r11, r15
0x180004784  and     r11d, 3
0x180004788  and     r9d, 3
0x18000478c  shl     r11, 4
0x180004790  mov     rdi, rsi
0x180004793  mov     esi, dword ptr [rsp+78h+var_60]
0x180004797  add     r11, rbp
0x18000479a  shl     r9, 4
0x18000479e  mov     ebx, r13d
0x1800047a1  add     r9, rbp
0x1800047a4  mov     [rsp+78h+var_48], r11
0x1800047a9  mov     rbp, [rsp+78h+var_50]
0x1800047ae  mov     [rsp+78h+var_40], r9
0x1800047b3  mov     ecx, ebx
0x1800047b5  lea     eax, [rbx+1]
0x1800047b8  and     ecx, 3
0x1800047bb  and     eax, 3
0x1800047be  mov     r13d, [r11+rcx*4]
0x1800047c2  mov     ecx, [r9+rcx*4]
0x1800047c6  mov     [rsp+78h+var_70], ecx
0x1800047ca  mov     ecx, [r11+rax*4]
0x1800047ce  mov     eax, [r9+rax*4]
0x1800047d2  mov     [rsp+78h+var_78], eax
0x1800047d5  mov     [rsp+78h+var_74], ecx
0x1800047d9  test    r8b, 1
0x1800047dd  jz      short loc_1800047E8
0x1800047df  movzx   edx, si
0x1800047e2  lea     eax, [rdx+r13]
0x1800047e6  jmp     short loc_1800047F0
0x1800047e8  movzx   edx, r14w
0x1800047ec  lea     eax, [rdx+r13]
0x1800047f0  movsxd  rcx, eax
0x1800047f3  add     ebx, 2
0x1800047f6  shr     r8w, 1
0x1800047fa  mov     al, [rcx+r12]
0x1800047fe  mov     [rdi], al
0x180004800  mov     eax, [rsp+78h+var_70]
0x180004804  add     eax, edx
0x180004806  movsxd  rcx, eax
0x180004809  mov     al, [rcx+r12]
0x18000480d  mov     [rdi+rbp], al
0x180004810  mov     eax, [rsp+78h+var_74]
0x180004814  add     eax, edx
0x180004816  movsxd  rcx, eax
0x180004819  mov     al, [rcx+r12]
0x18000481d  mov     [rdi+1], al
0x180004820  mov     eax, [rsp+78h+var_78]
0x180004823  add     eax, edx
0x180004825  movsxd  rcx, eax
0x180004828  mov     al, [rcx+r12]
0x18000482c  mov     [rdi+rbp+1], al
0x180004830  add     rdi, 2
0x180004834  cmp     ebx, 4
0x180004837  jb      loc_1800047B3
0x18000483d  mov     r11, [rsp+78h+arg_10]
0x180004845  mov     r9d, 7FFFh
0x18000484b  mov     rsi, [rsp+78h+arg_0]
0x180004853  lea     rbp, ditherr
0x18000485a  mov     r14d, dword ptr [rsp+78h+arg_20]
0x180004862  mov     r12, cs:lpScale
0x180004869  cmp     ebx, 8
0x18000486c  jnb     loc_180004945
0x180004872  mov     r11, [rsp+78h+var_48]
0x180004877  mov     r12, [rsp+78h+var_40]
0x18000487c  mov     rbp, cs:lpLookup
0x180004883  mov     r9, [rsp+78h+var_50]
0x180004888  mov     r14d, [rsp+78h+var_6C]
0x18000488d  mov     esi, [rsp+78h+var_68]
0x180004891  mov     ecx, ebx
0x180004893  lea     eax, [rbx+1]
0x180004896  and     ecx, 3
0x180004899  and     eax, 3
0x18000489c  mov     r13d, [r11+rcx*4]
0x1800048a0  mov     ecx, [r12+rcx*4]
0x1800048a4  mov     [rsp+78h+var_78], ecx
0x1800048a7  mov     ecx, [r11+rax*4]
0x1800048ab  mov     eax, [r12+rax*4]
0x1800048af  mov     [rsp+78h+var_70], eax
0x1800048b3  mov     [rsp+78h+var_74], ecx
0x1800048b7  test    r8b, 1
0x1800048bb  jz      short loc_1800048C6
0x1800048bd  movzx   edx, si
0x1800048c0  lea     eax, [rdx+r13]
0x1800048c4  jmp     short loc_1800048CE
0x1800048c6  movzx   edx, r14w
0x1800048ca  lea     eax, [rdx+r13]
0x1800048ce  movsxd  rcx, eax
0x1800048d1  add     ebx, 2
0x1800048d4  shr     r8w, 1
0x1800048d8  mov     al, [rcx+rbp]
0x1800048db  mov     [rdi], al
0x1800048dd  mov     eax, [rsp+78h+var_78]
0x1800048e0  add     eax, edx
0x1800048e2  movsxd  rcx, eax
0x1800048e5  mov     al, [rcx+rbp]
0x1800048e8  mov     [r9+rdi], al
0x1800048ec  mov     eax, [rsp+78h+var_74]
0x1800048f0  add     eax, edx
0x1800048f2  movsxd  rcx, eax
0x1800048f5  mov     al, [rcx+rbp]
0x1800048f8  mov     [rdi+1], al
0x1800048fb  mov     eax, [rsp+78h+var_70]
0x1800048ff  add     eax, edx
0x180004901  movsxd  rcx, eax
0x180004904  mov     al, [rcx+rbp]
0x180004907  mov     [r9+rdi+1], al
0x18000490c  add     rdi, 2
0x180004910  cmp     ebx, 8
0x180004913  jb      loc_180004891
0x180004919  mov     r11, [rsp+78h+arg_10]
0x180004921  lea     rbp, ditherr
0x180004928  mov     rsi, [rsp+78h+arg_0]
0x180004930  mov     r9d, 7FFFh
0x180004936  mov     r14d, dword ptr [rsp+78h+arg_20]
0x18000493e  mov     r12, cs:lpScale
0x180004945  add     rsi, [rsp+78h+var_58]
0x18000494a  add     r14d, 2
0x18000494e  mov     [rsp+78h+arg_0], rsi
0x180004956  mov     r13d, 0
0x18000495c  mov     dword ptr [rsp+78h+arg_20], r14d
0x180004964  cmp     r14d, 8
0x180004968  jb      loc_1800046C2
0x18000496e  jmp     loc_180004AE1
0x180004973  movzx   eax, word ptr [rcx]
0x180004976  add     r10, 2
0x18000497a  add     edx, 0FFFFFFFEh
0x18000497d  mov     [rsp+78h+arg_8], r10
0x180004985  mov     [r11], edx
0x180004988  jmp     loc_180004562
0x18000498d  movzx   ecx, word ptr [r10]
0x180004991  lea     eax, [rdx-2]
  ... truncated ...
```
