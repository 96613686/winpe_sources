# __scrt_initialize_crt

- ea: `0x1400013a4`
- end: `0x1400013de`
- name: `__scrt_initialize_crt`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001180`

## callees

- `0x1400013a4`
- `0x1400016c8`
- `0x1400018d0`

## pseudocode

```c
char __fastcall _scrt_initialize_crt(int a1)
{
  if ( !a1 )
    byte_1400040D1 = 1;
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
0x1400013a4  sub     rsp, 28h
0x1400013a8  test    ecx, ecx
0x1400013aa  jnz     short loc_1400013B3
0x1400013ac  mov     cs:byte_1400040D1, 1
0x1400013b3  call    __isa_available_init
0x1400013b8  call    __scrt_stub_for_acrt_uninitialize
0x1400013bd  test    al, al
0x1400013bf  jnz     short loc_1400013C5
0x1400013c1  xor     al, al
0x1400013c3  jmp     short loc_1400013D9
0x1400013c5  call    __scrt_stub_for_acrt_uninitialize
0x1400013ca  test    al, al
0x1400013cc  jnz     short loc_1400013D7
0x1400013ce  xor     ecx, ecx
0x1400013d0  call    __scrt_stub_for_acrt_uninitialize
0x1400013d5  jmp     short loc_1400013C1
0x1400013d7  mov     al, 1
0x1400013d9  add     rsp, 28h
0x1400013dd  retn
```
