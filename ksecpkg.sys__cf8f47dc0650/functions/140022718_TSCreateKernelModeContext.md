# TSCreateKernelModeContext

- ea: `0x140022718`
- end: `0x1400229f0`
- name: `TSCreateKernelModeContext`
- size: `728`
- prototype: `__int64 __fastcall(int, int, int, int, size_t Size)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140022b00`

## callees

- `0x1400102c0`
- `0x1400105c0`
- `0x140022718`
- `0x140022bcc`
- `0x140022d98`
- `0x140022f20`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002278e`
- `ntoskrnl!ExAllocatePool2` at `0x140022906`
- `ntoskrnl!ExAllocatePool2` at `0x14002278e`
- `ntoskrnl!ExAllocatePool2` at `0x140022906`

## pseudocode

```c
__int64 __fastcall TSCreateKernelModeContext(__int64 a1, __int64 a2, _QWORD *a3)
{
  int *v5; // rsi
  __int64 v6; // rcx
  _QWORD *Pool2; // rax
  _QWORD *v8; // rdi
  int v9; // ecx
  __int64 v10; // r9
  char *v11; // r9
  char *v12; // rax
  char *v13; // rax
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rax
  __int64 v17; // rcx
  unsigned int v18; // r13d
  _WORD *v19; // r15
  _WORD *v20; // r12
  __int64 v21; // rax
  unsigned int v22; // r14d
  __int64 v23; // rax
  void *v24; // rax
  _DWORD *v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rsi
  size_t v28; // [rsp+28h] [rbp-E0h]
  int v29[72]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v32; // [rsp+180h] [rbp+78h]
  unsigned int Sizea; // [rsp+188h] [rbp+80h]

  memset(v29, 0, 0xE8u);
  if ( *(_DWORD *)a2 < 0x54u )
    return 3221225485LL;
  v5 = *(int **)(a2 + 8);
  v6 = 256;
  if ( TSGlobalPoolType != PagedPool )
    v6 = 64;
  v32 = v6;
  Pool2 = (_QWORD *)ExAllocatePool2(v6, 280, 1802531668);
  v8 = Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, 0x118u);
    *(_DWORD *)v8 = 1;
    v9 = v5[11];
    v10 = (unsigned int)v5[10];
    v8[5] = *v5;
    v11 = (char *)v5 + v10;
    v8[6] = v5[1];
    v8[7] = v5[2];
    *((_DWORD *)v8 + 30) = v5[3];
    *(_QWORD *)((char *)v8 + 132) = *(_QWORD *)(v5 + 19);
    v29[6] = v5[6];
    v12 = (char *)v5 + (unsigned int)v5[7];
    v29[18] = v9;
    *(_QWORD *)&v29[8] = v12;
    v29[2] = v5[4];
    v13 = (char *)v5 + (unsigned int)v5[5];
    *(_QWORD *)&v29[16] = v11;
    *(_QWORD *)&v29[4] = v13;
    v29[10] = v5[8];
    *(_QWORD *)&v29[12] = (char *)v5 + (unsigned int)v5[9];
    if ( v9 )
    {
      LODWORD(v28) = v9;
      v14 = TSKCreateKerbCertLogonBuffer((int)&v29[10], (int)&v29[2], (int)&v29[6], (int)v11, v28, (__int64)(v8 + 12));
    }
    else
    {
      v14 = TSKCreateKerbLogonBuffer(&v29[6], &v29[2], &v29[10], v8 + 12);
    }
    v15 = v14;
    if ( v14 >= 0 )
    {
      v16 = (unsigned int)v5[17];
      v17 = -1;
      v18 = 0;
      v19 = 0;
      if ( (_DWORD)v16 )
      {
        v20 = (_WORD *)((char *)v5 + v16);
        v21 = -1;
        do
          ++v21;
        while ( v20[v21] );
        Sizea = 2 * v21 + 2;
        v22 = 2 * v21 + 34;
      }
      else
      {
        v22 = 32;
        Sizea = 0;
        v20 = 0;
      }
      v23 = (unsigned int)v5[18];
      if ( (_DWORD)v23 )
      {
        v19 = (_WORD *)((char *)v5 + v23);
        do
          ++v17;
        while ( v19[v17] );
        v22 += 2 * v17 + 2;
        v18 = 2 * v17 + 2;
      }
      v24 = (void *)ExAllocatePool2(v32, v22, 1802531668);
      v8[13] = v24;
      *((_DWORD *)v8 + 28) = v22;
      memset(v24, 0, v22);
      v25 = (_DWORD *)v8[13];
      if ( v25 )
      {
        *v25 = v5[14];
        *(_WORD *)(v8[13] + 4LL) = *((_WORD *)v5 + 30);
        *(_WORD *)(v8[13] + 6LL) = *((_WORD *)v5 + 31);
        *(_DWORD *)(v8[13] + 8LL) = v5[16];
        v26 = v8[13];
        v27 = v26 + 32;
        if ( v20 )
        {
          *(_QWORD *)(v26 + 16) = v27;
          memmove(*(void **)(v8[13] + 16LL), v20, Sizea);
          v27 += Sizea;
        }
        if ( v19 )
        {
          *(_QWORD *)(v8[13] + 24LL) = v27;
          memmove(*(void **)(v8[13] + 24LL), v19, v18);
        }
        v15 = 0;
        v8[1] = a1;
        *a3 = v8;
        return v15;
      }
      v15 = -1073741670;
    }
    TSKFreeContext(v8);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v15;
}

```

## disassembly

```asm
0x140022718  mov     rax, rsp
0x14002271b  mov     [rax+10h], rbx
0x14002271f  mov     [rax+20h], r9
0x140022723  mov     [rax+18h], r8
0x140022727  mov     [rax+8], rcx
0x14002272b  push    rbp
0x14002272c  push    rsi
0x14002272d  push    rdi
0x14002272e  push    r12
0x140022730  push    r13
0x140022732  push    r14
0x140022734  push    r15
0x140022736  lea     rbp, [rax-58h]
0x14002273a  sub     rsp, 120h
0x140022741  mov     rsi, rdx
0x140022744  lea     rcx, [rsp+150h+var_120]; void *
0x140022749  xor     edx, edx; Val
0x14002274b  mov     r8d, 0E8h; Size
0x140022751  call    memset
0x140022756  cmp     dword ptr [rsi], 54h ; 'T'
0x140022759  jnb     short loc_140022765
0x14002275b  mov     eax, 0C000000Dh
0x140022760  jmp     loc_1400229D4
0x140022765  cmp     cs:?TSGlobalPoolType@@3W4_POOL_TYPE@@A, 1; _POOL_TYPE TSGlobalPoolType
0x14002276c  mov     edx, 40h ; '@'
0x140022771  mov     rsi, [rsi+8]
0x140022775  mov     ecx, 100h
0x14002277a  cmovnz  ecx, edx
0x14002277d  mov     ebx, 118h
0x140022782  mov     edx, ebx
0x140022784  mov     [rbp+50h+arg_18], rcx
0x140022788  mov     r8d, 6B707354h
0x14002278e  call    cs:__imp_ExAllocatePool2
0x140022795  nop     dword ptr [rax+rax+00h]
0x14002279a  mov     rdi, rax
0x14002279d  test    rax, rax
0x1400227a0  jz      loc_1400229CD
0x1400227a6  mov     r8d, ebx; Size
0x1400227a9  xor     edx, edx; Val
0x1400227ab  mov     rcx, rax; void *
0x1400227ae  call    memset
0x1400227b3  mov     dword ptr [rdi], 1
0x1400227b9  movsxd  rax, dword ptr [rsi]
0x1400227bc  lea     rdx, [rsp+150h+var_118]; int
0x1400227c1  mov     ecx, [rsi+2Ch]
0x1400227c4  mov     r9d, [rsi+28h]
0x1400227c8  mov     [rdi+28h], rax
0x1400227cc  add     r9, rsi; int
0x1400227cf  movsxd  rax, dword ptr [rsi+4]
0x1400227d3  mov     [rdi+30h], rax
0x1400227d7  movsxd  rax, dword ptr [rsi+8]
0x1400227db  mov     [rdi+38h], rax
0x1400227df  mov     eax, [rsi+0Ch]
0x1400227e2  mov     [rdi+78h], eax
0x1400227e5  mov     rax, [rsi+4Ch]
0x1400227e9  mov     [rdi+84h], rax
0x1400227f0  movzx   eax, word ptr [rsi+18h]
0x1400227f4  mov     word ptr [rsp+150h+var_108], ax
0x1400227f9  movzx   eax, word ptr [rsi+1Ah]
0x1400227fd  mov     word ptr [rsp+150h+var_108+2], ax
0x140022802  mov     eax, [rsi+1Ch]
0x140022805  add     rax, rsi
0x140022808  mov     [rsp+78h], ecx
0x14002280c  mov     qword ptr [rsp+150h+var_100], rax
0x140022811  movzx   eax, word ptr [rsi+10h]
0x140022815  mov     word ptr [rsp+150h+var_118], ax
0x14002281a  movzx   eax, word ptr [rsi+12h]
0x14002281e  mov     word ptr [rsp+150h+var_118+2], ax
0x140022823  mov     eax, [rsi+14h]
0x140022826  add     rax, rsi
0x140022829  mov     qword ptr [rsp+150h+var_E0], r9
0x14002282e  mov     qword ptr [rsp+150h+var_110], rax
0x140022833  movzx   eax, word ptr [rsi+20h]
0x140022837  mov     word ptr [rsp+150h+var_F8], ax
0x14002283c  movzx   eax, word ptr [rsi+22h]
0x140022840  mov     word ptr [rsp+150h+var_F8+2], ax
0x140022845  mov     eax, [rsi+24h]
0x140022848  add     rax, rsi
0x14002284b  mov     [rsp+60h], rax
0x140022850  lea     rax, [rdi+60h]
0x140022854  test    ecx, ecx
0x140022856  jnz     short loc_14002286C
0x140022858  mov     r9, rax
0x14002285b  lea     r8, [rsp+150h+var_F8]
0x140022860  lea     rcx, [rsp+150h+var_108]
0x140022865  call    TSKCreateKerbLogonBuffer
0x14002286a  jmp     short loc_140022884
0x14002286c  mov     [rsp+150h+var_128], rax; __int64
0x140022871  lea     r8, [rsp+150h+var_108]; int
0x140022876  mov     dword ptr [rsp+150h+var_130], ecx; size_t
0x14002287a  lea     rcx, [rsp+150h+var_F8]; int
0x14002287f  call    TSKCreateKerbCertLogonBuffer
0x140022884  xor     edx, edx
0x140022886  mov     ebx, eax
0x140022888  test    eax, eax
0x14002288a  js      loc_140022938
0x140022890  mov     eax, [rsi+44h]
0x140022893  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140022897  mov     r13d, edx
0x14002289a  mov     r15d, edx
0x14002289d  test    eax, eax
0x14002289f  jz      short loc_1400228C5
0x1400228a1  lea     r12, [rsi+rax]
0x1400228a5  mov     rax, rcx
0x1400228a8  inc     rax
0x1400228ab  cmp     [r12+rax*2], dx
0x1400228b0  jnz     short loc_1400228A8
0x1400228b2  lea     eax, ds:2[rax*2]
0x1400228b9  mov     dword ptr [rbp+50h+Size], eax
0x1400228bf  lea     r14d, [rax+20h]
0x1400228c3  jmp     short loc_1400228D4
0x1400228c5  mov     r14d, 20h ; ' '
0x1400228cb  mov     dword ptr [rbp+50h+Size], edx
0x1400228d1  mov     r12, rdx
0x1400228d4  mov     eax, [rsi+48h]
0x1400228d7  test    eax, eax
0x1400228d9  jz      short loc_1400228F9
0x1400228db  lea     r15, [rsi+rax]
0x1400228df  inc     rcx
0x1400228e2  cmp     [r15+rcx*2], dx
0x1400228e7  jnz     short loc_1400228DF
0x1400228e9  lea     r14d, [r14+rcx*2]
0x1400228ed  add     r14d, 2
0x1400228f1  lea     r13d, ds:2[rcx*2]
0x1400228f9  mov     rcx, [rbp+50h+arg_18]
0x1400228fd  mov     r8d, 6B707354h
0x140022903  mov     edx, r14d
0x140022906  call    cs:__imp_ExAllocatePool2
0x14002290d  nop     dword ptr [rax+rax+00h]
0x140022912  mov     r8d, r14d; Size
0x140022915  xor     edx, edx; Val
0x140022917  mov     rcx, rax; void *
0x14002291a  mov     [rdi+68h], rax
0x14002291e  mov     [rdi+70h], r14d
0x140022922  call    memset
0x140022927  mov     rcx, [rdi+68h]
0x14002292b  xor     r14d, r14d
0x14002292e  test    rcx, rcx
0x140022931  jnz     short loc_140022945
0x140022933  mov     ebx, 0C000009Ah
0x140022938  mov     rcx, rdi; P
0x14002293b  call    TSKFreeContext
0x140022940  jmp     loc_1400229D2
0x140022945  mov     eax, [rsi+38h]
0x140022948  mov     [rcx], eax
0x14002294a  movzx   eax, word ptr [rsi+3Ch]
0x14002294e  mov     rcx, [rdi+68h]
0x140022952  mov     [rcx+4], ax
0x140022956  movzx   eax, word ptr [rsi+3Eh]
0x14002295a  mov     rcx, [rdi+68h]
0x14002295e  mov     [rcx+6], ax
0x140022962  mov     eax, [rsi+40h]
0x140022965  mov     rcx, [rdi+68h]
0x140022969  mov     [rcx+8], eax
0x14002296c  mov     rax, [rdi+68h]
0x140022970  lea     rsi, [rax+20h]
0x140022974  test    r12, r12
0x140022977  jz      short loc_140022999
0x140022979  mov     ebx, dword ptr [rbp+50h+Size]
0x14002297f  mov     rdx, r12; Src
0x140022982  mov     [rax+10h], rsi
0x140022986  mov     r8d, ebx; Size
0x140022989  mov     rcx, [rdi+68h]
0x14002298d  mov     rcx, [rcx+10h]; void *
0x140022991  call    memmove
0x140022996  add     rsi, rbx
0x140022999  test    r15, r15
0x14002299c  jz      short loc_1400229B9
0x14002299e  mov     rax, [rdi+68h]
0x1400229a2  mov     rdx, r15; Src
0x1400229a5  mov     r8d, r13d; Size
0x1400229a8  mov     [rax+18h], rsi
0x1400229ac  mov     rcx, [rdi+68h]
0x1400229b0  mov     rcx, [rcx+18h]; void *
0x1400229b4  call    memmove
0x1400229b9  mov     rax, [rbp+50h+arg_0]
0x1400229bd  mov     ebx, r14d
0x1400229c0  mov     [rdi+8], rax
0x1400229c4  mov     rax, [rbp+50h+arg_10]
0x1400229c8  mov     [rax], rdi
0x1400229cb  jmp     short loc_1400229D2
0x1400229cd  mov     ebx, 0C000009Ah
0x1400229d2  mov     eax, ebx
0x1400229d4  mov     rbx, [rsp+150h+arg_8]
0x1400229dc  add     rsp, 120h
0x1400229e3  pop     r15
0x1400229e5  pop     r14
0x1400229e7  pop     r13
0x1400229e9  pop     r12
0x1400229eb  pop     rdi
0x1400229ec  pop     rsi
0x1400229ed  pop     rbp
0x1400229ee  retn
```
