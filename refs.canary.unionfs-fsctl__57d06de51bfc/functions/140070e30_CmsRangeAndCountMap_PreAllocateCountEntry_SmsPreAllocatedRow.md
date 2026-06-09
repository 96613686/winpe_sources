# CmsRangeAndCountMap::PreAllocateCountEntry(_SmsPreAllocatedRow *)

- ea: `0x140070e30`
- end: `0x1400710c1`
- name: `?PreAllocateCountEntry@CmsRangeAndCountMap@@QEAAJPEAU_SmsPreAllocatedRow@@@Z`
- size: `657`
- prototype: `__int64 __fastcall(CmsRangeAndCountMap *__hidden this, struct _SmsPreAllocatedRow *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400c67ac`

## callees

- `0x140070e30`
- `0x1400710d0`
- `0x1400c8574`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140071009`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007106c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140071009`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007106c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140070e67`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140070e9b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140070e67`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140070e9b`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6bb4`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6bc6`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6bb4`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f6bc6`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140071026`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140071089`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140071026`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140071089`

## string_xrefs

- `0x1401f6bd8`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsRangeAndCountMap::PreAllocateCountEntry(
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
  _WORD *v10; // rax
  __int16 v11; // bx
  int v13; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v14; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v15; // rcx
  _OWORD v16[2]; // [rsp+20h] [rbp-28h] BYREF

  memset(v16, 0, 24);
  if ( CmsAvlTableLite::SizeOfAllocationsOnLookaside2 < 0x38 )
  {
    v11 = 0x8000;
    v10 = operator new(0x38u, a2);
    goto LABEL_16;
  }
  if ( CmsAvlTableLite::SizeOfAllocationsOnLookaside1 >= 0x38 )
  {
    v3 = (const struct std::nothrow_t *)(KeGetCurrentProcessorNumberEx(0) % NumProcessors);
    v4 = qword_140262458 + 192LL * (_QWORD)v3;
    if ( *(_DWORD *)v4 < 0x38u )
    {
      v4 = 0;
      goto LABEL_5;
    }
    if ( *(_BYTE *)(v4 + 8) )
    {
      v14 = (struct _NPAGED_LOOKASIDE_LIST *)(v4 + 64);
      if ( *(_BYTE *)(v4 + 9) )
        v10 = ExAllocateFromNPagedLookasideList(v14);
      else
        v10 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v14);
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
        v10 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v4 + 64));
      }
    }
    if ( v10 )
    {
LABEL_14:
      *(_QWORD *)v10 = v4;
      v10 += 8;
LABEL_15:
      v11 = 0x2000;
      goto LABEL_16;
    }
LABEL_31:
    if ( v4 )
    {
      v5 = *(unsigned int *)(v4 + 4);
LABEL_33:
      v10 = operator new(v5, v3);
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
    v5 = 72;
    goto LABEL_33;
  }
  KeGetCurrentProcessorNumberEx(0);
  v7 = qword_140262460;
  if ( *(_DWORD *)qword_140262460 < 0x38u )
  {
    v7 = 0;
    goto LABEL_8;
  }
  if ( *(_BYTE *)(qword_140262460 + 8) )
  {
    v15 = (struct _NPAGED_LOOKASIDE_LIST *)(qword_140262460 + 64);
    if ( *(_BYTE *)(qword_140262460 + 9) )
      v10 = ExAllocateFromNPagedLookasideList(v15);
    else
      v10 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v15);
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
      v10 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v7 + 64));
    }
  }
  if ( !v10 )
  {
LABEL_40:
    if ( v7 )
    {
      v8 = *(unsigned int *)(v7 + 4);
LABEL_42:
      v10 = operator new(v8, v6);
      if ( ((unsigned __int8)v10 & 0xF) != 0 )
        goto LABEL_47;
      if ( !v10 )
        goto LABEL_25;
      goto LABEL_24;
    }
LABEL_8:
    v8 = 72;
    goto LABEL_42;
  }
LABEL_24:
  *(_QWORD *)v10 = v7;
  v10 += 8;
LABEL_25:
  v11 = 0x4000;
LABEL_16:
  if ( !v10 )
    return 3221225626LL;
  v10[14] = 0;
  *((_OWORD *)v10 + 2) = v16[0];
  *((_QWORD *)v10 + 6) = *(_QWORD *)&v16[1];
  v10[13] = 4128;
  v10[14] |= v11;
  v10[15] = 24;
  *((_QWORD *)a2 + 4) = v10;
  *(_DWORD *)a2 = *((unsigned __int8 *)v10 + 27);
  *((_QWORD *)a2 + 1) = (char *)v10 + *((unsigned __int8 *)v10 + 26);
  *((_WORD *)a2 + 2) = 0;
  *((_DWORD *)a2 + 4) = (unsigned __int16)v10[15];
  *((_QWORD *)a2 + 3) = (char *)v10 + *((unsigned __int8 *)v10 + 26);
  return 0;
}

```

## disassembly

```asm
0x140070e30  mov     [rsp+arg_0], rbx
0x140070e35  push    rdi
0x140070e36  sub     rsp, 40h
0x140070e3a  cmp     cs:?SizeOfAllocationsOnLookaside2@CmsAvlTableLite@@2KA, 38h ; '8'; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside2
0x140070e41  xorps   xmm0, xmm0
0x140070e44  movdqu  [rsp+48h+var_28+8], xmm0
0x140070e4a  mov     rdi, rdx
0x140070e4d  mov     qword ptr [rsp+48h+var_28], 0
0x140070e56  jb      loc_140070F8A
0x140070e5c  xor     ecx, ecx; ProcNumber
0x140070e5e  cmp     cs:?SizeOfAllocationsOnLookaside1@CmsAvlTableLite@@2KA, 38h ; '8'; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside1
0x140070e65  jb      short loc_140070E9B
0x140070e67  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140070e6e  nop     dword ptr [rax+rax+00h]
0x140070e73  xor     edx, edx; struct std::nothrow_t *
0x140070e75  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140070e7b  lea     rbx, [rdx+rdx*2]
0x140070e7f  shl     rbx, 6
0x140070e83  add     rbx, cs:qword_140262458
0x140070e8a  cmp     dword ptr [rbx], 38h ; '8'
0x140070e8d  jnb     short loc_140070EC3
0x140070e8f  xor     ebx, ebx
0x140070e91  mov     ecx, 48h ; 'H'
0x140070e96  jmp     loc_140071043
0x140070e9b  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140070ea2  nop     dword ptr [rax+rax+00h]
0x140070ea7  mov     rbx, cs:qword_140262460
0x140070eae  cmp     dword ptr [rbx], 38h ; '8'
0x140070eb1  jnb     loc_140070F9E
0x140070eb7  xor     ebx, ebx
0x140070eb9  mov     ecx, 48h ; 'H'
0x140070ebe  jmp     loc_1400710A6
0x140070ec3  cmp     byte ptr [rbx+8], 0
0x140070ec7  jnz     loc_140070FFB
0x140070ecd  mov     rcx, [rbx+58h]
0x140070ed1  mov     rax, rcx
0x140070ed4  sar     rax, 20h
0x140070ed8  cmp     ecx, eax
0x140070eda  jle     loc_140071037
0x140070ee0  nop
0x140070ee1  or      ecx, 0FFFFFFFFh
0x140070ee4  lock xadd [rbx+58h], ecx
0x140070ee9  nop
0x140070eea  dec     ecx
0x140070eec  mov     eax, [rbx+5Ch]
0x140070eef  cmp     ecx, eax
0x140070ef1  jge     loc_14007101A
0x140070ef7  xor     eax, eax
0x140070ef9  nop
0x140070efa  lock inc dword ptr [rbx+58h]
0x140070efe  nop
0x140070eff  test    rax, rax
0x140070f02  jz      loc_140071037
0x140070f08  mov     [rax], rbx
0x140070f0b  add     rax, 10h
0x140070f0f  mov     ebx, 2000h
0x140070f14  mov     rcx, rax
0x140070f17  test    rax, rax
0x140070f1a  jz      short loc_140070F22
0x140070f1c  xor     eax, eax
0x140070f1e  mov     [rcx+1Ch], ax
0x140070f22  test    rcx, rcx
0x140070f25  jz      loc_140070FF4
0x140070f2b  movups  xmm0, [rsp+48h+var_28]
0x140070f30  movsd   xmm1, [rsp+48h+var_18]
0x140070f36  movups  xmmword ptr [rcx+20h], xmm0
0x140070f3a  movsd   qword ptr [rcx+30h], xmm1
0x140070f3f  mov     word ptr [rcx+1Ah], 1020h
0x140070f45  or      [rcx+1Ch], bx
0x140070f49  mov     word ptr [rcx+1Eh], 18h
0x140070f4f  mov     [rdi+20h], rcx
0x140070f53  movzx   eax, byte ptr [rcx+1Bh]
0x140070f57  mov     [rdi], eax
0x140070f59  movzx   eax, byte ptr [rcx+1Ah]
0x140070f5d  add     rax, rcx
0x140070f60  mov     [rdi+8], rax
0x140070f64  xor     eax, eax
0x140070f66  mov     [rdi+4], ax
0x140070f6a  movzx   eax, word ptr [rcx+1Eh]
0x140070f6e  mov     [rdi+10h], eax
0x140070f71  movzx   eax, byte ptr [rcx+1Ah]
0x140070f75  add     rax, rcx
0x140070f78  mov     [rdi+18h], rax
0x140070f7c  xor     eax, eax
0x140070f7e  mov     rbx, [rsp+48h+arg_0]
0x140070f83  add     rsp, 40h
0x140070f87  pop     rdi
0x140070f88  retn
0x140070f8a  mov     ecx, 38h ; '8'; unsigned __int64
0x140070f8f  mov     ebx, 8000h
0x140070f94  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140070f99  jmp     loc_140070F14
0x140070f9e  cmp     byte ptr [rbx+8], 0
0x140070fa2  jnz     loc_14007105E
0x140070fa8  mov     rcx, [rbx+58h]
0x140070fac  mov     rax, rcx
0x140070faf  sar     rax, 20h
0x140070fb3  cmp     ecx, eax
0x140070fb5  jle     loc_14007109A
0x140070fbb  nop
0x140070fbc  or      ecx, 0FFFFFFFFh
0x140070fbf  lock xadd [rbx+58h], ecx
0x140070fc4  nop
0x140070fc5  dec     ecx
0x140070fc7  mov     eax, [rbx+5Ch]
0x140070fca  cmp     ecx, eax
0x140070fcc  jge     loc_14007107D
0x140070fd2  xor     eax, eax
0x140070fd4  nop
0x140070fd5  lock inc dword ptr [rbx+58h]
0x140070fd9  nop
0x140070fda  test    rax, rax
0x140070fdd  jz      loc_14007109A
0x140070fe3  mov     [rax], rbx
0x140070fe6  add     rax, 10h
0x140070fea  mov     ebx, 4000h
0x140070fef  jmp     loc_140070F14
0x140070ff4  mov     eax, 0C000009Ah
0x140070ff9  jmp     short loc_140070F7E
0x140070ffb  cmp     byte ptr [rbx+9], 0
0x140070fff  lea     rcx, [rbx+40h]; Lookaside
0x140071003  jz      loc_1401F6BB4
0x140071009  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140071010  nop     dword ptr [rax+rax+00h]
0x140071015  jmp     loc_140070EFF
0x14007101a  test    ecx, ecx
0x14007101c  js      loc_140070EF7
0x140071022  lea     rcx, [rbx+40h]; ListHead
0x140071026  call    cs:__imp_ExpInterlockedPopEntrySList
0x14007102d  nop     dword ptr [rax+rax+00h]
0x140071032  jmp     loc_140070EFF
0x140071037  test    rbx, rbx
0x14007103a  jz      loc_140070E91
0x140071040  mov     ecx, [rbx+4]; unsigned __int64
0x140071043  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140071048  test    al, 0Fh
0x14007104a  jnz     loc_1401F6BD8
0x140071050  test    rax, rax
0x140071053  jz      loc_140070F0F
0x140071059  jmp     loc_140070F08
0x14007105e  cmp     byte ptr [rbx+9], 0
0x140071062  lea     rcx, [rbx+40h]; Lookaside
0x140071066  jz      loc_1401F6BC6
0x14007106c  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140071073  nop     dword ptr [rax+rax+00h]
0x140071078  jmp     loc_140070FDA
0x14007107d  test    ecx, ecx
0x14007107f  js      loc_140070FD2
0x140071085  lea     rcx, [rbx+40h]; ListHead
0x140071089  call    cs:__imp_ExpInterlockedPopEntrySList
0x140071090  nop     dword ptr [rax+rax+00h]
0x140071095  jmp     loc_140070FDA
0x14007109a  test    rbx, rbx
0x14007109d  jz      loc_140070EB9
0x1400710a3  mov     ecx, [rbx+4]; unsigned __int64
0x1400710a6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400710ab  test    al, 0Fh
0x1400710ad  jnz     loc_1401F6BD8
0x1400710b3  test    rax, rax
0x1400710b6  jz      loc_140070FEA
0x1400710bc  jmp     loc_140070FE3
0x1401f6bb4  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1401f6bbb  nop     dword ptr [rax+rax+00h]
0x1401f6bc0  nop
0x1401f6bc1  jmp     loc_140070EFF
0x1401f6bc6  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1401f6bcd  nop     dword ptr [rax+rax+00h]
0x1401f6bd2  nop
0x1401f6bd3  jmp     loc_140070FDA
0x1401f6bd8  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x1401f6bdf  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
```
