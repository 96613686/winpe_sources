# MupiUpdateMupDeviceOpenCount

- ea: `0x1400025ac`
- end: `0x14000260b`
- name: `MupiUpdateMupDeviceOpenCount`
- size: `95`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140019fb0`
- `0x14001a3c0`

## callees

- `0x1400025ac`

## import_xrefs

- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x1400025fd`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x1400025fd`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1400025db`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1400025db`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1400025bb`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1400025bb`

## pseudocode

```c
void __fastcall MupiUpdateMupDeviceOpenCount(char a1)
{
  KeAcquireGuardedMutex(&MupiMupDeviceOpenCountMutex);
  if ( a1 )
  {
    ++MupiMupDeviceOpenCount;
  }
  else if ( !--MupiMupDeviceOpenCount )
  {
    FsRtlTeardownPerStreamContexts(&g_MupAdvancedFcbHeader);
  }
  KeReleaseGuardedMutex(&MupiMupDeviceOpenCountMutex);
}

```

## disassembly

```asm
0x1400025ac  push    rbx
0x1400025ae  sub     rsp, 20h
0x1400025b2  mov     bl, cl
0x1400025b4  lea     rcx, MupiMupDeviceOpenCountMutex; Mutex
0x1400025bb  call    cs:__imp_KeAcquireGuardedMutex
0x1400025c2  nop     dword ptr [rax+rax+00h]
0x1400025c7  test    bl, bl
0x1400025c9  jnz     short loc_1400025EE
0x1400025cb  add     cs:MupiMupDeviceOpenCount, 0FFFFFFFFh
0x1400025d2  jz      short loc_1400025F6
0x1400025d4  lea     rcx, MupiMupDeviceOpenCountMutex; Mutex
0x1400025db  call    cs:__imp_KeReleaseGuardedMutex
0x1400025e2  nop     dword ptr [rax+rax+00h]
0x1400025e7  add     rsp, 20h
0x1400025eb  pop     rbx
0x1400025ec  retn
0x1400025ee  inc     cs:MupiMupDeviceOpenCount
0x1400025f4  jmp     short loc_1400025D4
0x1400025f6  lea     rcx, g_MupAdvancedFcbHeader; AdvancedHeader
0x1400025fd  call    cs:__imp_FsRtlTeardownPerStreamContexts
0x140002604  nop     dword ptr [rax+rax+00h]
0x140002609  jmp     short loc_1400025D4
```
