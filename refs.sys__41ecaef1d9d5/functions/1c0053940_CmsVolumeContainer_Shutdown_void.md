# CmsVolumeContainer::Shutdown(void)

- ea: `0x1c0053940`
- end: `0x1c0053aac`
- name: `?Shutdown@CmsVolumeContainer@@QEAAXXZ`
- size: `364`
- prototype: `void __fastcall(CmsVolumeContainer *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c004ffe0`

## callees

- `0x1c002357c`
- `0x1c0036a10`
- `0x1c0053940`
- `0x1c0053b30`
- `0x1c0053bbc`
- `0x1c006ac80`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1c00539cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0053a69`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0053a7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00539cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0053a69`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0053a7a`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1c005396e`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1c005396e`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x1c0053983`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x1c0053983`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x1c0053a0b`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x1c0053a0b`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x1c0053a20`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x1c0053a20`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1c0053a3e`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1c0053a3e`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x1c0053a8d`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x1c0053a8d`

## pseudocode

```c
void __fastcall CmsVolumeContainer::Shutdown(CmsVolumeContainer *this)
{
  struct _IO_REMOVE_LOCK *v1; // rbx
  __int64 v3; // r8
  CmsFailoverBPlusTable *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE *v7; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v8; // rax
  struct _RTL_DYNAMIC_HASH_TABLE *v9; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v10; // rbx
  struct _LIST_ENTRY *Flink; // rcx
  void *Signature; // rcx
  _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+30h] [rbp-38h] BYREF

  v1 = (struct _IO_REMOVE_LOCK *)((char *)this + 328);
  IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)((char *)this + 328), 0, File, 1u, 0x20u);
  IoReleaseRemoveLockAndWaitEx(v1, 0, 0x20u);
  CmsVolumeContainer::FreeCompactAndCompressContainerBuffers(this);
  v4 = (CmsFailoverBPlusTable *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    CmsFailoverBPlusTable::UninitializeCaching(v4, 0, 1u, 0, 0);
    CmsReferenced::Release(*((CmsReferenced **)this + 2));
    *((_QWORD *)this + 2) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 4);
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  v6 = *((_QWORD *)this + 8);
  if ( v6 )
  {
    LOBYTE(v3) = 1;
    (*(void (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 8LL))(v6, 0, v3, 0, 0);
    CmsReferenced::Release(*((CmsReferenced **)this + 8));
    *((_QWORD *)this + 8) = 0;
  }
  v7 = (struct _RTL_DYNAMIC_HASH_TABLE *)*((_QWORD *)this + 6);
  if ( v7 )
  {
    memset(&Enumerator, 0, sizeof(Enumerator));
    RtlInitEnumerationHashTable(v7, &Enumerator);
    while ( 1 )
    {
      v8 = RtlEnumerateEntryHashTable(*((PRTL_DYNAMIC_HASH_TABLE *)this + 6), &Enumerator);
      v9 = (struct _RTL_DYNAMIC_HASH_TABLE *)*((_QWORD *)this + 6);
      v10 = v8;
      if ( !v8 )
        break;
      RtlRemoveEntryHashTable(v9, v8, 0);
      Flink = v10[6].Linkage.Flink;
      if ( Flink )
        CmsLookasides::Free(Flink);
      Signature = (void *)v10[22].Signature;
      if ( Signature )
        ExFreePoolWithTag(Signature, 0);
      ExFreePoolWithTag(v10, 0);
    }
    RtlEndEnumerationHashTable(v9, &Enumerator);
  }
}

```

## disassembly

```asm
0x1c0053940  mov     [rsp+arg_0], rbx
0x1c0053945  push    rdi
0x1c0053946  sub     rsp, 60h
0x1c005394a  lea     rbx, [rcx+148h]
0x1c0053951  mov     [rsp+68h+RemlockSize], 20h ; ' '; struct CmsTransactionContext *
0x1c0053959  mov     rdi, rcx
0x1c005395c  lea     r8, File; File
0x1c0053963  mov     rcx, rbx; RemoveLock
0x1c0053966  mov     r9d, 1; Line
0x1c005396c  xor     edx, edx; Tag
0x1c005396e  call    cs:__imp_IoAcquireRemoveLockEx
0x1c0053975  nop     dword ptr [rax+rax+00h]
0x1c005397a  xor     edx, edx; Tag
0x1c005397c  mov     rcx, rbx; RemoveLock
0x1c005397f  lea     r8d, [rdx+20h]; RemlockSize
0x1c0053983  call    cs:__imp_IoReleaseRemoveLockAndWaitEx
0x1c005398a  nop     dword ptr [rax+rax+00h]
0x1c005398f  mov     rcx, rdi; this
0x1c0053992  call    ?FreeCompactAndCompressContainerBuffers@CmsVolumeContainer@@QEAAXXZ; CmsVolumeContainer::FreeCompactAndCompressContainerBuffers(void)
0x1c0053997  mov     rcx, [rdi+10h]; this
0x1c005399b  test    rcx, rcx
0x1c005399e  jz      short loc_1C00539C1
0x1c00539a0  and     qword ptr [rsp+68h+RemlockSize], 0
0x1c00539a6  xor     r9d, r9d; struct CmsBPlusTable *
0x1c00539a9  mov     r8b, 1; unsigned __int8
0x1c00539ac  xor     edx, edx; unsigned __int8
0x1c00539ae  call    ?UninitializeCaching@CmsFailoverBPlusTable@@UEAAXEEPEAVCmsBPlusTable@@PEAVCmsTransactionContext@@@Z; CmsFailoverBPlusTable::UninitializeCaching(uchar,uchar,CmsBPlusTable *,CmsTransactionContext *)
0x1c00539b3  mov     rcx, [rdi+10h]; this
0x1c00539b7  call    ?Release@CmsReferenced@@QEAAXXZ; CmsReferenced::Release(void)
0x1c00539bc  and     qword ptr [rdi+10h], 0
0x1c00539c1  mov     rcx, [rdi+20h]; P
0x1c00539c5  test    rcx, rcx
0x1c00539c8  jz      short loc_1C00539D8
0x1c00539ca  xor     edx, edx; Tag
0x1c00539cc  call    cs:__imp_ExFreePoolWithTag
0x1c00539d3  nop     dword ptr [rax+rax+00h]
0x1c00539d8  mov     rcx, [rdi+40h]
0x1c00539dc  test    rcx, rcx
0x1c00539df  jnz     loc_1C008810A
0x1c00539e5  mov     rcx, [rdi+30h]; HashTable
0x1c00539e9  test    rcx, rcx
0x1c00539ec  jz      loc_1C0053A99
0x1c00539f2  xorps   xmm0, xmm0
0x1c00539f5  lea     rdx, [rsp+68h+Enumerator]; Enumerator
0x1c00539fa  xor     eax, eax
0x1c00539fc  movups  xmmword ptr [rsp+68h+Enumerator], xmm0
0x1c0053a01  mov     qword ptr [rsp+68h+Enumerator.BucketIndex], rax
0x1c0053a06  movups  xmmword ptr [rsp+68h+Enumerator+10h], xmm0
0x1c0053a0b  call    cs:__imp_RtlInitEnumerationHashTable
0x1c0053a12  nop     dword ptr [rax+rax+00h]
0x1c0053a17  mov     rcx, [rdi+30h]; HashTable
0x1c0053a1b  lea     rdx, [rsp+68h+Enumerator]; Enumerator
0x1c0053a20  call    cs:__imp_RtlEnumerateEntryHashTable
0x1c0053a27  nop     dword ptr [rax+rax+00h]
0x1c0053a2c  mov     rcx, [rdi+30h]; HashTable
0x1c0053a30  mov     rbx, rax
0x1c0053a33  test    rax, rax
0x1c0053a36  jz      short loc_1C0053A88
0x1c0053a38  xor     r8d, r8d; Context
0x1c0053a3b  mov     rdx, rax; Entry
0x1c0053a3e  call    cs:__imp_RtlRemoveEntryHashTable
0x1c0053a45  nop     dword ptr [rax+rax+00h]
0x1c0053a4a  test    rbx, rbx
0x1c0053a4d  jz      short loc_1C0053A17
0x1c0053a4f  mov     rcx, [rbx+90h]; void *
0x1c0053a56  test    rcx, rcx
0x1c0053a59  jnz     short loc_1C0053AA5
0x1c0053a5b  mov     rcx, [rbx+220h]; P
0x1c0053a62  test    rcx, rcx
0x1c0053a65  jz      short loc_1C0053A75
0x1c0053a67  xor     edx, edx; Tag
0x1c0053a69  call    cs:__imp_ExFreePoolWithTag
0x1c0053a70  nop     dword ptr [rax+rax+00h]
0x1c0053a75  xor     edx, edx; Tag
0x1c0053a77  mov     rcx, rbx; P
0x1c0053a7a  call    cs:__imp_ExFreePoolWithTag
0x1c0053a81  nop     dword ptr [rax+rax+00h]
0x1c0053a86  jmp     short loc_1C0053A17
0x1c0053a88  lea     rdx, [rsp+68h+Enumerator]; Enumerator
0x1c0053a8d  call    cs:__imp_RtlEndEnumerationHashTable
0x1c0053a94  nop     dword ptr [rax+rax+00h]
0x1c0053a99  mov     rbx, [rsp+68h+arg_0]
0x1c0053a9e  add     rsp, 60h
0x1c0053aa2  pop     rdi
0x1c0053aa3  retn
0x1c0053aa5  call    ?Free@CmsLookasides@@SAXPEAX@Z; CmsLookasides::Free(void *)
0x1c0053aaa  jmp     short loc_1C0053A5B
0x1c008810a  mov     rax, [rcx]
0x1c008810d  xor     r9d, r9d
0x1c0088110  and     qword ptr [rsp+68h+RemlockSize], 0
0x1c0088116  mov     r8b, 1
0x1c0088119  xor     edx, edx
0x1c008811b  mov     rax, [rax+8]
0x1c008811f  call    cs:__guard_dispatch_icall_fptr
0x1c0088125  mov     rcx, [rdi+40h]; this
0x1c0088129  call    ?Release@CmsReferenced@@QEAAXXZ; CmsReferenced::Release(void)
0x1c008812e  and     qword ptr [rdi+40h], 0
0x1c0088133  jmp     loc_1C00539E5
```
