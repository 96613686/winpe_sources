# __security_check_cookie

- ea: `0x1400109c0`
- end: `0x1400109de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `37`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400029e0`
- `0x140003800`
- `0x1400038fc`
- `0x140003af8`
- `0x140003bf8`
- `0x140003da4`
- `0x140003ea4`
- `0x140004c88`
- `0x140005188`
- `0x140005630`
- `0x1400061e4`
- `0x140006a80`
- `0x140006fa4`
- `0x14000747c`
- `0x140008684`
- `0x140008c74`
- `0x140009240`
- `0x1400094a4`
- `0x1400096b4`
- `0x140009738`
- `0x140009824`
- `0x140009b50`
- `0x140009c48`
- `0x140009cc4`
- `0x14000a27c`
- `0x14000a5d4`
- `0x14000a798`
- `0x14000abd4`
- `0x14000c498`
- `0x14000ca10`
- `0x14000d998`
- `0x14000e0b0`
- `0x14000e360`
- `0x14000e5f8`
- `0x14000eb2c`
- `0x14000f768`
- `0x140010114`

## callees

- `0x140001590`
- `0x1400109c0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x1400109c0  cmp     rcx, cs:__security_cookie
0x1400109c7  jnz     short loc_1400109D9
0x1400109c9  rol     rcx, 10h
0x1400109cd  test    cx, 0FFFFh
0x1400109d2  jnz     short loc_1400109D5
0x1400109d4  retn
0x1400109d5  ror     rcx, 10h
0x1400109d9  jmp     __report_gsfailure
```
