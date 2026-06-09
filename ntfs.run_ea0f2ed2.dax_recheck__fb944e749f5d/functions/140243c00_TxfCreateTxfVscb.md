# TxfCreateTxfVscb

- ea: `0x140243c00`
- end: `0x140243eb5`
- name: `TxfCreateTxfVscb`
- size: `693`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400faa0c`
- `0x14019dc78`
- `0x140294b1c`

## callees

- `0x14000c450`
- `0x140012e70`
- `0x1400596c0`
- `0x140243c00`
- `0x140243ebc`

## import_xrefs

- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140243d0e`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140243d0e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b7cb6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b7cb6`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140243c6c`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140243c6c`
- `ntoskrnl!KeInitializeEvent` at `0x140243d40`
- `ntoskrnl!KeInitializeEvent` at `0x140243d40`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b7c9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b7c9f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140243ca0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140243ca0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140243c58`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140243c58`
- `ntoskrnl!ExReleaseResourceLite` at `0x140243e0d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140243e5c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140243e90`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b7cf5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140243e0d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140243e5c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140243e90`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b7cf5`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140243dc0`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140243dc0`

## pseudocode

```c
_DWORD *__fastcall TxfCreateTxfVscb(__int64 a1, __int64 a2, int a3, char a4)
{
  _DWORD *TableContext; // rdi
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // r8
  __int64 *i; // rcx
  __int64 *v14; // r14
  char v15; // dl

  NtfsAcquireSharedFcb(a1, *(_QWORD *)(a2 + 184), 0, 0);
  ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(a2 + 184) + 328LL) + 136LL), 1u);
  TableContext = ExAllocateFromLookasideListEx(&TxfVscbLookasideList);
  memset(TableContext, 0, 0x138u);
  *((_QWORD *)TableContext + 32) = ExAllocatePoolWithTag((POOL_TYPE)528, 0x38u, 0x6D667854u);
  *TableContext = 20449046;
  *((_QWORD *)TableContext + 2) = *(_QWORD *)(a2 + 528);
  if ( a3 && (*(_DWORD *)(a1 + 436) & 4) == 0 && *(_DWORD *)(a2 + 256) == 128 )
    TxfLoadVscbFileSizes(a1, TableContext, a2);
  RtlInitializeGenericTableAvl(
    (PRTL_AVL_TABLE)(TableContext + 38),
    TxfCompareChangeEntries,
    TxfAllocateChangeEntry,
    TxfFreeTableSpace,
    TableContext);
  v9 = *((_QWORD *)TableContext + 32);
  *(_DWORD *)v9 = 1;
  *(_QWORD *)(v9 + 8) = 0;
  *(_DWORD *)(v9 + 16) = 0;
  KeInitializeEvent((PRKEVENT)(v9 + 24), SynchronizationEvent, 0);
  *((_QWORD *)TableContext + 4) = *(_QWORD *)(*(_QWORD *)(a2 + 528) + 56LL);
  v10 = *(_QWORD *)(*(_QWORD *)(a2 + 528) + 56LL);
  if ( v10 )
  {
    *(_QWORD *)(v10 + 40) = TableContext;
    _InterlockedAdd(TableContext + 1, 1u);
  }
  *(_QWORD *)(*(_QWORD *)(a2 + 528) + 56LL) = TableContext;
  _InterlockedOr(TableContext + 2, *(_DWORD *)(*(_QWORD *)(a2 + 528) + 24LL) & 0xF0000000);
  *(_DWORD *)(*(_QWORD *)(a2 + 528) + 24LL) &= 0xFFFFFFFu;
  v11 = *(_QWORD *)(a2 + 184);
  ExAcquireResourceSharedLite(*(PERESOURCE *)(*(_QWORD *)(v11 + 328) + 136LL), 1u);
  v12 = *(_QWORD *)(v11 + 328);
  for ( i = *(__int64 **)(v12 + 88); i != (__int64 *)(v12 + 88); i = (__int64 *)*i )
  {
    v14 = i;
    v15 = 1;
    if ( (*((_BYTE *)i + 78) & 8) != 0 )
    {
      if ( a4 )
      {
LABEL_12:
        if ( i != (__int64 *)(v12 + 88) )
          goto LABEL_16;
        break;
      }
      v15 = 0;
    }
    if ( v15 )
      goto LABEL_12;
  }
  ExReleaseResourceLite(*(PERESOURCE *)(v12 + 136));
  v14 = 0;
LABEL_16:
  *((_QWORD *)TableContext + 13) = v14;
  ++*((_WORD *)v14 + 38);
  ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(a2 + 184) + 328LL) + 136LL));
  NtfsReleaseFcbEx(a1, *(_QWORD *)(a2 + 184), 0);
  ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(a2 + 184) + 328LL) + 136LL));
  return TableContext;
}

```

## disassembly

```asm
0x140243c00  mov     rax, rsp
0x140243c03  mov     [rax+18h], rbx
0x140243c07  mov     [rax+10h], rdx
0x140243c0b  mov     [rax+8], rcx
0x140243c0f  push    rsi
0x140243c10  push    rdi
0x140243c11  push    r12
0x140243c13  push    r14
0x140243c15  push    r15
0x140243c17  sub     rsp, 50h
0x140243c1b  mov     r12b, r9b
0x140243c1e  mov     ebx, r8d
0x140243c21  mov     rsi, rdx
0x140243c24  mov     r15, rcx
0x140243c27  mov     qword ptr [rax-40h], 0
0x140243c2f  xor     r9d, r9d
0x140243c32  xor     r8d, r8d
0x140243c35  mov     rdx, [rdx+0B8h]
0x140243c3c  call    NtfsAcquireSharedFcb
0x140243c41  mov     rax, [rsi+0B8h]
0x140243c48  mov     rcx, [rax+148h]
0x140243c4f  mov     dl, 1; Wait
0x140243c51  mov     rcx, [rcx+88h]; Resource
0x140243c58  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140243c5f  nop     dword ptr [rax+rax+00h]
0x140243c64  nop
0x140243c65  lea     rcx, TxfVscbLookasideList; Lookaside
0x140243c6c  call    cs:__imp_ExAllocateFromLookasideListEx
0x140243c73  nop     dword ptr [rax+rax+00h]
0x140243c78  mov     rdi, rax
0x140243c7b  mov     [rsp+78h+var_40], rax
0x140243c80  xor     edx, edx; Val
0x140243c82  mov     r8d, 138h; Size
0x140243c88  mov     rcx, rax; void *
0x140243c8b  call    memset
0x140243c90  mov     edx, 38h ; '8'; NumberOfBytes
0x140243c95  mov     ecx, 210h; PoolType
0x140243c9a  mov     r8d, 6D667854h; Tag
0x140243ca0  call    cs:__imp_ExAllocatePoolWithTag
0x140243ca7  nop     dword ptr [rax+rax+00h]
0x140243cac  mov     [rdi+100h], rax
0x140243cb3  mov     dword ptr [rdi], 1380716h
0x140243cb9  mov     rax, [rsi+210h]
0x140243cc0  mov     [rdi+10h], rax
0x140243cc4  test    ebx, ebx
0x140243cc6  jz      short loc_140243CED
0x140243cc8  mov     eax, [r15+1B4h]
0x140243ccf  test    al, 4
0x140243cd1  jnz     short loc_140243CED
0x140243cd3  cmp     dword ptr [rsi+100h], 80h
0x140243cdd  jnz     short loc_140243CED
0x140243cdf  mov     r8, rsi
0x140243ce2  mov     rdx, rdi
0x140243ce5  mov     rcx, r15
0x140243ce8  call    TxfLoadVscbFileSizes
0x140243ced  lea     rcx, [rdi+98h]; Table
0x140243cf4  mov     [rsp+78h+TableContext], rdi; TableContext
0x140243cf9  lea     r9, TxfFreeTableSpace; FreeRoutine
0x140243d00  lea     r8, TxfAllocateChangeEntry; AllocateRoutine
0x140243d07  lea     rdx, TxfCompareChangeEntries; CompareRoutine
0x140243d0e  call    cs:__imp_RtlInitializeGenericTableAvl
0x140243d15  nop     dword ptr [rax+rax+00h]
0x140243d1a  mov     rcx, [rdi+100h]
0x140243d21  mov     ebx, 1
0x140243d26  mov     [rcx], ebx
0x140243d28  mov     qword ptr [rcx+8], 0
0x140243d30  mov     dword ptr [rcx+10h], 0
0x140243d37  add     rcx, 18h; Event
0x140243d3b  xor     r8d, r8d; State
0x140243d3e  mov     edx, ebx; Type
0x140243d40  call    cs:__imp_KeInitializeEvent
0x140243d47  nop     dword ptr [rax+rax+00h]
0x140243d4c  mov     rax, [rsi+210h]
0x140243d53  mov     rcx, [rax+38h]
0x140243d57  mov     [rdi+20h], rcx
0x140243d5b  mov     rax, [rsi+210h]
0x140243d62  mov     rcx, [rax+38h]
0x140243d66  test    rcx, rcx
0x140243d69  jnz     loc_140243E1E
0x140243d6f  mov     rax, [rsi+210h]
0x140243d76  mov     [rax+38h], rdi
0x140243d7a  mov     rax, [rsi+210h]
0x140243d81  mov     ecx, [rax+18h]
0x140243d84  and     ecx, 0F0000000h
0x140243d8a  lock or [rdi+8], ecx
0x140243d8e  mov     rax, [rsi+210h]
0x140243d95  and     dword ptr [rax+18h], 0FFFFFFFh
0x140243d9c  mov     rbx, [rsi+0B8h]
0x140243da3  xor     r14d, r14d
0x140243da6  mov     [rsp+78h+var_38], r14
0x140243dab  mov     [rsp+78h+var_48], r14b
0x140243db0  mov     rcx, [rbx+148h]
0x140243db7  mov     dl, 1; Wait
0x140243db9  mov     rcx, [rcx+88h]; Resource
0x140243dc0  call    cs:__imp_ExAcquireResourceSharedLite
0x140243dc7  nop     dword ptr [rax+rax+00h]
0x140243dcc  mov     r8, [rbx+148h]
0x140243dd3  mov     rcx, [r8+58h]
0x140243dd7  lea     ebx, [r14+1]
0x140243ddb  lea     r9, [r8+58h]
0x140243ddf  cmp     rcx, r9
0x140243de2  jz      short loc_140243E06
0x140243de4  mov     r14, rcx
0x140243de7  mov     [rsp+78h+var_38], rcx
0x140243dec  mov     dl, bl
0x140243dee  mov     [rsp+78h+var_48], bl
0x140243df2  test    byte ptr [rcx+4Eh], 8
0x140243df6  jnz     short loc_140243E2B
0x140243df8  test    dl, dl
0x140243dfa  jnz     short loc_140243E01
0x140243dfc  mov     rcx, [rcx]
0x140243dff  jmp     short loc_140243DDB
0x140243e01  cmp     rcx, r9
0x140243e04  jnz     short loc_140243E3E
0x140243e06  mov     rcx, [r8+88h]; Resource
0x140243e0d  call    cs:__imp_ExReleaseResourceLite
0x140243e14  nop     dword ptr [rax+rax+00h]
0x140243e19  xor     r14d, r14d
0x140243e1c  jmp     short loc_140243E3E
0x140243e1e  mov     [rcx+28h], rdi
0x140243e22  lock add [rdi+4], ebx
0x140243e26  jmp     loc_140243D6F
0x140243e2b  test    r12b, r12b
0x140243e2e  jz      short loc_140243E36
0x140243e30  mov     [rsp+78h+var_48], bl
0x140243e34  jmp     short loc_140243E01
0x140243e36  xor     dl, dl
0x140243e38  mov     [rsp+78h+var_48], dl
0x140243e3c  jmp     short loc_140243DF8
0x140243e3e  mov     [rdi+68h], r14
0x140243e42  add     [r14+4Ch], bx
0x140243e47  mov     rax, [rsi+0B8h]
0x140243e4e  mov     rcx, [rax+148h]
0x140243e55  mov     rcx, [rcx+88h]; Resource
0x140243e5c  call    cs:__imp_ExReleaseResourceLite
0x140243e63  nop     dword ptr [rax+rax+00h]
0x140243e68  nop
0x140243e69  xor     r8d, r8d
0x140243e6c  mov     rdx, [rsi+0B8h]
0x140243e73  mov     rcx, r15
0x140243e76  call    NtfsReleaseFcbEx
0x140243e7b  mov     rax, [rsi+0B8h]
0x140243e82  mov     rcx, [rax+148h]
0x140243e89  mov     rcx, [rcx+88h]; Resource
0x140243e90  call    cs:__imp_ExReleaseResourceLite
0x140243e97  nop     dword ptr [rax+rax+00h]
0x140243e9c  mov     rax, rdi
0x140243e9f  mov     rbx, [rsp+78h+arg_10]
0x140243ea7  add     rsp, 50h
0x140243eab  pop     r15
0x140243ead  pop     r14
0x140243eaf  pop     r12
0x140243eb1  pop     rdi
0x140243eb2  pop     rsi
0x140243eb3  retn
0x1402b7c6f  push    rbx
0x1402b7c71  push    rbp
0x1402b7c72  sub     rsp, 38h
0x1402b7c76  mov     rbp, rdx
0x1402b7c79  test    cl, cl
0x1402b7c7b  jz      short loc_1402B7CC3
0x1402b7c7d  mov     al, cs:NtfsStatusDebugFlags
0x1402b7c83  mov     rbx, [rbp+38h]
0x1402b7c87  test    rbx, rbx
0x1402b7c8a  jz      short loc_1402B7CC3
0x1402b7c8c  cmp     qword ptr [rbx+100h], 0
0x1402b7c94  jz      short loc_1402B7CAC
0x1402b7c96  xor     edx, edx; Tag
0x1402b7c98  mov     rcx, [rbx+100h]; P
0x1402b7c9f  call    cs:__imp_ExFreePoolWithTag
0x1402b7ca6  nop     dword ptr [rax+rax+00h]
0x1402b7cab  nop
0x1402b7cac  mov     rdx, rbx; Entry
0x1402b7caf  lea     rcx, TxfVscbLookasideList; Lookaside
0x1402b7cb6  call    cs:__imp_ExFreeToLookasideListEx
0x1402b7cbd  nop     dword ptr [rax+rax+00h]
0x1402b7cc2  nop
0x1402b7cc3  xor     r8d, r8d
0x1402b7cc6  mov     rbx, [rbp+88h]
0x1402b7ccd  mov     rdx, [rbx+0B8h]
0x1402b7cd4  mov     rcx, [rbp+80h]
0x1402b7cdb  call    NtfsReleaseFcbEx
0x1402b7ce0  mov     rax, [rbx+0B8h]
0x1402b7ce7  mov     rcx, [rax+148h]
0x1402b7cee  mov     rcx, [rcx+88h]; Resource
0x1402b7cf5  call    cs:__imp_ExReleaseResourceLite
0x1402b7cfc  nop     dword ptr [rax+rax+00h]
0x1402b7d01  nop
0x1402b7d02  add     rsp, 38h
0x1402b7d06  pop     rbp
0x1402b7d07  pop     rbx
0x1402b7d08  retn
```
