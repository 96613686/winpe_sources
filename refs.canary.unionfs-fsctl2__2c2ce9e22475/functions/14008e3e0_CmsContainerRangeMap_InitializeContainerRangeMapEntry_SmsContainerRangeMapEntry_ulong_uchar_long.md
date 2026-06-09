# CmsContainerRangeMap::InitializeContainerRangeMapEntry(_SmsContainerRangeMapEntry * *,ulong,uchar,long *)

- ea: `0x14008e3e0`
- end: `0x14008e5bd`
- name: `?InitializeContainerRangeMapEntry@CmsContainerRangeMap@@SAJPEAPEAU_SmsContainerRangeMapEntry@@KEPEAJ@Z`
- size: `477`
- prototype: `__int64 __fastcall(struct _SmsContainerRangeMapEntry **, unsigned int, unsigned __int8, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14006d4c0`

## callees

- `0x14008e3e0`
- `0x1400c8574`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008e53e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008e592`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008e53e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008e592`
- `ntoskrnl!ExAllocatePool2` at `0x14008e4cd`
- `ntoskrnl!ExAllocatePool2` at `0x14008e560`
- `ntoskrnl!ExAllocatePool2` at `0x14008e4cd`
- `ntoskrnl!ExAllocatePool2` at `0x14008e560`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008e400`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008e490`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008e400`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14008e490`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f92de`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f92f2`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f92de`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f92f2`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008e433`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008e5ac`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008e433`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008e5ac`

## string_xrefs

- `0x1401f9304`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsContainerRangeMap::InitializeContainerRangeMapEntry(
        struct _SmsContainerRangeMapEntry **a1,
        int a2,
        char a3,
        int *a4)
{
  unsigned __int64 v5; // rbp
  unsigned int *v6; // rdi
  unsigned int v7; // ebx
  __int64 v8; // rdx
  struct _NPAGED_LOOKASIDE_LIST *v9; // rcx
  struct _SmsContainerRangeMapEntry *v10; // rcx
  signed __int64 v11; // rtt
  unsigned __int64 v13; // rdx
  __int64 Pool2; // rax
  int v15; // ecx
  __int64 v16; // rax
  struct _NPAGED_LOOKASIDE_LIST *v17; // rcx
  struct _SmsContainerRangeMapEntry *v18; // rax

  v5 = (unsigned int)(a2 + 16);
  if ( !a3 )
  {
    v7 = 0;
    v6 = (unsigned int *)(qword_1402624B0 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
    if ( v5 > *v6 )
    {
      v6 = 0;
      v13 = v5 + 16;
LABEL_14:
      Pool2 = ExAllocatePool2(66, v13, 1766871885);
      v10 = (struct _SmsContainerRangeMapEntry *)Pool2;
      if ( (Pool2 & 0xF) != 0 )
        goto LABEL_36;
      if ( !Pool2 )
        goto LABEL_9;
LABEL_8:
      *(_QWORD *)v10 = v6;
      v10 = (struct _SmsContainerRangeMapEntry *)((char *)v10 + 16);
      goto LABEL_9;
    }
    if ( !*((_BYTE *)v6 + 8) )
    {
      if ( (int)*((_QWORD *)v6 + 11) > (int)HIDWORD(*((_QWORD *)v6 + 11)) )
      {
        v15 = _InterlockedDecrement((volatile signed __int32 *)v6 + 22);
        if ( v15 >= (int)v6[23] && v15 >= 0 )
        {
          v18 = (struct _SmsContainerRangeMapEntry *)ExpInterlockedPopEntrySList((PSLIST_HEADER)v6 + 4);
          goto LABEL_22;
        }
        _InterlockedIncrement((volatile signed __int32 *)v6 + 22);
      }
LABEL_21:
      v13 = v6[1];
      goto LABEL_14;
    }
    v17 = (struct _NPAGED_LOOKASIDE_LIST *)(v6 + 16);
    if ( *((_BYTE *)v6 + 9) )
      v18 = (struct _SmsContainerRangeMapEntry *)ExAllocateFromNPagedLookasideList(v17);
    else
      v18 = (struct _SmsContainerRangeMapEntry *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v17);
LABEL_22:
    v10 = v18;
    if ( v18 )
      goto LABEL_8;
    goto LABEL_21;
  }
  _InterlockedDecrement(a4);
  KeGetCurrentProcessorNumberEx(0);
  v6 = (unsigned int *)qword_1402624A0;
  v7 = 0;
  if ( (unsigned int)v5 <= *(_DWORD *)qword_1402624A0 )
  {
    v9 = (struct _NPAGED_LOOKASIDE_LIST *)(qword_1402624A0 + 64);
    if ( *(_BYTE *)(qword_1402624A0 + 8) )
    {
      if ( *(_BYTE *)(qword_1402624A0 + 9) )
        v10 = (struct _SmsContainerRangeMapEntry *)ExAllocateFromNPagedLookasideList(v9);
      else
        v10 = (struct _SmsContainerRangeMapEntry *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v9);
    }
    else
    {
      v10 = (struct _SmsContainerRangeMapEntry *)ExpInterlockedPopEntrySList(&v9->L.ListHead);
      do
        v11 = *((_QWORD *)v6 + 11);
      while ( v11 != _InterlockedCompareExchange64(
                       (volatile signed __int64 *)v6 + 11,
                       (unsigned int)(v11 - 1) | ((unsigned __int64)(unsigned int)(HIDWORD(v11) - 1) << 32),
                       v11) );
    }
    if ( v10 )
      goto LABEL_8;
    v8 = v6[1];
  }
  else
  {
    v6 = 0;
    v8 = (unsigned int)v5 + 16LL;
  }
  v16 = ExAllocatePool2(66, v8, 1766871885);
  v10 = (struct _SmsContainerRangeMapEntry *)v16;
  if ( (v16 & 0xF) != 0 )
LABEL_36:
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( v16 )
    goto LABEL_8;
LABEL_9:
  *a1 = v10;
  if ( !v10 )
    return (unsigned int)-1073741670;
  return v7;
}

```

## disassembly

```asm
0x14008e3e0  push    rbx
0x14008e3e2  push    rbp
0x14008e3e3  push    rsi
0x14008e3e4  push    rdi
0x14008e3e5  sub     rsp, 28h
0x14008e3e9  mov     rsi, rcx
0x14008e3ec  lea     ebp, [rdx+10h]
0x14008e3ef  xor     ecx, ecx; ProcNumber
0x14008e3f1  test    r8b, r8b
0x14008e3f4  jz      loc_14008E490
0x14008e3fa  nop
0x14008e3fb  lock dec dword ptr [r9]
0x14008e3ff  nop
0x14008e400  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14008e407  nop     dword ptr [rax+rax+00h]
0x14008e40c  mov     rdi, cs:qword_1402624A0
0x14008e413  xor     ebx, ebx
0x14008e415  cmp     ebp, [rdi]
0x14008e417  jbe     short loc_14008E426
0x14008e419  mov     edx, ebp
0x14008e41b  mov     edi, ebx
0x14008e41d  add     rdx, 10h
0x14008e421  jmp     loc_14008E555
0x14008e426  lea     rcx, [rdi+40h]; Lookaside
0x14008e42a  cmp     [rdi+8], bl
0x14008e42d  jnz     loc_14008E535
0x14008e433  call    cs:__imp_ExpInterlockedPopEntrySList
0x14008e43a  nop     dword ptr [rax+rax+00h]
0x14008e43f  mov     rcx, rax
0x14008e442  mov     r9, [rdi+58h]
0x14008e446  mov     r8, r9
0x14008e449  mov     rax, r9
0x14008e44c  shr     r8, 20h
0x14008e450  dec     r8d
0x14008e453  shl     r8, 20h
0x14008e457  lea     edx, [r9-1]
0x14008e45b  or      r8, rdx
0x14008e45e  lock cmpxchg [rdi+58h], r8
0x14008e464  jnz     short loc_14008E442
0x14008e466  test    rcx, rcx
0x14008e469  jz      loc_14008E552
0x14008e46f  mov     [rcx], rdi
0x14008e472  add     rcx, 10h
0x14008e476  mov     eax, 0C000009Ah
0x14008e47b  mov     [rsi], rcx
0x14008e47e  test    rcx, rcx
0x14008e481  cmovz   ebx, eax
0x14008e484  mov     eax, ebx
0x14008e486  add     rsp, 28h
0x14008e48a  pop     rdi
0x14008e48b  pop     rsi
0x14008e48c  pop     rbp
0x14008e48d  pop     rbx
0x14008e48e  retn
0x14008e490  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14008e497  nop     dword ptr [rax+rax+00h]
0x14008e49c  xor     edx, edx
0x14008e49e  xor     ebx, ebx
0x14008e4a0  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14008e4a6  lea     rdi, [rdx+rdx*2]
0x14008e4aa  shl     rdi, 6
0x14008e4ae  add     rdi, cs:qword_1402624B0
0x14008e4b5  mov     eax, [rdi]
0x14008e4b7  cmp     rbp, rax
0x14008e4ba  jbe     short loc_14008E4EB
0x14008e4bc  mov     edi, ebx
0x14008e4be  lea     rdx, [rbp+10h]
0x14008e4c2  mov     ecx, 42h ; 'B'
0x14008e4c7  mov     r8d, 6950534Dh
0x14008e4cd  call    cs:__imp_ExAllocatePool2
0x14008e4d4  nop     dword ptr [rax+rax+00h]
0x14008e4d9  mov     rcx, rax
0x14008e4dc  test    al, 0Fh
0x14008e4de  jnz     loc_1401F9304
0x14008e4e4  test    rax, rax
0x14008e4e7  jz      short loc_14008E476
0x14008e4e9  jmp     short loc_14008E46F
0x14008e4eb  cmp     [rdi+8], bl
0x14008e4ee  jnz     loc_14008E585
0x14008e4f4  mov     rcx, [rdi+58h]
0x14008e4f8  mov     rax, rcx
0x14008e4fb  shr     rax, 20h
0x14008e4ff  cmp     ecx, eax
0x14008e501  jle     short loc_14008E522
0x14008e503  nop
0x14008e504  mov     ecx, 0FFFFFFFFh
0x14008e509  lock xadd [rdi+58h], ecx
0x14008e50e  nop
0x14008e50f  dec     ecx
0x14008e511  mov     eax, [rdi+5Ch]
0x14008e514  cmp     ecx, eax
0x14008e516  jge     loc_14008E5A0
0x14008e51c  nop
0x14008e51d  lock inc dword ptr [rdi+58h]
0x14008e521  nop
0x14008e522  mov     edx, [rdi+4]
0x14008e525  jmp     short loc_14008E4C2
0x14008e527  mov     rcx, rax
0x14008e52a  test    rax, rax
0x14008e52d  jnz     loc_14008E46F
0x14008e533  jmp     short loc_14008E522
0x14008e535  cmp     [rdi+9], bl
0x14008e538  jz      loc_1401F92DE
0x14008e53e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14008e545  nop     dword ptr [rax+rax+00h]
0x14008e54a  mov     rcx, rax
0x14008e54d  jmp     loc_14008E466
0x14008e552  mov     edx, [rdi+4]
0x14008e555  mov     ecx, 42h ; 'B'
0x14008e55a  mov     r8d, 6950534Dh
0x14008e560  call    cs:__imp_ExAllocatePool2
0x14008e567  nop     dword ptr [rax+rax+00h]
0x14008e56c  mov     rcx, rax
0x14008e56f  test    al, 0Fh
0x14008e571  jnz     loc_1401F9304
0x14008e577  test    rax, rax
0x14008e57a  jz      loc_14008E476
0x14008e580  jmp     loc_14008E46F
0x14008e585  lea     rcx, [rdi+40h]; Lookaside
0x14008e589  cmp     [rdi+9], bl
0x14008e58c  jz      loc_1401F92F2
0x14008e592  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14008e599  nop     dword ptr [rax+rax+00h]
0x14008e59e  jmp     short loc_14008E527
0x14008e5a0  test    ecx, ecx
0x14008e5a2  js      loc_14008E51C
0x14008e5a8  lea     rcx, [rdi+40h]; ListHead
0x14008e5ac  call    cs:__imp_ExpInterlockedPopEntrySList
0x14008e5b3  nop     dword ptr [rax+rax+00h]
0x14008e5b8  jmp     loc_14008E527
0x1401f92de  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1401f92e5  nop     dword ptr [rax+rax+00h]
0x1401f92ea  mov     rcx, rax
0x1401f92ed  jmp     loc_14008E466
0x1401f92f2  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1401f92f9  nop     dword ptr [rax+rax+00h]
0x1401f92fe  nop
0x1401f92ff  jmp     loc_14008E527
0x1401f9304  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x1401f930b  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
```
