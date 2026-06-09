# utils::CAsyncResultNoResult::SetAsCompleted(bool)

- ea: `0x18000fa20`
- end: `0x18000fa45`
- name: `?SetAsCompleted@CAsyncResultNoResult@utils@@UEAAX_N@Z`
- size: `37`
- prototype: `void __fastcall(utils::CAsyncResultNoResult *this, char, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011010`

## pseudocode

```c
void __fastcall utils::CAsyncResultNoResult::SetAsCompleted(utils::CAsyncResultNoResult *this, char a2, __int64 a3)
{
  __int64 v3; // rax
  int v4; // [rsp+30h] [rbp+8h] BYREF

  v3 = *(_QWORD *)this;
  LOBYTE(a3) = a2;
  v4 = 0;
  (*(void (__fastcall **)(utils::CAsyncResultNoResult *, int *, __int64))(v3 + 48))(this, &v4, a3);
}

```

## disassembly

```asm
0x18000fa20  sub     rsp, 28h
0x18000fa24  mov     rax, [rcx]
0x18000fa27  mov     r8b, dl
0x18000fa2a  lea     rdx, [rsp+28h+arg_0]
0x18000fa2f  mov     [rsp+28h+arg_0], 0
0x18000fa37  mov     rax, [rax+30h]
0x18000fa3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa40  add     rsp, 28h
0x18000fa44  retn
```
