# JetGetFullPathNameW(x,x,x,x)

- ea: `0x1005dae5`
- end: `0x1005dba8`
- name: `_JetGetFullPathNameW@16`
- size: `195`
- prototype: `int __stdcall(LPCWSTR lpFileName, DWORD nBufferLength, LPWSTR lpBuffer, LPWSTR *lpFilePart)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1002e140`
- `0x1002e9d0`

## callees

- `0x1005d64e`
- `0x1005d67f`
- `0x1005d7a3`
- `0x1005d817`
- `0x1005dae5`
- `0x1005e3b0`
- `0x1005f064`
- `0x1005f29a`
- `0x1005f2e8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1005db0d`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1005db0d`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1005db47`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1005db47`
- `ntdll!wcsrchr` at `0x1005db61`
- `ntdll!wcsrchr` at `0x1005db61`

## pseudocode

```c
DWORD __stdcall JetGetFullPathNameW(LPCWSTR lpFileName, DWORD nBufferLength, LPWSTR lpBuffer, LPWSTR *lpFilePart)
{
  DWORD FullPathNameA; // ebx
  wchar_t *v5; // eax
  LPSTR FilePart; // [esp+10h] [ebp-448h] BYREF
  _BYTE v8[4]; // [esp+14h] [ebp-444h] BYREF
  LPCSTR v9; // [esp+18h] [ebp-440h]
  _BYTE v10[4]; // [esp+22Ch] [ebp-22Ch] BYREF
  LPSTR v11; // [esp+230h] [ebp-228h]
  int v12; // [esp+454h] [ebp-4h]

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
0x1005dae5  push    43Ch
0x1005daea  mov     eax, offset loc_10062768
0x1005daef  call    __EH_prolog3_GS
0x1005daf4  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x1005dafb  mov     eax, [ebp+lpFileName]
0x1005dafe  mov     ebx, [ebp+nBufferLength]
0x1005db01  mov     edi, [ebp+lpBuffer]
0x1005db04  mov     esi, [ebp+lpFilePart]
0x1005db07  jz      short loc_1005DB1A
0x1005db09  push    esi; lpFilePart
0x1005db0a  push    edi; lpBuffer
0x1005db0b  push    ebx; nBufferLength
0x1005db0c  push    eax; lpFileName
0x1005db0d  call    ds:__imp__GetFullPathNameW@16; GetFullPathNameW(x,x,x,x)
0x1005db13  mov     ebx, eax
0x1005db15  jmp     loc_1005DB9E
0x1005db1a  push    eax; unsigned __int16 *
0x1005db1b  lea     ecx, [ebp+var_444]; this
0x1005db21  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x1005db26  push    ebx; int
0x1005db27  push    edi; unsigned __int16 *
0x1005db28  lea     ecx, [ebp+var_22C]; this
0x1005db2e  call    ??0CStrOut@@QAE@PAGH@Z; CStrOut::CStrOut(ushort *,int)
0x1005db33  lea     eax, [ebp+FilePart]
0x1005db39  push    eax; lpFilePart
0x1005db3a  push    [ebp+var_228]; lpBuffer
0x1005db40  push    ebx; nBufferLength
0x1005db41  push    [ebp+var_440]; lpFileName
0x1005db47  call    ds:__imp__GetFullPathNameA@16; GetFullPathNameA(x,x,x,x)
0x1005db4d  lea     ecx, [ebp+var_22C]; this
0x1005db53  mov     ebx, eax
0x1005db55  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x1005db5a  test    esi, esi
0x1005db5c  jz      short loc_1005DB76
0x1005db5e  push    5Ch ; '\'; Ch
0x1005db60  push    edi; Str
0x1005db61  call    ds:__imp__wcsrchr
0x1005db67  pop     ecx
0x1005db68  pop     ecx
0x1005db69  test    eax, eax
0x1005db6b  jz      short loc_1005DB74
0x1005db6d  add     eax, 2
0x1005db70  mov     [esi], eax
0x1005db72  jmp     short loc_1005DB76
0x1005db74  mov     [esi], edi
0x1005db76  lea     ecx, [ebp+var_22C]; this
0x1005db7c  mov     [ebp+var_4], 0
0x1005db83  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x1005db88  lea     ecx, [ebp+var_22C]; this
0x1005db8e  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x1005db93  lea     ecx, [ebp+var_444]; this
0x1005db99  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x1005db9e  mov     eax, ebx
0x1005dba0  call    __EH_epilog3_GS
0x1005dba5  retn    10h
0x1005f070  jmp     ds:__imp____std_terminate
0x10062768  nop
0x10062769  nop
0x1006276a  mov     edx, [esp-4+nBufferLength]
0x1006276e  lea     eax, [edx+0Ch]
0x10062771  mov     ecx, [edx-44Ch]
0x10062777  xor     ecx, eax; StackCookie
0x10062779  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1006277e  mov     ecx, [edx-4]
0x10062781  xor     ecx, eax; StackCookie
0x10062783  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10062788  mov     eax, offset stru_10062B00
0x1006278d  jmp     ___CxxFrameHandler3
```
