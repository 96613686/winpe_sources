# JetGetShortPathNameW(x,x,x)

- ea: `0x10046ed9`
- end: `0x10046f8d`
- name: `_JetGetShortPathNameW@12`
- size: `180`
- prototype: `int __stdcall(LPCWSTR lpszLongPath, LPWSTR lpszShortPath, DWORD cchBuffer)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x10051376`
- `0x1012178b`

## callees

- `0x100466b3`
- `0x100466e4`
- `0x10046808`
- `0x10046889`
- `0x1004691d`
- `0x10046ed9`
- `0x10122f60`
- `0x10123e98`
- `0x10123f79`
- `0x10123fc7`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x10046efd`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x10046efd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetShortPathNameA` at `0x10046f34`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetShortPathNameA` at `0x10046f34`

## pseudocode

```c
DWORD __stdcall JetGetShortPathNameW(LPCWSTR lpszLongPath, LPWSTR lpszShortPath, DWORD cchBuffer)
{
  int v3; // esi
  _BYTE v5[4]; // [esp+10h] [ebp-444h] BYREF
  LPCSTR v6; // [esp+14h] [ebp-440h]
  _BYTE v7[4]; // [esp+228h] [ebp-22Ch] BYREF
  LPSTR v8; // [esp+22Ch] [ebp-228h]
  int v9; // [esp+43Ch] [ebp-18h]
  int v10; // [esp+450h] [ebp-4h]

  if ( wrap )
    return GetShortPathNameW(lpszLongPath, lpszShortPath, cchBuffer);
  CStrIn::CStrIn((CStrIn *)v5, lpszLongPath);
  CStrOut::CStrOut((CStrOut *)v7, lpszShortPath, cchBuffer);
  if ( !GetShortPathNameA(v6, v8, (unsigned int)(2 * v9) >> 1) )
  {
    CStrOut::~CStrOut((CStrOut *)v7);
    v10 = 0;
    CConvertStr::Free((CConvertStr *)v5);
    return 0;
  }
  v3 = CStrOut::ConvertIncludingNul((CStrOut *)v7);
  CStrOut::~CStrOut((CStrOut *)v7);
  v10 = 1;
  CConvertStr::Free((CConvertStr *)v5);
  return v3;
}

```

## disassembly

```asm
0x10046ed9  push    438h
0x10046ede  mov     eax, offset loc_10124B79
0x10046ee3  call    __EH_prolog3_GS
0x10046ee8  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10046eef  mov     eax, [ebp+lpszLongPath]
0x10046ef2  mov     esi, [ebp+lpszShortPath]
0x10046ef5  mov     edi, [ebp+cchBuffer]
0x10046ef8  jz      short loc_10046F07
0x10046efa  push    edi; cchBuffer
0x10046efb  push    esi; lpszShortPath
0x10046efc  push    eax; lpszLongPath
0x10046efd  call    ds:__imp__GetShortPathNameW@12; GetShortPathNameW(x,x,x)
0x10046f03  mov     esi, eax
0x10046f05  jmp     short loc_10046F83
0x10046f07  push    eax; unsigned __int16 *
0x10046f08  lea     ecx, [ebp+var_444]; this
0x10046f0e  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10046f13  push    edi; int
0x10046f14  push    esi; unsigned __int16 *
0x10046f15  lea     ecx, [ebp+var_22C]; this
0x10046f1b  call    ??0CStrOut@@QAE@PAGH@Z; CStrOut::CStrOut(ushort *,int)
0x10046f20  mov     eax, [ebp+var_18]
0x10046f23  add     eax, eax
0x10046f25  shr     eax, 1
0x10046f27  push    eax; cchBuffer
0x10046f28  push    [ebp+var_228]; lpszShortPath
0x10046f2e  push    [ebp+var_440]; lpszLongPath
0x10046f34  call    ds:__imp__GetShortPathNameA@12; GetShortPathNameA(x,x,x)
0x10046f3a  lea     ecx, [ebp+var_22C]; this
0x10046f40  test    eax, eax
0x10046f42  jnz     short loc_10046F5F
0x10046f44  call    ??1CStrOut@@QAE@XZ; CStrOut::~CStrOut(void)
0x10046f49  lea     ecx, [ebp+var_444]; this
0x10046f4f  mov     [ebp+var_4], 0
0x10046f56  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10046f5b  xor     eax, eax
0x10046f5d  jmp     short loc_10046F85
0x10046f5f  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x10046f64  lea     ecx, [ebp+var_22C]; this
0x10046f6a  mov     esi, eax
0x10046f6c  call    ??1CStrOut@@QAE@XZ; CStrOut::~CStrOut(void)
0x10046f71  lea     ecx, [ebp+var_444]; this
0x10046f77  mov     [ebp+var_4], 1
0x10046f7e  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10046f83  mov     eax, esi
0x10046f85  call    __EH_epilog3_GS
0x10046f8a  retn    0Ch
0x10123eb0  jmp     ds:__imp____std_terminate
0x10124b79  nop
0x10124b7a  nop
0x10124b7b  mov     edx, [esp-4+lpszShortPath]
0x10124b7f  lea     eax, [edx+0Ch]
0x10124b82  mov     ecx, [edx-448h]
0x10124b88  xor     ecx, eax; StackCookie
0x10124b8a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124b8f  mov     ecx, [edx-4]
0x10124b92  xor     ecx, eax; StackCookie
0x10124b94  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124b99  mov     eax, offset stru_10127924
0x10124b9e  jmp     ___CxxFrameHandler3
```
