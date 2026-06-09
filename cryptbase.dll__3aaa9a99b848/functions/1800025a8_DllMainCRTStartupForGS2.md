# _DllMainCRTStartupForGS2

- ea: `0x1800025a8`
- end: `0x1800025c0`
- name: `_DllMainCRTStartupForGS2`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800011e0`

## callees

- `0x1800025a8`
- `0x1800025c8`

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
0x1800025a8  sub     rsp, 28h
0x1800025ac  cmp     edx, 1
0x1800025af  jnz     short loc_1800025B6
0x1800025b1  call    __security_init_cookie
0x1800025b6  mov     eax, 1
0x1800025bb  add     rsp, 28h
0x1800025bf  retn
```
