# _DevhlprGetReaderImageNameInternal_::_1_::dtor$26

- ea: `0x180024840`
- end: `0x18002486f`
- name: `_DevhlprGetReaderImageNameInternal_::_1_::dtor$26`
- size: `47`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800066d8`
- `0x180024840`

## pseudocode

```c
void __fastcall DevhlprGetReaderImageNameInternal_::_1_::dtor_26(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 168) & 2) != 0 )
  {
    *(_DWORD *)(a2 + 168) &= ~2u;
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(*(_QWORD *)(a2 + 176), a2);
  }
}

```

## disassembly

```asm
0x180024840  push    rbp
0x180024842  sub     rsp, 20h
0x180024846  mov     rbp, rdx
0x180024849  mov     eax, [rbp+0A8h]
0x18002484f  and     eax, 2
0x180024852  test    eax, eax
0x180024854  jz      short loc_180024869
0x180024856  and     dword ptr [rbp+0A8h], 0FFFFFFFDh
0x18002485d  mov     rcx, [rbp+0B0h]
0x180024864  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180024869  add     rsp, 20h
0x18002486d  pop     rbp
0x18002486e  retn
```
