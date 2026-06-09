# CmpStopRMLog

- ea: `0x1408e5fb0`
- end: `0x1408e6054`
- name: `CmpStopRMLog`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1408922f0`

## callees

- `0x140216db0`
- `0x14036f270`
- `0x1408e5fb0`
- `0x1408e7248`
- `0x1408e7274`
- `0x140bfa870`
- `0x140bfa950`

## import_xrefs

- `ext-ms-win-fs-clfs-l1-1-0!ClfsDeleteLogByPointer` at `0x1408e6046`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsDeleteLogByPointer` at `0x1408e6046`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsDeleteMarshallingArea` at `0x1408e6023`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsDeleteMarshallingArea` at `0x1408e6023`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x1408e5ffe`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x1408e5ffe`

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
    if ( (PVOID)a1 != CmRmSystem && *(_QWORD *)(a1 + 16) == a1 + 16 )
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
0x1408e5fb0  push    rbx
0x1408e5fb2  sub     rsp, 20h
0x1408e5fb6  mov     rbx, rcx
0x1408e5fb9  call    CmpLockRegistry
0x1408e5fbe  mov     rcx, rbx
0x1408e5fc1  call    LockRMLog
0x1408e5fc6  cmp     qword ptr [rbx+58h], 0
0x1408e5fcb  jnz     short loc_1408E5FEA
0x1408e5fcd  mov     rcx, [rbx+80h]; Resource
0x1408e5fd4  call    ExReleaseResourceLite
0x1408e5fd9  call    KeLeaveCriticalRegion
0x1408e5fde  call    CmpUnlockRegistry
0x1408e5fe3  add     rsp, 20h
0x1408e5fe7  pop     rbx
0x1408e5fe8  retn
0x1408e5fea  cmp     qword ptr [rbx+60h], 0
0x1408e5fef  jnz     short loc_1408E6014
0x1408e5ff1  cmp     rbx, cs:CmRmSystem
0x1408e5ff8  jnz     short loc_1408E6039
0x1408e5ffa  mov     rcx, [rbx+58h]; plfoLog
0x1408e5ffe  call    cs:__imp_ClfsCloseLogFileObject
0x1408e6005  nop     dword ptr [rax+rax+00h]
0x1408e600a  mov     qword ptr [rbx+58h], 0
0x1408e6012  jmp     short loc_1408E5FCD
0x1408e6014  xor     r8d, r8d
0x1408e6017  mov     rcx, rbx
0x1408e601a  call    CmpLogCheckpoint
0x1408e601f  mov     rcx, [rbx+60h]; pvMarshalContext
0x1408e6023  call    cs:__imp_ClfsDeleteMarshallingArea
0x1408e602a  nop     dword ptr [rax+rax+00h]
0x1408e602f  mov     qword ptr [rbx+60h], 0
0x1408e6037  jmp     short loc_1408E5FF1
0x1408e6039  lea     rax, [rbx+10h]
0x1408e603d  cmp     [rax], rax
0x1408e6040  jnz     short loc_1408E5FFA
0x1408e6042  mov     rcx, [rbx+58h]; plfoLog
0x1408e6046  call    cs:__imp_ClfsDeleteLogByPointer
0x1408e604d  nop     dword ptr [rax+rax+00h]
0x1408e6052  jmp     short loc_1408E5FFA
```
