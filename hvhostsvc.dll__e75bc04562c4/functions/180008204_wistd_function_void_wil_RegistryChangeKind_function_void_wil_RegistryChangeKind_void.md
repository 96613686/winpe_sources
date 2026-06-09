# wistd::function<void (wil::RegistryChangeKind)>::~function<void (wil::RegistryChangeKind)>(void)

- ea: `0x180008204`
- end: `0x180008222`
- name: `??1?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000832c`
- `0x1800084f4`
- `0x180009628`

## callees

- `0x180008204`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall wistd::function<void (enum wil::RegistryChangeKind)>::~function<void (enum wil::RegistryChangeKind)>(
        __int64 a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 112);
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 24LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180008204  sub     rsp, 28h
0x180008208  mov     rcx, [rcx+70h]
0x18000820c  test    rcx, rcx
0x18000820f  jz      short loc_18000821D
0x180008211  mov     rax, [rcx]
0x180008214  mov     rax, [rax+18h]
0x180008218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000821d  add     rsp, 28h
0x180008221  retn
```
