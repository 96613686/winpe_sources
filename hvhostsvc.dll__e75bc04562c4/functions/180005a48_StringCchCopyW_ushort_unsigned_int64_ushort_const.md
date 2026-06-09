# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005a48`
- end: `0x180005a77`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `47`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180003c14`
- `0x180005cc8`

## callees

- `0x180005a48`
- `0x180005b58`
- `0x180005c04`

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
0x180005a48  sub     rsp, 38h
0x180005a4c  mov     edx, 104h; cchDest
0x180005a51  call    StringValidateDestW
0x180005a56  mov     r9d, eax
0x180005a59  test    eax, eax
0x180005a5b  js      short loc_180005A6A
0x180005a5d  mov     r9, r8; pszSrc
0x180005a60  call    StringCopyWorkerW
0x180005a65  mov     r9d, eax
0x180005a68  jmp     short loc_180005A6F
0x180005a6a  xor     eax, eax
0x180005a6c  mov     [rcx], ax
0x180005a6f  mov     eax, r9d
0x180005a72  add     rsp, 38h
0x180005a76  retn
```
