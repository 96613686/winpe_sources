# WebRuntimeDevTools::DebugTargetManager::LCIEProcessMessage(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18001bb40`
- end: `0x18001be9b`
- name: `?LCIEProcessMessage@DebugTargetManager@WebRuntimeDevTools@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `859`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007810`
- `0x18000b0ec`
- `0x18001b178`
- `0x18001b218`
- `0x18001bb40`
- `0x18001bee8`
- `0x180023298`
- `0x1800274e0`
- `0x18002b530`
- `0x180035580`
- `0x180035b88`
- `0x18006d268`
- `0x18006ea64`
- `0x18007f104`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001be62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001be62`
- `edgeIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x18001bc3d`
- `edgeIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x18001bdac`
- `edgeIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x18001bc3d`
- `edgeIso!__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z` at `0x18001bdac`
- `edgeIso!__imp_?IsoGetArtifactAddress@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z` at `0x18001bbaf`
- `edgeIso!__imp_?IsoGetArtifactAddress@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z` at `0x18001bbaf`
- `edgeIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18001bd64`
- `edgeIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18001bd64`
- `edgeIso!__imp_?IsoReleaseThread@@YAKK@Z` at `0x18001bd4d`
- `edgeIso!__imp_?IsoReleaseThread@@YAKK@Z` at `0x18001bd4d`
- `edgeIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x18001bb8d`
- `edgeIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x18001bc2c`
- `edgeIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x18001bd9b`
- `edgeIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x18001bb8d`
- `edgeIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x18001bc2c`
- `edgeIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x18001bd9b`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x18001be77`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x18001be77`
- `edgeIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x18001bbd0`
- `edgeIso!__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z` at `0x18001bbd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WebRuntimeDevTools::DebugTargetManager::LCIEProcessMessage(
        HWND a1,
        __int64 a2,
        int a3,
        unsigned int a4)
{
  WebRuntimeDevTools::DebugTargetManager *v6; // rax
  WebRuntimeDevTools::DebugTargetManager *v7; // rdi
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  HSTRING v11; // rax
  struct _IsoMessage **v12; // rax
  struct _IsoMessage *v13; // r14
  __int64 (__fastcall *v14)(char *, unsigned int *); // rbx
  unsigned int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  struct _IsoMessage *v18; // rax
  const unsigned __int16 *v19; // rbx
  unsigned __int64 v20; // rcx
  int v21; // eax
  __int64 (__fastcall *v22)(char *, HSTRING, __int64 *); // rbx
  unsigned int v23; // eax
  __int64 v24; // rcx
  int v26; // [rsp+20h] [rbp-79h]
  int v27; // [rsp+20h] [rbp-79h]
  HSTRING string; // [rsp+30h] [rbp-69h] BYREF
  unsigned int v29[2]; // [rsp+38h] [rbp-61h] BYREF
  __int64 v30; // [rsp+40h] [rbp-59h] BYREF
  _IsoComponent *v31; // [rsp+48h] [rbp-51h] BYREF
  struct _IsoMessage *v32; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v33; // [rsp+58h] [rbp-41h] BYREF
  struct _IsoMessage *v34; // [rsp+60h] [rbp-39h] BYREF
  WebRuntimeDevTools::DebugTargetManager *v35; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v36[32]; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v37[32]; // [rsp+90h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v34 = 0;
  v33 = 0;
  if ( !IsoGetMessageBufferAddress(a4, 1, 0, &v34, &v33) )
  {
    v31 = 0;
    if ( !(unsigned int)IsoGetArtifactAddress(*(unsigned int *)v34, 1, &v31) )
    {
      v6 = (WebRuntimeDevTools::DebugTargetManager *)IsoInProcessData(v31, 0x30001u, *((_DWORD *)v31 + 65), 0);
      v7 = v6;
      if ( v6 )
      {
        v8 = a3 - 3419;
        if ( v8 )
        {
          v9 = v8 - 133;
          if ( v9 )
          {
            v10 = v9 - 10;
            if ( v10 )
            {
              if ( v10 == 1 )
                WebRuntimeDevTools::DebugTargetManager::HandleGetDebugTargetsResponse(v6, a4);
            }
            else
            {
              string = 0;
              if ( (int)IsoGetMessageBufferAddress(a4, 1, 0, (struct _IsoMessage **)&string, 0) < 0
                || VerifyUntrusted_IsoMessage_ExactSize(a4, 0x1068u) )
              {
                v11 = string;
              }
              else
              {
                v11 = 0;
                string = 0;
              }
              if ( v11 && v11 != (HSTRING)-32LL )
              {
                std::wstring::wstring(v37, v11 + 8);
                *(_QWORD *)v29 = 0;
                v35 = v7;
                std::wstring::wstring(v36, v37);
                v12 = (struct _IsoMessage **)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Collections::IVectorView_WebRuntime::DevTools::IDebugTargetInfo______::___Windows::Foundation::IAsyncOperation_Windows::Foundation::Collections::IVectorView_WebRuntime::DevTools::IDebugTargetInfo_________enum_ABI::Windows::Foundation::AsyncStatus__::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Foundation::Collections::IVectorView_WebRuntime::DevTools::IDebugTargetInfo________lambda_b0097a835298d3489bcff4455eda2ea8___1_Windows::Foundation::IAsyncOperation_Windows::Foundation::Collections::IVectorView_WebRuntime::DevTools::IDebugTargetInfo_________enum_ABI::Windows::Foundation::AsyncStatus___lambda_b0097a835298d3489bcff4455eda2ea8___(
                                               &v30,
                                               &v35);
                v13 = *v12;
                v32 = *v12;
                *v12 = 0;
                if ( v30 )
                {
                  v30 = 0;
                  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::Release();
                }
                std::wstring::_Tidy_deallocate(v36);
                v14 = *(__int64 (__fastcall **)(char *, unsigned int *))(*((_QWORD *)v7 + 2) + 48LL);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v29);
                v15 = v14((char *)v7 + 16, v29);
                if ( v15 )
                {
                  MicrosoftTelemetryAssertTriggeredArgs(v16, v15);
                }
                else
                {
                  v17 = (*(__int64 (__fastcall **)(_QWORD, struct _IsoMessage *))(**(_QWORD **)v29 + 48LL))(
                          *(_QWORD *)v29,
                          v13);
                  if ( v17 < 0 )
                    wil::details::in1diag3::_FailFast_Hr(
                      retaddr,
                      (void *)0x1EC,
                      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\debugtargetmanager.cpp",
                      (const char *)(unsigned int)v17,
                      v26);
                }
                if ( v13 )
                  (*(void (__fastcall **)(struct _IsoMessage *))(*(_QWORD *)v13 + 16LL))(v13);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v29);
                std::wstring::_Tidy_deallocate(v37);
              }
            }
          }
          else
          {
            IsoReleaseThread(*((_DWORD *)v31 + 10));
            _IsoComponent::SetAppObj(v31, 0);
            IsoRemoveArtifact(*(_DWORD *)v34);
            *((_BYTE *)v7 + 80) = 0;
            *((_DWORD *)v7 + 18) = 0;
            (*(void (__fastcall **)(WebRuntimeDevTools::DebugTargetManager *))(*(_QWORD *)v7 + 16LL))(v7);
          }
        }
        else
        {
          v32 = 0;
          if ( (int)IsoGetMessageBufferAddress(a4, 1, 0, &v32, 0) < 0 || VerifyUntrusted_IsoMessage_ExactSize(a4, 0x70u) )
          {
            v18 = v32;
          }
          else
          {
            v18 = 0;
            v32 = 0;
          }
          if ( v18 )
          {
            v19 = (const unsigned __int16 *)((char *)v18 + 32);
            if ( v18 != (struct _IsoMessage *)-32LL )
            {
              v30 = 0;
              string = 0;
              v29[0] = 0;
              v20 = -1;
              do
                ++v20;
              while ( v19[v20] );
              v21 = ULongLongToULong(v20, v29);
              if ( v21 >= 0 )
                v21 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, v19, v29[0]);
              if ( v21 < 0 )
                wil::details::in1diag3::_FailFast_Hr(
                  retaddr,
                  (void *)0x1FF,
                  (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\debugtargetmanager.cpp",
                  (const char *)(unsigned int)v21,
                  v27);
              v22 = *(__int64 (__fastcall **)(char *, HSTRING, __int64 *))(*((_QWORD *)v7 + 2) + 72LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
              v23 = v22((char *)v7 + 16, string, &v30);
              if ( v23 )
                MicrosoftTelemetryAssertTriggeredArgs(v24, v23);
              WindowsDeleteString(string);
              string = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
            }
          }
        }
      }
    }
    IsoFreeMessageBuffer(a4);
  }
  return 0;
}

```

## disassembly

```asm
0x18001bb40  push    rbp
0x18001bb42  push    rbx
0x18001bb43  push    rsi
0x18001bb44  push    rdi
0x18001bb45  push    r14
0x18001bb47  push    r15
0x18001bb49  lea     rbp, [rsp-2Fh]
0x18001bb4e  sub     rsp, 0C8h
0x18001bb55  mov     rax, cs:__security_cookie
0x18001bb5c  xor     rax, rsp
0x18001bb5f  mov     [rbp+57h+var_40], rax
0x18001bb63  mov     rsi, r9
0x18001bb66  mov     rbx, r8
0x18001bb69  xor     r15d, r15d
0x18001bb6c  mov     [rbp+57h+var_90], r15
0x18001bb70  mov     [rbp+57h+var_98], r15d
0x18001bb74  lea     rax, [rbp+57h+var_98]
0x18001bb78  mov     qword ptr [rsp+0F0h+var_D0], rax
0x18001bb7d  lea     r9, [rbp+57h+var_90]
0x18001bb81  xor     r8d, r8d
0x18001bb84  lea     r14d, [r15+1]
0x18001bb88  mov     edx, r14d
0x18001bb8b  mov     ecx, esi
0x18001bb8d  call    cs:__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z; IsoGetMessageBufferAddress(ulong,int,ulong *,_IsoMessage * *,ulong *)
0x18001bb93  test    eax, eax
0x18001bb95  jnz     loc_18001BE7D
0x18001bb9b  mov     [rbp+57h+var_A8], r15
0x18001bb9f  xor     r9d, r9d
0x18001bba2  lea     r8, [rbp+57h+var_A8]
0x18001bba6  mov     edx, r14d
0x18001bba9  mov     rcx, [rbp+57h+var_90]
0x18001bbad  mov     ecx, [rcx]
0x18001bbaf  call    cs:__imp_?IsoGetArtifactAddress@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z; IsoGetArtifactAddress(ulong,IsoArtifactType,_IsoArtifact * *,ulong *)
0x18001bbb5  test    eax, eax
0x18001bbb7  jnz     loc_18001BE75
0x18001bbbd  mov     rcx, [rbp+57h+var_A8]
0x18001bbc1  xor     r9d, r9d
0x18001bbc4  mov     r8d, [rcx+104h]
0x18001bbcb  mov     edx, 30001h
0x18001bbd0  call    cs:__imp_?IsoInProcessData@@YAPEAXPEAU_IsoArtifact@@KKPEAX@Z; IsoInProcessData(_IsoArtifact *,ulong,ulong,void *)
0x18001bbd6  mov     rdi, rax
0x18001bbd9  test    rax, rax
0x18001bbdc  jz      loc_18001BE75
0x18001bbe2  sub     ebx, 0D5Bh
0x18001bbe8  jz      loc_18001BD86
0x18001bbee  sub     ebx, 85h
0x18001bbf4  jz      loc_18001BD46
0x18001bbfa  sub     ebx, 0Ah
0x18001bbfd  jz      short loc_18001BC17
0x18001bbff  cmp     ebx, r14d
0x18001bc02  jnz     loc_18001BE75
0x18001bc08  mov     edx, esi; unsigned int
0x18001bc0a  mov     rcx, rax; this
0x18001bc0d  call    ?HandleGetDebugTargetsResponse@DebugTargetManager@WebRuntimeDevTools@@AEAAXK@Z; WebRuntimeDevTools::DebugTargetManager::HandleGetDebugTargetsResponse(ulong)
0x18001bc12  jmp     loc_18001BE75
0x18001bc17  mov     [rbp+57h+string], r15
0x18001bc1b  mov     qword ptr [rsp+0F0h+var_D0], r15; int
0x18001bc20  lea     r9, [rbp+57h+string]
0x18001bc24  xor     r8d, r8d
0x18001bc27  mov     edx, r14d
0x18001bc2a  mov     ecx, esi
0x18001bc2c  call    cs:__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z; IsoGetMessageBufferAddress(ulong,int,ulong *,_IsoMessage * *,ulong *)
0x18001bc32  test    eax, eax
0x18001bc34  js      short loc_18001BC50
0x18001bc36  mov     edx, 1068h
0x18001bc3b  mov     ecx, esi
0x18001bc3d  call    cs:__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z; VerifyUntrusted_IsoMessage_ExactSize(ulong,ulong)
0x18001bc43  test    al, al
0x18001bc45  jnz     short loc_18001BC50
0x18001bc47  mov     rax, r15
0x18001bc4a  mov     [rbp+57h+string], rax
0x18001bc4e  jmp     short loc_18001BC54
0x18001bc50  mov     rax, [rbp+57h+string]
0x18001bc54  test    rax, rax
0x18001bc57  jz      loc_18001BE75
0x18001bc5d  lea     rdx, [rax+20h]
0x18001bc61  test    rdx, rdx
0x18001bc64  jz      loc_18001BE75
0x18001bc6a  lea     rcx, [rbp+57h+var_60]
0x18001bc6e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001bc73  nop
0x18001bc74  mov     qword ptr [rbp+57h+var_B8], r15
0x18001bc78  mov     [rbp+57h+var_88], rdi
0x18001bc7c  lea     rdx, [rbp+57h+var_60]
0x18001bc80  lea     rcx, [rbp+57h+var_80]
0x18001bc84  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001bc89  lea     rdx, [rbp+57h+var_88]
0x18001bc8d  lea     rcx, [rbp+57h+var_B0]
0x18001bc91  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__IAsyncOperationCompletedHandler_impl_Windows__Foundation__Collections__IVectorView_WebRuntime__DevTools__IDebugTargetInfo___________Windows__Foundation__IAsyncOperation_Windows__Foundation__Collections__IVectorView_WebRuntime__DevTools__IDebugTargetInfo_________enum_ABI__Windows__Foundation__AsyncStatus____DelegateInvokeHelper_Windows__Foundation__IAsyncOperationCompletedHandler_Windows__Foundation__Collections__IVectorView_WebRuntime__DevTools__IDebugTargetInfo________lambda_b0097a835298d3489bcff4455eda2ea8___1_Windows__Foundation__IAsyncOperation_Windows__Foundation__Collections__IVectorView_WebRuntime__DevTools__IDebugTargetInfo_________enum_ABI__Windows__Foundation__AsyncStatus___lambda_b0097a835298d3489bcff4455eda2ea8___
0x18001bc96  mov     r14, [rax]
0x18001bc99  mov     [rbp+57h+var_A0], r14
0x18001bc9d  mov     [rax], r15
0x18001bca0  mov     rcx, [rbp+57h+var_B0]
0x18001bca4  test    rcx, rcx
0x18001bca7  jz      short loc_18001BCB3
0x18001bca9  mov     [rbp+57h+var_B0], r15
0x18001bcad  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::Release(void)
0x18001bcb2  nop
0x18001bcb3  lea     rcx, [rbp+57h+var_80]
0x18001bcb7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001bcbc  mov     rax, [rdi+10h]
0x18001bcc0  mov     rbx, [rax+30h]
0x18001bcc4  lea     rcx, [rbp+57h+var_B8]
0x18001bcc8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001bccd  lea     rdx, [rbp+57h+var_B8]
0x18001bcd1  lea     rcx, [rdi+10h]
0x18001bcd5  mov     rax, rbx
0x18001bcd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcdd  test    eax, eax
0x18001bcdf  jz      short loc_18001BD16
0x18001bce1  mov     edx, eax
0x18001bce3  call    MicrosoftTelemetryAssertTriggeredArgs
0x18001bce8  nop
0x18001bce9  test    r14, r14
0x18001bcec  jz      short loc_18001BCFE
0x18001bcee  mov     rax, [r14]
0x18001bcf1  mov     rcx, r14
0x18001bcf4  mov     rax, [rax+10h]
0x18001bcf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcfd  nop
0x18001bcfe  lea     rcx, [rbp+57h+var_B8]
0x18001bd02  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001bd07  nop
0x18001bd08  lea     rcx, [rbp+57h+var_60]
0x18001bd0c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001bd11  jmp     loc_18001BE75
0x18001bd16  mov     rcx, qword ptr [rbp+57h+var_B8]
0x18001bd1a  mov     rax, [rcx]
0x18001bd1d  mov     rdx, r14
0x18001bd20  mov     rax, [rax+30h]
0x18001bd24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd29  mov     rcx, [rbp+5Fh]; this
0x18001bd2d  test    eax, eax
0x18001bd2f  jns     short loc_18001BCE9
0x18001bd31  mov     r9d, eax; char *
0x18001bd34  lea     r8, aOnecoreuapInet_2; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18001bd3b  mov     edx, 1ECh; void *
0x18001bd40  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001bd46  mov     rcx, [rbp+57h+var_A8]
0x18001bd4a  mov     ecx, [rcx+28h]
0x18001bd4d  call    cs:__imp_?IsoReleaseThread@@YAKK@Z; IsoReleaseThread(ulong)
0x18001bd53  xor     edx, edx; void *
0x18001bd55  mov     rcx, [rbp+57h+var_A8]; this
0x18001bd59  call    ?SetAppObj@_IsoComponent@@QEAAXQEAX@Z; _IsoComponent::SetAppObj(void * const)
0x18001bd5e  mov     rcx, [rbp+57h+var_90]
0x18001bd62  mov     ecx, [rcx]
0x18001bd64  call    cs:__imp_?IsoRemoveArtifact@@YAJK@Z; IsoRemoveArtifact(ulong)
0x18001bd6a  mov     [rdi+50h], r15b
0x18001bd6e  mov     [rdi+48h], r15d
0x18001bd72  mov     rax, [rdi]
0x18001bd75  mov     rcx, rdi
0x18001bd78  mov     rax, [rax+10h]
0x18001bd7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd81  jmp     loc_18001BE75
0x18001bd86  mov     [rbp+57h+var_A0], r15
0x18001bd8a  mov     qword ptr [rsp+0F0h+var_D0], r15; int
0x18001bd8f  lea     r9, [rbp+57h+var_A0]
0x18001bd93  xor     r8d, r8d
0x18001bd96  mov     edx, r14d
0x18001bd99  mov     ecx, esi
0x18001bd9b  call    cs:__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z; IsoGetMessageBufferAddress(ulong,int,ulong *,_IsoMessage * *,ulong *)
0x18001bda1  test    eax, eax
0x18001bda3  js      short loc_18001BDBF
0x18001bda5  mov     edx, 70h ; 'p'
0x18001bdaa  mov     ecx, esi
0x18001bdac  call    cs:__imp_?VerifyUntrusted_IsoMessage_ExactSize@@YA_NKK@Z; VerifyUntrusted_IsoMessage_ExactSize(ulong,ulong)
0x18001bdb2  test    al, al
0x18001bdb4  jnz     short loc_18001BDBF
0x18001bdb6  mov     rax, r15
0x18001bdb9  mov     [rbp+57h+var_A0], rax
0x18001bdbd  jmp     short loc_18001BDC3
0x18001bdbf  mov     rax, [rbp+57h+var_A0]
0x18001bdc3  test    rax, rax
0x18001bdc6  jz      loc_18001BE75
0x18001bdcc  lea     rbx, [rax+20h]
0x18001bdd0  test    rbx, rbx
0x18001bdd3  jz      loc_18001BE75
0x18001bdd9  mov     [rbp+57h+var_B0], r15
0x18001bddd  mov     [rbp+57h+string], r15
0x18001bde1  mov     [rbp+57h+var_B8], r15d
0x18001bde5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001bde9  inc     rcx; unsigned __int64
0x18001bdec  cmp     [rbx+rcx*2], r15w
0x18001bdf1  jnz     short loc_18001BDE9
0x18001bdf3  lea     rdx, [rbp+57h+var_B8]; unsigned int *
0x18001bdf7  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18001bdfc  test    eax, eax
0x18001bdfe  js      short loc_18001BE10
0x18001be00  mov     r8d, [rbp+57h+var_B8]; unsigned int
0x18001be04  mov     rdx, rbx; unsigned __int16 *
0x18001be07  lea     rcx, [rbp+57h+string]; this
0x18001be0b  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18001be10  mov     rcx, [rbp+5Fh]; this
0x18001be14  test    eax, eax
0x18001be16  jns     short loc_18001BE2D
0x18001be18  mov     r9d, eax; char *
0x18001be1b  lea     r8, aOnecoreuapInet_2; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18001be22  mov     edx, 1FFh; void *
0x18001be27  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001be2d  mov     rax, [rdi+10h]
0x18001be31  mov     rbx, [rax+48h]
0x18001be35  lea     rcx, [rbp+57h+var_B0]
0x18001be39  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001be3e  lea     r8, [rbp+57h+var_B0]
0x18001be42  mov     rdx, [rbp+57h+string]
0x18001be46  lea     rcx, [rdi+10h]
0x18001be4a  mov     rax, rbx
0x18001be4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be52  test    eax, eax
0x18001be54  jz      short loc_18001BE5E
0x18001be56  mov     edx, eax
0x18001be58  call    MicrosoftTelemetryAssertTriggeredArgs
0x18001be5d  nop
0x18001be5e  mov     rcx, [rbp+57h+string]; string
0x18001be62  call    cs:__imp_WindowsDeleteString
0x18001be68  mov     [rbp+57h+string], r15
0x18001be6c  lea     rcx, [rbp+57h+var_B0]
0x18001be70  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001be75  mov     ecx, esi
0x18001be77  call    cs:__imp_?IsoFreeMessageBuffer@@YAJK@Z; IsoFreeMessageBuffer(ulong)
0x18001be7d  xor     eax, eax
0x18001be7f  mov     rcx, [rbp+57h+var_40]
0x18001be83  xor     rcx, rsp; StackCookie
0x18001be86  call    __security_check_cookie
0x18001be8b  add     rsp, 0C8h
0x18001be92  pop     r15
0x18001be94  pop     r14
0x18001be96  pop     rdi
0x18001be97  pop     rsi
0x18001be98  pop     rbx
0x18001be99  pop     rbp
0x18001be9a  retn
```
