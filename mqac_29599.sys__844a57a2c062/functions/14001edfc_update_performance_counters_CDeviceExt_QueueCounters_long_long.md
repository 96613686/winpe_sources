# update_performance_counters(CDeviceExt *,QueueCounters *,long,long)

- ea: `0x14001edfc`
- end: `0x14001ee2a`
- name: `?update_performance_counters@@YAXPEAUCDeviceExt@@PEAUQueueCounters@@JJ@Z`
- size: `46`
- prototype: `void __fastcall(struct CDeviceExt *, struct QueueCounters *, int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14001569c`
- `0x14001c9c0`

## callees

- `0x14001edfc`

## pseudocode

```c
void __fastcall update_performance_counters(struct CDeviceExt *a1, struct QueueCounters *a2, int a3, int a4)
{
  __int64 v4; // rax

  if ( a2 )
  {
    *((_QWORD *)a2 + 1) += a3;
    *(_QWORD *)a2 += a4;
  }
  v4 = *((_QWORD *)a1 + 136);
  if ( v4 )
  {
    *(_QWORD *)(v4 + 80) += a3;
    *(_QWORD *)(*((_QWORD *)a1 + 136) + 72LL) += a4;
  }
}

```

## disassembly

```asm
0x14001edfc  movsxd  r10, r8d
0x14001edff  movsxd  r8, r9d
0x14001ee02  test    rdx, rdx
0x14001ee05  jz      short loc_14001EE0E
0x14001ee07  add     [rdx+8], r10
0x14001ee0b  add     [rdx], r8
0x14001ee0e  mov     rax, [rcx+440h]
0x14001ee15  test    rax, rax
0x14001ee18  jz      short locret_14001EE29
0x14001ee1a  add     [rax+50h], r10
0x14001ee1e  mov     rax, [rcx+440h]
0x14001ee25  add     [rax+48h], r8
0x14001ee29  retn
```
