# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x180003570`
- end: `0x1800035a5`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `53`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800018c0`

## callees

- `0x180003570`
- `0x1800035b0`

## pseudocode

```c
HRESULT __fastcall StringCchCopyNW(unsigned __int16 *a1, __int64 a2, size_t *a3, size_t cchToCopy)
{
  HRESULT result; // eax

  if ( cchToCopy <= 0x7FFFFFFE )
    return StringCopyWorkerW(a1, 0x104u, a3, (STRSAFE_PCNZWCH)a3, cchToCopy);
  result = -2147024809;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180003570  sub     rsp, 38h
0x180003574  cmp     r9, 7FFFFFFEh
0x18000357b  ja      short loc_180003595
0x18000357d  mov     [rsp+38h+cchToCopy], r9; cchToCopy
0x180003582  mov     edx, 104h; cchDest
0x180003587  mov     r9, r8; pszSrc
0x18000358a  call    StringCopyWorkerW
0x18000358f  add     rsp, 38h
0x180003593  retn
0x180003595  xor     edx, edx
0x180003597  mov     eax, 80070057h
0x18000359c  mov     [rcx], dx
0x18000359f  add     rsp, 38h
0x1800035a3  retn
```
