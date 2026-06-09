# JetGetShortPathNameW(x,x,x)

- ea: `0x10047059`
- end: `0x1004710d`
- name: `_JetGetShortPathNameW@12`
- size: `180`
- prototype: `int __stdcall(LPCWSTR lpszLongPath, LPWSTR lpszShortPath, DWORD cchBuffer)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x10051506`
- `0x1012193b`

## callees

- `0x10046833`
- `0x10046864`
- `0x10046988`
- `0x10046a09`
- `0x10046a9d`
- `0x10047059`
- `0x10123110`
- `0x10124048`
- `0x10124129`
- `0x10124177`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x1004707d`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x1004707d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetShortPathNameA` at `0x100470b4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetShortPathNameA` at `0x100470b4`

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
0x10047059  push    438h
0x1004705e  mov     eax, offset loc_10124D29
0x10047063  call    __EH_prolog3_GS
0x10047068  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x1004706f  mov     eax, [ebp+lpszLongPath]
0x10047072  mov     esi, [ebp+lpszShortPath]
0x10047075  mov     edi, [ebp+cchBuffer]
0x10047078  jz      short loc_10047087
0x1004707a  push    edi; cchBuffer
0x1004707b  push    esi; lpszShortPath
0x1004707c  push    eax; lpszLongPath
0x1004707d  call    ds:__imp__GetShortPathNameW@12; GetShortPathNameW(x,x,x)
0x10047083  mov     esi, eax
0x10047085  jmp     short loc_10047103
0x10047087  push    eax; unsigned __int16 *
0x10047088  lea     ecx, [ebp+var_444]; this
0x1004708e  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10047093  push    edi; int
0x10047094  push    esi; unsigned __int16 *
0x10047095  lea     ecx, [ebp+var_22C]; this
0x1004709b  call    ??0CStrOut@@QAE@PAGH@Z; CStrOut::CStrOut(ushort *,int)
0x100470a0  mov     eax, [ebp+var_18]
0x100470a3  add     eax, eax
0x100470a5  shr     eax, 1
0x100470a7  push    eax; cchBuffer
0x100470a8  push    [ebp+var_228]; lpszShortPath
0x100470ae  push    [ebp+var_440]; lpszLongPath
0x100470b4  call    ds:__imp__GetShortPathNameA@12; GetShortPathNameA(x,x,x)
0x100470ba  lea     ecx, [ebp+var_22C]; this
0x100470c0  test    eax, eax
0x100470c2  jnz     short loc_100470DF
0x100470c4  call    ??1CStrOut@@QAE@XZ; CStrOut::~CStrOut(void)
0x100470c9  lea     ecx, [ebp+var_444]; this
0x100470cf  mov     [ebp+var_4], 0
0x100470d6  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x100470db  xor     eax, eax
0x100470dd  jmp     short loc_10047105
0x100470df  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x100470e4  lea     ecx, [ebp+var_22C]; this
0x100470ea  mov     esi, eax
0x100470ec  call    ??1CStrOut@@QAE@XZ; CStrOut::~CStrOut(void)
0x100470f1  lea     ecx, [ebp+var_444]; this
0x100470f7  mov     [ebp+var_4], 1
0x100470fe  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10047103  mov     eax, esi
0x10047105  call    __EH_epilog3_GS
0x1004710a  retn    0Ch
0x10124060  jmp     ds:__imp____std_terminate
0x10124d29  nop
0x10124d2a  nop
0x10124d2b  mov     edx, [esp-4+lpszShortPath]
0x10124d2f  lea     eax, [edx+0Ch]
0x10124d32  mov     ecx, [edx-448h]
0x10124d38  xor     ecx, eax; StackCookie
0x10124d3a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124d3f  mov     ecx, [edx-4]
0x10124d42  xor     ecx, eax; StackCookie
0x10124d44  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124d49  mov     eax, offset stru_10127AD4
0x10124d4e  jmp     ___CxxFrameHandler3
```
