# _ux::CLauncherMainTaskDialog::SetLauncherEnabled_::_1_::dtor$5

- ea: `0x18001079b`
- end: `0x1800107c7`
- name: `_ux::CLauncherMainTaskDialog::SetLauncherEnabled_::_1_::dtor$5`
- size: `44`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180009920`
- `0x18001079b`

## pseudocode

```c
__int64 __fastcall ux::CLauncherMainTaskDialog::SetLauncherEnabled_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 128) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 128) &= ~1u;
    return std::tr1::shared_ptr<utils::CAsyncResultNoResult>::~shared_ptr<utils::CAsyncResultNoResult>(a2 + 32);
  }
  return result;
}

```

## disassembly

```asm
0x18001079b  push    rbp
0x18001079d  sub     rsp, 20h
0x1800107a1  mov     rbp, rdx
0x1800107a4  mov     eax, [rbp+80h]
0x1800107aa  and     eax, 1
0x1800107ad  test    eax, eax
0x1800107af  jz      short loc_1800107C1
0x1800107b1  and     dword ptr [rbp+80h], 0FFFFFFFEh
0x1800107b8  lea     rcx, [rbp+20h]
0x1800107bc  call    ??1?$shared_ptr@VCAsyncResultNoResult@utils@@@tr1@std@@QEAA@XZ; std::tr1::shared_ptr<utils::CAsyncResultNoResult>::~shared_ptr<utils::CAsyncResultNoResult>(void)
0x1800107c1  add     rsp, 20h
0x1800107c5  pop     rbp
0x1800107c6  retn
```
