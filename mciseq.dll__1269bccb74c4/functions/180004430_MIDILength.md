# MIDILength

- ea: `0x180004430`
- end: `0x1800044e9`
- name: `MIDILength`
- size: `185`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003dc0`
- `0x180004588`
- `0x180004b30`

## callees

- `0x180004430`

## pseudocode

```c
__int64 __fastcall MIDILength(char a1)
{
  unsigned int v1; // ecx
  unsigned int v2; // ecx
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  unsigned int v5; // ecx
  unsigned int v6; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx

  if ( a1 >= 0 )
    return 0;
  switch ( a1 & 0xF0 )
  {
    case 128:
    case 144:
    case 160:
    case 176:
      return 3;
    case 192:
    case 208:
      return 2;
    case 224:
      return 3;
  }
  if ( (a1 & 0xF0) != 0xF0 )
    return 0;
  v1 = a1 & 0xF;
  if ( v1 > 8 )
  {
    v8 = v1 - 9;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( !v9 )
        return 1;
      v10 = v9 - 1;
      if ( !v10 )
        return 1;
      v11 = v10 - 1;
      if ( !v11 )
        return 1;
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( !v13 )
          return 1;
        if ( v13 == 1 )
          return 258;
      }
    }
    return 0;
  }
  if ( v1 == 8 )
    return 1;
  if ( !v1 )
    return 257;
  v2 = v1 - 1;
  if ( !v2 )
    return 2;
  v3 = v2 - 1;
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      v5 = v4 - 1;
      if ( !v5 )
        return 0;
      v6 = v5 - 1;
      return v6 && v6 - 1 < 2;
    }
    return 2;
  }
  return 3;
}

```

## disassembly

```asm
0x180004430  test    cl, cl
0x180004432  jns     short loc_1800044A5
0x180004434  movzx   ecx, cl
0x180004437  mov     edx, ecx
0x180004439  and     edx, 0F0h
0x18000443f  sub     edx, 80h
0x180004445  jz      loc_1800044E3
0x18000444b  mov     eax, 10h
0x180004450  sub     edx, eax
0x180004452  jz      loc_1800044E3
0x180004458  sub     edx, eax
0x18000445a  jz      loc_1800044E3
0x180004460  sub     edx, eax
0x180004462  jz      short loc_1800044E3
0x180004464  sub     edx, eax
0x180004466  jz      short loc_1800044DD
0x180004468  sub     edx, eax
0x18000446a  jz      short loc_1800044DD
0x18000446c  sub     edx, eax
0x18000446e  jz      short loc_1800044E3
0x180004470  cmp     edx, eax
0x180004472  jnz     short loc_1800044A5
0x180004474  and     ecx, 0Fh
0x180004477  cmp     ecx, 8
0x18000447a  ja      short loc_1800044AE
0x18000447c  jz      short loc_1800044D7
0x18000447e  test    ecx, ecx
0x180004480  jz      short loc_1800044A8
0x180004482  sub     ecx, 1
0x180004485  jz      short loc_1800044DD
0x180004487  sub     ecx, 1
0x18000448a  jz      short loc_1800044E3
0x18000448c  sub     ecx, 1
0x18000448f  jz      short loc_1800044DD
0x180004491  sub     ecx, 1
0x180004494  jz      short loc_1800044A5
0x180004496  sub     ecx, 1
0x180004499  jz      short loc_1800044A5
0x18000449b  sub     ecx, 1
0x18000449e  jz      short loc_1800044D7
0x1800044a0  cmp     ecx, 1
0x1800044a3  jz      short loc_1800044D7
0x1800044a5  xor     eax, eax
0x1800044a7  retn
0x1800044a8  mov     eax, 101h
0x1800044ad  retn
0x1800044ae  sub     ecx, 9
0x1800044b1  jz      short loc_1800044A5
0x1800044b3  sub     ecx, 1
0x1800044b6  jz      short loc_1800044D7
0x1800044b8  sub     ecx, 1
0x1800044bb  jz      short loc_1800044D7
0x1800044bd  sub     ecx, 1
0x1800044c0  jz      short loc_1800044D7
0x1800044c2  sub     ecx, 1
0x1800044c5  jz      short loc_1800044A5
0x1800044c7  sub     ecx, 1
0x1800044ca  jz      short loc_1800044D7
0x1800044cc  cmp     ecx, 1
0x1800044cf  jnz     short loc_1800044A5
0x1800044d1  mov     eax, 102h
0x1800044d6  retn
0x1800044d7  mov     eax, 1
0x1800044dc  retn
0x1800044dd  mov     eax, 2
0x1800044e2  retn
0x1800044e3  mov     eax, 3
0x1800044e8  retn
```
