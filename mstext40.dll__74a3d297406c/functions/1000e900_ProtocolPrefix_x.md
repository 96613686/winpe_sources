# ProtocolPrefix(x)

- ea: `0x1000e900`
- end: `0x1000e942`
- name: `_ProtocolPrefix@4`
- size: `66`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1000d2c0`
- `0x1000d720`
- `0x1000d7a0`
- `0x1000e350`
- `0x1000e950`

## callees

- `0x10009070`
- `0x1000e900`

## pseudocode

```c
int __stdcall ProtocolPrefix(int a1)
{
  int v1; // esi

  v1 = 0;
  while ( ascii_wcsnicmp(a1, (&off_1003E020)[2 * v1], (unsigned __int8)byte_1003E024[8 * v1]) )
  {
    if ( (unsigned int)++v1 >= 0x10 )
      return -1;
  }
  return v1;
}

```

## disassembly

```asm
0x1000e900  push    esi
0x1000e901  push    edi
0x1000e902  mov     edi, [esp+8+arg_0]
0x1000e906  xor     esi, esi
0x1000e908  jmp     short loc_1000E910
0x1000e910  movzx   eax, byte_1003E024[esi*8]
0x1000e918  push    eax
0x1000e919  push    off_1003E020[esi*8]; "http:"
0x1000e920  push    edi
0x1000e921  call    _ascii_wcsnicmp
0x1000e926  add     esp, 0Ch
0x1000e929  test    eax, eax
0x1000e92b  jz      short loc_1000E93B
0x1000e92d  inc     esi
0x1000e92e  cmp     esi, 10h
0x1000e931  jb      short loc_1000E910
0x1000e933  pop     edi
0x1000e934  or      eax, 0FFFFFFFFh
0x1000e937  pop     esi
0x1000e938  retn    4
0x1000e93b  pop     edi
0x1000e93c  mov     eax, esi
0x1000e93e  pop     esi
0x1000e93f  retn    4
```
