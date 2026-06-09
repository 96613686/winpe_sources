# UlStopConfigGroupFacet

- ea: `0x1c010a540`
- end: `0x1c010a655`
- name: `UlStopConfigGroupFacet`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1c008f21c`
- `0x1c008f680`
- `0x1c010a540`
- `0x1c010b5d0`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwarePushLock` at `0x1c010a5d1`
- `ntoskrnl!ExFreeCacheAwarePushLock` at `0x1c010a5d1`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c010a5ab`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c010a5ab`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c010a57e`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c010a57e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c010a5ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c010a61b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c010a5ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c010a61b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c010a5b7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c010a5b7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c010a56b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c010a56b`

## pseudocode

```c
__int64 __fastcall UlStopConfigGroupFacet(__int64 a1)
{
  _QWORD *i; // rdi
  _DWORD *v3; // rax
  __int64 result; // rax

  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
    WPP_SF_q(96, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids, a1);
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(a1 + 1360));
  for ( i = (_QWORD *)(a1 + 1336); (_QWORD *)*i != i; UlpTreeDeleteReservation((PVOID)(*i - 120LL)) )
    ;
  ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(a1 + 1360));
  KeLeaveCriticalRegion();
  if ( *(_QWORD *)(a1 + 1360) )
  {
    ExFreeCacheAwarePushLock();
    *(_QWORD *)(a1 + 1360) = 0;
  }
  v3 = *(_DWORD **)(a1 + 1312);
  if ( v3 )
  {
    *v3 = 1751338101;
    ExFreePoolWithTag(*(PVOID *)(a1 + 1312), 0);
    *(_QWORD *)(a1 + 1312) = 0;
  }
  ExFreePoolWithTag(*(PVOID *)(a1 + 1352), 0);
  *(_QWORD *)(a1 + 1352) = 0;
  result = LODWORD(WPP_MAIN_CB.Queue.ListEntry.Flink);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
    return WPP_SF_(97, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1c010a540  mov     [rsp+arg_0], rbx
0x1c010a545  push    rdi
0x1c010a546  sub     rsp, 20h
0x1c010a54a  mov     rbx, rcx
0x1c010a54d  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c010a553  test    al, 8
0x1c010a555  jz      short loc_1C010A56B
0x1c010a557  mov     ecx, 60h ; '`'
0x1c010a55c  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c010a563  mov     r8, rbx
0x1c010a566  call    WPP_SF_q
0x1c010a56b  call    cs:__imp_KeEnterCriticalRegion
0x1c010a572  nop     dword ptr [rax+rax+00h]
0x1c010a577  mov     rcx, [rbx+550h]
0x1c010a57e  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1c010a585  nop     dword ptr [rax+rax+00h]
0x1c010a58a  lea     rdi, [rbx+538h]
0x1c010a591  mov     rcx, [rdi]
0x1c010a594  cmp     rcx, rdi
0x1c010a597  jz      short loc_1C010A5A4
0x1c010a599  add     rcx, 0FFFFFFFFFFFFFF88h; P
0x1c010a59d  call    UlpTreeDeleteReservation
0x1c010a5a2  jmp     short loc_1C010A591
0x1c010a5a4  mov     rcx, [rbx+550h]
0x1c010a5ab  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1c010a5b2  nop     dword ptr [rax+rax+00h]
0x1c010a5b7  call    cs:__imp_KeLeaveCriticalRegion
0x1c010a5be  nop     dword ptr [rax+rax+00h]
0x1c010a5c3  mov     rcx, [rbx+550h]
0x1c010a5ca  xor     edi, edi
0x1c010a5cc  test    rcx, rcx
0x1c010a5cf  jz      short loc_1C010A5E4
0x1c010a5d1  call    cs:__imp_ExFreeCacheAwarePushLock
0x1c010a5d8  nop     dword ptr [rax+rax+00h]
0x1c010a5dd  mov     [rbx+550h], rdi
0x1c010a5e4  mov     rax, [rbx+520h]
0x1c010a5eb  test    rax, rax
0x1c010a5ee  jz      short loc_1C010A612
0x1c010a5f0  mov     dword ptr [rax], 68634C75h
0x1c010a5f6  xor     edx, edx; Tag
0x1c010a5f8  mov     rcx, [rbx+520h]; P
0x1c010a5ff  call    cs:__imp_ExFreePoolWithTag
0x1c010a606  nop     dword ptr [rax+rax+00h]
0x1c010a60b  mov     [rbx+520h], rdi
0x1c010a612  mov     rcx, [rbx+548h]; P
0x1c010a619  xor     edx, edx; Tag
0x1c010a61b  call    cs:__imp_ExFreePoolWithTag
0x1c010a622  nop     dword ptr [rax+rax+00h]
0x1c010a627  mov     [rbx+548h], rdi
0x1c010a62e  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c010a634  test    al, 8
0x1c010a636  jz      short loc_1C010A649
0x1c010a638  mov     ecx, 61h ; 'a'
0x1c010a63d  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c010a644  call    WPP_SF_
0x1c010a649  mov     rbx, [rsp+28h+arg_0]
0x1c010a64e  add     rsp, 20h
0x1c010a652  pop     rdi
0x1c010a653  retn
```
