# USER_SESSION::RenameFileOrDirectory(ushort const *,ushort const *,int,STRU *,STRU *,int *)

- ea: `0x180012c90`
- end: `0x180012f7c`
- name: `?RenameFileOrDirectory@USER_SESSION@@UEAAJPEBG0HPEAVSTRU@@1PEAH@Z`
- size: `748`
- prototype: `__int64 __fastcall(USER_SESSION *this, const unsigned __int16 *, const unsigned __int16 *, int, struct STRU *, struct STRU *, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting`

## callees

- `0x1800022b8`
- `0x18000fdd8`
- `0x1800116a4`
- `0x180012c90`
- `0x18001313c`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `KERNEL32!MoveFileExW` at `0x180012e47`
- `KERNEL32!MoveFileExW` at `0x180012e47`
- `KERNEL32!GetLastError` at `0x180012e64`
- `KERNEL32!GetLastError` at `0x180012e64`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180012ef2`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180012f26`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180012ef2`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180012f26`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012d9c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012df5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012d9c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012df5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180012d14`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180012d3e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180012d14`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180012d3e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012f3f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012f4a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012f3f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012f4a`

## string_xrefs

- `0x180012e8e`: `File system denied the access.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall USER_SESSION::RenameFileOrDirectory(
        USER_SESSION *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        struct STRU *a5,
        struct STRU *a6,
        int *a7)
{
  int v10; // ebx
  volatile signed __int32 *v11; // rdi
  bool v12; // zf
  void (*v13)(void); // rax
  signed int LastError; // eax
  const wchar_t *v15; // rax
  TOKEN_CACHE_ENTRY *v16; // rdi
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  TOKEN_CACHE_ENTRY *v19; // [rsp+48h] [rbp-B8h] BYREF
  TOKEN_CACHE_ENTRY *v20; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 *v21; // [rsp+58h] [rbp-A8h]
  const wchar_t *v22[4]; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpNewFileName; // [rsp+80h] [rbp-80h]
  const wchar_t *v24[4]; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+B8h] [rbp-48h]
  unsigned __int16 v26[264]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v27[264]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v21 = a3;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  memset_0(v26, 0, 0x208u);
  STRU::STRU((STRU *)v24, v26, 0x104u);
  memset_0(v27, 0, 0x208u);
  STRU::STRU((STRU *)v22, v27, 0x104u);
  *((_DWORD *)this + 278) = 0;
  *((_QWORD *)this + 138) = &WideCharStr;
  v10 = USER_SESSION::DoUserIsolationAndCheckAccessAndMapPath(this, (__int64)a2, 33, v24, 0, &v19, 0);
  v11 = (volatile signed __int32 *)v19;
  if ( v10 >= 0 )
  {
    if ( !a5 || (v10 = STRU::Copy(a5, lpExistingFileName), v10 >= 0) )
    {
      v10 = USER_SESSION::DoUserIsolationAndCheckAccessAndMapPath(this, (__int64)v21, 33, v22, 0, &v20, 0);
      if ( v10 >= 0 )
      {
        if ( !a6 || (v10 = STRU::Copy(a6, lpNewFileName), v10 >= 0) )
        {
          v10 = USER_SESSION::Impersonate(this, (struct TOKEN_CACHE_ENTRY *)v11, &v18);
          if ( v10 >= 0 )
          {
            (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 64LL))(g_pFtpServer);
            v12 = !MoveFileExW(lpExistingFileName, lpNewFileName, (a4 != 0) + 10);
            v13 = *(void (**)(void))(*(_QWORD *)g_pFtpServer + 56LL);
            if ( v12 )
            {
              v13();
              LastError = GetLastError();
              v10 = LastError;
              if ( LastError > 0 )
                v10 = (unsigned __int16)LastError | 0x80070000;
              *((_DWORD *)this + 278) = (v10 != -2147024891) + 2;
              v15 = L"File system returned an error.";
              if ( v10 == -2147024891 )
                v15 = L"File system denied the access.";
              *((_QWORD *)this + 138) = v15;
            }
            else
            {
              v13();
            }
          }
        }
      }
    }
  }
  if ( v18 )
  {
    USER_SESSION::RevertImpersonation(this);
    v18 = 0;
  }
  if ( v11 && _InterlockedExchangeAdd(v11 + 5, 0xFFFFFFFF) == 1 )
  {
    TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY((TOKEN_CACHE_ENTRY *)v11);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry, (void *)v11);
  }
  v16 = v20;
  if ( v20 && _InterlockedExchangeAdd((volatile signed __int32 *)v20 + 5, 0xFFFFFFFF) == 1 && v16 )
  {
    TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY(v16);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry, v16);
  }
  if ( a7 )
    *a7 = 0;
  STRU::~STRU(v22);
  STRU::~STRU(v24);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180012c90  mov     [rsp-8+arg_18], rbx
0x180012c95  push    rbp
0x180012c96  push    rsi
0x180012c97  push    rdi
0x180012c98  push    r12
0x180012c9a  push    r13
0x180012c9c  push    r14
0x180012c9e  push    r15
0x180012ca0  lea     rbp, [rsp-400h]
0x180012ca8  sub     rsp, 500h
0x180012caf  mov     rax, cs:__security_cookie
0x180012cb6  xor     rax, rsp
0x180012cb9  mov     [rbp+430h+var_40], rax
0x180012cc0  mov     r13d, r9d
0x180012cc3  mov     [rsp+530h+var_4D8], r8
0x180012cc8  mov     rbx, rdx
0x180012ccb  mov     rsi, rcx
0x180012cce  mov     r15, [rbp+430h+arg_20]
0x180012cd5  mov     r14, [rbp+430h+arg_28]
0x180012cdc  mov     r12, [rbp+430h+arg_30]
0x180012ce3  xor     eax, eax
0x180012ce5  mov     [rsp+530h+var_4F0], eax
0x180012ce9  mov     [rsp+530h+var_4E8], rax
0x180012cee  mov     [rsp+530h+var_4E0], rax
0x180012cf3  xor     edx, edx; Val
0x180012cf5  mov     r8d, 208h; Size
0x180012cfb  lea     rcx, [rbp+430h+var_460]; void *
0x180012cff  call    memset_0
0x180012d04  mov     edi, 104h
0x180012d09  mov     r8d, edi
0x180012d0c  lea     rdx, [rbp+430h+var_460]
0x180012d10  lea     rcx, [rbp+430h+var_498]
0x180012d14  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180012d1a  nop
0x180012d1b  xor     edx, edx; Val
0x180012d1d  mov     r8d, 208h; Size
0x180012d23  lea     rcx, [rbp+430h+var_250]; void *
0x180012d2a  call    memset_0
0x180012d2f  mov     r8d, edi
0x180012d32  lea     rdx, [rbp+430h+var_250]
0x180012d39  lea     rcx, [rsp+530h+var_4D0]
0x180012d3e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180012d44  nop
0x180012d45  xor     ecx, ecx
0x180012d47  mov     [rsi+458h], ecx
0x180012d4d  lea     rax, WideCharStr
0x180012d54  mov     [rsi+450h], rax
0x180012d5b  mov     [rsp+530h+var_500], ecx
0x180012d5f  lea     rax, [rsp+530h+var_4E8]
0x180012d64  mov     [rsp+530h+var_508], rax
0x180012d69  mov     [rsp+530h+var_510], rcx
0x180012d6e  lea     r9, [rbp+430h+var_498]
0x180012d72  lea     r8d, [rcx+21h]
0x180012d76  mov     rdx, rbx
0x180012d79  mov     rcx, rsi
0x180012d7c  call    ?DoUserIsolationAndCheckAccessAndMapPath@USER_SESSION@@AEAAJPEBGW4URL_AUTHORIZATION_ACCESS@@PEAVSTRU@@2PEAPEAVTOKEN_CACHE_ENTRY@@H@Z; USER_SESSION::DoUserIsolationAndCheckAccessAndMapPath(ushort const *,URL_AUTHORIZATION_ACCESS,STRU *,STRU *,TOKEN_CACHE_ENTRY * *,int)
0x180012d81  mov     ebx, eax
0x180012d83  mov     rdi, [rsp+530h+var_4E8]
0x180012d88  test    eax, eax
0x180012d8a  js      loc_180012EB0
0x180012d90  test    r15, r15
0x180012d93  jz      short loc_180012DAC
0x180012d95  mov     rdx, [rbp+430h+lpExistingFileName]
0x180012d99  mov     rcx, r15
0x180012d9c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180012da2  mov     ebx, eax
0x180012da4  test    eax, eax
0x180012da6  js      loc_180012EB0
0x180012dac  mov     [rsp+530h+var_500], 0
0x180012db4  lea     rax, [rsp+530h+var_4E0]
0x180012db9  mov     [rsp+530h+var_508], rax
0x180012dbe  mov     [rsp+530h+var_510], 0
0x180012dc7  lea     r9, [rsp+530h+var_4D0]
0x180012dcc  mov     r8d, 21h ; '!'
0x180012dd2  mov     rdx, [rsp+530h+var_4D8]
0x180012dd7  mov     rcx, rsi
0x180012dda  call    ?DoUserIsolationAndCheckAccessAndMapPath@USER_SESSION@@AEAAJPEBGW4URL_AUTHORIZATION_ACCESS@@PEAVSTRU@@2PEAPEAVTOKEN_CACHE_ENTRY@@H@Z; USER_SESSION::DoUserIsolationAndCheckAccessAndMapPath(ushort const *,URL_AUTHORIZATION_ACCESS,STRU *,STRU *,TOKEN_CACHE_ENTRY * *,int)
0x180012ddf  mov     ebx, eax
0x180012de1  test    eax, eax
0x180012de3  js      loc_180012EB0
0x180012de9  test    r14, r14
0x180012dec  jz      short loc_180012E05
0x180012dee  mov     rdx, [rbp+430h+lpNewFileName]
0x180012df2  mov     rcx, r14
0x180012df5  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180012dfb  mov     ebx, eax
0x180012dfd  test    eax, eax
0x180012dff  js      loc_180012EB0
0x180012e05  lea     r8, [rsp+530h+var_4F0]; int *
0x180012e0a  mov     rdx, rdi; struct TOKEN_CACHE_ENTRY *
0x180012e0d  mov     rcx, rsi; this
0x180012e10  call    ?Impersonate@USER_SESSION@@AEAAJPEAVTOKEN_CACHE_ENTRY@@PEAH@Z; USER_SESSION::Impersonate(TOKEN_CACHE_ENTRY *,int *)
0x180012e15  mov     ebx, eax
0x180012e17  test    eax, eax
0x180012e19  js      loc_180012EB0
0x180012e1f  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180012e26  mov     rax, [rcx]
0x180012e29  mov     rax, [rax+40h]
0x180012e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e32  neg     r13d
0x180012e35  sbb     r8d, r8d
0x180012e38  neg     r8d
0x180012e3b  add     r8d, 0Ah; dwFlags
0x180012e3f  mov     rdx, [rbp+430h+lpNewFileName]; lpNewFileName
0x180012e43  mov     rcx, [rbp+430h+lpExistingFileName]; lpExistingFileName
0x180012e47  call    cs:__imp_MoveFileExW
0x180012e4d  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180012e54  test    eax, eax
0x180012e56  mov     rax, [rcx]
0x180012e59  mov     rax, [rax+38h]
0x180012e5d  jnz     short loc_180012EAB
0x180012e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e64  call    cs:__imp_GetLastError
0x180012e6a  mov     ebx, eax
0x180012e6c  test    eax, eax
0x180012e6e  jle     short loc_180012E79
0x180012e70  movzx   ebx, ax
0x180012e73  or      ebx, 80070000h
0x180012e79  xor     eax, eax
0x180012e7b  mov     edx, 80070005h
0x180012e80  cmp     ebx, edx
0x180012e82  setnz   al
0x180012e85  add     eax, 2
0x180012e88  mov     [rsi+458h], eax
0x180012e8e  lea     rcx, aFileSystemDeni; "File system denied the access."
0x180012e95  lea     rax, aFileSystemRetu; "File system returned an error."
0x180012e9c  cmp     ebx, edx
0x180012e9e  cmovz   rax, rcx
0x180012ea2  mov     [rsi+450h], rax
0x180012ea9  jmp     short loc_180012EB0
0x180012eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012eb0  cmp     [rsp+530h+var_4F0], 0
0x180012eb5  jz      short loc_180012EC7
0x180012eb7  mov     rcx, rsi; this
0x180012eba  call    ?RevertImpersonation@USER_SESSION@@AEAAXXZ; USER_SESSION::RevertImpersonation(void)
0x180012ebf  mov     [rsp+530h+var_4F0], 0
0x180012ec7  or      esi, 0FFFFFFFFh
0x180012eca  test    rdi, rdi
0x180012ecd  jz      short loc_180012EF9
0x180012ecf  mov     eax, esi
0x180012ed1  lock xadd [rdi+14h], eax
0x180012ed6  add     eax, esi
0x180012ed8  jnz     short loc_180012EF9
0x180012eda  test    rdi, rdi
0x180012edd  jz      short loc_180012EF9
0x180012edf  mov     rcx, rdi; this
0x180012ee2  call    ??1TOKEN_CACHE_ENTRY@@AEAA@XZ; TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY(void)
0x180012ee7  nop
0x180012ee8  mov     rdx, rdi
0x180012eeb  mov     rcx, cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x180012ef2  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180012ef8  nop
0x180012ef9  mov     rdi, [rsp+530h+var_4E0]
0x180012efe  test    rdi, rdi
0x180012f01  jz      short loc_180012F2D
0x180012f03  mov     eax, esi
0x180012f05  lock xadd [rdi+14h], eax
0x180012f0a  add     eax, esi
0x180012f0c  jnz     short loc_180012F2D
0x180012f0e  test    rdi, rdi
0x180012f11  jz      short loc_180012F2D
0x180012f13  mov     rcx, rdi; this
0x180012f16  call    ??1TOKEN_CACHE_ENTRY@@AEAA@XZ; TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY(void)
0x180012f1b  nop
0x180012f1c  mov     rdx, rdi
0x180012f1f  mov     rcx, cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x180012f26  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180012f2c  nop
0x180012f2d  test    r12, r12
0x180012f30  jz      short loc_180012F3A
0x180012f32  mov     dword ptr [r12], 0
0x180012f3a  lea     rcx, [rsp+530h+var_4D0]
0x180012f3f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180012f45  nop
0x180012f46  lea     rcx, [rbp+430h+var_498]
0x180012f4a  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180012f50  mov     eax, ebx
0x180012f52  mov     rcx, [rbp+430h+var_40]
0x180012f59  xor     rcx, rsp; StackCookie
0x180012f5c  call    __security_check_cookie
0x180012f61  mov     rbx, [rsp+530h+arg_18]
0x180012f69  add     rsp, 500h
0x180012f70  pop     r15
0x180012f72  pop     r14
0x180012f74  pop     r13
0x180012f76  pop     r12
0x180012f78  pop     rdi
0x180012f79  pop     rsi
0x180012f7a  pop     rbp
0x180012f7b  retn
```
