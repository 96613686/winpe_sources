# CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Initialize(void)

- ea: `0x140070124`
- end: `0x140070434`
- name: `?Initialize@?$CmsRotatingSkipList@U_RANGE@@USmsAllocationRegionEx@@UOrderByStartOfRange@@URegionLockPolicies@@@@QEAAJXZ`
- size: `784`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation`

## callers

- `0x14015d2f8`

## callees

- `0x140070124`
- `0x1400710d0`
- `0x140072970`
- `0x1400b796c`
- `0x1400c8574`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007017f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400702a5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007017f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400702a5`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140070141`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14007026d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140070141`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14007026d`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14007018d`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400702b3`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14007018d`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400702b3`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400701c8`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400702ee`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400701c8`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400702ee`

## string_xrefs

- `0x140070427`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Initialize(
        unsigned __int16 *a1)
{
  unsigned __int64 v2; // rbp
  const struct std::nothrow_t *v3; // rdx
  unsigned int *v4; // rdi
  struct _NPAGED_LOOKASIDE_LIST *v5; // rcx
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  int v8; // ecx
  unsigned __int64 v9; // rcx
  _QWORD *v10; // rax
  int v11; // eax
  unsigned int v12; // edx
  int v13; // r8d
  __int64 v14; // rax
  unsigned __int64 v15; // rbp
  const struct std::nothrow_t *v16; // rdx
  unsigned int *v17; // rdi
  struct _NPAGED_LOOKASIDE_LIST *v18; // rcx
  _QWORD *v19; // rax
  _QWORD *v20; // rcx
  int v21; // ecx
  unsigned __int64 v22; // rcx
  _QWORD *v23; // rax
  int v24; // eax
  unsigned int v25; // edx
  int v26; // r8d
  __int64 v27; // rax
  unsigned __int16 v28; // r8
  unsigned __int16 i; // ax
  __int64 v30; // rdx
  unsigned __int128 v31; // rax
  unsigned __int64 v32; // kr00_8
  void *v33; // rax
  void *v35; // rcx
  void *v36; // rcx
  void *v37; // rcx

  v2 = 8LL * *a1 + 48;
  v3 = (const struct std::nothrow_t *)(KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  v4 = (unsigned int *)(qword_140262490 + 192LL * (_QWORD)v3);
  if ( v2 > *v4 )
  {
    v4 = 0;
    goto LABEL_16;
  }
  if ( *((_BYTE *)v4 + 8) )
  {
    v5 = (struct _NPAGED_LOOKASIDE_LIST *)(v4 + 16);
    if ( *((_BYTE *)v4 + 9) )
      v6 = ExAllocateFromNPagedLookasideList(v5);
    else
      v6 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v5);
    goto LABEL_6;
  }
  if ( (int)*((_QWORD *)v4 + 11) <= (int)HIDWORD(*((_QWORD *)v4 + 11)) )
    goto LABEL_13;
  v8 = _InterlockedDecrement((volatile signed __int32 *)v4 + 22);
  if ( v8 >= (int)v4[23] && v8 >= 0 )
  {
    v6 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v4 + 4);
LABEL_6:
    v7 = v6;
    goto LABEL_12;
  }
  v7 = 0;
  _InterlockedIncrement((volatile signed __int32 *)v4 + 22);
LABEL_12:
  if ( v7 )
  {
LABEL_19:
    *v7 = v4;
    v7 += 2;
    goto LABEL_20;
  }
LABEL_13:
  if ( v4 )
  {
    v9 = v4[1];
    goto LABEL_17;
  }
LABEL_16:
  v9 = v2 + 16;
LABEL_17:
  v10 = operator new(v9, v3);
  v7 = v10;
  if ( ((unsigned __int8)v10 & 0xF) != 0 )
    goto LABEL_64;
  if ( v10 )
    goto LABEL_19;
LABEL_20:
  if ( v7 )
  {
    v11 = *a1;
    v12 = 0;
    *v7 = 0;
    v13 = v11;
    v7[1] = 0;
    v7[2] = 0;
    *((_WORD *)v7 + 12) = 0;
    v7[4] = 0;
    v7[5] = 0;
    if ( v11 )
    {
      do
      {
        v14 = v12++;
        v7[v14 + 6] = 0;
      }
      while ( (int)v12 < v13 );
    }
  }
  else
  {
    v7 = 0;
  }
  *((_QWORD *)a1 + 2) = v7;
  if ( !v7 )
    goto LABEL_57;
  v15 = 8LL * *a1 + 48;
  v16 = (const struct std::nothrow_t *)(KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  v17 = (unsigned int *)(qword_140262490 + 192LL * (_QWORD)v16);
  if ( v15 > *v17 )
  {
    v17 = 0;
    goto LABEL_41;
  }
  if ( *((_BYTE *)v17 + 8) )
  {
    v18 = (struct _NPAGED_LOOKASIDE_LIST *)(v17 + 16);
    if ( *((_BYTE *)v17 + 9) )
      v19 = ExAllocateFromNPagedLookasideList(v18);
    else
      v19 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v18);
    goto LABEL_31;
  }
  if ( (int)*((_QWORD *)v17 + 11) <= (int)HIDWORD(*((_QWORD *)v17 + 11)) )
    goto LABEL_38;
  v21 = _InterlockedDecrement((volatile signed __int32 *)v17 + 22);
  if ( v21 >= (int)v17[23] && v21 >= 0 )
  {
    v19 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v17 + 4);
LABEL_31:
    v20 = v19;
    goto LABEL_37;
  }
  v20 = 0;
  _InterlockedIncrement((volatile signed __int32 *)v17 + 22);
LABEL_37:
  if ( !v20 )
  {
LABEL_38:
    if ( v17 )
    {
      v22 = v17[1];
      goto LABEL_42;
    }
LABEL_41:
    v22 = v15 + 16;
LABEL_42:
    v23 = operator new(v22, v16);
    v20 = v23;
    if ( ((unsigned __int8)v23 & 0xF) == 0 )
    {
      if ( !v23 )
        goto LABEL_45;
      goto LABEL_44;
    }
LABEL_64:
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  }
LABEL_44:
  *v20 = v17;
  v20 += 2;
LABEL_45:
  if ( v20 )
  {
    v24 = *a1;
    v25 = 0;
    *v20 = 0;
    v26 = v24;
    v20[1] = 0;
    v20[2] = 0;
    *((_WORD *)v20 + 12) = 0;
    v20[4] = 0;
    v20[5] = 0;
    if ( v24 )
    {
      do
      {
        v27 = v25++;
        v20[v27 + 6] = 0;
      }
      while ( (int)v25 < v26 );
    }
  }
  else
  {
    v20 = 0;
  }
  *((_QWORD *)a1 + 3) = v20;
  if ( v20 )
  {
    v28 = 0;
    *(_QWORD *)(*((_QWORD *)a1 + 2) + 32LL) = v20;
    *(_QWORD *)(*((_QWORD *)a1 + 3) + 40LL) = *((_QWORD *)a1 + 2);
    for ( i = *a1; v28 < *a1; i = *a1 )
    {
      v30 = v28++;
      *(_QWORD *)(*((_QWORD *)a1 + 2) + 8 * v30 + 48) = *((_QWORD *)a1 + 3);
    }
    v32 = i;
    v31 = i * (unsigned __int128)8uLL;
    if ( !is_mul_ok(v32, 8u) )
      *(_QWORD *)&v31 = -1;
    v33 = operator new(v31, *((const struct std::nothrow_t **)&v31 + 1));
    *((_QWORD *)a1 + 13) = v33;
    if ( v33 )
      return 0;
  }
LABEL_57:
  v35 = (void *)*((_QWORD *)a1 + 2);
  if ( v35 )
  {
    CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Node::`scalar deleting destructor'(v35);
    *((_QWORD *)a1 + 2) = 0;
  }
  v36 = (void *)*((_QWORD *)a1 + 3);
  if ( v36 )
  {
    CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Node::`scalar deleting destructor'(v36);
    *((_QWORD *)a1 + 3) = 0;
  }
  v37 = (void *)*((_QWORD *)a1 + 13);
  if ( v37 )
  {
    operator delete(v37);
    *((_QWORD *)a1 + 13) = 0;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x140070124  push    rbx
0x140070126  push    rbp
0x140070127  push    rsi
0x140070128  push    rdi
0x140070129  push    r14
0x14007012b  push    r15
0x14007012d  sub     rsp, 28h
0x140070131  movzx   eax, word ptr [rcx]
0x140070134  mov     rsi, rcx
0x140070137  xor     ecx, ecx; ProcNumber
0x140070139  lea     rbp, ds:30h[rax*8]
0x140070141  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140070148  nop     dword ptr [rax+rax+00h]
0x14007014d  xor     edx, edx; struct std::nothrow_t *
0x14007014f  or      r15, 0FFFFFFFFFFFFFFFFh
0x140070153  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140070159  xor     ebx, ebx
0x14007015b  lea     rdi, [rdx+rdx*2]
0x14007015f  shl     rdi, 6
0x140070163  add     rdi, cs:qword_140262490
0x14007016a  mov     eax, [rdi]
0x14007016c  cmp     rbp, rax
0x14007016f  ja      short loc_1400701EE
0x140070171  cmp     [rdi+8], bl
0x140070174  jz      short loc_14007019E
0x140070176  lea     rcx, [rdi+40h]; Lookaside
0x14007017a  cmp     [rdi+9], bl
0x14007017d  jz      short loc_14007018D
0x14007017f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140070186  nop     dword ptr [rax+rax+00h]
0x14007018b  jmp     short loc_140070199
0x14007018d  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140070194  nop     dword ptr [rax+rax+00h]
0x140070199  mov     rcx, rax
0x14007019c  jmp     short loc_1400701DF
0x14007019e  mov     rcx, [rdi+58h]
0x1400701a2  mov     rax, rcx
0x1400701a5  sar     rax, 20h
0x1400701a9  cmp     ecx, eax
0x1400701ab  jle     short loc_1400701E4
0x1400701ad  nop
0x1400701ae  mov     ecx, r15d
0x1400701b1  lock xadd [rdi+58h], ecx
0x1400701b6  nop
0x1400701b7  dec     ecx
0x1400701b9  mov     eax, [rdi+5Ch]
0x1400701bc  cmp     ecx, eax
0x1400701be  jl      short loc_1400701D6
0x1400701c0  test    ecx, ecx
0x1400701c2  js      short loc_1400701D6
0x1400701c4  lea     rcx, [rdi+40h]; ListHead
0x1400701c8  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400701cf  nop     dword ptr [rax+rax+00h]
0x1400701d4  jmp     short loc_140070199
0x1400701d6  mov     rcx, rbx
0x1400701d9  nop
0x1400701da  lock inc dword ptr [rdi+58h]
0x1400701de  nop
0x1400701df  test    rcx, rcx
0x1400701e2  jnz     short loc_14007020A
0x1400701e4  test    rdi, rdi
0x1400701e7  jz      short loc_1400701F1
0x1400701e9  mov     ecx, [rdi+4]
0x1400701ec  jmp     short loc_1400701F5
0x1400701ee  mov     rdi, rbx
0x1400701f1  lea     rcx, [rbp+10h]; unsigned __int64
0x1400701f5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400701fa  mov     rcx, rax
0x1400701fd  test    al, 0Fh
0x1400701ff  jnz     loc_140070427
0x140070205  test    rax, rax
0x140070208  jz      short loc_140070211
0x14007020a  mov     [rcx], rdi
0x14007020d  add     rcx, 10h
0x140070211  mov     r14d, 1
0x140070217  test    rcx, rcx
0x14007021a  jz      short loc_140070250
0x14007021c  movzx   eax, word ptr [rsi]
0x14007021f  mov     edx, ebx
0x140070221  mov     [rcx], rbx
0x140070224  mov     r8d, eax
0x140070227  mov     [rcx+8], rbx
0x14007022b  mov     [rcx+10h], rbx
0x14007022f  mov     [rcx+18h], bx
0x140070233  mov     [rcx+20h], rbx
0x140070237  mov     [rcx+28h], rbx
0x14007023b  test    eax, eax
0x14007023d  jz      short loc_140070253
0x14007023f  mov     eax, edx
0x140070241  add     edx, r14d
0x140070244  mov     [rcx+rax*8+30h], rbx
0x140070249  cmp     edx, r8d
0x14007024c  jl      short loc_14007023F
0x14007024e  jmp     short loc_140070253
0x140070250  mov     rcx, rbx
0x140070253  mov     [rsi+10h], rcx
0x140070257  test    rcx, rcx
0x14007025a  jz      loc_1400703EA
0x140070260  movzx   eax, word ptr [rsi]
0x140070263  xor     ecx, ecx; ProcNumber
0x140070265  lea     rbp, ds:30h[rax*8]
0x14007026d  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140070274  nop     dword ptr [rax+rax+00h]
0x140070279  xor     edx, edx; struct std::nothrow_t *
0x14007027b  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140070281  lea     rdi, [rdx+rdx*2]
0x140070285  shl     rdi, 6
0x140070289  add     rdi, cs:qword_140262490
0x140070290  mov     eax, [rdi]
0x140070292  cmp     rbp, rax
0x140070295  ja      short loc_140070314
0x140070297  cmp     [rdi+8], bl
0x14007029a  jz      short loc_1400702C4
0x14007029c  lea     rcx, [rdi+40h]; Lookaside
0x1400702a0  cmp     [rdi+9], bl
0x1400702a3  jz      short loc_1400702B3
0x1400702a5  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400702ac  nop     dword ptr [rax+rax+00h]
0x1400702b1  jmp     short loc_1400702BF
0x1400702b3  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400702ba  nop     dword ptr [rax+rax+00h]
0x1400702bf  mov     rcx, rax
0x1400702c2  jmp     short loc_140070305
0x1400702c4  mov     rcx, [rdi+58h]
0x1400702c8  mov     rax, rcx
0x1400702cb  sar     rax, 20h
0x1400702cf  cmp     ecx, eax
0x1400702d1  jle     short loc_14007030A
0x1400702d3  nop
0x1400702d4  mov     ecx, r15d
0x1400702d7  lock xadd [rdi+58h], ecx
0x1400702dc  nop
0x1400702dd  dec     ecx
0x1400702df  mov     eax, [rdi+5Ch]
0x1400702e2  cmp     ecx, eax
0x1400702e4  jl      short loc_1400702FC
0x1400702e6  test    ecx, ecx
0x1400702e8  js      short loc_1400702FC
0x1400702ea  lea     rcx, [rdi+40h]; ListHead
0x1400702ee  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400702f5  nop     dword ptr [rax+rax+00h]
0x1400702fa  jmp     short loc_1400702BF
0x1400702fc  mov     rcx, rbx
0x1400702ff  nop
0x140070300  lock inc dword ptr [rdi+58h]
0x140070304  nop
0x140070305  test    rcx, rcx
0x140070308  jnz     short loc_140070330
0x14007030a  test    rdi, rdi
0x14007030d  jz      short loc_140070317
0x14007030f  mov     ecx, [rdi+4]
0x140070312  jmp     short loc_14007031B
0x140070314  mov     rdi, rbx
0x140070317  lea     rcx, [rbp+10h]; unsigned __int64
0x14007031b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140070320  mov     rcx, rax
0x140070323  test    al, 0Fh
0x140070325  jnz     loc_140070427
0x14007032b  test    rax, rax
0x14007032e  jz      short loc_140070337
0x140070330  mov     [rcx], rdi
0x140070333  add     rcx, 10h
0x140070337  test    rcx, rcx
0x14007033a  jz      short loc_140070370
0x14007033c  movzx   eax, word ptr [rsi]
0x14007033f  mov     edx, ebx
0x140070341  mov     [rcx], rbx
0x140070344  mov     r8d, eax
0x140070347  mov     [rcx+8], rbx
0x14007034b  mov     [rcx+10h], rbx
0x14007034f  mov     [rcx+18h], bx
0x140070353  mov     [rcx+20h], rbx
0x140070357  mov     [rcx+28h], rbx
0x14007035b  test    eax, eax
0x14007035d  jz      short loc_140070373
0x14007035f  mov     eax, edx
0x140070361  add     edx, r14d
0x140070364  mov     [rcx+rax*8+30h], rbx
0x140070369  cmp     edx, r8d
0x14007036c  jl      short loc_14007035F
0x14007036e  jmp     short loc_140070373
0x140070370  mov     rcx, rbx
0x140070373  mov     [rsi+18h], rcx
0x140070377  test    rcx, rcx
0x14007037a  jz      short loc_1400703EA
0x14007037c  mov     rax, [rsi+10h]
0x140070380  movzx   r8d, bx
0x140070384  mov     [rax+20h], rcx
0x140070388  mov     rax, [rsi+10h]
0x14007038c  mov     rcx, [rsi+18h]
0x140070390  mov     [rcx+28h], rax
0x140070394  movzx   eax, word ptr [rsi]
0x140070397  cmp     bx, ax
0x14007039a  jnb     short loc_1400703BA
0x14007039c  mov     rax, [rsi+18h]
0x1400703a0  mov     rcx, [rsi+10h]
0x1400703a4  movzx   edx, r8w; struct std::nothrow_t *
0x1400703a8  add     r8w, r14w
0x1400703ac  mov     [rcx+rdx*8+30h], rax
0x1400703b1  movzx   eax, word ptr [rsi]
0x1400703b4  cmp     r8w, ax
0x1400703b8  jb      short loc_14007039C
0x1400703ba  movzx   ecx, ax
0x1400703bd  mov     eax, 8
0x1400703c2  mul     rcx
0x1400703c5  cmovb   rax, r15
0x1400703c9  mov     rcx, rax; unsigned __int64
0x1400703cc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400703d1  mov     [rsi+68h], rax
0x1400703d5  test    rax, rax
0x1400703d8  jz      short loc_1400703EA
0x1400703da  xor     eax, eax
0x1400703dc  add     rsp, 28h
0x1400703e0  pop     r15
0x1400703e2  pop     r14
0x1400703e4  pop     rdi
0x1400703e5  pop     rsi
0x1400703e6  pop     rbp
0x1400703e7  pop     rbx
0x1400703e8  retn
0x1400703ea  mov     rcx, [rsi+10h]; void *
0x1400703ee  test    rcx, rcx
0x1400703f1  jz      short loc_1400703FC
0x1400703f3  call    ??_GNode@?$CmsRotatingSkipList@U_RANGE@@USmsAllocationRegionEx@@UOrderByStartOfRange@@URegionLockPolicies@@@@AEAAPEAXI@Z; CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Node::`scalar deleting destructor'(uint)
0x1400703f8  mov     [rsi+10h], rbx
0x1400703fc  mov     rcx, [rsi+18h]; void *
0x140070400  test    rcx, rcx
0x140070403  jz      short loc_14007040E
0x140070405  call    ??_GNode@?$CmsRotatingSkipList@U_RANGE@@USmsAllocationRegionEx@@UOrderByStartOfRange@@URegionLockPolicies@@@@AEAAPEAXI@Z; CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Node::`scalar deleting destructor'(uint)
0x14007040a  mov     [rsi+18h], rbx
0x14007040e  mov     rcx, [rsi+68h]; void *
0x140070412  test    rcx, rcx
0x140070415  jz      short loc_140070420
0x140070417  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14007041c  mov     [rsi+68h], rbx
0x140070420  mov     eax, 0C000009Ah
0x140070425  jmp     short loc_1400703DC
0x140070427  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x14007042e  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
```
