# JetGetFullPathNameW(x,x,x,x)

- ea: `0x10046e19`
- end: `0x10046ece`
- name: `_JetGetFullPathNameW@16`
- size: `181`
- prototype: `int __stdcall(LPCWSTR lpFileName, DWORD nBufferLength, LPWSTR lpBuffer, LPWSTR *lpFilePart)`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x10050d9b`
- `0x10051376`
- `0x1012035e`
- `0x10121502`

## callees

- `0x100466b3`
- `0x100466e4`
- `0x10046808`
- `0x10046889`
- `0x1004691d`
- `0x10046e19`
- `0x10122f60`
- `0x10123e98`
- `0x10123f79`
- `0x10123fc7`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x10046e92`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x10046e92`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x10046e41`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x10046e41`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x10046e78`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x10046e78`

## pseudocode

```c
DWORD __stdcall JetGetFullPathNameW(LPCWSTR lpFileName, DWORD nBufferLength, LPWSTR lpBuffer, LPWSTR *lpFilePart)
{
  DWORD FullPathNameA; // ebx
  wchar_t *v5; // eax
  LPSTR FilePart; // [esp+10h] [ebp-444h] BYREF
  _BYTE v8[4]; // [esp+14h] [ebp-440h] BYREF
  LPCSTR v9; // [esp+18h] [ebp-43Ch]
  _BYTE v10[4]; // [esp+22Ch] [ebp-228h] BYREF
  LPSTR v11; // [esp+230h] [ebp-224h]
  int v12; // [esp+450h] [ebp-4h]

  if ( wrap )
    return GetFullPathNameW(lpFileName, nBufferLength, lpBuffer, lpFilePart);
  CStrIn::CStrIn((CStrIn *)v8, lpFileName);
  CStrOut::CStrOut((CStrOut *)v10, lpBuffer, nBufferLength);
  FullPathNameA = GetFullPathNameA(v9, nBufferLength, v11, &FilePart);
  CStrOut::ConvertIncludingNul((CStrOut *)v10);
  if ( lpFilePart )
  {
    v5 = _wcsrchr(lpBuffer, 0x5Cu);
    if ( v5 )
      *lpFilePart = v5 + 1;
    else
      *lpFilePart = lpBuffer;
  }
  CStrOut::~CStrOut((CStrOut *)v10);
  v12 = 0;
  CConvertStr::Free((CConvertStr *)v8);
  return FullPathNameA;
}

```

## disassembly

```asm
0x10046e19  push    438h
0x10046e1e  mov     eax, offset loc_10124B49
0x10046e23  call    __EH_prolog3_GS
0x10046e28  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10046e2f  mov     eax, [ebp+lpFileName]
0x10046e32  mov     ebx, [ebp+nBufferLength]
0x10046e35  mov     edi, [ebp+lpBuffer]
0x10046e38  mov     esi, [ebp+lpFilePart]
0x10046e3b  jz      short loc_10046E4B
0x10046e3d  push    esi; lpFilePart
0x10046e3e  push    edi; lpBuffer
0x10046e3f  push    ebx; nBufferLength
0x10046e40  push    eax; lpFileName
0x10046e41  call    ds:__imp__GetFullPathNameW@16; GetFullPathNameW(x,x,x,x)
0x10046e47  mov     ebx, eax
0x10046e49  jmp     short loc_10046EC4
0x10046e4b  push    eax; unsigned __int16 *
0x10046e4c  lea     ecx, [ebp+var_440]; this
0x10046e52  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10046e57  push    ebx; int
0x10046e58  push    edi; unsigned __int16 *
0x10046e59  lea     ecx, [ebp+var_228]; this
0x10046e5f  call    ??0CStrOut@@QAE@PAGH@Z; CStrOut::CStrOut(ushort *,int)
0x10046e64  lea     eax, [ebp+FilePart]
0x10046e6a  push    eax; lpFilePart
0x10046e6b  push    [ebp+var_224]; lpBuffer
0x10046e71  push    ebx; nBufferLength
0x10046e72  push    [ebp+var_43C]; lpFileName
0x10046e78  call    ds:__imp__GetFullPathNameA@16; GetFullPathNameA(x,x,x,x)
0x10046e7e  lea     ecx, [ebp+var_228]; this
0x10046e84  mov     ebx, eax
0x10046e86  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x10046e8b  test    esi, esi
0x10046e8d  jz      short loc_10046EA7
0x10046e8f  push    5Ch ; '\'; Ch
0x10046e91  push    edi; Str
0x10046e92  call    ds:__imp__wcsrchr
0x10046e98  pop     ecx
0x10046e99  pop     ecx
0x10046e9a  test    eax, eax
0x10046e9c  jz      short loc_10046EA5
0x10046e9e  add     eax, 2
0x10046ea1  mov     [esi], eax
0x10046ea3  jmp     short loc_10046EA7
0x10046ea5  mov     [esi], edi
0x10046ea7  lea     ecx, [ebp+var_228]; this
0x10046ead  call    ??1CStrOut@@QAE@XZ; CStrOut::~CStrOut(void)
0x10046eb2  lea     ecx, [ebp+var_440]; this
0x10046eb8  mov     [ebp+var_4], 0
0x10046ebf  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10046ec4  mov     eax, ebx
0x10046ec6  call    __EH_epilog3_GS
0x10046ecb  retn    10h
0x10123eb0  jmp     ds:__imp____std_terminate
0x10124b49  nop
0x10124b4a  nop
0x10124b4b  mov     edx, [esp-4+nBufferLength]
0x10124b4f  lea     eax, [edx+0Ch]
0x10124b52  mov     ecx, [edx-448h]
0x10124b58  xor     ecx, eax; StackCookie
0x10124b5a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124b5f  mov     ecx, [edx-4]
0x10124b62  xor     ecx, eax; StackCookie
0x10124b64  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124b69  mov     eax, offset stru_101278F8
0x10124b6e  jmp     ___CxxFrameHandler3
```
