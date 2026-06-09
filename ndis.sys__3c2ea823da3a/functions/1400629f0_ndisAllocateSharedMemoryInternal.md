# ndisAllocateSharedMemoryInternal

- ea: `0x1400629f0`
- end: `0x140062dce`
- name: `ndisAllocateSharedMemoryInternal`
- size: `990`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140062670`

## callees

- `0x1400629f0`
- `0x1400e6160`
- `0x1400e6240`
- `0x1400e62c0`

## import_xrefs

- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140062b2f`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140062b2f`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140062bb9`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140062bb9`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140062ad8`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140062ad8`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x140062b0e`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x140062b0e`
- `ntoskrnl!MmAllocateContiguousNodeMemory` at `0x1400ed637`
- `ntoskrnl!MmAllocateContiguousNodeMemory` at `0x1400ed637`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062bd2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062bd2`
- `ntoskrnl!ExAllocatePool2` at `0x140062a5b`
- `ntoskrnl!ExAllocatePool2` at `0x140062a5b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140062d27`
- `ntoskrnl!KeReleaseSpinLock` at `0x140062d27`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140062ca9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140062ca9`
- `ntoskrnl!MmGetPhysicalAddress` at `0x1400ed653`
- `ntoskrnl!MmGetPhysicalAddress` at `0x1400ed653`

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
    _InterlockedAdd64(&qword_14011CEA8, *((unsigned int *)a3 + 8));
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
    _InterlockedAdd64(&qword_14011CEB0, *((unsigned int *)a3 + 8));
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x1400629f0  push    rbx
0x1400629f2  push    rbp
0x1400629f3  push    rsi
0x1400629f4  push    rdi
0x1400629f5  push    r13
0x1400629f7  push    r15
0x1400629f9  sub     rsp, 88h
0x140062a00  mov     rax, cs:__security_cookie
0x140062a07  xor     rax, rsp
0x140062a0a  mov     [rsp+0B8h+var_48], rax
0x140062a0f  mov     eax, [r8+30h]
0x140062a13  xorps   xmm0, xmm0
0x140062a16  add     eax, 0B8h
0x140062a1b  mov     [rsp+0B8h+var_70], r9
0x140062a20  xorps   xmm1, xmm1
0x140062a23  mov     rsi, r8
0x140062a26  movups  xmmword ptr [rsp+0B8h+Affinity.Mask], xmm0
0x140062a2b  movups  xmmword ptr [rsp+0B8h+PreviousAffinity.Mask], xmm1
0x140062a30  cmp     eax, 0B8h
0x140062a35  jb      loc_140062D64
0x140062a3b  mov     rbp, [rcx+8]
0x140062a3f  mov     r8d, 6264444Eh
0x140062a45  mov     r15, [rcx+10h]
0x140062a49  mov     r13, [rcx+18h]
0x140062a4d  mov     ecx, 40h ; '@'
0x140062a52  mov     edx, eax
0x140062a54  mov     rdi, [rbp+1F8h]
0x140062a5b  call    cs:__imp_ExAllocatePool2
0x140062a62  nop     dword ptr [rax+rax+00h]
0x140062a67  mov     rbx, rax
0x140062a6a  test    rax, rax
0x140062a6d  jz      loc_140062D6E
0x140062a73  movups  xmm0, xmmword ptr [rsi]
0x140062a76  mov     [rax+38h], rbp
0x140062a7a  movups  xmm1, xmmword ptr [rsi+10h]
0x140062a7e  mov     [rax+40h], r15
0x140062a82  movups  xmmword ptr [rax+70h], xmm0
0x140062a86  mov     [rsp+0B8h+arg_8], r12
0x140062a8e  movups  xmm0, xmmword ptr [rsi+20h]
0x140062a92  mov     r12d, [rsi+18h]
0x140062a96  movups  xmmword ptr [rax+80h], xmm1
0x140062a9d  mov     [rsp+0B8h+var_38], r14
0x140062aa5  xor     r14b, r14b
0x140062aa8  movups  xmm1, xmmword ptr [rsi+30h]
0x140062aac  mov     [rbx+48h], r13
0x140062ab0  movups  xmmword ptr [rax+90h], xmm0
0x140062ab7  movsd   xmm0, qword ptr [rsi+40h]
0x140062abc  movups  xmmword ptr [rax+0A0h], xmm1
0x140062ac3  movsd   qword ptr [rax+0B0h], xmm0
0x140062acb  add     rax, 0B8h
0x140062ad1  mov     [rbx+0A8h], rax
0x140062ad8  call    cs:__imp_KeQueryHighestNodeNumber
0x140062adf  nop     dword ptr [rax+rax+00h]
0x140062ae4  cmp     r12d, 80000000h
0x140062aeb  jz      short loc_140062B3B
0x140062aed  movzx   eax, ax
0x140062af0  cmp     r12d, eax
0x140062af3  ja      loc_140062D83
0x140062af9  xor     eax, eax
0x140062afb  lea     r8, [rsp+0B8h+Count]; Count
0x140062b00  movzx   ecx, r12w; NodeNumber
0x140062b04  mov     [rsp+0B8h+Count], ax
0x140062b09  lea     rdx, [rsp+0B8h+Affinity]; Affinity
0x140062b0e  call    cs:__imp_KeQueryNodeActiveAffinity
0x140062b15  nop     dword ptr [rax+rax+00h]
0x140062b1a  cmp     [rsp+0B8h+Count], 0
0x140062b20  jbe     short loc_140062B3B
0x140062b22  lea     rdx, [rsp+0B8h+PreviousAffinity]; PreviousAffinity
0x140062b27  mov     r14b, 1
0x140062b2a  lea     rcx, [rsp+0B8h+Affinity]; Affinity
0x140062b2f  call    cs:__imp_KeSetSystemGroupAffinityThread
0x140062b36  nop     dword ptr [rax+rax+00h]
0x140062b3b  cmp     dword ptr [rsi+8], 0
0x140062b3f  jnz     loc_1400ED55E
0x140062b45  mov     rax, [rbp+0E10h]
0x140062b4c  test    rax, rax
0x140062b4f  jnz     loc_140062C0A
0x140062b55  test    rdi, rdi
0x140062b58  jz      loc_1400ED616
0x140062b5e  movzx   eax, cs:?ndisDmaUseNumaAwareAllocator@@3EA; uchar ndisDmaUseNumaAwareAllocator
0x140062b65  mov     rcx, [rdi+28h]
0x140062b69  test    al, al
0x140062b6b  jnz     loc_140062D8E
0x140062b71  mov     rax, [rcx+8]
0x140062b75  lea     r8, [rbx+68h]
0x140062b79  mov     edx, [rsi+20h]
0x140062b7c  mov     r9b, 1
0x140062b7f  mov     rax, [rax+10h]
0x140062b83  call    _guard_dispatch_icall
0x140062b88  mov     [rsi+28h], rax
0x140062b8c  test    rax, rax
0x140062b8f  jz      loc_140062DC4
0x140062b95  lock inc dword ptr [rdi+58h]
0x140062b99  or      dword ptr [rbx+30h], 1
0x140062b9d  xor     edi, edi
0x140062b9f  mov     r12, [rsp+0B8h+arg_8]
0x140062ba7  test    r14b, r14b
0x140062baa  mov     r14, [rsp+0B8h+var_38]
0x140062bb2  jz      short loc_140062BC5
0x140062bb4  lea     rcx, [rsp+0B8h+PreviousAffinity]; PreviousAffinity
0x140062bb9  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x140062bc0  nop     dword ptr [rax+rax+00h]
0x140062bc5  test    edi, edi
0x140062bc7  jns     loc_140062C5A
0x140062bcd  xor     edx, edx; Tag
0x140062bcf  mov     rcx, rbx; P
0x140062bd2  call    cs:__imp_ExFreePoolWithTag
0x140062bd9  nop     dword ptr [rax+rax+00h]
0x140062bde  cmp     edi, 0C000009Ah
0x140062be4  jz      loc_140062D73
0x140062bea  mov     eax, edi
0x140062bec  mov     rcx, [rsp+0B8h+var_48]
0x140062bf1  xor     rcx, rsp; StackCookie
0x140062bf4  call    __security_check_cookie
0x140062bf9  add     rsp, 88h
0x140062c00  pop     r15
0x140062c02  pop     r13
0x140062c04  pop     rdi
0x140062c05  pop     rsi
0x140062c06  pop     rbp
0x140062c07  pop     rbx
0x140062c08  retn
0x140062c0a  mov     rcx, [rbp+0E18h]
0x140062c11  lea     r8, [rbx+60h]
0x140062c15  mov     [rbx+50h], rcx
0x140062c19  mov     rdx, rsi
0x140062c1c  mov     rcx, [rbp+0E20h]
0x140062c23  mov     [rbx+58h], rcx
0x140062c27  call    _guard_dispatch_icall
0x140062c2c  mov     edi, eax
0x140062c2e  test    eax, eax
0x140062c30  js      loc_140062B9F
0x140062c36  mov     eax, [rsi+4]
0x140062c39  test    al, 1
0x140062c3b  jz      loc_1400ED5F9
0x140062c41  mov     rax, [rsi+38h]
0x140062c45  cmp     dword ptr [rax], 1
0x140062c48  jbe     loc_1400ED5F9
0x140062c4e  mov     rax, [rbp+0E18h]
0x140062c55  jmp     loc_1400ED5C9
0x140062c5a  mov     rax, [rsi+28h]
0x140062c5e  mov     [rbx+98h], rax
0x140062c65  mov     eax, [rbx+30h]
0x140062c68  test    al, 3
0x140062c6a  jz      short loc_140062C9A
0x140062c6c  cmp     dword ptr [rsi+30h], 28h ; '('
0x140062c70  jb      short loc_140062C92
0x140062c72  mov     rax, [rsi+38h]
0x140062c76  mov     dword ptr [rax], 1
0x140062c7c  mov     rcx, [rsi+38h]
0x140062c80  mov     rax, [rbx+68h]
0x140062c84  mov     [rcx+10h], rax
0x140062c88  mov     rcx, [rsi+38h]
0x140062c8c  mov     eax, [rsi+20h]
0x140062c8f  mov     [rcx+18h], eax
0x140062c92  mov     qword ptr [rsi+10h], 0
0x140062c9a  mov     eax, [rsi+20h]
0x140062c9d  lock add cs:qword_14011CEA8, rax
0x140062ca5  lea     rcx, [rbp+60h]; SpinLock
0x140062ca9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140062cb0  nop     dword ptr [rax+rax+00h]
0x140062cb5  mov     rcx, gs:188h
0x140062cbe  movzx   r8d, al
0x140062cc2  mov     [rbp+208h], rcx
0x140062cc9  lea     rcx, [rbp+0E00h]
0x140062cd0  mov     rdx, [rcx]
0x140062cd3  cmp     [rdx+8], rcx
0x140062cd7  jz      short loc_140062CE0
0x140062cd9  mov     ecx, 3
0x140062cde  int     29h; Win8: RtlFailFast(ecx)
0x140062ce0  mov     [rbx], rdx
0x140062ce3  mov     [rbx+8], rcx
0x140062ce7  mov     [rdx+8], rbx
0x140062ceb  mov     [rcx], rbx
0x140062cee  test    r15, r15
0x140062cf1  jnz     short loc_140062D40
0x140062cf3  mov     rdx, [r13+58h]
0x140062cf7  add     r13, 58h ; 'X'
0x140062cfb  cmp     [rdx+8], r13
0x140062cff  jnz     short loc_140062CD9
0x140062d01  lea     rax, [rbx+20h]
0x140062d05  mov     [rax], rdx
0x140062d08  lea     rcx, [rbp+60h]; SpinLock
0x140062d0c  mov     [rax+8], r13
0x140062d10  mov     [rdx+8], rax
0x140062d14  movzx   edx, r8b; NewIrql
0x140062d18  mov     [r13+0], rax
0x140062d1c  mov     qword ptr [rbp+208h], 0
0x140062d27  call    cs:__imp_KeReleaseSpinLock
0x140062d2e  nop     dword ptr [rax+rax+00h]
0x140062d33  mov     rax, [rsp+0B8h+var_70]
0x140062d38  mov     [rax], rbx
0x140062d3b  jmp     loc_140062BEA
0x140062d40  add     r15, 2F8h
0x140062d47  mov     rcx, [r15]
0x140062d4a  cmp     [rcx+8], r15
0x140062d4e  jnz     short loc_140062CD9
0x140062d50  lea     rax, [rbx+10h]
0x140062d54  mov     [rax], rcx
0x140062d57  mov     [rax+8], r15
0x140062d5b  mov     [rcx+8], rax
0x140062d5f  mov     [r15], rax
0x140062d62  jmp     short loc_140062CF3
0x140062d64  mov     edi, 0C000000Dh
0x140062d69  jmp     loc_140062BEA
0x140062d6e  mov     edi, 0C000009Ah
0x140062d73  mov     eax, [rsi+20h]
0x140062d76  lock add cs:qword_14011CEB0, rax
0x140062d7e  jmp     loc_140062BEA
0x140062d83  mov     r12d, 80000000h
0x140062d89  jmp     loc_140062B3B
0x140062d8e  mov     eax, [rdi+40h]
0x140062d91  test    al, 2
0x140062d93  jz      loc_140062B71
0x140062d99  mov     edx, [rsi+18h]
0x140062d9c  lea     r9, [rbx+68h]
0x140062da0  mov     rax, [rcx+8]
0x140062da4  mov     r8d, [rsi+20h]
0x140062da8  mov     [rsp+0B8h+var_90], edx
0x140062dac  xor     edx, edx
0x140062dae  mov     byte ptr [rsp+0B8h+var_98], 1
0x140062db3  mov     rax, [rax+98h]
0x140062dba  call    _guard_dispatch_icall
0x140062dbf  jmp     loc_140062B88
0x140062dc4  mov     edi, 0C000009Ah
0x140062dc9  jmp     loc_140062B9F
0x1400ed55e  test    r15, r15
0x1400ed561  jnz     loc_140062B45
0x1400ed567  mov     rdx, [r13+48h]
0x1400ed56b  test    rdx, rdx
0x1400ed56e  jz      loc_140062B45
0x1400ed574  cmp     [rdx+308h], r15
0x1400ed57b  jz      loc_140062B45
0x1400ed581  mov     rax, [rdx+310h]
0x1400ed588  lea     r8, [rbx+60h]
0x1400ed58c  mov     [rbx+50h], rax
0x1400ed590  mov     rcx, [rdx+318h]
0x1400ed597  mov     [rbx+58h], rcx
0x1400ed59b  mov     rax, [rdx+308h]
0x1400ed5a2  mov     rdx, rsi
0x1400ed5a5  call    _guard_dispatch_icall
0x1400ed5aa  mov     edi, eax
0x1400ed5ac  test    eax, eax
0x1400ed5ae  js      loc_140062B9F
0x1400ed5b4  mov     ecx, [rsi+4]
0x1400ed5b7  test    cl, 1
0x1400ed5ba  jz      short loc_1400ED5DC
0x1400ed5bc  mov     rcx, [rsi+38h]
0x1400ed5c0  cmp     dword ptr [rcx], 1
0x1400ed5c3  jbe     short loc_1400ED5DC
0x1400ed5c5  mov     rax, [rbx+50h]
0x1400ed5c9  mov     rdx, [rbx+60h]
0x1400ed5cd  mov     rcx, [rbx+58h]
0x1400ed5d1  call    _guard_dispatch_icall
0x1400ed5d6  nop
0x1400ed5d7  jmp     loc_140062DC4
0x1400ed5dc  mov     r8d, [rsi+30h]; Size
0x1400ed5e0  mov     rdx, [rsi+38h]; Src
0x1400ed5e4  mov     rcx, [rbx+0A8h]; void *
0x1400ed5eb  call    memmove
0x1400ed5f0  or      dword ptr [rbx+30h], 4
0x1400ed5f4  jmp     loc_140062B9F
0x1400ed5f9  mov     r8d, [rsi+30h]; Size
0x1400ed5fd  mov     rdx, [rsi+38h]; Src
0x1400ed601  mov     rcx, [rbx+0A8h]; void *
0x1400ed608  call    memmove
0x1400ed60d  or      dword ptr [rbx+30h], 8
0x1400ed611  jmp     loc_140062B9F
0x1400ed616  mov     rdx, cs:qword_1400FCC50
0x1400ed61d  mov     ecx, [rsi+20h]
0x1400ed620  mov     r9, rdx
0x1400ed623  mov     r8, cs:qword_1400FCC58
0x1400ed62a  mov     [rsp+0B8h+var_90], r12d
0x1400ed62f  mov     [rsp+0B8h+var_98], 4
0x1400ed637  call    cs:__imp_MmAllocateContiguousNodeMemory
0x1400ed63e  nop     dword ptr [rax+rax+00h]
0x1400ed643  mov     [rsi+28h], rax
0x1400ed647  test    rax, rax
0x1400ed64a  jz      loc_140062DC4
0x1400ed650  mov     rcx, rax; BaseAddress
0x1400ed653  call    cs:__imp_MmGetPhysicalAddress
0x1400ed65a  nop     dword ptr [rax+rax+00h]
0x1400ed65f  or      dword ptr [rbx+30h], 2
0x1400ed663  mov     [rbx+68h], rax
0x1400ed667  jmp     loc_140062B9D
```
