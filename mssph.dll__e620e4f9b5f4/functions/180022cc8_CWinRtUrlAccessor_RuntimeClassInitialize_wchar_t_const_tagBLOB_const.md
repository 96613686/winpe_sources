# CWinRtUrlAccessor::RuntimeClassInitialize(wchar_t const *,tagBLOB const *)

- ea: `0x180022cc8`
- end: `0x180022fb2`
- name: `?RuntimeClassInitialize@CWinRtUrlAccessor@@QEAAJPEB_WPEBUtagBLOB@@@Z`
- size: `746`
- prototype: `__int64 __fastcall(wchar_t *this, const wchar_t *, struct tagBLOB *)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002250c`

## callees

- `0x180007650`
- `0x180007b80`
- `0x1800080b0`
- `0x180009680`
- `0x18000be20`
- `0x18000c3e4`
- `0x18000cacc`
- `0x18000cde8`
- `0x18000e050`
- `0x18000e7fc`
- `0x18000e89c`
- `0x18000ec40`
- `0x18000fcd0`
- `0x18001469c`
- `0x18001e808`
- `0x180021f14`
- `0x180022418`
- `0x180022cc8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022eab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022eef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022eab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022eef`
- `efswrt!CdplUnprotectSecret` at `0x180022e66`
- `efswrt!CdplUnprotectSecret` at `0x180022e66`

## string_xrefs

- `0x180022d7a`: `onecoreuap\base\appmodel\search\mssph\winrt\winrtaccessor.cpp`
- `0x180022e87`: `onecoreuap\base\appmodel\search\mssph\winrt\winrtaccessor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWinRtUrlAccessor::RuntimeClassInitialize(wchar_t *this, const wchar_t *a2, struct tagBLOB *a3)
{
  int Content; // ebx
  wchar_t v7; // ax
  BYTE *pBlobData; // rbx
  ULONG cbSize; // edi
  void *v10; // rcx
  int v11; // edi
  LPVOID v12; // rbx
  void *v13; // rcx
  struct IStream **v14; // r9
  int v16; // [rsp+20h] [rbp-278h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-270h] BYREF
  wchar_t *v18; // [rsp+30h] [rbp-268h] BYREF
  __int128 v19; // [rsp+38h] [rbp-260h] BYREF
  LPVOID *p_pv; // [rsp+48h] [rbp-250h] BYREF
  tagBLOB v21; // [rsp+50h] [rbp-248h] BYREF
  int v22; // [rsp+60h] [rbp-238h] BYREF
  int v23; // [rsp+68h] [rbp-230h]
  LPVOID v24; // [rsp+70h] [rbp-228h]
  int v25; // [rsp+78h] [rbp-220h]
  void **v26; // [rsp+80h] [rbp-218h] BYREF
  int v27; // [rsp+88h] [rbp-210h]
  _QWORD v28[2]; // [rsp+98h] [rbp-200h] BYREF
  __int64 v29; // [rsp+A8h] [rbp-1F0h]
  _WORD v30[201]; // [rsp+B0h] [rbp-1E8h] BYREF
  unsigned __int16 v31; // [rsp+242h] [rbp-56h]
  int v32; // [rsp+258h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  v18 = this;
  pv = a3;
  v27 = 0;
  v28[1] = v30;
  v29 = 193;
  v30[0] = 0;
  v28[0] = &TLMString<192,64,32767>::`vftable';
  v26 = &CComObjectStackRefCount<CURL>::`vftable';
  v32 = 0;
  try
  {
    CURL::Init((CURL *)&v26, a2, (unsigned int)a3);
    CURL::ParseAccessType((CURL *)&v26);
    if ( v30[196] != 8 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x166,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssph\\winrt\\winrtaccessor.cpp",
        (const char *)0x80070057LL,
        v16);
    Content = 0;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      367,
      "onecoreuap\\base\\appmodel\\search\\mssph\\winrt\\winrtaccessor.cpp");
  }
  CURL::ParsePath((CURL *)&v26);
  if ( !HIDWORD(v29)
    || v31 != HIDWORD(v29)
    && (v31 != HIDWORD(v29) - 1 || (v7 = CLMString::Last((CLMString *)v28), !(unsigned int)IsSlash(v7))) )
  {
    if ( !a3 )
    {
      Content = -2147024809;
      goto LABEL_22;
    }
    v19 = 0;
    pBlobData = a3->pBlobData;
    *((_QWORD *)&v19 + 1) = pBlobData;
    cbSize = a3->cbSize;
    LODWORD(v19) = a3->cbSize;
    v24 = 0;
    v23 = 0;
    v22 = 0;
    v25 = 0;
    if ( IsCDPLEnabled() )
    {
      pv = 0;
      v16 = 0;
      p_pv = &pv;
      *(_QWORD *)&v21.cbSize = 0;
      LOBYTE(v21.pBlobData) = 1;
      Content = CdplUnprotectSecret(pBlobData, cbSize, &v21, &v16);
      wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
      if ( Content < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x183,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssph\\winrt\\winrtaccessor.cpp",
          (const char *)(unsigned int)Content,
          v16);
        v10 = pv;
        pv = 0;
        if ( v10 )
          CoTaskMemFree(v10);
LABEL_21:
        CBlob::Free((CBlob *)&v22);
        goto LABEL_22;
      }
      v11 = v16;
      v12 = pv;
      pv = 0;
      CBlob::Free((CBlob *)&v22);
      v23 = v11;
      v24 = v12;
      *((_QWORD *)&v19 + 1) = v12;
      LODWORD(v19) = v11;
      v13 = pv;
      pv = 0;
      if ( v13 )
        CoTaskMemFree(v13);
    }
    v18 = 0;
    Microsoft::WRL::ComPtr<IStream>::InternalRelease(&v18);
    p_pv = (LPVOID *)(this + 28);
    *(_QWORD *)&v21.cbSize = 0;
    LOBYTE(v21.pBlobData) = 1;
    Content = StoreAppUserBlob::GetContent((StoreAppUserBlob *)&v19, &v21, &v18, v14);
    wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
    if ( !Content )
    {
      *(_QWORD *)&v19 = v18;
      Microsoft::WRL::ComPtr<CWinRtStreamWrapper>::InternalRelease(this + 20);
      Content = Microsoft::WRL::Details::MakeAndInitialize<CWinRtStreamWrapper,CWinRtStreamWrapper,IStream *>(
                  this + 20,
                  &v19);
      if ( Content >= 0 )
        CWinRtUrlAccessor::_ResolveMimeType((CWinRtUrlAccessor *)this, *((const wchar_t **)this + 7));
    }
    Microsoft::WRL::ComPtr<IStream>::InternalRelease(&v18);
    goto LABEL_21;
  }
LABEL_22:
  CComObjectStackRefCount<CURL>::~CComObjectStackRefCount<CURL>(&v26);
  return (unsigned int)Content;
}

```

## disassembly

```asm
0x180022cc8  mov     r11, rsp
0x180022ccb  push    rbx
0x180022ccc  push    rsi
0x180022ccd  push    rdi
0x180022cce  push    r14
0x180022cd0  push    r15
0x180022cd2  sub     rsp, 270h
0x180022cd9  mov     rax, cs:__security_cookie
0x180022ce0  xor     rax, rsp
0x180022ce3  mov     [rsp+298h+var_38], rax
0x180022ceb  mov     r15, r8
0x180022cee  mov     r14, rcx
0x180022cf1  mov     [rsp+298h+var_268], rcx
0x180022cf6  mov     rdi, r8
0x180022cf9  mov     [rsp+298h+pv], r8
0x180022cfe  xor     esi, esi
0x180022d00  mov     [rsp+298h+var_210], esi
0x180022d07  lea     rax, [r11-1E8h]
0x180022d0e  mov     [r11-1F8h], rax
0x180022d15  mov     qword ptr [r11-1F0h], 0C1h
0x180022d20  mov     [rsp+298h+var_1E8], si
0x180022d28  lea     rax, ??_7?$TLMString@$0MA@$0EA@$0HPPP@@@6B@; const TLMString<192,64,32767>::`vftable'
0x180022d2f  mov     [r11-200h], rax
0x180022d36  lea     rax, ??_7?$CComObjectStackRefCount@VCURL@@@@6B@; const CComObjectStackRefCount<CURL>::`vftable'
0x180022d3d  mov     [r11-218h], rax
0x180022d44  mov     [r11-40h], esi
0x180022d48  lea     rcx, [r11-218h]; this
0x180022d4f  call    ?Init@CURL@@QEAAJPEB_WK@Z; CURL::Init(wchar_t const *,ulong)
0x180022d54  lea     rcx, [rsp+298h+var_218]; this
0x180022d5c  call    ?ParseAccessType@CURL@@IEAAXXZ; CURL::ParseAccessType(void)
0x180022d61  cmp     [rsp+298h+var_60], 8
0x180022d6a  jz      short loc_180022D8B
0x180022d6c  mov     rcx, [rsp+298h]; this
0x180022d74  mov     r9d, 80070057h; char *
0x180022d7a  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180022d81  mov     edx, 166h; void *
0x180022d86  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022d8b  mov     ebx, esi
0x180022d8d  jmp     short loc_180022DAA
0x180022d8f  mov     ebx, [rsp+298h+var_278]
0x180022d93  xor     esi, esi
0x180022d95  test    ebx, ebx
0x180022d97  js      loc_180022F84
0x180022d9d  mov     r14, [rsp+298h+var_268]
0x180022da2  mov     rdi, [rsp+298h+pv]
0x180022da7  mov     r15, rdi
0x180022daa  lea     rcx, [rsp+298h+var_218]; this
0x180022db2  call    ?ParsePath@CURL@@QEAAXXZ; CURL::ParsePath(void)
0x180022db7  mov     eax, [rsp+298h+var_1EC]
0x180022dbe  test    eax, eax
0x180022dc0  jz      short loc_180022DF5
0x180022dc2  movzx   ecx, [rsp+298h+var_56]
0x180022dca  cmp     ecx, eax
0x180022dcc  jz      loc_180022F84
0x180022dd2  dec     eax
0x180022dd4  cmp     ecx, eax
0x180022dd6  jnz     short loc_180022DF5
0x180022dd8  lea     rcx, [rsp+298h+var_200]; this
0x180022de0  call    ?Last@CLMString@@QEBA_WXZ; CLMString::Last(void)
0x180022de5  movzx   ecx, ax; wchar_t
0x180022de8  call    ?IsSlash@@YAH_W@Z; IsSlash(wchar_t)
0x180022ded  test    eax, eax
0x180022def  jnz     loc_180022F84
0x180022df5  test    rdi, rdi
0x180022df8  jnz     short loc_180022E04
0x180022dfa  mov     ebx, 80070057h
0x180022dff  jmp     loc_180022F84
0x180022e04  xorps   xmm0, xmm0
0x180022e07  movups  [rsp+298h+var_260], xmm0
0x180022e0c  mov     rbx, [rdi+8]
0x180022e10  mov     qword ptr [rsp+298h+var_260+8], rbx
0x180022e15  mov     edi, [r15]
0x180022e18  mov     dword ptr [rsp+298h+var_260], edi
0x180022e1c  mov     [rsp+298h+var_228], rsi
0x180022e21  mov     [rsp+298h+var_230], esi
0x180022e25  mov     [rsp+298h+var_238], esi
0x180022e29  mov     [rsp+298h+var_220], esi
0x180022e2d  call    ?IsCDPLEnabled@@YA_NXZ; IsCDPLEnabled(void)
0x180022e32  test    al, al
0x180022e34  jz      loc_180022EF5
0x180022e3a  mov     [rsp+298h+pv], rsi
0x180022e3f  mov     [rsp+298h+var_278], esi; int
0x180022e43  lea     rax, [rsp+298h+pv]
0x180022e48  mov     [rsp+298h+var_250], rax
0x180022e4d  mov     qword ptr [rsp+298h+var_248.cbSize], rsi
0x180022e52  mov     byte ptr [rsp+298h+var_248.pBlobData], 1
0x180022e57  lea     r9, [rsp+298h+var_278]
0x180022e5c  lea     r8, [rsp+298h+var_248]
0x180022e61  mov     edx, edi
0x180022e63  mov     rcx, rbx
0x180022e66  call    cs:__imp_CdplUnprotectSecret
0x180022e6c  mov     ebx, eax
0x180022e6e  lea     rcx, [rsp+298h+var_250]
0x180022e73  call    ??1?$out_param_t@V?$unique_ptr@_WU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180022e78  test    ebx, ebx
0x180022e7a  jns     short loc_180022EB6
0x180022e7c  mov     rcx, [rsp+298h]; this
0x180022e84  mov     r9d, ebx; char *
0x180022e87  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180022e8e  mov     edx, 183h; void *
0x180022e93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022e98  mov     rcx, [rsp+298h+pv]; pv
0x180022e9d  mov     [rsp+298h+pv], rsi
0x180022ea2  test    rcx, rcx
0x180022ea5  jz      loc_180022F79
0x180022eab  call    cs:__imp_CoTaskMemFree
0x180022eb1  jmp     loc_180022F79
0x180022eb6  mov     edi, [rsp+298h+var_278]
0x180022eba  mov     rbx, [rsp+298h+pv]
0x180022ebf  mov     [rsp+298h+pv], rsi
0x180022ec4  lea     rcx, [rsp+298h+var_238]; this
0x180022ec9  call    ?Free@CBlob@@AEAAXXZ; CBlob::Free(void)
0x180022ece  mov     [rsp+298h+var_230], edi
0x180022ed2  mov     [rsp+298h+var_228], rbx
0x180022ed7  mov     qword ptr [rsp+298h+var_260+8], rbx
0x180022edc  mov     dword ptr [rsp+298h+var_260], edi
0x180022ee0  mov     rcx, [rsp+298h+pv]; pv
0x180022ee5  mov     [rsp+298h+pv], rsi
0x180022eea  test    rcx, rcx
0x180022eed  jz      short loc_180022EF5
0x180022eef  call    cs:__imp_CoTaskMemFree
0x180022ef5  mov     [rsp+298h+var_268], rsi
0x180022efa  lea     rcx, [rsp+298h+var_268]
0x180022eff  call    ?InternalRelease@?$ComPtr@UIStream@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IStream>::InternalRelease(void)
0x180022f04  lea     rdi, [r14+38h]
0x180022f08  mov     [rsp+298h+var_250], rdi
0x180022f0d  mov     qword ptr [rsp+298h+var_248.cbSize], rsi
0x180022f12  mov     byte ptr [rsp+298h+var_248.pBlobData], 1
0x180022f17  lea     r8, [rsp+298h+var_268]; wchar_t **
0x180022f1c  lea     rdx, [rsp+298h+var_248]; struct tagBLOB *
0x180022f21  lea     rcx, [rsp+298h+var_260]; this
0x180022f26  call    ?GetContent@StoreAppUserBlob@@YAJPEBUtagBLOB@@PEAPEA_WPEAPEAUIStream@@@Z; StoreAppUserBlob::GetContent(tagBLOB const *,wchar_t * *,IStream * *)
0x180022f2b  mov     ebx, eax
0x180022f2d  lea     rcx, [rsp+298h+var_250]
0x180022f32  call    ??1?$out_param_t@V?$unique_ptr@_WU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180022f37  test    ebx, ebx
0x180022f39  jnz     short loc_180022F6E
0x180022f3b  mov     rax, [rsp+298h+var_268]
0x180022f40  mov     qword ptr [rsp+298h+var_260], rax
0x180022f45  lea     rcx, [r14+28h]
0x180022f49  call    ?InternalRelease@?$ComPtr@VCWinRtStreamWrapper@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CWinRtStreamWrapper>::InternalRelease(void)
0x180022f4e  lea     rdx, [rsp+298h+var_260]
0x180022f53  lea     rcx, [r14+28h]
0x180022f57  call    ??$MakeAndInitialize@VCWinRtStreamWrapper@@V1@PEAUIStream@@@Details@WRL@Microsoft@@YAJPEAPEAVCWinRtStreamWrapper@@$$QEAPEAUIStream@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CWinRtStreamWrapper,CWinRtStreamWrapper,IStream *>(CWinRtStreamWrapper * *,IStream * &&)
0x180022f5c  mov     ebx, eax
0x180022f5e  test    eax, eax
0x180022f60  js      short loc_180022F6E
0x180022f62  mov     rdx, [rdi]; wchar_t *
0x180022f65  mov     rcx, r14; this
0x180022f68  call    ?_ResolveMimeType@CWinRtUrlAccessor@@AEAAXPEB_W@Z; CWinRtUrlAccessor::_ResolveMimeType(wchar_t const *)
0x180022f6d  nop
0x180022f6e  lea     rcx, [rsp+298h+var_268]
0x180022f73  call    ?InternalRelease@?$ComPtr@UIStream@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IStream>::InternalRelease(void)
0x180022f78  nop
0x180022f79  lea     rcx, [rsp+298h+var_238]; this
0x180022f7e  call    ?Free@CBlob@@AEAAXXZ; CBlob::Free(void)
0x180022f83  nop
0x180022f84  lea     rcx, [rsp+298h+var_218]
0x180022f8c  call    ??1?$CComObjectStackRefCount@VCURL@@@@QEAA@XZ; CComObjectStackRefCount<CURL>::~CComObjectStackRefCount<CURL>(void)
0x180022f91  mov     eax, ebx
0x180022f93  mov     rcx, [rsp+298h+var_38]
0x180022f9b  xor     rcx, rsp; StackCookie
0x180022f9e  call    __security_check_cookie
0x180022fa3  add     rsp, 270h
0x180022faa  pop     r15
0x180022fac  pop     r14
0x180022fae  pop     rdi
0x180022faf  pop     rsi
0x180022fb0  pop     rbx
0x180022fb1  retn
```
