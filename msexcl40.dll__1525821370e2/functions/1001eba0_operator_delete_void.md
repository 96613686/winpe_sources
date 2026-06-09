# operator delete(void *)

- ea: `0x1001eba0`
- end: `0x1001ebdb`
- name: `??3@YAXPAX@Z`
- size: `59`
- prototype: `void __cdecl(void *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x100358c5`
- `0x100358db`
- `0x10035900`

## callees

- `0x10025ab7`
- `0x10035510`
- `0x10035e9f`

## pseudocode

```c
void __cdecl operator delete(_DWORD *a1)
{
  MemFree(a1);
}

```

## disassembly

```asm
0x1001eba0  mov     edi, edi
0x1001eba2  push    ebp
0x1001eba3  mov     ebp, esp
0x1001eba5  push    0FFFFFFFFh
0x1001eba7  push    offset ??3@YAXPAX@Z_SEH
0x1001ebac  mov     eax, large fs:0
0x1001ebb2  push    eax
0x1001ebb3  mov     eax, ___security_cookie
0x1001ebb8  xor     eax, ebp
0x1001ebba  push    eax
0x1001ebbb  lea     eax, [ebp+var_C]
0x1001ebbe  mov     large fs:0, eax
0x1001ebc4  mov     ecx, [ebp+arg_0]
0x1001ebc7  call    _MemFree@4; MemFree(x)
0x1001ebcc  mov     ecx, [ebp+var_C]
0x1001ebcf  mov     large fs:0, ecx
0x1001ebd6  pop     ecx
0x1001ebd7  mov     esp, ebp
0x1001ebd9  pop     ebp
0x1001ebda  retn
0x100366c0  nop
0x100366c1  nop
0x100366c2  mov     edx, [esp-4+arg_4]
0x100366c6  lea     eax, [edx+0Ch]
0x100366c9  mov     ecx, [edx-4]
0x100366cc  xor     ecx, eax; StackCookie
0x100366ce  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100366d3  mov     eax, offset stru_10036C50
0x100366d8  jmp     ___CxxFrameHandler3
```
