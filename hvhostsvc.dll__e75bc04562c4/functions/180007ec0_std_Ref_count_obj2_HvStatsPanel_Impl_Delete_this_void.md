# std::_Ref_count_obj2<HvStatsPanel::Impl>::_Delete_this(void)

- ea: `0x180007ec0`
- end: `0x180007edf`
- name: `?_Delete_this@?$_Ref_count_obj2@VImpl@HvStatsPanel@@@std@@EEAAXXZ`
- size: `31`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007ec0`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_obj2<HvStatsPanel::Impl>::_Delete_this(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, 1);
  return result;
}

```

## disassembly

```asm
0x180007ec0  sub     rsp, 28h
0x180007ec4  test    rcx, rcx
0x180007ec7  jz      short loc_180007EDA
0x180007ec9  mov     rax, [rcx]
0x180007ecc  mov     edx, 1
0x180007ed1  mov     rax, [rax+10h]
0x180007ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eda  add     rsp, 28h
0x180007ede  retn
```
