# CmsRangeAndCountMap::PreAllocateCountEntry(_SmsPreAllocatedRow *)

- ea: `0x140088694`
- end: `0x140088925`
- name: `?PreAllocateCountEntry@CmsRangeAndCountMap@@QEAAJPEAU_SmsPreAllocatedRow@@@Z`
- size: `657`
- prototype: `__int64 __fastcall(CmsRangeAndCountMap *__hidden this, struct _SmsPreAllocatedRow *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400cd694`

## callees

- `0x140088694`
- `0x140088930`
- `0x1400ceda0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008886d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400888d0`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008886d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400888d0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400886cb`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400886ff`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400886cb`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400886ff`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140200e9a`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140200eac`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140200e9a`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140200eac`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008888a`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400888ed`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008888a`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400888ed`

## string_xrefs

- `0x140200ebe`: `Lookaside list allocation must be double quad aligned.`

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
    v4 = qword_140269458 + 192LL * (_QWORD)v3;
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
  v7 = qword_140269460;
  if ( *(_DWORD *)qword_140269460 < 0x38u )
  {
    v7 = 0;
    goto LABEL_8;
  }
  if ( *(_BYTE *)(qword_140269460 + 8) )
  {
    v15 = (struct _NPAGED_LOOKASIDE_LIST *)(qword_140269460 + 64);
    if ( *(_BYTE *)(qword_140269460 + 9) )
      v10 = ExAllocateFromNPagedLookasideList(v15);
    else
      v10 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v15);
  }
  else
  {
    if ( (int)*(_QWORD *)(qword_140269460 + 88) <= (int)HIDWORD(*(_QWORD *)(qword_140269460 + 88)) )
      goto LABEL_40;
    v13 = _InterlockedDecrement((volatile signed __int32 *)(qword_140269460 + 88));
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
0x140088694  mov     [rsp+arg_0], rbx
0x140088699  push    rdi
0x14008869a  sub     rsp, 40h
0x14008869e  cmp     cs:?SizeOfAllocationsOnLookaside2@CmsAvlTableLite@@2KA, 38h ; '8'; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside2
0x1400886a5  xorps   xmm0, xmm0
0x1400886a8  movdqu  [rsp+48h+var_28+8], xmm0
0x1400886ae  mov     rdi, rdx
0x1400886b1  mov     qword ptr [rsp+48h+var_28], 0
0x1400886ba  jb      loc_1400887EE
0x1400886c0  xor     ecx, ecx; ProcNumber
0x1400886c2  cmp     cs:?SizeOfAllocationsOnLookaside1@CmsAvlTableLite@@2KA, 38h ; '8'; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside1
0x1400886c9  jb      short loc_1400886FF
0x1400886cb  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400886d2  nop     dword ptr [rax+rax+00h]
0x1400886d7  xor     edx, edx; struct std::nothrow_t *
0x1400886d9  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x1400886df  lea     rbx, [rdx+rdx*2]
0x1400886e3  shl     rbx, 6
0x1400886e7  add     rbx, cs:qword_140269458
0x1400886ee  cmp     dword ptr [rbx], 38h ; '8'
0x1400886f1  jnb     short loc_140088727
0x1400886f3  xor     ebx, ebx
0x1400886f5  mov     ecx, 48h ; 'H'
0x1400886fa  jmp     loc_1400888A7
0x1400886ff  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140088706  nop     dword ptr [rax+rax+00h]
0x14008870b  mov     rbx, cs:qword_140269460
0x140088712  cmp     dword ptr [rbx], 38h ; '8'
0x140088715  jnb     loc_140088802
0x14008871b  xor     ebx, ebx
0x14008871d  mov     ecx, 48h ; 'H'
0x140088722  jmp     loc_14008890A
0x140088727  cmp     byte ptr [rbx+8], 0
0x14008872b  jnz     loc_14008885F
0x140088731  mov     rcx, [rbx+58h]
0x140088735  mov     rax, rcx
0x140088738  sar     rax, 20h
0x14008873c  cmp     ecx, eax
0x14008873e  jle     loc_14008889B
0x140088744  nop
0x140088745  or      ecx, 0FFFFFFFFh
0x140088748  lock xadd [rbx+58h], ecx
0x14008874d  nop
0x14008874e  dec     ecx
0x140088750  mov     eax, [rbx+5Ch]
0x140088753  cmp     ecx, eax
0x140088755  jge     loc_14008887E
0x14008875b  xor     eax, eax
0x14008875d  nop
0x14008875e  lock inc dword ptr [rbx+58h]
0x140088762  nop
0x140088763  test    rax, rax
0x140088766  jz      loc_14008889B
0x14008876c  mov     [rax], rbx
0x14008876f  add     rax, 10h
0x140088773  mov     ebx, 2000h
0x140088778  mov     rcx, rax
0x14008877b  test    rax, rax
0x14008877e  jz      short loc_140088786
0x140088780  xor     eax, eax
0x140088782  mov     [rcx+1Ch], ax
0x140088786  test    rcx, rcx
0x140088789  jz      loc_140088858
0x14008878f  movups  xmm0, [rsp+48h+var_28]
0x140088794  movsd   xmm1, [rsp+48h+var_18]
0x14008879a  movups  xmmword ptr [rcx+20h], xmm0
0x14008879e  movsd   qword ptr [rcx+30h], xmm1
0x1400887a3  mov     word ptr [rcx+1Ah], 1020h
0x1400887a9  or      [rcx+1Ch], bx
0x1400887ad  mov     word ptr [rcx+1Eh], 18h
0x1400887b3  mov     [rdi+20h], rcx
0x1400887b7  movzx   eax, byte ptr [rcx+1Bh]
0x1400887bb  mov     [rdi], eax
0x1400887bd  movzx   eax, byte ptr [rcx+1Ah]
0x1400887c1  add     rax, rcx
0x1400887c4  mov     [rdi+8], rax
0x1400887c8  xor     eax, eax
0x1400887ca  mov     [rdi+4], ax
0x1400887ce  movzx   eax, word ptr [rcx+1Eh]
0x1400887d2  mov     [rdi+10h], eax
0x1400887d5  movzx   eax, byte ptr [rcx+1Ah]
0x1400887d9  add     rax, rcx
0x1400887dc  mov     [rdi+18h], rax
0x1400887e0  xor     eax, eax
0x1400887e2  mov     rbx, [rsp+48h+arg_0]
0x1400887e7  add     rsp, 40h
0x1400887eb  pop     rdi
0x1400887ec  retn
0x1400887ee  mov     ecx, 38h ; '8'; unsigned __int64
0x1400887f3  mov     ebx, 8000h
0x1400887f8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400887fd  jmp     loc_140088778
0x140088802  cmp     byte ptr [rbx+8], 0
0x140088806  jnz     loc_1400888C2
0x14008880c  mov     rcx, [rbx+58h]
0x140088810  mov     rax, rcx
0x140088813  sar     rax, 20h
0x140088817  cmp     ecx, eax
0x140088819  jle     loc_1400888FE
0x14008881f  nop
0x140088820  or      ecx, 0FFFFFFFFh
0x140088823  lock xadd [rbx+58h], ecx
0x140088828  nop
0x140088829  dec     ecx
0x14008882b  mov     eax, [rbx+5Ch]
0x14008882e  cmp     ecx, eax
0x140088830  jge     loc_1400888E1
0x140088836  xor     eax, eax
0x140088838  nop
0x140088839  lock inc dword ptr [rbx+58h]
0x14008883d  nop
0x14008883e  test    rax, rax
0x140088841  jz      loc_1400888FE
0x140088847  mov     [rax], rbx
0x14008884a  add     rax, 10h
0x14008884e  mov     ebx, 4000h
0x140088853  jmp     loc_140088778
0x140088858  mov     eax, 0C000009Ah
0x14008885d  jmp     short loc_1400887E2
0x14008885f  cmp     byte ptr [rbx+9], 0
0x140088863  lea     rcx, [rbx+40h]; Lookaside
0x140088867  jz      loc_140200E9A
0x14008886d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140088874  nop     dword ptr [rax+rax+00h]
0x140088879  jmp     loc_140088763
0x14008887e  test    ecx, ecx
0x140088880  js      loc_14008875B
0x140088886  lea     rcx, [rbx+40h]; ListHead
0x14008888a  call    cs:__imp_ExpInterlockedPopEntrySList
0x140088891  nop     dword ptr [rax+rax+00h]
0x140088896  jmp     loc_140088763
0x14008889b  test    rbx, rbx
0x14008889e  jz      loc_1400886F5
0x1400888a4  mov     ecx, [rbx+4]; unsigned __int64
0x1400888a7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400888ac  test    al, 0Fh
0x1400888ae  jnz     loc_140200EBE
0x1400888b4  test    rax, rax
0x1400888b7  jz      loc_140088773
0x1400888bd  jmp     loc_14008876C
0x1400888c2  cmp     byte ptr [rbx+9], 0
0x1400888c6  lea     rcx, [rbx+40h]; Lookaside
0x1400888ca  jz      loc_140200EAC
0x1400888d0  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400888d7  nop     dword ptr [rax+rax+00h]
0x1400888dc  jmp     loc_14008883E
0x1400888e1  test    ecx, ecx
0x1400888e3  js      loc_140088836
0x1400888e9  lea     rcx, [rbx+40h]; ListHead
0x1400888ed  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400888f4  nop     dword ptr [rax+rax+00h]
0x1400888f9  jmp     loc_14008883E
0x1400888fe  test    rbx, rbx
0x140088901  jz      loc_14008871D
0x140088907  mov     ecx, [rbx+4]; unsigned __int64
0x14008890a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14008890f  test    al, 0Fh
0x140088911  jnz     loc_140200EBE
0x140088917  test    rax, rax
0x14008891a  jz      loc_14008884E
0x140088920  jmp     loc_140088847
0x140200e9a  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140200ea1  nop     dword ptr [rax+rax+00h]
0x140200ea6  nop
0x140200ea7  jmp     loc_140088763
0x140200eac  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140200eb3  nop     dword ptr [rax+rax+00h]
0x140200eb8  nop
0x140200eb9  jmp     loc_14008883E
0x140200ebe  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x140200ec5  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
```
