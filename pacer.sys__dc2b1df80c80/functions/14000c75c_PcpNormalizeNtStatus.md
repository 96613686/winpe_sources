# PcpNormalizeNtStatus

- ea: `0x14000c75c`
- end: `0x14000c7d1`
- name: `PcpNormalizeNtStatus`
- size: `117`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x14000c460`
- `0x14000c550`
- `0x14000c5c0`
- `0x14000c6c0`
- `0x140010040`
- `0x1400102c0`

## callees

- `0x14000c75c`

## pseudocode

```c
__int64 __fastcall PcpNormalizeNtStatus(int a1)
{
  if ( a1 <= -1073610618 )
  {
    if ( a1 != -1073610618
      && a1 != -1073610624
      && a1 != -1073610623
      && a1 != -1073610622
      && a1 != -1073610621
      && a1 != -1073610620
      && a1 != -1073610619 )
    {
      return (unsigned int)a1;
    }
    return (unsigned int)-1073741811;
  }
  if ( a1 == -1073610617
    || a1 == -1073610616
    || a1 == -1073610615
    || a1 == -1073610608
    || a1 == -1073610607
    || a1 == -1073610606 )
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x14000c75c  mov     eax, 0C0020086h
0x14000c761  cmp     ecx, eax
0x14000c763  jg      short loc_14000C799
0x14000c765  jz      short loc_14000C7C9
0x14000c767  cmp     ecx, 0C0020080h
0x14000c76d  jz      short loc_14000C7C9
0x14000c76f  cmp     ecx, 0C0020081h
0x14000c775  jz      short loc_14000C7C9
0x14000c777  cmp     ecx, 0C0020082h
0x14000c77d  jz      short loc_14000C7C9
0x14000c77f  cmp     ecx, 0C0020083h
0x14000c785  jz      short loc_14000C7C9
0x14000c787  cmp     ecx, 0C0020084h
0x14000c78d  jz      short loc_14000C7C9
0x14000c78f  cmp     ecx, 0C0020085h
0x14000c795  jz      short loc_14000C7C9
0x14000c797  jmp     short loc_14000C7CE
0x14000c799  cmp     ecx, 0C0020087h
0x14000c79f  jz      short loc_14000C7C9
0x14000c7a1  cmp     ecx, 0C0020088h
0x14000c7a7  jz      short loc_14000C7C9
0x14000c7a9  cmp     ecx, 0C0020089h
0x14000c7af  jz      short loc_14000C7C9
0x14000c7b1  cmp     ecx, 0C0020090h
0x14000c7b7  jz      short loc_14000C7C9
0x14000c7b9  cmp     ecx, 0C0020091h
0x14000c7bf  jz      short loc_14000C7C9
0x14000c7c1  cmp     ecx, 0C0020092h
0x14000c7c7  jnz     short loc_14000C7CE
0x14000c7c9  mov     ecx, 0C000000Dh
0x14000c7ce  mov     eax, ecx
0x14000c7d0  retn
```
