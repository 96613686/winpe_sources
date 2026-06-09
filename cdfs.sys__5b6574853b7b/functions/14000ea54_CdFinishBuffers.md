# CdFinishBuffers

- ea: `0x14000ea54`
- end: `0x14000ecce`
- name: `CdFinishBuffers`
- size: `634`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f27c`
- `0x14000f618`

## callees

- `0x140003000`
- `0x14000ea54`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14000eaf5`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000ec01`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000eaf5`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000ec01`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000eb50`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000ec5c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000eb50`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000ec5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eb1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eb60`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ec28`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ec6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eb1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eb60`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ec28`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ec6c`
- `ntoskrnl!IoFreeMdl` at `0x14000eac9`
- `ntoskrnl!IoFreeMdl` at `0x14000eb86`
- `ntoskrnl!IoFreeMdl` at `0x14000ebd5`
- `ntoskrnl!IoFreeMdl` at `0x14000ec92`
- `ntoskrnl!IoFreeMdl` at `0x14000eac9`
- `ntoskrnl!IoFreeMdl` at `0x14000eb86`
- `ntoskrnl!IoFreeMdl` at `0x14000ebd5`
- `ntoskrnl!IoFreeMdl` at `0x14000ec92`
- `ntoskrnl!IoFreeIrp` at `0x14000eb96`
- `ntoskrnl!IoFreeIrp` at `0x14000eca2`
- `ntoskrnl!IoFreeIrp` at `0x14000eb96`
- `ntoskrnl!IoFreeIrp` at `0x14000eca2`

## pseudocode

```c
char __fastcall CdFinishBuffers(__int64 a1, __int64 a2, int a3, char a4, char a5)
{
  char v5; // r12
  int v6; // esi
  __int64 v9; // rbx
  unsigned int v10; // eax
  struct _MDL *v11; // rcx
  void *v12; // rcx
  __int64 v13; // rdi
  void *v14; // rcx
  __int64 v15; // rax
  struct _MDL *v16; // rcx
  struct _MDL *v17; // rcx
  void *v18; // rcx
  __int64 v19; // rdi
  void *v20; // rcx
  __int64 v21; // rax
  struct _MDL *v22; // rcx

  v5 = 0;
  v6 = a3;
  if ( a3 )
  {
    v9 = a2 + ((unsigned __int64)(unsigned int)(a3 - 1) << 6);
    if ( a4 )
    {
      do
      {
        if ( *(_DWORD *)(v9 + 32) )
        {
          v17 = *(struct _MDL **)(v9 + 40);
          if ( v17 != *(struct _MDL **)(*(_QWORD *)(a1 + 8) + 8LL) )
          {
            if ( v17 )
              IoFreeMdl(v17);
            v18 = *(void **)(v9 + 24);
            if ( v18 )
            {
              if ( a5 )
              {
                v19 = *(_QWORD *)(a1 + 16);
                ExAcquireFastMutex((PFAST_MUTEX)(v19 + 336));
                v20 = *(void **)(v19 + 112);
                *(_QWORD *)(v19 + 392) = KeGetCurrentThread();
                if ( v20 )
                {
                  ExFreePoolWithTag(v20, 0);
                  *(_QWORD *)(v19 + 112) = 0;
                }
                a5 = 0;
                *(_QWORD *)(v19 + 112) = *(_QWORD *)(v9 + 24);
                *(_QWORD *)(v19 + 120) = *(_QWORD *)v9;
                *(_QWORD *)(v19 + 392) = 0;
                ExReleaseFastMutex((PFAST_MUTEX)(v19 + 336));
              }
              else
              {
                ExFreePoolWithTag(v18, 0);
                *(_QWORD *)(v9 + 24) = 0;
              }
            }
          }
        }
        v21 = *(_QWORD *)(v9 + 56);
        if ( v21 )
        {
          v22 = *(struct _MDL **)(v21 + 8);
          if ( v22 )
            IoFreeMdl(v22);
          IoFreeIrp(*(PIRP *)(v9 + 56));
        }
        v9 -= 64;
        --v6;
      }
      while ( v6 );
    }
    else
    {
      do
      {
        v10 = *(_DWORD *)(v9 + 32);
        if ( v10 )
        {
          memmove(*(void **)(v9 + 16), (const void *)(*(_QWORD *)(v9 + 24) + *(unsigned int *)(v9 + 36)), v10);
          v5 = 1;
          v11 = *(struct _MDL **)(v9 + 40);
          if ( v11 != *(struct _MDL **)(*(_QWORD *)(a1 + 8) + 8LL) )
          {
            if ( v11 )
              IoFreeMdl(v11);
            v12 = *(void **)(v9 + 24);
            if ( v12 )
            {
              if ( a5 )
              {
                v13 = *(_QWORD *)(a1 + 16);
                ExAcquireFastMutex((PFAST_MUTEX)(v13 + 336));
                v14 = *(void **)(v13 + 112);
                *(_QWORD *)(v13 + 392) = KeGetCurrentThread();
                if ( v14 )
                {
                  ExFreePoolWithTag(v14, 0);
                  *(_QWORD *)(v13 + 112) = 0;
                }
                a5 = 0;
                *(_QWORD *)(v13 + 112) = *(_QWORD *)(v9 + 24);
                *(_QWORD *)(v13 + 120) = *(_QWORD *)v9;
                *(_QWORD *)(v13 + 392) = 0;
                ExReleaseFastMutex((PFAST_MUTEX)(v13 + 336));
              }
              else
              {
                ExFreePoolWithTag(v12, 0);
                *(_QWORD *)(v9 + 24) = 0;
              }
            }
          }
        }
        v15 = *(_QWORD *)(v9 + 56);
        if ( v15 )
        {
          v16 = *(struct _MDL **)(v15 + 8);
          if ( v16 )
            IoFreeMdl(v16);
          IoFreeIrp(*(PIRP *)(v9 + 56));
        }
        v9 -= 64;
        --v6;
      }
      while ( v6 );
    }
  }
  return v5;
}

```

## disassembly

```asm
0x14000ea54  push    rbx
0x14000ea56  push    rbp
0x14000ea57  push    rsi
0x14000ea58  push    rdi
0x14000ea59  push    r12
0x14000ea5b  push    r14
0x14000ea5d  push    r15
0x14000ea5f  sub     rsp, 20h
0x14000ea63  xor     r12b, r12b
0x14000ea66  mov     esi, r8d
0x14000ea69  mov     r15, rcx
0x14000ea6c  test    r8d, r8d
0x14000ea6f  jz      loc_14000ECBB
0x14000ea75  mov     r14b, [rsp+58h+arg_20]
0x14000ea7d  lea     ebx, [r8-1]
0x14000ea81  shl     rbx, 6
0x14000ea85  add     rbx, rdx
0x14000ea88  test    r9b, r9b
0x14000ea8b  jnz     loc_14000EBB4
0x14000ea91  mov     eax, [rbx+20h]
0x14000ea94  test    eax, eax
0x14000ea96  jz      loc_14000EB74
0x14000ea9c  mov     edx, [rbx+24h]
0x14000ea9f  mov     r8d, eax; Size
0x14000eaa2  add     rdx, [rbx+18h]; Src
0x14000eaa6  mov     rcx, [rbx+10h]; void *
0x14000eaaa  call    memmove
0x14000eaaf  mov     rax, [r15+8]
0x14000eab3  mov     r12b, 1
0x14000eab6  mov     rcx, [rbx+28h]; Mdl
0x14000eaba  cmp     rcx, [rax+8]
0x14000eabe  jz      loc_14000EB74
0x14000eac4  test    rcx, rcx
0x14000eac7  jz      short loc_14000EAD5
0x14000eac9  call    cs:__imp_IoFreeMdl
0x14000ead0  nop     dword ptr [rax+rax+00h]
0x14000ead5  mov     rcx, [rbx+18h]; P
0x14000ead9  test    rcx, rcx
0x14000eadc  jz      loc_14000EB74
0x14000eae2  test    r14b, r14b
0x14000eae5  jz      short loc_14000EB5E
0x14000eae7  mov     rdi, [r15+10h]
0x14000eaeb  lea     rbp, [rdi+150h]
0x14000eaf2  mov     rcx, rbp; FastMutex
0x14000eaf5  call    cs:__imp_ExAcquireFastMutex
0x14000eafc  nop     dword ptr [rax+rax+00h]
0x14000eb01  mov     rax, gs:188h
0x14000eb0a  mov     rcx, [rdi+70h]; P
0x14000eb0e  mov     [rdi+188h], rax
0x14000eb15  test    rcx, rcx
0x14000eb18  jz      short loc_14000EB30
0x14000eb1a  xor     edx, edx; Tag
0x14000eb1c  call    cs:__imp_ExFreePoolWithTag
0x14000eb23  nop     dword ptr [rax+rax+00h]
0x14000eb28  mov     qword ptr [rdi+70h], 0
0x14000eb30  mov     rax, [rbx+18h]
0x14000eb34  xor     r14b, r14b
0x14000eb37  mov     [rdi+70h], rax
0x14000eb3b  mov     rcx, rbp; FastMutex
0x14000eb3e  mov     rax, [rbx]
0x14000eb41  mov     [rdi+78h], rax
0x14000eb45  mov     qword ptr [rdi+188h], 0
0x14000eb50  call    cs:__imp_ExReleaseFastMutex
0x14000eb57  nop     dword ptr [rax+rax+00h]
0x14000eb5c  jmp     short loc_14000EB74
0x14000eb5e  xor     edx, edx; Tag
0x14000eb60  call    cs:__imp_ExFreePoolWithTag
0x14000eb67  nop     dword ptr [rax+rax+00h]
0x14000eb6c  mov     qword ptr [rbx+18h], 0
0x14000eb74  mov     rax, [rbx+38h]
0x14000eb78  test    rax, rax
0x14000eb7b  jz      short loc_14000EBA2
0x14000eb7d  mov     rcx, [rax+8]; Mdl
0x14000eb81  test    rcx, rcx
0x14000eb84  jz      short loc_14000EB92
0x14000eb86  call    cs:__imp_IoFreeMdl
0x14000eb8d  nop     dword ptr [rax+rax+00h]
0x14000eb92  mov     rcx, [rbx+38h]; Irp
0x14000eb96  call    cs:__imp_IoFreeIrp
0x14000eb9d  nop     dword ptr [rax+rax+00h]
0x14000eba2  sub     rbx, 40h ; '@'
0x14000eba6  add     esi, 0FFFFFFFFh
0x14000eba9  jnz     loc_14000EA91
0x14000ebaf  jmp     loc_14000ECBB
0x14000ebb4  cmp     dword ptr [rbx+20h], 0
0x14000ebb8  jz      loc_14000EC80
0x14000ebbe  mov     rax, [r15+8]
0x14000ebc2  mov     rcx, [rbx+28h]; Mdl
0x14000ebc6  cmp     rcx, [rax+8]
0x14000ebca  jz      loc_14000EC80
0x14000ebd0  test    rcx, rcx
0x14000ebd3  jz      short loc_14000EBE1
0x14000ebd5  call    cs:__imp_IoFreeMdl
0x14000ebdc  nop     dword ptr [rax+rax+00h]
0x14000ebe1  mov     rcx, [rbx+18h]; P
0x14000ebe5  test    rcx, rcx
0x14000ebe8  jz      loc_14000EC80
0x14000ebee  test    r14b, r14b
0x14000ebf1  jz      short loc_14000EC6A
0x14000ebf3  mov     rdi, [r15+10h]
0x14000ebf7  lea     rbp, [rdi+150h]
0x14000ebfe  mov     rcx, rbp; FastMutex
0x14000ec01  call    cs:__imp_ExAcquireFastMutex
0x14000ec08  nop     dword ptr [rax+rax+00h]
0x14000ec0d  mov     rax, gs:188h
0x14000ec16  mov     rcx, [rdi+70h]; P
0x14000ec1a  mov     [rdi+188h], rax
0x14000ec21  test    rcx, rcx
0x14000ec24  jz      short loc_14000EC3C
0x14000ec26  xor     edx, edx; Tag
0x14000ec28  call    cs:__imp_ExFreePoolWithTag
0x14000ec2f  nop     dword ptr [rax+rax+00h]
0x14000ec34  mov     qword ptr [rdi+70h], 0
0x14000ec3c  mov     rax, [rbx+18h]
0x14000ec40  xor     r14b, r14b
0x14000ec43  mov     [rdi+70h], rax
0x14000ec47  mov     rcx, rbp; FastMutex
0x14000ec4a  mov     rax, [rbx]
0x14000ec4d  mov     [rdi+78h], rax
0x14000ec51  mov     qword ptr [rdi+188h], 0
0x14000ec5c  call    cs:__imp_ExReleaseFastMutex
0x14000ec63  nop     dword ptr [rax+rax+00h]
0x14000ec68  jmp     short loc_14000EC80
0x14000ec6a  xor     edx, edx; Tag
0x14000ec6c  call    cs:__imp_ExFreePoolWithTag
0x14000ec73  nop     dword ptr [rax+rax+00h]
0x14000ec78  mov     qword ptr [rbx+18h], 0
0x14000ec80  mov     rax, [rbx+38h]
0x14000ec84  test    rax, rax
0x14000ec87  jz      short loc_14000ECAE
0x14000ec89  mov     rcx, [rax+8]; Mdl
0x14000ec8d  test    rcx, rcx
0x14000ec90  jz      short loc_14000EC9E
0x14000ec92  call    cs:__imp_IoFreeMdl
0x14000ec99  nop     dword ptr [rax+rax+00h]
0x14000ec9e  mov     rcx, [rbx+38h]; Irp
0x14000eca2  call    cs:__imp_IoFreeIrp
0x14000eca9  nop     dword ptr [rax+rax+00h]
0x14000ecae  sub     rbx, 40h ; '@'
0x14000ecb2  add     esi, 0FFFFFFFFh
0x14000ecb5  jnz     loc_14000EBB4
0x14000ecbb  mov     al, r12b
0x14000ecbe  add     rsp, 20h
0x14000ecc2  pop     r15
0x14000ecc4  pop     r14
0x14000ecc6  pop     r12
0x14000ecc8  pop     rdi
0x14000ecc9  pop     rsi
0x14000ecca  pop     rbp
0x14000eccb  pop     rbx
0x14000eccc  retn
```
