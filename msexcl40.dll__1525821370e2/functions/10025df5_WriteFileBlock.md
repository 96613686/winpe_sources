# WriteFileBlock

- ea: `0x10025df5`
- end: `0x10025e6c`
- name: `WriteFileBlock`
- size: `119`
- prototype: `int __thiscall(_DWORD)`
- caller_count: `12`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1000d760`
- `0x1000dcc0`
- `0x1000dd90`
- `0x1000df70`
- `0x10011730`
- `0x10025e72`
- `0x10025ed1`
- `0x10025f86`
- `0x100260bc`
- `0x1002611f`
- `0x10026233`
- `0x100264c2`

## callees

- `0x10025b48`
- `0x10025bee`
- `0x10025df5`

## pseudocode

```c
int __thiscall WriteFileBlock(DWORD *this)
{
  DWORD v2; // ebx
  int v3; // eax
  int v4; // ecx
  int result; // eax
  int v6; // eax
  DWORD v7; // eax

  OSSetFilePosition((int)this, 0, this[21]);
  if ( this[18] == 1 && this[19] == 1 )
    v2 = this[17] - this[1];
  else
    v2 = *this;
  v3 = OSWriteFile(v2);
  v4 = v3;
  if ( v3 == 0xFFFF )
    return -5;
  v6 = v3 + this[21];
  this[20] = v6;
  this[21] = v6;
  if ( v4 != v2 )
    return -12;
  v7 = this[1];
  this[2] = v7;
  this[17] = v7;
  result = 0;
  *this = 0;
  this[23] = 0;
  this[19] = 1;
  return result;
}

```

## disassembly

```asm
0x10025df5  mov     edi, edi
0x10025df7  push    ebx
0x10025df8  push    esi
0x10025df9  mov     esi, ecx
0x10025dfb  xor     edx, edx
0x10025dfd  push    edi
0x10025dfe  push    dword ptr [esi+54h]
0x10025e01  call    OSSetFilePosition
0x10025e06  cmp     dword ptr [esi+48h], 1
0x10025e0a  jnz     short loc_10025E1A
0x10025e0c  cmp     dword ptr [esi+4Ch], 1
0x10025e10  jnz     short loc_10025E1A
0x10025e12  mov     ebx, [esi+44h]
0x10025e15  sub     ebx, [esi+4]
0x10025e18  jmp     short loc_10025E1C
0x10025e1a  mov     ebx, [esi]
0x10025e1c  mov     edx, [esi+4]
0x10025e1f  mov     ecx, esi
0x10025e21  push    ebx; nNumberOfBytesToWrite
0x10025e22  call    OSWriteFile
0x10025e27  mov     ecx, eax
0x10025e29  cmp     ecx, 0FFFFh
0x10025e2f  jnz     short loc_10025E36
0x10025e31  push    0FFFFFFFBh
0x10025e33  pop     eax
0x10025e34  jmp     short loc_10025E68
0x10025e36  mov     eax, [esi+54h]
0x10025e39  add     eax, ecx
0x10025e3b  mov     [esi+50h], eax
0x10025e3e  mov     [esi+54h], eax
0x10025e41  cmp     ecx, ebx
0x10025e43  jz      short loc_10025E49
0x10025e45  push    0FFFFFFF4h
0x10025e47  jmp     short loc_10025E33
0x10025e49  mov     eax, [esi+4]
0x10025e4c  mov     [esi+8], eax
0x10025e4f  mov     [esi+44h], eax
0x10025e52  xor     eax, eax
0x10025e54  mov     dword ptr [esi], 0
0x10025e5a  mov     dword ptr [esi+5Ch], 0
0x10025e61  mov     dword ptr [esi+4Ch], 1
0x10025e68  pop     edi
0x10025e69  pop     esi
0x10025e6a  pop     ebx
0x10025e6b  retn
```
