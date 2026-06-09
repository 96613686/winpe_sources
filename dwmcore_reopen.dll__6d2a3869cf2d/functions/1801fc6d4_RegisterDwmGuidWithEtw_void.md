# RegisterDwmGuidWithEtw(void)

- ea: `0x1801fc6d4`
- end: `0x1801fc897`
- name: `?RegisterDwmGuidWithEtw@@YAXXZ`
- size: `451`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801c8a80`

## callees

- `0x180004c3c`
- `0x180159498`
- `0x18017c2dc`
- `0x1801f2b50`
- `0x1801fc6d4`
- `0x18021e2b8`
- `0x1802284b0`
- `0x18022945c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801fc76b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801fc76b`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1801fc786`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1801fc786`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801fc779`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801fc779`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801fc81d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801fc81d`

## pseudocode

```c
void __fastcall RegisterDwmGuidWithEtw(__int64 a1, __int64 a2)
{
  __int64 v2; // rdx
  DWORD CurrentProcessId; // eax
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  DWORD pdwType; // [rsp+20h] [rbp-E0h]
  DWORD pSessionId; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  _BYTE *v10; // [rsp+48h] [rbp-B8h] BYREF
  GUID *v11; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Value[40]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pvData[80]; // [rsp+B0h] [rbp-50h] BYREF

  McGenEventRegister_EventRegister(
    &Microsoft_Windows_Dwm_Core_Provider,
    a2,
    &Microsoft_Windows_Dwm_Core_Provider_Context,
    &Microsoft_Windows_Dwm_Core_Provider_Context);
  McGenEventRegister_EventRegister(
    &Microsoft_Windows_Dwm_Compositor,
    v2,
    &Microsoft_Windows_Dwm_Compositor_Context,
    &Microsoft_Windows_Dwm_Compositor_Context);
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1803B9858);
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&unk_1803B98C8);
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1803B97E8);
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1803B9820);
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1803B9890);
  EventActivityIdControl(3u, &gDwmCoreTelemetryActivityId);
  pSessionId = 0;
  CurrentProcessId = GetCurrentProcessId();
  if ( ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
  {
    memset_0(Value, 0, 0x44u);
    pdwType = pSessionId;
    if ( (int)StringCchPrintfW(Value, 0x22u, L"%s_%08X", L"DwmInitSessionActivityId", pdwType) >= 0 )
    {
      memset_0(pvData, 0, 0x4Au);
      pcbData = 74;
      if ( !RegGetValueW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\Dwm", Value, 2u, 0, pvData, &pcbData)
        && (unsigned int)dword_1803B97E8 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_1803B97E8, 0x400000000000LL) )
        {
          v11 = &gDwmCoreTelemetryActivityId;
          v10 = pvData;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>>(
            v4,
            (unsigned int)&unk_1803965B0,
            v5,
            v6,
            (__int64)&v11,
            (__int64)&v10);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1801fc6d4  mov     [rsp-8+arg_0], rdi
0x1801fc6d9  push    rbp
0x1801fc6da  lea     rbp, [rsp-10h]
0x1801fc6df  sub     rsp, 110h
0x1801fc6e6  mov     rax, cs:__security_cookie
0x1801fc6ed  xor     rax, rsp
0x1801fc6f0  mov     [rbp+10h+var_10], rax
0x1801fc6f4  lea     r8, Microsoft_Windows_Dwm_Core_Provider_Context
0x1801fc6fb  mov     r9, r8
0x1801fc6fe  lea     rcx, Microsoft_Windows_Dwm_Core_Provider
0x1801fc705  call    McGenEventRegister_EventRegister
0x1801fc70a  lea     r8, Microsoft_Windows_Dwm_Compositor_Context
0x1801fc711  mov     r9, r8
0x1801fc714  lea     rcx, Microsoft_Windows_Dwm_Compositor
0x1801fc71b  call    McGenEventRegister_EventRegister
0x1801fc720  lea     rcx, dword_1803B9858; CallbackContext
0x1801fc727  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1801fc72c  lea     rcx, unk_1803B98C8; CallbackContext
0x1801fc733  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1801fc738  lea     rcx, dword_1803B97E8; CallbackContext
0x1801fc73f  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1801fc744  lea     rcx, dword_1803B9820; CallbackContext
0x1801fc74b  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1801fc750  lea     rcx, dword_1803B9890; CallbackContext
0x1801fc757  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1801fc75c  lea     rdi, gDwmCoreTelemetryActivityId
0x1801fc763  mov     ecx, 3; ControlCode
0x1801fc768  mov     rdx, rdi; ActivityId
0x1801fc76b  call    cs:__imp_EventActivityIdControl
0x1801fc771  mov     [rsp+110h+pSessionId], 0
0x1801fc779  call    cs:__imp_GetCurrentProcessId
0x1801fc77f  mov     ecx, eax; dwProcessId
0x1801fc781  lea     rdx, [rsp+110h+pSessionId]; pSessionId
0x1801fc786  call    cs:__imp_ProcessIdToSessionId
0x1801fc78c  test    eax, eax
0x1801fc78e  jz      loc_1801FC87A
0x1801fc794  xor     edx, edx; Val
0x1801fc796  lea     rcx, [rsp+110h+Value]; void *
0x1801fc79b  lea     r8d, [rdx+44h]; Size
0x1801fc79f  call    memset_0
0x1801fc7a4  mov     eax, [rsp+110h+pSessionId]
0x1801fc7a8  lea     r9, aDwminitsession; "DwmInitSessionActivityId"
0x1801fc7af  lea     r8, aS08x; "%s_%08X"
0x1801fc7b6  mov     dword ptr [rsp+110h+pdwType], eax
0x1801fc7ba  mov     edx, 22h ; '"'; unsigned __int64
0x1801fc7bf  lea     rcx, [rsp+110h+Value]; unsigned __int16 *
0x1801fc7c4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801fc7c9  test    eax, eax
0x1801fc7cb  js      loc_1801FC87A
0x1801fc7d1  xor     edx, edx; Val
0x1801fc7d3  lea     rcx, [rbp+10h+var_60]; void *
0x1801fc7d7  lea     r8d, [rdx+4Ah]; Size
0x1801fc7db  call    memset_0
0x1801fc7e0  lea     rax, [rsp+110h+var_CC]
0x1801fc7e5  mov     [rsp+110h+var_CC], 4Ah ; 'J'
0x1801fc7ed  mov     [rsp+110h+pcbData], rax; pcbData
0x1801fc7f2  lea     r8, [rsp+110h+Value]; lpValue
0x1801fc7f7  lea     rax, [rbp+10h+var_60]
0x1801fc7fb  mov     r9d, 2; dwFlags
0x1801fc801  mov     [rsp+110h+pvData], rax; pvData
0x1801fc806  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\Dwm"
0x1801fc80d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1801fc814  mov     [rsp+110h+pdwType], 0; pdwType
0x1801fc81d  call    cs:__imp_RegGetValueW
0x1801fc823  test    eax, eax
0x1801fc825  jnz     short loc_1801FC87A
0x1801fc827  mov     eax, cs:dword_1803B97E8
0x1801fc82d  cmp     eax, 5
0x1801fc830  jbe     short loc_1801FC87A
0x1801fc832  mov     rdx, 400000000000h
0x1801fc83c  lea     rcx, dword_1803B97E8
0x1801fc843  call    _tlgKeywordOn
0x1801fc848  test    al, al
0x1801fc84a  jz      short loc_1801FC87A
0x1801fc84c  lea     rax, [rbp+10h+var_60]
0x1801fc850  mov     [rsp+110h+var_C0], rdi
0x1801fc855  mov     [rsp+110h+var_C8], rax
0x1801fc85a  lea     rdx, unk_1803965B0
0x1801fc861  lea     rax, [rsp+110h+var_C8]
0x1801fc866  mov     [rsp+110h+pvData], rax
0x1801fc86b  lea     rax, [rsp+110h+var_C0]
0x1801fc870  mov     [rsp+110h+pdwType], rax
0x1801fc875  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &)
0x1801fc87a  mov     rcx, [rbp+10h+var_10]
0x1801fc87e  xor     rcx, rsp; StackCookie
0x1801fc881  call    __security_check_cookie
0x1801fc886  mov     rdi, [rsp+110h+arg_0]
0x1801fc88e  add     rsp, 110h
0x1801fc895  pop     rbp
0x1801fc896  retn
```
