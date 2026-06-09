# DWMCursorBroker::Initialize(void)

- ea: `0x18003a734`
- end: `0x18003aa5a`
- name: `?Initialize@DWMCursorBroker@@QEAAJXZ`
- size: `806`
- prototype: `__int64 __fastcall(DWMCursorBroker *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007b2a8`

## callees

- `0x180012b74`
- `0x180033c84`
- `0x18003a734`
- `0x18003afb0`
- `0x18003b040`
- `0x180061c60`
- `0x18007d670`
- `0x18008dcac`
- `0x18008ead4`
- `0x1800aae90`
- `0x1801ce010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18003a913`
- `msvcp_win!_Mtx_unlock` at `0x18003aa4d`
- `msvcp_win!_Mtx_unlock` at `0x18003a913`
- `msvcp_win!_Mtx_unlock` at `0x18003aa4d`
- `CoreMessaging!CoreUICreate` at `0x18003a7a4`
- `CoreMessaging!CoreUICreate` at `0x18003a7a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a92a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a92a`
- `CoreUIComponents!CoreUIFactoryCreate` at `0x18003a804`
- `CoreUIComponents!CoreUIFactoryCreate` at `0x18003a804`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18003a902`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18003a902`

## string_xrefs

- `0x18003a778`: `System\Input\CursorBrokerPort`
- `0x18003a7d0`: `System\Input\CursorBrokerPort`
- `0x18003a870`: `System\Input\CursorBrokerEndpoint`
- `0x18003a8e1`: `onecoreuap\windows\moderncore\inputv2\systeminputrouters\dwm\components\cursor\lib\dwmcursorbroker.cpp`
- `0x18003a936`: `onecoreuap\windows\moderncore\inputv2\systeminputrouters\dwm\components\cursor\lib\dwmcursorbroker.cpp`
- `0x18003a94b`: `onecoreuap\windows\moderncore\inputv2\systeminputrouters\dwm\components\cursor\lib\dwmcursorbroker.cpp`
- `0x18003a960`: `onecoreuap\windows\moderncore\inputv2\systeminputrouters\dwm\components\cursor\lib\dwmcursorbroker.cpp`
- `0x18003a979`: `onecoreuap\windows\moderncore\inputv2\systeminputrouters\dwm\components\cursor\lib\dwmcursorbroker.cpp`
- `0x18003a997`: `onecoreuap\windows\moderncore\inputv2\systeminputrouters\dwm\components\cursor\lib\dwmcursorbroker.cpp`
- `0x18003a9b2`: `onecoreuap\windows\moderncore\inputv2\systeminputrouters\dwm\components\cursor\lib\dwmcursorbroker.cpp`
- `0x18003aa01`: `onecoreuap\windows\moderncore\inputv2\systeminputrouters\dwm\components\cursor\lib\dwmcursorbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall DWMCursorBroker::Initialize(DWMCursorBroker *this)
{
  __int64 v2; // rdx
  int v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HLOCAL, const wchar_t *, char *); // rbx
  int v8; // eax
  _QWORD *v9; // rsi
  int v10; // eax
  int v11; // eax
  __int64 v12; // rsi
  __int64 (__fastcall *v13)(__int64, unsigned __int64, _QWORD, _QWORD); // rdi
  int v14; // eax
  _QWORD *v15; // rsi
  struct InputConfigContextProvider *Instance; // rax
  int v17; // eax
  int v19; // eax
  int v20; // [rsp+20h] [rbp-50h]
  HLOCAL hMem; // [rsp+40h] [rbp-30h] BYREF
  char v22; // [rsp+48h] [rbp-28h]
  _BYTE v23[32]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  unsigned int v25; // [rsp+B8h] [rbp+48h] BYREF
  void *v26; // [rsp+C0h] [rbp+50h]
  __int64 v27; // [rsp+C8h] [rbp+58h]

  v26 = &DWMCursorBroker::s_lock;
  std::_Mutex_base::lock((std::_Mutex_base *)&DWMCursorBroker::s_lock);
  hMem = 0;
  v22 = 0;
  v25 = 0;
  v27 = 0;
  v3 = InputSecurityDescriptor::QueryDescriptor(&hMem, v2, L"System\\Input\\CursorBrokerPort");
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\components\\cursor\\lib\\dwmcursorbroker.cpp",
      (const char *)(unsigned int)v3,
      v20);
LABEL_9:
    if ( hMem )
    {
      if ( v22 )
        FreeTransientObjectSecurityDescriptor();
      else
        LocalFree(hMem);
      hMem = 0;
    }
    goto LABEL_13;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 176);
  v5 = CoreUICreate((char *)this + 176);
  v4 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\components\\cursor\\lib\\dwmcursorbroker.cpp",
      (const char *)(unsigned int)v5,
      v20);
LABEL_24:
    InputSecurityDescriptor::~InputSecurityDescriptor((InputSecurityDescriptor *)&hMem);
LABEL_13:
    _Mtx_unlock((_Mtx_t)&DWMCursorBroker::s_lock);
    return v4;
  }
  v6 = *((_QWORD *)this + 22);
  v7 = *(__int64 (__fastcall **)(__int64, HLOCAL, const wchar_t *, char *))(*(_QWORD *)v6 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 200);
  v8 = v7(v6, hMem, L"System\\Input\\CursorBrokerPort", (char *)this + 200);
  if ( v8 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\components\\cursor\\lib\\dwmcursorbroker.cpp",
      (const char *)(unsigned int)v8,
      v20);
  v9 = (_QWORD *)((char *)this + 184);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 184);
  v10 = CoreUIFactoryCreate((char *)this + 184);
  v4 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\components\\cursor\\lib\\dwmcursorbroker.cpp",
      (const char *)(unsigned int)v10,
      v20);
    goto LABEL_24;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, GUID *, unsigned int *))(*(_QWORD *)*v9 + 24LL))(
          *v9,
          &GUID_5f9adcb2_65c8_40db_988f_dffbe437aa7a,
          &v25);
  if ( v11 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\components\\cursor\\lib\\dwmcursorbroker.cpp",
      (const char *)(unsigned int)v11,
      v20);
  v12 = *v9;
  v13 = *(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD, _QWORD))(*(_QWORD *)v12 + 32LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 192);
  v14 = v13(v12, ((unsigned __int64)this + 8) & -(__int64)(this != 0), 0, v25);
  if ( v14 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x59,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\components\\cursor\\lib\\dwmcursorbroker.cpp",
      (const char *)(unsigned int)v14,
      (int)L"System\\Input\\CursorBrokerEndpoint");
  v15 = (_QWORD *)((char *)this + 472);
  Instance = InputConfigContextProvider::GetInstance();
  Microsoft::WRL::ComPtr<ISystemContextProvider>::operator=<InputConfigContextProvider>((char *)this + 472, Instance);
  v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v15 + 24LL))(
          *v15,
          ((unsigned __int64)this + 16) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
  v4 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\components\\cursor\\lib\\dwmcursorbroker.cpp",
      (const char *)(unsigned int)v17,
      (int)L"System\\Input\\CursorBrokerEndpoint");
    goto LABEL_9;
  }
  v23[24] = 0;
  if ( (*(int (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v15 + 40LL))(*v15, v23) >= 0 )
  {
    v19 = (*(__int64 (__fastcall **)(char *, _BYTE *))(*((_QWORD *)this + 2) + 24LL))((char *)this + 16, v23);
    v4 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\components\\cursor\\lib\\dwmcursorbroker.cpp",
        (const char *)(unsigned int)v19,
        (int)L"System\\Input\\CursorBrokerEndpoint");
      std::_Variant_base<std::monostate,InputConfigContextMessage,DisplayOcclusionContextMessage,VirtualTouchpadContextMessage,MIT_WIN32K_INPUTDESKTOP_STATE_MESSAGE>::_Destroy(v23);
      goto LABEL_24;
    }
  }
  *((_DWORD *)this + 114) = 3;
  std::_Variant_base<std::monostate,InputConfigContextMessage,DisplayOcclusionContextMessage,VirtualTouchpadContextMessage,MIT_WIN32K_INPUTDESKTOP_STATE_MESSAGE>::_Destroy(v23);
  InputSecurityDescriptor::~InputSecurityDescriptor((InputSecurityDescriptor *)&hMem);
  _Mtx_unlock((_Mtx_t)&DWMCursorBroker::s_lock);
  return 0;
}

```

## disassembly

```asm
0x18003a734  push    rbp
0x18003a736  push    rbx
0x18003a737  push    rsi
0x18003a738  push    rdi
0x18003a739  push    r13
0x18003a73b  push    r14
0x18003a73d  push    r15
0x18003a73f  mov     rbp, rsp
0x18003a742  sub     rsp, 70h
0x18003a746  mov     r14, rcx
0x18003a749  lea     r13, ?s_lock@DWMCursorBroker@@0Vrecursive_mutex@std@@A; std::recursive_mutex DWMCursorBroker::s_lock
0x18003a750  mov     [rbp+arg_10], r13
0x18003a754  mov     rcx, r13; this
0x18003a757  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18003a75c  nop
0x18003a75d  mov     [rbp+hMem], 0
0x18003a765  mov     [rbp+var_28], 0
0x18003a769  mov     [rbp+arg_8], 0
0x18003a770  mov     [rbp+arg_18], 0
0x18003a778  lea     r8, aSystemInputCur_1; "System\\Input\\CursorBrokerPort"
0x18003a77f  lea     rcx, [rbp+hMem]
0x18003a783  call    ?QueryDescriptor@InputSecurityDescriptor@@QEAAJW4TransientObject_Type@@PEBG@Z; InputSecurityDescriptor::QueryDescriptor(TransientObject_Type,ushort const *)
0x18003a788  mov     ebx, eax
0x18003a78a  test    eax, eax
0x18003a78c  js      loc_18003A972
0x18003a792  lea     rdi, [r14+0B0h]
0x18003a799  mov     rcx, rdi
0x18003a79c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a7a1  mov     rcx, rdi
0x18003a7a4  call    cs:__imp_CoreUICreate
0x18003a7aa  mov     ebx, eax
0x18003a7ac  test    eax, eax
0x18003a7ae  js      loc_18003A990
0x18003a7b4  mov     rdi, [rdi]
0x18003a7b7  mov     rax, [rdi]
0x18003a7ba  mov     rbx, [rax+38h]
0x18003a7be  lea     r15, [r14+0C8h]
0x18003a7c5  mov     rcx, r15
0x18003a7c8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a7cd  mov     r9, r15
0x18003a7d0  lea     r8, aSystemInputCur_1; "System\\Input\\CursorBrokerPort"
0x18003a7d7  mov     rdx, [rbp+hMem]
0x18003a7db  mov     rcx, rdi
0x18003a7de  mov     rax, rbx
0x18003a7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a7e6  mov     rcx, [rbp+38h]; this
0x18003a7ea  test    eax, eax
0x18003a7ec  js      loc_18003A933
0x18003a7f2  lea     rsi, [r14+0B8h]
0x18003a7f9  mov     rcx, rsi
0x18003a7fc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a801  mov     rcx, rsi
0x18003a804  call    cs:__imp_CoreUIFactoryCreate
0x18003a80a  mov     ebx, eax
0x18003a80c  test    eax, eax
0x18003a80e  js      loc_18003A9AB
0x18003a814  mov     rcx, [rsi]
0x18003a817  mov     rax, [rcx]
0x18003a81a  lea     r8, [rbp+arg_8]
0x18003a81e  lea     rdx, _GUID_5f9adcb2_65c8_40db_988f_dffbe437aa7a
0x18003a825  mov     rax, [rax+18h]
0x18003a829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a82e  mov     rcx, [rbp+38h]; this
0x18003a832  test    eax, eax
0x18003a834  js      loc_18003A948
0x18003a83a  mov     rsi, [rsi]
0x18003a83d  mov     rax, [rsi]
0x18003a840  mov     rdi, [rax+20h]
0x18003a844  lea     rbx, [r14+0C0h]
0x18003a84b  mov     rcx, rbx
0x18003a84e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a853  mov     rdx, r14
0x18003a856  lea     r8, [r14+8]
0x18003a85a  neg     rdx
0x18003a85d  sbb     rdx, rdx
0x18003a860  and     rdx, r8
0x18003a863  mov     [rsp+70h+var_40], rbx
0x18003a868  mov     r8, [r15]
0x18003a86b  mov     [rsp+70h+var_48], r8
0x18003a870  lea     rax, aSystemInputCur; "System\\Input\\CursorBrokerEndpoint"
0x18003a877  mov     qword ptr [rsp+70h+var_50], rax; int
0x18003a87c  mov     r9d, [rbp+arg_8]
0x18003a880  xor     r8d, r8d
0x18003a883  mov     rcx, rsi
0x18003a886  mov     rax, rdi
0x18003a889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a88e  mov     rcx, [rbp+38h]; this
0x18003a892  test    eax, eax
0x18003a894  js      loc_18003A95D
0x18003a89a  lea     rsi, [r14+1D8h]
0x18003a8a1  call    ?GetInstance@InputConfigContextProvider@@SAPEAV1@XZ; InputConfigContextProvider::GetInstance(void)
0x18003a8a6  mov     rdx, rax
0x18003a8a9  mov     rcx, rsi
0x18003a8ac  call    ??$?4VInputConfigContextProvider@@@?$ComPtr@UISystemContextProvider@@@WRL@Microsoft@@QEAAAEAV012@PEAVInputConfigContextProvider@@@Z; Microsoft::WRL::ComPtr<ISystemContextProvider>::operator=<InputConfigContextProvider>(InputConfigContextProvider *)
0x18003a8b1  mov     rcx, [rsi]
0x18003a8b4  lea     rdi, [r14+10h]
0x18003a8b8  mov     r8, [rcx]
0x18003a8bb  mov     rax, r14
0x18003a8be  neg     rax
0x18003a8c1  sbb     rdx, rdx
0x18003a8c4  and     rdx, rdi
0x18003a8c7  mov     rax, [r8+18h]
0x18003a8cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a8d0  mov     ebx, eax
0x18003a8d2  test    eax, eax
0x18003a8d4  jns     loc_18003A9C6
0x18003a8da  mov     rcx, [rbp+38h]; this
0x18003a8de  mov     r9d, eax; char *
0x18003a8e1  lea     r8, aOnecoreuapWind_73; "onecoreuap\\windows\\moderncore\\inputv"...
0x18003a8e8  mov     edx, 5Dh ; ']'; void *
0x18003a8ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a8f2  nop
0x18003a8f3  mov     rcx, [rbp+hMem]; hMem
0x18003a8f7  test    rcx, rcx
0x18003a8fa  jz      short loc_18003A910
0x18003a8fc  cmp     [rbp+var_28], 0
0x18003a900  jz      short loc_18003A92A
0x18003a902  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18003a908  mov     [rbp+hMem], 0
0x18003a910  mov     rcx, r13; _Mtx_t
0x18003a913  call    cs:__imp__Mtx_unlock
0x18003a919  mov     eax, ebx
0x18003a91b  add     rsp, 70h
0x18003a91f  pop     r15
0x18003a921  pop     r14
0x18003a923  pop     r13
0x18003a925  pop     rdi
0x18003a926  pop     rsi
0x18003a927  pop     rbx
0x18003a928  pop     rbp
0x18003a929  retn
0x18003a92a  call    cs:__imp_LocalFree
0x18003a930  nop
0x18003a931  jmp     short loc_18003A908
0x18003a933  mov     r9d, eax; char *
0x18003a936  lea     r8, aOnecoreuapWind_73; "onecoreuap\\windows\\moderncore\\inputv"...
0x18003a93d  mov     edx, 4Bh ; 'K'; void *
0x18003a942  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18003a948  mov     r9d, eax; char *
0x18003a94b  lea     r8, aOnecoreuapWind_73; "onecoreuap\\windows\\moderncore\\inputv"...
0x18003a952  mov     edx, 51h ; 'Q'; void *
0x18003a957  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18003a95d  mov     r9d, eax; char *
0x18003a960  lea     r8, aOnecoreuapWind_73; "onecoreuap\\windows\\moderncore\\inputv"...
0x18003a967  mov     edx, 59h ; 'Y'; void *
0x18003a96c  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18003a972  mov     rcx, [rbp+38h]; this
0x18003a976  mov     r9d, eax; char *
0x18003a979  lea     r8, aOnecoreuapWind_73; "onecoreuap\\windows\\moderncore\\inputv"...
0x18003a980  mov     edx, 44h ; 'D'; void *
0x18003a985  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a98a  nop
0x18003a98b  jmp     loc_18003A8F3
0x18003a990  mov     rcx, [rbp+38h]; this
0x18003a994  mov     r9d, eax; char *
0x18003a997  lea     r8, aOnecoreuapWind_73; "onecoreuap\\windows\\moderncore\\inputv"...
0x18003a99e  mov     edx, 46h ; 'F'; void *
0x18003a9a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a9a8  nop
0x18003a9a9  jmp     short loc_18003AA1D
0x18003a9ab  mov     rcx, [rbp+38h]; this
0x18003a9af  mov     r9d, eax; char *
0x18003a9b2  lea     r8, aOnecoreuapWind_73; "onecoreuap\\windows\\moderncore\\inputv"...
0x18003a9b9  mov     edx, 4Dh ; 'M'; void *
0x18003a9be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a9c3  nop
0x18003a9c4  jmp     short loc_18003AA1D
0x18003a9c6  mov     [rbp+var_8], 0
0x18003a9ca  mov     rcx, [rsi]
0x18003a9cd  mov     rax, [rcx]
0x18003a9d0  lea     rdx, [rbp+var_20]
0x18003a9d4  mov     rax, [rax+28h]
0x18003a9d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a9dd  test    eax, eax
0x18003a9df  js      short loc_18003AA2B
0x18003a9e1  mov     rax, [rdi]
0x18003a9e4  lea     rdx, [rbp+var_20]
0x18003a9e8  mov     rcx, rdi
0x18003a9eb  mov     rax, [rax+18h]
0x18003a9ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a9f4  mov     ebx, eax
0x18003a9f6  test    eax, eax
0x18003a9f8  jns     short loc_18003AA2B
0x18003a9fa  mov     rcx, [rbp+38h]; this
0x18003a9fe  mov     r9d, eax; char *
0x18003aa01  lea     r8, aOnecoreuapWind_73; "onecoreuap\\windows\\moderncore\\inputv"...
0x18003aa08  mov     edx, 63h ; 'c'; void *
0x18003aa0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003aa12  nop
0x18003aa13  lea     rcx, [rbp+var_20]
0x18003aa17  call    ?_Destroy@?$_Variant_base@Umonostate@std@@UInputConfigContextMessage@@UDisplayOcclusionContextMessage@@UVirtualTouchpadContextMessage@@UMIT_WIN32K_INPUTDESKTOP_STATE_MESSAGE@@@std@@QEAAXXZ; std::_Variant_base<std::monostate,InputConfigContextMessage,DisplayOcclusionContextMessage,VirtualTouchpadContextMessage,MIT_WIN32K_INPUTDESKTOP_STATE_MESSAGE>::_Destroy(void)
0x18003aa1c  nop
0x18003aa1d  lea     rcx, [rbp+hMem]; this
0x18003aa21  call    ??1InputSecurityDescriptor@@QEAA@XZ; InputSecurityDescriptor::~InputSecurityDescriptor(void)
0x18003aa26  jmp     loc_18003A910
0x18003aa2b  mov     dword ptr [r14+1C8h], 3
0x18003aa36  lea     rcx, [rbp+var_20]
0x18003aa3a  call    ?_Destroy@?$_Variant_base@Umonostate@std@@UInputConfigContextMessage@@UDisplayOcclusionContextMessage@@UVirtualTouchpadContextMessage@@UMIT_WIN32K_INPUTDESKTOP_STATE_MESSAGE@@@std@@QEAAXXZ; std::_Variant_base<std::monostate,InputConfigContextMessage,DisplayOcclusionContextMessage,VirtualTouchpadContextMessage,MIT_WIN32K_INPUTDESKTOP_STATE_MESSAGE>::_Destroy(void)
0x18003aa3f  nop
0x18003aa40  lea     rcx, [rbp+hMem]; this
0x18003aa44  call    ??1InputSecurityDescriptor@@QEAA@XZ; InputSecurityDescriptor::~InputSecurityDescriptor(void)
0x18003aa49  nop
0x18003aa4a  mov     rcx, r13; _Mtx_t
0x18003aa4d  call    cs:__imp__Mtx_unlock
0x18003aa53  xor     eax, eax
0x18003aa55  jmp     loc_18003A91B
```
