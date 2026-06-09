# JetGetComputerNameW(x,x)

- ea: `0x10046e86`
- end: `0x10046f0c`
- name: `_JetGetComputerNameW@8`
- size: `134`
- prototype: `int __stdcall(LPWSTR lpBuffer, LPDWORD nSize)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1012081d`
- `0x10120aed`
- `0x101211fb`

## callees

- `0x10046988`
- `0x10046a09`
- `0x10046a9d`
- `0x10046e86`
- `0x10123110`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x10046ed0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x10046ed0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x10046eb5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x10046eb5`

## pseudocode

```c
BOOL __stdcall JetGetComputerNameW(LPWSTR lpBuffer, LPDWORD nSize)
{
  BOOL ComputerNameA; // edi
  int v3; // eax
  DWORD v4; // ecx
  _BYTE v6[4]; // [esp+8h] [ebp-220h] BYREF
  LPSTR v7; // [esp+Ch] [ebp-21Ch]

  if ( wrap )
    return GetComputerNameW(lpBuffer, nSize);
  CStrOut::CStrOut((CStrOut *)v6, lpBuffer, *nSize);
  ComputerNameA = GetComputerNameA(v7, nSize);
  v3 = CStrOut::ConvertIncludingNul((CStrOut *)v6);
  v4 = v3 - 1;
  if ( v3 <= 0 )
    v4 = v3;
  *nSize = v4;
  CStrOut::~CStrOut((CStrOut *)v6);
  return ComputerNameA;
}

```

## disassembly

```asm
0x10046e86  mov     edi, edi
0x10046e88  push    ebp
0x10046e89  mov     ebp, esp
0x10046e8b  and     esp, 0FFFFFFF8h
0x10046e8e  sub     esp, 220h
0x10046e94  mov     eax, ___security_cookie
0x10046e99  xor     eax, esp
0x10046e9b  mov     [esp+220h+var_4], eax
0x10046ea2  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10046ea9  mov     eax, [ebp+lpBuffer]
0x10046eac  push    esi
0x10046ead  mov     esi, [ebp+nSize]
0x10046eb0  push    edi
0x10046eb1  jz      short loc_10046EBF
0x10046eb3  push    esi; nSize
0x10046eb4  push    eax; lpBuffer
0x10046eb5  call    ds:__imp__GetComputerNameW@8; GetComputerNameW(x,x)
0x10046ebb  mov     edi, eax
0x10046ebd  jmp     short loc_10046EF4
0x10046ebf  push    dword ptr [esi]; int
0x10046ec1  lea     ecx, [esp+22Ch+var_220]; this
0x10046ec5  push    eax; unsigned __int16 *
0x10046ec6  call    ??0CStrOut@@QAE@PAGH@Z; CStrOut::CStrOut(ushort *,int)
0x10046ecb  push    esi; nSize
0x10046ecc  push    [esp+22Ch+var_21C]; lpBuffer
0x10046ed0  call    ds:__imp__GetComputerNameA@8; GetComputerNameA(x,x)
0x10046ed6  lea     ecx, [esp+228h+var_220]; this
0x10046eda  mov     edi, eax
0x10046edc  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x10046ee1  test    eax, eax
0x10046ee3  lea     ecx, [eax-1]
0x10046ee6  cmovle  ecx, eax
0x10046ee9  mov     [esi], ecx
0x10046eeb  lea     ecx, [esp+228h+var_220]; this
0x10046eef  call    ??1CStrOut@@QAE@XZ; CStrOut::~CStrOut(void)
0x10046ef4  mov     ecx, [esp+228h+var_4]
0x10046efb  mov     eax, edi
0x10046efd  pop     edi
0x10046efe  pop     esi
0x10046eff  xor     ecx, esp; StackCookie
0x10046f01  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10046f06  mov     esp, ebp
0x10046f08  pop     ebp
0x10046f09  retn    8
```
