# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::Stop(ushort const *)

- ea: `0x18000d754`
- end: `0x18000d9a7`
- name: `?Stop@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEBG@Z`
- size: `595`
- prototype: `void __fastcall(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000e750`

## callees

- `0x1800013bc`
- `0x180001a4c`
- `0x18000247c`
- `0x18000b044`
- `0x18000c3bc`
- `0x18000d754`
- `0x18000fac8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d937`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d937`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::Stop(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *this,
        const unsigned __int16 *a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r9
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // [rsp+B0h] [rbp-80h] BYREF
  int v16; // [rsp+B4h] [rbp-7Ch] BYREF
  int v17; // [rsp+B8h] [rbp-78h] BYREF
  __int64 v18; // [rsp+C0h] [rbp-70h] BYREF
  const unsigned __int16 *v19; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v20; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v22; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v23; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v24; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v25; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v26; // [rsp+100h] [rbp-30h] BYREF
  __int64 v27; // [rsp+108h] [rbp-28h] BYREF
  __int64 v28[4]; // [rsp+110h] [rbp-20h] BYREF
  DWORD v29; // [rsp+140h] [rbp+10h] BYREF
  int v30; // [rsp+150h] [rbp+20h] BYREF
  const unsigned __int16 *v31; // [rsp+158h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x200000000000LL) )
    {
      v9 = *((_QWORD *)this + 34);
      v20 = *((_QWORD *)v6 + 15);
      v21 = *((_QWORD *)v6 + 14);
      v29 = v6[26];
      v22 = *((_QWORD *)v6 + 12);
      v23 = *((_QWORD *)v6 + 11);
      v30 = v6[20];
      v24 = *((_QWORD *)v6 + 9);
      LODWORD(v31) = v6[8];
      v25 = *((_QWORD *)v6 + 3);
      v15 = *v6;
      v26 = *((_QWORD *)v6 + 16);
      v16 = v6[16];
      v27 = *((_QWORD *)v6 + 7);
      v17 = v6[2];
      v19 = a2;
      v28[0] = 0x1000000;
      v18 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)&dword_180028ADC,
        v9 + 8,
        v8,
        (__int64)&v18,
        (__int64)v28,
        (__int64)&v17,
        &v27,
        (__int64)&v16,
        &v26,
        (__int64)&v15,
        &v25,
        (__int64)&v31,
        &v24,
        (__int64)&v30,
        &v23,
        &v22,
        (__int64)&v29,
        &v21,
        &v20,
        &v19);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v11 = (__int64)v10;
    if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x200000000000LL) )
    {
      v31 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      v29 = CurrentThreadId;
      v30 = *(_DWORD *)(v13 + 72);
      v18 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v11,
        (__int64)byte_1800289C1,
        v13 + 8,
        v14,
        (__int64)&v18,
        (__int64)&v30,
        (__int64)&v29,
        &v31);
    }
  }
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000d754  mov     [rsp-8+arg_8], rbx
0x18000d759  push    rbp
0x18000d75a  push    rsi
0x18000d75b  push    rdi
0x18000d75c  lea     rbp, [rsp+10h]
0x18000d761  sub     rsp, 120h
0x18000d768  mov     rdi, [rcx+110h]
0x18000d76f  mov     rsi, rdx
0x18000d772  mov     rbx, rcx
0x18000d775  mov     eax, [rdi+48h]
0x18000d778  test    eax, eax
0x18000d77a  jns     loc_18000D909
0x18000d780  add     rdi, 50h ; 'P'
0x18000d784  cmp     eax, [rdi+8]
0x18000d787  jnz     loc_18000D909
0x18000d78d  test    rdi, rdi
0x18000d790  jz      loc_18000D909
0x18000d796  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000d79b  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18000d7a0  mov     r9, rax
0x18000d7a3  mov     ecx, [rax]
0x18000d7a5  cmp     ecx, 5
0x18000d7a8  jbe     loc_18000D98D
0x18000d7ae  mov     rdx, 200000000000h
0x18000d7b8  mov     rcx, rax
0x18000d7bb  call    _tlgKeywordOn
0x18000d7c0  test    al, al
0x18000d7c2  jz      loc_18000D98D
0x18000d7c8  mov     rax, [rdi+78h]
0x18000d7cc  lea     rdx, dword_180028ADC
0x18000d7d3  mov     r8, [rbx+110h]
0x18000d7da  mov     rcx, r9
0x18000d7dd  mov     [rbp+var_60], rax
0x18000d7e1  add     r8, 8
0x18000d7e5  mov     rax, [rdi+70h]
0x18000d7e9  mov     [rbp+var_58], rax
0x18000d7ed  mov     eax, [rdi+68h]
0x18000d7f0  mov     [rbp+arg_0], eax
0x18000d7f3  mov     rax, [rdi+60h]
0x18000d7f7  mov     [rbp+var_50], rax
0x18000d7fb  mov     rax, [rdi+58h]
0x18000d7ff  mov     [rbp+var_48], rax
0x18000d803  mov     eax, [rdi+50h]
0x18000d806  mov     [rbp+arg_10], eax
0x18000d809  mov     rax, [rdi+48h]
0x18000d80d  mov     [rbp+var_40], rax
0x18000d811  mov     eax, [rdi+20h]
0x18000d814  mov     dword ptr [rbp+arg_18], eax
0x18000d817  mov     rax, [rdi+18h]
0x18000d81b  mov     [rbp+var_38], rax
0x18000d81f  mov     eax, [rdi]
0x18000d821  mov     [rbp+var_80], eax
0x18000d824  mov     rax, [rdi+80h]
0x18000d82b  mov     [rbp+var_30], rax
0x18000d82f  mov     eax, [rdi+40h]
0x18000d832  mov     [rbp+var_7C], eax
0x18000d835  mov     rax, [rdi+38h]
0x18000d839  mov     [rbp+var_28], rax
0x18000d83d  mov     eax, [rdi+8]
0x18000d840  mov     [rbp+var_78], eax
0x18000d843  lea     rax, [rbp+var_68]
0x18000d847  mov     [rsp+130h+var_90], rax
0x18000d84f  lea     rax, [rbp+var_60]
0x18000d853  mov     [rsp+130h+var_98], rax
0x18000d85b  lea     rax, [rbp+var_58]
0x18000d85f  mov     [rsp+130h+var_A0], rax
0x18000d867  lea     rax, [rbp+arg_0]
0x18000d86b  mov     [rsp+130h+var_A8], rax
0x18000d873  lea     rax, [rbp+var_50]
0x18000d877  mov     [rsp+130h+var_B0], rax
0x18000d87f  lea     rax, [rbp+var_48]
0x18000d883  mov     [rsp+130h+var_B8], rax
0x18000d888  lea     rax, [rbp+arg_10]
0x18000d88c  mov     [rsp+130h+var_C0], rax
0x18000d891  lea     rax, [rbp+var_40]
0x18000d895  mov     [rsp+130h+var_C8], rax
0x18000d89a  lea     rax, [rbp+arg_18]
0x18000d89e  mov     [rsp+130h+var_D0], rax
0x18000d8a3  lea     rax, [rbp+var_38]
0x18000d8a7  mov     [rsp+130h+var_D8], rax
0x18000d8ac  lea     rax, [rbp+var_80]
0x18000d8b0  mov     [rsp+130h+var_E0], rax
0x18000d8b5  lea     rax, [rbp+var_30]
0x18000d8b9  mov     [rsp+130h+var_E8], rax
0x18000d8be  lea     rax, [rbp+var_7C]
0x18000d8c2  mov     [rsp+130h+var_F0], rax
0x18000d8c7  lea     rax, [rbp+var_28]
0x18000d8cb  mov     [rsp+130h+var_F8], rax
0x18000d8d0  lea     rax, [rbp+var_78]
0x18000d8d4  mov     [rsp+130h+var_100], rax
0x18000d8d9  lea     rax, [rbp+var_20]
0x18000d8dd  mov     [rsp+130h+var_108], rax
0x18000d8e2  lea     rax, [rbp+var_70]
0x18000d8e6  mov     [rsp+130h+var_110], rax
0x18000d8eb  mov     [rbp+var_68], rsi
0x18000d8ef  mov     [rbp+var_20], 1000000h
0x18000d8f7  mov     [rbp+var_70], 0
0x18000d8ff  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564566@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000d904  jmp     loc_18000D98D
0x18000d909  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000d90e  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18000d913  mov     rdi, rax
0x18000d916  mov     ecx, [rax]
0x18000d918  cmp     ecx, 5
0x18000d91b  jbe     short loc_18000D98D
0x18000d91d  mov     rdx, 200000000000h
0x18000d927  mov     rcx, rax
0x18000d92a  call    _tlgKeywordOn
0x18000d92f  test    al, al
0x18000d931  jz      short loc_18000D98D
0x18000d933  mov     [rbp+arg_18], rsi
0x18000d937  call    cs:__imp_GetCurrentThreadId
0x18000d93d  mov     r8, [rbx+110h]
0x18000d944  lea     rdx, byte_1800289C1
0x18000d94b  mov     [rbp+arg_0], eax
0x18000d94e  mov     rcx, rdi
0x18000d951  mov     eax, [r8+48h]
0x18000d955  add     r8, 8
0x18000d959  mov     [rbp+arg_10], eax
0x18000d95c  lea     rax, [rbp+arg_18]
0x18000d960  mov     [rsp+130h+var_F8], rax
0x18000d965  lea     rax, [rbp+arg_0]
0x18000d969  mov     [rsp+130h+var_100], rax
0x18000d96e  lea     rax, [rbp+arg_10]
0x18000d972  mov     [rsp+130h+var_108], rax
0x18000d977  lea     rax, [rbp+var_70]
0x18000d97b  mov     [rsp+130h+var_110], rax
0x18000d980  mov     [rbp+var_70], 0
0x18000d988  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18000d98d  mov     rcx, rbx
0x18000d990  mov     rbx, [rsp+130h+arg_8]
0x18000d998  add     rsp, 120h
0x18000d99f  pop     rdi
0x18000d9a0  pop     rsi
0x18000d9a1  pop     rbp
0x18000d9a2  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
