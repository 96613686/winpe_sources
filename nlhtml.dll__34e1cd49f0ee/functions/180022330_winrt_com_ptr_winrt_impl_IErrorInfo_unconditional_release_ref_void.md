# winrt::com_ptr<winrt::impl::IErrorInfo>::unconditional_release_ref(void)

- ea: `0x180022330`
- end: `0x180022349`
- name: `?unconditional_release_ref@?$com_ptr@UIErrorInfo@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180022244`

## callees

- `0x180025010`

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
0x180022330  mov     rdx, [rcx]
0x180022333  mov     qword ptr [rcx], 0
0x18002233a  mov     rcx, rdx
0x18002233d  mov     rax, [rdx]
0x180022340  mov     rax, [rax+10h]
0x180022344  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
