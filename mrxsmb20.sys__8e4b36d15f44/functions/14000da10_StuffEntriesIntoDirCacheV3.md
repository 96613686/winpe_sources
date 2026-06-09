# StuffEntriesIntoDirCacheV3

- ea: `0x14000da10`
- end: `0x14000dea7`
- name: `StuffEntriesIntoDirCacheV3`
- size: `1175`
- prototype: `void __fastcall(_DWORD *, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000da10`
- `0x140029840`
- `0x1400372c0`
- `0x1400375c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000dccb`
- `ntoskrnl!ExAllocatePool2` at `0x14000dd17`
- `ntoskrnl!ExAllocatePool2` at `0x14000dccb`
- `ntoskrnl!ExAllocatePool2` at `0x14000dd17`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000da71`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000da96`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000db33`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000dd6a`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000ddf0`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000da71`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000da96`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000db33`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000dd6a`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000ddf0`

## pseudocode

```c
void __fastcall StuffEntriesIntoDirCacheV3(_DWORD *a1, __int64 a2)
{
  int v4; // edx
  unsigned int v5; // r8d
  __int64 v6; // rdi
  unsigned int v7; // r14d
  unsigned int v8; // r15d
  CCHAR MostSignificantBit; // al
  __int64 v10; // rsi
  CCHAR v11; // al
  __int64 v12; // r14
  __int64 v13; // r13
  unsigned int v14; // esi
  CCHAR v15; // al
  __int64 v16; // rax
  unsigned int v17; // ecx
  __int64 v18; // rdx
  __int64 v19; // rsi
  __int16 v20; // cx
  __int16 v21; // cx
  __int64 v22; // r13
  __int64 v23; // rax
  __int64 Pool2; // rax
  unsigned int v25; // r14d
  CCHAR v26; // al
  __int64 v27; // rdx
  unsigned int v28; // ecx
  __int64 v29; // rdx
  _WORD *v30; // r14
  unsigned int v31; // eax
  CCHAR v32; // al
  unsigned int v33; // eax
  int v34; // [rsp+60h] [rbp+8h]

  if ( (int)a1[6] < 0 )
    return;
  v4 = *(_DWORD *)(a2 + 60);
  v5 = a1[2];
  v34 = v4 + 122;
  if ( a1[3] + v4 + 122 <= v5 )
  {
    v6 = *(_QWORD *)a1;
    v7 = (unsigned int)(v4 + 87 + *(char *)(a2 + 96)) >> 7;
    v8 = v7 + 1;
    MostSignificantBit = RtlFindMostSignificantBit(*(unsigned int *)(*(_QWORD *)a1 + 220LL));
    if ( MostSignificantBit <= 4 )
      v10 = 0;
    else
      v10 = (unsigned int)(MostSignificantBit - 3) >> 1;
    v11 = RtlFindMostSignificantBit(v7 + *(_DWORD *)(v6 + 220));
    if ( v11 <= 4 )
      v12 = 0;
    else
      v12 = (unsigned int)(v11 - 3) >> 1;
    if ( (unsigned int)v12 >= 8
      || (unsigned int)v10 >= 8
      || v8 + *(_DWORD *)(v6 + 220) >= dbgDirCacheBlockCountLimit
      || v8 > 8 )
    {
      goto LABEL_29;
    }
    v13 = v6 + 8 * v10;
    if ( !*(_QWORD *)(v13 + 152) )
    {
      Pool2 = ExAllocatePool2(258, *((unsigned int *)qword_14003EDA8 + v10), 1834181444);
      *(_QWORD *)(v13 + 152) = Pool2;
      if ( !Pool2 )
        goto LABEL_29;
      *(_DWORD *)(v6 + 216) = 32 << (2 * v10);
    }
    if ( (_DWORD)v10 == (_DWORD)v12 )
    {
LABEL_13:
      v14 = *(_DWORD *)(v6 + 220);
      if ( v14 + v8 > *(_DWORD *)(v6 + 216) )
        goto LABEL_29;
      v15 = RtlFindMostSignificantBit(v14);
      if ( v15 <= 4 )
      {
        v16 = 0;
      }
      else
      {
        v16 = (unsigned int)(v15 - 3) >> 1;
        if ( (unsigned int)v16 >= 8 )
          goto LABEL_60;
      }
      _mm_lfence();
      if ( (_DWORD)v16 )
        v17 = v14 - (32 << (2 * v16 - 2));
      else
        v17 = v14;
      v18 = *(_QWORD *)(v6 + 8 * v16 + 152);
      if ( v18 && v14 < *(_DWORD *)(v6 + 216) )
      {
        v19 = v18 + (v17 << 7);
        goto LABEL_21;
      }
LABEL_60:
      __int2c();
      v19 = 0;
LABEL_21:
      *(_DWORD *)(v6 + 220) += v8;
      if ( v19 )
      {
        *(_QWORD *)v19 = *(_QWORD *)(a2 + 8);
        *(_QWORD *)(v19 + 8) = *(_QWORD *)(a2 + 16);
        *(_QWORD *)(v19 + 16) = *(_QWORD *)(a2 + 24);
        *(_QWORD *)(v19 + 24) = *(_QWORD *)(a2 + 32);
        *(_QWORD *)(v19 + 32) = *(_QWORD *)(a2 + 40);
        *(_QWORD *)(v19 + 40) = *(_QWORD *)(a2 + 48);
        *(_DWORD *)(v19 + 72) = *(_DWORD *)(a2 + 56);
        *(_DWORD *)(v19 + 76) = *(_DWORD *)(a2 + 64);
        *(_DWORD *)(v19 + 80) = *(_DWORD *)(a2 + 68);
        *(_QWORD *)(v19 + 48) = *(_QWORD *)(a2 + 72);
        *(_OWORD *)(v19 + 56) = *(_OWORD *)(a2 + 80);
        v20 = *(_WORD *)(v19 + 86) & 0xFFF0 | (*(_BYTE *)(a2 + 96) >> 1) & 0xF;
        *(_WORD *)(v19 + 86) = v20;
        v21 = v20 & 0xF;
        *(_WORD *)(v19 + 86) = v21 | (8 * (*(_WORD *)(a2 + 60) & 0xFFFE));
        *(_WORD *)(v19 + 84) = 0;
        if ( v21 )
          memmove((void *)(v19 + 88), (const void *)(a2 + 98), *(char *)(a2 + 96));
        memmove(
          (void *)(v19 + 2 * ((*(_WORD *)(v19 + 86) & 0xF) + 44LL)),
          (const void *)(a2 + 122),
          *(unsigned int *)(a2 + 60));
        a1[3] += v34;
        ++a1[4];
        a1[6] = 0;
        if ( *(_BYTE *)(a2 + 96) )
          ++a1[5];
        return;
      }
LABEL_29:
      a1[6] = -1073739516;
      return;
    }
    v22 = v6 + 8 * v12;
    if ( *(_QWORD *)(v22 + 152) )
      goto LABEL_37;
    v23 = ExAllocatePool2(258, *((unsigned int *)qword_14003EDA8 + v12), 1834181444);
    *(_QWORD *)(v22 + 152) = v23;
    if ( !v23 )
      goto LABEL_29;
    *(_DWORD *)(v6 + 216) = 32 << (2 * v12);
    while ( 1 )
    {
LABEL_37:
      v25 = *(_DWORD *)(v6 + 220);
      v26 = RtlFindMostSignificantBit(v25);
      if ( v26 <= 4 )
      {
        v27 = 0;
      }
      else
      {
        v27 = (unsigned int)(v26 - 3) >> 1;
        if ( (unsigned int)v27 >= 8 )
          goto LABEL_59;
      }
      _mm_lfence();
      if ( (_DWORD)v27 )
        v28 = v25 - (32 << (2 * v27 - 2));
      else
        v28 = v25;
      v29 = *(_QWORD *)(v6 + 8 * v27 + 152);
      if ( !v29 || v25 >= *(_DWORD *)(v6 + 216) )
      {
LABEL_59:
        __int2c();
        v30 = 0;
        goto LABEL_44;
      }
      v30 = (_WORD *)(v29 + (v28 << 7));
LABEL_44:
      memset(v30, 0, 0x80u);
      v30[42] |= 8u;
      v31 = *(_DWORD *)(v6 + 220) + 1;
      *(_DWORD *)(v6 + 220) = v31;
      v32 = RtlFindMostSignificantBit(v31);
      if ( v32 <= 4 )
        v33 = 0;
      else
        v33 = (unsigned int)(v32 - 3) >> 1;
      if ( v33 != (_DWORD)v10 )
        goto LABEL_13;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      23,
      WPP_b1ee9e7bd57e3d642558c0c0d0c622f3_Traceguids,
      *(_QWORD *)a1,
      v5);
  }
  a1[6] = -1073741670;
}

```

## disassembly

```asm
0x14000da10  push    rbx
0x14000da12  push    rbp
0x14000da13  sub     rsp, 48h
0x14000da17  cmp     dword ptr [rcx+18h], 0
0x14000da1b  mov     rbp, rdx
0x14000da1e  mov     rbx, rcx
0x14000da21  jl      loc_14000DCA2
0x14000da27  mov     edx, [rdx+3Ch]
0x14000da2a  mov     r8d, [rbx+8]
0x14000da2e  lea     ecx, [rdx+7Ah]
0x14000da31  mov     [rsp+58h+arg_0], ecx
0x14000da35  add     ecx, [rbx+0Ch]
0x14000da38  cmp     ecx, r8d
0x14000da3b  ja      loc_14000DE45
0x14000da41  mov     [rsp+58h+arg_8], rsi
0x14000da46  add     edx, 57h ; 'W'
0x14000da49  mov     [rsp+58h+arg_10], rdi
0x14000da4e  mov     rdi, [rbx]
0x14000da51  mov     [rsp+58h+var_20], r14
0x14000da56  movsx   r14d, byte ptr [rbp+60h]
0x14000da5b  add     r14d, edx
0x14000da5e  mov     [rsp+58h+var_28], r15
0x14000da63  mov     ecx, [rdi+0DCh]; Set
0x14000da69  shr     r14d, 7
0x14000da6d  lea     r15d, [r14+1]
0x14000da71  call    cs:__imp_RtlFindMostSignificantBit
0x14000da78  nop     dword ptr [rax+rax+00h]
0x14000da7d  cmp     al, 4
0x14000da7f  jle     loc_14000DCEC
0x14000da85  movsx   esi, al
0x14000da88  sub     esi, 3
0x14000da8b  shr     esi, 1
0x14000da8d  mov     ecx, [rdi+0DCh]
0x14000da93  add     ecx, r14d; Set
0x14000da96  call    cs:__imp_RtlFindMostSignificantBit
0x14000da9d  nop     dword ptr [rax+rax+00h]
0x14000daa2  cmp     al, 4
0x14000daa4  jle     loc_14000DCF3
0x14000daaa  movsx   r14d, al
0x14000daae  sub     r14d, 3
0x14000dab2  shr     r14d, 1
0x14000dab5  mov     ecx, [rdi+0DCh]
0x14000dabb  mov     eax, cs:dbgDirCacheBlockCountLimit
0x14000dac1  add     ecx, r15d
0x14000dac4  mov     [rsp+58h+arg_18], r12
0x14000dac9  mov     [rsp+58h+var_18], r13
0x14000dace  cmp     r14d, 8
0x14000dad2  jnb     loc_14000DCE3
0x14000dad8  cmp     esi, 8
0x14000dadb  jnb     loc_14000DCE3
0x14000dae1  cmp     ecx, eax
0x14000dae3  jnb     loc_14000DCE3
0x14000dae9  cmp     r15d, 8
0x14000daed  ja      loc_14000DCE3
0x14000daf3  lea     r13, [rdi+rsi*8]
0x14000daf7  mov     r12d, 20h ; ' '
0x14000dafd  cmp     qword ptr [r13+98h], 0
0x14000db05  lea     rcx, qword_14003EDA8
0x14000db0c  jz      loc_14000DD09
0x14000db12  cmp     esi, r14d
0x14000db15  jnz     loc_14000DCAA
0x14000db1b  mov     esi, [rdi+0DCh]
0x14000db21  lea     eax, [rsi+r15]
0x14000db25  cmp     eax, [rdi+0D8h]
0x14000db2b  ja      loc_14000DCE3
0x14000db31  mov     ecx, esi; Set
0x14000db33  call    cs:__imp_RtlFindMostSignificantBit
0x14000db3a  nop     dword ptr [rax+rax+00h]
0x14000db3f  cmp     al, 4
0x14000db41  jle     loc_14000DCFB
0x14000db47  movsx   eax, al
0x14000db4a  sub     eax, 3
0x14000db4d  shr     eax, 1
0x14000db4f  cmp     eax, 8
0x14000db52  jnb     loc_14000DE9E
0x14000db58  lfence
0x14000db5b  test    eax, eax
0x14000db5d  jz      loc_14000DD02
0x14000db63  lea     ecx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x14000db6a  shl     r12d, cl
0x14000db6d  mov     ecx, esi
0x14000db6f  sub     ecx, r12d
0x14000db72  mov     rdx, [rdi+rax*8+98h]
0x14000db7a  test    rdx, rdx
0x14000db7d  jz      loc_14000DE25
0x14000db83  cmp     esi, [rdi+0D8h]
0x14000db89  jnb     loc_14000DE2E
0x14000db8f  shl     ecx, 7
0x14000db92  mov     esi, ecx
0x14000db94  add     rsi, rdx
0x14000db97  add     [rdi+0DCh], r15d
0x14000db9e  test    rsi, rsi
0x14000dba1  jz      loc_14000DCE3
0x14000dba7  mov     rax, [rbp+8]
0x14000dbab  mov     edx, 0FFF0h
0x14000dbb0  mov     [rsi], rax
0x14000dbb3  mov     rax, [rbp+10h]
0x14000dbb7  mov     [rsi+8], rax
0x14000dbbb  mov     rax, [rbp+18h]
0x14000dbbf  mov     [rsi+10h], rax
0x14000dbc3  mov     rax, [rbp+20h]
0x14000dbc7  mov     [rsi+18h], rax
0x14000dbcb  mov     rax, [rbp+28h]
0x14000dbcf  mov     [rsi+20h], rax
0x14000dbd3  mov     rax, [rbp+30h]
0x14000dbd7  mov     [rsi+28h], rax
0x14000dbdb  mov     eax, [rbp+38h]
0x14000dbde  mov     [rsi+48h], eax
0x14000dbe1  mov     eax, [rbp+40h]
0x14000dbe4  mov     [rsi+4Ch], eax
0x14000dbe7  mov     eax, [rbp+44h]
0x14000dbea  mov     [rsi+50h], eax
0x14000dbed  mov     rax, [rbp+48h]
0x14000dbf1  mov     [rsi+30h], rax
0x14000dbf5  movups  xmm0, xmmword ptr [rbp+50h]
0x14000dbf9  movups  xmmword ptr [rsi+38h], xmm0
0x14000dbfd  movzx   eax, byte ptr [rbp+60h]
0x14000dc01  shr     al, 1
0x14000dc03  and     al, 0Fh
0x14000dc05  movzx   ecx, al
0x14000dc08  movzx   eax, word ptr [rsi+56h]
0x14000dc0c  and     ax, dx
0x14000dc0f  mov     edx, 0FFFEh
0x14000dc14  or      cx, ax
0x14000dc17  mov     [rsi+56h], cx
0x14000dc1b  and     cx, 0Fh
0x14000dc1f  movzx   eax, word ptr [rbp+3Ch]
0x14000dc23  and     ax, dx
0x14000dc26  shl     ax, 3
0x14000dc2a  or      ax, cx
0x14000dc2d  mov     [rsi+56h], ax
0x14000dc31  xor     eax, eax
0x14000dc33  mov     [rsi+54h], ax
0x14000dc37  test    cx, cx
0x14000dc3a  jz      short loc_14000DC4E
0x14000dc3c  movsx   r8, byte ptr [rbp+60h]; Size
0x14000dc41  lea     rdx, [rbp+62h]; Src
0x14000dc45  lea     rcx, [rsi+58h]; void *
0x14000dc49  call    memmove
0x14000dc4e  movzx   eax, word ptr [rsi+56h]
0x14000dc52  lea     rdx, [rbp+7Ah]; Src
0x14000dc56  mov     r8d, [rbp+3Ch]; Size
0x14000dc5a  and     eax, 0Fh
0x14000dc5d  lea     rax, [rax+2Ch]
0x14000dc61  lea     rcx, [rsi+rax*2]; void *
0x14000dc65  call    memmove
0x14000dc6a  mov     eax, [rsp+58h+arg_0]
0x14000dc6e  add     [rbx+0Ch], eax
0x14000dc71  inc     dword ptr [rbx+10h]
0x14000dc74  mov     dword ptr [rbx+18h], 0
0x14000dc7b  cmp     byte ptr [rbp+60h], 0
0x14000dc7f  jz      short loc_14000DC84
0x14000dc81  inc     dword ptr [rbx+14h]
0x14000dc84  mov     r13, [rsp+58h+var_18]
0x14000dc89  mov     r12, [rsp+58h+arg_18]
0x14000dc8e  mov     r14, [rsp+58h+var_20]
0x14000dc93  mov     rdi, [rsp+58h+arg_10]
0x14000dc98  mov     rsi, [rsp+58h+arg_8]
0x14000dc9d  mov     r15, [rsp+58h+var_28]
0x14000dca2  add     rsp, 48h
0x14000dca6  pop     rbp
0x14000dca7  pop     rbx
0x14000dca8  retn
0x14000dcaa  lea     r13, [rdi+r14*8]
0x14000dcae  cmp     qword ptr [r13+98h], 0
0x14000dcb6  jnz     loc_14000DD60
0x14000dcbc  mov     edx, [rcx+r14*4]
0x14000dcc0  mov     r8d, 6D536344h
0x14000dcc6  mov     ecx, 102h
0x14000dccb  call    cs:__imp_ExAllocatePool2
0x14000dcd2  nop     dword ptr [rax+rax+00h]
0x14000dcd7  mov     [r13+98h], rax
0x14000dcde  test    rax, rax
0x14000dce1  jnz     short loc_14000DD49
0x14000dce3  mov     dword ptr [rbx+18h], 0C0000904h
0x14000dcea  jmp     short loc_14000DC84
0x14000dcec  xor     esi, esi
0x14000dcee  jmp     loc_14000DA8D
0x14000dcf3  xor     r14d, r14d
0x14000dcf6  jmp     loc_14000DAB5
0x14000dcfb  xor     eax, eax
0x14000dcfd  jmp     loc_14000DB58
0x14000dd02  mov     ecx, esi
0x14000dd04  jmp     loc_14000DB72
0x14000dd09  mov     edx, [rcx+rsi*4]
0x14000dd0c  mov     r8d, 6D536344h
0x14000dd12  mov     ecx, 102h
0x14000dd17  call    cs:__imp_ExAllocatePool2
0x14000dd1e  nop     dword ptr [rax+rax+00h]
0x14000dd23  mov     [r13+98h], rax
0x14000dd2a  test    rax, rax
0x14000dd2d  jz      short loc_14000DCE3
0x14000dd2f  lea     ecx, [rsi+rsi]
0x14000dd32  mov     eax, r12d
0x14000dd35  shl     eax, cl
0x14000dd37  lea     rcx, qword_14003EDA8
0x14000dd3e  mov     [rdi+0D8h], eax
0x14000dd44  jmp     loc_14000DB12
0x14000dd49  lea     ecx, [r14+r14]
0x14000dd4d  mov     eax, r12d
0x14000dd50  shl     eax, cl
0x14000dd52  mov     [rdi+0D8h], eax
0x14000dd58  nop     dword ptr [rax+rax+00000000h]
0x14000dd60  mov     r14d, [rdi+0DCh]
0x14000dd67  mov     ecx, r14d; Set
0x14000dd6a  call    cs:__imp_RtlFindMostSignificantBit
0x14000dd71  nop     dword ptr [rax+rax+00h]
0x14000dd76  cmp     al, 4
0x14000dd78  jle     loc_14000DE15
0x14000dd7e  movsx   edx, al
0x14000dd81  sub     edx, 3
0x14000dd84  shr     edx, 1
0x14000dd86  cmp     edx, 8
0x14000dd89  jnb     loc_14000DE94
0x14000dd8f  lfence
0x14000dd92  test    edx, edx
0x14000dd94  jz      loc_14000DE20
0x14000dd9a  lea     ecx, ds:0FFFFFFFFFFFFFFFEh[rdx*2]
0x14000dda1  mov     eax, r12d
0x14000dda4  shl     eax, cl
0x14000dda6  mov     ecx, r14d
0x14000dda9  sub     ecx, eax
0x14000ddab  mov     rdx, [rdi+rdx*8+98h]
0x14000ddb3  test    rdx, rdx
0x14000ddb6  jz      short loc_14000DE37
0x14000ddb8  cmp     r14d, [rdi+0D8h]
0x14000ddbf  jnb     short loc_14000DE3E
0x14000ddc1  shl     ecx, 7
0x14000ddc4  mov     r14d, ecx
0x14000ddc7  add     r14, rdx
0x14000ddca  xor     edx, edx; Val
0x14000ddcc  mov     r8d, 80h; Size
0x14000ddd2  mov     rcx, r14; void *
0x14000ddd5  call    memset
0x14000ddda  or      word ptr [r14+54h], 8
0x14000dde0  mov     eax, [rdi+0DCh]
0x14000dde6  inc     eax
0x14000dde8  mov     ecx, eax; Set
0x14000ddea  mov     [rdi+0DCh], eax
0x14000ddf0  call    cs:__imp_RtlFindMostSignificantBit
0x14000ddf7  nop     dword ptr [rax+rax+00h]
0x14000ddfc  cmp     al, 4
0x14000ddfe  jle     short loc_14000DE1C
0x14000de00  movsx   eax, al
0x14000de03  sub     eax, 3
0x14000de06  shr     eax, 1
0x14000de08  cmp     eax, esi
0x14000de0a  jz      loc_14000DD60
0x14000de10  jmp     loc_14000DB1B
0x14000de15  xor     edx, edx
0x14000de17  jmp     loc_14000DD8F
0x14000de1c  xor     eax, eax
0x14000de1e  jmp     short loc_14000DE08
0x14000de20  mov     ecx, r14d
0x14000de23  jmp     short loc_14000DDAB
0x14000de25  int     2Ch; Windows NT - assertion failure
0x14000de27  xor     esi, esi
0x14000de29  jmp     loc_14000DB97
0x14000de2e  int     2Ch; Windows NT - assertion failure
0x14000de30  xor     esi, esi
0x14000de32  jmp     loc_14000DB97
0x14000de37  int     2Ch; Windows NT - assertion failure
0x14000de39  xor     r14d, r14d
0x14000de3c  jmp     short loc_14000DDCA
0x14000de3e  int     2Ch; Windows NT - assertion failure
0x14000de40  xor     r14d, r14d
0x14000de43  jmp     short loc_14000DDCA
0x14000de45  mov     rcx, cs:WPP_GLOBAL_Control
0x14000de4c  lea     rax, WPP_GLOBAL_Control
0x14000de53  cmp     rcx, rax
0x14000de56  jz      loc_140039C0A
0x14000de5c  mov     eax, [rcx+2Ch]
0x14000de5f  test    al, al
0x14000de61  jns     loc_140039C0A
0x14000de67  cmp     byte ptr [rcx+29h], 4
0x14000de6b  jb      loc_140039C0A
0x14000de71  mov     r9, [rbx]
0x14000de74  mov     edx, 17h
0x14000de79  mov     rcx, [rcx+18h]
0x14000de7d  mov     [rsp+58h+var_38], r8d
0x14000de82  lea     r8, WPP_b1ee9e7bd57e3d642558c0c0d0c622f3_Traceguids
0x14000de89  call    WPP_SF_qD
0x14000de8e  nop
0x14000de8f  jmp     loc_140039C0A
0x14000de94  int     2Ch; Windows NT - assertion failure
0x14000de96  xor     r14d, r14d
0x14000de99  jmp     loc_14000DDCA
0x14000de9e  int     2Ch; Windows NT - assertion failure
0x14000dea0  xor     esi, esi
0x14000dea2  jmp     loc_14000DB97
0x140039c0a  mov     dword ptr [rbx+18h], 0C000009Ah
0x140039c11  jmp     loc_14000DCA2
```
