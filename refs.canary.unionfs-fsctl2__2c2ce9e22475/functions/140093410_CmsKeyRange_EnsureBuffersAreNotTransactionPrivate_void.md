# CmsKeyRange::EnsureBuffersAreNotTransactionPrivate(void)

- ea: `0x140093410`
- end: `0x1400935f7`
- name: `?EnsureBuffersAreNotTransactionPrivate@CmsKeyRange@@QEAAJXZ`
- size: `487`
- prototype: `__int64 __fastcall(CmsKeyRange *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14002f4b0`

## callees

- `0x140093410`
- `0x1400c8574`
- `0x1401e9e40`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140093538`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140093538`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14009359b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14009359b`
- `ntoskrnl!ExAllocatePool2` at `0x14009346b`
- `ntoskrnl!ExAllocatePool2` at `0x14009346b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14009342f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14009342f`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f9824`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f9824`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140093525`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140093525`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f984b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f984b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400935b4`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400935b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400935e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400935e6`

## string_xrefs

- `0x14009347f`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsKeyRange::EnsureBuffersAreNotTransactionPrivate(CmsKeyRange *this)
{
  __int64 v2; // rbp
  __int64 v3; // rdi
  __int64 v4; // rdx
  __int64 Pool2; // rax
  __int64 result; // rax
  __int64 v7; // rdi
  __int64 v8; // rcx
  struct _SLIST_ENTRY *v9; // r8
  __int64 v10; // rsi
  struct _NPAGED_LOOKASIDE_LIST *v11; // rcx
  int v12; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v13; // rcx
  __int64 v14; // rcx

  if ( (*((_DWORD *)this + 6) & 8) == 0 )
    return 0;
  v2 = *((unsigned int *)this + 2);
  v3 = qword_140262420 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( (unsigned int)v2 > *(_DWORD *)v3 )
  {
    v3 = 0;
    v4 = v2 + 16;
    goto LABEL_4;
  }
  if ( *(_BYTE *)(v3 + 8) )
  {
    v13 = (struct _NPAGED_LOOKASIDE_LIST *)(v3 + 64);
    if ( *(_BYTE *)(v3 + 9) )
      Pool2 = (__int64)ExAllocateFromNPagedLookasideList(v13);
    else
      Pool2 = (__int64)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v13);
LABEL_7:
    if ( Pool2 )
      goto LABEL_8;
    goto LABEL_25;
  }
  if ( (int)*(_QWORD *)(v3 + 88) > (int)HIDWORD(*(_QWORD *)(v3 + 88)) )
  {
    v12 = _InterlockedDecrement((volatile signed __int32 *)(v3 + 88));
    if ( v12 >= *(_DWORD *)(v3 + 92) && v12 >= 0 )
    {
      Pool2 = (__int64)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v3 + 64));
      goto LABEL_7;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 88));
  }
LABEL_25:
  v4 = *(unsigned int *)(v3 + 4);
LABEL_4:
  Pool2 = ExAllocatePool2(66, v4, 1766871885);
  if ( (Pool2 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( !Pool2 )
    return 3221225626LL;
LABEL_8:
  *(_QWORD *)Pool2 = v3;
  v7 = Pool2 + 16;
  if ( Pool2 == -16 )
    return 3221225626LL;
  if ( *(_QWORD *)this )
  {
    memmove((void *)(Pool2 + 16), *(const void **)this, *((unsigned int *)this + 2));
    v8 = *(_QWORD *)this;
    if ( (*((_DWORD *)this + 6) & 8) != 0 )
    {
      *(_BYTE *)(v8 - 2431) = 0;
      *((_DWORD *)this + 6) &= ~8u;
    }
    else if ( v8 )
    {
      v9 = (struct _SLIST_ENTRY *)(v8 - 16);
      v10 = *(_QWORD *)(v8 - 16);
      if ( !v10 )
        goto LABEL_33;
      if ( *(_BYTE *)(v10 + 8) )
      {
        v11 = (struct _NPAGED_LOOKASIDE_LIST *)(v10 + 64);
        if ( *(_BYTE *)(v10 + 9) )
          ExFreeToNPagedLookasideList(v11, v9);
        else
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v11, v9);
        goto LABEL_12;
      }
      v14 = *(_QWORD *)(v10 + 88);
      if ( (int)v14 < *(_DWORD *)(v10 + 80) || SHIDWORD(v14) >= (int)v14 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v10 + 64), v9);
        _InterlockedIncrement((volatile signed __int32 *)(v10 + 88));
      }
      else
      {
LABEL_33:
        ExFreePoolWithTag(v9, 0);
      }
    }
  }
LABEL_12:
  *((_DWORD *)this + 6) &= ~8u;
  result = 0;
  *(_QWORD *)this = v7;
  *((_DWORD *)this + 2) = v2;
  return result;
}

```

## disassembly

```asm
0x140093410  push    rbx
0x140093412  sub     rsp, 20h
0x140093416  mov     eax, [rcx+18h]
0x140093419  mov     rbx, rcx
0x14009341c  test    al, 8
0x14009341e  jz      short loc_14009348C
0x140093420  mov     [rsp+28h+arg_0], rbp
0x140093425  mov     ebp, [rcx+8]
0x140093428  xor     ecx, ecx; ProcNumber
0x14009342a  mov     [rsp+28h+arg_10], rdi
0x14009342f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140093436  nop     dword ptr [rax+rax+00h]
0x14009343b  xor     edx, edx
0x14009343d  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140093443  lea     rdi, [rdx+rdx*2]
0x140093447  shl     rdi, 6
0x14009344b  add     rdi, cs:qword_140262420
0x140093452  cmp     ebp, [rdi]
0x140093454  jbe     loc_14009354B
0x14009345a  xor     edi, edi
0x14009345c  lea     rdx, [rbp+10h]
0x140093460  mov     ecx, 42h ; 'B'
0x140093465  mov     r8d, 6950534Dh
0x14009346b  call    cs:__imp_ExAllocatePool2
0x140093472  nop     dword ptr [rax+rax+00h]
0x140093477  test    al, 0Fh
0x140093479  jz      loc_1401F9836
0x14009347f  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x140093486  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x14009348c  xor     eax, eax
0x14009348e  add     rsp, 20h
0x140093492  pop     rbx
0x140093493  retn
0x140093495  test    rax, rax
0x140093498  jz      loc_14009357B
0x14009349e  mov     [rax], rdi
0x1400934a1  lea     rdi, [rax+10h]
0x1400934a5  test    rdi, rdi
0x1400934a8  jz      loc_140093583
0x1400934ae  mov     rdx, [rbx]; Src
0x1400934b1  test    rdx, rdx
0x1400934b4  jz      short loc_1400934D7
0x1400934b6  mov     r8d, [rbx+8]; Size
0x1400934ba  mov     rcx, rdi; void *
0x1400934bd  call    memmove
0x1400934c2  mov     eax, [rbx+18h]
0x1400934c5  mov     rcx, [rbx]
0x1400934c8  test    al, 8
0x1400934ca  jz      short loc_1400934F4
0x1400934cc  mov     byte ptr [rcx-97Fh], 0
0x1400934d3  and     dword ptr [rbx+18h], 0FFFFFFF7h
0x1400934d7  and     dword ptr [rbx+18h], 0FFFFFFF7h
0x1400934db  xor     eax, eax
0x1400934dd  mov     [rbx], rdi
0x1400934e0  mov     [rbx+8], ebp
0x1400934e3  mov     rbp, [rsp+28h+arg_0]
0x1400934e8  mov     rdi, [rsp+28h+arg_10]
0x1400934ed  add     rsp, 20h
0x1400934f1  pop     rbx
0x1400934f2  retn
0x1400934f4  test    rcx, rcx
0x1400934f7  jz      short loc_1400934D7
0x1400934f9  lea     r8, [rcx-10h]
0x1400934fd  mov     [rsp+28h+arg_8], rsi
0x140093502  mov     rsi, [r8]
0x140093505  test    rsi, rsi
0x140093508  jz      loc_1400935E1
0x14009350e  cmp     byte ptr [rsi+8], 0
0x140093512  jz      loc_1400935C5
0x140093518  cmp     byte ptr [rsi+9], 0
0x14009351c  lea     rcx, [rsi+40h]; Lookaside
0x140093520  mov     rdx, r8; Entry
0x140093523  jnz     short loc_140093538
0x140093525  call    cs:__imp_ExFreeToPagedLookasideList
0x14009352c  nop     dword ptr [rax+rax+00h]
0x140093531  mov     rsi, [rsp+28h+arg_8]
0x140093536  jmp     short loc_1400934D7
0x140093538  call    cs:__imp_ExFreeToNPagedLookasideList
0x14009353f  nop     dword ptr [rax+rax+00h]
0x140093544  mov     rsi, [rsp+28h+arg_8]
0x140093549  jmp     short loc_1400934D7
0x14009354b  cmp     byte ptr [rdi+8], 0
0x14009354f  jnz     short loc_14009358D
0x140093551  mov     rcx, [rdi+58h]
0x140093555  mov     rax, rcx
0x140093558  shr     rax, 20h
0x14009355c  cmp     ecx, eax
0x14009355e  jle     short loc_14009357B
0x140093560  nop
0x140093561  mov     ecx, 0FFFFFFFFh
0x140093566  lock xadd [rdi+58h], ecx
0x14009356b  nop
0x14009356c  dec     ecx
0x14009356e  mov     eax, [rdi+5Ch]
0x140093571  cmp     ecx, eax
0x140093573  jge     short loc_1400935AC
0x140093575  nop
0x140093576  lock inc dword ptr [rdi+58h]
0x14009357a  nop
0x14009357b  mov     edx, [rdi+4]
0x14009357e  jmp     loc_140093460
0x140093583  mov     eax, 0C000009Ah
0x140093588  jmp     loc_1400934E3
0x14009358d  cmp     byte ptr [rdi+9], 0
0x140093591  lea     rcx, [rdi+40h]; Lookaside
0x140093595  jz      loc_1401F9824
0x14009359b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400935a2  nop     dword ptr [rax+rax+00h]
0x1400935a7  jmp     loc_140093495
0x1400935ac  test    ecx, ecx
0x1400935ae  js      short loc_140093575
0x1400935b0  lea     rcx, [rdi+40h]; ListHead
0x1400935b4  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400935bb  nop     dword ptr [rax+rax+00h]
0x1400935c0  jmp     loc_140093495
0x1400935c5  mov     rcx, [rsi+58h]
0x1400935c9  cmp     ecx, [rsi+50h]
0x1400935cc  jl      loc_1401F9844
0x1400935d2  mov     rax, rcx
0x1400935d5  shr     rax, 20h
0x1400935d9  cmp     eax, ecx
0x1400935db  jge     loc_1401F9844
0x1400935e1  xor     edx, edx; Tag
0x1400935e3  mov     rcx, r8; P
0x1400935e6  call    cs:__imp_ExFreePoolWithTag
0x1400935ed  nop     dword ptr [rax+rax+00h]
0x1400935f2  jmp     loc_140093531
0x1401f9824  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1401f982b  nop     dword ptr [rax+rax+00h]
0x1401f9830  nop
0x1401f9831  jmp     loc_140093495
0x1401f9836  test    rax, rax
0x1401f9839  jz      loc_140093583
0x1401f983f  jmp     loc_14009349E
0x1401f9844  lea     rcx, [rsi+40h]; ListHead
0x1401f9848  mov     rdx, r8; ListEntry
0x1401f984b  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f9852  nop     dword ptr [rax+rax+00h]
0x1401f9857  nop
0x1401f9858  lock inc dword ptr [rsi+58h]
0x1401f985c  nop
0x1401f985d  jmp     loc_140093531
```
