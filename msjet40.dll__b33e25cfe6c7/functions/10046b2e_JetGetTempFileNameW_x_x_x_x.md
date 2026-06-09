# JetGetTempFileNameW(x,x,x,x)

- ea: `0x10046b2e`
- end: `0x10046bde`
- name: `_JetGetTempFileNameW@16`
- size: `176`
- prototype: `int __stdcall(LPCWSTR lpPathName, LPCWSTR lpPrefixString, UINT uUnique, LPWSTR lpTempFileName)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x10060f7d`

## callees

- `0x100466b3`
- `0x100466e4`
- `0x10046808`
- `0x1004691d`
- `0x10046b2e`
- `0x10122f60`
- `0x10123e98`
- `0x10123f79`
- `0x10123fc7`

## import_xrefs

- `api-ms-win-core-file-l1-2-2!GetTempFileNameA` at `0x10046b9d`
- `api-ms-win-core-file-l1-2-2!GetTempFileNameA` at `0x10046b9d`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x10046b55`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x10046b55`

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
0x10046b2e  push    64Ch
0x10046b33  mov     eax, offset loc_10124AE9
0x10046b38  call    __EH_prolog3_GS
0x10046b3d  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10046b44  mov     eax, [ebp+lpPathName]
0x10046b47  mov     esi, [ebp+lpPrefixString]
0x10046b4a  mov     edi, [ebp+lpTempFileName]
0x10046b4d  jz      short loc_10046B5F
0x10046b4f  push    edi; lpTempFileName
0x10046b50  push    [ebp+uUnique]; uUnique
0x10046b53  push    esi; lpPrefixString
0x10046b54  push    eax; lpPathName
0x10046b55  call    ds:__imp__GetTempFileNameW@16; GetTempFileNameW(x,x,x,x)
0x10046b5b  mov     esi, eax
0x10046b5d  jmp     short loc_10046BD4
0x10046b5f  push    eax; unsigned __int16 *
0x10046b60  lea     ecx, [ebp+var_440]; this
0x10046b66  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10046b6b  push    esi; unsigned __int16 *
0x10046b6c  lea     ecx, [ebp+var_228]; this
0x10046b72  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10046b77  push    104h; int
0x10046b7c  push    edi; unsigned __int16 *
0x10046b7d  lea     ecx, [ebp+var_658]; this
0x10046b83  call    ??0CStrOut@@QAE@PAGH@Z; CStrOut::CStrOut(ushort *,int)
0x10046b88  push    [ebp+var_654]; lpTempFileName
0x10046b8e  push    [ebp+uUnique]; uUnique
0x10046b91  push    [ebp+var_224]; lpPrefixString
0x10046b97  push    [ebp+var_43C]; lpPathName
0x10046b9d  call    ds:__imp__GetTempFileNameA@16; GetTempFileNameA(x,x,x,x)
0x10046ba3  lea     ecx, [ebp+var_658]; this
0x10046ba9  mov     esi, eax
0x10046bab  call    ??1CStrOut@@QAE@XZ; CStrOut::~CStrOut(void)
0x10046bb0  lea     ecx, [ebp+var_228]; this
0x10046bb6  mov     [ebp+var_4], 0
0x10046bbd  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10046bc2  lea     ecx, [ebp+var_440]; this
0x10046bc8  mov     [ebp+var_4], 1
0x10046bcf  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10046bd4  mov     eax, esi
0x10046bd6  call    __EH_epilog3_GS
0x10046bdb  retn    10h
0x10123eb0  jmp     ds:__imp____std_terminate
0x10124ae9  nop
0x10124aea  nop
0x10124aeb  mov     edx, [esp-4+lpPrefixString]
0x10124aef  lea     eax, [edx+0Ch]
0x10124af2  mov     ecx, [edx-65Ch]
0x10124af8  xor     ecx, eax; StackCookie
0x10124afa  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124aff  mov     ecx, [edx-4]
0x10124b02  xor     ecx, eax; StackCookie
0x10124b04  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124b09  mov     eax, offset stru_10127924
0x10124b0e  jmp     ___CxxFrameHandler3
```
