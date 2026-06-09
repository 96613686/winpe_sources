# DllGetClassObject

- ea: `0x18001f1f0`
- end: `0x18001f3c2`
- name: `DllGetClassObject`
- size: `466`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x1800026d4`
- `0x18000f144`
- `0x18001b9b8`
- `0x18001f10c`
- `0x18001f1f0`
- `0x180024010`

## string_xrefs

- `0x18001f24e`: `DllGetClassObject_CreateOnlineMemoryDiagnosticTask`
- `0x18001f2d0`: `DllGetClassObject_CreateOfflineMemoryDiagnosticTask`
- `0x18001f393`: `DllGetClassObject_DefaultCreatePath`

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

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::__private_IsEnabled(
                           &`wil::Feature<__WilFeatureTraits_Feature_57054134>::GetImpl'::`2'::impl,
                           riid,
                           ppv) )
    return CWinTaskModuleT<CMemoryDiagnosticHandler,&_GUID const CLSID_MemoryDiagnostic>::DllGetClassObject(
             v6,
             rclsid,
             riid,
             ppv);
  if ( *(_QWORD *)&CLSID_MemoryDiagnostic.Data1 == *(_QWORD *)&rclsid->Data1
    && *(_QWORD *)CLSID_MemoryDiagnostic.Data4 == *(_QWORD *)rclsid->Data4 )
  {
    v7 = TlgHelper::Provider();
    if ( *(_DWORD *)v7 > 4u && (*((_BYTE *)v7 + 16) & 1) != 0 )
    {
      v6 = *((_QWORD *)v7 + 3) & 1LL;
      if ( v6 == *((_QWORD *)v7 + 3) )
      {
        v19 = L"DllGetClassObject_CreateOnlineMemoryDiagnosticTask";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v7,
          (unsigned int)&unk_18002AF12,
          v8,
          v9,
          (__int64)&v19);
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
    if ( *(_DWORD *)v11 > 4u && (*((_BYTE *)v11 + 16) & 1) != 0 && (*((_QWORD *)v11 + 3) & 1LL) == *((_QWORD *)v11 + 3) )
    {
      v19 = L"DllGetClassObject_CreateOfflineMemoryDiagnosticTask";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v11,
        (unsigned int)&unk_18002AF12,
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
    if ( *(_DWORD *)v16 > 4u && (*((_BYTE *)v16 + 16) & 1) != 0 && (*((_QWORD *)v16 + 3) & 1LL) == *((_QWORD *)v16 + 3) )
    {
      v19 = L"DllGetClassObject_DefaultCreatePath";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v16,
        (unsigned int)&unk_18002AF12,
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
0x18001f1f0  mov     [rsp+arg_0], rbx
0x18001f1f5  mov     [rsp+arg_8], rsi
0x18001f1fa  push    rdi
0x18001f1fb  sub     rsp, 30h
0x18001f1ff  mov     rdi, r8
0x18001f202  mov     rsi, rdx
0x18001f205  mov     rbx, rcx
0x18001f208  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57054134@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57054134@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134> `wil::Feature<__WilFeatureTraits_Feature_57054134>::GetImpl(void)'::`2'::impl
0x18001f20f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57054134@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::__private_IsEnabled(void)
0x18001f214  test    al, al
0x18001f216  jz      short loc_18001F273
0x18001f218  mov     rax, qword ptr cs:CLSID_MemoryDiagnostic.Data1
0x18001f21f  cmp     rax, [rbx]
0x18001f222  jnz     short loc_18001F292
0x18001f224  mov     rax, qword ptr cs:CLSID_MemoryDiagnostic.Data4
0x18001f22b  cmp     rax, [rbx+8]
0x18001f22f  jnz     short loc_18001F292
0x18001f231  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18001f236  cmp     dword ptr [rax], 4
0x18001f239  jbe     short loc_18001F273
0x18001f23b  test    byte ptr [rax+10h], 1
0x18001f23f  jz      short loc_18001F273
0x18001f241  mov     rcx, [rax+18h]
0x18001f245  and     ecx, 1
0x18001f248  cmp     rcx, [rax+18h]
0x18001f24c  jnz     short loc_18001F273
0x18001f24e  lea     rcx, aDllgetclassobj_1; "DllGetClassObject_CreateOnlineMemoryDia"...
0x18001f255  mov     [rsp+38h+arg_18], rcx
0x18001f25a  lea     rdx, byte_18002AF12
0x18001f261  lea     rcx, [rsp+38h+arg_18]
0x18001f266  mov     [rsp+38h+var_18], rcx
0x18001f26b  mov     rcx, rax
0x18001f26e  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18001f273  mov     r9, rdi
0x18001f276  mov     r8, rsi
0x18001f279  mov     rdx, rbx
0x18001f27c  call    ?DllGetClassObject@?$CWinTaskModuleT@VCMemoryDiagnosticHandler@@$1?CLSID_MemoryDiagnostic@@3U_GUID@@B@@QEAAJAEBU_GUID@@0PEAPEAX@Z; CWinTaskModuleT<CMemoryDiagnosticHandler,&_GUID const CLSID_MemoryDiagnostic>::DllGetClassObject(_GUID const &,_GUID const &,void * *)
0x18001f281  mov     rbx, [rsp+38h+arg_0]
0x18001f286  mov     rsi, [rsp+38h+arg_8]
0x18001f28b  add     rsp, 30h
0x18001f28f  pop     rdi
0x18001f290  retn
0x18001f292  mov     rax, qword ptr cs:CLSID_AutomaticOfflineMemoryDiagnostic.Data1
0x18001f299  cmp     rax, [rbx]
0x18001f29c  jnz     loc_18001F376
0x18001f2a2  mov     rax, qword ptr cs:CLSID_AutomaticOfflineMemoryDiagnostic.Data4
0x18001f2a9  cmp     rax, [rbx+8]
0x18001f2ad  jnz     loc_18001F376
0x18001f2b3  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18001f2b8  cmp     dword ptr [rax], 4
0x18001f2bb  jbe     short loc_18001F2F5
0x18001f2bd  test    byte ptr [rax+10h], 1
0x18001f2c1  jz      short loc_18001F2F5
0x18001f2c3  mov     rcx, [rax+18h]
0x18001f2c7  and     ecx, 1
0x18001f2ca  cmp     rcx, [rax+18h]
0x18001f2ce  jnz     short loc_18001F2F5
0x18001f2d0  lea     rcx, aDllgetclassobj_2; "DllGetClassObject_CreateOfflineMemoryDi"...
0x18001f2d7  mov     [rsp+38h+arg_18], rcx
0x18001f2dc  lea     rdx, byte_18002AF12
0x18001f2e3  lea     rcx, [rsp+38h+arg_18]
0x18001f2e8  mov     [rsp+38h+var_18], rcx
0x18001f2ed  mov     rcx, rax
0x18001f2f0  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18001f2f5  test    rdi, rdi
0x18001f2f8  jnz     short loc_18001F301
0x18001f2fa  mov     edi, 80070057h
0x18001f2ff  jmp     short loc_18001F36F
0x18001f301  and     qword ptr [rdi], 0
0x18001f305  mov     rax, qword ptr cs:CLSID_AutomaticOfflineMemoryDiagnostic.Data1
0x18001f30c  cmp     rax, [rbx]
0x18001f30f  jnz     short loc_18001F36A
0x18001f311  mov     rax, qword ptr cs:CLSID_AutomaticOfflineMemoryDiagnostic.Data4
0x18001f318  cmp     rax, [rbx+8]
0x18001f31c  jnz     short loc_18001F36A
0x18001f31e  mov     ecx, 10h; Size
0x18001f323  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f328  mov     rbx, rax
0x18001f32b  lea     rax, ??_7?$CWinTaskClassFactoryT@VAOMDHandler@@$00@@6B@; const CWinTaskClassFactoryT<AOMDHandler,1>::`vftable'
0x18001f332  mov     [rbx], rax
0x18001f335  mov     dword ptr [rbx+8], 1
0x18001f33c  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18001f343  mov     rcx, [rbx]
0x18001f346  mov     r8, rdi
0x18001f349  mov     rdx, rsi
0x18001f34c  mov     rax, [rcx]
0x18001f34f  mov     rcx, rbx
0x18001f352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f357  mov     edi, eax
0x18001f359  mov     rax, [rbx]
0x18001f35c  mov     rcx, rbx
0x18001f35f  mov     rax, [rax+10h]
0x18001f363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f368  jmp     short loc_18001F36F
0x18001f36a  mov     edi, 80040111h
0x18001f36f  mov     eax, edi
0x18001f371  jmp     loc_18001F281
0x18001f376  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18001f37b  cmp     dword ptr [rax], 4
0x18001f37e  jbe     short loc_18001F3B8
0x18001f380  test    byte ptr [rax+10h], 1
0x18001f384  jz      short loc_18001F3B8
0x18001f386  mov     rcx, [rax+18h]
0x18001f38a  and     ecx, 1
0x18001f38d  cmp     rcx, [rax+18h]
0x18001f391  jnz     short loc_18001F3B8
0x18001f393  lea     rcx, aDllgetclassobj_0; "DllGetClassObject_DefaultCreatePath"
0x18001f39a  mov     [rsp+38h+arg_18], rcx
0x18001f39f  lea     rdx, byte_18002AF12
0x18001f3a6  lea     rcx, [rsp+38h+arg_18]
0x18001f3ab  mov     [rsp+38h+var_18], rcx
0x18001f3b0  mov     rcx, rax
0x18001f3b3  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18001f3b8  mov     eax, 80004002h
0x18001f3bd  jmp     loc_18001F281
```
