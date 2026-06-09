# n_fold_internal

- ea: `0x180001010`
- end: `0x180001447`
- name: `n_fold_internal`
- size: `1079`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800060a0`
- `0x180006350`

## callees

- `0x180001010`
- `0x180008415`

## pseudocode

```c
char __fastcall n_fold_internal(_OWORD *a1, unsigned int a2, const void *a3, __int64 a4, __int64 a5)
{
  __int64 v5; // r13
  size_t v7; // r14
  unsigned int v8; // r9d
  unsigned int v9; // eax
  unsigned int v10; // r10d
  int v11; // edx
  signed int v12; // edi
  unsigned int v13; // r12d
  unsigned int v14; // eax
  unsigned __int8 *v15; // rbx
  unsigned int v16; // r9d
  __int64 v17; // r8
  char *v18; // r11
  char v19; // r10
  __int64 v20; // rdx
  __int64 v21; // r8
  char v22; // r10
  __int64 v23; // rdx
  char v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rcx
  _OWORD *v27; // r10
  int v28; // r15d
  unsigned int v29; // r12d
  int v30; // edx
  char *v31; // rbx
  int v32; // r11d
  unsigned int v33; // eax
  __int64 v34; // rcx
  BOOL v35; // r9d
  int v36; // edx
  int v37; // eax
  unsigned int v38; // r10d
  char v39; // dl
  BOOL v40; // r9d
  int v41; // eax
  int v42; // edx
  unsigned int v43; // r10d
  char v44; // dl
  BOOL v45; // r9d
  int v46; // eax
  int v47; // edx
  unsigned int v48; // r10d
  char v49; // dl
  BOOL v50; // r9d
  int v51; // eax
  int v52; // edx
  unsigned int v53; // r10d
  char v54; // dl
  BOOL v55; // r9d
  int v56; // edx
  unsigned int v57; // r8d
  char v58; // dl
  int v59; // r8d
  _BYTE *v60; // rdx
  int v61; // ecx
  unsigned int v62; // ecx
  unsigned __int8 v63; // r10
  unsigned int v64; // ecx
  int v65; // ecx

  v5 = a5;
  v7 = a2;
  v8 = 16;
  v9 = a2;
  do
  {
    v10 = v8;
    v11 = v9 % v8;
    v9 = v8;
    v8 = v11;
  }
  while ( v11 );
  v12 = 0;
  v13 = 16 * (int)v7 / v10;
  v14 = v13 / (unsigned int)v7;
  if ( (int)(v13 / (unsigned int)v7) > 0 )
  {
    do
    {
      v15 = (unsigned __int8 *)a1 + (unsigned int)(v7 * v12);
      if ( v12 )
      {
        memcpy_0(v15, (char *)a1 + (unsigned int)(v7 * (v12 - 1)), v7);
        v16 = v7 - 1;
        LODWORD(v17) = v7 - 1;
        v18 = (char *)&v15[(unsigned int)(v7 - 1)];
        v19 = *v18;
        if ( (_DWORD)v7 == 1 )
        {
          v63 = (*v15 >> 1) | (v19 << 7);
          *v15 = v63;
          LOBYTE(v14) = 16 * *v18;
          *v15 = v14 | (v63 >> 4);
          v24 = *v18;
        }
        else
        {
          do
          {
            v20 = (unsigned int)v17;
            v17 = (unsigned int)(v17 - 1);
            v15[v20] = (v15[v20] >> 1) | (v15[v17] << 7);
          }
          while ( (_DWORD)v17 );
          LODWORD(v21) = v7 - 1;
          *v15 = (v19 << 7) | (*v15 >> 1);
          v22 = *v18;
          do
          {
            v23 = (unsigned int)v21;
            v21 = (unsigned int)(v21 - 1);
            v15[v23] = (v15[v23] >> 4) | (16 * v15[v21]);
          }
          while ( (_DWORD)v21 );
          *v15 = (16 * v22) | (*v15 >> 4);
          v24 = *v18;
          do
          {
            v25 = v16 - 1;
            v26 = v16;
            LOBYTE(v14) = v15[v25];
            --v16;
            v15[v26] = v14;
          }
          while ( (_DWORD)v25 );
        }
        *v15 = v24;
      }
      else
      {
        LOBYTE(v14) = (unsigned __int8)memcpy_0(v15, a3, v7);
      }
      ++v12;
    }
    while ( v12 < (int)(v13 / (unsigned int)v7) );
    v5 = a5;
  }
  v27 = a1;
  v28 = 1;
  v29 = v13 >> 4;
  *(_OWORD *)v5 = *a1;
  if ( v29 > 1 )
  {
    do
    {
      v30 = *(unsigned __int8 *)(v5 + 15);
      v31 = (char *)v27 + (unsigned int)(16 * v28);
      v32 = 14;
      v33 = v30 + (unsigned __int8)v31[15];
      *(_BYTE *)(v5 + 15) = v30 + v31[15];
      v34 = 14;
      v35 = v33 > 0xFF;
      do
      {
        v36 = *(unsigned __int8 *)(v34 + v5);
        v37 = (unsigned __int8)v31[v34];
        v38 = v36 + v37;
        v39 = v37 + v36;
        if ( v35 )
        {
          v40 = v38 + 1 > 0xFF;
          ++v39;
        }
        else
        {
          v40 = v38 > 0xFF;
        }
        *(_BYTE *)(v34 + v5) = v39;
        v41 = (unsigned __int8)v31[v34 - 1];
        v42 = *(unsigned __int8 *)(v34 + v5 - 1);
        v43 = v42 + v41;
        v44 = v41 + v42;
        if ( v40 )
        {
          v45 = v43 + 1 > 0xFF;
          ++v44;
        }
        else
        {
          v45 = v43 > 0xFF;
        }
        *(_BYTE *)(v34 + v5 - 1) = v44;
        v46 = (unsigned __int8)v31[v34 - 2];
        v47 = *(unsigned __int8 *)(v34 + v5 - 2);
        v48 = v47 + v46;
        v49 = v46 + v47;
        if ( v45 )
        {
          v50 = v48 + 1 > 0xFF;
          ++v49;
        }
        else
        {
          v50 = v48 > 0xFF;
        }
        *(_BYTE *)(v34 + v5 - 2) = v49;
        v51 = (unsigned __int8)v31[v34 - 3];
        v52 = *(unsigned __int8 *)(v34 + v5 - 3);
        v53 = v52 + v51;
        v54 = v51 + v52;
        if ( v50 )
        {
          v55 = v53 + 1 > 0xFF;
          ++v54;
        }
        else
        {
          v55 = v53 > 0xFF;
        }
        *(_BYTE *)(v34 + v5 - 3) = v54;
        v14 = (unsigned __int8)v31[v34 - 4];
        v56 = *(unsigned __int8 *)(v34 + v5 - 4);
        v57 = v56 + v14;
        v58 = v14 + v56;
        if ( v55 )
        {
          LOBYTE(v14) = v57 + 1;
          v35 = v57 + 1 > 0xFF;
          ++v58;
        }
        else
        {
          v35 = v57 > 0xFF;
        }
        *(_BYTE *)(v34 + v5 - 4) = v58;
        v34 -= 5;
        v32 -= 5;
      }
      while ( v32 >= 0 );
      if ( v35 )
      {
LABEL_36:
        v59 = 15;
        while ( v35 )
        {
          v60 = (_BYTE *)(v5 + (unsigned int)v59);
          v61 = (unsigned __int8)*v60;
          *v60 = v61 + 1;
          LOBYTE(v14) = v61 + 1;
          if ( (unsigned int)(v61 + 1) <= 0xFF )
            break;
          v14 = (unsigned __int8)*(v60 - 1);
          v62 = v14 + 1;
          LOBYTE(v14) = v14 + 1;
          *(v60 - 1) = v14;
          v35 = v62 > 0xFF;
          if ( v62 > 0xFF )
          {
            v14 = (unsigned __int8)*(v60 - 2);
            v64 = v14 + 1;
            LOBYTE(v14) = v14 + 1;
            *(v60 - 2) = v14;
            v35 = v64 > 0xFF;
            if ( v64 > 0xFF )
            {
              v65 = (unsigned __int8)*(v60 - 3);
              *(v60 - 3) = v65 + 1;
              LOBYTE(v14) = v65 + 1;
              v35 = (unsigned int)(v65 + 1) > 0xFF;
              v59 -= 4;
              if ( v59 >= 0 )
                continue;
            }
          }
          if ( !v35 )
            break;
          goto LABEL_36;
        }
      }
      v27 = a1;
      ++v28;
    }
    while ( v28 < (int)v29 );
  }
  return v14;
}

```

## disassembly

```asm
0x180001010  mov     [rsp+arg_18], rsi
0x180001015  mov     [rsp+arg_0], rcx
0x18000101a  push    rdi
0x18000101b  push    r12
0x18000101d  push    r13
0x18000101f  push    r14
0x180001021  push    r15
0x180001023  sub     rsp, 20h
0x180001027  mov     r13, [rsp+48h+arg_20]
0x18000102c  mov     r15, r8
0x18000102f  mov     r14d, edx
0x180001032  mov     r9d, 10h
0x180001038  mov     eax, edx
0x18000103a  nop     word ptr [rax+rax+00h]
0x180001040  xor     edx, edx
0x180001042  mov     r10d, r9d
0x180001045  div     r9d
0x180001048  mov     eax, r10d
0x18000104b  mov     r9d, edx
0x18000104e  test    edx, edx
0x180001050  jnz     short loc_180001040
0x180001052  xor     edx, edx
0x180001054  mov     [rsp+48h+arg_8], rbx
0x180001059  mov     eax, r14d
0x18000105c  mov     [rsp+48h+arg_10], rbp
0x180001061  shl     eax, 4
0x180001064  xor     edi, edi
0x180001066  div     r10d
0x180001069  xor     edx, edx
0x18000106b  mov     r12d, eax
0x18000106e  div     r14d
0x180001071  mov     esi, eax
0x180001073  test    eax, eax
0x180001075  jle     loc_180001169
0x18000107b  mov     r13, [rsp+48h+arg_0]
0x180001080  mov     ebx, edi
0x180001082  mov     r8, r14; Size
0x180001085  imul    ebx, r14d
0x180001089  add     rbx, r13
0x18000108c  mov     rcx, rbx; void *
0x18000108f  test    edi, edi
0x180001091  jz      loc_18000143A
0x180001097  lea     edx, [rdi-1]
0x18000109a  imul    edx, r14d
0x18000109e  add     rdx, r13; Src
0x1800010a1  call    memcpy_0
0x1800010a6  cmp     r14d, 1
0x1800010aa  jb      loc_18000115A
0x1800010b0  lea     r9d, [r14-1]
0x1800010b4  mov     r11d, r9d
0x1800010b7  mov     r8d, r9d
0x1800010ba  add     r11, rbx
0x1800010bd  movzx   r10d, byte ptr [r11]
0x1800010c1  test    r9d, r9d
0x1800010c4  jz      loc_1800013D1
0x1800010ca  nop     word ptr [rax+rax+00h]
0x1800010d0  mov     edx, r8d
0x1800010d3  dec     r8d
0x1800010d6  movzx   eax, byte ptr [rdx+rbx]
0x1800010da  movzx   ecx, byte ptr [r8+rbx]
0x1800010df  shl     cl, 7
0x1800010e2  shr     al, 1
0x1800010e4  or      cl, al
0x1800010e6  mov     [rdx+rbx], cl
0x1800010e9  test    r8d, r8d
0x1800010ec  jnz     short loc_1800010D0
0x1800010ee  movzx   eax, byte ptr [rbx]
0x1800010f1  mov     r8d, r9d
0x1800010f4  shl     r10b, 7
0x1800010f8  shr     al, 1
0x1800010fa  or      al, r10b
0x1800010fd  mov     [rbx], al
0x1800010ff  movzx   r10d, byte ptr [r11]
0x180001103  nop     dword ptr [rax+00h]
0x180001107  nop     word ptr [rax+rax+00000000h]
0x180001110  mov     edx, r8d
0x180001113  dec     r8d
0x180001116  movzx   eax, byte ptr [rdx+rbx]
0x18000111a  movzx   ecx, byte ptr [r8+rbx]
0x18000111f  shl     cl, 4
0x180001122  shr     al, 4
0x180001125  or      cl, al
0x180001127  mov     [rdx+rbx], cl
0x18000112a  test    r8d, r8d
0x18000112d  jnz     short loc_180001110
0x18000112f  movzx   eax, byte ptr [rbx]
0x180001132  shr     al, 4
0x180001135  shl     r10b, 4
0x180001139  or      al, r10b
0x18000113c  mov     [rbx], al
0x18000113e  movzx   r8d, byte ptr [r11]
0x180001142  lea     edx, [r9-1]
0x180001146  mov     ecx, r9d
0x180001149  movzx   eax, byte ptr [rdx+rbx]
0x18000114d  mov     r9d, edx
0x180001150  mov     [rcx+rbx], al
0x180001153  test    edx, edx
0x180001155  jnz     short loc_180001142
0x180001157  mov     [rbx], r8b
0x18000115a  inc     edi
0x18000115c  cmp     edi, esi
0x18000115e  jl      loc_180001080
0x180001164  mov     r13, [rsp+48h+arg_20]
0x180001169  mov     r10, [rsp+48h+arg_0]
0x18000116e  mov     r15d, 1
0x180001174  shr     r12d, 4
0x180001178  movups  xmm0, xmmword ptr [r10]
0x18000117c  movups  xmmword ptr [r13+0], xmm0
0x180001181  cmp     r12d, r15d
0x180001184  jbe     loc_1800012E4
0x18000118a  nop     word ptr [rax+rax+00h]
0x180001190  movzx   edx, byte ptr [r13+0Fh]
0x180001195  mov     eax, r15d
0x180001198  shl     eax, 4
0x18000119b  xor     r9d, r9d
0x18000119e  movzx   ecx, byte ptr [rax+r10+0Fh]
0x1800011a4  lea     rbx, [rax+r10]
0x1800011a8  mov     r8d, eax
0x1800011ab  mov     r11d, 0Eh
0x1800011b1  lea     eax, [rdx+rcx]
0x1800011b4  add     ecx, edx
0x1800011b6  cmp     ecx, 0FFh
0x1800011bc  mov     [r13+0Fh], al
0x1800011c0  lea     rdi, [r10+r8]
0x1800011c4  mov     ecx, r11d
0x1800011c7  setnbe  r9b
0x1800011cb  lea     rsi, [r8+r10]
0x1800011cf  lea     rbp, [r8+r10]
0x1800011d3  lea     r14, [r8+r10]
0x1800011d7  nop     word ptr [rax+rax+00000000h]
0x1800011e0  movzx   edx, byte ptr [rcx+r13]
0x1800011e5  lea     r8, [rcx+r13]
0x1800011e9  movzx   eax, byte ptr [rbx+rcx]
0x1800011ed  lea     r10d, [rdx+rax]
0x1800011f1  add     dl, al
0x1800011f3  test    r9d, r9d
0x1800011f6  jnz     loc_180001301
0x1800011fc  cmp     r10d, 0FFh
0x180001203  setnbe  r9b
0x180001207  mov     [r8], dl
0x18000120a  lea     r8, [rcx+r13]
0x18000120e  movzx   eax, byte ptr [rdi+rcx-1]
0x180001213  movzx   edx, byte ptr [rcx+r13-1]
0x180001219  lea     r10d, [rdx+rax]
0x18000121d  add     dl, al
0x18000121f  test    r9d, r9d
0x180001222  jnz     loc_180001318
0x180001228  cmp     r10d, 0FFh
0x18000122f  setnbe  r9b
0x180001233  mov     [r8-1], dl
0x180001237  lea     r8, [rcx+r13]
0x18000123b  movzx   eax, byte ptr [rsi+rcx-2]
0x180001240  movzx   edx, byte ptr [rcx+r13-2]
0x180001246  lea     r10d, [rdx+rax]
0x18000124a  add     dl, al
0x18000124c  test    r9d, r9d
0x18000124f  jnz     loc_18000132F
0x180001255  cmp     r10d, 0FFh
0x18000125c  setnbe  r9b
0x180001260  mov     [r8-2], dl
0x180001264  lea     r8, [rcx+r13]
0x180001268  movzx   eax, byte ptr [rcx+rbp-3]
0x18000126d  movzx   edx, byte ptr [rcx+r13-3]
0x180001273  lea     r10d, [rdx+rax]
0x180001277  add     dl, al
0x180001279  test    r9d, r9d
0x18000127c  jnz     loc_180001346
0x180001282  cmp     r10d, 0FFh
0x180001289  setnbe  r9b
0x18000128d  mov     [r8-3], dl
0x180001291  movzx   eax, byte ptr [r14+rcx-4]
0x180001297  movzx   edx, byte ptr [rcx+r13-4]
0x18000129d  lea     r8d, [rdx+rax]
0x1800012a1  add     dl, al
0x1800012a3  test    r9d, r9d
0x1800012a6  jnz     loc_18000135D
0x1800012ac  cmp     r8d, 0FFh
0x1800012b3  setnbe  r9b
0x1800012b7  mov     [rcx+r13-4], dl
0x1800012bc  sub     rcx, 5
0x1800012c0  sub     r11d, 5
0x1800012c4  jns     loc_1800011E0
0x1800012ca  test    r9d, r9d
0x1800012cd  jnz     loc_180001380
0x1800012d3  mov     r10, [rsp+48h+arg_0]
0x1800012d8  inc     r15d
0x1800012db  cmp     r15d, r12d
0x1800012de  jl      loc_180001190
0x1800012e4  mov     rbp, [rsp+48h+arg_10]
0x1800012e9  mov     rbx, [rsp+48h+arg_8]
0x1800012ee  mov     rsi, [rsp+48h+arg_18]
0x1800012f3  add     rsp, 20h
0x1800012f7  pop     r15
0x1800012f9  pop     r14
0x1800012fb  pop     r13
0x1800012fd  pop     r12
0x1800012ff  pop     rdi
0x180001300  retn
0x180001301  xor     r9d, r9d
0x180001304  lea     eax, [r10+1]
0x180001308  cmp     eax, 0FFh
0x18000130d  setnbe  r9b
0x180001311  inc     dl
0x180001313  jmp     loc_180001207
0x180001318  xor     r9d, r9d
0x18000131b  lea     eax, [r10+1]
0x18000131f  cmp     eax, 0FFh
0x180001324  setnbe  r9b
0x180001328  inc     dl
0x18000132a  jmp     loc_180001233
0x18000132f  xor     r9d, r9d
0x180001332  lea     eax, [r10+1]
0x180001336  cmp     eax, 0FFh
0x18000133b  setnbe  r9b
0x18000133f  inc     dl
0x180001341  jmp     loc_180001260
0x180001346  xor     r9d, r9d
0x180001349  lea     eax, [r10+1]
0x18000134d  cmp     eax, 0FFh
0x180001352  setnbe  r9b
0x180001356  inc     dl
0x180001358  jmp     loc_18000128D
0x18000135d  xor     r9d, r9d
0x180001360  lea     eax, [r8+1]
0x180001364  cmp     eax, 0FFh
0x180001369  setnbe  r9b
0x18000136d  inc     dl
0x18000136f  jmp     loc_1800012B7
0x180001380  mov     r8d, 0Fh
0x180001386  test    r9d, r9d
0x180001389  jz      loc_1800012D3
0x18000138f  mov     edx, r8d
0x180001392  add     rdx, r13
0x180001395  movzx   ecx, byte ptr [rdx]
0x180001398  lea     eax, [rcx+1]
0x18000139b  mov     [rdx], al
0x18000139d  lea     eax, [rcx+1]
0x1800013a0  cmp     eax, 0FFh
0x1800013a5  jbe     loc_1800012D3
0x1800013ab  movzx   eax, byte ptr [rdx-1]
0x1800013af  xor     r9d, r9d
0x1800013b2  lea     ecx, [rax+1]
0x1800013b5  inc     al
0x1800013b7  cmp     ecx, 0FFh
0x1800013bd  mov     [rdx-1], al
0x1800013c0  setnbe  r9b
0x1800013c4  ja      short loc_1800013FA
0x1800013c6  test    r9d, r9d
0x1800013c9  jz      loc_1800012D3
0x1800013cf  jmp     short loc_180001380
0x1800013d1  movzx   eax, byte ptr [rbx]
0x1800013d4  shr     al, 1
0x1800013d6  shl     r10b, 7
0x1800013da  or      r10b, al
0x1800013dd  mov     [rbx], r10b
0x1800013e0  movzx   eax, byte ptr [r11]
0x1800013e4  shl     al, 4
0x1800013e7  shr     r10b, 4
0x1800013eb  or      r10b, al
0x1800013ee  mov     [rbx], r10b
0x1800013f1  movzx   r8d, byte ptr [r11]
0x1800013f5  jmp     loc_180001157
0x1800013fa  movzx   eax, byte ptr [rdx-2]
0x1800013fe  xor     r9d, r9d
0x180001401  lea     ecx, [rax+1]
0x180001404  inc     al
0x180001406  cmp     ecx, 0FFh
0x18000140c  mov     [rdx-2], al
0x18000140f  setnbe  r9b
0x180001413  jbe     short loc_1800013C6
0x180001415  movzx   ecx, byte ptr [rdx-3]
0x180001419  xor     r9d, r9d
0x18000141c  lea     eax, [rcx+1]
0x18000141f  mov     [rdx-3], al
0x180001422  lea     eax, [rcx+1]
0x180001425  cmp     eax, 0FFh
0x18000142a  setnbe  r9b
0x18000142e  sub     r8d, 4
0x180001432  jns     loc_180001386
0x180001438  jmp     short loc_1800013C6
0x18000143a  mov     rdx, r15; Src
0x18000143d  call    memcpy_0
0x180001442  jmp     loc_18000115A
```
