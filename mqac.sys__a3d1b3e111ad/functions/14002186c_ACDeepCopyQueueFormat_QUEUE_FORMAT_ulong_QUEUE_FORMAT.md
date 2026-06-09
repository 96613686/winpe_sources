# ACDeepCopyQueueFormat(QUEUE_FORMAT *,ulong,QUEUE_FORMAT * *)

- ea: `0x14002186c`
- end: `0x140021b56`
- name: `?ACDeepCopyQueueFormat@@YAXPEAUQUEUE_FORMAT@@KPEAPEAU1@@Z`
- size: `746`
- prototype: `void(struct QUEUE_FORMAT *, unsigned int, struct QUEUE_FORMAT **)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x140004d64`
- `0x14000533c`
- `0x1400058fc`
- `0x1400242b4`

## callees

- `0x1400010a4`
- `0x140001128`
- `0x140001170`
- `0x140007684`
- `0x140009008`
- `0x14002186c`
- `0x14002479c`
- `0x140024cc0`
- `0x140024fc0`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x1400218f2`
- `ntoskrnl!ExRaiseStatus` at `0x140021b22`
- `ntoskrnl!ExRaiseStatus` at `0x1400218f2`
- `ntoskrnl!ExRaiseStatus` at `0x140021b22`

## pseudocode

```c
void __fastcall ACDeepCopyQueueFormat(struct QUEUE_FORMAT *a1, unsigned int a2, struct QUEUE_FORMAT **a3)
{
  unsigned int v3; // r15d
  struct QUEUE_FORMAT *v4; // r12
  __int128 v5; // xmm6
  __int64 v6; // r14
  unsigned __int64 v7; // rax
  QUEUE_FORMAT *v8; // rax
  unsigned __int64 v9; // rdx
  void *(*v10)(void *); // r9
  QUEUE_FORMAT *v11; // rdi
  NTSTATUS v12; // ebx
  unsigned int i; // eax
  __int64 v14; // r14
  char *v15; // r15
  char v16; // cl
  wchar_t *v17; // r13
  int v18; // ecx
  unsigned __int64 v19; // rax
  _WORD *v20; // rax
  _WORD *v21; // r12
  char v22; // al
  unsigned int v23; // [rsp+24h] [rbp-B4h]
  unsigned __int64 v24; // [rsp+40h] [rbp-98h]
  _OWORD *v25; // [rsp+60h] [rbp-78h]
  int v29; // [rsp+F8h] [rbp+20h]

  v3 = a2;
  v4 = a1;
  v5 = 0;
  v6 = a2;
  v7 = 32LL * a2;
  if ( !is_mul_ok(a2, 0x20u) )
    v7 = -1;
  v8 = (QUEUE_FORMAT *)operator new(v7, 0x100u, 0x4351514Du, LowPoolPriority);
  v11 = v8;
  if ( v8 )
    `vector constructor iterator'(v8, v9, (unsigned int)v6, v10);
  else
    v11 = 0;
  if ( !v11 )
    ExRaiseStatus(-1073741670);
  v12 = 0;
  memset(v11, 0, 32 * v6);
  for ( i = 0; ; ++i )
  {
    v23 = i;
    if ( i >= v3 )
      break;
    v14 = 32LL * i;
    v15 = (char *)v4 + v14;
    v25 = (_OWORD *)((char *)v4 + v14);
    v16 = *((_BYTE *)v4 + v14);
    if ( v16 == 3 )
      goto LABEL_13;
    if ( v16 != 6 )
    {
      if ( v16 != 8 )
        goto LABEL_15;
LABEL_13:
      v17 = (wchar_t *)*((_QWORD *)v15 + 1);
      v18 = 1;
      goto LABEL_14;
    }
    v5 = *(_OWORD *)(v15 + 8);
    v17 = (wchar_t *)*((_QWORD *)v15 + 3);
    if ( v17 )
      goto LABEL_20;
    v18 = 0;
LABEL_14:
    if ( !v18 )
    {
LABEL_15:
      *(_OWORD *)((char *)v11 + v14) = *(_OWORD *)v15;
      *(_OWORD *)((char *)v11 + v14 + 16) = *((_OWORD *)v15 + 1);
      goto LABEL_31;
    }
    if ( !v17 )
    {
      v12 = -1073741811;
      break;
    }
LABEL_20:
    v29 = ACWCUserStringLen(v17);
    ACProbeArrayElementsForRead(v17, 2u, (unsigned int)(v29 + 1));
    v24 = (unsigned int)(v29 + 1);
    v19 = 2 * v24;
    if ( !is_mul_ok(v24, 2u) )
      v19 = -1;
    v20 = operator new(v19, 0x100u, 0x4353514Du, LowPoolPriority);
    v21 = v20;
    if ( !v20 )
    {
      v12 = -1073741670;
      break;
    }
    v12 = 0;
    memmove(v20, v17, 2 * v24);
    v21[v29] = 0;
    *(_OWORD *)((char *)v11 + v14) = *v25;
    *(_OWORD *)((char *)v11 + v14 + 16) = v25[1];
    v22 = *((_BYTE *)v11 + v14);
    switch ( v22 )
    {
      case 3:
        *(_WORD *)((char *)v11 + v14) = 3;
        *(_QWORD *)((char *)v11 + v14 + 8) = v21;
        *((_BYTE *)v11 + v14 + 1) = v15[1] & 0xF;
        break;
      case 6:
        *(_WORD *)((char *)v11 + v14) = 6;
        *(_OWORD *)((char *)v11 + v14 + 8) = v5;
        *(_QWORD *)((char *)v11 + v14 + 24) = v21;
        break;
      case 8:
        *(_WORD *)((char *)v11 + v14) = 1288;
        *(_QWORD *)((char *)v11 + v14 + 8) = v21;
        break;
    }
    i = v23;
    v4 = a1;
LABEL_31:
    v3 = a2;
  }
  if ( v12 < 0 )
  {
    ACFreeDeepCopyQueueFormat(v11, a2);
    ExRaiseStatus(v12);
  }
  *a3 = v11;
}

```

## disassembly

```asm
0x14002186c  mov     rax, rsp
0x14002186f  mov     [rax+18h], r8
0x140021873  mov     [rax+10h], edx
0x140021876  mov     [rax+8], rcx
0x14002187a  push    rbx
0x14002187b  push    rsi
0x14002187c  push    rdi
0x14002187d  push    r12
0x14002187f  push    r13
0x140021881  push    r14
0x140021883  push    r15
0x140021885  sub     rsp, 0A0h
0x14002188c  movaps  xmmword ptr [rax-48h], xmm6
0x140021890  mov     r15d, edx
0x140021893  mov     r12, rcx
0x140021896  xorps   xmm6, xmm6
0x140021899  movups  xmmword ptr [rax-70h], xmm6
0x14002189d  mov     r14d, edx
0x1400218a0  mov     eax, 20h ; ' '
0x1400218a5  mul     r15
0x1400218a8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400218af  cmovb   rax, rcx
0x1400218b3  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x1400218b6  mov     edx, 100h; unsigned __int64
0x1400218bb  mov     r8d, 4351514Dh; unsigned int
0x1400218c1  mov     rcx, rax; unsigned __int64
0x1400218c4  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x1400218c9  mov     rdi, rax
0x1400218cc  xor     esi, esi
0x1400218ce  test    rax, rax
0x1400218d1  jz      short loc_1400218E0
0x1400218d3  mov     r8d, r14d; unsigned __int64
0x1400218d6  mov     rcx, rax; this
0x1400218d9  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1400218de  jmp     short loc_1400218E3
0x1400218e0  mov     rdi, rsi
0x1400218e3  mov     [rsp+0D8h+var_B0], rdi
0x1400218e8  test    rdi, rdi
0x1400218eb  jnz     short loc_1400218FF
0x1400218ed  mov     ecx, 0C000009Ah; Status
0x1400218f2  call    cs:__imp_ExRaiseStatus
0x1400218ff  mov     ebx, esi
0x140021901  shl     r14, 5
0x140021905  mov     r8, r14; Size
0x140021908  xor     edx, edx; Val
0x14002190a  mov     rcx, rdi; void *
0x14002190d  call    memset
0x140021912  nop
0x140021913  mov     eax, esi
0x140021915  mov     [rsp+0D8h+var_B4], eax
0x140021919  cmp     eax, r15d
0x14002191c  jnb     loc_140021B00
0x140021922  mov     [rsp+0D8h+var_A8], rsi
0x140021927  mov     r14d, eax
0x14002192a  shl     r14, 5
0x14002192e  mov     [rsp+0D8h+var_88], r14
0x140021933  lea     r15, [r14+r12]
0x140021937  mov     [rsp+0D8h+var_80], r15
0x14002193c  mov     [rsp+0D8h+var_78], r15
0x140021941  mov     cl, [r15]
0x140021944  cmp     cl, 3
0x140021947  jz      short loc_140021953
0x140021949  cmp     cl, 6
0x14002194c  jz      short loc_14002197E
0x14002194e  cmp     cl, 8
0x140021951  jnz     short loc_140021965
0x140021953  mov     r13, [r15+8]
0x140021957  mov     [rsp+0D8h+var_A8], r13
0x14002195c  mov     ecx, 1
0x140021961  test    ecx, ecx
0x140021963  jnz     short loc_14002199A
0x140021965  movups  xmm0, xmmword ptr [r15]
0x140021969  movups  xmmword ptr [r14+rdi], xmm0
0x14002196e  movups  xmm1, xmmword ptr [r15+10h]
0x140021973  movups  xmmword ptr [r14+rdi+10h], xmm1
0x140021979  jmp     loc_140021AF1
0x14002197e  movups  xmm6, xmmword ptr [r15+8]
0x140021983  movups  [rsp+0D8h+var_70], xmm6
0x140021988  mov     r13, [r15+18h]
0x14002198c  mov     [rsp+0D8h+var_A8], r13
0x140021991  test    r13, r13
0x140021994  jnz     short loc_1400219AD
0x140021996  mov     ecx, esi
0x140021998  jmp     short loc_140021961
0x14002199a  test    r13, r13
0x14002199d  jnz     short loc_1400219AD
0x14002199f  mov     ebx, 0C000000Dh
0x1400219a4  mov     [rsp+0D8h+var_B8], ebx
0x1400219a8  jmp     loc_140021B00
0x1400219ad  mov     rcx, r13; wchar_t *
0x1400219b0  call    ?ACWCUserStringLen@@YAKPEA_W@Z; ACWCUserStringLen(wchar_t *)
0x1400219b5  mov     [rsp+0D8h+arg_18], eax
0x1400219bc  lea     ebx, [rax+1]
0x1400219bf  mov     [rsp+0D8h+var_A0], ebx
0x1400219c3  mov     r8d, ebx; unsigned int
0x1400219c6  mov     edx, 2; unsigned int
0x1400219cb  mov     rcx, r13; void *
0x1400219ce  call    ?ACProbeArrayElementsForRead@@YAXPEAXKK@Z; ACProbeArrayElementsForRead(void *,ulong,ulong)
0x1400219d3  mov     ecx, ebx
0x1400219d5  mov     [rsp+0D8h+var_98], rcx
0x1400219da  mov     eax, 2
0x1400219df  mul     rcx
0x1400219e2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400219e9  cmovb   rax, rcx
0x1400219ed  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x1400219f0  mov     edx, 100h; unsigned __int64
0x1400219f5  mov     r8d, 4353514Dh; unsigned int
0x1400219fb  mov     rcx, rax; unsigned __int64
0x1400219fe  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x140021a03  mov     r12, rax
0x140021a06  mov     [rsp+0D8h+var_90], rax
0x140021a0b  mov     [rsp+0D8h+var_58], rax
0x140021a13  test    rax, rax
0x140021a16  jnz     short loc_140021A1F
0x140021a18  mov     ebx, 0C000009Ah
0x140021a1d  jmp     short loc_1400219A4
0x140021a1f  mov     ebx, esi
0x140021a21  mov     [rsp+0D8h+var_B8], ebx
0x140021a25  mov     r8, [rsp+0D8h+var_98]
0x140021a2a  add     r8, r8; Size
0x140021a2d  mov     rdx, r13; Src
0x140021a30  mov     rcx, rax; void *
0x140021a33  call    memmove
0x140021a38  jmp     short loc_140021A63
0x140021a3a  mov     ebx, eax
0x140021a3c  mov     r12, [rsp+0D8h+var_90]
0x140021a41  mov     rcx, r12; void *
0x140021a44  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140021a49  mov     [rsp+0D8h+var_B8], ebx
0x140021a4d  xor     esi, esi
0x140021a4f  mov     rdi, [rsp+0D8h+var_B0]
0x140021a54  movups  xmm6, [rsp+0D8h+var_70]
0x140021a59  mov     r14, [rsp+0D8h+var_88]
0x140021a5e  mov     r15, [rsp+0D8h+var_80]
0x140021a63  test    ebx, ebx
0x140021a65  js      loc_140021B00
0x140021a6b  mov     eax, [rsp+0D8h+arg_18]
0x140021a72  mov     [r12+rax*2], si
0x140021a77  mov     rax, [rsp+0D8h+var_78]
0x140021a7c  movups  xmm0, xmmword ptr [rax]
0x140021a7f  movups  xmmword ptr [r14+rdi], xmm0
0x140021a84  movups  xmm1, xmmword ptr [rax+10h]
0x140021a88  movups  xmmword ptr [r14+rdi+10h], xmm1
0x140021a8e  mov     al, [r14+rdi]
0x140021a92  cmp     al, 3
0x140021a94  jz      short loc_140021AC5
0x140021a96  cmp     al, 6
0x140021a98  jz      short loc_140021AAC
0x140021a9a  cmp     al, 8
0x140021a9c  jnz     short loc_140021AE5
0x140021a9e  mov     word ptr [r14+rdi], 508h
0x140021aa5  mov     [r14+rdi+8], r12
0x140021aaa  jmp     short loc_140021AE5
0x140021aac  mov     [rsp+0D8h+var_60], r12
0x140021ab1  mov     word ptr [r14+rdi], 6
0x140021ab8  movups  xmmword ptr [r14+rdi+8], xmm6
0x140021abe  mov     [r14+rdi+18h], r12
0x140021ac3  jmp     short loc_140021AE5
0x140021ac5  mov     word ptr [r14+rdi], 3
0x140021acc  mov     [r14+rdi+8], r12
0x140021ad1  movzx   eax, byte ptr [r15+1]
0x140021ad6  and     eax, 0Fh
0x140021ad9  mov     [rsp+0D8h+arg_18], eax
0x140021ae0  mov     [r14+rdi+1], al
0x140021ae5  mov     eax, [rsp+0D8h+var_B4]
0x140021ae9  mov     r12, [rsp+0D8h+arg_0]
0x140021af1  inc     eax
0x140021af3  mov     r15d, [rsp+0D8h+arg_8]
0x140021afb  jmp     loc_140021915
0x140021b00  jmp     short loc_140021B0D
0x140021b02  mov     ebx, eax
0x140021b04  mov     [rsp+0D8h+var_B8], eax
0x140021b08  mov     rdi, [rsp+0D8h+var_B0]
0x140021b0d  test    ebx, ebx
0x140021b0f  jns     short loc_140021B2F
0x140021b11  mov     edx, [rsp+0D8h+arg_8]; unsigned int
0x140021b18  mov     rcx, rdi; struct QUEUE_FORMAT *
0x140021b1b  call    ?ACFreeDeepCopyQueueFormat@@YAXPEAUQUEUE_FORMAT@@K@Z; ACFreeDeepCopyQueueFormat(QUEUE_FORMAT *,ulong)
0x140021b20  mov     ecx, ebx; Status
0x140021b22  call    cs:__imp_ExRaiseStatus
0x140021b2f  mov     rax, [rsp+0D8h+arg_10]
0x140021b37  mov     [rax], rdi
0x140021b3a  movaps  xmm6, [rsp+0D8h+var_48]
0x140021b42  add     rsp, 0A0h
0x140021b49  pop     r15
0x140021b4b  pop     r14
0x140021b4d  pop     r13
0x140021b4f  pop     r12
0x140021b51  pop     rdi
0x140021b52  pop     rsi
0x140021b53  pop     rbx
0x140021b54  retn
```
