# CursorManager::Initialize(void)

- ea: `0x1800e5a54`
- end: `0x1800e5c7d`
- name: `?Initialize@CursorManager@@IEAAJXZ`
- size: `553`
- prototype: `__int64 __fastcall(CursorManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801734ac`

## callees

- `0x180012b74`
- `0x18003afb0`
- `0x18007d670`
- `0x18008dcac`
- `0x18008ead4`
- `0x1800e5a54`
- `0x1800e5c84`
- `0x180118e84`
- `0x1801ce010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x1800e5c2e`
- `ntdll!RtlPublishWnfStateData` at `0x1800e5c2e`
- `CoreMessaging!CoreUICreate` at `0x1800e5a92`
- `CoreMessaging!CoreUICreate` at `0x1800e5a92`

## string_xrefs

- `0x1800e5b95`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\cursor\manager\cursormanager.cpp`
- `0x1800e5bfd`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\cursor\manager\cursormanager.cpp`
- `0x1800e5c3f`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\cursor\manager\cursormanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CursorManager::Initialize(CursorManager *this)
{
  _QWORD *v2; // rsi
  int Descriptor; // eax
  __int64 v4; // rdx
  __int64 v5; // r9
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64, const wchar_t *, __int64 *); // rbx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  int v13; // eax
  int v14; // eax
  int v15; // [rsp+20h] [rbp-28h]
  __int64 v16; // [rsp+30h] [rbp-18h] BYREF
  char v17; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]
  int v19; // [rsp+80h] [rbp+38h] BYREF
  __int64 v20; // [rsp+88h] [rbp+40h] BYREF
  __int64 v21; // [rsp+90h] [rbp+48h] BYREF
  CursorManager *v22; // [rsp+98h] [rbp+50h] BYREF

  v21 = 0;
  v20 = 0;
  v16 = 0;
  v17 = 0;
  v2 = (_QWORD *)((char *)this + 32);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 32);
  Descriptor = CoreUICreate(v2);
  v6 = Descriptor;
  if ( Descriptor < 0 )
  {
    v7 = 66;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\cursor\\manager\\cursormanager.cpp",
      (const char *)(unsigned int)Descriptor,
      v15);
    InputSecurityDescriptor::~InputSecurityDescriptor((InputSecurityDescriptor *)&v16);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
    return v6;
  }
  Descriptor = InputSecurityDescriptor::QueryDescriptor(
                 (__int64)&v16,
                 v4,
                 (__int64)L"System\\Input\\CursorManagerPort",
                 v5,
                 v15);
  v6 = Descriptor;
  if ( Descriptor < 0 )
  {
    v7 = 70;
    goto LABEL_13;
  }
  v8 = *v2;
  v9 = *(__int64 (__fastcall **)(__int64, __int64, const wchar_t *, __int64 *))(*(_QWORD *)*v2 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  Descriptor = v9(v8, v16, L"System\\Input\\CursorManagerPort", &v21);
  v6 = Descriptor;
  if ( Descriptor < 0 )
  {
    v7 = 75;
    goto LABEL_13;
  }
  v15 = (_DWORD)this + 64;
  Descriptor = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(void *, void *, int), CursorManager *, __int64))(*(_QWORD *)*v2 + 104LL))(
                 *v2,
                 CursorManager::OnCoreMessageStatic,
                 this,
                 v21);
  v6 = Descriptor;
  if ( Descriptor < 0 )
  {
    v7 = 81;
    goto LABEL_13;
  }
  v10 = *v2;
  v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v2 + 24LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  Descriptor = v11(v10, &v20);
  v6 = Descriptor;
  if ( Descriptor < 0 )
  {
    v7 = 83;
    goto LABEL_13;
  }
  Descriptor = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, __int64))(*(_QWORD *)v20 + 40LL))(
                 v20,
                 L"System\\Input\\CursorManagerEndpoint",
                 *((_QWORD *)this + 8),
                 1);
  v6 = Descriptor;
  if ( Descriptor < 0 )
  {
    v7 = 88;
    goto LABEL_13;
  }
  v22 = this;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 48);
  v13 = Microsoft::WRL::Details::MakeAndInitialize<MessageProxyReconnectAdapter,MessageProxyReconnectAdapter,_GUID const &,unsigned short const * const &,CursorManager *>(
          (char *)this + 48,
          &GUID_5f9adcb2_65c8_40db_988f_dffbe437aa7a,
          &off_1801DA3C0,
          &v22);
  if ( v13 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\cursor\\manager\\cursormanager.cpp",
      (const char *)(unsigned int)v13,
      v15);
  v19 = 1;
  v14 = RtlPublishWnfStateData(WNF_ISM_CURSOR_MANAGER_READY, 0, &v19, 4);
  if ( v14 < 0 )
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)0x66,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\cursor\\manager\\cursormanager.cpp",
      (const char *)(unsigned int)v14,
      0);
  InputSecurityDescriptor::~InputSecurityDescriptor((InputSecurityDescriptor *)&v16);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  return 0;
}

```

## disassembly

```asm
0x1800e5a54  push    rbp
0x1800e5a56  push    rbx
0x1800e5a57  push    rsi
0x1800e5a58  push    rdi
0x1800e5a59  push    r14
0x1800e5a5b  push    r15
0x1800e5a5d  mov     rbp, rsp
0x1800e5a60  sub     rsp, 48h
0x1800e5a64  mov     r14, rcx
0x1800e5a67  mov     [rbp+arg_10], 0
0x1800e5a6f  mov     [rbp+arg_8], 0
0x1800e5a77  mov     [rbp+var_18], 0
0x1800e5a7f  mov     [rbp+var_10], 0
0x1800e5a83  lea     rsi, [rcx+20h]
0x1800e5a87  mov     rcx, rsi
0x1800e5a8a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e5a8f  mov     rcx, rsi
0x1800e5a92  call    cs:__imp_CoreUICreate
0x1800e5a98  mov     ebx, eax
0x1800e5a9a  test    eax, eax
0x1800e5a9c  jns     short loc_1800E5AA8
0x1800e5a9e  mov     edx, 42h ; 'B'
0x1800e5aa3  jmp     loc_1800E5B92
0x1800e5aa8  lea     r8, aSystemInputCur_2; "System\\Input\\CursorManagerPort"
0x1800e5aaf  lea     rcx, [rbp+var_18]
0x1800e5ab3  call    ?QueryDescriptor@InputSecurityDescriptor@@QEAAJW4TransientObject_Type@@PEBG@Z; InputSecurityDescriptor::QueryDescriptor(TransientObject_Type,ushort const *)
0x1800e5ab8  mov     ebx, eax
0x1800e5aba  test    eax, eax
0x1800e5abc  jns     short loc_1800E5AC8
0x1800e5abe  mov     edx, 46h ; 'F'
0x1800e5ac3  jmp     loc_1800E5B92
0x1800e5ac8  mov     rdi, [rsi]
0x1800e5acb  mov     rax, [rdi]
0x1800e5ace  mov     rbx, [rax+38h]
0x1800e5ad2  lea     rcx, [rbp+arg_10]
0x1800e5ad6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e5adb  lea     r9, [rbp+arg_10]
0x1800e5adf  lea     r8, aSystemInputCur_2; "System\\Input\\CursorManagerPort"
0x1800e5ae6  mov     rdx, [rbp+var_18]
0x1800e5aea  mov     rcx, rdi
0x1800e5aed  mov     rax, rbx
0x1800e5af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5af5  mov     ebx, eax
0x1800e5af7  test    eax, eax
0x1800e5af9  jns     short loc_1800E5B05
0x1800e5afb  mov     edx, 4Bh ; 'K'
0x1800e5b00  jmp     loc_1800E5B92
0x1800e5b05  mov     rcx, [rsi]
0x1800e5b08  lea     r15, [r14+40h]
0x1800e5b0c  mov     rax, [rcx]
0x1800e5b0f  mov     qword ptr [rsp+48h+var_28], r15; int
0x1800e5b14  mov     r9, [rbp+arg_10]
0x1800e5b18  mov     r8, r14
0x1800e5b1b  lea     rdx, ?OnCoreMessageStatic@CursorManager@@SAJPEAX0H@Z; CursorManager::OnCoreMessageStatic(void *,void *,int)
0x1800e5b22  mov     rax, [rax+68h]
0x1800e5b26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5b2b  mov     ebx, eax
0x1800e5b2d  test    eax, eax
0x1800e5b2f  jns     short loc_1800E5B38
0x1800e5b31  mov     edx, 51h ; 'Q'
0x1800e5b36  jmp     short loc_1800E5B92
0x1800e5b38  mov     rdi, [rsi]
0x1800e5b3b  mov     rax, [rdi]
0x1800e5b3e  mov     rbx, [rax+18h]
0x1800e5b42  lea     rcx, [rbp+arg_8]
0x1800e5b46  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e5b4b  lea     rdx, [rbp+arg_8]
0x1800e5b4f  mov     rcx, rdi
0x1800e5b52  mov     rax, rbx
0x1800e5b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5b5a  mov     ebx, eax
0x1800e5b5c  test    eax, eax
0x1800e5b5e  jns     short loc_1800E5B67
0x1800e5b60  mov     edx, 53h ; 'S'
0x1800e5b65  jmp     short loc_1800E5B92
0x1800e5b67  mov     rcx, [rbp+arg_8]
0x1800e5b6b  mov     rax, [rcx]
0x1800e5b6e  mov     edi, 1
0x1800e5b73  mov     r9d, edi
0x1800e5b76  mov     r8, [r15]
0x1800e5b79  lea     rdx, aSystemInputCur_0; "System\\Input\\CursorManagerEndpoint"
0x1800e5b80  mov     rax, [rax+28h]
0x1800e5b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5b89  mov     ebx, eax
0x1800e5b8b  test    eax, eax
0x1800e5b8d  jns     short loc_1800E5BCA
0x1800e5b8f  lea     edx, [rdi+57h]; void *
0x1800e5b92  mov     r9d, eax; char *
0x1800e5b95  lea     r8, aOnecoreuapWind_32; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800e5b9c  mov     rcx, [rbp+30h]; this
0x1800e5ba0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5ba5  nop
0x1800e5ba6  lea     rcx, [rbp+var_18]; this
0x1800e5baa  call    ??1InputSecurityDescriptor@@QEAA@XZ; InputSecurityDescriptor::~InputSecurityDescriptor(void)
0x1800e5baf  nop
0x1800e5bb0  lea     rcx, [rbp+arg_8]
0x1800e5bb4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e5bb9  nop
0x1800e5bba  lea     rcx, [rbp+arg_10]
0x1800e5bbe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e5bc3  mov     eax, ebx
0x1800e5bc5  jmp     loc_1800E5C70
0x1800e5bca  mov     [rbp+arg_18], r14
0x1800e5bce  lea     rcx, [r14+30h]
0x1800e5bd2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e5bd7  lea     r9, [rbp+arg_18]
0x1800e5bdb  lea     r8, off_1801DA3C0; "System\\Input\\CursorBrokerEndpoint"
0x1800e5be2  lea     rdx, _GUID_5f9adcb2_65c8_40db_988f_dffbe437aa7a
0x1800e5be9  lea     rcx, [r14+30h]
0x1800e5bed  call    ??$MakeAndInitialize@VMessageProxyReconnectAdapter@@V1@AEBU_GUID@@AEBQEBGPEAVCursorManager@@@Details@WRL@Microsoft@@YAJPEAPEAVMessageProxyReconnectAdapter@@AEBU_GUID@@AEBQEBG$$QEAPEAVCursorManager@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MessageProxyReconnectAdapter,MessageProxyReconnectAdapter,_GUID const &,ushort const * const &,CursorManager *>(MessageProxyReconnectAdapter * *,_GUID const &,ushort const * const &,CursorManager * &&)
0x1800e5bf2  mov     rcx, [rbp+30h]; this
0x1800e5bf6  test    eax, eax
0x1800e5bf8  jns     short loc_1800E5C0F
0x1800e5bfa  mov     r9d, eax; char *
0x1800e5bfd  lea     r8, aOnecoreuapWind_32; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800e5c04  mov     edx, 62h ; 'b'; void *
0x1800e5c09  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800e5c0f  mov     [rbp+arg_0], edi
0x1800e5c12  mov     qword ptr [rsp+48h+var_28], 0; int
0x1800e5c1b  mov     r9d, 4
0x1800e5c21  lea     r8, [rbp+arg_0]
0x1800e5c25  xor     edx, edx
0x1800e5c27  mov     rcx, cs:WNF_ISM_CURSOR_MANAGER_READY
0x1800e5c2e  call    cs:__imp_RtlPublishWnfStateData
0x1800e5c34  mov     rcx, [rbp+30h]; this
0x1800e5c38  test    eax, eax
0x1800e5c3a  jns     short loc_1800E5C51
0x1800e5c3c  mov     r9d, eax; char *
0x1800e5c3f  lea     r8, aOnecoreuapWind_32; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800e5c46  mov     edx, 66h ; 'f'; void *
0x1800e5c4b  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x1800e5c50  nop
0x1800e5c51  lea     rcx, [rbp+var_18]; this
0x1800e5c55  call    ??1InputSecurityDescriptor@@QEAA@XZ; InputSecurityDescriptor::~InputSecurityDescriptor(void)
0x1800e5c5a  nop
0x1800e5c5b  lea     rcx, [rbp+arg_8]
0x1800e5c5f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e5c64  nop
0x1800e5c65  lea     rcx, [rbp+arg_10]
0x1800e5c69  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e5c6e  xor     eax, eax
0x1800e5c70  add     rsp, 48h
0x1800e5c74  pop     r15
0x1800e5c76  pop     r14
0x1800e5c78  pop     rdi
0x1800e5c79  pop     rsi
0x1800e5c7a  pop     rbx
0x1800e5c7b  pop     rbp
0x1800e5c7c  retn
```
