# StringCchLengthW

- ea: `0x18000d4a4`
- end: `0x18000d507`
- name: `StringCchLengthW`
- size: `99`
- prototype: `HRESULT __stdcall(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180006300`
- `0x180009060`
- `0x180009584`
- `0x180009920`
- `0x18000e5f8`
- `0x18000e8b0`

## callees

- `0x18000d4a4`

## pseudocode

```c
HRESULT __stdcall StringCchLengthW(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)
{
  size_t i; // r9
  HRESULT result; // eax

  if ( !psz || cchMax > 0x7FFFFFFF )
  {
    result = -2147024809;
    goto LABEL_13;
  }
  for ( i = cchMax; i; --i )
  {
    if ( !*psz )
      break;
    ++psz;
  }
  result = i == 0 ? 0x80070057 : 0;
  if ( !pcchLength )
  {
    if ( i )
      return result;
LABEL_13:
    if ( !pcchLength )
      return result;
    goto LABEL_14;
  }
  if ( i )
  {
    *pcchLength = cchMax - i;
    return result;
  }
  *pcchLength = 0;
LABEL_14:
  *pcchLength = 0;
  return result;
}

```

## disassembly

```asm
0x18000d4a4  xor     r10d, r10d
0x18000d4a7  test    rcx, rcx
0x18000d4aa  jz      short loc_18000D4F9
0x18000d4ac  cmp     rdx, 7FFFFFFFh
0x18000d4b3  ja      short loc_18000D4F9
0x18000d4b5  mov     r9, rdx
0x18000d4b8  test    rdx, rdx
0x18000d4bb  jz      short loc_18000D4CD
0x18000d4bd  cmp     [rcx], r10w
0x18000d4c1  jz      short loc_18000D4CD
0x18000d4c3  add     rcx, 2
0x18000d4c7  sub     r9, 1
0x18000d4cb  jnz     short loc_18000D4BD
0x18000d4cd  mov     rax, r9
0x18000d4d0  neg     rax
0x18000d4d3  sbb     eax, eax
0x18000d4d5  not     eax
0x18000d4d7  and     eax, 80070057h
0x18000d4dc  test    r8, r8
0x18000d4df  jz      short loc_18000D4F2
0x18000d4e1  test    r9, r9
0x18000d4e4  jz      short loc_18000D4ED
0x18000d4e6  sub     rdx, r9
0x18000d4e9  mov     [r8], rdx
0x18000d4ec  retn
0x18000d4ed  mov     [r8], r10
0x18000d4f0  jmp     short loc_18000D503
0x18000d4f2  test    r9, r9
0x18000d4f5  jnz     short locret_18000D506
0x18000d4f7  jmp     short loc_18000D4FE
0x18000d4f9  mov     eax, 80070057h
0x18000d4fe  test    r8, r8
0x18000d501  jz      short locret_18000D506
0x18000d503  mov     [r8], r10
0x18000d506  retn
```
