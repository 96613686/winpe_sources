# JetGetTempFileNameW(x,x,x,x)

- ea: `0x1005d996`
- end: `0x1005da4a`
- name: `_JetGetTempFileNameW@16`
- size: `180`
- prototype: `int __stdcall(LPCWSTR lpPathName, LPCWSTR lpPrefixString, UINT uUnique, LPWSTR lpTempFileName)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1004ed00`

## callees

- `0x1005d64e`
- `0x1005d67f`
- `0x1005d7a3`
- `0x1005d817`
- `0x1005d996`
- `0x1005e3b0`
- `0x1005f064`
- `0x1005f29a`
- `0x1005f2e8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1005d9bd`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1005d9bd`
- `api-ms-win-core-file-l1-2-2!GetTempFileNameA` at `0x1005da05`
- `api-ms-win-core-file-l1-2-2!GetTempFileNameA` at `0x1005da05`

## pseudocode

```c
UINT __stdcall JetGetTempFileNameW(LPCWSTR lpPathName, LPCWSTR lpPrefixString, UINT uUnique, LPWSTR lpTempFileName)
{
  UINT TempFileNameA; // esi
  _BYTE v6[4]; // [esp+10h] [ebp-658h] BYREF
  LPCSTR v7; // [esp+14h] [ebp-654h]
  _BYTE v8[4]; // [esp+228h] [ebp-440h] BYREF
  LPCSTR v9; // [esp+22Ch] [ebp-43Ch]
  _BYTE v10[4]; // [esp+440h] [ebp-228h] BYREF
  LPSTR v11; // [esp+444h] [ebp-224h]
  int v12; // [esp+664h] [ebp-4h]

  if ( wrap )
    return GetTempFileNameW(lpPathName, lpPrefixString, uUnique, lpTempFileName);
  CStrIn::CStrIn((CStrIn *)v6, lpPathName);
  CStrIn::CStrIn((CStrIn *)v8, lpPrefixString);
  CStrOut::CStrOut((CStrOut *)v10, lpTempFileName, 260);
  TempFileNameA = GetTempFileNameA(v7, v9, uUnique, v11);
  v12 = 0;
  CStrOut::ConvertIncludingNul((CStrOut *)v10);
  CConvertStr::Free((CConvertStr *)v10);
  CConvertStr::Free((CConvertStr *)v8);
  CConvertStr::Free((CConvertStr *)v6);
  return TempFileNameA;
}

```

## disassembly

```asm
0x1005d996  push    64Ch
0x1005d99b  mov     eax, offset loc_10062738
0x1005d9a0  call    __EH_prolog3_GS
0x1005d9a5  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x1005d9ac  mov     eax, [ebp+lpPathName]
0x1005d9af  mov     esi, [ebp+lpPrefixString]
0x1005d9b2  mov     edi, [ebp+lpTempFileName]
0x1005d9b5  jz      short loc_1005D9C7
0x1005d9b7  push    edi; lpTempFileName
0x1005d9b8  push    [ebp+uUnique]; uUnique
0x1005d9bb  push    esi; lpPrefixString
0x1005d9bc  push    eax; lpPathName
0x1005d9bd  call    ds:__imp__GetTempFileNameW@16; GetTempFileNameW(x,x,x,x)
0x1005d9c3  mov     esi, eax
0x1005d9c5  jmp     short loc_1005DA40
0x1005d9c7  push    eax; unsigned __int16 *
0x1005d9c8  lea     ecx, [ebp+var_658]; this
0x1005d9ce  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x1005d9d3  push    esi; unsigned __int16 *
0x1005d9d4  lea     ecx, [ebp+var_440]; this
0x1005d9da  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x1005d9df  push    104h; int
0x1005d9e4  push    edi; unsigned __int16 *
0x1005d9e5  lea     ecx, [ebp+var_228]; this
0x1005d9eb  call    ??0CStrOut@@QAE@PAGH@Z; CStrOut::CStrOut(ushort *,int)
0x1005d9f0  push    [ebp+var_224]; lpTempFileName
0x1005d9f6  push    [ebp+uUnique]; uUnique
0x1005d9f9  push    [ebp+var_43C]; lpPrefixString
0x1005d9ff  push    [ebp+var_654]; lpPathName
0x1005da05  call    ds:__imp__GetTempFileNameA@16; GetTempFileNameA(x,x,x,x)
0x1005da0b  mov     esi, eax
0x1005da0d  lea     ecx, [ebp+var_228]; this
0x1005da13  mov     [ebp+var_4], 0
0x1005da1a  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x1005da1f  lea     ecx, [ebp+var_228]; this
0x1005da25  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x1005da2a  lea     ecx, [ebp+var_440]; this
0x1005da30  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x1005da35  lea     ecx, [ebp+var_658]; this
0x1005da3b  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x1005da40  mov     eax, esi
0x1005da42  call    __EH_epilog3_GS
0x1005da47  retn    10h
0x1005f070  jmp     ds:__imp____std_terminate
0x10062738  nop
0x10062739  nop
0x1006273a  mov     edx, [esp-4+lpPrefixString]
0x1006273e  lea     eax, [edx+0Ch]
0x10062741  mov     ecx, [edx-65Ch]
0x10062747  xor     ecx, eax; StackCookie
0x10062749  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1006274e  mov     ecx, [edx-4]
0x10062751  xor     ecx, eax; StackCookie
0x10062753  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10062758  mov     eax, offset stru_10062B00
0x1006275d  jmp     ___CxxFrameHandler3
```
