# CmsKeyRange::CopyTo(CmsTransactionContext *,CmsKeyRange &)

- ea: `0x140078e60`
- end: `0x14007911e`
- name: `?CopyTo@CmsKeyRange@@QEAAJPEAVCmsTransactionContext@@AEAV1@@Z`
- size: `702`
- prototype: `int(CmsKeyRange *__hidden this, struct CmsTransactionContext *, struct CmsKeyRange *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400646a0`
- `0x1400cd3d4`

## callees

- `0x140078e60`
- `0x140089420`
- `0x1400ceda0`
- `0x1401f4100`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007903c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007903c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400790c2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400790c2`
- `ntoskrnl!ExAllocatePool2` at `0x140078f65`
- `ntoskrnl!ExAllocatePool2` at `0x140078f65`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140078f27`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140078f27`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401ff3e6`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401ff3e6`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140079095`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140079095`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401ff40d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401ff40d`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400790db`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400790db`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007910d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007910d`

## string_xrefs

- `0x140078f7c`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsKeyRange::CopyTo(CmsKeyRange *this, struct CmsTransactionContext *a2, struct CmsKeyRange *a3)
{
  size_t v6; // rbp
  const void *v8; // r13
  int v9; // r15d
  _QWORD *v10; // r14
  int v11; // r12d
  __int64 v12; // r9
  __int64 v13; // r15
  size_t v14; // rdx
  __int64 Pool2; // rax
  __int64 v16; // rcx
  unsigned int v17; // eax
  struct _SLIST_ENTRY *v18; // r8
  __int64 v19; // rcx
  int v20; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v21; // rcx
  _QWORD *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // [rsp+50h] [rbp+8h]

  if ( *(_QWORD *)a3 )
    CmsKeyRange::FreeKeysBuffer(a3);
  *(_OWORD *)a3 = 0;
  *((_OWORD *)a3 + 1) = 0;
  *((_DWORD *)a3 + 6) = 3;
  v6 = *((unsigned int *)this + 2);
  if ( !(_DWORD)v6 )
    goto LABEL_4;
  v8 = *(const void **)this;
  if ( a2 && !*((_BYTE *)a2 + 129) && (unsigned int)v6 <= 0x60 )
  {
    *((_BYTE *)a2 + 129) = 1;
    v9 = 96;
    v10 = (_QWORD *)((char *)a2 + 2560);
    v11 = 8;
    goto LABEL_16;
  }
  v13 = qword_140269420 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( (unsigned int)v6 > *(_DWORD *)v13 )
  {
    v13 = 0;
    v14 = v6 + 16;
    goto LABEL_11;
  }
  if ( *(_BYTE *)(v13 + 8) )
  {
    v21 = (struct _NPAGED_LOOKASIDE_LIST *)(v13 + 64);
    if ( *(_BYTE *)(v13 + 9) )
      v22 = ExAllocateFromNPagedLookasideList(v21);
    else
      v22 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v21);
  }
  else
  {
    if ( (int)*(_QWORD *)(v13 + 88) <= (int)HIDWORD(*(_QWORD *)(v13 + 88)) )
      goto LABEL_33;
    v20 = _InterlockedDecrement((volatile signed __int32 *)(v13 + 88));
    if ( v20 < *(_DWORD *)(v13 + 92) || v20 < 0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v13 + 88));
      goto LABEL_33;
    }
    v22 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v13 + 64));
  }
  v10 = v22;
  if ( !v22 )
  {
LABEL_33:
    v14 = *(unsigned int *)(v13 + 4);
LABEL_11:
    Pool2 = ExAllocatePool2(66, v14, 1766871885, v12);
    v10 = (_QWORD *)Pool2;
    if ( (Pool2 & 0xF) != 0 )
      MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
    if ( !Pool2 )
      goto LABEL_15;
  }
  *v10 = v13;
  v10 += 2;
LABEL_15:
  v9 = v6;
  v11 = 0;
LABEL_16:
  if ( v10 )
  {
    if ( !*(_QWORD *)a3 )
      goto LABEL_21;
    memmove(v10, *(const void **)a3, *((unsigned int *)a3 + 2));
    v16 = *(_QWORD *)a3;
    if ( (*((_DWORD *)a3 + 6) & 8) != 0 )
    {
      *(_BYTE *)(v16 - 2431) = 0;
      *((_DWORD *)a3 + 6) &= ~8u;
    }
    else if ( v16 )
    {
      v18 = (struct _SLIST_ENTRY *)(v16 - 16);
      v19 = *(_QWORD *)(v16 - 16);
      v24 = v19;
      if ( !v19 )
        goto LABEL_41;
      if ( *(_BYTE *)(v19 + 8) )
      {
        if ( *(_BYTE *)(v19 + 9) )
          ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v19 + 64), v18);
        else
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)(v19 + 64), v18);
        goto LABEL_20;
      }
      v23 = *(_QWORD *)(v19 + 88);
      if ( (int)v23 < *(_DWORD *)(v19 + 80) || SHIDWORD(v23) >= (int)v23 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v19 + 64), v18);
        _InterlockedIncrement((volatile signed __int32 *)(v24 + 88));
      }
      else
      {
LABEL_41:
        ExFreePoolWithTag(v18, 0);
      }
    }
LABEL_20:
    *((_DWORD *)a3 + 2) = 0;
LABEL_21:
    v17 = *((_DWORD *)a3 + 6) & 0xFFFFFFF7;
    *(_QWORD *)a3 = v10;
    *((_DWORD *)a3 + 2) = v9;
    *((_DWORD *)a3 + 6) = v11 | v17;
    if ( v8 )
      memmove(v10, v8, v6);
LABEL_4:
    *((_DWORD *)a3 + 3) = *((_DWORD *)this + 3);
    *((_DWORD *)a3 + 4) = *((_DWORD *)this + 4);
    *((_WORD *)a3 + 10) = *((_WORD *)this + 10);
    *((_WORD *)a3 + 11) = *((_WORD *)this + 11);
    *((_DWORD *)a3 + 6) = *((_DWORD *)this + 6) ^ (*((_DWORD *)a3 + 6) ^ *((_DWORD *)this + 6)) & 8;
    return 0;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x140078e60  push    rbx
0x140078e62  push    rbp
0x140078e63  push    rsi
0x140078e64  push    rdi
0x140078e65  push    r14
0x140078e67  sub     rsp, 20h
0x140078e6b  cmp     qword ptr [r8], 0
0x140078e6f  mov     rbx, r8
0x140078e72  mov     r14, rdx
0x140078e75  mov     rdi, rcx
0x140078e78  jnz     loc_1400790A6
0x140078e7e  xorps   xmm0, xmm0
0x140078e81  mov     [rsp+48h+arg_8], r12
0x140078e86  movups  xmmword ptr [rbx], xmm0
0x140078e89  mov     [rsp+48h+arg_10], r13
0x140078e8e  movups  xmmword ptr [rbx+10h], xmm0
0x140078e92  mov     dword ptr [rbx+18h], 3
0x140078e99  mov     ebp, [rdi+8]
0x140078e9c  mov     [rsp+48h+arg_18], r15
0x140078ea1  test    ebp, ebp
0x140078ea3  jnz     short loc_140078EF1
0x140078ea5  mov     eax, [rdi+0Ch]
0x140078ea8  lea     rdx, [rbx+18h]
0x140078eac  mov     [rbx+0Ch], eax
0x140078eaf  mov     eax, [rdi+10h]
0x140078eb2  mov     [rbx+10h], eax
0x140078eb5  movzx   eax, word ptr [rdi+14h]
0x140078eb9  mov     [rbx+14h], ax
0x140078ebd  movzx   eax, word ptr [rdi+16h]
0x140078ec1  mov     [rbx+16h], ax
0x140078ec5  mov     eax, [rdi+18h]
0x140078ec8  mov     ecx, eax
0x140078eca  xor     ecx, [rdx]
0x140078ecc  and     ecx, 8
0x140078ecf  xor     ecx, eax
0x140078ed1  mov     [rbx+18h], ecx
0x140078ed4  xor     eax, eax
0x140078ed6  mov     r15, [rsp+48h+arg_18]
0x140078edb  mov     r13, [rsp+48h+arg_10]
0x140078ee0  mov     r12, [rsp+48h+arg_8]
0x140078ee5  add     rsp, 20h
0x140078ee9  pop     r14
0x140078eeb  pop     rdi
0x140078eec  pop     rsi
0x140078eed  pop     rbp
0x140078eee  pop     rbx
0x140078eef  retn
0x140078ef1  mov     r13, [rdi]
0x140078ef4  test    r14, r14
0x140078ef7  jz      short loc_140078F25
0x140078ef9  cmp     byte ptr [r14+81h], 0
0x140078f01  jnz     short loc_140078F25
0x140078f03  cmp     ebp, 60h ; '`'
0x140078f06  ja      short loc_140078F25
0x140078f08  mov     byte ptr [r14+81h], 1
0x140078f10  mov     r15d, 60h ; '`'
0x140078f16  add     r14, 0A00h
0x140078f1d  mov     r12d, 8
0x140078f23  jmp     short loc_140078FA2
0x140078f25  xor     ecx, ecx; ProcNumber
0x140078f27  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140078f2e  nop     dword ptr [rax+rax+00h]
0x140078f33  xor     edx, edx
0x140078f35  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140078f3b  lea     r15, [rdx+rdx*2]
0x140078f3f  shl     r15, 6
0x140078f43  add     r15, cs:qword_140269420
0x140078f4a  cmp     ebp, [r15]
0x140078f4d  jbe     loc_140079054
0x140078f53  xor     r15d, r15d
0x140078f56  lea     rdx, [rbp+10h]
0x140078f5a  mov     ecx, 42h ; 'B'
0x140078f5f  mov     r8d, 6950534Dh
0x140078f65  call    cs:__imp_ExAllocatePool2
0x140078f6c  nop     dword ptr [rax+rax+00h]
0x140078f71  mov     r14, rax
0x140078f74  test    al, 0Fh
0x140078f76  jz      loc_1401FF3F8
0x140078f7c  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x140078f83  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x140078f89  mov     r14, rax
0x140078f8c  test    rax, rax
0x140078f8f  jz      loc_140079088
0x140078f95  mov     [r14], r15
0x140078f98  add     r14, 10h
0x140078f9c  mov     r15d, ebp
0x140078f9f  xor     r12d, r12d
0x140078fa2  test    r14, r14
0x140078fa5  jz      loc_14007904A
0x140078fab  mov     rdx, [rbx]; Src
0x140078fae  test    rdx, rdx
0x140078fb1  jz      short loc_140078FDB
0x140078fb3  mov     r8d, [rbx+8]; Size
0x140078fb7  mov     rcx, r14; void *
0x140078fba  call    memmove
0x140078fbf  mov     eax, [rbx+18h]
0x140078fc2  mov     rcx, [rbx]
0x140078fc5  test    al, 8
0x140078fc7  jz      short loc_14007900A
0x140078fc9  mov     byte ptr [rcx-97Fh], 0
0x140078fd0  and     dword ptr [rbx+18h], 0FFFFFFF7h
0x140078fd4  mov     dword ptr [rbx+8], 0
0x140078fdb  mov     eax, [rbx+18h]
0x140078fde  and     eax, 0FFFFFFF7h
0x140078fe1  mov     [rbx], r14
0x140078fe4  or      eax, r12d
0x140078fe7  mov     [rbx+8], r15d
0x140078feb  mov     [rbx+18h], eax
0x140078fee  test    r13, r13
0x140078ff1  jz      loc_140078EA5
0x140078ff7  mov     r8, rbp; Size
0x140078ffa  mov     rdx, r13; Src
0x140078ffd  mov     rcx, r14; void *
0x140079000  call    memmove
0x140079005  jmp     loc_140078EA5
0x14007900a  test    rcx, rcx
0x14007900d  jz      short loc_140078FD4
0x14007900f  lea     r8, [rcx-10h]
0x140079013  mov     rcx, [rcx-10h]
0x140079017  mov     [rsp+48h+arg_0], rcx
0x14007901c  test    rcx, rcx
0x14007901f  jz      loc_140079108
0x140079025  cmp     byte ptr [rcx+8], 0
0x140079029  jz      loc_1400790EC
0x14007902f  cmp     byte ptr [rcx+9], 0
0x140079033  mov     rdx, r8; Entry
0x140079036  jz      short loc_140079091
0x140079038  add     rcx, 40h ; '@'; Lookaside
0x14007903c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140079043  nop     dword ptr [rax+rax+00h]
0x140079048  jmp     short loc_140078FD4
0x14007904a  mov     eax, 0C000009Ah
0x14007904f  jmp     loc_140078ED6
0x140079054  cmp     byte ptr [r15+8], 0
0x140079059  jnz     short loc_1400790B3
0x14007905b  mov     rcx, [r15+58h]
0x14007905f  mov     rax, rcx
0x140079062  shr     rax, 20h
0x140079066  cmp     ecx, eax
0x140079068  jle     short loc_140079088
0x14007906a  nop
0x14007906b  mov     ecx, 0FFFFFFFFh
0x140079070  lock xadd [r15+58h], ecx
0x140079076  nop
0x140079077  dec     ecx
0x140079079  mov     eax, [r15+5Ch]
0x14007907d  cmp     ecx, eax
0x14007907f  jge     short loc_1400790D3
0x140079081  nop
0x140079082  lock inc dword ptr [r15+58h]
0x140079087  nop
0x140079088  mov     edx, [r15+4]
0x14007908c  jmp     loc_140078F5A
0x140079091  add     rcx, 40h ; '@'; Lookaside
0x140079095  call    cs:__imp_ExFreeToPagedLookasideList
0x14007909c  nop     dword ptr [rax+rax+00h]
0x1400790a1  jmp     loc_140078FD4
0x1400790a6  mov     rcx, rbx; this
0x1400790a9  call    ?FreeKeysBuffer@CmsKeyRange@@QEAAXXZ; CmsKeyRange::FreeKeysBuffer(void)
0x1400790ae  jmp     loc_140078E7E
0x1400790b3  cmp     byte ptr [r15+9], 0
0x1400790b8  lea     rcx, [r15+40h]; Lookaside
0x1400790bc  jz      loc_1401FF3E6
0x1400790c2  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400790c9  nop     dword ptr [rax+rax+00h]
0x1400790ce  jmp     loc_140078F89
0x1400790d3  test    ecx, ecx
0x1400790d5  js      short loc_140079081
0x1400790d7  lea     rcx, [r15+40h]; ListHead
0x1400790db  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400790e2  nop     dword ptr [rax+rax+00h]
0x1400790e7  jmp     loc_140078F89
0x1400790ec  mov     rdx, [rcx+58h]
0x1400790f0  cmp     edx, [rcx+50h]
0x1400790f3  jl      loc_1401FF406
0x1400790f9  mov     rax, rdx
0x1400790fc  shr     rax, 20h
0x140079100  cmp     eax, edx
0x140079102  jge     loc_1401FF406
0x140079108  xor     edx, edx; Tag
0x14007910a  mov     rcx, r8; P
0x14007910d  call    cs:__imp_ExFreePoolWithTag
0x140079114  nop     dword ptr [rax+rax+00h]
0x140079119  jmp     loc_140078FD4
0x1401ff3e6  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1401ff3ed  nop     dword ptr [rax+rax+00h]
0x1401ff3f2  nop
0x1401ff3f3  jmp     loc_140078F89
0x1401ff3f8  test    rax, rax
0x1401ff3fb  jz      loc_140078F9C
0x1401ff401  jmp     loc_140078F95
0x1401ff406  add     rcx, 40h ; '@'; ListHead
0x1401ff40a  mov     rdx, r8; ListEntry
0x1401ff40d  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401ff414  nop     dword ptr [rax+rax+00h]
0x1401ff419  mov     rax, [rsp+48h+arg_0]
0x1401ff41e  nop
0x1401ff41f  lock inc dword ptr [rax+58h]
0x1401ff423  nop
0x1401ff424  jmp     loc_140078FD4
```
