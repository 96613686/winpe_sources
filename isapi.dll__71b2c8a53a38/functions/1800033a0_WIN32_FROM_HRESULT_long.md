# WIN32_FROM_HRESULT(long)

- ea: `0x1800033a0`
- end: `0x1800033bb`
- name: `?WIN32_FROM_HRESULT@@YAKJ@Z`
- size: `27`
- prototype: `unsigned int __fastcall(int)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d9c`
- `0x1800034c0`
- `0x180003bc0`
- `0x180003ef0`
- `0x180004b70`
- `0x18000bd8c`
- `0x18000dd40`
- `0x18000e1bc`

## callees

- `0x1800033a0`

## pseudocode

```c
__int64 __fastcall WIN32_FROM_HRESULT(int a1)
{
  if ( a1 < 0 && (a1 & 0x1FFF0000) == 0x70000 )
    return (unsigned __int16)a1;
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x1800033a0  test    ecx, ecx
0x1800033a2  jns     short loc_1800033B8
0x1800033a4  mov     edx, ecx
0x1800033a6  movzx   eax, cx
0x1800033a9  and     edx, 1FFF0000h
0x1800033af  cmp     edx, 70000h
0x1800033b5  cmovz   ecx, eax
0x1800033b8  mov     eax, ecx
0x1800033ba  retn
```
