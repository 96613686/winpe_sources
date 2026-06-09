# MatchPatternEx

- ea: `0x14000d5c4`
- end: `0x14000d6e5`
- name: `MatchPatternEx`
- size: `289`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140005940`
- `0x14000612c`

## callees

- `0x14000cf88`
- `0x14000d204`
- `0x14000d5c4`
- `0x14000d6ec`
- `0x14000e228`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d609`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d609`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d616`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d616`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d5ff`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d5ff`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x14000d66f`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x14000d66f`

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
0x14000d5c4  mov     [rsp+arg_0], rbx
0x14000d5c9  mov     [rsp+arg_8], rsi
0x14000d5ce  push    rdi
0x14000d5cf  sub     rsp, 30h
0x14000d5d3  mov     edi, r8d
0x14000d5d6  mov     rbx, rdx
0x14000d5d9  mov     rsi, rcx
0x14000d5dc  test    rcx, rcx
0x14000d5df  jz      short loc_14000D61C
0x14000d5e1  test    rdx, rdx
0x14000d5e4  jnz     short loc_14000D62E
0x14000d5e6  xor     r9d, r9d
0x14000d5e9  lea     ecx, [rdx+6]
0x14000d5ec  xor     r8d, r8d
0x14000d5ef  call    GetTempBuffer
0x14000d5f4  mov     rbx, rax
0x14000d5f7  test    rax, rax
0x14000d5fa  jz      short loc_14000D609
0x14000d5fc  mov     rcx, rax; lpString
0x14000d5ff  call    cs:__imp_lstrlenW
0x14000d605  test    eax, eax
0x14000d607  jnz     short loc_14000D644
0x14000d609  call    cs:__imp_GetLastError
0x14000d60f  test    eax, eax
0x14000d611  jnz     short loc_14000D61C
0x14000d613  lea     ecx, [rax+57h]; dwErrCode
0x14000d616  call    cs:__imp_SetLastError
0x14000d61c  xor     eax, eax
0x14000d61e  mov     rbx, [rsp+38h+arg_0]
0x14000d623  mov     rsi, [rsp+38h+arg_8]
0x14000d628  add     rsp, 30h
0x14000d62c  pop     rdi
0x14000d62d  retn
0x14000d62e  test    dil, 2
0x14000d632  jnz     short loc_14000D644
0x14000d634  mov     rcx, rdx
0x14000d637  call    ParsePattern
0x14000d63c  mov     rbx, rax
0x14000d63f  test    rax, rax
0x14000d642  jz      short loc_14000D61C
0x14000d644  xor     r9d, r9d
0x14000d647  lea     rdx, asc_140010EB8; "*"
0x14000d64e  mov     rcx, rbx; lpString1
0x14000d651  call    StringCompareExW
0x14000d656  test    eax, eax
0x14000d658  jnz     short loc_14000D661
0x14000d65a  mov     eax, 1
0x14000d65f  jmp     short loc_14000D61E
0x14000d661  test    dil, 1
0x14000d665  jz      short loc_14000D66F
0x14000d667  mov     r10d, 7Fh
0x14000d66d  jmp     short loc_14000D678
0x14000d66f  call    cs:__imp_GetThreadLocale
0x14000d675  mov     r10d, eax
0x14000d678  mov     edx, edi
0x14000d67a  mov     [rsp+38h+var_18], 0
0x14000d682  shr     edx, 8
0x14000d685  and     edx, 1
0x14000d688  mov     r8d, edx
0x14000d68b  bts     r8d, 10h
0x14000d690  bt      edi, 9
0x14000d694  cmovnb  r8d, edx
0x14000d698  mov     ecx, r8d
0x14000d69b  or      ecx, 2
0x14000d69e  bt      edi, 0Ah
0x14000d6a2  cmovnb  ecx, r8d
0x14000d6a6  mov     r8d, 1000h
0x14000d6ac  mov     edx, ecx
0x14000d6ae  or      edx, 4
0x14000d6b1  bt      edi, 0Bh
0x14000d6b5  cmovnb  edx, ecx
0x14000d6b8  mov     ecx, edx
0x14000d6ba  bts     ecx, 11h
0x14000d6be  test    r8d, edi
0x14000d6c1  cmovz   ecx, edx
0x14000d6c4  mov     rdx, rbx
0x14000d6c7  mov     r9d, ecx
0x14000d6ca  or      r9d, r8d
0x14000d6cd  mov     r8d, r10d
0x14000d6d0  bt      edi, 0Dh
0x14000d6d4  cmovnb  r9d, ecx
0x14000d6d8  mov     rcx, rsi
0x14000d6db  call    InternalRecursiveMatchPatternEx
0x14000d6e0  jmp     loc_14000D61E
```
