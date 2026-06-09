# std::unique_ptr<std::_Facet_base,std::default_delete<std::_Facet_base>>::~unique_ptr<std::_Facet_base,std::default_delete<std::_Facet_base>>(void)

- ea: `0x14000e980`
- end: `0x14000e9a1`
- name: `??1?$unique_ptr@V_Facet_base@std@@U?$default_delete@V_Facet_base@std@@@2@@std@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400134f7`

## callees

- `0x14000e980`
- `0x140014010`

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
0x14000e980  sub     rsp, 28h
0x14000e984  mov     rcx, [rcx]
0x14000e987  test    rcx, rcx
0x14000e98a  jz      short loc_14000E99C
0x14000e98c  mov     rax, [rcx]
0x14000e98f  mov     edx, 1
0x14000e994  mov     rax, [rax]
0x14000e997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e99c  add     rsp, 28h
0x14000e9a0  retn
```
