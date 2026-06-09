# MatchPatternEx

- ea: `0x14000e050`
- end: `0x14000e18a`
- name: `MatchPatternEx`
- size: `314`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140005c78`
- `0x1400064b0`

## callees

- `0x14000d900`
- `0x14000dbb8`
- `0x14000e050`
- `0x14000e190`
- `0x14000ee5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e09b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e09b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e0ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e0ae`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000e08b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000e08b`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x14000e10e`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x14000e10e`

## pseudocode

```c
__int64 __fastcall MatchPatternEx(const WCHAR *a1, const WCHAR *a2, __int64 a3)
{
  unsigned int v3; // edi
  const WCHAR *v4; // rbx
  const WCHAR *TempBuffer; // rax
  LCID ThreadLocale; // r10d
  int v9; // r8d
  int v10; // ecx
  int v11; // edx
  int v12; // ecx
  DWORD v13; // r9d

  v3 = a3;
  v4 = a2;
  if ( !a1 )
    return 0;
  if ( a2 )
  {
    if ( (a3 & 2) == 0 )
    {
      v4 = (const WCHAR *)ParsePattern(a2);
      if ( !v4 )
        return 0;
    }
  }
  else
  {
    TempBuffer = (const WCHAR *)GetTempBuffer(6, 0, 0, 0);
    v4 = TempBuffer;
    if ( !TempBuffer || !lstrlenW(TempBuffer) )
    {
      if ( !GetLastError() )
        SetLastError(0x57u);
      return 0;
    }
  }
  if ( !(unsigned int)StringCompareExW(v4, L"*", a3, 0) )
    return 1;
  if ( (v3 & 1) != 0 )
    ThreadLocale = 127;
  else
    ThreadLocale = GetThreadLocale();
  v9 = (v3 >> 8) & 1 | 0x10000;
  if ( (v3 & 0x200) == 0 )
    v9 = (v3 >> 8) & 1;
  v10 = v9 | 2;
  if ( (v3 & 0x400) == 0 )
    v10 = v9;
  v11 = v10 | 4;
  if ( (v3 & 0x800) == 0 )
    v11 = v10;
  v12 = v11 | 0x20000;
  if ( (v3 & 0x1000) == 0 )
    v12 = v11;
  v13 = v12 | 0x1000;
  if ( (v3 & 0x2000) == 0 )
    v13 = v12;
  return InternalRecursiveMatchPatternEx(a1, v4, ThreadLocale, v13, 0);
}

```

## disassembly

```asm
0x14000e050  mov     [rsp+arg_0], rbx
0x14000e055  mov     [rsp+arg_8], rsi
0x14000e05a  push    rdi
0x14000e05b  sub     rsp, 30h
0x14000e05f  mov     edi, r8d
0x14000e062  mov     rbx, rdx
0x14000e065  mov     rsi, rcx
0x14000e068  test    rcx, rcx
0x14000e06b  jz      short loc_14000E0BA
0x14000e06d  test    rdx, rdx
0x14000e070  jnz     short loc_14000E0CD
0x14000e072  xor     r9d, r9d
0x14000e075  lea     ecx, [rdx+6]
0x14000e078  xor     r8d, r8d
0x14000e07b  call    GetTempBuffer
0x14000e080  mov     rbx, rax
0x14000e083  test    rax, rax
0x14000e086  jz      short loc_14000E09B
0x14000e088  mov     rcx, rax; lpString
0x14000e08b  call    cs:__imp_lstrlenW
0x14000e092  nop     dword ptr [rax+rax+00h]
0x14000e097  test    eax, eax
0x14000e099  jnz     short loc_14000E0E3
0x14000e09b  call    cs:__imp_GetLastError
0x14000e0a2  nop     dword ptr [rax+rax+00h]
0x14000e0a7  test    eax, eax
0x14000e0a9  jnz     short loc_14000E0BA
0x14000e0ab  lea     ecx, [rax+57h]; dwErrCode
0x14000e0ae  call    cs:__imp_SetLastError
0x14000e0b5  nop     dword ptr [rax+rax+00h]
0x14000e0ba  xor     eax, eax
0x14000e0bc  mov     rbx, [rsp+38h+arg_0]
0x14000e0c1  mov     rsi, [rsp+38h+arg_8]
0x14000e0c6  add     rsp, 30h
0x14000e0ca  pop     rdi
0x14000e0cb  retn
0x14000e0cd  test    dil, 2
0x14000e0d1  jnz     short loc_14000E0E3
0x14000e0d3  mov     rcx, rdx
0x14000e0d6  call    ParsePattern
0x14000e0db  mov     rbx, rax
0x14000e0de  test    rax, rax
0x14000e0e1  jz      short loc_14000E0BA
0x14000e0e3  xor     r9d, r9d
0x14000e0e6  lea     rdx, asc_140011EB8; "*"
0x14000e0ed  mov     rcx, rbx; lpString1
0x14000e0f0  call    StringCompareExW
0x14000e0f5  test    eax, eax
0x14000e0f7  jnz     short loc_14000E100
0x14000e0f9  mov     eax, 1
0x14000e0fe  jmp     short loc_14000E0BC
0x14000e100  test    dil, 1
0x14000e104  jz      short loc_14000E10E
0x14000e106  mov     r10d, 7Fh
0x14000e10c  jmp     short loc_14000E11D
0x14000e10e  call    cs:__imp_GetThreadLocale
0x14000e115  nop     dword ptr [rax+rax+00h]
0x14000e11a  mov     r10d, eax
0x14000e11d  mov     edx, edi
0x14000e11f  mov     [rsp+38h+var_18], 0
0x14000e127  shr     edx, 8
0x14000e12a  and     edx, 1
0x14000e12d  mov     r8d, edx
0x14000e130  bts     r8d, 10h
0x14000e135  bt      edi, 9
0x14000e139  cmovnb  r8d, edx
0x14000e13d  mov     ecx, r8d
0x14000e140  or      ecx, 2
0x14000e143  bt      edi, 0Ah
0x14000e147  cmovnb  ecx, r8d
0x14000e14b  mov     r8d, 1000h
0x14000e151  mov     edx, ecx
0x14000e153  or      edx, 4
0x14000e156  bt      edi, 0Bh
0x14000e15a  cmovnb  edx, ecx
0x14000e15d  mov     ecx, edx
0x14000e15f  bts     ecx, 11h
0x14000e163  test    r8d, edi
0x14000e166  cmovz   ecx, edx
0x14000e169  mov     rdx, rbx
0x14000e16c  mov     r9d, ecx
0x14000e16f  or      r9d, r8d
0x14000e172  mov     r8d, r10d
0x14000e175  bt      edi, 0Dh
0x14000e179  cmovnb  r9d, ecx
0x14000e17d  mov     rcx, rsi
0x14000e180  call    InternalRecursiveMatchPatternEx
0x14000e185  jmp     loc_14000E0BC
```
