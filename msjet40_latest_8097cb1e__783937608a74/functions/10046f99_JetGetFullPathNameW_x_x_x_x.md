# JetGetFullPathNameW(x,x,x,x)

- ea: `0x10046f99`
- end: `0x1004704e`
- name: `_JetGetFullPathNameW@16`
- size: `181`
- prototype: `int __stdcall(LPCWSTR lpFileName, DWORD nBufferLength, LPWSTR lpBuffer, LPWSTR *lpFilePart)`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x10050f2b`
- `0x10051506`
- `0x1012050e`
- `0x101216b2`

## callees

- `0x10046833`
- `0x10046864`
- `0x10046988`
- `0x10046a09`
- `0x10046a9d`
- `0x10046f99`
- `0x10123110`
- `0x10124048`
- `0x10124129`
- `0x10124177`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x10047012`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x10047012`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x10046fc1`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x10046fc1`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x10046ff8`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x10046ff8`

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
0x10046f99  push    438h
0x10046f9e  mov     eax, offset loc_10124CF9
0x10046fa3  call    __EH_prolog3_GS
0x10046fa8  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10046faf  mov     eax, [ebp+lpFileName]
0x10046fb2  mov     ebx, [ebp+nBufferLength]
0x10046fb5  mov     edi, [ebp+lpBuffer]
0x10046fb8  mov     esi, [ebp+lpFilePart]
0x10046fbb  jz      short loc_10046FCB
0x10046fbd  push    esi; lpFilePart
0x10046fbe  push    edi; lpBuffer
0x10046fbf  push    ebx; nBufferLength
0x10046fc0  push    eax; lpFileName
0x10046fc1  call    ds:__imp__GetFullPathNameW@16; GetFullPathNameW(x,x,x,x)
0x10046fc7  mov     ebx, eax
0x10046fc9  jmp     short loc_10047044
0x10046fcb  push    eax; unsigned __int16 *
0x10046fcc  lea     ecx, [ebp+var_440]; this
0x10046fd2  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10046fd7  push    ebx; int
0x10046fd8  push    edi; unsigned __int16 *
0x10046fd9  lea     ecx, [ebp+var_228]; this
0x10046fdf  call    ??0CStrOut@@QAE@PAGH@Z; CStrOut::CStrOut(ushort *,int)
0x10046fe4  lea     eax, [ebp+FilePart]
0x10046fea  push    eax; lpFilePart
0x10046feb  push    [ebp+var_224]; lpBuffer
0x10046ff1  push    ebx; nBufferLength
0x10046ff2  push    [ebp+var_43C]; lpFileName
0x10046ff8  call    ds:__imp__GetFullPathNameA@16; GetFullPathNameA(x,x,x,x)
0x10046ffe  lea     ecx, [ebp+var_228]; this
0x10047004  mov     ebx, eax
0x10047006  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x1004700b  test    esi, esi
0x1004700d  jz      short loc_10047027
0x1004700f  push    5Ch ; '\'; Ch
0x10047011  push    edi; Str
0x10047012  call    ds:__imp__wcsrchr
0x10047018  pop     ecx
0x10047019  pop     ecx
0x1004701a  test    eax, eax
0x1004701c  jz      short loc_10047025
0x1004701e  add     eax, 2
0x10047021  mov     [esi], eax
0x10047023  jmp     short loc_10047027
0x10047025  mov     [esi], edi
0x10047027  lea     ecx, [ebp+var_228]; this
0x1004702d  call    ??1CStrOut@@QAE@XZ; CStrOut::~CStrOut(void)
0x10047032  lea     ecx, [ebp+var_440]; this
0x10047038  mov     [ebp+var_4], 0
0x1004703f  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10047044  mov     eax, ebx
0x10047046  call    __EH_epilog3_GS
0x1004704b  retn    10h
0x10124060  jmp     ds:__imp____std_terminate
0x10124cf9  nop
0x10124cfa  nop
0x10124cfb  mov     edx, [esp-4+nBufferLength]
0x10124cff  lea     eax, [edx+0Ch]
0x10124d02  mov     ecx, [edx-448h]
0x10124d08  xor     ecx, eax; StackCookie
0x10124d0a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124d0f  mov     ecx, [edx-4]
0x10124d12  xor     ecx, eax; StackCookie
0x10124d14  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124d19  mov     eax, offset stru_10127AA8
0x10124d1e  jmp     ___CxxFrameHandler3
```
