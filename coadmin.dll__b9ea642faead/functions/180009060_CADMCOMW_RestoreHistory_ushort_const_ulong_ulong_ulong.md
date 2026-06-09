# CADMCOMW::RestoreHistory(ushort const *,ulong,ulong,ulong)

- ea: `0x180009060`
- end: `0x1800090ae`
- name: `?RestoreHistory@CADMCOMW@@UEAAJPEBGKKK@Z`
- size: `78`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008ae0`
- `0x180009060`

## pseudocode

```c
__int64 __fastcall CADMCOMW::RestoreHistory(
        CADMCOMW *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5)
{
  if ( (a5 & 0xFFFFFFFE) != 0 )
  {
    if ( a5 )
      return 2147943404LL;
  }
  else if ( (a5 & 1) != 0 && (a3 || a4) )
  {
    return 2147942487LL;
  }
  return CADMCOMW::RestoreHelper(this, a2, a3, a4, 0, a5, 1u);
}

```

## disassembly

```asm
0x180009060  sub     rsp, 48h
0x180009064  mov     eax, [rsp+48h+arg_20]
0x180009068  test    eax, 0FFFFFFFEh
0x18000906d  jz      short loc_18000907A
0x18000906f  test    eax, eax
0x180009071  jz      short loc_18000908F
0x180009073  mov     eax, 800703ECh
0x180009078  jmp     short loc_1800090A9
0x18000907a  test    al, 1
0x18000907c  jz      short loc_18000908F
0x18000907e  test    r8d, r8d
0x180009081  jnz     short loc_180009088
0x180009083  test    r9d, r9d
0x180009086  jz      short loc_18000908F
0x180009088  mov     eax, 80070057h
0x18000908d  jmp     short loc_1800090A9
0x18000908f  mov     [rsp+48h+var_18], 1; unsigned int
0x180009097  mov     [rsp+48h+var_20], eax; unsigned int
0x18000909b  mov     [rsp+48h+var_28], 0; unsigned __int16 *
0x1800090a4  call    ?RestoreHelper@CADMCOMW@@AEAAJPEBGKK0KK@Z; CADMCOMW::RestoreHelper(ushort const *,ulong,ulong,ushort const *,ulong,ulong)
0x1800090a9  add     rsp, 48h
0x1800090ad  retn
```
