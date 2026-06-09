# CmsRangeAndCountMap::PreAllocateRangeEntry(_SmsPreAllocatedRow *)

- ea: `0x140070b98`
- end: `0x140070e2a`
- name: `?PreAllocateRangeEntry@CmsRangeAndCountMap@@QEAAJPEAU_SmsPreAllocatedRow@@@Z`
- size: `658`
- prototype: `__int64 __fastcall(CmsRangeAndCountMap *__hidden this, struct _SmsPreAllocatedRow *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400c67ac`

## callees

- `0x140070b98`
- `0x1400710d0`
- `0x1400c8574`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140070d72`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140070dd5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140070d72`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140070dd5`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140070bcf`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140070c03`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140070bcf`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140070c03`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6b82`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6b94`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6b82`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6b94`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140070d8f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140070df2`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140070d8f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140070df2`

## string_xrefs

- `0x1401f6ba6`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsRangeAndCountMap::PreAllocateRangeEntry(
        CmsRangeAndCountMap *this,
        struct _SmsPreAllocatedRow *a2)
{
  const struct std::nothrow_t *v3; // rdx
  __int64 v4; // rbx
  unsigned __int64 v5; // rcx
  const struct std::nothrow_t *v6; // rdx
  __int64 v7; // rbx
  unsigned __int64 v8; // rcx
  int v9; // ecx
  __m256i *v10; // rax
  __int16 v11; // bx
  int v13; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v14; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v15; // rcx
  __m256i v16; // [rsp+20h] [rbp-28h] BYREF

  memset(&v16, 0, 24);
  if ( CmsAvlTableLite::SizeOfAllocationsOnLookaside2 < 0x40 )
  {
    v11 = 0x8000;
    v10 = (__m256i *)operator new(0x40u, a2);
    goto LABEL_16;
  }
  if ( CmsAvlTableLite::SizeOfAllocationsOnLookaside1 >= 0x40 )
  {
    v3 = (const struct std::nothrow_t *)(KeGetCurrentProcessorNumberEx(0) % NumProcessors);
    v4 = qword_140262458 + 192LL * (_QWORD)v3;
    if ( *(_DWORD *)v4 < 0x40u )
    {
      v4 = 0;
      goto LABEL_5;
    }
    if ( *(_BYTE *)(v4 + 8) )
    {
      v14 = (struct _NPAGED_LOOKASIDE_LIST *)(v4 + 64);
      if ( *(_BYTE *)(v4 + 9) )
        v10 = (__m256i *)ExAllocateFromNPagedLookasideList(v14);
      else
        v10 = (__m256i *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v14);
    }
    else
    {
      if ( (int)*(_QWORD *)(v4 + 88) <= (int)HIDWORD(*(_QWORD *)(v4 + 88)) )
        goto LABEL_31;
      v9 = _InterlockedDecrement((volatile signed __int32 *)(v4 + 88));
      if ( v9 < *(_DWORD *)(v4 + 92) || v9 < 0 )
      {
        v10 = 0;
        _InterlockedIncrement((volatile signed __int32 *)(v4 + 88));
      }
      else
      {
        v10 = (__m256i *)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v4 + 64));
      }
    }
    if ( v10 )
    {
LABEL_14:
      v10->m256i_i64[0] = v4;
      v10 = (__m256i *)((char *)v10 + 16);
LABEL_15:
      v11 = 0x2000;
      goto LABEL_16;
    }
LABEL_31:
    if ( v4 )
    {
      v5 = *(unsigned int *)(v4 + 4);
LABEL_33:
      v10 = (__m256i *)operator new(v5, v3);
      if ( ((unsigned __int8)v10 & 0xF) == 0 )
      {
        if ( !v10 )
          goto LABEL_15;
        goto LABEL_14;
      }
LABEL_47:
      MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
    }
LABEL_5:
    v5 = 80;
    goto LABEL_33;
  }
  KeGetCurrentProcessorNumberEx(0);
  v7 = qword_140262460;
  if ( *(_DWORD *)qword_140262460 < 0x40u )
  {
    v7 = 0;
    goto LABEL_8;
  }
  if ( *(_BYTE *)(qword_140262460 + 8) )
  {
    v15 = (struct _NPAGED_LOOKASIDE_LIST *)(qword_140262460 + 64);
    if ( *(_BYTE *)(qword_140262460 + 9) )
      v10 = (__m256i *)ExAllocateFromNPagedLookasideList(v15);
    else
      v10 = (__m256i *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v15);
  }
  else
  {
    if ( (int)*(_QWORD *)(qword_140262460 + 88) <= (int)HIDWORD(*(_QWORD *)(qword_140262460 + 88)) )
      goto LABEL_40;
    v13 = _InterlockedDecrement((volatile signed __int32 *)(qword_140262460 + 88));
    if ( v13 < *(_DWORD *)(v7 + 92) || v13 < 0 )
    {
      v10 = 0;
      _InterlockedIncrement((volatile signed __int32 *)(v7 + 88));
    }
    else
    {
      v10 = (__m256i *)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v7 + 64));
    }
  }
  if ( !v10 )
  {
LABEL_40:
    if ( v7 )
    {
      v8 = *(unsigned int *)(v7 + 4);
LABEL_42:
      v10 = (__m256i *)operator new(v8, v6);
      if ( ((unsigned __int8)v10 & 0xF) != 0 )
        goto LABEL_47;
      if ( !v10 )
        goto LABEL_25;
      goto LABEL_24;
    }
LABEL_8:
    v8 = 80;
    goto LABEL_42;
  }
LABEL_24:
  v10->m256i_i64[0] = v7;
  v10 = (__m256i *)((char *)v10 + 16);
LABEL_25:
  v11 = 0x4000;
LABEL_16:
  if ( !v10 )
    return 3221225626LL;
  v10->m256i_i16[14] = 0;
  v10[1] = v16;
  v10->m256i_i16[13] = 4128;
  v10->m256i_i16[14] |= v11;
  v10->m256i_i16[15] = 32;
  *((_QWORD *)a2 + 4) = v10;
  *(_DWORD *)a2 = v10->m256i_u8[27];
  *((_QWORD *)a2 + 1) = (char *)v10 + v10->m256i_u8[26];
  *((_WORD *)a2 + 2) = 0;
  *((_DWORD *)a2 + 4) = v10->m256i_u16[15];
  *((_QWORD *)a2 + 3) = (char *)v10 + v10->m256i_u8[26];
  return 0;
}

```

## disassembly

```asm
0x140070b98  mov     [rsp+arg_0], rbx
0x140070b9d  push    rdi
0x140070b9e  sub     rsp, 40h
0x140070ba2  cmp     cs:?SizeOfAllocationsOnLookaside2@CmsAvlTableLite@@2KA, 40h ; '@'; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside2
0x140070ba9  xorps   xmm0, xmm0
0x140070bac  movdqu  xmmword ptr [rsp+48h+var_28+8], xmm0
0x140070bb2  mov     rdi, rdx
0x140070bb5  mov     qword ptr [rsp+48h+var_28], 0
0x140070bbe  jb      loc_140070CF3
0x140070bc4  xor     ecx, ecx; ProcNumber
0x140070bc6  cmp     cs:?SizeOfAllocationsOnLookaside1@CmsAvlTableLite@@2KA, 40h ; '@'; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside1
0x140070bcd  jb      short loc_140070C03
0x140070bcf  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140070bd6  nop     dword ptr [rax+rax+00h]
0x140070bdb  xor     edx, edx; struct std::nothrow_t *
0x140070bdd  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140070be3  lea     rbx, [rdx+rdx*2]
0x140070be7  shl     rbx, 6
0x140070beb  add     rbx, cs:qword_140262458
0x140070bf2  cmp     dword ptr [rbx], 40h ; '@'
0x140070bf5  jnb     short loc_140070C2B
0x140070bf7  xor     ebx, ebx
0x140070bf9  mov     ecx, 50h ; 'P'
0x140070bfe  jmp     loc_140070DAC
0x140070c03  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140070c0a  nop     dword ptr [rax+rax+00h]
0x140070c0f  mov     rbx, cs:qword_140262460
0x140070c16  cmp     dword ptr [rbx], 40h ; '@'
0x140070c19  jnb     loc_140070D07
0x140070c1f  xor     ebx, ebx
0x140070c21  mov     ecx, 50h ; 'P'
0x140070c26  jmp     loc_140070E0F
0x140070c2b  cmp     byte ptr [rbx+8], 0
0x140070c2f  jnz     loc_140070D64
0x140070c35  mov     rcx, [rbx+58h]
0x140070c39  mov     rax, rcx
0x140070c3c  sar     rax, 20h
0x140070c40  cmp     ecx, eax
0x140070c42  jle     loc_140070DA0
0x140070c48  nop
0x140070c49  or      ecx, 0FFFFFFFFh
0x140070c4c  lock xadd [rbx+58h], ecx
0x140070c51  nop
0x140070c52  dec     ecx
0x140070c54  mov     eax, [rbx+5Ch]
0x140070c57  cmp     ecx, eax
0x140070c59  jge     loc_140070D83
0x140070c5f  xor     eax, eax
0x140070c61  nop
0x140070c62  lock inc dword ptr [rbx+58h]
0x140070c66  nop
0x140070c67  test    rax, rax
0x140070c6a  jz      loc_140070DA0
0x140070c70  mov     [rax], rbx
0x140070c73  add     rax, 10h
0x140070c77  mov     ebx, 2000h
0x140070c7c  mov     rcx, rax
0x140070c7f  test    rax, rax
0x140070c82  jz      short loc_140070C8A
0x140070c84  xor     eax, eax
0x140070c86  mov     [rcx+1Ch], ax
0x140070c8a  test    rcx, rcx
0x140070c8d  jz      loc_140070D5D
0x140070c93  movups  xmm0, xmmword ptr [rsp+48h+var_28]
0x140070c98  mov     eax, 20h ; ' '
0x140070c9d  movups  xmmword ptr [rcx+20h], xmm0
0x140070ca1  movups  xmm1, xmmword ptr [rsp+48h+var_28+10h]
0x140070ca6  movups  xmmword ptr [rcx+30h], xmm1
0x140070caa  mov     word ptr [rcx+1Ah], 1020h
0x140070cb0  or      [rcx+1Ch], bx
0x140070cb4  mov     [rcx+1Eh], ax
0x140070cb8  mov     [rdi+20h], rcx
0x140070cbc  movzx   eax, byte ptr [rcx+1Bh]
0x140070cc0  mov     [rdi], eax
0x140070cc2  movzx   eax, byte ptr [rcx+1Ah]
0x140070cc6  add     rax, rcx
0x140070cc9  mov     [rdi+8], rax
0x140070ccd  xor     eax, eax
0x140070ccf  mov     [rdi+4], ax
0x140070cd3  movzx   eax, word ptr [rcx+1Eh]
0x140070cd7  mov     [rdi+10h], eax
0x140070cda  movzx   eax, byte ptr [rcx+1Ah]
0x140070cde  add     rax, rcx
0x140070ce1  mov     [rdi+18h], rax
0x140070ce5  xor     eax, eax
0x140070ce7  mov     rbx, [rsp+48h+arg_0]
0x140070cec  add     rsp, 40h
0x140070cf0  pop     rdi
0x140070cf1  retn
0x140070cf3  mov     ecx, 40h ; '@'; unsigned __int64
0x140070cf8  mov     ebx, 8000h
0x140070cfd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140070d02  jmp     loc_140070C7C
0x140070d07  cmp     byte ptr [rbx+8], 0
0x140070d0b  jnz     loc_140070DC7
0x140070d11  mov     rcx, [rbx+58h]
0x140070d15  mov     rax, rcx
0x140070d18  sar     rax, 20h
0x140070d1c  cmp     ecx, eax
0x140070d1e  jle     loc_140070E03
0x140070d24  nop
0x140070d25  or      ecx, 0FFFFFFFFh
0x140070d28  lock xadd [rbx+58h], ecx
0x140070d2d  nop
0x140070d2e  dec     ecx
0x140070d30  mov     eax, [rbx+5Ch]
0x140070d33  cmp     ecx, eax
0x140070d35  jge     loc_140070DE6
0x140070d3b  xor     eax, eax
0x140070d3d  nop
0x140070d3e  lock inc dword ptr [rbx+58h]
0x140070d42  nop
0x140070d43  test    rax, rax
0x140070d46  jz      loc_140070E03
0x140070d4c  mov     [rax], rbx
0x140070d4f  add     rax, 10h
0x140070d53  mov     ebx, 4000h
0x140070d58  jmp     loc_140070C7C
0x140070d5d  mov     eax, 0C000009Ah
0x140070d62  jmp     short loc_140070CE7
0x140070d64  cmp     byte ptr [rbx+9], 0
0x140070d68  lea     rcx, [rbx+40h]; Lookaside
0x140070d6c  jz      loc_1401F6B82
0x140070d72  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140070d79  nop     dword ptr [rax+rax+00h]
0x140070d7e  jmp     loc_140070C67
0x140070d83  test    ecx, ecx
0x140070d85  js      loc_140070C5F
0x140070d8b  lea     rcx, [rbx+40h]; ListHead
0x140070d8f  call    cs:__imp_ExpInterlockedPopEntrySList
0x140070d96  nop     dword ptr [rax+rax+00h]
0x140070d9b  jmp     loc_140070C67
0x140070da0  test    rbx, rbx
0x140070da3  jz      loc_140070BF9
0x140070da9  mov     ecx, [rbx+4]; unsigned __int64
0x140070dac  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140070db1  test    al, 0Fh
0x140070db3  jnz     loc_1401F6BA6
0x140070db9  test    rax, rax
0x140070dbc  jz      loc_140070C77
0x140070dc2  jmp     loc_140070C70
0x140070dc7  cmp     byte ptr [rbx+9], 0
0x140070dcb  lea     rcx, [rbx+40h]; Lookaside
0x140070dcf  jz      loc_1401F6B94
0x140070dd5  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140070ddc  nop     dword ptr [rax+rax+00h]
0x140070de1  jmp     loc_140070D43
0x140070de6  test    ecx, ecx
0x140070de8  js      loc_140070D3B
0x140070dee  lea     rcx, [rbx+40h]; ListHead
0x140070df2  call    cs:__imp_ExpInterlockedPopEntrySList
0x140070df9  nop     dword ptr [rax+rax+00h]
0x140070dfe  jmp     loc_140070D43
0x140070e03  test    rbx, rbx
0x140070e06  jz      loc_140070C21
0x140070e0c  mov     ecx, [rbx+4]; unsigned __int64
0x140070e0f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140070e14  test    al, 0Fh
0x140070e16  jnz     loc_1401F6BA6
0x140070e1c  test    rax, rax
0x140070e1f  jz      loc_140070D53
0x140070e25  jmp     loc_140070D4C
0x1401f6b82  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1401f6b89  nop     dword ptr [rax+rax+00h]
0x1401f6b8e  nop
0x1401f6b8f  jmp     loc_140070C67
0x1401f6b94  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1401f6b9b  nop     dword ptr [rax+rax+00h]
0x1401f6ba0  nop
0x1401f6ba1  jmp     loc_140070D43
0x1401f6ba6  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x1401f6bad  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
```
