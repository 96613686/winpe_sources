# SmbCeConstructNetRootEntry

- ea: `0x14002d720`
- end: `0x14002daa1`
- name: `SmbCeConstructNetRootEntry`
- size: `897`
- prototype: `__int64 __fastcall(struct _LIST_ENTRY *BugCheckParameter2, __int64, struct _LIST_ENTRY **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14002eeb0`

## callees

- `0x140013540`
- `0x140026d60`
- `0x14002d720`
- `0x140059ea0`
- `0x140059f00`

## import_xrefs

- `ntoskrnl!ExInterlockedInsertTailList` at `0x14002d79e`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14002d79e`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14002d89d`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14002d89d`
- `ntoskrnl!RtlHashUnicodeString` at `0x14002d9a6`
- `ntoskrnl!RtlHashUnicodeString` at `0x14002d9a6`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002d836`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002d836`
- `ntoskrnl!ExAllocatePool2` at `0x14002d774`
- `ntoskrnl!ExAllocatePool2` at `0x14002d854`
- `ntoskrnl!ExAllocatePool2` at `0x14002d8c4`
- `ntoskrnl!ExAllocatePool2` at `0x14002d774`
- `ntoskrnl!ExAllocatePool2` at `0x14002d854`
- `ntoskrnl!ExAllocatePool2` at `0x14002d8c4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002da06`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002da06`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14002d9c0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14002d9c0`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002d978`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002d978`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002d91d`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002d91d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002d92d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002d92d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002da30`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002da5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002da30`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002da5c`

## pseudocode

```c
__int64 __fastcall SmbCeConstructNetRootEntry(
        struct _LIST_ENTRY *BugCheckParameter2,
        __int64 a2,
        struct _LIST_ENTRY **a3)
{
  struct _LIST_ENTRY *Blink; // rax
  struct _LIST_ENTRY *v5; // rdi
  unsigned int Flink; // r9d
  struct _LIST_ENTRY *Pool2; // rax
  struct _LIST_ENTRY *v9; // rbx
  struct _LIST_ENTRY *v10; // r14
  char *v11; // rcx
  struct _LIST_ENTRY *v12; // rax
  unsigned int v13; // edi
  unsigned int v14; // ecx
  ULONG ActiveProcessorCount; // eax
  __int64 v16; // rax
  struct _LIST_ENTRY *v17; // r15
  KIRQL v18; // r13
  struct _LIST_ENTRY *v19; // r8
  struct _LIST_ENTRY **v20; // rax
  PVOID *v21; // rdx
  PVOID **v22; // r8
  struct _LIST_ENTRY *v23; // rcx
  struct _LIST_ENTRY *v24; // rcx
  ULONG HashValue; // [rsp+60h] [rbp+8h] BYREF
  struct _LIST_ENTRY **v27; // [rsp+70h] [rbp+18h]

  v27 = a3;
  Blink = BugCheckParameter2[3].Blink;
  v5 = BugCheckParameter2[1].Blink;
  HashValue = 0;
  Flink = (unsigned int)Blink[1].Flink;
  if ( DWORD1(ObjectSizeInBytes) > Flink )
    Flink = DWORD1(ObjectSizeInBytes);
  Pool2 = (struct _LIST_ENTRY *)ExAllocatePool2(64, Flink + 16LL, 1834181955);
  if ( !Pool2 )
  {
    v13 = -1073741670;
    *(_QWORD *)(a2 + 40) = 0;
    return v13;
  }
  v9 = Pool2 + 1;
  ExInterlockedInsertTailList(&stru_140070E30, Pool2, &SmbMmSpinLock);
  HIDWORD(v9->Flink) = 0;
  LODWORD(v9->Flink) = 57857;
  HIDWORD(v9->Blink) = 1;
  v10 = v9 + 2;
  LODWORD(v9->Blink) = 1;
  v9[1].Blink = v5;
  v9[2].Blink = v9 + 2;
  v9[2].Flink = v9 + 2;
  v9[3].Blink = v9 + 3;
  v9[3].Flink = v9 + 3;
  if ( WORD1(v9->Flink) )
  {
    v11 = (char *)v9 + WORD1(v9->Flink);
    if ( v11 )
    {
      *((_DWORD *)v11 + 52) = -1073741300;
      *((_QWORD *)v11 + 2) = v11 + 8;
      *((_QWORD *)v11 + 1) = v11 + 8;
      *((_QWORD *)v11 + 32) = v11 + 248;
      *((_QWORD *)v11 + 31) = v11 + 248;
      *((_QWORD *)v11 + 28) = v11 + 216;
      *((_QWORD *)v11 + 27) = v11 + 216;
      *((_DWORD *)v11 + 53) = 0;
      *((_QWORD *)v11 + 30) = v11 + 232;
      *((_QWORD *)v11 + 29) = v11 + 232;
      KeInitializeSpinLock((PKSPIN_LOCK)v11 + 16);
    }
  }
  v12 = (struct _LIST_ENTRY *)ExAllocatePool2(66, **(unsigned __int16 **)(a2 + 88), 1834185806);
  v9[6].Blink = v12;
  if ( !v12 )
  {
    v13 = -1073741670;
    goto LABEL_16;
  }
  v14 = **(unsigned __int16 **)(a2 + 88);
  LOWORD(v9[6].Flink) = v14;
  WORD1(v9[6].Flink) = v14;
  memmove(v12, *(const void **)(*(_QWORD *)(a2 + 88) + 8LL), v14);
  ActiveProcessorCount = KeQueryActiveProcessorCountEx(0xFFFFu);
  LODWORD(v9[93].Flink) = ActiveProcessorCount;
  v16 = ExAllocatePool2(72, 192LL * ActiveProcessorCount, 1834185806);
  v9[92].Blink = (struct _LIST_ENTRY *)v16;
  if ( !v16 )
  {
    LODWORD(v9[93].Flink) = 0;
    v13 = -1073741670;
LABEL_16:
    *(_QWORD *)(a2 + 40) = 0;
    if ( v9 )
    {
      v23 = v9[6].Blink;
      if ( v23 )
      {
        ExFreePoolWithTag(v23, 0x6D53744Eu);
        v9[6].Blink = 0;
      }
      v9[6].Blink = 0;
      LODWORD(v9[6].Flink) = 0;
      v24 = v9[92].Blink;
      if ( v24 )
      {
        ExFreePoolWithTag(v24, 0x6D53744Eu);
        v9[92].Blink = 0;
      }
      SmbMmFreeObjectPool(v9);
    }
    return v13;
  }
  v13 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *))BugCheckParameter2[3].Blink[47].Blink)(v9);
  if ( (v13 & 0x80000000) == 0 )
  {
    SmbCeReferenceServerEntry((ULONG_PTR)BugCheckParameter2);
    v17 = BugCheckParameter2[1].Blink;
    v18 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)&v17[120]);
    LODWORD(v17[147].Flink) = (unsigned int)PsGetCurrentThreadId();
    v19 = BugCheckParameter2[34].Blink;
    if ( v19->Flink != &BugCheckParameter2[34] )
      goto LABEL_22;
    v10->Flink = BugCheckParameter2 + 34;
    v9[2].Blink = v19;
    v19->Flink = v10;
    BugCheckParameter2[34].Blink = v10;
    LODWORD(v17[147].Flink) = -1;
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)&v17[120], v18);
    v20 = v27;
    v9[5].Blink = BugCheckParameter2;
    v9[5].Flink = (struct _LIST_ENTRY *)a2;
    *(_QWORD *)(a2 + 40) = v9;
    *v20 = v9;
    RtlHashUnicodeString((PCUNICODE_STRING)&v9[6], 1u, 0, &HashValue);
    HashValue &= 0x1Fu;
    ExAcquirePushLockExclusiveEx(&MRxSmbPerfCounterNetRootsPushLock, 0);
    v21 = &WPP_MAIN_CB.DeviceExtension + 2 * HashValue;
    v22 = (PVOID **)v21[1];
    if ( *v22 != v21 )
LABEL_22:
      __fastfail(3u);
    v9[4].Flink = (struct _LIST_ENTRY *)v21;
    v9[4].Blink = (struct _LIST_ENTRY *)v22;
    *v22 = (PVOID *)&v9[4].Flink;
    v21[1] = &v9[4];
    ExReleasePushLockExclusiveEx(&MRxSmbPerfCounterNetRootsPushLock, 0);
  }
  if ( v13 )
    goto LABEL_16;
  return v13;
}

```

## disassembly

```asm
0x14002d720  mov     [rsp+arg_8], rbx
0x14002d725  mov     [rsp+arg_10], r8
0x14002d72a  push    rbp
0x14002d72b  push    rsi
0x14002d72c  push    rdi
0x14002d72d  push    r12
0x14002d72f  push    r13
0x14002d731  push    r14
0x14002d733  push    r15
0x14002d735  sub     rsp, 20h
0x14002d739  mov     rax, [rcx+38h]
0x14002d73d  mov     rsi, rdx
0x14002d740  mov     rdi, [rcx+18h]
0x14002d744  xor     r15d, r15d
0x14002d747  mov     [rsp+58h+HashValue], r15d
0x14002d74c  mov     rbp, rcx
0x14002d74f  mov     ecx, 40h ; '@'
0x14002d754  mov     r8d, 6D536543h
0x14002d75a  mov     r9d, [rax+10h]
0x14002d75e  cmp     dword ptr cs:ObjectSizeInBytes+4, r9d
0x14002d765  cmova   r9d, dword ptr cs:ObjectSizeInBytes+4
0x14002d76d  mov     edx, r9d
0x14002d770  add     rdx, 10h
0x14002d774  call    cs:__imp_ExAllocatePool2
0x14002d77b  nop     dword ptr [rax+rax+00h]
0x14002d780  test    rax, rax
0x14002d783  jz      loc_14002DA80
0x14002d789  lea     r8, SmbMmSpinLock; Lock
0x14002d790  mov     rdx, rax; ListEntry
0x14002d793  lea     rcx, stru_140070E30; ListHead
0x14002d79a  lea     rbx, [rax+10h]
0x14002d79e  call    cs:__imp_ExInterlockedInsertTailList
0x14002d7a5  nop     dword ptr [rax+rax+00h]
0x14002d7aa  mov     [rbx+4], r15d
0x14002d7ae  mov     dword ptr [rbx], 0E201h
0x14002d7b4  lea     rax, [rbx+30h]
0x14002d7b8  mov     dword ptr [rbx+0Ch], 1
0x14002d7bf  lea     r14, [rbx+20h]
0x14002d7c3  mov     dword ptr [rbx+8], 1
0x14002d7ca  mov     [rbx+18h], rdi
0x14002d7ce  mov     [r14+8], r14
0x14002d7d2  mov     [r14], r14
0x14002d7d5  mov     [rax+8], rax
0x14002d7d9  mov     [rax], rax
0x14002d7dc  movzx   eax, word ptr [rbx+2]
0x14002d7e0  test    ax, ax
0x14002d7e3  jz      short loc_14002D842
0x14002d7e5  mov     ecx, eax
0x14002d7e7  add     rcx, rbx
0x14002d7ea  jz      short loc_14002D842
0x14002d7ec  lea     rax, [rcx+8]
0x14002d7f0  mov     dword ptr [rcx+0D0h], 0C000020Ch
0x14002d7fa  mov     [rax+8], rax
0x14002d7fe  mov     [rax], rax
0x14002d801  lea     rax, [rcx+0F8h]
0x14002d808  mov     [rax+8], rax
0x14002d80c  mov     [rax], rax
0x14002d80f  lea     rax, [rcx+0D8h]
0x14002d816  mov     [rax+8], rax
0x14002d81a  mov     [rax], rax
0x14002d81d  lea     rax, [rcx+0E8h]
0x14002d824  mov     [rcx+0D4h], r15d
0x14002d82b  sub     rcx, 0FFFFFFFFFFFFFF80h; SpinLock
0x14002d82f  mov     [rax+8], rax
0x14002d833  mov     [rax], rax
0x14002d836  call    cs:__imp_KeInitializeSpinLock
0x14002d83d  nop     dword ptr [rax+rax+00h]
0x14002d842  mov     rax, [rsi+58h]
0x14002d846  mov     ecx, 42h ; 'B'
0x14002d84b  mov     r8d, 6D53744Eh
0x14002d851  movzx   edx, word ptr [rax]
0x14002d854  call    cs:__imp_ExAllocatePool2
0x14002d85b  nop     dword ptr [rax+rax+00h]
0x14002d860  mov     [rbx+68h], rax
0x14002d864  mov     r9, rax
0x14002d867  test    rax, rax
0x14002d86a  jnz     short loc_14002D876
0x14002d86c  mov     edi, 0C000009Ah
0x14002d871  jmp     loc_14002DA19
0x14002d876  mov     rax, [rsi+58h]
0x14002d87a  movzx   ecx, word ptr [rax]
0x14002d87d  mov     [rbx+60h], cx
0x14002d881  mov     r8d, ecx; Size
0x14002d884  mov     [rbx+62h], cx
0x14002d888  mov     rcx, r9; void *
0x14002d88b  mov     rdx, [rsi+58h]
0x14002d88f  mov     rdx, [rdx+8]; Src
0x14002d893  call    memmove
0x14002d898  mov     ecx, 0FFFFh; GroupNumber
0x14002d89d  call    cs:__imp_KeQueryActiveProcessorCountEx
0x14002d8a4  nop     dword ptr [rax+rax+00h]
0x14002d8a9  mov     eax, eax
0x14002d8ab  mov     ecx, 48h ; 'H'
0x14002d8b0  mov     r8d, 6D53744Eh
0x14002d8b6  mov     [rbx+5D0h], eax
0x14002d8bc  lea     rdx, [rax+rax*2]
0x14002d8c0  shl     rdx, 6
0x14002d8c4  call    cs:__imp_ExAllocatePool2
0x14002d8cb  nop     dword ptr [rax+rax+00h]
0x14002d8d0  mov     [rbx+5C8h], rax
0x14002d8d7  test    rax, rax
0x14002d8da  jnz     short loc_14002D8ED
0x14002d8dc  mov     [rbx+5D0h], r15d
0x14002d8e3  mov     edi, 0C000009Ah
0x14002d8e8  jmp     loc_14002DA19
0x14002d8ed  mov     rax, [rbp+38h]
0x14002d8f1  mov     rcx, rbx
0x14002d8f4  mov     rax, [rax+2F8h]
0x14002d8fb  call    _guard_dispatch_icall
0x14002d900  mov     edi, eax
0x14002d902  test    eax, eax
0x14002d904  js      loc_14002DA15
0x14002d90a  mov     rcx, rbp; BugCheckParameter2
0x14002d90d  call    SmbCeReferenceServerEntry
0x14002d912  mov     r15, [rbp+18h]
0x14002d916  lea     rcx, [r15+780h]; SpinLock
0x14002d91d  call    cs:__imp_ExAcquireSpinLockExclusive
0x14002d924  nop     dword ptr [rax+rax+00h]
0x14002d929  movzx   r13d, al
0x14002d92d  call    cs:__imp_PsGetCurrentThreadId
0x14002d934  nop     dword ptr [rax+rax+00h]
0x14002d939  lea     rdx, [rbp+220h]
0x14002d940  mov     [r15+930h], eax
0x14002d947  mov     r8, [rdx+8]
0x14002d94b  cmp     [r8], rdx
0x14002d94e  jnz     loc_14002DA79
0x14002d954  mov     [r14], rdx
0x14002d957  lea     rcx, [r15+780h]; SpinLock
0x14002d95e  mov     [r14+8], r8
0x14002d962  mov     [r8], r14
0x14002d965  mov     [rdx+8], r14
0x14002d969  movzx   edx, r13b; OldIrql
0x14002d96d  mov     dword ptr [r15+930h], 0FFFFFFFFh
0x14002d978  call    cs:__imp_ExReleaseSpinLockExclusive
0x14002d97f  nop     dword ptr [rax+rax+00h]
0x14002d984  mov     rax, [rsp+58h+arg_10]
0x14002d989  lea     r9, [rsp+58h+HashValue]; HashValue
0x14002d98e  mov     [rbx+58h], rbp
0x14002d992  lea     rcx, [rbx+60h]; String
0x14002d996  mov     [rbx+50h], rsi
0x14002d99a  xor     r8d, r8d; HashAlgorithm
0x14002d99d  mov     dl, 1; CaseInSensitive
0x14002d99f  mov     [rsi+28h], rbx
0x14002d9a3  mov     [rax], rbx
0x14002d9a6  call    cs:__imp_RtlHashUnicodeString
0x14002d9ad  nop     dword ptr [rax+rax+00h]
0x14002d9b2  and     [rsp+58h+HashValue], 1Fh
0x14002d9b7  lea     rcx, MRxSmbPerfCounterNetRootsPushLock
0x14002d9be  xor     edx, edx
0x14002d9c0  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14002d9c7  nop     dword ptr [rax+rax+00h]
0x14002d9cc  mov     eax, [rsp+58h+HashValue]
0x14002d9d0  lea     rdx, WPP_MAIN_CB.DeviceExtension
0x14002d9d7  shl     rax, 4
0x14002d9db  add     rdx, rax
0x14002d9de  mov     r8, [rdx+8]
0x14002d9e2  cmp     [r8], rdx
0x14002d9e5  jnz     loc_14002DA79
0x14002d9eb  lea     rax, [rbx+40h]
0x14002d9ef  mov     [rax], rdx
0x14002d9f2  lea     rcx, MRxSmbPerfCounterNetRootsPushLock
0x14002d9f9  mov     [rax+8], r8
0x14002d9fd  mov     [r8], rax
0x14002da00  mov     [rdx+8], rax
0x14002da04  xor     edx, edx
0x14002da06  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14002da0d  nop     dword ptr [rax+rax+00h]
0x14002da12  xor     r15d, r15d
0x14002da15  test    edi, edi
0x14002da17  jz      short loc_14002DA89
0x14002da19  mov     [rsi+28h], r15
0x14002da1d  test    rbx, rbx
0x14002da20  jz      short loc_14002DA89
0x14002da22  mov     rcx, [rbx+68h]; P
0x14002da26  test    rcx, rcx
0x14002da29  jz      short loc_14002DA40
0x14002da2b  mov     edx, 6D53744Eh; Tag
0x14002da30  call    cs:__imp_ExFreePoolWithTag
0x14002da37  nop     dword ptr [rax+rax+00h]
0x14002da3c  mov     [rbx+68h], r15
0x14002da40  mov     [rbx+68h], r15
0x14002da44  mov     dword ptr [rbx+60h], 0
0x14002da4b  mov     rcx, [rbx+5C8h]; P
0x14002da52  test    rcx, rcx
0x14002da55  jz      short loc_14002DA6F
0x14002da57  mov     edx, 6D53744Eh; Tag
0x14002da5c  call    cs:__imp_ExFreePoolWithTag
0x14002da63  nop     dword ptr [rax+rax+00h]
0x14002da68  mov     [rbx+5C8h], r15
0x14002da6f  mov     rcx, rbx
0x14002da72  call    SmbMmFreeObjectPool
0x14002da77  jmp     short loc_14002DA89
0x14002da79  mov     ecx, 3
0x14002da7e  int     29h; Win8: RtlFailFast(ecx)
0x14002da80  mov     edi, 0C000009Ah
0x14002da85  mov     [rsi+28h], r15
0x14002da89  mov     rbx, [rsp+58h+arg_8]
0x14002da8e  mov     eax, edi
0x14002da90  add     rsp, 20h
0x14002da94  pop     r15
0x14002da96  pop     r14
0x14002da98  pop     r13
0x14002da9a  pop     r12
0x14002da9c  pop     rdi
0x14002da9d  pop     rsi
0x14002da9e  pop     rbp
0x14002da9f  retn
```
