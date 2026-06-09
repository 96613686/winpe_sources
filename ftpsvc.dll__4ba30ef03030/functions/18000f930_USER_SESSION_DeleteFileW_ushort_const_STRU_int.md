# USER_SESSION::DeleteFileW(ushort const *,STRU *,int *)

- ea: `0x18000f930`
- end: `0x18000fb2d`
- name: `?DeleteFileW@USER_SESSION@@UEAAJPEBGPEAVSTRU@@PEAH@Z`
- size: `509`
- prototype: `__int64 __fastcall(USER_SESSION *__hidden this, const unsigned __int16 *, struct STRU *, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting`

## callees

- `0x1800022b8`
- `0x18000f930`
- `0x18000fdd8`
- `0x1800116a4`
- `0x18001313c`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18000fa44`
- `KERNEL32!DeleteFileW` at `0x18000fa44`
- `KERNEL32!GetLastError` at `0x18000fa61`
- `KERNEL32!GetLastError` at `0x18000fa61`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000faee`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000faee`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000fa02`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000fa02`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000f996`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000f996`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000fb06`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000fb06`

## string_xrefs

- `0x18000fa8b`: `File system denied the access.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall USER_SESSION::DeleteFileW(USER_SESSION *this, const unsigned __int16 *a2, struct STRU *a3, int *a4)
{
  int v8; // ebx
  volatile signed __int32 *v9; // rdi
  bool v10; // zf
  void (*v11)(void); // rax
  signed int LastError; // eax
  const wchar_t *v13; // rax
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  TOKEN_CACHE_ENTRY *v16; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v17[4]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpFileName; // [rsp+70h] [rbp-90h]
  unsigned __int16 v19[264]; // [rsp+90h] [rbp-70h] BYREF

  v15 = 0;
  v16 = 0;
  memset_0(v19, 0, 0x208u);
  STRU::STRU((STRU *)v17, v19, 0x104u);
  *((_DWORD *)this + 278) = 0;
  *((_QWORD *)this + 138) = &WideCharStr;
  v8 = USER_SESSION::DoUserIsolationAndCheckAccessAndMapPath(this, (__int64)a2, 3, v17, 0, &v16, 0);
  v9 = (volatile signed __int32 *)v16;
  if ( v8 >= 0 )
  {
    if ( !a3 || (v8 = STRU::Copy(a3, lpFileName), v8 >= 0) )
    {
      v8 = USER_SESSION::Impersonate(this, (struct TOKEN_CACHE_ENTRY *)v9, &v15);
      if ( v8 >= 0 )
      {
        (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 64LL))(g_pFtpServer);
        v10 = !DeleteFileW(lpFileName);
        v11 = *(void (**)(void))(*(_QWORD *)g_pFtpServer + 56LL);
        if ( v10 )
        {
          v11();
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
          *((_DWORD *)this + 278) = (v8 != -2147024891) + 2;
          v13 = L"File system returned an error.";
          if ( v8 == -2147024891 )
            v13 = L"File system denied the access.";
          *((_QWORD *)this + 138) = v13;
        }
        else
        {
          v11();
        }
      }
    }
  }
  if ( v15 )
  {
    USER_SESSION::RevertImpersonation(this);
    v15 = 0;
  }
  if ( v9 && _InterlockedExchangeAdd(v9 + 5, 0xFFFFFFFF) == 1 )
  {
    TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY((TOKEN_CACHE_ENTRY *)v9);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry, (void *)v9);
  }
  if ( a4 )
    *a4 = 0;
  STRU::~STRU(v17);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000f930  push    rbp
0x18000f932  push    rbx
0x18000f933  push    rsi
0x18000f934  push    rdi
0x18000f935  push    r14
0x18000f937  push    r15
0x18000f939  lea     rbp, [rsp-1B8h]
0x18000f941  sub     rsp, 2B8h
0x18000f948  mov     rax, cs:__security_cookie
0x18000f94f  xor     rax, rsp
0x18000f952  mov     [rbp+1E0h+var_40], rax
0x18000f959  mov     r15, r9
0x18000f95c  mov     r14, r8
0x18000f95f  mov     rbx, rdx
0x18000f962  mov     rsi, rcx
0x18000f965  mov     [rsp+2E0h+var_2A0], 0
0x18000f96d  mov     [rsp+2E0h+var_298], 0
0x18000f976  xor     edx, edx; Val
0x18000f978  mov     r8d, 208h; Size
0x18000f97e  lea     rcx, [rbp+1E0h+var_250]; void *
0x18000f982  call    memset_0
0x18000f987  mov     r8d, 104h
0x18000f98d  lea     rdx, [rbp+1E0h+var_250]
0x18000f991  lea     rcx, [rsp+2E0h+var_290]
0x18000f996  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000f99c  nop
0x18000f99d  mov     dword ptr [rsi+458h], 0
0x18000f9a7  lea     rax, WideCharStr
0x18000f9ae  mov     [rsi+450h], rax
0x18000f9b5  mov     [rsp+2E0h+var_2B0], 0
0x18000f9bd  lea     rax, [rsp+2E0h+var_298]
0x18000f9c2  mov     [rsp+2E0h+var_2B8], rax
0x18000f9c7  mov     [rsp+2E0h+var_2C0], 0
0x18000f9d0  lea     r9, [rsp+2E0h+var_290]
0x18000f9d5  mov     r8d, 3
0x18000f9db  mov     rdx, rbx
0x18000f9de  mov     rcx, rsi
0x18000f9e1  call    ?DoUserIsolationAndCheckAccessAndMapPath@USER_SESSION@@AEAAJPEBGW4URL_AUTHORIZATION_ACCESS@@PEAVSTRU@@2PEAPEAVTOKEN_CACHE_ENTRY@@H@Z; USER_SESSION::DoUserIsolationAndCheckAccessAndMapPath(ushort const *,URL_AUTHORIZATION_ACCESS,STRU *,STRU *,TOKEN_CACHE_ENTRY * *,int)
0x18000f9e6  mov     ebx, eax
0x18000f9e8  mov     rdi, [rsp+2E0h+var_298]
0x18000f9ed  test    eax, eax
0x18000f9ef  js      loc_18000FAAD
0x18000f9f5  test    r14, r14
0x18000f9f8  jz      short loc_18000FA12
0x18000f9fa  mov     rdx, [rsp+2E0h+lpFileName]
0x18000f9ff  mov     rcx, r14
0x18000fa02  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000fa08  mov     ebx, eax
0x18000fa0a  test    eax, eax
0x18000fa0c  js      loc_18000FAAD
0x18000fa12  lea     r8, [rsp+2E0h+var_2A0]; int *
0x18000fa17  mov     rdx, rdi; struct TOKEN_CACHE_ENTRY *
0x18000fa1a  mov     rcx, rsi; this
0x18000fa1d  call    ?Impersonate@USER_SESSION@@AEAAJPEAVTOKEN_CACHE_ENTRY@@PEAH@Z; USER_SESSION::Impersonate(TOKEN_CACHE_ENTRY *,int *)
0x18000fa22  mov     ebx, eax
0x18000fa24  test    eax, eax
0x18000fa26  js      loc_18000FAAD
0x18000fa2c  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000fa33  mov     rax, [rcx]
0x18000fa36  mov     rax, [rax+40h]
0x18000fa3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa3f  mov     rcx, [rsp+2E0h+lpFileName]; lpFileName
0x18000fa44  call    cs:__imp_DeleteFileW
0x18000fa4a  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000fa51  test    eax, eax
0x18000fa53  mov     rax, [rcx]
0x18000fa56  mov     rax, [rax+38h]
0x18000fa5a  jnz     short loc_18000FAA8
0x18000fa5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa61  call    cs:__imp_GetLastError
0x18000fa67  mov     ebx, eax
0x18000fa69  test    eax, eax
0x18000fa6b  jle     short loc_18000FA76
0x18000fa6d  movzx   ebx, ax
0x18000fa70  or      ebx, 80070000h
0x18000fa76  xor     eax, eax
0x18000fa78  mov     edx, 80070005h
0x18000fa7d  cmp     ebx, edx
0x18000fa7f  setnz   al
0x18000fa82  add     eax, 2
0x18000fa85  mov     [rsi+458h], eax
0x18000fa8b  lea     rcx, aFileSystemDeni; "File system denied the access."
0x18000fa92  lea     rax, aFileSystemRetu; "File system returned an error."
0x18000fa99  cmp     ebx, edx
0x18000fa9b  cmovz   rax, rcx
0x18000fa9f  mov     [rsi+450h], rax
0x18000faa6  jmp     short loc_18000FAAD
0x18000faa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000faad  cmp     [rsp+2E0h+var_2A0], 0
0x18000fab2  jz      short loc_18000FAC4
0x18000fab4  mov     rcx, rsi; this
0x18000fab7  call    ?RevertImpersonation@USER_SESSION@@AEAAXXZ; USER_SESSION::RevertImpersonation(void)
0x18000fabc  mov     [rsp+2E0h+var_2A0], 0
0x18000fac4  test    rdi, rdi
0x18000fac7  jz      short loc_18000FAF5
0x18000fac9  or      eax, 0FFFFFFFFh
0x18000facc  lock xadd [rdi+14h], eax
0x18000fad1  cmp     eax, 1
0x18000fad4  jnz     short loc_18000FAF5
0x18000fad6  test    rdi, rdi
0x18000fad9  jz      short loc_18000FAF5
0x18000fadb  mov     rcx, rdi; this
0x18000fade  call    ??1TOKEN_CACHE_ENTRY@@AEAA@XZ; TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY(void)
0x18000fae3  nop
0x18000fae4  mov     rdx, rdi
0x18000fae7  mov     rcx, cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x18000faee  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000faf4  nop
0x18000faf5  test    r15, r15
0x18000faf8  jz      short loc_18000FB01
0x18000fafa  mov     dword ptr [r15], 0
0x18000fb01  lea     rcx, [rsp+2E0h+var_290]
0x18000fb06  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000fb0c  mov     eax, ebx
0x18000fb0e  mov     rcx, [rbp+1E0h+var_40]
0x18000fb15  xor     rcx, rsp; StackCookie
0x18000fb18  call    __security_check_cookie
0x18000fb1d  add     rsp, 2B8h
0x18000fb24  pop     r15
0x18000fb26  pop     r14
0x18000fb28  pop     rdi
0x18000fb29  pop     rsi
0x18000fb2a  pop     rbx
0x18000fb2b  pop     rbp
0x18000fb2c  retn
```
