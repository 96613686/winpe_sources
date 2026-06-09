# shared::GetLogonSessionSidFromToken(void *)

- ea: `0x180094c90`
- end: `0x1800952d9`
- name: `?GetLogonSessionSidFromToken@shared@@YA?AV?$vector@EV?$allocator@E@std@@@std@@PEAX@Z`
- size: `1609`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180041b5c`
- `0x18020e290`

## callees

- `0x18000d02c`
- `0x18000d350`
- `0x18000f8d0`
- `0x180010ee0`
- `0x1800113bc`
- `0x180030190`
- `0x18007e71c`
- `0x180094c90`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800956d0`
- `0x180095a00`
- `0x180095a34`
- `0x1800969c8`
- `0x180098480`
- `0x1800e845c`
- `0x180143248`
- `0x18018ca48`
- `0x1801f6fb0`
- `0x1801f780e`
- `0x1801f7974`
- `0x1801fc4d4`
- `0x1801fcb36`
- `0x1801fcb5a`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180094ecd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180094f5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009503f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180095200`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180094ecd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180094f5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009503f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180095200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094d04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094eaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800951d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094d04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094eaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800951d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180094d21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180094d21`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180094d30`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180094d30`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180094cfc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180094d5e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180094cfc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180094d5e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180094db3`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180094db3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180094d97`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180094d97`

## string_xrefs

- `0x180094ef8`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180094f85`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180095062`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18009522b`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall shared::GetLogonSessionSidFromToken(_QWORD *a1, void *a2)
{
  BOOL TokenInformation; // ebx
  signed int LastError; // eax
  unsigned int v6; // edi
  DWORD v7; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int *v9; // r15
  unsigned int i; // ecx
  __int64 v11; // rbx
  DWORD LengthSid; // eax
  unsigned __int64 v13; // rdi
  size_t v14; // r14
  char *v15; // rcx
  __int64 v16; // rbx
  unsigned __int64 v17; // r12
  size_t v18; // r13
  __int64 v19; // rdi
  char *v20; // rbx
  char *v21; // rbx
  unsigned __int64 v22; // rdx
  size_t v23; // rdi
  void *v24; // rcx
  void *v25; // rdx
  int v27; // ecx
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rax
  int v32; // ecx
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rax
  char *v37; // rax
  unsigned __int64 v38; // rcx
  __int64 v39; // rdi
  char *v40; // rbx
  _BYTE *v41; // rdx
  DWORD CurrentThreadId; // eax
  ConnectedDevices::Exception::StackFrame *v43; // rbx
  const struct ConnectedDevices::Exception::StackFrame *v44; // rsi
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 v48; // rdx
  ConnectedDevices::Exception::StackFrame *v49; // rcx
  ConnectedDevices::Exception::StackFrame *v50; // rax
  signed int v51; // eax
  unsigned int v52; // ebx
  int v53; // ecx
  __int64 v54; // rax
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // rax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  ConnectedDevices::Exception::StackFrame **v59; // [rsp+38h] [rbp-C8h] BYREF
  int v60; // [rsp+40h] [rbp-C0h]
  const char *v61; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v62[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v63; // [rsp+60h] [rbp-A0h] BYREF
  void **pExceptionObject; // [rsp+68h] [rbp-98h] BYREF
  __int128 v65; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v66; // [rsp+80h] [rbp-80h]
  ConnectedDevices::Exception::StackFrame *v67; // [rsp+88h] [rbp-78h]
  ConnectedDevices::Exception::StackFrame *v68; // [rsp+90h] [rbp-70h]
  __int64 v69; // [rsp+98h] [rbp-68h]
  _QWORD *v70; // [rsp+A0h] [rbp-60h]
  unsigned int *v71; // [rsp+A8h] [rbp-58h]
  ConnectedDevices::Exception::StackFrame *v72[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v73; // [rsp+C0h] [rbp-40h]
  _BYTE v74[32]; // [rsp+D0h] [rbp-30h] BYREF
  int v75; // [rsp+F0h] [rbp-10h]
  __int128 v76; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v77; // [rsp+108h] [rbp+8h]
  __int64 v78; // [rsp+110h] [rbp+10h]
  char v79; // [rsp+118h] [rbp+18h] BYREF
  _BYTE pDestinationSid[80]; // [rsp+120h] [rbp+20h] BYREF

  v70 = a1;
  TokenInformationLength = 0;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v60 = 1;
  TokenInformation = GetTokenInformation(a2, TokenGroups, 0, 0, &TokenInformationLength);
  LastError = GetLastError();
  v6 = LastError;
  if ( TokenInformation || LastError != 122 )
  {
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    CurrentThreadId = GetCurrentThreadId();
    cdp::detail::StringFormat(
      v72,
      "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      v6,
      ".\\platformshared.cpp",
      562,
      CurrentThreadId);
    v60 = 3;
    shared::LogMessage(1, v72);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v72);
    std::string::string(v74, ".\\platformshared.cpp");
    v75 = 562;
    v76 = 0;
    v77 = 0;
    v78 = 0;
    std::string::_Construct<1,char const *>(&v76, qword_1803986E0, 0);
    *(_OWORD *)v72 = 0;
    v73 = 0;
    std::vector<ConnectedDevices::Exception::StackFrame>::_Buy_nonzero(v72, 1);
    v59 = v72;
    v43 = v72[0];
    v44 = (const struct ConnectedDevices::Exception::StackFrame *)v74;
    v61 = (const char *)v72[0];
    v62[0] = v72[0];
    v62[1] = v72;
    do
    {
      ConnectedDevices::Exception::StackFrame::StackFrame(v43, v44);
      v43 = (ConnectedDevices::Exception::StackFrame *)((char *)v43 + 72);
      v62[0] = v43;
      v44 = (const struct ConnectedDevices::Exception::StackFrame *)((char *)v44 + 72);
    }
    while ( v44 != (const struct ConnectedDevices::Exception::StackFrame *)&v79 );
    std::_Destroy_range<std::allocator<ConnectedDevices::Exception::StackFrame>>(v43);
    v72[1] = v43;
    v59 = 0;
    std::_Tidy_guard<std::vector<ConnectedDevices::Exception::StackFrame>>::~_Tidy_guard<std::vector<ConnectedDevices::Exception::StackFrame>>(&v59);
    v60 = 7;
    `eh vector destructor iterator'(
      v74,
      0x48u,
      1u,
      (void (*)(void *))ConnectedDevices::Exception::StackFrame::~StackFrame);
    pExceptionObject = &std::exception::`vftable';
    v65 = 0;
    v61 = (const char *)cdp::ErrorCodeToString(v6, v45, v46, v47);
    LOBYTE(v62[0]) = 1;
    o___std_exception_copy_0(&v61, &v65);
    pExceptionObject = &ConnectedDevices::Exception::`vftable';
    v66 = v6;
    v48 = v73;
    v73 = 0;
    v49 = v72[1];
    v72[1] = 0;
    v50 = v72[0];
    v72[0] = 0;
    v67 = v50;
    v68 = v49;
    v69 = v48;
    throw (ConnectedDevices::Exception *)&pExceptionObject;
  }
  v7 = TokenInformationLength;
  ProcessHeap = GetProcessHeap();
  v9 = (unsigned int *)HeapAlloc(ProcessHeap, v6 - 114, v7);
  v71 = v9;
  if ( !v9 )
  {
    v61 = ".\\platformshared.cpp";
    LODWORD(v62[0]) = 557;
    LODWORD(v59) = -2147024882;
    v63 = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v32,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v59,
      (unsigned int)&v61,
      (__int64)v62,
      (__int64)&v63);
    v33 = cdp::ExceptionStackFromSourceLocationInfo(v72, &v61);
    v36 = cdp::ErrorCodeToString(2147942414LL, v34, v35, v33);
    ConnectedDevices::Exception::Exception(&pExceptionObject, 2147942414LL, v36);
    throw (ConnectedDevices::Exception *)&pExceptionObject;
  }
  if ( !GetTokenInformation(
          a2,
          (TOKEN_INFORMATION_CLASS)(v6 - 120),
          v9,
          TokenInformationLength,
          &TokenInformationLength) )
  {
    v51 = GetLastError();
    v52 = v51;
    if ( v51 > 0 )
      v52 = (unsigned __int16)v51 | 0x80070000;
    v61 = ".\\platformshared.cpp";
    LODWORD(v62[0]) = 552;
    LODWORD(v59) = v52;
    v63 = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v53,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v59,
      (unsigned int)&v61,
      (__int64)v62,
      (__int64)&v63);
    v54 = cdp::ExceptionStackFromSourceLocationInfo(v72, &v61);
    v57 = cdp::ErrorCodeToString(v52, v55, v56, v54);
    ConnectedDevices::Exception::Exception(&pExceptionObject, v52, v57);
    throw (ConnectedDevices::Exception *)&pExceptionObject;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= *v9 )
      goto LABEL_20;
    v11 = 2LL * i;
    if ( (v9[4 * i + 4] & 0xC0000000) == 0xC0000000 )
      break;
  }
  LengthSid = GetLengthSid(*(PSID *)&v9[4 * i + 2]);
  v13 = LengthSid;
  if ( LengthSid > 0x44 )
  {
LABEL_20:
    v61 = ".\\platformshared.cpp";
    LODWORD(v62[0]) = 545;
    LODWORD(v59) = -2147221243;
    v63 = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v27,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v59,
      (unsigned int)&v61,
      (__int64)v62,
      (__int64)&v63);
    v28 = cdp::ExceptionStackFromSourceLocationInfo(v72, &v61);
    v31 = cdp::ErrorCodeToString(2147746053LL, v29, v30, v28);
    ConnectedDevices::Exception::Exception(&pExceptionObject, 2147746053LL, v31);
    throw (ConnectedDevices::Exception *)&pExceptionObject;
  }
  if ( !CopySid(LengthSid, pDestinationSid, *(PSID *)&v9[2 * v11 + 2]) )
  {
    GetLastError();
    goto LABEL_20;
  }
  v14 = (unsigned int)v13;
  v15 = (char *)*a1;
  v16 = a1[1];
  v17 = v16 - *a1;
  if ( v13 < v17 )
  {
    v37 = &v15[v13];
  }
  else
  {
    if ( v13 <= v17 )
      goto LABEL_15;
    v18 = (unsigned int)v13 - v17;
    if ( v13 > a1[2] - (_QWORD)v15 )
    {
      v19 = std::vector<unsigned char>::_Calculate_growth(a1, (unsigned int)v13);
      v20 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(v19);
      memset_0(&v20[v17], 0, v18);
      memmove_0(v20, (const void *)*a1, a1[1] - *a1);
      std::vector<unsigned char>::_Change_array(a1, v20, (unsigned int)v14, v19);
      goto LABEL_15;
    }
    memset_0((void *)a1[1], 0, (unsigned int)v13 - v17);
    v37 = (char *)(v16 + v18);
  }
  a1[1] = v37;
LABEL_15:
  v21 = (char *)*a1;
  v22 = a1[2] - *a1;
  if ( v14 > v22 )
  {
    v38 = v22 >> 1;
    v39 = 0x7FFFFFFFFFFFFFFFLL;
    if ( v22 <= 0x7FFFFFFFFFFFFFFFLL - (v22 >> 1) )
    {
      v39 = v38 + v22;
      if ( v38 + v22 < v14 )
        v39 = v14;
    }
    if ( v21 )
    {
      std::_Deallocate<16>(*a1, v22);
      *a1 = 0;
      a1[1] = 0;
      a1[2] = 0;
    }
    v40 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(v39);
    *a1 = v40;
    a1[2] = &v40[v39];
    v41 = pDestinationSid;
    goto LABEL_30;
  }
  v23 = a1[1] - (_QWORD)v21;
  v24 = (void *)*a1;
  if ( v14 > v23 )
  {
    memmove_0(v24, pDestinationSid, a1[1] - (_QWORD)v21);
    v40 = (char *)a1[1];
    v14 -= v23;
    v41 = &pDestinationSid[v23];
LABEL_30:
    memmove_0(v40, v41, v14);
    a1[1] = &v40[v14];
    goto LABEL_18;
  }
  memmove_0(v24, pDestinationSid, v14);
  a1[1] = &v21[v14];
LABEL_18:
  wil::details::FreeProcessHeap((wil::details *)v9, v25);
  return a1;
}

```

## disassembly

```asm
0x180094c90  mov     [rsp-8+arg_10], rbx
0x180094c95  push    rbp
0x180094c96  push    rsi
0x180094c97  push    rdi
0x180094c98  push    r12
0x180094c9a  push    r13
0x180094c9c  push    r14
0x180094c9e  push    r15
0x180094ca0  lea     rbp, [rsp-80h]
0x180094ca5  sub     rsp, 180h
0x180094cac  mov     rax, cs:__security_cookie
0x180094cb3  xor     rax, rsp
0x180094cb6  mov     [rbp+0B0h+var_40], rax
0x180094cba  mov     r14, rdx
0x180094cbd  mov     rsi, rcx
0x180094cc0  mov     [rbp+0B0h+var_110], rcx
0x180094cc4  xor     r13d, r13d
0x180094cc7  mov     [rsp+1B0h+var_170], r13d
0x180094ccc  mov     [rsp+1B0h+TokenInformationLength], r13d
0x180094cd1  mov     [rcx], r13
0x180094cd4  mov     [rcx+8], r13
0x180094cd8  mov     [rcx+10h], r13
0x180094cdc  lea     r12d, [r13+1]
0x180094ce0  mov     [rsp+1B0h+var_170], r12d
0x180094ce5  lea     rax, [rsp+1B0h+TokenInformationLength]
0x180094cea  mov     [rsp+1B0h+ReturnLength], rax; ReturnLength
0x180094cef  xor     r9d, r9d; TokenInformationLength
0x180094cf2  xor     r8d, r8d; TokenInformation
0x180094cf5  lea     edx, [r13+2]; TokenInformationClass
0x180094cf9  mov     rcx, r14; TokenHandle
0x180094cfc  call    cs:__imp_GetTokenInformation
0x180094d02  mov     ebx, eax
0x180094d04  call    cs:__imp_GetLastError
0x180094d0a  mov     edi, eax
0x180094d0c  test    ebx, ebx
0x180094d0e  jnz     loc_180095037
0x180094d14  cmp     eax, 7Ah ; 'z'
0x180094d17  jnz     loc_180095037
0x180094d1d  mov     ebx, [rsp+1B0h+TokenInformationLength]
0x180094d21  call    cs:__imp_GetProcessHeap
0x180094d27  mov     r8d, ebx; dwBytes
0x180094d2a  lea     edx, [rdi-72h]; dwFlags
0x180094d2d  mov     rcx, rax; hHeap
0x180094d30  call    cs:__imp_HeapAlloc
0x180094d36  mov     r15, rax
0x180094d39  mov     [rbp+0B0h+var_108], rax
0x180094d3d  test    rax, rax
0x180094d40  jz      loc_180094F3D
0x180094d46  lea     rax, [rsp+1B0h+TokenInformationLength]
0x180094d4b  mov     [rsp+1B0h+ReturnLength], rax; ReturnLength
0x180094d50  mov     r9d, [rsp+1B0h+TokenInformationLength]; TokenInformationLength
0x180094d55  mov     r8, r15; TokenInformation
0x180094d58  lea     edx, [rdi-78h]; TokenInformationClass
0x180094d5b  mov     rcx, r14; TokenHandle
0x180094d5e  call    cs:__imp_GetTokenInformation
0x180094d64  test    eax, eax
0x180094d66  jz      loc_1800951D8
0x180094d6c  mov     ecx, r13d
0x180094d6f  mov     edx, 0C0000000h
0x180094d74  cmp     ecx, [r15]
0x180094d77  jnb     loc_180094EB0
0x180094d7d  mov     ebx, ecx
0x180094d7f  add     rbx, rbx
0x180094d82  mov     eax, [r15+rbx*8+10h]
0x180094d87  and     eax, edx
0x180094d89  cmp     eax, edx
0x180094d8b  jz      short loc_180094D92
0x180094d8d  add     ecx, r12d
0x180094d90  jmp     short loc_180094D74
0x180094d92  mov     rcx, [r15+rbx*8+8]; pSid
0x180094d97  call    cs:__imp_GetLengthSid
0x180094d9d  mov     edi, eax
0x180094d9f  cmp     eax, 44h ; 'D'
0x180094da2  ja      loc_180094EB0
0x180094da8  mov     r8, [r15+rbx*8+8]; pSourceSid
0x180094dad  lea     rdx, [rbp+0B0h+pDestinationSid]; pDestinationSid
0x180094db1  mov     ecx, edi; nDestinationSidLength
0x180094db3  call    cs:__imp_CopySid
0x180094db9  test    eax, eax
0x180094dbb  jz      loc_180094EAA
0x180094dc1  mov     r14d, edi
0x180094dc4  mov     rcx, [rsi]
0x180094dc7  mov     rbx, [rsi+8]
0x180094dcb  mov     r12, rbx
0x180094dce  sub     r12, rcx
0x180094dd1  cmp     rdi, r12
0x180094dd4  jb      loc_180094FCA
0x180094dda  jbe     short loc_180094E3E
0x180094ddc  mov     r13d, edi
0x180094ddf  sub     r13, r12
0x180094de2  mov     rax, [rsi+10h]
0x180094de6  sub     rax, rcx
0x180094de9  cmp     rdi, rax
0x180094dec  jbe     loc_180095270
0x180094df2  mov     edx, edi
0x180094df4  mov     rcx, rsi
0x180094df7  call    ?_Calculate_growth@?$vector@EV?$allocator@E@std@@@std@@AEBA_K_K@Z; std::vector<uchar>::_Calculate_growth(unsigned __int64)
0x180094dfc  mov     rdi, rax
0x180094dff  mov     rcx, rax
0x180094e02  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180094e07  mov     rbx, rax
0x180094e0a  lea     rcx, [r12+rax]; void *
0x180094e0e  mov     r8, r13; Size
0x180094e11  xor     edx, edx; Val
0x180094e13  call    memset_0
0x180094e18  mov     r8, [rsi+8]
0x180094e1c  sub     r8, [rsi]; Size
0x180094e1f  mov     rdx, [rsi]; Src
0x180094e22  mov     rcx, rbx; void *
0x180094e25  call    memmove_0
0x180094e2a  mov     r9, rdi
0x180094e2d  mov     r8d, r14d
0x180094e30  mov     rdx, rbx
0x180094e33  mov     rcx, rsi
0x180094e36  call    ?_Change_array@?$vector@EV?$allocator@E@std@@@std@@AEAAXQEAE_K1@Z; std::vector<uchar>::_Change_array(uchar * const,unsigned __int64,unsigned __int64)
0x180094e3b  xor     r13d, r13d
0x180094e3e  mov     rbx, [rsi]
0x180094e41  mov     rdx, [rsi+10h]
0x180094e45  sub     rdx, rbx
0x180094e48  cmp     r14, rdx
0x180094e4b  ja      loc_180094FD7
0x180094e51  mov     rdi, [rsi+8]
0x180094e55  sub     rdi, rbx
0x180094e58  lea     rdx, [rbp+0B0h+pDestinationSid]; Src
0x180094e5c  mov     rcx, rbx; void *
0x180094e5f  cmp     r14, rdi
0x180094e62  ja      loc_1800952A1
0x180094e68  mov     r8, r14; Size
0x180094e6b  call    memmove_0
0x180094e70  lea     rcx, [r14+rbx]
0x180094e74  mov     [rsi+8], rcx
0x180094e78  mov     rcx, r15; this
0x180094e7b  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180094e80  mov     rax, rsi
0x180094e83  mov     rcx, [rbp+0B0h+var_40]
0x180094e87  xor     rcx, rsp; StackCookie
0x180094e8a  call    __security_check_cookie
0x180094e8f  mov     rbx, [rsp+1B0h+arg_10]
0x180094e97  add     rsp, 180h
0x180094e9e  pop     r15
0x180094ea0  pop     r14
0x180094ea2  pop     r13
0x180094ea4  pop     r12
0x180094ea6  pop     rdi
0x180094ea7  pop     rsi
0x180094ea8  pop     rbp
0x180094ea9  retn
0x180094eaa  call    cs:__imp_GetLastError
0x180094eb0  lea     rsi, aPlatformshared; ".\\platformshared.cpp"
0x180094eb7  mov     [rsp+1B0h+var_168], rsi
0x180094ebc  mov     dword ptr [rsp+1B0h+var_160], 221h
0x180094ec4  mov     ebx, 80040105h
0x180094ec9  mov     dword ptr [rsp+1B0h+var_178], ebx
0x180094ecd  call    cs:__imp_GetCurrentThreadId
0x180094ed3  mov     eax, eax
0x180094ed5  mov     [rsp+1B0h+var_150], rax
0x180094eda  lea     rax, [rsp+1B0h+var_150]
0x180094edf  mov     [rsp+1B0h+var_188], rax
0x180094ee4  lea     rax, [rsp+1B0h+var_160]
0x180094ee9  mov     [rsp+1B0h+ReturnLength], rax
0x180094eee  lea     r9, [rsp+1B0h+var_168]
0x180094ef3  lea     r8, [rsp+1B0h+var_178]
0x180094ef8  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180094eff  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180094f04  lea     rdx, [rsp+1B0h+var_168]
0x180094f09  lea     rcx, [rbp+0B0h+var_100]
0x180094f0d  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180094f12  mov     r9, rax
0x180094f15  mov     ecx, ebx
0x180094f17  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180094f1c  mov     r8, rax
0x180094f1f  mov     edx, ebx
0x180094f21  lea     rcx, [rsp+1B0h+pExceptionObject]
0x180094f26  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180094f2b  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180094f32  lea     rcx, [rsp+1B0h+pExceptionObject]; pExceptionObject
0x180094f37  call    _CxxThrowException_0
0x180094f3d  lea     rsi, aPlatformshared; ".\\platformshared.cpp"
0x180094f44  mov     [rsp+1B0h+var_168], rsi
0x180094f49  mov     dword ptr [rsp+1B0h+var_160], 22Dh
0x180094f51  mov     ebx, 8007000Eh
0x180094f56  mov     dword ptr [rsp+1B0h+var_178], ebx
0x180094f5a  call    cs:__imp_GetCurrentThreadId
0x180094f60  mov     eax, eax
0x180094f62  mov     [rsp+1B0h+var_150], rax
0x180094f67  lea     rax, [rsp+1B0h+var_150]
0x180094f6c  mov     [rsp+1B0h+var_188], rax
0x180094f71  lea     rax, [rsp+1B0h+var_160]
0x180094f76  mov     [rsp+1B0h+ReturnLength], rax
0x180094f7b  lea     r9, [rsp+1B0h+var_168]
0x180094f80  lea     r8, [rsp+1B0h+var_178]
0x180094f85  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180094f8c  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180094f91  lea     rdx, [rsp+1B0h+var_168]
0x180094f96  lea     rcx, [rbp+0B0h+var_100]
0x180094f9a  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180094f9f  mov     r9, rax
0x180094fa2  mov     ecx, ebx
0x180094fa4  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180094fa9  mov     r8, rax
0x180094fac  mov     edx, ebx
0x180094fae  lea     rcx, [rsp+1B0h+pExceptionObject]
0x180094fb3  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180094fb8  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180094fbf  lea     rcx, [rsp+1B0h+pExceptionObject]; pExceptionObject
0x180094fc4  call    _CxxThrowException_0
0x180094fca  lea     rax, [rdi+rcx]
0x180094fce  mov     [rsi+8], rax
0x180094fd2  jmp     loc_180094E3E
0x180094fd7  mov     rcx, rdx
0x180094fda  shr     rcx, 1
0x180094fdd  mov     rdi, 7FFFFFFFFFFFFFFFh
0x180094fe7  mov     rax, rdi
0x180094fea  sub     rax, rcx
0x180094fed  cmp     rdx, rax
0x180094ff0  ja      short loc_180094FFD
0x180094ff2  lea     rdi, [rcx+rdx]
0x180094ff6  cmp     rdi, r14
0x180094ff9  cmovb   rdi, r14
0x180094ffd  test    rbx, rbx
0x180095000  jnz     loc_180095289
0x180095006  mov     rcx, rdi
0x180095009  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18009500e  mov     rbx, rax
0x180095011  mov     [rsi], rax
0x180095014  add     rax, rdi
0x180095017  mov     [rsi+10h], rax
0x18009501b  lea     rdx, [rbp+0B0h+pDestinationSid]; Src
0x18009501f  mov     r8, r14; Size
0x180095022  mov     rcx, rbx; void *
0x180095025  call    memmove_0
0x18009502a  lea     rax, [r14+rbx]
0x18009502e  mov     [rsi+8], rax
0x180095032  jmp     loc_180094E78
0x180095037  test    eax, eax
0x180095039  jg      loc_1800952CA
0x18009503f  call    cs:__imp_GetCurrentThreadId
0x180095045  mov     eax, eax
0x180095047  mov     [rsp+1B0h+var_188], rax
0x18009504c  mov     ebx, 232h
0x180095051  mov     dword ptr [rsp+1B0h+ReturnLength], ebx
0x180095055  lea     rsi, aPlatformshared; ".\\platformshared.cpp"
0x18009505c  mov     r9, rsi
0x18009505f  mov     r8d, edi
0x180095062  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180095069  lea     rcx, [rbp+0B0h+var_100]
0x18009506d  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x180095072  mov     [rsp+1B0h+var_170], 3
0x18009507a  lea     rdx, [rbp+0B0h+var_100]
0x18009507e  mov     ecx, r12d
0x180095081  call    ?LogMessage@shared@@YAXW4CDPLogLevel@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; shared::LogMessage(CDPLogLevel,std::string &)
0x180095086  nop
0x180095087  lea     rcx, [rbp+0B0h+var_100]; void *
0x18009508b  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180095090  nop
0x180095091  mov     rdx, rsi
0x180095094  lea     rcx, [rbp+0B0h+var_E0]
0x180095098  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18009509d  nop
0x18009509e  mov     [rbp+0B0h+var_C0], ebx
0x1800950a1  xorps   xmm0, xmm0
0x1800950a4  movups  [rbp+0B0h+var_B8], xmm0
0x1800950a8  mov     [rbp+0B0h+var_A8], r13
0x1800950ac  mov     [rbp+0B0h+var_A0], r13
0x1800950b0  xor     r8d, r8d
0x1800950b3  lea     rdx, qword_1803986E0
0x1800950ba  lea     rcx, [rbp+0B0h+var_B8]
0x1800950be  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800950c3  nop
0x1800950c4  xorps   xmm0, xmm0
0x1800950c7  movdqu  xmmword ptr [rbp+0B0h+var_100], xmm0
0x1800950cc  mov     [rbp+0B0h+var_F0], r13
0x1800950d0  mov     rdx, r12
0x1800950d3  lea     rcx, [rbp+0B0h+var_100]
0x1800950d7  call    ?_Buy_nonzero@?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEAAX_K@Z; std::vector<ConnectedDevices::Exception::StackFrame>::_Buy_nonzero(unsigned __int64)
0x1800950dc  lea     rax, [rbp+0B0h+var_100]
0x1800950e0  mov     [rsp+1B0h+var_178], rax
0x1800950e5  mov     rbx, [rbp+0B0h+var_100]
0x1800950e9  lea     rsi, [rbp+0B0h+var_E0]
0x1800950ed  mov     [rsp+1B0h+var_168], rbx
0x1800950f2  mov     [rsp+1B0h+var_160], rbx
0x1800950f7  lea     rax, [rbp+0B0h+var_100]
0x1800950fb  mov     [rsp+1B0h+var_158], rax
0x180095100  mov     rdx, rsi; struct ConnectedDevices::Exception::StackFrame *
0x180095103  mov     rcx, rbx; this
0x180095106  call    ??0StackFrame@Exception@ConnectedDevices@@QEAA@AEBU012@@Z; ConnectedDevices::Exception::StackFrame::StackFrame(ConnectedDevices::Exception::StackFrame const &)
0x18009510b  add     rbx, 48h ; 'H'
0x18009510f  mov     [rsp+1B0h+var_160], rbx
0x180095114  add     rsi, 48h ; 'H'
0x180095118  lea     rax, [rbp+0B0h+var_98]
0x18009511c  cmp     rsi, rax
0x18009511f  jnz     short loc_180095100
0x180095121  mov     rdx, rbx
0x180095124  mov     rcx, rbx; this
0x180095127  call    ??$_Destroy_range@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@YAXPEAUStackFrame@Exception@ConnectedDevices@@QEAU123@AEAV?$allocator@UStackFrame@Exception@ConnectedDevices@@@0@@Z; std::_Destroy_range<std::allocator<ConnectedDevices::Exception::StackFrame>>(ConnectedDevices::Exception::StackFrame *,ConnectedDevices::Exception::StackFrame * const,std::allocator<ConnectedDevices::Exception::StackFrame> &)
0x18009512c  mov     [rbp+0B0h+var_100+8], rbx
0x180095130  mov     [rsp+1B0h+var_178], r13
0x180095135  lea     rcx, [rsp+1B0h+var_178]
0x18009513a  call    ??1?$_Tidy_guard@V?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<ConnectedDevices::Exception::StackFrame>>::~_Tidy_guard<std::vector<ConnectedDevices::Exception::StackFrame>>(void)
0x18009513f  mov     [rsp+1B0h+var_170], 7
  ... truncated ...
```
