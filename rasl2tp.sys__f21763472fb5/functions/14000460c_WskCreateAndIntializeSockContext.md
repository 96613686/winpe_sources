# WskCreateAndIntializeSockContext

- ea: `0x14000460c`
- end: `0x140004683`
- name: `WskCreateAndIntializeSockContext`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140019358`

## callees

- `0x14000460c`

## import_xrefs

- `ntoskrnl!MmLockPagableDataSection` at `0x140004620`
- `ntoskrnl!MmLockPagableDataSection` at `0x140004620`
- `ntoskrnl!ExAllocatePool2` at `0x140004643`
- `ntoskrnl!ExAllocatePool2` at `0x140004643`

## pseudocode

```c
__int64 WskCreateAndIntializeSockContext()
{
  __int64 result; // rax

  if ( !g_fWSKPagesLocked )
  {
    MmLockPagableDataSection(WskCreateSocket);
    g_fWSKPagesLocked = 1;
  }
  result = ExAllocatePool2(64, 576, 1951674956);
  if ( result )
  {
    *(_DWORD *)result = 1129010007;
    *(_QWORD *)(result + 48) = WskLibDummyLogger;
    *(_QWORD *)(result + 520) = FreeSockHandle;
    *(_DWORD *)(result + 512) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x14000460c  sub     rsp, 28h
0x140004610  cmp     cs:g_fWSKPagesLocked, 0
0x140004617  jnz     short loc_140004633
0x140004619  lea     rcx, WskCreateSocket; AddressWithinSection
0x140004620  call    cs:__imp_MmLockPagableDataSection
0x140004627  nop     dword ptr [rax+rax+00h]
0x14000462c  mov     cs:g_fWSKPagesLocked, 1
0x140004633  mov     edx, 240h
0x140004638  mov     r8d, 7454324Ch
0x14000463e  mov     ecx, 40h ; '@'
0x140004643  call    cs:__imp_ExAllocatePool2
0x14000464a  nop     dword ptr [rax+rax+00h]
0x14000464f  test    rax, rax
0x140004652  jz      short loc_14000467D
0x140004654  lea     rcx, WskLibDummyLogger
0x14000465b  mov     dword ptr [rax], 434B5357h
0x140004661  mov     [rax+30h], rcx
0x140004665  lea     rcx, FreeSockHandle
0x14000466c  mov     [rax+208h], rcx
0x140004673  mov     dword ptr [rax+200h], 1
0x14000467d  add     rsp, 28h
0x140004681  retn
```
