# StdEncoderOutputDynamicBlock

- ea: `0x180004760`
- end: `0x180004bd2`
- name: `StdEncoderOutputDynamicBlock`
- size: `1138`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800026e0`

## callees

- `0x180004220`
- `0x180004760`
- `0x180004be0`

## pseudocode

```c
__int64 __fastcall StdEncoderOutputDynamicBlock(__int64 a1)
{
  __int64 v2; // rdi
  int v3; // esi
  int v4; // ecx
  unsigned int v6; // eax
  unsigned int v7; // ecx
  unsigned __int8 *v8; // rdx
  unsigned int v9; // r9d
  int v10; // r10d
  _BYTE *v11; // r14
  __int64 v12; // r8
  int v13; // ecx
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // ecx
  unsigned int v17; // eax
  int v18; // r9d
  unsigned __int8 *v19; // rdx
  int v20; // ecx
  int v21; // edx
  int v22; // ebp
  int v23; // eax
  int v24; // eax
  int v25; // eax
  unsigned __int8 *v26; // rbp
  unsigned int v27; // r9d
  int v28; // r11d
  int v29; // r10d
  int v30; // eax
  __int64 v31; // rax
  int v32; // ecx
  __int64 v33; // rax
  __int64 v34; // rax
  int v35; // ecx
  __int64 v36; // r8
  unsigned int v37; // eax
  int v38; // r9d
  int v39; // eax
  int v40; // edx
  int v41; // ecx
  int v42; // r11d
  int v43; // eax
  int v44; // r8d
  char v45; // cl
  int v46; // eax
  int v47; // edx
  int v48; // eax
  unsigned int v49; // eax
  int v50; // r9d
  unsigned __int8 *v51; // rbp
  unsigned __int8 *v52; // [rsp+50h] [rbp+8h]

  v2 = *(_QWORD *)(a1 + 80);
  v3 = 2;
  if ( *(_DWORD *)a1 )
  {
    if ( *(_DWORD *)a1 != 1 )
      goto LABEL_7;
  }
  else
  {
    v4 = *(unsigned __int16 *)(v2 + 148234);
    *(_DWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 4) = v4;
    *(_QWORD *)(a1 + 16) = v2 + 148236;
    outputBits(a1, 1, 0);
    outputBits(a1, 2, 2);
    *(_DWORD *)a1 = 1;
  }
  if ( *(_QWORD *)(a1 + 40) > (unsigned __int64)(*(_QWORD *)(a1 + 48) - 512LL) )
    return 0;
  outputTreeStructure(a1, v2 + 194976, v2 + 195456);
  *(_DWORD *)a1 = 2;
LABEL_7:
  v6 = *(_DWORD *)(a1 + 24);
  v7 = *(_DWORD *)(a1 + 28);
  if ( v6 >= v7 )
    goto LABEL_48;
  v8 = *(unsigned __int8 **)(a1 + 16);
  v9 = *(_DWORD *)(a1 + 4);
  v10 = *(_DWORD *)(a1 + 8);
  v52 = v8;
  while ( 1 )
  {
    v11 = *(_BYTE **)(a1 + 40);
    if ( (unsigned __int64)v11 >= *(_QWORD *)(a1 + 56) )
      break;
    v12 = (unsigned int)*(__int16 *)(v2 + 2LL * (v9 & 0xFFF) + 181888);
    if ( (int)v12 < 0 )
    {
      v13 = 4096;
      do
      {
        v14 = 2LL * -(int)v12;
        if ( (v13 & v9) != 0 )
          v15 = v14 + 191232;
        else
          v15 = v14 + 190080;
        v13 *= 2;
        v12 = (unsigned int)*(__int16 *)(v2 + v15);
      }
      while ( (int)v12 < 0 );
    }
    v16 = *(unsigned __int8 *)(v12 + v2 + 192384);
    v9 >>= v16;
    v10 -= v16;
    v17 = v9;
    if ( v10 <= 0 )
    {
      v18 = *v8 << (v10 + 16);
      v19 = v8 + 1;
      v9 = v17 | v18;
      v52 = v19;
      v10 += 8;
      if ( v10 <= 0 )
      {
        v9 |= *v19 << (v10 + 16);
        v52 = v19 + 1;
        v10 += 8;
      }
    }
    v20 = *(_DWORD *)(a1 + 68);
    v21 = *(unsigned __int8 *)(v12 + v2 + 194976);
    *(_DWORD *)(a1 + 64) |= *(unsigned __int16 *)(v2 + 2 * v12 + 194400) << v20;
    v22 = *(_DWORD *)(a1 + 64);
    v23 = v21 + v20;
    *(_DWORD *)(a1 + 68) = v21 + v20;
    if ( (unsigned int)v12 >= 0x100 )
    {
      if ( v23 >= 16 )
      {
        *v11 = v22;
        *(_BYTE *)++*(_QWORD *)(a1 + 40) = BYTE1(*(_DWORD *)(a1 + 64));
        ++*(_QWORD *)(a1 + 40);
        v25 = *(unsigned __int16 *)(a1 + 66);
        *(_DWORD *)(a1 + 68) -= 16;
        *(_DWORD *)(a1 + 64) = v25;
      }
      if ( (unsigned int)v12 >= 0x109 && (_mm_lfence(), *((_BYTE *)&g_FastEncoderDistanceTreeLength[1] + v12 + 7)) )
      {
        outputBits(
          a1,
          *((unsigned __int8 *)&g_FastEncoderDistanceTreeLength[1] + v12 + 7),
          v9 & ((1 << *((_BYTE *)&g_FastEncoderDistanceTreeLength[1] + v12 + 7)) - 1));
        v26 = v52;
        v9 = v27 >> v28;
        v10 = v29 - v28;
        if ( v10 <= 0 )
        {
          v26 = v52 + 1;
          v9 |= *v52++ << (v10 + 16);
          v10 += 8;
          if ( v10 <= 0 )
          {
            v30 = *v26++ << (v10 + 16);
            v9 |= v30;
            v52 = v26;
            v10 += 8;
          }
        }
      }
      else
      {
        v26 = v52;
      }
      v31 = (unsigned int)*(__int16 *)(v2 + 2LL * (unsigned __int8)v9 + 181024);
      if ( (int)v31 < 0 )
      {
        v32 = 256;
        do
        {
          v33 = 2LL * -(int)v31;
          if ( (v32 & v9) != 0 )
            v34 = v33 + 181664;
          else
            v34 = v33 + 181536;
          v32 *= 2;
          v31 = (unsigned int)*(__int16 *)(v2 + v34);
        }
        while ( (int)v31 < 0 );
      }
      v35 = *(unsigned __int8 *)(v31 + v2 + 181792);
      v9 >>= v35;
      v10 -= v35;
      v36 = (unsigned int)v31;
      v37 = v9;
      if ( v10 <= 0 )
      {
        v38 = *v26++ << (v10 + 16);
        v9 = v37 | v38;
        v52 = v26;
        v10 += 8;
        if ( v10 <= 0 )
        {
          v39 = *v26++ << (v10 + 16);
          v9 |= v39;
          v52 = v26;
          v10 += 8;
        }
      }
      v40 = *(unsigned __int8 *)(v36 + v2 + 195456);
      v41 = *(_DWORD *)(a1 + 68);
      *(_DWORD *)(a1 + 64) |= *(unsigned __int16 *)(v2 + 2 * v36 + 195392) << v41;
      v42 = *(_DWORD *)(a1 + 64);
      v43 = v40 + v41;
      *(_DWORD *)(a1 + 68) = v40 + v41;
      if ( v40 + v41 >= 16 )
      {
        *(_BYTE *)(*(_QWORD *)(a1 + 40))++ = v42;
        *(_BYTE *)(*(_QWORD *)(a1 + 40))++ = BYTE1(*(_DWORD *)(a1 + 64));
        v42 = *(unsigned __int16 *)(a1 + 66);
        *(_DWORD *)(a1 + 68) -= 16;
        v43 = *(_DWORD *)(a1 + 68);
        *(_DWORD *)(a1 + 64) = v42;
      }
      v44 = (unsigned __int8)g_ExtraDistanceBits[v36];
      if ( v44 )
      {
        v45 = v43;
        v46 = v44 + v43;
        *(_DWORD *)(a1 + 68) = v46;
        v47 = v42 | ((v9 & ((1 << v44) - 1)) << v45);
        *(_DWORD *)(a1 + 64) = v47;
        if ( v46 >= 16 )
        {
          *(_BYTE *)(*(_QWORD *)(a1 + 40))++ = v47;
          *(_BYTE *)(*(_QWORD *)(a1 + 40))++ = BYTE1(*(_DWORD *)(a1 + 64));
          v48 = *(unsigned __int16 *)(a1 + 66);
          *(_DWORD *)(a1 + 68) -= 16;
          *(_DWORD *)(a1 + 64) = v48;
        }
        v10 -= v44;
        v9 >>= v44;
        v49 = v9;
        if ( v10 <= 0 )
        {
          v50 = *v26 << (v10 + 16);
          v51 = v26 + 1;
          v9 = v49 | v50;
          v52 = v51;
          v10 += 8;
          if ( v10 <= 0 )
          {
            v9 |= *v51 << (v10 + 16);
            v52 = v51 + 1;
            v10 += 8;
          }
        }
      }
    }
    else if ( v23 >= 16 )
    {
      *v11 = v22;
      *(_BYTE *)++*(_QWORD *)(a1 + 40) = BYTE1(*(_DWORD *)(a1 + 64));
      ++*(_QWORD *)(a1 + 40);
      v24 = *(unsigned __int16 *)(a1 + 66);
      *(_DWORD *)(a1 + 68) -= 16;
      *(_DWORD *)(a1 + 64) = v24;
    }
    v6 = ++*(_DWORD *)(a1 + 24);
    v7 = *(_DWORD *)(a1 + 28);
    v8 = v52;
    if ( v6 >= v7 )
      goto LABEL_48;
  }
  if ( v6 >= v7 )
  {
LABEL_48:
    outputBits(a1, *(unsigned __int8 *)(v2 + 195232), *(unsigned __int16 *)(v2 + 194912));
    v3 = 0;
  }
  else
  {
    *(_DWORD *)(a1 + 4) = v9;
    *(_DWORD *)(a1 + 8) = v10;
    *(_QWORD *)(a1 + 16) = v8;
  }
  *(_DWORD *)a1 = v3;
  return 1;
}

```

## disassembly

```asm
0x180004760  mov     [rsp+arg_18], rbx
0x180004765  push    rsi
0x180004766  push    rdi
0x180004767  push    r12
0x180004769  push    r13
0x18000476b  push    r15
0x18000476d  sub     rsp, 20h
0x180004771  mov     eax, [rcx]
0x180004773  mov     rbx, rcx
0x180004776  mov     rdi, [rcx+50h]
0x18000477a  mov     esi, 2
0x18000477f  test    eax, eax
0x180004781  jnz     short loc_1800047D0
0x180004783  movzx   ecx, byte ptr [rdi+2430Bh]
0x18000478a  xor     r8d, r8d
0x18000478d  movzx   eax, byte ptr [rdi+2430Ah]
0x180004794  mov     edx, 1
0x180004799  shl     ecx, 8
0x18000479c  or      ecx, eax
0x18000479e  mov     dword ptr [rbx+8], 0
0x1800047a5  mov     [rbx+4], ecx
0x1800047a8  lea     rax, [rdi+2430Ch]
0x1800047af  mov     rcx, rbx
0x1800047b2  mov     [rbx+10h], rax
0x1800047b6  call    outputBits
0x1800047bb  mov     r8d, esi
0x1800047be  mov     edx, esi
0x1800047c0  mov     rcx, rbx
0x1800047c3  call    outputBits
0x1800047c8  mov     dword ptr [rbx], 1
0x1800047ce  jmp     short loc_1800047D5
0x1800047d0  cmp     eax, 1
0x1800047d3  jnz     short loc_180004804
0x1800047d5  mov     rax, [rbx+30h]
0x1800047d9  sub     rax, 200h
0x1800047df  cmp     [rbx+28h], rax
0x1800047e3  jbe     short loc_1800047EC
0x1800047e5  xor     eax, eax
0x1800047e7  jmp     loc_180004BAE
0x1800047ec  lea     r8, [rdi+2FB80h]
0x1800047f3  mov     rcx, rbx
0x1800047f6  lea     rdx, [rdi+2F9A0h]
0x1800047fd  call    outputTreeStructure
0x180004802  mov     [rbx], esi
0x180004804  mov     eax, [rbx+18h]
0x180004807  mov     ecx, [rbx+1Ch]
0x18000480a  mov     [rsp+48h+arg_8], rbp
0x18000480f  mov     [rsp+48h+arg_10], r14
0x180004814  cmp     eax, ecx
0x180004816  jnb     loc_180004B84
0x18000481c  mov     rdx, [rbx+10h]
0x180004820  mov     r9d, [rbx+4]
0x180004824  mov     r10d, [rbx+8]
0x180004828  mov     [rsp+48h+arg_0], rdx
0x18000482d  nop     dword ptr [rax]
0x180004830  mov     r14, [rbx+28h]
0x180004834  cmp     r14, [rbx+38h]
0x180004838  jnb     loc_180004BC0
0x18000483e  mov     eax, r9d
0x180004841  and     eax, 0FFFh
0x180004846  movsx   r8d, word ptr [rdi+rax*2+2C680h]
0x18000484f  test    r8d, r8d
0x180004852  jns     short loc_180004883
0x180004854  mov     ecx, 1000h
0x180004859  neg     r8d
0x18000485c  movsxd  rax, r8d
0x18000485f  add     rax, rax
0x180004862  test    r9d, ecx
0x180004865  jnz     short loc_18000486F
0x180004867  add     rax, 2E680h
0x18000486d  jmp     short loc_180004875
0x18000486f  add     rax, 2EB00h
0x180004875  add     rax, rdi
0x180004878  add     ecx, ecx
0x18000487a  movsx   r8d, word ptr [rax]
0x18000487e  test    r8d, r8d
0x180004881  js      short loc_180004859
0x180004883  movzx   ecx, byte ptr [r8+rdi+2EF80h]
0x18000488c  shr     r9d, cl
0x18000488f  sub     r10d, ecx
0x180004892  mov     eax, r9d
0x180004895  test    r10d, r10d
0x180004898  jg      short loc_1800048D1
0x18000489a  movzx   r9d, byte ptr [rdx]
0x18000489e  lea     ecx, [r10+10h]
0x1800048a2  shl     r9d, cl
0x1800048a5  inc     rdx
0x1800048a8  or      r9d, eax
0x1800048ab  mov     [rsp+48h+arg_0], rdx
0x1800048b0  add     r10d, 8
0x1800048b4  test    r10d, r10d
0x1800048b7  jg      short loc_1800048D1
0x1800048b9  movzx   eax, byte ptr [rdx]
0x1800048bc  lea     ecx, [r10+10h]
0x1800048c0  shl     eax, cl
0x1800048c2  inc     rdx
0x1800048c5  or      r9d, eax
0x1800048c8  mov     [rsp+48h+arg_0], rdx
0x1800048cd  add     r10d, 8
0x1800048d1  mov     ecx, [rbx+44h]
0x1800048d4  movzx   edx, byte ptr [r8+rdi+2F9A0h]
0x1800048dd  movzx   eax, word ptr [rdi+r8*2+2F760h]
0x1800048e6  shl     eax, cl
0x1800048e8  or      [rbx+40h], eax
0x1800048eb  mov     ebp, [rbx+40h]
0x1800048ee  lea     eax, [rdx+rcx]
0x1800048f1  mov     [rbx+44h], eax
0x1800048f4  cmp     r8d, 100h
0x1800048fb  jnb     short loc_18000492D
0x1800048fd  cmp     eax, 10h
0x180004900  jl      loc_180004B6E
0x180004906  mov     [r14], bpl
0x180004909  inc     qword ptr [rbx+28h]
0x18000490d  mov     eax, [rbx+40h]
0x180004910  mov     rcx, [rbx+28h]
0x180004914  shr     eax, 8
0x180004917  mov     [rcx], al
0x180004919  inc     qword ptr [rbx+28h]
0x18000491d  movzx   eax, word ptr [rbx+42h]
0x180004921  add     dword ptr [rbx+44h], 0FFFFFFF0h
0x180004925  mov     [rbx+40h], eax
0x180004928  jmp     loc_180004B6E
0x18000492d  cmp     eax, 10h
0x180004930  jl      short loc_180004954
0x180004932  mov     [r14], bpl
0x180004935  inc     qword ptr [rbx+28h]
0x180004939  mov     eax, [rbx+40h]
0x18000493c  mov     rcx, [rbx+28h]
0x180004940  shr     eax, 8
0x180004943  mov     [rcx], al
0x180004945  inc     qword ptr [rbx+28h]
0x180004949  movzx   eax, word ptr [rbx+42h]
0x18000494d  add     dword ptr [rbx+44h], 0FFFFFFF0h
0x180004951  mov     [rbx+40h], eax
0x180004954  lea     r14, cs:180000000h
0x18000495b  cmp     r8d, 109h
0x180004962  jb      short loc_1800049E3
0x180004964  lfence
0x180004967  movzx   r11d, byte ptr [r8+r14+783Fh]
0x180004970  test    r11d, r11d
0x180004973  jz      short loc_1800049E3
0x180004975  mov     ecx, r11d
0x180004978  mov     r8d, 1
0x18000497e  shl     r8d, cl
0x180004981  mov     edx, r11d
0x180004984  dec     r8d
0x180004987  mov     rcx, rbx
0x18000498a  and     r8d, r9d
0x18000498d  call    outputBits
0x180004992  mov     rbp, [rsp+48h+arg_0]
0x180004997  mov     ecx, r11d
0x18000499a  shr     r9d, cl
0x18000499d  sub     r10d, r11d
0x1800049a0  mov     eax, r9d
0x1800049a3  test    r10d, r10d
0x1800049a6  jg      short loc_1800049E8
0x1800049a8  movzx   r9d, byte ptr [rbp+0]
0x1800049ad  lea     ecx, [r10+10h]
0x1800049b1  shl     r9d, cl
0x1800049b4  inc     rbp
0x1800049b7  or      r9d, eax
0x1800049ba  mov     [rsp+48h+arg_0], rbp
0x1800049bf  add     r10d, 8
0x1800049c3  test    r10d, r10d
0x1800049c6  jg      short loc_1800049E8
0x1800049c8  movzx   eax, byte ptr [rbp+0]
0x1800049cc  lea     ecx, [r10+10h]
0x1800049d0  shl     eax, cl
0x1800049d2  inc     rbp
0x1800049d5  or      r9d, eax
0x1800049d8  mov     [rsp+48h+arg_0], rbp
0x1800049dd  add     r10d, 8
0x1800049e1  jmp     short loc_1800049E8
0x1800049e3  mov     rbp, [rsp+48h+arg_0]
0x1800049e8  movzx   ecx, r9b
0x1800049ec  movsx   eax, word ptr [rdi+rcx*2+2C320h]
0x1800049f4  test    eax, eax
0x1800049f6  jns     short loc_180004A23
0x1800049f8  mov     ecx, 100h
0x1800049fd  neg     eax
0x1800049ff  cdqe
0x180004a01  add     rax, rax
0x180004a04  test    r9d, ecx
0x180004a07  jnz     short loc_180004A11
0x180004a09  add     rax, 2C520h
0x180004a0f  jmp     short loc_180004A17
0x180004a11  add     rax, 2C5A0h
0x180004a17  add     rax, rdi
0x180004a1a  add     ecx, ecx
0x180004a1c  movsx   eax, word ptr [rax]
0x180004a1f  test    eax, eax
0x180004a21  js      short loc_1800049FD
0x180004a23  movzx   ecx, byte ptr [rax+rdi+2C620h]
0x180004a2b  shr     r9d, cl
0x180004a2e  sub     r10d, ecx
0x180004a31  mov     r8d, eax
0x180004a34  mov     eax, r9d
0x180004a37  test    r10d, r10d
0x180004a3a  jg      short loc_180004A75
0x180004a3c  movzx   r9d, byte ptr [rbp+0]
0x180004a41  lea     ecx, [r10+10h]
0x180004a45  shl     r9d, cl
0x180004a48  inc     rbp
0x180004a4b  or      r9d, eax
0x180004a4e  mov     [rsp+48h+arg_0], rbp
0x180004a53  add     r10d, 8
0x180004a57  test    r10d, r10d
0x180004a5a  jg      short loc_180004A75
0x180004a5c  movzx   eax, byte ptr [rbp+0]
0x180004a60  lea     ecx, [r10+10h]
0x180004a64  shl     eax, cl
0x180004a66  inc     rbp
0x180004a69  or      r9d, eax
0x180004a6c  mov     [rsp+48h+arg_0], rbp
0x180004a71  add     r10d, 8
0x180004a75  movzx   edx, byte ptr [r8+rdi+2FB80h]
0x180004a7e  mov     ecx, [rbx+44h]
0x180004a81  movzx   eax, word ptr [rdi+r8*2+2FB40h]
0x180004a8a  shl     eax, cl
0x180004a8c  or      [rbx+40h], eax
0x180004a8f  mov     r11d, [rbx+40h]
0x180004a93  lea     eax, [rdx+rcx]
0x180004a96  mov     [rbx+44h], eax
0x180004a99  cmp     eax, 10h
0x180004a9c  jl      short loc_180004AC9
0x180004a9e  mov     rax, [rbx+28h]
0x180004aa2  mov     [rax], r11b
0x180004aa5  inc     qword ptr [rbx+28h]
0x180004aa9  mov     eax, [rbx+40h]
0x180004aac  mov     rcx, [rbx+28h]
0x180004ab0  shr     eax, 8
0x180004ab3  mov     [rcx], al
0x180004ab5  inc     qword ptr [rbx+28h]
0x180004ab9  movzx   r11d, word ptr [rbx+42h]
0x180004abe  add     dword ptr [rbx+44h], 0FFFFFFF0h
0x180004ac2  mov     eax, [rbx+44h]
0x180004ac5  mov     [rbx+40h], r11d
0x180004ac9  movzx   r8d, byte ptr [r8+r14+7920h]
0x180004ad2  test    r8d, r8d
0x180004ad5  jz      loc_180004B6E
0x180004adb  mov     ecx, r8d
0x180004ade  mov     edx, 1
0x180004ae3  shl     edx, cl
0x180004ae5  mov     ecx, eax
0x180004ae7  dec     edx
0x180004ae9  add     eax, r8d
0x180004aec  and     edx, r9d
0x180004aef  mov     [rbx+44h], eax
0x180004af2  shl     edx, cl
0x180004af4  or      edx, r11d
0x180004af7  mov     [rbx+40h], edx
0x180004afa  cmp     eax, 10h
0x180004afd  jl      short loc_180004B24
0x180004aff  mov     rax, [rbx+28h]
0x180004b03  mov     [rax], dl
0x180004b05  inc     qword ptr [rbx+28h]
0x180004b09  mov     eax, [rbx+40h]
0x180004b0c  mov     rcx, [rbx+28h]
0x180004b10  shr     eax, 8
0x180004b13  mov     [rcx], al
0x180004b15  inc     qword ptr [rbx+28h]
0x180004b19  movzx   eax, word ptr [rbx+42h]
0x180004b1d  add     dword ptr [rbx+44h], 0FFFFFFF0h
0x180004b21  mov     [rbx+40h], eax
0x180004b24  mov     ecx, r8d
0x180004b27  sub     r10d, r8d
0x180004b2a  shr     r9d, cl
0x180004b2d  mov     eax, r9d
0x180004b30  test    r10d, r10d
0x180004b33  jg      short loc_180004B6E
0x180004b35  movzx   r9d, byte ptr [rbp+0]
0x180004b3a  lea     ecx, [r10+10h]
0x180004b3e  shl     r9d, cl
0x180004b41  inc     rbp
0x180004b44  or      r9d, eax
0x180004b47  mov     [rsp+48h+arg_0], rbp
0x180004b4c  add     r10d, 8
0x180004b50  test    r10d, r10d
0x180004b53  jg      short loc_180004B6E
0x180004b55  movzx   eax, byte ptr [rbp+0]
0x180004b59  lea     ecx, [r10+10h]
0x180004b5d  shl     eax, cl
0x180004b5f  inc     rbp
0x180004b62  or      r9d, eax
0x180004b65  mov     [rsp+48h+arg_0], rbp
0x180004b6a  add     r10d, 8
0x180004b6e  inc     dword ptr [rbx+18h]
0x180004b71  mov     eax, [rbx+18h]
0x180004b74  mov     ecx, [rbx+1Ch]
0x180004b77  mov     rdx, [rsp+48h+arg_0]
0x180004b7c  cmp     eax, ecx
0x180004b7e  jb      loc_180004830
0x180004b84  movzx   r8d, word ptr [rdi+2F960h]
0x180004b8c  mov     rcx, rbx
0x180004b8f  movzx   edx, byte ptr [rdi+2FAA0h]
0x180004b96  call    outputBits
0x180004b9b  xor     esi, esi
0x180004b9d  mov     [rbx], esi
0x180004b9f  mov     eax, 1
0x180004ba4  mov     r14, [rsp+48h+arg_10]
  ... truncated ...
```
