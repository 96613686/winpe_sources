# _DllMainCRTStartupForGS2

- ea: `0x180001008`
- end: `0x180001020`
- name: `_DllMainCRTStartupForGS2`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002280`

## callees

- `0x180001008`
- `0x180001028`

## pseudocode

```c
__int64 __fastcall DllMainCRTStartupForGS2(__int64 a1, int a2)
{
  if ( a2 == 1 )
    _security_init_cookie();
  return 1;
}

```

## disassembly

```asm
0x180001008  sub     rsp, 28h
0x18000100c  cmp     edx, 1
0x18000100f  jnz     short loc_180001016
0x180001011  call    __security_init_cookie
0x180001016  mov     eax, 1
0x18000101b  add     rsp, 28h
0x18000101f  retn
```
