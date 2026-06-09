# NdisWanFreeCmAfSapCB

- ea: `0x14002c0bc`
- end: `0x14002c163`
- name: `NdisWanFreeCmAfSapCB`
- size: `167`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400257a0`

## callees

- `0x14000c930`
- `0x14002c0bc`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14002c114`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c114`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c0dc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c0dc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002c13f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002c13f`

## pseudocode

```c
void __fastcall NdisWanFreeCmAfSapCB(_QWORD *Entry)
{
  __int64 v1; // rbx
  _QWORD *v3; // rdx
  PVOID *v4; // rax

  v1 = Entry[3];
  *(_BYTE *)(v1 + 168) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 160));
  _InterlockedDecrement((volatile signed __int32 *)(v1 + 64));
  v3 = (_QWORD *)*Entry;
  if ( *(_QWORD **)(*Entry + 8LL) != Entry || (v4 = (PVOID *)Entry[1], *v4 != Entry) )
    __fastfail(3u);
  *v4 = v3;
  v3[1] = v4;
  KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 160), *(_BYTE *)(v1 + 168));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 16), 0xFFFFFFFF) == 1 )
    NdisWanFreeMiniportCB((PVOID)v1);
  ExFreeToNPagedLookasideList(&AfSapVcCBList, Entry);
}

```

## disassembly

```asm
0x14002c0bc  mov     [rsp+arg_0], rbx
0x14002c0c1  mov     [rsp+arg_8], rsi
0x14002c0c6  push    rdi
0x14002c0c7  sub     rsp, 20h
0x14002c0cb  mov     rbx, [rcx+18h]
0x14002c0cf  mov     rdi, rcx
0x14002c0d2  lea     rsi, [rbx+0A0h]
0x14002c0d9  mov     rcx, rsi; SpinLock
0x14002c0dc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002c0e3  nop     dword ptr [rax+rax+00h]
0x14002c0e8  mov     [rbx+0A8h], al
0x14002c0ee  lock dec dword ptr [rbx+40h]
0x14002c0f2  mov     rdx, [rdi]
0x14002c0f5  cmp     [rdx+8], rdi
0x14002c0f9  jnz     short loc_14002C15C
0x14002c0fb  mov     rax, [rdi+8]
0x14002c0ff  cmp     [rax], rdi
0x14002c102  jnz     short loc_14002C15C
0x14002c104  mov     [rax], rdx
0x14002c107  mov     rcx, rsi; SpinLock
0x14002c10a  mov     [rdx+8], rax
0x14002c10e  mov     dl, [rbx+0A8h]; NewIrql
0x14002c114  call    cs:__imp_KeReleaseSpinLock
0x14002c11b  nop     dword ptr [rax+rax+00h]
0x14002c120  or      eax, 0FFFFFFFFh
0x14002c123  lock xadd [rbx+10h], eax
0x14002c128  cmp     eax, 1
0x14002c12b  jnz     short loc_14002C135
0x14002c12d  mov     rcx, rbx; P
0x14002c130  call    NdisWanFreeMiniportCB
0x14002c135  mov     rdx, rdi; Entry
0x14002c138  lea     rcx, AfSapVcCBList; Lookaside
0x14002c13f  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002c146  nop     dword ptr [rax+rax+00h]
0x14002c14b  mov     rbx, [rsp+28h+arg_0]
0x14002c150  mov     rsi, [rsp+28h+arg_8]
0x14002c155  add     rsp, 20h
0x14002c159  pop     rdi
0x14002c15a  retn
0x14002c15c  mov     ecx, 3
0x14002c161  int     29h; Win8: RtlFailFast(ecx)
```
