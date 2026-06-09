# EtwReadThunk_AllocateData

- ea: `0x18000ed54`
- end: `0x18000edd9`
- name: `EtwReadThunk_AllocateData`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000af2c`

## callees

- `0x18000ed20`
- `0x18000ed54`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000ed79`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000ed79`

## pseudocode

```c
struct _SINGLE_LIST_ENTRY *EtwReadThunk_AllocateData()
{
  struct _SINGLE_LIST_ENTRY *Next; // rax
  struct _SINGLE_LIST_ENTRY *v1; // rcx
  struct _SINGLE_LIST_ENTRY *v2; // rbx
  struct _RTL_SRWLOCK *v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  RtlSRWLockHolderExclusive_t::Unlock((RtlSRWLockHolderExclusive_t *)&v4);
  v4 = &EtwReadThunk_Lock;
  RtlAcquireSRWLockExclusive();
  Next = EtwReadThunk_Pool.Next;
  while ( 1 )
  {
    v1 = Next;
    if ( !Next )
      break;
    Next = Next->Next;
    v2 = v1 - 1;
    EtwReadThunk_Pool.Next = Next;
    if ( v1[-1].Next )
    {
      v1->Next = 0;
      v1[1].Next = 0;
      RtlSRWLockHolderExclusive_t::Unlock((RtlSRWLockHolderExclusive_t *)&v4);
      return v2;
    }
  }
  RtlSRWLockHolderExclusive_t::Unlock((RtlSRWLockHolderExclusive_t *)&v4);
  return 0;
}

```

## disassembly

```asm
0x18000ed54  push    rbx
0x18000ed56  sub     rsp, 20h
0x18000ed5a  lea     rcx, [rsp+28h+arg_0]; this
0x18000ed5f  mov     [rsp+28h+arg_0], 0
0x18000ed68  call    ?Unlock@RtlSRWLockHolderExclusive_t@@AEAAXXZ; RtlSRWLockHolderExclusive_t::Unlock(void)
0x18000ed6d  lea     rcx, ?EtwReadThunk_Lock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK EtwReadThunk_Lock
0x18000ed74  mov     [rsp+28h+arg_0], rcx
0x18000ed79  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000ed80  nop     dword ptr [rax+rax+00h]
0x18000ed85  mov     rax, cs:?EtwReadThunk_Pool@@3U_SINGLE_LIST_ENTRY@@A; _SINGLE_LIST_ENTRY EtwReadThunk_Pool
0x18000ed8c  mov     rcx, rax
0x18000ed8f  test    rax, rax
0x18000ed92  jz      short loc_18000EDC6
0x18000ed94  mov     rax, [rax]
0x18000ed97  lea     rbx, [rcx-8]
0x18000ed9b  mov     cs:?EtwReadThunk_Pool@@3U_SINGLE_LIST_ENTRY@@A, rax; _SINGLE_LIST_ENTRY EtwReadThunk_Pool
0x18000eda2  cmp     qword ptr [rbx], 0
0x18000eda6  jz      short loc_18000ED8C
0x18000eda8  mov     qword ptr [rcx], 0
0x18000edaf  mov     qword ptr [rcx+8], 0
0x18000edb7  lea     rcx, [rsp+28h+arg_0]; this
0x18000edbc  call    ?Unlock@RtlSRWLockHolderExclusive_t@@AEAAXXZ; RtlSRWLockHolderExclusive_t::Unlock(void)
0x18000edc1  mov     rax, rbx
0x18000edc4  jmp     short loc_18000EDD2
0x18000edc6  lea     rcx, [rsp+28h+arg_0]; this
0x18000edcb  call    ?Unlock@RtlSRWLockHolderExclusive_t@@AEAAXXZ; RtlSRWLockHolderExclusive_t::Unlock(void)
0x18000edd0  xor     eax, eax
0x18000edd2  add     rsp, 20h
0x18000edd6  pop     rbx
0x18000edd7  retn
```
