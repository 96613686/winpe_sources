# ClRtlDeleteQueue

- ea: `0x18009e1f8`
- end: `0x18009e232`
- name: `ClRtlDeleteQueue`
- size: `58`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002e04c`
- `0x18005c424`

## callees

- `0x180003c14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009e205`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009e205`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e20f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e219`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e20f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e219`

## pseudocode

```c
void *__fastcall ClRtlDeleteQueue(char *a1)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  CloseHandle(*((HANDLE *)a1 + 7));
  CloseHandle(*((HANDLE *)a1 + 9));
  return memset_0(a1, 0, 0x50u);
}

```

## disassembly

```asm
0x18009e1f8  push    rbx
0x18009e1fa  sub     rsp, 20h
0x18009e1fe  mov     rbx, rcx
0x18009e201  add     rcx, 10h; lpCriticalSection
0x18009e205  call    cs:__imp_DeleteCriticalSection
0x18009e20b  mov     rcx, [rbx+38h]; hObject
0x18009e20f  call    cs:__imp_CloseHandle
0x18009e215  mov     rcx, [rbx+48h]; hObject
0x18009e219  call    cs:__imp_CloseHandle
0x18009e21f  xor     edx, edx; Val
0x18009e221  mov     rcx, rbx; void *
0x18009e224  lea     r8d, [rdx+50h]; Size
0x18009e228  add     rsp, 20h
0x18009e22c  pop     rbx
0x18009e22d  jmp     memset_0
```
