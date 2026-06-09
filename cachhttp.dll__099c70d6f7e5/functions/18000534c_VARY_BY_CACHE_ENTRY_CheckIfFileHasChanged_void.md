# VARY_BY_CACHE_ENTRY::CheckIfFileHasChanged(void *)

- ea: `0x18000534c`
- end: `0x1800054e0`
- name: `?CheckIfFileHasChanged@VARY_BY_CACHE_ENTRY@@QEAAHPEAX@Z`
- size: `404`
- prototype: `__int64 __fastcall(VARY_BY_CACHE_ENTRY *this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180002f20`

## callees

- `0x18000534c`
- `0x180008bf0`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005401`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005401`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005393`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005494`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005393`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005494`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800053b2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800053b2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800053f7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800053f7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800054b7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800054b7`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800053e7`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800053e7`

## pseudocode

```c
__int64 __fastcall VARY_BY_CACHE_ENTRY::CheckIfFileHasChanged(VARY_BY_CACHE_ENTRY *this, void *a2)
{
  int v2; // ebp
  DWORD v5; // ebx
  int v6; // ebp
  unsigned int v7; // ebx
  const WCHAR *Str; // rax
  signed int LastError; // eax
  int v10; // edx
  __int128 FileInformation; // [rsp+20h] [rbp-48h] BYREF
  __int128 v13; // [rsp+30h] [rbp-38h]
  unsigned int v14; // [rsp+40h] [rbp-28h]

  v2 = *((_DWORD *)this + 162);
  if ( !v2 )
    return 0;
  if ( *((_QWORD *)this + 85) )
    return 0;
  v5 = *((_DWORD *)g_pOutputCache + 28);
  if ( GetTickCount() - v2 <= v5 )
    return 0;
  v6 = 0;
  v7 = 1;
  if ( a2 )
  {
    SetThreadToken(0, a2);
    v6 = 1;
  }
  (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 24LL))(g_pGlobalInfo);
  FileInformation = 0;
  v14 = 0;
  v13 = 0;
  Str = STRU::QueryStr((VARY_BY_CACHE_ENTRY *)((char *)this + 336));
  if ( GetFileAttributesExW(Str, GetFileExInfoStandard, &FileInformation) )
  {
    if ( (_DWORD)FileInformation == *((_DWORD *)this + 166)
      && *(_QWORD *)((char *)&v13 + 4) / 0x989680uLL == *((_QWORD *)this + 84) / 0x989680uLL
      && ((FileInformation & 0x10) != 0 || __PAIR64__(HIDWORD(v13), v14) == *((_QWORD *)this + 82)) )
    {
      v7 = 0;
      *((_DWORD *)this + 162) = GetTickCount();
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError == -2147024775
      || (unsigned int)(LastError + 2147024845) <= 0x10 && (v10 = 73997, _bittest(&v10, LastError + 2147024845))
      || LastError == -2147023665 )
    {
      v7 = 0;
    }
  }
  (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 32LL))(g_pGlobalInfo);
  if ( v6 )
    RevertToSelf();
  return v7;
}

```

## disassembly

```asm
0x18000534c  mov     [rsp+arg_10], rbx
0x180005351  push    rbp
0x180005352  push    rsi
0x180005353  push    rdi
0x180005354  sub     rsp, 50h
0x180005358  mov     rax, cs:__security_cookie
0x18000535f  xor     rax, rsp
0x180005362  mov     [rsp+68h+var_20], rax
0x180005367  mov     ebp, [rcx+288h]
0x18000536d  mov     rsi, rdx
0x180005370  mov     rdi, rcx
0x180005373  test    ebp, ebp
0x180005375  jz      loc_1800054C1
0x18000537b  cmp     qword ptr [rcx+2A8h], 0
0x180005383  jnz     loc_1800054C1
0x180005389  mov     rax, cs:?g_pOutputCache@@3PEAVOUTPUT_CACHE@@EA; OUTPUT_CACHE * g_pOutputCache
0x180005390  mov     ebx, [rax+70h]
0x180005393  call    cs:__imp_GetTickCount
0x180005399  sub     eax, ebp
0x18000539b  cmp     eax, ebx
0x18000539d  jbe     loc_1800054C1
0x1800053a3  xor     ebp, ebp
0x1800053a5  lea     ebx, [rbp+1]
0x1800053a8  test    rsi, rsi
0x1800053ab  jz      short loc_1800053BA
0x1800053ad  mov     rdx, rsi; Token
0x1800053b0  xor     ecx, ecx; Thread
0x1800053b2  call    cs:__imp_SetThreadToken
0x1800053b8  mov     ebp, ebx
0x1800053ba  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800053c1  mov     rax, [rcx]
0x1800053c4  mov     rax, [rax+18h]
0x1800053c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053cd  xorps   xmm0, xmm0
0x1800053d0  lea     rcx, [rdi+150h]
0x1800053d7  xor     eax, eax
0x1800053d9  movups  [rsp+68h+FileInformation], xmm0
0x1800053de  mov     [rsp+68h+var_28], eax
0x1800053e2  movups  [rsp+68h+var_38], xmm0
0x1800053e7  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x1800053ed  lea     r8, [rsp+68h+FileInformation]; lpFileInformation
0x1800053f2  xor     edx, edx; fInfoLevelId
0x1800053f4  mov     rcx, rax; lpFileName
0x1800053f7  call    cs:__imp_GetFileAttributesExW
0x1800053fd  test    eax, eax
0x1800053ff  jnz     short loc_18000543A
0x180005401  call    cs:__imp_GetLastError
0x180005407  test    eax, eax
0x180005409  jle     short loc_180005413
0x18000540b  movzx   eax, ax
0x18000540e  or      eax, 80070000h
0x180005413  cmp     eax, 80070079h
0x180005418  jz      short loc_180005436
0x18000541a  lea     ecx, [rax+7FF8FFCDh]
0x180005420  cmp     ecx, 10h
0x180005423  ja      short loc_18000542F
0x180005425  mov     edx, 1210Dh
0x18000542a  bt      edx, ecx
0x18000542d  jb      short loc_180005436
0x18000542f  cmp     eax, 800704CFh
0x180005434  jnz     short loc_1800054A0
0x180005436  xor     ebx, ebx
0x180005438  jmp     short loc_1800054A0
0x18000543a  mov     r8d, dword ptr [rsp+68h+FileInformation]
0x18000543f  cmp     r8d, [rdi+298h]
0x180005446  jnz     short loc_1800054A0
0x180005448  mov     r9, 0D6BF94D5E57A42BDh
0x180005452  mov     rax, r9
0x180005455  mul     qword ptr [rdi+2A0h]
0x18000545c  mov     rax, r9
0x18000545f  mov     rcx, rdx
0x180005462  mul     qword ptr [rsp+68h+var_38+4]
0x180005467  shr     rcx, 17h
0x18000546b  shr     rdx, 17h
0x18000546f  cmp     rdx, rcx
0x180005472  jnz     short loc_1800054A0
0x180005474  test    r8b, 10h
0x180005478  jnz     short loc_180005492
0x18000547a  mov     eax, [rdi+294h]
0x180005480  cmp     dword ptr [rsp+68h+var_38+0Ch], eax
0x180005484  jnz     short loc_1800054A0
0x180005486  mov     eax, [rdi+290h]
0x18000548c  cmp     [rsp+68h+var_28], eax
0x180005490  jnz     short loc_1800054A0
0x180005492  xor     ebx, ebx
0x180005494  call    cs:__imp_GetTickCount
0x18000549a  mov     [rdi+288h], eax
0x1800054a0  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800054a7  mov     rdx, [rcx]
0x1800054aa  mov     rax, [rdx+20h]
0x1800054ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054b3  test    ebp, ebp
0x1800054b5  jz      short loc_1800054BD
0x1800054b7  call    cs:__imp_RevertToSelf
0x1800054bd  mov     eax, ebx
0x1800054bf  jmp     short loc_1800054C3
0x1800054c1  xor     eax, eax
0x1800054c3  mov     rcx, [rsp+68h+var_20]
0x1800054c8  xor     rcx, rsp; StackCookie
0x1800054cb  call    __security_check_cookie
0x1800054d0  mov     rbx, [rsp+68h+arg_10]
0x1800054d8  add     rsp, 50h
0x1800054dc  pop     rdi
0x1800054dd  pop     rsi
0x1800054de  pop     rbp
0x1800054df  retn
```
