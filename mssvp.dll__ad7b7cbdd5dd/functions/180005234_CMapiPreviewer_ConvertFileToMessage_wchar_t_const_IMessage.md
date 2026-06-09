# CMapiPreviewer::ConvertFileToMessage(wchar_t const *,IMessage * *)

- ea: `0x180005234`
- end: `0x1800054f3`
- name: `?ConvertFileToMessage@CMapiPreviewer@@AEAAJPEB_WPEAPEAUIMessage@@@Z`
- size: `703`
- prototype: `__int64 __fastcall(CMapiPreviewer *this, const wchar_t *, LPMESSAGE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025a90`

## callees

- `0x180005210`
- `0x180005234`
- `0x1800054fc`
- `0x180006270`
- `0x180006dcc`
- `0x180007110`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054a2`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800052a3`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800052a3`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800053b6`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800053b6`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800053fd`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800053fd`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageOnILockBytes` at `0x180005423`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageOnILockBytes` at `0x180005423`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x180005346`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x180005346`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x180005328`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x180005328`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageEx` at `0x18000530b`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageEx` at `0x18000530b`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIAllocateBuffer` at `0x180005485`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIAllocateMore` at `0x18000547e`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIFreeBuffer` at `0x180005477`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIGetDefaultMalloc` at `0x180005266`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIGetDefaultMalloc` at `0x180005266`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_OpenIMsgOnIStg` at `0x18000548e`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_OpenIMsgOnIStg` at `0x18000548e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMapiPreviewer::ConvertFileToMessage(CMapiPreviewer *this, const wchar_t *a2, LPMESSAGE *a3)
{
  LPMALLOC v5; // rax
  IMalloc *v6; // rsi
  HRESULT v7; // ebx
  int v8; // ebx
  void *v9; // rdi
  IUnknown *v10; // rdx
  signed int LastError; // eax
  IStream *ppstm; // [rsp+60h] [rbp-A0h] BYREF
  IStorage *ppstgOpen; // [rsp+68h] [rbp-98h] BYREF
  LPLOCKBYTES pplkbyt; // [rsp+70h] [rbp-90h] BYREF
  char *FirstFileW; // [rsp+78h] [rbp-88h] BYREF
  LPMALLOC v17[2]; // [rsp+80h] [rbp-80h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+90h] [rbp-70h] BYREF

  v5 = MAPIGetDefaultMalloc();
  v6 = v5;
  v17[0] = v5;
  if ( v5 )
    ((void (__fastcall *)(LPMALLOC))v5->lpVtbl->AddRef)(v5);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (char *)FindFirstFileW(a2, &FindFileData);
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    ppstgOpen = 0;
    if ( !FindFileData.nFileSizeHigh && FindFileData.nFileSizeLow < 0xF4240 )
    {
      ppstm = 0;
      v7 = StgOpenStorageEx(a2, 0x10000u, 4u, 0, 0, 0, &IID_IStorage, (void **)&ppstm);
      if ( v7 >= 0 )
      {
        pplkbyt = 0;
        v7 = CreateILockBytesOnHGlobal(0, 1, &pplkbyt);
        if ( v7 >= 0 )
        {
          v7 = StgCreateDocfileOnILockBytes(pplkbyt, 0x1012u, 0, &ppstgOpen);
          if ( v7 >= 0 )
            v7 = (*(__int64 (__fastcall **)(IStream *, _QWORD, _QWORD, _QWORD, IStorage *))(*(_QWORD *)ppstm + 56LL))(
                   ppstm,
                   0,
                   0,
                   0,
                   ppstgOpen);
        }
        ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>((__int64 *)&pplkbyt);
      }
      ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>((__int64 *)&ppstm);
      if ( v7 >= 0 )
        goto LABEL_17;
    }
    ppstm = 0;
    v8 = SHCreateStreamOnFileEx(a2, 0x20u, 4u, 0, 0, &ppstm);
    if ( v8 >= 0 )
    {
      v9 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
      pplkbyt = (LPLOCKBYTES)v9;
      if ( v9 )
      {
        v10 = (IUnknown *)ppstm;
        *(_QWORD *)v9 = &CLockBytesOnStream::`vftable';
        *((_QWORD *)v9 + 1) = 0;
        *((_DWORD *)v9 + 4) = 1;
        IUnknown_Set((IUnknown **)v9 + 1, v10);
        v8 = StgOpenStorageOnILockBytes((ILockBytes *)v9, 0, 0x20u, 0, 0, &ppstgOpen);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
      }
      else
      {
        v8 = -2147024882;
      }
    }
    ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>((__int64 *)&ppstm);
    if ( v8 >= 0 )
LABEL_17:
      v8 = OpenIMsgOnIStg(0, MAPIAllocateBuffer, MAPIAllocateMore, MAPIFreeBuffer, v6, 0, ppstgOpen, 0, 0, 0, a3);
    ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>((__int64 *)&ppstgOpen);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&FirstFileW);
  ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>((__int64 *)v17);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180005234  mov     [rsp-8+arg_0], rbx
0x180005239  push    rbp
0x18000523a  push    rsi
0x18000523b  push    rdi
0x18000523c  push    r14
0x18000523e  push    r15
0x180005240  lea     rbp, [rsp-1F0h]
0x180005248  sub     rsp, 2F0h
0x18000524f  mov     rax, cs:__security_cookie
0x180005256  xor     rax, rsp
0x180005259  mov     [rbp+210h+var_30], rax
0x180005260  mov     r14, r8
0x180005263  mov     rdi, rdx
0x180005266  call    cs:__imp_MAPIGetDefaultMalloc
0x18000526c  mov     rsi, rax
0x18000526f  mov     [rbp+210h+var_290], rax
0x180005273  xor     r15d, r15d
0x180005276  test    rax, rax
0x180005279  jz      short loc_18000528B
0x18000527b  mov     rcx, [rax]
0x18000527e  mov     rax, [rcx+8]
0x180005282  mov     rcx, rsi
0x180005285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000528a  nop
0x18000528b  xor     edx, edx; Val
0x18000528d  mov     r8d, 250h; Size
0x180005293  lea     rcx, [rbp+210h+FindFileData]; void *
0x180005297  call    memset_0
0x18000529c  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x1800052a0  mov     rcx, rdi; lpFileName
0x1800052a3  call    cs:__imp_FindFirstFileW
0x1800052a9  mov     [rsp+310h+var_298], rax
0x1800052ae  dec     rax
0x1800052b1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800052b5  ja      loc_1800054A2
0x1800052bb  mov     [rsp+310h+ppstgOpen], r15
0x1800052c0  cmp     [rbp+210h+FindFileData.nFileSizeHigh], r15d
0x1800052c4  jnz     loc_180005394
0x1800052ca  cmp     [rbp+210h+FindFileData.nFileSizeLow], 0F4240h
0x1800052d1  jnb     loc_180005394
0x1800052d7  mov     [rsp+310h+ppstm], r15
0x1800052dc  lea     rax, [rsp+310h+ppstm]
0x1800052e1  mov     [rsp+310h+ppObjectOpen], rax; ppObjectOpen
0x1800052e6  lea     rax, IID_IStorage
0x1800052ed  mov     [rsp+310h+riid], rax; riid
0x1800052f2  mov     [rsp+310h+pSecurityDescriptor], r15; pSecurityDescriptor
0x1800052f7  mov     [rsp+310h+pStgOptions], r15; pStgOptions
0x1800052fc  xor     r9d, r9d; grfAttrs
0x1800052ff  mov     edx, 10000h; grfMode
0x180005304  lea     r8d, [r9+4]; stgfmt
0x180005308  mov     rcx, rdi; pwcsName
0x18000530b  call    cs:__imp_StgOpenStorageEx
0x180005311  mov     ebx, eax
0x180005313  test    eax, eax
0x180005315  js      short loc_180005382
0x180005317  mov     [rsp+310h+pplkbyt], r15
0x18000531c  lea     r8, [rsp+310h+pplkbyt]; pplkbyt
0x180005321  mov     edx, 1; fDeleteOnRelease
0x180005326  xor     ecx, ecx; hGlobal
0x180005328  call    cs:__imp_CreateILockBytesOnHGlobal
0x18000532e  mov     ebx, eax
0x180005330  test    eax, eax
0x180005332  js      short loc_180005377
0x180005334  lea     r9, [rsp+310h+ppstgOpen]; ppstgOpen
0x180005339  xor     r8d, r8d; reserved
0x18000533c  mov     edx, 1012h; grfMode
0x180005341  mov     rcx, [rsp+310h+pplkbyt]; plkbyt
0x180005346  call    cs:__imp_StgCreateDocfileOnILockBytes
0x18000534c  mov     ebx, eax
0x18000534e  test    eax, eax
0x180005350  js      short loc_180005377
0x180005352  mov     rcx, [rsp+310h+ppstm]
0x180005357  mov     rdx, [rsp+310h+ppstgOpen]
0x18000535c  mov     rax, [rcx]
0x18000535f  mov     [rsp+310h+pStgOptions], rdx
0x180005364  xor     r9d, r9d
0x180005367  xor     r8d, r8d
0x18000536a  xor     edx, edx
0x18000536c  mov     rax, [rax+38h]
0x180005370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005375  mov     ebx, eax
0x180005377  lea     rcx, [rsp+310h+pplkbyt]
0x18000537c  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180005381  nop
0x180005382  lea     rcx, [rsp+310h+ppstm]
0x180005387  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18000538c  test    ebx, ebx
0x18000538e  jns     loc_18000544F
0x180005394  mov     [rsp+310h+ppstm], r15
0x180005399  lea     rax, [rsp+310h+ppstm]
0x18000539e  mov     [rsp+310h+pSecurityDescriptor], rax; ppstm
0x1800053a3  mov     [rsp+310h+pStgOptions], r15; pstmTemplate
0x1800053a8  xor     r9d, r9d; fCreate
0x1800053ab  lea     edx, [r9+20h]; grfMode
0x1800053af  lea     r8d, [r9+4]; dwAttributes
0x1800053b3  mov     rcx, rdi; pszFile
0x1800053b6  call    cs:__imp_SHCreateStreamOnFileEx
0x1800053bc  mov     ebx, eax
0x1800053be  test    eax, eax
0x1800053c0  js      short loc_180005441
0x1800053c2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800053c9  mov     ecx, 18h; unsigned __int64
0x1800053ce  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800053d3  mov     rdi, rax
0x1800053d6  mov     [rsp+310h+pplkbyt], rax
0x1800053db  test    rax, rax
0x1800053de  jz      short loc_18000543C
0x1800053e0  mov     rdx, [rsp+310h+ppstm]; punk
0x1800053e5  lea     rax, ??_7CLockBytesOnStream@@6B@; const CLockBytesOnStream::`vftable'
0x1800053ec  mov     [rdi], rax
0x1800053ef  lea     rcx, [rdi+8]; ppunk
0x1800053f3  mov     [rcx], r15
0x1800053f6  mov     dword ptr [rdi+10h], 1
0x1800053fd  call    cs:__imp_IUnknown_Set
0x180005403  test    rdi, rdi
0x180005406  jz      short loc_18000543C
0x180005408  lea     rax, [rsp+310h+ppstgOpen]
0x18000540d  mov     [rsp+310h+pSecurityDescriptor], rax; ppstgOpen
0x180005412  mov     dword ptr [rsp+310h+pStgOptions], r15d; reserved
0x180005417  xor     r9d, r9d; snbExclude
0x18000541a  xor     edx, edx; pstgPriority
0x18000541c  lea     r8d, [r9+20h]; grfMode
0x180005420  mov     rcx, rdi; plkbyt
0x180005423  call    cs:__imp_StgOpenStorageOnILockBytes
0x180005429  mov     ebx, eax
0x18000542b  mov     rax, [rdi]
0x18000542e  mov     rcx, rdi
0x180005431  mov     rax, [rax+10h]
0x180005435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000543a  jmp     short loc_180005441
0x18000543c  mov     ebx, 8007000Eh
0x180005441  lea     rcx, [rsp+310h+ppstm]
0x180005446  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18000544b  test    ebx, ebx
0x18000544d  js      short loc_180005496
0x18000544f  mov     rax, [rsp+310h+ppstgOpen]
0x180005454  mov     [rsp+310h+lppMsg], r14; lppMsg
0x180005459  mov     [rsp+310h+ulFlags], r15d; ulFlags
0x18000545e  mov     [rsp+310h+ulCallerData], r15d; ulCallerData
0x180005463  mov     [rsp+310h+ppObjectOpen], r15; lpfMsgCallRelease
0x180005468  mov     [rsp+310h+riid], rax; lpStg
0x18000546d  mov     [rsp+310h+pSecurityDescriptor], r15; lpMapiSup
0x180005472  mov     [rsp+310h+pStgOptions], rsi; lpMalloc
0x180005477  mov     r9, cs:__imp_MAPIFreeBuffer; lpFreeBuffer
0x18000547e  mov     r8, cs:__imp_MAPIAllocateMore; lpAllocateMore
0x180005485  mov     rdx, cs:__imp_MAPIAllocateBuffer; lpAllocateBuffer
0x18000548c  xor     ecx, ecx; lpMsgSess
0x18000548e  call    cs:__imp_OpenIMsgOnIStg
0x180005494  mov     ebx, eax
0x180005496  lea     rcx, [rsp+310h+ppstgOpen]
0x18000549b  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x1800054a0  jmp     short loc_1800054B7
0x1800054a2  call    cs:__imp_GetLastError
0x1800054a8  mov     ebx, eax
0x1800054aa  test    eax, eax
0x1800054ac  jle     short loc_1800054B7
0x1800054ae  movzx   ebx, ax
0x1800054b1  or      ebx, 80070000h
0x1800054b7  lea     rcx, [rsp+310h+var_298]
0x1800054bc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800054c1  nop
0x1800054c2  lea     rcx, [rbp+210h+var_290]
0x1800054c6  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x1800054cb  mov     eax, ebx
0x1800054cd  mov     rcx, [rbp+210h+var_30]
0x1800054d4  xor     rcx, rsp; StackCookie
0x1800054d7  call    __security_check_cookie
0x1800054dc  mov     rbx, [rsp+310h+arg_0]
0x1800054e4  add     rsp, 2F0h
0x1800054eb  pop     r15
0x1800054ed  pop     r14
0x1800054ef  pop     rdi
0x1800054f0  pop     rsi
0x1800054f1  pop     rbp
0x1800054f2  retn
```
