# std::_Destroy_range<std::allocator<std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>>>>(std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>> *,std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>> * const,std::allocator<std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>>> &)

- ea: `0x1800070a8`
- end: `0x1800070e0`
- name: `??$_Destroy_range@V?$allocator@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@@0@@Z`
- size: `56`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180005e14`
- `0x180006674`
- `0x1800072cc`
- `0x18000fbfc`
- `0x18000fde0`

## callees

- `0x180005de4`
- `0x1800070a8`

## pseudocode

```c
__int64 __fastcall std::_Destroy_range<std::allocator<std::unique_ptr<D3DCoreModule>>>(_QWORD *a1, _QWORD *a2)
{
  _QWORD *v3; // rbx
  __int64 result; // rax

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      if ( *v3 )
        result = std::default_delete<D3DCoreModule>::operator()();
      ++v3;
    }
    while ( v3 != a2 );
  }
  return result;
}

```

## disassembly

```asm
0x1800070a8  cmp     rcx, rdx
0x1800070ab  jz      short locret_1800070D8
0x1800070ad  mov     [rsp+arg_0], rbx
0x1800070b2  push    rdi
0x1800070b3  sub     rsp, 20h
0x1800070b7  mov     rdi, rdx
0x1800070ba  mov     rbx, rcx
0x1800070bd  mov     rdx, [rbx]
0x1800070c0  test    rdx, rdx
0x1800070c3  jnz     short loc_1800070D9
0x1800070c5  add     rbx, 8
0x1800070c9  cmp     rbx, rdi
0x1800070cc  jnz     short loc_1800070BD
0x1800070ce  mov     rbx, [rsp+28h+arg_0]
0x1800070d3  add     rsp, 20h
0x1800070d7  pop     rdi
0x1800070d8  retn
0x1800070d9  call    ??R?$default_delete@VD3DCoreModule@@@std@@QEBAXPEAVD3DCoreModule@@@Z; std::default_delete<D3DCoreModule>::operator()(D3DCoreModule *)
0x1800070de  jmp     short loc_1800070C5
```
