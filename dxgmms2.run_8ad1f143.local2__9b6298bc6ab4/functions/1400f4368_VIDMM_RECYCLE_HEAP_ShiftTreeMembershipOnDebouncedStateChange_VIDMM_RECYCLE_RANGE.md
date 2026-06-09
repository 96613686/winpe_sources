# VIDMM_RECYCLE_HEAP::ShiftTreeMembershipOnDebouncedStateChange(VIDMM_RECYCLE_RANGE *)

- ea: `0x1400f4368`
- end: `0x1400f46a8`
- name: `?ShiftTreeMembershipOnDebouncedStateChange@VIDMM_RECYCLE_HEAP@@QEAAXPEAVVIDMM_RECYCLE_RANGE@@@Z`
- size: `832`
- prototype: `void __fastcall(VIDMM_RECYCLE_HEAP *__hidden this, struct VIDMM_RECYCLE_RANGE *)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1400f0d24`
- `0x1400f26b8`
- `0x1400f5dd8`

## callees

- `0x1400abebc`
- `0x1400f4368`
- `0x1400f598c`
- `0x1400f5a58`
- `0x1400f5ca0`
- `0x1400f5eec`
- `0x1400f6074`

## import_xrefs

- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f43fa`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f43fa`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f44df`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f44df`
- `watchdog!WdLogSingleEntry2` at `0x1400f43bf`
- `watchdog!WdLogSingleEntry2` at `0x1400f43bf`
- `watchdog!WdLogSingleEntry5` at `0x1400f4659`
- `watchdog!WdLogSingleEntry5` at `0x1400f4659`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f4632`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
void __fastcall VIDMM_RECYCLE_HEAP::ShiftTreeMembershipOnDebouncedStateChange(
        VIDMM_RECYCLE_HEAP *this,
        struct VIDMM_RECYCLE_RANGE *a2)
{
  __int64 v4; // rsi
  unsigned int v5; // r14d
  unsigned int v6; // ebx
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // r10
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // r9
  __int64 v11; // rbx
  __int64 v12; // rax
  int v13; // edx
  char *v14; // rcx
  __int64 v15; // rdx
  _QWORD *v16; // r15
  __int64 v17; // r8
  __int64 v18; // rbx
  __int64 Multirange; // r13
  int v20; // eax
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8

  if ( *((_DWORD *)a2 + 16) != 4 )
  {
    if ( *((_DWORD *)a2 + 16) != 5 )
    {
      v6 = 3;
      v5 = 3;
      goto LABEL_23;
    }
    v4 = *((_QWORD *)a2 + 18);
    v5 = 1;
    goto LABEL_4;
  }
  v5 = 0;
  v4 = *((_QWORD *)a2 + 19);
  v13 = **(_DWORD **)(*((_QWORD *)a2 + 9) + 32LL);
  if ( (unsigned int)(v13 - 3) <= 3 || (v6 = 1, (unsigned int)(v13 - 9) <= 1) )
LABEL_4:
    v6 = 2;
  if ( !v4 )
  {
LABEL_23:
    VIDMM_RECYCLE_HEAP::RemoveRangeFromTree(this, v5, a2);
    VIDMM_RECYCLE_HEAP::AddRangeToTree(this, v6, a2);
    return;
  }
  WdLogSingleEntry2(4, v4, v5);
  WdLogGlobalForLineNumber = 8471;
  if ( v5 )
    v14 = (char *)this + 56;
  else
    v14 = (char *)this + 48;
  RtlAvlRemoveNode(v14, v4);
  v7 = *(_QWORD *)(v4 + 32);
  v8 = *(_QWORD *)(v4 + 40);
  *(_DWORD *)(v4 + 88) = 3;
  v9 = *((_QWORD *)a2 + 4);
  v10 = *((_QWORD *)a2 + 5);
  if ( v7 < v9 )
  {
    if ( v8 > v10 )
    {
      v15 = *((_QWORD *)a2 + 15);
      v16 = 0;
      v17 = *((_QWORD *)a2 + 9);
      v18 = *(_QWORD *)(v4 + 72);
      if ( v15 != v17 + 72 )
        v16 = (_QWORD *)(v15 - 120);
      Multirange = VIDMM_RECYCLE_HEAP_MGR::CreateMultirange(
                     *((_QWORD *)this + 1),
                     *(unsigned int *)(v4 + 144),
                     v17,
                     v10,
                     v8);
      *(_QWORD *)(Multirange + 64) = v16;
      *(_QWORD *)(Multirange + 72) = v18;
      VIDMM_RECYCLE_MULTIRANGE::ShrinkTo((VIDMM_RECYCLE_MULTIRANGE *)v4, *(_QWORD *)(v4 + 32), *((_QWORD *)a2 + 4));
      while ( 1 )
      {
        v20 = *(_DWORD *)(Multirange + 144);
        if ( v20 )
        {
          v21 = v20 - 1;
          if ( v21 )
          {
            if ( v21 == 1 )
              v16[19] = Multirange;
          }
          else
          {
            v16[18] = Multirange;
          }
        }
        else
        {
          v16[17] = Multirange;
        }
        if ( v16 == *(_QWORD **)(Multirange + 72) )
          break;
        v22 = v16[15];
        v23 = v16[9];
        v16 = 0;
        if ( v22 != v23 + 72 )
          v16 = (_QWORD *)(v22 - 120);
      }
      if ( *((_DWORD *)a2 + 16) == 4 )
      {
        *((_QWORD *)a2 + 19) = 0;
      }
      else if ( *((_DWORD *)a2 + 16) == 5 )
      {
        *((_QWORD *)a2 + 18) = 0;
      }
      VIDMM_RECYCLE_HEAP::AddMultirangeToTree(this, v5, v4);
      v24 = Multirange;
      goto LABEL_40;
    }
LABEL_36:
    VIDMM_RECYCLE_MULTIRANGE::ShrinkTo((VIDMM_RECYCLE_MULTIRANGE *)v4, v7, v9);
    if ( *((_DWORD *)a2 + 16) == 4 )
    {
      *((_QWORD *)a2 + 19) = 0;
    }
    else if ( *((_DWORD *)a2 + 16) == 5 )
    {
      *((_QWORD *)a2 + 18) = 0;
    }
    v24 = v4;
LABEL_40:
    VIDMM_RECYCLE_HEAP::AddMultirangeToTree(this, v5, v24);
    return;
  }
  if ( v8 > v10 )
  {
    v9 = v8;
    v7 = *((_QWORD *)a2 + 5);
    goto LABEL_36;
  }
  v11 = *((_QWORD *)this + 1);
  VIDMM_RECYCLE_MULTIRANGE::Destroy((VIDMM_RECYCLE_MULTIRANGE *)v4);
  v12 = *(unsigned int *)(v11 + 1620);
  if ( (unsigned int)v12 >= 4 )
  {
    ExFreeToLookasideListEx(*(PLOOKASIDE_LIST_EX *)(v11 + 1320), (PVOID)v4);
  }
  else
  {
    *(_QWORD *)(v11 + 8 * v12 + 1656) = v4;
    ++*(_DWORD *)(v11 + 1620);
  }
  --*(_DWORD *)(v11 + 1688);
  if ( *((_DWORD *)a2 + 16) == 4 )
  {
    *((_QWORD *)a2 + 19) = 0;
  }
  else if ( *((_DWORD *)a2 + 16) == 5 )
  {
    *((_QWORD *)a2 + 18) = 0;
  }
}

```

## disassembly

```asm
0x1400f4368  push    rbx
0x1400f436a  push    rbp
0x1400f436b  push    rsi
0x1400f436c  push    rdi
0x1400f436d  push    r13
0x1400f436f  push    r14
0x1400f4371  push    r15
0x1400f4373  sub     rsp, 30h
0x1400f4377  mov     rbp, rcx
0x1400f437a  mov     r13d, 4
0x1400f4380  mov     ecx, [rdx+40h]
0x1400f4383  mov     rdi, rdx
0x1400f4386  sub     ecx, r13d
0x1400f4389  jz      loc_1400F4487
0x1400f438f  cmp     ecx, 1
0x1400f4392  jnz     loc_1400F44F9
0x1400f4398  mov     rsi, [rdx+90h]
0x1400f439f  mov     r15d, ecx
0x1400f43a2  mov     r14d, ecx
0x1400f43a5  mov     ebx, 2
0x1400f43aa  test    rsi, rsi
0x1400f43ad  jz      loc_1400F4501
0x1400f43b3  mov     r8d, r14d
0x1400f43b6  mov     rdx, rsi
0x1400f43b9  mov     ecx, r13d
0x1400f43bc  mov     ebx, r14d
0x1400f43bf  call    cs:__imp_WdLogSingleEntry2
0x1400f43c6  nop     dword ptr [rax+rax+00h]
0x1400f43cb  mov     cs:WdLogGlobalForLineNumber, 2117h
0x1400f43d5  mov     ecx, r14d
0x1400f43d8  test    r14d, r14d
0x1400f43db  jz      loc_1400F44CC
0x1400f43e1  sub     ecx, 1
0x1400f43e4  jz      loc_1400F44F0
0x1400f43ea  cmp     ecx, 1
0x1400f43ed  jnz     loc_1400F4632
0x1400f43f3  lea     rcx, [rbp+40h]
0x1400f43f7  mov     rdx, rsi
0x1400f43fa  call    cs:__imp_RtlAvlRemoveNode
0x1400f4401  nop     dword ptr [rax+rax+00h]
0x1400f4406  mov     rdx, [rsi+20h]
0x1400f440a  mov     r10, [rsi+28h]
0x1400f440e  mov     dword ptr [rsi+58h], 3
0x1400f4415  mov     r8, [rdi+20h]
0x1400f4419  mov     r9, [rdi+28h]
0x1400f441d  cmp     rdx, r8
0x1400f4420  jb      loc_1400F4521
0x1400f4426  cmp     r10, r9
0x1400f4429  ja      loc_1400F45B8
0x1400f442f  mov     rbx, [rbp+8]
0x1400f4433  mov     rcx, rsi; this
0x1400f4436  call    ?Destroy@VIDMM_RECYCLE_MULTIRANGE@@QEAAXXZ; VIDMM_RECYCLE_MULTIRANGE::Destroy(void)
0x1400f443b  mov     eax, [rbx+654h]
0x1400f4441  cmp     eax, r13d
0x1400f4444  jnb     loc_1400F44D5
0x1400f444a  mov     [rbx+rax*8+678h], rsi
0x1400f4452  add     [rbx+654h], r15d
0x1400f4459  dec     dword ptr [rbx+698h]
0x1400f445f  mov     ecx, [rdi+40h]
0x1400f4462  sub     ecx, r13d
0x1400f4465  jz      short loc_1400F44BF
0x1400f4467  cmp     ecx, 1
0x1400f446a  jnz     short loc_1400F4477
0x1400f446c  mov     qword ptr [rdi+90h], 0
0x1400f4477  add     rsp, 30h
0x1400f447b  pop     r15
0x1400f447d  pop     r14
0x1400f447f  pop     r13
0x1400f4481  pop     rdi
0x1400f4482  pop     rsi
0x1400f4483  pop     rbp
0x1400f4484  pop     rbx
0x1400f4485  retn
0x1400f4487  mov     rax, [rdx+48h]
0x1400f448b  xor     r14d, r14d
0x1400f448e  mov     rsi, [rdx+98h]
0x1400f4495  mov     rcx, [rax+20h]
0x1400f4499  lea     r15d, [r14+1]
0x1400f449d  mov     edx, [rcx]
0x1400f449f  lea     eax, [rdx-3]
0x1400f44a2  cmp     eax, 3
0x1400f44a5  jbe     loc_1400F43A5
0x1400f44ab  lea     eax, [rdx-9]
0x1400f44ae  mov     ebx, r15d
0x1400f44b1  cmp     eax, r15d
0x1400f44b4  jbe     loc_1400F43A5
0x1400f44ba  jmp     loc_1400F43AA
0x1400f44bf  mov     qword ptr [rdi+98h], 0
0x1400f44ca  jmp     short loc_1400F4477
0x1400f44cc  lea     rcx, [rbp+30h]
0x1400f44d0  jmp     loc_1400F43F7
0x1400f44d5  mov     rcx, [rbx+528h]; Lookaside
0x1400f44dc  mov     rdx, rsi; Entry
0x1400f44df  call    cs:__imp_ExFreeToLookasideListEx
0x1400f44e6  nop     dword ptr [rax+rax+00h]
0x1400f44eb  jmp     loc_1400F4459
0x1400f44f0  lea     rcx, [rbp+38h]
0x1400f44f4  jmp     loc_1400F43F7
0x1400f44f9  mov     ebx, 3
0x1400f44fe  mov     r14d, ebx
0x1400f4501  mov     r8, rdi
0x1400f4504  mov     edx, r14d
0x1400f4507  mov     rcx, rbp
0x1400f450a  call    ?RemoveRangeFromTree@VIDMM_RECYCLE_HEAP@@QEAAXW4VIDMM_RECYCLE_HEAP_TREE@@PEAVVIDMM_RECYCLE_RANGE@@@Z; VIDMM_RECYCLE_HEAP::RemoveRangeFromTree(VIDMM_RECYCLE_HEAP_TREE,VIDMM_RECYCLE_RANGE *)
0x1400f450f  mov     r8, rdi
0x1400f4512  mov     edx, ebx
0x1400f4514  mov     rcx, rbp
0x1400f4517  call    ?AddRangeToTree@VIDMM_RECYCLE_HEAP@@QEAAXW4VIDMM_RECYCLE_HEAP_TREE@@PEAVVIDMM_RECYCLE_RANGE@@@Z; VIDMM_RECYCLE_HEAP::AddRangeToTree(VIDMM_RECYCLE_HEAP_TREE,VIDMM_RECYCLE_RANGE *)
0x1400f451c  jmp     loc_1400F4477
0x1400f4521  cmp     r10, r9
0x1400f4524  jbe     loc_1400F45BE
0x1400f452a  mov     rdx, [rdi+78h]
0x1400f452e  xor     r15d, r15d
0x1400f4531  mov     r8, [rdi+48h]
0x1400f4535  mov     rbx, [rsi+48h]
0x1400f4539  mov     [rsp+68h+var_48], r10
0x1400f453e  lea     rax, [rdx-78h]
0x1400f4542  lea     rcx, [r8+48h]
0x1400f4546  cmp     rdx, rcx
0x1400f4549  mov     edx, [rsi+90h]
0x1400f454f  mov     rcx, [rbp+8]
0x1400f4553  cmovnz  r15, rax
0x1400f4557  call    ?CreateMultirange@VIDMM_RECYCLE_HEAP_MGR@@QEAAPEAVVIDMM_RECYCLE_MULTIRANGE@@W4VIDMM_RECYCLE_MULTIRANGE_STATE@@PEAVVIDMM_RECYCLE_BLOCK@@_K2@Z; VIDMM_RECYCLE_HEAP_MGR::CreateMultirange(VIDMM_RECYCLE_MULTIRANGE_STATE,VIDMM_RECYCLE_BLOCK *,unsigned __int64,unsigned __int64)
0x1400f455c  mov     rcx, rsi; this
0x1400f455f  mov     r13, rax
0x1400f4562  mov     [rax+40h], r15
0x1400f4566  mov     [rax+48h], rbx
0x1400f456a  mov     r8, [rdi+20h]; unsigned __int64
0x1400f456e  mov     rdx, [rsi+20h]; unsigned __int64
0x1400f4572  call    ?ShrinkTo@VIDMM_RECYCLE_MULTIRANGE@@QEAAX_K0@Z; VIDMM_RECYCLE_MULTIRANGE::ShrinkTo(unsigned __int64,unsigned __int64)
0x1400f4577  mov     eax, [r13+90h]
0x1400f457e  test    eax, eax
0x1400f4580  jz      loc_1400F466F
0x1400f4586  sub     eax, 1
0x1400f4589  jnz     loc_1400F461D
0x1400f458f  mov     [r15+90h], r13
0x1400f4596  cmp     r15, [r13+48h]
0x1400f459a  jz      short loc_1400F45EE
0x1400f459c  mov     rdx, [r15+78h]
0x1400f45a0  mov     rcx, [r15+48h]
0x1400f45a4  xor     r15d, r15d
0x1400f45a7  add     rcx, 48h ; 'H'
0x1400f45ab  cmp     rdx, rcx
0x1400f45ae  lea     rax, [rdx-78h]
0x1400f45b2  cmovnz  r15, rax
0x1400f45b6  jmp     short loc_1400F4577
0x1400f45b8  mov     r8, r10; unsigned __int64
0x1400f45bb  mov     rdx, r9; unsigned __int64
0x1400f45be  mov     rcx, rsi; this
0x1400f45c1  call    ?ShrinkTo@VIDMM_RECYCLE_MULTIRANGE@@QEAAX_K0@Z; VIDMM_RECYCLE_MULTIRANGE::ShrinkTo(unsigned __int64,unsigned __int64)
0x1400f45c6  mov     eax, [rdi+40h]
0x1400f45c9  sub     eax, r13d
0x1400f45cc  jz      loc_1400F4698
0x1400f45d2  cmp     eax, 1
0x1400f45d5  jz      loc_1400F4688
0x1400f45db  mov     r8, rsi
0x1400f45de  mov     edx, r14d
0x1400f45e1  mov     rcx, rbp
0x1400f45e4  call    ?AddMultirangeToTree@VIDMM_RECYCLE_HEAP@@QEAAXW4VIDMM_RECYCLE_HEAP_TREE@@PEAVVIDMM_RECYCLE_MULTIRANGE@@@Z; VIDMM_RECYCLE_HEAP::AddMultirangeToTree(VIDMM_RECYCLE_HEAP_TREE,VIDMM_RECYCLE_MULTIRANGE *)
0x1400f45e9  jmp     loc_1400F4477
0x1400f45ee  mov     ecx, [rdi+40h]
0x1400f45f1  sub     ecx, 4
0x1400f45f4  jz      loc_1400F467B
0x1400f45fa  cmp     ecx, 1
0x1400f45fd  jnz     short loc_1400F460A
0x1400f45ff  mov     qword ptr [rdi+90h], 0
0x1400f460a  mov     r8, rsi
0x1400f460d  mov     edx, r14d
0x1400f4610  mov     rcx, rbp
0x1400f4613  call    ?AddMultirangeToTree@VIDMM_RECYCLE_HEAP@@QEAAXW4VIDMM_RECYCLE_HEAP_TREE@@PEAVVIDMM_RECYCLE_MULTIRANGE@@@Z; VIDMM_RECYCLE_HEAP::AddMultirangeToTree(VIDMM_RECYCLE_HEAP_TREE,VIDMM_RECYCLE_MULTIRANGE *)
0x1400f4618  mov     r8, r13
0x1400f461b  jmp     short loc_1400F45DE
0x1400f461d  cmp     eax, 1
0x1400f4620  jnz     loc_1400F4596
0x1400f4626  mov     [r15+98h], r13
0x1400f462d  jmp     loc_1400F4596
0x1400f4632  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400f4639  mov     [rax], r15d
0x1400f463c  xor     ecx, ecx
0x1400f463e  mov     [rsp+68h+var_40], 0
0x1400f4647  mov     edx, 10Eh
0x1400f464c  mov     [rsp+68h+var_48], rbx
0x1400f4651  lea     r9d, [rcx+10h]
0x1400f4655  lea     r8d, [rcx+34h]
0x1400f4659  call    cs:__imp_WdLogSingleEntry5
0x1400f4660  nop     dword ptr [rax+rax+00h]
0x1400f4665  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400f466f  mov     [r15+88h], r13
0x1400f4676  jmp     loc_1400F4596
0x1400f467b  mov     qword ptr [rdi+98h], 0
0x1400f4686  jmp     short loc_1400F460A
0x1400f4688  mov     qword ptr [rdi+90h], 0
0x1400f4693  jmp     loc_1400F45DB
0x1400f4698  mov     qword ptr [rdi+98h], 0
0x1400f46a3  jmp     loc_1400F45DB
```
