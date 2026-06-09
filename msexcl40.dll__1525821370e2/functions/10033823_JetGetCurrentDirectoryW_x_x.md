# JetGetCurrentDirectoryW(x,x)

- ea: `0x10033823`
- end: `0x10033895`
- name: `_JetGetCurrentDirectoryW@8`
- size: `114`
- prototype: `int __stdcall(DWORD nBufferLength, LPWSTR lpBuffer)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x10026676`

## callees

- `0x10032925`
- `0x10032a7a`
- `0x10032aee`
- `0x10033823`
- `0x10035510`
- `0x10035e9f`
- `0x10036060`
- `0x100360ae`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryA` at `0x10033866`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryA` at `0x10033866`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x10033843`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x10033843`

## pseudocode

```c
DWORD __stdcall JetGetCurrentDirectoryW(DWORD nBufferLength, LPWSTR lpBuffer)
{
  DWORD CurrentDirectoryA; // esi
  _BYTE v4[4]; // [esp+10h] [ebp-228h] BYREF
  LPSTR v5; // [esp+14h] [ebp-224h]
  int v6; // [esp+224h] [ebp-14h]
  int v7; // [esp+234h] [ebp-4h]

  if ( wrap )
    return GetCurrentDirectoryW(nBufferLength, lpBuffer);
  CStrOut::CStrOut((CStrOut *)v4, lpBuffer, nBufferLength);
  CurrentDirectoryA = GetCurrentDirectoryA((unsigned int)(2 * v6) >> 1, v5);
  v7 = 0;
  CStrOut::ConvertIncludingNul((CStrOut *)v4);
  CConvertStr::Free((CConvertStr *)v4);
  return CurrentDirectoryA;
}

```

## disassembly

```asm
0x10033823  push    21Ch
0x10033828  mov     eax, offset loc_10036AF6
0x1003382d  call    __EH_prolog3_GS
0x10033832  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10033839  mov     eax, [ebp+nBufferLength]
0x1003383c  mov     ecx, [ebp+lpBuffer]
0x1003383f  jz      short loc_1003384B
0x10033841  push    ecx; lpBuffer
0x10033842  push    eax; nBufferLength
0x10033843  call    ds:__imp__GetCurrentDirectoryW@8; GetCurrentDirectoryW(x,x)
0x10033849  jmp     short loc_1003388D
0x1003384b  push    eax; int
0x1003384c  push    ecx; unsigned __int16 *
0x1003384d  lea     ecx, [ebp+var_228]; this
0x10033853  call    ??0CStrOut@@QAE@PAGH@Z; CStrOut::CStrOut(ushort *,int)
0x10033858  mov     eax, [ebp+var_14]
0x1003385b  push    [ebp+var_224]; lpBuffer
0x10033861  add     eax, eax
0x10033863  shr     eax, 1
0x10033865  push    eax; nBufferLength
0x10033866  call    ds:__imp__GetCurrentDirectoryA@8; GetCurrentDirectoryA(x,x)
0x1003386c  mov     esi, eax
0x1003386e  lea     ecx, [ebp+var_228]; this
0x10033874  mov     [ebp+var_4], 0
0x1003387b  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x10033880  lea     ecx, [ebp+var_228]; this
0x10033886  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x1003388b  mov     eax, esi
0x1003388d  call    __EH_epilog3_GS
0x10033892  retn    8
0x10035eb0  jmp     ds:__imp____std_terminate
0x10036af6  nop
0x10036af7  nop
0x10036af8  mov     edx, [esp-4+lpFilename]
0x10036afc  lea     eax, [edx+0Ch]
0x10036aff  mov     ecx, [edx-22Ch]
0x10036b05  xor     ecx, eax; StackCookie
0x10036b07  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10036b0c  mov     ecx, [edx-4]
0x10036b0f  xor     ecx, eax; StackCookie
0x10036b11  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10036b16  mov     eax, offset stru_10036C74
0x10036b1b  jmp     ___CxxFrameHandler3
```
