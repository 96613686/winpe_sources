# CACHED_FILE_INFO::CheckIfFileHasChanged(void *)

- ea: `0x180002030`
- end: `0x180002288`
- name: `?CheckIfFileHasChanged@CACHED_FILE_INFO@@UEAAHPEAX@Z`
- size: `600`
- prototype: `__int64 __fastcall(CACHED_FILE_INFO *this, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180002030`
- `0x180003c32`
- `0x180003c70`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000209f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000222a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000209f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000222a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020db`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800021a5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800021a5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180002162`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180002162`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000224d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000224d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000207f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000207f`
- `iisutil!MakePathCanonicalizationProof` at `0x180002132`
- `iisutil!MakePathCanonicalizationProof` at `0x180002132`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180002195`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180002195`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800020b0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002141`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000227b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800020b0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002141`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000227b`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x180002270`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x180002270`

## pseudocode

```c
__int64 __fastcall CACHED_FILE_INFO::CheckIfFileHasChanged(CACHED_FILE_INFO *this, void *a2)
{
  int v4; // esi
  DWORD v5; // edi
  signed int LastError; // eax
  int v8; // edx
  unsigned int v9; // edi
  const unsigned __int16 *v10; // rax
  int v11; // esi
  const WCHAR *Str; // rax
  const unsigned __int16 *v13; // rax
  __int128 FileInformation; // [rsp+20h] [rbp-188h] BYREF
  __int128 v15; // [rsp+30h] [rbp-178h]
  unsigned int v16; // [rsp+40h] [rbp-168h]
  _BYTE v17[56]; // [rsp+48h] [rbp-160h] BYREF
  unsigned __int16 v18[128]; // [rsp+80h] [rbp-128h] BYREF

  memset_0(v18, 0, sizeof(v18));
  STRU::STRU((STRU *)v17, v18, 0x80u);
  if ( *((_QWORD *)this + 41)
    || (v4 = *((_DWORD *)this + 85), v5 = *((_DWORD *)g_pFileCache + 17), GetTickCount() - v4 <= v5) )
  {
    STRU::~STRU((STRU *)v17);
    return 0;
  }
  else
  {
    v10 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(CACHED_FILE_INFO *))(*(_QWORD *)this + 88LL))(this);
    if ( (int)MakePathCanonicalizationProof(v10, (struct STRU *)v17) >= 0 )
    {
      v11 = 0;
      v9 = 1;
      if ( a2 )
      {
        SetThreadToken(0, a2);
        v11 = 1;
      }
      (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 24LL))(g_pGlobalInfo);
      FileInformation = 0;
      v16 = 0;
      v15 = 0;
      Str = STRU::QueryStr((STRU *)v17);
      if ( GetFileAttributesExW(Str, GetFileExInfoStandard, &FileInformation) )
      {
        if ( (_DWORD)FileInformation == *((_DWORD *)this + 84)
          && *(_QWORD *)((char *)&v15 + 4) / 10000000LL == *((_QWORD *)this + 43) / 10000000LL
          && ((FileInformation & 0x10) != 0 || __PAIR64__(HIDWORD(v15), v16) == *((_QWORD *)this + 44)) )
        {
          v9 = 0;
          *((_DWORD *)this + 85) = GetTickCount();
        }
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( LastError == -2147024775
          || (unsigned int)(LastError + 2147024845) <= 0x10 && (v8 = 73997, _bittest(&v8, LastError + 2147024845))
          || LastError == -2147023665 )
        {
          v9 = 0;
        }
      }
      (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 32LL))(g_pGlobalInfo);
      if ( v11 )
        RevertToSelf();
      if ( v9 )
      {
        v13 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(CACHED_FILE_INFO *))(*(_QWORD *)this + 88LL))(this);
        TREE_HASH_TABLE::DeletePath((TREE_HASH_TABLE *)g_pFileCache, v13);
      }
      STRU::~STRU((STRU *)v17);
      return v9;
    }
    else
    {
      STRU::~STRU((STRU *)v17);
      return 1;
    }
  }
}

```

## disassembly

```asm
0x180002030  mov     [rsp+arg_10], rbx
0x180002035  push    rbp
0x180002036  push    rsi
0x180002037  push    rdi
0x180002038  sub     rsp, 190h
0x18000203f  mov     rax, cs:__security_cookie
0x180002046  xor     rax, rsp
0x180002049  mov     [rsp+1A8h+var_28], rax
0x180002051  mov     rbp, rdx
0x180002054  mov     rbx, rcx
0x180002057  xor     edx, edx; Val
0x180002059  lea     rcx, [rsp+1A8h+var_128]; void *
0x180002061  mov     r8d, 100h; Size
0x180002067  call    memset_0
0x18000206c  mov     r8d, 80h
0x180002072  lea     rdx, [rsp+1A8h+var_128]
0x18000207a  lea     rcx, [rsp+1A8h+var_160]
0x18000207f  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002085  cmp     qword ptr [rbx+148h], 0
0x18000208d  jnz     short loc_1800020AB
0x18000208f  mov     rax, cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA; FILE_CACHE * g_pFileCache
0x180002096  mov     esi, [rbx+154h]
0x18000209c  mov     edi, [rax+44h]
0x18000209f  call    cs:__imp_GetTickCount
0x1800020a5  sub     eax, esi
0x1800020a7  cmp     eax, edi
0x1800020a9  ja      short loc_18000211B
0x1800020ab  lea     rcx, [rsp+1A8h+var_160]
0x1800020b0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800020b6  xor     eax, eax
0x1800020b8  mov     rcx, [rsp+1A8h+var_28]
0x1800020c0  xor     rcx, rsp; StackCookie
0x1800020c3  call    __security_check_cookie
0x1800020c8  mov     rbx, [rsp+1A8h+arg_10]
0x1800020d0  add     rsp, 190h
0x1800020d7  pop     rdi
0x1800020d8  pop     rsi
0x1800020d9  pop     rbp
0x1800020da  retn
0x1800020db  call    cs:__imp_GetLastError
0x1800020e1  test    eax, eax
0x1800020e3  jle     short loc_1800020ED
0x1800020e5  movzx   eax, ax
0x1800020e8  or      eax, 80070000h
0x1800020ed  cmp     eax, 80070079h
0x1800020f2  jz      short loc_180002114
0x1800020f4  lea     ecx, [rax+7FF8FFCDh]
0x1800020fa  cmp     ecx, 10h
0x1800020fd  ja      short loc_180002109
0x1800020ff  mov     edx, 1210Dh
0x180002104  bt      edx, ecx
0x180002107  jb      short loc_180002114
0x180002109  cmp     eax, 800704CFh
0x18000210e  jnz     loc_180002236
0x180002114  xor     edi, edi
0x180002116  jmp     loc_180002236
0x18000211b  mov     rax, [rbx]
0x18000211e  mov     rcx, rbx
0x180002121  mov     rax, [rax+58h]
0x180002125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000212a  mov     rcx, rax
0x18000212d  lea     rdx, [rsp+1A8h+var_160]
0x180002132  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x180002138  test    eax, eax
0x18000213a  jns     short loc_180002151
0x18000213c  lea     rcx, [rsp+1A8h+var_160]
0x180002141  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002147  mov     eax, 1
0x18000214c  jmp     loc_1800020B8
0x180002151  xor     esi, esi
0x180002153  mov     edi, 1
0x180002158  test    rbp, rbp
0x18000215b  jz      short loc_18000216A
0x18000215d  mov     rdx, rbp; Token
0x180002160  xor     ecx, ecx; Thread
0x180002162  call    cs:__imp_SetThreadToken
0x180002168  mov     esi, edi
0x18000216a  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180002171  mov     rax, [rcx]
0x180002174  mov     rax, [rax+18h]
0x180002178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000217d  xorps   xmm0, xmm0
0x180002180  lea     rcx, [rsp+1A8h+var_160]
0x180002185  xor     eax, eax
0x180002187  movups  [rsp+1A8h+FileInformation], xmm0
0x18000218c  mov     [rsp+1A8h+var_168], eax
0x180002190  movups  [rsp+1A8h+var_178], xmm0
0x180002195  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000219b  lea     r8, [rsp+1A8h+FileInformation]; lpFileInformation
0x1800021a0  xor     edx, edx; fInfoLevelId
0x1800021a2  mov     rcx, rax; lpFileName
0x1800021a5  call    cs:__imp_GetFileAttributesExW
0x1800021ab  test    eax, eax
0x1800021ad  jz      loc_1800020DB
0x1800021b3  mov     r9d, dword ptr [rsp+1A8h+FileInformation]
0x1800021b8  cmp     r9d, [rbx+150h]
0x1800021bf  jnz     short loc_180002236
0x1800021c1  mov     rcx, [rbx+158h]
0x1800021c8  mov     r10, 0D6BF94D5E57A42BDh
0x1800021d2  mov     rax, r10
0x1800021d5  imul    rcx
0x1800021d8  mov     rax, r10
0x1800021db  lea     r8, [rcx+rdx]
0x1800021df  imul    qword ptr [rsp+1A8h+var_178+4]
0x1800021e4  sar     r8, 17h
0x1800021e8  add     rdx, qword ptr [rsp+1A8h+var_178+4]
0x1800021ed  mov     rcx, r8
0x1800021f0  sar     rdx, 17h
0x1800021f4  mov     rax, rdx
0x1800021f7  shr     rcx, 3Fh
0x1800021fb  shr     rax, 3Fh
0x1800021ff  add     r8, rcx
0x180002202  add     rdx, rax
0x180002205  cmp     rdx, r8
0x180002208  jnz     short loc_180002236
0x18000220a  test    r9b, 10h
0x18000220e  jnz     short loc_180002228
0x180002210  mov     eax, [rbx+164h]
0x180002216  cmp     dword ptr [rsp+1A8h+var_178+0Ch], eax
0x18000221a  jnz     short loc_180002236
0x18000221c  mov     eax, [rbx+160h]
0x180002222  cmp     [rsp+1A8h+var_168], eax
0x180002226  jnz     short loc_180002236
0x180002228  xor     edi, edi
0x18000222a  call    cs:__imp_GetTickCount
0x180002230  mov     [rbx+154h], eax
0x180002236  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000223d  mov     rax, [rcx]
0x180002240  mov     rax, [rax+20h]
0x180002244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002249  test    esi, esi
0x18000224b  jz      short loc_180002253
0x18000224d  call    cs:__imp_RevertToSelf
0x180002253  test    edi, edi
0x180002255  jz      short loc_180002276
0x180002257  mov     rdx, [rbx]
0x18000225a  mov     rcx, rbx
0x18000225d  mov     rax, [rdx+58h]
0x180002261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002266  mov     rcx, cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA; FILE_CACHE * g_pFileCache
0x18000226d  mov     rdx, rax
0x180002270  call    cs:__imp_?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z; TREE_HASH_TABLE::DeletePath(ushort const *)
0x180002276  lea     rcx, [rsp+1A8h+var_160]
0x18000227b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002281  mov     eax, edi
0x180002283  jmp     loc_1800020B8
```
