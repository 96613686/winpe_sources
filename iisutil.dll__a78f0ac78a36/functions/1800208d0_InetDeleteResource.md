# InetDeleteResource

- ea: `0x1800208d0`
- end: `0x180020906`
- name: `InetDeleteResource`
- size: `54`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180019dc0`

## callees

- `0x18002c48e`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800208d9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800208d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800208e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800208ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800208e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800208ed`

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
0x1800208d0  push    rbx
0x1800208d2  sub     rsp, 20h
0x1800208d6  mov     rbx, rcx
0x1800208d9  call    cs:__imp_DeleteCriticalSection
0x1800208df  mov     rcx, [rbx+28h]; hObject
0x1800208e3  call    cs:__imp_CloseHandle
0x1800208e9  mov     rcx, [rbx+38h]; hObject
0x1800208ed  call    cs:__imp_CloseHandle
0x1800208f3  xor     edx, edx; Val
0x1800208f5  mov     rcx, rbx; void *
0x1800208f8  lea     r8d, [rdx+60h]; Size
0x1800208fc  add     rsp, 20h
0x180020900  pop     rbx
0x180020901  jmp     memset_0
```
