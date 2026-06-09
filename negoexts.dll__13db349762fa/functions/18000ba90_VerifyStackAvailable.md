# VerifyStackAvailable

- ea: `0x18000ba90`
- end: `0x18000bab2`
- name: `VerifyStackAvailable`
- size: `34`
- prototype: `__int64(void)`
- caller_count: `13`
- callee_count: `3`
- tags: ``

## callers

- `0x180001414`
- `0x180004404`
- `0x180005bc0`
- `0x180006a48`
- `0x1800070d0`
- `0x180008e60`
- `0x18000bf1c`
- `0x18000d388`
- `0x18000ef54`
- `0x180016f70`
- `0x180017b60`
- `0x18001a3b4`
- `0x18001bba4`

## callees

- `0x18000ba90`
- `0x18000bab8`
- `0x18001e9ec`

## pseudocode

```c
__int64 VerifyStackAvailable()
{
  InternalVerifyStackAvailable();
  return 1;
}

```

## disassembly

```asm
0x18000ba90  push    rbx
0x18000ba92  sub     rsp, 20h
0x18000ba96  mov     ebx, 1
0x18000ba9b  call    InternalVerifyStackAvailable
0x18000baa0  jmp     short loc_18000BAAA
0x18000baa2  xor     ebx, ebx
0x18000baa4  call    _resetstkoflw_static
0x18000baa9  nop
0x18000baaa  mov     eax, ebx
0x18000baac  add     rsp, 20h
0x18000bab0  pop     rbx
0x18000bab1  retn
0x18001ef62  push    rbp
0x18001ef64  sub     rsp, 20h
0x18001ef68  mov     rbp, rdx
0x18001ef6b  mov     rax, [rcx]
0x18001ef6e  xor     ecx, ecx
0x18001ef70  cmp     dword ptr [rax], 0C00000FDh
0x18001ef76  setz    cl
0x18001ef79  mov     eax, ecx
0x18001ef7b  add     rsp, 20h
0x18001ef7f  pop     rbp
0x18001ef80  retn
```
