# OleClassInfoVerbIterator::Next(IOleVerb * *)

- ea: `0x1800cb430`
- end: `0x1800cb711`
- name: `?Next@OleClassInfoVerbIterator@@UEAAJPEAPEAUIOleVerb@@@Z`
- size: `737`
- prototype: `HRESULT __fastcall(OleClassInfoVerbIterator *this, IOleVerb **ppVerb)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001217c`
- `0x180033bb0`
- `0x180099f40`
- `0x18009a004`
- `0x18009a0e8`
- `0x1800c958c`
- `0x1800cb430`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb4e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb526`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb5d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb5f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb634`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb6c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb6e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb4e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb526`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb5d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb5f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb634`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb6c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cb6e1`

## string_xrefs

- `0x1800cb477`: `com\ole32\oleregistrationenumeration\oleregistrationenumeration.cpp`
- `0x1800cb4bf`: `com\ole32\oleregistrationenumeration\oleregistrationenumeration.cpp`
- `0x1800cb50e`: `com\ole32\oleregistrationenumeration\oleregistrationenumeration.cpp`
- `0x1800cb5b0`: `com\ole32\oleregistrationenumeration\oleregistrationenumeration.cpp`
- `0x1800cb621`: `com\ole32\oleregistrationenumeration\oleregistrationenumeration.cpp`

## pseudocode

```c
__int64 __fastcall OleClassInfoVerbIterator::Next(OleClassInfoVerbIterator *this, IOleVerb **ppVerb)
{
  Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *m_ptr; // rcx
  HRESULT v5; // ebx
  unsigned int v6; // edx
  Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *v7; // rcx
  struct IUnknownVtbl *lpVtbl; // rax
  HRESULT v9; // eax
  Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *v10; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  HRESULT v12; // eax
  struct IUnknownVtbl *v13; // rax
  HRESULT v14; // r15d
  bool v15; // r8
  bool v16; // r9
  IInspectable *v17; // rbx
  HRESULT hrState; // edi
  IInspectable *v19; // rcx
  HRESULT v20; // eax
  HRESULT String; // eax
  unsigned int v22; // edx
  HSTRING__ *hstr; // [rsp+30h] [rbp-48h] BYREF
  HSTRING__ *v25; // [rsp+38h] [rbp-40h] BYREF
  IResourceContext *p_verbPropValue; // [rsp+40h] [rbp-38h] BYREF
  IInspectable *pI; // [rsp+48h] [rbp-30h] BYREF
  RoVariant v28; // [rsp+50h] [rbp-28h] BYREF
  RoVariant verbPropValue; // [rsp+60h] [rbp-18h] BYREF
  void *retaddr; // [rsp+B8h] [rbp+40h]
  unsigned __int8 hasCurrent; // [rsp+C0h] [rbp+48h] BYREF
  Microsoft::WRL::Wrappers::HString verbId; // [rsp+C8h] [rbp+50h] BYREF
  Microsoft::WRL::Wrappers::HString verbValue; // [rsp+D0h] [rbp+58h] BYREF
  wil::com_ptr_t<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,wil::err_returncode_policy> verbPair; // [rsp+D8h] [rbp+60h] BYREF

  *ppVerb = 0;
  m_ptr = this->m_verbIterator.m_ptr;
  hasCurrent = 0;
  v5 = ((__int64 (__fastcall *)(Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *, unsigned __int8 *))m_ptr->lpVtbl[2].AddRef)(
         m_ptr,
         &hasCurrent);
  if ( v5 >= 0 )
  {
    if ( !hasCurrent )
    {
      v5 = -2147024637;
      v6 = 1004;
      goto LABEL_3;
    }
    v7 = this->m_verbIterator.m_ptr;
    lpVtbl = v7->lpVtbl;
    verbPair.m_ptr = 0;
    v9 = ((__int64 (__fastcall *)(Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *, wil::com_ptr_t<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,wil::err_returncode_policy> *))lpVtbl[2].QueryInterface)(
           v7,
           &verbPair);
    v5 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        0x3EFu,
        "com\\ole32\\oleregistrationenumeration\\oleregistrationenumeration.cpp",
        v9);
LABEL_22:
      wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&verbPair);
      return (unsigned int)v5;
    }
    v10 = verbPair.m_ptr;
    QueryInterface = verbPair.m_ptr->lpVtbl[2].QueryInterface;
    WindowsDeleteString(0);
    verbId.hstr_ = 0;
    v12 = ((__int64 (__fastcall *)(Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *, Microsoft::WRL::Wrappers::HString *))QueryInterface)(
            v10,
            &verbId);
    v5 = v12;
    if ( v12 >= 0 )
    {
      verbPropValue._pI = 0;
      verbPropValue._hrState = 0;
      v13 = verbPair.m_ptr->lpVtbl;
      p_verbPropValue = (IResourceContext *)&verbPropValue;
      pI = 0;
      v14 = ((__int64 (__fastcall *)(Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *, IInspectable **))v13[2].AddRef)(
              verbPair.m_ptr,
              &pI);
      RoVariant::RoVariant(&v28, pI, v15, v16);
      v17 = v28._pI;
      hrState = v28._hrState;
      v28._pI = 0;
      v28._hrState = 0;
      RoVariant::~RoVariant(&v28);
      v19 = verbPropValue._pI;
      verbPropValue._pI = v17;
      v20 = verbPropValue._hrState;
      v28._pI = v19;
      verbPropValue._hrState = hrState;
      v28._hrState = v20;
      RoVariant::~RoVariant(&v28);
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          0x3F5u,
          "com\\ole32\\oleregistrationenumeration\\oleregistrationenumeration.cpp",
          v14);
        RoVariant::~RoVariant(&verbPropValue);
        WindowsDeleteString(verbId.hstr_);
        v5 = v14;
        goto LABEL_21;
      }
      v28 = verbPropValue;
      WindowsDeleteString(0);
      verbValue.hstr_ = 0;
      String = RoVariant::Accessor::GetString((RoVariant::Accessor *)&v28, &verbValue.hstr_);
      v5 = String;
      if ( String >= 0 )
      {
        String = ((__int64 (__fastcall *)(Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *, unsigned __int8 *))this->m_verbIterator.m_ptr->lpVtbl[2].Release)(
                   this->m_verbIterator.m_ptr,
                   &hasCurrent);
        v5 = String;
        if ( String >= 0 )
        {
          hstr = verbValue.hstr_;
          v25 = verbId.hstr_;
          p_verbPropValue = this->m_resourceContext.m_ptr;
          v28._pI = (IInspectable *)this->m_resourceManager.m_ptr;
          String = Microsoft::WRL::Details::MakeAndInitialize<OleClassInfoVerb,IOleVerb,IMrtResourceManager *,IResourceContext *,HSTRING__ *,HSTRING__ *>(
                     ppVerb,
                     (IMrtResourceManager **)&v28,
                     &p_verbPropValue,
                     &v25,
                     &hstr);
          v5 = String;
          if ( String >= 0 )
          {
            WindowsDeleteString(verbValue.hstr_);
            verbValue.hstr_ = 0;
            RoVariant::~RoVariant(&verbPropValue);
            WindowsDeleteString(verbId.hstr_);
            v5 = 0;
            goto LABEL_21;
          }
          v22 = 1020;
        }
        else
        {
          v22 = 1018;
        }
      }
      else
      {
        v22 = 1016;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        v22,
        "com\\ole32\\oleregistrationenumeration\\oleregistrationenumeration.cpp",
        String);
      WindowsDeleteString(verbValue.hstr_);
      verbValue.hstr_ = 0;
      RoVariant::~RoVariant(&verbPropValue);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        0x3F2u,
        "com\\ole32\\oleregistrationenumeration\\oleregistrationenumeration.cpp",
        v12);
    }
    WindowsDeleteString(verbId.hstr_);
LABEL_21:
    verbId.hstr_ = 0;
    goto LABEL_22;
  }
  v6 = 1003;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    v6,
    "com\\ole32\\oleregistrationenumeration\\oleregistrationenumeration.cpp",
    v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800cb430  push    rbp
0x1800cb432  push    rbx
0x1800cb433  push    rsi
0x1800cb434  push    rdi
0x1800cb435  push    r12
0x1800cb437  push    r13
0x1800cb439  push    r14
0x1800cb43b  push    r15
0x1800cb43d  mov     rbp, rsp
0x1800cb440  sub     rsp, 78h
0x1800cb444  xor     r13d, r13d
0x1800cb447  mov     r14, this
0x1800cb44a  mov     [ppVerb], r13
0x1800cb44d  mov     r12, ppVerb
0x1800cb450  mov     this, [this+20h]
0x1800cb454  lea     ppVerb, [rbp+hasCurrent]
0x1800cb458  mov     [rbp+hasCurrent], r13b
0x1800cb45c  mov     rax, [this]
0x1800cb45f  mov     rax, [rax+38h]
0x1800cb463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb468  mov     ebx, eax
0x1800cb46a  test    eax, eax
0x1800cb46c  jns     short loc_1800CB48B
0x1800cb46e  mov     edx, 3EBh; lineNumber
0x1800cb473  mov     this, [rbp+40h]; callerReturnAddress
0x1800cb477  lea     r8, aComOle32Olereg; "com\\ole32\\oleregistrationenumeration"...
0x1800cb47e  mov     r9d, ebx; hr
0x1800cb481  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb486  jmp     loc_1800CB6FD
0x1800cb48b  cmp     [rbp+hasCurrent], r13b
0x1800cb48f  jnz     short loc_1800CB49D
0x1800cb491  mov     ebx, 80070103h
0x1800cb496  mov     edx, 3ECh
0x1800cb49b  jmp     short loc_1800CB473
0x1800cb49d  mov     this, [r14+20h]
0x1800cb4a1  lea     ppVerb, [rbp+verbPair]
0x1800cb4a5  mov     rax, [this]
0x1800cb4a8  mov     [rbp+verbPair.m_ptr], r13
0x1800cb4ac  mov     rax, [rax+30h]
0x1800cb4b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb4b5  mov     ebx, eax
0x1800cb4b7  test    eax, eax
0x1800cb4b9  jns     short loc_1800CB4D8
0x1800cb4bb  mov     this, [rbp+40h]; callerReturnAddress
0x1800cb4bf  lea     r8, aComOle32Olereg; "com\\ole32\\oleregistrationenumeration"...
0x1800cb4c6  mov     r9d, eax; hr
0x1800cb4c9  mov     edx, 3EFh; lineNumber
0x1800cb4ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb4d3  jmp     loc_1800CB6F4
0x1800cb4d8  mov     rbx, [rbp+verbPair.m_ptr]
0x1800cb4dc  xor     ecx, ecx; string
0x1800cb4de  mov     rax, [rbx]
0x1800cb4e1  mov     rdi, [rax+30h]
0x1800cb4e5  call    cs:__imp_WindowsDeleteString
0x1800cb4ec  nop     dword ptr [rax+rax+00h]
0x1800cb4f1  lea     ppVerb, [rbp+verbId]
0x1800cb4f5  mov     [rbp+verbId.hstr_], r13
0x1800cb4f9  mov     this, rbx
0x1800cb4fc  mov     rax, rdi
0x1800cb4ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb504  mov     ebx, eax
0x1800cb506  test    eax, eax
0x1800cb508  jns     short loc_1800CB537
0x1800cb50a  mov     this, [rbp+40h]; callerReturnAddress
0x1800cb50e  lea     r8, aComOle32Olereg; "com\\ole32\\oleregistrationenumeration"...
0x1800cb515  mov     r9d, eax; hr
0x1800cb518  mov     edx, 3F2h; lineNumber
0x1800cb51d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb522  mov     this, [rbp+verbId.hstr_]; string
0x1800cb526  call    cs:__imp_WindowsDeleteString
0x1800cb52d  nop     dword ptr [rax+rax+00h]
0x1800cb532  jmp     loc_1800CB6F0
0x1800cb537  mov     this, [rbp+verbPair.m_ptr]
0x1800cb53b  lea     ppVerb, [rbp+verbPropValue]
0x1800cb53f  mov     [rbp+verbPropValue._pI], r13
0x1800cb543  mov     [rbp+verbPropValue._hrState], r13d
0x1800cb547  mov     rax, [this]
0x1800cb54a  mov     [rbp+var_38], ppVerb
0x1800cb54e  lea     ppVerb, [rbp+pI]
0x1800cb552  mov     [rbp+pI], r13
0x1800cb556  mov     rax, [rax+38h]
0x1800cb55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb55f  mov     ppVerb, [rbp+pI]; pI
0x1800cb563  lea     this, [rbp+var_28]; this
0x1800cb567  mov     rsi, [rbp+var_38]
0x1800cb56b  mov     r15d, eax
0x1800cb56e  call    ??0RoVariant@@AEAA@PEAUIInspectable@@_N1@Z; RoVariant::RoVariant(IInspectable *,bool,bool)
0x1800cb573  mov     rbx, [rbp+var_28._pI]
0x1800cb577  lea     this, [rbp+var_28]; this
0x1800cb57b  mov     edi, [rbp+var_28._hrState]
0x1800cb57e  mov     [rbp+var_28._pI], r13
0x1800cb582  mov     [rbp+var_28._hrState], r13d
0x1800cb586  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1800cb58b  mov     this, [rsi]
0x1800cb58e  mov     [rsi], rbx
0x1800cb591  mov     eax, [rsi+8]
0x1800cb594  mov     [rbp+var_28._pI], this
0x1800cb598  lea     this, [rbp+var_28]; this
0x1800cb59c  mov     [rsi+8], edi
0x1800cb59f  mov     [rbp+var_28._hrState], eax
0x1800cb5a2  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1800cb5a7  test    r15d, r15d
0x1800cb5aa  jns     short loc_1800CB5E5
0x1800cb5ac  mov     this, [rbp+40h]; callerReturnAddress
0x1800cb5b0  lea     r8, aComOle32Olereg; "com\\ole32\\oleregistrationenumeration"...
0x1800cb5b7  mov     r9d, r15d; hr
0x1800cb5ba  mov     edx, 3F5h; lineNumber
0x1800cb5bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb5c4  lea     this, [rbp+verbPropValue]; this
0x1800cb5c8  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1800cb5cd  mov     this, [rbp+verbId.hstr_]; string
0x1800cb5d1  call    cs:__imp_WindowsDeleteString
0x1800cb5d8  nop     dword ptr [rax+rax+00h]
0x1800cb5dd  mov     ebx, r15d
0x1800cb5e0  jmp     loc_1800CB6F0
0x1800cb5e5  mov     rax, [rbp+verbPropValue._pI]
0x1800cb5e9  xor     ecx, ecx; string
0x1800cb5eb  mov     [rbp+var_28._pI], rax
0x1800cb5ef  mov     eax, [rbp+verbPropValue._hrState]
0x1800cb5f2  mov     [rbp+var_28._hrState], eax
0x1800cb5f5  call    cs:__imp_WindowsDeleteString
0x1800cb5fc  nop     dword ptr [rax+rax+00h]
0x1800cb601  lea     ppVerb, [rbp+verbValue]; value
0x1800cb605  mov     [rbp+verbValue.hstr_], r13
0x1800cb609  lea     this, [rbp+var_28]; this
0x1800cb60d  call    ?GetString@Accessor@RoVariant@@QEBAJPEAPEAUHSTRING__@@@Z; RoVariant::Accessor::GetString(HSTRING__ * *)
0x1800cb612  mov     ebx, eax
0x1800cb614  test    eax, eax
0x1800cb616  jns     short loc_1800CB652
0x1800cb618  mov     edx, 3F8h; lineNumber
0x1800cb61d  mov     this, [rbp+40h]; callerReturnAddress
0x1800cb621  lea     r8, aComOle32Olereg; "com\\ole32\\oleregistrationenumeration"...
0x1800cb628  mov     r9d, eax; hr
0x1800cb62b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb630  mov     this, [rbp+verbValue.hstr_]; string
0x1800cb634  call    cs:__imp_WindowsDeleteString
0x1800cb63b  nop     dword ptr [rax+rax+00h]
0x1800cb640  lea     this, [rbp+verbPropValue]; this
0x1800cb644  mov     [rbp+verbValue.hstr_], r13
0x1800cb648  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1800cb64d  jmp     loc_1800CB522
0x1800cb652  mov     this, [r14+20h]
0x1800cb656  lea     ppVerb, [rbp+hasCurrent]
0x1800cb65a  mov     rax, [this]
0x1800cb65d  mov     rax, [rax+40h]
0x1800cb661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb666  mov     ebx, eax
0x1800cb668  test    eax, eax
0x1800cb66a  jns     short loc_1800CB673
0x1800cb66c  mov     edx, 3FAh
0x1800cb671  jmp     short loc_1800CB61D
0x1800cb673  mov     rax, [rbp+verbValue.hstr_]
0x1800cb677  lea     r9, [rbp+var_40]; <args_2>
0x1800cb67b  mov     [rbp+var_48], rax
0x1800cb67f  lea     r8, [rbp+var_38]; <args_1>
0x1800cb683  mov     rax, [rbp+verbId.hstr_]
0x1800cb687  lea     ppVerb, [rbp+var_28]; <args_0>
0x1800cb68b  mov     [rbp+var_40], rax
0x1800cb68f  mov     this, r12; result
0x1800cb692  mov     rax, [r14+18h]
0x1800cb696  mov     [rbp+var_38], rax
0x1800cb69a  mov     rax, [r14+10h]
0x1800cb69e  mov     [rbp+var_28._pI], rax
0x1800cb6a2  lea     rax, [rbp+var_48]
0x1800cb6a6  mov     [rsp+78h+var_58], rax; <args_3>
0x1800cb6ab  call    ??$MakeAndInitialize@VOleClassInfoVerb@@UIOleVerb@@PEAUIMrtResourceManager@@PEAUIResourceContext@@PEAUHSTRING__@@PEAU5@@Details@WRL@Microsoft@@YAJPEAPEAUIOleVerb@@$$QEAPEAUIMrtResourceManager@@$$QEAPEAUIResourceContext@@$$QEAPEAUHSTRING__@@3@Z; Microsoft::WRL::Details::MakeAndInitialize<OleClassInfoVerb,IOleVerb,IMrtResourceManager *,IResourceContext *,HSTRING__ *,HSTRING__ *>(IOleVerb * *,IMrtResourceManager * &&,IResourceContext * &&,HSTRING__ * &&,HSTRING__ * &&)
0x1800cb6b0  mov     ebx, eax
0x1800cb6b2  test    eax, eax
0x1800cb6b4  jns     short loc_1800CB6C0
0x1800cb6b6  mov     edx, 3FCh
0x1800cb6bb  jmp     loc_1800CB61D
0x1800cb6c0  mov     this, [rbp+verbValue.hstr_]; string
0x1800cb6c4  call    cs:__imp_WindowsDeleteString
0x1800cb6cb  nop     dword ptr [rax+rax+00h]
0x1800cb6d0  lea     this, [rbp+verbPropValue]; this
0x1800cb6d4  mov     [rbp+verbValue.hstr_], r13
0x1800cb6d8  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1800cb6dd  mov     this, [rbp+verbId.hstr_]; string
0x1800cb6e1  call    cs:__imp_WindowsDeleteString
0x1800cb6e8  nop     dword ptr [rax+rax+00h]
0x1800cb6ed  mov     ebx, r13d
0x1800cb6f0  mov     [rbp+verbId.hstr_], r13
0x1800cb6f4  lea     this, [rbp+verbPair]; this
0x1800cb6f8  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x1800cb6fd  mov     eax, ebx
0x1800cb6ff  add     rsp, 78h
0x1800cb703  pop     r15
0x1800cb705  pop     r14
0x1800cb707  pop     r13
0x1800cb709  pop     r12
0x1800cb70b  pop     rdi
0x1800cb70c  pop     rsi
0x1800cb70d  pop     rbx
0x1800cb70e  pop     rbp
0x1800cb70f  retn
```
