# FveFrRangeListInitializeEx

- ea: `0x140094020`
- end: `0x140094224`
- name: `FveFrRangeListInitializeEx`
- size: `516`
- prototype: `__int64 __fastcall(POOL_TYPE PoolType, ULONG Tag, void *)`
- caller_count: `12`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002e3d8`
- `0x1400500c4`
- `0x1400567d0`
- `0x140057354`
- `0x140057544`
- `0x1400577f4`
- `0x140061eb0`
- `0x1400769d4`
- `0x140077790`
- `0x140093bfc`
- `0x140093e10`
- `0x14009422c`

## callees

- `0x140018128`
- `0x140018198`
- `0x140021d00`
- `0x140094020`
- `0x1400944cc`

## import_xrefs

- `ntoskrnl!ExInitializeLookasideListEx` at `0x14009416f`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14009416f`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x140094108`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x140094108`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1400941d3`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1400941d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400940ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400940ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009411f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400940ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400940ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009411f`
- `ntoskrnl!ExAllocatePool2` at `0x140094098`
- `ntoskrnl!ExAllocatePool2` at `0x14009419e`
- `ntoskrnl!ExAllocatePool2` at `0x1400941fe`
- `ntoskrnl!ExAllocatePool2` at `0x140094098`
- `ntoskrnl!ExAllocatePool2` at `0x14009419e`
- `ntoskrnl!ExAllocatePool2` at `0x1400941fe`

## pseudocode

```c
__int64 __fastcall FveFrRangeListInitializeEx(POOL_TYPE PoolType, ULONG Tag, char *a3, char a4)
{
  char v8; // r15
  __int64 v9; // rbp
  __int64 v10; // rcx
  struct _LOOKASIDE_LIST_EX *Pool2; // rax
  unsigned int v12; // edi
  void *v13; // rcx
  __int64 v15; // rcx
  struct _RTL_AVL_TABLE *v16; // rax
  __int64 v17; // rax

  v8 = 0;
  FveFrRangeListFree(a3);
  *((_DWORD *)a3 + 6) = 0;
  *((_QWORD *)a3 + 4) = 0;
  v9 = 258;
  *((_QWORD *)a3 + 5) = -1;
  v10 = 258;
  *((_QWORD *)a3 + 6) = 0;
  *((_DWORD *)a3 + 14) = PoolType;
  *((_DWORD *)a3 + 15) = Tag;
  *((_QWORD *)a3 + 10) = a3 + 72;
  *((_QWORD *)a3 + 9) = a3 + 72;
  *((_QWORD *)a3 + 2) = 56;
  if ( PoolType != PagedPool )
    v10 = 66;
  Pool2 = (struct _LOOKASIDE_LIST_EX *)ExAllocatePool2(v10, 96, Tag);
  *((_QWORD *)a3 + 1) = Pool2;
  if ( Pool2 )
  {
    v12 = ExInitializeLookasideListEx(Pool2, 0, 0, PoolType, 0, *((_QWORD *)a3 + 2), Tag, 0);
    if ( (v12 & 0x80000000) != 0 )
      goto LABEL_5;
    v8 = 1;
    v15 = 258;
    if ( PoolType != PagedPool )
      v15 = 66;
    v16 = (struct _RTL_AVL_TABLE *)ExAllocatePool2(v15, 104, Tag);
    *(_QWORD *)a3 = v16;
    if ( v16 )
    {
      RtlInitializeGenericTableAvl(v16, FveFrpCompare, FveFrpAllocate, FveFrpFree, a3);
      if ( !a4 )
        return v12;
      if ( PoolType != PagedPool )
        v9 = 66;
      v17 = ExAllocatePool2(v9, 20, Tag);
      *((_QWORD *)a3 + 8) = v17;
      if ( v17 )
      {
        FveRangeListInitialize(v17);
        return v12;
      }
    }
  }
  v12 = -1073741670;
LABEL_5:
  if ( *((_QWORD *)a3 + 8) )
  {
    FveRangeListFree();
    ExFreePoolWithTag(*((PVOID *)a3 + 8), *((_DWORD *)a3 + 14));
    *((_QWORD *)a3 + 8) = 0;
  }
  if ( *(_QWORD *)a3 )
  {
    ExFreePoolWithTag(*(PVOID *)a3, Tag);
    *(_QWORD *)a3 = 0;
  }
  if ( v8 )
    ExDeleteLookasideListEx(*((PLOOKASIDE_LIST_EX *)a3 + 1));
  v13 = (void *)*((_QWORD *)a3 + 1);
  if ( v13 )
    ExFreePoolWithTag(v13, Tag);
  memset(a3, 0, 0x58u);
  return v12;
}

```

## disassembly

```asm
0x140094020  push    rbx
0x140094022  push    rbp
0x140094023  push    rsi
0x140094024  push    rdi
0x140094025  push    r12
0x140094027  push    r14
0x140094029  push    r15
0x14009402b  sub     rsp, 40h
0x14009402f  mov     r14d, ecx
0x140094032  mov     r12b, r9b
0x140094035  mov     rcx, r8; void *
0x140094038  mov     rbx, r8
0x14009403b  mov     esi, edx
0x14009403d  xor     r15b, r15b
0x140094040  call    FveFrRangeListFree
0x140094045  mov     dword ptr [rbx+18h], 0
0x14009404c  lea     rax, [rbx+48h]
0x140094050  mov     qword ptr [rbx+20h], 0
0x140094058  mov     ebp, 102h
0x14009405d  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x140094065  mov     ecx, ebp
0x140094067  mov     qword ptr [rbx+30h], 0
0x14009406f  mov     [rbx+38h], r14d
0x140094073  mov     [rbx+3Ch], esi
0x140094076  mov     [rax+8], rax
0x14009407a  mov     [rax], rax
0x14009407d  mov     qword ptr [rbx+10h], 38h ; '8'
0x140094085  cmp     r14d, 1
0x140094089  jz      short loc_140094090
0x14009408b  mov     ecx, 42h ; 'B'
0x140094090  mov     r8d, esi
0x140094093  mov     edx, 60h ; '`'
0x140094098  call    cs:__imp_ExAllocatePool2
0x14009409f  nop     dword ptr [rax+rax+00h]
0x1400940a4  mov     [rbx+8], rax
0x1400940a8  mov     rcx, rax; Lookaside
0x1400940ab  test    rax, rax
0x1400940ae  jnz     loc_14009414B
0x1400940b4  mov     edi, 0C000009Ah
0x1400940b9  mov     rcx, [rbx+40h]
0x1400940bd  test    rcx, rcx
0x1400940c0  jz      short loc_1400940E2
0x1400940c2  call    FveRangeListFree
0x1400940c7  mov     edx, [rbx+38h]; Tag
0x1400940ca  mov     rcx, [rbx+40h]; P
0x1400940ce  call    cs:__imp_ExFreePoolWithTag
0x1400940d5  nop     dword ptr [rax+rax+00h]
0x1400940da  mov     qword ptr [rbx+40h], 0
0x1400940e2  mov     rcx, [rbx]; P
0x1400940e5  test    rcx, rcx
0x1400940e8  jz      short loc_1400940FF
0x1400940ea  mov     edx, esi; Tag
0x1400940ec  call    cs:__imp_ExFreePoolWithTag
0x1400940f3  nop     dword ptr [rax+rax+00h]
0x1400940f8  mov     qword ptr [rbx], 0
0x1400940ff  test    r15b, r15b
0x140094102  jz      short loc_140094114
0x140094104  mov     rcx, [rbx+8]; Lookaside
0x140094108  call    cs:__imp_ExDeleteLookasideListEx
0x14009410f  nop     dword ptr [rax+rax+00h]
0x140094114  mov     rcx, [rbx+8]; P
0x140094118  test    rcx, rcx
0x14009411b  jz      short loc_14009412B
0x14009411d  mov     edx, esi; Tag
0x14009411f  call    cs:__imp_ExFreePoolWithTag
0x140094126  nop     dword ptr [rax+rax+00h]
0x14009412b  xor     edx, edx; Val
0x14009412d  mov     rcx, rbx; void *
0x140094130  lea     r8d, [rdx+58h]; Size
0x140094134  call    memset
0x140094139  mov     eax, edi
0x14009413b  add     rsp, 40h
0x14009413f  pop     r15
0x140094141  pop     r14
0x140094143  pop     r12
0x140094145  pop     rdi
0x140094146  pop     rsi
0x140094147  pop     rbp
0x140094148  pop     rbx
0x140094149  retn
0x14009414b  xor     eax, eax
0x14009414d  mov     r9d, r14d; PoolType
0x140094150  mov     [rsp+78h+Depth], ax; Depth
0x140094155  xor     r8d, r8d; Free
0x140094158  mov     rax, [rbx+10h]
0x14009415c  xor     edx, edx; Allocate
0x14009415e  mov     [rsp+78h+Tag], esi; Tag
0x140094162  mov     [rsp+78h+Size], rax; Size
0x140094167  mov     [rsp+78h+Flags], 0; Flags
0x14009416f  call    cs:__imp_ExInitializeLookasideListEx
0x140094176  nop     dword ptr [rax+rax+00h]
0x14009417b  mov     edi, eax
0x14009417d  test    eax, eax
0x14009417f  js      loc_1400940B9
0x140094185  mov     r15b, 1
0x140094188  mov     rcx, rbp
0x14009418b  cmp     r14d, 1
0x14009418f  jz      short loc_140094196
0x140094191  mov     ecx, 42h ; 'B'
0x140094196  mov     r8d, esi
0x140094199  mov     edx, 68h ; 'h'
0x14009419e  call    cs:__imp_ExAllocatePool2
0x1400941a5  nop     dword ptr [rax+rax+00h]
0x1400941aa  mov     [rbx], rax
0x1400941ad  test    rax, rax
0x1400941b0  jz      loc_1400940B4
0x1400941b6  lea     r9, FveFrpFree; FreeRoutine
0x1400941bd  mov     qword ptr [rsp+78h+Flags], rbx; TableContext
0x1400941c2  lea     r8, FveFrpAllocate; AllocateRoutine
0x1400941c9  mov     rcx, rax; Table
0x1400941cc  lea     rdx, FveFrpCompare; CompareRoutine
0x1400941d3  call    cs:__imp_RtlInitializeGenericTableAvl
0x1400941da  nop     dword ptr [rax+rax+00h]
0x1400941df  test    r12b, r12b
0x1400941e2  jz      loc_140094139
0x1400941e8  cmp     r14d, 1
0x1400941ec  jz      short loc_1400941F3
0x1400941ee  mov     ebp, 42h ; 'B'
0x1400941f3  mov     r8d, esi
0x1400941f6  mov     edx, 14h
0x1400941fb  mov     rcx, rbp
0x1400941fe  call    cs:__imp_ExAllocatePool2
0x140094205  nop     dword ptr [rax+rax+00h]
0x14009420a  mov     [rbx+40h], rax
0x14009420e  test    rax, rax
0x140094211  jz      loc_1400940B4
0x140094217  mov     rcx, rax
0x14009421a  call    FveRangeListInitialize
0x14009421f  jmp     loc_140094139
```
