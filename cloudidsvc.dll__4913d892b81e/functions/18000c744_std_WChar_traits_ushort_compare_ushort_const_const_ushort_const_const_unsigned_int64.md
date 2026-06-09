# std::_WChar_traits<ushort>::compare(ushort const * const,ushort const * const,unsigned __int64)

- ea: `0x18000c744`
- end: `0x18000c749`
- name: `?compare@?$_WChar_traits@G@std@@SAHQEBG0_K@Z`
- size: `5`
- prototype: `int __cdecl(const wchar_t *S1, const wchar_t *S2, size_t N)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800097bc`

## callees

- `0x18000cf44`

## pseudocode

```c
// attributes: thunk
int __cdecl std::_WChar_traits<unsigned short>::compare(const wchar_t *S1, const wchar_t *S2, size_t N)
{
  return wmemcmp(S1, S2, N);
}

```

## disassembly

```asm
0x18000c744  jmp     wmemcmp
```
