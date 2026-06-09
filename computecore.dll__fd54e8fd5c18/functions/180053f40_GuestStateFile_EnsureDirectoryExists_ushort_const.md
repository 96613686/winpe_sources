# GuestStateFile::EnsureDirectoryExists(ushort const *)

- ea: `0x180053f40`
- end: `0x180054170`
- name: `?EnsureDirectoryExists@GuestStateFile@@CAXPEBG@Z`
- size: `560`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180053c84`
- `0x180054ee0`

## callees

- `0x1800067c0`
- `0x180009e8c`
- `0x180011894`
- `0x18001587c`
- `0x18001e220`
- `0x180053f40`
- `0x18005ac60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053ffe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800540c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053ffe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800540c2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800540d7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800540d7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180053ff0`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800540b8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180053ff0`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800540b8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x180053fd6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x180053fd6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x180054079`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x180054079`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18005406a`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18005406a`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180053fad`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180053fad`

## string_xrefs

- `0x18005412a`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x18005415e`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x180054152`: `Failed to create directory at "%ws"`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall GuestStateFile::EnsureDirectoryExists(const unsigned __int16 *a1)
{
  __int64 v1; // r8
  WCHAR *v2; // rcx
  HRESULT v3; // eax
  const WCHAR *v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  DWORD LastError; // eax
  __int64 v9; // rcx
  WCHAR *v10; // rax
  WCHAR *v11; // rcx
  LPWSTR v12; // rax
  LPWSTR v13; // rbx
  WCHAR v14; // ax
  DWORD v15; // eax
  DWORD FileAttributesW; // eax
  const char *v17; // rax
  const char *v18; // r9
  int v19; // [rsp+20h] [rbp-E0h]
  PWSTR pszPath[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v21; // [rsp+40h] [rbp-C0h]
  WCHAR PathName[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  *(_OWORD *)pszPath = 0;
  v21 = 0;
  v1 = -1;
  do
    ++v1;
  while ( a1[v1] );
  std::wstring::_Construct<1,unsigned short const *>(pszPath, a1);
  v2 = (WCHAR *)pszPath;
  if ( *((_QWORD *)&v21 + 1) > 7u )
    v2 = pszPath[0];
  v3 = PathCchRemoveFileSpec(v2, v21 + 1);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
      (const char *)(unsigned int)v3,
      v19);
  v4 = (const WCHAR *)pszPath;
  if ( *((_QWORD *)&v21 + 1) > 7u )
    v4 = pszPath[0];
  if ( PathIsRelativeW(v4) )
    goto LABEL_9;
  if ( CreateDirectoryW(v4, 0) )
    goto LABEL_32;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError != 3 )
  {
LABEL_33:
    if ( !(_DWORD)v7 || (_DWORD)v7 == 183 )
      goto LABEL_32;
LABEL_37:
    v17 = (const char *)std::wstring::c_str(pszPath, v5, v6, v7);
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0xCC,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
      v18,
      (unsigned int)"Failed to create directory at \"%ws\"",
      v17);
  }
  v9 = 2147483646;
  v5 = 260;
  v10 = PathName;
  do
  {
    if ( !v9 )
      break;
    v6 = *v4;
    if ( !(_WORD)v6 )
      break;
    ++v4;
    *v10++ = v6;
    --v9;
    --v5;
  }
  while ( v5 );
  v11 = v10 - 1;
  if ( v5 )
    v11 = v10;
  *v11 = 0;
  if ( !v5 || PathCchAddBackslash(PathName, 0x104u) < 0 )
  {
    v7 = 206;
    goto LABEL_37;
  }
  v12 = PathSkipRootW(PathName);
  v13 = v12;
  if ( !v12 )
  {
LABEL_9:
    v7 = 161;
    goto LABEL_37;
  }
  if ( *v12 )
  {
    do
    {
      v14 = *v13;
      do
      {
        if ( v14 == 92 )
          break;
        v14 = *++v13;
      }
      while ( *v13 );
      if ( *v13 )
      {
        *v13 = 0;
        if ( !CreateDirectoryW(PathName, 0) )
        {
          v15 = GetLastError();
          v7 = v15;
          if ( v15 != 183 )
            goto LABEL_33;
          FileAttributesW = GetFileAttributesW(PathName);
          if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
            break;
        }
      }
      *v13++ = 92;
    }
    while ( *v13 );
  }
LABEL_32:
  std::wstring::~wstring(pszPath);
}

```

## disassembly

```asm
0x180053f40  push    rbp
0x180053f42  push    rbx
0x180053f43  push    rsi
0x180053f44  push    rdi
0x180053f45  lea     rbp, [rsp-178h]
0x180053f4d  sub     rsp, 278h
0x180053f54  mov     rax, cs:__security_cookie
0x180053f5b  xor     rax, rsp
0x180053f5e  mov     [rbp+190h+var_30], rax
0x180053f65  xorps   xmm0, xmm0
0x180053f68  movups  xmmword ptr [rsp+290h+pszPath], xmm0
0x180053f6d  xorps   xmm1, xmm1
0x180053f70  movdqu  [rsp+290h+var_250], xmm1
0x180053f76  or      r8, 0FFFFFFFFFFFFFFFFh
0x180053f7a  xor     edi, edi
0x180053f7c  inc     r8
0x180053f7f  cmp     [rcx+r8*2], di
0x180053f84  jnz     short loc_180053F7C
0x180053f86  mov     rdx, rcx
0x180053f89  lea     rcx, [rsp+290h+pszPath]
0x180053f8e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180053f93  nop
0x180053f94  mov     rdx, qword ptr [rsp+290h+var_250]
0x180053f99  lea     rcx, [rsp+290h+pszPath]
0x180053f9e  cmp     qword ptr [rsp+290h+var_250+8], 7
0x180053fa4  cmova   rcx, [rsp+290h+pszPath]; pszPath
0x180053faa  inc     rdx; cchPath
0x180053fad  call    cs:__imp_PathCchRemoveFileSpec
0x180053fb3  mov     rcx, [rbp+198h]; this
0x180053fba  test    eax, eax
0x180053fbc  js      loc_180054127
0x180053fc2  lea     rbx, [rsp+290h+pszPath]
0x180053fc7  cmp     qword ptr [rsp+290h+var_250+8], 7
0x180053fcd  cmova   rbx, [rsp+290h+pszPath]
0x180053fd3  mov     rcx, rbx; pszPath
0x180053fd6  call    cs:__imp_PathIsRelativeW
0x180053fdc  test    eax, eax
0x180053fde  jz      short loc_180053FEB
0x180053fe0  mov     r9d, 0A1h
0x180053fe6  jmp     loc_18005413C
0x180053feb  xor     edx, edx; lpSecurityAttributes
0x180053fed  mov     rcx, rbx; lpPathName
0x180053ff0  call    cs:__imp_CreateDirectoryW
0x180053ff6  test    eax, eax
0x180053ff8  jnz     loc_1800540F2
0x180053ffe  call    cs:__imp_GetLastError
0x180054004  mov     r9d, eax
0x180054007  cmp     eax, 3
0x18005400a  jnz     loc_180054117
0x180054010  mov     ecx, 7FFFFFFEh
0x180054015  mov     r9d, 104h
0x18005401b  mov     edx, r9d
0x18005401e  lea     rax, [rsp+290h+PathName]
0x180054023  test    rcx, rcx
0x180054026  jz      short loc_180054047
0x180054028  movzx   r8d, word ptr [rbx]
0x18005402c  test    r8w, r8w
0x180054030  jz      short loc_180054047
0x180054032  add     rbx, 2
0x180054036  mov     [rax], r8w
0x18005403a  add     rax, 2
0x18005403e  dec     rcx
0x180054041  sub     rdx, 1
0x180054045  jnz     short loc_180054023
0x180054047  lea     rcx, [rax-2]
0x18005404b  test    rdx, rdx
0x18005404e  cmovnz  rcx, rax
0x180054052  mov     [rcx], di
0x180054055  jnz     short loc_180054062
0x180054057  mov     r9d, 0CEh
0x18005405d  jmp     loc_18005413C
0x180054062  mov     rdx, r9; cchPath
0x180054065  lea     rcx, [rsp+290h+PathName]; pszPath
0x18005406a  call    cs:__imp_PathCchAddBackslash
0x180054070  test    eax, eax
0x180054072  js      short loc_180054057
0x180054074  lea     rcx, [rsp+290h+PathName]; pszPath
0x180054079  call    cs:__imp_PathSkipRootW
0x18005407f  mov     rbx, rax
0x180054082  test    rax, rax
0x180054085  jz      loc_180053FE0
0x18005408b  cmp     [rax], di
0x18005408e  jz      short loc_1800540F2
0x180054090  mov     esi, 5Ch ; '\'
0x180054095  movzx   eax, word ptr [rbx]
0x180054098  cmp     ax, si
0x18005409b  jz      short loc_1800540A9
0x18005409d  add     rbx, 2
0x1800540a1  movzx   eax, word ptr [rbx]
0x1800540a4  test    ax, ax
0x1800540a7  jnz     short loc_180054098
0x1800540a9  cmp     [rbx], di
0x1800540ac  jz      short loc_1800540E6
0x1800540ae  mov     [rbx], di
0x1800540b1  xor     edx, edx; lpSecurityAttributes
0x1800540b3  lea     rcx, [rsp+290h+PathName]; lpPathName
0x1800540b8  call    cs:__imp_CreateDirectoryW
0x1800540be  test    eax, eax
0x1800540c0  jnz     short loc_1800540E6
0x1800540c2  call    cs:__imp_GetLastError
0x1800540c8  mov     r9d, eax
0x1800540cb  cmp     eax, 0B7h
0x1800540d0  jnz     short loc_180054117
0x1800540d2  lea     rcx, [rsp+290h+PathName]; lpFileName
0x1800540d7  call    cs:__imp_GetFileAttributesW
0x1800540dd  cmp     eax, 0FFFFFFFFh
0x1800540e0  jz      short loc_1800540F2
0x1800540e2  test    al, 10h
0x1800540e4  jz      short loc_1800540F2
0x1800540e6  mov     [rbx], si
0x1800540e9  add     rbx, 2
0x1800540ed  cmp     [rbx], di
0x1800540f0  jnz     short loc_180054095
0x1800540f2  lea     rcx, [rsp+290h+pszPath]
0x1800540f7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800540fc  mov     rcx, [rbp+190h+var_30]
0x180054103  xor     rcx, rsp; StackCookie
0x180054106  call    __security_check_cookie
0x18005410b  add     rsp, 278h
0x180054112  pop     rdi
0x180054113  pop     rsi
0x180054114  pop     rbx
0x180054115  pop     rbp
0x180054116  retn
0x180054117  test    r9d, r9d
0x18005411a  jz      short loc_1800540F2
0x18005411c  cmp     r9d, 0B7h
0x180054123  jnz     short loc_18005413C
0x180054125  jmp     short loc_1800540F2
0x180054127  mov     r9d, eax; char *
0x18005412a  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\gueststate\\guests"...
0x180054131  mov     edx, 0C5h; void *
0x180054136  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005413c  lea     rcx, [rsp+290h+pszPath]
0x180054141  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180054146  mov     rcx, [rbp+198h]; this
0x18005414d  mov     [rsp+290h+var_268], rax; char *
0x180054152  lea     rax, aFailedToCreate; "Failed to create directory at \"%ws\""
0x180054159  mov     qword ptr [rsp+290h+var_270], rax; unsigned int
0x18005415e  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\gueststate\\guests"...
0x180054165  mov     edx, 0CCh; void *
0x18005416a  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
