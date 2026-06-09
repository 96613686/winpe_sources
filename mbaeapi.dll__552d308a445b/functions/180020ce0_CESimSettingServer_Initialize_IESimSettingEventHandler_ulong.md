# CESimSettingServer::Initialize(IESimSettingEventHandler *,ulong)

- ea: `0x180020ce0`
- end: `0x180020f99`
- name: `?Initialize@CESimSettingServer@@UEAAJPEAUIESimSettingEventHandler@@K@Z`
- size: `697`
- prototype: `__int64 __fastcall(CESimSettingServer *this, struct IESimSettingEventHandler *, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000178c`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x180013a74`
- `0x1800172bc`
- `0x18001dd10`
- `0x180020660`
- `0x180020ce0`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020e7c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020e7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020dc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020dc1`

## pseudocode

```c
__int64 __fastcall CESimSettingServer::Initialize(
        CESimSettingServer *this,
        struct IESimSettingEventHandler *a2,
        int a3)
{
  const struct _tlgProvider_t *v6; // rax
  int v7; // r8d
  int v8; // r9d
  DWORD CurrentThreadId; // ebx
  int v10; // ecx
  bool v11; // zf
  char v12; // al
  unsigned int v13; // ebx
  __int64 v14; // rdx
  const struct _tlgProvider_t *v16; // rax
  int v17; // r8d
  int v18; // r9d
  unsigned int v19; // edi
  int v20[2]; // [rsp+20h] [rbp-49h]
  __int64 v21; // [rsp+30h] [rbp-39h]
  volatile signed __int32 *v22; // [rsp+38h] [rbp-31h]
  unsigned __int16 *v23[2]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v24; // [rsp+50h] [rbp-19h]
  unsigned __int16 *v25[2]; // [rsp+58h] [rbp-11h] BYREF
  struct IESimSettingEventHandler *v26; // [rsp+68h] [rbp-1h]
  int v27; // [rsp+70h] [rbp+7h]
  int v28; // [rsp+74h] [rbp+Bh]
  unsigned int *v29; // [rsp+78h] [rbp+Fh]
  unsigned __int16 **v30; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  unsigned int v32; // [rsp+D0h] [rbp+67h] BYREF
  unsigned __int16 *v33; // [rsp+E8h] [rbp+7Fh] BYREF

  *(_OWORD *)v25 = 0;
  v26 = 0;
  *(_OWORD *)v23 = 0;
  v24 = 0;
  std::vector<unsigned short>::resize(v25);
  std::vector<unsigned short>::resize(v23);
  StringCchPrintfW(v25[0], v25[1] - v25[0], L"Enter");
  v20[0] = 18;
  StringCchPrintfW(v23[0], v23[1] - v23[0], L"%S(%d):%s", "CESimSettingServer::Initialize");
  v6 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v6 > 5u )
  {
    v33 = v23[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v6,
      (unsigned int)byte_180075EF5,
      v7,
      v8,
      (__int64)&v33);
  }
  std::vector<unsigned short>::~vector<unsigned short>(v23);
  std::vector<unsigned short>::~vector<unsigned short>(v25);
  CurrentThreadId = GetCurrentThreadId();
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::GetImpl'::`2'::impl) )
  {
    v10 = *((_DWORD *)this + 53);
    if ( !v10 )
      goto LABEL_10;
    v11 = CurrentThreadId == v10;
  }
  else
  {
    if ( !*((_DWORD *)this + 56) )
      goto LABEL_10;
    v11 = CurrentThreadId == *((_DWORD *)this + 56);
  }
  if ( v11 )
  {
    v12 = 0;
    goto LABEL_11;
  }
LABEL_10:
  v12 = 1;
LABEL_11:
  if ( !v12 )
  {
    v13 = -2147024342;
    v14 = 20;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\esimsettingserver.cpp",
      (const char *)v13,
      v20[0]);
    return v13;
  }
  if ( !a2 )
  {
    v13 = -2147467261;
    v14 = 21;
    goto LABEL_13;
  }
  v32 = 0;
  v25[0] = (unsigned __int16 *)off_18005EA18;
  v25[1] = (unsigned __int16 *)this;
  v26 = a2;
  v27 = a3;
  v28 = HIDWORD(a2);
  v29 = &v32;
  v30 = v25;
  CSOperationDispatcher::Enqueue((char *)this + 152);
  WaitForSingleObject(*(HANDLE *)(v21 + 16), 0xFFFFFFFF);
  *(_OWORD *)v23 = 0;
  v24 = 0;
  *(_OWORD *)v25 = 0;
  v26 = 0;
  std::vector<unsigned short>::resize(v23);
  std::vector<unsigned short>::resize(v25);
  StringCchPrintfW(v23[0], v23[1] - v23[0], L"Exit");
  v20[0] = 44;
  StringCchPrintfW(v25[0], v25[1] - v25[0], L"%S(%d):%s", "CESimSettingServer::Initialize", *(_QWORD *)v20, v23[0]);
  v16 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v16 > 5u )
  {
    v33 = v25[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v16,
      (unsigned int)word_180075ED2,
      v17,
      v18,
      (__int64)&v33);
  }
  std::vector<unsigned short>::~vector<unsigned short>(v25);
  std::vector<unsigned short>::~vector<unsigned short>(v23);
  v19 = v32;
  if ( v22 && _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)())v22)();
    if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)())(*(_QWORD *)v22 + 8LL))();
  }
  return v19;
}

```

## disassembly

```asm
0x180020ce0  mov     [rsp-8+arg_8], rbx
0x180020ce5  push    rbp
0x180020ce6  push    rsi
0x180020ce7  push    rdi
0x180020ce8  push    r14
0x180020cea  push    r15
0x180020cec  lea     rbp, [rsp-37h]
0x180020cf1  sub     rsp, 0A0h
0x180020cf8  mov     r15d, r8d
0x180020cfb  mov     rsi, rdx
0x180020cfe  mov     r14, rcx
0x180020d01  xorps   xmm0, xmm0
0x180020d04  movdqu  xmmword ptr [rbp+57h+var_68], xmm0
0x180020d09  mov     [rbp+57h+var_58], 0
0x180020d11  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x180020d16  mov     [rbp+57h+var_70], 0
0x180020d1e  lea     rcx, [rbp+57h+var_68]
0x180020d22  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180020d27  lea     rcx, [rbp+57h+var_80]
0x180020d2b  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180020d30  mov     rdx, [rbp+57h+var_68+8]
0x180020d34  mov     rcx, [rbp+57h+var_68]; unsigned __int16 *
0x180020d38  sub     rdx, rcx
0x180020d3b  sar     rdx, 1; unsigned __int64
0x180020d3e  lea     r8, aEnter; "Enter"
0x180020d45  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180020d4a  mov     rdx, [rbp+57h+var_80+8]
0x180020d4e  mov     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x180020d52  sub     rdx, rcx
0x180020d55  sar     rdx, 1; unsigned __int64
0x180020d58  mov     rax, [rbp+57h+var_68]
0x180020d5c  mov     [rsp+0C0h+var_98], rax
0x180020d61  mov     [rsp+0C0h+var_A0], 12h
0x180020d69  lea     r9, aCesimsettingse_10; "CESimSettingServer::Initialize"
0x180020d70  lea     r8, aSDS; "%S(%d):%s"
0x180020d77  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180020d7c  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180020d81  mov     ecx, [rax]
0x180020d83  cmp     ecx, 5
0x180020d86  jbe     short loc_180020DA8
0x180020d88  mov     rcx, [rbp+57h+var_80]
0x180020d8c  mov     [rbp+57h+arg_18], rcx
0x180020d90  lea     rcx, [rbp+57h+arg_18]
0x180020d94  mov     qword ptr [rsp+0C0h+var_A0], rcx; int
0x180020d99  lea     rdx, byte_180075EF5
0x180020da0  mov     rcx, rax
0x180020da3  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180020da8  lea     rcx, [rbp+57h+var_80]
0x180020dac  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180020db1  lea     rcx, [rbp+57h+var_68]
0x180020db5  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180020dba  lea     rdi, [r14+98h]
0x180020dc1  call    cs:__imp_GetCurrentThreadId
0x180020dc7  mov     ebx, eax
0x180020dc9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346> `wil::Feature<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::GetImpl(void)'::`2'::impl
0x180020dd0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::__private_IsEnabled(void)
0x180020dd5  test    al, al
0x180020dd7  jz      short loc_180020DE5
0x180020dd9  mov     ecx, [rdi+3Ch]
0x180020ddc  nop
0x180020ddd  test    ecx, ecx
0x180020ddf  jz      short loc_180020DF4
0x180020de1  cmp     ebx, ecx
0x180020de3  jmp     short loc_180020DEE
0x180020de5  cmp     dword ptr [rdi+48h], 0
0x180020de9  jz      short loc_180020DF4
0x180020deb  cmp     ebx, [rdi+48h]
0x180020dee  jnz     short loc_180020DF4
0x180020df0  xor     al, al
0x180020df2  jmp     short loc_180020DF6
0x180020df4  mov     al, 1
0x180020df6  test    al, al
0x180020df8  jnz     short loc_180020E1E
0x180020dfa  mov     ebx, 8007022Ah
0x180020dff  mov     edx, 14h; void *
0x180020e04  lea     r8, aOnecoreuapNetM_5; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180020e0b  mov     r9d, ebx; char *
0x180020e0e  mov     rcx, [rbp+5Fh]; this
0x180020e12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020e17  mov     eax, ebx
0x180020e19  jmp     loc_180020F82
0x180020e1e  test    rsi, rsi
0x180020e21  jnz     short loc_180020E2D
0x180020e23  mov     ebx, 80004003h
0x180020e28  lea     edx, [rsi+15h]
0x180020e2b  jmp     short loc_180020E04
0x180020e2d  mov     [rbp+57h+arg_0], 0
0x180020e34  lea     rax, off_18005EA18
0x180020e3b  mov     [rbp+57h+var_68], rax
0x180020e3f  mov     [rbp+57h+var_68+8], r14
0x180020e43  mov     [rbp+57h+var_58], rsi
0x180020e47  mov     [rbp+57h+var_50], r15d
0x180020e4b  mov     eax, dword ptr [rbp+57h+var_58+4]
0x180020e4e  mov     [rbp+57h+var_4C], eax
0x180020e51  lea     rax, [rbp+57h+arg_0]
0x180020e55  mov     [rbp+57h+var_48], rax
0x180020e59  lea     rax, [rbp+57h+var_68]
0x180020e5d  mov     [rbp+57h+var_30], rax
0x180020e61  lea     r8, [rbp+57h+var_68]
0x180020e65  lea     rdx, [rbp+57h+var_90]
0x180020e69  mov     rcx, rdi; pv
0x180020e6c  call    ?Enqueue@CSOperationDispatcher@@QEAA?AV?$shared_ptr@VWaitableOperation@@@std@@V?$function@$$A6AXXZ@3@@Z; CSOperationDispatcher::Enqueue(std::function<void (void)>)
0x180020e71  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180020e74  mov     rcx, [rbp+57h+var_90]
0x180020e78  mov     rcx, [rcx+10h]; hHandle
0x180020e7c  call    cs:__imp_WaitForSingleObject
0x180020e82  xorps   xmm0, xmm0
0x180020e85  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x180020e8a  mov     [rbp+57h+var_70], 0
0x180020e92  xorps   xmm1, xmm1
0x180020e95  movdqu  xmmword ptr [rbp+57h+var_68], xmm1
0x180020e9a  mov     [rbp+57h+var_58], 0
0x180020ea2  lea     rcx, [rbp+57h+var_80]
0x180020ea6  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180020eab  lea     rcx, [rbp+57h+var_68]
0x180020eaf  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180020eb4  mov     rdx, [rbp+57h+var_80+8]
0x180020eb8  mov     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x180020ebc  sub     rdx, rcx
0x180020ebf  sar     rdx, 1; unsigned __int64
0x180020ec2  lea     r8, aExit; "Exit"
0x180020ec9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180020ece  mov     rdx, [rbp+57h+var_68+8]
0x180020ed2  mov     rcx, [rbp+57h+var_68]; unsigned __int16 *
0x180020ed6  sub     rdx, rcx
0x180020ed9  sar     rdx, 1; unsigned __int64
0x180020edc  mov     rax, [rbp+57h+var_80]
0x180020ee0  mov     [rsp+0C0h+var_98], rax
0x180020ee5  mov     [rsp+0C0h+var_A0], 2Ch ; ','
0x180020eed  lea     r9, aCesimsettingse_10; "CESimSettingServer::Initialize"
0x180020ef4  lea     r8, aSDS; "%S(%d):%s"
0x180020efb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180020f00  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180020f05  mov     ecx, [rax]
0x180020f07  cmp     ecx, 5
0x180020f0a  jbe     short loc_180020F2C
0x180020f0c  mov     rcx, [rbp+57h+var_68]
0x180020f10  mov     [rbp+57h+arg_18], rcx
0x180020f14  lea     rcx, [rbp+57h+arg_18]
0x180020f18  mov     qword ptr [rsp+0C0h+var_A0], rcx
0x180020f1d  lea     rdx, word_180075ED2
0x180020f24  mov     rcx, rax
0x180020f27  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180020f2c  lea     rcx, [rbp+57h+var_68]
0x180020f30  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180020f35  lea     rcx, [rbp+57h+var_80]
0x180020f39  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180020f3e  mov     edi, [rbp+57h+arg_0]
0x180020f41  mov     rbx, [rbp+57h+var_88]
0x180020f45  test    rbx, rbx
0x180020f48  jz      short loc_180020F80
0x180020f4a  or      esi, 0FFFFFFFFh
0x180020f4d  mov     eax, esi
0x180020f4f  lock xadd [rbx+8], eax
0x180020f54  add     eax, esi
0x180020f56  jnz     short loc_180020F80
0x180020f58  mov     rax, [rbx]
0x180020f5b  mov     rcx, rbx
0x180020f5e  mov     rax, [rax]
0x180020f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f66  mov     edx, esi
0x180020f68  lock xadd [rbx+0Ch], edx
0x180020f6d  add     edx, esi
0x180020f6f  jnz     short loc_180020F80
0x180020f71  mov     rdx, [rbx]
0x180020f74  mov     rcx, rbx
0x180020f77  mov     rax, [rdx+8]
0x180020f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f80  mov     eax, edi
0x180020f82  mov     rbx, [rsp+0C0h+arg_8]
0x180020f8a  add     rsp, 0A0h
0x180020f91  pop     r15
0x180020f93  pop     r14
0x180020f95  pop     rdi
0x180020f96  pop     rsi
0x180020f97  pop     rbp
0x180020f98  retn
```
