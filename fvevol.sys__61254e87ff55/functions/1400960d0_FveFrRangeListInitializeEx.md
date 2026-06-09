# FveFrRangeListInitializeEx

- ea: `0x1400960d0`
- end: `0x1400962d4`
- name: `FveFrRangeListInitializeEx`
- size: `516`
- prototype: `__int64 __fastcall(POOL_TYPE PoolType, ULONG Tag, void *)`
- caller_count: `12`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002f3d8`
- `0x1400520c4`
- `0x14005881c`
- `0x1400593a4`
- `0x140059594`
- `0x140059844`
- `0x140063f30`
- `0x140078a04`
- `0x1400797c0`
- `0x140095cac`
- `0x140095ec0`
- `0x1400962dc`

## callees

- `0x140018b38`
- `0x140018ba8`
- `0x140023040`
- `0x1400960d0`
- `0x14009657c`

## import_xrefs

- `ntoskrnl!ExInitializeLookasideListEx` at `0x14009621f`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14009621f`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400961b8`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400961b8`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140096283`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140096283`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009617e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009619c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400961cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009617e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009619c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400961cf`
- `ntoskrnl!ExAllocatePool2` at `0x140096148`
- `ntoskrnl!ExAllocatePool2` at `0x14009624e`
- `ntoskrnl!ExAllocatePool2` at `0x1400962ae`
- `ntoskrnl!ExAllocatePool2` at `0x140096148`
- `ntoskrnl!ExAllocatePool2` at `0x14009624e`
- `ntoskrnl!ExAllocatePool2` at `0x1400962ae`

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
0x1400960d0  push    rbx
0x1400960d2  push    rbp
0x1400960d3  push    rsi
0x1400960d4  push    rdi
0x1400960d5  push    r12
0x1400960d7  push    r14
0x1400960d9  push    r15
0x1400960db  sub     rsp, 40h
0x1400960df  mov     r14d, ecx
0x1400960e2  mov     r12b, r9b
0x1400960e5  mov     rcx, r8; void *
0x1400960e8  mov     rbx, r8
0x1400960eb  mov     esi, edx
0x1400960ed  xor     r15b, r15b
0x1400960f0  call    FveFrRangeListFree
0x1400960f5  mov     dword ptr [rbx+18h], 0
0x1400960fc  lea     rax, [rbx+48h]
0x140096100  mov     qword ptr [rbx+20h], 0
0x140096108  mov     ebp, 102h
0x14009610d  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x140096115  mov     ecx, ebp
0x140096117  mov     qword ptr [rbx+30h], 0
0x14009611f  mov     [rbx+38h], r14d
0x140096123  mov     [rbx+3Ch], esi
0x140096126  mov     [rax+8], rax
0x14009612a  mov     [rax], rax
0x14009612d  mov     qword ptr [rbx+10h], 38h ; '8'
0x140096135  cmp     r14d, 1
0x140096139  jz      short loc_140096140
0x14009613b  mov     ecx, 42h ; 'B'
0x140096140  mov     r8d, esi
0x140096143  mov     edx, 60h ; '`'
0x140096148  call    cs:__imp_ExAllocatePool2
0x14009614f  nop     dword ptr [rax+rax+00h]
0x140096154  mov     [rbx+8], rax
0x140096158  mov     rcx, rax; Lookaside
0x14009615b  test    rax, rax
0x14009615e  jnz     loc_1400961FB
0x140096164  mov     edi, 0C000009Ah
0x140096169  mov     rcx, [rbx+40h]
0x14009616d  test    rcx, rcx
0x140096170  jz      short loc_140096192
0x140096172  call    FveRangeListFree
0x140096177  mov     edx, [rbx+38h]; Tag
0x14009617a  mov     rcx, [rbx+40h]; P
0x14009617e  call    cs:__imp_ExFreePoolWithTag
0x140096185  nop     dword ptr [rax+rax+00h]
0x14009618a  mov     qword ptr [rbx+40h], 0
0x140096192  mov     rcx, [rbx]; P
0x140096195  test    rcx, rcx
0x140096198  jz      short loc_1400961AF
0x14009619a  mov     edx, esi; Tag
0x14009619c  call    cs:__imp_ExFreePoolWithTag
0x1400961a3  nop     dword ptr [rax+rax+00h]
0x1400961a8  mov     qword ptr [rbx], 0
0x1400961af  test    r15b, r15b
0x1400961b2  jz      short loc_1400961C4
0x1400961b4  mov     rcx, [rbx+8]; Lookaside
0x1400961b8  call    cs:__imp_ExDeleteLookasideListEx
0x1400961bf  nop     dword ptr [rax+rax+00h]
0x1400961c4  mov     rcx, [rbx+8]; P
0x1400961c8  test    rcx, rcx
0x1400961cb  jz      short loc_1400961DB
0x1400961cd  mov     edx, esi; Tag
0x1400961cf  call    cs:__imp_ExFreePoolWithTag
0x1400961d6  nop     dword ptr [rax+rax+00h]
0x1400961db  xor     edx, edx; Val
0x1400961dd  mov     rcx, rbx; void *
0x1400961e0  lea     r8d, [rdx+58h]; Size
0x1400961e4  call    memset
0x1400961e9  mov     eax, edi
0x1400961eb  add     rsp, 40h
0x1400961ef  pop     r15
0x1400961f1  pop     r14
0x1400961f3  pop     r12
0x1400961f5  pop     rdi
0x1400961f6  pop     rsi
0x1400961f7  pop     rbp
0x1400961f8  pop     rbx
0x1400961f9  retn
0x1400961fb  xor     eax, eax
0x1400961fd  mov     r9d, r14d; PoolType
0x140096200  mov     [rsp+78h+Depth], ax; Depth
0x140096205  xor     r8d, r8d; Free
0x140096208  mov     rax, [rbx+10h]
0x14009620c  xor     edx, edx; Allocate
0x14009620e  mov     [rsp+78h+Tag], esi; Tag
0x140096212  mov     [rsp+78h+Size], rax; Size
0x140096217  mov     [rsp+78h+Flags], 0; Flags
0x14009621f  call    cs:__imp_ExInitializeLookasideListEx
0x140096226  nop     dword ptr [rax+rax+00h]
0x14009622b  mov     edi, eax
0x14009622d  test    eax, eax
0x14009622f  js      loc_140096169
0x140096235  mov     r15b, 1
0x140096238  mov     rcx, rbp
0x14009623b  cmp     r14d, 1
0x14009623f  jz      short loc_140096246
0x140096241  mov     ecx, 42h ; 'B'
0x140096246  mov     r8d, esi
0x140096249  mov     edx, 68h ; 'h'
0x14009624e  call    cs:__imp_ExAllocatePool2
0x140096255  nop     dword ptr [rax+rax+00h]
0x14009625a  mov     [rbx], rax
0x14009625d  test    rax, rax
0x140096260  jz      loc_140096164
0x140096266  lea     r9, FveFrpFree; FreeRoutine
0x14009626d  mov     qword ptr [rsp+78h+Flags], rbx; TableContext
0x140096272  lea     r8, FveFrpAllocate; AllocateRoutine
0x140096279  mov     rcx, rax; Table
0x14009627c  lea     rdx, FveFrpCompare; CompareRoutine
0x140096283  call    cs:__imp_RtlInitializeGenericTableAvl
0x14009628a  nop     dword ptr [rax+rax+00h]
0x14009628f  test    r12b, r12b
0x140096292  jz      loc_1400961E9
0x140096298  cmp     r14d, 1
0x14009629c  jz      short loc_1400962A3
0x14009629e  mov     ebp, 42h ; 'B'
0x1400962a3  mov     r8d, esi
0x1400962a6  mov     edx, 14h
0x1400962ab  mov     rcx, rbp
0x1400962ae  call    cs:__imp_ExAllocatePool2
0x1400962b5  nop     dword ptr [rax+rax+00h]
0x1400962ba  mov     [rbx+40h], rax
0x1400962be  test    rax, rax
0x1400962c1  jz      loc_140096164
0x1400962c7  mov     rcx, rax
0x1400962ca  call    FveRangeListInitialize
0x1400962cf  jmp     loc_1400961E9
```
