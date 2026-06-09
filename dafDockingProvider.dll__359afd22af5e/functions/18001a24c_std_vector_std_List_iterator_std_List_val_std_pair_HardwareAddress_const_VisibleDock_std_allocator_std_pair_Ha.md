# std::vector<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>>,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>>>>::reserve(unsigned __int64)

- ea: `0x18001a24c`
- end: `0x18001a314`
- name: `?reserve@?$vector@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@2@@std@@QEAAX_K@Z`
- size: `200`
- prototype: `unsigned __int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800180ec`
- `0x18001884c`
- `0x180019be0`

## callees

- `0x180001484`
- `0x1800014d0`
- `0x1800020bd`
- `0x18001117c`
- `0x1800131f4`
- `0x1800180c4`
- `0x18001a24c`

## pseudocode

```c
unsigned __int64 __fastcall std::vector<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>::reserve(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 result; // rax
  __int64 v4; // r14
  _QWORD *v5; // rdi
  _QWORD *v6; // rax
  const char *v7; // rdx
  void *v8; // rcx
  __int64 v9; // rsi
  _BYTE pExceptionObject[72]; // [rsp+30h] [rbp-48h] BYREF
  _QWORD *v11; // [rsp+88h] [rbp+10h]

  if ( a2 > 0x1FFFFFFFFFFFFFFFLL )
    std::vector<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>::_Xlen();
  result = (__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3;
  if ( result < a2 )
  {
    v4 = a2;
    if ( a2 )
    {
      v6 = operator new(8 * a2);
      v5 = v6;
      v11 = v6;
      if ( !v6 )
      {
        std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, v7);
        throw (std::bad_alloc *)pExceptionObject;
      }
    }
    else
    {
      v5 = 0;
      v11 = 0;
    }
    try
    {
      std::_Uninit_move<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>(
        *(_QWORD **)a1,
        *(_QWORD **)(a1 + 8),
        v5);
      v8 = *(void **)a1;
      v9 = (__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 3;
      if ( *(_QWORD *)a1 )
        operator delete(v8);
      *(_QWORD *)(a1 + 16) = &v5[v4];
      result = (unsigned __int64)&v5[v9];
      *(_QWORD *)(a1 + 8) = result;
      *(_QWORD *)a1 = v5;
    }
    catch ( ... )
    {
      std::allocator<Dock>::deallocate(v8, v11);
      throw;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001a24c  push    rbx
0x18001a24e  push    rsi
0x18001a24f  push    rdi
0x18001a250  push    r14
0x18001a252  sub     rsp, 58h
0x18001a256  mov     rbx, rcx
0x18001a259  mov     rax, 1FFFFFFFFFFFFFFFh
0x18001a263  cmp     rdx, rax
0x18001a266  ja      loc_18001A30E
0x18001a26c  mov     rax, [rcx+10h]
0x18001a270  sub     rax, [rcx]
0x18001a273  sar     rax, 3
0x18001a277  cmp     rax, rdx
0x18001a27a  jnb     short loc_18001A2E8
0x18001a27c  lea     r14, ds:0[rdx*8]
0x18001a284  test    rdx, rdx
0x18001a287  jnz     short loc_18001A295
0x18001a289  xor     edi, edi
0x18001a28b  mov     [rsp+78h+arg_8], rdi
0x18001a293  jmp     short loc_18001A2AD
0x18001a295  mov     rcx, r14; Size
0x18001a298  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a29d  mov     rdi, rax
0x18001a2a0  mov     [rsp+78h+arg_8], rax
0x18001a2a8  test    rax, rax
0x18001a2ab  jz      short loc_18001A2F2
0x18001a2ad  mov     r8, rdi
0x18001a2b0  mov     rdx, [rbx+8]
0x18001a2b4  mov     rcx, [rbx]
0x18001a2b7  call    ??$_Uninit_move@PEAV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@PEAV12@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@2@V12@@std@@YAPEAV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@0@PEAV10@00AEAV?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>(std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>> &,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_Nonscalar_ptr_iterator_tag)
0x18001a2bc  nop
0x18001a2bd  mov     rcx, [rbx]; Block
0x18001a2c0  mov     rsi, [rbx+8]
0x18001a2c4  sub     rsi, rcx
0x18001a2c7  sar     rsi, 3
0x18001a2cb  test    rcx, rcx
0x18001a2ce  jz      short loc_18001A2D5
0x18001a2d0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a2d5  lea     rax, [r14+rdi]
0x18001a2d9  mov     [rbx+10h], rax
0x18001a2dd  lea     rax, [rdi+rsi*8]
0x18001a2e1  mov     [rbx+8], rax
0x18001a2e5  mov     [rbx], rdi
0x18001a2e8  add     rsp, 58h
0x18001a2ec  pop     r14
0x18001a2ee  pop     rdi
0x18001a2ef  pop     rsi
0x18001a2f0  pop     rbx
0x18001a2f1  retn
0x18001a2f2  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18001a2f7  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x18001a2fc  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001a303  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18001a308  call    _CxxThrowException_0
0x18001a30e  call    ?_Xlen@?$vector@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@2@@std@@IEBAXXZ; std::vector<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>::_Xlen(void)
```
