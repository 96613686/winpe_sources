# W3_FILE_INFO::AccessCheck(void *,void *)

- ea: `0x18002e990`
- end: `0x18002eb36`
- name: `?AccessCheck@W3_FILE_INFO@@UEAAJPEAX0@Z`
- size: `422`
- prototype: `__int64 __fastcall(W3_FILE_INFO *this, void *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18002e990`
- `0x18003773a`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002ea27`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002ea27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ead9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ead9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eab7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eab7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002eaa5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002eaa5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002eaf5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002eaf5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002eb06`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002eb06`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002ea70`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002ea70`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002e9dd`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002e9dd`
- `iisutil!MakePathCanonicalizationProof` at `0x18002ea0c`
- `iisutil!MakePathCanonicalizationProof` at `0x18002ea0c`
- `W3TP!ThreadPoolSetInfo` at `0x18002ea5f`
- `W3TP!ThreadPoolSetInfo` at `0x18002eae9`
- `W3TP!ThreadPoolSetInfo` at `0x18002ea5f`
- `W3TP!ThreadPoolSetInfo` at `0x18002eae9`

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
0x18002e990  mov     [rsp+arg_10], rbx
0x18002e995  push    rdi
0x18002e996  sub     rsp, 890h
0x18002e99d  mov     rax, cs:__security_cookie
0x18002e9a4  xor     rax, rsp
0x18002e9a7  mov     [rsp+898h+var_18], rax
0x18002e9af  mov     rdi, rdx
0x18002e9b2  mov     rbx, rcx
0x18002e9b5  xor     edx, edx; Val
0x18002e9b7  lea     rcx, [rsp+898h+var_818]; void *
0x18002e9bf  mov     r8d, 800h; Size
0x18002e9c5  call    memset_0
0x18002e9ca  mov     r8d, 400h
0x18002e9d0  lea     rdx, [rsp+898h+var_818]
0x18002e9d8  lea     rcx, [rsp+898h+var_858]
0x18002e9dd  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002e9e4  nop     dword ptr [rax+rax+00h]
0x18002e9e9  test    rdi, rdi
0x18002e9ec  jnz     short loc_18002E9F5
0x18002e9ee  xor     ebx, ebx
0x18002e9f0  jmp     loc_18002EB01
0x18002e9f5  mov     rax, [rbx]
0x18002e9f8  mov     rcx, rbx
0x18002e9fb  mov     rax, [rax+58h]
0x18002e9ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea04  mov     rcx, rax
0x18002ea07  lea     rdx, [rsp+898h+var_858]
0x18002ea0c  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x18002ea13  nop     dword ptr [rax+rax+00h]
0x18002ea18  mov     ebx, eax
0x18002ea1a  test    eax, eax
0x18002ea1c  js      loc_18002EB01
0x18002ea22  mov     rdx, rdi; Token
0x18002ea25  xor     ecx, ecx; Thread
0x18002ea27  call    cs:__imp_SetThreadToken
0x18002ea2e  nop     dword ptr [rax+rax+00h]
0x18002ea33  test    eax, eax
0x18002ea35  jnz     short loc_18002EA5B
0x18002ea37  call    cs:__imp_GetLastError
0x18002ea3e  nop     dword ptr [rax+rax+00h]
0x18002ea43  mov     ebx, eax
0x18002ea45  test    eax, eax
0x18002ea47  jle     loc_18002EB01
0x18002ea4d  movzx   ebx, ax
0x18002ea50  or      ebx, 80070000h
0x18002ea56  jmp     loc_18002EB01
0x18002ea5b  xor     edx, edx
0x18002ea5d  xor     ecx, ecx
0x18002ea5f  call    cs:__imp_?ThreadPoolSetInfo@@YA_KW4THREAD_POOL_INFO@@_K@Z; ThreadPoolSetInfo(THREAD_POOL_INFO,unsigned __int64)
0x18002ea66  nop     dword ptr [rax+rax+00h]
0x18002ea6b  lea     rcx, [rsp+898h+var_858]
0x18002ea70  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002ea77  nop     dword ptr [rax+rax+00h]
0x18002ea7c  mov     edi, 1
0x18002ea81  mov     [rsp+898h+hTemplateFile], 0; hTemplateFile
0x18002ea8a  mov     rcx, rax; lpFileName
0x18002ea8d  mov     [rsp+898h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x18002ea91  xor     r9d, r9d; lpSecurityAttributes
0x18002ea94  mov     [rsp+898h+dwCreationDisposition], 3; dwCreationDisposition
0x18002ea9c  mov     edx, 80000000h; dwDesiredAccess
0x18002eaa1  lea     r8d, [rdi+6]; dwShareMode
0x18002eaa5  call    cs:__imp_CreateFileW
0x18002eaac  nop     dword ptr [rax+rax+00h]
0x18002eab1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002eab5  jnz     short loc_18002EAD4
0x18002eab7  call    cs:__imp_GetLastError
0x18002eabe  nop     dword ptr [rax+rax+00h]
0x18002eac3  mov     ebx, eax
0x18002eac5  test    eax, eax
0x18002eac7  jle     short loc_18002EAE5
0x18002eac9  movzx   ebx, ax
0x18002eacc  or      ebx, 80070000h
0x18002ead2  jmp     short loc_18002EAE5
0x18002ead4  xor     ebx, ebx
0x18002ead6  mov     rcx, rax; hObject
0x18002ead9  call    cs:__imp_CloseHandle
0x18002eae0  nop     dword ptr [rax+rax+00h]
0x18002eae5  xor     edx, edx
0x18002eae7  mov     ecx, edi
0x18002eae9  call    cs:__imp_?ThreadPoolSetInfo@@YA_KW4THREAD_POOL_INFO@@_K@Z; ThreadPoolSetInfo(THREAD_POOL_INFO,unsigned __int64)
0x18002eaf0  nop     dword ptr [rax+rax+00h]
0x18002eaf5  call    cs:__imp_RevertToSelf
0x18002eafc  nop     dword ptr [rax+rax+00h]
0x18002eb01  lea     rcx, [rsp+898h+var_858]
0x18002eb06  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002eb0d  nop     dword ptr [rax+rax+00h]
0x18002eb12  mov     eax, ebx
0x18002eb14  mov     rcx, [rsp+898h+var_18]
0x18002eb1c  xor     rcx, rsp; StackCookie
0x18002eb1f  call    __security_check_cookie
0x18002eb24  mov     rbx, [rsp+898h+arg_10]
0x18002eb2c  add     rsp, 890h
0x18002eb33  pop     rdi
0x18002eb34  retn
```
