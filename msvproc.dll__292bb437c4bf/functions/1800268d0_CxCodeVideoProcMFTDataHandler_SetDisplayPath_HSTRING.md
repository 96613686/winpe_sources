# CxCodeVideoProcMFTDataHandler::SetDisplayPath(HSTRING__ *)

- ea: `0x1800268d0`
- end: `0x180026b72`
- name: `?SetDisplayPath@CxCodeVideoProcMFTDataHandler@@QEAAJPEAUHSTRING__@@@Z`
- size: `674`
- prototype: `int(CxCodeVideoProcMFTDataHandler *__hidden this, HSTRING)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180026720`
- `0x1800300ac`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x1800268d0`
- `0x18003639c`
- `0x180054140`
- `0x180066474`
- `0x1800b40a4`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180026917`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180026917`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026934`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026934`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800269e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026aa5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800269e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026aa5`

## string_xrefs

- `0x180026944`: `CxCodeVideoProcMFTDataHandler::SetDisplayPath`
- `0x180026a3d`: `CxCodeVideoProcMFTDataHandler::SetDisplayPath`
- `0x180026afc`: `CxCodeVideoProcMFTDataHandler::SetDisplayPath`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcMFTDataHandler::SetDisplayPath(HSTRING *this, HSTRING a2)
{
  int Attributes; // ebx
  HSTRING *v3; // rdi
  PCWSTR StringRawBuffer; // r14
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v8; // ebx
  __int128 v9; // xmm0
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  _BYTE v18[8]; // [rsp+30h] [rbp-30h] BYREF
  struct IMFAttributes *v19; // [rsp+38h] [rbp-28h] BYREF
  UINT32 length; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v21[16]; // [rsp+48h] [rbp-18h] BYREF

  Attributes = 0;
  v3 = this + 298;
  if ( a2 != this[298] )
  {
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      v3,
      0);
    WindowsDuplicateString(a2, v3);
  }
  if ( this[217] )
  {
    length = 0;
    v19 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(a2, &length);
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v18,
      "CxCodeVideoProcMFTDataHandler::SetDisplayPath",
      6425);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && this[388] )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v8 = (*(__int64 (__fastcall **)(HSTRING))(*(_QWORD *)this[388] + 296LL))(this[388]);
      v9 = *(_OWORD *)(*(__int64 (__fastcall **)(HSTRING, _BYTE *))(*(_QWORD *)this[388] + 280LL))(this[388], v21);
      *((_DWORD *)ThreadRelativeContext + 504) = v8;
      *((_OWORD *)ThreadRelativeContext + 125) = v9;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
    Attributes = RendererEffectWrapper::GetAttributes((RendererEffectWrapper *)(this + 198), &v19);
    if ( Attributes >= 0 )
    {
      if ( !StringRawBuffer )
        goto LABEL_31;
      Attributes = ((__int64 (__fastcall *)(struct IMFAttributes *, __int64 *, PCWSTR))v19->lpVtbl->SetString)(
                     v19,
                     MF_CURRENT_DISPLAY_PATH,
                     StringRawBuffer);
      if ( Attributes >= 0 )
        goto LABEL_31;
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)v16 + 499) != Attributes )
          CallStackContext::TraceFailure(v16, "CxCodeVideoProcMFTDataHandler::SetDisplayPath", 6428, Attributes);
      }
      if ( !g_wppLevels )
        goto LABEL_31;
      v13 = 306;
    }
    else
    {
      v10 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v11;
        if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
        {
          v10 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v10 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v10 + 8) )
      {
        v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
        if ( *((_DWORD *)v12 + 499) != Attributes )
          CallStackContext::TraceFailure(v12, "CxCodeVideoProcMFTDataHandler::SetDisplayPath", 6425, Attributes);
      }
      if ( !g_wppLevels )
        goto LABEL_31;
      v13 = 305;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
      this,
      Attributes);
LABEL_31:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v18);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  }
  return (unsigned int)Attributes;
}

```

## disassembly

```asm
0x1800268d0  mov     [rsp-18h+arg_10], rbx
0x1800268d5  mov     [rsp-18h+arg_18], rsi
0x1800268da  push    rbp
0x1800268db  push    rdi
0x1800268dc  push    r14
0x1800268de  mov     rbp, rsp
0x1800268e1  sub     rsp, 60h
0x1800268e5  mov     rax, cs:__security_cookie
0x1800268ec  xor     rax, rsp
0x1800268ef  mov     [rbp+var_8], rax
0x1800268f3  xor     ebx, ebx
0x1800268f5  lea     rdi, [rcx+950h]
0x1800268fc  mov     r14, rdx
0x1800268ff  mov     rsi, rcx
0x180026902  cmp     rdx, [rdi]
0x180026905  jz      short loc_18002691D
0x180026907  xor     edx, edx
0x180026909  mov     rcx, rdi
0x18002690c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180026911  mov     rdx, rdi; newString
0x180026914  mov     rcx, r14; string
0x180026917  call    cs:__imp_WindowsDuplicateString
0x18002691d  cmp     [rsi+6C8h], rbx
0x180026924  jz      loc_180026B4F
0x18002692a  lea     rdx, [rbp+length]; length
0x18002692e  mov     [rbp+length], ebx
0x180026931  mov     rcx, r14; string
0x180026934  call    cs:__imp_WindowsGetStringRawBuffer
0x18002693a  mov     r8d, 1919h; int
0x180026940  mov     [rbp+var_28], rbx
0x180026944  lea     rdx, aCxcodevideopro_40; "CxCodeVideoProcMFTDataHandler::SetDispl"...
0x18002694b  mov     r14, rax
0x18002694e  lea     rcx, [rbp+var_30]; this
0x180026952  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180026957  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002695e  cmp     [rcx+8], bl
0x180026961  jz      short loc_1800269B7
0x180026963  cmp     [rsi+0C20h], rbx
0x18002696a  jz      short loc_1800269B7
0x18002696c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180026971  mov     rcx, [rsi+0C20h]
0x180026978  mov     rdi, rax
0x18002697b  mov     rax, [rcx]
0x18002697e  mov     rax, [rax+128h]
0x180026985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002698a  mov     rcx, [rsi+0C20h]
0x180026991  lea     rdx, [rbp+var_18]
0x180026995  mov     ebx, eax
0x180026997  mov     rax, [rcx]
0x18002699a  mov     rax, [rax+118h]
0x1800269a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269a6  movups  xmm0, xmmword ptr [rax]
0x1800269a9  mov     [rdi+7E0h], ebx
0x1800269af  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800269b7  lea     rcx, [rbp+var_28]
0x1800269bb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800269c0  lea     rcx, [rsi+630h]; this
0x1800269c7  lea     rdx, [rbp+var_28]; struct IMFAttributes **
0x1800269cb  call    ?GetAttributes@RendererEffectWrapper@@QEAAJPEAPEAUIMFAttributes@@@Z; RendererEffectWrapper::GetAttributes(IMFAttributes * *)
0x1800269d0  mov     ebx, eax
0x1800269d2  test    eax, eax
0x1800269d4  jns     loc_180026A69
0x1800269da  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800269e1  test    rcx, rcx
0x1800269e4  jnz     short loc_180026A27
0x1800269e6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800269ec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800269f3  mov     rcx, rax
0x1800269f6  test    rax, rax
0x1800269f9  jz      short loc_180026A19
0x1800269fb  mov     rax, [rax]
0x1800269fe  mov     edx, 7F0h
0x180026a03  mov     rax, [rax+8]
0x180026a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a0c  test    eax, eax
0x180026a0e  jz      short loc_180026A19
0x180026a10  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026a17  jmp     short loc_180026A27
0x180026a19  lea     rcx, qword_180153440; this
0x180026a20  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026a27  cmp     byte ptr [rcx+8], 0
0x180026a2b  jz      short loc_180026A52
0x180026a2d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180026a32  cmp     [rax+7CCh], ebx
0x180026a38  jz      short loc_180026A52
0x180026a3a  mov     r9d, ebx; int
0x180026a3d  lea     rdx, aCxcodevideopro_40; "CxCodeVideoProcMFTDataHandler::SetDispl"...
0x180026a44  mov     r8d, 1919h; int
0x180026a4a  mov     rcx, rax; this
0x180026a4d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180026a52  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180026a59  jb      loc_180026B3D
0x180026a5f  mov     edx, 131h
0x180026a64  jmp     loc_180026B1F
0x180026a69  test    r14, r14
0x180026a6c  jz      loc_180026B3D
0x180026a72  mov     rcx, [rbp+var_28]
0x180026a76  lea     rdx, MF_CURRENT_DISPLAY_PATH
0x180026a7d  mov     r8, r14
0x180026a80  mov     rax, [rcx]
0x180026a83  mov     rax, [rax+0C8h]
0x180026a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a8f  mov     ebx, eax
0x180026a91  test    eax, eax
0x180026a93  jns     loc_180026B3D
0x180026a99  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026aa0  test    rcx, rcx
0x180026aa3  jnz     short loc_180026AE6
0x180026aa5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026aab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026ab2  mov     rcx, rax
0x180026ab5  test    rax, rax
0x180026ab8  jz      short loc_180026AD8
0x180026aba  mov     rax, [rax]
0x180026abd  mov     edx, 7F0h
0x180026ac2  mov     rax, [rax+8]
0x180026ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026acb  test    eax, eax
0x180026acd  jz      short loc_180026AD8
0x180026acf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026ad6  jmp     short loc_180026AE6
0x180026ad8  lea     rcx, qword_180153440; this
0x180026adf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026ae6  cmp     byte ptr [rcx+8], 0
0x180026aea  jz      short loc_180026B11
0x180026aec  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180026af1  cmp     [rax+7CCh], ebx
0x180026af7  jz      short loc_180026B11
0x180026af9  mov     r9d, ebx; int
0x180026afc  lea     rdx, aCxcodevideopro_40; "CxCodeVideoProcMFTDataHandler::SetDispl"...
0x180026b03  mov     r8d, 191Ch; int
0x180026b09  mov     rcx, rax; this
0x180026b0c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180026b11  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180026b18  jb      short loc_180026B3D
0x180026b1a  mov     edx, 132h
0x180026b1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180026b26  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x180026b2d  mov     r9, rsi
0x180026b30  mov     [rsp+60h+var_40], ebx
0x180026b34  mov     rcx, [rcx+10h]
0x180026b38  call    WPP_SF_qD
0x180026b3d  lea     rcx, [rbp+var_30]; this
0x180026b41  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180026b46  lea     rcx, [rbp+var_28]
0x180026b4a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026b4f  mov     eax, ebx
0x180026b51  mov     rcx, [rbp+var_8]
0x180026b55  xor     rcx, rsp; StackCookie
0x180026b58  call    __security_check_cookie
0x180026b5d  lea     r11, [rsp+60h+var_s0]
0x180026b62  mov     rbx, [r11+30h]
0x180026b66  mov     rsi, [r11+38h]
0x180026b6a  mov     rsp, r11
0x180026b6d  pop     r14
0x180026b6f  pop     rdi
0x180026b70  pop     rbp
0x180026b71  retn
```
