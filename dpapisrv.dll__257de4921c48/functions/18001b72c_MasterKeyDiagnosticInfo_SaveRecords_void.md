# MasterKeyDiagnosticInfo::SaveRecords(void)

- ea: `0x18001b72c`
- end: `0x18001b946`
- name: `?SaveRecords@MasterKeyDiagnosticInfo@@QEAAXXZ`
- size: `538`
- prototype: `void __fastcall(MasterKeyDiagnosticInfo *__hidden this)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x18001b0e0`
- `0x18001b550`
- `0x18003a8b0`

## callees

- `0x1800060e0`
- `0x180006c60`
- `0x1800097f0`
- `0x18000db1c`
- `0x1800107c4`
- `0x1800116ec`
- `0x1800136d4`
- `0x18001b72c`
- `0x18001cf40`
- `0x18003a6b8`
- `0x18003ae00`
- `0x18003ae3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18001b740`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x18001b740`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b777`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b777`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001b83f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001b83f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001b884`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001b884`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18001b850`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18001b850`

## pseudocode

```c
void __fastcall MasterKeyDiagnosticInfo::SaveRecords(MasterKeyDiagnosticInfo *this)
{
  struct CRYPT_SERVER_CONTEXT *v1; // rax
  unsigned int v2; // r8d
  const char *v3; // r9
  struct CRYPT_SERVER_CONTEXT *v4; // rbx
  unsigned int v5; // eax
  unsigned int v6; // r8d
  unsigned int v7; // eax
  unsigned int v8; // r8d
  unsigned int v9; // eax
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  const char *v12; // r9
  unsigned int v13; // r8d
  const char *v14; // r9
  unsigned int lpOverlapped; // [rsp+20h] [rbp-48h]
  unsigned int lpOverlappeda; // [rsp+20h] [rbp-48h]
  unsigned int lpOverlappedb; // [rsp+20h] [rbp-48h]
  struct CRYPT_SERVER_CONTEXT *v18; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v19[2]; // [rsp+40h] [rbp-28h] BYREF
  _BYTE v20[24]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  MasterKeyDiagnosticInfo *NumberOfBytesWritten; // [rsp+70h] [rbp+8h] BYREF
  HANDLE hFile; // [rsp+78h] [rbp+10h] BYREF
  unsigned __int16 *v24; // [rsp+80h] [rbp+18h] BYREF
  unsigned __int64 v25; // [rsp+88h] [rbp+20h] BYREF

  NumberOfBytesWritten = this;
  v25 = (unsigned __int64)&SRWLock & -(__int64)(TryAcquireSRWLockExclusive(&SRWLock) != 0);
  if ( v25 )
  {
    v1 = (struct CRYPT_SERVER_CONTEXT *)LocalAlloc(0, 0x270u);
    try
    {
      v4 = v1;
      v18 = v1;
      if ( !v1 )
        wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0xB2, v2, v3);
      v5 = CPSCreateServerContext(v1, 0, 0, 0);
      if ( v5 )
        wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0xB4, v6, (const char *)v5, lpOverlapped);
      v24 = 0;
      v7 = CPSGetUserStorageArea(v4, 0, 1u, 1, &v24);
      if ( v7 )
        wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0xBD, v8, (const char *)v7, lpOverlappeda);
      hFile = (HANDLE)-1LL;
      v9 = OpenFileInStorageArea(v4, 0xC0000000, v24, L"Diagnostic.log", &hFile);
      if ( v9 != 183 && v9 )
        wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0xC9, v10, (const char *)v9, lpOverlappedb);
      SetFilePointer(hFile, 0, 0, 0);
      SetEndOfFile(hFile);
      LODWORD(NumberOfBytesWritten) = 0;
      if ( !WriteFile(
              hFile,
              &MasterKeyDiagnosticInfo::s_currentlySupportedVersion,
              4u,
              (LPDWORD)&NumberOfBytesWritten,
              0) )
        wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xDC, v11, v12);
      v19[0] = &hFile;
      v19[1] = &NumberOfBytesWritten;
      std::for_each<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>>>>>,_lambda_c16354c18a8367b613a24b6278bec278_>(
        v20,
        *(_QWORD *)qword_18004C920,
        qword_18004C920,
        v19);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
      wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>(&v24);
      wil::details::unique_storage<wil::details::resource_policy<CRYPT_SERVER_CONTEXT *,unsigned long (*)(CRYPT_SERVER_CONTEXT *),&unsigned long CPSDeleteServerContext(CRYPT_SERVER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,CRYPT_SERVER_CONTEXT *,CRYPT_SERVER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<CRYPT_SERVER_CONTEXT *,unsigned long (*)(CRYPT_SERVER_CONTEXT *),&unsigned long CPSDeleteServerContext(CRYPT_SERVER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,CRYPT_SERVER_CONTEXT *,CRYPT_SERVER_CONTEXT *,0,std::nullptr_t>>(&v18);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v25);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Throw_CaughtException(retaddr, (void *)0xF0, v13, v14);
    }
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v25);
  }
}

```

## disassembly

```asm
0x18001b72c  mov     [rsp+NumberOfBytesWritten], rcx
0x18001b731  push    rbx
0x18001b732  sub     rsp, 60h
0x18001b736  lea     rbx, SRWLock
0x18001b73d  mov     rcx, rbx; SRWLock
0x18001b740  call    cs:__imp_TryAcquireSRWLockExclusive
0x18001b747  nop     dword ptr [rax+rax+00h]
0x18001b74c  neg     al
0x18001b74e  sbb     rcx, rcx
0x18001b751  and     rcx, rbx
0x18001b754  mov     [rsp+68h+arg_18], rcx
0x18001b75c  jnz     short loc_18001B770
0x18001b75e  lea     rcx, [rsp+68h+arg_18]
0x18001b766  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001b76b  jmp     loc_18001B900
0x18001b770  mov     edx, 270h; uBytes
0x18001b775  xor     ecx, ecx; uFlags
0x18001b777  call    cs:__imp_LocalAlloc
0x18001b77e  nop     dword ptr [rax+rax+00h]
0x18001b783  mov     rbx, rax
0x18001b786  mov     [rsp+68h+var_38], rax
0x18001b78b  mov     rcx, [rsp+68h]; this
0x18001b790  test    rax, rax
0x18001b793  jz      loc_18001B907
0x18001b799  xor     r9d, r9d; unsigned int *
0x18001b79c  xor     r8d, r8d; unsigned __int16 **
0x18001b79f  xor     edx, edx; void *
0x18001b7a1  mov     rcx, rbx; struct CRYPT_SERVER_CONTEXT *
0x18001b7a4  call    ?CPSCreateServerContext@@YAKPEAUCRYPT_SERVER_CONTEXT@@PEAXPEAPEBGPEAK@Z; CPSCreateServerContext(CRYPT_SERVER_CONTEXT *,void *,ushort const * *,ulong *)
0x18001b7a9  mov     rcx, [rsp+68h]; this
0x18001b7ae  test    eax, eax
0x18001b7b0  jnz     loc_18001B911
0x18001b7b6  mov     [rsp+68h+arg_10], 0
0x18001b7c2  lea     rax, [rsp+68h+arg_10]
0x18001b7ca  mov     qword ptr [rsp+68h+lpOverlapped], rax; unsigned int
0x18001b7cf  mov     r8d, 1; int
0x18001b7d5  mov     r9d, r8d; int
0x18001b7d8  xor     edx, edx; void *
0x18001b7da  mov     rcx, rbx; void *
0x18001b7dd  call    ?CPSGetUserStorageArea@@YAKPEAX0HHPEAPEAG@Z; CPSGetUserStorageArea(void *,void *,int,int,ushort * *)
0x18001b7e2  mov     rcx, [rsp+68h]; this
0x18001b7e7  test    eax, eax
0x18001b7e9  jnz     loc_18001B91F
0x18001b7ef  mov     [rsp+68h+hFile], 0FFFFFFFFFFFFFFFFh
0x18001b7f8  lea     rax, [rsp+68h+hFile]
0x18001b7fd  mov     qword ptr [rsp+68h+lpOverlapped], rax; unsigned int
0x18001b802  lea     r9, aDiagnosticLog; "Diagnostic.log"
0x18001b809  mov     r8, [rsp+68h+arg_10]; unsigned __int16 *
0x18001b811  mov     edx, 0C0000000h; unsigned int
0x18001b816  mov     rcx, rbx; void *
0x18001b819  call    ?OpenFileInStorageArea@@YAKPEAXKPEBG1PEAPEAX@Z; OpenFileInStorageArea(void *,ulong,ushort const *,ushort const *,void * *)
0x18001b81e  cmp     eax, 0B7h
0x18001b823  jz      short loc_18001B832
0x18001b825  mov     rcx, [rsp+68h]; this
0x18001b82a  test    eax, eax
0x18001b82c  jnz     loc_18001B92D
0x18001b832  xor     r9d, r9d; dwMoveMethod
0x18001b835  xor     r8d, r8d; lpDistanceToMoveHigh
0x18001b838  xor     edx, edx; lDistanceToMove
0x18001b83a  mov     rcx, [rsp+68h+hFile]; hFile
0x18001b83f  call    cs:__imp_SetFilePointer
0x18001b846  nop     dword ptr [rax+rax+00h]
0x18001b84b  mov     rcx, [rsp+68h+hFile]; hFile
0x18001b850  call    cs:__imp_SetEndOfFile
0x18001b857  nop     dword ptr [rax+rax+00h]
0x18001b85c  mov     dword ptr [rsp+68h+NumberOfBytesWritten], 0
0x18001b864  mov     qword ptr [rsp+68h+lpOverlapped], 0; lpOverlapped
0x18001b86d  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001b872  mov     r8d, 4; nNumberOfBytesToWrite
0x18001b878  lea     rdx, ?s_currentlySupportedVersion@MasterKeyDiagnosticInfo@@0KB; lpBuffer
0x18001b87f  mov     rcx, [rsp+68h+hFile]; hFile
0x18001b884  call    cs:__imp_WriteFile
0x18001b88b  nop     dword ptr [rax+rax+00h]
0x18001b890  mov     rcx, [rsp+68h]; this
0x18001b895  test    eax, eax
0x18001b897  jz      loc_18001B93A
0x18001b89d  mov     rdx, cs:qword_18004C920
0x18001b8a4  lea     rax, [rsp+68h+hFile]
0x18001b8a9  mov     [rsp+68h+var_28], rax
0x18001b8ae  lea     rax, [rsp+68h+NumberOfBytesWritten]
0x18001b8b3  mov     [rsp+68h+var_20], rax
0x18001b8b8  lea     r9, [rsp+68h+var_28]
0x18001b8bd  mov     r8, rdx
0x18001b8c0  mov     rdx, [rdx]
0x18001b8c3  lea     rcx, [rsp+68h+var_18]
0x18001b8c8  call    ??$for_each@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@URecord_v2@MasterKeyDiagnosticInfo@@@std@@@std@@@std@@@std@@@std@@V_lambda_c16354c18a8367b613a24b6278bec278_@@@std@@YA?AV_lambda_c16354c18a8367b613a24b6278bec278_@@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@URecord_v2@MasterKeyDiagnosticInfo@@@std@@@std@@@std@@@std@@@0@0V1@@Z; std::for_each<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>>>>>,_lambda_c16354c18a8367b613a24b6278bec278_>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>>>>>,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<MasterKeyDiagnosticInfo::Record_v2>>>>>,_lambda_c16354c18a8367b613a24b6278bec278_)
0x18001b8cd  nop
0x18001b8ce  lea     rcx, [rsp+68h+hFile]
0x18001b8d3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001b8d8  nop
0x18001b8d9  lea     rcx, [rsp+68h+arg_10]
0x18001b8e1  call    ??1?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>(void)
0x18001b8e6  nop
0x18001b8e7  lea     rcx, [rsp+68h+var_38]
0x18001b8ec  call    ??1?$unique_storage@U?$resource_policy@PEAUCRYPT_SERVER_CONTEXT@@P6AKPEAU1@@Z$1?CPSDeleteServerContext@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<CRYPT_SERVER_CONTEXT *,ulong (*)(CRYPT_SERVER_CONTEXT *),&CPSDeleteServerContext(CRYPT_SERVER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,CRYPT_SERVER_CONTEXT *,CRYPT_SERVER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<CRYPT_SERVER_CONTEXT *,ulong (*)(CRYPT_SERVER_CONTEXT *),&CPSDeleteServerContext(CRYPT_SERVER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,CRYPT_SERVER_CONTEXT *,CRYPT_SERVER_CONTEXT *,0,std::nullptr_t>>(void)
0x18001b8f1  nop
0x18001b8f2  lea     rcx, [rsp+68h+arg_18]
0x18001b8fa  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001b8ff  nop
0x18001b900  add     rsp, 60h
0x18001b904  pop     rbx
0x18001b905  retn
0x18001b907  mov     edx, 0B2h; void *
0x18001b90c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18001b911  mov     r9d, eax; char *
0x18001b914  mov     edx, 0B4h; void *
0x18001b919  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18001b91f  mov     r9d, eax; char *
0x18001b922  mov     edx, 0BDh; void *
0x18001b927  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18001b92d  mov     r9d, eax; char *
0x18001b930  mov     edx, 0C9h; void *
0x18001b935  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18001b93a  mov     edx, 0DCh; void *
0x18001b93f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
