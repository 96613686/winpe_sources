# UxCaptureString

- ea: `0x1c00bdf90`
- end: `0x1c00be1e7`
- name: `UxCaptureString`
- size: `599`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c002e754`
- `0x1c004c264`
- `0x1c00bbfe0`
- `0x1c010d8ac`
- `0x1c0120bfc`

## callees

- `0x1c0001118`
- `0x1c000b640`
- `0x1c001b610`
- `0x1c001b640`
- `0x1c008f30c`
- `0x1c00bdf90`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00be087`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00ed6b6`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00be087`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00ed6b6`
- `ntoskrnl!MmUserProbeAddress` at `0x1c00be0d0`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00ed66e`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00ed66e`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00ed716`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00ed716`

## pseudocode

```c
__int64 __fastcall UxCaptureString(char *Src, __int64 a2, __int64 a3, __int64 a4)
{
  char v5; // r14
  size_t v6; // r15
  unsigned int v8; // r12d
  SIZE_T v10; // rdx
  __int64 v11; // r9
  unsigned int v12; // r8d
  __int64 v13; // rax
  __int64 v14; // r14
  void *PoolWithTagPriority; // rbx
  __int64 v16; // rax
  __int64 v17; // rbx
  unsigned int v18; // r8d
  __int64 v19; // rax
  __int64 v20; // rbx
  __int64 v21; // [rsp+30h] [rbp-68h]
  __int128 v22; // [rsp+40h] [rbp-58h] BYREF
  __int64 v23; // [rsp+50h] [rbp-48h]
  __int64 v24; // [rsp+A0h] [rbp+8h]
  char v25; // [rsp+B0h] [rbp+18h]

  v25 = a3;
  v5 = a3;
  v6 = (unsigned __int16)a2;
  v8 = 0;
  v22 = 0;
  v23 = 0;
  *(_OWORD *)a4 = 0;
  *(_QWORD *)(a4 + 16) = 0;
  if ( Src || (_WORD)a2 )
  {
    if ( !Src && (_WORD)a2 || (_WORD)a2 == 0xFFFF )
      goto LABEL_28;
    v10 = (unsigned __int16)a2 + 1LL;
    if ( v6 + 1 > 0x80 )
    {
      WORD1(v22) = v6 + 1;
      PoolWithTagPriority = ExAllocatePoolWithTagPriority(PagedPool, v10, 0x55536C55u, LowPoolPriority);
      *((_QWORD *)&v22 + 1) = PoolWithTagPriority;
      if ( !PoolWithTagPriority )
      {
        v8 = -1073741670;
        goto LABEL_3;
      }
    }
    else
    {
      LOBYTE(v23) = 1;
      WORD1(v22) = 128;
      if ( UxCompactMode )
      {
        v17 = qword_1C0074540;
        v24 = qword_1C0074540;
        v18 = KeGetCurrentNodeNumber() + 1;
        v19 = (unsigned int)(*(_DWORD *)v17 - 1);
        if ( v18 < *(_DWORD *)v17 )
          v19 = v18;
        v20 = *(_QWORD *)(*(_QWORD *)(v17 + 32) + 8 * v19);
        v21 = v20;
        if ( !*(_BYTE *)(v20 + 112) )
          PplpLazyInitializeLookasideList(v24, v20);
        ++*(_DWORD *)(v20 + 20);
        PoolWithTagPriority = ExpInterlockedPopEntrySList((PSLIST_HEADER)v20);
        if ( !PoolWithTagPriority )
        {
          ++*(_DWORD *)(v21 + 24);
          PoolWithTagPriority = (void *)(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(v21 + 48))(
                                          *(unsigned int *)(v21 + 36),
                                          *(unsigned int *)(v21 + 44),
                                          *(unsigned int *)(v21 + 40),
                                          v21);
        }
      }
      else
      {
        v11 = *(_QWORD *)(qword_1C0074540 + 32);
        v12 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
        v13 = (unsigned int)(*(_DWORD *)qword_1C0074540 - 1);
        if ( v12 < *(_DWORD *)qword_1C0074540 )
          v13 = v12;
        v14 = *(_QWORD *)(v11 + 8 * v13);
        if ( !*(_BYTE *)(v14 + 112) )
          PplpLazyInitializeLookasideList(qword_1C0074540, *(_QWORD *)(v11 + 8 * v13));
        ++*(_DWORD *)(v14 + 20);
        PoolWithTagPriority = ExpInterlockedPopEntrySList((PSLIST_HEADER)v14);
        if ( !PoolWithTagPriority )
        {
          ++*(_DWORD *)(v14 + 24);
          PoolWithTagPriority = (void *)(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(v14 + 48))(
                                          *(unsigned int *)(v14 + 36),
                                          *(unsigned int *)(v14 + 44),
                                          *(unsigned int *)(v14 + 40),
                                          v14);
        }
        v5 = v25;
      }
      *((_QWORD *)&v22 + 1) = PoolWithTagPriority;
      if ( !PoolWithTagPriority )
      {
        v8 = -1073741670;
        goto LABEL_3;
      }
    }
    if ( (WORD2(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x100) != 0 )
      WPP_SF_PqLc(10, a2, v6, Src);
    if ( v5 && v6 && ((unsigned __int64)&Src[v6] > MmUserProbeAddress || &Src[v6] < Src) )
      *(_BYTE *)MmUserProbeAddress = 0;
    memmove(PoolWithTagPriority, Src, v6);
    *((_BYTE *)PoolWithTagPriority + (unsigned __int16)v6) = 0;
    v16 = -1;
    do
      ++v16;
    while ( *((_BYTE *)PoolWithTagPriority + v16) );
    if ( v16 != v6 )
    {
LABEL_28:
      v8 = -1073741811;
    }
    else
    {
      LOWORD(v22) = v6;
      *(_OWORD *)a4 = v22;
      *(_QWORD *)(a4 + 16) = v23;
      v22 = 0;
      v23 = 0;
    }
  }
LABEL_3:
  UxFreeCapturedAnsiString(&v22, a2, a3);
  return v8;
}

```

## disassembly

```asm
0x1c00bdf90  mov     [rsp+arg_18], r9
0x1c00bdf95  mov     [rsp+arg_10], r8b
0x1c00bdf9a  mov     [rsp+arg_8], dx
0x1c00bdf9f  push    rbx
0x1c00bdfa0  push    rsi
0x1c00bdfa1  push    rdi
0x1c00bdfa2  push    r12
0x1c00bdfa4  push    r13
0x1c00bdfa6  push    r14
0x1c00bdfa8  push    r15
0x1c00bdfaa  sub     rsp, 60h
0x1c00bdfae  mov     r13, r9
0x1c00bdfb1  movzx   r14d, r8b
0x1c00bdfb5  movzx   r15d, dx
0x1c00bdfb9  mov     rsi, rcx
0x1c00bdfbc  xor     r12d, r12d
0x1c00bdfbf  xorps   xmm0, xmm0
0x1c00bdfc2  xor     eax, eax
0x1c00bdfc4  movups  [rsp+98h+var_58], xmm0
0x1c00bdfc9  mov     [rsp+98h+var_48], rax
0x1c00bdfce  xorps   xmm1, xmm1
0x1c00bdfd1  movups  xmmword ptr [r9], xmm1
0x1c00bdfd5  mov     [r9+10h], rax
0x1c00bdfd9  test    rcx, rcx
0x1c00bdfdc  jnz     short loc_1C00BE002
0x1c00bdfde  test    r15w, r15w
0x1c00bdfe2  jnz     short loc_1C00BE002
0x1c00bdfe4  lea     rcx, [rsp+98h+var_58]
0x1c00bdfe9  call    UxFreeCapturedAnsiString
0x1c00bdfee  mov     eax, r12d
0x1c00bdff1  add     rsp, 60h
0x1c00bdff5  pop     r15
0x1c00bdff7  pop     r14
0x1c00bdff9  pop     r13
0x1c00bdffb  pop     r12
0x1c00bdffd  pop     rdi
0x1c00bdffe  pop     rsi
0x1c00bdfff  pop     rbx
0x1c00be000  retn
0x1c00be002  test    rsi, rsi
0x1c00be005  jz      loc_1C00ED64A
0x1c00be00b  mov     eax, 0FFFEh
0x1c00be010  cmp     r15w, ax
0x1c00be014  ja      loc_1C00ED654
0x1c00be01a  mov     rdi, r15
0x1c00be01d  mov     [rsp+98h+var_60], r15
0x1c00be022  lea     rdx, [r15+1]; NumberOfBytes
0x1c00be026  mov     eax, 80h
0x1c00be02b  cmp     rdx, rax
0x1c00be02e  ja      loc_1C00ED700
0x1c00be034  mov     byte ptr [rsp+98h+var_48], 1
0x1c00be039  mov     word ptr [rsp+98h+var_58+2], ax
0x1c00be03e  cmp     cs:UxCompactMode, r12b
0x1c00be045  jnz     loc_1C00ED65F
0x1c00be04b  mov     eax, gs:1A4h
0x1c00be053  mov     rcx, cs:qword_1C0074540
0x1c00be05a  mov     r9, [rcx+20h]
0x1c00be05e  lea     r8d, [rax+1]
0x1c00be062  mov     edx, [rcx]
0x1c00be064  lea     eax, [rdx-1]
0x1c00be067  cmp     r8d, edx
0x1c00be06a  cmovb   eax, r8d
0x1c00be06e  mov     r14, [r9+rax*8]
0x1c00be072  cmp     [r14+70h], r12b
0x1c00be076  jnz     short loc_1C00BE080
0x1c00be078  mov     rdx, r14
0x1c00be07b  call    PplpLazyInitializeLookasideList
0x1c00be080  inc     dword ptr [r14+14h]
0x1c00be084  mov     rcx, r14; ListHead
0x1c00be087  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c00be08e  nop     dword ptr [rax+rax+00h]
0x1c00be093  mov     rbx, rax
0x1c00be096  test    rax, rax
0x1c00be099  jz      loc_1C00BE1C2
0x1c00be09f  movzx   r14d, [rsp+98h+arg_10]
0x1c00be0a8  mov     qword ptr [rsp+98h+var_58+8], rbx
0x1c00be0ad  test    rbx, rbx
0x1c00be0b0  jz      loc_1C00ED6F5
0x1c00be0b6  test    dword ptr cs:WPP_MAIN_CB.Queue+4, 100h
0x1c00be0c0  jnz     short loc_1C00BE0E9
0x1c00be0c2  test    r14b, r14b
0x1c00be0c5  jz      short loc_1C00BE117
0x1c00be0c7  test    r15, r15
0x1c00be0ca  jz      short loc_1C00BE117
0x1c00be0cc  lea     rcx, [r15+rsi]
0x1c00be0d0  mov     rax, cs:MmUserProbeAddress
0x1c00be0d7  mov     rdx, [rax]
0x1c00be0da  cmp     rcx, rdx
0x1c00be0dd  ja      short loc_1C00BE0E4
0x1c00be0df  cmp     rcx, rsi
0x1c00be0e2  jnb     short loc_1C00BE117
0x1c00be0e4  mov     byte ptr [rdx], 0
0x1c00be0e7  jmp     short loc_1C00BE117
0x1c00be0e9  mov     eax, 55h ; 'U'
0x1c00be0ee  mov     ecx, 4Bh ; 'K'
0x1c00be0f3  test    r14b, r14b
0x1c00be0f6  cmovz   eax, ecx
0x1c00be0f9  mov     ecx, 0Ah
0x1c00be0fe  mov     [rsp+98h+var_70], al
0x1c00be102  mov     [rsp+98h+var_78], 1
0x1c00be10a  mov     r9, rsi
0x1c00be10d  mov     r8, r15
0x1c00be110  call    WPP_SF_PqLc
0x1c00be115  jmp     short loc_1C00BE0C2
0x1c00be117  mov     r8, r15; Size
0x1c00be11a  mov     rdx, rsi; Src
0x1c00be11d  mov     rcx, rbx; void *
0x1c00be120  call    memmove
0x1c00be125  jmp     short loc_1C00BE16C
0x1c00be127  mov     r12d, eax
0x1c00be12a  and     eax, 0C0000000h
0x1c00be12f  cmp     eax, 80000000h
0x1c00be134  jnz     short loc_1C00BE147
0x1c00be136  cmp     r12d, 80000005h
0x1c00be13d  jz      short loc_1C00BE147
0x1c00be13f  mov     r12d, 0C000000Dh
0x1c00be145  jmp     short loc_1C00BE14C
0x1c00be147  test    r12d, r12d
0x1c00be14a  jns     short loc_1C00BE151
0x1c00be14c  jmp     loc_1C00BDFE4
0x1c00be151  mov     r13, [rsp+98h+arg_18]
0x1c00be159  movzx   r15d, [rsp+98h+arg_8]
0x1c00be162  mov     rbx, qword ptr [rsp+98h+var_58+8]
0x1c00be167  mov     rdi, [rsp+98h+var_60]
0x1c00be16c  movzx   eax, r15w
0x1c00be170  mov     byte ptr [rax+rbx], 0
0x1c00be174  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1c00be17b  nop     dword ptr [rax+rax+00h]
0x1c00be180  inc     rax
0x1c00be183  cmp     byte ptr [rbx+rax], 0
0x1c00be187  jnz     short loc_1C00BE180
0x1c00be189  cmp     rax, rdi
0x1c00be18c  jnz     loc_1C00ED654
0x1c00be192  mov     word ptr [rsp+98h+var_58], r15w
0x1c00be198  movups  xmm0, [rsp+98h+var_58]
0x1c00be19d  movups  xmmword ptr [r13+0], xmm0
0x1c00be1a2  movsd   xmm1, [rsp+98h+var_48]
0x1c00be1a8  movsd   qword ptr [r13+10h], xmm1
0x1c00be1ae  xorps   xmm0, xmm0
0x1c00be1b1  xor     eax, eax
0x1c00be1b3  movups  [rsp+98h+var_58], xmm0
0x1c00be1b8  mov     [rsp+98h+var_48], rax
0x1c00be1bd  jmp     loc_1C00BDFE4
0x1c00be1c2  inc     dword ptr [r14+18h]
0x1c00be1c6  mov     edx, [r14+2Ch]
0x1c00be1ca  mov     rax, [r14+30h]
0x1c00be1ce  mov     r9, r14
0x1c00be1d1  mov     r8d, [r14+28h]
0x1c00be1d5  mov     ecx, [r14+24h]
0x1c00be1d9  call    cs:__guard_dispatch_icall_fptr
0x1c00be1df  mov     rbx, rax
0x1c00be1e2  jmp     loc_1C00BE09F
0x1c00ed64a  test    r15w, r15w
0x1c00ed64e  jz      loc_1C00BE00B
0x1c00ed654  mov     r12d, 0C000000Dh
0x1c00ed65a  jmp     loc_1C00BDFE4
0x1c00ed65f  mov     rbx, cs:qword_1C0074540
0x1c00ed666  mov     [rsp+98h+arg_0], rbx
0x1c00ed66e  call    cs:__imp_KeGetCurrentNodeNumber
0x1c00ed675  nop     dword ptr [rax+rax+00h]
0x1c00ed67a  movzx   r8d, ax
0x1c00ed67e  mov     r9, [rbx+20h]
0x1c00ed682  inc     r8d
0x1c00ed685  mov     edx, [rbx]
0x1c00ed687  lea     eax, [rdx-1]
0x1c00ed68a  cmp     r8d, edx
0x1c00ed68d  cmovb   eax, r8d
0x1c00ed691  mov     rbx, [r9+rax*8]
0x1c00ed695  mov     [rsp+98h+var_68], rbx
0x1c00ed69a  cmp     [rbx+70h], r12b
0x1c00ed69e  jnz     short loc_1C00ED6B0
0x1c00ed6a0  mov     rdx, rbx
0x1c00ed6a3  mov     rcx, [rsp+98h+arg_0]
0x1c00ed6ab  call    PplpLazyInitializeLookasideList
0x1c00ed6b0  inc     dword ptr [rbx+14h]
0x1c00ed6b3  mov     rcx, rbx; ListHead
0x1c00ed6b6  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c00ed6bd  nop     dword ptr [rax+rax+00h]
0x1c00ed6c2  mov     rbx, rax
0x1c00ed6c5  test    rax, rax
0x1c00ed6c8  jnz     loc_1C00BE0A8
0x1c00ed6ce  mov     rcx, [rsp+98h+var_68]
0x1c00ed6d3  inc     dword ptr [rcx+18h]
0x1c00ed6d6  mov     edx, [rcx+2Ch]
0x1c00ed6d9  mov     rax, [rcx+30h]
0x1c00ed6dd  mov     r9, rcx
0x1c00ed6e0  mov     r8d, [rcx+28h]
0x1c00ed6e4  mov     ecx, [rcx+24h]
0x1c00ed6e7  call    cs:__guard_dispatch_icall_fptr
0x1c00ed6ed  mov     rbx, rax
0x1c00ed6f0  jmp     loc_1C00BE0A8
0x1c00ed6f5  mov     r12d, 0C000009Ah
0x1c00ed6fb  jmp     loc_1C00BDFE4
0x1c00ed700  lea     eax, [r15+1]
0x1c00ed704  mov     word ptr [rsp+98h+var_58+2], ax
0x1c00ed709  xor     r9d, r9d; Priority
0x1c00ed70c  lea     ecx, [r9+1]; PoolType
0x1c00ed710  mov     r8d, 55536C55h; Tag
0x1c00ed716  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c00ed71d  nop     dword ptr [rax+rax+00h]
0x1c00ed722  mov     rbx, rax
0x1c00ed725  mov     qword ptr [rsp+98h+var_58+8], rax
0x1c00ed72a  test    rax, rax
0x1c00ed72d  jnz     loc_1C00BE0B6
0x1c00ed733  mov     r12d, 0C000009Ah
0x1c00ed739  jmp     loc_1C00BDFE4
```
