# CmsContainerRangeMap::AddToContainerList(unsigned __int64,_SmsContainerRangeMapEntry *,uchar,long *)

- ea: `0x14001dfc0`
- end: `0x14001e27a`
- name: `?AddToContainerList@CmsContainerRangeMap@@AEAAJ_KPEAU_SmsContainerRangeMapEntry@@EPEAJ@Z`
- size: `698`
- prototype: `__int64 __usercall@<rax>(CmsContainerRangeMap *__hidden this@<rcx>, unsigned __int64@<rdx>, struct _SmsContainerRangeMapEntry *@<r8>, unsigned __int8@<r9b>, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14006d4c0`

## callees

- `0x14001dfc0`
- `0x14001e280`
- `0x14001e2c4`
- `0x140062510`
- `0x14009ac80`
- `0x1400c8574`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001e245`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001e245`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14001e01d`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14001e01d`
- `ntoskrnl!ExAllocatePool2` at `0x14001e125`
- `ntoskrnl!ExAllocatePool2` at `0x14001e125`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001e0e5`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001e0e5`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401eef74`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401eef74`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14001e25e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14001e25e`
- `ntoskrnl!ExReleasePushLockEx` at `0x14001e049`
- `ntoskrnl!ExReleasePushLockEx` at `0x14001e089`
- `ntoskrnl!ExReleasePushLockEx` at `0x14001e1ce`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401eefad`
- `ntoskrnl!ExReleasePushLockEx` at `0x14001e049`
- `ntoskrnl!ExReleasePushLockEx` at `0x14001e089`
- `ntoskrnl!ExReleasePushLockEx` at `0x14001e1ce`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401eefad`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001e195`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001e195`

## string_xrefs

- `0x14001e13c`: `Lookaside list allocation must be double quad aligned.`

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
  __int64 v16; // rdx
  __int64 Pool2; // rax
  PSLIST_ENTRY *v18; // r15
  struct _SLIST_ENTRY *v19; // rax
  PSLIST_ENTRY *v20; // rcx
  int v21; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v22; // rcx
  struct _SLIST_ENTRY *v23; // rax
  _QWORD *v24; // rax
  unsigned int v25; // eax
  struct _SLIST_ENTRY *v26; // [rsp+50h] [rbp+8h] BYREF

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
  v15 = qword_1402624B8 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( *(_DWORD *)v15 < 0x30u )
  {
    v15 = 0;
    v16 = 64;
    goto LABEL_15;
  }
  if ( *(_BYTE *)(v15 + 8) )
  {
    v22 = (struct _NPAGED_LOOKASIDE_LIST *)(v15 + 64);
    if ( *(_BYTE *)(v15 + 9) )
      v23 = (struct _SLIST_ENTRY *)ExAllocateFromNPagedLookasideList(v22);
    else
      v23 = (struct _SLIST_ENTRY *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v22);
LABEL_9:
    v12 = v23;
    if ( v23 )
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
    v21 = _InterlockedDecrement((volatile signed __int32 *)(v15 + 88));
    if ( v21 >= *(_DWORD *)(v15 + 92) && v21 >= 0 )
    {
      v23 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v15 + 64));
      goto LABEL_9;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v15 + 88));
  }
LABEL_27:
  v16 = *(unsigned int *)(v15 + 4);
LABEL_15:
  Pool2 = ExAllocatePool2(66, v16, 1766871885);
  v12 = (PSLIST_ENTRY)Pool2;
  if ( (Pool2 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( Pool2 )
    goto LABEL_10;
LABEL_11:
  v26 = v12;
  if ( v12 )
  {
    *((_QWORD *)&v12[1].Next + 1) = 0;
    v12[2].Next = 0;
    *((_QWORD *)&v12[2].Next + 1) = 0;
    *((_QWORD *)&v12->Next + 1) = 0;
    v12->Next = 0;
    v12[1].Next = a2;
    v18 = (PSLIST_ENTRY *)(*(_QWORD *)this
                         + 24
                         * (((69069 * (_DWORD)a2 + 1) & 0xFFFF0000
                           | (unsigned __int64)((unsigned int)(1103515245 * (_DWORD)a2 + 12345) >> 16))
                          % *((unsigned int *)this + 2)));
    ExAcquirePushLockExclusiveEx(v18 + 2, 0);
    if ( v18[1] )
    {
      v24 = *v18;
      while ( (struct _SLIST_ENTRY *)v24[2] != a2 )
      {
        v24 = (_QWORD *)*v24;
        if ( v24 == (_QWORD *)*v18 )
          goto LABEL_18;
      }
      ExReleasePushLockEx(v18 + 2, 0);
      CmsLookasides::Free(v12);
      v25 = CmsHashTableLite::PinInIndex<1>(this, a2, &v26, 0);
      v12 = v26;
      v13 = v25;
    }
    else
    {
LABEL_18:
      v19 = *v18;
      if ( *v18 )
      {
        v20 = (PSLIST_ENTRY *)*((_QWORD *)&v19->Next + 1);
        if ( *v20 != v19 )
          __fastfail(3u);
        v12->Next = v19;
        *((_QWORD *)&v12->Next + 1) = v20;
        *v20 = v12;
        *((_QWORD *)&v19->Next + 1) = v12;
      }
      else
      {
        *((_QWORD *)&v12->Next + 1) = v12;
        v12->Next = v12;
        *v18 = v12;
      }
      v18[1] = (PSLIST_ENTRY)((char *)v18[1] + 1);
      _InterlockedIncrement((volatile signed __int32 *)this + 3);
      ExReleasePushLockEx(v18 + 2, 0);
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
0x14001dfc0  mov     [rsp+arg_8], rbx
0x14001dfc5  mov     [rsp+arg_10], rbp
0x14001dfca  push    rsi
0x14001dfcb  push    rdi
0x14001dfcc  push    r12
0x14001dfce  push    r14
0x14001dfd0  push    r15
0x14001dfd2  sub     rsp, 20h
0x14001dfd6  imul    eax, edx, 10DCDh
0x14001dfdc  mov     rdi, rdx
0x14001dfdf  imul    edx, 41C64E6Dh
0x14001dfe5  mov     r14, rcx
0x14001dfe8  movzx   ebp, r9b
0x14001dfec  mov     r12, r8
0x14001dfef  inc     eax
0x14001dff1  add     edx, 3039h
0x14001dff7  and     eax, 0FFFF0000h
0x14001dffc  shr     edx, 10h
0x14001dfff  or      eax, edx
0x14001e001  xor     edx, edx
0x14001e003  div     dword ptr [rcx+8]
0x14001e006  mov     rax, [rcx]
0x14001e009  lea     rdx, [rdx+rdx*2]
0x14001e00d  lea     rbx, [rax+rdx*8]
0x14001e011  mov     edx, 4
0x14001e016  lea     rsi, [rbx+10h]
0x14001e01a  mov     rcx, rsi
0x14001e01d  call    cs:__imp_ExAcquirePushLockSharedEx
0x14001e024  nop     dword ptr [rax+rax+00h]
0x14001e029  cmp     qword ptr [rbx+8], 0
0x14001e02e  jbe     short loc_14001E044
0x14001e030  mov     rax, [rbx]
0x14001e033  mov     rbx, rax
0x14001e036  cmp     [rbx+10h], rdi
0x14001e03a  jz      short loc_14001E084
0x14001e03c  mov     rbx, [rbx]
0x14001e03f  cmp     rbx, rax
0x14001e042  jnz     short loc_14001E036
0x14001e044  xor     edx, edx
0x14001e046  mov     rcx, rsi
0x14001e049  call    cs:__imp_ExReleasePushLockEx
0x14001e050  nop     dword ptr [rax+rax+00h]
0x14001e055  xor     esi, esi
0x14001e057  test    bpl, bpl
0x14001e05a  jz      loc_14001E0E3
0x14001e060  mov     rax, [rsp+48h+arg_20]
0x14001e065  nop
0x14001e066  mov     edx, 15h
0x14001e06b  mov     ecx, 30h ; '0'
0x14001e070  mov     r8d, 1
0x14001e076  lock dec dword ptr [rax]
0x14001e079  nop
0x14001e07a  call    ?Allocate@CmsLookasides@@SAPEAX_KW4EmsLookaside@@K@Z; CmsLookasides::Allocate(unsigned __int64,EmsLookaside,ulong)
0x14001e07f  mov     rbx, rax
0x14001e082  jmp     short loc_14001E0D2
0x14001e084  xor     edx, edx
0x14001e086  mov     rcx, rsi
0x14001e089  call    cs:__imp_ExReleasePushLockEx
0x14001e090  nop     dword ptr [rax+rax+00h]
0x14001e095  xor     esi, esi
0x14001e097  mov     r8, r12; struct _SmsContainerRangeMapEntry *
0x14001e09a  mov     rdx, rbx; struct _SmsContainerRangeMapListHead *
0x14001e09d  mov     rcx, r14; this
0x14001e0a0  call    ?InterlockedPushListEntry@CmsContainerRangeMap@@QEAAXPEAU_SmsContainerRangeMapListHead@@PEAU_SmsContainerRangeMapEntry@@@Z; CmsContainerRangeMap::InterlockedPushListEntry(_SmsContainerRangeMapListHead *,_SmsContainerRangeMapEntry *)
0x14001e0a5  mov     eax, esi
0x14001e0a7  mov     rbx, [rsp+48h+arg_8]
0x14001e0ac  mov     rbp, [rsp+48h+arg_10]
0x14001e0b1  add     rsp, 20h
0x14001e0b5  pop     r15
0x14001e0b7  pop     r14
0x14001e0b9  pop     r12
0x14001e0bb  pop     rdi
0x14001e0bc  pop     rsi
0x14001e0bd  retn
0x14001e0bf  mov     rbx, rax
0x14001e0c2  test    rax, rax
0x14001e0c5  jz      loc_14001E21F
0x14001e0cb  mov     [rbx], rbp
0x14001e0ce  add     rbx, 10h
0x14001e0d2  mov     [rsp+48h+arg_0], rbx
0x14001e0d7  test    rbx, rbx
0x14001e0da  jnz     short loc_14001E149
0x14001e0dc  mov     eax, 0C000009Ah
0x14001e0e1  jmp     short loc_14001E0A7
0x14001e0e3  xor     ecx, ecx; ProcNumber
0x14001e0e5  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14001e0ec  nop     dword ptr [rax+rax+00h]
0x14001e0f1  xor     edx, edx
0x14001e0f3  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14001e0f9  lea     rbp, [rdx+rdx*2]
0x14001e0fd  shl     rbp, 6
0x14001e101  add     rbp, cs:qword_1402624B8
0x14001e108  cmp     dword ptr [rbp+0], 30h ; '0'
0x14001e10c  jnb     loc_14001E1EF
0x14001e112  mov     rbp, rsi
0x14001e115  mov     edx, 40h ; '@'
0x14001e11a  mov     ecx, 42h ; 'B'
0x14001e11f  mov     r8d, 6950534Dh
0x14001e125  call    cs:__imp_ExAllocatePool2
0x14001e12c  nop     dword ptr [rax+rax+00h]
0x14001e131  mov     rbx, rax
0x14001e134  test    al, 0Fh
0x14001e136  jz      loc_1401EEF86
0x14001e13c  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x14001e143  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x14001e149  mov     [rbx+18h], rsi
0x14001e14d  xor     edx, edx
0x14001e14f  mov     [rbx+20h], rsi
0x14001e153  mov     [rbx+28h], rsi
0x14001e157  mov     [rbx+8], rsi
0x14001e15b  mov     [rbx], rsi
0x14001e15e  mov     [rbx+10h], rdi
0x14001e162  imul    eax, edi, 41C64E6Dh
0x14001e168  imul    ecx, edi, 10DCDh
0x14001e16e  add     eax, 3039h
0x14001e173  shr     eax, 10h
0x14001e176  inc     ecx
0x14001e178  and     ecx, 0FFFF0000h
0x14001e17e  or      eax, ecx
0x14001e180  div     dword ptr [r14+8]
0x14001e184  mov     rax, [r14]
0x14001e187  lea     rdx, [rdx+rdx*2]
0x14001e18b  lea     r15, [rax+rdx*8]
0x14001e18f  xor     edx, edx
0x14001e191  lea     rcx, [r15+10h]
0x14001e195  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001e19c  nop     dword ptr [rax+rax+00h]
0x14001e1a1  cmp     [r15+8], rsi
0x14001e1a5  ja      loc_14001E26F
0x14001e1ab  mov     rax, [r15]
0x14001e1ae  test    rax, rax
0x14001e1b1  jnz     short loc_14001E1DF
0x14001e1b3  mov     [rbx+8], rbx
0x14001e1b7  mov     [rbx], rbx
0x14001e1ba  mov     [r15], rbx
0x14001e1bd  inc     qword ptr [r15+8]
0x14001e1c1  nop
0x14001e1c2  lock inc dword ptr [r14+0Ch]
0x14001e1c7  nop
0x14001e1c8  xor     edx, edx
0x14001e1ca  lea     rcx, [r15+10h]
0x14001e1ce  call    cs:__imp_ExReleasePushLockEx
0x14001e1d5  nop     dword ptr [rax+rax+00h]
0x14001e1da  jmp     loc_14001E097
0x14001e1df  mov     rcx, [rax+8]
0x14001e1e3  cmp     [rcx], rax
0x14001e1e6  jz      short loc_14001E227
0x14001e1e8  mov     ecx, 3
0x14001e1ed  int     29h; Win8: RtlFailFast(ecx)
0x14001e1ef  cmp     [rbp+8], sil
0x14001e1f3  jnz     short loc_14001E237
0x14001e1f5  mov     rcx, [rbp+58h]
0x14001e1f9  mov     rax, rcx
0x14001e1fc  shr     rax, 20h
0x14001e200  cmp     ecx, eax
0x14001e202  jle     short loc_14001E21F
0x14001e204  nop
0x14001e205  mov     ecx, 0FFFFFFFFh
0x14001e20a  lock xadd [rbp+58h], ecx
0x14001e20f  nop
0x14001e210  dec     ecx
0x14001e212  mov     eax, [rbp+5Ch]
0x14001e215  cmp     ecx, eax
0x14001e217  jge     short loc_14001E256
0x14001e219  nop
0x14001e21a  lock inc dword ptr [rbp+58h]
0x14001e21e  nop
0x14001e21f  mov     edx, [rbp+4]
0x14001e222  jmp     loc_14001E11A
0x14001e227  mov     [rbx], rax
0x14001e22a  mov     [rbx+8], rcx
0x14001e22e  mov     [rcx], rbx
0x14001e231  mov     [rax+8], rbx
0x14001e235  jmp     short loc_14001E1BD
0x14001e237  lea     rcx, [rbp+40h]; Lookaside
0x14001e23b  cmp     [rbp+9], sil
0x14001e23f  jz      loc_1401EEF74
0x14001e245  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001e24c  nop     dword ptr [rax+rax+00h]
0x14001e251  jmp     loc_14001E0BF
0x14001e256  test    ecx, ecx
0x14001e258  js      short loc_14001E219
0x14001e25a  lea     rcx, [rbp+40h]; ListHead
0x14001e25e  call    cs:__imp_ExpInterlockedPopEntrySList
0x14001e265  nop     dword ptr [rax+rax+00h]
0x14001e26a  jmp     loc_14001E0BF
0x14001e26f  mov     rax, [r15]
0x14001e272  mov     rcx, rax
0x14001e275  jmp     loc_1401EEF94
0x1401eef74  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1401eef7b  nop     dword ptr [rax+rax+00h]
0x1401eef80  nop
0x1401eef81  jmp     loc_14001E0BF
0x1401eef86  test    rax, rax
0x1401eef89  jz      loc_14001E0D2
0x1401eef8f  jmp     loc_14001E0CB
0x1401eef94  cmp     [rax+10h], rdi
0x1401eef98  jz      short loc_1401EEFA7
0x1401eef9a  mov     rax, [rax]
0x1401eef9d  cmp     rax, rcx
0x1401eefa0  jnz     short loc_1401EEF94
0x1401eefa2  jmp     loc_14001E1AB
0x1401eefa7  xor     edx, edx
0x1401eefa9  lea     rcx, [r15+10h]
0x1401eefad  call    cs:__imp_ExReleasePushLockEx
0x1401eefb4  nop     dword ptr [rax+rax+00h]
0x1401eefb9  mov     rcx, rbx; void *
0x1401eefbc  call    ?Free@CmsLookasides@@SAXPEAX@Z; CmsLookasides::Free(void *)
0x1401eefc1  xor     r9d, r9d
0x1401eefc4  lea     r8, [rsp+48h+arg_0]
0x1401eefc9  mov     rdx, rdi
0x1401eefcc  mov     rcx, r14
0x1401eefcf  call    ??$PinInIndex@$00@CmsHashTableLite@@QEAAJ_KPEAPEAUSmsHashEntryLite@@P6AEPEAU1@@Z@Z; CmsHashTableLite::PinInIndex<1>(unsigned __int64,SmsHashEntryLite * *,uchar (*)(SmsHashEntryLite *))
0x1401eefd4  mov     rbx, [rsp+48h+arg_0]
0x1401eefd9  mov     esi, eax
0x1401eefdb  jmp     loc_14001E097
```
