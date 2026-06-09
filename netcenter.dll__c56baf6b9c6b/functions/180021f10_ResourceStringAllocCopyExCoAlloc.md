# _ResourceStringAllocCopyExCoAlloc

- ea: `0x180021f10`
- end: `0x180021f39`
- name: `_ResourceStringAllocCopyExCoAlloc`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180021f10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021f1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021f1c`

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
0x180021f10  push    rbx
0x180021f12  sub     rsp, 20h
0x180021f16  mov     rcx, rdx; cb
0x180021f19  mov     rbx, r8
0x180021f1c  call    cs:__imp_CoTaskMemAlloc
0x180021f22  test    rax, rax
0x180021f25  jz      short loc_180021F2E
0x180021f27  mov     [rbx], rax
0x180021f2a  xor     eax, eax
0x180021f2c  jmp     short loc_180021F33
0x180021f2e  mov     eax, 8007000Eh
0x180021f33  add     rsp, 20h
0x180021f37  pop     rbx
0x180021f38  retn
```
