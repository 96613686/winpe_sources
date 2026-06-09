# JetGetTempPathW(x,x)

- ea: `0x10046f12`
- end: `0x10046f93`
- name: `_JetGetTempPathW@8`
- size: `129`
- prototype: `int __stdcall(DWORD nBufferLength, LPWSTR lpBuffer)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x10061111`

## callees

- `0x10046988`
- `0x10046a09`
- `0x10046a9d`
- `0x10046f12`
- `0x10123110`

## import_xrefs

- `api-ms-win-core-file-l1-2-2!GetTempPathA` at `0x10046f5e`
- `api-ms-win-core-file-l1-2-2!GetTempPathA` at `0x10046f5e`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x10046f39`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x10046f39`

## pseudocode

```c
DWORD __stdcall JetGetTempPathW(DWORD nBufferLength, LPWSTR lpBuffer)
{
  int v2; // esi
  int v3; // eax
  _BYTE v5[4]; // [esp+8h] [ebp-220h] BYREF
  LPSTR v6; // [esp+Ch] [ebp-21Ch]
  int v7; // [esp+21Ch] [ebp-Ch]

  if ( wrap )
    return GetTempPathW(nBufferLength, lpBuffer);
  CStrOut::CStrOut((CStrOut *)v5, lpBuffer, nBufferLength);
  GetTempPathA((unsigned int)(2 * v7) >> 1, v6);
  v3 = CStrOut::ConvertIncludingNul((CStrOut *)v5);
  v2 = v3 - 1;
  if ( v3 <= 0 )
    v2 = v3;
  CStrOut::~CStrOut((CStrOut *)v5);
  return v2;
}

```

## disassembly

```asm
0x10046f12  mov     edi, edi
0x10046f14  push    ebp
0x10046f15  mov     ebp, esp
0x10046f17  sub     esp, 224h
0x10046f1d  mov     eax, ___security_cookie
0x10046f22  xor     eax, ebp
0x10046f24  mov     [ebp+var_4], eax
0x10046f27  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10046f2e  mov     eax, [ebp+nBufferLength]
0x10046f31  mov     ecx, [ebp+lpBuffer]
0x10046f34  push    esi
0x10046f35  jz      short loc_10046F43
0x10046f37  push    ecx; lpBuffer
0x10046f38  push    eax; nBufferLength
0x10046f39  call    ds:__imp__GetTempPathW@8; GetTempPathW(x,x)
0x10046f3f  mov     esi, eax
0x10046f41  jmp     short loc_10046F82
0x10046f43  push    eax; int
0x10046f44  push    ecx; unsigned __int16 *
0x10046f45  lea     ecx, [ebp+var_220]; this
0x10046f4b  call    ??0CStrOut@@QAE@PAGH@Z; CStrOut::CStrOut(ushort *,int)
0x10046f50  mov     eax, [ebp+var_C]
0x10046f53  push    [ebp+var_21C]; lpBuffer
0x10046f59  add     eax, eax
0x10046f5b  shr     eax, 1
0x10046f5d  push    eax; nBufferLength
0x10046f5e  call    ds:__imp__GetTempPathA@8; GetTempPathA(x,x)
0x10046f64  lea     ecx, [ebp+var_220]; this
0x10046f6a  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x10046f6f  test    eax, eax
0x10046f71  lea     ecx, [ebp+var_220]; this
0x10046f77  lea     esi, [eax-1]
0x10046f7a  cmovle  esi, eax
0x10046f7d  call    ??1CStrOut@@QAE@XZ; CStrOut::~CStrOut(void)
0x10046f82  mov     ecx, [ebp+var_4]
0x10046f85  mov     eax, esi
0x10046f87  xor     ecx, ebp; StackCookie
0x10046f89  pop     esi
0x10046f8a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10046f8f  leave
0x10046f90  retn    8
```
