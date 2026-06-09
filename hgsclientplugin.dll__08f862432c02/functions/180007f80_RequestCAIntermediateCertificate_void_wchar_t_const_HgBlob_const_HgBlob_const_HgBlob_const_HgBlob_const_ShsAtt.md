# RequestCAIntermediateCertificate(void *,wchar_t const *,HgBlob * const,HgBlob * const,HgBlob * const,HgBlob * const,ShsAttestationFlag *,wchar_t * *,uint *,AttestationResult * *)

- ea: `0x180007f80`
- end: `0x180008281`
- name: `?RequestCAIntermediateCertificate@@YAJPEAXPEB_WQEAUHgBlob@@222PEAW4ShsAttestationFlag@@PEAPEA_WPEAIPEAPEAUAttestationResult@@@Z`
- size: `769`
- prototype: `__int64 __fastcall(void *, const wchar_t *, struct HgBlob *const, struct HgBlob *const, struct HgBlob *const, struct HgBlob *const, enum ShsAttestationFlag *, wchar_t **, unsigned int *, struct AttestationResult **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001520`
- `0x1800049f4`
- `0x180006060`
- `0x180006260`
- `0x1800062ec`
- `0x1800075bc`
- `0x180007f80`
- `0x1800082a8`
- `0x180008ecc`

## string_xrefs

- `0x180008093`: `servercommon\base\securehostingservice\common\service\plugin\hgsclientplugin.cpp`
- `0x180008158`: `servercommon\base\securehostingservice\common\service\plugin\hgsclientplugin.cpp`
- `0x180008244`: `servercommon\base\securehostingservice\common\service\plugin\hgsclientplugin.cpp`

## pseudocode

```c
__int64 __fastcall RequestCAIntermediateCertificate(
        void *a1,
        const wchar_t *a2,
        struct HgBlob *const a3,
        struct HgBlob *const a4,
        struct HgBlob *const a5,
        struct HgBlob *const a6,
        enum ShsAttestationFlag *a7,
        wchar_t **a8,
        unsigned int *a9,
        struct AttestationResult **a10)
{
  int v10; // r14d
  int v11; // r15d
  unsigned int v13; // esi
  __int128 *v14; // rdx
  int v15; // [rsp+20h] [rbp-148h]
  int v16; // [rsp+20h] [rbp-148h]
  const char *v17; // [rsp+28h] [rbp-140h]
  int v18; // [rsp+50h] [rbp-118h] BYREF
  wchar_t *v19; // [rsp+58h] [rbp-110h] BYREF
  int v20[2]; // [rsp+60h] [rbp-108h]
  __int128 v21; // [rsp+68h] [rbp-100h] BYREF
  __int64 v22; // [rsp+78h] [rbp-F0h]
  unsigned __int64 v23; // [rsp+80h] [rbp-E8h]
  _BYTE v24[32]; // [rsp+90h] [rbp-D8h] BYREF
  _BYTE v25[32]; // [rsp+B0h] [rbp-B8h] BYREF
  _BYTE v26[24]; // [rsp+D0h] [rbp-98h] BYREF
  _BYTE v27[56]; // [rsp+E8h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v10 = (int)a4;
  v11 = (int)a3;
  *(_QWORD *)v20 = a6;
  if ( a3
    && a4
    && a5
    && *(_DWORD *)a3
    && *((_QWORD *)a3 + 1)
    && *(_DWORD *)a4
    && *((_QWORD *)a4 + 1)
    && *(_DWORD *)a5
    && *((_QWORD *)a5 + 1)
    && a9
    && a10 )
  {
    if ( a7 )
      *(_DWORD *)a7 = 0;
    if ( a8 )
      *a8 = 0;
    *a9 = 0;
    *a10 = 0;
    Microsoft::HostGuardian::Client::Plugin::HgsClientData::HgsClientData(
      (Microsoft::HostGuardian::Client::Plugin::HgsClientData *)v24,
      a2);
    if ( v27[40] )
    {
      v19 = (wchar_t *)v24;
      v18 = 0;
      v21 = 0;
      v22 = 0;
      v23 = 7;
      LOWORD(v21) = 0;
      v13 = Microsoft::HostGuardian::Client::Plugin::AttestationHandler::RequestCAIntermediateCertificate(
              (unsigned int)&v19,
              v11,
              v10,
              (_DWORD)a5,
              *(__int64 *)v20,
              (__int64)&v18);
      if ( v13 == -2063724543 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC6,
          (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\hgsclientplugin.cpp",
          (const char *)0x84FE1001LL,
          v16);
        std::wstring::~wstring(&v21);
        std::vector<std::wstring>::~vector<std::wstring>(v27);
        std::vector<std::wstring>::~vector<std::wstring>(v26);
        std::wstring::~wstring(v25);
        std::wstring::~wstring(v24);
        return 2231242753LL;
      }
      else
      {
        if ( a7 )
          *(_DWORD *)a7 = v18;
        if ( v22 && a8 )
        {
          v14 = &v21;
          if ( v23 > 7 )
            v14 = (__int128 *)v21;
          wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
            &v19,
            v14);
          *a8 = v19;
        }
        std::wstring::~wstring(&v21);
        std::vector<std::wstring>::~vector<std::wstring>(v27);
        std::vector<std::wstring>::~vector<std::wstring>(v26);
        std::wstring::~wstring(v25);
        std::wstring::~wstring(v24);
        return v13;
      }
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xB6,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\hgsclientplugin.cpp",
        (const char *)0x80070032LL,
        (int)"CA cert is not supported",
        v17);
      std::vector<std::wstring>::~vector<std::wstring>(v27);
      std::vector<std::wstring>::~vector<std::wstring>(v26);
      std::wstring::~wstring(v25);
      std::wstring::~wstring(v24);
      return 2147942450LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAA,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\hgsclientplugin.cpp",
      (const char *)0x80070057LL,
      v15);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180007f80  push    rbx
0x180007f82  push    rsi
0x180007f83  push    rdi
0x180007f84  push    r12
0x180007f86  push    r13
0x180007f88  push    r14
0x180007f8a  push    r15
0x180007f8c  sub     rsp, 130h
0x180007f93  mov     rax, cs:__security_cookie
0x180007f9a  xor     rax, rsp
0x180007f9d  mov     [rsp+168h+var_48], rax
0x180007fa5  mov     r14, r9
0x180007fa8  mov     r15, r8
0x180007fab  mov     rsi, [rsp+168h+arg_20]
0x180007fb3  mov     rax, [rsp+168h+arg_28]
0x180007fbb  mov     qword ptr [rsp+168h+var_108], rax
0x180007fc0  mov     rbx, [rsp+168h+arg_30]
0x180007fc8  mov     rdi, [rsp+168h+arg_38]
0x180007fd0  mov     r12, [rsp+168h+arg_40]
0x180007fd8  mov     r13, [rsp+168h+arg_48]
0x180007fe0  xor     eax, eax
0x180007fe2  test    r8, r8
0x180007fe5  jz      loc_180008234
0x180007feb  test    r9, r9
0x180007fee  jz      loc_180008234
0x180007ff4  test    rsi, rsi
0x180007ff7  jz      loc_180008234
0x180007ffd  cmp     [r8], eax
0x180008000  jbe     loc_180008234
0x180008006  cmp     [r8+8], rax
0x18000800a  jz      loc_180008234
0x180008010  cmp     [r9], eax
0x180008013  jbe     loc_180008234
0x180008019  cmp     [r9+8], rax
0x18000801d  jz      loc_180008234
0x180008023  cmp     [rsi], eax
0x180008025  jbe     loc_180008234
0x18000802b  cmp     [rsi+8], rax
0x18000802f  jz      loc_180008234
0x180008035  test    r12, r12
0x180008038  jz      loc_180008234
0x18000803e  test    r13, r13
0x180008041  jz      loc_180008234
0x180008047  test    rbx, rbx
0x18000804a  jz      short loc_18000804E
0x18000804c  mov     [rbx], eax
0x18000804e  test    rdi, rdi
0x180008051  jz      short loc_180008056
0x180008053  mov     [rdi], rax
0x180008056  mov     [r12], eax
0x18000805a  mov     [r13+0], rax
0x18000805e  lea     rcx, [rsp+168h+var_D8]; this
0x180008066  call    ??0HgsClientData@Plugin@Client@HostGuardian@Microsoft@@QEAA@PEB_W@Z; Microsoft::HostGuardian::Client::Plugin::HgsClientData::HgsClientData(wchar_t const *)
0x18000806b  nop
0x18000806c  xor     ecx, ecx
0x18000806e  cmp     [rsp+168h+var_58], cl
0x180008075  jnz     short loc_1800080E0
0x180008077  mov     rcx, [rsp+168h]; this
0x18000807f  lea     rax, aCaCertIsNotSup; "CA cert is not supported"
0x180008086  mov     qword ptr [rsp+168h+var_148], rax; int
0x18000808b  mov     ebx, 80070032h
0x180008090  mov     r9d, ebx; char *
0x180008093  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000809a  mov     edx, 0B6h; void *
0x18000809f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800080a4  nop
0x1800080a5  lea     rcx, [rsp+168h+var_80]
0x1800080ad  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x1800080b2  lea     rcx, [rsp+168h+var_98]
0x1800080ba  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x1800080bf  lea     rcx, [rsp+168h+var_B8]
0x1800080c7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800080cc  lea     rcx, [rsp+168h+var_D8]
0x1800080d4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800080d9  mov     eax, ebx
0x1800080db  jmp     loc_18000825D
0x1800080e0  lea     rax, [rsp+168h+var_D8]
0x1800080e8  mov     [rsp+168h+var_110], rax
0x1800080ed  mov     [rsp+168h+var_118], ecx
0x1800080f1  xorps   xmm0, xmm0
0x1800080f4  movups  [rsp+168h+var_100], xmm0
0x1800080f9  mov     [rsp+168h+var_F0], rcx
0x1800080fe  mov     [rsp+168h+var_E8], 7
0x18000810a  mov     word ptr [rsp+168h+var_100], cx
0x18000810f  mov     [rsp+168h+var_128], r13
0x180008114  mov     [rsp+168h+var_130], r12
0x180008119  lea     rax, [rsp+168h+var_118]
0x18000811e  mov     [rsp+168h+var_140], rax
0x180008123  mov     rax, qword ptr [rsp+168h+var_108]
0x180008128  mov     qword ptr [rsp+168h+var_148], rax; int
0x18000812d  mov     r9, rsi
0x180008130  mov     r8, r14
0x180008133  mov     rdx, r15
0x180008136  lea     rcx, [rsp+168h+var_110]
0x18000813b  call    ?RequestCAIntermediateCertificate@AttestationHandler@Plugin@Client@HostGuardian@Microsoft@@QEAA?AW4AttestationError@@QEAUHgBlob@@000AEAW4ShsAttestationFlag@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAIPEAPEAUAttestationResult@@@Z; Microsoft::HostGuardian::Client::Plugin::AttestationHandler::RequestCAIntermediateCertificate(HgBlob * const,HgBlob * const,HgBlob * const,HgBlob * const,ShsAttestationFlag &,std::wstring &,uint *,AttestationResult * *)
0x180008140  mov     esi, eax
0x180008142  mov     r14d, 84FE1001h
0x180008148  cmp     eax, r14d
0x18000814b  jnz     short loc_1800081B1
0x18000814d  mov     rcx, [rsp+168h]; this
0x180008155  mov     r9d, r14d; char *
0x180008158  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000815f  mov     edx, 0C6h; void *
0x180008164  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008169  nop
0x18000816a  lea     rcx, [rsp+168h+var_100]
0x18000816f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008174  nop
0x180008175  lea     rcx, [rsp+168h+var_80]
0x18000817d  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180008182  lea     rcx, [rsp+168h+var_98]
0x18000818a  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x18000818f  lea     rcx, [rsp+168h+var_B8]
0x180008197  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000819c  lea     rcx, [rsp+168h+var_D8]
0x1800081a4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800081a9  mov     eax, r14d
0x1800081ac  jmp     loc_18000825D
0x1800081b1  test    rbx, rbx
0x1800081b4  jz      short loc_1800081BC
0x1800081b6  mov     eax, [rsp+168h+var_118]
0x1800081ba  mov     [rbx], eax
0x1800081bc  mov     r8, [rsp+168h+var_F0]
0x1800081c1  test    r8, r8
0x1800081c4  jz      short loc_1800081F1
0x1800081c6  test    rdi, rdi
0x1800081c9  jz      short loc_1800081F1
0x1800081cb  lea     rdx, [rsp+168h+var_100]
0x1800081d0  cmp     [rsp+168h+var_E8], 7
0x1800081d9  cmova   rdx, qword ptr [rsp+168h+var_100]
0x1800081df  lea     rcx, [rsp+168h+var_110]
0x1800081e4  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x1800081e9  mov     rax, [rsp+168h+var_110]
0x1800081ee  mov     [rdi], rax
0x1800081f1  lea     rcx, [rsp+168h+var_100]
0x1800081f6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800081fb  nop
0x1800081fc  lea     rcx, [rsp+168h+var_80]
0x180008204  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180008209  lea     rcx, [rsp+168h+var_98]
0x180008211  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180008216  lea     rcx, [rsp+168h+var_B8]
0x18000821e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008223  lea     rcx, [rsp+168h+var_D8]
0x18000822b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008230  mov     eax, esi
0x180008232  jmp     short loc_18000825D
0x180008234  mov     rcx, [rsp+168h]; this
0x18000823c  mov     ebx, 80070057h
0x180008241  mov     r9d, ebx; char *
0x180008244  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000824b  mov     edx, 0AAh; void *
0x180008250  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008255  mov     eax, ebx
0x180008257  jmp     short loc_18000825D
0x180008259  mov     eax, [rsp+168h+var_118]
0x18000825d  mov     rcx, [rsp+168h+var_48]
0x180008265  xor     rcx, rsp; StackCookie
0x180008268  call    __security_check_cookie
0x18000826d  add     rsp, 130h
0x180008274  pop     r15
0x180008276  pop     r14
0x180008278  pop     r13
0x18000827a  pop     r12
0x18000827c  pop     rdi
0x18000827d  pop     rsi
0x18000827e  pop     rbx
0x18000827f  retn
```
