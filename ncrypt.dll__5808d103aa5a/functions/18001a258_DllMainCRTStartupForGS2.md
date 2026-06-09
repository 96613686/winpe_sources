# _DllMainCRTStartupForGS2

- ea: `0x18001a258`
- end: `0x18001a270`
- name: `_DllMainCRTStartupForGS2`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013880`

## callees

- `0x18001a258`
- `0x18001a400`

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
0x18001a258  sub     rsp, 28h
0x18001a25c  cmp     edx, 1
0x18001a25f  jnz     short loc_18001A266
0x18001a261  call    __security_init_cookie
0x18001a266  mov     eax, 1
0x18001a26b  add     rsp, 28h
0x18001a26f  retn
```
