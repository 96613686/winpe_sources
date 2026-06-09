# CSpCluster::_LoadMessagePipe(void)

- ea: `0x18004f544`
- end: `0x18004f84a`
- name: `?_LoadMessagePipe@CSpCluster@@AEAA?AW4_MI_Result@@XZ`
- size: `774`
- prototype: `enum _MI_Result __fastcall(CSpCluster *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18004e634`

## callees

- `0x1800011b0`
- `0x1800015b8`
- `0x180013938`
- `0x18004c038`
- `0x18004f544`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f5b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f5b9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004f5ab`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004f5ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004f63a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004f64d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004f660`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004f63a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004f64d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004f660`

## string_xrefs

- `0x18004f5a4`: `resutils.dll`
- `0x18004f640`: `CreateClusterStorageSpacesSubProvider`
- `0x18004f630`: `CreateClusterStorageSpacesResourceLocator`
- `0x18004f653`: `CreateClusterStorageSpacesClustering`

## pseudocode

```c
enum _MI_Result __fastcall CSpCluster::_LoadMessagePipe(CSpCluster *this, __int64 a2, __int64 a3, __int64 a4)
{
  HMODULE Library; // rax
  HMODULE v6; // rbx
  __int64 v7; // rcx
  DWORD LastError; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  char *v11; // rdx
  FARPROC ProcAddress; // r15
  FARPROC v13; // rdi
  FARPROC v14; // rax
  __int64 (__fastcall *v15)(__int64, char *); // r14
  __int64 v16; // rcx
  const char *v18; // [rsp+40h] [rbp-10h] BYREF
  const char *v19; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v20; // [rsp+A8h] [rbp+58h] BYREF

  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v19 = "CSpCluster::_LoadMessagePipe";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (__int64)&byte_18030186F,
      a3,
      a4,
      &v19);
  }
  v20 = 0;
  Library = LoadLibraryExW(L"resutils.dll", 0, 0x800u);
  v6 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "CreateClusterStorageSpacesResourceLocator");
    v13 = GetProcAddress(v6, "CreateClusterStorageSpacesSubProvider");
    v14 = GetProcAddress(v6, "CreateClusterStorageSpacesClustering");
    v15 = (__int64 (__fastcall *)(__int64, char *))v14;
    if ( ProcAddress && v13 && v14 )
    {
      LastError = ((__int64 (__fastcall *)(__int64 *))ProcAddress)(&v20);
      if ( LastError )
      {
        if ( LastError == 122 )
        {
          if ( (unsigned int)dword_180397B68 <= 3 )
            goto LABEL_36;
          v11 = (char *)&dword_180302114;
          LODWORD(v19) = 401;
        }
        else
        {
          if ( (unsigned int)dword_180397B68 <= 2 )
            goto LABEL_36;
          LODWORD(v19) = 401;
          v11 = (char *)qword_1803049B8;
        }
      }
      else
      {
        CSmRefPtrBase<IFmIfsClient>::Release((char *)this + 176);
        LastError = ((__int64 (__fastcall *)(__int64, char *))v13)(v20, (char *)this + 176);
        if ( LastError )
        {
          if ( LastError == 122 )
          {
            if ( (unsigned int)dword_180397B68 <= 3 )
              goto LABEL_36;
            v11 = (char *)&word_18030206E;
            LODWORD(v19) = 409;
          }
          else
          {
            if ( (unsigned int)dword_180397B68 <= 2 )
              goto LABEL_36;
            LODWORD(v19) = 409;
            v11 = &byte_18030302F;
          }
        }
        else
        {
          CSmRefPtrBase<IFmIfsClient>::Release((char *)this + 168);
          LastError = v15(v20, (char *)this + 168);
          if ( !LastError )
            goto LABEL_36;
          if ( LastError == 122 )
          {
            if ( (unsigned int)dword_180397B68 <= 3 )
              goto LABEL_36;
            v11 = (char *)&dword_180302184;
            LODWORD(v19) = 417;
          }
          else
          {
            if ( (unsigned int)dword_180397B68 <= 2 )
              goto LABEL_36;
            LODWORD(v19) = 417;
            v11 = byte_180301F65;
          }
        }
      }
    }
    else
    {
      LastError = 1168;
      if ( (unsigned int)dword_180397B68 <= 2 )
        goto LABEL_36;
      LODWORD(v19) = 389;
      v11 = &byte_180305397;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError == 122 )
      {
        if ( (unsigned int)dword_180397B68 <= 3 )
          goto LABEL_36;
        v11 = (char *)&dword_1803026AC;
        LODWORD(v19) = 367;
      }
      else
      {
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_36;
        LODWORD(v19) = 367;
        v11 = byte_18030200B;
      }
    }
    else
    {
      v7 = (unsigned int)dword_180397B68;
      if ( (unsigned int)dword_180397B68 <= 4 )
        goto LABEL_36;
      v11 = (char *)&word_1803012B6;
      LODWORD(v19) = 367;
    }
  }
  v18 = "CSpCluster::_LoadMessagePipe";
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
    v7,
    (__int64)v11,
    v9,
    v10,
    &v18);
LABEL_36:
  v16 = v20;
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v19 = "CSpCluster::_LoadMessagePipe";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v16,
      (__int64)qword_180304648,
      v9,
      v10,
      &v19);
  }
  return MI_FROM_WIN32(LastError);
}

```

## disassembly

```asm
0x18004f544  push    rbp
0x18004f546  push    rbx
0x18004f547  push    rsi
0x18004f548  push    rdi
0x18004f549  push    r12
0x18004f54b  push    r14
0x18004f54d  push    r15
0x18004f54f  mov     rbp, rsp
0x18004f552  sub     rsp, 50h
0x18004f556  mov     eax, cs:dword_180397B68
0x18004f55c  lea     r12, aCspclusterLoad; "CSpCluster::_LoadMessagePipe"
0x18004f563  mov     rsi, rcx
0x18004f566  cmp     eax, 5
0x18004f569  jbe     short loc_18004F594
0x18004f56b  lea     rax, [rbp+arg_8]
0x18004f56f  mov     [rbp+arg_8], 15Ch
0x18004f576  mov     [rsp+50h+var_28], rax
0x18004f57b  lea     rdx, byte_18030186F
0x18004f582  lea     rax, [rbp+arg_10]
0x18004f586  mov     [rbp+arg_10], r12
0x18004f58a  mov     [rsp+50h+var_30], rax
0x18004f58f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18004f594  xor     edx, edx; hFile
0x18004f596  mov     [rbp+arg_18], 0
0x18004f59e  mov     r8d, 800h; dwFlags
0x18004f5a4  lea     rcx, aResutilsDll_0; "resutils.dll"
0x18004f5ab  call    cs:__imp_LoadLibraryExW
0x18004f5b1  mov     rbx, rax
0x18004f5b4  test    rax, rax
0x18004f5b7  jnz     short loc_18004F630
0x18004f5b9  call    cs:__imp_GetLastError
0x18004f5bf  mov     ebx, eax
0x18004f5c1  test    eax, eax
0x18004f5c3  jnz     short loc_18004F5EA
0x18004f5c5  mov     ecx, cs:dword_180397B68
0x18004f5cb  cmp     ecx, 4
0x18004f5ce  jbe     loc_18004F7E4
0x18004f5d4  mov     [rbp+arg_8], eax
0x18004f5d7  lea     rdx, word_1803012B6
0x18004f5de  mov     dword ptr [rbp+arg_10], 16Fh
0x18004f5e5  jmp     loc_18004F7C0
0x18004f5ea  mov     eax, cs:dword_180397B68
0x18004f5f0  cmp     ebx, 7Ah ; 'z'
0x18004f5f3  jnz     short loc_18004F614
0x18004f5f5  cmp     eax, 3
0x18004f5f8  jbe     loc_18004F7E4
0x18004f5fe  mov     [rbp+arg_8], ebx
0x18004f601  lea     rdx, dword_1803026AC
0x18004f608  mov     dword ptr [rbp+arg_10], 16Fh
0x18004f60f  jmp     loc_18004F7C0
0x18004f614  cmp     eax, 2
0x18004f617  jbe     loc_18004F7E4
0x18004f61d  mov     dword ptr [rbp+arg_10], 16Fh
0x18004f624  lea     rdx, byte_18030200B
0x18004f62b  jmp     loc_18004F7BD
0x18004f630  lea     rdx, aCreateclusters; "CreateClusterStorageSpacesResourceLocat"...
0x18004f637  mov     rcx, rbx; hModule
0x18004f63a  call    cs:__imp_GetProcAddress
0x18004f640  lea     rdx, aCreateclusters_1; "CreateClusterStorageSpacesSubProvider"
0x18004f647  mov     rcx, rbx; hModule
0x18004f64a  mov     r15, rax
0x18004f64d  call    cs:__imp_GetProcAddress
0x18004f653  lea     rdx, aCreateclusters_0; "CreateClusterStorageSpacesClustering"
0x18004f65a  mov     rcx, rbx; hModule
0x18004f65d  mov     rdi, rax
0x18004f660  call    cs:__imp_GetProcAddress
0x18004f666  mov     r14, rax
0x18004f669  test    r15, r15
0x18004f66c  jz      loc_18004F79F
0x18004f672  test    rdi, rdi
0x18004f675  jz      loc_18004F79F
0x18004f67b  test    rax, rax
0x18004f67e  jz      loc_18004F79F
0x18004f684  lea     rcx, [rbp+arg_18]
0x18004f688  mov     rax, r15
0x18004f68b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f690  mov     ebx, eax
0x18004f692  test    eax, eax
0x18004f694  jz      short loc_18004F6DC
0x18004f696  mov     eax, cs:dword_180397B68
0x18004f69c  cmp     ebx, 7Ah ; 'z'
0x18004f69f  jnz     short loc_18004F6C0
0x18004f6a1  cmp     eax, 3
0x18004f6a4  jbe     loc_18004F7E4
0x18004f6aa  mov     [rbp+arg_8], ebx
0x18004f6ad  lea     rdx, dword_180302114
0x18004f6b4  mov     dword ptr [rbp+arg_10], 191h
0x18004f6bb  jmp     loc_18004F7C0
0x18004f6c0  cmp     eax, 2
0x18004f6c3  jbe     loc_18004F7E4
0x18004f6c9  mov     dword ptr [rbp+arg_10], 191h
0x18004f6d0  lea     rdx, qword_1803049B8
0x18004f6d7  jmp     loc_18004F7BD
0x18004f6dc  lea     rbx, [rsi+0B0h]
0x18004f6e3  mov     rcx, rbx
0x18004f6e6  call    ?Release@?$CSmRefPtrBase@UIFmIfsClient@@@@QEAAXXZ; CSmRefPtrBase<IFmIfsClient>::Release(void)
0x18004f6eb  mov     rcx, [rbp+arg_18]
0x18004f6ef  mov     rdx, rbx
0x18004f6f2  mov     rax, rdi
0x18004f6f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f6fa  mov     ebx, eax
0x18004f6fc  test    eax, eax
0x18004f6fe  jz      short loc_18004F743
0x18004f700  mov     eax, cs:dword_180397B68
0x18004f706  cmp     ebx, 7Ah ; 'z'
0x18004f709  jnz     short loc_18004F72A
0x18004f70b  cmp     eax, 3
0x18004f70e  jbe     loc_18004F7E4
0x18004f714  mov     [rbp+arg_8], ebx
0x18004f717  lea     rdx, word_18030206E
0x18004f71e  mov     dword ptr [rbp+arg_10], 199h
0x18004f725  jmp     loc_18004F7C0
0x18004f72a  cmp     eax, 2
0x18004f72d  jbe     loc_18004F7E4
0x18004f733  mov     dword ptr [rbp+arg_10], 199h
0x18004f73a  lea     rdx, byte_18030302F
0x18004f741  jmp     short loc_18004F7BD
0x18004f743  lea     rbx, [rsi+0A8h]
0x18004f74a  mov     rcx, rbx
0x18004f74d  call    ?Release@?$CSmRefPtrBase@UIFmIfsClient@@@@QEAAXXZ; CSmRefPtrBase<IFmIfsClient>::Release(void)
0x18004f752  mov     rcx, [rbp+arg_18]
0x18004f756  mov     rdx, rbx
0x18004f759  mov     rax, r14
0x18004f75c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f761  mov     ebx, eax
0x18004f763  test    eax, eax
0x18004f765  jz      short loc_18004F7E4
0x18004f767  mov     eax, cs:dword_180397B68
0x18004f76d  cmp     ebx, 7Ah ; 'z'
0x18004f770  jnz     short loc_18004F78A
0x18004f772  cmp     eax, 3
0x18004f775  jbe     short loc_18004F7E4
0x18004f777  mov     [rbp+arg_8], ebx
0x18004f77a  lea     rdx, dword_180302184
0x18004f781  mov     dword ptr [rbp+arg_10], 1A1h
0x18004f788  jmp     short loc_18004F7C0
0x18004f78a  cmp     eax, 2
0x18004f78d  jbe     short loc_18004F7E4
0x18004f78f  mov     dword ptr [rbp+arg_10], 1A1h
0x18004f796  lea     rdx, byte_180301F65
0x18004f79d  jmp     short loc_18004F7BD
0x18004f79f  mov     eax, cs:dword_180397B68
0x18004f7a5  mov     ebx, 490h
0x18004f7aa  cmp     eax, 2
0x18004f7ad  jbe     short loc_18004F7E4
0x18004f7af  mov     dword ptr [rbp+arg_10], 185h
0x18004f7b6  lea     rdx, byte_180305397
0x18004f7bd  mov     [rbp+arg_8], ebx
0x18004f7c0  lea     rax, [rbp+arg_8]
0x18004f7c4  mov     [rbp+var_10], r12
0x18004f7c8  mov     [rsp+50h+var_20], rax
0x18004f7cd  lea     rax, [rbp+arg_10]
0x18004f7d1  mov     [rsp+50h+var_28], rax
0x18004f7d6  lea     rax, [rbp+var_10]
0x18004f7da  mov     [rsp+50h+var_30], rax
0x18004f7df  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004f7e4  mov     rcx, [rbp+arg_18]
0x18004f7e8  test    rcx, rcx
0x18004f7eb  jz      short loc_18004F801
0x18004f7ed  mov     rax, [rcx]
0x18004f7f0  mov     rax, [rax+10h]
0x18004f7f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f7f9  mov     [rbp+arg_18], 0
0x18004f801  mov     eax, cs:dword_180397B68
0x18004f807  cmp     eax, 5
0x18004f80a  jbe     short loc_18004F835
0x18004f80c  lea     rax, [rbp+arg_8]
0x18004f810  mov     [rbp+arg_8], 1A9h
0x18004f817  mov     [rsp+50h+var_28], rax
0x18004f81c  lea     rdx, qword_180304648
0x18004f823  lea     rax, [rbp+arg_10]
0x18004f827  mov     [rbp+arg_10], r12
0x18004f82b  mov     [rsp+50h+var_30], rax
0x18004f830  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18004f835  mov     ecx, ebx; unsigned int
0x18004f837  add     rsp, 50h
0x18004f83b  pop     r15
0x18004f83d  pop     r14
0x18004f83f  pop     r12
0x18004f841  pop     rdi
0x18004f842  pop     rsi
0x18004f843  pop     rbx
0x18004f844  pop     rbp
0x18004f845  jmp     ?MI_FROM_WIN32@@YA?AW4_MI_Result@@K@Z; MI_FROM_WIN32(ulong)
```
