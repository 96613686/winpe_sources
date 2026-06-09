# std::_Ref_count_base::_Decwref(void)

- ea: `0x180007e94`
- end: `0x180007eb6`
- name: `?_Decwref@_Ref_count_base@std@@QEAAXXZ`
- size: `34`
- prototype: `void __fastcall(std::_Ref_count_base *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000195c`
- `0x180007870`
- `0x1800079ac`
- `0x180009700`
- `0x180009750`

## callees

- `0x180007e94`
- `0x18000a010`

## pseudocode

```c
void __fastcall std::_Ref_count_base::_Decwref(std::_Ref_count_base *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 3, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)this + 8LL))(this);
}

```

## disassembly

```asm
0x180007e94  sub     rsp, 28h
0x180007e98  or      eax, 0FFFFFFFFh
0x180007e9b  lock xadd [rcx+0Ch], eax
0x180007ea0  cmp     eax, 1
0x180007ea3  jnz     short loc_180007EB1
0x180007ea5  mov     rax, [rcx]
0x180007ea8  mov     rax, [rax+8]
0x180007eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eb1  add     rsp, 28h
0x180007eb5  retn
```
