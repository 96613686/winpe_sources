# ProtocolPrefix(x)

- ea: `0x10022838`
- end: `0x1002286b`
- name: `_ProtocolPrefix@4`
- size: `51`
- prototype: `int __thiscall(_DWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10022871`
- `0x10022e8a`
- `0x100234fb`
- `0x10023a8d`
- `0x10023bdb`
- `0x10026c60`

## callees

- `0x100223ec`
- `0x10022838`

## pseudocode

```c
int ProtocolPrefix()
{
  int v0; // esi

  v0 = 0;
  while ( WCSNICMP((unsigned __int8)byte_10038E84[8 * v0]) )
  {
    if ( (unsigned int)++v0 >= 0x10 )
      return -1;
  }
  return v0;
}

```

## disassembly

```asm
0x10022838  mov     edi, edi
0x1002283a  push    esi
0x1002283b  push    edi
0x1002283c  mov     edi, ecx
0x1002283e  xor     esi, esi
0x10022840  movzx   eax, byte_10038E84[esi*8]
0x10022848  mov     ecx, edi
0x1002284a  mov     edx, off_10038E80[esi*8]; "http:"
0x10022851  push    eax
0x10022852  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x10022857  test    eax, eax
0x10022859  jz      short loc_10022866
0x1002285b  inc     esi
0x1002285c  cmp     esi, 10h
0x1002285f  jb      short loc_10022840
0x10022861  or      eax, 0FFFFFFFFh
0x10022864  jmp     short loc_10022868
0x10022866  mov     eax, esi
0x10022868  pop     edi
0x10022869  pop     esi
0x1002286a  retn
```
