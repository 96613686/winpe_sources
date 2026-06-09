# RtlpCheckBounds

- ea: `0x180013b40`
- end: `0x180013b74`
- name: `RtlpCheckBounds`
- size: `52`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800134a0`
- `0x1800135c4`
- `0x180013624`
- `0x180013b7c`
- `0x180015790`
- `0x180015808`

## callees

- `0x180013b40`

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
      if ( a1 + a2 <= v4 && v5 >= a3 && a3 <= v4 && a1 <= v5 && a2 <= a4 )
        return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180013b40  cmp     rcx, r8
0x180013b43  jb      short loc_180013B71
0x180013b45  lea     rax, [r8+r9]
0x180013b49  cmp     rcx, rax
0x180013b4c  ja      short loc_180013B71
0x180013b4e  lea     r10, [rcx+rdx]
0x180013b52  cmp     r10, rax
0x180013b55  ja      short loc_180013B71
0x180013b57  cmp     r10, r8
0x180013b5a  jb      short loc_180013B71
0x180013b5c  cmp     r8, rax
0x180013b5f  ja      short loc_180013B71
0x180013b61  cmp     rcx, r10
0x180013b64  ja      short loc_180013B71
0x180013b66  cmp     rdx, r9
0x180013b69  ja      short loc_180013B71
0x180013b6b  mov     eax, 1
0x180013b70  retn
0x180013b71  xor     eax, eax
0x180013b73  retn
```
