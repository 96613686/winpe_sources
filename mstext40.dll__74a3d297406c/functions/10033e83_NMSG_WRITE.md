# __NMSG_WRITE

- ea: `0x10033e83`
- end: `0x1003403f`
- name: `__NMSG_WRITE`
- size: `444`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1002df6a`
- `0x10033b92`
- `0x10033e26`
- `0x10034efc`

## callees

- `0x1002b81a`
- `0x10030880`
- `0x100308ab`
- `0x10030b62`
- `0x10033e5f`
- `0x10033e83`
- `0x10036290`
- `0x1003711c`
- `0x10037188`
- `0x1003a51e`
- `0x1003a55e`

## import_xrefs

- `KERNEL32!WriteFile` at `0x1003401e`
- `KERNEL32!WriteFile` at `0x1003401e`
- `KERNEL32!GetModuleFileNameW` at `0x10033f15`
- `KERNEL32!GetModuleFileNameW` at `0x10033f15`
- `KERNEL32!GetStdHandle` at `0x10033fcf`
- `KERNEL32!GetStdHandle` at `0x10033fcf`

## pseudocode

```c
const wchar_t *__cdecl _NMSG_WRITE(int a1)
{
  const wchar_t *result; // eax
  const wchar_t *v2; // edi
  size_t v3; // eax
  wchar_t *v4; // esi
  unsigned int i; // ecx
  size_t v6; // eax
  DWORD NumberOfBytesWritten; // [esp+8h] [ebp-1FCh] BYREF
  char Str[500]; // [esp+Ch] [ebp-1F8h] BYREF

  result = (const wchar_t *)_GET_RTERRMSG(a1);
  v2 = result;
  if ( result )
  {
    if ( _set_error_mode(3) == 1 || (result = (const wchar_t *)_set_error_mode(3)) == 0 && __app_type == 1 )
    {
      result = (const wchar_t *)GetStdHandle(0xFFFFFFF4);
      v4 = (wchar_t *)result;
      if ( result && result != (const wchar_t *)-1 )
      {
        for ( i = 0; i < 0x1F4; ++i )
        {
          Str[i] = v2[i];
          if ( !v2[i] )
            break;
        }
        Str[499] = 0;
        v6 = strlen(Str);
        return (const wchar_t *)WriteFile(v4, Str, v6, &NumberOfBytesWritten, 0);
      }
    }
    else if ( a1 != 252 )
    {
      if ( wcscpy_s(&Destination, 0x314u, L"Runtime Error!\n\nProgram: ")
        || (word_100449C2 = 0, !GetModuleFileNameW(0, &Filename, 0x104u))
        && wcscpy_s(&Filename, 0x2FBu, L"<program name unknown>")
        || wcslen(&Filename) + 1 > 0x3C
        && (v3 = wcslen(&Filename),
            wcsncpy_s(
              (wchar_t *)&_pnhHeap + v3,
              763 - (((char *)&_pnhHeap + 2 * v3 - (char *)&Filename) >> 1),
              L"...",
              3u))
        || wcscat_s(&Destination, 0x314u, L"\n\n")
        || wcscat_s(&Destination, 0x314u, v2) )
      {
        _invoke_watson(0, 0, 0, 0, 0);
      }
      return (const wchar_t *)__crtMessageBoxW(&Destination, (int)L"Microsoft Visual C++ Runtime Library", 73744);
    }
  }
  return result;
}

```

## disassembly

```asm
0x10033e83  push    ebp
0x10033e84  mov     ebp, esp
0x10033e86  sub     esp, 1FCh
0x10033e8c  mov     eax, ___security_cookie
0x10033e91  xor     eax, ebp
0x10033e93  mov     [ebp+var_4], eax
0x10033e96  push    esi
0x10033e97  mov     esi, [ebp+arg_0]
0x10033e9a  push    edi
0x10033e9b  push    esi
0x10033e9c  call    __GET_RTERRMSG
0x10033ea1  mov     edi, eax
0x10033ea3  pop     ecx
0x10033ea4  test    edi, edi
0x10033ea6  jz      loc_10034025
0x10033eac  push    ebx
0x10033ead  push    3; Mode
0x10033eaf  call    __set_error_mode
0x10033eb4  pop     ecx
0x10033eb5  cmp     eax, 1
0x10033eb8  jz      loc_10033FCD
0x10033ebe  push    3; Mode
0x10033ec0  call    __set_error_mode
0x10033ec5  pop     ecx
0x10033ec6  test    eax, eax
0x10033ec8  jnz     short loc_10033ED7
0x10033eca  cmp     ___app_type, 1
0x10033ed1  jz      loc_10033FCD
0x10033ed7  cmp     esi, 0FCh
0x10033edd  jz      loc_10034024
0x10033ee3  push    offset aRuntimeErrorPr
0x10033ee8  push    314h; SizeInWords
0x10033eed  push    offset Destination; Destination
0x10033ef2  call    _wcscpy_s
0x10033ef7  add     esp, 0Ch
0x10033efa  xor     ebx, ebx
0x10033efc  test    eax, eax
0x10033efe  jnz     loc_10034035
0x10033f04  push    104h; nSize
0x10033f09  push    offset Filename; lpFilename
0x10033f0e  push    ebx; hModule
0x10033f0f  mov     word_100449C2, ax
0x10033f15  call    ds:__imp__GetModuleFileNameW@12
0x10033f1b  mov     esi, 2FBh
0x10033f20  test    eax, eax
0x10033f22  jnz     short loc_10033F3F
0x10033f24  push    offset aProgramNameUnk
0x10033f29  push    esi; SizeInWords
0x10033f2a  push    offset Filename; Destination
0x10033f2f  call    _wcscpy_s
0x10033f34  add     esp, 0Ch
0x10033f37  test    eax, eax
0x10033f39  jnz     loc_10034035
0x10033f3f  push    offset Filename; String
0x10033f44  call    _wcslen
0x10033f49  inc     eax
0x10033f4a  pop     ecx
0x10033f4b  cmp     eax, 3Ch ; '<'
0x10033f4e  jbe     short loc_10033F85
0x10033f50  push    offset Filename; String
0x10033f55  call    _wcslen
0x10033f5a  push    3; MaxCount
0x10033f5c  push    offset asc_10006674
0x10033f61  lea     ecx, ?_pnhHeap@@3P6AHI@ZA[eax*2]
0x10033f68  mov     eax, ecx
0x10033f6a  sub     eax, offset Filename
0x10033f6f  sar     eax, 1
0x10033f71  sub     esi, eax
0x10033f73  push    esi; SizeInWords
0x10033f74  push    ecx; Destination
0x10033f75  call    _wcsncpy_s
0x10033f7a  add     esp, 14h
0x10033f7d  test    eax, eax
0x10033f7f  jnz     loc_10034035
0x10033f85  push    offset asc_1000667C
0x10033f8a  push    314h; SizeInWords
0x10033f8f  mov     esi, offset Destination
0x10033f94  push    esi; Destination
0x10033f95  call    _wcscat_s
0x10033f9a  add     esp, 0Ch
0x10033f9d  test    eax, eax
0x10033f9f  jnz     loc_10034035
0x10033fa5  push    edi; Source
0x10033fa6  push    314h; SizeInWords
0x10033fab  push    esi; Destination
0x10033fac  call    _wcscat_s
0x10033fb1  add     esp, 0Ch
0x10033fb4  test    eax, eax
0x10033fb6  jnz     short loc_10034035
0x10033fb8  push    12010h
0x10033fbd  push    offset aMicrosoftVisua
0x10033fc2  push    esi
0x10033fc3  call    ___crtMessageBoxW
0x10033fc8  add     esp, 0Ch
0x10033fcb  jmp     short loc_10034024
0x10033fcd  push    0FFFFFFF4h; nStdHandle
0x10033fcf  call    ds:__imp__GetStdHandle@4
0x10033fd5  mov     esi, eax
0x10033fd7  test    esi, esi
0x10033fd9  jz      short loc_10034024
0x10033fdb  cmp     esi, 0FFFFFFFFh
0x10033fde  jz      short loc_10034024
0x10033fe0  xor     ebx, ebx
0x10033fe2  mov     ecx, ebx
0x10033fe4  mov     al, [edi+ecx*2]
0x10033fe7  mov     [ebp+ecx+Str], al
0x10033fee  cmp     [edi+ecx*2], bx
0x10033ff2  jz      short loc_10033FFD
0x10033ff4  inc     ecx
0x10033ff5  cmp     ecx, 1F4h
0x10033ffb  jb      short loc_10033FE4
0x10033ffd  push    ebx; lpOverlapped
0x10033ffe  lea     eax, [ebp+NumberOfBytesWritten]
0x10034004  mov     [ebp+var_5], bl
0x10034007  push    eax; lpNumberOfBytesWritten
0x10034008  lea     eax, [ebp+Str]
0x1003400e  push    eax; Str
0x1003400f  call    _strlen
0x10034014  pop     ecx
0x10034015  push    eax; nNumberOfBytesToWrite
0x10034016  lea     eax, [ebp+Str]
0x1003401c  push    eax; lpBuffer
0x1003401d  push    esi; hFile
0x1003401e  call    ds:__imp__WriteFile@20
0x10034024  pop     ebx
0x10034025  mov     ecx, [ebp+var_4]
0x10034028  pop     edi
0x10034029  xor     ecx, ebp; StackCookie
0x1003402b  pop     esi
0x1003402c  call    @__security_check_cookie@4
0x10034031  mov     esp, ebp
0x10034033  pop     ebp
0x10034034  retn
0x10034035  push    ebx; Reserved
0x10034036  push    ebx; LineNo
0x10034037  push    ebx; FileName
0x10034038  push    ebx; FunctionName
0x10034039  push    ebx; Expression
0x1003403a  call    __invoke_watson
```
