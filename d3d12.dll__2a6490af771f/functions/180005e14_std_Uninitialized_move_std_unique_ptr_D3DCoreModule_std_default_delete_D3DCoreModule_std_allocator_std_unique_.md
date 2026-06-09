# std::_Uninitialized_move<std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>> *,std::allocator<std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>>>>(std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>> * const,std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>> * const,std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>> *,std::allocator<std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>>> &)

- ea: `0x180005e14`
- end: `0x180005e4d`
- name: `??$_Uninitialized_move@PEAV?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@V?$allocator@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@@0@@Z`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800072cc`

## callees

- `0x180005e14`
- `0x1800070a8`

## pseudocode

```c
_QWORD *__fastcall std::_Uninitialized_move<std::unique_ptr<D3DCoreModule> *,std::allocator<std::unique_ptr<D3DCoreModule>>>(
        __int64 *a1,
        __int64 *a2,
        _QWORD *a3)
{
  __int64 v4; // r8

  while ( a1 != a2 )
  {
    v4 = *a1;
    *a1 = 0;
    *a3++ = v4;
    ++a1;
  }
  std::_Destroy_range<std::allocator<std::unique_ptr<D3DCoreModule>>>(a3, a3);
  return a3;
}

```

## disassembly

```asm
0x180005e14  push    rbx
0x180005e16  sub     rsp, 20h
0x180005e1a  mov     rbx, r8
0x180005e1d  jmp     short loc_180005E34
0x180005e1f  mov     r8, [rcx]
0x180005e22  mov     qword ptr [rcx], 0
0x180005e29  mov     [rbx], r8
0x180005e2c  add     rbx, 8
0x180005e30  add     rcx, 8
0x180005e34  cmp     rcx, rdx
0x180005e37  jnz     short loc_180005E1F
0x180005e39  mov     rdx, rbx
0x180005e3c  mov     rcx, rbx
0x180005e3f  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<D3DCoreModule>>>(std::unique_ptr<D3DCoreModule> *,std::unique_ptr<D3DCoreModule> * const,std::allocator<std::unique_ptr<D3DCoreModule>> &)
0x180005e44  mov     rax, rbx
0x180005e47  add     rsp, 20h
0x180005e4b  pop     rbx
0x180005e4c  retn
```
