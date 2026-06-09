# std::unique_ptr<_VM_PERF_COUNTERSET_INSTANCE,std::default_delete<_VM_PERF_COUNTERSET_INSTANCE>>::~unique_ptr<_VM_PERF_COUNTERSET_INSTANCE,std::default_delete<_VM_PERF_COUNTERSET_INSTANCE>>(void)

- ea: `0x180007048`
- end: `0x18000705e`
- name: `??1?$unique_ptr@U_VM_PERF_COUNTERSET_INSTANCE@@U?$default_delete@U_VM_PERF_COUNTERSET_INSTANCE@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180006da8`
- `0x180007110`
- `0x18000956e`
- `0x1800095fc`

## callees

- `0x180007048`
- `0x180007268`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<_VM_PERF_COUNTERSET_INSTANCE>::~unique_ptr<_VM_PERF_COUNTERSET_INSTANCE>(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return std::default_delete<_VM_PERF_COUNTERSET_INSTANCE>::operator()();
  return result;
}

```

## disassembly

```asm
0x180007048  sub     rsp, 28h
0x18000704c  mov     rdx, [rcx]
0x18000704f  test    rdx, rdx
0x180007052  jz      short loc_180007059
0x180007054  call    ??R?$default_delete@U_VM_PERF_COUNTERSET_INSTANCE@@@std@@QEBAXPEAU_VM_PERF_COUNTERSET_INSTANCE@@@Z; std::default_delete<_VM_PERF_COUNTERSET_INSTANCE>::operator()(_VM_PERF_COUNTERSET_INSTANCE *)
0x180007059  add     rsp, 28h
0x18000705d  retn
```
