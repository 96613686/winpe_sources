# PathCchStripToRoot

- ea: `0x1800100a8`
- end: `0x18001014e`
- name: `PathCchStripToRoot`
- size: `166`
- prototype: `HRESULT __stdcall(PWSTR pszPath, size_t cchPath)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x18000741c`
- `0x18000fc8c`

## callees

- `0x180005424`
- `0x18000f6b0`
- `0x18001004c`
- `0x1800100a8`

## pseudocode

```c
HRESULT __stdcall PathCchStripToRoot(PWSTR pszPath, size_t cchPath)
{
  int v4; // r11d
  unsigned __int16 *v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = 0;
  if ( pszPath && cchPath - 1 <= 0x7FFF )
  {
    if ( (int)PathCchSkipRoot(pszPath, &v6) < 0 || v6 >= &pszPath[cchPath] )
      goto LABEL_5;
    if ( *v6 )
    {
      *v6 = 0;
      PathCchRemoveBackslash(pszPath, cchPath);
      return 0;
    }
    v4 = PathCchRemoveBackslash(pszPath, cchPath);
    if ( v4 < 0 )
LABEL_5:
      StringCchCopyW(pszPath, cchPath, (unsigned __int16 *)&dword_18001EDA4);
    return v4;
  }
  return -2147024809;
}

```

## disassembly

```asm
0x1800100a8  mov     r11, rsp
0x1800100ab  mov     [r11+10h], rbx
0x1800100af  mov     [r11+18h], rsi
0x1800100b3  push    rdi
0x1800100b4  sub     rsp, 20h
0x1800100b8  xor     esi, esi
0x1800100ba  mov     rdi, rdx
0x1800100bd  mov     [r11+8], rsi
0x1800100c1  mov     rbx, rcx
0x1800100c4  test    rcx, rcx
0x1800100c7  jz      short loc_180010139
0x1800100c9  lea     rax, [rdx-1]
0x1800100cd  cmp     rax, 7FFFh
0x1800100d3  ja      short loc_180010139
0x1800100d5  lea     rdx, [r11+8]; unsigned __int16 **
0x1800100d9  call    ?PathCchSkipRoot@@YAJPEAGPEAPEAG@Z; PathCchSkipRoot(ushort *,ushort * *)
0x1800100de  mov     r11d, eax
0x1800100e1  test    eax, eax
0x1800100e3  js      short loc_1800100F9
0x1800100e5  mov     rcx, [rsp+28h+arg_0]
0x1800100ea  lea     rax, [rbx+rdi*2]
0x1800100ee  cmp     rcx, rax
0x1800100f1  jb      short loc_180010110
0x1800100f3  mov     r11d, 80070057h
0x1800100f9  lea     r8, dword_18001EDA4; unsigned __int16 *
0x180010100  mov     rdx, rdi; unsigned __int64
0x180010103  mov     rcx, rbx; unsigned __int16 *
0x180010106  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001010b  mov     eax, r11d
0x18001010e  jmp     short loc_18001013E
0x180010110  mov     rdx, rdi; cchPath
0x180010113  cmp     [rcx], si
0x180010116  jnz     short loc_180010129
0x180010118  mov     rcx, rbx; pszPath
0x18001011b  call    PathCchRemoveBackslash
0x180010120  mov     r11d, eax
0x180010123  test    eax, eax
0x180010125  jns     short loc_18001010B
0x180010127  jmp     short loc_1800100F9
0x180010129  mov     [rcx], si
0x18001012c  mov     rcx, rbx; pszPath
0x18001012f  call    PathCchRemoveBackslash
0x180010134  mov     r11d, esi
0x180010137  jmp     short loc_18001010B
0x180010139  mov     eax, 80070057h
0x18001013e  mov     rbx, [rsp+28h+arg_8]
0x180010143  mov     rsi, [rsp+28h+arg_10]
0x180010148  add     rsp, 20h
0x18001014c  pop     rdi
0x18001014d  retn
```
