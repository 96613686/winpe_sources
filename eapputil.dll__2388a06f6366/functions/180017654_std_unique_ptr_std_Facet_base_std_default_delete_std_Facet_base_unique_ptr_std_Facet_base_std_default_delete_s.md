# std::unique_ptr<std::_Facet_base,std::default_delete<std::_Facet_base>>::~unique_ptr<std::_Facet_base,std::default_delete<std::_Facet_base>>(void)

- ea: `0x180017654`
- end: `0x180017675`
- name: `??1?$unique_ptr@V_Facet_base@std@@U?$default_delete@V_Facet_base@std@@@2@@std@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64))`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800320cd`
- `0x1800320df`

## callees

- `0x180017654`
- `0x180033010`

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
0x180017654  sub     rsp, 28h
0x180017658  mov     rcx, [rcx]
0x18001765b  test    rcx, rcx
0x18001765e  jz      short loc_180017670
0x180017660  mov     rax, [rcx]
0x180017663  mov     edx, 1
0x180017668  mov     rax, [rax]
0x18001766b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017670  add     rsp, 28h
0x180017674  retn
```
