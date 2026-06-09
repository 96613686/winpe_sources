# FormatFileTraceEvent

- ea: `0x140002d68`
- end: `0x1400031ea`
- name: `FormatFileTraceEvent`
- size: `1154`
- prototype: `char __fastcall(__int64, __int64, _DWORD *, int *, __int64 *Size)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400010b0`
- `0x140001ae0`
- `0x140002a00`

## callees

- `0x140002d68`
- `0x140003600`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002f0d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002f0d`
- `ntoskrnl!KeGetCurrentIrql` at `0x140002e94`
- `ntoskrnl!KeGetCurrentIrql` at `0x140002e94`
- `ntoskrnl!MmIsAddressValid` at `0x140002e81`
- `ntoskrnl!MmIsAddressValid` at `0x140002e81`
- `ntoskrnl!ExAllocatePool2` at `0x140002f42`
- `ntoskrnl!ExAllocatePool2` at `0x140002f42`

## pseudocode

```c
char __fastcall FormatFileTraceEvent(__int64 a1, __int64 a2, _DWORD *a3, int *a4, __int64 *Size)
{
  signed __int32 v8; // r12d
  unsigned __int16 *v9; // rcx
  _WORD *v10; // rax
  int v11; // edx
  int v12; // r8d
  int v13; // ecx
  int v14; // eax
  __int64 v15; // rdx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  unsigned __int16 *v19; // rcx
  int v20; // r8d
  int v21; // ecx
  int v22; // ecx
  __int64 v23; // rax
  int v24; // eax
  int v25; // eax
  void *v26; // rcx
  unsigned int v27; // r14d
  size_t v28; // r13
  __int64 v29; // r15
  int v30; // ecx
  PVOID v31; // rax
  __int64 v32; // rcx
  __int64 Pool2; // rax
  _DWORD *v35; // rbx
  unsigned int v36; // eax
  const void *v37; // rdx
  _WORD *v38; // rsi
  const void *v39; // rdx
  const void *v40; // rdx
  const void *v41; // rdx
  unsigned __int16 *v42; // rcx
  _WORD *v43; // rdx
  unsigned __int64 v44; // rcx
  const void *v45; // rdx
  _WORD *v46; // rsi
  __int64 v47; // rax
  const void *v48; // rdx
  _WORD *v49; // rdx
  _WORD *v50; // rdx
  _WORD *v51; // rbx
  __int64 v52; // rax
  _WORD *v53; // rdx
  _WORD *v54; // rbx
  const void **v55; // rcx
  __int64 v56; // [rsp+50h] [rbp+8h]
  unsigned int Sizea; // [rsp+70h] [rbp+28h]

  v56 = *Size;
  v8 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
  *a4 = 86;
  v9 = *(unsigned __int16 **)(a2 + 8);
  if ( !v9 )
    goto LABEL_8;
  v10 = (_WORD *)*((_QWORD *)v9 + 1);
  if ( v10 )
  {
    if ( *v10 != 58 )
    {
      v11 = **(unsigned __int16 **)(a2 + 32);
      v12 = *v9;
      if ( (unsigned __int16)v12 > (unsigned __int16)v11 )
      {
        v13 = v12 - v11 + 88;
        goto LABEL_9;
      }
    }
  }
  if ( !*((_QWORD *)v9 + 1) || (v14 = *v9, v13 = v14 + 88, !(_WORD)v14) )
LABEL_8:
    v13 = 88;
LABEL_9:
  *a4 = v13;
  v15 = *(_QWORD *)(a2 + 32);
  if ( v15 != -16 && *(_QWORD *)(v15 + 24) && (v16 = *(unsigned __int16 *)(v15 + 16), (_WORD)v16) )
    v17 = v13 + v16;
  else
    v17 = v13;
  v18 = v17 + 2;
  *a4 = v18;
  v19 = *(unsigned __int16 **)(a2 + 32);
  if ( !v19 || !*((_QWORD *)v19 + 1) || (v20 = *v19, v21 = v18 + v20, !(_WORD)v20) )
    v21 = v18;
  v22 = v21 + 2;
  *a4 = v22;
  v23 = *(_QWORD *)(a2 + 32);
  if ( v23 != -32 && *(_QWORD *)(v23 + 40) && (v24 = *(unsigned __int16 *)(v23 + 32), (_WORD)v24) )
    v25 = v22 + v24;
  else
    v25 = v22;
  *a4 = v25 + 2;
  v26 = *(void **)(a2 + 144);
  if ( !v26 )
    goto LABEL_31;
  if ( !MmIsAddressValid(v26) || KeGetCurrentIrql() >= 2u || *(_BYTE *)(a2 + 17) )
  {
    *(_QWORD *)(a2 + 144) = 0;
LABEL_31:
    v27 = 0;
    goto LABEL_32;
  }
  v27 = *(_DWORD *)(a2 + 136);
  if ( v27 > 0x400 )
    v27 = 1024;
LABEL_32:
  v28 = *(unsigned int *)(a2 + 120);
  Sizea = *(_DWORD *)(a2 + 152);
  v29 = 4;
  v30 = 4;
  if ( *(_DWORD *)(a2 + 96) )
    v30 = *(_DWORD *)(a2 + 96);
  *a4 += v27 + v30 + *(_DWORD *)(a2 + 152) + v28;
  if ( (unsigned int)*a4 <= 0x180 )
  {
    v32 = v56;
    goto LABEL_43;
  }
  if ( (unsigned int)*a4 > 0x800 )
  {
    Pool2 = ExAllocatePool2(64, (unsigned int)*a4, 1920224326);
    *Size = Pool2;
    if ( Pool2 )
    {
      *a3 = 2;
      goto LABEL_38;
    }
    return 0;
  }
  v31 = ExAllocateFromNPagedLookasideList(&Lookaside);
  *Size = (__int64)v31;
  if ( !v31 )
    return 0;
  *a3 = 1;
LABEL_38:
  v32 = *Size;
LABEL_43:
  *(_DWORD *)v32 = *(_DWORD *)a2;
  *(_BYTE *)(a2 + 4) += 22;
  *(_BYTE *)(v32 + 4) = *(_BYTE *)(a2 + 4);
  *(_BYTE *)(v32 + 5) = *(_BYTE *)(a2 + 5);
  *(_DWORD *)(v32 + 6) = v8;
  *(_BYTE *)(v32 + 10) = *(_BYTE *)(a2 + 17);
  *(_BYTE *)(v32 + 11) = *(_BYTE *)(a2 + 18);
  *(_BYTE *)(v32 + 12) = *(_BYTE *)(a2 + 16);
  *(_BYTE *)(v32 + 13) = *(_BYTE *)(a2 + 64);
  *(_QWORD *)(v32 + 14) = *(_QWORD *)(a2 + 24);
  *(_DWORD *)(v32 + 22) = *(_DWORD *)(a2 + 48);
  *(_QWORD *)(v32 + 26) = *(_QWORD *)(a2 + 56);
  *(_QWORD *)(v32 + 34) = *(_QWORD *)(a2 + 40);
  *(_QWORD *)(v32 + 42) = *(_QWORD *)(a2 + 72);
  *(_DWORD *)(v32 + 50) = *(_DWORD *)(a2 + 80);
  *(_QWORD *)(v32 + 54) = *(_QWORD *)(a2 + 112);
  *(_QWORD *)(v32 + 62) = *(_QWORD *)(a2 + 88);
  *(_DWORD *)(v32 + 70) = *(_DWORD *)(a2 + 96);
  *(_DWORD *)(v32 + 74) = v28;
  *(_DWORD *)(v32 + 78) = v27;
  *(_DWORD *)(v32 + 82) = Sizea;
  v35 = (_DWORD *)(v32 + 86);
  v36 = *(_DWORD *)(a2 + 96);
  if ( v36 && (v37 = *(const void **)(a2 + 104)) != 0 )
  {
    memmove(v35, v37, v36);
    v29 = *(unsigned int *)(a2 + 96);
  }
  else
  {
    *v35 = 0;
  }
  v38 = (_WORD *)((char *)v35 + v29);
  if ( (_DWORD)v28 )
  {
    v39 = *(const void **)(a2 + 128);
    if ( v39 )
    {
      memmove((char *)v35 + v29, v39, v28);
      v38 = (_WORD *)((char *)v38 + v28);
    }
  }
  if ( v27 )
  {
    v40 = *(const void **)(a2 + 144);
    if ( v40 )
    {
      memmove(v38, v40, v27);
      v38 = (_WORD *)((char *)v38 + v27);
    }
  }
  if ( Sizea )
  {
    v41 = *(const void **)(a2 + 160);
    if ( v41 )
    {
      memmove(v38, v41, Sizea);
      v38 = (_WORD *)((char *)v38 + Sizea);
    }
  }
  v42 = *(unsigned __int16 **)(a2 + 8);
  if ( !v42 )
    goto LABEL_64;
  v43 = (_WORD *)*((_QWORD *)v42 + 1);
  if ( !v43 || *v43 == 58 || *v42 <= **(_WORD **)(a2 + 32) )
  {
    v45 = (const void *)*((_QWORD *)v42 + 1);
    if ( !v45 )
      goto LABEL_64;
    memmove(v38, v45, *v42);
    v44 = **(unsigned __int16 **)(a2 + 8);
  }
  else
  {
    memmove(
      v38,
      (char *)v43 + **(unsigned __int16 **)(a2 + 32),
      *v42 - (unsigned __int64)**(unsigned __int16 **)(a2 + 32));
    v44 = **(unsigned __int16 **)(a2 + 8) - (unsigned __int64)**(unsigned __int16 **)(a2 + 32);
  }
  v38 = (_WORD *)((char *)v38 + v44);
LABEL_64:
  *v38 = 0;
  v46 = v38 + 1;
  v47 = *(_QWORD *)(a2 + 32);
  if ( v47 == -32 || (v48 = *(const void **)(v47 + 40)) == 0 )
  {
    v49 = v46;
  }
  else
  {
    memmove(v46, v48, *(unsigned __int16 *)(v47 + 32));
    v49 = (_WORD *)((char *)v46 + *(unsigned __int16 *)(*(_QWORD *)(a2 + 32) + 32LL));
  }
  *v49 = 0;
  v50 = v49 + 1;
  v51 = v50;
  v52 = *(_QWORD *)(a2 + 32);
  if ( v52 != -16 && *(_QWORD *)(v52 + 24) )
  {
    memmove(v50, *(const void **)(v52 + 24), *(unsigned __int16 *)(v52 + 16));
    v50 = (_WORD *)((char *)v51 + *(unsigned __int16 *)(*(_QWORD *)(a2 + 32) + 16LL));
  }
  *v50 = 0;
  v53 = v50 + 1;
  v54 = v53;
  v55 = *(const void ***)(a2 + 32);
  if ( v55 )
  {
    if ( v55[1] )
    {
      memmove(v53, v55[1], *(unsigned __int16 *)v55);
      v53 = (_WORD *)((char *)v54 + **(unsigned __int16 **)(a2 + 32));
    }
  }
  *v53 = 0;
  return 1;
}

```

## disassembly

```asm
0x140002d68  mov     [rsp+arg_8], rbx
0x140002d6d  mov     [rsp+arg_18], rsi
0x140002d72  mov     [rsp+arg_10], r8
0x140002d77  push    rdi
0x140002d78  push    r12
0x140002d7a  push    r13
0x140002d7c  push    r14
0x140002d7e  push    r15
0x140002d80  sub     rsp, 20h
0x140002d84  mov     rbx, r9
0x140002d87  mov     rdi, rdx
0x140002d8a  mov     rsi, [rsp+48h+Size]
0x140002d8f  mov     rax, [rsi]
0x140002d92  mov     [rsp+48h+arg_0], rax
0x140002d97  mov     r12d, 1
0x140002d9d  lock xadd [rcx+10h], r12d
0x140002da3  inc     r12d
0x140002da6  mov     dword ptr [r9], 56h ; 'V'
0x140002dad  mov     rcx, [rdx+8]
0x140002db1  xor     r10d, r10d
0x140002db4  test    rcx, rcx
0x140002db7  jz      short loc_140002DF9
0x140002db9  mov     rax, [rcx+8]
0x140002dbd  test    rax, rax
0x140002dc0  jz      short loc_140002DE3
0x140002dc2  cmp     word ptr [rax], 3Ah ; ':'
0x140002dc6  jz      short loc_140002DE3
0x140002dc8  mov     rax, [rdx+20h]
0x140002dcc  movzx   edx, word ptr [rax]
0x140002dcf  movzx   r8d, word ptr [rcx]
0x140002dd3  cmp     r8w, dx
0x140002dd7  jbe     short loc_140002DE3
0x140002dd9  mov     ecx, r8d
0x140002ddc  sub     ecx, edx
0x140002dde  add     ecx, 58h ; 'X'
0x140002de1  jmp     short loc_140002DFE
0x140002de3  test    rcx, rcx
0x140002de6  jz      short loc_140002DF9
0x140002de8  cmp     [rcx+8], r10
0x140002dec  jz      short loc_140002DF9
0x140002dee  movzx   eax, word ptr [rcx]
0x140002df1  test    ax, ax
0x140002df4  lea     ecx, [rax+58h]
0x140002df7  jnz     short loc_140002DFE
0x140002df9  mov     ecx, 58h ; 'X'
0x140002dfe  mov     rax, rbx
0x140002e01  mov     [rbx], ecx
0x140002e03  mov     rdx, [rdi+20h]
0x140002e07  lea     r8, [rdx+10h]
0x140002e0b  test    r8, r8
0x140002e0e  jz      short loc_140002E23
0x140002e10  cmp     [rdx+18h], r10
0x140002e14  jz      short loc_140002E23
0x140002e16  movzx   edx, word ptr [r8]
0x140002e1a  test    dx, dx
0x140002e1d  jz      short loc_140002E23
0x140002e1f  add     edx, ecx
0x140002e21  jmp     short loc_140002E25
0x140002e23  mov     edx, ecx
0x140002e25  add     edx, 2
0x140002e28  mov     [rax], edx
0x140002e2a  mov     rcx, [rdi+20h]
0x140002e2e  test    rcx, rcx
0x140002e31  jz      short loc_140002E47
0x140002e33  cmp     [rcx+8], r10
0x140002e37  jz      short loc_140002E47
0x140002e39  movzx   r8d, word ptr [rcx]
0x140002e3d  test    r8w, r8w
0x140002e41  lea     ecx, [rdx+r8]
0x140002e45  jnz     short loc_140002E49
0x140002e47  mov     ecx, edx
0x140002e49  add     ecx, 2
0x140002e4c  mov     [rax], ecx
0x140002e4e  mov     rax, [rdi+20h]
0x140002e52  lea     rdx, [rax+20h]
0x140002e56  test    rdx, rdx
0x140002e59  jz      short loc_140002E6D
0x140002e5b  cmp     [rax+28h], r10
0x140002e5f  jz      short loc_140002E6D
0x140002e61  movzx   eax, word ptr [rdx]
0x140002e64  test    ax, ax
0x140002e67  jz      short loc_140002E6D
0x140002e69  add     eax, ecx
0x140002e6b  jmp     short loc_140002E6F
0x140002e6d  mov     eax, ecx
0x140002e6f  add     eax, 2
0x140002e72  mov     [r9], eax
0x140002e75  mov     rcx, [rdi+90h]; VirtualAddress
0x140002e7c  test    rcx, rcx
0x140002e7f  jz      short loc_140002EC9
0x140002e81  call    cs:__imp_MmIsAddressValid
0x140002e88  nop     dword ptr [rax+rax+00h]
0x140002e8d  xor     r10d, r10d
0x140002e90  test    al, al
0x140002e92  jz      short loc_140002EC2
0x140002e94  call    cs:__imp_KeGetCurrentIrql
0x140002e9b  nop     dword ptr [rax+rax+00h]
0x140002ea0  xor     r10d, r10d
0x140002ea3  cmp     al, 2
0x140002ea5  jnb     short loc_140002EC2
0x140002ea7  cmp     [rdi+11h], r10b
0x140002eab  jnz     short loc_140002EC2
0x140002ead  mov     r14d, [rdi+88h]
0x140002eb4  mov     eax, 400h
0x140002eb9  cmp     r14d, eax
0x140002ebc  cmova   r14d, eax
0x140002ec0  jmp     short loc_140002ECC
0x140002ec2  mov     [rdi+90h], r10
0x140002ec9  mov     r14d, r10d
0x140002ecc  mov     r13d, [rdi+78h]
0x140002ed0  mov     edx, [rdi+98h]
0x140002ed6  mov     dword ptr [rsp+48h+Size], edx
0x140002eda  mov     eax, [rdi+60h]
0x140002edd  mov     r15d, 4
0x140002ee3  mov     ecx, r15d
0x140002ee6  test    eax, eax
0x140002ee8  cmovnz  ecx, eax
0x140002eeb  lea     eax, [rdx+r13]
0x140002eef  add     eax, ecx
0x140002ef1  add     eax, r14d
0x140002ef4  add     [rbx], eax
0x140002ef6  mov     eax, [rbx]
0x140002ef8  cmp     eax, 180h
0x140002efd  jbe     short loc_140002F6D
0x140002eff  cmp     eax, 800h
0x140002f04  ja      short loc_140002F34
0x140002f06  lea     rcx, Lookaside; Lookaside
0x140002f0d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140002f14  nop     dword ptr [rax+rax+00h]
0x140002f19  mov     [rsi], rax
0x140002f1c  xor     r10d, r10d
0x140002f1f  test    rax, rax
0x140002f22  jz      short loc_140002F59
0x140002f24  mov     rax, [rsp+48h+arg_10]
0x140002f29  mov     dword ptr [rax], 1
0x140002f2f  mov     rcx, [rsi]
0x140002f32  jmp     short loc_140002F72
0x140002f34  mov     rdx, rax
0x140002f37  mov     ecx, 40h ; '@'
0x140002f3c  mov     r8d, 72744C46h
0x140002f42  call    cs:__imp_ExAllocatePool2
0x140002f49  nop     dword ptr [rax+rax+00h]
0x140002f4e  mov     [rsi], rax
0x140002f51  xor     r10d, r10d
0x140002f54  test    rax, rax
0x140002f57  jnz     short loc_140002F60
0x140002f59  xor     al, al
0x140002f5b  jmp     loc_1400031D1
0x140002f60  mov     rax, [rsp+48h+arg_10]
0x140002f65  mov     dword ptr [rax], 2
0x140002f6b  jmp     short loc_140002F2F
0x140002f6d  mov     rcx, [rsp+48h+arg_0]
0x140002f72  mov     eax, [rdi]
0x140002f74  mov     [rcx], eax
0x140002f76  add     byte ptr [rdi+4], 16h
0x140002f7a  mov     al, [rdi+4]
0x140002f7d  mov     [rcx+4], al
0x140002f80  mov     al, [rdi+5]
0x140002f83  mov     [rcx+5], al
0x140002f86  mov     [rcx+6], r12d
0x140002f8a  mov     al, [rdi+11h]
0x140002f8d  mov     [rcx+0Ah], al
0x140002f90  mov     al, [rdi+12h]
0x140002f93  mov     [rcx+0Bh], al
0x140002f96  mov     al, [rdi+10h]
0x140002f99  mov     [rcx+0Ch], al
0x140002f9c  mov     al, [rdi+40h]
0x140002f9f  mov     [rcx+0Dh], al
0x140002fa2  mov     rax, [rdi+18h]
0x140002fa6  mov     [rcx+0Eh], rax
0x140002faa  mov     eax, [rdi+30h]
0x140002fad  mov     [rcx+16h], eax
0x140002fb0  mov     rax, [rdi+38h]
0x140002fb4  mov     [rcx+1Ah], rax
0x140002fb8  mov     rax, [rdi+28h]
0x140002fbc  mov     [rcx+22h], rax
0x140002fc0  mov     rax, [rdi+48h]
0x140002fc4  mov     [rcx+2Ah], rax
0x140002fc8  mov     eax, [rdi+50h]
0x140002fcb  mov     [rcx+32h], eax
0x140002fce  mov     rax, [rdi+70h]
0x140002fd2  mov     [rcx+36h], rax
0x140002fd6  mov     rax, [rdi+58h]
0x140002fda  mov     [rcx+3Eh], rax
0x140002fde  mov     eax, [rdi+60h]
0x140002fe1  mov     [rcx+46h], eax
0x140002fe4  lea     rax, [rcx+4Ah]
0x140002fe8  mov     [rax], r13d
0x140002feb  add     rax, r15
0x140002fee  mov     [rax], r14d
0x140002ff1  mov     r12d, dword ptr [rsp+48h+Size]
0x140002ff6  mov     [rax+r15], r12d
0x140002ffa  lea     rbx, [r15+4]
0x140002ffe  add     rbx, rax
0x140003001  mov     eax, [rdi+60h]
0x140003004  test    eax, eax
0x140003006  jz      short loc_140003025
0x140003008  mov     rdx, [rdi+68h]; Src
0x14000300c  test    rdx, rdx
0x14000300f  jz      short loc_140003025
0x140003011  mov     r8d, eax; Size
0x140003014  mov     rcx, rbx; void *
0x140003017  call    memmove
0x14000301c  mov     r15d, [rdi+60h]
0x140003020  xor     r10d, r10d
0x140003023  jmp     short loc_140003028
0x140003025  mov     [rbx], r10d
0x140003028  lea     rsi, [rbx+r15]
0x14000302c  test    r13d, r13d
0x14000302f  jz      short loc_14000304E
0x140003031  mov     rdx, [rdi+80h]; Src
0x140003038  test    rdx, rdx
0x14000303b  jz      short loc_14000304E
0x14000303d  mov     r8, r13; Size
0x140003040  mov     rcx, rsi; void *
0x140003043  call    memmove
0x140003048  add     rsi, r13
0x14000304b  xor     r10d, r10d
0x14000304e  test    r14d, r14d
0x140003051  jz      short loc_14000307D
0x140003053  mov     rdx, [rdi+90h]; Src
0x14000305a  test    rdx, rdx
0x14000305d  jz      short loc_14000307D
0x14000305f  mov     ebx, r14d
0x140003062  mov     r8d, r14d; Size
0x140003065  mov     rcx, rsi; void *
0x140003068  call    memmove
0x14000306d  nop
0x14000306e  add     rsi, rbx
0x140003071  xor     r10d, r10d
0x140003074  jmp     short loc_14000307D
0x140003076  xor     al, al
0x140003078  jmp     loc_1400031D1
0x14000307d  test    r12d, r12d
0x140003080  jz      short loc_14000309F
0x140003082  mov     rdx, [rdi+0A0h]; Src
0x140003089  test    rdx, rdx
0x14000308c  jz      short loc_14000309F
0x14000308e  mov     r8, r12; Size
0x140003091  mov     rcx, rsi; void *
0x140003094  call    memmove
0x140003099  add     rsi, r12
0x14000309c  xor     r10d, r10d
0x14000309f  mov     rcx, [rdi+8]
0x1400030a3  test    rcx, rcx
0x1400030a6  jz      short loc_140003117
0x1400030a8  mov     rdx, [rcx+8]
0x1400030ac  test    rdx, rdx
0x1400030af  jz      short loc_1400030F0
0x1400030b1  cmp     word ptr [rdx], 3Ah ; ':'
0x1400030b5  jz      short loc_1400030F0
0x1400030b7  mov     rax, [rdi+20h]
0x1400030bb  movzx   r8d, word ptr [rax]
0x1400030bf  movzx   r9d, word ptr [rcx]
0x1400030c3  cmp     r9w, r8w
0x1400030c7  jbe     short loc_1400030F0
0x1400030c9  mov     eax, r8d
0x1400030cc  mov     r8d, r9d
0x1400030cf  sub     r8, rax; Size
0x1400030d2  add     rdx, rax; Src
0x1400030d5  mov     rcx, rsi; void *
0x1400030d8  call    memmove
0x1400030dd  mov     rax, [rdi+20h]
0x1400030e1  movzx   edx, word ptr [rax]
0x1400030e4  mov     rax, [rdi+8]
0x1400030e8  movzx   ecx, word ptr [rax]
0x1400030eb  sub     rcx, rdx
0x1400030ee  jmp     short loc_140003111
0x1400030f0  test    rcx, rcx
0x1400030f3  jz      short loc_140003117
0x1400030f5  mov     rdx, [rcx+8]; Src
0x1400030f9  test    rdx, rdx
0x1400030fc  jz      short loc_140003117
0x1400030fe  movzx   r8d, word ptr [rcx]; Size
0x140003102  mov     rcx, rsi; void *
0x140003105  call    memmove
0x14000310a  mov     rax, [rdi+8]
0x14000310e  movzx   ecx, word ptr [rax]
0x140003111  add     rsi, rcx
0x140003114  xor     r10d, r10d
0x140003117  mov     [rsi], r10w
0x14000311b  add     rsi, 2
0x14000311f  mov     rax, [rdi+20h]
0x140003123  lea     rcx, [rax+20h]
0x140003127  test    rcx, rcx
0x14000312a  jz      short loc_140003151
0x14000312c  mov     rdx, [rax+28h]; Src
0x140003130  test    rdx, rdx
0x140003133  jz      short loc_140003151
0x140003135  movzx   r8d, word ptr [rcx]; Size
0x140003139  mov     rcx, rsi; void *
0x14000313c  call    memmove
0x140003141  mov     rax, [rdi+20h]
0x140003145  movzx   edx, word ptr [rax+20h]
0x140003149  add     rdx, rsi
0x14000314c  xor     r10d, r10d
0x14000314f  jmp     short loc_140003154
0x140003151  mov     rdx, rsi
0x140003154  mov     [rdx], r10w
0x140003158  add     rdx, 2
  ... truncated ...
```
