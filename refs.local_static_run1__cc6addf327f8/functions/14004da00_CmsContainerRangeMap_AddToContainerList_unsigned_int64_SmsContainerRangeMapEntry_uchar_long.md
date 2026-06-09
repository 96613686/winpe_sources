# CmsContainerRangeMap::AddToContainerList(unsigned __int64,_SmsContainerRangeMapEntry *,uchar,long *)

- ea: `0x14004da00`
- end: `0x14004dcba`
- name: `?AddToContainerList@CmsContainerRangeMap@@AEAAJ_KPEAU_SmsContainerRangeMapEntry@@EPEAJ@Z`
- size: `698`
- prototype: `__int64 __usercall@<rax>(CmsContainerRangeMap *__hidden this@<rcx>, unsigned __int64@<rdx>, struct _SmsContainerRangeMapEntry *@<r8>, unsigned __int8@<r9b>, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140055570`

## callees

- `0x140024c60`
- `0x14004da00`
- `0x14004dcc0`
- `0x14004dd04`
- `0x140095e10`
- `0x1400ceda0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004dc85`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004dc85`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14004da5d`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14004da5d`
- `ntoskrnl!ExAllocatePool2` at `0x14004db65`
- `ntoskrnl!ExAllocatePool2` at `0x14004db65`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004db25`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004db25`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fd3a2`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401fd3a2`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14004dc9e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14004dc9e`
- `ntoskrnl!ExReleasePushLockEx` at `0x14004da89`
- `ntoskrnl!ExReleasePushLockEx` at `0x14004dac9`
- `ntoskrnl!ExReleasePushLockEx` at `0x14004dc0e`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401fd3db`
- `ntoskrnl!ExReleasePushLockEx` at `0x14004da89`
- `ntoskrnl!ExReleasePushLockEx` at `0x14004dac9`
- `ntoskrnl!ExReleasePushLockEx` at `0x14004dc0e`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401fd3db`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14004dbd5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14004dbd5`

## string_xrefs

- `0x14004db7c`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsContainerRangeMap::AddToContainerList(
        CmsContainerRangeMap *this,
        struct _SLIST_ENTRY *a2,
        struct _SmsContainerRangeMapEntry *a3,
        char a4,
        int *a5)
{
  PSLIST_ENTRY *v9; // rbx
  _QWORD *v10; // rsi
  struct _SLIST_ENTRY *v11; // rax
  PSLIST_ENTRY v12; // rbx
  unsigned int v13; // esi
  __int64 v15; // rbp
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 Pool2; // rax
  PSLIST_ENTRY *v19; // r15
  struct _SLIST_ENTRY *v20; // rax
  PSLIST_ENTRY *v21; // rcx
  int v22; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v23; // rcx
  struct _SLIST_ENTRY *v24; // rax
  _QWORD *v25; // rax
  unsigned int v26; // eax
  struct _SLIST_ENTRY *v27; // [rsp+50h] [rbp+8h] BYREF

  v9 = (PSLIST_ENTRY *)(*(_QWORD *)this
                      + 24LL
                      * ((((unsigned int)(1103515245 * (_DWORD)a2 + 12345) >> 16) | (69069 * (_DWORD)a2 + 1)
                                                                                  & 0xFFFF0000)
                       % *((_DWORD *)this + 2)));
  v10 = v9 + 2;
  ExAcquirePushLockSharedEx(v9 + 2, 4);
  if ( v9[1] )
  {
    v11 = *v9;
    v12 = *v9;
    while ( v12[1].Next != a2 )
    {
      v12 = v12->Next;
      if ( v12 == v11 )
        goto LABEL_5;
    }
    ExReleasePushLockEx(v10, 0);
    v13 = 0;
    goto LABEL_8;
  }
LABEL_5:
  ExReleasePushLockEx(v10, 0);
  v13 = 0;
  if ( a4 )
  {
    _InterlockedDecrement(a5);
    v12 = CmsLookasides::Allocate(0x30u, 0x15u, 1);
    goto LABEL_11;
  }
  v15 = qword_1402694B8 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( *(_DWORD *)v15 < 0x30u )
  {
    v15 = 0;
    v17 = 64;
    goto LABEL_15;
  }
  if ( *(_BYTE *)(v15 + 8) )
  {
    v23 = (struct _NPAGED_LOOKASIDE_LIST *)(v15 + 64);
    if ( *(_BYTE *)(v15 + 9) )
      v24 = (struct _SLIST_ENTRY *)ExAllocateFromNPagedLookasideList(v23);
    else
      v24 = (struct _SLIST_ENTRY *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v23);
LABEL_9:
    v12 = v24;
    if ( v24 )
    {
LABEL_10:
      v12->Next = (struct _SLIST_ENTRY *)v15;
      ++v12;
      goto LABEL_11;
    }
    goto LABEL_27;
  }
  if ( (int)*(_QWORD *)(v15 + 88) > (int)HIDWORD(*(_QWORD *)(v15 + 88)) )
  {
    v22 = _InterlockedDecrement((volatile signed __int32 *)(v15 + 88));
    if ( v22 >= *(_DWORD *)(v15 + 92) && v22 >= 0 )
    {
      v24 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v15 + 64));
      goto LABEL_9;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v15 + 88));
  }
LABEL_27:
  v17 = *(unsigned int *)(v15 + 4);
LABEL_15:
  Pool2 = ExAllocatePool2(66, v17, 1766871885, v16);
  v12 = (PSLIST_ENTRY)Pool2;
  if ( (Pool2 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( Pool2 )
    goto LABEL_10;
LABEL_11:
  v27 = v12;
  if ( v12 )
  {
    *((_QWORD *)&v12[1].Next + 1) = 0;
    v12[2].Next = 0;
    *((_QWORD *)&v12[2].Next + 1) = 0;
    *((_QWORD *)&v12->Next + 1) = 0;
    v12->Next = 0;
    v12[1].Next = a2;
    v19 = (PSLIST_ENTRY *)(*(_QWORD *)this
                         + 24
                         * (((69069 * (_DWORD)a2 + 1) & 0xFFFF0000
                           | (unsigned __int64)((unsigned int)(1103515245 * (_DWORD)a2 + 12345) >> 16))
                          % *((unsigned int *)this + 2)));
    ExAcquirePushLockExclusiveEx(v19 + 2, 0);
    if ( v19[1] )
    {
      v25 = *v19;
      while ( (struct _SLIST_ENTRY *)v25[2] != a2 )
      {
        v25 = (_QWORD *)*v25;
        if ( v25 == (_QWORD *)*v19 )
          goto LABEL_18;
      }
      ExReleasePushLockEx(v19 + 2, 0);
      CmsLookasides::Free(v12);
      v26 = CmsHashTableLite::PinInIndex<1>(this, a2, &v27, 0);
      v12 = v27;
      v13 = v26;
    }
    else
    {
LABEL_18:
      v20 = *v19;
      if ( *v19 )
      {
        v21 = (PSLIST_ENTRY *)*((_QWORD *)&v20->Next + 1);
        if ( *v21 != v20 )
          __fastfail(3u);
        v12->Next = v20;
        *((_QWORD *)&v12->Next + 1) = v21;
        *v21 = v12;
        *((_QWORD *)&v20->Next + 1) = v12;
      }
      else
      {
        *((_QWORD *)&v12->Next + 1) = v12;
        v12->Next = v12;
        *v19 = v12;
      }
      v19[1] = (PSLIST_ENTRY)((char *)v19[1] + 1);
      _InterlockedIncrement((volatile signed __int32 *)this + 3);
      ExReleasePushLockEx(v19 + 2, 0);
    }
LABEL_8:
    CmsContainerRangeMap::InterlockedPushListEntry(this, (struct _SmsContainerRangeMapListHead *)v12, a3);
    return v13;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14004da00  mov     [rsp+arg_8], rbx
0x14004da05  mov     [rsp+arg_10], rbp
0x14004da0a  push    rsi
0x14004da0b  push    rdi
0x14004da0c  push    r12
0x14004da0e  push    r14
0x14004da10  push    r15
0x14004da12  sub     rsp, 20h
0x14004da16  imul    eax, edx, 10DCDh
0x14004da1c  mov     rdi, rdx
0x14004da1f  imul    edx, 41C64E6Dh
0x14004da25  mov     r14, rcx
0x14004da28  movzx   ebp, r9b
0x14004da2c  mov     r12, r8
0x14004da2f  inc     eax
0x14004da31  add     edx, 3039h
0x14004da37  and     eax, 0FFFF0000h
0x14004da3c  shr     edx, 10h
0x14004da3f  or      eax, edx
0x14004da41  xor     edx, edx
0x14004da43  div     dword ptr [rcx+8]
0x14004da46  mov     rax, [rcx]
0x14004da49  lea     rdx, [rdx+rdx*2]
0x14004da4d  lea     rbx, [rax+rdx*8]
0x14004da51  mov     edx, 4
0x14004da56  lea     rsi, [rbx+10h]
0x14004da5a  mov     rcx, rsi
0x14004da5d  call    cs:__imp_ExAcquirePushLockSharedEx
0x14004da64  nop     dword ptr [rax+rax+00h]
0x14004da69  cmp     qword ptr [rbx+8], 0
0x14004da6e  jbe     short loc_14004DA84
0x14004da70  mov     rax, [rbx]
0x14004da73  mov     rbx, rax
0x14004da76  cmp     [rbx+10h], rdi
0x14004da7a  jz      short loc_14004DAC4
0x14004da7c  mov     rbx, [rbx]
0x14004da7f  cmp     rbx, rax
0x14004da82  jnz     short loc_14004DA76
0x14004da84  xor     edx, edx
0x14004da86  mov     rcx, rsi
0x14004da89  call    cs:__imp_ExReleasePushLockEx
0x14004da90  nop     dword ptr [rax+rax+00h]
0x14004da95  xor     esi, esi
0x14004da97  test    bpl, bpl
0x14004da9a  jz      loc_14004DB23
0x14004daa0  mov     rax, [rsp+48h+arg_20]
0x14004daa5  nop
0x14004daa6  mov     edx, 15h
0x14004daab  mov     ecx, 30h ; '0'
0x14004dab0  mov     r8d, 1
0x14004dab6  lock dec dword ptr [rax]
0x14004dab9  nop
0x14004daba  call    ?Allocate@CmsLookasides@@SAPEAX_KW4EmsLookaside@@K@Z; CmsLookasides::Allocate(unsigned __int64,EmsLookaside,ulong)
0x14004dabf  mov     rbx, rax
0x14004dac2  jmp     short loc_14004DB12
0x14004dac4  xor     edx, edx
0x14004dac6  mov     rcx, rsi
0x14004dac9  call    cs:__imp_ExReleasePushLockEx
0x14004dad0  nop     dword ptr [rax+rax+00h]
0x14004dad5  xor     esi, esi
0x14004dad7  mov     r8, r12; struct _SmsContainerRangeMapEntry *
0x14004dada  mov     rdx, rbx; struct _SmsContainerRangeMapListHead *
0x14004dadd  mov     rcx, r14; this
0x14004dae0  call    ?InterlockedPushListEntry@CmsContainerRangeMap@@QEAAXPEAU_SmsContainerRangeMapListHead@@PEAU_SmsContainerRangeMapEntry@@@Z; CmsContainerRangeMap::InterlockedPushListEntry(_SmsContainerRangeMapListHead *,_SmsContainerRangeMapEntry *)
0x14004dae5  mov     eax, esi
0x14004dae7  mov     rbx, [rsp+48h+arg_8]
0x14004daec  mov     rbp, [rsp+48h+arg_10]
0x14004daf1  add     rsp, 20h
0x14004daf5  pop     r15
0x14004daf7  pop     r14
0x14004daf9  pop     r12
0x14004dafb  pop     rdi
0x14004dafc  pop     rsi
0x14004dafd  retn
0x14004daff  mov     rbx, rax
0x14004db02  test    rax, rax
0x14004db05  jz      loc_14004DC5F
0x14004db0b  mov     [rbx], rbp
0x14004db0e  add     rbx, 10h
0x14004db12  mov     [rsp+48h+arg_0], rbx
0x14004db17  test    rbx, rbx
0x14004db1a  jnz     short loc_14004DB89
0x14004db1c  mov     eax, 0C000009Ah
0x14004db21  jmp     short loc_14004DAE7
0x14004db23  xor     ecx, ecx; ProcNumber
0x14004db25  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14004db2c  nop     dword ptr [rax+rax+00h]
0x14004db31  xor     edx, edx
0x14004db33  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14004db39  lea     rbp, [rdx+rdx*2]
0x14004db3d  shl     rbp, 6
0x14004db41  add     rbp, cs:qword_1402694B8
0x14004db48  cmp     dword ptr [rbp+0], 30h ; '0'
0x14004db4c  jnb     loc_14004DC2F
0x14004db52  mov     rbp, rsi
0x14004db55  mov     edx, 40h ; '@'
0x14004db5a  mov     ecx, 42h ; 'B'
0x14004db5f  mov     r8d, 6950534Dh
0x14004db65  call    cs:__imp_ExAllocatePool2
0x14004db6c  nop     dword ptr [rax+rax+00h]
0x14004db71  mov     rbx, rax
0x14004db74  test    al, 0Fh
0x14004db76  jz      loc_1401FD3B4
0x14004db7c  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x14004db83  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x14004db89  mov     [rbx+18h], rsi
0x14004db8d  xor     edx, edx
0x14004db8f  mov     [rbx+20h], rsi
0x14004db93  mov     [rbx+28h], rsi
0x14004db97  mov     [rbx+8], rsi
0x14004db9b  mov     [rbx], rsi
0x14004db9e  mov     [rbx+10h], rdi
0x14004dba2  imul    eax, edi, 41C64E6Dh
0x14004dba8  imul    ecx, edi, 10DCDh
0x14004dbae  add     eax, 3039h
0x14004dbb3  shr     eax, 10h
0x14004dbb6  inc     ecx
0x14004dbb8  and     ecx, 0FFFF0000h
0x14004dbbe  or      eax, ecx
0x14004dbc0  div     dword ptr [r14+8]
0x14004dbc4  mov     rax, [r14]
0x14004dbc7  lea     rdx, [rdx+rdx*2]
0x14004dbcb  lea     r15, [rax+rdx*8]
0x14004dbcf  xor     edx, edx
0x14004dbd1  lea     rcx, [r15+10h]
0x14004dbd5  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14004dbdc  nop     dword ptr [rax+rax+00h]
0x14004dbe1  cmp     [r15+8], rsi
0x14004dbe5  ja      loc_14004DCAF
0x14004dbeb  mov     rax, [r15]
0x14004dbee  test    rax, rax
0x14004dbf1  jnz     short loc_14004DC1F
0x14004dbf3  mov     [rbx+8], rbx
0x14004dbf7  mov     [rbx], rbx
0x14004dbfa  mov     [r15], rbx
0x14004dbfd  inc     qword ptr [r15+8]
0x14004dc01  nop
0x14004dc02  lock inc dword ptr [r14+0Ch]
0x14004dc07  nop
0x14004dc08  xor     edx, edx
0x14004dc0a  lea     rcx, [r15+10h]
0x14004dc0e  call    cs:__imp_ExReleasePushLockEx
0x14004dc15  nop     dword ptr [rax+rax+00h]
0x14004dc1a  jmp     loc_14004DAD7
0x14004dc1f  mov     rcx, [rax+8]
0x14004dc23  cmp     [rcx], rax
0x14004dc26  jz      short loc_14004DC67
0x14004dc28  mov     ecx, 3
0x14004dc2d  int     29h; Win8: RtlFailFast(ecx)
0x14004dc2f  cmp     [rbp+8], sil
0x14004dc33  jnz     short loc_14004DC77
0x14004dc35  mov     rcx, [rbp+58h]
0x14004dc39  mov     rax, rcx
0x14004dc3c  shr     rax, 20h
0x14004dc40  cmp     ecx, eax
0x14004dc42  jle     short loc_14004DC5F
0x14004dc44  nop
0x14004dc45  mov     ecx, 0FFFFFFFFh
0x14004dc4a  lock xadd [rbp+58h], ecx
0x14004dc4f  nop
0x14004dc50  dec     ecx
0x14004dc52  mov     eax, [rbp+5Ch]
0x14004dc55  cmp     ecx, eax
0x14004dc57  jge     short loc_14004DC96
0x14004dc59  nop
0x14004dc5a  lock inc dword ptr [rbp+58h]
0x14004dc5e  nop
0x14004dc5f  mov     edx, [rbp+4]
0x14004dc62  jmp     loc_14004DB5A
0x14004dc67  mov     [rbx], rax
0x14004dc6a  mov     [rbx+8], rcx
0x14004dc6e  mov     [rcx], rbx
0x14004dc71  mov     [rax+8], rbx
0x14004dc75  jmp     short loc_14004DBFD
0x14004dc77  lea     rcx, [rbp+40h]; Lookaside
0x14004dc7b  cmp     [rbp+9], sil
0x14004dc7f  jz      loc_1401FD3A2
0x14004dc85  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004dc8c  nop     dword ptr [rax+rax+00h]
0x14004dc91  jmp     loc_14004DAFF
0x14004dc96  test    ecx, ecx
0x14004dc98  js      short loc_14004DC59
0x14004dc9a  lea     rcx, [rbp+40h]; ListHead
0x14004dc9e  call    cs:__imp_ExpInterlockedPopEntrySList
0x14004dca5  nop     dword ptr [rax+rax+00h]
0x14004dcaa  jmp     loc_14004DAFF
0x14004dcaf  mov     rax, [r15]
0x14004dcb2  mov     rcx, rax
0x14004dcb5  jmp     loc_1401FD3C2
0x1401fd3a2  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1401fd3a9  nop     dword ptr [rax+rax+00h]
0x1401fd3ae  nop
0x1401fd3af  jmp     loc_14004DAFF
0x1401fd3b4  test    rax, rax
0x1401fd3b7  jz      loc_14004DB12
0x1401fd3bd  jmp     loc_14004DB0B
0x1401fd3c2  cmp     [rax+10h], rdi
0x1401fd3c6  jz      short loc_1401FD3D5
0x1401fd3c8  mov     rax, [rax]
0x1401fd3cb  cmp     rax, rcx
0x1401fd3ce  jnz     short loc_1401FD3C2
0x1401fd3d0  jmp     loc_14004DBEB
0x1401fd3d5  xor     edx, edx
0x1401fd3d7  lea     rcx, [r15+10h]
0x1401fd3db  call    cs:__imp_ExReleasePushLockEx
0x1401fd3e2  nop     dword ptr [rax+rax+00h]
0x1401fd3e7  mov     rcx, rbx; void *
0x1401fd3ea  call    ?Free@CmsLookasides@@SAXPEAX@Z; CmsLookasides::Free(void *)
0x1401fd3ef  xor     r9d, r9d
0x1401fd3f2  lea     r8, [rsp+48h+arg_0]
0x1401fd3f7  mov     rdx, rdi
0x1401fd3fa  mov     rcx, r14
0x1401fd3fd  call    ??$PinInIndex@$00@CmsHashTableLite@@QEAAJ_KPEAPEAUSmsHashEntryLite@@P6AEPEAU1@@Z@Z; CmsHashTableLite::PinInIndex<1>(unsigned __int64,SmsHashEntryLite * *,uchar (*)(SmsHashEntryLite *))
0x1401fd402  mov     rbx, [rsp+48h+arg_0]
0x1401fd407  mov     esi, eax
0x1401fd409  jmp     loc_14004DAD7
```
