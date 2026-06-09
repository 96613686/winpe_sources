# std::vector<std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>>,std::allocator<std::unique_ptr<D3DCoreModule,std::default_delete<D3DCoreModule>>>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x18000fbfc`
- end: `0x18000fc30`
- name: `??1_Reallocation_guard@?$vector@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@V?$allocator@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800072cc`

## callees

- `0x180006e2c`
- `0x1800070a8`
- `0x18000fbfc`

## pseudocode

```c
__int64 __fastcall std::vector<std::unique_ptr<D3DCoreModule>>::_Reallocation_guard::~_Reallocation_guard(__int64 a1)
{
  __int64 result; // rax

  if ( *(_QWORD *)(a1 + 8) )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<D3DCoreModule>>>(*(_QWORD **)(a1 + 24), *(_QWORD **)(a1 + 32));
    return std::_Deallocate<16>(*(_QWORD *)(a1 + 8), 8LL * *(_QWORD *)(a1 + 16));
  }
  return result;
}

```

## disassembly

```asm
0x18000fbfc  push    rbx
0x18000fbfe  sub     rsp, 20h
0x18000fc02  cmp     qword ptr [rcx+8], 0
0x18000fc07  mov     rbx, rcx
0x18000fc0a  jz      short loc_18000FC2A
0x18000fc0c  mov     rdx, [rcx+20h]
0x18000fc10  mov     rcx, [rcx+18h]
0x18000fc14  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VD3DCoreModule@@U?$default_delete@VD3DCoreModule@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<D3DCoreModule>>>(std::unique_ptr<D3DCoreModule> *,std::unique_ptr<D3DCoreModule> * const,std::allocator<std::unique_ptr<D3DCoreModule>> &)
0x18000fc19  mov     rdx, [rbx+10h]
0x18000fc1d  mov     rcx, [rbx+8]
0x18000fc21  shl     rdx, 3
0x18000fc25  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000fc2a  add     rsp, 20h
0x18000fc2e  pop     rbx
0x18000fc2f  retn
```
