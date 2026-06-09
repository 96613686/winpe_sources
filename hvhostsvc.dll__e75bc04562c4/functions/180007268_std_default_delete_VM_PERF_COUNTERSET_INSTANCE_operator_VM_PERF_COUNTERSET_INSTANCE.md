# std::default_delete<_VM_PERF_COUNTERSET_INSTANCE>::operator()(_VM_PERF_COUNTERSET_INSTANCE *)

- ea: `0x180007268`
- end: `0x180007291`
- name: `??R?$default_delete@U_VM_PERF_COUNTERSET_INSTANCE@@@std@@QEBAXPEAU_VM_PERF_COUNTERSET_INSTANCE@@@Z`
- size: `41`
- prototype: `void __fastcall(__int64, char *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180006da8`
- `0x180007048`
- `0x180007110`

## callees

- `0x1800024d0`
- `0x180007268`
- `0x180007fd4`

## pseudocode

```c
void __fastcall std::default_delete<_VM_PERF_COUNTERSET_INSTANCE>::operator()(__int64 a1, char *a2)
{
  if ( a2 )
  {
    std::wstring::_Tidy_deallocate(a2 + 8);
    operator delete(a2, (const struct std::nothrow_t *)0x30);
  }
}

```

## disassembly

```asm
0x180007268  test    rdx, rdx
0x18000726b  jz      short locret_180007290
0x18000726d  push    rbx
0x18000726e  sub     rsp, 20h
0x180007272  lea     rcx, [rdx+8]
0x180007276  mov     rbx, rdx
0x180007279  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000727e  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x180007283  mov     rcx, rbx; void *
0x180007286  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000728b  add     rsp, 20h
0x18000728f  pop     rbx
0x180007290  retn
```
