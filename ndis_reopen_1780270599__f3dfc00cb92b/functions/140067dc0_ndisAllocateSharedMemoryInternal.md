# ndisAllocateSharedMemoryInternal

- ea: `0x140067dc0`
- end: `0x14006819e`
- name: `ndisAllocateSharedMemoryInternal`
- size: `990`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140067a40`

## callees

- `0x140067dc0`
- `0x1400eb380`
- `0x1400eb460`
- `0x1400eb4c0`

## import_xrefs

- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140067eff`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140067eff`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140067f89`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140067f89`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140067ea8`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140067ea8`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x140067ede`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x140067ede`
- `ntoskrnl!MmAllocateContiguousNodeMemory` at `0x1400f28d3`
- `ntoskrnl!MmAllocateContiguousNodeMemory` at `0x1400f28d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140067fa2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140067fa2`
- `ntoskrnl!ExAllocatePool2` at `0x140067e2b`
- `ntoskrnl!ExAllocatePool2` at `0x140067e2b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400680f7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400680f7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140068079`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140068079`
- `ntoskrnl!MmGetPhysicalAddress` at `0x1400f28ef`
- `ntoskrnl!MmGetPhysicalAddress` at `0x1400f28ef`

## pseudocode

```c
__int64 __fastcall ndisAllocateSharedMemoryInternal(_QWORD *a1, __int64 a2, __int128 *a3, _QWORD *a4)
{
  unsigned int v4; // eax
  KSPIN_LOCK *v6; // rbp
  __int64 v7; // r15
  __int64 v8; // r13
  KSPIN_LOCK v9; // rdi
  __int64 Pool2; // rax
  char *v11; // rbx
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  unsigned int v15; // r12d
  char v16; // r14
  __int128 v17; // xmm1
  USHORT HighestNodeNumber; // ax
  __int64 v19; // r9
  __int64 (__fastcall *v20)(KSPIN_LOCK, __int128 *, char *); // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  int v23; // edi
  KSPIN_LOCK v25; // rcx
  KIRQL v26; // r8
  _QWORD *v27; // rcx
  KSPIN_LOCK v28; // rdx
  __int64 v29; // rdx
  _QWORD *v30; // r13
  __int64 *v31; // r15
  __int64 v32; // rcx
  _QWORD *v33; // rdx
  __int64 v34; // rcx
  void *ContiguousNodeMemory; // rax
  PHYSICAL_ADDRESS PhysicalAddress; // rax
  USHORT Count; // [rsp+40h] [rbp-78h] BYREF
  _QWORD *v38; // [rsp+48h] [rbp-70h]
  struct _GROUP_AFFINITY Affinity; // [rsp+50h] [rbp-68h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+60h] [rbp-58h] BYREF

  v4 = *((_DWORD *)a3 + 12) + 184;
  v38 = a4;
  Affinity = 0;
  PreviousAffinity = 0;
  if ( v4 < 0xB8 )
    return (unsigned int)-1073741811;
  v6 = (KSPIN_LOCK *)a1[1];
  v7 = a1[2];
  v8 = a1[3];
  v9 = v6[63];
  Pool2 = ExAllocatePool2(64, v4, 1650738254);
  v11 = (char *)Pool2;
  if ( !Pool2 )
  {
    v23 = -1073741670;
    goto LABEL_37;
  }
  v12 = *a3;
  *(_QWORD *)(Pool2 + 56) = v6;
  v13 = a3[1];
  *(_QWORD *)(Pool2 + 64) = v7;
  *(_OWORD *)(Pool2 + 112) = v12;
  v14 = a3[2];
  v15 = *((_DWORD *)a3 + 6);
  *(_OWORD *)(Pool2 + 128) = v13;
  v16 = 0;
  v17 = a3[3];
  *(_QWORD *)(Pool2 + 72) = v8;
  *(_OWORD *)(Pool2 + 144) = v14;
  *(_QWORD *)&v14 = *((_QWORD *)a3 + 8);
  *(_OWORD *)(Pool2 + 160) = v17;
  *(_QWORD *)(Pool2 + 176) = v14;
  *(_QWORD *)(Pool2 + 168) = Pool2 + 184;
  HighestNodeNumber = KeQueryHighestNodeNumber();
  if ( v15 != 0x80000000 )
  {
    if ( v15 > HighestNodeNumber )
    {
      v15 = 0x80000000;
    }
    else
    {
      Count = 0;
      KeQueryNodeActiveAffinity(v15, &Affinity, &Count);
      if ( Count )
      {
        v16 = 1;
        KeSetSystemGroupAffinityThread(&Affinity, &PreviousAffinity);
      }
    }
  }
  if ( !*((_DWORD *)a3 + 2) || v7 || (v33 = *(_QWORD **)(v8 + 72)) == 0 || !v33[97] )
  {
    v20 = (__int64 (__fastcall *)(KSPIN_LOCK, __int128 *, char *))v6[450];
    if ( v20 )
    {
      *((_QWORD *)v11 + 10) = v6[451];
      v25 = v6[452];
      *((_QWORD *)v11 + 11) = v25;
      v23 = v20(v25, a3, v11 + 96);
      if ( v23 < 0 )
        goto LABEL_15;
      if ( (*((_DWORD *)a3 + 1) & 1) == 0 || **((_DWORD **)a3 + 7) <= 1u )
      {
        memmove(*((void **)v11 + 21), *((const void **)a3 + 7), *((unsigned int *)a3 + 12));
        *((_DWORD *)v11 + 12) |= 8u;
        goto LABEL_15;
      }
      ((void (__fastcall *)(_QWORD, _QWORD))v6[451])(*((_QWORD *)v11 + 11), *((_QWORD *)v11 + 12));
    }
    else
    {
      if ( v9 )
      {
        v21 = *(_QWORD *)(v9 + 40);
        if ( ndisDmaUseNumaAwareAllocator && (*(_DWORD *)(v9 + 64) & 2) != 0 )
        {
          v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, char *, char, _DWORD))(*(_QWORD *)(v21 + 8) + 152LL))(
                  v21,
                  0,
                  *((unsigned int *)a3 + 8),
                  v11 + 104,
                  1,
                  *((_DWORD *)a3 + 6));
        }
        else
        {
          LOBYTE(v19) = 1;
          v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *, __int64))(*(_QWORD *)(v21 + 8) + 16LL))(
                  v21,
                  *((unsigned int *)a3 + 8),
                  v11 + 104,
                  v19);
        }
        *((_QWORD *)a3 + 5) = v22;
        if ( !v22 )
          goto LABEL_41;
        _InterlockedIncrement((volatile signed __int32 *)(v9 + 88));
        *((_DWORD *)v11 + 12) |= 1u;
LABEL_14:
        v23 = 0;
        goto LABEL_15;
      }
      ContiguousNodeMemory = (void *)MmAllocateContiguousNodeMemory(*((unsigned int *)a3 + 8), 0, -1, 0, 4, v15);
      *((_QWORD *)a3 + 5) = ContiguousNodeMemory;
      if ( ContiguousNodeMemory )
      {
        PhysicalAddress = MmGetPhysicalAddress(ContiguousNodeMemory);
        *((_DWORD *)v11 + 12) |= 2u;
        *((PHYSICAL_ADDRESS *)v11 + 13) = PhysicalAddress;
        goto LABEL_14;
      }
    }
LABEL_41:
    v23 = -1073741670;
    goto LABEL_15;
  }
  *((_QWORD *)v11 + 10) = v33[98];
  v34 = v33[99];
  *((_QWORD *)v11 + 11) = v34;
  v23 = ((__int64 (__fastcall *)(__int64, __int128 *, char *))v33[97])(v34, a3, v11 + 96);
  if ( v23 >= 0 )
  {
    if ( (*((_DWORD *)a3 + 1) & 1) != 0 && **((_DWORD **)a3 + 7) > 1u )
    {
      (*((void (__fastcall **)(_QWORD, _QWORD))v11 + 10))(*((_QWORD *)v11 + 11), *((_QWORD *)v11 + 12));
      goto LABEL_41;
    }
    memmove(*((void **)v11 + 21), *((const void **)a3 + 7), *((unsigned int *)a3 + 12));
    *((_DWORD *)v11 + 12) |= 4u;
  }
LABEL_15:
  if ( v16 )
    KeRevertToUserGroupAffinityThread(&PreviousAffinity);
  if ( v23 >= 0 )
  {
    *((_QWORD *)v11 + 19) = *((_QWORD *)a3 + 5);
    if ( (*((_DWORD *)v11 + 12) & 3) != 0 )
    {
      if ( *((_DWORD *)a3 + 12) >= 0x28u )
      {
        **((_DWORD **)a3 + 7) = 1;
        *(_QWORD *)(*((_QWORD *)a3 + 7) + 16LL) = *((_QWORD *)v11 + 13);
        *(_DWORD *)(*((_QWORD *)a3 + 7) + 24LL) = *((_DWORD *)a3 + 8);
      }
      *((_QWORD *)a3 + 2) = 0;
    }
    _InterlockedAdd64(&qword_140122EA8, *((unsigned int *)a3 + 8));
    v26 = KeAcquireSpinLockRaiseToDpc(v6 + 12);
    v6[65] = (KSPIN_LOCK)KeGetCurrentThread();
    v27 = v6 + 448;
    v28 = v6[448];
    if ( *(KSPIN_LOCK **)(v28 + 8) == v6 + 448 )
    {
      *(_QWORD *)v11 = v28;
      *((_QWORD *)v11 + 1) = v27;
      *(_QWORD *)(v28 + 8) = v11;
      *v27 = v11;
      if ( v7 )
      {
        v31 = (__int64 *)(v7 + 760);
        v32 = *v31;
        if ( *(__int64 **)(*v31 + 8) != v31 )
          goto LABEL_29;
        *((_QWORD *)v11 + 2) = v32;
        *((_QWORD *)v11 + 3) = v31;
        *(_QWORD *)(v32 + 8) = v11 + 16;
        *v31 = (__int64)(v11 + 16);
      }
      v29 = *(_QWORD *)(v8 + 88);
      v30 = (_QWORD *)(v8 + 88);
      if ( *(_QWORD **)(v29 + 8) == v30 )
      {
        *((_QWORD *)v11 + 4) = v29;
        *((_QWORD *)v11 + 5) = v30;
        *(_QWORD *)(v29 + 8) = v11 + 32;
        *v30 = v11 + 32;
        v6[65] = 0;
        KeReleaseSpinLock(v6 + 12, v26);
        *v38 = v11;
        return (unsigned int)v23;
      }
    }
LABEL_29:
    __fastfail(3u);
  }
  ExFreePoolWithTag(v11, 0);
  if ( v23 == -1073741670 )
LABEL_37:
    _InterlockedAdd64(&qword_140122EB0, *((unsigned int *)a3 + 8));
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x140067dc0  push    rbx
0x140067dc2  push    rbp
0x140067dc3  push    rsi
0x140067dc4  push    rdi
0x140067dc5  push    r13
0x140067dc7  push    r15
0x140067dc9  sub     rsp, 88h
0x140067dd0  mov     rax, cs:__security_cookie
0x140067dd7  xor     rax, rsp
0x140067dda  mov     [rsp+0B8h+var_48], rax
0x140067ddf  mov     eax, [r8+30h]
0x140067de3  xorps   xmm0, xmm0
0x140067de6  add     eax, 0B8h
0x140067deb  mov     [rsp+0B8h+var_70], r9
0x140067df0  xorps   xmm1, xmm1
0x140067df3  mov     rsi, r8
0x140067df6  movups  xmmword ptr [rsp+0B8h+Affinity.Mask], xmm0
0x140067dfb  movups  xmmword ptr [rsp+0B8h+PreviousAffinity.Mask], xmm1
0x140067e00  cmp     eax, 0B8h
0x140067e05  jb      loc_140068134
0x140067e0b  mov     rbp, [rcx+8]
0x140067e0f  mov     r8d, 6264444Eh
0x140067e15  mov     r15, [rcx+10h]
0x140067e19  mov     r13, [rcx+18h]
0x140067e1d  mov     ecx, 40h ; '@'
0x140067e22  mov     edx, eax
0x140067e24  mov     rdi, [rbp+1F8h]
0x140067e2b  call    cs:__imp_ExAllocatePool2
0x140067e32  nop     dword ptr [rax+rax+00h]
0x140067e37  mov     rbx, rax
0x140067e3a  test    rax, rax
0x140067e3d  jz      loc_14006813E
0x140067e43  movups  xmm0, xmmword ptr [rsi]
0x140067e46  mov     [rax+38h], rbp
0x140067e4a  movups  xmm1, xmmword ptr [rsi+10h]
0x140067e4e  mov     [rax+40h], r15
0x140067e52  movups  xmmword ptr [rax+70h], xmm0
0x140067e56  mov     [rsp+0B8h+arg_8], r12
0x140067e5e  movups  xmm0, xmmword ptr [rsi+20h]
0x140067e62  mov     r12d, [rsi+18h]
0x140067e66  movups  xmmword ptr [rax+80h], xmm1
0x140067e6d  mov     [rsp+0B8h+var_38], r14
0x140067e75  xor     r14b, r14b
0x140067e78  movups  xmm1, xmmword ptr [rsi+30h]
0x140067e7c  mov     [rbx+48h], r13
0x140067e80  movups  xmmword ptr [rax+90h], xmm0
0x140067e87  movsd   xmm0, qword ptr [rsi+40h]
0x140067e8c  movups  xmmword ptr [rax+0A0h], xmm1
0x140067e93  movsd   qword ptr [rax+0B0h], xmm0
0x140067e9b  add     rax, 0B8h
0x140067ea1  mov     [rbx+0A8h], rax
0x140067ea8  call    cs:__imp_KeQueryHighestNodeNumber
0x140067eaf  nop     dword ptr [rax+rax+00h]
0x140067eb4  cmp     r12d, 80000000h
0x140067ebb  jz      short loc_140067F0B
0x140067ebd  movzx   eax, ax
0x140067ec0  cmp     r12d, eax
0x140067ec3  ja      loc_140068153
0x140067ec9  xor     eax, eax
0x140067ecb  lea     r8, [rsp+0B8h+Count]; Count
0x140067ed0  movzx   ecx, r12w; NodeNumber
0x140067ed4  mov     [rsp+0B8h+Count], ax
0x140067ed9  lea     rdx, [rsp+0B8h+Affinity]; Affinity
0x140067ede  call    cs:__imp_KeQueryNodeActiveAffinity
0x140067ee5  nop     dword ptr [rax+rax+00h]
0x140067eea  cmp     [rsp+0B8h+Count], 0
0x140067ef0  jbe     short loc_140067F0B
0x140067ef2  lea     rdx, [rsp+0B8h+PreviousAffinity]; PreviousAffinity
0x140067ef7  mov     r14b, 1
0x140067efa  lea     rcx, [rsp+0B8h+Affinity]; Affinity
0x140067eff  call    cs:__imp_KeSetSystemGroupAffinityThread
0x140067f06  nop     dword ptr [rax+rax+00h]
0x140067f0b  cmp     dword ptr [rsi+8], 0
0x140067f0f  jnz     loc_1400F27FA
0x140067f15  mov     rax, [rbp+0E10h]
0x140067f1c  test    rax, rax
0x140067f1f  jnz     loc_140067FDA
0x140067f25  test    rdi, rdi
0x140067f28  jz      loc_1400F28B2
0x140067f2e  movzx   eax, cs:?ndisDmaUseNumaAwareAllocator@@3EA; uchar ndisDmaUseNumaAwareAllocator
0x140067f35  mov     rcx, [rdi+28h]
0x140067f39  test    al, al
0x140067f3b  jnz     loc_14006815E
0x140067f41  mov     rax, [rcx+8]
0x140067f45  lea     r8, [rbx+68h]
0x140067f49  mov     edx, [rsi+20h]
0x140067f4c  mov     r9b, 1
0x140067f4f  mov     rax, [rax+10h]
0x140067f53  call    _guard_dispatch_icall
0x140067f58  mov     [rsi+28h], rax
0x140067f5c  test    rax, rax
0x140067f5f  jz      loc_140068194
0x140067f65  lock inc dword ptr [rdi+58h]
0x140067f69  or      dword ptr [rbx+30h], 1
0x140067f6d  xor     edi, edi
0x140067f6f  mov     r12, [rsp+0B8h+arg_8]
0x140067f77  test    r14b, r14b
0x140067f7a  mov     r14, [rsp+0B8h+var_38]
0x140067f82  jz      short loc_140067F95
0x140067f84  lea     rcx, [rsp+0B8h+PreviousAffinity]; PreviousAffinity
0x140067f89  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x140067f90  nop     dword ptr [rax+rax+00h]
0x140067f95  test    edi, edi
0x140067f97  jns     loc_14006802A
0x140067f9d  xor     edx, edx; Tag
0x140067f9f  mov     rcx, rbx; P
0x140067fa2  call    cs:__imp_ExFreePoolWithTag
0x140067fa9  nop     dword ptr [rax+rax+00h]
0x140067fae  cmp     edi, 0C000009Ah
0x140067fb4  jz      loc_140068143
0x140067fba  mov     eax, edi
0x140067fbc  mov     rcx, [rsp+0B8h+var_48]
0x140067fc1  xor     rcx, rsp; StackCookie
0x140067fc4  call    __security_check_cookie
0x140067fc9  add     rsp, 88h
0x140067fd0  pop     r15
0x140067fd2  pop     r13
0x140067fd4  pop     rdi
0x140067fd5  pop     rsi
0x140067fd6  pop     rbp
0x140067fd7  pop     rbx
0x140067fd8  retn
0x140067fda  mov     rcx, [rbp+0E18h]
0x140067fe1  lea     r8, [rbx+60h]
0x140067fe5  mov     [rbx+50h], rcx
0x140067fe9  mov     rdx, rsi
0x140067fec  mov     rcx, [rbp+0E20h]
0x140067ff3  mov     [rbx+58h], rcx
0x140067ff7  call    _guard_dispatch_icall
0x140067ffc  mov     edi, eax
0x140067ffe  test    eax, eax
0x140068000  js      loc_140067F6F
0x140068006  mov     eax, [rsi+4]
0x140068009  test    al, 1
0x14006800b  jz      loc_1400F2895
0x140068011  mov     rax, [rsi+38h]
0x140068015  cmp     dword ptr [rax], 1
0x140068018  jbe     loc_1400F2895
0x14006801e  mov     rax, [rbp+0E18h]
0x140068025  jmp     loc_1400F2865
0x14006802a  mov     rax, [rsi+28h]
0x14006802e  mov     [rbx+98h], rax
0x140068035  mov     eax, [rbx+30h]
0x140068038  test    al, 3
0x14006803a  jz      short loc_14006806A
0x14006803c  cmp     dword ptr [rsi+30h], 28h ; '('
0x140068040  jb      short loc_140068062
0x140068042  mov     rax, [rsi+38h]
0x140068046  mov     dword ptr [rax], 1
0x14006804c  mov     rcx, [rsi+38h]
0x140068050  mov     rax, [rbx+68h]
0x140068054  mov     [rcx+10h], rax
0x140068058  mov     rcx, [rsi+38h]
0x14006805c  mov     eax, [rsi+20h]
0x14006805f  mov     [rcx+18h], eax
0x140068062  mov     qword ptr [rsi+10h], 0
0x14006806a  mov     eax, [rsi+20h]
0x14006806d  lock add cs:qword_140122EA8, rax
0x140068075  lea     rcx, [rbp+60h]; SpinLock
0x140068079  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140068080  nop     dword ptr [rax+rax+00h]
0x140068085  mov     rcx, gs:188h
0x14006808e  movzx   r8d, al
0x140068092  mov     [rbp+208h], rcx
0x140068099  lea     rcx, [rbp+0E00h]
0x1400680a0  mov     rdx, [rcx]
0x1400680a3  cmp     [rdx+8], rcx
0x1400680a7  jz      short loc_1400680B0
0x1400680a9  mov     ecx, 3
0x1400680ae  int     29h; Win8: RtlFailFast(ecx)
0x1400680b0  mov     [rbx], rdx
0x1400680b3  mov     [rbx+8], rcx
0x1400680b7  mov     [rdx+8], rbx
0x1400680bb  mov     [rcx], rbx
0x1400680be  test    r15, r15
0x1400680c1  jnz     short loc_140068110
0x1400680c3  mov     rdx, [r13+58h]
0x1400680c7  add     r13, 58h ; 'X'
0x1400680cb  cmp     [rdx+8], r13
0x1400680cf  jnz     short loc_1400680A9
0x1400680d1  lea     rax, [rbx+20h]
0x1400680d5  mov     [rax], rdx
0x1400680d8  lea     rcx, [rbp+60h]; SpinLock
0x1400680dc  mov     [rax+8], r13
0x1400680e0  mov     [rdx+8], rax
0x1400680e4  movzx   edx, r8b; NewIrql
0x1400680e8  mov     [r13+0], rax
0x1400680ec  mov     qword ptr [rbp+208h], 0
0x1400680f7  call    cs:__imp_KeReleaseSpinLock
0x1400680fe  nop     dword ptr [rax+rax+00h]
0x140068103  mov     rax, [rsp+0B8h+var_70]
0x140068108  mov     [rax], rbx
0x14006810b  jmp     loc_140067FBA
0x140068110  add     r15, 2F8h
0x140068117  mov     rcx, [r15]
0x14006811a  cmp     [rcx+8], r15
0x14006811e  jnz     short loc_1400680A9
0x140068120  lea     rax, [rbx+10h]
0x140068124  mov     [rax], rcx
0x140068127  mov     [rax+8], r15
0x14006812b  mov     [rcx+8], rax
0x14006812f  mov     [r15], rax
0x140068132  jmp     short loc_1400680C3
0x140068134  mov     edi, 0C000000Dh
0x140068139  jmp     loc_140067FBA
0x14006813e  mov     edi, 0C000009Ah
0x140068143  mov     eax, [rsi+20h]
0x140068146  lock add cs:qword_140122EB0, rax
0x14006814e  jmp     loc_140067FBA
0x140068153  mov     r12d, 80000000h
0x140068159  jmp     loc_140067F0B
0x14006815e  mov     eax, [rdi+40h]
0x140068161  test    al, 2
0x140068163  jz      loc_140067F41
0x140068169  mov     edx, [rsi+18h]
0x14006816c  lea     r9, [rbx+68h]
0x140068170  mov     rax, [rcx+8]
0x140068174  mov     r8d, [rsi+20h]
0x140068178  mov     [rsp+0B8h+var_90], edx
0x14006817c  xor     edx, edx
0x14006817e  mov     byte ptr [rsp+0B8h+var_98], 1
0x140068183  mov     rax, [rax+98h]
0x14006818a  call    _guard_dispatch_icall
0x14006818f  jmp     loc_140067F58
0x140068194  mov     edi, 0C000009Ah
0x140068199  jmp     loc_140067F6F
0x1400f27fa  test    r15, r15
0x1400f27fd  jnz     loc_140067F15
0x1400f2803  mov     rdx, [r13+48h]
0x1400f2807  test    rdx, rdx
0x1400f280a  jz      loc_140067F15
0x1400f2810  cmp     [rdx+308h], r15
0x1400f2817  jz      loc_140067F15
0x1400f281d  mov     rax, [rdx+310h]
0x1400f2824  lea     r8, [rbx+60h]
0x1400f2828  mov     [rbx+50h], rax
0x1400f282c  mov     rcx, [rdx+318h]
0x1400f2833  mov     [rbx+58h], rcx
0x1400f2837  mov     rax, [rdx+308h]
0x1400f283e  mov     rdx, rsi
0x1400f2841  call    _guard_dispatch_icall
0x1400f2846  mov     edi, eax
0x1400f2848  test    eax, eax
0x1400f284a  js      loc_140067F6F
0x1400f2850  mov     ecx, [rsi+4]
0x1400f2853  test    cl, 1
0x1400f2856  jz      short loc_1400F2878
0x1400f2858  mov     rcx, [rsi+38h]
0x1400f285c  cmp     dword ptr [rcx], 1
0x1400f285f  jbe     short loc_1400F2878
0x1400f2861  mov     rax, [rbx+50h]
0x1400f2865  mov     rdx, [rbx+60h]
0x1400f2869  mov     rcx, [rbx+58h]
0x1400f286d  call    _guard_dispatch_icall
0x1400f2872  nop
0x1400f2873  jmp     loc_140068194
0x1400f2878  mov     r8d, [rsi+30h]; Size
0x1400f287c  mov     rdx, [rsi+38h]; Src
0x1400f2880  mov     rcx, [rbx+0A8h]; void *
0x1400f2887  call    memmove
0x1400f288c  or      dword ptr [rbx+30h], 4
0x1400f2890  jmp     loc_140067F6F
0x1400f2895  mov     r8d, [rsi+30h]; Size
0x1400f2899  mov     rdx, [rsi+38h]; Src
0x1400f289d  mov     rcx, [rbx+0A8h]; void *
0x1400f28a4  call    memmove
0x1400f28a9  or      dword ptr [rbx+30h], 8
0x1400f28ad  jmp     loc_140067F6F
0x1400f28b2  mov     rdx, cs:qword_140101C90
0x1400f28b9  mov     ecx, [rsi+20h]
0x1400f28bc  mov     r9, rdx
0x1400f28bf  mov     r8, cs:qword_140101C98
0x1400f28c6  mov     [rsp+0B8h+var_90], r12d
0x1400f28cb  mov     [rsp+0B8h+var_98], 4
0x1400f28d3  call    cs:__imp_MmAllocateContiguousNodeMemory
0x1400f28da  nop     dword ptr [rax+rax+00h]
0x1400f28df  mov     [rsi+28h], rax
0x1400f28e3  test    rax, rax
0x1400f28e6  jz      loc_140068194
0x1400f28ec  mov     rcx, rax; BaseAddress
0x1400f28ef  call    cs:__imp_MmGetPhysicalAddress
0x1400f28f6  nop     dword ptr [rax+rax+00h]
0x1400f28fb  or      dword ptr [rbx+30h], 2
0x1400f28ff  mov     [rbx+68h], rax
0x1400f2903  jmp     loc_140067F6D
```
