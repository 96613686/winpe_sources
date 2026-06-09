# JetGetTempPathW(x,x)

- ea: `0x1002aed0`
- end: `0x1002af94`
- name: `_JetGetTempPathW@8`
- size: `196`
- prototype: `int __stdcall(DWORD nBufferLength, LPWSTR lpBuffer)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1000b790`

## callees

- `0x1002a3b0`
- `0x1002a550`
- `0x1002aed0`
- `0x1002b81a`
- `0x1002df32`

## import_xrefs

- `KERNEL32!GetTempPathW` at `0x1002aefd`
- `KERNEL32!GetTempPathW` at `0x1002aefd`
- `KERNEL32!GetTempPathA` at `0x1002af36`
- `KERNEL32!GetTempPathA` at `0x1002af36`

## pseudocode

```c
DWORD __stdcall JetGetTempPathW(DWORD nBufferLength, LPWSTR lpBuffer)
{
  int v3; // eax
  int v4; // esi
  int v5; // [esp+0h] [ebp-21Ch] BYREF
  LPSTR v6; // [esp+4h] [ebp-218h]
  char v7; // [esp+8h] [ebp-214h] BYREF
  int v8; // [esp+214h] [ebp-8h]

  if ( wrap )
    return GetTempPathW(nBufferLength, lpBuffer);
  CStrOut::CStrOut((CStrOut *)&v5, lpBuffer, nBufferLength);
  GetTempPathA((unsigned int)(2 * v8) >> 1, v6);
  v3 = CStrOut::ConvertIncludingNul((CStrOut *)&v5);
  v4 = v3;
  if ( v3 > 0 )
    v4 = v3 - 1;
  CStrOut::ConvertIncludingNul((CStrOut *)&v5);
  if ( v6 != &v7 && (unsigned int)v6 >> 16 && v5 != -1 )
    free(v6);
  return v4;
}

```

## disassembly

```asm
0x1002aed0  sub     esp, 21Ch
0x1002aed6  mov     eax, ___security_cookie
0x1002aedb  xor     eax, esp
0x1002aedd  mov     [esp+21Ch+var_4], eax
0x1002aee4  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x1002aeeb  mov     eax, [esp+21Ch+nBufferLength]
0x1002aef2  mov     ecx, [esp+21Ch+lpBuffer]
0x1002aef9  jz      short loc_1002AF1A
0x1002aefb  push    ecx; lpBuffer
0x1002aefc  push    eax; nBufferLength
0x1002aefd  call    ds:__imp__GetTempPathW@8; GetTempPathW(x,x)
0x1002af03  mov     ecx, [esp+21Ch+var_4]
0x1002af0a  xor     ecx, esp; StackCookie
0x1002af0c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002af11  add     esp, 21Ch
0x1002af17  retn    8
0x1002af1a  push    esi
0x1002af1b  push    eax; int
0x1002af1c  push    ecx; wchar_t *
0x1002af1d  lea     ecx, [esp+228h+var_21C]; this
0x1002af21  call    ??0CStrOut@@QAE@PA_WH@Z; CStrOut::CStrOut(wchar_t *,int)
0x1002af26  mov     eax, [esp+220h+var_8]
0x1002af2d  push    [esp+220h+var_218]; lpBuffer
0x1002af31  add     eax, eax
0x1002af33  shr     eax, 1
0x1002af35  push    eax; nBufferLength
0x1002af36  call    ds:__imp__GetTempPathA@8; GetTempPathA(x,x)
0x1002af3c  lea     ecx, [esp+220h+var_21C]; this
0x1002af40  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x1002af45  mov     esi, eax
0x1002af47  test    esi, esi
0x1002af49  jle     short loc_1002AF4C
0x1002af4b  dec     esi
0x1002af4c  lea     ecx, [esp+220h+var_21C]; this
0x1002af50  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x1002af55  mov     eax, [esp+220h+var_218]
0x1002af59  lea     ecx, [esp+220h+var_214]
0x1002af5d  cmp     eax, ecx
0x1002af5f  jz      short loc_1002AF7A
0x1002af61  mov     ecx, eax
0x1002af63  shr     ecx, 10h
0x1002af66  test    ecx, ecx
0x1002af68  jz      short loc_1002AF7A
0x1002af6a  cmp     [esp+220h+var_21C], 0FFFFFFFFh
0x1002af6f  jz      short loc_1002AF7A
0x1002af71  push    eax; Block
0x1002af72  call    _free
0x1002af77  add     esp, 4
0x1002af7a  mov     ecx, [esp+220h+var_4]
0x1002af81  mov     eax, esi
0x1002af83  pop     esi
0x1002af84  xor     ecx, esp; StackCookie
0x1002af86  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002af8b  add     esp, 21Ch
0x1002af91  retn    8
```
