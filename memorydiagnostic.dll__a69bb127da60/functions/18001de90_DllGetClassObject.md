# DllGetClassObject

- ea: `0x18001de90`
- end: `0x18001e079`
- name: `DllGetClassObject`
- size: `489`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x180002e74`
- `0x18000e7ec`
- `0x18001a9e4`
- `0x18001ddb0`
- `0x18001de90`
- `0x180023010`

## string_xrefs

- `0x18001def5`: `DllGetClassObject_CreateOnlineMemoryDiagnosticTask`
- `0x18001df7d`: `DllGetClassObject_CreateOfflineMemoryDiagnosticTask`
- `0x18001e04a`: `DllGetClassObject_DefaultCreatePath`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v6; // rcx
  const struct _tlgProvider_t *v7; // rax
  int v8; // r8d
  int v9; // r9d
  const struct _tlgProvider_t *v11; // rax
  int v12; // r8d
  int v13; // r9d
  HRESULT v14; // edi
  _DWORD *v15; // rbx
  const struct _tlgProvider_t *v16; // rax
  int v17; // r8d
  int v18; // r9d
  const wchar_t *v19; // [rsp+58h] [rbp+20h] BYREF

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57054134>::GetImpl'::`2'::impl) )
    return CWinTaskModuleT<CMemoryDiagnosticHandler,&_GUID const CLSID_MemoryDiagnostic>::DllGetClassObject(
             v6,
             rclsid,
             riid,
             ppv);
  if ( *(_QWORD *)&CLSID_MemoryDiagnostic.Data1 == *(_QWORD *)&rclsid->Data1
    && *(_QWORD *)CLSID_MemoryDiagnostic.Data4 == *(_QWORD *)rclsid->Data4 )
  {
    v7 = TlgHelper::Provider();
    v6 = *(unsigned int *)v7;
    if ( (unsigned int)v6 > 4 )
    {
      v6 = *((_QWORD *)v7 + 2);
      if ( (v6 & 1) != 0 )
      {
        v6 = *((_QWORD *)v7 + 3) & 1LL;
        if ( v6 == *((_QWORD *)v7 + 3) )
        {
          v19 = L"DllGetClassObject_CreateOnlineMemoryDiagnosticTask";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (_DWORD)v7,
            (unsigned int)word_18002A69A,
            v8,
            v9,
            (__int64)&v19);
        }
      }
    }
    return CWinTaskModuleT<CMemoryDiagnosticHandler,&_GUID const CLSID_MemoryDiagnostic>::DllGetClassObject(
             v6,
             rclsid,
             riid,
             ppv);
  }
  if ( *(_QWORD *)&CLSID_AutomaticOfflineMemoryDiagnostic.Data1 == *(_QWORD *)&rclsid->Data1
    && *(_QWORD *)CLSID_AutomaticOfflineMemoryDiagnostic.Data4 == *(_QWORD *)rclsid->Data4 )
  {
    v11 = TlgHelper::Provider();
    if ( *(_DWORD *)v11 > 4u && (*((_QWORD *)v11 + 2) & 1) != 0 && (*((_QWORD *)v11 + 3) & 1LL) == *((_QWORD *)v11 + 3) )
    {
      v19 = L"DllGetClassObject_CreateOfflineMemoryDiagnosticTask";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v11,
        (unsigned int)&word_18002A676,
        v12,
        v13,
        (__int64)&v19);
    }
    if ( !ppv )
      return -2147024809;
    *ppv = 0;
    if ( *(_QWORD *)&CLSID_AutomaticOfflineMemoryDiagnostic.Data1 != *(_QWORD *)&rclsid->Data1
      || *(_QWORD *)CLSID_AutomaticOfflineMemoryDiagnostic.Data4 != *(_QWORD *)rclsid->Data4 )
    {
      return -2147221231;
    }
    v15 = operator new(0x10u);
    *(_QWORD *)v15 = &CWinTaskClassFactoryT<AOMDHandler,1>::`vftable';
    v15[2] = 1;
    _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
    v14 = (**(__int64 (__fastcall ***)(_DWORD *, const IID *const, LPVOID *))v15)(v15, riid, ppv);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v15 + 16LL))(v15);
    return v14;
  }
  else
  {
    v16 = TlgHelper::Provider();
    if ( *(_DWORD *)v16 > 4u && (*((_QWORD *)v16 + 2) & 1) != 0 && (*((_QWORD *)v16 + 3) & 1LL) == *((_QWORD *)v16 + 3) )
    {
      v19 = L"DllGetClassObject_DefaultCreatePath";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v16,
        (unsigned int)&word_18002A5F6,
        v17,
        v18,
        (__int64)&v19);
    }
    return -2147467262;
  }
}

```

## disassembly

```asm
0x18001de90  mov     [rsp+arg_0], rbx
0x18001de95  mov     [rsp+arg_8], rsi
0x18001de9a  push    rdi
0x18001de9b  sub     rsp, 30h
0x18001de9f  mov     rdi, r8
0x18001dea2  mov     rsi, rdx
0x18001dea5  mov     rbx, rcx
0x18001dea8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57054134@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57054134@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134> `wil::Feature<__WilFeatureTraits_Feature_57054134>::GetImpl(void)'::`2'::impl
0x18001deaf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57054134@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::__private_IsEnabled(void)
0x18001deb4  test    al, al
0x18001deb6  jz      short loc_18001DF1A
0x18001deb8  mov     rax, qword ptr cs:CLSID_MemoryDiagnostic.Data1
0x18001debf  cmp     rax, [rbx]
0x18001dec2  jnz     short loc_18001DF38
0x18001dec4  mov     rax, qword ptr cs:CLSID_MemoryDiagnostic.Data4
0x18001decb  cmp     rax, [rbx+8]
0x18001decf  jnz     short loc_18001DF38
0x18001ded1  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18001ded6  mov     ecx, [rax]
0x18001ded8  cmp     ecx, 4
0x18001dedb  jbe     short loc_18001DF1A
0x18001dedd  mov     rdx, [rax+18h]
0x18001dee1  mov     rcx, [rax+10h]
0x18001dee5  test    cl, 1
0x18001dee8  jz      short loc_18001DF1A
0x18001deea  mov     rcx, rdx
0x18001deed  and     ecx, 1
0x18001def0  cmp     rcx, rdx
0x18001def3  jnz     short loc_18001DF1A
0x18001def5  lea     rcx, aDllgetclassobj_1; "DllGetClassObject_CreateOnlineMemoryDia"...
0x18001defc  mov     [rsp+38h+arg_18], rcx
0x18001df01  lea     rdx, word_18002A69A
0x18001df08  lea     rcx, [rsp+38h+arg_18]
0x18001df0d  mov     [rsp+38h+var_18], rcx
0x18001df12  mov     rcx, rax
0x18001df15  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18001df1a  mov     r9, rdi
0x18001df1d  mov     r8, rsi
0x18001df20  mov     rdx, rbx
0x18001df23  call    ?DllGetClassObject@?$CWinTaskModuleT@VCMemoryDiagnosticHandler@@$1?CLSID_MemoryDiagnostic@@3U_GUID@@B@@QEAAJAEBU_GUID@@0PEAPEAX@Z; CWinTaskModuleT<CMemoryDiagnosticHandler,&_GUID const CLSID_MemoryDiagnostic>::DllGetClassObject(_GUID const &,_GUID const &,void * *)
0x18001df28  mov     rbx, [rsp+38h+arg_0]
0x18001df2d  mov     rsi, [rsp+38h+arg_8]
0x18001df32  add     rsp, 30h
0x18001df36  pop     rdi
0x18001df37  retn
0x18001df38  mov     rax, qword ptr cs:CLSID_AutomaticOfflineMemoryDiagnostic.Data1
0x18001df3f  cmp     rax, [rbx]
0x18001df42  jnz     loc_18001E026
0x18001df48  mov     rax, qword ptr cs:CLSID_AutomaticOfflineMemoryDiagnostic.Data4
0x18001df4f  cmp     rax, [rbx+8]
0x18001df53  jnz     loc_18001E026
0x18001df59  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18001df5e  mov     ecx, [rax]
0x18001df60  cmp     ecx, 4
0x18001df63  jbe     short loc_18001DFA2
0x18001df65  mov     rdx, [rax+18h]
0x18001df69  mov     rcx, [rax+10h]
0x18001df6d  test    cl, 1
0x18001df70  jz      short loc_18001DFA2
0x18001df72  mov     rcx, rdx
0x18001df75  and     ecx, 1
0x18001df78  cmp     rcx, rdx
0x18001df7b  jnz     short loc_18001DFA2
0x18001df7d  lea     rcx, aDllgetclassobj_2; "DllGetClassObject_CreateOfflineMemoryDi"...
0x18001df84  mov     [rsp+38h+arg_18], rcx
0x18001df89  lea     rdx, word_18002A676
0x18001df90  lea     rcx, [rsp+38h+arg_18]
0x18001df95  mov     [rsp+38h+var_18], rcx
0x18001df9a  mov     rcx, rax
0x18001df9d  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18001dfa2  test    rdi, rdi
0x18001dfa5  jnz     short loc_18001DFAE
0x18001dfa7  mov     edi, 80070057h
0x18001dfac  jmp     short loc_18001E01F
0x18001dfae  mov     qword ptr [rdi], 0
0x18001dfb5  mov     rax, qword ptr cs:CLSID_AutomaticOfflineMemoryDiagnostic.Data1
0x18001dfbc  cmp     rax, [rbx]
0x18001dfbf  jnz     short loc_18001E01A
0x18001dfc1  mov     rax, qword ptr cs:CLSID_AutomaticOfflineMemoryDiagnostic.Data4
0x18001dfc8  cmp     rax, [rbx+8]
0x18001dfcc  jnz     short loc_18001E01A
0x18001dfce  mov     ecx, 10h; Size
0x18001dfd3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001dfd8  mov     rbx, rax
0x18001dfdb  lea     rax, ??_7?$CWinTaskClassFactoryT@VAOMDHandler@@$00@@6B@; const CWinTaskClassFactoryT<AOMDHandler,1>::`vftable'
0x18001dfe2  mov     [rbx], rax
0x18001dfe5  mov     dword ptr [rbx+8], 1
0x18001dfec  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18001dff3  mov     rcx, [rbx]
0x18001dff6  mov     r8, rdi
0x18001dff9  mov     rdx, rsi
0x18001dffc  mov     rax, [rcx]
0x18001dfff  mov     rcx, rbx
0x18001e002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e007  mov     edi, eax
0x18001e009  mov     rax, [rbx]
0x18001e00c  mov     rcx, rbx
0x18001e00f  mov     rax, [rax+10h]
0x18001e013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e018  jmp     short loc_18001E01F
0x18001e01a  mov     edi, 80040111h
0x18001e01f  mov     eax, edi
0x18001e021  jmp     loc_18001DF28
0x18001e026  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18001e02b  mov     ecx, [rax]
0x18001e02d  cmp     ecx, 4
0x18001e030  jbe     short loc_18001E06F
0x18001e032  mov     rdx, [rax+18h]
0x18001e036  mov     rcx, [rax+10h]
0x18001e03a  test    cl, 1
0x18001e03d  jz      short loc_18001E06F
0x18001e03f  mov     rcx, rdx
0x18001e042  and     ecx, 1
0x18001e045  cmp     rcx, rdx
0x18001e048  jnz     short loc_18001E06F
0x18001e04a  lea     rcx, aDllgetclassobj_0; "DllGetClassObject_DefaultCreatePath"
0x18001e051  mov     [rsp+38h+arg_18], rcx
0x18001e056  lea     rdx, word_18002A5F6
0x18001e05d  lea     rcx, [rsp+38h+arg_18]
0x18001e062  mov     [rsp+38h+var_18], rcx
0x18001e067  mov     rcx, rax
0x18001e06a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18001e06f  mov     eax, 80004002h
0x18001e074  jmp     loc_18001DF28
```
