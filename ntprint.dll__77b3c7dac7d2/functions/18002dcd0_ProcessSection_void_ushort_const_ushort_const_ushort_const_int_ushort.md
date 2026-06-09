# ProcessSection(void *,ushort const *,ushort const *,ushort const *,int,ushort * *)

- ea: `0x18002dcd0`
- end: `0x18002ddc9`
- name: `?ProcessSection@@YAJPEAXPEBG11HPEAPEAG@Z`
- size: `249`
- prototype: `int(void *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18002dc90`
- `0x18002ddd0`

## callees

- `0x18000b200`
- `0x18002c9fc`
- `0x18002ca6c`
- `0x18002dcd0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dd62`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dda7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dd62`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002dda7`
- `KERNEL32!WritePrivateProfileStringW` at `0x18002dd83`
- `KERNEL32!WritePrivateProfileStringW` at `0x18002dd83`

## pseudocode

```c
__int64 __fastcall ProcessSection(
        char *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5,
        unsigned __int16 **a6)
{
  int LineText; // eax
  unsigned __int16 *v10; // rbx
  int QuotedString; // edi
  NCoreLibrary *v12; // rcx
  HLOCAL hMem; // [rsp+40h] [rbp+8h] BYREF

  hMem = 0;
  if ( (unsigned __int64)(a1 - 1) > 0xFFFFFFFFFFFFFFFDuLL || !a2 || !a3 || !a4 )
    return (unsigned int)-2147024809;
  LineText = GetLineText(a1, a3, a4, (unsigned __int16 **)&hMem);
  v10 = (unsigned __int16 *)hMem;
  QuotedString = LineText;
  if ( LineText >= 0 )
  {
    if ( a5 && hMem )
    {
      hMem = 0;
      QuotedString = GetQuotedString(v10, (unsigned __int16 **)&hMem);
      if ( QuotedString < 0 )
        goto LABEL_15;
      LocalFree(v10);
      v10 = (unsigned __int16 *)hMem;
    }
    if ( a6 )
    {
      *a6 = v10;
      v10 = 0;
    }
    else if ( WritePrivateProfileStringW(a3, a4, v10, a2) )
    {
      QuotedString = 0;
    }
    else
    {
      QuotedString = NCoreLibrary::GetLastErrorAsFailHR(v12);
    }
  }
LABEL_15:
  if ( v10 )
    LocalFree(v10);
  return (unsigned int)QuotedString;
}

```

## disassembly

```asm
0x18002dcd0  mov     r11, rsp
0x18002dcd3  mov     [r11+10h], rbx
0x18002dcd7  mov     [r11+18h], rbp
0x18002dcdb  push    rsi
0x18002dcdc  push    rdi
0x18002dcdd  push    r14
0x18002dcdf  sub     rsp, 20h
0x18002dce3  lea     rax, [rcx-1]
0x18002dce7  mov     qword ptr [r11+8], 0
0x18002dcef  mov     rsi, r9
0x18002dcf2  mov     rbp, r8
0x18002dcf5  mov     r14, rdx
0x18002dcf8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002dcfc  ja      loc_18002DDAF
0x18002dd02  test    rdx, rdx
0x18002dd05  jz      loc_18002DDAF
0x18002dd0b  test    r8, r8
0x18002dd0e  jz      loc_18002DDAF
0x18002dd14  test    r9, r9
0x18002dd17  jz      loc_18002DDAF
0x18002dd1d  lea     r9, [r11+8]; unsigned __int16 **
0x18002dd21  mov     r8, rsi; unsigned __int16 *
0x18002dd24  mov     rdx, rbp; unsigned __int16 *
0x18002dd27  call    ?GetLineText@@YAJPEAXPEBG1PEAPEAG@Z; GetLineText(void *,ushort const *,ushort const *,ushort * *)
0x18002dd2c  mov     rbx, [rsp+38h+hMem]
0x18002dd31  mov     edi, eax
0x18002dd33  test    eax, eax
0x18002dd35  js      short loc_18002DD9F
0x18002dd37  cmp     [rsp+38h+arg_20], 0
0x18002dd3c  jz      short loc_18002DD6D
0x18002dd3e  test    rbx, rbx
0x18002dd41  jz      short loc_18002DD6D
0x18002dd43  lea     rdx, [rsp+38h+hMem]; unsigned __int16 **
0x18002dd48  mov     [rsp+38h+hMem], 0
0x18002dd51  mov     rcx, rbx; unsigned __int16 *
0x18002dd54  call    ?GetQuotedString@@YAJPEBGPEAPEAG@Z; GetQuotedString(ushort const *,ushort * *)
0x18002dd59  mov     edi, eax
0x18002dd5b  test    eax, eax
0x18002dd5d  js      short loc_18002DD9F
0x18002dd5f  mov     rcx, rbx; hMem
0x18002dd62  call    cs:__imp_LocalFree
0x18002dd68  mov     rbx, [rsp+38h+hMem]
0x18002dd6d  mov     rax, [rsp+38h+arg_28]
0x18002dd72  test    rax, rax
0x18002dd75  jnz     short loc_18002DD9A
0x18002dd77  mov     r9, r14; lpFileName
0x18002dd7a  mov     r8, rbx; lpString
0x18002dd7d  mov     rdx, rsi; lpKeyName
0x18002dd80  mov     rcx, rbp; lpAppName
0x18002dd83  call    cs:__imp_WritePrivateProfileStringW
0x18002dd89  test    eax, eax
0x18002dd8b  jz      short loc_18002DD91
0x18002dd8d  xor     edi, edi
0x18002dd8f  jmp     short loc_18002DD9F
0x18002dd91  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002dd96  mov     edi, eax
0x18002dd98  jmp     short loc_18002DD9F
0x18002dd9a  mov     [rax], rbx
0x18002dd9d  xor     ebx, ebx
0x18002dd9f  test    rbx, rbx
0x18002dda2  jz      short loc_18002DDB4
0x18002dda4  mov     rcx, rbx; hMem
0x18002dda7  call    cs:__imp_LocalFree
0x18002ddad  jmp     short loc_18002DDB4
0x18002ddaf  mov     edi, 80070057h
0x18002ddb4  mov     rbx, [rsp+38h+arg_8]
0x18002ddb9  mov     eax, edi
0x18002ddbb  mov     rbp, [rsp+38h+arg_10]
0x18002ddc0  add     rsp, 20h
0x18002ddc4  pop     r14
0x18002ddc6  pop     rdi
0x18002ddc7  pop     rsi
0x18002ddc8  retn
```
