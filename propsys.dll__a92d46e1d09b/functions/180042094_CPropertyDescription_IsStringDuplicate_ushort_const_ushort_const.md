# CPropertyDescription::_IsStringDuplicate(ushort const *,ushort const *)

- ea: `0x180042094`
- end: `0x1800421a8`
- name: `?_IsStringDuplicate@CPropertyDescription@@AEAAPEBGPEBG0@Z`
- size: `276`
- prototype: `const unsigned __int16 *(CPropertyDescription *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008870`
- `0x18000c234`
- `0x180041fc8`
- `0x180069094`

## callees

- `0x180042094`
- `0x1800421b0`
- `0x1800421e8`
- `0x18006bac8`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x1800420cf`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180042152`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x1800420cf`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180042152`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800420ec`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004216e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800420ec`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004216e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180042192`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180042192`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpCW` at `0x18004219d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpCW` at `0x18004219d`

## pseudocode

```c
const unsigned __int16 *__fastcall CPropertyDescription::_IsStringDuplicate(
        CPropertyDescription *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const unsigned __int16 *v4; // rsi
  int IsDiscrete; // eax
  __int64 v7; // r8
  LCID v8; // eax
  int v9; // eax
  unsigned int Depth; // r15d
  unsigned int v12; // ebx
  unsigned int v13; // r12d
  __int64 v14; // rdi
  __int64 cchCount2; // rbx
  LCID ThreadLocale; // eax

  v4 = 0;
  if ( (*(_BYTE *)(*((_QWORD *)this + 5) + 60LL) & 0x20) != 0 )
  {
    Depth = TreeValueGetDepth(a2);
    v12 = TreeValueGetDepth(a3);
    v13 = v12;
    if ( Depth < v12 )
      v12 = Depth;
    v14 = TreeValueFindTokenEndN(a2, v12) - a2;
    cchCount2 = TreeValueFindTokenEndN(a3, v12) - a3;
    ThreadLocale = GetThreadLocale();
    if ( CompareStringW(ThreadLocale, 1u, a2, v14, a3, cchCount2) == 2 )
    {
      v4 = a3;
      if ( Depth <= v13 )
        return a2;
    }
  }
  else
  {
    IsDiscrete = CPropertyDescription::_IsDiscrete(this);
    if ( *(_DWORD *)(v7 + 88) == 4 && *(_DWORD *)(v7 + 164) )
    {
      if ( IsDiscrete )
        v9 = StrCmpICW(a2, a3);
      else
        v9 = StrCmpCW(a2, a3);
    }
    else
    {
      v8 = GetThreadLocale();
      v9 = CompareStringW(v8, 1u, a2, -1, a3, -1) - 2;
    }
    if ( !v9 )
      return a2;
  }
  return v4;
}

```

## disassembly

```asm
0x180042094  push    rbx
0x180042096  push    rbp
0x180042097  push    rsi
0x180042098  push    rdi
0x180042099  push    r12
0x18004209b  push    r14
0x18004209d  push    r15
0x18004209f  sub     rsp, 30h
0x1800420a3  mov     r14, r8
0x1800420a6  xor     esi, esi
0x1800420a8  mov     r8, [rcx+28h]
0x1800420ac  mov     rbp, rdx
0x1800420af  test    byte ptr [r8+3Ch], 20h
0x1800420b4  jnz     short loc_18004210D
0x1800420b6  call    ?_IsDiscrete@CPropertyDescription@@AEAAHXZ; CPropertyDescription::_IsDiscrete(void)
0x1800420bb  cmp     dword ptr [r8+58h], 4
0x1800420c0  jnz     short loc_1800420CF
0x1800420c2  cmp     [r8+0A4h], esi
0x1800420c9  jnz     loc_180042188
0x1800420cf  call    cs:__imp_GetThreadLocale
0x1800420d5  or      r9d, 0FFFFFFFFh; cchCount1
0x1800420d9  mov     r8, rbp; lpString1
0x1800420dc  mov     [rsp+68h+cchCount2], r9d; cchCount2
0x1800420e1  mov     ecx, eax; Locale
0x1800420e3  mov     [rsp+68h+lpString2], r14; lpString2
0x1800420e8  lea     edx, [r9+2]; dwCmpFlags
0x1800420ec  call    cs:__imp_CompareStringW
0x1800420f2  sub     eax, 2
0x1800420f5  test    eax, eax
0x1800420f7  cmovz   rsi, rbp
0x1800420fb  mov     rax, rsi
0x1800420fe  add     rsp, 30h
0x180042102  pop     r15
0x180042104  pop     r14
0x180042106  pop     r12
0x180042108  pop     rdi
0x180042109  pop     rsi
0x18004210a  pop     rbp
0x18004210b  pop     rbx
0x18004210c  retn
0x18004210d  mov     rcx, rbp; pszStart
0x180042110  call    ?TreeValueGetDepth@@YAKPEBG@Z; TreeValueGetDepth(ushort const *)
0x180042115  mov     rcx, r14; pszStart
0x180042118  mov     r15d, eax
0x18004211b  call    ?TreeValueGetDepth@@YAKPEBG@Z; TreeValueGetDepth(ushort const *)
0x180042120  cmp     r15d, eax
0x180042123  mov     ebx, eax
0x180042125  mov     rcx, rbp; lpString
0x180042128  mov     r12d, eax
0x18004212b  cmovb   ebx, r15d
0x18004212f  mov     edx, ebx; unsigned int
0x180042131  call    ?TreeValueFindTokenEndN@@YAPEBGPEBGK@Z; TreeValueFindTokenEndN(ushort const *,ulong)
0x180042136  mov     rdi, rax
0x180042139  mov     edx, ebx; unsigned int
0x18004213b  sub     rdi, rbp
0x18004213e  mov     rcx, r14; lpString
0x180042141  sar     rdi, 1
0x180042144  call    ?TreeValueFindTokenEndN@@YAPEBGPEBGK@Z; TreeValueFindTokenEndN(ushort const *,ulong)
0x180042149  mov     rbx, rax
0x18004214c  sub     rbx, r14
0x18004214f  sar     rbx, 1
0x180042152  call    cs:__imp_GetThreadLocale
0x180042158  mov     [rsp+68h+cchCount2], ebx; cchCount2
0x18004215c  mov     r9d, edi; cchCount1
0x18004215f  mov     ecx, eax; Locale
0x180042161  mov     [rsp+68h+lpString2], r14; lpString2
0x180042166  mov     r8, rbp; lpString1
0x180042169  mov     edx, 1; dwCmpFlags
0x18004216e  call    cs:__imp_CompareStringW
0x180042174  cmp     eax, 2
0x180042177  jnz     short loc_1800420FB
0x180042179  cmp     r15d, r12d
0x18004217c  mov     rsi, r14
0x18004217f  cmovbe  rsi, rbp
0x180042183  jmp     loc_1800420FB
0x180042188  mov     rdx, r14; pszStr2
0x18004218b  mov     rcx, rbp; pszStr1
0x18004218e  test    eax, eax
0x180042190  jz      short loc_18004219D
0x180042192  call    cs:__imp_StrCmpICW
0x180042198  jmp     loc_1800420F5
0x18004219d  call    cs:__imp_StrCmpCW
0x1800421a3  jmp     loc_1800420F5
```
