# wil::CreateDirectoryDeepNoThrow(ushort const *)

- ea: `0x1800d3634`
- end: `0x1800d37fa`
- name: `?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z`
- size: `454`
- prototype: `__int64 __fastcall(wil *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, reparse_path`

## callers

- `0x18003b3f0`
- `0x1800d3634`
- `0x1800d3800`

## callees

- `0x1800091b0`
- `0x180009260`
- `0x18000d4d4`
- `0x18002aed0`
- `0x1800d3634`
- `0x1800d496c`
- `0x1800d49c4`
- `0x1800d5434`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d365d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3778`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d365d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3778`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800d3646`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800d3768`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800d3646`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800d3768`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x1800d367f`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x1800d367f`

## string_xrefs

- `0x1800d36e8`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800d3799`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800d37c0`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

## pseudocode

```c
int __fastcall wil::CreateDirectoryDeepNoThrow(const WCHAR *this, const unsigned __int16 *a2)
{
  DWORD LastError; // eax
  const unsigned __int16 *v4; // rdx
  size_t v5; // rdi
  unsigned __int64 v6; // rax
  const wchar_t *v7; // rcx
  wchar_t *v8; // rbx
  size_t v9; // r8
  size_t v11; // rdx
  HRESULT v12; // ebp
  size_t *v13; // r8
  const unsigned __int16 *v14; // rdx
  int DirectoryDeepNoThrow; // eax
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // rdx
  unsigned int cchToCopy; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  PCWSTR ppszRootEnd; // [rsp+78h] [rbp+10h] BYREF

  if ( CreateDirectoryW(this, 0) )
    return 0;
  LastError = GetLastError();
  if ( LastError == 3 )
  {
    ppszRootEnd = 0;
    if ( PathCchSkipRoot(this, &ppszRootEnd) < 0 )
      goto LABEL_17;
    if ( !*ppszRootEnd )
      goto LABEL_17;
    v5 = wil::find_last_path_segment(this, v4) - this;
    if ( !v5 )
      goto LABEL_17;
    v6 = 2 * (v5 + 1);
    if ( !is_mul_ok(v5 + 1, 2u) )
      v6 = -1;
    v8 = (wchar_t *)operator new[](v6, (const struct std::nothrow_t *)std::nothrow);
    if ( !v8 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)0x8007000ELL,
        cchToCopy);
      return -2147024882;
    }
    v12 = StringValidateDestW(v7, v5 + 1, v9);
    if ( v12 < 0 )
    {
      if ( v5 != -1 )
        goto LABEL_23;
    }
    else
    {
      if ( v5 > 0x7FFFFFFE )
      {
        v12 = -2147024809;
LABEL_23:
        *v8 = 0;
        goto LABEL_24;
      }
      v12 = StringCopyWorkerW_0(v8, v11, v13, this, v5);
      if ( v12 >= 0 )
      {
        DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow((wil *)v8, v14);
        v12 = DirectoryDeepNoThrow;
        if ( DirectoryDeepNoThrow < 0 )
        {
          v16 = (unsigned int)DirectoryDeepNoThrow;
          v17 = 132;
LABEL_25:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v17,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
            (const char *)v16,
            cchToCopy);
          operator delete(v8);
          return v12;
        }
        operator delete(v8);
LABEL_17:
        if ( !CreateDirectoryW(this, 0) )
        {
          LastError = GetLastError();
          if ( LastError != 183 )
          {
            if ( LastError )
            {
              v18 = 139;
              return wil::details::in1diag3::Return_Win32(
                       retaddr,
                       (void *)v18,
                       (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                       (const char *)LastError,
                       cchToCopy);
            }
          }
        }
        return 0;
      }
    }
LABEL_24:
    v16 = (unsigned int)v12;
    v17 = 131;
    goto LABEL_25;
  }
  if ( LastError != 183 && LastError )
  {
    v18 = 145;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v18,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
             (const char *)LastError,
             cchToCopy);
  }
  return 0;
}

```

## disassembly

```asm
0x1800d3634  push    rbx
0x1800d3636  push    rbp
0x1800d3637  push    rsi
0x1800d3638  push    rdi
0x1800d3639  push    r14
0x1800d363b  push    r15
0x1800d363d  sub     rsp, 38h
0x1800d3641  xor     edx, edx; lpSecurityAttributes
0x1800d3643  mov     rsi, rcx
0x1800d3646  call    cs:__imp_CreateDirectoryW
0x1800d364d  nop     dword ptr [rax+rax+00h]
0x1800d3652  xor     r15d, r15d
0x1800d3655  test    eax, eax
0x1800d3657  jnz     loc_1800D37EA
0x1800d365d  call    cs:__imp_GetLastError
0x1800d3664  nop     dword ptr [rax+rax+00h]
0x1800d3669  cmp     eax, 3
0x1800d366c  jnz     loc_1800D37D8
0x1800d3672  lea     rdx, [rsp+68h+ppszRootEnd]; ppszRootEnd
0x1800d3677  mov     [rsp+68h+ppszRootEnd], r15
0x1800d367c  mov     rcx, rsi; pszPath
0x1800d367f  call    cs:__imp_PathCchSkipRoot
0x1800d3686  nop     dword ptr [rax+rax+00h]
0x1800d368b  test    eax, eax
0x1800d368d  js      loc_1800D3763
0x1800d3693  mov     rax, [rsp+68h+ppszRootEnd]
0x1800d3698  cmp     [rax], r15w
0x1800d369c  jz      loc_1800D3763
0x1800d36a2  mov     rcx, rsi; lpStringSource
0x1800d36a5  call    ?find_last_path_segment@wil@@YAPEBGPEBG@Z; wil::find_last_path_segment(ushort const *)
0x1800d36aa  mov     rdi, rax
0x1800d36ad  sub     rdi, rsi
0x1800d36b0  sar     rdi, 1
0x1800d36b3  jz      loc_1800D3763
0x1800d36b9  lea     rcx, [r15-1]
0x1800d36bd  lea     r14, [rdi+1]
0x1800d36c1  lea     eax, [r15+2]
0x1800d36c5  mul     r14
0x1800d36c8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800d36cf  cmovb   rax, rcx
0x1800d36d3  mov     rcx, rax; unsigned __int64
0x1800d36d6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800d36db  mov     rbx, rax
0x1800d36de  test    rax, rax
0x1800d36e1  jnz     short loc_1800D3708
0x1800d36e3  mov     rcx, [rsp+68h]; this
0x1800d36e8  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800d36ef  mov     ebx, 8007000Eh
0x1800d36f4  mov     edx, 82h; void *
0x1800d36f9  mov     r9d, ebx; char *
0x1800d36fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d3701  mov     eax, ebx
0x1800d3703  jmp     loc_1800D37EC
0x1800d3708  mov     rdx, r14; cchDest
0x1800d370b  call    StringValidateDestW
0x1800d3710  mov     ebp, eax
0x1800d3712  test    eax, eax
0x1800d3714  js      loc_1800D37AA
0x1800d371a  cmp     rdi, 7FFFFFFEh
0x1800d3721  jbe     short loc_1800D372D
0x1800d3723  mov     ebp, 80070057h
0x1800d3728  jmp     loc_1800D37AF
0x1800d372d  mov     r9, rsi; pszSrc
0x1800d3730  mov     qword ptr [rsp+68h+cchToCopy], rdi; int
0x1800d3735  mov     rcx, rbx; pszDest
0x1800d3738  call    StringCopyWorkerW_0
0x1800d373d  mov     ebp, eax
0x1800d373f  test    eax, eax
0x1800d3741  js      short loc_1800D37B3
0x1800d3743  mov     rcx, rbx; this
0x1800d3746  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x1800d374b  mov     ebp, eax
0x1800d374d  test    eax, eax
0x1800d374f  jns     short loc_1800D375B
0x1800d3751  mov     r9d, eax
0x1800d3754  mov     edx, 84h
0x1800d3759  jmp     short loc_1800D37BB
0x1800d375b  mov     rcx, rbx; Block
0x1800d375e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d3763  xor     edx, edx; lpSecurityAttributes
0x1800d3765  mov     rcx, rsi; lpPathName
0x1800d3768  call    cs:__imp_CreateDirectoryW
0x1800d376f  nop     dword ptr [rax+rax+00h]
0x1800d3774  test    eax, eax
0x1800d3776  jnz     short loc_1800D37EA
0x1800d3778  call    cs:__imp_GetLastError
0x1800d377f  nop     dword ptr [rax+rax+00h]
0x1800d3784  cmp     eax, 0B7h
0x1800d3789  jz      short loc_1800D37EA
0x1800d378b  test    eax, eax
0x1800d378d  jz      short loc_1800D37EA
0x1800d378f  mov     edx, 8Bh; void *
0x1800d3794  mov     rcx, [rsp+68h]; this
0x1800d3799  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800d37a0  mov     r9d, eax; char *
0x1800d37a3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d37a8  jmp     short loc_1800D37EC
0x1800d37aa  test    r14, r14
0x1800d37ad  jz      short loc_1800D37B3
0x1800d37af  mov     [rbx], r15w
0x1800d37b3  mov     r9d, ebp; char *
0x1800d37b6  mov     edx, 83h; void *
0x1800d37bb  mov     rcx, [rsp+68h]; this
0x1800d37c0  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800d37c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d37cc  mov     rcx, rbx; Block
0x1800d37cf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d37d4  mov     eax, ebp
0x1800d37d6  jmp     short loc_1800D37EC
0x1800d37d8  cmp     eax, 0B7h
0x1800d37dd  jz      short loc_1800D37EA
0x1800d37df  test    eax, eax
0x1800d37e1  jz      short loc_1800D37EA
0x1800d37e3  mov     edx, 91h
0x1800d37e8  jmp     short loc_1800D3794
0x1800d37ea  xor     eax, eax
0x1800d37ec  add     rsp, 38h
0x1800d37f0  pop     r15
0x1800d37f2  pop     r14
0x1800d37f4  pop     rdi
0x1800d37f5  pop     rsi
0x1800d37f6  pop     rbp
0x1800d37f7  pop     rbx
0x1800d37f8  retn
```
