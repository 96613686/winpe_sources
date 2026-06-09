# StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)

- ea: `0x140005bf0`
- end: `0x140005c3c`
- name: `?StringCchCatW@@YAJPEA_W_KPEB_W@Z`
- size: `76`
- prototype: `int __fastcall(wchar_t *, size_t, const wchar_t *, size_t)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140004190`
- `0x140005f40`
- `0x140010d34`
- `0x140011100`
- `0x1400244a0`

## callees

- `0x140005bf0`
- `0x140005d70`
- `0x140005e38`

## pseudocode

```c
int __fastcall StringCchCatW(wchar_t *a1, size_t a2, const wchar_t *a3, size_t a4)
{
  int result; // eax
  size_t *v7; // r8
  __int64 v8; // r11
  size_t v9; // [rsp+20h] [rbp-18h]
  size_t pcchDestLength; // [rsp+58h] [rbp+20h] BYREF

  pcchDestLength = 0;
  result = StringValidateDestAndLengthW(a1, a2, &pcchDestLength, a4);
  if ( result >= 0 )
    return StringCopyWorkerW(&a1[pcchDestLength], v8 - pcchDestLength, v7, a3, v9);
  return result;
}

```

## disassembly

```asm
0x140005bf0  mov     [rsp+arg_0], rbx
0x140005bf5  push    rdi
0x140005bf6  sub     rsp, 30h
0x140005bfa  mov     rdi, r8
0x140005bfd  mov     [rsp+38h+pcchDestLength], 0
0x140005c06  lea     r8, [rsp+38h+pcchDestLength]; pcchDestLength
0x140005c0b  mov     r11, rdx
0x140005c0e  mov     rbx, rcx
0x140005c11  call    StringValidateDestAndLengthW
0x140005c16  test    eax, eax
0x140005c18  js      short loc_140005C31
0x140005c1a  mov     rax, [rsp+38h+pcchDestLength]
0x140005c1f  mov     r9, rdi; pszSrc
0x140005c22  sub     r11, rax
0x140005c25  mov     rdx, r11; cchDest
0x140005c28  lea     rcx, [rbx+rax*2]; pszDest
0x140005c2c  call    StringCopyWorkerW
0x140005c31  mov     rbx, [rsp+38h+arg_0]
0x140005c36  add     rsp, 30h
0x140005c3a  pop     rdi
0x140005c3b  retn
```
