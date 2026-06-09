# wil::CreateDirectoryDeepNoThrow(ushort const *)

- ea: `0x180017c4c`
- end: `0x180017dce`
- name: `?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z`
- size: `386`
- prototype: `__int64 __fastcall(wil *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x180017c4c`
- `0x180017f60`

## callees

- `0x180002b84`
- `0x180003018`
- `0x1800076d4`
- `0x180017c4c`
- `0x1800190d8`
- `0x180019244`
- `0x180019590`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d7b`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x180017c90`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x180017c90`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180017c63`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180017d71`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180017c63`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180017d71`

## string_xrefs

- `0x180017cf3`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180017d49`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x180017d96`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

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
            v7 = (unsigned __int16 *)operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
            v8 = v7;
            if ( !v7 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x82,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
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
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
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
                     (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
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
               (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
               (const char *)LastError,
               v17);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180017c4c  mov     [rsp+arg_0], rbx
0x180017c51  mov     [rsp+arg_10], rbp
0x180017c56  push    rsi
0x180017c57  push    rdi
0x180017c58  push    r14; unsigned int
0x180017c5a  sub     rsp, 20h
0x180017c5e  xor     edx, edx; lpSecurityAttributes
0x180017c60  mov     rbx, rcx
0x180017c63  call    cs:__imp_CreateDirectoryW
0x180017c69  xor     r14d, r14d
0x180017c6c  test    eax, eax
0x180017c6e  jnz     loc_180017DB9
0x180017c74  call    cs:__imp_GetLastError
0x180017c7a  cmp     eax, 3
0x180017c7d  jnz     loc_180017DA7
0x180017c83  lea     rdx, [rsp+38h+ppszRootEnd]; ppszRootEnd
0x180017c88  mov     [rsp+38h+ppszRootEnd], r14
0x180017c8d  mov     rcx, rbx; pszPath
0x180017c90  call    cs:__imp_PathCchSkipRoot
0x180017c96  test    eax, eax
0x180017c98  js      loc_180017D6C
0x180017c9e  mov     rax, [rsp+38h+ppszRootEnd]
0x180017ca3  cmp     [rax], r14w
0x180017ca7  jz      loc_180017D6C
0x180017cad  mov     rcx, rbx; lpStringSource
0x180017cb0  call    ?find_last_path_segment@wil@@YAPEBGPEBG@Z; wil::find_last_path_segment(ushort const *)
0x180017cb5  mov     rdi, rax
0x180017cb8  sub     rdi, rbx
0x180017cbb  sar     rdi, 1
0x180017cbe  jz      loc_180017D6C
0x180017cc4  lea     rcx, [r14-1]
0x180017cc8  lea     rbp, [rdi+1]
0x180017ccc  lea     eax, [r14+2]
0x180017cd0  mul     rbp
0x180017cd3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017cda  cmovb   rax, rcx
0x180017cde  mov     rcx, rax; unsigned __int64
0x180017ce1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180017ce6  mov     rsi, rax
0x180017ce9  test    rax, rax
0x180017cec  jnz     short loc_180017D13
0x180017cee  mov     rcx, [rsp+38h]; this
0x180017cf3  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180017cfa  mov     ebx, 8007000Eh
0x180017cff  mov     edx, 82h; void *
0x180017d04  mov     r9d, ebx; char *
0x180017d07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017d0c  mov     eax, ebx
0x180017d0e  jmp     loc_180017DBB
0x180017d13  mov     r9, rdi; unsigned __int64
0x180017d16  mov     r8, rbx; unsigned __int16 *
0x180017d19  mov     rdx, rbp; unsigned __int64
0x180017d1c  mov     rcx, rsi; unsigned __int16 *
0x180017d1f  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180017d24  mov     edi, eax
0x180017d26  test    eax, eax
0x180017d28  jns     short loc_180017D31
0x180017d2a  mov     edx, 83h
0x180017d2f  jmp     short loc_180017D44
0x180017d31  mov     rcx, rsi; this
0x180017d34  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x180017d39  mov     edi, eax
0x180017d3b  test    eax, eax
0x180017d3d  jns     short loc_180017D64
0x180017d3f  mov     edx, 84h; void *
0x180017d44  mov     rcx, [rsp+38h]; this
0x180017d49  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180017d50  mov     r9d, eax; char *
0x180017d53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017d58  mov     rcx, rsi; void *
0x180017d5b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017d60  mov     eax, edi
0x180017d62  jmp     short loc_180017DBB
0x180017d64  mov     rcx, rsi; void *
0x180017d67  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017d6c  xor     edx, edx; lpSecurityAttributes
0x180017d6e  mov     rcx, rbx; lpPathName
0x180017d71  call    cs:__imp_CreateDirectoryW
0x180017d77  test    eax, eax
0x180017d79  jnz     short loc_180017DB9
0x180017d7b  call    cs:__imp_GetLastError
0x180017d81  cmp     eax, 0B7h
0x180017d86  jz      short loc_180017DB9
0x180017d88  test    eax, eax
0x180017d8a  jz      short loc_180017DB9
0x180017d8c  mov     edx, 8Bh; void *
0x180017d91  mov     rcx, [rsp+38h]; this
0x180017d96  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180017d9d  mov     r9d, eax; char *
0x180017da0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180017da5  jmp     short loc_180017DBB
0x180017da7  cmp     eax, 0B7h
0x180017dac  jz      short loc_180017DB9
0x180017dae  test    eax, eax
0x180017db0  jz      short loc_180017DB9
0x180017db2  mov     edx, 91h
0x180017db7  jmp     short loc_180017D91
0x180017db9  xor     eax, eax
0x180017dbb  mov     rbx, [rsp+38h+arg_0]
0x180017dc0  mov     rbp, [rsp+38h+arg_10]
0x180017dc5  add     rsp, 20h
0x180017dc9  pop     r14
0x180017dcb  pop     rdi
0x180017dcc  pop     rsi
0x180017dcd  retn
```
