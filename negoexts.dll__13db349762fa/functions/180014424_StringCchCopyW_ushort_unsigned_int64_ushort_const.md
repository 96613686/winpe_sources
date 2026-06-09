# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180014424`
- end: `0x180014453`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `47`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180010e9c`
- `0x180014970`

## callees

- `0x180014424`
- `0x1800144f8`
- `0x1800145a4`

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
0x180014424  sub     rsp, 38h
0x180014428  mov     edx, 104h; cchDest
0x18001442d  call    StringValidateDestW
0x180014432  mov     r9d, eax
0x180014435  test    eax, eax
0x180014437  js      short loc_180014446
0x180014439  mov     r9, r8; pszSrc
0x18001443c  call    StringCopyWorkerW
0x180014441  mov     r9d, eax
0x180014444  jmp     short loc_18001444B
0x180014446  xor     eax, eax
0x180014448  mov     [rcx], ax
0x18001444b  mov     eax, r9d
0x18001444e  add     rsp, 38h
0x180014452  retn
```
