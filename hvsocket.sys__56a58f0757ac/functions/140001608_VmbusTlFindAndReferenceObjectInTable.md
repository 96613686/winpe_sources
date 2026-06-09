# VmbusTlFindAndReferenceObjectInTable

- ea: `0x140001608`
- end: `0x1400016e9`
- name: `VmbusTlFindAndReferenceObjectInTable`
- size: `225`
- prototype: `__int64 __fastcall(__int64, struct _RTL_AVL_TABLE *, void *, char)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400095a0`
- `0x140018350`
- `0x140018a88`
- `0x14001f1ec`

## callees

- `0x140001608`
- `0x14000a048`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140001648`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140001648`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400016ce`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400016ce`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400016c2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400016c2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001626`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001626`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140001636`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140001636`

## pseudocode

```c
__int64 __fastcall VmbusTlFindAndReferenceObjectInTable(__int64 a1, struct _RTL_AVL_TABLE *a2, void *a3, char a4)
{
  __int64 v4; // rbx
  _QWORD *v9; // rax
  signed __int64 v10; // rax
  unsigned __int64 i; // rcx
  signed __int64 v12; // rtt

  v4 = 0;
  if ( !a4 )
  {
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  }
  v9 = RtlLookupElementGenericTableAvl(a2, a3);
  if ( v9 )
  {
    v4 = v9[2];
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (const int *)"VmbusTlFindAndReferenceObjectInTable",
        443,
        v4,
        *(_QWORD *)(v4 + 8),
        (const int *)"Reference object");
    _m_prefetchw((const void *)(v4 + 8));
    v10 = *(_QWORD *)(v4 + 8);
    for ( i = v10 + 1; i > 1; i = v10 + 1 )
    {
      v12 = v10;
      v10 = _InterlockedCompareExchange64((volatile signed __int64 *)(v4 + 8), i, v10);
      if ( v12 == v10 )
        goto LABEL_13;
    }
    if ( i != 1 )
      __fastfail(0xEu);
    v4 = 0;
  }
LABEL_13:
  if ( !a4 )
  {
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
    KeLeaveCriticalRegion();
  }
  return v4;
}

```

## disassembly

```asm
0x140001608  push    rbx
0x14000160a  push    rbp
0x14000160b  push    rsi
0x14000160c  push    rdi
0x14000160d  push    r14
0x14000160f  sub     rsp, 30h
0x140001613  xor     ebx, ebx
0x140001615  mov     sil, r9b
0x140001618  mov     rbp, r8
0x14000161b  mov     r14, rdx
0x14000161e  mov     rdi, rcx
0x140001621  test    r9b, r9b
0x140001624  jnz     short loc_140001642
0x140001626  call    cs:__imp_KeEnterCriticalRegion
0x14000162d  nop     dword ptr [rax+rax+00h]
0x140001632  lea     rcx, [rdi+10h]; FastMutex
0x140001636  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14000163d  nop     dword ptr [rax+rax+00h]
0x140001642  mov     rdx, rbp; Buffer
0x140001645  mov     rcx, r14; Table
0x140001648  call    cs:__imp_RtlLookupElementGenericTableAvl
0x14000164f  nop     dword ptr [rax+rax+00h]
0x140001654  test    rax, rax
0x140001657  jz      short loc_1400016B9
0x140001659  mov     rbx, [rax+10h]
0x14000165d  mov     eax, cs:dword_140013058
0x140001663  cmp     eax, 5
0x140001666  jbe     short loc_14000168C
0x140001668  mov     r9, [rbx+8]
0x14000166c  lea     rax, aReferenceObjec; "Reference object"
0x140001673  mov     r8, rbx
0x140001676  mov     [rsp+58h+var_38], rax
0x14000167b  mov     edx, 1BBh
0x140001680  lea     rcx, aVmbustlfindand_1; "VmbusTlFindAndReferenceObjectInTable"
0x140001687  call    HvsocketTraceReferenceCount
0x14000168c  prefetchw byte ptr [rbx+8]
0x140001690  mov     rax, [rbx+8]
0x140001694  lea     rcx, [rax+1]
0x140001698  jmp     short loc_1400016A8
0x14000169a  lock cmpxchg [rbx+8], rcx
0x1400016a0  mov     rcx, rax
0x1400016a3  jz      short loc_1400016B9
0x1400016a5  inc     rcx
0x1400016a8  cmp     rcx, 1
0x1400016ac  ja      short loc_14000169A
0x1400016ae  jz      short loc_1400016B7
0x1400016b0  mov     ecx, 0Eh
0x1400016b5  int     29h; Win8: RtlFailFast(ecx)
0x1400016b7  xor     ebx, ebx
0x1400016b9  test    sil, sil
0x1400016bc  jnz     short loc_1400016DA
0x1400016be  lea     rcx, [rdi+10h]; FastMutex
0x1400016c2  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400016c9  nop     dword ptr [rax+rax+00h]
0x1400016ce  call    cs:__imp_KeLeaveCriticalRegion
0x1400016d5  nop     dword ptr [rax+rax+00h]
0x1400016da  mov     rax, rbx
0x1400016dd  add     rsp, 30h
0x1400016e1  pop     r14
0x1400016e3  pop     rdi
0x1400016e4  pop     rsi
0x1400016e5  pop     rbp
0x1400016e6  pop     rbx
0x1400016e7  retn
```
