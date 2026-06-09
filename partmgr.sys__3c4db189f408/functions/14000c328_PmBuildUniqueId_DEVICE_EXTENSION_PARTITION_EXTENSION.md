# PmBuildUniqueId(_DEVICE_EXTENSION *,_PARTITION_EXTENSION *)

- ea: `0x14000c328`
- end: `0x14000c473`
- name: `?PmBuildUniqueId@@YAJPEAU_DEVICE_EXTENSION@@PEAU_PARTITION_EXTENSION@@@Z`
- size: `331`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _PARTITION_EXTENSION *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140007f70`
- `0x1400254c8`

## callees

- `0x14000ae88`
- `0x14000c328`
- `0x140011140`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c455`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c455`
- `ntoskrnl!ExAllocatePool2` at `0x14000c393`
- `ntoskrnl!ExAllocatePool2` at `0x14000c393`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c43f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c43f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c426`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c426`

## pseudocode

```c
__int64 __fastcall PmBuildUniqueId(struct _DEVICE_EXTENSION *a1, struct _PARTITION_EXTENSION *a2)
{
  unsigned int *v2; // r15
  __int64 v5; // rdx
  char *v6; // rbx
  int v7; // r14d
  __int64 Pool2; // rax
  _WORD *v9; // r12
  unsigned int v10; // esi
  __int64 v11; // r9
  __int128 v12; // xmm0
  KSPIN_LOCK *v13; // rbx
  KIRQL v14; // al
  void *v15; // rbp

  v2 = (unsigned int *)((char *)a1 + 516);
  if ( *((_DWORD *)a2 + 42) == 1 || (ScReadNoFence((unsigned int *)a1 + 129) & 0x2800) != 0 )
  {
    v7 = 24;
    v6 = (char *)a1 + 8;
  }
  else
  {
    v6 = (char *)a1 + 8;
    if ( (*(_DWORD *)(*((_QWORD *)a1 + 1) + 52LL) & 1) != 0 )
      v7 = *(unsigned __int16 *)(v5 + 48);
    else
      v7 = 12;
  }
  Pool2 = ExAllocatePool2(66, (unsigned int)(v7 + 2), 1178758480);
  v9 = (_WORD *)Pool2;
  if ( Pool2 )
  {
    v10 = 0;
    v11 = Pool2 + 2;
    if ( *((_DWORD *)a2 + 42) == 1 || (ScReadNoFence(v2) & 0x2800) != 0 )
    {
      v12 = *((_OWORD *)a2 + 4);
      *(_QWORD *)v11 = 0x3A44493A4F494D44LL;
      *(_OWORD *)(v11 + 8) = v12;
    }
    else if ( (*(_DWORD *)(*(_QWORD *)v6 + 52LL) & 1) != 0 )
    {
      memmove((void *)v11, *((const void **)a2 + 7), *((unsigned __int16 *)a2 + 24));
    }
    else
    {
      *(_DWORD *)v11 = *((_DWORD *)a2 + 52);
      *(_QWORD *)(v11 + 4) = *((_QWORD *)a2 + 22);
    }
    v13 = (KSPIN_LOCK *)((char *)a1 + 112);
    *v9 = v7;
    v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
    v15 = (void *)*((_QWORD *)a2 + 10);
    *((_QWORD *)a2 + 10) = v9;
    KeReleaseSpinLock(v13, v14);
    if ( v15 )
      ExFreePoolWithTag(v15, 0);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v10;
}

```

## disassembly

```asm
0x14000c328  push    rbx
0x14000c32a  push    rbp
0x14000c32b  push    rsi
0x14000c32c  push    rdi
0x14000c32d  push    r12
0x14000c32f  push    r14
0x14000c331  push    r15
0x14000c333  sub     rsp, 20h
0x14000c337  cmp     dword ptr [rdx+0A8h], 1
0x14000c33e  lea     r15, [rcx+204h]
0x14000c345  mov     rdi, rdx
0x14000c348  mov     rbp, rcx
0x14000c34b  jz      short loc_14000C37A
0x14000c34d  mov     rcx, r15; unsigned int *
0x14000c350  call    ?ScReadNoFence@@YAKPEAK@Z; ScReadNoFence(ulong *)
0x14000c355  test    eax, 2800h
0x14000c35a  jnz     short loc_14000C37A
0x14000c35c  lea     rbx, [rbp+8]
0x14000c360  mov     rax, [rbx]
0x14000c363  mov     ecx, [rax+34h]
0x14000c366  test    cl, 1
0x14000c369  jz      short loc_14000C372
0x14000c36b  movzx   r14d, word ptr [rdx+30h]
0x14000c370  jmp     short loc_14000C384
0x14000c372  mov     r14d, 0Ch
0x14000c378  jmp     short loc_14000C384
0x14000c37a  mov     r14d, 18h
0x14000c380  lea     rbx, [rbp+8]
0x14000c384  lea     edx, [r14+2]
0x14000c388  mov     ecx, 42h ; 'B'
0x14000c38d  mov     r8d, 46426D50h
0x14000c393  call    cs:__imp_ExAllocatePool2
0x14000c39a  nop     dword ptr [rax+rax+00h]
0x14000c39f  mov     r12, rax
0x14000c3a2  test    rax, rax
0x14000c3a5  jnz     short loc_14000C3B1
0x14000c3a7  mov     esi, 0C000009Ah
0x14000c3ac  jmp     loc_14000C461
0x14000c3b1  xor     esi, esi
0x14000c3b3  lea     r9, [rax+2]
0x14000c3b7  cmp     dword ptr [rdi+0A8h], 1
0x14000c3be  jz      short loc_14000C403
0x14000c3c0  mov     rcx, r15; unsigned int *
0x14000c3c3  call    ?ScReadNoFence@@YAKPEAK@Z; ScReadNoFence(ulong *)
0x14000c3c8  test    eax, 2800h
0x14000c3cd  jnz     short loc_14000C403
0x14000c3cf  mov     rax, [rbx]
0x14000c3d2  mov     edx, [rax+34h]
0x14000c3d5  test    dl, 1
0x14000c3d8  jz      short loc_14000C3ED
0x14000c3da  movzx   r8d, word ptr [rdi+30h]; Size
0x14000c3df  mov     rcx, r9; void *
0x14000c3e2  mov     rdx, [rdi+38h]; Src
0x14000c3e6  call    memmove
0x14000c3eb  jmp     short loc_14000C41A
0x14000c3ed  mov     eax, [rdi+0D0h]
0x14000c3f3  mov     [r9], eax
0x14000c3f6  mov     rax, [rdi+0B0h]
0x14000c3fd  mov     [r9+4], rax
0x14000c401  jmp     short loc_14000C41A
0x14000c403  movups  xmm0, xmmword ptr [rdi+40h]
0x14000c407  mov     rax, 3A44493A4F494D44h
0x14000c411  mov     [r9], rax
0x14000c414  movdqu  xmmword ptr [r9+8], xmm0
0x14000c41a  lea     rbx, [rbp+70h]
0x14000c41e  mov     [r12], r14w
0x14000c423  mov     rcx, rbx; SpinLock
0x14000c426  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000c42d  nop     dword ptr [rax+rax+00h]
0x14000c432  mov     rbp, [rdi+50h]
0x14000c436  mov     rcx, rbx; SpinLock
0x14000c439  mov     dl, al; NewIrql
0x14000c43b  mov     [rdi+50h], r12
0x14000c43f  call    cs:__imp_KeReleaseSpinLock
0x14000c446  nop     dword ptr [rax+rax+00h]
0x14000c44b  test    rbp, rbp
0x14000c44e  jz      short loc_14000C461
0x14000c450  xor     edx, edx; Tag
0x14000c452  mov     rcx, rbp; P
0x14000c455  call    cs:__imp_ExFreePoolWithTag
0x14000c45c  nop     dword ptr [rax+rax+00h]
0x14000c461  mov     eax, esi
0x14000c463  add     rsp, 20h
0x14000c467  pop     r15
0x14000c469  pop     r14
0x14000c46b  pop     r12
0x14000c46d  pop     rdi
0x14000c46e  pop     rsi
0x14000c46f  pop     rbp
0x14000c470  pop     rbx
0x14000c471  retn
```
