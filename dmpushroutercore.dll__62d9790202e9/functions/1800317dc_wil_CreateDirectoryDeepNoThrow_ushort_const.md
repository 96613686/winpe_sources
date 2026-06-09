# wil::CreateDirectoryDeepNoThrow(ushort const *)

- ea: `0x1800317dc`
- end: `0x180031a0e`
- name: `?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z`
- size: `562`
- prototype: `int __fastcall(const WCHAR *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path`

## callers

- `0x1800317dc`
- `0x180031a14`

## callees

- `0x180003a14`
- `0x1800060b4`
- `0x18000bab4`
- `0x18001cc68`
- `0x1800317dc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180031880`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180031880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031804`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031988`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031804`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031988`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800317f3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003197e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800317f3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003197e`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x180031820`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x180031820`

## string_xrefs

- `0x1800318cc`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800319a3`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`
- `0x1800319cf`: `onecore\internal\sdk\inc\wil\opensource\wil\filesystem.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
int __fastcall wil::CreateDirectoryDeepNoThrow(const WCHAR *this, const unsigned __int16 *a2)
{
  DWORD LastError; // eax
  __int64 v4; // r8
  const WCHAR *v5; // rdi
  int StringOrdinal; // eax
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rbp
  unsigned __int64 v9; // rax
  wil *v10; // rax
  wil *v11; // rbx
  unsigned int v13; // edi
  const WCHAR *v14; // rax
  unsigned __int16 *v15; // rdx
  unsigned __int16 *v16; // rcx
  int DirectoryDeepNoThrow; // eax
  const struct std::nothrow_t *v18; // rdx
  unsigned __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // rdx
  const struct std::nothrow_t *v22; // rdx
  int cchValue; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  PCWSTR ppszRootEnd; // [rsp+58h] [rbp+10h] BYREF

  if ( CreateDirectoryW(this, 0) )
    return 0;
  LastError = GetLastError();
  if ( LastError == 3 )
  {
    ppszRootEnd = 0;
    if ( PathCchSkipRoot(this, &ppszRootEnd) < 0 || !*ppszRootEnd )
      goto LABEL_31;
    v4 = -1;
    do
      ++v4;
    while ( this[v4] );
    v5 = &this[v4];
    if ( v4 && *(v5 - 1) == 92 )
      LODWORD(v4) = v4 - 1;
    StringOrdinal = FindStringOrdinal(0x800000u, this, v4, L"\\", 1, 1);
    if ( StringOrdinal != -1 )
      v5 = &this[StringOrdinal + 1];
    v7 = v5 - this;
    if ( !v7 )
      goto LABEL_31;
    v8 = v7 + 1;
    v9 = 2 * (v7 + 1);
    if ( !is_mul_ok(v7 + 1, 2u) )
      v9 = -1;
    v10 = (wil *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
    v11 = v10;
    if ( !v10 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
        (const char *)0x8007000ELL,
        cchValue);
      return -2147024882;
    }
    if ( v7 == -1 )
    {
      v13 = -2147024809;
    }
    else if ( v8 > 0x7FFFFFFF || v7 > 0x7FFFFFFE )
    {
      v13 = -2147024809;
      *(_WORD *)v10 = 0;
    }
    else
    {
      v14 = this;
      v15 = (unsigned __int16 *)v11;
      do
      {
        if ( !v7 )
          break;
        if ( !*v14 )
          break;
        *v15++ = *v14++;
        --v7;
        --v8;
      }
      while ( v8 );
      v16 = v15 - 1;
      v13 = v8 == 0 ? 0x8007007A : 0;
      if ( v8 )
        v16 = v15;
      *v16 = 0;
      if ( v8 )
      {
        DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow(v11, v15);
        v13 = DirectoryDeepNoThrow;
        if ( DirectoryDeepNoThrow < 0 )
        {
          v19 = (unsigned int)DirectoryDeepNoThrow;
          v20 = 132;
LABEL_38:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v20,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
            (const char *)v19,
            cchValue);
          operator delete(v11, v22);
          return v13;
        }
        operator delete(v11, v18);
LABEL_31:
        if ( !CreateDirectoryW(this, 0) )
        {
          LastError = GetLastError();
          if ( LastError != 183 )
          {
            if ( LastError )
            {
              v21 = 139;
              return wil::details::in1diag3::Return_Win32(
                       retaddr,
                       (void *)v21,
                       (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
                       (const char *)LastError,
                       cchValue);
            }
          }
        }
        return 0;
      }
    }
    v19 = v13;
    v20 = 131;
    goto LABEL_38;
  }
  if ( LastError != 183 && LastError )
  {
    v21 = 145;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v21,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\filesystem.h",
             (const char *)LastError,
             cchValue);
  }
  return 0;
}

```

## disassembly

```asm
0x1800317dc  mov     [rsp+arg_0], rbx
0x1800317e1  mov     [rsp+arg_10], rbp
0x1800317e6  push    rsi
0x1800317e7  push    rdi
0x1800317e8  push    r14
0x1800317ea  sub     rsp, 30h
0x1800317ee  xor     edx, edx; lpSecurityAttributes
0x1800317f0  mov     rsi, rcx
0x1800317f3  call    cs:__imp_CreateDirectoryW
0x1800317f9  xor     r14d, r14d
0x1800317fc  test    eax, eax
0x1800317fe  jnz     loc_1800319F9
0x180031804  call    cs:__imp_GetLastError
0x18003180a  cmp     eax, 3
0x18003180d  jnz     loc_1800319E7
0x180031813  lea     rdx, [rsp+48h+ppszRootEnd]; ppszRootEnd
0x180031818  mov     [rsp+48h+ppszRootEnd], r14
0x18003181d  mov     rcx, rsi; pszPath
0x180031820  call    cs:__imp_PathCchSkipRoot
0x180031826  test    eax, eax
0x180031828  js      loc_180031979
0x18003182e  mov     rax, [rsp+48h+ppszRootEnd]
0x180031833  cmp     [rax], r14w
0x180031837  jz      loc_180031979
0x18003183d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180031841  mov     r8, rbx
0x180031844  inc     r8
0x180031847  cmp     [rsi+r8*2], r14w
0x18003184c  jnz     short loc_180031844
0x18003184e  lea     rdi, [rsi+r8*2]
0x180031852  test    r8, r8
0x180031855  jz      short loc_180031861
0x180031857  cmp     word ptr [rdi-2], 5Ch ; '\'
0x18003185c  jnz     short loc_180031861
0x18003185e  dec     r8; cchSource
0x180031861  mov     [rsp+48h+bIgnoreCase], 1; bIgnoreCase
0x180031869  lea     r9, StringValue; "\\"
0x180031870  mov     rdx, rsi; lpStringSource
0x180031873  mov     [rsp+48h+cchValue], 1; int
0x18003187b  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x180031880  call    cs:__imp_FindStringOrdinal
0x180031886  cmp     eax, ebx
0x180031888  jz      short loc_180031894
0x18003188a  movsxd  rdi, eax
0x18003188d  inc     rdi
0x180031890  lea     rdi, [rsi+rdi*2]
0x180031894  sub     rdi, rsi
0x180031897  sar     rdi, 1
0x18003189a  jz      loc_180031979
0x1800318a0  lea     rbp, [rdi+1]
0x1800318a4  mov     eax, 2
0x1800318a9  mul     rbp
0x1800318ac  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800318b3  cmovb   rax, rbx
0x1800318b7  mov     rcx, rax; unsigned __int64
0x1800318ba  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800318bf  mov     rbx, rax
0x1800318c2  test    rax, rax
0x1800318c5  jnz     short loc_1800318EC
0x1800318c7  mov     rcx, [rsp+48h]; this
0x1800318cc  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800318d3  mov     ebx, 8007000Eh
0x1800318d8  mov     edx, 82h; void *
0x1800318dd  mov     r9d, ebx; char *
0x1800318e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800318e5  mov     eax, ebx
0x1800318e7  jmp     loc_1800319FB
0x1800318ec  test    rbp, rbp
0x1800318ef  jz      loc_1800319B4
0x1800318f5  cmp     rbp, 7FFFFFFFh
0x1800318fc  jbe     short loc_180031908
0x1800318fe  mov     edi, 80070057h
0x180031903  jmp     loc_1800319BE
0x180031908  cmp     rdi, 7FFFFFFEh
0x18003190f  ja      short loc_1800318FE
0x180031911  mov     rax, rsi
0x180031914  mov     rdx, rbx
0x180031917  test    rdi, rdi
0x18003191a  jz      short loc_180031938
0x18003191c  movzx   ecx, word ptr [rax]
0x18003191f  test    cx, cx
0x180031922  jz      short loc_180031938
0x180031924  mov     [rdx], cx
0x180031927  add     rax, 2
0x18003192b  add     rdx, 2; unsigned __int16 *
0x18003192f  dec     rdi
0x180031932  sub     rbp, 1
0x180031936  jnz     short loc_180031917
0x180031938  mov     rax, rbp
0x18003193b  lea     rcx, [rdx-2]
0x18003193f  neg     rax
0x180031942  sbb     edi, edi
0x180031944  not     edi
0x180031946  and     edi, 8007007Ah
0x18003194c  test    rbp, rbp
0x18003194f  cmovnz  rcx, rdx
0x180031953  mov     [rcx], r14w
0x180031957  jz      short loc_1800319C2
0x180031959  mov     rcx, rbx; this
0x18003195c  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x180031961  mov     edi, eax
0x180031963  test    eax, eax
0x180031965  jns     short loc_180031971
0x180031967  mov     r9d, eax
0x18003196a  mov     edx, 84h
0x18003196f  jmp     short loc_1800319CA
0x180031971  mov     rcx, rbx; void *
0x180031974  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180031979  xor     edx, edx; lpSecurityAttributes
0x18003197b  mov     rcx, rsi; lpPathName
0x18003197e  call    cs:__imp_CreateDirectoryW
0x180031984  test    eax, eax
0x180031986  jnz     short loc_1800319F9
0x180031988  call    cs:__imp_GetLastError
0x18003198e  cmp     eax, 0B7h
0x180031993  jz      short loc_1800319F9
0x180031995  test    eax, eax
0x180031997  jz      short loc_1800319F9
0x180031999  mov     edx, 8Bh; void *
0x18003199e  mov     rcx, [rsp+48h]; this
0x1800319a3  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800319aa  mov     r9d, eax; char *
0x1800319ad  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800319b2  jmp     short loc_1800319FB
0x1800319b4  mov     edi, 80070057h
0x1800319b9  test    rbp, rbp
0x1800319bc  jz      short loc_1800319C2
0x1800319be  mov     [rax], r14w
0x1800319c2  mov     r9d, edi; char *
0x1800319c5  mov     edx, 83h; void *
0x1800319ca  mov     rcx, [rsp+48h]; this
0x1800319cf  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800319d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800319db  mov     rcx, rbx; void *
0x1800319de  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800319e3  mov     eax, edi
0x1800319e5  jmp     short loc_1800319FB
0x1800319e7  cmp     eax, 0B7h
0x1800319ec  jz      short loc_1800319F9
0x1800319ee  test    eax, eax
0x1800319f0  jz      short loc_1800319F9
0x1800319f2  mov     edx, 91h
0x1800319f7  jmp     short loc_18003199E
0x1800319f9  xor     eax, eax
0x1800319fb  mov     rbx, [rsp+48h+arg_0]
0x180031a00  mov     rbp, [rsp+48h+arg_10]
0x180031a05  add     rsp, 30h
0x180031a09  pop     r14
0x180031a0b  pop     rdi
0x180031a0c  pop     rsi
0x180031a0d  retn
```
