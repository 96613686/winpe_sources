# ProcessSectionIfExists(void *,ushort const *,ushort const *,ushort const *,int,ushort const *)

- ea: `0x18002ddd0`
- end: `0x18002deaf`
- name: `?ProcessSectionIfExists@@YAJPEAXPEBG11H1@Z`
- size: `223`
- prototype: `int(void *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18002d0d8`
- `0x18002d6f4`
- `0x18002db64`

## callees

- `0x18000b200`
- `0x18002dcd0`
- `0x18002ddd0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002de8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002de8e`
- `KERNEL32!WritePrivateProfileStringW` at `0x18002de6c`
- `KERNEL32!WritePrivateProfileStringW` at `0x18002de6c`

## pseudocode

```c
__int64 __fastcall ProcessSectionIfExists(
        char *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5,
        unsigned __int16 **a6)
{
  int LastErrorAsFailHR; // ebx
  NCoreLibrary *v10; // rcx
  __int64 result; // rax
  LPCWSTR lpString; // [rsp+60h] [rbp+8h] BYREF

  if ( (unsigned __int64)(a1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && a2 && a3 && a4 )
  {
    if ( a6 )
    {
      lpString = 0;
      LastErrorAsFailHR = ProcessSection(a1, a2, (const unsigned __int16 *)a6, a4, a5, (unsigned __int16 **)&lpString);
      if ( LastErrorAsFailHR >= 0 )
      {
        if ( WritePrivateProfileStringW(a3, a4, lpString, a2) )
          LastErrorAsFailHR = 0;
        else
          LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v10);
      }
      if ( lpString )
        LocalFree((HLOCAL)lpString);
    }
    else
    {
      LastErrorAsFailHR = ProcessSection(a1, a2, a3, a4, a5, 0);
    }
  }
  else
  {
    LastErrorAsFailHR = -2147024809;
  }
  result = 0;
  if ( (_WORD)LastErrorAsFailHR != 258 )
    return (unsigned int)LastErrorAsFailHR;
  return result;
}

```

## disassembly

```asm
0x18002ddd0  push    rbx
0x18002ddd2  push    rbp
0x18002ddd3  push    rsi
0x18002ddd4  push    r14
0x18002ddd6  sub     rsp, 38h
0x18002ddda  lea     rax, [rcx-1]
0x18002ddde  mov     rsi, r9
0x18002dde1  mov     r14, r8
0x18002dde4  mov     rbp, rdx
0x18002dde7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ddeb  ja      loc_18002DE96
0x18002ddf1  test    rdx, rdx
0x18002ddf4  jz      loc_18002DE96
0x18002ddfa  test    r8, r8
0x18002ddfd  jz      loc_18002DE96
0x18002de03  test    r9, r9
0x18002de06  jz      loc_18002DE96
0x18002de0c  mov     r8, [rsp+58h+arg_28]; unsigned __int16 *
0x18002de14  test    r8, r8
0x18002de17  jnz     short loc_18002DE35
0x18002de19  mov     eax, [rsp+58h+arg_20]
0x18002de20  mov     [rsp+58h+var_30], r8; unsigned __int16 **
0x18002de25  mov     r8, r14; unsigned __int16 *
0x18002de28  mov     [rsp+58h+var_38], eax; int
0x18002de2c  call    ?ProcessSection@@YAJPEAXPEBG11HPEAPEAG@Z; ProcessSection(void *,ushort const *,ushort const *,ushort const *,int,ushort * *)
0x18002de31  mov     ebx, eax
0x18002de33  jmp     short loc_18002DE9B
0x18002de35  lea     rax, [rsp+58h+lpString]
0x18002de3a  mov     [rsp+58h+lpString], 0
0x18002de43  mov     [rsp+58h+var_30], rax; unsigned __int16 **
0x18002de48  mov     eax, [rsp+58h+arg_20]
0x18002de4f  mov     [rsp+58h+var_38], eax; int
0x18002de53  call    ?ProcessSection@@YAJPEAXPEBG11HPEAPEAG@Z; ProcessSection(void *,ushort const *,ushort const *,ushort const *,int,ushort * *)
0x18002de58  mov     ebx, eax
0x18002de5a  test    eax, eax
0x18002de5c  js      short loc_18002DE81
0x18002de5e  mov     r8, [rsp+58h+lpString]; lpString
0x18002de63  mov     r9, rbp; lpFileName
0x18002de66  mov     rdx, rsi; lpKeyName
0x18002de69  mov     rcx, r14; lpAppName
0x18002de6c  call    cs:__imp_WritePrivateProfileStringW
0x18002de72  test    eax, eax
0x18002de74  jz      short loc_18002DE7A
0x18002de76  xor     ebx, ebx
0x18002de78  jmp     short loc_18002DE81
0x18002de7a  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002de7f  mov     ebx, eax
0x18002de81  cmp     [rsp+58h+lpString], 0
0x18002de87  jz      short loc_18002DE9B
0x18002de89  mov     rcx, [rsp+58h+lpString]; hMem
0x18002de8e  call    cs:__imp_LocalFree
0x18002de94  jmp     short loc_18002DE9B
0x18002de96  mov     ebx, 80070057h
0x18002de9b  xor     eax, eax
0x18002de9d  cmp     bx, 102h
0x18002dea2  cmovnz  eax, ebx
0x18002dea5  add     rsp, 38h
0x18002dea9  pop     r14
0x18002deab  pop     rsi
0x18002deac  pop     rbp
0x18002dead  pop     rbx
0x18002deae  retn
```
