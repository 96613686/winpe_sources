# DecompressCBlock16To555

- ea: `0x1800037e0`
- end: `0x180003b11`
- name: `DecompressCBlock16To555`
- size: `817`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800054f0`

## callees

- `0x1800037e0`

## pseudocode

```c
unsigned __int16 *__fastcall DecompressCBlock16To555(int *a1, unsigned __int16 *a2, unsigned int *a3, int a4, int *a5)
{
  unsigned __int16 *v5; // r10
  __int64 v6; // r14
  int v8; // r9d
  unsigned int v9; // eax
  int v10; // r8d
  int v11; // eax
  unsigned __int16 v12; // cx
  int v13; // ebx
  unsigned int v14; // ecx
  unsigned __int16 *v15; // rdx
  unsigned __int16 *v16; // r10
  unsigned __int16 v17; // ax
  int v18; // edi
  int v19; // ebx
  unsigned __int16 v20; // cx
  unsigned __int16 v21; // si
  unsigned int v22; // eax
  unsigned __int16 *v23; // rdx
  unsigned __int16 v24; // ax
  int v25; // r13d
  int v26; // r15d
  int v27; // ebp
  char v28; // dl
  char v29; // al
  int v30; // ecx
  int v31; // eax
  unsigned int v32; // ecx
  unsigned __int16 v33; // dx
  unsigned __int16 *v34; // rax
  unsigned __int16 v35; // ax
  int v36; // ebp
  int v37; // edi
  unsigned __int16 v38; // cx
  unsigned __int16 v39; // bx
  unsigned int v40; // eax
  unsigned __int16 v41; // ax
  int v42; // r12d
  int v43; // ebx
  int v44; // r8d
  char v45; // dl
  char v46; // al
  int v47; // ecx
  int v48; // eax
  unsigned int v49; // eax
  unsigned __int16 v50; // ax
  int v51; // r8d
  int v52; // edi
  int v53; // ebx
  char v54; // dl
  char v55; // al
  unsigned __int16 *v57; // [rsp+68h] [rbp+10h]

  v5 = a2;
  v6 = a4;
  if ( *a5 > 0 )
  {
    --*a5;
    return v5;
  }
  if ( *a3 <= 1 )
  {
    LOWORD(v8) = 0;
LABEL_12:
    v12 = 0;
    goto LABEL_42;
  }
  v8 = *a2;
  v9 = *a3 - 2;
  v5 = a2 + 1;
  *a3 = v9;
  if ( (v8 & 0x8000u) != 0 )
  {
    if ( (v8 & 0xFFFFFC00) == 0x8400 )
    {
      *a5 = (v8 & 0x3FF) - 1;
    }
    else
    {
      v10 = 4;
      v11 = v8 & 0x7FFF | ((v8 & 0x7FFF) << 16);
      do
      {
        *a1 = v11;
        a1[1] = v11;
        a1 = (int *)((char *)a1 + v6);
        --v10;
      }
      while ( v10 );
    }
    return v5;
  }
  if ( v9 <= 1 )
    goto LABEL_12;
  v13 = *v5;
  if ( (v13 & 0x8000u) == 0 )
  {
    v49 = v9 - 2;
    *a3 = v49;
    if ( v49 > 1 )
    {
      v5 = a2 + 3;
      *a3 = v49 - 2;
      v50 = a2[2];
      v12 = v13;
LABEL_44:
      v51 = 4;
      v52 = v50 | (v50 << 16);
      v53 = v52 ^ (v12 | (v12 << 16));
      do
      {
        v54 = v8;
        v55 = v8;
        LOWORD(v8) = (unsigned __int16)v8 >> 4;
        *a1 = v52 ^ v53 & *((_DWORD *)Bits2Bytes + (v55 & 3));
        a1[1] = v52 ^ v53 & *((_DWORD *)Bits2Bytes + (v54 & 0xC));
        a1 = (int *)((char *)a1 + v6);
        --v51;
      }
      while ( v51 );
      return v5;
    }
    v5 = a2 + 2;
    v12 = v13;
LABEL_42:
    v50 = 0;
    goto LABEL_44;
  }
  v14 = v9 - 2;
  *a3 = v9 - 2;
  v15 = a2 + 2;
  v57 = v5 + 1;
  v16 = v5 + 1;
  if ( v9 - 2 > 1 )
  {
    v17 = *v15;
    ++v16;
    v14 -= 2;
    v57 = v16;
    *a3 = v14;
  }
  else
  {
    v17 = 0;
  }
  v18 = v17 | (v17 << 16);
  v19 = v18 ^ (v13 | (v13 << 16));
  if ( v14 > 1 )
  {
    v21 = *v16;
    v22 = v14 - 2;
    *a3 = v14 - 2;
    v23 = v16 + 1;
    v20 = v21;
    if ( v22 > 1 )
    {
      v16 += 2;
      *a3 = v22 - 2;
      v24 = *v23;
      v57 = v23 + 1;
      goto LABEL_23;
    }
    ++v16;
    v57 = v23;
  }
  else
  {
    v20 = 0;
  }
  v24 = 0;
LABEL_23:
  v25 = 2;
  v26 = v24 | (v24 << 16);
  v27 = v26 ^ (v20 | (v20 << 16));
  do
  {
    v28 = v8;
    v29 = v8;
    LOWORD(v8) = (unsigned __int16)v8 >> 4;
    v30 = v18 ^ v19 & *((_DWORD *)Bits2Bytes + (v29 & 3));
    v31 = v26 ^ v27 & *((_DWORD *)Bits2Bytes + (v28 & 0xC));
    *a1 = v30;
    a1[1] = v31;
    a1 = (int *)((char *)a1 + v6);
    --v25;
  }
  while ( v25 );
  v32 = *a3;
  if ( *a3 <= 1 )
  {
    v33 = 0;
LABEL_29:
    v35 = 0;
    goto LABEL_31;
  }
  v33 = *v16;
  v34 = v16 + 1;
  v32 -= 2;
  *a3 = v32;
  if ( v32 <= 1 )
  {
    ++v16;
    v57 = v34;
    goto LABEL_29;
  }
  v16 += 2;
  v32 -= 2;
  v35 = *v34;
  v57 = v16;
  *a3 = v32;
LABEL_31:
  v36 = v35 | (v35 << 16);
  v37 = v36 ^ (v33 | (v33 << 16));
  if ( v32 <= 1 )
  {
    v38 = 0;
LABEL_35:
    v41 = 0;
    goto LABEL_37;
  }
  v39 = *v16;
  v40 = v32 - 2;
  *a3 = v32 - 2;
  v38 = v39;
  if ( v40 <= 1 )
  {
    v57 = v16 + 1;
    goto LABEL_35;
  }
  *a3 = v40 - 2;
  v41 = v16[1];
  v57 = v16 + 2;
LABEL_37:
  v42 = 2;
  v43 = v41 | (v41 << 16);
  v44 = v43 ^ (v38 | (v38 << 16));
  do
  {
    v45 = v8;
    v46 = v8;
    LOWORD(v8) = (unsigned __int16)v8 >> 4;
    v47 = v36 ^ v37 & *((_DWORD *)Bits2Bytes + (v46 & 3));
    v48 = v43 ^ v44 & *((_DWORD *)Bits2Bytes + (v45 & 0xC));
    *a1 = v47;
    a1[1] = v48;
    a1 = (int *)((char *)a1 + v6);
    --v42;
  }
  while ( v42 );
  return v57;
}

```

## disassembly

```asm
0x1800037e0  push    rbx
0x1800037e2  push    rbp
0x1800037e3  push    rsi
0x1800037e4  push    rdi
0x1800037e5  push    r12
0x1800037e7  push    r13
0x1800037e9  push    r14
0x1800037eb  push    r15
0x1800037ed  sub     rsp, 18h
0x1800037f1  mov     r10, rdx
0x1800037f4  movsxd  r14, r9d
0x1800037f7  mov     rdx, [rsp+58h+arg_20]
0x1800037ff  xor     ebp, ebp
0x180003801  mov     r11, rcx
0x180003804  mov     eax, [rdx]
0x180003806  test    eax, eax
0x180003808  jle     short loc_180003813
0x18000380a  dec     eax
0x18000380c  mov     [rdx], eax
0x18000380e  jmp     loc_180003AFD
0x180003813  mov     eax, [r8]
0x180003816  mov     r15d, 1
0x18000381c  cmp     eax, r15d
0x18000381f  ja      short loc_180003826
0x180003821  mov     r9d, ebp
0x180003824  jmp     short loc_18000388B
0x180003826  movzx   r9d, word ptr [r10]
0x18000382a  add     eax, 0FFFFFFFEh
0x18000382d  add     r10, 2
0x180003831  mov     [r8], eax
0x180003834  test    r9w, r9w
0x180003838  jns     short loc_180003886
0x18000383a  mov     eax, r9d
0x18000383d  mov     ecx, r9d
0x180003840  and     eax, 0FFFFFC00h
0x180003845  cmp     eax, 8400h
0x18000384a  jnz     short loc_18000385C
0x18000384c  and     ecx, 3FFh
0x180003852  sub     ecx, r15d
0x180003855  mov     [rdx], ecx
0x180003857  jmp     loc_180003AFD
0x18000385c  and     ecx, 7FFFh
0x180003862  mov     r8d, 4
0x180003868  mov     eax, ecx
0x18000386a  shl     eax, 10h
0x18000386d  or      eax, ecx
0x18000386f  or      esi, 0FFFFFFFFh
0x180003872  mov     [r11], eax
0x180003875  mov     [r11+4], eax
0x180003879  add     r11, r14
0x18000387c  add     r8d, esi
0x18000387f  jnz     short loc_180003872
0x180003881  jmp     loc_180003AFD
0x180003886  cmp     eax, r15d
0x180003889  ja      short loc_180003892
0x18000388b  mov     ecx, ebp
0x18000388d  jmp     loc_180003A90
0x180003892  movzx   ebx, word ptr [r10]
0x180003896  test    bx, bx
0x180003899  jns     loc_180003A7B
0x18000389f  lea     ecx, [rax-2]
0x1800038a2  mov     r12d, 2
0x1800038a8  mov     [r8], ecx
0x1800038ab  lea     rdx, [r10+2]
0x1800038af  mov     [rsp+58h+arg_8], rdx
0x1800038b4  mov     r10, rdx
0x1800038b7  mov     [rsp+58h+var_58], r12
0x1800038bb  cmp     ecx, r15d
0x1800038be  ja      short loc_1800038C4
0x1800038c0  mov     eax, ebp
0x1800038c2  jmp     short loc_1800038D5
0x1800038c4  movzx   eax, word ptr [rdx]
0x1800038c7  add     r10, r12
0x1800038ca  add     ecx, 0FFFFFFFEh
0x1800038cd  mov     [rsp+58h+arg_8], r10
0x1800038d2  mov     [r8], ecx
0x1800038d5  movzx   eax, ax
0x1800038d8  mov     edi, eax
0x1800038da  shl     edi, 10h
0x1800038dd  or      edi, eax
0x1800038df  mov     eax, ebx
0x1800038e1  shl     ebx, 10h
0x1800038e4  or      ebx, eax
0x1800038e6  xor     ebx, edi
0x1800038e8  cmp     ecx, r15d
0x1800038eb  ja      short loc_1800038F1
0x1800038ed  mov     ecx, ebp
0x1800038ef  jmp     short loc_18000390F
0x1800038f1  movzx   esi, word ptr [r10]
0x1800038f5  lea     eax, [rcx-2]
0x1800038f8  mov     [r8], eax
0x1800038fb  lea     rdx, [r10+2]
0x1800038ff  movzx   ecx, si
0x180003902  cmp     eax, r15d
0x180003905  ja      short loc_180003913
0x180003907  mov     r10, rdx
0x18000390a  mov     [rsp+58h+arg_8], rdx
0x18000390f  mov     eax, ebp
0x180003911  jmp     short loc_180003925
0x180003913  add     eax, 0FFFFFFFEh
0x180003916  lea     r10, [rdx+2]
0x18000391a  mov     [r8], eax
0x18000391d  movzx   eax, word ptr [rdx]
0x180003920  mov     [rsp+58h+arg_8], r10
0x180003925  movzx   eax, ax
0x180003928  mov     r13d, r12d
0x18000392b  mov     r15d, eax
0x18000392e  mov     [rsp+58h+arg_20], r14
0x180003936  mov     r12, [rsp+58h+arg_20]
0x18000393e  lea     r14, Bits2Bytes
0x180003945  shl     r15d, 10h
0x180003949  or      r15d, eax
0x18000394c  movzx   eax, cx
0x18000394f  mov     ebp, eax
0x180003951  shl     ebp, 10h
0x180003954  or      ebp, eax
0x180003956  xor     ebp, r15d
0x180003959  or      esi, 0FFFFFFFFh
0x18000395c  movzx   edx, r9w
0x180003960  mov     eax, edx
0x180003962  shr     r9w, 4
0x180003967  and     eax, 3
0x18000396a  and     edx, 0Ch
0x18000396d  mov     ecx, [r14+rax*4]
0x180003971  mov     eax, [r14+rdx*4]
0x180003975  and     ecx, ebx
0x180003977  and     eax, ebp
0x180003979  xor     ecx, edi
0x18000397b  xor     eax, r15d
0x18000397e  mov     [r11], ecx
0x180003981  mov     [r11+4], eax
0x180003985  add     r11, r12
0x180003988  add     r13d, esi
0x18000398b  jnz     short loc_18000395C
0x18000398d  mov     ecx, [r8]
0x180003990  cmp     ecx, 1
0x180003993  ja      short loc_180003999
0x180003995  xor     edx, edx
0x180003997  jmp     short loc_1800039B4
0x180003999  movzx   edx, word ptr [r10]
0x18000399d  lea     rax, [r10+2]
0x1800039a1  add     ecx, 0FFFFFFFEh
0x1800039a4  mov     [r8], ecx
0x1800039a7  cmp     ecx, 1
0x1800039aa  ja      short loc_1800039B8
0x1800039ac  mov     r10, rax
0x1800039af  mov     [rsp+58h+arg_8], rax
0x1800039b4  xor     eax, eax
0x1800039b6  jmp     short loc_1800039CA
0x1800039b8  lea     r10, [rax+2]
0x1800039bc  add     ecx, 0FFFFFFFEh
0x1800039bf  movzx   eax, word ptr [rax]
0x1800039c2  mov     [rsp+58h+arg_8], r10
0x1800039c7  mov     [r8], ecx
0x1800039ca  movzx   eax, ax
0x1800039cd  mov     ebp, eax
0x1800039cf  shl     ebp, 10h
0x1800039d2  or      ebp, eax
0x1800039d4  movzx   eax, dx
0x1800039d7  mov     edi, eax
0x1800039d9  shl     edi, 10h
0x1800039dc  or      edi, eax
0x1800039de  xor     edi, ebp
0x1800039e0  cmp     ecx, 1
0x1800039e3  ja      short loc_1800039E9
0x1800039e5  xor     ecx, ecx
0x1800039e7  jmp     short loc_180003A04
0x1800039e9  movzx   ebx, word ptr [r10]
0x1800039ed  lea     eax, [rcx-2]
0x1800039f0  mov     [r8], eax
0x1800039f3  lea     rdx, [r10+2]
0x1800039f7  movzx   ecx, bx
0x1800039fa  cmp     eax, 1
0x1800039fd  ja      short loc_180003A08
0x1800039ff  mov     [rsp+58h+arg_8], rdx
0x180003a04  xor     eax, eax
0x180003a06  jmp     short loc_180003A1A
0x180003a08  add     eax, 0FFFFFFFEh
0x180003a0b  lea     r10, [rdx+2]
0x180003a0f  mov     [r8], eax
0x180003a12  movzx   eax, word ptr [rdx]
0x180003a15  mov     [rsp+58h+arg_8], r10
0x180003a1a  mov     r12, [rsp+58h+var_58]
0x180003a1e  mov     r10, [rsp+58h+arg_20]
0x180003a26  movzx   eax, ax
0x180003a29  mov     ebx, eax
0x180003a2b  shl     ebx, 10h
0x180003a2e  or      ebx, eax
0x180003a30  movzx   eax, cx
0x180003a33  mov     r8d, eax
0x180003a36  shl     r8d, 10h
0x180003a3a  or      r8d, eax
0x180003a3d  xor     r8d, ebx
0x180003a40  movzx   edx, r9w
0x180003a44  mov     eax, edx
0x180003a46  shr     r9w, 4
0x180003a4b  and     eax, 3
0x180003a4e  and     edx, 0Ch
0x180003a51  mov     ecx, [r14+rax*4]
0x180003a55  mov     eax, [r14+rdx*4]
0x180003a59  and     ecx, edi
0x180003a5b  and     eax, r8d
0x180003a5e  xor     ecx, ebp
0x180003a60  xor     eax, ebx
0x180003a62  mov     [r11], ecx
0x180003a65  mov     [r11+4], eax
0x180003a69  add     r11, r10
0x180003a6c  add     r12d, esi
0x180003a6f  jnz     short loc_180003A40
0x180003a71  mov     r10, [rsp+58h+arg_8]
0x180003a76  jmp     loc_180003AFD
0x180003a7b  add     eax, 0FFFFFFFEh
0x180003a7e  lea     rcx, [r10+2]
0x180003a82  mov     [r8], eax
0x180003a85  cmp     eax, r15d
0x180003a88  ja      short loc_180003A94
0x180003a8a  mov     r10, rcx
0x180003a8d  movzx   ecx, bx
0x180003a90  mov     eax, ebp
0x180003a92  jmp     short loc_180003AA4
0x180003a94  add     eax, 0FFFFFFFEh
0x180003a97  lea     r10, [rcx+2]
0x180003a9b  mov     [r8], eax
0x180003a9e  movzx   eax, word ptr [rcx]
0x180003aa1  movzx   ecx, bx
0x180003aa4  movzx   eax, ax
0x180003aa7  mov     rbp, r14
0x180003aaa  mov     edi, eax
0x180003aac  lea     r14, Bits2Bytes
0x180003ab3  shl     edi, 10h
0x180003ab6  mov     r8d, 4
0x180003abc  or      edi, eax
0x180003abe  movzx   eax, cx
0x180003ac1  mov     ebx, eax
0x180003ac3  shl     ebx, 10h
0x180003ac6  or      ebx, eax
0x180003ac8  xor     ebx, edi
0x180003aca  or      esi, 0FFFFFFFFh
0x180003acd  movzx   edx, r9w
0x180003ad1  mov     eax, edx
0x180003ad3  shr     r9w, 4
0x180003ad8  and     eax, 3
0x180003adb  and     edx, 0Ch
0x180003ade  mov     ecx, [r14+rax*4]
0x180003ae2  and     ecx, ebx
0x180003ae4  xor     ecx, edi
0x180003ae6  mov     [r11], ecx
0x180003ae9  mov     ecx, [r14+rdx*4]
0x180003aed  and     ecx, ebx
0x180003aef  xor     ecx, edi
0x180003af1  mov     [r11+4], ecx
0x180003af5  add     r11, rbp
0x180003af8  add     r8d, esi
0x180003afb  jnz     short loc_180003ACD
0x180003afd  mov     rax, r10
0x180003b00  add     rsp, 18h
0x180003b04  pop     r15
0x180003b06  pop     r14
0x180003b08  pop     r13
0x180003b0a  pop     r12
0x180003b0c  pop     rdi
0x180003b0d  pop     rsi
0x180003b0e  pop     rbp
0x180003b0f  pop     rbx
0x180003b10  retn
```
