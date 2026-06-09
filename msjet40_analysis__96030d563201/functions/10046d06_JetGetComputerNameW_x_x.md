# JetGetComputerNameW(x,x)

- ea: `0x10046d06`
- end: `0x10046d8c`
- name: `_JetGetComputerNameW@8`
- size: `134`
- prototype: `int __stdcall(LPWSTR lpBuffer, LPDWORD nSize)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1012066d`
- `0x1012093d`
- `0x1012104b`

## callees

- `0x10046808`
- `0x10046889`
- `0x1004691d`
- `0x10046d06`
- `0x10122f60`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x10046d50`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x10046d50`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x10046d35`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x10046d35`

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
0x10046d06  mov     edi, edi
0x10046d08  push    ebp
0x10046d09  mov     ebp, esp
0x10046d0b  and     esp, 0FFFFFFF8h
0x10046d0e  sub     esp, 220h
0x10046d14  mov     eax, ___security_cookie
0x10046d19  xor     eax, esp
0x10046d1b  mov     [esp+220h+var_4], eax
0x10046d22  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10046d29  mov     eax, [ebp+lpBuffer]
0x10046d2c  push    esi
0x10046d2d  mov     esi, [ebp+nSize]
0x10046d30  push    edi
0x10046d31  jz      short loc_10046D3F
0x10046d33  push    esi; nSize
0x10046d34  push    eax; lpBuffer
0x10046d35  call    ds:__imp__GetComputerNameW@8; GetComputerNameW(x,x)
0x10046d3b  mov     edi, eax
0x10046d3d  jmp     short loc_10046D74
0x10046d3f  push    dword ptr [esi]; int
0x10046d41  lea     ecx, [esp+22Ch+var_220]; this
0x10046d45  push    eax; unsigned __int16 *
0x10046d46  call    ??0CStrOut@@QAE@PAGH@Z; CStrOut::CStrOut(ushort *,int)
0x10046d4b  push    esi; nSize
0x10046d4c  push    [esp+22Ch+var_21C]; lpBuffer
0x10046d50  call    ds:__imp__GetComputerNameA@8; GetComputerNameA(x,x)
0x10046d56  lea     ecx, [esp+228h+var_220]; this
0x10046d5a  mov     edi, eax
0x10046d5c  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x10046d61  test    eax, eax
0x10046d63  lea     ecx, [eax-1]
0x10046d66  cmovle  ecx, eax
0x10046d69  mov     [esi], ecx
0x10046d6b  lea     ecx, [esp+228h+var_220]; this
0x10046d6f  call    ??1CStrOut@@QAE@XZ; CStrOut::~CStrOut(void)
0x10046d74  mov     ecx, [esp+228h+var_4]
0x10046d7b  mov     eax, edi
0x10046d7d  pop     edi
0x10046d7e  pop     esi
0x10046d7f  xor     ecx, esp; StackCookie
0x10046d81  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10046d86  mov     esp, ebp
0x10046d88  pop     ebp
0x10046d89  retn    8
```
