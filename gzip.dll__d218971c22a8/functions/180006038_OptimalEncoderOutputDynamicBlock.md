# OptimalEncoderOutputDynamicBlock

- ea: `0x180006038`
- end: `0x18000637d`
- name: `OptimalEncoderOutputDynamicBlock`
- size: `837`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005e58`

## callees

- `0x180004220`
- `0x180004be0`
- `0x180006038`

## pseudocode

```c
__int64 __fastcall OptimalEncoderOutputDynamicBlock(__int64 a1)
{
  __int64 v2; // rdi
  int v3; // r15d
  int v4; // edx
  unsigned int v6; // ecx
  unsigned int v7; // edx
  unsigned __int8 *v8; // r11
  unsigned int v9; // r9d
  int v10; // r10d
  __int64 v11; // rbp
  int v12; // edx
  __int64 v13; // rcx
  int v14; // ebp
  unsigned __int8 *v15; // r11
  int v16; // r10d
  int v17; // r10d
  unsigned int v18; // r9d
  unsigned int v19; // eax
  int v20; // r9d
  unsigned __int8 *v21; // r11
  int v22; // r10d
  __int64 v23; // rdx
  int v24; // r8d
  __int64 v25; // rcx
  __int64 v26; // rbp
  int v27; // ebp
  int v28; // r10d
  unsigned int v29; // r9d
  unsigned int v30; // eax
  int v31; // r9d
  int v32; // eax

  v2 = *(_QWORD *)(a1 + 88);
  v3 = 2;
  if ( *(_DWORD *)a1 )
  {
    if ( *(_DWORD *)a1 != 1 )
      goto LABEL_7;
  }
  else
  {
    v4 = *(unsigned __int16 *)(v2 + 475628);
    *(_DWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 4) = v4;
    *(_QWORD *)(a1 + 16) = v2 + 475630;
    outputBits(a1, 1, 0);
    outputBits(a1, 2, 2);
    *(_DWORD *)a1 = 1;
  }
  if ( *(_QWORD *)(a1 + 40) > (unsigned __int64)(*(_QWORD *)(a1 + 48) - 512LL) )
    return 0;
  outputTreeStructure(a1, v2 + 555140, v2 + 555620);
  *(_DWORD *)a1 = 2;
LABEL_7:
  v6 = *(_DWORD *)(a1 + 24);
  v7 = *(_DWORD *)(a1 + 28);
  if ( v6 >= v7 )
    goto LABEL_27;
  v8 = *(unsigned __int8 **)(a1 + 16);
  v9 = *(_DWORD *)(a1 + 4);
  v10 = *(_DWORD *)(a1 + 8);
  while ( *(_QWORD *)(a1 + 40) < *(_QWORD *)(a1 + 56) )
  {
    v11 = (unsigned int)*(__int16 *)(v2 + 2LL * (v9 & 0xFFF) + 542052);
    if ( (int)v11 < 0 )
    {
      v12 = 4096;
      do
      {
        v13 = (v9 & v12) != 0 ? 0x480 : 0;
        v12 *= 2;
        v11 = (unsigned int)*(__int16 *)(v13 + 550244 - 2LL * (int)v11 + v2);
      }
      while ( (int)v11 < 0 );
    }
    outputBits(a1, *(unsigned __int8 *)(v11 + v2 + 555140), *(unsigned __int16 *)(v2 + 2 * v11 + 554564));
    if ( (unsigned int)v11 >= 0x100 )
    {
      if ( (unsigned int)v11 >= 0x109 )
      {
        _mm_lfence();
        v14 = *((unsigned __int8 *)&g_FastEncoderDistanceTreeLength[1] + v11 + 7);
        if ( v14 )
        {
          outputBits(a1, v14, v9 & ((1 << v14) - 1));
          v17 = v16 - v14;
          v9 = v18 >> v14;
          v19 = v9;
          if ( v17 <= 0 )
          {
            v20 = *v15 << (v17 + 16);
            v21 = v15 + 1;
            v9 = v19 | v20;
            v22 = v17 + 8;
            if ( v22 <= 0 )
              v9 |= *v21 << (v22 + 16);
          }
        }
      }
      v23 = (unsigned int)*(__int16 *)(v2 + 2LL * (unsigned __int8)v9 + 541188);
      if ( (int)v23 < 0 )
      {
        v24 = 256;
        do
        {
          v25 = (v9 & v24) != 0 ? 0x80 : 0;
          v24 *= 2;
          v23 = (unsigned int)*(__int16 *)(v25 + 541700 - 2LL * (int)v23 + v2);
        }
        while ( (int)v23 < 0 );
      }
      v26 = (unsigned int)v23;
      outputBits(a1, *(unsigned __int8 *)(v2 + v23 + 555620), *(unsigned __int16 *)(v2 + 2 * v23 + 555556));
      v27 = (unsigned __int8)g_ExtraDistanceBits[v26];
      if ( v27 )
      {
        outputBits(a1, v27, v9 & ((1 << v27) - 1));
        v10 = v28 - v27;
        v9 = v29 >> v27;
        v30 = v9;
        if ( v10 <= 0 )
        {
          v31 = *v8++ << (v10 + 16);
          v9 = v30 | v31;
          v10 += 8;
          if ( v10 <= 0 )
          {
            v32 = *v8++ << (v10 + 16);
            v9 |= v32;
            v10 += 8;
          }
        }
      }
    }
    v6 = ++*(_DWORD *)(a1 + 24);
    v7 = *(_DWORD *)(a1 + 28);
    if ( v6 >= v7 )
      goto LABEL_27;
  }
  if ( v6 >= v7 )
  {
LABEL_27:
    outputBits(a1, *(unsigned __int8 *)(v2 + 555396), *(unsigned __int16 *)(v2 + 555076));
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
0x180006038  push    rbx
0x18000603a  push    rbp
0x18000603b  push    rdi
0x18000603c  push    r13
0x18000603e  push    r14
0x180006040  push    r15
0x180006042  sub     rsp, 28h
0x180006046  cmp     dword ptr [rcx], 0
0x180006049  mov     rbx, rcx
0x18000604c  mov     rdi, [rcx+58h]
0x180006050  mov     r15d, 2
0x180006056  jnz     short loc_1800060A2
0x180006058  movzx   eax, byte ptr [rdi+741ECh]
0x18000605f  xor     r8d, r8d
0x180006062  movzx   edx, byte ptr [rdi+741EDh]
0x180006069  shl     edx, 8
0x18000606c  or      edx, eax
0x18000606e  mov     dword ptr [rcx+8], 0
0x180006075  mov     [rcx+4], edx
0x180006078  lea     rax, [rdi+741EEh]
0x18000607f  lea     edx, [r15-1]
0x180006083  mov     [rcx+10h], rax
0x180006087  call    outputBits
0x18000608c  mov     r8d, r15d
0x18000608f  mov     edx, r15d
0x180006092  mov     rcx, rbx
0x180006095  call    outputBits
0x18000609a  mov     dword ptr [rbx], 1
0x1800060a0  jmp     short loc_1800060A7
0x1800060a2  cmp     dword ptr [rcx], 1
0x1800060a5  jnz     short loc_1800060D7
0x1800060a7  mov     rax, [rbx+30h]
0x1800060ab  sub     rax, 200h
0x1800060b1  cmp     [rbx+28h], rax
0x1800060b5  jbe     short loc_1800060BE
0x1800060b7  xor     eax, eax
0x1800060b9  jmp     loc_18000635D
0x1800060be  lea     r8, [rdi+87A64h]
0x1800060c5  mov     rcx, rbx
0x1800060c8  lea     rdx, [rdi+87884h]
0x1800060cf  call    outputTreeStructure
0x1800060d4  mov     [rbx], r15d
0x1800060d7  mov     ecx, [rbx+18h]
0x1800060da  mov     edx, [rbx+1Ch]
0x1800060dd  cmp     ecx, edx
0x1800060df  jnb     loc_18000633B
0x1800060e5  mov     r11, [rbx+10h]
0x1800060e9  lea     r13, cs:180000000h
0x1800060f0  mov     r9d, [rbx+4]
0x1800060f4  mov     r10d, [rbx+8]
0x1800060f8  mov     rax, [rbx+38h]
0x1800060fc  cmp     [rbx+28h], rax
0x180006100  jnb     loc_18000636B
0x180006106  mov     eax, r9d
0x180006109  and     eax, 0FFFh
0x18000610e  movsx   ebp, word ptr [rdi+rax*2+84564h]
0x180006116  test    ebp, ebp
0x180006118  jns     short loc_180006149
0x18000611a  mov     edx, 1000h
0x18000611f  mov     eax, edx
0x180006121  and     eax, r9d
0x180006124  neg     eax
0x180006126  movsxd  rax, ebp
0x180006129  sbb     rcx, rcx
0x18000612c  add     rax, rax
0x18000612f  and     ecx, 480h
0x180006135  add     edx, edx
0x180006137  add     rcx, 86564h
0x18000613e  sub     rcx, rax
0x180006141  movsx   ebp, word ptr [rcx+rdi]
0x180006145  test    ebp, ebp
0x180006147  js      short loc_18000611F
0x180006149  movzx   ecx, byte ptr [rbp+rdi+86E64h]
0x180006151  shr     r9d, cl
0x180006154  sub     r10d, ecx
0x180006157  mov     eax, r9d
0x18000615a  test    r10d, r10d
0x18000615d  jg      short loc_18000618D
0x18000615f  movzx   r9d, byte ptr [r11]
0x180006163  lea     ecx, [r10+10h]
0x180006167  shl     r9d, cl
0x18000616a  inc     r11
0x18000616d  or      r9d, eax
0x180006170  add     r10d, 8
0x180006174  test    r10d, r10d
0x180006177  jg      short loc_18000618D
0x180006179  movzx   eax, byte ptr [r11]
0x18000617d  lea     ecx, [r10+10h]
0x180006181  shl     eax, cl
0x180006183  inc     r11
0x180006186  or      r9d, eax
0x180006189  add     r10d, 8
0x18000618d  movzx   r8d, word ptr [rdi+rbp*2+87644h]
0x180006196  mov     rcx, rbx
0x180006199  movzx   edx, byte ptr [rbp+rdi+87884h]
0x1800061a1  call    outputBits
0x1800061a6  cmp     ebp, 100h
0x1800061ac  jb      loc_18000632A
0x1800061b2  cmp     ebp, 109h
0x1800061b8  jb      short loc_180006223
0x1800061ba  lfence
0x1800061bd  movzx   ebp, byte ptr [rbp+r13+783Fh]
0x1800061c6  test    ebp, ebp
0x1800061c8  jz      short loc_180006223
0x1800061ca  mov     ecx, ebp
0x1800061cc  mov     r8d, 1
0x1800061d2  shl     r8d, cl
0x1800061d5  mov     edx, ebp
0x1800061d7  dec     r8d
0x1800061da  mov     rcx, rbx
0x1800061dd  and     r8d, r9d
0x1800061e0  call    outputBits
0x1800061e5  mov     ecx, ebp
0x1800061e7  sub     r10d, ebp
0x1800061ea  shr     r9d, cl
0x1800061ed  mov     eax, r9d
0x1800061f0  test    r10d, r10d
0x1800061f3  jg      short loc_180006223
0x1800061f5  movzx   r9d, byte ptr [r11]
0x1800061f9  lea     ecx, [r10+10h]
0x1800061fd  shl     r9d, cl
0x180006200  inc     r11
0x180006203  or      r9d, eax
0x180006206  add     r10d, 8
0x18000620a  test    r10d, r10d
0x18000620d  jg      short loc_180006223
0x18000620f  movzx   eax, byte ptr [r11]
0x180006213  lea     ecx, [r10+10h]
0x180006217  shl     eax, cl
0x180006219  inc     r11
0x18000621c  or      r9d, eax
0x18000621f  add     r10d, 8
0x180006223  movzx   ecx, r9b
0x180006227  movsx   edx, word ptr [rdi+rcx*2+84204h]
0x18000622f  test    edx, edx
0x180006231  jns     short loc_180006265
0x180006233  mov     r8d, 100h
0x180006239  mov     eax, r8d
0x18000623c  and     eax, r9d
0x18000623f  neg     eax
0x180006241  movsxd  rax, edx
0x180006244  sbb     rcx, rcx
0x180006247  add     rax, rax
0x18000624a  and     ecx, 80h
0x180006250  add     r8d, r8d
0x180006253  add     rcx, 84404h
0x18000625a  sub     rcx, rax
0x18000625d  movsx   edx, word ptr [rcx+rdi]
0x180006261  test    edx, edx
0x180006263  js      short loc_180006239
0x180006265  movzx   ecx, byte ptr [rdi+rdx+84504h]
0x18000626d  shr     r9d, cl
0x180006270  sub     r10d, ecx
0x180006273  mov     ebp, edx
0x180006275  mov     eax, r9d
0x180006278  test    r10d, r10d
0x18000627b  jg      short loc_1800062AB
0x18000627d  movzx   r9d, byte ptr [r11]
0x180006281  lea     ecx, [r10+10h]
0x180006285  shl     r9d, cl
0x180006288  inc     r11
0x18000628b  or      r9d, eax
0x18000628e  add     r10d, 8
0x180006292  test    r10d, r10d
0x180006295  jg      short loc_1800062AB
0x180006297  movzx   eax, byte ptr [r11]
0x18000629b  lea     ecx, [r10+10h]
0x18000629f  shl     eax, cl
0x1800062a1  inc     r11
0x1800062a4  or      r9d, eax
0x1800062a7  add     r10d, 8
0x1800062ab  movzx   r8d, word ptr [rdi+rdx*2+87A24h]
0x1800062b4  mov     rcx, rbx
0x1800062b7  movzx   edx, byte ptr [rdi+rdx+87A64h]
0x1800062bf  call    outputBits
0x1800062c4  movzx   ebp, ds:rva g_ExtraDistanceBits[r13+rbp]
0x1800062cd  test    ebp, ebp
0x1800062cf  jz      short loc_18000632A
0x1800062d1  mov     ecx, ebp
0x1800062d3  mov     r8d, 1
0x1800062d9  shl     r8d, cl
0x1800062dc  mov     edx, ebp
0x1800062de  dec     r8d
0x1800062e1  mov     rcx, rbx
0x1800062e4  and     r8d, r9d
0x1800062e7  call    outputBits
0x1800062ec  mov     ecx, ebp
0x1800062ee  sub     r10d, ebp
0x1800062f1  shr     r9d, cl
0x1800062f4  mov     eax, r9d
0x1800062f7  test    r10d, r10d
0x1800062fa  jg      short loc_18000632A
0x1800062fc  movzx   r9d, byte ptr [r11]
0x180006300  lea     ecx, [r10+10h]
0x180006304  shl     r9d, cl
0x180006307  inc     r11
0x18000630a  or      r9d, eax
0x18000630d  add     r10d, 8
0x180006311  test    r10d, r10d
0x180006314  jg      short loc_18000632A
0x180006316  movzx   eax, byte ptr [r11]
0x18000631a  lea     ecx, [r10+10h]
0x18000631e  shl     eax, cl
0x180006320  inc     r11
0x180006323  or      r9d, eax
0x180006326  add     r10d, 8
0x18000632a  inc     dword ptr [rbx+18h]
0x18000632d  mov     ecx, [rbx+18h]
0x180006330  mov     edx, [rbx+1Ch]
0x180006333  cmp     ecx, edx
0x180006335  jb      loc_1800060F8
0x18000633b  movzx   r8d, word ptr [rdi+87844h]
0x180006343  mov     rcx, rbx
0x180006346  movzx   edx, byte ptr [rdi+87984h]
0x18000634d  call    outputBits
0x180006352  xor     r15d, r15d
0x180006355  mov     [rbx], r15d
0x180006358  mov     eax, 1
0x18000635d  add     rsp, 28h
0x180006361  pop     r15
0x180006363  pop     r14
0x180006365  pop     r13
0x180006367  pop     rdi
0x180006368  pop     rbp
0x180006369  pop     rbx
0x18000636a  retn
0x18000636b  cmp     ecx, edx
0x18000636d  jnb     short loc_18000633B
0x18000636f  mov     [rbx+4], r9d
0x180006373  mov     [rbx+8], r10d
0x180006377  mov     [rbx+10h], r11
0x18000637b  jmp     short loc_180006355
```
