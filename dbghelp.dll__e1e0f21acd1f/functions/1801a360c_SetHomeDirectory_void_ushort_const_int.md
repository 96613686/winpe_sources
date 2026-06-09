# SetHomeDirectory(void *,ushort const *,int)

- ea: `0x1801a360c`
- end: `0x1801a389c`
- name: `?SetHomeDirectory@@YAPEAGPEAXPEBGH@Z`
- size: `656`
- prototype: `unsigned __int16 *__fastcall(void *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801a03ec`
- `0x1801a82d0`

## callees

- `0x18000aeec`
- `0x180012e28`
- `0x180012e6c`
- `0x180012ed4`
- `0x180022d28`
- `0x1801a2748`
- `0x1801a2834`
- `0x1801a360c`
- `0x1801aeedc`
- `0x1801d6350`
- `0x180205010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801a3687`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801a3687`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1801a3712`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1801a3712`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801a376b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801a376b`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1801a36b4`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1801a36b4`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x1801a36d3`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x1801a36d3`

## pseudocode

```c
unsigned __int16 *__fastcall SetHomeDirectory(void *a1, const unsigned __int16 *a2, int a3)
{
  const unsigned __int16 *v6; // rcx
  unsigned __int16 *v7; // rcx
  unsigned __int64 v8; // rdx
  unsigned __int16 *v9; // rcx
  unsigned __int64 v10; // rdx
  unsigned __int16 *v11; // rcx
  struct _PROCESS_ENTRY *ProcessEntry; // rax
  wchar_t Drive[8]; // [rsp+50h] [rbp-468h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-458h] BYREF
  wchar_t Dir[264]; // [rsp+270h] [rbp-248h] BYREF

  PathName = 0;
  if ( a2 && *a2 )
  {
    wcscpy_s_ex(&PathName, 0x105u, a2);
    if ( !a3 && dir && !(unsigned int)_o__wcsicmp(a2, &dir) )
      return &PathName;
  }
  else
  {
    if ( dir )
    {
LABEL_26:
      wcscpy_s_ex(&PathName, 0x105u, &dir);
      return &PathName;
    }
    if ( !GetEnvironmentVariableW(L"DBGHELP_HOMEDIR", &PathName, 0x105u) )
    {
      PathName = 0;
      if ( GetModuleFileNameW(0, Filename, 0x105u) )
      {
        _wsplitpath_s(Filename, Drive, 4u, Dir, 0x101u, 0, 0, 0, 0);
        wcscpy_s_ex(Filename, 0x105u, Drive);
        wcscat_s_ex(Filename, 0x105u, Dir);
        BackslashCut(Filename);
        wcscpy_s_ex(&PathName, 0x105u, Filename);
      }
    }
  }
  if ( !PathName )
    goto LABEL_26;
  CreateDirectoryW(&PathName, 0);
  if ( !FolderAccessCheckOnThreadToken(v6) || dir || (unsigned int)GetCommonAppDataDirectory(v7) )
  {
    wcscpy_s_ex(&dir, 0x105u, &PathName);
    wcscpy_s_ex(&word_1802B0BBA, 0x105u, &PathName);
    if ( (dword_1802AF9CC & 0x400000) == 0 )
    {
      BackslashCat(&word_1802B0BBA, 261);
      wcscat_s_ex(v9, v8, L"sym");
    }
    symsrvSetOptions(0x2000u, (unsigned __int64)&word_1802B0BBA);
    wcscpy_s_ex(&word_1802B0DC4, 0x105u, &PathName);
    if ( (dword_1802AF9CC & 0x400000) == 0 )
    {
      BackslashCat(&word_1802B0DC4, 261);
      wcscat_s_ex(v11, v10, L"src");
    }
    ProcessEntry = FindProcessEntry(a1);
    if ( ProcessEntry && a1 && word_1802B0DC4 && *((_DWORD *)ProcessEntry + 27423) && qword_1802AF938 )
      qword_1802AF938(a1, &word_1802B0DC4);
  }
  else
  {
    PathName = 0;
  }
  return &PathName;
}

```

## disassembly

```asm
0x1801a360c  mov     [rsp+arg_10], rbx
0x1801a3611  push    rbp
0x1801a3612  push    rsi
0x1801a3613  push    rdi
0x1801a3614  push    r14
0x1801a3616  push    r15
0x1801a3618  sub     rsp, 490h
0x1801a361f  mov     rax, cs:__security_cookie
0x1801a3626  xor     rax, rsp
0x1801a3629  mov     [rsp+4B8h+var_38], rax
0x1801a3631  xor     ebp, ebp
0x1801a3633  lea     r15, PathName
0x1801a363a  mov     cs:PathName, bp
0x1801a3641  mov     esi, r8d
0x1801a3644  mov     rbx, rdx
0x1801a3647  mov     rdi, rcx
0x1801a364a  mov     r14d, 105h
0x1801a3650  test    rdx, rdx
0x1801a3653  jz      short loc_1801A369A
0x1801a3655  cmp     [rdx], bp
0x1801a3658  jz      short loc_1801A369A
0x1801a365a  mov     r8, rdx; unsigned __int16 *
0x1801a365d  mov     rcx, r15; unsigned __int16 *
0x1801a3660  mov     edx, r14d; unsigned __int64
0x1801a3663  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a3668  test    esi, esi
0x1801a366a  jnz     loc_1801A3759
0x1801a3670  cmp     cs:dir, bp
0x1801a3677  jz      loc_1801A3759
0x1801a367d  lea     rdx, dir
0x1801a3684  mov     rcx, rbx
0x1801a3687  call    cs:__imp__o__wcsicmp
0x1801a368d  test    eax, eax
0x1801a368f  jz      loc_1801A3872
0x1801a3695  jmp     loc_1801A3759
0x1801a369a  cmp     cs:dir, bp
0x1801a36a1  jnz     loc_1801A3860
0x1801a36a7  mov     r8d, r14d; nSize
0x1801a36aa  lea     rcx, aDbghelpHomedir; "DBGHELP_HOMEDIR"
0x1801a36b1  mov     rdx, r15; lpBuffer
0x1801a36b4  call    cs:__imp_GetEnvironmentVariableW
0x1801a36ba  test    eax, eax
0x1801a36bc  jnz     loc_1801A3759
0x1801a36c2  mov     r8d, r14d; nSize
0x1801a36c5  mov     cs:PathName, bp
0x1801a36cc  lea     rdx, [rsp+4B8h+Filename]; lpFilename
0x1801a36d1  xor     ecx, ecx; hModule
0x1801a36d3  call    cs:__imp_GetModuleFileNameW
0x1801a36d9  test    eax, eax
0x1801a36db  jz      short loc_1801A3759
0x1801a36dd  mov     [rsp+4B8h+ExtCount], rbp; ExtCount
0x1801a36e2  lea     r9, [rsp+4B8h+Dir]; Dir
0x1801a36ea  mov     [rsp+4B8h+Ext], rbp; Ext
0x1801a36ef  lea     rdx, [rsp+4B8h+Drive]; Drive
0x1801a36f4  mov     [rsp+4B8h+FilenameCount], rbp; FilenameCount
0x1801a36f9  lea     rcx, [rsp+4B8h+Filename]; FullPath
0x1801a36fe  mov     [rsp+4B8h+var_490], rbp; Filename
0x1801a3703  mov     r8d, 4; DriveCount
0x1801a3709  mov     [rsp+4B8h+DirCount], 101h; DirCount
0x1801a3712  call    cs:__imp__wsplitpath_s
0x1801a3718  lea     r8, [rsp+4B8h+Drive]; unsigned __int16 *
0x1801a371d  mov     rdx, r14; unsigned __int64
0x1801a3720  lea     rcx, [rsp+4B8h+Filename]; unsigned __int16 *
0x1801a3725  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a372a  lea     r8, [rsp+4B8h+Dir]; unsigned __int16 *
0x1801a3732  mov     rdx, r14; unsigned __int64
0x1801a3735  lea     rcx, [rsp+4B8h+Filename]; unsigned __int16 *
0x1801a373a  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a373f  lea     rcx, [rsp+4B8h+Filename]; unsigned __int16 *
0x1801a3744  call    ?BackslashCut@@YAXPEAG@Z; BackslashCut(ushort *)
0x1801a3749  lea     r8, [rsp+4B8h+Filename]; unsigned __int16 *
0x1801a374e  mov     rdx, r14; unsigned __int64
0x1801a3751  mov     rcx, r15; unsigned __int16 *
0x1801a3754  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a3759  cmp     cs:PathName, bp
0x1801a3760  jz      loc_1801A3860
0x1801a3766  xor     edx, edx; lpSecurityAttributes
0x1801a3768  mov     rcx, r15; lpPathName
0x1801a376b  call    cs:__imp_CreateDirectoryW
0x1801a3771  call    ?FolderAccessCheckOnThreadToken@@YAJPEBGK@Z; FolderAccessCheckOnThreadToken(ushort const *,ulong)
0x1801a3776  test    eax, eax
0x1801a3778  jz      short loc_1801A3798
0x1801a377a  cmp     cs:dir, bp
0x1801a3781  jnz     short loc_1801A3798
0x1801a3783  call    ?GetCommonAppDataDirectory@@YAHPEAG@Z; GetCommonAppDataDirectory(ushort *)
0x1801a3788  test    eax, eax
0x1801a378a  jnz     short loc_1801A3798
0x1801a378c  mov     cs:PathName, bp
0x1801a3793  jmp     loc_1801A3872
0x1801a3798  mov     r8, r15; unsigned __int16 *
0x1801a379b  lea     rcx, dir; unsigned __int16 *
0x1801a37a2  mov     rdx, r14; unsigned __int64
0x1801a37a5  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a37aa  lea     rbx, word_1802B0BBA
0x1801a37b1  mov     r8, r15; unsigned __int16 *
0x1801a37b4  mov     rcx, rbx; unsigned __int16 *
0x1801a37b7  mov     rdx, r14; unsigned __int64
0x1801a37ba  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a37bf  mov     esi, 400000h
0x1801a37c4  test    cs:dword_1802AF9CC, esi
0x1801a37ca  jnz     short loc_1801A37E3
0x1801a37cc  mov     rdx, r14
0x1801a37cf  mov     rcx, rbx
0x1801a37d2  call    BackslashCat
0x1801a37d7  lea     r8, aSym_0; "sym"
0x1801a37de  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a37e3  mov     rdx, rbx; unsigned __int64
0x1801a37e6  mov     ecx, 2000h; unsigned __int64
0x1801a37eb  call    ?symsrvSetOptions@@YAX_K0@Z; symsrvSetOptions(unsigned __int64,unsigned __int64)
0x1801a37f0  lea     rbx, word_1802B0DC4
0x1801a37f7  mov     r8, r15; unsigned __int16 *
0x1801a37fa  mov     rcx, rbx; unsigned __int16 *
0x1801a37fd  mov     rdx, r14; unsigned __int64
0x1801a3800  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a3805  test    cs:dword_1802AF9CC, esi
0x1801a380b  jnz     short loc_1801A3824
0x1801a380d  mov     rdx, r14
0x1801a3810  mov     rcx, rbx
0x1801a3813  call    BackslashCat
0x1801a3818  lea     r8, aSrc_0; "src"
0x1801a381f  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a3824  mov     rcx, rdi; void *
0x1801a3827  call    ?FindProcessEntry@@YAPEAU_PROCESS_ENTRY@@PEAX@Z; FindProcessEntry(void *)
0x1801a382c  test    rax, rax
0x1801a382f  jz      short loc_1801A3872
0x1801a3831  test    rdi, rdi
0x1801a3834  jz      short loc_1801A3872
0x1801a3836  cmp     cs:word_1802B0DC4, bp
0x1801a383d  jz      short loc_1801A3872
0x1801a383f  cmp     [rax+1AC7Ch], ebp
0x1801a3845  jz      short loc_1801A3872
0x1801a3847  mov     rax, cs:qword_1802AF938
0x1801a384e  test    rax, rax
0x1801a3851  jz      short loc_1801A3872
0x1801a3853  mov     rdx, rbx
0x1801a3856  mov     rcx, rdi
0x1801a3859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a385e  jmp     short loc_1801A3872
0x1801a3860  lea     r8, dir; unsigned __int16 *
0x1801a3867  mov     rdx, r14; unsigned __int64
0x1801a386a  mov     rcx, r15; unsigned __int16 *
0x1801a386d  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a3872  mov     rax, r15
0x1801a3875  mov     rcx, [rsp+4B8h+var_38]
0x1801a387d  xor     rcx, rsp; StackCookie
0x1801a3880  call    __security_check_cookie
0x1801a3885  mov     rbx, [rsp+4B8h+arg_10]
0x1801a388d  add     rsp, 490h
0x1801a3894  pop     r15
0x1801a3896  pop     r14
0x1801a3898  pop     rdi
0x1801a3899  pop     rsi
0x1801a389a  pop     rbp
0x1801a389b  retn
```
