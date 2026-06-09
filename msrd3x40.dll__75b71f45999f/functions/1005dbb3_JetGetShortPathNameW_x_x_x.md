# JetGetShortPathNameW(x,x,x)

- ea: `0x1005dbb3`
- end: `0x1005dc82`
- name: `_JetGetShortPathNameW@12`
- size: `207`
- prototype: `int __stdcall(LPCWSTR lpszLongPath, LPWSTR lpszShortPath, DWORD cchBuffer)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1002e9d0`

## callees

- `0x1005d64e`
- `0x1005d67f`
- `0x1005d7a3`
- `0x1005d817`
- `0x1005dbb3`
- `0x1005e3b0`
- `0x1005f064`
- `0x1005f29a`
- `0x1005f2e8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x1005dbd7`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x1005dbd7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetShortPathNameA` at `0x1005dc11`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetShortPathNameA` at `0x1005dc11`

## pseudocode

```c
DWORD __stdcall JetGetShortPathNameW(LPCWSTR lpszLongPath, LPWSTR lpszShortPath, DWORD cchBuffer)
{
  int v3; // esi
  _BYTE v5[4]; // [esp+10h] [ebp-444h] BYREF
  LPCSTR v6; // [esp+14h] [ebp-440h]
  _BYTE v7[4]; // [esp+228h] [ebp-22Ch] BYREF
  LPSTR v8; // [esp+22Ch] [ebp-228h]
  int v9; // [esp+43Ch] [ebp-18h]
  int v10; // [esp+450h] [ebp-4h]

  if ( wrap )
    return GetShortPathNameW(lpszLongPath, lpszShortPath, cchBuffer);
  CStrIn::CStrIn((CStrIn *)v5, lpszLongPath);
  CStrOut::CStrOut((CStrOut *)v7, lpszShortPath, cchBuffer);
  if ( !GetShortPathNameA(v6, v8, (unsigned int)(2 * v9) >> 1) )
  {
    v10 = 0;
    CStrOut::ConvertIncludingNul((CStrOut *)v7);
    CConvertStr::Free((CConvertStr *)v7);
    CConvertStr::Free((CConvertStr *)v5);
    return 0;
  }
  v3 = CStrOut::ConvertIncludingNul((CStrOut *)v7);
  v10 = 1;
  CStrOut::ConvertIncludingNul((CStrOut *)v7);
  CConvertStr::Free((CConvertStr *)v7);
  CConvertStr::Free((CConvertStr *)v5);
  return v3;
}

```

## disassembly

```asm
0x1005dbb3  push    438h
0x1005dbb8  mov     eax, offset loc_10062798
0x1005dbbd  call    __EH_prolog3_GS
0x1005dbc2  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x1005dbc9  mov     eax, [ebp+lpszLongPath]
0x1005dbcc  mov     esi, [ebp+lpszShortPath]
0x1005dbcf  mov     edi, [ebp+cchBuffer]
0x1005dbd2  jz      short loc_1005DBE4
0x1005dbd4  push    edi; cchBuffer
0x1005dbd5  push    esi; lpszShortPath
0x1005dbd6  push    eax; lpszLongPath
0x1005dbd7  call    ds:__imp__GetShortPathNameW@12; GetShortPathNameW(x,x,x)
0x1005dbdd  mov     esi, eax
0x1005dbdf  jmp     loc_1005DC78
0x1005dbe4  push    eax; unsigned __int16 *
0x1005dbe5  lea     ecx, [ebp+var_444]; this
0x1005dbeb  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x1005dbf0  push    edi; int
0x1005dbf1  push    esi; unsigned __int16 *
0x1005dbf2  lea     ecx, [ebp+var_22C]; this
0x1005dbf8  call    ??0CStrOut@@QAE@PAGH@Z; CStrOut::CStrOut(ushort *,int)
0x1005dbfd  mov     eax, [ebp+var_18]
0x1005dc00  add     eax, eax
0x1005dc02  shr     eax, 1
0x1005dc04  push    eax; cchBuffer
0x1005dc05  push    [ebp+var_228]; lpszShortPath
0x1005dc0b  push    [ebp+var_440]; lpszLongPath
0x1005dc11  call    ds:__imp__GetShortPathNameA@12; GetShortPathNameA(x,x,x)
0x1005dc17  test    eax, eax
0x1005dc19  jnz     short loc_1005DC43
0x1005dc1b  lea     ecx, [ebp+var_22C]; this
0x1005dc21  mov     [ebp+var_4], eax
0x1005dc24  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x1005dc29  lea     ecx, [ebp+var_22C]; this
0x1005dc2f  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x1005dc34  lea     ecx, [ebp+var_444]; this
0x1005dc3a  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x1005dc3f  xor     eax, eax
0x1005dc41  jmp     short loc_1005DC7A
0x1005dc43  lea     ecx, [ebp+var_22C]; this
0x1005dc49  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x1005dc4e  mov     esi, eax
0x1005dc50  lea     ecx, [ebp+var_22C]; this
0x1005dc56  mov     [ebp+var_4], 1
0x1005dc5d  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x1005dc62  lea     ecx, [ebp+var_22C]; this
0x1005dc68  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x1005dc6d  lea     ecx, [ebp+var_444]; this
0x1005dc73  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x1005dc78  mov     eax, esi
0x1005dc7a  call    __EH_epilog3_GS
0x1005dc7f  retn    0Ch
0x1005f070  jmp     ds:__imp____std_terminate
0x10062798  nop
0x10062799  nop
0x1006279a  mov     edx, [esp-4+lpszShortPath]
0x1006279e  lea     eax, [edx+0Ch]
0x100627a1  mov     ecx, [edx-448h]
0x100627a7  xor     ecx, eax; StackCookie
0x100627a9  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100627ae  mov     ecx, [edx-4]
0x100627b1  xor     ecx, eax; StackCookie
0x100627b3  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100627b8  mov     eax, offset stru_10062BE4
0x100627bd  jmp     ___CxxFrameHandler3
```
