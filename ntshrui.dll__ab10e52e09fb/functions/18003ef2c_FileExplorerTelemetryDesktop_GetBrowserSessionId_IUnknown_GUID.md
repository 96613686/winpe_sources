# FileExplorerTelemetryDesktop::GetBrowserSessionId(IUnknown *,_GUID *)

- ea: `0x18003ef2c`
- end: `0x18003f011`
- name: `?GetBrowserSessionId@FileExplorerTelemetryDesktop@@SAJPEAUIUnknown@@PEAU_GUID@@@Z`
- size: `229`
- prototype: `__int64 __fastcall(IUnknown *punk, GUID *value)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003cdc4`

## callees

- `0x180008900`
- `0x18003ef2c`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18003ef6e`
- `SHCORE!IUnknown_QueryService` at `0x18003efa5`
- `SHCORE!IUnknown_QueryService` at `0x18003efce`
- `SHCORE!IUnknown_QueryService` at `0x18003ef6e`
- `SHCORE!IUnknown_QueryService` at `0x18003efa5`
- `SHCORE!IUnknown_QueryService` at `0x18003efce`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x18003eff1`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x18003eff1`

## pseudocode

```c
__int64 __fastcall FileExplorerTelemetryDesktop::GetBrowserSessionId(IUnknown *punk, GUID *value)
{
  HRESULT GUID; // ebx
  void *ppvOut; // [rsp+48h] [rbp+28h] BYREF
  IUnknown *punka; // [rsp+50h] [rbp+30h] BYREF

  ppvOut = 0;
  *value = 0;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppvOut);
  GUID = IUnknown_QueryService(
           punk,
           &GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1,
           &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
           &ppvOut);
  if ( GUID >= 0 )
    goto LABEL_6;
  if ( punk )
  {
    punka = 0;
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&punka);
    if ( IUnknown_QueryService(punk, &IID_IShellBrowser, &GUID_00000000_0000_0000_c000_000000000046, (void **)&punka) >= 0 )
    {
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppvOut);
      GUID = IUnknown_QueryService(
               punka,
               &GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1,
               &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
               &ppvOut);
    }
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&punka);
    if ( GUID >= 0 )
LABEL_6:
      GUID = PSPropertyBag_ReadGUID((IPropertyBag *)ppvOut, L"BrowserSessionId", value);
  }
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppvOut);
  return (unsigned int)GUID;
}

```

## disassembly

```asm
0x18003ef2c  mov     [rsp-18h+arg_0], rbx
0x18003ef31  push    rbp
0x18003ef32  push    rsi
0x18003ef33  push    rdi
0x18003ef34  mov     rbp, rsp
0x18003ef37  sub     rsp, 20h
0x18003ef3b  mov     rdi, rcx
0x18003ef3e  mov     [rbp+ppvOut], 0
0x18003ef46  xorps   xmm0, xmm0
0x18003ef49  lea     rcx, [rbp+ppvOut]
0x18003ef4d  movdqu  xmmword ptr [rdx], xmm0
0x18003ef51  mov     rsi, rdx
0x18003ef54  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18003ef59  lea     r9, [rbp+ppvOut]; ppvOut
0x18003ef5d  mov     rcx, rdi; punk
0x18003ef60  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18003ef67  lea     rdx, _GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1; guidService
0x18003ef6e  call    cs:__imp_IUnknown_QueryService
0x18003ef74  mov     ebx, eax
0x18003ef76  test    eax, eax
0x18003ef78  jns     short loc_18003EFE3
0x18003ef7a  test    rdi, rdi
0x18003ef7d  jz      short loc_18003EFF9
0x18003ef7f  lea     rcx, [rbp+punk]
0x18003ef83  mov     [rbp+punk], 0
0x18003ef8b  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18003ef90  lea     r9, [rbp+punk]; ppvOut
0x18003ef94  mov     rcx, rdi; punk
0x18003ef97  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18003ef9e  lea     rdx, IID_IShellBrowser; guidService
0x18003efa5  call    cs:__imp_IUnknown_QueryService
0x18003efab  test    eax, eax
0x18003efad  js      short loc_18003EFD6
0x18003efaf  lea     rcx, [rbp+ppvOut]
0x18003efb3  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18003efb8  mov     rcx, [rbp+punk]; punk
0x18003efbc  lea     r9, [rbp+ppvOut]; ppvOut
0x18003efc0  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18003efc7  lea     rdx, _GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1; guidService
0x18003efce  call    cs:__imp_IUnknown_QueryService
0x18003efd4  mov     ebx, eax
0x18003efd6  lea     rcx, [rbp+punk]
0x18003efda  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18003efdf  test    ebx, ebx
0x18003efe1  js      short loc_18003EFF9
0x18003efe3  mov     rcx, [rbp+ppvOut]; propBag
0x18003efe7  lea     rdx, propName; "BrowserSessionId"
0x18003efee  mov     r8, rsi; value
0x18003eff1  call    cs:__imp_PSPropertyBag_ReadGUID
0x18003eff7  mov     ebx, eax
0x18003eff9  lea     rcx, [rbp+ppvOut]
0x18003effd  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18003f002  mov     eax, ebx
0x18003f004  mov     rbx, [rsp+20h+arg_0]
0x18003f009  add     rsp, 20h
0x18003f00d  pop     rdi
0x18003f00e  pop     rsi
0x18003f00f  pop     rbp
0x18003f010  retn
```
