# __scrt_initialize_crt

- ea: `0x180001600`
- end: `0x18000163a`
- name: `__scrt_initialize_crt`
- size: `58`
- prototype: `char __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001148`

## callees

- `0x180001600`
- `0x180001a00`
- `0x180001df8`

## pseudocode

```c
char __fastcall _scrt_initialize_crt(int a1)
{
  __int64 v1; // rcx
  __int64 v2; // rcx

  if ( !a1 )
    byte_180008151 = 1;
  _isa_available_init();
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical(v1) )
    return 0;
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical(v2) )
  {
    _scrt_stub_for_acrt_uninitialize_critical(0);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180001600  sub     rsp, 28h
0x180001604  test    ecx, ecx
0x180001606  jnz     short loc_18000160F
0x180001608  mov     cs:byte_180008151, 1
0x18000160f  call    __isa_available_init
0x180001614  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001619  test    al, al
0x18000161b  jnz     short loc_180001621
0x18000161d  xor     al, al
0x18000161f  jmp     short loc_180001635
0x180001621  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001626  test    al, al
0x180001628  jnz     short loc_180001633
0x18000162a  xor     ecx, ecx
0x18000162c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001631  jmp     short loc_18000161D
0x180001633  mov     al, 1
0x180001635  add     rsp, 28h
0x180001639  retn
```
