# _CopyTree(ushort *,unsigned __int64,ushort *,unsigned __int64,void *)

- ea: `0x18000d620`
- end: `0x18000d97e`
- name: `?_CopyTree@@YAJPEAG_K01PEAX@Z`
- size: `862`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int16 *, PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18000d620`
- `0x180016bec`

## callees

- `0x1800063e0`
- `0x180006a9c`
- `0x180007c60`
- `0x1800090f0`
- `0x18000a1c0`
- `0x18000a540`
- `0x18000a750`
- `0x18000d620`
- `0x18000d984`
- `0x18000da48`
- `0x1800169e0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18000d7df`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18000d7df`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000d709`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000d709`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000d931`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000d931`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000d828`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000d904`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000d828`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000d904`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000d78f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000d78f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000d920`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000d920`

## string_xrefs

- `0x18000d7ad`: `Failed to create target folder %ws`

## pseudocode

```c
__int64 __fastcall _CopyTree(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  int v7; // eax
  unsigned __int64 v8; // rdx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  unsigned __int16 *v11; // r12
  LPWIN32_FIND_DATAW v12; // rsi
  HANDLE FirstFileW; // r13
  int v14; // eax
  __int64 v15; // rdx
  BOOL DirectoryW; // eax
  int v17; // eax
  BOOL v18; // eax
  int v19; // eax
  int v20; // eax
  __int64 v21; // rdx
  BOOL v22; // eax
  int v23; // eax
  int v24; // eax
  __int64 v25; // rdx
  int Error; // eax
  int v28; // [rsp+20h] [rbp-20h]
  unsigned __int64 v29; // [rsp+30h] [rbp-10h] BYREF
  LPWIN32_FIND_DATAW lpFindFileData; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  unsigned __int64 v33; // [rsp+88h] [rbp+48h] BYREF
  unsigned __int16 *v34; // [rsp+98h] [rbp+58h] BYREF

  v34 = a4;
  lpFindFileData = 0;
  v33 = 0;
  v7 = PathCchAddBackslashEx(a1, a2, (unsigned __int16 **)&lpFindFileData, &v33);
  v9 = v7;
  if ( v7 < 0 )
  {
    v10 = 222;
LABEL_9:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"minio\\profapi\\load.cpp",
      (const char *)(unsigned int)v7,
      v28);
    return v9;
  }
  v34 = 0;
  v29 = 0;
  v7 = PathCchAddBackslashEx(a3, v8, &v34, &v29);
  v9 = v7;
  if ( v7 < 0 )
  {
    v10 = 227;
    goto LABEL_9;
  }
  v11 = (unsigned __int16 *)lpFindFileData;
  v7 = StringCchCopyW((unsigned __int16 *)lpFindFileData, v33, L"*.*");
  v9 = v7;
  if ( v7 < 0 )
  {
    v10 = 230;
    goto LABEL_9;
  }
  lpFindFileData = 0;
  v7 = ResultFromHeapAlloc(0x250u, (void **)&lpFindFileData);
  v9 = v7;
  if ( v7 < 0 )
  {
    v10 = 235;
    goto LABEL_9;
  }
  v12 = lpFindFileData;
  FirstFileW = FindFirstFileW(a1, lpFindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    while ( 1 )
    {
      if ( (v12->dwFileAttributes & 0x10) != 0 )
      {
        if ( StringIsEqual(v12->cFileName, L".")
          || StringIsEqual(v12->cFileName, L"..")
          || (v12->dwFileAttributes & 0x400) != 0 )
        {
          goto LABEL_40;
        }
        v14 = StringCchCopyW(v34, v29, v12->cFileName);
        v9 = v14;
        if ( v14 >= 0 )
        {
          DirectoryW = CreateDirectoryW(a3, 0);
          v17 = ResultFromWin32Bool(DirectoryW);
          v9 = v17;
          if ( v17 < 0 )
          {
            if ( v17 != -2147024713 )
            {
              wil::details::in1diag3::Log_HrMsg(
                retaddr,
                (void *)0x121,
                (unsigned int)"minio\\profapi\\load.cpp",
                (const char *)(unsigned int)v17,
                (int)"Failed to create target folder %ws",
                (const char *)a3);
LABEL_39:
              *v34 = 0;
              goto LABEL_40;
            }
            v18 = SetFileSecurityW(a3, 4u, pSecurityDescriptor);
            v19 = ResultFromWin32Bool(v18);
            if ( v19 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x110,
                (unsigned int)"minio\\profapi\\load.cpp",
                (const char *)(unsigned int)v19,
                v28);
          }
          v20 = StringCchCopyW(v11, v33, v12->cFileName);
          v9 = v20;
          if ( v20 < 0 )
          {
            v21 = 277;
LABEL_33:
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)v21,
              (unsigned int)"minio\\profapi\\load.cpp",
              (const char *)(unsigned int)v20,
              v28);
            goto LABEL_39;
          }
          v22 = SetFileAttributesW(a3, v12->dwFileAttributes);
          v23 = ResultFromWin32Bool(v22);
          if ( v23 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x118,
              (unsigned int)"minio\\profapi\\load.cpp",
              (const char *)(unsigned int)v23,
              v28);
          v24 = _CopyTree(a1, 0x104u, a3, 0x104u, pSecurityDescriptor);
          v9 = v24;
          if ( v24 < 0 )
          {
            v25 = 283;
            goto LABEL_36;
          }
          goto LABEL_38;
        }
        v15 = 260;
      }
      else
      {
        v14 = StringCchCopyW(v34, v29, v12->cFileName);
        v9 = v14;
        if ( v14 >= 0 )
        {
          v20 = StringCchCopyW(v11, v33, v12->cFileName);
          v9 = v20;
          if ( v20 < 0 )
          {
            v21 = 301;
            goto LABEL_33;
          }
          v24 = _CopyFile(a1, a3);
          v9 = v24;
          if ( v24 >= 0 )
          {
            SetFileAttributesW(a3, v12->dwFileAttributes);
          }
          else
          {
            v25 = 304;
LABEL_36:
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)v25,
              (unsigned int)"minio\\profapi\\load.cpp",
              (const char *)(unsigned int)v24,
              v28);
          }
LABEL_38:
          *v11 = 0;
          goto LABEL_39;
        }
        v15 = 298;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"minio\\profapi\\load.cpp",
        (const char *)(unsigned int)v14,
        v28);
LABEL_40:
      if ( !FindNextFileW(FirstFileW, v12) )
      {
        FindClose(FirstFileW);
        goto LABEL_44;
      }
    }
  }
  Error = ResultFromKnownLastError();
  v9 = Error;
  if ( Error < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x140,
      (unsigned int)"minio\\profapi\\load.cpp",
      (const char *)(unsigned int)Error,
      v28);
LABEL_44:
  ResultFromHeapFree(v12);
  return v9;
}

```

## disassembly

```asm
0x18000d620  mov     rax, rsp
0x18000d623  mov     [rax+18h], rbx
0x18000d627  mov     [rax+20h], r9
0x18000d62b  mov     [rax+10h], rdx
0x18000d62f  mov     [rax+8], rcx
0x18000d633  push    rbp
0x18000d634  push    rsi
0x18000d635  push    rdi
0x18000d636  push    r12
0x18000d638  push    r13
0x18000d63a  push    r14
0x18000d63c  push    r15
0x18000d63e  mov     rbp, rsp
0x18000d641  sub     rsp, 40h
0x18000d645  mov     r14, r8
0x18000d648  mov     [rbp+lpFindFileData], 0
0x18000d650  lea     r8, [rbp+lpFindFileData]; unsigned __int16 **
0x18000d654  mov     [rbp+arg_8], 0
0x18000d65c  lea     r9, [rbp+arg_8]; unsigned __int64 *
0x18000d660  mov     rdi, rcx
0x18000d663  call    ?PathCchAddBackslashEx@@YAJPEAG_KPEAPEAGPEA_K@Z; PathCchAddBackslashEx(ushort *,unsigned __int64,ushort * *,unsigned __int64 *)
0x18000d668  mov     ebx, eax
0x18000d66a  test    eax, eax
0x18000d66c  jns     short loc_18000D675
0x18000d66e  mov     edx, 0DEh
0x18000d673  jmp     short loc_18000D6E7
0x18000d675  lea     r9, [rbp+var_10]; unsigned __int64 *
0x18000d679  mov     [rbp+arg_18], 0
0x18000d681  lea     r8, [rbp+arg_18]; unsigned __int16 **
0x18000d685  mov     [rbp+var_10], 0
0x18000d68d  mov     rcx, r14; unsigned __int16 *
0x18000d690  call    ?PathCchAddBackslashEx@@YAJPEAG_KPEAPEAGPEA_K@Z; PathCchAddBackslashEx(ushort *,unsigned __int64,ushort * *,unsigned __int64 *)
0x18000d695  mov     ebx, eax
0x18000d697  test    eax, eax
0x18000d699  jns     short loc_18000D6A2
0x18000d69b  mov     edx, 0E3h
0x18000d6a0  jmp     short loc_18000D6E7
0x18000d6a2  mov     r12, [rbp+lpFindFileData]
0x18000d6a6  lea     r8, asc_18001A4E0; "*.*"
0x18000d6ad  mov     rdx, [rbp+arg_8]; unsigned __int64
0x18000d6b1  mov     rcx, r12; unsigned __int16 *
0x18000d6b4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d6b9  mov     ebx, eax
0x18000d6bb  test    eax, eax
0x18000d6bd  jns     short loc_18000D6C6
0x18000d6bf  mov     edx, 0E6h
0x18000d6c4  jmp     short loc_18000D6E7
0x18000d6c6  lea     rdx, [rbp+lpFindFileData]; void **
0x18000d6ca  mov     [rbp+lpFindFileData], 0
0x18000d6d2  mov     ecx, 250h; dwBytes
0x18000d6d7  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x18000d6dc  mov     ebx, eax
0x18000d6de  test    eax, eax
0x18000d6e0  jns     short loc_18000D6FF
0x18000d6e2  mov     edx, 0EBh; void *
0x18000d6e7  mov     rcx, [rbp+38h]; this
0x18000d6eb  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x18000d6f2  mov     r9d, eax; char *
0x18000d6f5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d6fa  jmp     loc_18000D964
0x18000d6ff  mov     rsi, [rbp+lpFindFileData]
0x18000d703  mov     rcx, rdi; lpFileName
0x18000d706  mov     rdx, rsi; lpFindFileData
0x18000d709  call    cs:__imp_FindFirstFileW
0x18000d70f  mov     r13, rax
0x18000d712  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d716  jz      loc_18000D939
0x18000d71c  lea     rdi, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x18000d723  test    byte ptr [rsi], 10h
0x18000d726  jz      loc_18000D87E
0x18000d72c  lea     r15, [rsi+2Ch]
0x18000d730  mov     rcx, r15; unsigned __int16 *
0x18000d733  lea     rdx, asc_18001CB10; "."
0x18000d73a  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x18000d73f  test    eax, eax
0x18000d741  jnz     loc_18000D91A
0x18000d747  lea     rdx, asc_18001CBD8; ".."
0x18000d74e  mov     rcx, r15; unsigned __int16 *
0x18000d751  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x18000d756  test    eax, eax
0x18000d758  jnz     loc_18000D91A
0x18000d75e  test    dword ptr [rsi], 400h
0x18000d764  jnz     loc_18000D91A
0x18000d76a  mov     rdx, [rbp+var_10]; unsigned __int64
0x18000d76e  mov     r8, r15; unsigned __int16 *
0x18000d771  mov     rcx, [rbp+arg_18]; unsigned __int16 *
0x18000d775  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d77a  mov     ebx, eax
0x18000d77c  test    eax, eax
0x18000d77e  jns     short loc_18000D78A
0x18000d780  mov     edx, 104h
0x18000d785  jmp     loc_18000D89A
0x18000d78a  xor     edx, edx; lpSecurityAttributes
0x18000d78c  mov     rcx, r14; lpPathName
0x18000d78f  call    cs:__imp_CreateDirectoryW
0x18000d795  mov     ecx, eax; int
0x18000d797  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18000d79c  mov     ebx, eax
0x18000d79e  test    eax, eax
0x18000d7a0  jns     short loc_18000D804
0x18000d7a2  cmp     eax, 800700B7h
0x18000d7a7  jz      short loc_18000D7D3
0x18000d7a9  mov     rcx, [rbp+38h]; this
0x18000d7ad  lea     rax, aFailedToCreate; "Failed to create target folder %ws"
0x18000d7b4  mov     [rsp+40h+var_18], r14; char *
0x18000d7b9  mov     r9d, ebx; char *
0x18000d7bc  mov     r8, rdi; unsigned int
0x18000d7bf  mov     [rsp+40h+var_20], rax; int
0x18000d7c4  mov     edx, 121h; void *
0x18000d7c9  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000d7ce  jmp     loc_18000D911
0x18000d7d3  mov     r8, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18000d7d7  mov     edx, 4; SecurityInformation
0x18000d7dc  mov     rcx, r14; lpFileName
0x18000d7df  call    cs:__imp_SetFileSecurityW
0x18000d7e5  mov     ecx, eax; int
0x18000d7e7  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18000d7ec  test    eax, eax
0x18000d7ee  jns     short loc_18000D804
0x18000d7f0  mov     rcx, [rbp+38h]; this
0x18000d7f4  mov     r9d, eax; char *
0x18000d7f7  mov     r8, rdi; unsigned int
0x18000d7fa  mov     edx, 110h; void *
0x18000d7ff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d804  mov     rdx, [rbp+arg_8]; unsigned __int64
0x18000d808  mov     r8, r15; unsigned __int16 *
0x18000d80b  mov     rcx, r12; unsigned __int16 *
0x18000d80e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d813  mov     ebx, eax
0x18000d815  test    eax, eax
0x18000d817  jns     short loc_18000D823
0x18000d819  mov     edx, 115h
0x18000d81e  jmp     loc_18000D8C6
0x18000d823  mov     edx, [rsi]; dwFileAttributes
0x18000d825  mov     rcx, r14; lpFileName
0x18000d828  call    cs:__imp_SetFileAttributesW
0x18000d82e  mov     ecx, eax; int
0x18000d830  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18000d835  test    eax, eax
0x18000d837  jns     short loc_18000D84D
0x18000d839  mov     rcx, [rbp+38h]; this
0x18000d83d  mov     r9d, eax; char *
0x18000d840  mov     r8, rdi; unsigned int
0x18000d843  mov     edx, 118h; void *
0x18000d848  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d84d  mov     rax, [rbp+pSecurityDescriptor]
0x18000d851  mov     r15d, 104h
0x18000d857  mov     rcx, [rbp+lpFileName]; unsigned __int16 *
0x18000d85b  mov     r9d, r15d; unsigned __int64
0x18000d85e  mov     edx, r15d; unsigned __int64
0x18000d861  mov     [rsp+40h+var_20], rax; int
0x18000d866  mov     r8, r14; unsigned __int16 *
0x18000d869  call    ?_CopyTree@@YAJPEAG_K01PEAX@Z; _CopyTree(ushort *,unsigned __int64,ushort *,unsigned __int64,void *)
0x18000d86e  mov     ebx, eax
0x18000d870  test    eax, eax
0x18000d872  jns     loc_18000D90A
0x18000d878  lea     edx, [r15+17h]
0x18000d87c  jmp     short loc_18000D8EE
0x18000d87e  mov     rdx, [rbp+var_10]; unsigned __int64
0x18000d882  lea     r8, [rsi+2Ch]; unsigned __int16 *
0x18000d886  mov     rcx, [rbp+arg_18]; unsigned __int16 *
0x18000d88a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d88f  mov     ebx, eax
0x18000d891  test    eax, eax
0x18000d893  jns     short loc_18000D8AB
0x18000d895  mov     edx, 12Ah; void *
0x18000d89a  mov     rcx, [rbp+38h]; this
0x18000d89e  mov     r8, rdi; unsigned int
0x18000d8a1  mov     r9d, eax; char *
0x18000d8a4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d8a9  jmp     short loc_18000D91A
0x18000d8ab  mov     rdx, [rbp+arg_8]; unsigned __int64
0x18000d8af  lea     r8, [rsi+2Ch]; unsigned __int16 *
0x18000d8b3  mov     rcx, r12; unsigned __int16 *
0x18000d8b6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d8bb  mov     ebx, eax
0x18000d8bd  test    eax, eax
0x18000d8bf  jns     short loc_18000D8D7
0x18000d8c1  mov     edx, 12Dh; void *
0x18000d8c6  mov     rcx, [rbp+38h]; this
0x18000d8ca  mov     r8, rdi; unsigned int
0x18000d8cd  mov     r9d, eax; char *
0x18000d8d0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d8d5  jmp     short loc_18000D911
0x18000d8d7  mov     rcx, [rbp+lpFileName]; unsigned __int16 *
0x18000d8db  mov     rdx, r14; unsigned __int16 *
0x18000d8de  call    ?_CopyFile@@YAJPEBG0@Z; _CopyFile(ushort const *,ushort const *)
0x18000d8e3  mov     ebx, eax
0x18000d8e5  test    eax, eax
0x18000d8e7  jns     short loc_18000D8FF
0x18000d8e9  mov     edx, 130h; void *
0x18000d8ee  mov     rcx, [rbp+38h]; this
0x18000d8f2  mov     r8, rdi; unsigned int
0x18000d8f5  mov     r9d, eax; char *
0x18000d8f8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d8fd  jmp     short loc_18000D90A
0x18000d8ff  mov     edx, [rsi]; dwFileAttributes
0x18000d901  mov     rcx, r14; lpFileName
0x18000d904  call    cs:__imp_SetFileAttributesW
0x18000d90a  xor     eax, eax
0x18000d90c  mov     [r12], ax
0x18000d911  mov     rcx, [rbp+arg_18]
0x18000d915  xor     eax, eax
0x18000d917  mov     [rcx], ax
0x18000d91a  mov     rdx, rsi; lpFindFileData
0x18000d91d  mov     rcx, r13; hFindFile
0x18000d920  call    cs:__imp_FindNextFileW
0x18000d926  test    eax, eax
0x18000d928  jnz     loc_18000D723
0x18000d92e  mov     rcx, r13; hFindFile
0x18000d931  call    cs:__imp_FindClose
0x18000d937  jmp     short loc_18000D95C
0x18000d939  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000d93e  mov     ebx, eax
0x18000d940  test    eax, eax
0x18000d942  jns     short loc_18000D95C
0x18000d944  mov     rcx, [rbp+38h]; this
0x18000d948  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x18000d94f  mov     r9d, eax; char *
0x18000d952  mov     edx, 140h; void *
0x18000d957  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d95c  mov     rcx, rsi; lpMem
0x18000d95f  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18000d964  mov     eax, ebx
0x18000d966  mov     rbx, [rsp+40h+arg_10]
0x18000d96e  add     rsp, 40h
0x18000d972  pop     r15
0x18000d974  pop     r14
0x18000d976  pop     r13
0x18000d978  pop     r12
0x18000d97a  pop     rdi
0x18000d97b  pop     rsi
0x18000d97c  pop     rbp
0x18000d97d  retn
```
