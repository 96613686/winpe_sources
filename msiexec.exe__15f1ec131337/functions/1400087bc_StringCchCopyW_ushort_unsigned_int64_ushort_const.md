# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1400087bc`
- end: `0x140008802`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `70`
- prototype: `__int64 __fastcall(unsigned __int16 *, size_t, size_t *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140003ffc`
- `0x1400064f0`
- `0x140006ad0`
- `0x140006e10`
- `0x140007568`
- `0x1400089f0`
- `0x140008b10`

## callees

- `0x1400087bc`
- `0x14000894c`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, size_t a2, size_t *a3)
{
  unsigned int v3; // edx

  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      return (unsigned int)StringCopyWorkerW(a1, a2, a3, (STRSAFE_PCNZWCH)a3, 0x7FFFFFFEu);
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
0x1400087bc  sub     rsp, 38h
0x1400087c0  mov     rax, rdx
0x1400087c3  test    rdx, rdx
0x1400087c6  jz      short loc_1400087EC
0x1400087c8  cmp     rax, 7FFFFFFFh
0x1400087ce  jbe     short loc_1400087D7
0x1400087d0  mov     edx, 80070057h; cchDest
0x1400087d5  jmp     short loc_1400087F6
0x1400087d7  mov     r9, r8; pszSrc
0x1400087da  mov     [rsp+38h+cchToCopy], 7FFFFFFEh; cchToCopy
0x1400087e3  call    StringCopyWorkerW
0x1400087e8  mov     edx, eax
0x1400087ea  jmp     short loc_1400087FB
0x1400087ec  mov     edx, 80070057h
0x1400087f1  test    rax, rax
0x1400087f4  jz      short loc_1400087FB
0x1400087f6  xor     eax, eax
0x1400087f8  mov     [rcx], ax
0x1400087fb  mov     eax, edx
0x1400087fd  add     rsp, 38h
0x140008801  retn
```
