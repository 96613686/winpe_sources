# StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)

- ea: `0x180005e60`
- end: `0x180005e9e`
- name: `?StringCchCopyW@@YAJPEA_W_KPEB_W@Z`
- size: `62`
- prototype: `int(wchar_t *, unsigned __int64, const wchar_t *)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x180004008`
- `0x180006038`
- `0x180007a68`
- `0x180009578`
- `0x180009980`
- `0x18000a01c`
- `0x18000ab50`
- `0x18000f400`
- `0x18000fa40`
- `0x180010470`
- `0x180012d1c`
- `0x180013bec`
- `0x180013ce0`
- `0x180013e00`
- `0x180017c78`
- `0x1800188c0`

## callees

- `0x180005e60`
- `0x180005f08`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(wchar_t *a1, size_t a2, wchar_t *a3)
{
  unsigned int v3; // edx
  size_t v5; // [rsp+20h] [rbp-18h]

  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      return (unsigned int)StringCopyWorkerW(a1, a2, (size_t *)a3, a3, v5);
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
0x180005e60  sub     rsp, 38h
0x180005e64  mov     rax, rdx
0x180005e67  test    rdx, rdx
0x180005e6a  jz      short loc_180005E87
0x180005e6c  cmp     rax, 7FFFFFFFh
0x180005e72  jbe     short loc_180005E7B
0x180005e74  mov     edx, 80070057h; cchDest
0x180005e79  jmp     short loc_180005E91
0x180005e7b  mov     r9, r8; pszSrc
0x180005e7e  call    StringCopyWorkerW
0x180005e83  mov     edx, eax
0x180005e85  jmp     short loc_180005E96
0x180005e87  mov     edx, 80070057h
0x180005e8c  test    rax, rax
0x180005e8f  jz      short loc_180005E96
0x180005e91  xor     eax, eax
0x180005e93  mov     [rcx], ax
0x180005e96  mov     eax, edx
0x180005e98  add     rsp, 38h
0x180005e9c  retn
```
