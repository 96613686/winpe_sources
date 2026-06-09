# JetGetFullPathNameW(x,x,x,x)

- ea: `0x10032fa0`
- end: `0x10033063`
- name: `_JetGetFullPathNameW@16`
- size: `195`
- prototype: `int __stdcall(LPCWSTR lpFileName, DWORD nBufferLength, LPWSTR lpBuffer, LPWSTR *lpFilePart)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x10011280`
- `0x100158d0`

## callees

- `0x10032925`
- `0x10032956`
- `0x10032a7a`
- `0x10032aee`
- `0x10032fa0`
- `0x10035510`
- `0x10035e9f`
- `0x10036060`
- `0x100360ae`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1003301c`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1003301c`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x10033002`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x10033002`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x10032fc8`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x10032fc8`

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
  v12 = 0;
  CStrOut::ConvertIncludingNul((CStrOut *)v10);
  CConvertStr::Free((CConvertStr *)v10);
  CConvertStr::Free((CConvertStr *)v8);
  return FullPathNameA;
}

```

## disassembly

```asm
0x10032fa0  push    438h
0x10032fa5  mov     eax, offset loc_10036B26
0x10032faa  call    __EH_prolog3_GS
0x10032faf  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10032fb6  mov     eax, [ebp+lpFileName]
0x10032fb9  mov     ebx, [ebp+nBufferLength]
0x10032fbc  mov     edi, [ebp+lpBuffer]
0x10032fbf  mov     esi, [ebp+lpFilePart]
0x10032fc2  jz      short loc_10032FD5
0x10032fc4  push    esi; lpFilePart
0x10032fc5  push    edi; lpBuffer
0x10032fc6  push    ebx; nBufferLength
0x10032fc7  push    eax; lpFileName
0x10032fc8  call    ds:__imp__GetFullPathNameW@16; GetFullPathNameW(x,x,x,x)
0x10032fce  mov     ebx, eax
0x10032fd0  jmp     loc_10033059
0x10032fd5  push    eax; unsigned __int16 *
0x10032fd6  lea     ecx, [ebp+var_440]; this
0x10032fdc  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10032fe1  push    ebx; int
0x10032fe2  push    edi; unsigned __int16 *
0x10032fe3  lea     ecx, [ebp+var_228]; this
0x10032fe9  call    ??0CStrOut@@QAE@PAGH@Z; CStrOut::CStrOut(ushort *,int)
0x10032fee  lea     eax, [ebp+FilePart]
0x10032ff4  push    eax; lpFilePart
0x10032ff5  push    [ebp+var_224]; lpBuffer
0x10032ffb  push    ebx; nBufferLength
0x10032ffc  push    [ebp+var_43C]; lpFileName
0x10033002  call    ds:__imp__GetFullPathNameA@16; GetFullPathNameA(x,x,x,x)
0x10033008  lea     ecx, [ebp+var_228]; this
0x1003300e  mov     ebx, eax
0x10033010  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x10033015  test    esi, esi
0x10033017  jz      short loc_10033031
0x10033019  push    5Ch ; '\'; Ch
0x1003301b  push    edi; Str
0x1003301c  call    ds:__imp__wcsrchr
0x10033022  pop     ecx
0x10033023  pop     ecx
0x10033024  test    eax, eax
0x10033026  jz      short loc_1003302F
0x10033028  add     eax, 2
0x1003302b  mov     [esi], eax
0x1003302d  jmp     short loc_10033031
0x1003302f  mov     [esi], edi
0x10033031  lea     ecx, [ebp+var_228]; this
0x10033037  mov     [ebp+var_4], 0
0x1003303e  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x10033043  lea     ecx, [ebp+var_228]; this
0x10033049  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x1003304e  lea     ecx, [ebp+var_440]; this
0x10033054  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10033059  mov     eax, ebx
0x1003305b  call    __EH_epilog3_GS
0x10033060  retn    10h
0x10035eb0  jmp     ds:__imp____std_terminate
0x10036b26  nop
0x10036b27  nop
0x10036b28  mov     edx, [esp-4+nBufferLength]
0x10036b2c  lea     eax, [edx+0Ch]
0x10036b2f  mov     ecx, [edx-448h]
0x10036b35  xor     ecx, eax; StackCookie
0x10036b37  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10036b3c  mov     ecx, [edx-4]
0x10036b3f  xor     ecx, eax; StackCookie
0x10036b41  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10036b46  mov     eax, offset stru_10036C74
0x10036b4b  jmp     ___CxxFrameHandler3
```
