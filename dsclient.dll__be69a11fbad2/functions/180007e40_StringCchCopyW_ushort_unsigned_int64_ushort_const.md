# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180007e40`
- end: `0x180007e6f`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `47`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180005074`
- `0x180008358`

## callees

- `0x180007e40`
- `0x180007ec8`
- `0x180007f74`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, __int64 a2, const unsigned __int16 *a3)
{
  size_t v3; // rdx
  wchar_t *v4; // rcx
  size_t *v5; // r8
  HRESULT v6; // r9d
  size_t v8; // [rsp+20h] [rbp-18h]

  v6 = StringValidateDestW(a1, 0x104u, (const size_t)a3);
  if ( v6 < 0 )
    *v4 = 0;
  else
    return (unsigned int)StringCopyWorkerW(v4, v3, v5, (STRSAFE_PCNZWCH)v5, v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180007e40  sub     rsp, 38h
0x180007e44  mov     edx, 104h; cchDest
0x180007e49  call    StringValidateDestW
0x180007e4e  mov     r9d, eax
0x180007e51  test    eax, eax
0x180007e53  js      short loc_180007E62
0x180007e55  mov     r9, r8; pszSrc
0x180007e58  call    StringCopyWorkerW
0x180007e5d  mov     r9d, eax
0x180007e60  jmp     short loc_180007E67
0x180007e62  xor     eax, eax
0x180007e64  mov     [rcx], ax
0x180007e67  mov     eax, r9d
0x180007e6a  add     rsp, 38h
0x180007e6e  retn
```
