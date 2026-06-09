# WskCreateAndIntializeSockContext

- ea: `0x1400073a0`
- end: `0x140007417`
- name: `WskCreateAndIntializeSockContext`
- size: `119`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140011d04`
- `0x140012da4`
- `0x140014fd8`

## callees

- `0x1400073a0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400073d7`
- `ntoskrnl!ExAllocatePool2` at `0x1400073d7`
- `ntoskrnl!MmLockPagableDataSection` at `0x1400073b4`
- `ntoskrnl!MmLockPagableDataSection` at `0x1400073b4`

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
  result = ExAllocatePool2(64, 576, 1465078864);
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
0x1400073a0  sub     rsp, 28h
0x1400073a4  cmp     cs:g_fWSKPagesLocked, 0
0x1400073ab  jnz     short loc_1400073C7
0x1400073ad  lea     rcx, WskCreateSocket; AddressWithinSection
0x1400073b4  call    cs:__imp_MmLockPagableDataSection
0x1400073bb  nop     dword ptr [rax+rax+00h]
0x1400073c0  mov     cs:g_fWSKPagesLocked, 1
0x1400073c7  mov     edx, 240h
0x1400073cc  mov     r8d, 57535450h
0x1400073d2  mov     ecx, 40h ; '@'
0x1400073d7  call    cs:__imp_ExAllocatePool2
0x1400073de  nop     dword ptr [rax+rax+00h]
0x1400073e3  test    rax, rax
0x1400073e6  jz      short loc_140007411
0x1400073e8  lea     rcx, WskLibDummyLogger
0x1400073ef  mov     dword ptr [rax], 434B5357h
0x1400073f5  mov     [rax+30h], rcx
0x1400073f9  lea     rcx, FreeSockHandle
0x140007400  mov     [rax+208h], rcx
0x140007407  mov     dword ptr [rax+200h], 1
0x140007411  add     rsp, 28h
0x140007415  retn
```
