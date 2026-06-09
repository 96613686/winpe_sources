# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180008e5c`
- end: `0x180008e99`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `__int64 __fastcall(unsigned __int16 *, size_t, size_t *)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x180001898`
- `0x180008258`
- `0x180008b54`
- `0x18000cac0`
- `0x18000e8bc`
- `0x180011880`
- `0x180012f28`
- `0x180013a20`
- `0x180019570`
- `0x18001bb38`
- `0x18001bc94`
- `0x18001d264`
- `0x18001d328`
- `0x18001df18`

## callees

- `0x180003c20`
- `0x180008e5c`

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
0x180008e5c  sub     rsp, 38h
0x180008e60  mov     rax, rdx
0x180008e63  test    rdx, rdx
0x180008e66  jz      short loc_180008E83
0x180008e68  cmp     rax, 7FFFFFFFh
0x180008e6e  jbe     short loc_180008E77
0x180008e70  mov     edx, 80070057h; cchDest
0x180008e75  jmp     short loc_180008E8D
0x180008e77  mov     r9, r8; pszSrc
0x180008e7a  call    StringCopyWorkerW
0x180008e7f  mov     edx, eax
0x180008e81  jmp     short loc_180008E92
0x180008e83  mov     edx, 80070057h
0x180008e88  test    rax, rax
0x180008e8b  jz      short loc_180008E92
0x180008e8d  xor     eax, eax
0x180008e8f  mov     [rcx], ax
0x180008e92  mov     eax, edx
0x180008e94  add     rsp, 38h
0x180008e98  retn
```
