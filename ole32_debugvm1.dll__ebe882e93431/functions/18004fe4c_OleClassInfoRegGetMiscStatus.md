# OleClassInfoRegGetMiscStatus

- ea: `0x18004fe4c`
- end: `0x1800500ba`
- name: `OleClassInfoRegGetMiscStatus`
- size: `622`
- prototype: `HRESULT __fastcall(IOleClassInfo *pOleClassInfo, unsigned int dwAspect, unsigned int *pdwStatus)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ae0c`

## callees

- `0x18001775c`
- `0x1800185ec`
- `0x180019c4c`
- `0x180019eec`
- `0x18001b0e4`
- `0x180037c1c`
- `0x18004fe4c`
- `0x1800500c0`
- `0x180052390`
- `0x180098a48`
- `0x180098bc0`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18004fffe`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180050069`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18004fffe`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180050069`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004ff0a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004ff0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ffe1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050011`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050082`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ffe1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050011`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050082`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004ffef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005005a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004ffef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005005a`

## string_xrefs

- `0x18004ffc4`: `com\ole32\ole232\stdimpl\olereg.cpp`

## pseudocode

```c
__int64 __fastcall OleClassInfoRegGetMiscStatus(
        IOleClassInfo *pOleClassInfo,
        unsigned int dwAspect,
        unsigned int *pdwStatus)
{
  struct IUnknownVtbl *lpVtbl; // rax
  Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> *m_ptr; // rbx
  unsigned __int64 v8; // rcx
  struct IUnknownVtbl *v9; // rdi
  signed int v10; // eax
  unsigned int v11; // eax
  int v12; // eax
  IInspectable *pI; // rsi
  int v14; // r14d
  bool v15; // r8
  bool v16; // r9
  HSTRING__ *v17; // rbx
  int v18; // edi
  HSTRING__ *v19; // rcx
  int v20; // eax
  HRESULT String; // eax
  unsigned int v22; // ebx
  const wchar_t *StringRawBuffer; // rax
  int v24; // eax
  HSTRING__ *v25; // rcx
  struct IUnknownVtbl *v27; // rax
  int v28; // eax
  HSTRING__ *v29; // rcx
  const wchar_t *v30; // rax
  int v31; // eax
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > miscStatus; // [rsp+20h] [rbp-59h] BYREF
  int v33; // [rsp+28h] [rbp-51h]
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > miscStatusDefault; // [rsp+30h] [rbp-49h] BYREF
  wil::com_ptr_t<Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *>,wil::err_returncode_policy> miscStatusMap; // [rsp+38h] [rbp-41h] BYREF
  RoVariant::Accessor v36; // [rsp+40h] [rbp-39h] BYREF
  RoVariant miscStatusPropValue; // [rsp+50h] [rbp-29h] BYREF
  Microsoft::WRL::Wrappers::HStringReference v38; // [rsp+60h] [rbp-19h] BYREF
  wchar_t aspectString[12]; // [rsp+80h] [rbp+7h] BYREF
  void *retaddr; // [rsp+D8h] [rbp+5Fh]

  lpVtbl = pOleClassInfo->lpVtbl;
  miscStatusMap.m_ptr = 0;
  if ( ((int (__fastcall *)(IOleClassInfo *, wil::com_ptr_t<Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *>,wil::err_returncode_policy> *))lpVtbl[4].Release)(
         pOleClassInfo,
         &miscStatusMap) >= 0 )
  {
    memset(aspectString, 0, 22);
    StringCchPrintfW(aspectString, 0xBu, L"%ld", dwAspect);
    m_ptr = miscStatusMap.m_ptr;
    miscStatusPropValue._pI = 0;
    v8 = -1;
    miscStatusPropValue._hrState = 0;
    LODWORD(miscStatus.m_ptr) = 0;
    v9 = miscStatusMap.m_ptr->lpVtbl;
    v36._pI = (IInspectable *)&miscStatusPropValue;
    *(_QWORD *)&v36._hrState = 0;
    do
      ++v8;
    while ( aspectString[v8] );
    v10 = ULongLongToUInt(v8, (unsigned int *)&miscStatus);
    if ( v10 < 0 )
    {
      RaiseException(v10, 1u, 0, 0);
      __debugbreak();
    }
    v11 = Microsoft::WRL::Wrappers::HStringReference::AddOne((const unsigned int)miscStatus.m_ptr);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v38, aspectString, v11, (unsigned int)miscStatus.m_ptr);
    v12 = ((__int64 (__fastcall *)(Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> *, HSTRING__ *, HRESULT *))v9[2].QueryInterface)(
            m_ptr,
            v38.hstr_,
            &v36._hrState);
    pI = v36._pI;
    v14 = v12;
    v38.hstr_ = 0;
    RoVariant::RoVariant((RoVariant *)&miscStatus, *(IInspectable **)&v36._hrState, v15, v16);
    v17 = miscStatus.m_ptr;
    v18 = v33;
    miscStatus.m_ptr = 0;
    v33 = 0;
    RoVariant::~RoVariant((RoVariant *)&miscStatus);
    v19 = (HSTRING__ *)pI->lpVtbl;
    pI->lpVtbl = (struct IUnknownVtbl *)v17;
    v20 = (int)pI[1].lpVtbl;
    miscStatus.m_ptr = v19;
    LODWORD(pI[1].lpVtbl) = v18;
    v33 = v20;
    RoVariant::~RoVariant((RoVariant *)&miscStatus);
    if ( v14 >= 0 )
    {
      v36 = (RoVariant::Accessor)miscStatusPropValue;
      miscStatus.m_ptr = 0;
      String = RoVariant::Accessor::GetString(&v36, &miscStatus.m_ptr);
      v22 = String;
      if ( String >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(miscStatus.m_ptr, 0);
        v24 = wcstol(StringRawBuffer, 0, 10);
        v25 = miscStatus.m_ptr;
        *pdwStatus = v24;
        if ( v25 )
          WindowsDeleteString(v25);
        v22 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(retaddr, 0x25Cu, "com\\ole32\\ole232\\stdimpl\\olereg.cpp", String);
        if ( miscStatus.m_ptr )
          WindowsDeleteString(miscStatus.m_ptr);
      }
      RoVariant::~RoVariant(&miscStatusPropValue);
      wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&miscStatusMap);
      return v22;
    }
    RoVariant::~RoVariant(&miscStatusPropValue);
  }
  v27 = pOleClassInfo->lpVtbl;
  miscStatusDefault.m_ptr = 0;
  v28 = ((__int64 (__fastcall *)(IOleClassInfo *, wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > *))v27[4].AddRef)(
          pOleClassInfo,
          &miscStatusDefault);
  v29 = miscStatusDefault.m_ptr;
  if ( v28 < 0 )
  {
    *pdwStatus = 0;
  }
  else
  {
    v30 = WindowsGetStringRawBuffer(miscStatusDefault.m_ptr, 0);
    v31 = wcstol(v30, 0, 10);
    v29 = miscStatusDefault.m_ptr;
    *pdwStatus = v31;
  }
  if ( v29 )
    WindowsDeleteString(v29);
  wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&miscStatusMap);
  return 0;
}

```

## disassembly

```asm
0x18004fe4c  mov     [rsp-8+arg_18], rbx
0x18004fe51  push    rbp
0x18004fe52  push    rsi
0x18004fe53  push    rdi
0x18004fe54  push    r12
0x18004fe56  push    r13
0x18004fe58  push    r14
0x18004fe5a  push    r15
0x18004fe5c  lea     rbp, [rsp-27h]
0x18004fe61  sub     rsp, 0A0h
0x18004fe68  mov     rax, cs:__security_cookie
0x18004fe6f  xor     rax, rsp
0x18004fe72  mov     [rbp+57h+var_38], rax
0x18004fe76  mov     rax, [pOleClassInfo]
0x18004fe79  mov     ebx, dwAspect
0x18004fe7b  xor     r13d, r13d
0x18004fe7e  lea     rdx, [rbp+57h+miscStatusMap]
0x18004fe82  mov     r12, pdwStatus
0x18004fe85  mov     [rbp+57h+miscStatusMap.m_ptr], r13
0x18004fe89  mov     r15, pOleClassInfo
0x18004fe8c  mov     rax, [rax+70h]
0x18004fe90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fe95  test    eax, eax
0x18004fe97  js      loc_180050039
0x18004fe9d  xor     eax, eax
0x18004fe9f  lea     pdwStatus, aLd; "%ld"
0x18004fea6  xorps   xmm0, xmm0
0x18004fea9  lea     pOleClassInfo, [rbp+57h+aspectString]; pszDest
0x18004fead  movups  xmmword ptr [rbp+57h+aspectString], xmm0
0x18004feb1  mov     r9d, ebx
0x18004feb4  mov     qword ptr [rbp+57h+aspectString+0Eh], rax
0x18004feb8  lea     dwAspect, [rax+0Bh]; cchDest
0x18004febb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004fec0  mov     rbx, [rbp+57h+miscStatusMap.m_ptr]
0x18004fec4  lea     rax, [rbp+57h+miscStatusPropValue]
0x18004fec8  mov     [rbp+57h+miscStatusPropValue._pI], r13
0x18004fecc  or      pOleClassInfo, 0FFFFFFFFFFFFFFFFh
0x18004fed0  mov     [rbp+57h+miscStatusPropValue._hrState], r13d
0x18004fed4  mov     dword ptr [rbp+57h+miscStatus.m_ptr], r13d
0x18004fed8  mov     rdi, [rbx]
0x18004fedb  mov     [rbp+57h+var_90._pI], rax
0x18004fedf  lea     rax, [rbp+57h+aspectString]
0x18004fee3  mov     qword ptr [rbp+57h+var_90._hrState], r13
0x18004fee7  inc     pOleClassInfo; ullOperand
0x18004feea  cmp     [rax+pOleClassInfo*2], r13w
0x18004feef  jnz     short loc_18004FEE7
0x18004fef1  lea     rdx, [rbp+57h+miscStatus]; puResult
0x18004fef5  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18004fefa  test    eax, eax
0x18004fefc  jns     short loc_18004FF11
0x18004fefe  xor     r9d, r9d; lpArguments
0x18004ff01  xor     r8d, r8d; nNumberOfArguments
0x18004ff04  mov     ecx, eax; dwExceptionCode
0x18004ff06  lea     dwAspect, [r9+1]; dwExceptionFlags
0x18004ff0a  call    cs:__imp_RaiseException
0x18004ff10  int     3; Trap to Debugger
0x18004ff11  mov     ecx, dword ptr [rbp+57h+miscStatus.m_ptr]; augend
0x18004ff14  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18004ff19  mov     r9d, dword ptr [rbp+57h+miscStatus.m_ptr]; len
0x18004ff1d  lea     rdx, [rbp+57h+aspectString]; str
0x18004ff21  mov     r8d, eax; bufferLen
0x18004ff24  lea     pOleClassInfo, [rbp+57h+var_70]; this
0x18004ff28  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004ff2d  mov     rdx, [rbp+57h+var_70.hstr_]
0x18004ff31  lea     pdwStatus, [rbp+57h+var_90._hrState]
0x18004ff35  mov     rax, [rdi+30h]
0x18004ff39  mov     pOleClassInfo, rbx
0x18004ff3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ff41  mov     rdx, qword ptr [rbp+57h+var_90._hrState]; pI
0x18004ff45  lea     pOleClassInfo, [rbp+57h+miscStatus]; this
0x18004ff49  mov     rsi, [rbp+57h+var_90._pI]
0x18004ff4d  mov     r14d, eax
0x18004ff50  mov     [rbp+57h+var_70.hstr_], r13
0x18004ff54  call    ??0RoVariant@@AEAA@PEAUIInspectable@@_N1@Z; RoVariant::RoVariant(IInspectable *,bool,bool)
0x18004ff59  mov     rbx, [rbp+57h+miscStatus.m_ptr]
0x18004ff5d  lea     pOleClassInfo, [rbp+57h+miscStatus]; this
0x18004ff61  mov     edi, [rbp+57h+var_A8]
0x18004ff64  mov     [rbp+57h+miscStatus.m_ptr], r13
0x18004ff68  mov     [rbp+57h+var_A8], r13d
0x18004ff6c  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18004ff71  mov     pOleClassInfo, [rsi]
0x18004ff74  mov     [rsi], rbx
0x18004ff77  mov     eax, [rsi+8]
0x18004ff7a  mov     [rbp+57h+miscStatus.m_ptr], pOleClassInfo
0x18004ff7e  lea     pOleClassInfo, [rbp+57h+miscStatus]; this
0x18004ff82  mov     [rsi+8], edi
0x18004ff85  mov     [rbp+57h+var_A8], eax
0x18004ff88  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18004ff8d  shr     r14d, 1Fh
0x18004ff91  xor     r14b, 1
0x18004ff95  jz      loc_180050030
0x18004ff9b  mov     rax, [rbp+57h+miscStatusPropValue._pI]
0x18004ff9f  lea     rdx, [rbp+57h+miscStatus]; value
0x18004ffa3  mov     [rbp+57h+var_90._pI], rax
0x18004ffa7  lea     pOleClassInfo, [rbp+57h+var_90]; this
0x18004ffab  mov     eax, [rbp+57h+miscStatusPropValue._hrState]
0x18004ffae  mov     [rbp+57h+var_90._hrState], eax
0x18004ffb1  mov     [rbp+57h+miscStatus.m_ptr], r13
0x18004ffb5  call    ?GetString@Accessor@RoVariant@@QEBAJPEAPEAUHSTRING__@@@Z; RoVariant::Accessor::GetString(HSTRING__ * *)
0x18004ffba  mov     ebx, eax
0x18004ffbc  test    eax, eax
0x18004ffbe  jns     short loc_18004FFE9
0x18004ffc0  mov     pOleClassInfo, [rbp+5Fh]; callerReturnAddress
0x18004ffc4  lea     pdwStatus, aComOle32Ole232_5; "com\\ole32\\ole232\\stdimpl\\olereg.cpp"
0x18004ffcb  mov     r9d, eax; hr
0x18004ffce  mov     dwAspect, 25Ch; lineNumber
0x18004ffd3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ffd8  mov     pOleClassInfo, [rbp+57h+miscStatus.m_ptr]; string
0x18004ffdc  test    pOleClassInfo, pOleClassInfo
0x18004ffdf  jz      short loc_18005001A
0x18004ffe1  call    cs:__imp_WindowsDeleteString
0x18004ffe7  jmp     short loc_18005001A
0x18004ffe9  mov     pOleClassInfo, [rbp+57h+miscStatus.m_ptr]; string
0x18004ffed  xor     dwAspect, dwAspect; length
0x18004ffef  call    cs:__imp_WindowsGetStringRawBuffer
0x18004fff5  xor     dwAspect, dwAspect; EndPtr
0x18004fff7  mov     pOleClassInfo, rax; String
0x18004fffa  lea     r8d, [rdx+0Ah]; Radix
0x18004fffe  call    cs:__imp_wcstol
0x180050004  mov     pOleClassInfo, [rbp+57h+miscStatus.m_ptr]; string
0x180050008  mov     [r12], eax
0x18005000c  test    pOleClassInfo, pOleClassInfo
0x18005000f  jz      short loc_180050017
0x180050011  call    cs:__imp_WindowsDeleteString
0x180050017  mov     ebx, r13d
0x18005001a  lea     pOleClassInfo, [rbp+57h+miscStatusPropValue]; this
0x18005001e  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180050023  lea     pOleClassInfo, [rbp+57h+miscStatusMap]; this
0x180050027  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x18005002c  mov     eax, ebx
0x18005002e  jmp     short loc_180050093
0x180050030  lea     pOleClassInfo, [rbp+57h+miscStatusPropValue]; this
0x180050034  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180050039  mov     rax, [r15]
0x18005003c  lea     rdx, [rbp+57h+miscStatusDefault]
0x180050040  mov     pOleClassInfo, r15
0x180050043  mov     [rbp+57h+miscStatusDefault.m_ptr], r13
0x180050047  mov     rax, [rax+68h]
0x18005004b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050050  mov     pOleClassInfo, [rbp+57h+miscStatusDefault.m_ptr]; string
0x180050054  test    eax, eax
0x180050056  js      short loc_180050079
0x180050058  xor     dwAspect, dwAspect; length
0x18005005a  call    cs:__imp_WindowsGetStringRawBuffer
0x180050060  xor     dwAspect, dwAspect; EndPtr
0x180050062  mov     pOleClassInfo, rax; String
0x180050065  lea     r8d, [rdx+0Ah]; Radix
0x180050069  call    cs:__imp_wcstol
0x18005006f  mov     pOleClassInfo, [rbp+57h+miscStatusDefault.m_ptr]
0x180050073  mov     [r12], eax
0x180050077  jmp     short loc_18005007D
0x180050079  mov     [r12], r13d
0x18005007d  test    pOleClassInfo, pOleClassInfo
0x180050080  jz      short loc_180050088
0x180050082  call    cs:__imp_WindowsDeleteString
0x180050088  lea     pOleClassInfo, [rbp+57h+miscStatusMap]; this
0x18005008c  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x180050091  xor     eax, eax
0x180050093  mov     pOleClassInfo, [rbp+57h+var_38]
0x180050097  xor     pOleClassInfo, rsp; StackCookie
0x18005009a  call    __security_check_cookie
0x18005009f  mov     rbx, [rsp+0D0h+arg_18]
0x1800500a7  add     rsp, 0A0h
0x1800500ae  pop     r15
0x1800500b0  pop     r14
0x1800500b2  pop     r13
0x1800500b4  pop     r12
0x1800500b6  pop     rdi
0x1800500b7  pop     rsi
0x1800500b8  pop     rbp
0x1800500b9  retn
```
