# VerifyProtocolList(uchar *,ulong,ulong)

- ea: `0x140035490`
- end: `0x1400354ba`
- name: `?VerifyProtocolList@@YAJPEAEKK@Z`
- size: `42`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400352d4`
- `0x140035490`
- `0x1400354c0`

## pseudocode

```c
__int64 __fastcall VerifyProtocolList(unsigned __int8 *a1, unsigned int a2, int a3)
{
  char v3; // al

  v3 = *a1 >> 3;
  if ( v3 == 6 )
    return VerifySingleProtocolList(a1, a2, a3);
  if ( v3 == 7 )
    return VerifyMultipleProtocolLists(a1, a2, a3);
  return 3221225485LL;
}

```

## disassembly

```asm
0x140035490  sub     rsp, 28h
0x140035494  mov     al, [rcx]
0x140035496  shr     al, 3
0x140035499  cmp     al, 6
0x14003549b  jnz     short loc_1400354A4
0x14003549d  call    ?VerifySingleProtocolList@@YAJPEAEKK@Z; VerifySingleProtocolList(uchar *,ulong,ulong)
0x1400354a2  jmp     short loc_1400354B4
0x1400354a4  cmp     al, 7
0x1400354a6  jnz     short loc_1400354AF
0x1400354a8  call    ?VerifyMultipleProtocolLists@@YAJPEAEKK@Z; VerifyMultipleProtocolLists(uchar *,ulong,ulong)
0x1400354ad  jmp     short loc_1400354B4
0x1400354af  mov     eax, 0C000000Dh
0x1400354b4  add     rsp, 28h
0x1400354b8  retn
```
