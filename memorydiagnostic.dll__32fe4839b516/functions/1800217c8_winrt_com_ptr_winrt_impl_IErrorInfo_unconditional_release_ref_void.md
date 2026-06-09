# winrt::com_ptr<winrt::impl::IErrorInfo>::unconditional_release_ref(void)

- ea: `0x1800217c8`
- end: `0x1800217de`
- name: `?unconditional_release_ref@?$com_ptr@UIErrorInfo@impl@winrt@@@winrt@@AEAAXXZ`
- size: `22`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180023188`
- `0x180023262`
- `0x1800234bf`

## callees

- `0x180024010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::IErrorInfo>::unconditional_release_ref(__int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x1800217c8  mov     rdx, [rcx]
0x1800217cb  and     qword ptr [rcx], 0
0x1800217cf  mov     rcx, rdx
0x1800217d2  mov     rax, [rdx]
0x1800217d5  mov     rax, [rax+10h]
0x1800217d9  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
