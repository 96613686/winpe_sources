# StringCbCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140011db8`
- end: `0x140011e04`
- name: `?StringCbCopyW@@YAJPEAG_KPEBG@Z`
- size: `76`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140013530`

## callees

- `0x140011db8`
- `0x140011f54`

## pseudocode

```c
__int64 __fastcall StringCbCopyW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3)
{
  unsigned int v3; // edx

  if ( a2 >> 1 )
  {
    if ( a2 >> 1 <= 0x7FFFFFFF )
    {
      return (unsigned int)StringCopyWorkerW_0(a1, a2 >> 1, 0, a3, 0x7FFFFFFEu);
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
0x140011db8  sub     rsp, 38h
0x140011dbc  mov     rax, rdx
0x140011dbf  shr     rax, 1
0x140011dc2  jz      short loc_140011DEE
0x140011dc4  cmp     rax, 7FFFFFFFh
0x140011dca  jbe     short loc_140011DD3
0x140011dcc  mov     edx, 80070057h
0x140011dd1  jmp     short loc_140011DF8
0x140011dd3  mov     r9, r8; pszSrc
0x140011dd6  mov     [rsp+38h+cchToCopy], 7FFFFFFEh; cchToCopy
0x140011ddf  xor     r8d, r8d; pcchNewDestLength
0x140011de2  mov     rdx, rax; cchDest
0x140011de5  call    StringCopyWorkerW_0
0x140011dea  mov     edx, eax
0x140011dec  jmp     short loc_140011DFD
0x140011dee  mov     edx, 80070057h
0x140011df3  test    rax, rax
0x140011df6  jz      short loc_140011DFD
0x140011df8  xor     eax, eax
0x140011dfa  mov     [rcx], ax
0x140011dfd  mov     eax, edx
0x140011dff  add     rsp, 38h
0x140011e03  retn
```
