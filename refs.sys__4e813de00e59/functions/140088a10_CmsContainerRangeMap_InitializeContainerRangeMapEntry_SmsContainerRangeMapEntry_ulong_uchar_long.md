# CmsContainerRangeMap::InitializeContainerRangeMapEntry(_SmsContainerRangeMapEntry * *,ulong,uchar,long *)

- ea: `0x140088a10`
- end: `0x140088bed`
- name: `?InitializeContainerRangeMapEntry@CmsContainerRangeMap@@SAJPEAPEAU_SmsContainerRangeMapEntry@@KEPEAJ@Z`
- size: `477`
- prototype: `__int64 __fastcall(struct _SmsContainerRangeMapEntry **, unsigned int, unsigned __int8, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140055570`

## callees

- `0x140088a10`
- `0x1400ceda0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140088b6e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140088bc2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140088b6e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140088bc2`
- `ntoskrnl!ExAllocatePool2` at `0x140088afd`
- `ntoskrnl!ExAllocatePool2` at `0x140088b90`
- `ntoskrnl!ExAllocatePool2` at `0x140088afd`
- `ntoskrnl!ExAllocatePool2` at `0x140088b90`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140088a30`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140088ac0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140088a30`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140088ac0`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140200ecc`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140200ee0`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140200ecc`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140200ee0`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140088a63`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140088bdc`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140088a63`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140088bdc`

## string_xrefs

- `0x140200ef2`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsContainerRangeMap::InitializeContainerRangeMapEntry(
        struct _SmsContainerRangeMapEntry **a1,
        int a2,
        char a3,
        int *a4)
{
  unsigned __int64 v5; // rbp
  signed __int64 v6; // r9
  unsigned int *v7; // rdi
  unsigned int v8; // ebx
  __int64 v9; // rdx
  struct _NPAGED_LOOKASIDE_LIST *v10; // rcx
  struct _SmsContainerRangeMapEntry *v11; // rcx
  __int64 v13; // r9
  unsigned __int64 v14; // rdx
  __int64 Pool2; // rax
  int v16; // ecx
  __int64 v17; // rax
  struct _NPAGED_LOOKASIDE_LIST *v18; // rcx
  struct _SmsContainerRangeMapEntry *v19; // rax

  v5 = (unsigned int)(a2 + 16);
  if ( !a3 )
  {
    v8 = 0;
    v7 = (unsigned int *)(qword_1402694B0 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
    if ( v5 > *v7 )
    {
      v7 = 0;
      v14 = v5 + 16;
LABEL_14:
      Pool2 = ExAllocatePool2(66, v14, 1766871885, v13);
      v11 = (struct _SmsContainerRangeMapEntry *)Pool2;
      if ( (Pool2 & 0xF) != 0 )
        goto LABEL_36;
      if ( !Pool2 )
        goto LABEL_9;
LABEL_8:
      *(_QWORD *)v11 = v7;
      v11 = (struct _SmsContainerRangeMapEntry *)((char *)v11 + 16);
      goto LABEL_9;
    }
    if ( !*((_BYTE *)v7 + 8) )
    {
      if ( (int)*((_QWORD *)v7 + 11) > (int)HIDWORD(*((_QWORD *)v7 + 11)) )
      {
        v16 = _InterlockedDecrement((volatile signed __int32 *)v7 + 22);
        if ( v16 >= (int)v7[23] && v16 >= 0 )
        {
          v19 = (struct _SmsContainerRangeMapEntry *)ExpInterlockedPopEntrySList((PSLIST_HEADER)v7 + 4);
          goto LABEL_22;
        }
        _InterlockedIncrement((volatile signed __int32 *)v7 + 22);
      }
LABEL_21:
      v14 = v7[1];
      goto LABEL_14;
    }
    v18 = (struct _NPAGED_LOOKASIDE_LIST *)(v7 + 16);
    if ( *((_BYTE *)v7 + 9) )
      v19 = (struct _SmsContainerRangeMapEntry *)ExAllocateFromNPagedLookasideList(v18);
    else
      v19 = (struct _SmsContainerRangeMapEntry *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v18);
LABEL_22:
    v11 = v19;
    if ( v19 )
      goto LABEL_8;
    goto LABEL_21;
  }
  _InterlockedDecrement(a4);
  KeGetCurrentProcessorNumberEx(0);
  v7 = (unsigned int *)qword_1402694A0;
  v8 = 0;
  if ( (unsigned int)v5 <= *(_DWORD *)qword_1402694A0 )
  {
    v10 = (struct _NPAGED_LOOKASIDE_LIST *)(qword_1402694A0 + 64);
    if ( *(_BYTE *)(qword_1402694A0 + 8) )
    {
      if ( *(_BYTE *)(qword_1402694A0 + 9) )
        v11 = (struct _SmsContainerRangeMapEntry *)ExAllocateFromNPagedLookasideList(v10);
      else
        v11 = (struct _SmsContainerRangeMapEntry *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v10);
    }
    else
    {
      v11 = (struct _SmsContainerRangeMapEntry *)ExpInterlockedPopEntrySList(&v10->L.ListHead);
      do
        v6 = *((_QWORD *)v7 + 11);
      while ( v6 != _InterlockedCompareExchange64(
                      (volatile signed __int64 *)v7 + 11,
                      (unsigned int)(v6 - 1) | ((unsigned __int64)(unsigned int)(HIDWORD(v6) - 1) << 32),
                      v6) );
    }
    if ( v11 )
      goto LABEL_8;
    v9 = v7[1];
  }
  else
  {
    v7 = 0;
    v9 = (unsigned int)v5 + 16LL;
  }
  v17 = ExAllocatePool2(66, v9, 1766871885, v6);
  v11 = (struct _SmsContainerRangeMapEntry *)v17;
  if ( (v17 & 0xF) != 0 )
LABEL_36:
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( v17 )
    goto LABEL_8;
LABEL_9:
  *a1 = v11;
  if ( !v11 )
    return (unsigned int)-1073741670;
  return v8;
}

```

## disassembly

```asm
0x140088a10  push    rbx
0x140088a12  push    rbp
0x140088a13  push    rsi
0x140088a14  push    rdi
0x140088a15  sub     rsp, 28h
0x140088a19  mov     rsi, rcx
0x140088a1c  lea     ebp, [rdx+10h]
0x140088a1f  xor     ecx, ecx; ProcNumber
0x140088a21  test    r8b, r8b
0x140088a24  jz      loc_140088AC0
0x140088a2a  nop
0x140088a2b  lock dec dword ptr [r9]
0x140088a2f  nop
0x140088a30  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140088a37  nop     dword ptr [rax+rax+00h]
0x140088a3c  mov     rdi, cs:qword_1402694A0
0x140088a43  xor     ebx, ebx
0x140088a45  cmp     ebp, [rdi]
0x140088a47  jbe     short loc_140088A56
0x140088a49  mov     edx, ebp
0x140088a4b  mov     edi, ebx
0x140088a4d  add     rdx, 10h
0x140088a51  jmp     loc_140088B85
0x140088a56  lea     rcx, [rdi+40h]; Lookaside
0x140088a5a  cmp     [rdi+8], bl
0x140088a5d  jnz     loc_140088B65
0x140088a63  call    cs:__imp_ExpInterlockedPopEntrySList
0x140088a6a  nop     dword ptr [rax+rax+00h]
0x140088a6f  mov     rcx, rax
0x140088a72  mov     r9, [rdi+58h]
0x140088a76  mov     r8, r9
0x140088a79  mov     rax, r9
0x140088a7c  shr     r8, 20h
0x140088a80  dec     r8d
0x140088a83  shl     r8, 20h
0x140088a87  lea     edx, [r9-1]
0x140088a8b  or      r8, rdx
0x140088a8e  lock cmpxchg [rdi+58h], r8
0x140088a94  jnz     short loc_140088A72
0x140088a96  test    rcx, rcx
0x140088a99  jz      loc_140088B82
0x140088a9f  mov     [rcx], rdi
0x140088aa2  add     rcx, 10h
0x140088aa6  mov     eax, 0C000009Ah
0x140088aab  mov     [rsi], rcx
0x140088aae  test    rcx, rcx
0x140088ab1  cmovz   ebx, eax
0x140088ab4  mov     eax, ebx
0x140088ab6  add     rsp, 28h
0x140088aba  pop     rdi
0x140088abb  pop     rsi
0x140088abc  pop     rbp
0x140088abd  pop     rbx
0x140088abe  retn
0x140088ac0  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140088ac7  nop     dword ptr [rax+rax+00h]
0x140088acc  xor     edx, edx
0x140088ace  xor     ebx, ebx
0x140088ad0  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140088ad6  lea     rdi, [rdx+rdx*2]
0x140088ada  shl     rdi, 6
0x140088ade  add     rdi, cs:qword_1402694B0
0x140088ae5  mov     eax, [rdi]
0x140088ae7  cmp     rbp, rax
0x140088aea  jbe     short loc_140088B1B
0x140088aec  mov     edi, ebx
0x140088aee  lea     rdx, [rbp+10h]
0x140088af2  mov     ecx, 42h ; 'B'
0x140088af7  mov     r8d, 6950534Dh
0x140088afd  call    cs:__imp_ExAllocatePool2
0x140088b04  nop     dword ptr [rax+rax+00h]
0x140088b09  mov     rcx, rax
0x140088b0c  test    al, 0Fh
0x140088b0e  jnz     loc_140200EF2
0x140088b14  test    rax, rax
0x140088b17  jz      short loc_140088AA6
0x140088b19  jmp     short loc_140088A9F
0x140088b1b  cmp     [rdi+8], bl
0x140088b1e  jnz     loc_140088BB5
0x140088b24  mov     rcx, [rdi+58h]
0x140088b28  mov     rax, rcx
0x140088b2b  shr     rax, 20h
0x140088b2f  cmp     ecx, eax
0x140088b31  jle     short loc_140088B52
0x140088b33  nop
0x140088b34  mov     ecx, 0FFFFFFFFh
0x140088b39  lock xadd [rdi+58h], ecx
0x140088b3e  nop
0x140088b3f  dec     ecx
0x140088b41  mov     eax, [rdi+5Ch]
0x140088b44  cmp     ecx, eax
0x140088b46  jge     loc_140088BD0
0x140088b4c  nop
0x140088b4d  lock inc dword ptr [rdi+58h]
0x140088b51  nop
0x140088b52  mov     edx, [rdi+4]
0x140088b55  jmp     short loc_140088AF2
0x140088b57  mov     rcx, rax
0x140088b5a  test    rax, rax
0x140088b5d  jnz     loc_140088A9F
0x140088b63  jmp     short loc_140088B52
0x140088b65  cmp     [rdi+9], bl
0x140088b68  jz      loc_140200ECC
0x140088b6e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140088b75  nop     dword ptr [rax+rax+00h]
0x140088b7a  mov     rcx, rax
0x140088b7d  jmp     loc_140088A96
0x140088b82  mov     edx, [rdi+4]
0x140088b85  mov     ecx, 42h ; 'B'
0x140088b8a  mov     r8d, 6950534Dh
0x140088b90  call    cs:__imp_ExAllocatePool2
0x140088b97  nop     dword ptr [rax+rax+00h]
0x140088b9c  mov     rcx, rax
0x140088b9f  test    al, 0Fh
0x140088ba1  jnz     loc_140200EF2
0x140088ba7  test    rax, rax
0x140088baa  jz      loc_140088AA6
0x140088bb0  jmp     loc_140088A9F
0x140088bb5  lea     rcx, [rdi+40h]; Lookaside
0x140088bb9  cmp     [rdi+9], bl
0x140088bbc  jz      loc_140200EE0
0x140088bc2  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140088bc9  nop     dword ptr [rax+rax+00h]
0x140088bce  jmp     short loc_140088B57
0x140088bd0  test    ecx, ecx
0x140088bd2  js      loc_140088B4C
0x140088bd8  lea     rcx, [rdi+40h]; ListHead
0x140088bdc  call    cs:__imp_ExpInterlockedPopEntrySList
0x140088be3  nop     dword ptr [rax+rax+00h]
0x140088be8  jmp     loc_140088B57
0x140200ecc  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140200ed3  nop     dword ptr [rax+rax+00h]
0x140200ed8  mov     rcx, rax
0x140200edb  jmp     loc_140088A96
0x140200ee0  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140200ee7  nop     dword ptr [rax+rax+00h]
0x140200eec  nop
0x140200eed  jmp     loc_140088B57
0x140200ef2  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x140200ef9  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
```
