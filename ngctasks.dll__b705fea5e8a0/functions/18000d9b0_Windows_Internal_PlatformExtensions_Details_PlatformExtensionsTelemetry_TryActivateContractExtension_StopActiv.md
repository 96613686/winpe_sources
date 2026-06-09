# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StopActivity(void)

- ea: `0x18000d9b0`
- end: `0x18000dbd4`
- name: `?StopActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180001010`
- `0x1800019bc`
- `0x18000247c`
- `0x18000b044`
- `0x18000c3bc`
- `0x18000d9b0`
- `0x18000fac8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000db75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000db75`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StopActivity(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r9
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // rdi
  int v9; // [rsp+A0h] [rbp-19h] BYREF
  int v10; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v11; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v12; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v13; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v14; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v15; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v16; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v17; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v18; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v19; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v20[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD CurrentThreadId; // [rsp+120h] [rbp+67h] BYREF
  int v22; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v23; // [rsp+130h] [rbp+77h] BYREF
  int v24; // [rsp+138h] [rbp+7Fh] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
    {
      v11 = *((_QWORD *)v4 + 15);
      v12 = *((_QWORD *)v4 + 14);
      CurrentThreadId = v4[26];
      v13 = *((_QWORD *)v4 + 12);
      v14 = *((_QWORD *)v4 + 11);
      v22 = v4[20];
      v15 = *((_QWORD *)v4 + 9);
      LODWORD(v23) = v4[8];
      v16 = *((_QWORD *)v4 + 3);
      v24 = *v4;
      v17 = *((_QWORD *)v4 + 16);
      v9 = v4[16];
      v18 = *((_QWORD *)v4 + 7);
      v10 = v4[2];
      v19 = 0x1000000;
      v20[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v6,
        (__int64)&dword_18002879C,
        *((_QWORD *)this + 34) + 8LL,
        v6,
        (__int64)v20,
        (__int64)&v19,
        (__int64)&v10,
        &v18,
        (__int64)&v9,
        &v17,
        (__int64)&v24,
        &v16,
        (__int64)&v23,
        &v15,
        (__int64)&v22,
        &v14,
        &v13,
        (__int64)&CurrentThreadId,
        &v12,
        &v11);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v8 = (__int64)v7;
    if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v22 = *(_DWORD *)(*((_QWORD *)this + 34) + 72LL);
      v23 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v8,
        (__int64)byte_180028301);
    }
  }
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000d9b0  push    rbp
0x18000d9b2  push    rbx
0x18000d9b3  push    rdi
0x18000d9b4  lea     rbp, [rsp-47h]
0x18000d9b9  sub     rsp, 100h
0x18000d9c0  mov     rbx, rcx
0x18000d9c3  mov     rdi, [rcx+110h]
0x18000d9ca  mov     eax, [rdi+48h]
0x18000d9cd  test    eax, eax
0x18000d9cf  jns     loc_18000DB4B
0x18000d9d5  add     rdi, 50h ; 'P'
0x18000d9d9  cmp     eax, [rdi+8]
0x18000d9dc  jnz     loc_18000DB4B
0x18000d9e2  test    rdi, rdi
0x18000d9e5  jz      loc_18000DB4B
0x18000d9eb  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000d9f0  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18000d9f5  mov     r9, rax
0x18000d9f8  mov     ecx, [rax]
0x18000d9fa  cmp     ecx, 5
0x18000d9fd  jbe     loc_18000DBC2
0x18000da03  mov     rdx, 400000000000h
0x18000da0d  mov     rcx, rax
0x18000da10  call    _tlgKeywordOn
0x18000da15  test    al, al
0x18000da17  jz      loc_18000DBC2
0x18000da1d  mov     rcx, [rdi+78h]
0x18000da21  mov     [rbp+57h+var_68], rcx
0x18000da25  mov     rax, [rdi+70h]
0x18000da29  mov     [rbp+57h+var_60], rax
0x18000da2d  mov     eax, [rdi+68h]
0x18000da30  mov     [rbp+57h+arg_0], eax
0x18000da33  mov     rax, [rdi+60h]
0x18000da37  mov     [rbp+57h+var_58], rax
0x18000da3b  mov     rax, [rdi+58h]
0x18000da3f  mov     [rbp+57h+var_50], rax
0x18000da43  mov     eax, [rdi+50h]
0x18000da46  mov     [rbp+57h+arg_8], eax
0x18000da49  mov     rax, [rdi+48h]
0x18000da4d  mov     [rbp+57h+var_48], rax
0x18000da51  mov     eax, [rdi+20h]
0x18000da54  mov     dword ptr [rbp+57h+arg_10], eax
0x18000da57  mov     rax, [rdi+18h]
0x18000da5b  mov     [rbp+57h+var_40], rax
0x18000da5f  mov     eax, [rdi]
0x18000da61  mov     [rbp+57h+arg_18], eax
0x18000da64  mov     rax, [rdi+80h]
0x18000da6b  mov     [rbp+57h+var_38], rax
0x18000da6f  mov     eax, [rdi+40h]
0x18000da72  mov     [rbp+57h+var_70], eax
0x18000da75  mov     rax, [rdi+38h]
0x18000da79  mov     [rbp+57h+var_30], rax
0x18000da7d  mov     eax, [rdi+8]
0x18000da80  mov     [rbp+57h+var_6C], eax
0x18000da83  mov     [rbp+57h+var_28], 1000000h
0x18000da8b  mov     [rbp+57h+var_20], 0
0x18000da93  mov     r8, [rbx+110h]
0x18000da9a  add     r8, 8
0x18000da9e  lea     rax, [rbp+57h+var_68]
0x18000daa2  mov     [rsp+110h+var_78], rax
0x18000daaa  lea     rax, [rbp+57h+var_60]
0x18000daae  mov     [rsp+110h+var_80], rax
0x18000dab6  lea     rax, [rbp+57h+arg_0]
0x18000daba  mov     [rsp+110h+var_88], rax
0x18000dac2  lea     rax, [rbp+57h+var_58]
0x18000dac6  mov     [rsp+110h+var_90], rax
0x18000dace  lea     rax, [rbp+57h+var_50]
0x18000dad2  mov     [rsp+110h+var_98], rax
0x18000dad7  lea     rax, [rbp+57h+arg_8]
0x18000dadb  mov     [rsp+110h+var_A0], rax
0x18000dae0  lea     rax, [rbp+57h+var_48]
0x18000dae4  mov     [rsp+110h+var_A8], rax
0x18000dae9  lea     rax, [rbp+57h+arg_10]
0x18000daed  mov     [rsp+110h+var_B0], rax
0x18000daf2  lea     rax, [rbp+57h+var_40]
0x18000daf6  mov     [rsp+110h+var_B8], rax
0x18000dafb  lea     rax, [rbp+57h+arg_18]
0x18000daff  mov     [rsp+110h+var_C0], rax
0x18000db04  lea     rax, [rbp+57h+var_38]
0x18000db08  mov     [rsp+110h+var_C8], rax
0x18000db0d  lea     rax, [rbp+57h+var_70]
0x18000db11  mov     [rsp+110h+var_D0], rax
0x18000db16  lea     rax, [rbp+57h+var_30]
0x18000db1a  mov     [rsp+110h+var_D8], rax
0x18000db1f  lea     rax, [rbp+57h+var_6C]
0x18000db23  mov     [rsp+110h+var_E0], rax
0x18000db28  lea     rax, [rbp+57h+var_28]
0x18000db2c  mov     [rsp+110h+var_E8], rax
0x18000db31  lea     rax, [rbp+57h+var_20]
0x18000db35  mov     [rsp+110h+var_F0], rax
0x18000db3a  lea     rdx, dword_18002879C
0x18000db41  mov     rcx, r9
0x18000db44  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000db49  jmp     short loc_18000DBC2
0x18000db4b  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000db50  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18000db55  mov     rdi, rax
0x18000db58  mov     ecx, [rax]
0x18000db5a  cmp     ecx, 5
0x18000db5d  jbe     short loc_18000DBC2
0x18000db5f  mov     rdx, 400000000000h
0x18000db69  mov     rcx, rax
0x18000db6c  call    _tlgKeywordOn
0x18000db71  test    al, al
0x18000db73  jz      short loc_18000DBC2
0x18000db75  call    cs:__imp_GetCurrentThreadId
0x18000db7b  mov     [rbp+57h+arg_0], eax
0x18000db7e  mov     r8, [rbx+110h]
0x18000db85  mov     eax, [r8+48h]
0x18000db89  mov     [rbp+57h+arg_8], eax
0x18000db8c  mov     [rbp+57h+arg_10], 0
0x18000db94  add     r8, 8
0x18000db98  lea     rax, [rbp+57h+arg_0]
0x18000db9c  mov     [rsp+110h+var_E0], rax
0x18000dba1  lea     rax, [rbp+57h+arg_8]
0x18000dba5  mov     [rsp+110h+var_E8], rax
0x18000dbaa  lea     rax, [rbp+57h+arg_10]
0x18000dbae  mov     [rsp+110h+var_F0], rax
0x18000dbb3  lea     rdx, byte_180028301
0x18000dbba  mov     rcx, rdi
0x18000dbbd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000dbc2  mov     rcx, rbx
0x18000dbc5  add     rsp, 100h
0x18000dbcc  pop     rdi
0x18000dbcd  pop     rbx
0x18000dbce  pop     rbp
0x18000dbcf  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
