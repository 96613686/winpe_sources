# TXTUpdate(x,x,x,x,x)

- ea: `0x100160b0`
- end: `0x10016121`
- name: `_TXTUpdate@20`
- size: `113`
- prototype: `int __stdcall(int, int, void *, size_t Size, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1000fe70`
- `0x10014460`
- `0x100154f0`
- `0x100160b0`

## pseudocode

```c
int __stdcall TXTUpdate(int a1, int a2, void *a3, size_t Size, _DWORD *a5)
{
  int v5; // eax
  int v6; // esi
  int result; // eax

  if ( a5 )
    *a5 = 0;
  v5 = ISAMDBFindCursor(a1, a2);
  v6 = v5;
  if ( !v5 )
    return -1310;
  if ( !*(_DWORD *)(v5 + 76) )
    return -1609;
  if ( *(_BYTE *)(v5 + 28) == 1 )
    return -1809;
  result = EstablishAsCurrentCursor(v5);
  if ( !result )
  {
    if ( *(_DWORD *)(v6 + 76) == 1 )
      return RecordInsert(v6, a3, Size, (int)a5);
    return -1609;
  }
  return result;
}

```

## disassembly

```asm
0x100160b0  push    esi
0x100160b1  push    edi
0x100160b2  mov     edi, [esp+8+arg_10]
0x100160b6  test    edi, edi
0x100160b8  jz      short loc_100160C0
0x100160ba  mov     dword ptr [edi], 0
0x100160c0  push    [esp+8+arg_4]
0x100160c4  push    [esp+0Ch+arg_0]
0x100160c8  call    _ISAMDBFindCursor@8; ISAMDBFindCursor(x,x)
0x100160cd  mov     esi, eax
0x100160cf  test    esi, esi
0x100160d1  jnz     short loc_100160DD
0x100160d3  pop     edi
0x100160d4  mov     eax, 0FFFFFAE2h
0x100160d9  pop     esi
0x100160da  retn    14h
0x100160dd  cmp     dword ptr [esi+4Ch], 0
0x100160e1  jz      short loc_10016117
0x100160e3  cmp     byte ptr [esi+1Ch], 1
0x100160e7  jnz     short loc_100160F3
0x100160e9  pop     edi
0x100160ea  mov     eax, 0FFFFF8EFh
0x100160ef  pop     esi
0x100160f0  retn    14h
0x100160f3  push    esi
0x100160f4  call    _EstablishAsCurrentCursor@4; EstablishAsCurrentCursor(x)
0x100160f9  test    eax, eax
0x100160fb  jnz     short loc_1001611C
0x100160fd  cmp     dword ptr [esi+4Ch], 1
0x10016101  jnz     short loc_10016117
0x10016103  push    edi; int
0x10016104  push    [esp+0Ch+Size]; Size
0x10016108  push    [esp+10h+arg_8]; void *
0x1001610c  push    esi; int
0x1001610d  call    RecordInsert
0x10016112  pop     edi
0x10016113  pop     esi
0x10016114  retn    14h
0x10016117  mov     eax, 0FFFFF9B7h
0x1001611c  pop     edi
0x1001611d  pop     esi
0x1001611e  retn    14h
```
