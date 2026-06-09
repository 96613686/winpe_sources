# MIDL_user_free

- ea: `0x140009090`
- end: `0x1400090b3`
- name: `MIDL_user_free`
- size: `35`
- prototype: `void __stdcall(void *)`
- caller_count: `38`
- callee_count: `0`
- tags: ``

## callers

- `0x140009850`
- `0x14000a380`
- `0x14000a4f4`
- `0x14000b5d4`
- `0x14000bc74`
- `0x14000be64`
- `0x14000bf80`
- `0x14000c350`
- `0x14000f8bc`
- `0x14000faa8`
- `0x14000fea4`
- `0x14001211c`
- `0x140014828`
- `0x140014fd8`
- `0x1400160d8`
- `0x14001687c`
- `0x140016900`
- `0x140016c80`
- `0x140016d70`
- `0x140017000`
- `0x1400177a0`
- `0x140017880`
- `0x1400185d8`
- `0x140018634`
- `0x140018b30`
- `0x140018b78`
- `0x14001917c`
- `0x140019330`
- `0x140019410`
- `0x1400195e0`
- `0x140019840`
- `0x140019940`
- `0x140019e10`
- `0x140019f38`
- `0x14001a068`
- `0x14001a0e0`
- `0x14001a3a8`
- `0x14001a494`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400090ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009099`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009099`

## pseudocode

```c
void __stdcall MIDL_user_free(void *a1)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x140009090  push    rbx
0x140009092  sub     rsp, 20h
0x140009096  mov     rbx, rcx
0x140009099  call    cs:__imp_GetProcessHeap
0x14000909f  mov     r8, rbx
0x1400090a2  xor     edx, edx
0x1400090a4  mov     rcx, rax
0x1400090a7  add     rsp, 20h
0x1400090ab  pop     rbx
0x1400090ac  jmp     cs:__imp_HeapFree
```
