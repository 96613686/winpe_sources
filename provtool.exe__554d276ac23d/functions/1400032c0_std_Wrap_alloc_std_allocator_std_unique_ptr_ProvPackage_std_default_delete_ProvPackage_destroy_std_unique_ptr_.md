# std::_Wrap_alloc<std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>>::destroy<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>(std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>> *)

- ea: `0x1400032c0`
- end: `0x1400032e2`
- name: `??$destroy@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@?$_Wrap_alloc@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@std@@@std@@QEAAXPEAV?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@1@@Z`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000eb23`

## callees

- `0x1400032c0`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall std::_Wrap_alloc<std::allocator<std::unique_ptr<ProvPackage>>>::destroy<std::unique_ptr<ProvPackage>>(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax

  if ( *a2 )
    return (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a2 + 64LL))(*a2, 1);
  return result;
}

```

## disassembly

```asm
0x1400032c0  sub     rsp, 28h
0x1400032c4  mov     rcx, [rdx]
0x1400032c7  test    rcx, rcx
0x1400032ca  jz      short loc_1400032DD
0x1400032cc  mov     rax, [rcx]
0x1400032cf  mov     edx, 1
0x1400032d4  mov     rax, [rax+40h]
0x1400032d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032dd  add     rsp, 28h
0x1400032e1  retn
```
