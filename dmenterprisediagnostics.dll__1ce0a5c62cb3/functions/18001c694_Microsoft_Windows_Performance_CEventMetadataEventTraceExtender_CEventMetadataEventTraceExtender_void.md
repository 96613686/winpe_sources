# Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(void)

- ea: `0x18001c694`
- end: `0x18001c817`
- name: `??0CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `387`
- prototype: `Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001cd8c`

## callees

- `0x180008f10`
- `0x180018998`
- `0x18001c694`
- `0x18001e034`
- `0x18001e068`

## string_xrefs

- `0x18001c703`: `tdh.dll`
- `0x18001c6f8`: `api-ms-win-eventing-tdh-l1-1-0.dll`
- `0x18001c783`: `ext-ms-win-eventing-tdh-ext-l1-1-0.dll`
- `0x18001c7dd`: `TdhLoadManifestFromBinary`

## pseudocode

```c
Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__fastcall Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(
        Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this)
{
  _QWORD *v2; // rcx

  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::`vftable';
  *((_BYTE *)this + 32) = 0;
  v2 = (_QWORD *)((char *)this + 40);
  *v2 = 0;
  v2[1] = 0;
  std::_Tree<std::_Tmap_traits<_GUID,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>,0>>::_Alloc_sentinel_and_proxy();
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = L"api-ms-win-eventing-tdh-l1-1-0.dll";
  *((_QWORD *)this + 17) = L"tdh.dll";
  *((_BYTE *)this + 144) = 0;
  *((_QWORD *)this + 19) = (char *)this + 120;
  *((_QWORD *)this + 20) = "TdhQueryProviderFieldInformation";
  *((_QWORD *)this + 21) = 0;
  *((_BYTE *)this + 176) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)this + 200);
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  std::_Tree<std::_Tmap_traits<_GUID,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState>>,0>>::_Alloc_sentinel_and_proxy();
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = L"api-ms-win-eventing-tdh-l1-1-0.dll";
  *((_QWORD *)this + 30) = L"tdh.dll";
  *((_BYTE *)this + 248) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = L"ext-ms-win-eventing-tdh-ext-l1-1-0.dll";
  *((_QWORD *)this + 34) = L"tdh.dll";
  *((_BYTE *)this + 280) = 0;
  *((_QWORD *)this + 36) = (char *)this + 224;
  *((_QWORD *)this + 37) = "TdhGetEventInformation";
  *((_QWORD *)this + 38) = 0;
  *((_BYTE *)this + 312) = 0;
  *((_QWORD *)this + 40) = (char *)this + 224;
  *((_QWORD *)this + 41) = "TdhGetEventMapInformation";
  *((_QWORD *)this + 42) = 0;
  *((_BYTE *)this + 344) = 0;
  *((_QWORD *)this + 44) = (char *)this + 256;
  *((_QWORD *)this + 45) = "TdhLoadManifestFromBinary";
  *((_QWORD *)this + 46) = 0;
  *((_BYTE *)this + 376) = 0;
  if ( !Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((char *)this + 288) )
    *((_BYTE *)this + 32) = 1;
  return this;
}

```

## disassembly

```asm
0x18001c694  mov     [rsp+arg_10], rbx
0x18001c699  mov     [rsp+arg_0], rcx
0x18001c69e  push    rbp
0x18001c69f  push    rsi
0x18001c6a0  push    rdi
0x18001c6a1  sub     rsp, 20h
0x18001c6a5  mov     rbx, rcx
0x18001c6a8  xor     ebp, ebp
0x18001c6aa  mov     [rcx+18h], ebp
0x18001c6ad  mov     [rcx+8], rbp
0x18001c6b1  mov     [rcx+10h], rbp
0x18001c6b5  lea     rax, ??_7CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@6B@; const Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::`vftable'
0x18001c6bc  mov     [rcx], rax
0x18001c6bf  mov     [rcx+20h], bpl
0x18001c6c3  add     rcx, 28h ; '('
0x18001c6c7  mov     [rcx], rbp
0x18001c6ca  mov     [rcx+8], rbp
0x18001c6ce  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@U_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@UlessGuid@4@V?$allocator@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<_GUID,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18001c6d3  nop
0x18001c6d4  mov     [rbx+38h], rbp
0x18001c6d8  mov     [rbx+40h], ebp
0x18001c6db  mov     [rbx+48h], rbp
0x18001c6df  mov     [rbx+50h], ebp
0x18001c6e2  mov     [rbx+58h], rbp
0x18001c6e6  mov     [rbx+60h], ebp
0x18001c6e9  mov     [rbx+68h], rbp
0x18001c6ed  mov     [rbx+70h], rbp
0x18001c6f1  lea     rax, [rbx+78h]
0x18001c6f5  mov     [rax], rbp
0x18001c6f8  lea     rdi, aApiMsWinEventi_3; "api-ms-win-eventing-tdh-l1-1-0.dll"
0x18001c6ff  mov     [rax+8], rdi
0x18001c703  lea     rsi, aTdhDll; "tdh.dll"
0x18001c70a  mov     [rax+10h], rsi
0x18001c70e  mov     [rax+18h], bpl
0x18001c712  mov     [rbx+98h], rax
0x18001c719  lea     rax, aTdhqueryprovid; "TdhQueryProviderFieldInformation"
0x18001c720  mov     [rbx+0A0h], rax
0x18001c727  mov     [rbx+0A8h], rbp
0x18001c72e  mov     [rbx+0B0h], bpl
0x18001c735  mov     [rbx+0B8h], rbp
0x18001c73c  mov     [rbx+0C0h], rbp
0x18001c743  lea     rcx, [rbx+0C8h]
0x18001c74a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001c74f  nop
0x18001c750  lea     rcx, [rbx+0D0h]
0x18001c757  mov     [rcx], rbp
0x18001c75a  mov     [rcx+8], rbp
0x18001c75e  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@U_GUID@@UCProviderState@CEventSourceHandler@Performance@Windows@Microsoft@@UlessGuid@4@V?$allocator@U?$pair@$$CBU_GUID@@UCProviderState@CEventSourceHandler@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<_GUID,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18001c763  lea     rdx, [rbx+0E0h]
0x18001c76a  mov     [rdx], rbp
0x18001c76d  mov     [rdx+8], rdi
0x18001c771  mov     [rdx+10h], rsi
0x18001c775  mov     [rdx+18h], bpl
0x18001c779  lea     rax, [rbx+100h]
0x18001c780  mov     [rax], rbp
0x18001c783  lea     rcx, aExtMsWinEventi; "ext-ms-win-eventing-tdh-ext-l1-1-0.dll"
0x18001c78a  mov     [rax+8], rcx
0x18001c78e  mov     [rax+10h], rsi
0x18001c792  mov     [rax+18h], bpl
0x18001c796  lea     rcx, [rbx+120h]
0x18001c79d  mov     [rcx], rdx
0x18001c7a0  lea     r8, aTdhgeteventinf; "TdhGetEventInformation"
0x18001c7a7  mov     [rcx+8], r8
0x18001c7ab  mov     [rcx+10h], rbp
0x18001c7af  mov     [rcx+18h], bpl
0x18001c7b3  mov     [rbx+140h], rdx
0x18001c7ba  lea     rdx, aTdhgeteventmap; "TdhGetEventMapInformation"
0x18001c7c1  mov     [rbx+148h], rdx
0x18001c7c8  mov     [rbx+150h], rbp
0x18001c7cf  mov     [rbx+158h], bpl
0x18001c7d6  mov     [rbx+160h], rax
0x18001c7dd  lea     rax, aTdhloadmanifes_0; "TdhLoadManifestFromBinary"
0x18001c7e4  mov     [rbx+168h], rax
0x18001c7eb  mov     [rbx+170h], rbp
0x18001c7f2  mov     [rbx+178h], bpl
0x18001c7f9  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001c7fe  test    rax, rax
0x18001c801  jnz     short loc_18001C807
0x18001c803  mov     byte ptr [rbx+20h], 1
0x18001c807  mov     rax, rbx
0x18001c80a  mov     rbx, [rsp+38h+arg_10]
0x18001c80f  add     rsp, 20h
0x18001c813  pop     rdi
0x18001c814  pop     rsi
0x18001c815  pop     rbp
0x18001c816  retn
```
