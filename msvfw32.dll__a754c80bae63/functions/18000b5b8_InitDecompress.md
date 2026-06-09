# InitDecompress

- ea: `0x18000b5b8`
- end: `0x18000b7d4`
- name: `InitDecompress`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009aec`

## callees

- `0x180003a60`
- `0x18000b2ac`
- `0x18000b5b8`

## pseudocode

```c
__int64 __fastcall InitDecompress(__int64 a1)
{
  int v2; // ecx
  _DWORD *v3; // rbx
  int v4; // r15d
  HIC *v5; // r14
  __int64 *v6; // rsi
  HIC v7; // rcx
  HIC *v8; // r15
  __int64 v9; // rax
  DWORD_PTR dw1[6]; // [rsp+20h] [rbp-50h] BYREF
  int v12; // [rsp+50h] [rbp-20h]
  int v13; // [rsp+54h] [rbp-1Ch]
  __int64 v14; // [rsp+58h] [rbp-18h]
  int v15; // [rsp+60h] [rbp-10h]
  int v16; // [rsp+64h] [rbp-Ch]

  v2 = *(_DWORD *)(a1 + 4);
  if ( (v2 & 0x600000) == 0 )
    return 1;
  v3 = (_DWORD *)(a1 + 12);
  if ( (v2 & 0x10004000) != 0 )
    *v3 = 0;
  v4 = v2 & 0x200000;
  if ( (v2 & 0x8400000) != 0x400000 )
  {
    v5 = (HIC *)(a1 + 328);
    v6 = (__int64 *)(a1 + 336);
    goto LABEL_14;
  }
  if ( *v3 == 2 )
    return 1;
  v5 = (HIC *)(a1 + 328);
  v6 = (__int64 *)(a1 + 336);
  if ( (v2 & 0x100000) != 0 )
  {
    ICSendMessage(*v5, 0x401Du, (a1 + 352) & -(__int64)(*(_QWORD *)(a1 + 48) != 0), 0);
    goto LABEL_10;
  }
  if ( FixUpCodecPalette(*v5, *v6) )
  {
LABEL_10:
    v7 = *v5;
    dw1[1] = *v6;
    v15 = *(_DWORD *)(a1 + 16);
    v16 = *(_DWORD *)(a1 + 20);
    dw1[3] = (DWORD_PTR)&biScreen;
    dw1[4] = lpScreen;
    v12 = *(_DWORD *)(a1 + 24);
    v13 = *(_DWORD *)(a1 + 28);
    dw1[0] = 0;
    dw1[2] = 0;
    v14 = 0;
    dw1[5] = 0;
    if ( !ICSendMessage(v7, 0x403Cu, (DWORD_PTR)dw1, 0x48u) )
    {
      *(_DWORD *)(a1 + 4) |= 0x1000000u;
      *v3 = 2;
      return 1;
    }
    goto LABEL_13;
  }
  *v3 = 0;
LABEL_13:
  *(_DWORD *)(a1 + 4) &= ~0x400000u;
  *v3 = 0;
LABEL_14:
  if ( v4 )
  {
    if ( *v3 == 1 )
      return 1;
    if ( (*(_DWORD *)(a1 + 4) & 0x100000) != 0 )
    {
      ICSendMessage(*v5, 0x401Du, (a1 + 352) & -(__int64)(*(_QWORD *)(a1 + 48) != 0), 0);
    }
    else if ( !FixUpCodecPalette(*v5, *v6) )
    {
      *v3 = 0;
LABEL_22:
      *v3 = 0;
      v6 = (__int64 *)(a1 + 336);
      v8 = (HIC *)(a1 + 328);
      goto LABEL_24;
    }
    if ( !ICSendMessage(*v5, 0x400Cu, *v6, a1 + 1416) )
    {
      *(_DWORD *)(a1 + 4) |= 0x1000000u;
      *v3 = 1;
      return 1;
    }
    goto LABEL_22;
  }
  v8 = v5;
LABEL_24:
  if ( *v3 != 3 )
  {
    *(_DWORD *)(a1 + 4) |= 0x1000000u;
    v9 = *(_QWORD *)(a1 + 48);
    *v3 = 3;
    ICSendMessage(*v5, 0x401Du, (a1 + 352) & -(__int64)(v9 != 0), 0);
    ICSendMessage(*v8, 0x400Cu, *v6, a1 + 352);
  }
  return 1;
}

```

## disassembly

```asm
0x18000b5b8  push    rbp
0x18000b5ba  push    rbx
0x18000b5bb  push    rsi
0x18000b5bc  push    rdi
0x18000b5bd  push    r12
0x18000b5bf  push    r14
0x18000b5c1  push    r15
0x18000b5c3  mov     rbp, rsp
0x18000b5c6  sub     rsp, 70h
0x18000b5ca  mov     rdi, rcx
0x18000b5cd  mov     ecx, [rcx+4]
0x18000b5d0  test    ecx, 600000h
0x18000b5d6  jz      loc_18000B7C0
0x18000b5dc  xor     r12d, r12d
0x18000b5df  lea     rbx, [rdi+0Ch]
0x18000b5e3  test    ecx, 10004000h
0x18000b5e9  jz      short loc_18000B5EE
0x18000b5eb  mov     [rbx], r12d
0x18000b5ee  mov     r15d, ecx
0x18000b5f1  mov     eax, ecx
0x18000b5f3  and     r15d, 200000h
0x18000b5fa  and     eax, 8400000h
0x18000b5ff  cmp     eax, 400000h
0x18000b604  jz      short loc_18000B619
0x18000b606  lea     r14, [rdi+148h]
0x18000b60d  lea     rsi, [rdi+150h]
0x18000b614  jmp     loc_18000B6E7
0x18000b619  cmp     dword ptr [rbx], 2
0x18000b61c  jz      loc_18000B7C0
0x18000b622  lea     r14, [rdi+148h]
0x18000b629  lea     rsi, [rdi+150h]
0x18000b630  bt      ecx, 14h
0x18000b634  jnb     short loc_18000B65C
0x18000b636  mov     rax, [rdi+30h]
0x18000b63a  lea     rcx, [rdi+160h]
0x18000b641  neg     rax
0x18000b644  mov     edx, 401Dh; msg
0x18000b649  sbb     r8, r8
0x18000b64c  xor     r9d, r9d; dw2
0x18000b64f  and     r8, rcx; dw1
0x18000b652  mov     rcx, [r14]; hic
0x18000b655  call    ICSendMessage
0x18000b65a  jmp     short loc_18000B66B
0x18000b65c  mov     rdx, [rsi]
0x18000b65f  mov     rcx, [r14]; hic
0x18000b662  call    FixUpCodecPalette
0x18000b667  test    eax, eax
0x18000b669  jz      short loc_18000B6DC
0x18000b66b  mov     rax, [rsi]
0x18000b66e  lea     r8, [rbp+dw1]; dw1
0x18000b672  mov     rcx, [r14]; hic
0x18000b675  mov     r9d, 48h ; 'H'; dw2
0x18000b67b  mov     [rbp+var_48], rax
0x18000b67f  mov     edx, 403Ch; msg
0x18000b684  mov     eax, [rdi+10h]
0x18000b687  mov     [rbp+var_10], eax
0x18000b68a  mov     eax, [rdi+14h]
0x18000b68d  mov     [rbp+var_C], eax
0x18000b690  lea     rax, biScreen
0x18000b697  mov     [rbp+var_38], rax
0x18000b69b  mov     rax, cs:lpScreen
0x18000b6a2  mov     [rbp+var_30], rax
0x18000b6a6  mov     eax, [rdi+18h]
0x18000b6a9  mov     [rbp+var_20], eax
0x18000b6ac  mov     eax, [rdi+1Ch]
0x18000b6af  mov     [rbp+var_1C], eax
0x18000b6b2  mov     [rbp+dw1], r12
0x18000b6b6  mov     [rbp+var_40], r12
0x18000b6ba  mov     [rbp+var_18], r12
0x18000b6be  mov     [rbp+var_28], r12
0x18000b6c2  call    ICSendMessage
0x18000b6c7  test    rax, rax
0x18000b6ca  jnz     short loc_18000B6DF
0x18000b6cc  bts     dword ptr [rdi+4], 18h
0x18000b6d1  mov     dword ptr [rbx], 2
0x18000b6d7  jmp     loc_18000B7C0
0x18000b6dc  mov     [rbx], r12d
0x18000b6df  btr     dword ptr [rdi+4], 16h
0x18000b6e4  mov     [rbx], r12d
0x18000b6e7  test    r15d, r15d
0x18000b6ea  jz      loc_18000B776
0x18000b6f0  cmp     dword ptr [rbx], 1
0x18000b6f3  jz      loc_18000B7C0
0x18000b6f9  test    dword ptr [rdi+4], 100000h
0x18000b700  jz      short loc_18000B728
0x18000b702  mov     rax, [rdi+30h]
0x18000b706  lea     rcx, [rdi+160h]
0x18000b70d  neg     rax
0x18000b710  mov     edx, 401Dh; msg
0x18000b715  sbb     r8, r8
0x18000b718  xor     r9d, r9d; dw2
0x18000b71b  and     r8, rcx; dw1
0x18000b71e  mov     rcx, [r14]; hic
0x18000b721  call    ICSendMessage
0x18000b726  jmp     short loc_18000B737
0x18000b728  mov     rdx, [rsi]
0x18000b72b  mov     rcx, [r14]; hic
0x18000b72e  call    FixUpCodecPalette
0x18000b733  test    eax, eax
0x18000b735  jz      short loc_18000B760
0x18000b737  mov     r8, [rsi]; dw1
0x18000b73a  lea     r9, [rdi+588h]; dw2
0x18000b741  mov     rcx, [r14]; hic
0x18000b744  mov     edx, 400Ch; msg
0x18000b749  call    ICSendMessage
0x18000b74e  test    rax, rax
0x18000b751  jnz     short loc_18000B763
0x18000b753  bts     dword ptr [rdi+4], 18h
0x18000b758  mov     dword ptr [rbx], 1
0x18000b75e  jmp     short loc_18000B7C0
0x18000b760  mov     [rbx], r12d
0x18000b763  mov     [rbx], r12d
0x18000b766  lea     rsi, [rdi+150h]
0x18000b76d  lea     r15, [rdi+148h]
0x18000b774  jmp     short loc_18000B779
0x18000b776  mov     r15, r14
0x18000b779  cmp     dword ptr [rbx], 3
0x18000b77c  jz      short loc_18000B7C0
0x18000b77e  bts     dword ptr [rdi+4], 18h
0x18000b783  mov     edx, 401Dh; msg
0x18000b788  mov     rax, [rdi+30h]
0x18000b78c  mov     dword ptr [rbx], 3
0x18000b792  neg     rax
0x18000b795  mov     rcx, [r14]; hic
0x18000b798  lea     rbx, [rdi+160h]
0x18000b79f  sbb     r8, r8
0x18000b7a2  xor     r9d, r9d; dw2
0x18000b7a5  and     r8, rbx; dw1
0x18000b7a8  call    ICSendMessage
0x18000b7ad  mov     r8, [rsi]; dw1
0x18000b7b0  mov     r9, rbx; dw2
0x18000b7b3  mov     rcx, [r15]; hic
0x18000b7b6  mov     edx, 400Ch; msg
0x18000b7bb  call    ICSendMessage
0x18000b7c0  mov     eax, 1
0x18000b7c5  add     rsp, 70h
0x18000b7c9  pop     r15
0x18000b7cb  pop     r14
0x18000b7cd  pop     r12
0x18000b7cf  pop     rdi
0x18000b7d0  pop     rsi
0x18000b7d1  pop     rbx
0x18000b7d2  pop     rbp
0x18000b7d3  retn
```
