# Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(void)

- ea: `0x18001d170`
- end: `0x18001d2f4`
- name: `??0CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `388`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001d8a0`

## callees

- `0x18000938c`
- `0x18001934c`
- `0x18001d170`
- `0x18001eb84`
- `0x18001ebb8`

## string_xrefs

- `0x18001d1df`: `tdh.dll`
- `0x18001d1d4`: `api-ms-win-eventing-tdh-l1-1-0.dll`
- `0x18001d25f`: `ext-ms-win-eventing-tdh-ext-l1-1-0.dll`
- `0x18001d2b9`: `TdhLoadManifestFromBinary`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 200);
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
0x18001d170  mov     [rsp+arg_10], rbx
0x18001d175  mov     [rsp+arg_0], rcx
0x18001d17a  push    rbp
0x18001d17b  push    rsi
0x18001d17c  push    rdi
0x18001d17d  sub     rsp, 20h
0x18001d181  mov     rbx, rcx
0x18001d184  xor     ebp, ebp
0x18001d186  mov     [rcx+18h], ebp
0x18001d189  mov     [rcx+8], rbp
0x18001d18d  mov     [rcx+10h], rbp
0x18001d191  lea     rax, ??_7CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@6B@; const Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::`vftable'
0x18001d198  mov     [rcx], rax
0x18001d19b  mov     [rcx+20h], bpl
0x18001d19f  add     rcx, 28h ; '('
0x18001d1a3  mov     [rcx], rbp
0x18001d1a6  mov     [rcx+8], rbp
0x18001d1aa  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@U_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@UlessGuid@4@V?$allocator@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<_GUID,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18001d1af  nop
0x18001d1b0  mov     [rbx+38h], rbp
0x18001d1b4  mov     [rbx+40h], ebp
0x18001d1b7  mov     [rbx+48h], rbp
0x18001d1bb  mov     [rbx+50h], ebp
0x18001d1be  mov     [rbx+58h], rbp
0x18001d1c2  mov     [rbx+60h], ebp
0x18001d1c5  mov     [rbx+68h], rbp
0x18001d1c9  mov     [rbx+70h], rbp
0x18001d1cd  lea     rax, [rbx+78h]
0x18001d1d1  mov     [rax], rbp
0x18001d1d4  lea     rdi, aApiMsWinEventi_3; "api-ms-win-eventing-tdh-l1-1-0.dll"
0x18001d1db  mov     [rax+8], rdi
0x18001d1df  lea     rsi, aTdhDll; "tdh.dll"
0x18001d1e6  mov     [rax+10h], rsi
0x18001d1ea  mov     [rax+18h], bpl
0x18001d1ee  mov     [rbx+98h], rax
0x18001d1f5  lea     rax, aTdhqueryprovid; "TdhQueryProviderFieldInformation"
0x18001d1fc  mov     [rbx+0A0h], rax
0x18001d203  mov     [rbx+0A8h], rbp
0x18001d20a  mov     [rbx+0B0h], bpl
0x18001d211  mov     [rbx+0B8h], rbp
0x18001d218  mov     [rbx+0C0h], rbp
0x18001d21f  lea     rcx, [rbx+0C8h]
0x18001d226  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001d22b  nop
0x18001d22c  lea     rcx, [rbx+0D0h]
0x18001d233  mov     [rcx], rbp
0x18001d236  mov     [rcx+8], rbp
0x18001d23a  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@U_GUID@@UCProviderState@CEventSourceHandler@Performance@Windows@Microsoft@@UlessGuid@4@V?$allocator@U?$pair@$$CBU_GUID@@UCProviderState@CEventSourceHandler@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<_GUID,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18001d23f  lea     rdx, [rbx+0E0h]
0x18001d246  mov     [rdx], rbp
0x18001d249  mov     [rdx+8], rdi
0x18001d24d  mov     [rdx+10h], rsi
0x18001d251  mov     [rdx+18h], bpl
0x18001d255  lea     rax, [rbx+100h]
0x18001d25c  mov     [rax], rbp
0x18001d25f  lea     rcx, aExtMsWinEventi; "ext-ms-win-eventing-tdh-ext-l1-1-0.dll"
0x18001d266  mov     [rax+8], rcx
0x18001d26a  mov     [rax+10h], rsi
0x18001d26e  mov     [rax+18h], bpl
0x18001d272  lea     rcx, [rbx+120h]
0x18001d279  mov     [rcx], rdx
0x18001d27c  lea     r8, aTdhgeteventinf; "TdhGetEventInformation"
0x18001d283  mov     [rcx+8], r8
0x18001d287  mov     [rcx+10h], rbp
0x18001d28b  mov     [rcx+18h], bpl
0x18001d28f  mov     [rbx+140h], rdx
0x18001d296  lea     rdx, aTdhgeteventmap; "TdhGetEventMapInformation"
0x18001d29d  mov     [rbx+148h], rdx
0x18001d2a4  mov     [rbx+150h], rbp
0x18001d2ab  mov     [rbx+158h], bpl
0x18001d2b2  mov     [rbx+160h], rax
0x18001d2b9  lea     rax, aTdhloadmanifes_0; "TdhLoadManifestFromBinary"
0x18001d2c0  mov     [rbx+168h], rax
0x18001d2c7  mov     [rbx+170h], rbp
0x18001d2ce  mov     [rbx+178h], bpl
0x18001d2d5  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001d2da  test    rax, rax
0x18001d2dd  jnz     short loc_18001D2E3
0x18001d2df  mov     byte ptr [rbx+20h], 1
0x18001d2e3  mov     rax, rbx
0x18001d2e6  mov     rbx, [rsp+38h+arg_10]
0x18001d2eb  add     rsp, 20h
0x18001d2ef  pop     rdi
0x18001d2f0  pop     rsi
0x18001d2f1  pop     rbp
0x18001d2f2  retn
```
