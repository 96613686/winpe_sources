# makeTable

- ea: `0x180004c30`
- end: `0x180004ed4`
- name: `makeTable`
- size: `676`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800026e0`
- `0x180005e58`

## callees

- `0x180004c30`
- `0x180006ad5`
- `0x180006b00`

## pseudocode

```c
__int64 __fastcall makeTable(int a1, int a2, __int64 a3, _WORD *a4, __int64 a5, __int64 a6)
{
  int v8; // ebx
  __int64 v10; // rdx
  int v11; // r15d
  __int64 v12; // rcx
  int j; // ecx
  __int64 v14; // rcx
  _WORD *v15; // rdi
  __int64 v16; // r8
  __int64 v17; // rdx
  unsigned int v18; // eax
  unsigned int v19; // r11d
  _DWORD *v20; // r10
  unsigned int v21; // edi
  int v22; // ecx
  int v23; // r11d
  int m; // edi
  int v25; // edx
  __int64 v26; // r9
  int v27; // r8d
  int v28; // edx
  int n; // ecx
  int v30; // edx
  int v31; // r10d
  __int16 *v32; // r8
  __int16 v33; // ax
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int128 v38; // [rsp+30h] [rbp-D0h]
  __int128 v39; // [rsp+40h] [rbp-C0h]
  __int128 v40; // [rsp+50h] [rbp-B0h]
  __int128 i; // [rsp+60h] [rbp-A0h]
  int v42; // [rsp+70h] [rbp-90h]
  _DWORD v43[1]; // [rsp+80h] [rbp-80h] BYREF
  int v44; // [rsp+84h] [rbp-7Ch]
  int v45; // [rsp+88h] [rbp-78h]
  int v46; // [rsp+8Ch] [rbp-74h]
  int v47; // [rsp+90h] [rbp-70h]
  int v48; // [rsp+94h] [rbp-6Ch]
  int v49; // [rsp+98h] [rbp-68h]
  int v50; // [rsp+9Ch] [rbp-64h]
  int v51; // [rsp+A0h] [rbp-60h]
  int v52; // [rsp+A4h] [rbp-5Ch]
  int v53; // [rsp+A8h] [rbp-58h]
  int v54; // [rsp+ACh] [rbp-54h]
  int v55; // [rsp+B0h] [rbp-50h]
  int v56; // [rsp+B4h] [rbp-4Ch]
  int v57; // [rsp+B8h] [rbp-48h]
  int v58; // [rsp+BCh] [rbp-44h]
  int k; // [rsp+C0h] [rbp-40h]
  _DWORD v60[288]; // [rsp+D0h] [rbp-30h] BYREF

  v8 = a1;
  memset_0(v60, 0, sizeof(v60));
  v42 = 0;
  v10 = 0;
  v11 = 1 << a2;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  for ( i = 0; (int)v10 < v8; ++*((_DWORD *)&v38 + v12) )
  {
    v12 = *(unsigned __int8 *)(v10 + a3);
    v10 = (unsigned int)(v10 + 1);
  }
  for ( j = a2; j <= 16; ++j )
  {
    if ( *((int *)&v38 + j) > 0 )
    {
      if ( v11 > 0 )
      {
        v14 = v11;
        v15 = a4;
        while ( v14 )
        {
          *v15++ = 0;
          --v14;
        }
      }
      break;
    }
  }
  v16 = 0;
  v44 = 0;
  v45 = 2 * DWORD1(v38);
  v46 = 2 * (DWORD2(v38) + 2 * DWORD1(v38));
  v47 = 2 * (HIDWORD(v38) + v46);
  v48 = 2 * (v39 + v47);
  v49 = 2 * (DWORD1(v39) + v48);
  v50 = 2 * (DWORD2(v39) + v49);
  v51 = 2 * (HIDWORD(v39) + v50);
  v52 = 2 * (v40 + v51);
  v53 = 2 * (DWORD1(v40) + v52);
  v54 = 2 * (DWORD2(v40) + v53);
  v55 = 2 * (HIDWORD(v40) + v54);
  v56 = 2 * (i + v55);
  v57 = 2 * (DWORD1(i) + v56);
  v58 = 2 * (DWORD2(i) + v57);
  for ( k = 2 * (HIDWORD(i) + v58); (int)v16 < v8; v16 = (unsigned int)(v16 + 1) )
  {
    v17 = *(unsigned __int8 *)(v16 + a3);
    if ( *(_BYTE *)(v16 + a3) )
    {
      v18 = 0;
      v19 = v43[v17];
      v20 = &v43[v17];
      v21 = v19;
      do
      {
        LODWORD(v17) = v17 - 1;
        v22 = v21 & 1;
        v21 >>= 1;
        v18 = 2 * (v22 | v18);
      }
      while ( (int)v17 > 0 );
      v60[v16] = v18 >> 1;
      *v20 = v19 + 1;
    }
  }
  v23 = v8;
  for ( m = 0; m < v8; ++m )
  {
    v25 = *(unsigned __int8 *)(m + a3);
    if ( *(_BYTE *)(m + a3) )
    {
      v26 = (unsigned int)v60[m];
      if ( v25 > a2 )
      {
        v30 = v25 - a2;
        v31 = 1 << a2;
        v32 = &a4[(unsigned int)v26 & (v11 - 1)];
        if ( *v32 > 0 )
          return 0;
        do
        {
          v33 = *v32;
          if ( !*v32 )
          {
            v34 = 2LL * v23;
            *(_WORD *)(v34 + a5) = 0;
            *(_WORD *)(v34 + a6) = 0;
            v33 = -(__int16)v23;
            *v32 = -(__int16)v23++;
          }
          v35 = a5;
          if ( (v31 & (unsigned int)v26) != 0 )
            v35 = a6;
          v31 *= 2;
          v32 = (__int16 *)(v35 + 2LL * -v33);
          --v30;
        }
        while ( v30 );
        v8 = a1;
        *v32 = m;
      }
      else
      {
        v27 = 1 << v25;
        if ( (unsigned int)v26 >= 1 << v25 )
          return 0;
        v28 = 1 << (a2 - v25);
        for ( n = 0; n < v28; v26 = (unsigned int)(v27 + v26) )
        {
          a4[v26] = m;
          ++n;
        }
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180004c30  push    rbp
0x180004c32  push    rbx
0x180004c33  push    rsi
0x180004c34  push    rdi
0x180004c35  push    r12
0x180004c37  push    r13
0x180004c39  push    r14
0x180004c3b  push    r15
0x180004c3d  lea     rbp, [rsp-468h]
0x180004c45  sub     rsp, 568h
0x180004c4c  mov     rax, cs:__security_cookie
0x180004c53  xor     rax, rsp
0x180004c56  mov     [rbp+4A0h+var_50], rax
0x180004c5d  mov     rax, [rbp+4A0h+arg_28]
0x180004c64  mov     rsi, r8
0x180004c67  mov     r13, [rbp+4A0h+arg_20]
0x180004c6e  mov     r14d, edx
0x180004c71  mov     ebx, ecx
0x180004c73  mov     [rsp+5A0h+var_580], ecx
0x180004c77  xor     edx, edx; Val
0x180004c79  mov     [rsp+5A0h+var_578], rax
0x180004c7e  mov     r8d, 480h; Size
0x180004c84  lea     rcx, [rbp+4A0h+var_4D0]; void *
0x180004c88  mov     r12, r9
0x180004c8b  call    memset_0
0x180004c90  xorps   xmm0, xmm0
0x180004c93  xor     eax, eax
0x180004c95  mov     ecx, r14d
0x180004c98  mov     [rsp+5A0h+var_530], eax
0x180004c9c  mov     r15d, 1
0x180004ca2  xor     edx, edx
0x180004ca4  shl     r15d, cl
0x180004ca7  movups  [rsp+5A0h+var_570], xmm0
0x180004cac  movups  [rsp+5A0h+var_560], xmm0
0x180004cb1  movups  [rsp+5A0h+var_550], xmm0
0x180004cb6  movups  [rsp+5A0h+var_540], xmm0
0x180004cbb  test    ebx, ebx
0x180004cbd  jle     short loc_180004CCE
0x180004cbf  nop
0x180004cc0  movzx   ecx, byte ptr [rdx+rsi]
0x180004cc4  inc     edx
0x180004cc6  inc     dword ptr [rsp+rcx*4+5A0h+var_570]
0x180004cca  cmp     edx, ebx
0x180004ccc  jl      short loc_180004CC0
0x180004cce  mov     ecx, r14d
0x180004cd1  cmp     ecx, 10h
0x180004cd4  jg      short loc_180004CF8
0x180004cd6  movsxd  rax, ecx
0x180004cd9  cmp     dword ptr [rsp+rax*4+5A0h+var_570], 0
0x180004cde  jg      short loc_180004CE4
0x180004ce0  inc     ecx
0x180004ce2  jmp     short loc_180004CD1
0x180004ce4  test    r15d, r15d
0x180004ce7  jle     short loc_180004CF8
0x180004ce9  xor     eax, eax
0x180004ceb  movsxd  rcx, r15d
0x180004cee  movsx   rax, ax
0x180004cf2  mov     rdi, r12
0x180004cf5  rep stosw
0x180004cf8  mov     eax, dword ptr [rsp+5A0h+var_570+4]
0x180004cfc  xor     r8d, r8d
0x180004cff  mov     [rbp+4A0h+var_51C], 0
0x180004d06  lea     ecx, [rax+rax]
0x180004d09  mov     [rbp+4A0h+var_518], ecx
0x180004d0c  add     ecx, dword ptr [rsp+5A0h+var_570+8]
0x180004d10  add     ecx, ecx
0x180004d12  mov     [rbp+4A0h+var_514], ecx
0x180004d15  add     ecx, dword ptr [rsp+5A0h+var_570+0Ch]
0x180004d19  add     ecx, ecx
0x180004d1b  mov     [rbp+4A0h+var_510], ecx
0x180004d1e  add     ecx, dword ptr [rsp+5A0h+var_560]
0x180004d22  add     ecx, ecx
0x180004d24  mov     [rbp+4A0h+var_50C], ecx
0x180004d27  add     ecx, dword ptr [rsp+5A0h+var_560+4]
0x180004d2b  add     ecx, ecx
0x180004d2d  mov     [rbp+4A0h+var_508], ecx
0x180004d30  add     ecx, dword ptr [rsp+5A0h+var_560+8]
0x180004d34  add     ecx, ecx
0x180004d36  mov     [rbp+4A0h+var_504], ecx
0x180004d39  add     ecx, dword ptr [rsp+5A0h+var_560+0Ch]
0x180004d3d  add     ecx, ecx
0x180004d3f  mov     [rbp+4A0h+var_500], ecx
0x180004d42  add     ecx, dword ptr [rsp+5A0h+var_550]
0x180004d46  add     ecx, ecx
0x180004d48  mov     [rbp+4A0h+var_4FC], ecx
0x180004d4b  add     ecx, dword ptr [rsp+5A0h+var_550+4]
0x180004d4f  add     ecx, ecx
0x180004d51  mov     [rbp+4A0h+var_4F8], ecx
0x180004d54  add     ecx, dword ptr [rsp+5A0h+var_550+8]
0x180004d58  add     ecx, ecx
0x180004d5a  mov     [rbp+4A0h+var_4F4], ecx
0x180004d5d  add     ecx, dword ptr [rsp+5A0h+var_550+0Ch]
0x180004d61  add     ecx, ecx
0x180004d63  mov     [rbp+4A0h+var_4F0], ecx
0x180004d66  add     ecx, dword ptr [rsp+5A0h+var_540]
0x180004d6a  add     ecx, ecx
0x180004d6c  mov     [rbp+4A0h+var_4EC], ecx
0x180004d6f  add     ecx, dword ptr [rsp+5A0h+var_540+4]
0x180004d73  add     ecx, ecx
0x180004d75  mov     [rbp+4A0h+var_4E8], ecx
0x180004d78  add     ecx, dword ptr [rsp+5A0h+var_540+8]
0x180004d7c  add     ecx, ecx
0x180004d7e  mov     [rbp+4A0h+var_4E4], ecx
0x180004d81  add     ecx, dword ptr [rsp+5A0h+var_540+0Ch]
0x180004d85  add     ecx, ecx
0x180004d87  mov     [rbp+4A0h+var_4E0], ecx
0x180004d8a  test    ebx, ebx
0x180004d8c  jle     short loc_180004DD7
0x180004d8e  xchg    ax, ax
0x180004d90  movzx   edx, byte ptr [r8+rsi]
0x180004d95  test    edx, edx
0x180004d97  jz      short loc_180004DCF
0x180004d99  lea     r10, [rbp+4A0h+var_520]
0x180004d9d  xor     eax, eax
0x180004d9f  mov     r11d, [r10+rdx*4]
0x180004da3  lea     r10, [r10+rdx*4]
0x180004da7  mov     edi, r11d
0x180004daa  nop     word ptr [rax+rax+00h]
0x180004db0  mov     ecx, edi
0x180004db2  dec     edx
0x180004db4  and     ecx, 1
0x180004db7  shr     edi, 1
0x180004db9  or      eax, ecx
0x180004dbb  add     eax, eax
0x180004dbd  test    edx, edx
0x180004dbf  jg      short loc_180004DB0
0x180004dc1  shr     eax, 1
0x180004dc3  mov     [rbp+r8*4+4A0h+var_4D0], eax
0x180004dc8  lea     eax, [r11+1]
0x180004dcc  mov     [r10], eax
0x180004dcf  inc     r8d
0x180004dd2  cmp     r8d, ebx
0x180004dd5  jl      short loc_180004D90
0x180004dd7  mov     r11d, ebx
0x180004dda  xor     edi, edi
0x180004ddc  nop     dword ptr [rax+00h]
0x180004de0  cmp     edi, ebx
0x180004de2  jge     loc_180004EAC
0x180004de8  movsxd  rax, edi
0x180004deb  movzx   edx, byte ptr [rax+rsi]
0x180004def  test    edx, edx
0x180004df1  jz      loc_180004EA1
0x180004df7  mov     r9d, [rbp+rax*4+4A0h+var_4D0]
0x180004dfc  cmp     edx, r14d
0x180004dff  jg      short loc_180004E37
0x180004e01  mov     ecx, edx
0x180004e03  mov     r8d, 1
0x180004e09  shl     r8d, cl
0x180004e0c  cmp     r9d, r8d
0x180004e0f  jnb     loc_180004EA8
0x180004e15  mov     ecx, r14d
0x180004e18  sub     ecx, edx
0x180004e1a  mov     edx, 1
0x180004e1f  shl     edx, cl
0x180004e21  xor     ecx, ecx
0x180004e23  test    edx, edx
0x180004e25  jle     short loc_180004EA1
0x180004e27  mov     [r12+r9*2], di
0x180004e2c  inc     ecx
0x180004e2e  add     r9d, r8d
0x180004e31  cmp     ecx, edx
0x180004e33  jl      short loc_180004E27
0x180004e35  jmp     short loc_180004EA1
0x180004e37  lea     ecx, [r15-1]
0x180004e3b  sub     edx, r14d
0x180004e3e  and     rcx, r9
0x180004e41  mov     r10d, r15d
0x180004e44  cmp     word ptr [r12+rcx*2], 0
0x180004e4a  lea     r8, [r12+rcx*2]
0x180004e4e  jg      short loc_180004EA8
0x180004e50  mov     rbx, [rsp+5A0h+var_578]
0x180004e55  movzx   eax, word ptr [r8]
0x180004e59  test    ax, ax
0x180004e5c  jnz     short loc_180004E7E
0x180004e5e  movsxd  rax, r11d
0x180004e61  lea     rcx, [rax+rax]
0x180004e65  xor     eax, eax
0x180004e67  mov     [rcx+r13], ax
0x180004e6c  mov     [rcx+rbx], ax
0x180004e70  movzx   eax, r11w
0x180004e74  neg     ax
0x180004e77  mov     [r8], ax
0x180004e7b  inc     r11d
0x180004e7e  test    r9d, r10d
0x180004e81  cwde
0x180004e82  mov     rcx, r13
0x180004e85  cmovnz  rcx, rbx
0x180004e89  neg     eax
0x180004e8b  cdqe
0x180004e8d  add     r10d, r10d
0x180004e90  lea     r8, [rcx+rax*2]
0x180004e94  sub     edx, 1
0x180004e97  jnz     short loc_180004E55
0x180004e99  mov     ebx, [rsp+5A0h+var_580]
0x180004e9d  mov     [r8], di
0x180004ea1  inc     edi
0x180004ea3  jmp     loc_180004DE0
0x180004ea8  xor     eax, eax
0x180004eaa  jmp     short loc_180004EB1
0x180004eac  mov     eax, 1
0x180004eb1  mov     rcx, [rbp+4A0h+var_50]
0x180004eb8  xor     rcx, rsp; StackCookie
0x180004ebb  call    __security_check_cookie
0x180004ec0  add     rsp, 568h
0x180004ec7  pop     r15
0x180004ec9  pop     r14
0x180004ecb  pop     r13
0x180004ecd  pop     r12
0x180004ecf  pop     rdi
0x180004ed0  pop     rsi
0x180004ed1  pop     rbx
0x180004ed2  pop     rbp
0x180004ed3  retn
```
