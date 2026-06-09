# _ResourceStringAllocCopyExCoAlloc

- ea: `0x18002dac4`
- end: `0x18002daed`
- name: `_ResourceStringAllocCopyExCoAlloc`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002d9c4`

## callees

- `0x18002dac4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002dad0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002dad0`

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
0x18002dac4  push    rbx
0x18002dac6  sub     rsp, 20h
0x18002daca  mov     rcx, rdx; cb
0x18002dacd  mov     rbx, r8
0x18002dad0  call    cs:__imp_CoTaskMemAlloc
0x18002dad6  test    rax, rax
0x18002dad9  jz      short loc_18002DAE2
0x18002dadb  mov     [rbx], rax
0x18002dade  xor     eax, eax
0x18002dae0  jmp     short loc_18002DAE7
0x18002dae2  mov     eax, 8007000Eh
0x18002dae7  add     rsp, 20h
0x18002daeb  pop     rbx
0x18002daec  retn
```
