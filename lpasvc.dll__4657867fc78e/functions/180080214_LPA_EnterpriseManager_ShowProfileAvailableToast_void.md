# LPA::EnterpriseManager::ShowProfileAvailableToast(void)

- ea: `0x180080214`
- end: `0x18008047e`
- name: `?ShowProfileAvailableToast@EnterpriseManager@LPA@@AEAAXXZ`
- size: `618`
- prototype: `void __fastcall(LPA::EnterpriseManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007d420`

## callees

- `0x1800017c8`
- `0x18000df90`
- `0x18000ebf4`
- `0x18005aa2c`
- `0x18006ba8c`
- `0x180080214`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180080299`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800802cb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800802fd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18008032c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180080299`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800802cb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800802fd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18008032c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180080394`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180080394`

## string_xrefs

- `0x180080428`: `LpaServiceEnterpriseManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LPA::EnterpriseManager::ShowProfileAvailableToast(LPA::EnterpriseManager *this)
{
  CommonUtil *v1; // rcx
  int v2; // ecx
  HRESULT LastErrorToHResultAndForceFailure; // ebx
  int v4; // r8d
  int v5; // r9d
  CommonUtil *v6; // rcx
  CommonUtil *v7; // rcx
  CommonUtil *v8; // rcx
  LPVOID ppv; // [rsp+60h] [rbp-A0h] BYREF
  const char *v10; // [rsp+68h] [rbp-98h] BYREF
  IID rclsid; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v12[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR v13[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR v14[264]; // [rsp+4A0h] [rbp+3A0h] BYREF
  WCHAR Buffer[264]; // [rsp+6B0h] [rbp+5B0h] BYREF

  memset_0(Buffer, 0, 0x208u);
  memset_0(v14, 0, 0x208u);
  memset_0(v13, 0, 0x208u);
  memset_0(v12, 0, 0x208u);
  if ( !LoadStringW(g_hInstanceDll, 0x7D1u, Buffer, 260) )
  {
    LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v1);
    if ( LastErrorToHResultAndForceFailure < 0 )
      goto LABEL_12;
  }
  if ( !LoadStringW(g_hInstanceDll, 0x7D2u, v14, 260) )
  {
    LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v6);
    if ( LastErrorToHResultAndForceFailure < 0 )
      goto LABEL_12;
  }
  if ( !LoadStringW(g_hInstanceDll, 0x7D3u, v13, 260) )
  {
    LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v7);
    if ( LastErrorToHResultAndForceFailure < 0 )
      goto LABEL_12;
  }
  if ( !LoadStringW(g_hInstanceDll, 0x7D4u, v12, 260) )
  {
    LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v8);
    if ( LastErrorToHResultAndForceFailure < 0 )
      goto LABEL_12;
  }
  ppv = 0;
  rclsid.Data1 = -1810082878;
  *(_DWORD *)&rclsid.Data2 = 1282724567;
  *(_DWORD *)rclsid.Data4 = -131536252;
  *(_DWORD *)&rclsid.Data4[4] = 1267549174;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  LastErrorToHResultAndForceFailure = CoCreateInstance(&rclsid, 0, 4u, &GUID_045f4fa7_0503_458f_9b08_eb3c5d3b0336, &ppv);
  if ( LastErrorToHResultAndForceFailure >= 0 )
    LastErrorToHResultAndForceFailure = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, WCHAR *, WCHAR *, WCHAR *, WCHAR *, const wchar_t *, const unsigned __int16 *, int))(*(_QWORD *)ppv + 24LL))(
                                          ppv,
                                          1,
                                          1,
                                          Buffer,
                                          v14,
                                          v13,
                                          v12,
                                          L"ms-settings:network-cellular",
                                          &qword_1801130E8,
                                          1);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  if ( LastErrorToHResultAndForceFailure < 0 )
  {
LABEL_12:
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(ppv) = LastErrorToHResultAndForceFailure;
      v10 = "LPA::EnterpriseManager::ShowProfileAvailableToast";
      *(_QWORD *)&rclsid.Data1 = "LpaServiceEnterpriseManager";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v2,
        (unsigned int)&word_18012B116,
        v4,
        v5,
        (__int64)&rclsid,
        (__int64)&v10,
        (__int64)&ppv);
    }
  }
}

```

## disassembly

```asm
0x180080214  mov     [rsp-8+arg_0], rbx
0x180080219  push    rbp
0x18008021a  lea     rbp, [rsp-7D0h]
0x180080222  sub     rsp, 8D0h
0x180080229  mov     rax, cs:__security_cookie
0x180080230  xor     rax, rsp
0x180080233  mov     [rbp+7D0h+var_10], rax
0x18008023a  mov     ebx, 208h
0x18008023f  mov     r8d, ebx; Size
0x180080242  xor     edx, edx; Val
0x180080244  lea     rcx, [rbp+7D0h+Buffer]; void *
0x18008024b  call    memset_0
0x180080250  mov     r8d, ebx; Size
0x180080253  xor     edx, edx; Val
0x180080255  lea     rcx, [rbp+7D0h+var_430]; void *
0x18008025c  call    memset_0
0x180080261  mov     r8d, ebx; Size
0x180080264  xor     edx, edx; Val
0x180080266  lea     rcx, [rbp+7D0h+var_640]; void *
0x18008026d  call    memset_0
0x180080272  mov     r8d, ebx; Size
0x180080275  xor     edx, edx; Val
0x180080277  lea     rcx, [rbp+7D0h+var_850]; void *
0x18008027b  call    memset_0
0x180080280  mov     r9d, 104h; cchBufferMax
0x180080286  lea     r8, [rbp+7D0h+Buffer]; lpBuffer
0x18008028d  mov     edx, 7D1h; uID
0x180080292  mov     rcx, cs:?g_hInstanceDll@@3PEAUHINSTANCE__@@EA; hInstance
0x180080299  call    cs:__imp_LoadStringW
0x18008029f  test    eax, eax
0x1800802a1  jnz     short loc_1800802B2
0x1800802a3  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800802a8  mov     ebx, eax
0x1800802aa  test    eax, eax
0x1800802ac  js      loc_18008040D
0x1800802b2  mov     r9d, 104h; cchBufferMax
0x1800802b8  lea     r8, [rbp+7D0h+var_430]; lpBuffer
0x1800802bf  mov     edx, 7D2h; uID
0x1800802c4  mov     rcx, cs:?g_hInstanceDll@@3PEAUHINSTANCE__@@EA; hInstance
0x1800802cb  call    cs:__imp_LoadStringW
0x1800802d1  test    eax, eax
0x1800802d3  jnz     short loc_1800802E4
0x1800802d5  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800802da  mov     ebx, eax
0x1800802dc  test    eax, eax
0x1800802de  js      loc_18008040D
0x1800802e4  mov     r9d, 104h; cchBufferMax
0x1800802ea  lea     r8, [rbp+7D0h+var_640]; lpBuffer
0x1800802f1  mov     edx, 7D3h; uID
0x1800802f6  mov     rcx, cs:?g_hInstanceDll@@3PEAUHINSTANCE__@@EA; hInstance
0x1800802fd  call    cs:__imp_LoadStringW
0x180080303  test    eax, eax
0x180080305  jnz     short loc_180080316
0x180080307  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x18008030c  mov     ebx, eax
0x18008030e  test    eax, eax
0x180080310  js      loc_18008040D
0x180080316  mov     r9d, 104h; cchBufferMax
0x18008031c  lea     r8, [rbp+7D0h+var_850]; lpBuffer
0x180080320  mov     edx, 7D4h; uID
0x180080325  mov     rcx, cs:?g_hInstanceDll@@3PEAUHINSTANCE__@@EA; hInstance
0x18008032c  call    cs:__imp_LoadStringW
0x180080332  test    eax, eax
0x180080334  jnz     short loc_180080345
0x180080336  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x18008033b  mov     ebx, eax
0x18008033d  test    eax, eax
0x18008033f  js      loc_18008040D
0x180080345  mov     [rsp+8D0h+var_870], 0
0x18008034e  mov     [rsp+8D0h+rclsid.Data1], 941C53C2h
0x180080356  mov     dword ptr [rsp+8D0h+rclsid.Data2], 4C74D2D7h
0x18008035e  mov     dword ptr [rsp+8D0h+rclsid.Data4], 0F828EA84h
0x180080366  mov     dword ptr [rsp+8D0h+rclsid.Data4+4], 4B8D43F6h
0x18008036e  lea     rcx, [rsp+8D0h+var_870]
0x180080373  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180080378  lea     rax, [rsp+8D0h+var_870]
0x18008037d  mov     [rsp+8D0h+ppv], rax; ppv
0x180080382  lea     r9, _GUID_045f4fa7_0503_458f_9b08_eb3c5d3b0336; riid
0x180080389  xor     edx, edx; pUnkOuter
0x18008038b  lea     r8d, [rdx+4]; dwClsContext
0x18008038f  lea     rcx, [rsp+8D0h+rclsid]; rclsid
0x180080394  call    cs:__imp_CoCreateInstance
0x18008039a  mov     ebx, eax
0x18008039c  test    eax, eax
0x18008039e  js      short loc_1800803FF
0x1800803a0  mov     rcx, [rsp+8D0h+var_870]
0x1800803a5  mov     rax, [rcx]
0x1800803a8  mov     edx, 1
0x1800803ad  mov     [rsp+8D0h+var_888], edx
0x1800803b1  lea     r8, qword_1801130E8
0x1800803b8  mov     [rsp+8D0h+var_890], r8
0x1800803bd  lea     r8, aMsSettingsNetw; "ms-settings:network-cellular"
0x1800803c4  mov     [rsp+8D0h+var_898], r8
0x1800803c9  lea     r8, [rbp+7D0h+var_850]
0x1800803cd  mov     [rsp+8D0h+var_8A0], r8
0x1800803d2  lea     r8, [rbp+7D0h+var_640]
0x1800803d9  mov     [rsp+8D0h+var_8A8], r8
0x1800803de  lea     r8, [rbp+7D0h+var_430]
0x1800803e5  mov     [rsp+8D0h+ppv], r8
0x1800803ea  lea     r9, [rbp+7D0h+Buffer]
0x1800803f1  mov     r8d, edx
0x1800803f4  mov     rax, [rax+18h]
0x1800803f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800803fd  mov     ebx, eax
0x1800803ff  lea     rcx, [rsp+8D0h+var_870]
0x180080404  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180080409  test    ebx, ebx
0x18008040b  jns     short loc_18008045E
0x18008040d  mov     eax, cs:CallbackContext
0x180080413  cmp     eax, 2
0x180080416  jbe     short loc_18008045E
0x180080418  mov     dword ptr [rsp+8D0h+var_870], ebx
0x18008041c  lea     rax, aLpaEnterprisem_6; "LPA::EnterpriseManager::ShowProfileAvai"...
0x180080423  mov     [rsp+8D0h+var_868], rax
0x180080428  lea     rax, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18008042f  mov     qword ptr [rsp+8D0h+rclsid.Data1], rax
0x180080434  lea     rax, [rsp+8D0h+var_870]
0x180080439  mov     [rsp+8D0h+var_8A0], rax
0x18008043e  lea     rax, [rsp+8D0h+var_868]
0x180080443  mov     [rsp+8D0h+var_8A8], rax
0x180080448  lea     rax, [rsp+8D0h+rclsid]
0x18008044d  mov     [rsp+8D0h+ppv], rax
0x180080452  lea     rdx, word_18012B116
0x180080459  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008045e  mov     rcx, [rbp+7D0h+var_10]
0x180080465  xor     rcx, rsp; StackCookie
0x180080468  call    __security_check_cookie
0x18008046d  mov     rbx, [rsp+8D0h+arg_0]
0x180080475  add     rsp, 8D0h
0x18008047c  pop     rbp
0x18008047d  retn
```
