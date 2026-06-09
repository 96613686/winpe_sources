# WfpMemFree

- ea: `0x18000eed4`
- end: `0x18000ef24`
- name: `WfpMemFree`
- size: `80`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180008b74`
- `0x18000bc38`
- `0x18000ca08`
- `0x180010a00`

## callees

- `0x18000eed4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eefd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eefd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ef0b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ef0b`

## pseudocode

```c
void __fastcall WfpMemFree(void **a1)
{
  void *v1; // rbx
  HANDLE ProcessHeap; // rax

  v1 = *a1;
  if ( *a1 && v1 != (void *)0xBADBADFABADBADFALL )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
  *a1 = (void *)0xBADBADFABADBADFALL;
}

```

## disassembly

```asm
0x18000eed4  mov     [rsp+arg_0], rbx
0x18000eed9  mov     [rsp+arg_8], rsi
0x18000eede  push    rdi
0x18000eedf  sub     rsp, 20h
0x18000eee3  mov     rbx, [rcx]
0x18000eee6  mov     rdi, rcx
0x18000eee9  mov     rsi, 0BADBADFABADBADFAh
0x18000eef3  test    rbx, rbx
0x18000eef6  jz      short loc_18000EF11
0x18000eef8  cmp     rbx, rsi
0x18000eefb  jz      short loc_18000EF11
0x18000eefd  call    cs:__imp_GetProcessHeap
0x18000ef03  mov     r8, rbx; lpMem
0x18000ef06  xor     edx, edx; dwFlags
0x18000ef08  mov     rcx, rax; hHeap
0x18000ef0b  call    cs:__imp_HeapFree
0x18000ef11  mov     rbx, [rsp+28h+arg_0]
0x18000ef16  mov     [rdi], rsi
0x18000ef19  mov     rsi, [rsp+28h+arg_8]
0x18000ef1e  add     rsp, 20h
0x18000ef22  pop     rdi
0x18000ef23  retn
```
