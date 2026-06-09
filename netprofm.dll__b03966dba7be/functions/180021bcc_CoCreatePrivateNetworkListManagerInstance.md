# CoCreatePrivateNetworkListManagerInstance

- ea: `0x180021bcc`
- end: `0x180021ca0`
- name: `CoCreatePrivateNetworkListManagerInstance`
- size: `212`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180022b2c`
- `0x180026c04`
- `0x180029678`

## callees

- `0x180001084`
- `0x1800011a0`
- `0x180007540`
- `0x1800086e0`
- `0x1800120d0`
- `0x180021bcc`
- `0x18002aed0`
- `0x180033a1c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021c2e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021c2e`

## pseudocode

```c
__int64 __fastcall CoCreatePrivateNetworkListManagerInstance(LPVOID *ppv)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  unsigned int Instance; // ebx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v9; // [rsp+30h] [rbp-38h] BYREF
  __int128 Parameter; // [rsp+38h] [rbp-30h] BYREF
  __int64 v11; // [rsp+48h] [rbp-20h]

  if ( (unsigned int)IsSystemSetupInProgress() )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v3, v2);
    return (unsigned int)-2147023834;
  }
  else
  {
    Parameter = 0;
    v11 = 0;
    CRPCTimeout::CRPCTimeout(&Parameter);
    Instance = CoCreateInstance(&CLSID_CNetworkListManager, 0, 4u, &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b, ppv);
    if ( BYTE4(Parameter)
      && (unsigned int)dword_18005F140 > 5
      && (unsigned __int8)tlgKeywordOn(&dword_18005F140, 0x400000000000LL) )
    {
      v9 = 2048;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        v5,
        (int)&dword_18005611C,
        v6,
        v7,
        (__int64)&v9);
    }
    CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)&Parameter);
  }
  return Instance;
}

```

## disassembly

```asm
0x180021bcc  push    rbx
0x180021bce  sub     rsp, 60h
0x180021bd2  mov     rax, cs:__security_cookie
0x180021bd9  xor     rax, rsp
0x180021bdc  mov     [rsp+68h+var_18], rax
0x180021be1  mov     rbx, rcx
0x180021be4  call    IsSystemSetupInProgress
0x180021be9  test    eax, eax
0x180021beb  jz      short loc_180021BFC
0x180021bed  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180021bf2  mov     ebx, 80070426h
0x180021bf7  jmp     loc_180021C8B
0x180021bfc  xorps   xmm0, xmm0
0x180021bff  lea     rcx, [rsp+68h+Parameter]; Parameter
0x180021c04  xor     eax, eax
0x180021c06  movups  [rsp+68h+Parameter], xmm0
0x180021c0b  mov     [rsp+68h+var_20], rax
0x180021c10  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x180021c15  xor     edx, edx; pUnkOuter
0x180021c17  mov     [rsp+68h+ppv], rbx; ppv
0x180021c1c  lea     r9, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b; riid
0x180021c23  lea     rcx, CLSID_CNetworkListManager; rclsid
0x180021c2a  lea     r8d, [rdx+4]; dwClsContext
0x180021c2e  call    cs:__imp_CoCreateInstance
0x180021c34  cmp     byte ptr [rsp+68h+Parameter+4], 0
0x180021c39  mov     ebx, eax
0x180021c3b  jz      short loc_180021C81
0x180021c3d  mov     ecx, cs:dword_18005F140
0x180021c43  cmp     ecx, 5
0x180021c46  jbe     short loc_180021C81
0x180021c48  mov     rdx, 400000000000h
0x180021c52  lea     rcx, dword_18005F140
0x180021c59  call    _tlgKeywordOn
0x180021c5e  test    al, al
0x180021c60  jz      short loc_180021C81
0x180021c62  lea     rax, [rsp+68h+var_38]
0x180021c67  mov     [rsp+68h+var_38], 800h
0x180021c70  lea     rdx, dword_18005611C
0x180021c77  mov     [rsp+68h+ppv], rax
0x180021c7c  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x180021c81  lea     rcx, [rsp+68h+Parameter]; this
0x180021c86  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x180021c8b  mov     eax, ebx
0x180021c8d  mov     rcx, [rsp+68h+var_18]
0x180021c92  xor     rcx, rsp; StackCookie
0x180021c95  call    __security_check_cookie
0x180021c9a  add     rsp, 60h
0x180021c9e  pop     rbx
0x180021c9f  retn
```
