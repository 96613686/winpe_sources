# HasProtocolPrefix

- ea: `0x10026e70`
- end: `0x10026eb7`
- name: `HasProtocolPrefix`
- size: `71`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10027030`
- `0x10029000`

## callees

- `0x10009070`
- `0x10026e70`

## pseudocode

```c
int __stdcall HasProtocolPrefix(int a1)
{
  unsigned int v1; // esi

  v1 = 0;
  while ( ascii_wcsnicmp(a1, (&off_1003F0D0)[v1], (unsigned __int8)byte_1003F0D4[v1 * 4]) )
  {
    v1 += 2;
    if ( v1 >= 32 )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x10026e70  push    esi
0x10026e71  push    edi
0x10026e72  mov     edi, [esp+8+arg_0]
0x10026e76  xor     esi, esi
0x10026e78  jmp     short loc_10026E80
0x10026e80  movzx   eax, byte_1003F0D4[esi]
0x10026e87  push    eax
0x10026e88  push    off_1003F0D0[esi]; "http:"
0x10026e8e  push    edi
0x10026e8f  call    _ascii_wcsnicmp
0x10026e94  add     esp, 0Ch
0x10026e97  test    eax, eax
0x10026e99  jz      short loc_10026EAD
0x10026e9b  add     esi, 8
0x10026e9e  cmp     esi, 80h
0x10026ea4  jb      short loc_10026E80
0x10026ea6  pop     edi
0x10026ea7  xor     eax, eax
0x10026ea9  pop     esi
0x10026eaa  retn    4
0x10026ead  pop     edi
0x10026eae  mov     eax, 1
0x10026eb3  pop     esi
0x10026eb4  retn    4
```
