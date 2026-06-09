# CUserProfileRoamingProvider::_SetHiveFileTime(void)

- ea: `0x1800092d4`
- end: `0x180009582`
- name: `?_SetHiveFileTime@CUserProfileRoamingProvider@@AEAAJXZ`
- size: `686`
- prototype: `__int64 __fastcall(CUserProfileRoamingProvider *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180008258`

## callees

- `0x180005234`
- `0x180005424`
- `0x18000547c`
- `0x180006a9c`
- `0x1800092d4`
- `0x180011454`
- `0x180013da0`
- `0x180016eb0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800093e6`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18000950f`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800093e6`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18000950f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009396`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800094ae`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009396`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800094ae`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x1800094e8`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180009536`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x1800094e8`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180009536`

## string_xrefs

- `0x180009357`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x1800093ad`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180009465`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x1800094c5`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUserProfileRoamingProvider::_SetHiveFileTime(CUserProfileRoamingProvider *this)
{
  const unsigned __int16 *v2; // r14
  const unsigned __int16 *v3; // rbx
  __int64 v4; // rax
  int v5; // eax
  unsigned int LastError; // ebx
  HANDLE FileW; // rax
  const char *v8; // r9
  void *v9; // rdi
  unsigned int v10; // r8d
  const char *v11; // r9
  __int64 v12; // rax
  int v13; // eax
  HANDLE v14; // rax
  const char *v15; // r9
  void *v16; // rbx
  unsigned int v17; // r8d
  const char *v18; // r9
  unsigned int v19; // r8d
  const char *v20; // r9
  unsigned int v21; // r8d
  const char *v22; // r9
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-50h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-50h]
  LPCWSTR v26[3]; // [rsp+40h] [rbp-30h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  struct _FILETIME LastWriteTime; // [rsp+A0h] [rbp+30h] BYREF
  HANDLE v30; // [rsp+A8h] [rbp+38h] BYREF
  HANDLE v31; // [rsp+B0h] [rbp+40h] BYREF

  memset(lpFileName, 0, sizeof(lpFileName));
  v2 = L"ntuser.man";
  v3 = L"ntuser.man";
  if ( ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) & 1) == 0 )
    v3 = L"ntuser.dat";
  v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 80LL))(*((_QWORD *)this + 1));
  v5 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
         lpFileName,
         L"%s\\%s",
         v4,
         v3);
  LastError = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAE6,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)(unsigned int)v5,
      dwCreationDisposition);
    goto LABEL_23;
  }
  FileW = CreateFileW(lpFileName[0], 0xC0000000, 1u, 0, 3u, 0x80u, 0);
  v9 = FileW;
  v30 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xAF0,
                  (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
                  v8);
LABEL_7:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v30);
    goto LABEL_23;
  }
  LastWriteTime = 0;
  if ( !GetFileTime(FileW, 0, 0, &LastWriteTime) )
    wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0xAF4, v10, v11);
  memset(v26, 0, sizeof(v26));
  if ( ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) & 1) == 0 )
    v2 = L"ntuser.dat";
  v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 72LL))(*((_QWORD *)this + 1));
  v13 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
          v26,
          L"%s\\%s",
          v12,
          v2);
  LastError = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAFA,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)(unsigned int)v13,
      dwCreationDispositiona);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v26);
    goto LABEL_7;
  }
  v14 = CreateFileW(v26[0], 0xC0000000, 1u, 0, 3u, 0x80u, 0);
  v16 = v14;
  v31 = v14;
  if ( v14 == (HANDLE)-1LL )
  {
    wil::details::in1diag3::Log_GetLastError(
      retaddr,
      (void *)0xB06,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      v15);
  }
  else
  {
    if ( !SetFileTime(v14, 0, 0, &LastWriteTime) )
      wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0xB0A, v17, v18);
    if ( !GetFileTime(v16, 0, 0, &LastWriteTime) )
      wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0xB0B, v19, v20);
  }
  if ( !SetFileTime(v9, 0, 0, &LastWriteTime) )
    wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0xB0F, v21, v22);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v31);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v26);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v30);
  LastError = 0;
LABEL_23:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
  return LastError;
}

```

## disassembly

```asm
0x1800092d4  push    rbp
0x1800092d6  push    rbx
0x1800092d7  push    rsi
0x1800092d8  push    rdi
0x1800092d9  push    r14
0x1800092db  mov     rbp, rsp
0x1800092de  sub     rsp, 70h
0x1800092e2  mov     rsi, rcx
0x1800092e5  mov     [rbp+lpFileName], 0
0x1800092ed  mov     [rbp+var_10], 0
0x1800092f5  mov     [rbp+var_8], 0
0x1800092fd  mov     rcx, [rcx+8]
0x180009301  mov     rax, [rcx]
0x180009304  mov     rax, [rax+10h]
0x180009308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000930d  test    al, 1
0x18000930f  lea     rax, ?c_szNTUserDat@@3QBGB; "ntuser.dat"
0x180009316  lea     r14, ?c_szNTUserMan@@3QBGB; "ntuser.man"
0x18000931d  mov     rbx, r14
0x180009320  cmovz   rbx, rax
0x180009324  mov     rcx, [rsi+8]
0x180009328  mov     rax, [rcx]
0x18000932b  mov     rax, [rax+50h]
0x18000932f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009334  mov     r8, rax
0x180009337  mov     r9, rbx
0x18000933a  lea     rdx, aSS; "%s\\%s"
0x180009341  lea     rcx, [rbp+lpFileName]
0x180009345  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18000934a  mov     ebx, eax
0x18000934c  test    eax, eax
0x18000934e  jns     short loc_18000936D
0x180009350  mov     rcx, [rbp+28h]; this
0x180009354  mov     r9d, eax; char *
0x180009357  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x18000935e  mov     edx, 0AE6h; void *
0x180009363  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009368  jmp     loc_18000956C
0x18000936d  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x180009376  mov     [rsp+70h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000937e  mov     [rsp+70h+dwCreationDisposition], 3; int
0x180009386  xor     r9d, r9d; lpSecurityAttributes
0x180009389  mov     edx, 0C0000000h; dwDesiredAccess
0x18000938e  lea     r8d, [r9+1]; dwShareMode
0x180009392  mov     rcx, [rbp+lpFileName]; lpFileName
0x180009396  call    cs:__imp_CreateFileW
0x18000939c  mov     rdi, rax
0x18000939f  mov     [rbp+arg_8], rax
0x1800093a3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800093a7  jnz     short loc_1800093CE
0x1800093a9  mov     rcx, [rbp+28h]; this
0x1800093ad  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x1800093b4  mov     edx, 0AF0h; void *
0x1800093b9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800093be  mov     ebx, eax
0x1800093c0  lea     rcx, [rbp+arg_8]
0x1800093c4  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800093c9  jmp     loc_18000956C
0x1800093ce  mov     qword ptr [rbp+LastWriteTime.dwLowDateTime], 0
0x1800093d6  mov     rbx, [rbp+28h]
0x1800093da  lea     r9, [rbp+LastWriteTime]; lpLastWriteTime
0x1800093de  xor     r8d, r8d; lpLastAccessTime
0x1800093e1  xor     edx, edx; lpCreationTime
0x1800093e3  mov     rcx, rdi; hFile
0x1800093e6  call    cs:__imp_GetFileTime
0x1800093ec  test    eax, eax
0x1800093ee  jnz     short loc_1800093FD
0x1800093f0  mov     edx, 0AF4h; void *
0x1800093f5  mov     rcx, rbx; this
0x1800093f8  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800093fd  mov     [rbp+var_30], 0
0x180009405  mov     [rbp+var_28], 0
0x18000940d  mov     [rbp+var_20], 0
0x180009415  mov     rcx, [rsi+8]
0x180009419  mov     rax, [rcx]
0x18000941c  mov     rax, [rax+10h]
0x180009420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009425  test    al, 1
0x180009427  lea     rax, ?c_szNTUserDat@@3QBGB; "ntuser.dat"
0x18000942e  cmovz   r14, rax
0x180009432  mov     rcx, [rsi+8]
0x180009436  mov     rax, [rcx]
0x180009439  mov     rax, [rax+48h]
0x18000943d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009442  mov     r8, rax
0x180009445  mov     r9, r14
0x180009448  lea     rdx, aSS; "%s\\%s"
0x18000944f  lea     rcx, [rbp+var_30]
0x180009453  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180009458  mov     ebx, eax
0x18000945a  test    eax, eax
0x18000945c  jns     short loc_180009485
0x18000945e  mov     rcx, [rbp+28h]; this
0x180009462  mov     r9d, eax; char *
0x180009465  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x18000946c  mov     edx, 0AFAh; void *
0x180009471  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009476  nop
0x180009477  lea     rcx, [rbp+var_30]
0x18000947b  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180009480  jmp     loc_1800093C0
0x180009485  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x18000948e  mov     [rsp+70h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180009496  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x18000949e  xor     r9d, r9d; lpSecurityAttributes
0x1800094a1  mov     edx, 0C0000000h; dwDesiredAccess
0x1800094a6  lea     r8d, [r9+1]; dwShareMode
0x1800094aa  mov     rcx, [rbp+var_30]; lpFileName
0x1800094ae  call    cs:__imp_CreateFileW
0x1800094b4  mov     rbx, rax
0x1800094b7  mov     [rbp+arg_10], rax
0x1800094bb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800094bf  jnz     short loc_1800094D8
0x1800094c1  mov     rcx, [rbp+28h]; this
0x1800094c5  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x1800094cc  mov     edx, 0B06h; void *
0x1800094d1  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x1800094d6  jmp     short loc_180009526
0x1800094d8  mov     rsi, [rbp+28h]
0x1800094dc  lea     r9, [rbp+LastWriteTime]; lpLastWriteTime
0x1800094e0  xor     r8d, r8d; lpLastAccessTime
0x1800094e3  xor     edx, edx; lpCreationTime
0x1800094e5  mov     rcx, rbx; hFile
0x1800094e8  call    cs:__imp_SetFileTime
0x1800094ee  test    eax, eax
0x1800094f0  jnz     short loc_1800094FF
0x1800094f2  mov     edx, 0B0Ah; void *
0x1800094f7  mov     rcx, rsi; this
0x1800094fa  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800094ff  mov     rsi, [rbp+28h]
0x180009503  lea     r9, [rbp+LastWriteTime]; lpLastWriteTime
0x180009507  xor     r8d, r8d; lpLastAccessTime
0x18000950a  xor     edx, edx; lpCreationTime
0x18000950c  mov     rcx, rbx; hFile
0x18000950f  call    cs:__imp_GetFileTime
0x180009515  test    eax, eax
0x180009517  jnz     short loc_180009526
0x180009519  mov     edx, 0B0Bh; void *
0x18000951e  mov     rcx, rsi; this
0x180009521  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180009526  mov     rbx, [rbp+28h]
0x18000952a  lea     r9, [rbp+LastWriteTime]; lpLastWriteTime
0x18000952e  xor     r8d, r8d; lpLastAccessTime
0x180009531  xor     edx, edx; lpCreationTime
0x180009533  mov     rcx, rdi; hFile
0x180009536  call    cs:__imp_SetFileTime
0x18000953c  test    eax, eax
0x18000953e  jnz     short loc_18000954D
0x180009540  mov     edx, 0B0Fh; void *
0x180009545  mov     rcx, rbx; this
0x180009548  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18000954d  lea     rcx, [rbp+arg_10]
0x180009551  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180009556  nop
0x180009557  lea     rcx, [rbp+var_30]
0x18000955b  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180009560  nop
0x180009561  lea     rcx, [rbp+arg_8]
0x180009565  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000956a  xor     ebx, ebx
0x18000956c  lea     rcx, [rbp+lpFileName]
0x180009570  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180009575  mov     eax, ebx
0x180009577  add     rsp, 70h
0x18000957b  pop     r14
0x18000957d  pop     rdi
0x18000957e  pop     rsi
0x18000957f  pop     rbx
0x180009580  pop     rbp
0x180009581  retn
```
