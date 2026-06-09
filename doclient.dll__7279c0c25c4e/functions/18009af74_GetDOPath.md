# GetDOPath

- ea: `0x18009af74`
- end: `0x18009b287`
- name: `GetDOPath`
- size: `787`
- prototype: `__int64 __fastcall(__int64, _BYTE *, const WCHAR *, char)`
- caller_count: `5`
- callee_count: `13`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18009b300`
- `0x18009b368`
- `0x18009b450`
- `0x18009b538`
- `0x18009b880`

## callees

- `0x180008d14`
- `0x18000933c`
- `0x18000cea4`
- `0x18000ef98`
- `0x18001dffc`
- `0x18009adfc`
- `0x18009af74`
- `0x1800a6520`
- `0x1800a979c`
- `0x1800a98f8`
- `0x1800f82f0`
- `0x180108e50`
- `0x180108ed0`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsSameRootW` at `0x18009b104`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsSameRootW` at `0x18009b104`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18009b0e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18009b0e2`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18009b08a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18009b08a`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18009b17e`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18009b1b2`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18009b1d7`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18009b17e`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18009b1b2`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18009b1d7`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18009b0c4`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18009b0c4`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18009b14a`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18009b14a`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall GetDOPath(__int64 a1, _BYTE *a2, const WCHAR *a3, char a4)
{
  __int64 v7; // rax
  LPCWSTR *v8; // rax
  const WCHAR *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  HRESULT v12; // eax
  HRESULT BasicProfileFolderPath; // eax
  int v14; // ebx
  __int64 v15; // rdx
  HRESULT v16; // eax
  HRESULT v17; // eax
  const char *v18; // rcx
  int v19; // eax
  int v21; // [rsp+20h] [rbp-E0h]
  _BYTE v22[32]; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpSrc[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v25; // [rsp+68h] [rbp-98h]
  WCHAR pszPathOut[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Dst[264]; // [rsp+280h] [rbp+180h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4D8h] [rbp+3D8h]

  *(_OWORD *)lpSrc = 0;
  v24 = 0;
  v25 = 7;
  LOWORD(lpSrc[0]) = 0;
  if ( a2 && *a2 )
  {
    v7 = UTF8toWstr(v22, a2, 0);
    std::wstring::operator=(lpSrc, v7);
    std::wstring::~wstring(v22);
  }
  else if ( (int)GetRedirectPath((__int64)lpSrc) < 0 && a4 )
  {
    v24 = 0;
    v8 = lpSrc;
    if ( v25 > 7 )
      v8 = (LPCWSTR *)lpSrc[0];
    *(_WORD *)v8 = 0;
    if ( CGlobalObjects::_pPlatformHost )
      (*(void (__fastcall **)(struct IDOPlatformHost *, LPCWSTR *))(*(_QWORD *)CGlobalObjects::_pPlatformHost + 32LL))(
        CGlobalObjects::_pPlatformHost,
        lpSrc);
  }
  memset(pszPathOut, 0, 0x208u);
  if ( v24 )
  {
    v9 = (const WCHAR *)lpSrc;
    if ( v25 > 7 )
      v9 = lpSrc[0];
    if ( ExpandEnvironmentStringsW(v9, Dst, 0x104u) - 1 > 0x103 )
    {
      v10 = 45;
LABEL_15:
      v11 = 2147942522LL;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\StatePersistence\\win10\\PersistenceLocation.cpp",
        (const char *)v11,
        v21);
      goto LABEL_22;
    }
    v12 = PathCchCanonicalize(pszPathOut, 0x104u, Dst);
    if ( v12 < 0 )
    {
      v11 = (unsigned int)v12;
      v10 = 46;
      goto LABEL_16;
    }
    if ( GetWindowsDirectoryW(Dst, 0x104u) - 1 > 0x102 )
    {
      v10 = 49;
      goto LABEL_15;
    }
    if ( !PathIsSameRootW(pszPathOut, Dst) )
      goto LABEL_31;
  }
LABEL_22:
  if ( !CGlobalObjects::_pPlatformHost
    || (*(int (__fastcall **)(struct IDOPlatformHost *, WCHAR *, __int64))(*(_QWORD *)CGlobalObjects::_pPlatformHost
                                                                         + 64LL))(
         CGlobalObjects::_pPlatformHost,
         pszPathOut,
         260) < 0 )
  {
    BasicProfileFolderPath = GetBasicProfileFolderPath(8, L"S-1-5-20", pszPathOut, 260);
    v14 = BasicProfileFolderPath;
    if ( BasicProfileFolderPath < 0 )
    {
      v15 = 61;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\StatePersistence\\win10\\PersistenceLocation.cpp",
        (const char *)(unsigned int)BasicProfileFolderPath,
        v21);
      goto LABEL_30;
    }
  }
  BasicProfileFolderPath = PathCchAppend(pszPathOut, 0x104u, L"Microsoft\\Windows");
  v14 = BasicProfileFolderPath;
  if ( BasicProfileFolderPath < 0 )
  {
    v15 = 63;
    goto LABEL_26;
  }
  v14 = 0;
LABEL_30:
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\StatePersistence\\win10\\PersistenceLocation.cpp",
      (const char *)(unsigned int)v14,
      v21);
LABEL_31:
  v16 = PathCchAppend(pszPathOut, 0x104u, L"DeliveryOptimization");
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\StatePersistence\\win10\\PersistenceLocation.cpp",
      (const char *)(unsigned int)v16,
      v21);
  if ( a3 )
  {
    v17 = PathCchAppend(pszPathOut, 0x104u, a3);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x79,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\StatePersistence\\win10\\PersistenceLocation.cpp",
        (const char *)(unsigned int)v17,
        v21);
  }
  WstrToUTF8(a1, pszPathOut, 0);
  v18 = (const char *)a1;
  if ( *(_QWORD *)(a1 + 24) > 0xFu )
    v18 = *(const char **)a1;
  v19 = CPath::Create(v18);
  if ( v19 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x7F,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\StatePersistence\\win10\\PersistenceLocation.cpp",
      (const char *)(unsigned int)v19,
      v21);
  std::wstring::~wstring(lpSrc);
  return a1;
}

```

## disassembly

```asm
0x18009af74  push    rbp
0x18009af76  push    rbx
0x18009af77  push    rsi
0x18009af78  push    rdi
0x18009af79  push    r12
0x18009af7b  push    r14
0x18009af7d  push    r15
0x18009af7f  lea     rbp, [rsp-3A0h]
0x18009af87  sub     rsp, 4A0h
0x18009af8e  mov     rax, cs:__security_cookie
0x18009af95  xor     rax, rsp
0x18009af98  mov     [rbp+3D0h+var_40], rax
0x18009af9f  mov     bl, r9b
0x18009afa2  mov     rsi, r8
0x18009afa5  mov     rdi, rcx
0x18009afa8  mov     [rsp+4D0h+var_4A8], rcx
0x18009afad  xor     r14d, r14d
0x18009afb0  xorps   xmm0, xmm0
0x18009afb3  movups  xmmword ptr [rsp+4D0h+lpSrc], xmm0
0x18009afb8  mov     [rsp+4D0h+var_470], r14
0x18009afbd  mov     [rsp+4D0h+var_468], 7
0x18009afc6  mov     word ptr [rsp+4D0h+lpSrc], r14w
0x18009afcc  test    rdx, rdx
0x18009afcf  jz      short loc_18009AFFC
0x18009afd1  cmp     [rdx], r14b
0x18009afd4  jz      short loc_18009AFFC
0x18009afd6  xor     r8d, r8d
0x18009afd9  lea     rcx, [rsp+4D0h+var_4A0]
0x18009afde  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x18009afe3  mov     rdx, rax
0x18009afe6  lea     rcx, [rsp+4D0h+lpSrc]
0x18009afeb  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18009aff0  lea     rcx, [rsp+4D0h+var_4A0]
0x18009aff5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009affa  jmp     short loc_18009B045
0x18009affc  lea     rcx, [rsp+4D0h+lpSrc]
0x18009b001  call    GetRedirectPath
0x18009b006  test    eax, eax
0x18009b008  jns     short loc_18009B045
0x18009b00a  test    bl, bl
0x18009b00c  jz      short loc_18009B045
0x18009b00e  mov     [rsp+4D0h+var_470], r14
0x18009b013  lea     rax, [rsp+4D0h+lpSrc]
0x18009b018  cmp     [rsp+4D0h+var_468], 7
0x18009b01e  cmova   rax, [rsp+4D0h+lpSrc]
0x18009b024  mov     [rax], r14w
0x18009b028  mov     rcx, cs:?_pPlatformHost@CGlobalObjects@@0PEAVIDOPlatformHost@@EA; IDOPlatformHost * CGlobalObjects::_pPlatformHost
0x18009b02f  test    rcx, rcx
0x18009b032  jz      short loc_18009B045
0x18009b034  mov     rax, [rcx]
0x18009b037  lea     rdx, [rsp+4D0h+lpSrc]
0x18009b03c  mov     rax, [rax+20h]
0x18009b040  call    _guard_dispatch_icall
0x18009b045  xor     edx, edx; Val
0x18009b047  mov     r8d, 208h; Size
0x18009b04d  lea     rcx, [rsp+4D0h+pszPathOut]; void *
0x18009b052  call    memset
0x18009b057  lea     r15, aCW1SSrcDeliver_110; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18009b05e  mov     r12d, 104h
0x18009b064  cmp     [rsp+4D0h+var_470], r14
0x18009b069  jz      loc_18009B112
0x18009b06f  lea     rcx, [rsp+4D0h+lpSrc]
0x18009b074  cmp     [rsp+4D0h+var_468], 7
0x18009b07a  cmova   rcx, [rsp+4D0h+lpSrc]; lpSrc
0x18009b080  mov     r8d, r12d; nSize
0x18009b083  lea     rdx, [rbp+3D0h+Dst]; lpDst
0x18009b08a  call    cs:__imp_ExpandEnvironmentStringsW
0x18009b090  dec     eax
0x18009b092  cmp     eax, 103h
0x18009b097  jbe     short loc_18009B0B5
0x18009b099  mov     edx, 2Dh ; '-'; void *
0x18009b09e  mov     r9d, 8007007Ah; char *
0x18009b0a4  mov     rcx, [rbp+3D8h]; this
0x18009b0ab  mov     r8, r15; unsigned int
0x18009b0ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b0b3  jmp     short loc_18009B112
0x18009b0b5  lea     r8, [rbp+3D0h+Dst]; pszPathIn
0x18009b0bc  mov     rdx, r12; cchPathOut
0x18009b0bf  lea     rcx, [rsp+4D0h+pszPathOut]; pszPathOut
0x18009b0c4  call    cs:__imp_PathCchCanonicalize
0x18009b0ca  test    eax, eax
0x18009b0cc  jns     short loc_18009B0D8
0x18009b0ce  mov     r9d, eax
0x18009b0d1  mov     edx, 2Eh ; '.'
0x18009b0d6  jmp     short loc_18009B0A4
0x18009b0d8  mov     edx, r12d; uSize
0x18009b0db  lea     rcx, [rbp+3D0h+Dst]; lpBuffer
0x18009b0e2  call    cs:__imp_GetWindowsDirectoryW
0x18009b0e8  dec     eax
0x18009b0ea  cmp     eax, 102h
0x18009b0ef  jbe     short loc_18009B0F8
0x18009b0f1  mov     edx, 31h ; '1'
0x18009b0f6  jmp     short loc_18009B09E
0x18009b0f8  lea     rdx, [rbp+3D0h+Dst]; pszPath2
0x18009b0ff  lea     rcx, [rsp+4D0h+pszPathOut]; pszPath1
0x18009b104  call    cs:__imp_PathIsSameRootW
0x18009b10a  test    eax, eax
0x18009b10c  jz      loc_18009B1A3
0x18009b112  mov     rcx, cs:?_pPlatformHost@CGlobalObjects@@0PEAVIDOPlatformHost@@EA; IDOPlatformHost * CGlobalObjects::_pPlatformHost
0x18009b119  test    rcx, rcx
0x18009b11c  jz      short loc_18009B136
0x18009b11e  mov     rax, [rcx]
0x18009b121  mov     r8d, r12d
0x18009b124  lea     rdx, [rsp+4D0h+pszPathOut]
0x18009b129  mov     rax, [rax+40h]
0x18009b12d  call    _guard_dispatch_icall
0x18009b132  test    eax, eax
0x18009b134  jns     short loc_18009B16F
0x18009b136  mov     r9, r12
0x18009b139  lea     r8, [rsp+4D0h+pszPathOut]
0x18009b13e  lea     rdx, aS1520; "S-1-5-20"
0x18009b145  mov     ecx, 8
0x18009b14a  call    cs:__imp_GetBasicProfileFolderPath
0x18009b150  mov     ebx, eax
0x18009b152  test    eax, eax
0x18009b154  jns     short loc_18009B16F
0x18009b156  mov     edx, 3Dh ; '='; void *
0x18009b15b  mov     r8, r15; unsigned int
0x18009b15e  mov     r9d, eax; char *
0x18009b161  mov     rcx, [rbp+3D8h]; this
0x18009b168  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b16d  jmp     short loc_18009B194
0x18009b16f  lea     r8, pszMore; "Microsoft\\Windows"
0x18009b176  mov     rdx, r12; cchPath
0x18009b179  lea     rcx, [rsp+4D0h+pszPathOut]; pszPath
0x18009b17e  call    cs:__imp_PathCchAppend
0x18009b184  mov     ebx, eax
0x18009b186  test    eax, eax
0x18009b188  jns     short loc_18009B191
0x18009b18a  mov     edx, 3Fh ; '?'
0x18009b18f  jmp     short loc_18009B15B
0x18009b191  mov     ebx, r14d
0x18009b194  mov     rcx, [rbp+3D8h]; this
0x18009b19b  test    ebx, ebx
0x18009b19d  js      loc_18009B265
0x18009b1a3  lea     r8, aDeliveryoptimi_0; "DeliveryOptimization"
0x18009b1aa  mov     rdx, r12; cchPath
0x18009b1ad  lea     rcx, [rsp+4D0h+pszPathOut]; pszPath
0x18009b1b2  call    cs:__imp_PathCchAppend
0x18009b1b8  mov     rcx, [rbp+3D8h]; this
0x18009b1bf  test    eax, eax
0x18009b1c1  js      loc_18009B276
0x18009b1c7  test    rsi, rsi
0x18009b1ca  jz      short loc_18009B1E8
0x18009b1cc  mov     r8, rsi; pszMore
0x18009b1cf  mov     rdx, r12; cchPath
0x18009b1d2  lea     rcx, [rsp+4D0h+pszPathOut]; pszPath
0x18009b1d7  call    cs:__imp_PathCchAppend
0x18009b1dd  mov     rcx, [rbp+3D8h]; this
0x18009b1e4  test    eax, eax
0x18009b1e6  js      short loc_18009B254
0x18009b1e8  xor     r8d, r8d
0x18009b1eb  lea     rdx, [rsp+4D0h+pszPathOut]
0x18009b1f0  mov     rcx, rdi
0x18009b1f3  call    ?WstrToUTF8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEB_W_K@Z; WstrToUTF8(wchar_t const *,unsigned __int64)
0x18009b1f8  mov     rcx, rdi
0x18009b1fb  cmp     qword ptr [rdi+18h], 0Fh
0x18009b200  jbe     short loc_18009B205
0x18009b202  mov     rcx, [rdi]; char *
0x18009b205  call    ?Create@CPath@@SAJPEBD@Z; CPath::Create(char const *)
0x18009b20a  mov     rcx, [rbp+3D8h]; this
0x18009b211  test    eax, eax
0x18009b213  jns     short loc_18009B226
0x18009b215  mov     r9d, eax; char *
0x18009b218  mov     r8, r15; unsigned int
0x18009b21b  mov     edx, 7Fh; void *
0x18009b220  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009b225  nop
0x18009b226  lea     rcx, [rsp+4D0h+lpSrc]
0x18009b22b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009b230  mov     rax, rdi
0x18009b233  mov     rcx, [rbp+3D0h+var_40]
0x18009b23a  xor     rcx, rsp; StackCookie
0x18009b23d  call    __security_check_cookie
0x18009b242  add     rsp, 4A0h
0x18009b249  pop     r15
0x18009b24b  pop     r14
0x18009b24d  pop     r12
0x18009b24f  pop     rdi
0x18009b250  pop     rsi
0x18009b251  pop     rbx
0x18009b252  pop     rbp
0x18009b253  retn
0x18009b254  mov     r9d, eax; char *
0x18009b257  mov     r8, r15; unsigned int
0x18009b25a  mov     edx, 79h ; 'y'; void *
0x18009b25f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009b265  mov     r9d, ebx; char *
0x18009b268  mov     r8, r15; unsigned int
0x18009b26b  mov     edx, 72h ; 'r'; void *
0x18009b270  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009b276  mov     r9d, eax; char *
0x18009b279  mov     r8, r15; unsigned int
0x18009b27c  mov     edx, 76h ; 'v'; void *
0x18009b281  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
