# std::unique_ptr<std::_Facet_base,std::default_delete<std::_Facet_base>>::~unique_ptr<std::_Facet_base,std::default_delete<std::_Facet_base>>(void)

- ea: `0x140005d70`
- end: `0x140005d91`
- name: `??1?$unique_ptr@V_Facet_base@std@@U?$default_delete@V_Facet_base@std@@@2@@std@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64))`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140005138`
- `0x140011c70`
- `0x1400142a0`
- `0x1400185ea`

## callees

- `0x140005d70`
- `0x14001a010`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(
        __int64 (__fastcall ****a1)(_QWORD, __int64))
{
  __int64 (__fastcall ***v1)(_QWORD, __int64); // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (**v1)(v1, 1);
  return result;
}

```

## disassembly

```asm
0x140005d70  sub     rsp, 28h
0x140005d74  mov     rcx, [rcx]
0x140005d77  test    rcx, rcx
0x140005d7a  jz      short loc_140005D8C
0x140005d7c  mov     rax, [rcx]
0x140005d7f  mov     edx, 1
0x140005d84  mov     rax, [rax]
0x140005d87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d8c  add     rsp, 28h
0x140005d90  retn
```
