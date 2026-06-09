# QueryAttestationResults(void *,wchar_t const *,uint,AttestationResultType *,ShsAttestationFlag *,wchar_t * *,uint *,AttestationResult * *)

- ea: `0x180007c80`
- end: `0x180007f78`
- name: `?QueryAttestationResults@@YAJPEAXPEB_WIPEAW4AttestationResultType@@PEAW4ShsAttestationFlag@@PEAPEA_WPEAIPEAPEAUAttestationResult@@@Z`
- size: `760`
- prototype: `__int64 __fastcall(void *, const wchar_t *, unsigned int, enum AttestationResultType *, enum ShsAttestationFlag *, wchar_t **, unsigned int *, struct AttestationResult **)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001520`
- `0x1800049f4`
- `0x180006060`
- `0x180006260`
- `0x1800062ec`
- `0x180006f44`
- `0x1800075bc`
- `0x1800077b8`
- `0x180007c80`
- `0x180008bd0`

## import_xrefs

- `hgattest!Attest` at `0x180007e07`
- `hgattest!Attest` at `0x180007e07`

## string_xrefs

- `0x180007e25`: `servercommon\base\securehostingservice\common\service\plugin\hgsclientplugin.cpp`
- `0x180007f36`: `servercommon\base\securehostingservice\common\service\plugin\hgsclientplugin.cpp`

## pseudocode

```c
__int64 __fastcall QueryAttestationResults(
        void *a1,
        const wchar_t *a2,
        unsigned int a3,
        enum AttestationResultType *a4,
        enum ShsAttestationFlag *a5,
        wchar_t **a6,
        unsigned int *a7,
        struct AttestationResult **a8)
{
  __int64 v9; // r12
  int v10; // r14d
  __int64 v11; // r8
  unsigned __int64 v12; // r9
  unsigned int v13; // ebx
  __int128 *v15; // rdx
  int v16; // [rsp+20h] [rbp-148h]
  int v17; // [rsp+30h] [rbp-138h] BYREF
  wchar_t *v18; // [rsp+38h] [rbp-130h] BYREF
  _QWORD v19[3]; // [rsp+40h] [rbp-128h] BYREF
  int v20; // [rsp+58h] [rbp-110h] BYREF
  __int128 v21; // [rsp+5Ch] [rbp-10Ch]
  int v22; // [rsp+6Ch] [rbp-FCh]
  int v23; // [rsp+70h] [rbp-F8h]
  int v24; // [rsp+74h] [rbp-F4h]
  __int64 v25; // [rsp+78h] [rbp-F0h]
  __int128 v26; // [rsp+80h] [rbp-E8h] BYREF
  __int64 v27; // [rsp+90h] [rbp-D8h]
  __int64 v28; // [rsp+98h] [rbp-D0h]
  _BYTE v29[32]; // [rsp+A0h] [rbp-C8h] BYREF
  _BYTE v30[32]; // [rsp+C0h] [rbp-A8h] BYREF
  _BYTE v31[24]; // [rsp+E0h] [rbp-88h] BYREF
  _BYTE v32[24]; // [rsp+F8h] [rbp-70h] BYREF
  int v33; // [rsp+110h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v9 = a3;
  if ( !a4 || !a3 || !a7 || !a8 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x73,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\hgsclientplugin.cpp",
      (const char *)0x80070057LL,
      v16);
    return 2147942487LL;
  }
  if ( a5 )
    *(_DWORD *)a5 = 0;
  if ( a6 )
    *a6 = 0;
  *a7 = 0;
  *a8 = 0;
  Microsoft::HostGuardian::Client::Plugin::HgsClientData::HgsClientData(
    (Microsoft::HostGuardian::Client::Plugin::HgsClientData *)v29,
    a2);
  v18 = (wchar_t *)v29;
  std::vector<enum AttestationResultType>::vector<enum AttestationResultType>(v19, a4, (char *)a4 + 4 * v9);
  v10 = 0;
  v17 = 0;
  v26 = 0;
  v11 = 0;
  v27 = 0;
  v12 = 7;
  v28 = 7;
  LOWORD(v26) = 0;
  if ( v33 == 1 )
  {
    v21 = 0;
    v22 = 0;
    v24 = 0;
    v20 = 40;
    v25 = v19[0];
    v23 = (__int64)(v19[1] - v19[0]) >> 2;
    v13 = Attest(1, &v20, a7, a8);
    goto LABEL_14;
  }
  if ( v33 == 2 )
  {
    v13 = Microsoft::HostGuardian::Client::Plugin::AttestationHandler::AttestShs(
            (unsigned int)&v18,
            (unsigned int)v19,
            (unsigned int)&v17,
            (unsigned int)&v26,
            (__int64)a7,
            (__int64)a8);
    v10 = v17;
LABEL_14:
    if ( v13 == -2063724543 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x89,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\hgsclientplugin.cpp",
        (const char *)0x84FE1001LL,
        v16);
      std::wstring::~wstring(&v26);
      std::vector<enum AttestationResultType>::~vector<enum AttestationResultType>(v19);
      std::vector<std::wstring>::~vector<std::wstring>(v32);
      std::vector<std::wstring>::~vector<std::wstring>(v31);
      std::wstring::~wstring(v30);
      std::wstring::~wstring(v29);
      return 2231242753LL;
    }
    v12 = v28;
    v11 = v27;
    goto LABEL_17;
  }
  v13 = -2147467263;
LABEL_17:
  if ( a5 )
    *(_DWORD *)a5 = v10;
  if ( v11 && a6 )
  {
    v15 = &v26;
    if ( v12 > 7 )
      v15 = (__int128 *)v26;
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
      &v18,
      v15);
    *a6 = v18;
  }
  std::wstring::~wstring(&v26);
  std::vector<enum AttestationResultType>::~vector<enum AttestationResultType>(v19);
  std::vector<std::wstring>::~vector<std::wstring>(v32);
  std::vector<std::wstring>::~vector<std::wstring>(v31);
  std::wstring::~wstring(v30);
  std::wstring::~wstring(v29);
  return v13;
}

```

## disassembly

```asm
0x180007c80  mov     [rsp+arg_0], rbx
0x180007c85  push    rsi
0x180007c86  push    rdi
0x180007c87  push    r12
0x180007c89  push    r14
0x180007c8b  push    r15
0x180007c8d  sub     rsp, 140h
0x180007c94  mov     rax, cs:__security_cookie
0x180007c9b  xor     rax, rsp
0x180007c9e  mov     [rsp+168h+var_38], rax
0x180007ca6  mov     r14, r9
0x180007ca9  mov     r12d, r8d
0x180007cac  mov     rsi, [rsp+168h+arg_20]
0x180007cb4  mov     rdi, [rsp+168h+arg_28]
0x180007cbc  mov     rbx, [rsp+168h+arg_30]
0x180007cc4  mov     r15, [rsp+168h+arg_38]
0x180007ccc  test    r9, r9
0x180007ccf  jz      loc_180007F26
0x180007cd5  test    r8d, r8d
0x180007cd8  jz      loc_180007F26
0x180007cde  test    rbx, rbx
0x180007ce1  jz      loc_180007F26
0x180007ce7  test    r15, r15
0x180007cea  jz      loc_180007F26
0x180007cf0  test    rsi, rsi
0x180007cf3  jz      short loc_180007CFB
0x180007cf5  mov     dword ptr [rsi], 0
0x180007cfb  test    rdi, rdi
0x180007cfe  jz      short loc_180007D07
0x180007d00  mov     qword ptr [rdi], 0
0x180007d07  mov     dword ptr [rbx], 0
0x180007d0d  mov     qword ptr [r15], 0
0x180007d14  lea     rcx, [rsp+168h+var_C8]; this
0x180007d1c  call    ??0HgsClientData@Plugin@Client@HostGuardian@Microsoft@@QEAA@PEB_W@Z; Microsoft::HostGuardian::Client::Plugin::HgsClientData::HgsClientData(wchar_t const *)
0x180007d21  nop
0x180007d22  lea     rax, [rsp+168h+var_C8]
0x180007d2a  mov     [rsp+168h+var_130], rax
0x180007d2f  lea     r8, [r14+r12*4]
0x180007d33  mov     rdx, r14
0x180007d36  lea     rcx, [rsp+168h+var_128]
0x180007d3b  call    ??$?0PEAW4AttestationResultType@@$0A@@?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@QEAA@PEAW4AttestationResultType@@0AEBV?$allocator@W4AttestationResultType@@@1@@Z; std::vector<AttestationResultType>::vector<AttestationResultType>(AttestationResultType *,AttestationResultType *,std::allocator<AttestationResultType> const &)
0x180007d40  nop
0x180007d41  xor     r14d, r14d
0x180007d44  mov     [rsp+168h+var_138], r14d
0x180007d49  xorps   xmm0, xmm0
0x180007d4c  movups  [rsp+168h+var_E8], xmm0
0x180007d54  xor     r8d, r8d
0x180007d57  mov     [rsp+168h+var_D8], r8
0x180007d5f  lea     r9d, [r14+7]
0x180007d63  mov     [rsp+168h+var_D0], r9
0x180007d6b  xor     eax, eax
0x180007d6d  mov     word ptr [rsp+168h+var_E8], ax
0x180007d75  mov     ecx, [rsp+168h+var_58]
0x180007d7c  sub     ecx, 1
0x180007d7f  jz      short loc_180007DBF
0x180007d81  cmp     ecx, 1
0x180007d84  jz      short loc_180007D90
0x180007d86  mov     ebx, 80004001h
0x180007d8b  jmp     loc_180007E9C
0x180007d90  mov     [rsp+168h+var_140], r15
0x180007d95  mov     [rsp+168h+var_148], rbx
0x180007d9a  lea     r9, [rsp+168h+var_E8]
0x180007da2  lea     r8, [rsp+168h+var_138]
0x180007da7  lea     rdx, [rsp+168h+var_128]
0x180007dac  lea     rcx, [rsp+168h+var_130]
0x180007db1  call    ?AttestShs@AttestationHandler@Plugin@Client@HostGuardian@Microsoft@@AEAA?AW4AttestationError@@AEBV?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@AEAW4ShsAttestationFlag@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@8@PEAIPEAPEAUAttestationResult@@@Z; Microsoft::HostGuardian::Client::Plugin::AttestationHandler::AttestShs(std::vector<AttestationResultType> const &,ShsAttestationFlag &,std::wstring &,uint *,AttestationResult * *)
0x180007db6  mov     ebx, eax
0x180007db8  mov     r14d, [rsp+168h+var_138]
0x180007dbd  jmp     short loc_180007E0F
0x180007dbf  movdqu  [rsp+168h+var_10C], xmm0
0x180007dc5  mov     [rsp+168h+var_FC], 0
0x180007dcd  mov     [rsp+168h+var_F4], 0
0x180007dd5  mov     [rsp+168h+var_110], 28h ; '('
0x180007ddd  mov     rax, [rsp+168h+var_128]
0x180007de2  mov     [rsp+168h+var_F0], rax
0x180007de7  mov     rcx, [rsp+168h+var_120]
0x180007dec  sub     rcx, rax
0x180007def  sar     rcx, 2
0x180007df3  mov     [rsp+168h+var_F8], ecx
0x180007df7  mov     r9, r15
0x180007dfa  mov     r8, rbx
0x180007dfd  lea     rdx, [rsp+168h+var_110]
0x180007e02  mov     ecx, 1
0x180007e07  call    cs:__imp_Attest
0x180007e0d  mov     ebx, eax
0x180007e0f  mov     r15d, 84FE1001h
0x180007e15  cmp     ebx, r15d
0x180007e18  jnz     short loc_180007E8C
0x180007e1a  mov     rcx, [rsp+168h]; this
0x180007e22  mov     r9d, r15d; char *
0x180007e25  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x180007e2c  mov     edx, 89h; void *
0x180007e31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007e36  nop
0x180007e37  lea     rcx, [rsp+168h+var_E8]
0x180007e3f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007e44  nop
0x180007e45  lea     rcx, [rsp+168h+var_128]
0x180007e4a  call    ??1?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@QEAA@XZ; std::vector<AttestationResultType>::~vector<AttestationResultType>(void)
0x180007e4f  nop
0x180007e50  lea     rcx, [rsp+168h+var_70]
0x180007e58  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180007e5d  lea     rcx, [rsp+168h+var_88]
0x180007e65  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180007e6a  lea     rcx, [rsp+168h+var_A8]
0x180007e72  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007e77  lea     rcx, [rsp+168h+var_C8]
0x180007e7f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007e84  mov     eax, r15d
0x180007e87  jmp     loc_180007F4F
0x180007e8c  mov     r9, [rsp+168h+var_D0]
0x180007e94  mov     r8, [rsp+168h+var_D8]
0x180007e9c  test    rsi, rsi
0x180007e9f  jz      short loc_180007EA4
0x180007ea1  mov     [rsi], r14d
0x180007ea4  test    r8, r8
0x180007ea7  jz      short loc_180007ED5
0x180007ea9  test    rdi, rdi
0x180007eac  jz      short loc_180007ED5
0x180007eae  lea     rdx, [rsp+168h+var_E8]
0x180007eb6  cmp     r9, 7
0x180007eba  cmova   rdx, qword ptr [rsp+168h+var_E8]
0x180007ec3  lea     rcx, [rsp+168h+var_130]
0x180007ec8  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x180007ecd  mov     rax, [rsp+168h+var_130]
0x180007ed2  mov     [rdi], rax
0x180007ed5  lea     rcx, [rsp+168h+var_E8]
0x180007edd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007ee2  nop
0x180007ee3  lea     rcx, [rsp+168h+var_128]
0x180007ee8  call    ??1?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@QEAA@XZ; std::vector<AttestationResultType>::~vector<AttestationResultType>(void)
0x180007eed  nop
0x180007eee  lea     rcx, [rsp+168h+var_70]
0x180007ef6  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180007efb  lea     rcx, [rsp+168h+var_88]
0x180007f03  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180007f08  lea     rcx, [rsp+168h+var_A8]
0x180007f10  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007f15  lea     rcx, [rsp+168h+var_C8]
0x180007f1d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007f22  mov     eax, ebx
0x180007f24  jmp     short loc_180007F4F
0x180007f26  mov     rcx, [rsp+168h]; this
0x180007f2e  mov     ebx, 80070057h
0x180007f33  mov     r9d, ebx; char *
0x180007f36  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x180007f3d  mov     edx, 73h ; 's'; void *
0x180007f42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f47  mov     eax, ebx
0x180007f49  jmp     short loc_180007F4F
0x180007f4b  mov     eax, [rsp+168h+var_138]
0x180007f4f  mov     rcx, [rsp+168h+var_38]
0x180007f57  xor     rcx, rsp; StackCookie
0x180007f5a  call    __security_check_cookie
0x180007f5f  mov     rbx, [rsp+168h+arg_0]
0x180007f67  add     rsp, 140h
0x180007f6e  pop     r15
0x180007f70  pop     r14
0x180007f72  pop     r12
0x180007f74  pop     rdi
0x180007f75  pop     rsi
0x180007f76  retn
```
