# CmpStopRMLog

- ea: `0x1408b10a0`
- end: `0x1408b1144`
- name: `CmpStopRMLog`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1408977e0`

## callees

- `0x140227210`
- `0x1402f8270`
- `0x1408b10a0`
- `0x1408b2338`
- `0x1408b2364`
- `0x140bf7870`
- `0x140bf7950`

## import_xrefs

- `ext-ms-win-fs-clfs-l1-1-0!ClfsDeleteLogByPointer` at `0x1408b1136`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsDeleteLogByPointer` at `0x1408b1136`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsDeleteMarshallingArea` at `0x1408b1113`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsDeleteMarshallingArea` at `0x1408b1113`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x1408b10ee`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x1408b10ee`

## pseudocode

```c
__int64 __fastcall CmpStopRMLog(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx

  CmpLockRegistry(a1);
  LockRMLog(a1);
  if ( *(_QWORD *)(a1 + 88) )
  {
    if ( *(_QWORD *)(a1 + 96) )
    {
      CmpLogCheckpoint(a1, v2, 0);
      ClfsDeleteMarshallingArea(*(PVOID *)(a1 + 96));
      *(_QWORD *)(a1 + 96) = 0;
    }
    if ( (struct _LIST_ENTRY *)a1 != WheapPfaLock.Timer.TimerListEntry.Blink && *(_QWORD *)(a1 + 16) == a1 + 16 )
      ClfsDeleteLogByPointer(*(PLOG_FILE_OBJECT *)(a1 + 88));
    ClfsCloseLogFileObject(*(PLOG_FILE_OBJECT *)(a1 + 88));
    *(_QWORD *)(a1 + 88) = 0;
  }
  ExReleaseResourceLite(*(PERESOURCE *)(a1 + 128));
  KeLeaveCriticalRegion();
  return CmpUnlockRegistry(v3);
}

```

## disassembly

```asm
0x1408b10a0  push    rbx
0x1408b10a2  sub     rsp, 20h
0x1408b10a6  mov     rbx, rcx
0x1408b10a9  call    CmpLockRegistry
0x1408b10ae  mov     rcx, rbx
0x1408b10b1  call    LockRMLog
0x1408b10b6  cmp     qword ptr [rbx+58h], 0
0x1408b10bb  jnz     short loc_1408B10DA
0x1408b10bd  mov     rcx, [rbx+80h]; Resource
0x1408b10c4  call    ExReleaseResourceLite
0x1408b10c9  call    KeLeaveCriticalRegion
0x1408b10ce  call    CmpUnlockRegistry
0x1408b10d3  add     rsp, 20h
0x1408b10d7  pop     rbx
0x1408b10d8  retn
0x1408b10da  cmp     qword ptr [rbx+60h], 0
0x1408b10df  jnz     short loc_1408B1104
0x1408b10e1  cmp     rbx, cs:WheapPfaLock.Timer.TimerListEntry.Blink
0x1408b10e8  jnz     short loc_1408B1129
0x1408b10ea  mov     rcx, [rbx+58h]; plfoLog
0x1408b10ee  call    cs:__imp_ClfsCloseLogFileObject
0x1408b10f5  nop     dword ptr [rax+rax+00h]
0x1408b10fa  mov     qword ptr [rbx+58h], 0
0x1408b1102  jmp     short loc_1408B10BD
0x1408b1104  xor     r8d, r8d
0x1408b1107  mov     rcx, rbx
0x1408b110a  call    CmpLogCheckpoint
0x1408b110f  mov     rcx, [rbx+60h]; pvMarshalContext
0x1408b1113  call    cs:__imp_ClfsDeleteMarshallingArea
0x1408b111a  nop     dword ptr [rax+rax+00h]
0x1408b111f  mov     qword ptr [rbx+60h], 0
0x1408b1127  jmp     short loc_1408B10E1
0x1408b1129  lea     rax, [rbx+10h]
0x1408b112d  cmp     [rax], rax
0x1408b1130  jnz     short loc_1408B10EA
0x1408b1132  mov     rcx, [rbx+58h]; plfoLog
0x1408b1136  call    cs:__imp_ClfsDeleteLogByPointer
0x1408b113d  nop     dword ptr [rax+rax+00h]
0x1408b1142  jmp     short loc_1408B10EA
```
