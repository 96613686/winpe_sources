# SQLWritePrivateProfileString

- ea: `0x18000fdd0`
- end: `0x18000fea2`
- name: `SQLWritePrivateProfileString`
- size: `210`
- prototype: `BOOL __stdcall(LPCSTR lpszSection, LPCSTR lpszEntry, LPCSTR lpszString, LPCSTR lpszFilename)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002940`
- `0x18000a320`
- `0x18000fdd0`
- `0x1800138e4`

## pseudocode

```c
BOOL __stdcall SQLWritePrivateProfileString(
        LPCSTR lpszSection,
        LPCSTR lpszEntry,
        LPCSTR lpszString,
        LPCSTR lpszFilename)
{
  WCHAR *v4; // rbx
  BOOL v8; // edi
  int v9; // eax
  LPCWSTR lpszFilenamea; // [rsp+20h] [rbp-28h] BYREF
  LPCWSTR lpszSectiona; // [rsp+28h] [rbp-20h] BYREF
  LPCWSTR lpszEntrya; // [rsp+30h] [rbp-18h] BYREF
  LPCWSTR lpszStringa; // [rsp+38h] [rbp-10h] BYREF

  v4 = 0;
  lpszSectiona = 0;
  lpszEntrya = 0;
  lpszStringa = 0;
  lpszFilenamea = 0;
  v8 = 0;
  if ( (unsigned int)GWConvertToUnicode(lpszSection, (WCHAR **)&lpszSectiona, 0xFFFFFFFD) )
  {
    if ( (unsigned int)GWConvertToUnicode(lpszEntry, (WCHAR **)&lpszEntrya, 0xFFFFFFFD) )
    {
      if ( (unsigned int)GWConvertToUnicode(lpszString, (WCHAR **)&lpszStringa, 0xFFFFFFFD) )
      {
        v9 = GWConvertToUnicode(lpszFilename, (WCHAR **)&lpszFilenamea, 0xFFFFFFFD);
        v4 = (WCHAR *)lpszFilenamea;
        if ( v9 )
          v8 = SQLWritePrivateProfileStringW(lpszSectiona, lpszEntrya, lpszStringa, lpszFilenamea);
      }
    }
  }
  OFree((void *)lpszSectiona);
  OFree((void *)lpszEntrya);
  OFree((void *)lpszStringa);
  OFree(v4);
  return v8;
}

```

## disassembly

```asm
0x18000fdd0  push    rbp
0x18000fdd2  push    rbx
0x18000fdd3  push    rsi
0x18000fdd4  push    rdi
0x18000fdd5  push    r14
0x18000fdd7  push    r15
0x18000fdd9  mov     rbp, rsp
0x18000fddc  sub     rsp, 48h
0x18000fde0  xor     ebx, ebx
0x18000fde2  mov     [rbp+lpszSection], 0
0x18000fdea  mov     r15, r8
0x18000fded  mov     [rbp+lpszEntry], 0
0x18000fdf5  mov     rsi, rdx
0x18000fdf8  mov     [rbp+lpszString], 0
0x18000fe00  lea     rdx, [rbp+lpszSection]
0x18000fe04  mov     [rbp+lpszFilename], rbx
0x18000fe08  lea     r8d, [rbx-3]
0x18000fe0c  mov     r14, r9
0x18000fe0f  xor     edi, edi
0x18000fe11  call    GWConvertToUnicode
0x18000fe16  test    eax, eax
0x18000fe18  jz      short loc_18000FE70
0x18000fe1a  lea     r8d, [rbx-3]
0x18000fe1e  mov     rcx, rsi; lpMultiByteStr
0x18000fe21  lea     rdx, [rbp+lpszEntry]
0x18000fe25  call    GWConvertToUnicode
0x18000fe2a  test    eax, eax
0x18000fe2c  jz      short loc_18000FE70
0x18000fe2e  lea     r8d, [rbx-3]
0x18000fe32  mov     rcx, r15; lpMultiByteStr
0x18000fe35  lea     rdx, [rbp+lpszString]
0x18000fe39  call    GWConvertToUnicode
0x18000fe3e  test    eax, eax
0x18000fe40  jz      short loc_18000FE70
0x18000fe42  lea     r8d, [rbx-3]
0x18000fe46  mov     rcx, r14; lpMultiByteStr
0x18000fe49  lea     rdx, [rbp+lpszFilename]
0x18000fe4d  call    GWConvertToUnicode
0x18000fe52  mov     rbx, [rbp+lpszFilename]
0x18000fe56  test    eax, eax
0x18000fe58  jz      short loc_18000FE70
0x18000fe5a  mov     r8, [rbp+lpszString]; lpszString
0x18000fe5e  mov     r9, rbx; lpszFilename
0x18000fe61  mov     rdx, [rbp+lpszEntry]; lpszEntry
0x18000fe65  mov     rcx, [rbp+lpszSection]; lpszSection
0x18000fe69  call    SQLWritePrivateProfileStringW
0x18000fe6e  mov     edi, eax
0x18000fe70  mov     rcx, [rbp+lpszSection]
0x18000fe74  call    OFree
0x18000fe79  mov     rcx, [rbp+lpszEntry]
0x18000fe7d  call    OFree
0x18000fe82  mov     rcx, [rbp+lpszString]
0x18000fe86  call    OFree
0x18000fe8b  mov     rcx, rbx
0x18000fe8e  call    OFree
0x18000fe93  mov     eax, edi
0x18000fe95  add     rsp, 48h
0x18000fe99  pop     r15
0x18000fe9b  pop     r14
0x18000fe9d  pop     rdi
0x18000fe9e  pop     rsi
0x18000fe9f  pop     rbx
0x18000fea0  pop     rbp
0x18000fea1  retn
```
