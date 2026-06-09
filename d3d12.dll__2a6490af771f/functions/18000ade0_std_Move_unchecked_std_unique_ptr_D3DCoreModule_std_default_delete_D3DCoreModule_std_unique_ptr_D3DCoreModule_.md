# std::_Move_unchecked<std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>> *,std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>> *>(std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>> *,std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>> *,std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>> *)

- ea: `0x18000ade0`
- end: `0x18000ae28`
- name: `??$_Move_unchecked@PEAV?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@PEAV12@@std@@YAPEAV?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@0@PEAV10@00@Z`
- size: `72`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ad90`
- `0x18000fde0`

## callees

- `0x18000ade0`
- `0x18000f574`

## pseudocode

```c
D3DCoreModule **__fastcall std::_Move_unchecked<std::unique_ptr<D3DCoreModule> *,std::unique_ptr<D3DCoreModule> *>(
        D3DCoreModule **a1,
        D3DCoreModule **a2,
        D3DCoreModule **a3)
{
  D3DCoreModule **i; // rdi

  for ( i = a1; i != a2; ++i )
    std::unique_ptr<D3DCoreModule>::operator=<std::default_delete<D3DCoreModule>,0>(a3++, i);
  return a3;
}

```

## disassembly

```asm
0x18000ade0  mov     [rsp+arg_0], rbx
0x18000ade5  mov     [rsp+arg_8], rsi
0x18000adea  push    rdi
0x18000adeb  sub     rsp, 20h
0x18000adef  mov     rbx, r8
0x18000adf2  mov     rsi, rdx
0x18000adf5  mov     rdi, rcx
0x18000adf8  cmp     rcx, rdx
0x18000adfb  jz      short loc_18000AE15
0x18000adfd  mov     rdx, rdi
0x18000ae00  mov     rcx, rbx
0x18000ae03  call    ??$?4U?$default_delete@VD3DCoreModule@@@std@@$0A@@?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z
0x18000ae08  add     rbx, 8
0x18000ae0c  add     rdi, 8
0x18000ae10  cmp     rdi, rsi
0x18000ae13  jnz     short loc_18000ADFD
0x18000ae15  mov     rsi, [rsp+28h+arg_8]
0x18000ae1a  mov     rax, rbx
0x18000ae1d  mov     rbx, [rsp+28h+arg_0]
0x18000ae22  add     rsp, 20h
0x18000ae26  pop     rdi
0x18000ae27  retn
```
