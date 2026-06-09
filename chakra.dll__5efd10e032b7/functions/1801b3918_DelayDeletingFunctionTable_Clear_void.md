# DelayDeletingFunctionTable::Clear(void)

- ea: `0x1801b3918`
- end: `0x1801b39a4`
- name: `?Clear@DelayDeletingFunctionTable@@SAXXZ`
- size: `140`
- prototype: `void(void)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x1801b1710`
- `0x1801b1e88`
- `0x1801b27a4`
- `0x1801b3290`
- `0x1801b3378`
- `0x1801b34e4`
- `0x1801b3820`
- `0x1801b44d8`
- `0x1801b5ff0`
- `0x1803d6278`
- `0x18053f6f4`
- `0x180541258`
- `0x180541578`
- `0x18056120c`
- `0x180561364`

## callees

- `0x1801b3918`
- `0x1801b39ac`

## import_xrefs

- `msvcrt!_aligned_free` at `0x1801b3995`
- `msvcrt!_aligned_free` at `0x1801b3995`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b3970`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b3970`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801b3945`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801b3945`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1801b3959`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1801b3959`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void DelayDeletingFunctionTable::Clear(void)
{
  PSLIST_ENTRY v0; // rax
  PSLIST_ENTRY v1; // rbx

  if ( DelayDeletingFunctionTable::Head )
  {
    EnterCriticalSection(&DelayDeletingFunctionTable::cs);
    while ( 1 )
    {
      v0 = InterlockedPopEntrySList(DelayDeletingFunctionTable::Head);
      v1 = v0;
      if ( !v0 )
        break;
      DelayDeletingFunctionTable::DeleteFunctionTable((struct Memory::XDataAllocation *)v0[1].Next);
      _aligned_free(v1);
    }
    LeaveCriticalSection(&DelayDeletingFunctionTable::cs);
  }
}

```

## disassembly

```asm
0x1801b3918  push    rdi
0x1801b391a  sub     rsp, 30h
0x1801b391e  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1801b3927  mov     [rsp+38h+arg_0], rbx
0x1801b392c  cmp     cs:?Head@DelayDeletingFunctionTable@@2PEAT_SLIST_HEADER@@EA, 0; _SLIST_HEADER * DelayDeletingFunctionTable::Head
0x1801b3934  jz      short loc_1801B397D
0x1801b3936  lea     rdi, ?cs@DelayDeletingFunctionTable@@2VCriticalSection@@A; CriticalSection DelayDeletingFunctionTable::cs
0x1801b393d  mov     [rsp+38h+var_10], rdi
0x1801b3942  mov     rcx, rdi; lpCriticalSection
0x1801b3945  call    cs:__imp_EnterCriticalSection
0x1801b394c  nop     dword ptr [rax+rax+00h]
0x1801b3951  nop
0x1801b3952  mov     rcx, cs:?Head@DelayDeletingFunctionTable@@2PEAT_SLIST_HEADER@@EA; ListHead
0x1801b3959  call    cs:__imp_InterlockedPopEntrySList
0x1801b3960  nop     dword ptr [rax+rax+00h]
0x1801b3965  test    rax, rax
0x1801b3968  mov     rbx, rax
0x1801b396b  jnz     short loc_1801B3989
0x1801b396d  mov     rcx, rdi; lpCriticalSection
0x1801b3970  call    cs:__imp_LeaveCriticalSection
0x1801b3977  nop     dword ptr [rax+rax+00h]
0x1801b397c  nop
0x1801b397d  mov     rbx, [rsp+38h+arg_0]
0x1801b3982  add     rsp, 30h
0x1801b3986  pop     rdi
0x1801b3987  retn
0x1801b3989  mov     rcx, [rbx+10h]; struct Memory::XDataAllocation *
0x1801b398d  call    ?DeleteFunctionTable@DelayDeletingFunctionTable@@SAXPEAUXDataAllocation@Memory@@@Z; DelayDeletingFunctionTable::DeleteFunctionTable(Memory::XDataAllocation *)
0x1801b3992  mov     rcx, rbx; Block
0x1801b3995  call    cs:__imp__aligned_free
0x1801b399c  nop     dword ptr [rax+rax+00h]
0x1801b39a1  jmp     short loc_1801B3952
```
