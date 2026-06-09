# PropsysTelemetry::SchemaCacheGlobalMappingLoad::StartActivity(ushort const *,bool)

- ea: `0x1800398d8`
- end: `0x180039a07`
- name: `?StartActivity@SchemaCacheGlobalMappingLoad@PropsysTelemetry@@QEAAXPEBG_N@Z`
- size: `303`
- prototype: `void __fastcall(PropsysTelemetry::SchemaCacheGlobalMappingLoad *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180035a14`
- `0x180037c70`

## callees

- `0x1800398d8`
- `0x18004cbbc`
- `0x180059500`
- `0x180059fd8`
- `0x18005bd14`
- `0x18006896c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003995f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003995f`
- `ntdll!EtwEventActivityIdControl` at `0x18003991d`
- `ntdll!EtwEventActivityIdControl` at `0x18003991d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003994e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003994e`

## pseudocode

```c
void __fastcall PropsysTelemetry::SchemaCacheGlobalMappingLoad::StartActivity(
        PropsysTelemetry::SchemaCacheGlobalMappingLoad *this,
        const unsigned __int16 *a2,
        char a3)
{
  __int64 v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  int v8; // edi
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  int v11; // r9d
  DWORD v12; // [rsp+50h] [rbp-20h] BYREF
  const unsigned __int16 *v13; // [rsp+58h] [rbp-18h] BYREF
  __int64 v14; // [rsp+60h] [rbp-10h] BYREF
  char v15; // [rsp+90h] [rbp+20h] BYREF
  DWORD TickCount; // [rsp+A8h] [rbp+38h] BYREF

  wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &v15);
  v6 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)PropsysTelemetry::Provider() <= 5u )
    *(_OWORD *)(v6 + 8) = 0;
  else
    EtwEventActivityIdControl(3, v6 + 8);
  *(_DWORD *)v6 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
  v7 = PropsysTelemetry::Provider();
  v8 = (int)v7;
  if ( *(_DWORD *)v7 > 5u )
  {
    TickCount = GetTickCount();
    v15 = a3;
    v13 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v10 = *((_QWORD *)this + 34);
    v12 = CurrentThreadId;
    v14 = 0;
    if ( !*(_BYTE *)(v10 + 4)
      || (v11 = v10 + 24, !*(_DWORD *)(v10 + 24))
      && !*(_DWORD *)(v10 + 28)
      && !*(_DWORD *)(v10 + 32)
      && !*(_DWORD *)(v10 + 36) )
    {
      v11 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
      v8,
      (unsigned int)&word_1800DDCBE,
      v10 + 8,
      v11,
      (__int64)&v14,
      (__int64)&v12,
      (__int64)&v13,
      (__int64)&v15,
      (__int64)&TickCount);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((PropsysTelemetry::SchemaCacheGlobalMappingLoad *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800398d8  mov     [rsp-18h+arg_8], rbx
0x1800398dd  mov     [rsp-18h+arg_10], rsi
0x1800398e2  push    rbp
0x1800398e3  push    rdi
0x1800398e4  push    r14
0x1800398e6  mov     rbp, rsp
0x1800398e9  sub     rsp, 70h
0x1800398ed  mov     r14, rdx
0x1800398f0  mov     sil, r8b
0x1800398f3  lea     rdx, [rbp+arg_0]
0x1800398f7  mov     rbx, rcx
0x1800398fa  call    ?LockExclusive@?$ActivityBase@VPropsysTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PropsysTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800398ff  mov     rdi, [rbx+110h]
0x180039906  call    ?Provider@PropsysTelemetry@@SAPEBU_tlgProvider_t@@XZ; PropsysTelemetry::Provider(void)
0x18003990b  mov     r9d, [rax]
0x18003990e  cmp     r9d, 5
0x180039912  jbe     short loc_180039925
0x180039914  lea     rdx, [rdi+8]
0x180039918  mov     ecx, 3
0x18003991d  call    cs:__imp_EtwEventActivityIdControl
0x180039923  jmp     short loc_18003992C
0x180039925  xorps   xmm0, xmm0
0x180039928  movups  xmmword ptr [rdi+8], xmm0
0x18003992c  lea     rcx, [rbp+arg_0]
0x180039930  mov     dword ptr [rdi], 1
0x180039936  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003993b  call    ?Provider@PropsysTelemetry@@SAPEBU_tlgProvider_t@@XZ; PropsysTelemetry::Provider(void)
0x180039940  mov     rdi, rax
0x180039943  mov     ecx, [rax]
0x180039945  cmp     ecx, 5
0x180039948  jbe     loc_1800399E0
0x18003994e  call    cs:__imp_GetTickCount
0x180039954  mov     [rbp+arg_18], eax
0x180039957  mov     [rbp+arg_0], sil
0x18003995b  mov     [rbp+var_18], r14
0x18003995f  call    cs:__imp_GetCurrentThreadId
0x180039965  mov     r8, [rbx+110h]
0x18003996c  mov     [rbp+var_20], eax
0x18003996f  mov     [rbp+var_10], 0
0x180039977  cmp     byte ptr [r8+4], 0
0x18003997c  jz      short loc_18003999D
0x18003997e  lea     r9, [r8+18h]
0x180039982  cmp     dword ptr [r9], 0
0x180039986  jnz     short loc_1800399A0
0x180039988  cmp     dword ptr [r9+4], 0
0x18003998d  jnz     short loc_1800399A0
0x18003998f  cmp     dword ptr [r9+8], 0
0x180039994  jnz     short loc_1800399A0
0x180039996  cmp     dword ptr [r9+0Ch], 0
0x18003999b  jnz     short loc_1800399A0
0x18003999d  xor     r9d, r9d
0x1800399a0  lea     rax, [rbp+arg_18]
0x1800399a4  add     r8, 8
0x1800399a8  mov     [rsp+70h+var_30], rax
0x1800399ad  lea     rdx, word_1800DDCBE
0x1800399b4  lea     rax, [rbp+arg_0]
0x1800399b8  mov     rcx, rdi
0x1800399bb  mov     [rsp+70h+var_38], rax
0x1800399c0  lea     rax, [rbp+var_18]
0x1800399c4  mov     [rsp+70h+var_40], rax
0x1800399c9  lea     rax, [rbp+var_20]
0x1800399cd  mov     [rsp+70h+var_48], rax
0x1800399d2  lea     rax, [rbp+var_10]
0x1800399d6  mov     [rsp+70h+var_50], rax
0x1800399db  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x1800399e0  lea     rcx, [rbx+120h]; this
0x1800399e7  cmp     dword ptr [rcx+18h], 0
0x1800399eb  jnz     short loc_1800399F2
0x1800399ed  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800399f2  lea     r11, [rsp+70h+var_s0]
0x1800399f7  mov     rbx, [r11+28h]
0x1800399fb  mov     rsi, [r11+30h]
0x1800399ff  mov     rsp, r11
0x180039a02  pop     r14
0x180039a04  pop     rdi
0x180039a05  pop     rbp
0x180039a06  retn
```
