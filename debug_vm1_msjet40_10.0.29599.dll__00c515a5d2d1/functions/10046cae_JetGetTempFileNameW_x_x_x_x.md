# JetGetTempFileNameW(x,x,x,x)

- ea: `0x10046cae`
- end: `0x10046d5e`
- name: `_JetGetTempFileNameW@16`
- size: `176`
- prototype: `int __stdcall(LPCWSTR lpPathName, LPCWSTR lpPrefixString, UINT uUnique, LPWSTR lpTempFileName)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x10061111`

## callees

- `0x10046833`
- `0x10046864`
- `0x10046988`
- `0x10046a9d`
- `0x10046cae`
- `0x10123110`
- `0x10124048`
- `0x10124129`
- `0x10124177`

## import_xrefs

- `api-ms-win-core-file-l1-2-2!GetTempFileNameA` at `0x10046d1d`
- `api-ms-win-core-file-l1-2-2!GetTempFileNameA` at `0x10046d1d`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x10046cd5`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x10046cd5`

## pseudocode

```c
UINT __stdcall JetGetTempFileNameW(LPCWSTR lpPathName, LPCWSTR lpPrefixString, UINT uUnique, LPWSTR lpTempFileName)
{
  UINT TempFileNameA; // esi
  _BYTE v6[4]; // [esp+10h] [ebp-658h] BYREF
  LPSTR v7; // [esp+14h] [ebp-654h]
  _BYTE v8[4]; // [esp+228h] [ebp-440h] BYREF
  LPCSTR v9; // [esp+22Ch] [ebp-43Ch]
  _BYTE v10[4]; // [esp+440h] [ebp-228h] BYREF
  LPCSTR v11; // [esp+444h] [ebp-224h]
  int v12; // [esp+664h] [ebp-4h]

  if ( wrap )
    return GetTempFileNameW(lpPathName, lpPrefixString, uUnique, lpTempFileName);
  CStrIn::CStrIn((CStrIn *)v8, lpPathName);
  CStrIn::CStrIn((CStrIn *)v10, lpPrefixString);
  CStrOut::CStrOut((CStrOut *)v6, lpTempFileName, 260);
  TempFileNameA = GetTempFileNameA(v9, v11, uUnique, v7);
  CStrOut::~CStrOut((CStrOut *)v6);
  v12 = 0;
  CConvertStr::Free((CConvertStr *)v10);
  v12 = 1;
  CConvertStr::Free((CConvertStr *)v8);
  return TempFileNameA;
}

```

## disassembly

```asm
0x10046cae  push    64Ch
0x10046cb3  mov     eax, offset loc_10124C99
0x10046cb8  call    __EH_prolog3_GS
0x10046cbd  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10046cc4  mov     eax, [ebp+lpPathName]
0x10046cc7  mov     esi, [ebp+lpPrefixString]
0x10046cca  mov     edi, [ebp+lpTempFileName]
0x10046ccd  jz      short loc_10046CDF
0x10046ccf  push    edi; lpTempFileName
0x10046cd0  push    [ebp+uUnique]; uUnique
0x10046cd3  push    esi; lpPrefixString
0x10046cd4  push    eax; lpPathName
0x10046cd5  call    ds:__imp__GetTempFileNameW@16; GetTempFileNameW(x,x,x,x)
0x10046cdb  mov     esi, eax
0x10046cdd  jmp     short loc_10046D54
0x10046cdf  push    eax; unsigned __int16 *
0x10046ce0  lea     ecx, [ebp+var_440]; this
0x10046ce6  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10046ceb  push    esi; unsigned __int16 *
0x10046cec  lea     ecx, [ebp+var_228]; this
0x10046cf2  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10046cf7  push    104h; int
0x10046cfc  push    edi; unsigned __int16 *
0x10046cfd  lea     ecx, [ebp+var_658]; this
0x10046d03  call    ??0CStrOut@@QAE@PAGH@Z; CStrOut::CStrOut(ushort *,int)
0x10046d08  push    [ebp+var_654]; lpTempFileName
0x10046d0e  push    [ebp+uUnique]; uUnique
0x10046d11  push    [ebp+var_224]; lpPrefixString
0x10046d17  push    [ebp+var_43C]; lpPathName
0x10046d1d  call    ds:__imp__GetTempFileNameA@16; GetTempFileNameA(x,x,x,x)
0x10046d23  lea     ecx, [ebp+var_658]; this
0x10046d29  mov     esi, eax
0x10046d2b  call    ??1CStrOut@@QAE@XZ; CStrOut::~CStrOut(void)
0x10046d30  lea     ecx, [ebp+var_228]; this
0x10046d36  mov     [ebp+var_4], 0
0x10046d3d  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10046d42  lea     ecx, [ebp+var_440]; this
0x10046d48  mov     [ebp+var_4], 1
0x10046d4f  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10046d54  mov     eax, esi
0x10046d56  call    __EH_epilog3_GS
0x10046d5b  retn    10h
0x10124060  jmp     ds:__imp____std_terminate
0x10124c99  nop
0x10124c9a  nop
0x10124c9b  mov     edx, [esp-4+lpPrefixString]
0x10124c9f  lea     eax, [edx+0Ch]
0x10124ca2  mov     ecx, [edx-65Ch]
0x10124ca8  xor     ecx, eax; StackCookie
0x10124caa  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124caf  mov     ecx, [edx-4]
0x10124cb2  xor     ecx, eax; StackCookie
0x10124cb4  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124cb9  mov     eax, offset stru_10127AD4
0x10124cbe  jmp     ___CxxFrameHandler3
```
