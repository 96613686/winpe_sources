# CmsAvlTableLite::PreAllocateForInsert(_CmsRow *,_SmsPreAllocatedRow *,ulong)

- ea: `0x140093a70`
- end: `0x140093d1f`
- name: `?PreAllocateForInsert@CmsAvlTableLite@@SAJPEAU_CmsRow@@PEAU_SmsPreAllocatedRow@@K@Z`
- size: `687`
- prototype: `__int64 __fastcall(struct _CmsRow *, struct _SmsPreAllocatedRow *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140093a1c`

## callees

- `0x140093a70`
- `0x1400c8574`
- `0x1401e9e40`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140093cbe`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140093cf4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140093cbe`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140093cf4`
- `ntoskrnl!ExAllocatePool2` at `0x140093aea`
- `ntoskrnl!ExAllocatePool2` at `0x140093b3e`
- `ntoskrnl!ExAllocatePool2` at `0x140093bb1`
- `ntoskrnl!ExAllocatePool2` at `0x140093aea`
- `ntoskrnl!ExAllocatePool2` at `0x140093b3e`
- `ntoskrnl!ExAllocatePool2` at `0x140093bb1`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140093aab`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140093b0f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140093aab`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140093b0f`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f9862`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f9874`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f9862`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f9874`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140093cd8`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140093d0e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140093cd8`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140093d0e`

## string_xrefs

- `0x1401f9886`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsAvlTableLite::PreAllocateForInsert(struct _CmsRow *a1, struct _SmsPreAllocatedRow *a2)
{
  int v2; // ebp
  char v4; // r15
  unsigned int v6; // eax
  unsigned __int64 v7; // rbx
  unsigned int *v8; // rsi
  unsigned __int64 v9; // rdx
  __int64 Pool2; // rax
  __int64 v11; // rbx
  __int64 v12; // rsi
  unsigned __int64 v13; // rdx
  __int64 v14; // rax
  int v15; // ecx
  __int16 v16; // si
  int v18; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v19; // rcx
  void *v20; // rax
  struct _NPAGED_LOOKASIDE_LIST *v21; // rcx
  void *v22; // rax

  v2 = *((_DWORD *)a1 + 4);
  v4 = *(_BYTE *)a1;
  v6 = ((v2 + 7) & 0xFFFFFFF8) + 32;
  v7 = v6;
  if ( v6 <= CmsAvlTableLite::SizeOfAllocationsOnLookaside2 )
  {
    if ( v6 <= CmsAvlTableLite::SizeOfAllocationsOnLookaside1 )
    {
      v8 = (unsigned int *)(qword_140262458 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
      if ( v7 > *v8 )
      {
        v8 = 0;
        v9 = v7 + 16;
        goto LABEL_5;
      }
      if ( !*((_BYTE *)v8 + 8) )
      {
        if ( (int)*((_QWORD *)v8 + 11) > (int)HIDWORD(*((_QWORD *)v8 + 11)) )
        {
          v15 = _InterlockedDecrement((volatile signed __int32 *)v8 + 22);
          if ( v15 >= (int)v8[23] && v15 >= 0 )
          {
            v20 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v8 + 4);
            goto LABEL_26;
          }
          _InterlockedIncrement((volatile signed __int32 *)v8 + 22);
        }
LABEL_17:
        v9 = v8[1];
LABEL_5:
        Pool2 = ExAllocatePool2(66, v9, 1766871885);
        v11 = Pool2;
        if ( (Pool2 & 0xF) == 0 )
        {
          if ( !Pool2 )
          {
LABEL_28:
            v16 = 0x2000;
            goto LABEL_29;
          }
LABEL_27:
          *(_QWORD *)v11 = v8;
          v11 += 16;
          goto LABEL_28;
        }
LABEL_44:
        MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
      }
      v19 = (struct _NPAGED_LOOKASIDE_LIST *)(v8 + 16);
      if ( *((_BYTE *)v8 + 9) )
        v20 = ExAllocateFromNPagedLookasideList(v19);
      else
        v20 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v19);
LABEL_26:
      v11 = (__int64)v20;
      if ( v20 )
        goto LABEL_27;
      goto LABEL_17;
    }
    KeGetCurrentProcessorNumberEx(0);
    v12 = qword_140262460;
    if ( v7 > *(unsigned int *)qword_140262460 )
    {
      v12 = 0;
      v13 = v7 + 16;
      goto LABEL_10;
    }
    if ( !*(_BYTE *)(qword_140262460 + 8) )
    {
      if ( (int)*(_QWORD *)(qword_140262460 + 88) > (int)HIDWORD(*(_QWORD *)(qword_140262460 + 88)) )
      {
        v18 = _InterlockedDecrement((volatile signed __int32 *)(qword_140262460 + 88));
        if ( v18 >= *(_DWORD *)(v12 + 92) && v18 >= 0 )
        {
          v22 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v12 + 64));
          goto LABEL_31;
        }
        _InterlockedIncrement((volatile signed __int32 *)(v12 + 88));
      }
LABEL_25:
      v13 = *(unsigned int *)(v12 + 4);
LABEL_10:
      v14 = ExAllocatePool2(66, v13, 1766871885);
      v11 = v14;
      if ( (v14 & 0xF) != 0 )
        goto LABEL_44;
      if ( !v14 )
      {
LABEL_33:
        v16 = 0x4000;
LABEL_29:
        if ( !v11 )
          return 3221225626LL;
LABEL_20:
        *(_WORD *)(v11 + 28) = 0;
        memmove((void *)(v11 + 32), *((const void **)a1 + 3), *((unsigned int *)a1 + 4));
        *(_BYTE *)(v11 + 26) = 32;
        *(_WORD *)(v11 + 28) |= v16;
        *(_WORD *)(v11 + 30) = v2;
        *(_BYTE *)(v11 + 27) = v4;
        *((_QWORD *)a2 + 4) = v11;
        *(_DWORD *)a2 = *(unsigned __int8 *)(v11 + 27);
        *((_QWORD *)a2 + 1) = v11 + *(unsigned __int8 *)(v11 + 26);
        *((_WORD *)a2 + 2) = 0;
        *((_DWORD *)a2 + 4) = *(unsigned __int16 *)(v11 + 30);
        *((_QWORD *)a2 + 3) = v11 + *(unsigned __int8 *)(v11 + 26);
        return 0;
      }
LABEL_32:
      *(_QWORD *)v11 = v12;
      v11 += 16;
      goto LABEL_33;
    }
    v21 = (struct _NPAGED_LOOKASIDE_LIST *)(qword_140262460 + 64);
    if ( *(_BYTE *)(qword_140262460 + 9) )
      v22 = ExAllocateFromNPagedLookasideList(v21);
    else
      v22 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v21);
LABEL_31:
    v11 = (__int64)v22;
    if ( v22 )
      goto LABEL_32;
    goto LABEL_25;
  }
  v11 = ExAllocatePool2(66, ((v2 + 7) & 0xFFFFFFF8) + 32, 1766871885);
  if ( v11 )
  {
    v16 = 0x8000;
    goto LABEL_20;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x140093a70  push    rbx
0x140093a72  push    rbp
0x140093a73  push    rsi
0x140093a74  push    rdi
0x140093a75  push    r14
0x140093a77  push    r15
0x140093a79  sub     rsp, 28h
0x140093a7d  mov     ebp, [rcx+10h]
0x140093a80  mov     rdi, rdx
0x140093a83  movzx   r15d, byte ptr [rcx]
0x140093a87  mov     r14, rcx
0x140093a8a  lea     eax, [rbp+7]
0x140093a8d  and     eax, 0FFFFFFF8h
0x140093a90  add     eax, 20h ; ' '
0x140093a93  cmp     eax, cs:?SizeOfAllocationsOnLookaside2@CmsAvlTableLite@@2KA; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside2
0x140093a99  mov     ebx, eax
0x140093a9b  ja      loc_140093BA3
0x140093aa1  xor     ecx, ecx; ProcNumber
0x140093aa3  cmp     eax, cs:?SizeOfAllocationsOnLookaside1@CmsAvlTableLite@@2KA; ulong CmsAvlTableLite::SizeOfAllocationsOnLookaside1
0x140093aa9  ja      short loc_140093B0F
0x140093aab  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140093ab2  nop     dword ptr [rax+rax+00h]
0x140093ab7  xor     edx, edx
0x140093ab9  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140093abf  lea     rsi, [rdx+rdx*2]
0x140093ac3  shl     rsi, 6
0x140093ac7  add     rsi, cs:qword_140262458
0x140093ace  mov     eax, [rsi]
0x140093ad0  cmp     rbx, rax
0x140093ad3  jbe     loc_140093B63
0x140093ad9  xor     esi, esi
0x140093adb  lea     rdx, [rbx+10h]
0x140093adf  mov     ecx, 42h ; 'B'
0x140093ae4  mov     r8d, 6950534Dh
0x140093aea  call    cs:__imp_ExAllocatePool2
0x140093af1  nop     dword ptr [rax+rax+00h]
0x140093af6  mov     rbx, rax
0x140093af9  test    al, 0Fh
0x140093afb  jnz     loc_1401F9886
0x140093b01  test    rax, rax
0x140093b04  jz      loc_140093C85
0x140093b0a  jmp     loc_140093C7E
0x140093b0f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140093b16  nop     dword ptr [rax+rax+00h]
0x140093b1b  mov     rsi, cs:qword_140262460
0x140093b22  mov     eax, [rsi]
0x140093b24  cmp     rbx, rax
0x140093b27  jbe     loc_140093C32
0x140093b2d  xor     esi, esi
0x140093b2f  lea     rdx, [rbx+10h]
0x140093b33  mov     ecx, 42h ; 'B'
0x140093b38  mov     r8d, 6950534Dh
0x140093b3e  call    cs:__imp_ExAllocatePool2
0x140093b45  nop     dword ptr [rax+rax+00h]
0x140093b4a  mov     rbx, rax
0x140093b4d  test    al, 0Fh
0x140093b4f  jnz     loc_1401F9886
0x140093b55  test    rax, rax
0x140093b58  jz      loc_140093CA9
0x140093b5e  jmp     loc_140093CA2
0x140093b63  cmp     byte ptr [rsi+8], 0
0x140093b67  jnz     loc_140093CB0
0x140093b6d  mov     rcx, [rsi+58h]
0x140093b71  mov     rax, rcx
0x140093b74  shr     rax, 20h
0x140093b78  cmp     ecx, eax
0x140093b7a  jle     short loc_140093B9B
0x140093b7c  nop
0x140093b7d  mov     ecx, 0FFFFFFFFh
0x140093b82  lock xadd [rsi+58h], ecx
0x140093b87  nop
0x140093b88  dec     ecx
0x140093b8a  mov     eax, [rsi+5Ch]
0x140093b8d  cmp     ecx, eax
0x140093b8f  jge     loc_140093CCC
0x140093b95  nop
0x140093b96  lock inc dword ptr [rsi+58h]
0x140093b9a  nop
0x140093b9b  mov     edx, [rsi+4]
0x140093b9e  jmp     loc_140093ADF
0x140093ba3  mov     r8d, 6950534Dh
0x140093ba9  mov     rdx, rbx
0x140093bac  mov     ecx, 42h ; 'B'
0x140093bb1  call    cs:__imp_ExAllocatePool2
0x140093bb8  nop     dword ptr [rax+rax+00h]
0x140093bbd  mov     rbx, rax
0x140093bc0  test    rax, rax
0x140093bc3  jz      loc_140093C93
0x140093bc9  mov     esi, 8000h
0x140093bce  xor     eax, eax
0x140093bd0  lea     rcx, [rbx+20h]; void *
0x140093bd4  mov     [rbx+1Ch], ax
0x140093bd8  mov     r8d, [r14+10h]; Size
0x140093bdc  mov     rdx, [r14+18h]; Src
0x140093be0  call    memmove
0x140093be5  mov     byte ptr [rbx+1Ah], 20h ; ' '
0x140093be9  or      [rbx+1Ch], si
0x140093bed  mov     [rbx+1Eh], bp
0x140093bf1  mov     [rbx+1Bh], r15b
0x140093bf5  mov     [rdi+20h], rbx
0x140093bf9  movzx   eax, byte ptr [rbx+1Bh]
0x140093bfd  mov     [rdi], eax
0x140093bff  movzx   eax, byte ptr [rbx+1Ah]
0x140093c03  add     rax, rbx
0x140093c06  mov     [rdi+8], rax
0x140093c0a  xor     eax, eax
0x140093c0c  mov     [rdi+4], ax
0x140093c10  movzx   eax, word ptr [rbx+1Eh]
0x140093c14  mov     [rdi+10h], eax
0x140093c17  movzx   eax, byte ptr [rbx+1Ah]
0x140093c1b  add     rax, rbx
0x140093c1e  mov     [rdi+18h], rax
0x140093c22  xor     eax, eax
0x140093c24  add     rsp, 28h
0x140093c28  pop     r15
0x140093c2a  pop     r14
0x140093c2c  pop     rdi
0x140093c2d  pop     rsi
0x140093c2e  pop     rbp
0x140093c2f  pop     rbx
0x140093c30  retn
0x140093c32  cmp     byte ptr [rsi+8], 0
0x140093c36  jnz     loc_140093CE6
0x140093c3c  mov     rcx, [rsi+58h]
0x140093c40  mov     rax, rcx
0x140093c43  shr     rax, 20h
0x140093c47  cmp     ecx, eax
0x140093c49  jle     short loc_140093C6A
0x140093c4b  nop
0x140093c4c  mov     ecx, 0FFFFFFFFh
0x140093c51  lock xadd [rsi+58h], ecx
0x140093c56  nop
0x140093c57  dec     ecx
0x140093c59  mov     eax, [rsi+5Ch]
0x140093c5c  cmp     ecx, eax
0x140093c5e  jge     loc_140093D02
0x140093c64  nop
0x140093c65  lock inc dword ptr [rsi+58h]
0x140093c69  nop
0x140093c6a  mov     edx, [rsi+4]
0x140093c6d  jmp     loc_140093B33
0x140093c72  mov     rbx, rax
0x140093c75  test    rax, rax
0x140093c78  jz      loc_140093B9B
0x140093c7e  mov     [rbx], rsi
0x140093c81  add     rbx, 10h
0x140093c85  mov     esi, 2000h
0x140093c8a  test    rbx, rbx
0x140093c8d  jnz     loc_140093BCE
0x140093c93  mov     eax, 0C000009Ah
0x140093c98  jmp     short loc_140093C24
0x140093c9a  mov     rbx, rax
0x140093c9d  test    rax, rax
0x140093ca0  jz      short loc_140093C6A
0x140093ca2  mov     [rbx], rsi
0x140093ca5  add     rbx, 10h
0x140093ca9  mov     esi, 4000h
0x140093cae  jmp     short loc_140093C8A
0x140093cb0  cmp     byte ptr [rsi+9], 0
0x140093cb4  lea     rcx, [rsi+40h]; Lookaside
0x140093cb8  jz      loc_1401F9862
0x140093cbe  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140093cc5  nop     dword ptr [rax+rax+00h]
0x140093cca  jmp     short loc_140093C72
0x140093ccc  test    ecx, ecx
0x140093cce  js      loc_140093B95
0x140093cd4  lea     rcx, [rsi+40h]; ListHead
0x140093cd8  call    cs:__imp_ExpInterlockedPopEntrySList
0x140093cdf  nop     dword ptr [rax+rax+00h]
0x140093ce4  jmp     short loc_140093C72
0x140093ce6  cmp     byte ptr [rsi+9], 0
0x140093cea  lea     rcx, [rsi+40h]; Lookaside
0x140093cee  jz      loc_1401F9874
0x140093cf4  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140093cfb  nop     dword ptr [rax+rax+00h]
0x140093d00  jmp     short loc_140093C9A
0x140093d02  test    ecx, ecx
0x140093d04  js      loc_140093C64
0x140093d0a  lea     rcx, [rsi+40h]; ListHead
0x140093d0e  call    cs:__imp_ExpInterlockedPopEntrySList
0x140093d15  nop     dword ptr [rax+rax+00h]
0x140093d1a  jmp     loc_140093C9A
0x1401f9862  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1401f9869  nop     dword ptr [rax+rax+00h]
0x1401f986e  nop
0x1401f986f  jmp     loc_140093C72
0x1401f9874  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1401f987b  nop     dword ptr [rax+rax+00h]
0x1401f9880  nop
0x1401f9881  jmp     loc_140093C9A
0x1401f9886  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x1401f988d  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
```
