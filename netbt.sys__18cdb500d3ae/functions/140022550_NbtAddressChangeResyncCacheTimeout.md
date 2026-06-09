# NbtAddressChangeResyncCacheTimeout

- ea: `0x140022550`
- end: `0x1400225e2`
- name: `NbtAddressChangeResyncCacheTimeout`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140022550`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x1400225d1`
- `ntoskrnl!ExQueueWorkItem` at `0x1400225d1`
- `ntoskrnl!ExAllocatePool2` at `0x14002256d`
- `ntoskrnl!ExAllocatePool2` at `0x14002256d`

## pseudocode

```c
void __fastcall NbtAddressChangeResyncCacheTimeout(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 Pool2; // rax

  if ( a3 )
  {
    Pool2 = ExAllocatePool2(64, 80, 842162766);
    if ( Pool2 )
    {
      *(_DWORD *)(Pool2 + 72) = 1;
      *(_QWORD *)(Pool2 + 32) = 0;
      *(_QWORD *)(Pool2 + 40) = 0;
      *(_QWORD *)(Pool2 + 48) = 0;
      *(_QWORD *)(Pool2 + 56) = 0;
      *(_QWORD *)(Pool2 + 64) = DelayedNbtResyncRemoteCache;
      _InterlockedAdd(&dword_140039754, 1u);
      *(_QWORD *)(Pool2 + 24) = Pool2;
      *(_QWORD *)(Pool2 + 16) = NTExecuteDedicatedWorkitem;
      *(_QWORD *)Pool2 = 0;
      ExQueueWorkItem((PWORK_QUEUE_ITEM)Pool2, DelayedWorkQueue);
    }
  }
}

```

## disassembly

```asm
0x140022550  sub     rsp, 28h
0x140022554  test    r8, r8
0x140022557  jnz     short loc_14002255F
0x140022559  add     rsp, 28h
0x14002255d  retn
0x14002255f  mov     edx, 50h ; 'P'
0x140022564  mov     r8d, 3232624Eh
0x14002256a  lea     ecx, [rdx-10h]
0x14002256d  call    cs:__imp_ExAllocatePool2
0x140022574  nop     dword ptr [rax+rax+00h]
0x140022579  test    rax, rax
0x14002257c  jz      short loc_140022559
0x14002257e  mov     edx, 1; QueueType
0x140022583  lea     rcx, DelayedNbtResyncRemoteCache
0x14002258a  mov     [rax+48h], edx
0x14002258d  mov     qword ptr [rax+20h], 0
0x140022595  mov     qword ptr [rax+28h], 0
0x14002259d  mov     qword ptr [rax+30h], 0
0x1400225a5  mov     qword ptr [rax+38h], 0
0x1400225ad  mov     [rax+40h], rcx
0x1400225b1  lock add cs:dword_140039754, edx
0x1400225b8  lea     rcx, NTExecuteDedicatedWorkitem
0x1400225bf  mov     [rax+18h], rax
0x1400225c3  mov     [rax+10h], rcx
0x1400225c7  mov     rcx, rax; WorkItem
0x1400225ca  mov     qword ptr [rax], 0
0x1400225d1  call    cs:__imp_ExQueueWorkItem
0x1400225d8  nop     dword ptr [rax+rax+00h]
0x1400225dd  jmp     loc_140022559
```
