# itrp_MSIRP

- ea: `0x14001d630`
- end: `0x14001d989`
- name: `itrp_MSIRP`
- size: `857`
- prototype: `__int64 __fastcall(struct fnt_LocalGraphicStateType *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x14002e8e0`
- `0x140095ae0`

## callees

- `0x14001d630`
- `0x14001e120`
- `0x1400250f0`
- `0x140025f10`
- `0x140072578`
- `0x140098010`

## pseudocode

```c
__int64 __fastcall itrp_MSIRP(struct fnt_LocalGraphicStateType *a1, __int64 a2, char a3)
{
  __int64 v3; // r14
  __int64 v5; // rcx
  __int64 v6; // r12
  __int64 v7; // rax
  __int64 v8; // r15
  int *v9; // rsi
  __int64 v10; // rbp
  __int64 v11; // r13
  __int64 v12; // rdi
  __int64 v14; // rdi
  __int64 v15; // rsi
  int v16; // eax
  int v17; // eax
  int v18; // edx
  int v19; // r8d
  int v20; // eax
  struct fnt_LocalGraphicStateType *v21; // rcx
  __int64 v22; // [rsp+78h] [rbp+10h]

  v22 = a2;
  v3 = *((_QWORD *)a1 + 8);
  v5 = *((_QWORD *)a1 + 5);
  v6 = 0;
  v7 = (v5 - *(_QWORD *)v3) >> 2;
  if ( v7 < 0 )
    goto LABEL_10;
  if ( (unsigned __int64)v7 < 2 )
  {
    *((_DWORD *)a1 + 42) = 4368;
    return *((_QWORD *)a1 + 22);
  }
  v8 = *(_QWORD *)a1;
  v9 = (int *)(v5 - 8);
  v10 = *((int *)a1 + 20);
  *((_QWORD *)a1 + 5) = v5 - 4;
  v11 = *(int *)(v5 - 4);
  *((_QWORD *)a1 + 5) = v5 - 8;
  if ( *((_QWORD *)a1 + 7) == v8 )
  {
    if ( (int)v10 >= *(unsigned __int16 *)(*(_QWORD *)(v3 + 376) + 16LL) || (int)v10 < 0 )
      goto LABEL_14;
    v12 = 0;
  }
  else
  {
    if ( (int)v10 >= *(_DWORD *)(v3 + 432) || (int)v10 < 0 )
      goto LABEL_14;
    v12 = 4;
  }
  if ( !CHECK_ELEMENT_EP_PTR_ALLOW_OUTOF_BOUND(a1, (struct fnt_ElementType *)v8) || *(__int16 *)(v8 + 80) <= 0 )
    goto LABEL_14;
  v5 = *(__int16 *)(v8 + 80);
  a2 = v12 + *(__int16 *)(*(_QWORD *)(v8 + 64) + 2 * v5 - 2);
  if ( (unsigned __int64)(a2 + 0x80000000LL) > 0xFFFFFFFF
    || (v5 = (int)a2 + 1LL, (unsigned __int64)((int)a2 + 2147483649LL) > 0xFFFFFFFF) )
  {
LABEL_10:
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v5, a2);
    __debugbreak();
  }
  if ( (int)v5 <= (int)v10 )
    goto LABEL_14;
  v14 = *((_QWORD *)a1 + 1);
  v15 = *v9;
  if ( *((_QWORD *)a1 + 7) == v14 )
  {
    if ( (int)v15 >= *(unsigned __int16 *)(*(_QWORD *)(v3 + 376) + 16LL) || (int)v15 < 0 )
      goto LABEL_14;
  }
  else
  {
    if ( (int)v15 >= *(_DWORD *)(v3 + 432) || (int)v15 < 0 )
      goto LABEL_14;
    v6 = 4;
  }
  if ( !CHECK_ELEMENT_EP_PTR_ALLOW_OUTOF_BOUND(a1, (struct fnt_ElementType *)v14) || *(__int16 *)(v14 + 80) <= 0 )
  {
LABEL_14:
    *((_DWORD *)a1 + 42) = 4370;
    return *((_QWORD *)a1 + 22);
  }
  v5 = *(__int16 *)(v14 + 80);
  a2 = v6 + *(__int16 *)(*(_QWORD *)(v14 + 64) + 2 * v5 - 2);
  if ( (unsigned __int64)(a2 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_10;
  v5 = (int)a2 + 1LL;
  if ( (unsigned __int64)((int)a2 + 2147483649LL) > 0xFFFFFFFF )
    goto LABEL_10;
  if ( (int)v5 <= (int)v15 )
    goto LABEL_14;
  if ( v14 == *((_QWORD *)a1 + 7) )
    goto LABEL_39;
  if ( *(_BYTE *)(v3 + 363) == 2 && *((_WORD *)a1 + 102) && (*(_BYTE *)(v3 + 448) & 2) != 0 )
  {
    v20 = DoubleCheckLinkColor((struct fnt_ElementType *)v14, v10, v15, 1);
    AddDistance(v21, (struct fnt_ElementType *)v14, v10, v15, v20);
  }
  if ( v14 == *((_QWORD *)a1 + 7) )
  {
LABEL_39:
    *(_DWORD *)(*(_QWORD *)(v14 + 16) + 4 * v15) = *(_DWORD *)(*(_QWORD *)(v8 + 16) + 4 * v10)
                                                 + ((((v11 * *((__int16 *)a1 + 12)) >> 13) + 1) >> 1);
    *(_DWORD *)(*(_QWORD *)(v14 + 24) + 4 * v15) = *(_DWORD *)(*(_QWORD *)(v8 + 24) + 4 * v10)
                                                 + ((((v11 * *((__int16 *)a1 + 13)) >> 13) + 1) >> 1);
    *(_DWORD *)(*(_QWORD *)v14 + 4 * v15) = *(_DWORD *)(*(_QWORD *)(v14 + 16) + 4 * v15);
    *(_DWORD *)(*(_QWORD *)(v14 + 8) + 4 * v15) = *(_DWORD *)(*(_QWORD *)(v14 + 24) + 4 * v15);
  }
  if ( (*(_BYTE *)(*((_QWORD *)a1 + 8) + 136LL) & 4) == 0 )
  {
    if ( *((_WORD *)a1 + 102) )
    {
      v17 = (*((__int64 (__fastcall **)(struct fnt_LocalGraphicStateType *, _QWORD, _QWORD))a1 + 15))(
              a1,
              (unsigned int)(*(_DWORD *)(*(_QWORD *)(v14 + 16) + 4 * v15) - *(_DWORD *)(*(_QWORD *)(v8 + 16) + 4 * v10)),
              (unsigned int)(*(_DWORD *)(*(_QWORD *)(v14 + 24) + 4 * v15) - *(_DWORD *)(*(_QWORD *)(v8 + 24) + 4 * v10)));
      if ( v17 )
      {
        v18 = 16 * (v11 - v17);
        v19 = *(_DWORD *)(*((_QWORD *)a1 + 8) + 120LL);
        if ( v18 > v19 || v18 < -v19 )
          LODWORD(v11) = v17;
      }
    }
  }
  v16 = (*((__int64 (__fastcall **)(struct fnt_LocalGraphicStateType *, _QWORD, _QWORD))a1 + 14))(
          a1,
          (unsigned int)(*(_DWORD *)(*(_QWORD *)v14 + 4 * v15) - *(_DWORD *)(*(_QWORD *)v8 + 4 * v10)),
          (unsigned int)(*(_DWORD *)(*(_QWORD *)(v14 + 8) + 4 * v15) - *(_DWORD *)(*(_QWORD *)(v8 + 8) + 4 * v10)));
  (*((void (__fastcall **)(struct fnt_LocalGraphicStateType *, __int64, _QWORD, _QWORD))a1 + 13))(
    a1,
    v14,
    (unsigned int)v15,
    (unsigned int)(v11 - v16));
  *((_DWORD *)a1 + 21) = v10;
  *((_DWORD *)a1 + 22) = v15;
  if ( (a3 & 1) != 0 )
    *((_DWORD *)a1 + 20) = v15;
  return v22;
}

```

## disassembly

```asm
0x14001d630  mov     [rsp+arg_0], rbx
0x14001d635  mov     [rsp+arg_10], r8d
0x14001d63a  mov     [rsp+arg_8], rdx
0x14001d63f  push    rbp
0x14001d640  push    rsi
0x14001d641  push    rdi
0x14001d642  push    r12
0x14001d644  push    r13
0x14001d646  push    r14
0x14001d648  push    r15
0x14001d64a  sub     rsp, 30h
0x14001d64e  mov     r14, [rcx+40h]
0x14001d652  mov     rbx, rcx
0x14001d655  mov     rcx, [rcx+28h]
0x14001d659  xor     r12d, r12d
0x14001d65c  mov     rax, rcx
0x14001d65f  sub     rax, [r14]
0x14001d662  sar     rax, 2
0x14001d666  test    rax, rax
0x14001d669  js      short loc_14001D6E4
0x14001d66b  cmp     rax, 2
0x14001d66f  jb      loc_14001D97A
0x14001d675  mov     r15, [rbx]
0x14001d678  lea     rax, [rcx-4]
0x14001d67c  lea     rsi, [rax-4]
0x14001d680  movsxd  rbp, dword ptr [rbx+50h]
0x14001d684  mov     [rbx+28h], rax
0x14001d688  movsxd  r13, dword ptr [rax]
0x14001d68b  mov     [rbx+28h], rsi
0x14001d68f  cmp     [rbx+38h], r15
0x14001d693  jz      short loc_14001D6EA
0x14001d695  cmp     ebp, [r14+1B0h]
0x14001d69c  jge     short loc_14001D702
0x14001d69e  test    ebp, ebp
0x14001d6a0  js      short loc_14001D702
0x14001d6a2  lea     edi, [r12+4]
0x14001d6a7  mov     rdx, r15; struct fnt_ElementType *
0x14001d6aa  mov     rcx, rbx; struct fnt_LocalGraphicStateType *
0x14001d6ad  call    ?CHECK_ELEMENT_EP_PTR_ALLOW_OUTOF_BOUND@@YA_NPEAUfnt_LocalGraphicStateType@@PEAUfnt_ElementType@@@Z; CHECK_ELEMENT_EP_PTR_ALLOW_OUTOF_BOUND(fnt_LocalGraphicStateType *,fnt_ElementType *)
0x14001d6b2  test    al, al
0x14001d6b4  jz      short loc_14001D702
0x14001d6b6  cmp     [r15+50h], r12w
0x14001d6bb  jle     short loc_14001D702
0x14001d6bd  mov     rax, [r15+40h]
0x14001d6c1  mov     r8d, 80000000h
0x14001d6c7  movsx   rcx, word ptr [r15+50h]
0x14001d6cc  mov     r9d, 0FFFFFFFFh
0x14001d6d2  movsx   rdx, word ptr [rax+rcx*2-2]
0x14001d6d8  add     rdx, rdi
0x14001d6db  lea     rax, [rdx+r8]
0x14001d6df  cmp     rax, r9
0x14001d6e2  jbe     short loc_14001D728
0x14001d6e4  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x14001d6e9  int     3; Trap to Debugger
0x14001d6ea  mov     rax, [r14+178h]
0x14001d6f1  movzx   ecx, word ptr [rax+10h]
0x14001d6f5  cmp     ebp, ecx
0x14001d6f7  jge     short loc_14001D702
0x14001d6f9  test    ebp, ebp
0x14001d6fb  js      short loc_14001D702
0x14001d6fd  mov     rdi, r12
0x14001d700  jmp     short loc_14001D6A7
0x14001d702  mov     dword ptr [rbx+0A8h], 1112h
0x14001d70c  mov     rax, [rbx+0B0h]
0x14001d713  mov     rbx, [rsp+68h+arg_0]
0x14001d718  add     rsp, 30h
0x14001d71c  pop     r15
0x14001d71e  pop     r14
0x14001d720  pop     r13
0x14001d722  pop     r12
0x14001d724  pop     rdi
0x14001d725  pop     rsi
0x14001d726  pop     rbp
0x14001d727  retn
0x14001d728  movsxd  rcx, edx
0x14001d72b  inc     rcx
0x14001d72e  lea     rax, [rcx+r8]
0x14001d732  cmp     rax, r9
0x14001d735  ja      short loc_14001D6E4
0x14001d737  cmp     ecx, ebp
0x14001d739  jle     short loc_14001D702
0x14001d73b  mov     rdi, [rbx+8]
0x14001d73f  movsxd  rsi, dword ptr [rsi]
0x14001d742  cmp     [rbx+38h], rdi
0x14001d746  jz      loc_14001D862
0x14001d74c  cmp     esi, [r14+1B0h]
0x14001d753  jge     short loc_14001D702
0x14001d755  test    esi, esi
0x14001d757  js      short loc_14001D702
0x14001d759  mov     r12d, 4
0x14001d75f  mov     rdx, rdi; struct fnt_ElementType *
0x14001d762  mov     rcx, rbx; struct fnt_LocalGraphicStateType *
0x14001d765  call    ?CHECK_ELEMENT_EP_PTR_ALLOW_OUTOF_BOUND@@YA_NPEAUfnt_LocalGraphicStateType@@PEAUfnt_ElementType@@@Z; CHECK_ELEMENT_EP_PTR_ALLOW_OUTOF_BOUND(fnt_LocalGraphicStateType *,fnt_ElementType *)
0x14001d76a  xor     r10d, r10d
0x14001d76d  test    al, al
0x14001d76f  jz      short loc_14001D702
0x14001d771  cmp     [rdi+50h], r10w
0x14001d776  jle     short loc_14001D702
0x14001d778  mov     rax, [rdi+40h]
0x14001d77c  mov     r8d, 80000000h
0x14001d782  movsx   rcx, word ptr [rdi+50h]
0x14001d787  mov     r9d, 0FFFFFFFFh
0x14001d78d  movsx   rdx, word ptr [rax+rcx*2-2]
0x14001d793  add     rdx, r12
0x14001d796  lea     rax, [rdx+r8]
0x14001d79a  cmp     rax, r9
0x14001d79d  ja      loc_14001D6E4
0x14001d7a3  movsxd  rcx, edx
0x14001d7a6  inc     rcx
0x14001d7a9  lea     rax, [rcx+r8]
0x14001d7ad  cmp     rax, r9
0x14001d7b0  ja      loc_14001D6E4
0x14001d7b6  cmp     ecx, esi
0x14001d7b8  jle     loc_14001D702
0x14001d7be  cmp     rdi, [rbx+38h]
0x14001d7c2  jz      loc_14001D882
0x14001d7c8  cmp     byte ptr [r14+16Bh], 2
0x14001d7d0  jnz     short loc_14001D7E0
0x14001d7d2  cmp     [rbx+0CCh], r10w
0x14001d7da  jnz     loc_14001D93F
0x14001d7e0  cmp     rdi, [rbx+38h]
0x14001d7e4  jz      loc_14001D882
0x14001d7ea  mov     rax, [rbx+40h]
0x14001d7ee  test    byte ptr [rax+88h], 4
0x14001d7f5  jnz     short loc_14001D805
0x14001d7f7  cmp     [rbx+0CCh], r10w
0x14001d7ff  jnz     loc_14001D8E4
0x14001d805  mov     rcx, [rdi+8]
0x14001d809  mov     rax, [r15+8]
0x14001d80d  mov     r8d, [rcx+rsi*4]
0x14001d811  mov     rcx, [rdi]
0x14001d814  sub     r8d, [rax+rbp*4]
0x14001d818  mov     rax, [r15]
0x14001d81b  mov     edx, [rcx+rsi*4]
0x14001d81e  mov     rcx, rbx
0x14001d821  sub     edx, [rax+rbp*4]
0x14001d824  mov     rax, [rbx+70h]
0x14001d828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d82d  sub     r13d, eax
0x14001d830  mov     r8d, esi
0x14001d833  mov     rax, [rbx+68h]
0x14001d837  mov     r9d, r13d
0x14001d83a  mov     rdx, rdi
0x14001d83d  mov     rcx, rbx
0x14001d840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d845  test    byte ptr [rsp+68h+arg_10], 1
0x14001d84d  mov     [rbx+54h], ebp
0x14001d850  mov     [rbx+58h], esi
0x14001d853  jz      short loc_14001D858
0x14001d855  mov     [rbx+50h], esi
0x14001d858  mov     rax, [rsp+68h+arg_8]
0x14001d85d  jmp     loc_14001D713
0x14001d862  mov     rax, [r14+178h]
0x14001d869  movzx   ecx, word ptr [rax+10h]
0x14001d86d  cmp     esi, ecx
0x14001d86f  jge     loc_14001D702
0x14001d875  test    esi, esi
0x14001d877  jns     loc_14001D75F
0x14001d87d  jmp     loc_14001D702
0x14001d882  mov     rax, [r15+10h]
0x14001d886  movsx   rcx, word ptr [rbx+18h]
0x14001d88b  imul    rcx, r13
0x14001d88f  sar     rcx, 0Dh
0x14001d893  inc     rcx
0x14001d896  sar     rcx, 1
0x14001d899  add     ecx, [rax+rbp*4]
0x14001d89c  mov     rax, [rdi+10h]
0x14001d8a0  mov     [rax+rsi*4], ecx
0x14001d8a3  mov     rax, [r15+18h]
0x14001d8a7  movsx   rcx, word ptr [rbx+1Ah]
0x14001d8ac  imul    rcx, r13
0x14001d8b0  sar     rcx, 0Dh
0x14001d8b4  inc     rcx
0x14001d8b7  sar     rcx, 1
0x14001d8ba  add     ecx, [rax+rbp*4]
0x14001d8bd  mov     rax, [rdi+18h]
0x14001d8c1  mov     [rax+rsi*4], ecx
0x14001d8c4  mov     rax, [rdi+10h]
0x14001d8c8  mov     rcx, [rdi]
0x14001d8cb  mov     eax, [rax+rsi*4]
0x14001d8ce  mov     [rcx+rsi*4], eax
0x14001d8d1  mov     rax, [rdi+18h]
0x14001d8d5  mov     rcx, [rdi+8]
0x14001d8d9  mov     eax, [rax+rsi*4]
0x14001d8dc  mov     [rcx+rsi*4], eax
0x14001d8df  jmp     loc_14001D7EA
0x14001d8e4  mov     rcx, [rdi+18h]
0x14001d8e8  mov     rax, [r15+18h]
0x14001d8ec  mov     r8d, [rcx+rsi*4]
0x14001d8f0  mov     rcx, [rdi+10h]
0x14001d8f4  sub     r8d, [rax+rbp*4]
0x14001d8f8  mov     rax, [r15+10h]
0x14001d8fc  mov     edx, [rcx+rsi*4]
0x14001d8ff  mov     rcx, rbx
0x14001d902  sub     edx, [rax+rbp*4]
0x14001d905  mov     rax, [rbx+78h]
0x14001d909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d90e  test    eax, eax
0x14001d910  jz      loc_14001D805
0x14001d916  mov     rcx, [rbx+40h]
0x14001d91a  mov     edx, r13d
0x14001d91d  sub     edx, eax
0x14001d91f  shl     edx, 4
0x14001d922  mov     r8d, [rcx+78h]
0x14001d926  cmp     edx, r8d
0x14001d929  jg      short loc_14001D937
0x14001d92b  neg     r8d
0x14001d92e  cmp     edx, r8d
0x14001d931  jge     loc_14001D805
0x14001d937  mov     r13d, eax
0x14001d93a  jmp     loc_14001D805
0x14001d93f  test    byte ptr [r14+1C0h], 2
0x14001d947  jz      loc_14001D7E0
0x14001d94d  mov     r9d, 1; int
0x14001d953  mov     r8d, esi; int
0x14001d956  mov     edx, ebp; int
0x14001d958  mov     rcx, rdi; struct fnt_ElementType *
0x14001d95b  call    ?DoubleCheckLinkColor@@YAHPEAUfnt_ElementType@@HHH@Z; DoubleCheckLinkColor(fnt_ElementType *,int,int,int)
0x14001d960  mov     r9d, esi; int
0x14001d963  mov     [rsp+68h+var_48], eax; int
0x14001d967  mov     r8d, ebp; int
0x14001d96a  mov     rdx, rdi; struct fnt_ElementType *
0x14001d96d  call    ?AddDistance@@YAXPEAUfnt_LocalGraphicStateType@@PEAUfnt_ElementType@@HHH@Z; AddDistance(fnt_LocalGraphicStateType *,fnt_ElementType *,int,int,int)
0x14001d972  xor     r10d, r10d
0x14001d975  jmp     loc_14001D7E0
0x14001d97a  mov     dword ptr [rbx+0A8h], 1110h
0x14001d984  jmp     loc_14001D70C
```
