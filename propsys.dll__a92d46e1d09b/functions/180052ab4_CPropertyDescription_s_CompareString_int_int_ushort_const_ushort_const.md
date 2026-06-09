# CPropertyDescription::s_CompareString(int,int,ushort const *,ushort const *)

- ea: `0x180052ab4`
- end: `0x180052b13`
- name: `?s_CompareString@CPropertyDescription@@SAHHHPEBG0@Z`
- size: `95`
- prototype: `static int(int, int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180052a50`

## callees

- `0x180052ab4`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180052ae3`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180052ae3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180052b00`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180052b00`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180052ad2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180052ad2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpCW` at `0x180052b0b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpCW` at `0x180052b0b`

## pseudocode

```c
int __fastcall CPropertyDescription::s_CompareString(
        int a1,
        int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  LCID ThreadLocale; // eax

  if ( a1 )
  {
    if ( a2 )
      return StrCmpICW(a3, a4);
    else
      return StrCmpCW(a3, a4);
  }
  else
  {
    ThreadLocale = GetThreadLocale();
    return CompareStringW(ThreadLocale, 1u, a3, -1, a4, -1) - 2;
  }
}

```

## disassembly

```asm
0x180052ab4  mov     [rsp+arg_0], rbx
0x180052ab9  push    rdi
0x180052aba  sub     rsp, 30h
0x180052abe  mov     rbx, r9
0x180052ac1  mov     rdi, r8
0x180052ac4  test    ecx, ecx
0x180052ac6  jz      short loc_180052AE3
0x180052ac8  test    edx, edx
0x180052aca  mov     rcx, r8; pszStr1
0x180052acd  mov     rdx, rbx; pszStr2
0x180052ad0  jz      short loc_180052B0B
0x180052ad2  call    cs:__imp_StrCmpICW
0x180052ad8  mov     rbx, [rsp+38h+arg_0]
0x180052add  add     rsp, 30h
0x180052ae1  pop     rdi
0x180052ae2  retn
0x180052ae3  call    cs:__imp_GetThreadLocale
0x180052ae9  or      r9d, 0FFFFFFFFh; cchCount1
0x180052aed  mov     r8, rdi; lpString1
0x180052af0  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x180052af5  mov     ecx, eax; Locale
0x180052af7  mov     [rsp+38h+lpString2], rbx; lpString2
0x180052afc  lea     edx, [r9+2]; dwCmpFlags
0x180052b00  call    cs:__imp_CompareStringW
0x180052b06  sub     eax, 2
0x180052b09  jmp     short loc_180052AD8
0x180052b0b  call    cs:__imp_StrCmpCW
0x180052b11  jmp     short loc_180052AD8
```
