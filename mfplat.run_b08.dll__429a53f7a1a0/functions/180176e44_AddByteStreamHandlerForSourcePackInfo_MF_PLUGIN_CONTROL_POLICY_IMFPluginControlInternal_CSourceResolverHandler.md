# AddByteStreamHandlerForSourcePackInfo(MF_PLUGIN_CONTROL_POLICY,IMFPluginControlInternal *,CSourceResolverHandlerList *,SourcePackInfo &)

- ea: `0x180176e44`
- end: `0x18017743e`
- name: `?AddByteStreamHandlerForSourcePackInfo@@YAJW4MF_PLUGIN_CONTROL_POLICY@@PEAUIMFPluginControlInternal@@PEAVCSourceResolverHandlerList@@AEAUSourcePackInfo@@@Z`
- size: `1530`
- prototype: `__int64 __fastcall(enum MF_PLUGIN_CONTROL_POLICY, struct IMFPluginControlInternal *, struct CSourceResolverHandlerList *, struct SourcePackInfo *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001ce20`
- `0x180176adc`

## callees

- `0x180004870`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18005e230`
- `0x1800c655c`
- `0x1800dccf0`
- `0x1800e6f9c`
- `0x180176900`
- `0x180176e44`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18017732c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180177401`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18017732c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180177401`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180177252`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180177252`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18017725f`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18017725f`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall AddByteStreamHandlerForSourcePackInfo(
        enum MF_PLUGIN_CONTROL_POLICY a1,
        struct IMFPluginControlInternal *a2,
        struct CSourceResolverHandlerList *a3,
        struct SourcePackInfo *a4)
{
  int v8; // ebx
  CallStackTracing *v9; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  CallStackTracing *v12; // rcx
  struct CallStackContext *v13; // rax
  CallStackTracing *v14; // rcx
  struct CallStackContext *v15; // rax
  CallStackTracing *v16; // rcx
  struct CallStackContext *v17; // rax
  struct IMFActivate *v18; // rdi
  HRESULT (__stdcall *ActivateObject)(IMFActivate *, const IID *const, void **); // rbx
  CallStackTracing *v20; // rcx
  struct CallStackContext *v21; // rax
  const WCHAR *StringRawBuffer; // rax
  CallStackTracing *v23; // rcx
  struct CallStackContext *v24; // rax
  void *v25; // rcx
  CallStackTracing *v26; // rcx
  struct CallStackContext *v27; // rax
  void *v28; // rcx
  int v30; // [rsp+30h] [rbp-48h] BYREF
  struct IMFActivate *v31; // [rsp+38h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-38h] BYREF
  struct IUnknown *v33; // [rsp+48h] [rbp-30h] BYREF
  LPVOID *p_pv; // [rsp+50h] [rbp-28h] BYREF
  LPWSTR ppwsz; // [rsp+58h] [rbp-20h] BYREF
  char v36; // [rsp+60h] [rbp-18h]
  CallStackScopeTrace v37; // [rsp+D8h] [rbp+60h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(&v37, "AddByteStreamHandlerForSourcePackInfo", 123);
  v31 = 0;
  if ( *((_BYTE *)a4 + 33) )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    v8 = MFCreateByteStreamHandlerInprocActivate(&v31);
    if ( v8 < 0 )
    {
      v9 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v9 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v9 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v9->m_fEnabled )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v9);
        if ( ThreadRelativeContext->m_result != v8 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "AddByteStreamHandlerForSourcePackInfo", 129, v8);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v11 = 13;
LABEL_12:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_b75d7078c4363b03f2a23387d5361fbc_Traceguids, 0, v8);
        goto LABEL_83;
      }
      goto LABEL_83;
    }
LABEL_23:
    v8 = SetPackagedActivateAttributes(v31, a1, a4);
    if ( v8 >= 0 )
    {
      v30 = 1;
      v8 = (*(__int64 (__fastcall **)(struct IMFPluginControlInternal *, __int64, struct IMFActivate *, _QWORD, int *))(*(_QWORD *)a2 + 40LL))(
             a2,
             1,
             v31,
             (unsigned int)a1,
             &v30);
      if ( v8 >= 0 )
      {
        if ( v30 )
        {
          v33 = 0;
          v18 = v31;
          ActivateObject = v31->lpVtbl->ActivateObject;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
          v8 = ((__int64 (__fastcall *)(struct IMFActivate *, GUID *, struct IUnknown **))ActivateObject)(
                 v18,
                 &GUID_bb420aa4_765b_4a1f_91fe_d6a8a143924c,
                 &v33);
          if ( v8 >= 0 )
          {
            pv = 0;
            p_pv = &pv;
            ppwsz = 0;
            v36 = 1;
            StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)a4 + 1), 0);
            v8 = SHStrDupW(StringRawBuffer, &ppwsz);
            wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
            if ( v8 >= 0 )
            {
              v8 = CSourceResolverHandlerList::AddStoreHandler(a3, v33, (unsigned __int16 *)pv, *((_BYTE *)a4 + 34));
              if ( v8 >= 0 )
              {
                pv = 0;
              }
              else
              {
                v26 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  CallStackTracing::s_wpInstance = &stru_1801FC290;
                  if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                  {
                    v26 = CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v26 = &stru_1801F8A30;
                    CallStackTracing::s_wpInstance = &stru_1801F8A30;
                  }
                }
                if ( v26->m_fEnabled )
                {
                  v27 = CallStackTracing::GetThreadRelativeContext(v26);
                  if ( v27->m_result != v8 )
                    CallStackContext::TraceFailure(v27, "AddByteStreamHandlerForSourcePackInfo", 153, v8);
                }
                if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    19,
                    &WPP_b75d7078c4363b03f2a23387d5361fbc_Traceguids,
                    0,
                    v8);
                v28 = pv;
                pv = 0;
                if ( v28 )
                  CoTaskMemFree(v28);
              }
            }
            else
            {
              v23 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::s_wpInstance = &stru_1801FC290;
                if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                {
                  v23 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v23 = &stru_1801F8A30;
                  CallStackTracing::s_wpInstance = &stru_1801F8A30;
                }
              }
              if ( v23->m_fEnabled )
              {
                v24 = CallStackTracing::GetThreadRelativeContext(v23);
                if ( v24->m_result != v8 )
                  CallStackContext::TraceFailure(v24, "AddByteStreamHandlerForSourcePackInfo", 152, v8);
              }
              if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  18,
                  &WPP_b75d7078c4363b03f2a23387d5361fbc_Traceguids,
                  0,
                  v8);
              v25 = pv;
              pv = 0;
              if ( v25 )
                CoTaskMemFree(v25);
            }
          }
          else
          {
            v20 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v20 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v20 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v20->m_fEnabled )
            {
              v21 = CallStackTracing::GetThreadRelativeContext(v20);
              if ( v21->m_result != v8 )
                CallStackContext::TraceFailure(v21, "AddByteStreamHandlerForSourcePackInfo", 149, v8);
            }
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                17,
                &WPP_b75d7078c4363b03f2a23387d5361fbc_Traceguids,
                0,
                v8);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
        }
      }
      else
      {
        v16 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v16 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v16 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v16->m_fEnabled )
        {
          v17 = CallStackTracing::GetThreadRelativeContext(v16);
          if ( v17->m_result != v8 )
            CallStackContext::TraceFailure(v17, "AddByteStreamHandlerForSourcePackInfo", 144, v8);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v11 = 16;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v14 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v14 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v14->m_fEnabled )
      {
        v15 = CallStackTracing::GetThreadRelativeContext(v14);
        if ( v15->m_result != v8 )
          CallStackContext::TraceFailure(v15, "AddByteStreamHandlerForSourcePackInfo", 136, v8);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v11 = 15;
        goto LABEL_12;
      }
    }
    goto LABEL_83;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  v8 = MFCreateByteStreamHandlerAppServiceActivate(&v31);
  if ( v8 >= 0 )
    goto LABEL_23;
  v12 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v12 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v12 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v12->m_fEnabled )
  {
    v13 = CallStackTracing::GetThreadRelativeContext(v12);
    if ( v13->m_result != v8 )
      CallStackContext::TraceFailure(v13, "AddByteStreamHandlerForSourcePackInfo", 133, v8);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v11 = 14;
    goto LABEL_12;
  }
LABEL_83:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  CallStackScopeTrace::~CallStackScopeTrace(&v37);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180176e44  push    rbp
0x180176e46  push    rbx
0x180176e47  push    rsi
0x180176e48  push    rdi
0x180176e49  push    r12
0x180176e4b  push    r13
0x180176e4d  push    r14
0x180176e4f  push    r15
0x180176e51  mov     rbp, rsp
0x180176e54  sub     rsp, 78h
0x180176e58  mov     rsi, r9
0x180176e5b  mov     r15, r8
0x180176e5e  mov     r14, rdx
0x180176e61  mov     edi, ecx
0x180176e63  mov     r8d, 7Bh ; '{'; int
0x180176e69  lea     r13, aAddbytestreamh; "AddByteStreamHandlerForSourcePackInfo"
0x180176e70  mov     rdx, r13; char *
0x180176e73  lea     rcx, [rbp+arg_18]; this
0x180176e77  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180176e7c  nop
0x180176e7d  xor     r12d, r12d
0x180176e80  mov     [rbp+var_40], r12
0x180176e84  lea     rcx, [rbp+var_40]
0x180176e88  cmp     [rsi+21h], r12b
0x180176e8c  jz      loc_180176F50
0x180176e92  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176e97  lea     rcx, [rbp+var_40]
0x180176e9b  call    MFCreateByteStreamHandlerInprocActivate
0x180176ea0  mov     ebx, eax
0x180176ea2  test    eax, eax
0x180176ea4  jns     loc_180176FF0
0x180176eaa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180176eb1  test    rcx, rcx
0x180176eb4  jnz     short loc_180176EF4
0x180176eb6  lea     rcx, stru_1801FC290
0x180176ebd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180176ec4  mov     rdx, cs:stru_1801FC290.__vftable
0x180176ecb  mov     rax, [rdx+8]
0x180176ecf  mov     edx, 7F0h
0x180176ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180176ed9  test    eax, eax
0x180176edb  jnz     short loc_180176EED
0x180176edd  lea     rcx, stru_1801F8A30
0x180176ee4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180176eeb  jmp     short loc_180176EF4
0x180176eed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180176ef4  cmp     [rcx+8], r12b
0x180176ef8  jz      short loc_180176F1B
0x180176efa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180176eff  cmp     [rax+7CCh], ebx
0x180176f05  jz      short loc_180176F1B
0x180176f07  mov     r9d, ebx; int
0x180176f0a  mov     r8d, 81h; int
0x180176f10  mov     rdx, r13; char *
0x180176f13  mov     rcx, rax; this
0x180176f16  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180176f1b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180176f22  jb      loc_180177418
0x180176f28  mov     edx, 0Dh
0x180176f2d  mov     dword ptr [rsp+78h+var_58], ebx
0x180176f31  xor     r9d, r9d
0x180176f34  lea     r8, WPP_b75d7078c4363b03f2a23387d5361fbc_Traceguids
0x180176f3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180176f42  mov     rcx, [rcx+10h]
0x180176f46  call    WPP_SF_qD
0x180176f4b  jmp     loc_180177418
0x180176f50  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176f55  lea     rcx, [rbp+var_40]
0x180176f59  call    MFCreateByteStreamHandlerAppServiceActivate
0x180176f5e  mov     ebx, eax
0x180176f60  test    eax, eax
0x180176f62  jns     loc_180176FF0
0x180176f68  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180176f6f  test    rcx, rcx
0x180176f72  jnz     short loc_180176FB2
0x180176f74  lea     rcx, stru_1801FC290
0x180176f7b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180176f82  mov     rax, cs:stru_1801FC290.__vftable
0x180176f89  mov     edx, 7F0h
0x180176f8e  mov     rax, [rax+8]
0x180176f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180176f97  test    eax, eax
0x180176f99  jnz     short loc_180176FAB
0x180176f9b  lea     rcx, stru_1801F8A30
0x180176fa2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180176fa9  jmp     short loc_180176FB2
0x180176fab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180176fb2  cmp     [rcx+8], r12b
0x180176fb6  jz      short loc_180176FD9
0x180176fb8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180176fbd  cmp     [rax+7CCh], ebx
0x180176fc3  jz      short loc_180176FD9
0x180176fc5  mov     r9d, ebx; int
0x180176fc8  mov     r8d, 85h; int
0x180176fce  mov     rdx, r13; char *
0x180176fd1  mov     rcx, rax; this
0x180176fd4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180176fd9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180176fe0  jb      loc_180177418
0x180176fe6  mov     edx, 0Eh
0x180176feb  jmp     loc_180176F2D
0x180176ff0  mov     r8, rsi; struct SourcePackInfo *
0x180176ff3  mov     edx, edi; enum MF_PLUGIN_CONTROL_POLICY
0x180176ff5  mov     rcx, [rbp+var_40]; struct IMFActivate *
0x180176ff9  call    ?SetPackagedActivateAttributes@@YAJPEAUIMFActivate@@W4MF_PLUGIN_CONTROL_POLICY@@AEAUSourcePackInfo@@@Z; SetPackagedActivateAttributes(IMFActivate *,MF_PLUGIN_CONTROL_POLICY,SourcePackInfo &)
0x180176ffe  mov     ebx, eax
0x180177000  test    eax, eax
0x180177002  jns     loc_180177090
0x180177008  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18017700f  test    rcx, rcx
0x180177012  jnz     short loc_180177052
0x180177014  lea     rcx, stru_1801FC290
0x18017701b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180177022  mov     rax, cs:stru_1801FC290.__vftable
0x180177029  mov     edx, 7F0h
0x18017702e  mov     rax, [rax+8]
0x180177032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180177037  test    eax, eax
0x180177039  jnz     short loc_18017704B
0x18017703b  lea     rcx, stru_1801F8A30
0x180177042  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180177049  jmp     short loc_180177052
0x18017704b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180177052  cmp     [rcx+8], r12b
0x180177056  jz      short loc_180177079
0x180177058  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18017705d  cmp     [rax+7CCh], ebx
0x180177063  jz      short loc_180177079
0x180177065  mov     r9d, ebx; int
0x180177068  mov     r8d, 88h; int
0x18017706e  mov     rdx, r13; char *
0x180177071  mov     rcx, rax; this
0x180177074  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180177079  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180177080  jb      loc_180177418
0x180177086  mov     edx, 0Fh
0x18017708b  jmp     loc_180176F2D
0x180177090  mov     [rbp+var_48], 1
0x180177097  mov     rax, [r14]
0x18017709a  lea     rcx, [rbp+var_48]
0x18017709e  mov     [rsp+78h+var_58], rcx
0x1801770a3  mov     r9d, edi
0x1801770a6  mov     r8, [rbp+var_40]
0x1801770aa  mov     edx, 1
0x1801770af  mov     rcx, r14
0x1801770b2  mov     rax, [rax+28h]
0x1801770b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801770bb  mov     ebx, eax
0x1801770bd  test    eax, eax
0x1801770bf  jns     loc_18017714D
0x1801770c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801770cc  test    rcx, rcx
0x1801770cf  jnz     short loc_18017710F
0x1801770d1  lea     rcx, stru_1801FC290
0x1801770d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801770df  mov     rax, cs:stru_1801FC290.__vftable
0x1801770e6  mov     edx, 7F0h
0x1801770eb  mov     rax, [rax+8]
0x1801770ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801770f4  test    eax, eax
0x1801770f6  jnz     short loc_180177108
0x1801770f8  lea     rcx, stru_1801F8A30
0x1801770ff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180177106  jmp     short loc_18017710F
0x180177108  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18017710f  cmp     [rcx+8], r12b
0x180177113  jz      short loc_180177136
0x180177115  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18017711a  cmp     [rax+7CCh], ebx
0x180177120  jz      short loc_180177136
0x180177122  mov     r9d, ebx; int
0x180177125  mov     r8d, 90h; int
0x18017712b  mov     rdx, r13; char *
0x18017712e  mov     rcx, rax; this
0x180177131  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180177136  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18017713d  jb      loc_180177418
0x180177143  mov     edx, 10h
0x180177148  jmp     loc_180176F2D
0x18017714d  cmp     [rbp+var_48], r12d
0x180177151  jz      loc_180177418
0x180177157  mov     [rbp+var_30], r12
0x18017715b  mov     rdi, [rbp+var_40]
0x18017715f  mov     rax, [rdi]
0x180177162  mov     rbx, [rax+108h]
0x180177169  lea     rcx, [rbp+var_30]
0x18017716d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180177172  lea     r8, [rbp+var_30]
0x180177176  lea     rdx, _GUID_bb420aa4_765b_4a1f_91fe_d6a8a143924c
0x18017717d  mov     rcx, rdi
0x180177180  mov     rax, rbx
0x180177183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180177188  mov     ebx, eax
0x18017718a  test    eax, eax
0x18017718c  jns     loc_180177238
0x180177192  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180177199  test    rcx, rcx
0x18017719c  jnz     short loc_1801771DC
0x18017719e  lea     rcx, stru_1801FC290
0x1801771a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801771ac  mov     rax, cs:stru_1801FC290.__vftable
0x1801771b3  mov     edx, 7F0h
0x1801771b8  mov     rax, [rax+8]
0x1801771bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801771c1  test    eax, eax
0x1801771c3  jnz     short loc_1801771D5
0x1801771c5  lea     rcx, stru_1801F8A30
0x1801771cc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801771d3  jmp     short loc_1801771DC
0x1801771d5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801771dc  cmp     [rcx+8], r12b
0x1801771e0  jz      short loc_180177203
0x1801771e2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801771e7  cmp     [rax+7CCh], ebx
0x1801771ed  jz      short loc_180177203
0x1801771ef  mov     r9d, ebx; int
0x1801771f2  mov     r8d, 95h; int
0x1801771f8  mov     rdx, r13; char *
0x1801771fb  mov     rcx, rax; this
0x1801771fe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180177203  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18017720a  jb      loc_18017740E
0x180177210  mov     edx, 11h
0x180177215  mov     dword ptr [rsp+78h+var_58], ebx
0x180177219  xor     r9d, r9d
0x18017721c  lea     r8, WPP_b75d7078c4363b03f2a23387d5361fbc_Traceguids
0x180177223  mov     rcx, cs:WPP_GLOBAL_Control
0x18017722a  mov     rcx, [rcx+10h]
0x18017722e  call    WPP_SF_qD
0x180177233  jmp     loc_18017740E
0x180177238  mov     [rbp+pv], r12
0x18017723c  lea     rax, [rbp+pv]
0x180177240  mov     [rbp+var_28], rax
0x180177244  mov     [rbp+ppwsz], r12
0x180177248  mov     [rbp+var_18], 1
0x18017724c  xor     edx, edx; length
0x18017724e  mov     rcx, [rsi+8]; string
0x180177252  call    cs:__imp_WindowsGetStringRawBuffer
0x180177258  lea     rdx, [rbp+ppwsz]; ppwsz
0x18017725c  mov     rcx, rax; psz
0x18017725f  call    cs:__imp_SHStrDupW
0x180177265  mov     ebx, eax
0x180177267  lea     rcx, [rbp+var_28]
0x18017726b  call    ??1?$out_param_t@V?$unique_ptr@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180177270  mov     eax, ebx
0x180177272  shr     eax, 1Fh
0x180177275  test    al, al
0x180177277  jz      loc_180177338
0x18017727d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180177284  test    rcx, rcx
0x180177287  jnz     short loc_1801772C7
0x180177289  lea     rcx, stru_1801FC290
0x180177290  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180177297  mov     rax, cs:stru_1801FC290.__vftable
0x18017729e  mov     edx, 7F0h
0x1801772a3  mov     rax, [rax+8]
0x1801772a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801772ac  test    eax, eax
0x1801772ae  jnz     short loc_1801772C0
0x1801772b0  lea     rcx, stru_1801F8A30
0x1801772b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801772be  jmp     short loc_1801772C7
0x1801772c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801772c7  cmp     [rcx+8], r12b
0x1801772cb  jz      short loc_1801772F2
0x1801772cd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801772d2  test    ebx, ebx
0x1801772d4  jns     short loc_1801772F2
0x1801772d6  cmp     [rax+7CCh], ebx
0x1801772dc  jz      short loc_1801772F2
0x1801772de  mov     r9d, ebx; int
0x1801772e1  mov     r8d, 98h; int
0x1801772e7  mov     rdx, r13; char *
0x1801772ea  mov     rcx, rax; this
0x1801772ed  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801772f2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801772f9  jb      short loc_18017731F
0x1801772fb  mov     edx, 12h
0x180177300  mov     dword ptr [rsp+78h+var_58], ebx
0x180177304  xor     r9d, r9d
0x180177307  lea     r8, WPP_b75d7078c4363b03f2a23387d5361fbc_Traceguids
0x18017730e  mov     rcx, cs:WPP_GLOBAL_Control
0x180177315  mov     rcx, [rcx+10h]
0x180177319  call    WPP_SF_qD
0x18017731e  nop
0x18017731f  mov     rcx, [rbp+pv]; pv
0x180177323  mov     [rbp+pv], r12
0x180177327  test    rcx, rcx
0x18017732a  jz      short loc_180177333
0x18017732c  call    cs:__imp_CoTaskMemFree
0x180177332  nop
0x180177333  jmp     loc_18017740E
0x180177338  mov     r9b, [rsi+22h]; bool
0x18017733c  mov     r8, [rbp+pv]; unsigned __int16 *
0x180177340  mov     rdx, [rbp+var_30]; struct IUnknown *
0x180177344  mov     rcx, r15; this
0x180177347  call    ?AddStoreHandler@CSourceResolverHandlerList@@QEAAJPEAUIUnknown@@PEAG_N@Z; CSourceResolverHandlerList::AddStoreHandler(IUnknown *,ushort *,bool)
0x18017734c  mov     ebx, eax
0x18017734e  test    eax, eax
0x180177350  jns     loc_18017740A
  ... truncated ...
```
