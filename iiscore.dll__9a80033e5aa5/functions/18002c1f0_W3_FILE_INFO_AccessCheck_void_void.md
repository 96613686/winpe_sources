# W3_FILE_INFO::AccessCheck(void *,void *)

- ea: `0x18002c1f0`
- end: `0x18002c34a`
- name: `?AccessCheck@W3_FILE_INFO@@UEAAJPEAX0@Z`
- size: `346`
- prototype: `__int64 __fastcall(W3_FILE_INFO *this, void *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18002c1f0`
- `0x18003439a`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002c27b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002c27b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c306`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c306`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c285`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c2ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c285`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c2ea`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c2de`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c2de`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002c316`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002c316`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002c321`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002c321`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002c2af`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002c2af`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002c23d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002c23d`
- `iisutil!MakePathCanonicalizationProof` at `0x18002c266`
- `iisutil!MakePathCanonicalizationProof` at `0x18002c266`
- `W3TP!ThreadPoolSetInfo` at `0x18002c2a4`
- `W3TP!ThreadPoolSetInfo` at `0x18002c310`
- `W3TP!ThreadPoolSetInfo` at `0x18002c2a4`
- `W3TP!ThreadPoolSetInfo` at `0x18002c310`

## pseudocode

```c
__int64 __fastcall W3_FILE_INFO::AccessCheck(W3_FILE_INFO *this, void *a2, void *a3)
{
  signed int PathCanonicalizationProof; // ebx
  const unsigned __int16 *v6; // rax
  signed int v7; // eax
  const WCHAR *Str; // rax
  HANDLE FileW; // rax
  signed int LastError; // eax
  _BYTE v12[64]; // [rsp+40h] [rbp-858h] BYREF
  unsigned __int16 v13[1024]; // [rsp+80h] [rbp-818h] BYREF

  memset_0(v13, 0, sizeof(v13));
  STRU::STRU((STRU *)v12, v13, 0x400u);
  if ( a2 )
  {
    v6 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(W3_FILE_INFO *))(*(_QWORD *)this + 88LL))(this);
    PathCanonicalizationProof = MakePathCanonicalizationProof(v6, (struct STRU *)v12);
    if ( PathCanonicalizationProof >= 0 )
    {
      if ( SetThreadToken(0, a2) )
      {
        ThreadPoolSetInfo(0, 0);
        Str = STRU::QueryStr((STRU *)v12);
        FileW = CreateFileW(Str, 0x80000000, 7u, 0, 3u, 1u, 0);
        if ( FileW == (HANDLE)-1LL )
        {
          LastError = GetLastError();
          PathCanonicalizationProof = LastError;
          if ( LastError > 0 )
            PathCanonicalizationProof = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          PathCanonicalizationProof = 0;
          CloseHandle(FileW);
        }
        ThreadPoolSetInfo(1, 0);
        RevertToSelf();
      }
      else
      {
        v7 = GetLastError();
        PathCanonicalizationProof = v7;
        if ( v7 > 0 )
          PathCanonicalizationProof = (unsigned __int16)v7 | 0x80070000;
      }
    }
  }
  else
  {
    PathCanonicalizationProof = 0;
  }
  STRU::~STRU((STRU *)v12);
  return (unsigned int)PathCanonicalizationProof;
}

```

## disassembly

```asm
0x18002c1f0  mov     [rsp+arg_10], rbx
0x18002c1f5  push    rdi
0x18002c1f6  sub     rsp, 890h
0x18002c1fd  mov     rax, cs:__security_cookie
0x18002c204  xor     rax, rsp
0x18002c207  mov     [rsp+898h+var_18], rax
0x18002c20f  mov     rdi, rdx
0x18002c212  mov     rbx, rcx
0x18002c215  xor     edx, edx; Val
0x18002c217  lea     rcx, [rsp+898h+var_818]; void *
0x18002c21f  mov     r8d, 800h; Size
0x18002c225  call    memset_0
0x18002c22a  mov     r8d, 400h
0x18002c230  lea     rdx, [rsp+898h+var_818]
0x18002c238  lea     rcx, [rsp+898h+var_858]
0x18002c23d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002c243  test    rdi, rdi
0x18002c246  jnz     short loc_18002C24F
0x18002c248  xor     ebx, ebx
0x18002c24a  jmp     loc_18002C31C
0x18002c24f  mov     rax, [rbx]
0x18002c252  mov     rcx, rbx
0x18002c255  mov     rax, [rax+58h]
0x18002c259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c25e  mov     rcx, rax
0x18002c261  lea     rdx, [rsp+898h+var_858]
0x18002c266  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x18002c26c  mov     ebx, eax
0x18002c26e  test    eax, eax
0x18002c270  js      loc_18002C31C
0x18002c276  mov     rdx, rdi; Token
0x18002c279  xor     ecx, ecx; Thread
0x18002c27b  call    cs:__imp_SetThreadToken
0x18002c281  test    eax, eax
0x18002c283  jnz     short loc_18002C2A0
0x18002c285  call    cs:__imp_GetLastError
0x18002c28b  mov     ebx, eax
0x18002c28d  test    eax, eax
0x18002c28f  jle     loc_18002C31C
0x18002c295  movzx   ebx, ax
0x18002c298  or      ebx, 80070000h
0x18002c29e  jmp     short loc_18002C31C
0x18002c2a0  xor     edx, edx
0x18002c2a2  xor     ecx, ecx
0x18002c2a4  call    cs:__imp_?ThreadPoolSetInfo@@YA_KW4THREAD_POOL_INFO@@_K@Z; ThreadPoolSetInfo(THREAD_POOL_INFO,unsigned __int64)
0x18002c2aa  lea     rcx, [rsp+898h+var_858]
0x18002c2af  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002c2b5  mov     edi, 1
0x18002c2ba  mov     [rsp+898h+hTemplateFile], 0; hTemplateFile
0x18002c2c3  mov     rcx, rax; lpFileName
0x18002c2c6  mov     [rsp+898h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x18002c2ca  xor     r9d, r9d; lpSecurityAttributes
0x18002c2cd  mov     [rsp+898h+dwCreationDisposition], 3; dwCreationDisposition
0x18002c2d5  mov     edx, 80000000h; dwDesiredAccess
0x18002c2da  lea     r8d, [rdi+6]; dwShareMode
0x18002c2de  call    cs:__imp_CreateFileW
0x18002c2e4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002c2e8  jnz     short loc_18002C301
0x18002c2ea  call    cs:__imp_GetLastError
0x18002c2f0  mov     ebx, eax
0x18002c2f2  test    eax, eax
0x18002c2f4  jle     short loc_18002C30C
0x18002c2f6  movzx   ebx, ax
0x18002c2f9  or      ebx, 80070000h
0x18002c2ff  jmp     short loc_18002C30C
0x18002c301  xor     ebx, ebx
0x18002c303  mov     rcx, rax; hObject
0x18002c306  call    cs:__imp_CloseHandle
0x18002c30c  xor     edx, edx
0x18002c30e  mov     ecx, edi
0x18002c310  call    cs:__imp_?ThreadPoolSetInfo@@YA_KW4THREAD_POOL_INFO@@_K@Z; ThreadPoolSetInfo(THREAD_POOL_INFO,unsigned __int64)
0x18002c316  call    cs:__imp_RevertToSelf
0x18002c31c  lea     rcx, [rsp+898h+var_858]
0x18002c321  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002c327  mov     eax, ebx
0x18002c329  mov     rcx, [rsp+898h+var_18]
0x18002c331  xor     rcx, rsp; StackCookie
0x18002c334  call    __security_check_cookie
0x18002c339  mov     rbx, [rsp+898h+arg_10]
0x18002c341  add     rsp, 890h
0x18002c348  pop     rdi
0x18002c349  retn
```
