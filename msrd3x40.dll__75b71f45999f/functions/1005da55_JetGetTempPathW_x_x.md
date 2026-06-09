# JetGetTempPathW(x,x)

- ea: `0x1005da55`
- end: `0x1005dada`
- name: `_JetGetTempPathW@8`
- size: `133`
- prototype: `int __stdcall(DWORD nBufferLength, LPWSTR lpBuffer)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1004ed00`

## callees

- `0x1005d64e`
- `0x1005d7a3`
- `0x1005d817`
- `0x1005da55`
- `0x1005e3b0`
- `0x1005f064`
- `0x1005f29a`
- `0x1005f2e8`

## import_xrefs

- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1005da75`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1005da75`
- `api-ms-win-core-file-l1-2-2!GetTempPathA` at `0x1005da9a`
- `api-ms-win-core-file-l1-2-2!GetTempPathA` at `0x1005da9a`

## pseudocode

```c
DWORD __stdcall JetGetTempPathW(DWORD nBufferLength, LPWSTR lpBuffer)
{
  int v2; // esi
  int v3; // eax
  _BYTE v5[4]; // [esp+10h] [ebp-228h] BYREF
  LPSTR v6; // [esp+14h] [ebp-224h]
  int v7; // [esp+224h] [ebp-14h]
  int v8; // [esp+234h] [ebp-4h]

  if ( wrap )
    return GetTempPathW(nBufferLength, lpBuffer);
  CStrOut::CStrOut((CStrOut *)v5, lpBuffer, nBufferLength);
  GetTempPathA((unsigned int)(2 * v7) >> 1, v6);
  v3 = CStrOut::ConvertIncludingNul((CStrOut *)v5);
  v2 = v3 - 1;
  if ( v3 <= 0 )
    v2 = v3;
  v8 = 0;
  CStrOut::ConvertIncludingNul((CStrOut *)v5);
  CConvertStr::Free((CConvertStr *)v5);
  return v2;
}

```

## disassembly

```asm
0x1005da55  push    21Ch
0x1005da5a  mov     eax, offset loc_10062708
0x1005da5f  call    __EH_prolog3_GS
0x1005da64  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x1005da6b  mov     eax, [ebp+nBufferLength]
0x1005da6e  mov     ecx, [ebp+lpBuffer]
0x1005da71  jz      short loc_1005DA7F
0x1005da73  push    ecx; lpBuffer
0x1005da74  push    eax; nBufferLength
0x1005da75  call    ds:__imp__GetTempPathW@8; GetTempPathW(x,x)
0x1005da7b  mov     esi, eax
0x1005da7d  jmp     short loc_1005DAD0
0x1005da7f  push    eax; int
0x1005da80  push    ecx; unsigned __int16 *
0x1005da81  lea     ecx, [ebp+var_228]; this
0x1005da87  call    ??0CStrOut@@QAE@PAGH@Z; CStrOut::CStrOut(ushort *,int)
0x1005da8c  mov     eax, [ebp+var_14]
0x1005da8f  push    [ebp+var_224]; lpBuffer
0x1005da95  add     eax, eax
0x1005da97  shr     eax, 1
0x1005da99  push    eax; nBufferLength
0x1005da9a  call    ds:__imp__GetTempPathA@8; GetTempPathA(x,x)
0x1005daa0  lea     ecx, [ebp+var_228]; this
0x1005daa6  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x1005daab  test    eax, eax
0x1005daad  lea     esi, [eax-1]
0x1005dab0  cmovle  esi, eax
0x1005dab3  lea     ecx, [ebp+var_228]; this
0x1005dab9  mov     [ebp+var_4], 0
0x1005dac0  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x1005dac5  lea     ecx, [ebp+var_228]; this
0x1005dacb  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x1005dad0  mov     eax, esi
0x1005dad2  call    __EH_epilog3_GS
0x1005dad7  retn    8
0x1005f070  jmp     ds:__imp____std_terminate
0x10062708  nop
0x10062709  nop
0x1006270a  mov     edx, [esp-4+lpFilename]
0x1006270e  lea     eax, [edx+0Ch]
0x10062711  mov     ecx, [edx-22Ch]
0x10062717  xor     ecx, eax; StackCookie
0x10062719  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1006271e  mov     ecx, [edx-4]
0x10062721  xor     ecx, eax; StackCookie
0x10062723  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10062728  mov     eax, offset stru_10062B00
0x1006272d  jmp     ___CxxFrameHandler3
```
