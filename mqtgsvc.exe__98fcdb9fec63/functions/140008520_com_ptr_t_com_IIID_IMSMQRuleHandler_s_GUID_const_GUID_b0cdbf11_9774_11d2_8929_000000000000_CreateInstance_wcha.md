# _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::CreateInstance(wchar_t const *,IUnknown *,ulong)

- ea: `0x140008520`
- end: `0x140008586`
- name: `?CreateInstance@?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEAAJPEB_WPEAUIUnknown@@K@Z`
- size: `102`
- prototype: `HRESULT __fastcall(LPVOID *ppv)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140008f50`
- `0x14000d110`

## callees

- `0x140008464`
- `0x140008520`
- `0x14001cf00`

## import_xrefs

- `ole32!CLSIDFromProgID` at `0x140008553`
- `ole32!CLSIDFromProgID` at `0x140008553`

## pseudocode

```c
HRESULT __fastcall _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::CreateInstance(
        LPVOID *ppv)
{
  HRESULT result; // eax
  GUID clsid; // [rsp+20h] [rbp-28h] BYREF

  clsid = 0;
  result = CLSIDFromProgID(L"MSMQTriggerObjects.MSMQRuleHandler", &clsid);
  if ( result >= 0 )
    return _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::CreateInstance(
             ppv,
             &clsid);
  return result;
}

```

## disassembly

```asm
0x140008520  mov     [rsp+arg_8], rbx
0x140008525  push    rdi
0x140008526  sub     rsp, 40h
0x14000852a  mov     rax, cs:__security_cookie
0x140008531  xor     rax, rsp
0x140008534  mov     [rsp+48h+var_18], rax
0x140008539  mov     edi, r9d
0x14000853c  mov     rbx, rcx
0x14000853f  xorps   xmm0, xmm0
0x140008542  movups  xmmword ptr [rsp+48h+clsid.Data1], xmm0
0x140008547  lea     rdx, [rsp+48h+clsid]; lpclsid
0x14000854c  lea     rcx, szProgID; "MSMQTriggerObjects.MSMQRuleHandler"
0x140008553  call    cs:__imp_CLSIDFromProgID
0x140008559  test    eax, eax
0x14000855b  js      short loc_14000856E
0x14000855d  mov     r9d, edi
0x140008560  lea     rdx, [rsp+48h+clsid]; rclsid
0x140008565  mov     rcx, rbx; ppv
0x140008568  call    ?CreateInstance@?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::CreateInstance(_GUID const &,IUnknown *,ulong)
0x14000856d  nop
0x14000856e  mov     rcx, [rsp+48h+var_18]
0x140008573  xor     rcx, rsp; StackCookie
0x140008576  call    __security_check_cookie
0x14000857b  mov     rbx, [rsp+48h+arg_8]
0x140008580  add     rsp, 40h
0x140008584  pop     rdi
0x140008585  retn
```
