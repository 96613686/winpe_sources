# std::unique_ptr<std::_Facet_base,std::default_delete<std::_Facet_base>>::~unique_ptr<std::_Facet_base,std::default_delete<std::_Facet_base>>(void)

- ea: `0x1400065ac`
- end: `0x1400065cd`
- name: `??1?$unique_ptr@V_Facet_base@std@@U?$default_delete@V_Facet_base@std@@@2@@std@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64))`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001157e`

## callees

- `0x1400065ac`
- `0x140012010`

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
0x1400065ac  sub     rsp, 28h
0x1400065b0  mov     rcx, [rcx]
0x1400065b3  test    rcx, rcx
0x1400065b6  jz      short loc_1400065C8
0x1400065b8  mov     rax, [rcx]
0x1400065bb  mov     edx, 1
0x1400065c0  mov     rax, [rax]
0x1400065c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400065c8  add     rsp, 28h
0x1400065cc  retn
```
