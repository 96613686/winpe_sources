# InternalStringHash

- ea: `0x18001efe0`
- end: `0x18001f079`
- name: `InternalStringHash`
- size: `153`
- prototype: `__int64 __fastcall(LPCWSTR lpSrcStr, int cchSrc)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f42c`

## callees

- `0x180004ec4`
- `0x18001e6f4`
- `0x18001efe0`
- `0x1800201c4`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18001f00c`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18001f00c`

## string_xrefs

- `0x18001f02b`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\namestr.cxx"`
- `0x18001f05b`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\namestr.cxx"`
- `0x18001f01f`: `[UtilCommon] LCMapString() converted %ld out of %ld characters`
- `0x18001f04f`: `[UtilCommon] InternalStringHash is returning fixed value, 0, as hash value.Possibly caused by empty string.`

## pseudocode

```c
unsigned int __fastcall InternalStringHash(WCHAR *lpSrcStr, int cchSrc)
{
  int v2; // ebx
  unsigned int v4; // eax
  const wchar_t *v5; // r9
  unsigned int v6; // edi
  __int64 v8; // [rsp+20h] [rbp-18h]

  v2 = cchSrc;
  v4 = LCMapStringW(0x800u, 0x200u, lpSrcStr, cchSrc, lpSrcStr, cchSrc);
  v6 = v4;
  if ( v4 != v2 )
  {
    LODWORD(v8) = v2;
    SearchIndexerTrace::Warning(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmutild\\\\namestr.cxx\"",
      (const wchar_t *)0x2C,
      (unsigned int)L"[UtilCommon] LCMapString() converted %ld out of %ld characters",
      (const wchar_t *)v4,
      v8);
    if ( !v6 )
      goto LABEL_6;
    v2 = v6 - 1;
  }
  if ( v2 )
    return CDiffCrc::Crc32((const unsigned __int8 *)lpSrcStr, 2 * v2);
LABEL_6:
  SearchIndexerTrace::Information(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmutild\\\\namestr.cxx\"",
    (const wchar_t *)0x3D,
    (unsigned int)L"[UtilCommon] InternalStringHash is returning fixed value, 0, as hash value.Possibly caused by empty string.",
    v5);
  return 0;
}

```

## disassembly

```asm
0x18001efe0  mov     rax, rsp
0x18001efe3  mov     [rax+8], rbx
0x18001efe7  mov     [rax+10h], rsi
0x18001efeb  push    rdi
0x18001efec  sub     rsp, 30h
0x18001eff0  mov     [rax-10h], edx
0x18001eff3  mov     ebx, edx
0x18001eff5  mov     [rax-18h], rcx
0x18001eff9  mov     rsi, rcx
0x18001effc  mov     r9d, edx; cchSrc
0x18001efff  mov     r8, rcx; lpSrcStr
0x18001f002  mov     ecx, 800h; Locale
0x18001f007  mov     edx, 200h; dwMapFlags
0x18001f00c  call    cs:__imp_LCMapStringW
0x18001f012  mov     edi, eax
0x18001f014  cmp     eax, ebx
0x18001f016  jz      short loc_18001F03E
0x18001f018  mov     r9d, eax; wchar_t *
0x18001f01b  mov     dword ptr [rsp+38h+var_18], ebx
0x18001f01f  lea     r8, aUtilcommonLcma; "[UtilCommon] LCMapString() converted %l"...
0x18001f026  mov     edx, 2Ch ; ','; wchar_t *
0x18001f02b  lea     rcx, aOnecoreuapBase_12; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18001f032  call    ?Warning@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Warning(wchar_t const *,uint,wchar_t const *,...)
0x18001f037  test    edi, edi
0x18001f039  jz      short loc_18001F04F
0x18001f03b  lea     ebx, [rdi-1]
0x18001f03e  test    ebx, ebx
0x18001f040  jz      short loc_18001F04F
0x18001f042  lea     edx, [rbx+rbx]; unsigned int
0x18001f045  mov     rcx, rsi; unsigned __int8 *
0x18001f048  call    ?Crc32@CDiffCrc@@SAKPEBEK@Z; CDiffCrc::Crc32(uchar const *,ulong)
0x18001f04d  jmp     short loc_18001F069
0x18001f04f  lea     r8, aUtilcommonInte; "[UtilCommon] InternalStringHash is retu"...
0x18001f056  mov     edx, 3Dh ; '='; wchar_t *
0x18001f05b  lea     rcx, aOnecoreuapBase_12; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18001f062  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x18001f067  xor     eax, eax
0x18001f069  mov     rbx, [rsp+38h+arg_0]
0x18001f06e  mov     rsi, [rsp+38h+arg_8]
0x18001f073  add     rsp, 30h
0x18001f077  pop     rdi
0x18001f078  retn
```
