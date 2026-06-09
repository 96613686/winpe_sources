# LConvertToAnsiWordLengths

- ea: `0x180013c2c`
- end: `0x180013c73`
- name: `LConvertToAnsiWordLengths`
- size: `71`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, unsigned __int16, CHAR **, unsigned __int16, _WORD *)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ecc0`
- `0x18000eea0`
- `0x18000f100`
- `0x18000f2b0`
- `0x18000f3e0`
- `0x18000f530`
- `0x18000f600`
- `0x18000f7d0`
- `0x18000f930`

## callees

- `0x180013a64`
- `0x180013c2c`

## pseudocode

```c
__int64 __fastcall LConvertToAnsiWordLengths(
        __int64 a1,
        const WCHAR *a2,
        unsigned __int16 a3,
        CHAR **a4,
        unsigned __int16 a5,
        _WORD *a6)
{
  __int64 result; // rax
  int v7; // [rsp+60h] [rbp+18h] BYREF

  v7 = 0;
  result = LConvertToAnsi((__int64)&v7, a2, a3, a4, a5, &v7, 9);
  if ( a6 )
    *a6 = v7;
  return result;
}

```

## disassembly

```asm
0x180013c2c  sub     rsp, 48h
0x180013c30  movzx   eax, [rsp+48h+arg_20]
0x180013c35  lea     rcx, [rsp+48h+arg_10]
0x180013c3a  mov     [rsp+48h+var_18], 9
0x180013c42  mov     [rsp+48h+var_20], rcx
0x180013c47  movzx   r8d, r8w
0x180013c4b  mov     [rsp+48h+var_28], eax
0x180013c4f  mov     [rsp+48h+arg_10], 0
0x180013c57  call    LConvertToAnsi
0x180013c5c  mov     rdx, [rsp+48h+arg_28]
0x180013c61  test    rdx, rdx
0x180013c64  jz      short loc_180013C6E
0x180013c66  movzx   ecx, word ptr [rsp+48h+arg_10]
0x180013c6b  mov     [rdx], cx
0x180013c6e  add     rsp, 48h
0x180013c72  retn
```
