# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140004d68`
- end: `0x140004da5`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140003138`
- `0x140003394`
- `0x140004f44`
- `0x14000566c`

## callees

- `0x140004d68`
- `0x140004e10`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, size_t a2, size_t *a3)
{
  unsigned int v3; // edx
  size_t v5; // [rsp+20h] [rbp-18h]

  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      return (unsigned int)StringCopyWorkerW(a1, a2, a3, (STRSAFE_PCNZWCH)a3, v5);
    }
    else
    {
      v3 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x140004d68  sub     rsp, 38h
0x140004d6c  mov     rax, rdx
0x140004d6f  test    rdx, rdx
0x140004d72  jz      short loc_140004D8F
0x140004d74  cmp     rax, 7FFFFFFFh
0x140004d7a  jbe     short loc_140004D83
0x140004d7c  mov     edx, 80070057h; cchDest
0x140004d81  jmp     short loc_140004D99
0x140004d83  mov     r9, r8; pszSrc
0x140004d86  call    StringCopyWorkerW
0x140004d8b  mov     edx, eax
0x140004d8d  jmp     short loc_140004D9E
0x140004d8f  mov     edx, 80070057h
0x140004d94  test    rax, rax
0x140004d97  jz      short loc_140004D9E
0x140004d99  xor     eax, eax
0x140004d9b  mov     [rcx], ax
0x140004d9e  mov     eax, edx
0x140004da0  add     rsp, 38h
0x140004da4  retn
```
