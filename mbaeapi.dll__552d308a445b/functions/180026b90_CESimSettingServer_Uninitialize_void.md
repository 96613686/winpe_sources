# CESimSettingServer::Uninitialize(void)

- ea: `0x180026b90`
- end: `0x180026e6d`
- name: `?Uninitialize@CESimSettingServer@@UEAAJXZ`
- size: `733`
- prototype: `__int64 __fastcall(CESimSettingServer *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callees

- `0x18000178c`
- `0x180009ffc`
- `0x18000ad78`
- `0x18001105c`
- `0x180013a74`
- `0x1800172bc`
- `0x18001dd10`
- `0x180020660`
- `0x180026b90`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180026cd5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180026d0c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180026cd5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180026d0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026c64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026c64`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CESimSettingServer::Uninitialize(CESimSettingServer *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  DWORD CurrentThreadId; // edi
  const char *v6; // r9
  int v7; // ecx
  bool v8; // zf
  char v9; // al
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  volatile signed __int32 *v13; // rbx
  volatile signed __int32 *v14; // rbx
  int v16; // [rsp+20h] [rbp-69h]
  __int64 v17; // [rsp+20h] [rbp-69h]
  unsigned __int16 *v18[2]; // [rsp+30h] [rbp-59h] BYREF
  __int64 v19; // [rsp+40h] [rbp-49h]
  unsigned __int16 *v20[2]; // [rsp+48h] [rbp-41h] BYREF
  __int64 v21; // [rsp+58h] [rbp-31h]
  __int64 v22; // [rsp+60h] [rbp-29h] BYREF
  volatile signed __int32 *v23; // [rsp+68h] [rbp-21h]
  __int64 v24; // [rsp+70h] [rbp-19h] BYREF
  volatile signed __int32 *v25; // [rsp+78h] [rbp-11h]
  __int64 (__fastcall **v26)(); // [rsp+80h] [rbp-9h] BYREF
  CESimSettingServer *v27; // [rsp+88h] [rbp-1h]
  __int64 (__fastcall ***v28)(); // [rsp+B8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  unsigned __int16 *v30; // [rsp+F0h] [rbp+67h] BYREF

  *(_OWORD *)v20 = 0;
  v21 = 0;
  *(_OWORD *)v18 = 0;
  v19 = 0;
  std::vector<unsigned short>::resize(v20);
  std::vector<unsigned short>::resize(v18);
  StringCchPrintfW(v20[0], v20[1] - v20[0], L"Enter");
  v16 = 50;
  StringCchPrintfW(v18[0], v18[1] - v18[0], L"%S(%d):%s", "CESimSettingServer::Uninitialize", v16, v20[0]);
  v2 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    v30 = v18[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)&byte_180075EAF,
      v3,
      v4,
      (const unsigned __int16 **)&v30);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v18);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v20);
  CurrentThreadId = GetCurrentThreadId();
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::GetImpl'::`2'::impl) )
  {
    v7 = *((_DWORD *)this + 53);
    if ( !v7 )
      goto LABEL_10;
    v8 = CurrentThreadId == v7;
  }
  else
  {
    if ( !*((_DWORD *)this + 56) )
      goto LABEL_10;
    v8 = CurrentThreadId == *((_DWORD *)this + 56);
  }
  if ( v8 )
  {
    v9 = 0;
    goto LABEL_11;
  }
LABEL_10:
  v9 = 1;
LABEL_11:
  if ( !v9 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\esimsettingserver.cpp",
      v6);
  v26 = off_18005E9E8;
  v27 = this;
  v28 = &v26;
  CSOperationDispatcher::Enqueue((char *)this + 152, &v24, (__int64)&v26);
  WaitForSingleObject(*(HANDLE *)(v24 + 16), 0xFFFFFFFF);
  v26 = off_18005E9B8;
  v27 = this;
  v28 = &v26;
  CSOperationDispatcher::Enqueue((char *)this + 152, &v22, (__int64)&v26);
  WaitForSingleObject(*(HANDLE *)(v22 + 16), 0xFFFFFFFF);
  *(_OWORD *)v18 = 0;
  v19 = 0;
  *(_OWORD *)v20 = 0;
  v21 = 0;
  std::vector<unsigned short>::resize(v18);
  std::vector<unsigned short>::resize(v20);
  StringCchPrintfW(v18[0], v18[1] - v18[0], L"Exit");
  LODWORD(v17) = 66;
  StringCchPrintfW(v20[0], v20[1] - v20[0], L"%S(%d):%s", "CESimSettingServer::Uninitialize", v17, v18[0]);
  v10 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v10 > 5u )
  {
    v30 = v20[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v10,
      (__int64)&dword_180075E8C,
      v11,
      v12,
      (const unsigned __int16 **)&v30);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v20);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v18);
  v13 = v23;
  if ( v23 )
  {
    if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  v14 = v25;
  if ( v25 )
  {
    if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180026b90  push    rbp
0x180026b92  push    rbx
0x180026b93  push    rsi
0x180026b94  push    rdi
0x180026b95  lea     rbp, [rsp-3Fh]
0x180026b9a  sub     rsp, 0C8h
0x180026ba1  mov     rsi, rcx
0x180026ba4  xorps   xmm0, xmm0
0x180026ba7  movdqu  xmmword ptr [rbp+57h+var_98], xmm0
0x180026bac  mov     [rbp+57h+var_88], 0
0x180026bb4  movdqu  xmmword ptr [rbp+57h+var_B0], xmm0
0x180026bb9  mov     [rbp+57h+var_A0], 0
0x180026bc1  lea     rcx, [rbp+57h+var_98]
0x180026bc5  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180026bca  lea     rcx, [rbp+57h+var_B0]
0x180026bce  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180026bd3  mov     rdx, [rbp+57h+var_98+8]
0x180026bd7  mov     rcx, [rbp+57h+var_98]; unsigned __int16 *
0x180026bdb  sub     rdx, rcx
0x180026bde  sar     rdx, 1; unsigned __int64
0x180026be1  lea     r8, aEnter; "Enter"
0x180026be8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026bed  mov     rdx, [rbp+57h+var_B0+8]
0x180026bf1  mov     rcx, [rbp+57h+var_B0]; unsigned __int16 *
0x180026bf5  sub     rdx, rcx
0x180026bf8  sar     rdx, 1; unsigned __int64
0x180026bfb  mov     rax, [rbp+57h+var_98]
0x180026bff  mov     [rsp+0E0h+var_B8], rax
0x180026c04  mov     dword ptr [rsp+0E0h+var_C0], 32h ; '2'
0x180026c0c  lea     r9, aCesimsettingse_19; "CESimSettingServer::Uninitialize"
0x180026c13  lea     r8, aSDS; "%S(%d):%s"
0x180026c1a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026c1f  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180026c24  mov     ecx, [rax]
0x180026c26  cmp     ecx, 5
0x180026c29  jbe     short loc_180026C4B
0x180026c2b  mov     rcx, [rbp+57h+var_B0]
0x180026c2f  mov     [rbp+57h+arg_0], rcx
0x180026c33  lea     rcx, [rbp+57h+arg_0]
0x180026c37  mov     [rsp+0E0h+var_C0], rcx
0x180026c3c  lea     rdx, byte_180075EAF
0x180026c43  mov     rcx, rax
0x180026c46  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180026c4b  lea     rcx, [rbp+57h+var_B0]
0x180026c4f  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180026c54  lea     rcx, [rbp+57h+var_98]
0x180026c58  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180026c5d  lea     rbx, [rsi+98h]
0x180026c64  call    cs:__imp_GetCurrentThreadId
0x180026c6a  mov     edi, eax
0x180026c6c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346> `wil::Feature<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::GetImpl(void)'::`2'::impl
0x180026c73  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::__private_IsEnabled(void)
0x180026c78  test    al, al
0x180026c7a  jz      short loc_180026C88
0x180026c7c  mov     ecx, [rbx+3Ch]
0x180026c7f  nop
0x180026c80  test    ecx, ecx
0x180026c82  jz      short loc_180026C97
0x180026c84  cmp     edi, ecx
0x180026c86  jmp     short loc_180026C91
0x180026c88  cmp     dword ptr [rbx+48h], 0
0x180026c8c  jz      short loc_180026C97
0x180026c8e  cmp     edi, [rbx+48h]
0x180026c91  jnz     short loc_180026C97
0x180026c93  xor     al, al
0x180026c95  jmp     short loc_180026C99
0x180026c97  mov     al, 1
0x180026c99  test    al, al
0x180026c9b  jz      loc_180026E57
0x180026ca1  lea     rax, off_18005E9E8
0x180026ca8  mov     [rbp+57h+var_60], rax
0x180026cac  mov     [rbp+57h+var_58], rsi
0x180026cb0  lea     rax, [rbp+57h+var_60]
0x180026cb4  mov     [rbp+57h+var_28], rax
0x180026cb8  lea     r8, [rbp+57h+var_60]
0x180026cbc  lea     rdx, [rbp+57h+var_70]
0x180026cc0  mov     rcx, rbx; pv
0x180026cc3  call    ?Enqueue@CSOperationDispatcher@@QEAA?AV?$shared_ptr@VWaitableOperation@@@std@@V?$function@$$A6AXXZ@3@@Z; CSOperationDispatcher::Enqueue(std::function<void (void)>)
0x180026cc8  or      edi, 0FFFFFFFFh
0x180026ccb  mov     edx, edi; dwMilliseconds
0x180026ccd  mov     rcx, [rbp+57h+var_70]
0x180026cd1  mov     rcx, [rcx+10h]; hHandle
0x180026cd5  call    cs:__imp_WaitForSingleObject
0x180026cdb  lea     rax, off_18005E9B8
0x180026ce2  mov     [rbp+57h+var_60], rax
0x180026ce6  mov     [rbp+57h+var_58], rsi
0x180026cea  lea     rax, [rbp+57h+var_60]
0x180026cee  mov     [rbp+57h+var_28], rax
0x180026cf2  lea     r8, [rbp+57h+var_60]
0x180026cf6  lea     rdx, [rbp+57h+var_80]
0x180026cfa  mov     rcx, rbx; pv
0x180026cfd  call    ?Enqueue@CSOperationDispatcher@@QEAA?AV?$shared_ptr@VWaitableOperation@@@std@@V?$function@$$A6AXXZ@3@@Z; CSOperationDispatcher::Enqueue(std::function<void (void)>)
0x180026d02  mov     edx, edi; dwMilliseconds
0x180026d04  mov     rcx, [rbp+57h+var_80]
0x180026d08  mov     rcx, [rcx+10h]; hHandle
0x180026d0c  call    cs:__imp_WaitForSingleObject
0x180026d12  xorps   xmm0, xmm0
0x180026d15  movdqu  xmmword ptr [rbp+57h+var_B0], xmm0
0x180026d1a  mov     [rbp+57h+var_A0], 0
0x180026d22  xorps   xmm1, xmm1
0x180026d25  movdqu  xmmword ptr [rbp+57h+var_98], xmm1
0x180026d2a  mov     [rbp+57h+var_88], 0
0x180026d32  lea     rcx, [rbp+57h+var_B0]
0x180026d36  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180026d3b  lea     rcx, [rbp+57h+var_98]
0x180026d3f  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180026d44  mov     rdx, [rbp+57h+var_B0+8]
0x180026d48  mov     rcx, [rbp+57h+var_B0]; unsigned __int16 *
0x180026d4c  sub     rdx, rcx
0x180026d4f  sar     rdx, 1; unsigned __int64
0x180026d52  lea     r8, aExit; "Exit"
0x180026d59  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026d5e  mov     rdx, [rbp+57h+var_98+8]
0x180026d62  mov     rcx, [rbp+57h+var_98]; unsigned __int16 *
0x180026d66  sub     rdx, rcx
0x180026d69  sar     rdx, 1; unsigned __int64
0x180026d6c  mov     rax, [rbp+57h+var_B0]
0x180026d70  mov     [rsp+0E0h+var_B8], rax
0x180026d75  mov     dword ptr [rsp+0E0h+var_C0], 42h ; 'B'
0x180026d7d  lea     r9, aCesimsettingse_19; "CESimSettingServer::Uninitialize"
0x180026d84  lea     r8, aSDS; "%S(%d):%s"
0x180026d8b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026d90  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180026d95  mov     ecx, [rax]
0x180026d97  cmp     ecx, 5
0x180026d9a  jbe     short loc_180026DBC
0x180026d9c  mov     rcx, [rbp+57h+var_98]
0x180026da0  mov     [rbp+57h+arg_0], rcx
0x180026da4  lea     rcx, [rbp+57h+arg_0]
0x180026da8  mov     [rsp+0E0h+var_C0], rcx
0x180026dad  lea     rdx, dword_180075E8C
0x180026db4  mov     rcx, rax
0x180026db7  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180026dbc  lea     rcx, [rbp+57h+var_98]
0x180026dc0  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180026dc5  lea     rcx, [rbp+57h+var_B0]
0x180026dc9  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180026dce  or      edi, 0FFFFFFFFh
0x180026dd1  mov     rbx, [rbp+57h+var_78]
0x180026dd5  test    rbx, rbx
0x180026dd8  jz      short loc_180026E0D
0x180026dda  mov     eax, edi
0x180026ddc  lock xadd [rbx+8], eax
0x180026de1  add     eax, edi
0x180026de3  jnz     short loc_180026E0D
0x180026de5  mov     rax, [rbx]
0x180026de8  mov     rcx, rbx
0x180026deb  mov     rax, [rax]
0x180026dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026df3  mov     eax, edi
0x180026df5  lock xadd [rbx+0Ch], eax
0x180026dfa  add     eax, edi
0x180026dfc  jnz     short loc_180026E0D
0x180026dfe  mov     rax, [rbx]
0x180026e01  mov     rcx, rbx
0x180026e04  mov     rax, [rax+8]
0x180026e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e0d  mov     rbx, [rbp+57h+var_68]
0x180026e11  test    rbx, rbx
0x180026e14  jz      short loc_180026E49
0x180026e16  mov     eax, edi
0x180026e18  lock xadd [rbx+8], eax
0x180026e1d  add     eax, edi
0x180026e1f  jnz     short loc_180026E49
0x180026e21  mov     rax, [rbx]
0x180026e24  mov     rcx, rbx
0x180026e27  mov     rax, [rax]
0x180026e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e2f  mov     eax, edi
0x180026e31  lock xadd [rbx+0Ch], eax
0x180026e36  add     eax, edi
0x180026e38  jnz     short loc_180026E49
0x180026e3a  mov     rax, [rbx]
0x180026e3d  mov     rcx, rbx
0x180026e40  mov     rax, [rax+8]
0x180026e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e49  xor     eax, eax
0x180026e4b  add     rsp, 0C8h
0x180026e52  pop     rdi
0x180026e53  pop     rsi
0x180026e54  pop     rbx
0x180026e55  pop     rbp
0x180026e56  retn
0x180026e57  mov     rcx, [rbp+5Fh]; this
0x180026e5b  lea     r8, aOnecoreuapNetM_5; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180026e62  mov     edx, 34h ; '4'; void *
0x180026e67  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
