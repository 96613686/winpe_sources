# utils::CAsyncResult<bool>::SetAsCompleted(bool const &,bool)

- ea: `0x18000d3a0`
- end: `0x18000d3c7`
- name: `?SetAsCompleted@?$CAsyncResult@_N@utils@@UEAAXAEB_N_N@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64 *, _BYTE *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011010`

## pseudocode

```c
__int64 __fastcall utils::CAsyncResult<bool>::SetAsCompleted(__int64 *a1, _BYTE *a2)
{
  __int64 v2; // rax
  int v4; // [rsp+30h] [rbp+8h] BYREF

  *((_BYTE *)a1 + 56) = *a2;
  v2 = *a1;
  v4 = 0;
  return (*(__int64 (__fastcall **)(__int64 *, int *))(v2 + 48))(a1, &v4);
}

```

## disassembly

```asm
0x18000d3a0  sub     rsp, 28h
0x18000d3a4  mov     al, [rdx]
0x18000d3a6  lea     rdx, [rsp+28h+arg_0]
0x18000d3ab  mov     [rcx+38h], al
0x18000d3ae  mov     rax, [rcx]
0x18000d3b1  mov     [rsp+28h+arg_0], 0
0x18000d3b9  mov     rax, [rax+30h]
0x18000d3bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3c2  add     rsp, 28h
0x18000d3c6  retn
```
