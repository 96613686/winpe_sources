# RtlpCheckBounds

- ea: `0x1800140c8`
- end: `0x1800140fc`
- name: `RtlpCheckBounds`
- size: `52`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800139e4`
- `0x180014104`
- `0x180014218`
- `0x18001446c`
- `0x1800144fc`

## callees

- `0x1800140c8`

## pseudocode

```c
_BOOL8 __fastcall RtlpCheckBounds(unsigned __int64 a1, unsigned __int64 a2, unsigned __int64 a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // rax
  unsigned __int64 v5; // r10
  _BOOL8 result; // rax

  result = 0;
  if ( a1 >= a3 )
  {
    v4 = a3 + a4;
    if ( a1 <= a3 + a4 )
    {
      v5 = a1 + a2;
      if ( a1 + a2 >= a3 && v5 <= v4 && a3 <= v4 && a1 <= v5 && a2 <= a4 )
        return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800140c8  cmp     rcx, r8
0x1800140cb  jb      short loc_1800140F9
0x1800140cd  lea     rax, [r8+r9]
0x1800140d1  cmp     rcx, rax
0x1800140d4  ja      short loc_1800140F9
0x1800140d6  lea     r10, [rcx+rdx]
0x1800140da  cmp     r10, r8
0x1800140dd  jb      short loc_1800140F9
0x1800140df  cmp     r10, rax
0x1800140e2  ja      short loc_1800140F9
0x1800140e4  cmp     r8, rax
0x1800140e7  ja      short loc_1800140F9
0x1800140e9  cmp     rcx, r10
0x1800140ec  ja      short loc_1800140F9
0x1800140ee  cmp     rdx, r9
0x1800140f1  ja      short loc_1800140F9
0x1800140f3  mov     eax, 1
0x1800140f8  retn
0x1800140f9  xor     eax, eax
0x1800140fb  retn
```
