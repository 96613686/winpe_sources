# InetDeleteResource

- ea: `0x180021db0`
- end: `0x180021df8`
- name: `InetDeleteResource`
- size: `72`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ac50`

## callees

- `0x18002e52e`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021db9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021db9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021dc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021dd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021dc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021dd9`

## pseudocode

```c
void *__fastcall InetDeleteResource(struct _RTL_CRITICAL_SECTION *a1)
{
  DeleteCriticalSection(a1);
  CloseHandle(a1[1].DebugInfo);
  CloseHandle(a1[1].OwningThread);
  return memset_0(a1, 0, 0x60u);
}

```

## disassembly

```asm
0x180021db0  push    rbx
0x180021db2  sub     rsp, 20h
0x180021db6  mov     rbx, rcx
0x180021db9  call    cs:__imp_DeleteCriticalSection
0x180021dc0  nop     dword ptr [rax+rax+00h]
0x180021dc5  mov     rcx, [rbx+28h]; hObject
0x180021dc9  call    cs:__imp_CloseHandle
0x180021dd0  nop     dword ptr [rax+rax+00h]
0x180021dd5  mov     rcx, [rbx+38h]; hObject
0x180021dd9  call    cs:__imp_CloseHandle
0x180021de0  nop     dword ptr [rax+rax+00h]
0x180021de5  xor     edx, edx; Val
0x180021de7  mov     rcx, rbx; void *
0x180021dea  lea     r8d, [rdx+60h]; Size
0x180021dee  add     rsp, 20h
0x180021df2  pop     rbx
0x180021df3  jmp     memset_0
```
