# USER_SESSION::CreateDirectoryW(ushort const *,STRU *,int *)

- ea: `0x18000f560`
- end: `0x18000f78b`
- name: `?CreateDirectoryW@USER_SESSION@@UEAAJPEBGPEAVSTRU@@PEAH@Z`
- size: `555`
- prototype: `__int64 __fastcall(USER_SESSION *this, const unsigned __int16 *, const wchar_t **, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting`

## callees

- `0x1800022b8`
- `0x18000f560`
- `0x18000fdd8`
- `0x1800116a4`
- `0x1800129c0`
- `0x18001313c`
- `0x180049010`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x18000f6ba`
- `KERNEL32!CreateDirectoryW` at `0x18000f6ba`
- `KERNEL32!GetLastError` at `0x18000f6d7`
- `KERNEL32!GetLastError` at `0x18000f6d7`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000f765`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000f765`
- `iisutil!PuDbgPrint` at `0x18000f62e`
- `iisutil!PuDbgPrint` at `0x18000f62e`

## string_xrefs

- `0x18000f607`: `DoUserIsolationAndCheckAccessAndMapPath failed on CheckDirectory(%S). Error = 0x%x. Info = %S\n`
- `0x18000f613`: `USER_SESSION::CreateDirectoryW`
- `0x18000f702`: `File system denied the access.`

## pseudocode

```c
__int64 __fastcall USER_SESSION::CreateDirectoryW(
        USER_SESSION *this,
        const unsigned __int16 *a2,
        const wchar_t **a3,
        int *a4)
{
  int v8; // edi
  volatile signed __int32 *v9; // rsi
  const wchar_t *v10; // rax
  __int64 v11; // rax
  const unsigned __int16 *v12; // rbx
  struct CEtwTracer *v13; // rax
  bool v14; // zf
  void (*v15)(void); // rax
  signed int LastError; // eax
  const wchar_t *v17; // rax
  int v19; // [rsp+70h] [rbp+8h] BYREF
  TOKEN_CACHE_ENTRY *v20; // [rsp+88h] [rbp+20h] BYREF

  v19 = 0;
  v20 = 0;
  *((_DWORD *)this + 278) = 0;
  *((_QWORD *)this + 138) = &WideCharStr;
  v8 = USER_SESSION::DoUserIsolationAndCheckAccessAndMapPath(this, (__int64)a2, 17, a3, 0, &v20, 0);
  v9 = (volatile signed __int32 *)v20;
  if ( v8 >= 0 )
  {
    v8 = USER_SESSION::Impersonate(this, v20, &v19);
    if ( v8 >= 0 )
    {
      (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 64LL))(g_pFtpServer);
      v11 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      if ( *(_DWORD *)(v11 + 8) && (*(_BYTE *)(v11 + 40) & 0x11) != 0 && *(_DWORD *)(v11 + 44) >= 5u )
      {
        v12 = a3[4];
        v13 = (struct CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
        FtpFileSystemAccessEvents::StartCreateFile::RaiseEvent(v13, (const struct _GUID *)((char *)this + 1272), v12);
      }
      v14 = !CreateDirectoryW(a3[4], 0);
      v15 = *(void (**)(void))(*(_QWORD *)g_pFtpServer + 56LL);
      if ( v14 )
      {
        v15();
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        *((_DWORD *)this + 278) = (v8 != -2147024891) + 2;
        v17 = L"File system returned an error.";
        if ( v8 == -2147024891 )
          v17 = L"File system denied the access.";
        *((_QWORD *)this + 138) = v17;
      }
      else
      {
        v15();
      }
    }
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    v10 = (const wchar_t *)(*(__int64 (__fastcall **)(USER_SESSION *))(*(_QWORD *)this + 208LL))(this);
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
      1506,
      "USER_SESSION::CreateDirectoryW",
      "DoUserIsolationAndCheckAccessAndMapPath failed on CheckDirectory(%S). Error = 0x%x. Info = %S\n",
      a2,
      v8,
      v10);
  }
  if ( v19 )
  {
    USER_SESSION::RevertImpersonation(this);
    v19 = 0;
  }
  if ( v9 && _InterlockedExchangeAdd(v9 + 5, 0xFFFFFFFF) == 1 )
  {
    TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY((TOKEN_CACHE_ENTRY *)v9);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry, (void *)v9);
  }
  if ( a4 )
    *a4 = 0;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000f560  mov     r11, rsp
0x18000f563  mov     [r11+10h], rbx
0x18000f567  push    rbp
0x18000f568  push    rsi
0x18000f569  push    rdi
0x18000f56a  push    r14
0x18000f56c  push    r15
0x18000f56e  sub     rsp, 40h
0x18000f572  mov     r15, r9
0x18000f575  mov     rbp, r8
0x18000f578  mov     rbx, rdx
0x18000f57b  mov     r14, rcx
0x18000f57e  mov     [rsp+68h+arg_0], 0
0x18000f586  mov     qword ptr [r11+20h], 0
0x18000f58e  mov     dword ptr [rcx+458h], 0
0x18000f598  lea     rax, WideCharStr
0x18000f59f  mov     [rcx+450h], rax
0x18000f5a6  mov     [rsp+68h+var_38], 0
0x18000f5ae  lea     rax, [r11+20h]
0x18000f5b2  mov     [r11-40h], rax
0x18000f5b6  mov     qword ptr [r11-48h], 0
0x18000f5be  mov     r9, r8
0x18000f5c1  mov     r8d, 11h
0x18000f5c7  call    ?DoUserIsolationAndCheckAccessAndMapPath@USER_SESSION@@AEAAJPEBGW4URL_AUTHORIZATION_ACCESS@@PEAVSTRU@@2PEAPEAVTOKEN_CACHE_ENTRY@@H@Z; USER_SESSION::DoUserIsolationAndCheckAccessAndMapPath(ushort const *,URL_AUTHORIZATION_ACCESS,STRU *,STRU *,TOKEN_CACHE_ENTRY * *,int)
0x18000f5cc  mov     edi, eax
0x18000f5ce  mov     rsi, [rsp+68h+arg_18]
0x18000f5d6  test    eax, eax
0x18000f5d8  jns     short loc_18000F639
0x18000f5da  test    byte ptr cs:g_dwDebugFlags, 3
0x18000f5e1  jz      loc_18000F724
0x18000f5e7  mov     rcx, [r14]
0x18000f5ea  mov     rax, [rcx+0D0h]
0x18000f5f1  mov     rcx, r14
0x18000f5f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5f9  mov     [rsp+68h+var_30], rax
0x18000f5fe  mov     [rsp+68h+var_38], edi
0x18000f602  mov     [rsp+68h+var_40], rbx
0x18000f607  lea     rax, aDouserisolatio; "DoUserIsolationAndCheckAccessAndMapPath"...
0x18000f60e  mov     [rsp+68h+var_48], rax
0x18000f613  lea     r9, aUserSessionCre; "USER_SESSION::CreateDirectoryW"
0x18000f61a  mov     r8d, 5E2h
0x18000f620  lea     rdx, aInetsrvIisIisr_36; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000f627  mov     rcx, cs:g_pDebug
0x18000f62e  call    cs:__imp_PuDbgPrint
0x18000f634  jmp     loc_18000F724
0x18000f639  lea     r8, [rsp+68h+arg_0]; int *
0x18000f63e  mov     rdx, rsi; struct TOKEN_CACHE_ENTRY *
0x18000f641  mov     rcx, r14; this
0x18000f644  call    ?Impersonate@USER_SESSION@@AEAAJPEAVTOKEN_CACHE_ENTRY@@PEAH@Z; USER_SESSION::Impersonate(TOKEN_CACHE_ENTRY *,int *)
0x18000f649  mov     edi, eax
0x18000f64b  test    eax, eax
0x18000f64d  js      loc_18000F724
0x18000f653  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000f65a  mov     rax, [rcx]
0x18000f65d  mov     rax, [rax+40h]
0x18000f661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f666  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000f66d  mov     rax, [rcx]
0x18000f670  mov     rax, [rax+20h]
0x18000f674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f679  cmp     dword ptr [rax+8], 0
0x18000f67d  jz      short loc_18000F6B4
0x18000f67f  test    byte ptr [rax+28h], 11h
0x18000f683  jz      short loc_18000F6B4
0x18000f685  cmp     dword ptr [rax+2Ch], 5
0x18000f689  jb      short loc_18000F6B4
0x18000f68b  mov     rbx, [rbp+20h]
0x18000f68f  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000f696  mov     rax, [rcx]
0x18000f699  mov     rax, [rax+20h]
0x18000f69d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6a2  lea     rdx, [r14+4F8h]; struct _GUID *
0x18000f6a9  mov     r8, rbx; unsigned __int16 *
0x18000f6ac  mov     rcx, rax; struct CEtwTracer *
0x18000f6af  call    ?RaiseEvent@StartCreateFile@FtpFileSystemAccessEvents@@SAJPEAVCEtwTracer@@PEBU_GUID@@PEBG@Z; FtpFileSystemAccessEvents::StartCreateFile::RaiseEvent(CEtwTracer *,_GUID const *,ushort const *)
0x18000f6b4  xor     edx, edx; lpSecurityAttributes
0x18000f6b6  mov     rcx, [rbp+20h]; lpPathName
0x18000f6ba  call    cs:__imp_CreateDirectoryW
0x18000f6c0  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000f6c7  test    eax, eax
0x18000f6c9  mov     rax, [rcx]
0x18000f6cc  mov     rax, [rax+38h]
0x18000f6d0  jnz     short loc_18000F71F
0x18000f6d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6d7  call    cs:__imp_GetLastError
0x18000f6dd  mov     edi, eax
0x18000f6df  test    eax, eax
0x18000f6e1  jle     short loc_18000F6EC
0x18000f6e3  movzx   edi, ax
0x18000f6e6  or      edi, 80070000h
0x18000f6ec  xor     eax, eax
0x18000f6ee  mov     edx, 80070005h
0x18000f6f3  cmp     edi, edx
0x18000f6f5  setnz   al
0x18000f6f8  add     eax, 2
0x18000f6fb  mov     [r14+458h], eax
0x18000f702  lea     rcx, aFileSystemDeni; "File system denied the access."
0x18000f709  lea     rax, aFileSystemRetu; "File system returned an error."
0x18000f710  cmp     edi, edx
0x18000f712  cmovz   rax, rcx
0x18000f716  mov     [r14+450h], rax
0x18000f71d  jmp     short loc_18000F724
0x18000f71f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f724  cmp     [rsp+68h+arg_0], 0
0x18000f729  jz      short loc_18000F73B
0x18000f72b  mov     rcx, r14; this
0x18000f72e  call    ?RevertImpersonation@USER_SESSION@@AEAAXXZ; USER_SESSION::RevertImpersonation(void)
0x18000f733  mov     [rsp+68h+arg_0], 0
0x18000f73b  test    rsi, rsi
0x18000f73e  jz      short loc_18000F76C
0x18000f740  or      eax, 0FFFFFFFFh
0x18000f743  lock xadd [rsi+14h], eax
0x18000f748  cmp     eax, 1
0x18000f74b  jnz     short loc_18000F76C
0x18000f74d  test    rsi, rsi
0x18000f750  jz      short loc_18000F76C
0x18000f752  mov     rcx, rsi; this
0x18000f755  call    ??1TOKEN_CACHE_ENTRY@@AEAA@XZ; TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY(void)
0x18000f75a  nop
0x18000f75b  mov     rdx, rsi
0x18000f75e  mov     rcx, cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x18000f765  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000f76b  nop
0x18000f76c  test    r15, r15
0x18000f76f  jz      short loc_18000F778
0x18000f771  mov     dword ptr [r15], 0
0x18000f778  mov     eax, edi
0x18000f77a  mov     rbx, [rsp+68h+arg_8]
0x18000f77f  add     rsp, 40h
0x18000f783  pop     r15
0x18000f785  pop     r14
0x18000f787  pop     rdi
0x18000f788  pop     rsi
0x18000f789  pop     rbp
0x18000f78a  retn
```
