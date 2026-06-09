# std::_Ref_count_base::_Decwref(void)

- ea: `0x180005b9c`
- end: `0x180005bbe`
- name: `?_Decwref@_Ref_count_base@std@@QEAAXXZ`
- size: `34`
- prototype: `void __fastcall(std::_Ref_count_base *__hidden this)`
- caller_count: `26`
- callee_count: `2`
- tags: ``

## callers

- `0x180003df4`
- `0x1800044f4`
- `0x1800045fc`
- `0x1800047ec`
- `0x180004940`
- `0x180005070`
- `0x1800051b0`
- `0x180005354`
- `0x1800056d0`
- `0x180005820`
- `0x180005cd0`
- `0x180005d50`
- `0x180005dd0`
- `0x180009610`
- `0x180009754`
- `0x180009860`
- `0x18000b2a4`
- `0x18000b544`
- `0x18000b8a4`
- `0x18000c834`
- `0x18000d3dc`
- `0x18001224c`
- `0x18001240c`
- `0x180012904`
- `0x180012b80`
- `0x180012ca0`

## callees

- `0x180005b9c`
- `0x180015010`

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
0x180005b9c  sub     rsp, 28h
0x180005ba0  or      eax, 0FFFFFFFFh
0x180005ba3  lock xadd [rcx+0Ch], eax
0x180005ba8  cmp     eax, 1
0x180005bab  jnz     short loc_180005BB9
0x180005bad  mov     rax, [rcx]
0x180005bb0  mov     rax, [rax+8]
0x180005bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bb9  add     rsp, 28h
0x180005bbd  retn
```
