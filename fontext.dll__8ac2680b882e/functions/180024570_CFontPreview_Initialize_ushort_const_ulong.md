# CFontPreview::Initialize(ushort const *,ulong)

- ea: `0x180024570`
- end: `0x18002465c`
- name: `?Initialize@CFontPreview@@UEAAJPEBGK@Z`
- size: `236`
- prototype: `__int64 __fastcall(LPWSTR *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180023c7c`
- `0x180024570`
- `0x180024b98`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x1800245b6`
- `SHLWAPI!SHStrDupW` at `0x180024626`
- `SHLWAPI!SHStrDupW` at `0x1800245b6`
- `SHLWAPI!SHStrDupW` at `0x180024626`
- `SHLWAPI!PathFindExtensionW` at `0x1800245c5`
- `SHLWAPI!PathFindExtensionW` at `0x1800245c5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800245e3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800245e3`

## pseudocode

```c
__int64 __fastcall CFontPreview::Initialize(LPWSTR *this, const unsigned __int16 *a2)
{
  LPCWSTR *v4; // rsi
  HRESULT v5; // ebx
  const WCHAR *ExtensionW; // rax
  CFontPreview *v7; // rcx
  unsigned __int64 v8; // r9
  WCHAR psz[528]; // [rsp+30h] [rbp-438h] BYREF

  CFontPreview::CleanupPerPreviewData((CFontPreview *)(this - 3));
  if ( a2 )
  {
    v4 = (LPCWSTR *)(this + 4);
    v5 = SHStrDupW(a2, this + 4);
    if ( v5 >= 0 )
    {
      ExtensionW = PathFindExtensionW(*v4);
      if ( CompareStringOrdinal(L".PFM", -1, ExtensionW, -1, 1) == 2 )
      {
        memset_0(psz, 0, 0x412u);
        v5 = CFontPreview::_BuildType1FontSpec(v7, *v4, psz, v8);
        if ( v5 >= 0 )
        {
          *((_DWORD *)this + 54) = 1;
          return (unsigned int)SHStrDupW(psz, this + 5);
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180024570  mov     [rsp+arg_10], rbx
0x180024575  mov     [rsp+arg_18], rsi
0x18002457a  push    rdi
0x18002457b  sub     rsp, 460h
0x180024582  mov     rax, cs:__security_cookie
0x180024589  xor     rax, rsp
0x18002458c  mov     [rsp+468h+var_18], rax
0x180024594  mov     rdi, rcx
0x180024597  mov     rbx, rdx
0x18002459a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002459e  call    ?CleanupPerPreviewData@CFontPreview@@AEAAXXZ; CFontPreview::CleanupPerPreviewData(void)
0x1800245a3  test    rbx, rbx
0x1800245a6  jz      loc_180024630
0x1800245ac  lea     rsi, [rdi+20h]
0x1800245b0  mov     rcx, rbx; psz
0x1800245b3  mov     rdx, rsi; ppwsz
0x1800245b6  call    cs:__imp_SHStrDupW
0x1800245bc  mov     ebx, eax
0x1800245be  test    eax, eax
0x1800245c0  js      short loc_180024635
0x1800245c2  mov     rcx, [rsi]; pszPath
0x1800245c5  call    cs:__imp_PathFindExtensionW
0x1800245cb  or      edx, 0FFFFFFFFh; cchCount1
0x1800245ce  mov     [rsp+468h+bIgnoreCase], 1; bIgnoreCase
0x1800245d6  mov     r9d, edx; cchCount2
0x1800245d9  lea     rcx, aPfm_1; ".PFM"
0x1800245e0  mov     r8, rax; lpString2
0x1800245e3  call    cs:__imp_CompareStringOrdinal
0x1800245e9  cmp     eax, 2
0x1800245ec  jnz     short loc_180024635
0x1800245ee  xor     edx, edx; Val
0x1800245f0  lea     rcx, [rsp+468h+psz]; void *
0x1800245f5  mov     r8d, 412h; Size
0x1800245fb  call    memset_0
0x180024600  mov     rdx, [rsi]; unsigned __int16 *
0x180024603  lea     r8, [rsp+468h+psz]; unsigned __int16 *
0x180024608  call    ?_BuildType1FontSpec@CFontPreview@@AEAAJPEBGPEAG_K@Z; CFontPreview::_BuildType1FontSpec(ushort const *,ushort *,unsigned __int64)
0x18002460d  mov     ebx, eax
0x18002460f  test    eax, eax
0x180024611  js      short loc_180024635
0x180024613  lea     rdx, [rdi+28h]; ppwsz
0x180024617  mov     dword ptr [rdi+0D8h], 1
0x180024621  lea     rcx, [rsp+468h+psz]; psz
0x180024626  call    cs:__imp_SHStrDupW
0x18002462c  mov     ebx, eax
0x18002462e  jmp     short loc_180024635
0x180024630  mov     ebx, 80070057h
0x180024635  mov     eax, ebx
0x180024637  mov     rcx, [rsp+468h+var_18]
0x18002463f  xor     rcx, rsp; StackCookie
0x180024642  call    __security_check_cookie
0x180024647  lea     r11, [rsp+468h+var_8]
0x18002464f  mov     rbx, [r11+20h]
0x180024653  mov     rsi, [r11+28h]
0x180024657  mov     rsp, r11
0x18002465a  pop     rdi
0x18002465b  retn
```
