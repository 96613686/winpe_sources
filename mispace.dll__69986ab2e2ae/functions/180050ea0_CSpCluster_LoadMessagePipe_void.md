# CSpCluster::_LoadMessagePipe(void)

- ea: `0x180050ea0`
- end: `0x1800511c4`
- name: `?_LoadMessagePipe@CSpCluster@@AEAA?AW4_MI_Result@@XZ`
- size: `804`
- prototype: `enum _MI_Result __fastcall(CSpCluster *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18004ff18`

## callees

- `0x1800011c4`
- `0x1800015d8`
- `0x180013bf8`
- `0x18004d7ac`
- `0x180050ea0`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050f1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050f1b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180050f07`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180050f07`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180050fa2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180050fbb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180050fd4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180050fa2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180050fbb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180050fd4`

## string_xrefs

- `0x180050f00`: `resutils.dll`
- `0x180050fae`: `CreateClusterStorageSpacesSubProvider`
- `0x180050f98`: `CreateClusterStorageSpacesResourceLocator`
- `0x180050fc7`: `CreateClusterStorageSpacesClustering`

## pseudocode

```c
enum _MI_Result __fastcall CSpCluster::_LoadMessagePipe(CSpCluster *this, __int64 a2, int a3, int a4)
{
  HMODULE Library; // rax
  HMODULE v6; // rbx
  int v7; // ecx
  DWORD LastError; // ebx
  int v9; // r8d
  int v10; // r9d
  char *v11; // rdx
  FARPROC ProcAddress; // r15
  FARPROC v13; // rdi
  FARPROC v14; // rax
  __int64 (__fastcall *v15)(__int64, char *); // r14
  int v16; // ecx
  const char *v18; // [rsp+40h] [rbp-10h] BYREF
  int v19; // [rsp+98h] [rbp+48h] BYREF
  const char *v20; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v21; // [rsp+A8h] [rbp+58h] BYREF

  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v19 = 348;
    v20 = "CSpCluster::_LoadMessagePipe";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)&byte_1803087F7,
      a3,
      a4,
      (__int64)&v20,
      (__int64)&v19);
  }
  v21 = 0;
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
      LastError = ((__int64 (__fastcall *)(__int64 *))ProcAddress)(&v21);
      if ( LastError )
      {
        if ( LastError == 122 )
        {
          if ( (unsigned int)dword_18039EB68 <= 3 )
            goto LABEL_37;
          v19 = 122;
          v11 = (char *)&dword_18030909C;
          LODWORD(v20) = 401;
          goto LABEL_36;
        }
        if ( (unsigned int)dword_18039EB68 <= 2 )
          goto LABEL_37;
        LODWORD(v20) = 401;
        v11 = (char *)qword_18030B940;
      }
      else
      {
        CSmRefPtrBase<IFmIfsClient>::Release((char *)this + 176);
        LastError = ((__int64 (__fastcall *)(__int64, char *))v13)(v21, (char *)this + 176);
        if ( LastError )
        {
          if ( LastError == 122 )
          {
            if ( (unsigned int)dword_18039EB68 <= 3 )
              goto LABEL_37;
            v19 = 122;
            v11 = (char *)&word_180308FF6;
            LODWORD(v20) = 409;
            goto LABEL_36;
          }
          if ( (unsigned int)dword_18039EB68 <= 2 )
            goto LABEL_37;
          LODWORD(v20) = 409;
          v11 = &byte_180309FB7;
        }
        else
        {
          CSmRefPtrBase<IFmIfsClient>::Release((char *)this + 168);
          LastError = v15(v21, (char *)this + 168);
          if ( !LastError )
            goto LABEL_37;
          if ( LastError == 122 )
          {
            if ( (unsigned int)dword_18039EB68 <= 3 )
              goto LABEL_37;
            v19 = 122;
            v11 = (char *)&dword_18030910C;
            LODWORD(v20) = 417;
            goto LABEL_36;
          }
          if ( (unsigned int)dword_18039EB68 <= 2 )
            goto LABEL_37;
          LODWORD(v20) = 417;
          v11 = byte_180308EED;
        }
      }
    }
    else
    {
      LastError = 1168;
      if ( (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_37;
      LODWORD(v20) = 389;
      v11 = &byte_18030C31F;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( !LastError )
    {
      v7 = dword_18039EB68;
      if ( (unsigned int)dword_18039EB68 <= 4 )
        goto LABEL_37;
      v19 = 0;
      v11 = (char *)&word_18030823E;
      LODWORD(v20) = 367;
      goto LABEL_36;
    }
    if ( LastError == 122 )
    {
      if ( (unsigned int)dword_18039EB68 <= 3 )
        goto LABEL_37;
      v19 = 122;
      v11 = (char *)&dword_180309634;
      LODWORD(v20) = 367;
      goto LABEL_36;
    }
    if ( (unsigned int)dword_18039EB68 <= 2 )
      goto LABEL_37;
    LODWORD(v20) = 367;
    v11 = byte_180308F93;
  }
  v19 = LastError;
LABEL_36:
  v18 = "CSpCluster::_LoadMessagePipe";
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
    v7,
    (_DWORD)v11,
    v9,
    v10,
    (__int64)&v18,
    (__int64)&v20,
    (__int64)&v19);
LABEL_37:
  v16 = v21;
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v19 = 425;
    v20 = "CSpCluster::_LoadMessagePipe";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v16,
      (unsigned int)qword_18030B5D0,
      v9,
      v10,
      (__int64)&v20,
      (__int64)&v19);
  }
  return MI_FROM_WIN32(LastError);
}

```

## disassembly

```asm
0x180050ea0  push    rbp
0x180050ea2  push    rbx
0x180050ea3  push    rsi
0x180050ea4  push    rdi
0x180050ea5  push    r12
0x180050ea7  push    r14
0x180050ea9  push    r15
0x180050eab  mov     rbp, rsp
0x180050eae  sub     rsp, 50h
0x180050eb2  mov     eax, cs:dword_18039EB68
0x180050eb8  lea     r12, aCspclusterLoad; "CSpCluster::_LoadMessagePipe"
0x180050ebf  mov     rsi, rcx
0x180050ec2  cmp     eax, 5
0x180050ec5  jbe     short loc_180050EF0
0x180050ec7  lea     rax, [rbp+arg_8]
0x180050ecb  mov     [rbp+arg_8], 15Ch
0x180050ed2  mov     [rsp+50h+var_28], rax
0x180050ed7  lea     rdx, byte_1803087F7
0x180050ede  lea     rax, [rbp+arg_10]
0x180050ee2  mov     [rbp+arg_10], r12
0x180050ee6  mov     [rsp+50h+var_30], rax
0x180050eeb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180050ef0  xor     edx, edx; hFile
0x180050ef2  mov     [rbp+arg_18], 0
0x180050efa  mov     r8d, 800h; dwFlags
0x180050f00  lea     rcx, aResutilsDll_0; "resutils.dll"
0x180050f07  call    cs:__imp_LoadLibraryExW
0x180050f0e  nop     dword ptr [rax+rax+00h]
0x180050f13  mov     rbx, rax
0x180050f16  test    rax, rax
0x180050f19  jnz     short loc_180050F98
0x180050f1b  call    cs:__imp_GetLastError
0x180050f22  nop     dword ptr [rax+rax+00h]
0x180050f27  mov     ebx, eax
0x180050f29  test    eax, eax
0x180050f2b  jnz     short loc_180050F52
0x180050f2d  mov     ecx, cs:dword_18039EB68
0x180050f33  cmp     ecx, 4
0x180050f36  jbe     loc_18005115E
0x180050f3c  mov     [rbp+arg_8], eax
0x180050f3f  lea     rdx, word_18030823E
0x180050f46  mov     dword ptr [rbp+arg_10], 16Fh
0x180050f4d  jmp     loc_18005113A
0x180050f52  mov     eax, cs:dword_18039EB68
0x180050f58  cmp     ebx, 7Ah ; 'z'
0x180050f5b  jnz     short loc_180050F7C
0x180050f5d  cmp     eax, 3
0x180050f60  jbe     loc_18005115E
0x180050f66  mov     [rbp+arg_8], ebx
0x180050f69  lea     rdx, dword_180309634
0x180050f70  mov     dword ptr [rbp+arg_10], 16Fh
0x180050f77  jmp     loc_18005113A
0x180050f7c  cmp     eax, 2
0x180050f7f  jbe     loc_18005115E
0x180050f85  mov     dword ptr [rbp+arg_10], 16Fh
0x180050f8c  lea     rdx, byte_180308F93
0x180050f93  jmp     loc_180051137
0x180050f98  lea     rdx, aCreateclusters; "CreateClusterStorageSpacesResourceLocat"...
0x180050f9f  mov     rcx, rbx; hModule
0x180050fa2  call    cs:__imp_GetProcAddress
0x180050fa9  nop     dword ptr [rax+rax+00h]
0x180050fae  lea     rdx, aCreateclusters_1; "CreateClusterStorageSpacesSubProvider"
0x180050fb5  mov     rcx, rbx; hModule
0x180050fb8  mov     r15, rax
0x180050fbb  call    cs:__imp_GetProcAddress
0x180050fc2  nop     dword ptr [rax+rax+00h]
0x180050fc7  lea     rdx, aCreateclusters_0; "CreateClusterStorageSpacesClustering"
0x180050fce  mov     rcx, rbx; hModule
0x180050fd1  mov     rdi, rax
0x180050fd4  call    cs:__imp_GetProcAddress
0x180050fdb  nop     dword ptr [rax+rax+00h]
0x180050fe0  mov     r14, rax
0x180050fe3  test    r15, r15
0x180050fe6  jz      loc_180051119
0x180050fec  test    rdi, rdi
0x180050fef  jz      loc_180051119
0x180050ff5  test    rax, rax
0x180050ff8  jz      loc_180051119
0x180050ffe  lea     rcx, [rbp+arg_18]
0x180051002  mov     rax, r15
0x180051005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005100a  mov     ebx, eax
0x18005100c  test    eax, eax
0x18005100e  jz      short loc_180051056
0x180051010  mov     eax, cs:dword_18039EB68
0x180051016  cmp     ebx, 7Ah ; 'z'
0x180051019  jnz     short loc_18005103A
0x18005101b  cmp     eax, 3
0x18005101e  jbe     loc_18005115E
0x180051024  mov     [rbp+arg_8], ebx
0x180051027  lea     rdx, dword_18030909C
0x18005102e  mov     dword ptr [rbp+arg_10], 191h
0x180051035  jmp     loc_18005113A
0x18005103a  cmp     eax, 2
0x18005103d  jbe     loc_18005115E
0x180051043  mov     dword ptr [rbp+arg_10], 191h
0x18005104a  lea     rdx, qword_18030B940
0x180051051  jmp     loc_180051137
0x180051056  lea     rbx, [rsi+0B0h]
0x18005105d  mov     rcx, rbx
0x180051060  call    ?Release@?$CSmRefPtrBase@UIFmIfsClient@@@@QEAAXXZ; CSmRefPtrBase<IFmIfsClient>::Release(void)
0x180051065  mov     rcx, [rbp+arg_18]
0x180051069  mov     rdx, rbx
0x18005106c  mov     rax, rdi
0x18005106f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051074  mov     ebx, eax
0x180051076  test    eax, eax
0x180051078  jz      short loc_1800510BD
0x18005107a  mov     eax, cs:dword_18039EB68
0x180051080  cmp     ebx, 7Ah ; 'z'
0x180051083  jnz     short loc_1800510A4
0x180051085  cmp     eax, 3
0x180051088  jbe     loc_18005115E
0x18005108e  mov     [rbp+arg_8], ebx
0x180051091  lea     rdx, word_180308FF6
0x180051098  mov     dword ptr [rbp+arg_10], 199h
0x18005109f  jmp     loc_18005113A
0x1800510a4  cmp     eax, 2
0x1800510a7  jbe     loc_18005115E
0x1800510ad  mov     dword ptr [rbp+arg_10], 199h
0x1800510b4  lea     rdx, byte_180309FB7
0x1800510bb  jmp     short loc_180051137
0x1800510bd  lea     rbx, [rsi+0A8h]
0x1800510c4  mov     rcx, rbx
0x1800510c7  call    ?Release@?$CSmRefPtrBase@UIFmIfsClient@@@@QEAAXXZ; CSmRefPtrBase<IFmIfsClient>::Release(void)
0x1800510cc  mov     rcx, [rbp+arg_18]
0x1800510d0  mov     rdx, rbx
0x1800510d3  mov     rax, r14
0x1800510d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800510db  mov     ebx, eax
0x1800510dd  test    eax, eax
0x1800510df  jz      short loc_18005115E
0x1800510e1  mov     eax, cs:dword_18039EB68
0x1800510e7  cmp     ebx, 7Ah ; 'z'
0x1800510ea  jnz     short loc_180051104
0x1800510ec  cmp     eax, 3
0x1800510ef  jbe     short loc_18005115E
0x1800510f1  mov     [rbp+arg_8], ebx
0x1800510f4  lea     rdx, dword_18030910C
0x1800510fb  mov     dword ptr [rbp+arg_10], 1A1h
0x180051102  jmp     short loc_18005113A
0x180051104  cmp     eax, 2
0x180051107  jbe     short loc_18005115E
0x180051109  mov     dword ptr [rbp+arg_10], 1A1h
0x180051110  lea     rdx, byte_180308EED
0x180051117  jmp     short loc_180051137
0x180051119  mov     eax, cs:dword_18039EB68
0x18005111f  mov     ebx, 490h
0x180051124  cmp     eax, 2
0x180051127  jbe     short loc_18005115E
0x180051129  mov     dword ptr [rbp+arg_10], 185h
0x180051130  lea     rdx, byte_18030C31F
0x180051137  mov     [rbp+arg_8], ebx
0x18005113a  lea     rax, [rbp+arg_8]
0x18005113e  mov     [rbp+var_10], r12
0x180051142  mov     [rsp+50h+var_20], rax
0x180051147  lea     rax, [rbp+arg_10]
0x18005114b  mov     [rsp+50h+var_28], rax
0x180051150  lea     rax, [rbp+var_10]
0x180051154  mov     [rsp+50h+var_30], rax
0x180051159  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005115e  mov     rcx, [rbp+arg_18]
0x180051162  test    rcx, rcx
0x180051165  jz      short loc_18005117B
0x180051167  mov     rax, [rcx]
0x18005116a  mov     rax, [rax+10h]
0x18005116e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051173  mov     [rbp+arg_18], 0
0x18005117b  mov     eax, cs:dword_18039EB68
0x180051181  cmp     eax, 5
0x180051184  jbe     short loc_1800511AF
0x180051186  lea     rax, [rbp+arg_8]
0x18005118a  mov     [rbp+arg_8], 1A9h
0x180051191  mov     [rsp+50h+var_28], rax
0x180051196  lea     rdx, qword_18030B5D0
0x18005119d  lea     rax, [rbp+arg_10]
0x1800511a1  mov     [rbp+arg_10], r12
0x1800511a5  mov     [rsp+50h+var_30], rax
0x1800511aa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800511af  mov     ecx, ebx; unsigned int
0x1800511b1  add     rsp, 50h
0x1800511b5  pop     r15
0x1800511b7  pop     r14
0x1800511b9  pop     r12
0x1800511bb  pop     rdi
0x1800511bc  pop     rsi
0x1800511bd  pop     rbx
0x1800511be  pop     rbp
0x1800511bf  jmp     ?MI_FROM_WIN32@@YA?AW4_MI_Result@@K@Z; MI_FROM_WIN32(ulong)
```
