# wil::CreateDirectoryDeepNoThrow(ushort const *)

- ea: `0x1400554f4`
- end: `0x1400556df`
- name: `?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z`
- size: `491`
- prototype: `__int64 __fastcall(wil *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path`

## callers

- `0x1400554f4`
- `0x14005f3e4`

## callees

- `0x1400036e4`
- `0x140005864`
- `0x14000b0f4`
- `0x140013068`
- `0x140019444`
- `0x1400554f4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1400555a7`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1400555a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140055522`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140055685`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140055522`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140055685`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14005550b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140055675`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14005550b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140055675`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x140055544`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x140055544`

## string_xrefs

- `0x1400555f9`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x14005564f`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1400556a6`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

## pseudocode

```c
int __fastcall wil::CreateDirectoryDeepNoThrow(wil *this, const unsigned __int16 *a2)
{
  DWORD LastError; // eax
  __int64 v4; // r8
  char *v5; // rbx
  int StringOrdinal; // eax
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rax
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rsi
  int v11; // ebx
  int DirectoryDeepNoThrow; // eax
  const unsigned __int16 *v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdx
  int cchValue; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  PCWSTR ppszRootEnd; // [rsp+58h] [rbp+10h] BYREF

  if ( !CreateDirectoryW((LPCWSTR)this, 0) )
  {
    LastError = GetLastError();
    if ( LastError == 3 )
    {
      ppszRootEnd = 0;
      if ( PathCchSkipRoot((PCWSTR)this, &ppszRootEnd) >= 0 && *ppszRootEnd )
      {
        v4 = -1;
        do
          ++v4;
        while ( *((_WORD *)this + v4) );
        v5 = (char *)this + 2 * v4;
        if ( v4 && *((_WORD *)v5 - 1) == 92 )
          LODWORD(v4) = v4 - 1;
        StringOrdinal = FindStringOrdinal(0x800000u, (LPCWSTR)this, v4, L"\\", 1, 1);
        if ( StringOrdinal != -1 )
          v5 = (char *)this + 2 * StringOrdinal + 2;
        v7 = (v5 - (char *)this) >> 1;
        if ( v7 )
        {
          v8 = 2 * (v7 + 1);
          if ( !is_mul_ok(v7 + 1, 2u) )
            v8 = -1;
          v9 = (unsigned __int16 *)operator new[](v8, (const struct std::nothrow_t *)std::nothrow);
          v10 = v9;
          if ( !v9 )
          {
            v11 = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x82,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
              (const char *)0x8007000ELL,
              cchValue);
            return v11;
          }
          DirectoryDeepNoThrow = StringCchCopyNW(v9, v7 + 1, (const unsigned __int16 *)this, v7);
          v11 = DirectoryDeepNoThrow;
          if ( DirectoryDeepNoThrow < 0 )
          {
            v15 = 131;
LABEL_22:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v15,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
              (const char *)(unsigned int)DirectoryDeepNoThrow,
              cchValue);
            operator delete(v10);
            return v11;
          }
          DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow((wil *)v10, v14);
          v11 = DirectoryDeepNoThrow;
          if ( DirectoryDeepNoThrow < 0 )
          {
            v15 = 132;
            goto LABEL_22;
          }
          operator delete(v10);
        }
      }
      if ( !CreateDirectoryW((LPCWSTR)this, 0) )
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
                     cchValue);
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
               cchValue);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400554f4  mov     [rsp+arg_0], rbx
0x1400554f9  mov     [rsp+arg_10], rbp
0x1400554fe  push    rsi
0x1400554ff  push    rdi
0x140055500  push    r14
0x140055502  sub     rsp, 30h
0x140055506  xor     edx, edx; lpSecurityAttributes
0x140055508  mov     rdi, rcx
0x14005550b  call    cs:__imp_CreateDirectoryW
0x140055512  nop     dword ptr [rax+rax+00h]
0x140055517  xor     r14d, r14d
0x14005551a  test    eax, eax
0x14005551c  jnz     loc_1400556C9
0x140055522  call    cs:__imp_GetLastError
0x140055529  nop     dword ptr [rax+rax+00h]
0x14005552e  cmp     eax, 3
0x140055531  jnz     loc_1400556B7
0x140055537  lea     rdx, [rsp+48h+ppszRootEnd]; ppszRootEnd
0x14005553c  mov     [rsp+48h+ppszRootEnd], r14
0x140055541  mov     rcx, rdi; pszPath
0x140055544  call    cs:__imp_PathCchSkipRoot
0x14005554b  nop     dword ptr [rax+rax+00h]
0x140055550  test    eax, eax
0x140055552  js      loc_140055670
0x140055558  mov     rax, [rsp+48h+ppszRootEnd]
0x14005555d  cmp     [rax], r14w
0x140055561  jz      loc_140055670
0x140055567  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14005556b  mov     r8, rsi
0x14005556e  inc     r8
0x140055571  cmp     [rdi+r8*2], r14w
0x140055576  jnz     short loc_14005556E
0x140055578  lea     rbx, [rdi+r8*2]
0x14005557c  test    r8, r8
0x14005557f  jz      short loc_14005558B
0x140055581  cmp     word ptr [rbx-2], 5Ch ; '\'
0x140055586  jnz     short loc_14005558B
0x140055588  dec     r8; cchSource
0x14005558b  mov     eax, 1
0x140055590  lea     r9, pszSrc; "\\"
0x140055597  mov     [rsp+48h+bIgnoreCase], eax; bIgnoreCase
0x14005559b  mov     rdx, rdi; lpStringSource
0x14005559e  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x1400555a3  mov     [rsp+48h+cchValue], eax; unsigned int
0x1400555a7  call    cs:__imp_FindStringOrdinal
0x1400555ae  nop     dword ptr [rax+rax+00h]
0x1400555b3  cmp     eax, esi
0x1400555b5  jz      short loc_1400555C1
0x1400555b7  movsxd  rbx, eax
0x1400555ba  inc     rbx
0x1400555bd  lea     rbx, [rdi+rbx*2]
0x1400555c1  sub     rbx, rdi
0x1400555c4  sar     rbx, 1
0x1400555c7  jz      loc_140055670
0x1400555cd  lea     rbp, [rbx+1]
0x1400555d1  mov     eax, 2
0x1400555d6  mul     rbp
0x1400555d9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400555e0  cmovb   rax, rsi
0x1400555e4  mov     rcx, rax; unsigned __int64
0x1400555e7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400555ec  mov     rsi, rax
0x1400555ef  test    rax, rax
0x1400555f2  jnz     short loc_140055619
0x1400555f4  mov     rcx, [rsp+48h]; this
0x1400555f9  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140055600  mov     ebx, 8007000Eh
0x140055605  mov     edx, 82h; void *
0x14005560a  mov     r9d, ebx; char *
0x14005560d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140055612  mov     eax, ebx
0x140055614  jmp     loc_1400556CB
0x140055619  mov     r9, rbx; unsigned __int64
0x14005561c  mov     r8, rdi; unsigned __int16 *
0x14005561f  mov     rdx, rbp; unsigned __int64
0x140055622  mov     rcx, rsi; unsigned __int16 *
0x140055625  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x14005562a  mov     ebx, eax
0x14005562c  test    eax, eax
0x14005562e  jns     short loc_140055637
0x140055630  mov     edx, 83h
0x140055635  jmp     short loc_14005564A
0x140055637  mov     rcx, rsi; this
0x14005563a  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x14005563f  mov     ebx, eax
0x140055641  test    eax, eax
0x140055643  jns     short loc_140055668
0x140055645  mov     edx, 84h; void *
0x14005564a  mov     rcx, [rsp+48h]; this
0x14005564f  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140055656  mov     r9d, eax; char *
0x140055659  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005565e  mov     rcx, rsi; Block
0x140055661  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140055666  jmp     short loc_140055612
0x140055668  mov     rcx, rsi; Block
0x14005566b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140055670  xor     edx, edx; lpSecurityAttributes
0x140055672  mov     rcx, rdi; lpPathName
0x140055675  call    cs:__imp_CreateDirectoryW
0x14005567c  nop     dword ptr [rax+rax+00h]
0x140055681  test    eax, eax
0x140055683  jnz     short loc_1400556C9
0x140055685  call    cs:__imp_GetLastError
0x14005568c  nop     dword ptr [rax+rax+00h]
0x140055691  cmp     eax, 0B7h
0x140055696  jz      short loc_1400556C9
0x140055698  test    eax, eax
0x14005569a  jz      short loc_1400556C9
0x14005569c  mov     edx, 8Bh; void *
0x1400556a1  mov     rcx, [rsp+48h]; this
0x1400556a6  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400556ad  mov     r9d, eax; char *
0x1400556b0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400556b5  jmp     short loc_1400556CB
0x1400556b7  cmp     eax, 0B7h
0x1400556bc  jz      short loc_1400556C9
0x1400556be  test    eax, eax
0x1400556c0  jz      short loc_1400556C9
0x1400556c2  mov     edx, 91h
0x1400556c7  jmp     short loc_1400556A1
0x1400556c9  xor     eax, eax
0x1400556cb  mov     rbx, [rsp+48h+arg_0]
0x1400556d0  mov     rbp, [rsp+48h+arg_10]
0x1400556d5  add     rsp, 30h
0x1400556d9  pop     r14
0x1400556db  pop     rdi
0x1400556dc  pop     rsi
0x1400556dd  retn
```
