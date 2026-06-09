# __scrt_initialize_crt

- ea: `0x1400013e4`
- end: `0x14000141e`
- name: `__scrt_initialize_crt`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400011d0`

## callees

- `0x1400013e4`
- `0x140001708`
- `0x140001950`

## pseudocode

```c
char __fastcall _scrt_initialize_crt(int a1)
{
  if ( !a1 )
    byte_1400070D1 = 1;
  _isa_available_init();
  if ( !(unsigned __int8)((__int64 (*)(void))_scrt_stub_for_acrt_uninitialize)() )
    return 0;
  if ( !(unsigned __int8)((__int64 (*)(void))_scrt_stub_for_acrt_uninitialize)() )
  {
    _scrt_stub_for_acrt_uninitialize(0);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1400013e4  sub     rsp, 28h
0x1400013e8  test    ecx, ecx
0x1400013ea  jnz     short loc_1400013F3
0x1400013ec  mov     cs:byte_1400070D1, 1
0x1400013f3  call    __isa_available_init
0x1400013f8  call    __scrt_stub_for_acrt_uninitialize
0x1400013fd  test    al, al
0x1400013ff  jnz     short loc_140001405
0x140001401  xor     al, al
0x140001403  jmp     short loc_140001419
0x140001405  call    __scrt_stub_for_acrt_uninitialize
0x14000140a  test    al, al
0x14000140c  jnz     short loc_140001417
0x14000140e  xor     ecx, ecx
0x140001410  call    __scrt_stub_for_acrt_uninitialize
0x140001415  jmp     short loc_140001401
0x140001417  mov     al, 1
0x140001419  add     rsp, 28h
0x14000141d  retn
```
