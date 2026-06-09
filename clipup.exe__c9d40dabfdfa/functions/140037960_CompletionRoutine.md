# CompletionRoutine

- ea: `0x140037960`
- end: `0x14003798f`
- name: `CompletionRoutine`
- size: `47`
- prototype: `void __stdcall(DWORD dwErrorCode, DWORD dwNumberOfBytesTransfered, LPOVERLAPPED lpOverlapped)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000b94c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003796d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003796d`

## pseudocode

```c
void __fastcall CompletionRoutine(DWORD dwErrorCode, DWORD dwNumberOfBytesTransfered, LPOVERLAPPED lpOverlapped)
{
  CloseHandle(lpOverlapped->hEvent);
  sub_14000B94C(lpOverlapped[1].Internal);
  sub_14000B94C(lpOverlapped);
}

```

## disassembly

```asm
0x140037960  push    rbx
0x140037962  sub     rsp, 20h
0x140037966  mov     rcx, [r8+18h]; hObject
0x14003796a  mov     rbx, r8
0x14003796d  call    cs:CloseHandle
0x140037974  nop     dword ptr [rax+rax+00h]
0x140037979  mov     rcx, [rbx+20h]
0x14003797d  call    sub_14000B94C
0x140037982  mov     rcx, rbx
0x140037985  add     rsp, 20h
0x140037989  pop     rbx
0x14003798a  jmp     sub_14000B94C
```
