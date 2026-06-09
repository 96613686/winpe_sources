# std::vector<std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>>,std::allocator<std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>>>>::vector<std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>>,std::allocator<std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>>>>(void)

- ea: `0x180006ea4`
- end: `0x180006eb5`
- name: `??0?$vector@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@V?$allocator@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `17`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180006cac`
- `0x18000a650`
- `0x18000a740`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::unique_ptr<D3DCoreModule>>::vector<std::unique_ptr<D3DCoreModule>>(_QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  return a1;
}

```

## disassembly

```asm
0x180006ea4  xor     eax, eax
0x180006ea6  mov     [rcx], rax
0x180006ea9  mov     [rcx+8], rax
0x180006ead  mov     [rcx+10h], rax
0x180006eb1  mov     rax, rcx
0x180006eb4  retn
```
