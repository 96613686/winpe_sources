# _ResourceStringAllocCopyExCoAlloc

- ea: `0x14001cc38`
- end: `0x14001cc61`
- name: `_ResourceStringAllocCopyExCoAlloc`
- size: `41`
- prototype: `__int64 __fastcall(__int64, SIZE_T, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001cb38`

## callees

- `0x14001cc38`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001cc44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001cc44`

## pseudocode

```c
__int64 __fastcall ResourceStringAllocCopyExCoAlloc(__int64 a1, SIZE_T a2, _QWORD *a3)
{
  LPVOID v4; // rax

  v4 = CoTaskMemAlloc(a2);
  if ( !v4 )
    return 2147942414LL;
  *a3 = v4;
  return 0;
}

```

## disassembly

```asm
0x14001cc38  push    rbx
0x14001cc3a  sub     rsp, 20h
0x14001cc3e  mov     rcx, rdx; cb
0x14001cc41  mov     rbx, r8
0x14001cc44  call    cs:__imp_CoTaskMemAlloc
0x14001cc4a  test    rax, rax
0x14001cc4d  jz      short loc_14001CC56
0x14001cc4f  mov     [rbx], rax
0x14001cc52  xor     eax, eax
0x14001cc54  jmp     short loc_14001CC5B
0x14001cc56  mov     eax, 8007000Eh
0x14001cc5b  add     rsp, 20h
0x14001cc5f  pop     rbx
0x14001cc60  retn
```
