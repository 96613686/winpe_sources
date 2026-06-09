# WIN32_FROM_HRESULT(long)

- ea: `0x180007490`
- end: `0x1800074ab`
- name: `?WIN32_FROM_HRESULT@@YAKJ@Z`
- size: `27`
- prototype: `unsigned int __fastcall(int)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1800019c0`
- `0x180002fc0`
- `0x180004bf0`
- `0x180006920`
- `0x180006aa0`
- `0x180006f50`
- `0x1800071c0`
- `0x180007d40`
- `0x1800084b0`
- `0x18000a6b0`
- `0x18000c6a0`

## callees

- `0x180007490`

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
0x180007490  test    ecx, ecx
0x180007492  jns     short loc_1800074A8
0x180007494  mov     edx, ecx
0x180007496  movzx   eax, cx
0x180007499  and     edx, 1FFF0000h
0x18000749f  cmp     edx, 70000h
0x1800074a5  cmovz   ecx, eax
0x1800074a8  mov     eax, ecx
0x1800074aa  retn
```
