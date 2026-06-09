# _VmPerfCreateInstance_::_1_::dtor$2

- ea: `0x1800095fc`
- end: `0x180009622`
- name: `_VmPerfCreateInstance_::_1_::dtor$2`
- size: `38`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007048`
- `0x1800095fc`

## pseudocode

```c
__int64 __fastcall VmPerfCreateInstance_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 48) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    return std::unique_ptr<_VM_PERF_COUNTERSET_INSTANCE>::~unique_ptr<_VM_PERF_COUNTERSET_INSTANCE>(*(_QWORD **)(a2 + 56));
  }
  return result;
}

```

## disassembly

```asm
0x1800095fc  push    rbp
0x1800095fe  sub     rsp, 20h
0x180009602  mov     rbp, rdx
0x180009605  mov     eax, [rbp+30h]
0x180009608  and     eax, 1
0x18000960b  test    eax, eax
0x18000960d  jz      short loc_18000961C
0x18000960f  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x180009613  mov     rcx, [rbp+38h]
0x180009617  call    ??1?$unique_ptr@U_VM_PERF_COUNTERSET_INSTANCE@@U?$default_delete@U_VM_PERF_COUNTERSET_INSTANCE@@@std@@@std@@QEAA@XZ; std::unique_ptr<_VM_PERF_COUNTERSET_INSTANCE>::~unique_ptr<_VM_PERF_COUNTERSET_INSTANCE>(void)
0x18000961c  add     rsp, 20h
0x180009620  pop     rbp
0x180009621  retn
```
