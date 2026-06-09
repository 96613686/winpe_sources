# JetGetTempPathW(x,x)

- ea: `0x10046d92`
- end: `0x10046e13`
- name: `_JetGetTempPathW@8`
- size: `129`
- prototype: `int __stdcall(DWORD nBufferLength, LPWSTR lpBuffer)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x10060f7d`

## callees

- `0x10046808`
- `0x10046889`
- `0x1004691d`
- `0x10046d92`
- `0x10122f60`

## import_xrefs

- `api-ms-win-core-file-l1-2-2!GetTempPathA` at `0x10046dde`
- `api-ms-win-core-file-l1-2-2!GetTempPathA` at `0x10046dde`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x10046db9`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x10046db9`

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
0x10046d92  mov     edi, edi
0x10046d94  push    ebp
0x10046d95  mov     ebp, esp
0x10046d97  sub     esp, 224h
0x10046d9d  mov     eax, ___security_cookie
0x10046da2  xor     eax, ebp
0x10046da4  mov     [ebp+var_4], eax
0x10046da7  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10046dae  mov     eax, [ebp+nBufferLength]
0x10046db1  mov     ecx, [ebp+lpBuffer]
0x10046db4  push    esi
0x10046db5  jz      short loc_10046DC3
0x10046db7  push    ecx; lpBuffer
0x10046db8  push    eax; nBufferLength
0x10046db9  call    ds:__imp__GetTempPathW@8; GetTempPathW(x,x)
0x10046dbf  mov     esi, eax
0x10046dc1  jmp     short loc_10046E02
0x10046dc3  push    eax; int
0x10046dc4  push    ecx; unsigned __int16 *
0x10046dc5  lea     ecx, [ebp+var_220]; this
0x10046dcb  call    ??0CStrOut@@QAE@PAGH@Z; CStrOut::CStrOut(ushort *,int)
0x10046dd0  mov     eax, [ebp+var_C]
0x10046dd3  push    [ebp+var_21C]; lpBuffer
0x10046dd9  add     eax, eax
0x10046ddb  shr     eax, 1
0x10046ddd  push    eax; nBufferLength
0x10046dde  call    ds:__imp__GetTempPathA@8; GetTempPathA(x,x)
0x10046de4  lea     ecx, [ebp+var_220]; this
0x10046dea  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x10046def  test    eax, eax
0x10046df1  lea     ecx, [ebp+var_220]; this
0x10046df7  lea     esi, [eax-1]
0x10046dfa  cmovle  esi, eax
0x10046dfd  call    ??1CStrOut@@QAE@XZ; CStrOut::~CStrOut(void)
0x10046e02  mov     ecx, [ebp+var_4]
0x10046e05  mov     eax, esi
0x10046e07  xor     ecx, ebp; StackCookie
0x10046e09  pop     esi
0x10046e0a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10046e0f  leave
0x10046e10  retn    8
```
