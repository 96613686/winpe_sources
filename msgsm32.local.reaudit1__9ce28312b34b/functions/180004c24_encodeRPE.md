# encodeRPE

- ea: `0x180004c24`
- end: `0x180004f53`
- name: `encodeRPE`
- size: `815`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005350`

## callees

- `0x180001440`
- `0x180002bb4`
- `0x180004c24`
- `0x180006479`

## pseudocode

```c
__int64 __fastcall encodeRPE(__int64 a1, const void *a2, __int16 *a3, int a4, __int64 a5, _WORD *a6)
{
  __int64 v6; // rcx
  unsigned __int64 v10; // rdx
  unsigned int i; // r9d
  int v12; // edi
  unsigned int j; // r8d
  int v14; // eax
  int v15; // eax
  int v16; // ecx
  __int64 v17; // rax
  int v18; // r9d
  unsigned int k; // edi
  int v20; // edx
  unsigned int m; // r8d
  int v22; // eax
  int v23; // eax
  int v24; // ecx
  __int16 v25; // ax
  unsigned int v26; // edx
  int v27; // edi
  __int64 v28; // rcx
  __int64 v29; // rax
  int v30; // ecx
  __int16 v31; // di
  char v32; // r8
  int v33; // eax
  int v34; // eax
  int v35; // r10d
  int v36; // r11d
  __int64 n; // rdx
  int v38; // eax
  int v39; // eax
  int v40; // eax
  int v41; // eax
  int v42; // edx
  _WORD *v43; // rdi
  __int64 v44; // rcx
  unsigned int v45; // r8d
  __int64 v46; // rdi
  __int64 v47; // rcx
  __int64 result; // rax
  __int16 v49[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v50; // [rsp+34h] [rbp-CCh] BYREF
  _WORD v51[25]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v52[230]; // [rsp+6Ah] [rbp-96h] BYREF

  v6 = 0;
  v50 = 0;
  v49[0] = 0;
  do
  {
    v10 = (unsigned int)v6;
    if ( v10 >= 50 )
LABEL_75:
      _report_rangecheckfailure(v6, v10 * 2);
    v6 = (unsigned int)(v6 + 1);
    v51[v10 + 20] = 0;
  }
  while ( (unsigned int)v6 <= 4 );
  memcpy_0(v52, a2, 0x50u);
  v6 = 45;
  do
  {
    v10 = (unsigned int)v6;
    if ( v10 >= 50 )
      goto LABEL_75;
    v6 = (unsigned int)(v6 + 1);
    v51[v10 + 20] = 0;
  }
  while ( (unsigned int)v6 <= 0x31 );
  for ( i = 0; i <= 0x27; ++i )
  {
    v12 = 0x2000;
    for ( j = 0; j <= 0xA; ++j )
    {
      v14 = 2 * H[j] * (__int16)v51[i + 20 + j] + v12;
      if ( v12 < 0 )
      {
        if ( ((H[j] * (__int16)v51[i + 20 + j]) & 0x40000000) != 0 && v14 >= 0 )
        {
          v12 = 0x80000000;
          continue;
        }
LABEL_15:
        v12 = v14;
        continue;
      }
      if ( ((H[j] * (__int16)v51[i + 20 + j]) & 0x40000000) != 0 )
        goto LABEL_15;
      v12 = 0x7FFFFFFF;
      if ( v14 >= 0 )
        goto LABEL_15;
    }
    v15 = 2 * v12;
    if ( v12 >= 0 )
    {
      if ( (v12 & 0x40000000) == 0 )
        goto LABEL_21;
LABEL_25:
      HIWORD(v16) = 0x7FFF;
      goto LABEL_26;
    }
    if ( (v12 & 0x40000000) == 0 )
    {
LABEL_23:
      HIWORD(v16) = 0x8000;
      goto LABEL_26;
    }
LABEL_21:
    v16 = 4 * v12;
    if ( (v12 & 0x40000000) == 0 )
    {
      if ( (v15 & 0x40000000) == 0 )
        goto LABEL_26;
      goto LABEL_25;
    }
    if ( (v15 & 0x40000000) == 0 )
      goto LABEL_23;
LABEL_26:
    v17 = i;
    *(_WORD *)&v52[2 * v17 + 102] = HIWORD(v16);
  }
  v18 = 0;
  *a3 = 0;
  for ( k = 0; k <= 3; ++k )
  {
    v20 = 0;
    for ( m = 0; m <= 0xC; ++m )
    {
      v22 = *(__int16 *)&v52[4 * m + 102 + 2 * m + 2 * k] >> 2;
      v23 = v22 * v22;
      v24 = v20 + 2 * v23;
      if ( (v23 & 0x40000000) != 0 )
      {
        if ( v20 < 0 && v24 >= 0 )
        {
          v20 = 0x80000000;
          continue;
        }
LABEL_35:
        v20 = v24;
        continue;
      }
      if ( v20 < 0 )
        goto LABEL_35;
      v20 = 0x7FFFFFFF;
      if ( v24 >= 0 )
        goto LABEL_35;
    }
    if ( v20 <= v18 )
    {
      v25 = *a3;
    }
    else
    {
      *a3 = k;
      v18 = v20;
      v25 = k;
    }
  }
  v26 = 0;
  v27 = v25;
  do
  {
    v28 = v26;
    v29 = v26 + v27 + 2 * v26;
    ++v26;
    v51[v28] = *(_WORD *)&v52[2 * v29 + 102];
  }
  while ( v26 <= 0xC );
  APCMQuantize(v28, (unsigned int)v51, a4, a5, (__int64)&v50, (__int64)v49);
  v30 = 6 - v50;
  if ( v30 >= -32768 )
  {
    if ( v30 <= 0x7FFF )
      v31 = 6 - v50;
    else
      v31 = 0x7FFF;
  }
  else
  {
    v31 = 0x8000;
  }
  v32 = v31;
  v33 = v31 - 1;
  if ( v33 < -32768 )
  {
    LOWORD(v33) = 0x8000;
    goto LABEL_50;
  }
  if ( v33 > 0x7FFF )
  {
    LOBYTE(v33) = -1;
    goto LABEL_57;
  }
  if ( (v33 & 0x8000u) != 0 )
LABEL_50:
    v34 = 1 >> -(__int16)v33;
  else
LABEL_57:
    v34 = 1 << v33;
  v35 = FAC[v49[0]];
  v36 = (__int16)v34;
  for ( n = 0; n != 13; ++n )
  {
    v38 = (__int16)(2 * *(_WORD *)(a5 + 2 * n)) - 7;
    if ( v38 >= -32768 )
    {
      if ( v38 > 0x7FFF )
        LOWORD(v38) = 0x7FFF;
    }
    else
    {
      LOWORD(v38) = 0x8000;
    }
    v39 = v35 * (__int16)((_WORD)v38 << 12) + 0x4000;
    if ( v39 >= 0x40000000 )
      v39 = 0x3FFFFFFF;
    v40 = v36 + (__int16)((unsigned int)v39 >> 15);
    if ( v40 >= -32768 )
    {
      if ( v40 > 0x7FFF )
        LOWORD(v40) = 0x7FFF;
    }
    else
    {
      LOWORD(v40) = 0x8000;
    }
    if ( v31 < 0 )
    {
      v41 = (__int16)v40 << -v32;
    }
    else
    {
      v32 = v31;
      v41 = (__int16)v40 >> v31;
    }
    v51[n] = v41;
  }
  v42 = *a3;
  v43 = a6;
  v44 = 40;
  v45 = 0;
  while ( v44 )
  {
    *v43++ = 0;
    --v44;
  }
  do
  {
    v46 = v45;
    v47 = v45 + v42 + 2 * v45;
    ++v45;
    result = (unsigned __int16)v51[v46];
    a6[v47] = result;
  }
  while ( v45 <= 0xC );
  return result;
}

```

## disassembly

```asm
0x180004c24  mov     [rsp-8+arg_0], rbx
0x180004c29  push    rbp
0x180004c2a  push    rsi
0x180004c2b  push    rdi
0x180004c2c  push    r12
0x180004c2e  push    r13
0x180004c30  push    r14
0x180004c32  push    r15
0x180004c34  lea     rbp, [rsp-20h]
0x180004c39  sub     rsp, 120h
0x180004c40  mov     r14, [rbp+50h+arg_28]
0x180004c47  xor     r12d, r12d
0x180004c4a  mov     r15, [rbp+50h+arg_20]
0x180004c51  mov     ecx, r12d
0x180004c54  mov     [rsp+150h+var_11C], r12w
0x180004c5a  mov     rbx, r9
0x180004c5d  mov     [rsp+150h+var_120], r12w
0x180004c63  mov     rsi, r8
0x180004c66  mov     rdi, rdx
0x180004c69  mov     eax, ecx
0x180004c6b  lea     rdx, [rax+rax]
0x180004c6f  cmp     rdx, 64h ; 'd'
0x180004c73  jnb     loc_180004F4D
0x180004c79  inc     ecx
0x180004c7b  mov     [rsp+rdx+150h+var_F0], r12w
0x180004c81  cmp     ecx, 4
0x180004c84  jbe     short loc_180004C69
0x180004c86  mov     r8d, 50h ; 'P'; Size
0x180004c8c  lea     rcx, [rsp+150h+var_E6]; void *
0x180004c91  mov     rdx, rdi; Src
0x180004c94  call    memcpy_0
0x180004c99  mov     ecx, 2Dh ; '-'
0x180004c9e  mov     eax, ecx
0x180004ca0  lea     rdx, [rax+rax]
0x180004ca4  cmp     rdx, 64h ; 'd'
0x180004ca8  jnb     loc_180004F4D
0x180004cae  inc     ecx
0x180004cb0  mov     [rsp+rdx+150h+var_F0], r12w
0x180004cb6  cmp     ecx, 31h ; '1'
0x180004cb9  jbe     short loc_180004C9E
0x180004cbb  mov     r9d, r12d
0x180004cbe  lea     r13, __ImageBase
0x180004cc5  mov     r10d, 80000000h
0x180004ccb  mov     r11d, 7FFFFFFFh
0x180004cd1  mov     edi, 2000h
0x180004cd6  mov     r8d, r12d
0x180004cd9  lea     eax, [r9+r8]
0x180004cdd  movsx   edx, [rsp+rax*2+150h+var_F0]
0x180004ce2  mov     eax, r8d
0x180004ce5  movsx   eax, ds:rva H[r13+rax*2]
0x180004cee  imul    edx, eax
0x180004cf1  add     edx, edx
0x180004cf3  lea     eax, [rdx+rdi]
0x180004cf6  test    edi, edi
0x180004cf8  jns     short loc_180004D07
0x180004cfa  test    edx, edx
0x180004cfc  jns     short loc_180004D12
0x180004cfe  test    eax, eax
0x180004d00  js      short loc_180004D12
0x180004d02  mov     edi, r10d
0x180004d05  jmp     short loc_180004D14
0x180004d07  test    edx, edx
0x180004d09  js      short loc_180004D12
0x180004d0b  mov     edi, r11d
0x180004d0e  test    eax, eax
0x180004d10  js      short loc_180004D14
0x180004d12  mov     edi, eax
0x180004d14  inc     r8d
0x180004d17  cmp     r8d, 0Ah
0x180004d1b  jbe     short loc_180004CD9
0x180004d1d  lea     eax, [rdi+rdi]
0x180004d20  test    edi, edi
0x180004d22  jns     short loc_180004D2A
0x180004d24  test    eax, eax
0x180004d26  js      short loc_180004D2E
0x180004d28  jmp     short loc_180004D39
0x180004d2a  test    eax, eax
0x180004d2c  js      short loc_180004D42
0x180004d2e  lea     ecx, [rax+rax]
0x180004d31  test    eax, eax
0x180004d33  jns     short loc_180004D3E
0x180004d35  test    ecx, ecx
0x180004d37  js      short loc_180004D45
0x180004d39  mov     ecx, r10d
0x180004d3c  jmp     short loc_180004D45
0x180004d3e  test    ecx, ecx
0x180004d40  jns     short loc_180004D45
0x180004d42  mov     ecx, r11d
0x180004d45  mov     eax, r9d
0x180004d48  inc     r9d
0x180004d4b  sar     ecx, 10h
0x180004d4e  mov     [rbp+rax*2+50h+var_80], cx
0x180004d53  cmp     r9d, 27h ; '''
0x180004d57  jbe     loc_180004CD1
0x180004d5d  mov     r9d, r12d
0x180004d60  mov     [rsi], r12w
0x180004d64  mov     edi, r12d
0x180004d67  mov     edx, r12d
0x180004d6a  mov     r8d, r12d
0x180004d6d  lea     ecx, [rdi+r8*2]
0x180004d71  add     ecx, r8d
0x180004d74  movsx   eax, [rbp+rcx*2+50h+var_80]
0x180004d79  sar     eax, 2
0x180004d7c  imul    eax, eax
0x180004d7f  add     eax, eax
0x180004d81  lea     ecx, [rdx+rax]
0x180004d84  jns     short loc_180004D93
0x180004d86  test    edx, edx
0x180004d88  jns     short loc_180004D9E
0x180004d8a  test    ecx, ecx
0x180004d8c  js      short loc_180004D9E
0x180004d8e  mov     edx, r10d
0x180004d91  jmp     short loc_180004DA0
0x180004d93  test    edx, edx
0x180004d95  js      short loc_180004D9E
0x180004d97  mov     edx, r11d
0x180004d9a  test    ecx, ecx
0x180004d9c  js      short loc_180004DA0
0x180004d9e  mov     edx, ecx
0x180004da0  inc     r8d
0x180004da3  cmp     r8d, 0Ch
0x180004da7  jbe     short loc_180004D6D
0x180004da9  cmp     edx, r9d
0x180004dac  jle     short loc_180004DB9
0x180004dae  mov     [rsi], di
0x180004db1  mov     r9d, edx
0x180004db4  movzx   eax, di
0x180004db7  jmp     short loc_180004DBC
0x180004db9  movzx   eax, word ptr [rsi]
0x180004dbc  inc     edi
0x180004dbe  cmp     edi, 3
0x180004dc1  jbe     short loc_180004D67
0x180004dc3  mov     edx, r12d
0x180004dc6  movsx   edi, ax
0x180004dc9  lea     eax, [rdi+rdx*2]
0x180004dcc  mov     ecx, edx
0x180004dce  add     eax, edx
0x180004dd0  inc     edx
0x180004dd2  movzx   eax, [rbp+rax*2+50h+var_80]
0x180004dd7  mov     [rsp+rcx*2+150h+var_118], ax
0x180004ddc  cmp     edx, 0Ch
0x180004ddf  jbe     short loc_180004DC9
0x180004de1  lea     rax, [rsp+150h+var_120]
0x180004de6  mov     r9, r15
0x180004de9  mov     [rsp+150h+var_128], rax
0x180004dee  lea     rdx, [rsp+150h+var_118]
0x180004df3  lea     rax, [rsp+150h+var_11C]
0x180004df8  mov     r8, rbx
0x180004dfb  mov     [rsp+150h+var_130], rax
0x180004e00  call    APCMQuantize
0x180004e05  movsx   rax, [rsp+150h+var_120]
0x180004e0b  mov     ecx, 6
0x180004e10  mov     ebx, 7FFFh
0x180004e15  movsx   edx, ds:rva FAC[r13+rax*2]
0x180004e1e  mov     r13d, 0FFFF8000h
0x180004e24  movsx   eax, [rsp+150h+var_11C]
0x180004e29  sub     ecx, eax
0x180004e2b  cmp     ecx, r13d
0x180004e2e  jge     short loc_180004E36
0x180004e30  movzx   edi, r13w
0x180004e34  jmp     short loc_180004E41
0x180004e36  cmp     ecx, ebx
0x180004e38  jle     short loc_180004E3E
0x180004e3a  mov     edi, ebx
0x180004e3c  jmp     short loc_180004E41
0x180004e3e  movzx   edi, cx
0x180004e41  movsx   r8d, di
0x180004e45  mov     r9d, r8d
0x180004e48  lea     eax, [r8-1]
0x180004e4c  cmp     eax, r13d
0x180004e4f  jge     short loc_180004E82
0x180004e51  movzx   eax, r13w
0x180004e55  movsx   ecx, ax
0x180004e58  mov     eax, 1
0x180004e5d  neg     ecx
0x180004e5f  sar     eax, cl
0x180004e61  mov     r10d, edx
0x180004e64  movsx   r11d, ax
0x180004e68  mov     rdx, r12
0x180004e6b  movzx   eax, word ptr [r15+rdx*2]
0x180004e70  add     ax, ax
0x180004e73  cwde
0x180004e74  add     eax, 0FFFFFFF9h
0x180004e77  cmp     eax, r13d
0x180004e7a  jge     short loc_180004E9B
0x180004e7c  movzx   eax, r13w
0x180004e80  jmp     short loc_180004EA1
0x180004e82  cmp     eax, ebx
0x180004e84  jle     short loc_180004E8B
0x180004e86  movzx   eax, bx
0x180004e89  jmp     short loc_180004E90
0x180004e8b  test    ax, ax
0x180004e8e  js      short loc_180004E55
0x180004e90  mov     cl, al
0x180004e92  mov     eax, 1
0x180004e97  shl     eax, cl
0x180004e99  jmp     short loc_180004E61
0x180004e9b  cmp     eax, ebx
0x180004e9d  jle     short loc_180004EA1
0x180004e9f  mov     eax, ebx
0x180004ea1  shl     ax, 0Ch
0x180004ea5  mov     ecx, 3FFFFFFFh
0x180004eaa  cwde
0x180004eab  imul    eax, r10d
0x180004eaf  add     eax, 4000h
0x180004eb4  cmp     eax, 40000000h
0x180004eb9  cmovge  eax, ecx
0x180004ebc  shr     eax, 0Fh
0x180004ebf  cwde
0x180004ec0  add     eax, r11d
0x180004ec3  cmp     eax, r13d
0x180004ec6  jge     short loc_180004ECE
0x180004ec8  movzx   eax, r13w
0x180004ecc  jmp     short loc_180004ED4
0x180004ece  cmp     eax, ebx
0x180004ed0  jle     short loc_180004ED4
0x180004ed2  mov     eax, ebx
0x180004ed4  cwde
0x180004ed5  test    di, di
0x180004ed8  js      short loc_180004EE4
0x180004eda  mov     ecx, r9d
0x180004edd  mov     r8d, r9d
0x180004ee0  sar     eax, cl
0x180004ee2  jmp     short loc_180004EEB
0x180004ee4  mov     ecx, r8d
0x180004ee7  neg     ecx
0x180004ee9  shl     eax, cl
0x180004eeb  mov     [rsp+rdx*2+150h+var_118], ax
0x180004ef0  inc     rdx
0x180004ef3  cmp     rdx, 0Dh
0x180004ef7  jnz     loc_180004E6B
0x180004efd  movsx   edx, word ptr [rsi]
0x180004f00  mov     rdi, r14
0x180004f03  movsxd  rax, r12d
0x180004f06  mov     ecx, 28h ; '('
0x180004f0b  movsx   rax, ax
0x180004f0f  mov     r8d, r12d
0x180004f12  rep stosw
0x180004f15  lea     ecx, [rdx+r8*2]
0x180004f19  mov     edi, r8d
0x180004f1c  add     ecx, r8d
0x180004f1f  inc     r8d
0x180004f22  movzx   eax, [rsp+rdi*2+150h+var_118]
0x180004f27  mov     [r14+rcx*2], ax
0x180004f2c  cmp     r8d, 0Ch
0x180004f30  jbe     short loc_180004F15
0x180004f32  mov     rbx, [rsp+150h+arg_0]
0x180004f3a  add     rsp, 120h
0x180004f41  pop     r15
0x180004f43  pop     r14
0x180004f45  pop     r13
0x180004f47  pop     r12
0x180004f49  pop     rdi
0x180004f4a  pop     rsi
0x180004f4b  pop     rbp
0x180004f4c  retn
0x180004f4d  call    __report_rangecheckfailure
```
