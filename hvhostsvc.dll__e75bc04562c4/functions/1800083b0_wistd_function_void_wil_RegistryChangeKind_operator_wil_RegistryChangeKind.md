# wistd::function<void (wil::RegistryChangeKind)>::operator()(wil::RegistryChangeKind)

- ea: `0x1800083b0`
- end: `0x1800083dd`
- name: `??R?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@QEBAXW4RegistryChangeKind@wil@@@Z`
- size: `45`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180008a50`

## callees

- `0x180005fc4`
- `0x1800083b0`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall wistd::function<void (enum wil::RegistryChangeKind)>::operator()(__int64 a1, int a2)
{
  __int64 v2; // rcx
  int v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = a2;
  v2 = *(_QWORD *)(a1 + 112);
  if ( !v2 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
  return (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v2 + 32LL))(v2, &v4);
}

```

## disassembly

```asm
0x1800083b0  mov     [rsp+arg_8], edx
0x1800083b4  sub     rsp, 28h
0x1800083b8  mov     rcx, [rcx+70h]; this
0x1800083bc  test    rcx, rcx
0x1800083bf  jz      short loc_1800083D7
0x1800083c1  mov     rax, [rcx]
0x1800083c4  lea     rdx, [rsp+28h+arg_8]
0x1800083c9  mov     rax, [rax+20h]
0x1800083cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083d2  add     rsp, 28h
0x1800083d6  retn
0x1800083d7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
