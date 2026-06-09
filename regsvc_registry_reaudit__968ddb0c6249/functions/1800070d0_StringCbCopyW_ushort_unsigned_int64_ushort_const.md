# StringCbCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800070d0`
- end: `0x1800070fc`
- name: `?StringCbCopyW@@YAJPEAG_KPEBG@Z`
- size: `44`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180003b40`
- `0x1800044a0`
- `0x180004b00`
- `0x18000c424`
- `0x18000d534`
- `0x180014b54`
- `0x180015250`
- `0x180015e20`

## callees

- `0x1800070d0`
- `0x180007104`
- `0x180007120`

## pseudocode

```c
int __fastcall StringCbCopyW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3)
{
  int result; // eax
  size_t v4; // rdx
  wchar_t *v5; // rcx
  size_t *v6; // r8
  size_t v7; // [rsp+20h] [rbp-18h]

  result = StringValidateDestW(a1, a2 >> 1, (const size_t)a3);
  if ( result >= 0 )
    return StringCopyWorkerW(v5, v4, v6, (STRSAFE_PCNZWCH)v6, v7);
  if ( v4 )
    *v5 = 0;
  return result;
}

```

## disassembly

```asm
0x1800070d0  sub     rsp, 38h
0x1800070d4  shr     rdx, 1; cchDest
0x1800070d7  call    StringValidateDestW
0x1800070dc  test    eax, eax
0x1800070de  js      short loc_1800070ED
0x1800070e0  mov     r9, r8; pszSrc
0x1800070e3  call    StringCopyWorkerW
0x1800070e8  add     rsp, 38h
0x1800070ec  retn
0x1800070ed  test    rdx, rdx
0x1800070f0  jz      short loc_1800070F7
0x1800070f2  xor     edx, edx
0x1800070f4  mov     [rcx], dx
0x1800070f7  add     rsp, 38h
0x1800070fb  retn
```
