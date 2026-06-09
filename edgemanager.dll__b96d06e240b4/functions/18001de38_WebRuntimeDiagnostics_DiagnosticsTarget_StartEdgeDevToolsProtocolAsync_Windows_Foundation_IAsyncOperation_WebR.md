# WebRuntimeDiagnostics::DiagnosticsTarget::StartEdgeDevToolsProtocolAsync(Windows::Foundation::IAsyncOperation<WebRuntime::Diagnostics::ITargetContext *> * *)

- ea: `0x18001de38`
- end: `0x18001e071`
- name: `?StartEdgeDevToolsProtocolAsync@DiagnosticsTarget@WebRuntimeDiagnostics@@AEAAJPEAPEAU?$IAsyncOperation@PEAUITargetContext@Diagnostics@WebRuntime@@@Foundation@Windows@@@Z`
- size: `569`
- prototype: `__int64 __fastcall(WebRuntimeDiagnostics::DiagnosticsTarget *this)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001e080`

## callees

- `0x1800090b4`
- `0x18000b0ec`
- `0x1800131c4`
- `0x18001d8d4`
- `0x18001de38`
- `0x18001e610`
- `0x18001e6a0`
- `0x18001e6e4`
- `0x18001ea88`
- `0x180026258`
- `0x180035b88`
- `0x180059c90`
- `0x180069a88`
- `0x18006a0bc`
- `0x18006ade0`
- `0x18006b840`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001df4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001df4d`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18001df09`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18001df09`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WebRuntimeDiagnostics::DiagnosticsTarget::StartEdgeDevToolsProtocolAsync(
        WebRuntimeDiagnostics::DiagnosticsTarget *this,
        _QWORD *a2)
{
  char *v4; // r14
  void *v6; // rdi
  int v7; // esi
  unsigned int v8; // esi
  bool v9; // di
  __int64 v10; // rdx
  DWORD CurrentProcessId; // eax
  __int64 v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  int v17; // [rsp+20h] [rbp-20h]
  _BYTE v18[16]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  void *Buffer; // [rsp+70h] [rbp+30h] BYREF
  __int64 v21; // [rsp+80h] [rbp+40h] BYREF
  void *v22; // [rsp+88h] [rbp+48h] BYREF

  v4 = (char *)this + 112;
  if ( *((_QWORD *)this + 14) )
    return 2147483658LL;
  v21 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  Microsoft::WRL::Details::Make_WebRuntimeDiagnostics::_AsyncOperation_WebRuntimeDiagnostics::ComInterfaceResultRetriever_WebRuntime::Diagnostics::ITargetContext_____lambda_d67388efd93de19a58fd1746e591f792_____lambda_d67388efd93de19a58fd1746e591f792____(&Buffer);
  v6 = Buffer;
  if ( Buffer )
  {
    v7 = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::IAsyncOperation<WebRuntime::Diagnostics::ITargetContext *>,IAsyncInfo,Microsoft::WRL::CloakedIid<WebRuntimeDiagnostics::IAsyncDeferral<WebRuntime::Diagnostics::ITargetContext *>>>>(
           Buffer,
           &GUID_1851223a_efa0_5289_aff1_77ddd3af0221,
           &v21);
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::IAsyncOperation<WebRuntime::Diagnostics::ITargetContext *>,IAsyncInfo,Microsoft::WRL::CloakedIid<WebRuntimeDiagnostics::IAsyncDeferral<WebRuntime::Diagnostics::ITargetContext *>>>::Release(v6);
  }
  else
  {
    v21 = 0;
    v7 = -2147024882;
  }
  if ( v7 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xFD,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
      (const char *)(unsigned int)v7,
      v17);
  v8 = 0;
  if ( *((_QWORD *)this + 16) )
  {
    LODWORD(Buffer) = -1;
    v13 = Microsoft::WRL::Details::Make<WebRuntimeDiagnostics::TargetContext,std::shared_ptr<WebRuntimeDiagnostics::DiagnosticsTarget::DiagnosticsEndpoint> &,enum WebRuntimeDiagnostics::ContextType>(
            v18,
            (char *)this + 128,
            &Buffer);
    Microsoft::WRL::ComPtr<WebRuntimeDiagnostics::TargetContext>::operator=((char *)this + 120, v13);
    Microsoft::WRL::ComPtr<WebRuntimeDiagnostics::TargetContext>::InternalRelease(v18);
    v22 = 0;
    v14 = Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<WebRuntime::Diagnostics::ITargetContext *>>::As<WebRuntimeDiagnostics::IAsyncDeferral<WebRuntime::Diagnostics::ITargetContext *>>(
            &v21,
            &v22);
    if ( v14 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x125,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
        (const char *)(unsigned int)v14,
        v17);
    v15 = *(_QWORD *)v22;
    Buffer = (void *)*((_QWORD *)this + 15);
    v16 = (*(__int64 (__fastcall **)(void *, _QWORD, void **))(v15 + 24))(v22, 0, &Buffer);
    if ( v16 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x126,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
        (const char *)(unsigned int)v16,
        v17);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<WebRuntime::Diagnostics::ITargetContext *>>::operator=(
      v4,
      &v21);
    v9 = 0;
    LODWORD(Buffer) = 0;
    if ( GetEnvironmentVariableW(L"F12REMOTESCRIPTSDEBUGENABLED", (LPWSTR)&Buffer, 2u) )
    {
      v10 = (unsigned int)(unsigned __int16)Buffer - 49;
      if ( (unsigned __int16)Buffer == 49 )
        v10 = WORD1(Buffer);
      v9 = (_DWORD)v10 == 0;
    }
    LOBYTE(v10) = v9;
    *((_DWORD *)this + 18) = WebRuntimeDiagnostics::DiagnosticsTarget::GetDiagnosticsFlagsForTarget(this, v10, 1);
    if ( *(_BYTE *)(*((_QWORD *)this + 6) + 56LL) )
    {
      CurrentProcessId = GetCurrentProcessId();
      v22 = 0;
      Buffer = 0;
      WebRuntimeDiagnostics::DiagnosticsTarget::CreateRemoteDiagnosticsSite(this, CurrentProcessId, &v22, &Buffer);
      WebRuntimeDiagnostics::DiagnosticsTarget::HandleCreateTargetContextReply(
        this,
        v12,
        *(unsigned int *)(*((_QWORD *)this + 6) + 4LL),
        v22,
        Buffer);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v4);
    }
    else
    {
      v8 = WebRuntimeDiagnostics::DiagnosticsTarget::SetupWebRuntimeDiagnosticsIsoComponents(this);
    }
  }
  *((_BYTE *)this + 56) = 0;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v21);
  *a2 = v21;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  return v8;
}

```

## disassembly

```asm
0x18001de38  mov     [rsp-28h+arg_8], rbx
0x18001de3d  push    rbp
0x18001de3e  push    rsi
0x18001de3f  push    rdi
0x18001de40  push    r14
0x18001de42  push    r15
0x18001de44  mov     rbp, rsp
0x18001de47  sub     rsp, 40h
0x18001de4b  mov     r15, rdx
0x18001de4e  mov     rbx, rcx
0x18001de51  lea     r14, [rcx+70h]
0x18001de55  cmp     qword ptr [r14], 0
0x18001de59  jz      short loc_18001DE65
0x18001de5b  mov     eax, 8000000Ah
0x18001de60  jmp     loc_18001E060
0x18001de65  mov     [rbp+arg_10], 0
0x18001de6d  lea     rcx, [rbp+arg_10]
0x18001de71  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001de76  lea     rcx, [rbp+Buffer]
0x18001de7a  call    Microsoft__WRL__Details__Make_WebRuntimeDiagnostics___AsyncOperation_WebRuntimeDiagnostics__ComInterfaceResultRetriever_WebRuntime__Diagnostics__ITargetContext_____lambda_d67388efd93de19a58fd1746e591f792_____lambda_d67388efd93de19a58fd1746e591f792____
0x18001de7f  mov     rdi, [rbp+Buffer]
0x18001de83  test    rdi, rdi
0x18001de86  jz      short loc_18001DEAC
0x18001de88  lea     r8, [rbp+arg_10]
0x18001de8c  lea     rdx, _GUID_1851223a_efa0_5289_aff1_77ddd3af0221
0x18001de93  mov     rcx, rdi
0x18001de96  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$IAsyncOperation@PEAUITargetContext@Diagnostics@WebRuntime@@@Foundation@Windows@@UIAsyncInfo@@U?$CloakedIid@U?$IAsyncDeferral@PEAUITargetContext@Diagnostics@WebRuntime@@@WebRuntimeDiagnostics@@@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$IAsyncOperation@PEAUITargetContext@Diagnostics@WebRuntime@@@Foundation@Windows@@UIAsyncInfo@@U?$CloakedIid@U?$IAsyncDeferral@PEAUITargetContext@Diagnostics@WebRuntime@@@WebRuntimeDiagnostics@@@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::IAsyncOperation<WebRuntime::Diagnostics::ITargetContext *>,IAsyncInfo,Microsoft::WRL::CloakedIid<WebRuntimeDiagnostics::IAsyncDeferral<WebRuntime::Diagnostics::ITargetContext *>>>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::IAsyncOperation<WebRuntime::Diagnostics::ITargetContext *>,IAsyncInfo,Microsoft::WRL::CloakedIid<WebRuntimeDiagnostics::IAsyncDeferral<WebRuntime::Diagnostics::ITargetContext *>>> *,_GUID const &,void * *)
0x18001de9b  mov     esi, eax
0x18001de9d  test    rdi, rdi
0x18001dea0  jz      short loc_18001DEB9
0x18001dea2  mov     rcx, rdi
0x18001dea5  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$IAsyncOperation@PEAUITargetContext@Diagnostics@WebRuntime@@@Foundation@Windows@@UIAsyncInfo@@U?$CloakedIid@U?$IAsyncDeferral@PEAUITargetContext@Diagnostics@WebRuntime@@@WebRuntimeDiagnostics@@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::IAsyncOperation<WebRuntime::Diagnostics::ITargetContext *>,IAsyncInfo,Microsoft::WRL::CloakedIid<WebRuntimeDiagnostics::IAsyncDeferral<WebRuntime::Diagnostics::ITargetContext *>>>::Release(void)
0x18001deaa  jmp     short loc_18001DEB9
0x18001deac  mov     [rbp+arg_10], 0
0x18001deb4  mov     esi, 8007000Eh
0x18001deb9  mov     rcx, [rbp+28h]; this
0x18001debd  test    esi, esi
0x18001debf  jns     short loc_18001DED6
0x18001dec1  mov     r9d, esi; char *
0x18001dec4  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18001decb  mov     edx, 0FDh; void *
0x18001ded0  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001ded6  xor     esi, esi
0x18001ded8  lea     rdx, [rbx+80h]
0x18001dedf  cmp     [rdx], rsi
0x18001dee2  jnz     loc_18001DFA6
0x18001dee8  lea     rdx, [rbp+arg_10]
0x18001deec  mov     rcx, r14
0x18001deef  call    ??4?$ComPtr@U?$IAsyncOperation@PEAUITargetContext@Diagnostics@WebRuntime@@@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<WebRuntime::Diagnostics::ITargetContext *>>::operator=(Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<WebRuntime::Diagnostics::ITargetContext *>> const &)
0x18001def4  xor     dil, dil
0x18001def7  mov     dword ptr [rbp+Buffer], esi
0x18001defa  lea     r8d, [rsi+2]; nSize
0x18001defe  lea     rdx, [rbp+Buffer]; lpBuffer
0x18001df02  lea     rcx, Name; "F12REMOTESCRIPTSDEBUGENABLED"
0x18001df09  call    cs:__imp_GetEnvironmentVariableW
0x18001df0f  lea     r8d, [rsi+1]
0x18001df13  test    eax, eax
0x18001df15  jz      short loc_18001DF35
0x18001df17  movzx   edx, word ptr [rbp+Buffer]
0x18001df1b  sub     edx, 31h ; '1'
0x18001df1e  jnz     short loc_18001DF2B
0x18001df20  movzx   edx, word ptr [rbp+Buffer+2]
0x18001df24  xor     eax, eax
0x18001df26  movzx   ecx, ax
0x18001df29  sub     edx, ecx
0x18001df2b  movzx   edi, dil
0x18001df2f  test    edx, edx
0x18001df31  cmovz   edi, r8d
0x18001df35  mov     dl, dil
0x18001df38  mov     rcx, rbx
0x18001df3b  call    ?GetDiagnosticsFlagsForTarget@DiagnosticsTarget@WebRuntimeDiagnostics@@AEAA?AW4DiagnosticsFlags@@_N0@Z; WebRuntimeDiagnostics::DiagnosticsTarget::GetDiagnosticsFlagsForTarget(bool,bool)
0x18001df40  mov     [rbx+48h], eax
0x18001df43  mov     rax, [rbx+30h]
0x18001df47  cmp     [rax+38h], sil
0x18001df4b  jz      short loc_18001DF97
0x18001df4d  call    cs:__imp_GetCurrentProcessId
0x18001df53  mov     [rbp+arg_18], rsi
0x18001df57  mov     [rbp+Buffer], rsi
0x18001df5b  lea     r9, [rbp+Buffer]; void **
0x18001df5f  lea     r8, [rbp+arg_18]; void **
0x18001df63  mov     edx, eax; unsigned int
0x18001df65  mov     rcx, rbx; this
0x18001df68  call    ?CreateRemoteDiagnosticsSite@DiagnosticsTarget@WebRuntimeDiagnostics@@AEBAXKPEAPEAX0@Z; WebRuntimeDiagnostics::DiagnosticsTarget::CreateRemoteDiagnosticsSite(ulong,void * *,void * *)
0x18001df6d  mov     r8, [rbx+30h]
0x18001df71  mov     rax, [rbp+Buffer]
0x18001df75  mov     qword ptr [rsp+40h+var_20], rax
0x18001df7a  mov     r9, [rbp+arg_18]
0x18001df7e  mov     r8d, [r8+4]
0x18001df82  mov     rcx, rbx
0x18001df85  call    ?HandleCreateTargetContextReply@DiagnosticsTarget@WebRuntimeDiagnostics@@AEAAXW4ContextType@2@KQEAX1@Z; WebRuntimeDiagnostics::DiagnosticsTarget::HandleCreateTargetContextReply(WebRuntimeDiagnostics::ContextType,ulong,void * const,void * const)
0x18001df8a  mov     rcx, r14
0x18001df8d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001df92  jmp     loc_18001E041
0x18001df97  mov     rcx, rbx; this
0x18001df9a  call    ?SetupWebRuntimeDiagnosticsIsoComponents@DiagnosticsTarget@WebRuntimeDiagnostics@@AEAAJXZ; WebRuntimeDiagnostics::DiagnosticsTarget::SetupWebRuntimeDiagnosticsIsoComponents(void)
0x18001df9f  mov     esi, eax
0x18001dfa1  jmp     loc_18001E041
0x18001dfa6  mov     dword ptr [rbp+Buffer], 0FFFFFFFFh
0x18001dfad  lea     r8, [rbp+Buffer]
0x18001dfb1  lea     rcx, [rbp+var_10]
0x18001dfb5  call    ??$Make@VTargetContext@WebRuntimeDiagnostics@@AEAV?$shared_ptr@VDiagnosticsEndpoint@DiagnosticsTarget@WebRuntimeDiagnostics@@@std@@W4ContextType@2@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VTargetContext@WebRuntimeDiagnostics@@@12@AEAV?$shared_ptr@VDiagnosticsEndpoint@DiagnosticsTarget@WebRuntimeDiagnostics@@@std@@$$QEAW4ContextType@WebRuntimeDiagnostics@@@Z; Microsoft::WRL::Details::Make<WebRuntimeDiagnostics::TargetContext,std::shared_ptr<WebRuntimeDiagnostics::DiagnosticsTarget::DiagnosticsEndpoint> &,WebRuntimeDiagnostics::ContextType>(std::shared_ptr<WebRuntimeDiagnostics::DiagnosticsTarget::DiagnosticsEndpoint> &,WebRuntimeDiagnostics::ContextType &&)
0x18001dfba  mov     rdx, rax
0x18001dfbd  lea     rcx, [rbx+78h]
0x18001dfc1  call    ??4?$ComPtr@VTargetContext@WebRuntimeDiagnostics@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<WebRuntimeDiagnostics::TargetContext>::operator=(Microsoft::WRL::ComPtr<WebRuntimeDiagnostics::TargetContext> &&)
0x18001dfc6  lea     rcx, [rbp+var_10]
0x18001dfca  call    ?InternalRelease@?$ComPtr@VTargetContext@WebRuntimeDiagnostics@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WebRuntimeDiagnostics::TargetContext>::InternalRelease(void)
0x18001dfcf  mov     [rbp+arg_18], rsi
0x18001dfd3  lea     rdx, [rbp+arg_18]
0x18001dfd7  lea     rcx, [rbp+arg_10]
0x18001dfdb  call    ??$As@U?$IAsyncDeferral@PEAUITargetContext@Diagnostics@WebRuntime@@@WebRuntimeDiagnostics@@@?$ComPtr@U?$IAsyncOperation@PEAUITargetContext@Diagnostics@WebRuntime@@@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncDeferral@PEAUITargetContext@Diagnostics@WebRuntime@@@WebRuntimeDiagnostics@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<WebRuntime::Diagnostics::ITargetContext *>>::As<WebRuntimeDiagnostics::IAsyncDeferral<WebRuntime::Diagnostics::ITargetContext *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WebRuntimeDiagnostics::IAsyncDeferral<WebRuntime::Diagnostics::ITargetContext *>>>)
0x18001dfe0  mov     rcx, [rbp+28h]; this
0x18001dfe4  test    eax, eax
0x18001dfe6  jns     short loc_18001DFFD
0x18001dfe8  mov     r9d, eax; char *
0x18001dfeb  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18001dff2  mov     edx, 125h; void *
0x18001dff7  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001dffd  mov     rcx, [rbp+arg_18]
0x18001e001  mov     rax, [rcx]
0x18001e004  mov     rdx, [rbx+78h]
0x18001e008  mov     [rbp+Buffer], rdx
0x18001e00c  lea     r8, [rbp+Buffer]
0x18001e010  xor     edx, edx
0x18001e012  mov     rax, [rax+18h]
0x18001e016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e01b  mov     rcx, [rbp+28h]; this
0x18001e01f  test    eax, eax
0x18001e021  jns     short loc_18001E038
0x18001e023  mov     r9d, eax; char *
0x18001e026  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18001e02d  mov     edx, 126h; void *
0x18001e032  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001e038  lea     rcx, [rbp+arg_18]
0x18001e03c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001e041  mov     byte ptr [rbx+38h], 0
0x18001e045  lea     rcx, [rbp+arg_10]
0x18001e049  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18001e04e  mov     rax, [rbp+arg_10]
0x18001e052  mov     [r15], rax
0x18001e055  lea     rcx, [rbp+arg_10]
0x18001e059  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001e05e  mov     eax, esi
0x18001e060  mov     rbx, [rsp+40h+arg_8]
0x18001e065  add     rsp, 40h
0x18001e069  pop     r15
0x18001e06b  pop     r14
0x18001e06d  pop     rdi
0x18001e06e  pop     rsi
0x18001e06f  pop     rbp
0x18001e070  retn
```
