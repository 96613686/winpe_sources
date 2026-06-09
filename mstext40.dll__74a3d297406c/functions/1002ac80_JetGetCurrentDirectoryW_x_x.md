# JetGetCurrentDirectoryW(x,x)

- ea: `0x1002ac80`
- end: `0x1002ad36`
- name: `_JetGetCurrentDirectoryW@8`
- size: `182`
- prototype: `int __stdcall(DWORD nBufferLength, LPWSTR lpBuffer)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1000b860`

## callees

- `0x1002a3b0`
- `0x1002a550`
- `0x1002ac80`
- `0x1002b81a`
- `0x1002df32`

## import_xrefs

- `KERNEL32!GetCurrentDirectoryA` at `0x1002ace6`
- `KERNEL32!GetCurrentDirectoryA` at `0x1002ace6`
- `KERNEL32!GetCurrentDirectoryW` at `0x1002acad`
- `KERNEL32!GetCurrentDirectoryW` at `0x1002acad`

## pseudocode

```c
DWORD __stdcall JetGetCurrentDirectoryW(DWORD nBufferLength, LPWSTR lpBuffer)
{
  DWORD CurrentDirectoryA; // esi
  int v4; // [esp+0h] [ebp-21Ch] BYREF
  LPSTR v5; // [esp+4h] [ebp-218h]
  char v6; // [esp+8h] [ebp-214h] BYREF
  int v7; // [esp+214h] [ebp-8h]

  if ( wrap )
    return GetCurrentDirectoryW(nBufferLength, lpBuffer);
  CStrOut::CStrOut((CStrOut *)&v4, lpBuffer, nBufferLength);
  CurrentDirectoryA = GetCurrentDirectoryA((unsigned int)(2 * v7) >> 1, v5);
  CStrOut::ConvertIncludingNul((CStrOut *)&v4);
  if ( v5 != &v6 && (unsigned int)v5 >> 16 && v4 != -1 )
    free(v5);
  return CurrentDirectoryA;
}

```

## disassembly

```asm
0x1002ac80  sub     esp, 21Ch
0x1002ac86  mov     eax, ___security_cookie
0x1002ac8b  xor     eax, esp
0x1002ac8d  mov     [esp+21Ch+var_4], eax
0x1002ac94  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x1002ac9b  mov     eax, [esp+21Ch+nBufferLength]
0x1002aca2  mov     ecx, [esp+21Ch+lpBuffer]
0x1002aca9  jz      short loc_1002ACCA
0x1002acab  push    ecx; lpBuffer
0x1002acac  push    eax; nBufferLength
0x1002acad  call    ds:__imp__GetCurrentDirectoryW@8; GetCurrentDirectoryW(x,x)
0x1002acb3  mov     ecx, [esp+21Ch+var_4]
0x1002acba  xor     ecx, esp; StackCookie
0x1002acbc  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002acc1  add     esp, 21Ch
0x1002acc7  retn    8
0x1002acca  push    esi
0x1002accb  push    eax; int
0x1002accc  push    ecx; wchar_t *
0x1002accd  lea     ecx, [esp+228h+var_21C]; this
0x1002acd1  call    ??0CStrOut@@QAE@PA_WH@Z; CStrOut::CStrOut(wchar_t *,int)
0x1002acd6  mov     eax, [esp+220h+var_8]
0x1002acdd  push    [esp+220h+var_218]; lpBuffer
0x1002ace1  add     eax, eax
0x1002ace3  shr     eax, 1
0x1002ace5  push    eax; nBufferLength
0x1002ace6  call    ds:__imp__GetCurrentDirectoryA@8; GetCurrentDirectoryA(x,x)
0x1002acec  lea     ecx, [esp+220h+var_21C]; this
0x1002acf0  mov     esi, eax
0x1002acf2  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x1002acf7  mov     edx, [esp+220h+var_218]
0x1002acfb  lea     eax, [esp+220h+var_214]
0x1002acff  cmp     edx, eax
0x1002ad01  jz      short loc_1002AD1C
0x1002ad03  mov     ecx, edx
0x1002ad05  shr     ecx, 10h
0x1002ad08  test    ecx, ecx
0x1002ad0a  jz      short loc_1002AD1C
0x1002ad0c  cmp     [esp+220h+var_21C], 0FFFFFFFFh
0x1002ad11  jz      short loc_1002AD1C
0x1002ad13  push    edx; Block
0x1002ad14  call    _free
0x1002ad19  add     esp, 4
0x1002ad1c  mov     ecx, [esp+220h+var_4]
0x1002ad23  mov     eax, esi
0x1002ad25  pop     esi
0x1002ad26  xor     ecx, esp; StackCookie
0x1002ad28  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002ad2d  add     esp, 21Ch
0x1002ad33  retn    8
```
