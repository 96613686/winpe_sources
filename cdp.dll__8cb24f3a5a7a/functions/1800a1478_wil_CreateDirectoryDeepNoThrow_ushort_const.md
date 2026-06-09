# wil::CreateDirectoryDeepNoThrow(ushort const *)

- ea: `0x1800a1478`
- end: `0x1800a15fa`
- name: `?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z`
- size: `386`
- prototype: `__int64 __fastcall(wil *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x1800a0db0`
- `0x1800a1478`

## callees

- `0x1800a1478`
- `0x1800d6f48`
- `0x180149448`
- `0x1801fc5e8`
- `0x1801fca38`
- `0x18023ac94`
- `0x18023acdc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a14a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a15a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a14a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a15a7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800a148f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800a159d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800a148f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800a159d`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x1800a14bc`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x1800a14bc`

## string_xrefs

- `0x1800a151f`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800a1575`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`
- `0x1800a15c2`: `onecore\internal\sdk\inc\wil\opensource/wil/filesystem.h`

## pseudocode

```c
int __fastcall wil::CreateDirectoryDeepNoThrow(const WCHAR *this, const unsigned __int16 *a2)
{
  DWORD LastError; // eax
  const unsigned __int16 *v4; // rdx
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // rax
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rsi
  int DirectoryDeepNoThrow; // eax
  const unsigned __int16 *v11; // rdx
  int v12; // edi
  __int64 v13; // rdx
  const struct std::nothrow_t *v14; // rdx
  const struct std::nothrow_t *v15; // rdx
  __int64 v16; // rdx
  unsigned int v17; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  PCWSTR ppszRootEnd; // [rsp+48h] [rbp+10h] BYREF

  if ( !CreateDirectoryW(this, 0) )
  {
    LastError = GetLastError();
    if ( LastError == 3 )
    {
      ppszRootEnd = 0;
      if ( PathCchSkipRoot(this, &ppszRootEnd) >= 0 )
      {
        if ( *ppszRootEnd )
        {
          v5 = wil::find_last_path_segment(this, v4) - this;
          if ( v5 )
          {
            v6 = 2 * (v5 + 1);
            if ( !is_mul_ok(v5 + 1, 2u) )
              v6 = -1;
            v7 = (unsigned __int16 *)operator new[](v6, (const struct std::nothrow_t *)std::nothrow);
            v8 = v7;
            if ( !v7 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x82,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                (const char *)0x8007000ELL,
                v17);
              return -2147024882;
            }
            DirectoryDeepNoThrow = StringCchCopyNW(v7, v5 + 1, this, v5);
            v12 = DirectoryDeepNoThrow;
            if ( DirectoryDeepNoThrow < 0 )
            {
              v13 = 131;
LABEL_14:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v13,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                (const char *)(unsigned int)DirectoryDeepNoThrow,
                v17);
              operator delete(v8, v15);
              return v12;
            }
            DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow((wil *)v8, v11);
            v12 = DirectoryDeepNoThrow;
            if ( DirectoryDeepNoThrow < 0 )
            {
              v13 = 132;
              goto LABEL_14;
            }
            operator delete(v8, v14);
          }
        }
      }
      if ( !CreateDirectoryW(this, 0) )
      {
        LastError = GetLastError();
        if ( LastError != 183 )
        {
          if ( LastError )
          {
            v16 = 139;
            return wil::details::in1diag3::Return_Win32(
                     retaddr,
                     (void *)v16,
                     (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
                     (const char *)LastError,
                     v17);
          }
        }
      }
    }
    else if ( LastError != 183 && LastError )
    {
      v16 = 145;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v16,
               (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/filesystem.h",
               (const char *)LastError,
               v17);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800a1478  mov     [rsp+arg_0], rbx
0x1800a147d  mov     [rsp+arg_10], rbp
0x1800a1482  push    rsi
0x1800a1483  push    rdi
0x1800a1484  push    r14; unsigned int
0x1800a1486  sub     rsp, 20h
0x1800a148a  xor     edx, edx; lpSecurityAttributes
0x1800a148c  mov     rbx, rcx
0x1800a148f  call    cs:__imp_CreateDirectoryW
0x1800a1495  xor     r14d, r14d
0x1800a1498  test    eax, eax
0x1800a149a  jnz     loc_1800A15E5
0x1800a14a0  call    cs:__imp_GetLastError
0x1800a14a6  cmp     eax, 3
0x1800a14a9  jnz     loc_1800A15D3
0x1800a14af  lea     rdx, [rsp+38h+ppszRootEnd]; ppszRootEnd
0x1800a14b4  mov     [rsp+38h+ppszRootEnd], r14
0x1800a14b9  mov     rcx, rbx; pszPath
0x1800a14bc  call    cs:__imp_PathCchSkipRoot
0x1800a14c2  test    eax, eax
0x1800a14c4  js      loc_1800A1598
0x1800a14ca  mov     rax, [rsp+38h+ppszRootEnd]
0x1800a14cf  cmp     [rax], r14w
0x1800a14d3  jz      loc_1800A1598
0x1800a14d9  mov     rcx, rbx; lpStringSource
0x1800a14dc  call    ?find_last_path_segment@wil@@YAPEBGPEBG@Z; wil::find_last_path_segment(ushort const *)
0x1800a14e1  mov     rdi, rax
0x1800a14e4  sub     rdi, rbx
0x1800a14e7  sar     rdi, 1
0x1800a14ea  jz      loc_1800A1598
0x1800a14f0  lea     rcx, [r14-1]
0x1800a14f4  lea     rbp, [rdi+1]
0x1800a14f8  lea     eax, [r14+2]
0x1800a14fc  mul     rbp
0x1800a14ff  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a1506  cmovb   rax, rcx
0x1800a150a  mov     rcx, rax; unsigned __int64
0x1800a150d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800a1512  mov     rsi, rax
0x1800a1515  test    rax, rax
0x1800a1518  jnz     short loc_1800A153F
0x1800a151a  mov     rcx, [rsp+38h]; this
0x1800a151f  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a1526  mov     ebx, 8007000Eh
0x1800a152b  mov     edx, 82h; void *
0x1800a1530  mov     r9d, ebx; char *
0x1800a1533  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1538  mov     eax, ebx
0x1800a153a  jmp     loc_1800A15E7
0x1800a153f  mov     r9, rdi; unsigned __int64
0x1800a1542  mov     r8, rbx; unsigned __int16 *
0x1800a1545  mov     rdx, rbp; unsigned __int64
0x1800a1548  mov     rcx, rsi; unsigned __int16 *
0x1800a154b  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800a1550  mov     edi, eax
0x1800a1552  test    eax, eax
0x1800a1554  jns     short loc_1800A155D
0x1800a1556  mov     edx, 83h
0x1800a155b  jmp     short loc_1800A1570
0x1800a155d  mov     rcx, rsi; this
0x1800a1560  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x1800a1565  mov     edi, eax
0x1800a1567  test    eax, eax
0x1800a1569  jns     short loc_1800A1590
0x1800a156b  mov     edx, 84h; void *
0x1800a1570  mov     rcx, [rsp+38h]; this
0x1800a1575  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a157c  mov     r9d, eax; char *
0x1800a157f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1584  mov     rcx, rsi; void *
0x1800a1587  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a158c  mov     eax, edi
0x1800a158e  jmp     short loc_1800A15E7
0x1800a1590  mov     rcx, rsi; void *
0x1800a1593  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a1598  xor     edx, edx; lpSecurityAttributes
0x1800a159a  mov     rcx, rbx; lpPathName
0x1800a159d  call    cs:__imp_CreateDirectoryW
0x1800a15a3  test    eax, eax
0x1800a15a5  jnz     short loc_1800A15E5
0x1800a15a7  call    cs:__imp_GetLastError
0x1800a15ad  cmp     eax, 0B7h
0x1800a15b2  jz      short loc_1800A15E5
0x1800a15b4  test    eax, eax
0x1800a15b6  jz      short loc_1800A15E5
0x1800a15b8  mov     edx, 8Bh; void *
0x1800a15bd  mov     rcx, [rsp+38h]; this
0x1800a15c2  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a15c9  mov     r9d, eax; char *
0x1800a15cc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a15d1  jmp     short loc_1800A15E7
0x1800a15d3  cmp     eax, 0B7h
0x1800a15d8  jz      short loc_1800A15E5
0x1800a15da  test    eax, eax
0x1800a15dc  jz      short loc_1800A15E5
0x1800a15de  mov     edx, 91h
0x1800a15e3  jmp     short loc_1800A15BD
0x1800a15e5  xor     eax, eax
0x1800a15e7  mov     rbx, [rsp+38h+arg_0]
0x1800a15ec  mov     rbp, [rsp+38h+arg_10]
0x1800a15f1  add     rsp, 20h
0x1800a15f5  pop     r14
0x1800a15f7  pop     rdi
0x1800a15f8  pop     rsi
0x1800a15f9  retn
```
