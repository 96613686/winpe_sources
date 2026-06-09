# CHttpAgent::_OpenRequest(bool,char const *,DownloadRange const *,unsigned __int64,unsigned __int64)

- ea: `0x1800ccb24`
- end: `0x1800cd13c`
- name: `?_OpenRequest@CHttpAgent@@AEAAJ_NPEBDPEBUDownloadRange@@_K3@Z`
- size: `1560`
- prototype: `__int64 __usercall@<rax>(CHttpAgent *__hidden this@<rcx>, bool@<dl>, const char *@<r8>, const struct DownloadRange *@<r9>, unsigned __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, service_task`

## callers

- `0x1800cb870`
- `0x1800cb8e0`

## callees

- `0x180008d44`
- `0x180009ab4`
- `0x18000cea4`
- `0x18000ef98`
- `0x1800199b4`
- `0x180019c5c`
- `0x18001d5fc`
- `0x18001dffc`
- `0x18001eeac`
- `0x180027188`
- `0x1800a979c`
- `0x1800ae66c`
- `0x1800ae878`
- `0x1800ccb24`
- `0x1800cd144`
- `0x1800cd460`
- `0x1800cec6c`
- `0x1800cf144`
- `0x1800cfdcc`
- `0x1800d010c`
- `0x1800d0318`
- `0x1800d0b80`
- `0x1800f82f0`
- `0x1800f8314`
- `0x1800f8320`
- `0x180107e60`
- `0x180108ed0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ccc62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ccc62`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800ccc4c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800ccc4c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ccef3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ccfb0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cd06c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ccef3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ccfb0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cd06c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ccea8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ccea8`
- `WINHTTP!WinHttpSetTimeouts` at `0x1800ccc36`
- `WINHTTP!WinHttpSetTimeouts` at `0x1800ccc36`

## string_xrefs

- `0x1800cd0f9`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\HttpAgent.cpp`
- `0x1800cd10d`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\HttpAgent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CHttpAgent::_OpenRequest(
        CHttpAgent *this,
        char a2,
        char *a3,
        const struct DownloadRange *a4,
        unsigned __int64 a5,
        unsigned __int64 a6)
{
  unsigned __int64 v10; // r14
  __int128 v11; // rax
  const wchar_t *v12; // rdx
  int v13; // ebx
  const char *v14; // r9
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdx
  void *v18; // rax
  __int64 v19; // rax
  int v20; // eax
  TraceLoggingCorrelationVector *v21; // rcx
  __int64 v22; // rax
  _QWORD *v23; // rsi
  _QWORD *v24; // rbx
  _QWORD *v25; // r14
  void *v26; // rcx
  int v27; // eax
  int v28; // eax
  __int64 result; // rax
  _QWORD *v30; // rax
  _QWORD *v31; // rbx
  size_t v32; // r8
  int nReceiveTimeout; // [rsp+20h] [rbp-218h]
  int nReceiveTimeouta[2]; // [rsp+20h] [rbp-218h]
  _QWORD v36[4]; // [rsp+38h] [rbp-200h] BYREF
  __int64 v37; // [rsp+58h] [rbp-1E0h]
  _OWORD v38[2]; // [rsp+60h] [rbp-1D8h] BYREF
  wchar_t Buffer[48]; // [rsp+80h] [rbp-1B8h] BYREF
  _BYTE v40[32]; // [rsp+E0h] [rbp-158h] BYREF
  _BYTE v41[32]; // [rsp+100h] [rbp-138h] BYREF
  HINTERNET hInternet; // [rsp+120h] [rbp-118h] BYREF
  void *v43; // [rsp+128h] [rbp-110h] BYREF
  char v44; // [rsp+130h] [rbp-108h] BYREF
  __int128 Src; // [rsp+138h] [rbp-100h] BYREF
  __int128 v46; // [rsp+148h] [rbp-F0h]
  char v47[16]; // [rsp+160h] [rbp-D8h] BYREF
  __int128 v48; // [rsp+170h] [rbp-C8h]
  __int128 v49; // [rsp+180h] [rbp-B8h]
  __int128 v50; // [rsp+190h] [rbp-A8h]
  __int128 v51; // [rsp+1A0h] [rbp-98h]
  __int128 v52; // [rsp+1B0h] [rbp-88h]
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  v10 = a6;
  v11 = -(__int128)(unsigned __int64)a3;
  v12 = (const wchar_t *)((unsigned __int64)L"POST" & *((_QWORD *)&v11 + 1));
  if ( a2 && *((_BYTE *)this + 389) )
  {
    v12 = L"HEAD";
    a4 = 0;
  }
  hInternet = 0;
  try
  {
    v13 = CHttpAgent::_CreateRequest(this, v12, &hInternet);
    if ( v13 >= 0 )
    {
      v43 = 0;
      v44 = 0;
      v37 = 1;
      v36[0] = this;
      v36[1] = &v43;
      v36[2] = &v44;
      v36[3] = &hInternet;
      CHttpAgent::_ImpersonateUserToken((__int64)this);
      WinHttpSetTimeouts(
        hInternet,
        *((_DWORD *)this + 60),
        *((_DWORD *)this + 60),
        *((_DWORD *)this + 60),
        *((_DWORD *)this + 61));
      if ( a3 )
      {
        v15 = -1;
        do
          ++v15;
        while ( a3[v15] );
      }
      v16 = std::to_wstring(v41);
      v18 = (void *)std::operator+<wchar_t>(v40, v17, v16);
      v19 = std::wstring::append(v18, L"\r\n");
      Src = 0;
      v46 = 0u;
      Src = *(_OWORD *)v19;
      v46 = *(_OWORD *)(v19 + 16);
      *(_QWORD *)(v19 + 16) = 0;
      *(_QWORD *)(v19 + 24) = 7;
      *(_WORD *)v19 = 0;
      std::wstring::~wstring((__int64)v40);
      std::wstring::~wstring((__int64)v41);
      if ( a4 )
      {
        memset(Buffer, 0, sizeof(Buffer));
        if ( (unsigned __int64)(*((_QWORD *)a4 + 1) + *(_QWORD *)a4 - 1LL) < *(_QWORD *)a4 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x663,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
            (const char *)0x80070216LL,
            nReceiveTimeout);
        *(_QWORD *)nReceiveTimeouta = *((_QWORD *)a4 + 1) + *(_QWORD *)a4 - 1LL;
        v20 = StringCchPrintfW(Buffer, 0x30u, L"Range: bytes=%llu-%llu\r\n");
        if ( v20 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x665,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
            (const char *)(unsigned int)v20,
            nReceiveTimeouta[0]);
        *(_OWORD *)v47 = *(_OWORD *)Buffer;
        v48 = *(_OWORD *)&Buffer[8];
        v49 = *(_OWORD *)&Buffer[16];
        v50 = *(_OWORD *)&Buffer[24];
        v51 = *(_OWORD *)&Buffer[32];
        v52 = *(_OWORD *)&Buffer[40];
        std::wstring::append(&Src, v47);
      }
      v21 = (TraceLoggingCorrelationVector *)*((_QWORD *)this + 32);
      if ( v21 )
      {
        TraceLoggingCorrelationVector::Increment(v21, v47);
        std::wstring::append(&Src, L"MS-CV: ");
        UTF8toWstr(v38, v47, 0);
        std::wstring::operator+=(&Src);
        std::wstring::~wstring((__int64)v38);
        std::wstring::append(&Src, L"\r\n");
      }
      if ( *((_QWORD *)this + 7) )
        std::wstring::operator+=(&Src);
      if ( a2 )
      {
        v10 = 0;
      }
      else if ( a6 <= 0x40000 )
      {
        AcquireSRWLockExclusive((PSRWLOCK)this + 17);
        v22 = *((_QWORD *)this + 15);
        v23 = 0;
        v24 = 0;
        v25 = 0;
        if ( *((_QWORD *)this + 14) != v22 )
        {
          v23 = *(_QWORD **)(v22 - 8);
          *(_QWORD *)(v22 - 8) = 0;
          v26 = *(void **)(*((_QWORD *)this + 15) - 8LL);
          if ( v26 )
            operator delete(v26);
          *((_QWORD *)this + 15) -= 8LL;
          v24 = v23;
          v25 = v23;
        }
        ReleaseSRWLockExclusive((PSRWLOCK)this + 17);
        if ( !v23 )
        {
          v24 = operator new(0x40008u);
          memset(v24, 0, 0x40008u);
          std::chrono::steady_clock::now(v24 + 0x8000);
          v25 = v24;
        }
        v24[0x8000] = 0;
        v43 = v25;
        v10 = 0x40000;
        v44 = 1;
      }
      else
      {
        v43 = operator new[](a6);
      }
      v38[0] = (unsigned __int64)this + 280;
      if ( (unsigned int)mtx_do_lock((char *)this + 280) )
        std::_Throw_Cpp_error(5);
      v27 = *((_DWORD *)this + 89);
      if ( v27 == 0x7FFFFFFF )
      {
        *((_DWORD *)this + 89) = 2147483646;
        std::_Throw_Cpp_error(6);
      }
      BYTE8(v38[0]) = 1;
      if ( *((_BYTE *)this + 387) )
      {
        v28 = v27 - 1;
        *((_DWORD *)this + 89) = v28;
        if ( !v28 )
        {
          *((_DWORD *)this + 88) = -1;
          ReleaseSRWLockExclusive((PSRWLOCK)this + 37);
        }
        std::wstring::~wstring((__int64)&Src);
        wil::details::lambda_call__CHttpAgent::_OpenRequest_::_9_::_lambda_1___::_lambda_call__CHttpAgent::_OpenRequest_::_9_::_lambda_1___(v36);
        return 2147500036LL;
      }
      v30 = (_QWORD *)std::map<void *,CHttpAgent::RequestCtx>::operator[]((char *)this + 24, &hInternet);
      v31 = v30;
      *v30 = a5;
      if ( a3 )
      {
        v32 = -1;
        do
          ++v32;
        while ( a3[v32] );
        std::string::assign(v30 + 1, a3, v32);
      }
      std::wstring::operator=(v31 + 5, &Src);
      v31[9] = ((unsigned __int64)this + 112) & -(__int64)(v44 != 0);
      v31[10] = v43;
      v31[11] = v10;
      *((_BYTE *)v31 + 104) = *((_QWORD *)this + 13) != 0;
      if ( (*((_DWORD *)this + 89))-- == 1 )
      {
        *((_DWORD *)this + 88) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)this + 37);
      }
      BYTE8(v38[0]) = 0;
      LOBYTE(v37) = 0;
      v13 = CHttpAgent::_DoSendRequest(this, hInternet);
      if ( v13 < 0 )
        CHttpAgent::_DoneWithRequest(this, hInternet);
      std::wstring::~wstring((__int64)&Src);
      wil::details::lambda_call__CHttpAgent::_OpenRequest_::_9_::_lambda_1___::_lambda_call__CHttpAgent::_OpenRequest_::_9_::_lambda_1___(v36);
    }
    result = (unsigned int)v13;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2D4,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\HttpAgent.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x1800ccb24  push    rbx
0x1800ccb26  push    rsi
0x1800ccb27  push    rdi
0x1800ccb28  push    r12
0x1800ccb2a  push    r13
0x1800ccb2c  push    r14
0x1800ccb2e  push    r15
0x1800ccb30  sub     rsp, 200h
0x1800ccb37  mov     rax, cs:__security_cookie
0x1800ccb3e  xor     rax, rsp
0x1800ccb41  mov     [rsp+238h+var_48], rax
0x1800ccb49  mov     rsi, r9
0x1800ccb4c  mov     r12, r8
0x1800ccb4f  mov     r15b, dl
0x1800ccb52  mov     rdi, rcx
0x1800ccb55  mov     r14, [rsp+238h+arg_28]
0x1800ccb5d  xor     r13d, r13d
0x1800ccb60  mov     rax, r8
0x1800ccb63  lea     rcx, aPost; "POST"
0x1800ccb6a  neg     rax
0x1800ccb6d  sbb     rdx, rdx
0x1800ccb70  and     rdx, rcx
0x1800ccb73  test    r15b, r15b
0x1800ccb76  jz      short loc_1800CCB8B
0x1800ccb78  cmp     [rdi+185h], r13b
0x1800ccb7f  jz      short loc_1800CCB8B
0x1800ccb81  lea     rdx, aHead; "HEAD"
0x1800ccb88  mov     esi, r13d
0x1800ccb8b  mov     [rsp+238h+hInternet], r13
0x1800ccb93  lea     r8, [rsp+238h+hInternet]; void **
0x1800ccb9b  mov     rcx, rdi; this
0x1800ccb9e  call    ?_CreateRequest@CHttpAgent@@AEAAJPEB_WPEAPEAX@Z; CHttpAgent::_CreateRequest(wchar_t const *,void * *)
0x1800ccba3  mov     ebx, eax
0x1800ccba5  test    eax, eax
0x1800ccba7  js      loc_1800CD0BB
0x1800ccbad  mov     [rsp+238h+var_110], r13
0x1800ccbb5  mov     [rsp+238h+var_108], r13b
0x1800ccbbd  xorps   xmm0, xmm0
0x1800ccbc0  xor     eax, eax
0x1800ccbc2  movups  [rsp+238h+var_200], xmm0
0x1800ccbc7  movups  [rsp+238h+var_1F0], xmm0
0x1800ccbcc  mov     [rsp+238h+var_1E0], rax
0x1800ccbd1  mov     qword ptr [rsp+238h+var_200], rdi
0x1800ccbd6  lea     rax, [rsp+238h+var_110]
0x1800ccbde  mov     qword ptr [rsp+238h+var_200+8], rax
0x1800ccbe3  lea     rax, [rsp+238h+var_108]
0x1800ccbeb  mov     qword ptr [rsp+238h+var_1F0], rax
0x1800ccbf0  lea     rax, [rsp+238h+hInternet]
0x1800ccbf8  mov     qword ptr [rsp+238h+var_1F0+8], rax
0x1800ccbfd  mov     byte ptr [rsp+238h+var_1E0], 1
0x1800ccc02  mov     [rsp+238h+Token], 0FFFFFFFFFFFFFFFFh
0x1800ccc0b  lea     rdx, [rsp+238h+Token]
0x1800ccc10  mov     rcx, rdi
0x1800ccc13  call    ?_ImpersonateUserToken@CHttpAgent@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@@Z; CHttpAgent::_ImpersonateUserToken(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x1800ccc18  mov     edx, [rdi+0F0h]; nResolveTimeout
0x1800ccc1e  mov     eax, [rdi+0F4h]
0x1800ccc24  mov     [rsp+238h+nReceiveTimeout], eax; int
0x1800ccc28  mov     r9d, edx; nSendTimeout
0x1800ccc2b  mov     r8d, edx; nConnectTimeout
0x1800ccc2e  mov     rcx, [rsp+238h+hInternet]; hInternet
0x1800ccc36  call    cs:__imp_WinHttpSetTimeouts
0x1800ccc3c  mov     rbx, [rsp+238h+Token]
0x1800ccc41  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800ccc45  jz      short loc_1800CCC68
0x1800ccc47  mov     rdx, rbx; Token
0x1800ccc4a  xor     ecx, ecx; Thread
0x1800ccc4c  call    cs:__imp_SetThreadToken
0x1800ccc52  test    eax, eax
0x1800ccc54  jz      loc_1800CD0ED
0x1800ccc5a  test    rbx, rbx
0x1800ccc5d  jz      short loc_1800CCC68
0x1800ccc5f  mov     rcx, rbx; hObject
0x1800ccc62  call    cs:__imp_CloseHandle
0x1800ccc68  test    r12, r12
0x1800ccc6b  jz      short loc_1800CCC7C
0x1800ccc6d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800ccc71  inc     rdx
0x1800ccc74  cmp     [r12+rdx], r13b
0x1800ccc78  jnz     short loc_1800CCC71
0x1800ccc7a  jmp     short loc_1800CCC7F
0x1800ccc7c  mov     edx, r13d
0x1800ccc7f  lea     rcx, [rsp+238h+var_138]; void *
0x1800ccc87  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@I@Z; std::to_wstring(uint)
0x1800ccc8c  nop
0x1800ccc8d  mov     r8, rax
0x1800ccc90  lea     rcx, [rsp+238h+var_158]
0x1800ccc98  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEB_W$$QEAV10@@Z; std::operator+<wchar_t>(wchar_t const * const,std::wstring &&)
0x1800ccc9d  nop
0x1800ccc9e  lea     rdx, asc_18013CD68; "\r\n"
0x1800ccca5  mov     rcx, rax; Src
0x1800ccca8  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x1800cccad  xorps   xmm0, xmm0
0x1800cccb0  movups  [rsp+238h+Src], xmm0
0x1800cccb8  mov     qword ptr [rsp+238h+var_F0], r13
0x1800cccc0  mov     qword ptr [rsp+238h+var_F0+8], r13
0x1800cccc8  movups  xmm0, xmmword ptr [rax]
0x1800ccccb  movups  [rsp+238h+Src], xmm0
0x1800cccd3  movups  xmm1, xmmword ptr [rax+10h]
0x1800cccd7  movups  [rsp+238h+var_F0], xmm1
0x1800cccdf  mov     [rax+10h], r13
0x1800ccce3  mov     qword ptr [rax+18h], 7
0x1800ccceb  mov     [rax], r13w
0x1800cccef  lea     rcx, [rsp+238h+var_158]
0x1800cccf7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800cccfc  nop
0x1800cccfd  lea     rcx, [rsp+238h+var_138]
0x1800ccd05  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ccd0a  test    rsi, rsi
0x1800ccd0d  jz      loc_1800CCDE5
0x1800ccd13  xor     edx, edx; Val
0x1800ccd15  lea     r8d, [rdx+60h]; Size
0x1800ccd19  lea     rcx, [rsp+238h+Buffer]; void *
0x1800ccd21  call    memset
0x1800ccd26  mov     r9, [rsi]
0x1800ccd29  lea     rdx, [r9-1]
0x1800ccd2d  add     rdx, [rsi+8]
0x1800ccd31  mov     rcx, [rsp+238h]; this
0x1800ccd39  cmp     rdx, r9
0x1800ccd3c  jb      loc_1800CD0F3
0x1800ccd42  mov     qword ptr [rsp+238h+nReceiveTimeout], rdx; int
0x1800ccd47  lea     r8, aRangeBytesLluL; "Range: bytes=%llu-%llu\r\n"
0x1800ccd4e  mov     edx, 30h ; '0'; unsigned __int64
0x1800ccd53  lea     rcx, [rsp+238h+Buffer]; Buffer
0x1800ccd5b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800ccd60  mov     rcx, [rsp+238h]; this
0x1800ccd68  test    eax, eax
0x1800ccd6a  js      loc_1800CD10A
0x1800ccd70  movups  xmm0, xmmword ptr [rsp+238h+Buffer]
0x1800ccd78  movaps  xmmword ptr [rsp+238h+var_D8], xmm0
0x1800ccd80  movups  xmm1, [rsp+238h+var_1A8]
0x1800ccd88  movaps  [rsp+238h+var_C8], xmm1
0x1800ccd90  movups  xmm0, [rsp+238h+var_198]
0x1800ccd98  movaps  [rsp+238h+var_B8], xmm0
0x1800ccda0  movups  xmm1, [rsp+238h+var_188]
0x1800ccda8  movaps  [rsp+238h+var_A8], xmm1
0x1800ccdb0  movups  xmm0, [rsp+238h+var_178]
0x1800ccdb8  movaps  [rsp+238h+var_98], xmm0
0x1800ccdc0  movups  xmm1, [rsp+238h+var_168]
0x1800ccdc8  movaps  [rsp+238h+var_88], xmm1
0x1800ccdd0  lea     rdx, [rsp+238h+var_D8]; void *
0x1800ccdd8  lea     rcx, [rsp+238h+Src]; Src
0x1800ccde0  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x1800ccde5  mov     rcx, [rdi+100h]; this
0x1800ccdec  test    rcx, rcx
0x1800ccdef  jz      short loc_1800CCE57
0x1800ccdf1  lea     rdx, [rsp+238h+var_D8]; char *
0x1800ccdf9  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x1800ccdfe  lea     rdx, aMsCv; "MS-CV: "
0x1800cce05  lea     rcx, [rsp+238h+Src]; Src
0x1800cce0d  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x1800cce12  xor     r8d, r8d
0x1800cce15  lea     rdx, [rsp+238h+var_D8]
0x1800cce1d  lea     rcx, [rsp+238h+var_1D8]
0x1800cce22  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x1800cce27  nop
0x1800cce28  mov     rdx, rax
0x1800cce2b  lea     rcx, [rsp+238h+Src]; Src
0x1800cce33  call    ??Y?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x1800cce38  nop
0x1800cce39  lea     rcx, [rsp+238h+var_1D8]
0x1800cce3e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800cce43  lea     rdx, asc_18013CD68; "\r\n"
0x1800cce4a  lea     rcx, [rsp+238h+Src]; Src
0x1800cce52  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x1800cce57  cmp     [rdi+38h], r13
0x1800cce5b  jz      short loc_1800CCE6E
0x1800cce5d  lea     rdx, [rdi+28h]
0x1800cce61  lea     rcx, [rsp+238h+Src]; Src
0x1800cce69  call    ??Y?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x1800cce6e  test    r15b, r15b
0x1800cce71  jz      short loc_1800CCE7B
0x1800cce73  mov     r14, r13
0x1800cce76  jmp     loc_1800CCF4C
0x1800cce7b  cmp     r14, 40000h
0x1800cce82  jbe     short loc_1800CCE99
0x1800cce84  mov     rcx, r14; unsigned __int64
0x1800cce87  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800cce8c  mov     [rsp+238h+var_110], rax
0x1800cce94  jmp     loc_1800CCF4C
0x1800cce99  mov     [rsp+238h+Token], r13
0x1800cce9e  lea     r15, [rdi+88h]
0x1800ccea5  mov     rcx, r15; SRWLock
0x1800ccea8  call    cs:__imp_AcquireSRWLockExclusive
0x1800cceae  mov     rax, [rdi+78h]
0x1800cceb2  mov     rsi, r13
0x1800cceb5  mov     rbx, r13
0x1800cceb8  mov     r14, r13
0x1800ccebb  cmp     [rdi+70h], rax
0x1800ccebf  jz      short loc_1800CCEF0
0x1800ccec1  mov     rsi, [rax-8]
0x1800ccec5  mov     [rax-8], r13
0x1800ccec9  mov     [rsp+238h+Token], rsi
0x1800ccece  mov     rax, [rdi+78h]
0x1800cced2  mov     rcx, [rax-8]; Block
0x1800cced6  test    rcx, rcx
0x1800cced9  jz      short loc_1800CCEE5
0x1800ccedb  mov     edx, 40008h
0x1800ccee0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ccee5  add     qword ptr [rdi+78h], 0FFFFFFFFFFFFFFF8h
0x1800cceea  mov     rbx, rsi
0x1800cceed  mov     r14, rsi
0x1800ccef0  mov     rcx, r15; SRWLock
0x1800ccef3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ccef9  test    rsi, rsi
0x1800ccefc  jnz     short loc_1800CCF2F
0x1800ccefe  mov     ecx, 40008h; Size
0x1800ccf03  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ccf08  mov     rbx, rax
0x1800ccf0b  xor     edx, edx; Val
0x1800ccf0d  mov     r8d, 40008h; Size
0x1800ccf13  mov     rcx, rax; void *
0x1800ccf16  call    memset
0x1800ccf1b  lea     rcx, [rbx+40000h]
0x1800ccf22  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x1800ccf27  mov     [rsp+238h+Token], rbx
0x1800ccf2c  mov     r14, rbx
0x1800ccf2f  mov     [rbx+40000h], r13
0x1800ccf36  mov     [rsp+238h+var_110], r14
0x1800ccf3e  mov     r14d, 40000h
0x1800ccf44  mov     [rsp+238h+var_108], 1
0x1800ccf4c  xorps   xmm0, xmm0
0x1800ccf4f  movups  [rsp+238h+var_1D8], xmm0
0x1800ccf54  lea     rsi, [rdi+118h]
0x1800ccf5b  mov     qword ptr [rsp+238h+var_1D8], rsi
0x1800ccf60  mov     byte ptr [rsp+238h+var_1D8+8], r13b
0x1800ccf65  mov     rcx, rsi
0x1800ccf68  call    mtx_do_lock
0x1800ccf6d  test    eax, eax
0x1800ccf6f  jnz     loc_1800CD11E
0x1800ccf75  mov     eax, [rdi+164h]
0x1800ccf7b  cmp     eax, 7FFFFFFFh
0x1800ccf80  jz      loc_1800CD128
0x1800ccf86  mov     byte ptr [rsp+238h+var_1D8+8], 1
0x1800ccf8b  cmp     [rdi+183h], r13b
0x1800ccf92  jz      short loc_1800CCFD9
0x1800ccf94  sub     eax, 1
0x1800ccf97  mov     [rdi+164h], eax
0x1800ccf9d  jnz     short loc_1800CCFB7
0x1800ccf9f  mov     dword ptr [rdi+160h], 0FFFFFFFFh
0x1800ccfa9  lea     rcx, [rdi+128h]; SRWLock
0x1800ccfb0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ccfb6  nop
0x1800ccfb7  lea     rcx, [rsp+238h+Src]
0x1800ccfbf  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ccfc4  nop
0x1800ccfc5  lea     rcx, [rsp+238h+var_200]
0x1800ccfca  call    wil__details__lambda_call__CHttpAgent___OpenRequest____9____lambda_1______lambda_call__CHttpAgent___OpenRequest____9____lambda_1___
0x1800ccfcf  mov     eax, 80004004h
0x1800ccfd4  jmp     loc_1800CD0CA
0x1800ccfd9  lea     rcx, [rdi+18h]
0x1800ccfdd  lea     rdx, [rsp+238h+hInternet]
0x1800ccfe5  call    ??A?$map@PEAXURequestCtx@CHttpAgent@@U?$less@PEAX@std@@V?$allocator@U?$pair@QEAXURequestCtx@CHttpAgent@@@std@@@4@@std@@QEAAAEAURequestCtx@CHttpAgent@@AEBQEAX@Z; std::map<void *,CHttpAgent::RequestCtx>::operator[](void * const &)
0x1800ccfea  mov     rbx, rax
0x1800ccfed  mov     rcx, [rsp+238h+arg_20]
0x1800ccff5  mov     [rax], rcx
0x1800ccff8  test    r12, r12
0x1800ccffb  jz      short loc_1800CD016
0x1800ccffd  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800cd001  inc     r8; Size
0x1800cd004  cmp     [r12+r8], r13b
0x1800cd008  jnz     short loc_1800CD001
0x1800cd00a  lea     rcx, [rax+8]; void *
0x1800cd00e  mov     rdx, r12; Src
0x1800cd011  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1800cd016  lea     rcx, [rbx+28h]
0x1800cd01a  lea     rdx, [rsp+238h+Src]
0x1800cd022  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800cd027  mov     al, [rsp+238h+var_108]
0x1800cd02e  lea     rdx, [rdi+70h]
0x1800cd032  neg     al
0x1800cd034  sbb     rcx, rcx
0x1800cd037  and     rcx, rdx
0x1800cd03a  mov     [rbx+48h], rcx
0x1800cd03e  mov     rax, [rsp+238h+var_110]
0x1800cd046  mov     [rbx+50h], rax
0x1800cd04a  mov     [rbx+58h], r14
0x1800cd04e  cmp     [rdi+68h], r13
0x1800cd052  setnz   al
0x1800cd055  mov     [rbx+68h], al
0x1800cd058  sub     dword ptr [rdi+164h], 1
0x1800cd05f  jnz     short loc_1800CD072
0x1800cd061  mov     dword ptr [rsi+48h], 0FFFFFFFFh
0x1800cd068  lea     rcx, [rsi+10h]; SRWLock
0x1800cd06c  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cd072  mov     byte ptr [rsp+238h+var_1D8+8], r13b
0x1800cd077  mov     byte ptr [rsp+238h+var_1E0], r13b
0x1800cd07c  mov     rdx, [rsp+238h+hInternet]; void *
0x1800cd084  mov     rcx, rdi; this
0x1800cd087  call    ?_DoSendRequest@CHttpAgent@@AEAAJPEAX@Z; CHttpAgent::_DoSendRequest(void *)
0x1800cd08c  mov     ebx, eax
0x1800cd08e  test    eax, eax
0x1800cd090  jns     short loc_1800CD0A3
0x1800cd092  mov     rdx, [rsp+238h+hInternet]; void *
0x1800cd09a  mov     rcx, rdi; this
0x1800cd09d  call    ?_DoneWithRequest@CHttpAgent@@AEAAXPEAX@Z; CHttpAgent::_DoneWithRequest(void *)
0x1800cd0a2  nop
0x1800cd0a3  lea     rcx, [rsp+238h+Src]
0x1800cd0ab  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800cd0b0  nop
0x1800cd0b1  lea     rcx, [rsp+238h+var_200]
  ... truncated ...
```
