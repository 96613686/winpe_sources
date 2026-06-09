# JetGetTempPathW(x,x)

- ea: `0x10032f10`
- end: `0x10032f95`
- name: `_JetGetTempPathW@8`
- size: `133`
- prototype: `int __stdcall(DWORD nBufferLength, LPWSTR lpBuffer)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x10022890`

## callees

- `0x10032925`
- `0x10032a7a`
- `0x10032aee`
- `0x10032f10`
- `0x10035510`
- `0x10035e9f`
- `0x10036060`
- `0x100360ae`

## import_xrefs

- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x10032f30`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x10032f30`
- `api-ms-win-core-file-l1-2-2!GetTempPathA` at `0x10032f55`
- `api-ms-win-core-file-l1-2-2!GetTempPathA` at `0x10032f55`

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
0x10032f10  push    21Ch
0x10032f15  mov     eax, offset loc_10036AF6
0x10032f1a  call    __EH_prolog3_GS
0x10032f1f  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10032f26  mov     eax, [ebp+nBufferLength]
0x10032f29  mov     ecx, [ebp+lpBuffer]
0x10032f2c  jz      short loc_10032F3A
0x10032f2e  push    ecx; lpBuffer
0x10032f2f  push    eax; nBufferLength
0x10032f30  call    ds:__imp__GetTempPathW@8; GetTempPathW(x,x)
0x10032f36  mov     esi, eax
0x10032f38  jmp     short loc_10032F8B
0x10032f3a  push    eax; int
0x10032f3b  push    ecx; unsigned __int16 *
0x10032f3c  lea     ecx, [ebp+var_228]; this
0x10032f42  call    ??0CStrOut@@QAE@PAGH@Z; CStrOut::CStrOut(ushort *,int)
0x10032f47  mov     eax, [ebp+var_14]
0x10032f4a  push    [ebp+var_224]; lpBuffer
0x10032f50  add     eax, eax
0x10032f52  shr     eax, 1
0x10032f54  push    eax; nBufferLength
0x10032f55  call    ds:__imp__GetTempPathA@8; GetTempPathA(x,x)
0x10032f5b  lea     ecx, [ebp+var_228]; this
0x10032f61  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x10032f66  test    eax, eax
0x10032f68  lea     esi, [eax-1]
0x10032f6b  cmovle  esi, eax
0x10032f6e  lea     ecx, [ebp+var_228]; this
0x10032f74  mov     [ebp+var_4], 0
0x10032f7b  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x10032f80  lea     ecx, [ebp+var_228]; this
0x10032f86  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10032f8b  mov     eax, esi
0x10032f8d  call    __EH_epilog3_GS
0x10032f92  retn    8
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
