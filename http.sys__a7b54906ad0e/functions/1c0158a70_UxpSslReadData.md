# UxpSslReadData

- ea: `0x1c0158a70`
- end: `0x1c0158e11`
- name: `UxpSslReadData`
- size: `929`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c0156990`
- `0x1c01576c0`

## callees

- `0x1c0001118`
- `0x1c001b610`
- `0x1c0158a70`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x1c0158b60`
- `ntoskrnl!MmSizeOfMdl` at `0x1c0158b60`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1c0158ccb`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1c0158ccb`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c0158de4`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c0158de4`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0158b1c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0158c10`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0158b1c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0158c10`
- `ntoskrnl!ExQueryDepthSList` at `0x1c0158db7`
- `ntoskrnl!ExQueryDepthSList` at `0x1c0158db7`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0158aa6`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0158b9e`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0158d44`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0158aa6`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0158b9e`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0158d44`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c0158c66`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c0158c66`

## pseudocode

```c
__int64 __fastcall UxpSslReadData(__int64 a1, unsigned int a2)
{
  SIZE_T v2; // r15
  __int64 v3; // rbx
  unsigned int v4; // r9d
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 v7; // rcx
  unsigned int v8; // r8d
  unsigned int v9; // eax
  PSLIST_ENTRY v10; // rsi
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 (__fastcall *v14)(__int64, __int64, __int64, __int64); // rax
  unsigned int v15; // ebp
  char v16; // r12
  _QWORD *v17; // r14
  unsigned int v18; // r8d
  unsigned int v19; // eax
  __int64 v20; // rdi
  PVOID v21; // rcx
  unsigned int v22; // r8d
  unsigned int v23; // eax
  struct _MDL *PoolWithTagPriority; // r14
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 (__fastcall *v28)(__int64, __int64, __int64, __int64); // rax
  __int64 v29; // r14
  unsigned int v30; // r8d
  unsigned int v31; // eax
  __int64 v32; // rdi
  __int64 v33; // rcx
  unsigned int v34; // r8d
  unsigned int v35; // eax
  void (__fastcall *v36)(PSLIST_ENTRY, __int64); // rax

  v2 = a2;
  if ( UxCompactMode )
  {
    v3 = qword_1C00743C0;
    v4 = KeGetCurrentNodeNumber() + 1;
    v5 = (unsigned int)(*(_DWORD *)v3 - 1);
    if ( v4 < *(_DWORD *)v3 )
      v5 = v4;
    v6 = *(_QWORD *)(*(_QWORD *)(v3 + 32) + 8 * v5);
    if ( !*(_BYTE *)(v6 + 112) )
    {
      v7 = v3;
LABEL_9:
      PplpLazyInitializeLookasideList(v7, v6);
    }
  }
  else
  {
    v7 = qword_1C00743C0;
    v8 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
    v9 = *(_DWORD *)qword_1C00743C0 - 1;
    if ( v8 < *(_DWORD *)qword_1C00743C0 )
      v9 = v8;
    v6 = *(_QWORD *)(*(_QWORD *)(qword_1C00743C0 + 32) + 8LL * v9);
    if ( !*(_BYTE *)(v6 + 112) )
      goto LABEL_9;
  }
  ++*(_DWORD *)(v6 + 20);
  v10 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v6);
  if ( !v10 )
  {
    v11 = *(unsigned int *)(v6 + 40);
    v12 = *(unsigned int *)(v6 + 44);
    v13 = *(unsigned int *)(v6 + 36);
    v14 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v6 + 48);
    ++*(_DWORD *)(v6 + 24);
    v10 = (PSLIST_ENTRY)v14(v13, v12, v11, v6);
  }
  if ( v10 )
  {
    v15 = (MmSizeOfMdl((PVOID)0xFFF, v2) + 7) & 0xFFFFFFF8;
    if ( (unsigned int)v2 + v15 < v15 )
      goto LABEL_30;
    if ( (unsigned int)v2 > UxSslReadMdlSize )
    {
      v16 = 0;
      PoolWithTagPriority = (struct _MDL *)ExAllocatePoolWithTagPriority(
                                             (POOL_TYPE)512,
                                             (unsigned int)v2 + v15,
                                             0x52537855u,
                                             LowPoolPriority);
      if ( !PoolWithTagPriority )
        goto LABEL_30;
      goto LABEL_29;
    }
    v16 = 1;
    if ( UxCompactMode )
    {
      v17 = P;
      v18 = KeGetCurrentNodeNumber() + 1;
      v19 = *(_DWORD *)v17 - 1;
      if ( v18 < *(_DWORD *)v17 )
        v19 = v18;
      v20 = *(_QWORD *)(v17[4] + 8LL * v19);
      if ( !*(_BYTE *)(v20 + 112) )
      {
        v21 = v17;
LABEL_23:
        PplpLazyInitializeLookasideList(v21, v20);
      }
    }
    else
    {
      v21 = P;
      v22 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
      v23 = *(_DWORD *)P - 1;
      if ( v22 < *(_DWORD *)P )
        v23 = v22;
      v20 = *(_QWORD *)(*((_QWORD *)P + 4) + 8LL * v23);
      if ( !*(_BYTE *)(v20 + 112) )
        goto LABEL_23;
    }
    ++*(_DWORD *)(v20 + 20);
    PoolWithTagPriority = (struct _MDL *)ExpInterlockedPopEntrySList((PSLIST_HEADER)v20);
    if ( !PoolWithTagPriority )
    {
      v25 = *(unsigned int *)(v20 + 40);
      v26 = *(unsigned int *)(v20 + 44);
      v27 = *(unsigned int *)(v20 + 36);
      v28 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v20 + 48);
      ++*(_DWORD *)(v20 + 24);
      PoolWithTagPriority = (struct _MDL *)v28(v27, v26, v25, v20);
    }
    if ( !PoolWithTagPriority )
    {
LABEL_30:
      if ( !v10 )
        return 0;
      if ( UxCompactMode )
      {
        v29 = qword_1C00743C0;
        v30 = KeGetCurrentNodeNumber() + 1;
        v31 = *(_DWORD *)v29 - 1;
        if ( v30 < *(_DWORD *)v29 )
          v31 = v30;
        v32 = *(_QWORD *)(*(_QWORD *)(v29 + 32) + 8LL * v31);
        if ( *(_BYTE *)(v32 + 112) )
          goto LABEL_40;
        v33 = v29;
      }
      else
      {
        v33 = qword_1C00743C0;
        v34 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
        v35 = *(_DWORD *)qword_1C00743C0 - 1;
        if ( v34 < *(_DWORD *)qword_1C00743C0 )
          v35 = v34;
        v32 = *(_QWORD *)(*(_QWORD *)(qword_1C00743C0 + 32) + 8LL * v35);
        if ( *(_BYTE *)(v32 + 112) )
          goto LABEL_40;
      }
      PplpLazyInitializeLookasideList(v33, v32);
LABEL_40:
      ++*(_DWORD *)(v32 + 28);
      if ( ExQueryDepthSList((PSLIST_HEADER)v32) < *(_WORD *)(v32 + 16) )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)v32, v10);
      }
      else
      {
        v36 = *(void (__fastcall **)(PSLIST_ENTRY, __int64))(v32 + 56);
        ++*(_DWORD *)(v32 + 32);
        v36(v10, v32);
      }
      return 0;
    }
LABEL_29:
    PoolWithTagPriority->Next = 0;
    PoolWithTagPriority->MdlFlags = 0;
    PoolWithTagPriority->ByteCount = v2;
    PoolWithTagPriority->StartVa = (PVOID)(((unsigned __int64)PoolWithTagPriority + v15) & 0xFFFFFFFFFFFFF000uLL);
    PoolWithTagPriority->ByteOffset = ((_DWORD)PoolWithTagPriority + v15) & 0xFFF;
    PoolWithTagPriority->Size = 8 * ((((((unsigned int)PoolWithTagPriority + v15) & 0xFFFLL) + v2 + 4095) >> 12) + 6);
    MmBuildMdlForNonPagedPool(PoolWithTagPriority);
    *((_QWORD *)&v10[2].Next + 1) = a1;
    v10[2].Next = (struct _SLIST_ENTRY *)PoolWithTagPriority;
    LODWORD(v10[3].Next) = v2;
    BYTE4(v10[3].Next) = v16;
    _InterlockedAdd((volatile signed __int32 *)(a1 + 20), 1u);
    (*(void (__fastcall **)(_QWORD, _QWORD, struct _MDL *, _QWORD, SIZE_T, __int64 (__fastcall *)(PSLIST_ENTRY), PSLIST_ENTRY))(*(_QWORD *)(a1 + 56) + 104LL))(
      *(_QWORD *)(a1 + 48),
      0,
      PoolWithTagPriority,
      0,
      v2,
      UxpSslRestartReadData,
      v10);
    v10 = 0;
    goto LABEL_30;
  }
  return 0;
}

```

## disassembly

```asm
0x1c0158a70  mov     rax, rsp
0x1c0158a73  mov     [rax+10h], rbx
0x1c0158a77  mov     [rax+18h], rbp
0x1c0158a7b  mov     [rax+20h], rsi
0x1c0158a7f  mov     [rax+8], rcx
0x1c0158a83  push    rdi
0x1c0158a84  push    r12
0x1c0158a86  push    r13
0x1c0158a88  push    r14
0x1c0158a8a  push    r15
0x1c0158a8c  sub     rsp, 40h
0x1c0158a90  xor     r14d, r14d
0x1c0158a93  mov     r15d, edx
0x1c0158a96  cmp     cs:UxCompactMode, r14b
0x1c0158a9d  jz      short loc_1C0158ADA
0x1c0158a9f  mov     rbx, cs:qword_1C00743C0
0x1c0158aa6  call    cs:__imp_KeGetCurrentNodeNumber
0x1c0158aad  nop     dword ptr [rax+rax+00h]
0x1c0158ab2  mov     r8d, [rbx]
0x1c0158ab5  movzx   r9d, ax
0x1c0158ab9  mov     rax, [rbx+20h]
0x1c0158abd  inc     r9d
0x1c0158ac0  cmp     r9d, r8d
0x1c0158ac3  lea     edx, [r8-1]
0x1c0158ac7  cmovb   edx, r9d
0x1c0158acb  mov     rdi, [rax+rdx*8]
0x1c0158acf  cmp     [rdi+70h], r14b
0x1c0158ad3  jnz     short loc_1C0158B11
0x1c0158ad5  mov     rcx, rbx
0x1c0158ad8  jmp     short loc_1C0158B09
0x1c0158ada  mov     eax, gs:1A4h
0x1c0158ae2  mov     rcx, cs:qword_1C00743C0
0x1c0158ae9  lea     r8d, [rax+1]
0x1c0158aed  mov     edx, [rcx]
0x1c0158aef  cmp     r8d, edx
0x1c0158af2  lea     eax, [rdx-1]
0x1c0158af5  cmovb   eax, r8d
0x1c0158af9  mov     edx, eax
0x1c0158afb  mov     rax, [rcx+20h]
0x1c0158aff  mov     rdi, [rax+rdx*8]
0x1c0158b03  cmp     [rdi+70h], r14b
0x1c0158b07  jnz     short loc_1C0158B11
0x1c0158b09  mov     rdx, rdi
0x1c0158b0c  call    PplpLazyInitializeLookasideList
0x1c0158b11  mov     ebx, 1
0x1c0158b16  mov     rcx, rdi; ListHead
0x1c0158b19  add     [rdi+14h], ebx
0x1c0158b1c  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c0158b23  nop     dword ptr [rax+rax+00h]
0x1c0158b28  mov     rsi, rax
0x1c0158b2b  test    rax, rax
0x1c0158b2e  jnz     short loc_1C0158B4D
0x1c0158b30  mov     r8d, [rdi+28h]
0x1c0158b34  mov     r9, rdi
0x1c0158b37  mov     edx, [rdi+2Ch]
0x1c0158b3a  mov     ecx, [rdi+24h]
0x1c0158b3d  mov     rax, [rdi+30h]
0x1c0158b41  add     [rdi+18h], ebx
0x1c0158b44  call    cs:__guard_dispatch_icall_fptr
0x1c0158b4a  mov     rsi, rax
0x1c0158b4d  test    rsi, rsi
0x1c0158b50  jz      loc_1C0158DF0
0x1c0158b56  mov     edi, 0FFFh
0x1c0158b5b  mov     rdx, r15; Length
0x1c0158b5e  mov     ecx, edi; Base
0x1c0158b60  call    cs:__imp_MmSizeOfMdl
0x1c0158b67  nop     dword ptr [rax+rax+00h]
0x1c0158b6c  lea     ebp, [rax+7]
0x1c0158b6f  and     ebp, 0FFFFFFF8h
0x1c0158b72  lea     eax, [r15+rbp]
0x1c0158b76  cmp     eax, ebp
0x1c0158b78  jb      loc_1C0158D2B
0x1c0158b7e  cmp     r15d, cs:UxSslReadMdlSize
0x1c0158b85  ja      loc_1C0158C53
0x1c0158b8b  cmp     cs:UxCompactMode, r14b
0x1c0158b92  mov     r12b, bl
0x1c0158b95  jz      short loc_1C0158BD3
0x1c0158b97  mov     r14, cs:P
0x1c0158b9e  call    cs:__imp_KeGetCurrentNodeNumber
0x1c0158ba5  nop     dword ptr [rax+rax+00h]
0x1c0158baa  mov     edx, [r14]
0x1c0158bad  movzx   r8d, ax
0x1c0158bb1  inc     r8d
0x1c0158bb4  cmp     r8d, edx
0x1c0158bb7  lea     eax, [rdx-1]
0x1c0158bba  cmovb   eax, r8d
0x1c0158bbe  mov     edx, eax
0x1c0158bc0  mov     rax, [r14+20h]
0x1c0158bc4  mov     rdi, [rax+rdx*8]
0x1c0158bc8  cmp     byte ptr [rdi+70h], 0
0x1c0158bcc  jnz     short loc_1C0158C0A
0x1c0158bce  mov     rcx, r14
0x1c0158bd1  jmp     short loc_1C0158C02
0x1c0158bd3  mov     eax, gs:1A4h
0x1c0158bdb  mov     rcx, cs:P
0x1c0158be2  lea     r8d, [rax+1]
0x1c0158be6  mov     edx, [rcx]
0x1c0158be8  cmp     r8d, edx
0x1c0158beb  lea     eax, [rdx-1]
0x1c0158bee  cmovb   eax, r8d
0x1c0158bf2  mov     edx, eax
0x1c0158bf4  mov     rax, [rcx+20h]
0x1c0158bf8  mov     rdi, [rax+rdx*8]
0x1c0158bfc  cmp     [rdi+70h], r14b
0x1c0158c00  jnz     short loc_1C0158C0A
0x1c0158c02  mov     rdx, rdi
0x1c0158c05  call    PplpLazyInitializeLookasideList
0x1c0158c0a  add     [rdi+14h], ebx
0x1c0158c0d  mov     rcx, rdi; ListHead
0x1c0158c10  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c0158c17  nop     dword ptr [rax+rax+00h]
0x1c0158c1c  mov     r14, rax
0x1c0158c1f  test    rax, rax
0x1c0158c22  jnz     short loc_1C0158C41
0x1c0158c24  mov     r8d, [rdi+28h]
0x1c0158c28  mov     r9, rdi
0x1c0158c2b  mov     edx, [rdi+2Ch]
0x1c0158c2e  mov     ecx, [rdi+24h]
0x1c0158c31  mov     rax, [rdi+30h]
0x1c0158c35  add     [rdi+18h], ebx
0x1c0158c38  call    cs:__guard_dispatch_icall_fptr
0x1c0158c3e  mov     r14, rax
0x1c0158c41  xor     eax, eax
0x1c0158c43  test    r14, r14
0x1c0158c46  jz      loc_1C0158D28
0x1c0158c4c  mov     edi, 0FFFh
0x1c0158c51  jmp     short loc_1C0158C80
0x1c0158c53  mov     edx, eax; NumberOfBytes
0x1c0158c55  xor     r9d, r9d; Priority
0x1c0158c58  mov     ecx, 200h; PoolType
0x1c0158c5d  mov     r8d, 52537855h; Tag
0x1c0158c63  mov     r12b, r14b
0x1c0158c66  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c0158c6d  nop     dword ptr [rax+rax+00h]
0x1c0158c72  mov     r14, rax
0x1c0158c75  xor     eax, eax
0x1c0158c77  test    r14, r14
0x1c0158c7a  jz      loc_1C0158D28
0x1c0158c80  mov     r9d, ebp
0x1c0158c83  lea     rdx, [r15+0FFFh]
0x1c0158c8a  add     r9, r14
0x1c0158c8d  mov     [r14], rax
0x1c0158c90  mov     r8d, r9d
0x1c0158c93  mov     [r14+0Ah], ax
0x1c0158c98  mov     ecx, r8d
0x1c0158c9b  mov     [r14+28h], r15d
0x1c0158c9f  and     rcx, rdi
0x1c0158ca2  and     r9, 0FFFFFFFFFFFFF000h
0x1c0158ca9  add     rdx, rcx
0x1c0158cac  mov     [r14+20h], r9
0x1c0158cb0  shr     rdx, 0Ch
0x1c0158cb4  and     r8d, edi
0x1c0158cb7  add     dx, 6
0x1c0158cbb  mov     [r14+2Ch], r8d
0x1c0158cbf  shl     dx, 3
0x1c0158cc3  mov     rcx, r14; MemoryDescriptorList
0x1c0158cc6  mov     [r14+8], dx
0x1c0158ccb  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1c0158cd2  nop     dword ptr [rax+rax+00h]
0x1c0158cd7  mov     rcx, [rsp+68h+arg_0]
0x1c0158cdc  mov     [rsi+28h], rcx
0x1c0158ce0  mov     [rsi+20h], r14
0x1c0158ce4  mov     [rsi+30h], r15d
0x1c0158ce8  mov     [rsi+34h], r12b
0x1c0158cec  lock add [rcx+14h], ebx
0x1c0158cf0  mov     rax, [rcx+38h]
0x1c0158cf4  lea     rdx, UxpSslRestartReadData
0x1c0158cfb  mov     rcx, [rcx+30h]
0x1c0158cff  xor     r9d, r9d
0x1c0158d02  mov     [rsp+68h+var_38], rsi
0x1c0158d07  mov     r8, r14
0x1c0158d0a  mov     [rsp+68h+var_40], rdx
0x1c0158d0f  xor     edx, edx
0x1c0158d11  mov     rax, [rax+68h]
0x1c0158d15  mov     [rsp+68h+var_48], r15
0x1c0158d1a  call    cs:__guard_dispatch_icall_fptr
0x1c0158d20  xor     r14d, r14d
0x1c0158d23  mov     esi, r14d
0x1c0158d26  jmp     short loc_1C0158D2B
0x1c0158d28  xor     r14d, r14d
0x1c0158d2b  test    rsi, rsi
0x1c0158d2e  jz      loc_1C0158DF0
0x1c0158d34  cmp     cs:UxCompactMode, r14b
0x1c0158d3b  jz      short loc_1C0158D7A
0x1c0158d3d  mov     r14, cs:qword_1C00743C0
0x1c0158d44  call    cs:__imp_KeGetCurrentNodeNumber
0x1c0158d4b  nop     dword ptr [rax+rax+00h]
0x1c0158d50  mov     edx, [r14]
0x1c0158d53  movzx   r8d, ax
0x1c0158d57  inc     r8d
0x1c0158d5a  cmp     r8d, edx
0x1c0158d5d  lea     eax, [rdx-1]
0x1c0158d60  cmovb   eax, r8d
0x1c0158d64  mov     edx, eax
0x1c0158d66  mov     rax, [r14+20h]
0x1c0158d6a  mov     rdi, [rax+rdx*8]
0x1c0158d6e  xor     eax, eax
0x1c0158d70  cmp     [rdi+70h], al
0x1c0158d73  jnz     short loc_1C0158DB1
0x1c0158d75  mov     rcx, r14
0x1c0158d78  jmp     short loc_1C0158DA9
0x1c0158d7a  mov     eax, gs:1A4h
0x1c0158d82  mov     rcx, cs:qword_1C00743C0
0x1c0158d89  lea     r8d, [rax+1]
0x1c0158d8d  mov     edx, [rcx]
0x1c0158d8f  cmp     r8d, edx
0x1c0158d92  lea     eax, [rdx-1]
0x1c0158d95  cmovb   eax, r8d
0x1c0158d99  mov     edx, eax
0x1c0158d9b  mov     rax, [rcx+20h]
0x1c0158d9f  mov     rdi, [rax+rdx*8]
0x1c0158da3  cmp     [rdi+70h], r14b
0x1c0158da7  jnz     short loc_1C0158DB1
0x1c0158da9  mov     rdx, rdi
0x1c0158dac  call    PplpLazyInitializeLookasideList
0x1c0158db1  add     [rdi+1Ch], ebx
0x1c0158db4  mov     rcx, rdi; SListHead
0x1c0158db7  call    cs:__imp_ExQueryDepthSList
0x1c0158dbe  nop     dword ptr [rax+rax+00h]
0x1c0158dc3  cmp     ax, [rdi+10h]
0x1c0158dc7  jb      short loc_1C0158DDE
0x1c0158dc9  mov     rax, [rdi+38h]
0x1c0158dcd  mov     rdx, rdi
0x1c0158dd0  add     [rdi+20h], ebx
0x1c0158dd3  mov     rcx, rsi
0x1c0158dd6  call    cs:__guard_dispatch_icall_fptr
0x1c0158ddc  jmp     short loc_1C0158DF0
0x1c0158dde  mov     rdx, rsi; ListEntry
0x1c0158de1  mov     rcx, rdi; ListHead
0x1c0158de4  call    cs:__imp_ExpInterlockedPushEntrySList
0x1c0158deb  nop     dword ptr [rax+rax+00h]
0x1c0158df0  lea     r11, [rsp+68h+var_28]
0x1c0158df5  xor     eax, eax
0x1c0158df7  mov     rbx, [r11+38h]
0x1c0158dfb  mov     rbp, [r11+40h]
0x1c0158dff  mov     rsi, [r11+48h]
0x1c0158e03  mov     rsp, r11
0x1c0158e06  pop     r15
0x1c0158e08  pop     r14
0x1c0158e0a  pop     r13
0x1c0158e0c  pop     r12
0x1c0158e0e  pop     rdi
0x1c0158e0f  retn
```
