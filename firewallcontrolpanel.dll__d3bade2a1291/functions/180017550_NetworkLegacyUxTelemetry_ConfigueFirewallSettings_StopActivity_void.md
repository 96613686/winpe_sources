# NetworkLegacyUxTelemetry::ConfigueFirewallSettings::StopActivity(void)

- ea: `0x180017550`
- end: `0x180017774`
- name: `?StopActivity@ConfigueFirewallSettings@NetworkLegacyUxTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(NetworkLegacyUxTelemetry::ConfigueFirewallSettings *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x1800012b8`
- `0x1800015dc`
- `0x180001b8c`
- `0x18000cc84`
- `0x18000dfc0`
- `0x18000eecc`
- `0x180017550`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017715`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017715`

## pseudocode

```c
void __fastcall NetworkLegacyUxTelemetry::ConfigueFirewallSettings::StopActivity(
        NetworkLegacyUxTelemetry::ConfigueFirewallSettings *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  const WCHAR *v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  const WCHAR *v18; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v19; // [rsp+B0h] [rbp-9h] BYREF
  const WCHAR *v20; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v21; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v22; // [rsp+C8h] [rbp+Fh] BYREF
  const WCHAR *v23; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v24; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v25; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v28; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = NetworkLegacyUxLogging::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL, v7) )
    {
      v9 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v28 = v4[26];
      v20 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v9;
      v26 = 0x1000000;
      v27[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)&byte_1800397FF,
        v10 + 8,
        v8,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v17,
        &v25,
        (__int64)&v16,
        &v24,
        (__int64)&v31,
        &v23,
        (__int64)&v30,
        &v22,
        (__int64)&v29,
        &v21,
        &v20,
        (__int64)&v28,
        &v19,
        &v18);
    }
  }
  else
  {
    wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = NetworkLegacyUxLogging::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL, v7) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v30 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)&byte_18003992F,
        v14 + 8,
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x180017550  push    rbp
0x180017552  push    rbx
0x180017553  push    rdi
0x180017554  lea     rbp, [rsp-47h]
0x180017559  sub     rsp, 100h
0x180017560  mov     rdi, [rcx+110h]
0x180017567  mov     rbx, rcx
0x18001756a  mov     eax, [rdi+48h]
0x18001756d  test    eax, eax
0x18001756f  jns     loc_1800176EB
0x180017575  add     rdi, 50h ; 'P'
0x180017579  cmp     eax, [rdi+8]
0x18001757c  jnz     loc_1800176EB
0x180017582  test    rdi, rdi
0x180017585  jz      loc_1800176EB
0x18001758b  call    ?zInternalStop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180017590  call    ?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ; NetworkLegacyUxLogging::Provider(void)
0x180017595  mov     r9, rax
0x180017598  mov     ecx, [rax]
0x18001759a  cmp     ecx, 5
0x18001759d  jbe     loc_180017762
0x1800175a3  mov     rdx, 400000000000h
0x1800175ad  mov     rcx, rax
0x1800175b0  call    _tlgKeywordOn
0x1800175b5  test    al, al
0x1800175b7  jz      loc_180017762
0x1800175bd  mov     rax, [rdi+70h]
0x1800175c1  lea     rdx, byte_1800397FF
0x1800175c8  mov     rcx, [rdi+78h]
0x1800175cc  mov     r8, [rbx+110h]
0x1800175d3  mov     [rbp+57h+var_60], rax
0x1800175d7  add     r8, 8
0x1800175db  mov     eax, [rdi+68h]
0x1800175de  mov     [rbp+57h+arg_0], eax
0x1800175e1  mov     rax, [rdi+60h]
0x1800175e5  mov     [rbp+57h+var_58], rax
0x1800175e9  mov     rax, [rdi+58h]
0x1800175ed  mov     [rbp+57h+var_50], rax
0x1800175f1  mov     eax, [rdi+50h]
0x1800175f4  mov     [rbp+57h+arg_8], eax
0x1800175f7  mov     rax, [rdi+48h]
0x1800175fb  mov     [rbp+57h+var_48], rax
0x1800175ff  mov     eax, [rdi+20h]
0x180017602  mov     dword ptr [rbp+57h+arg_10], eax
0x180017605  mov     rax, [rdi+18h]
0x180017609  mov     [rbp+57h+var_40], rax
0x18001760d  mov     eax, [rdi]
0x18001760f  mov     [rbp+57h+arg_18], eax
0x180017612  mov     rax, [rdi+80h]
0x180017619  mov     [rbp+57h+var_38], rax
0x18001761d  mov     eax, [rdi+40h]
0x180017620  mov     [rbp+57h+var_70], eax
0x180017623  mov     rax, [rdi+38h]
0x180017627  mov     [rbp+57h+var_30], rax
0x18001762b  mov     eax, [rdi+8]
0x18001762e  mov     [rbp+57h+var_6C], eax
0x180017631  lea     rax, [rbp+57h+var_68]
0x180017635  mov     [rsp+110h+var_78], rax
0x18001763d  lea     rax, [rbp+57h+var_60]
0x180017641  mov     [rsp+110h+var_80], rax
0x180017649  lea     rax, [rbp+57h+arg_0]
0x18001764d  mov     [rsp+110h+var_88], rax
0x180017655  lea     rax, [rbp+57h+var_58]
0x180017659  mov     [rsp+110h+var_90], rax
0x180017661  lea     rax, [rbp+57h+var_50]
0x180017665  mov     [rsp+110h+var_98], rax
0x18001766a  lea     rax, [rbp+57h+arg_8]
0x18001766e  mov     [rsp+110h+var_A0], rax
0x180017673  lea     rax, [rbp+57h+var_48]
0x180017677  mov     [rsp+110h+var_A8], rax
0x18001767c  lea     rax, [rbp+57h+arg_10]
0x180017680  mov     [rsp+110h+var_B0], rax
0x180017685  lea     rax, [rbp+57h+var_40]
0x180017689  mov     [rsp+110h+var_B8], rax
0x18001768e  lea     rax, [rbp+57h+arg_18]
0x180017692  mov     [rsp+110h+var_C0], rax
0x180017697  lea     rax, [rbp+57h+var_38]
0x18001769b  mov     [rsp+110h+var_C8], rax
0x1800176a0  lea     rax, [rbp+57h+var_70]
0x1800176a4  mov     [rsp+110h+var_D0], rax
0x1800176a9  lea     rax, [rbp+57h+var_30]
0x1800176ad  mov     [rsp+110h+var_D8], rax
0x1800176b2  lea     rax, [rbp+57h+var_6C]
0x1800176b6  mov     [rsp+110h+var_E0], rax
0x1800176bb  lea     rax, [rbp+57h+var_28]
0x1800176bf  mov     [rsp+110h+var_E8], rax
0x1800176c4  lea     rax, [rbp+57h+var_20]
0x1800176c8  mov     [rbp+57h+var_68], rcx
0x1800176cc  mov     rcx, r9
0x1800176cf  mov     [rsp+110h+var_F0], rax
0x1800176d4  mov     [rbp+57h+var_28], 1000000h
0x1800176dc  mov     [rbp+57h+var_20], 0
0x1800176e4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800176e9  jmp     short loc_180017762
0x1800176eb  call    ?zInternalStop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800176f0  call    ?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ; NetworkLegacyUxLogging::Provider(void)
0x1800176f5  mov     rdi, rax
0x1800176f8  mov     ecx, [rax]
0x1800176fa  cmp     ecx, 5
0x1800176fd  jbe     short loc_180017762
0x1800176ff  mov     rdx, 400000000000h
0x180017709  mov     rcx, rax
0x18001770c  call    _tlgKeywordOn
0x180017711  test    al, al
0x180017713  jz      short loc_180017762
0x180017715  call    cs:__imp_GetCurrentThreadId
0x18001771b  mov     r8, [rbx+110h]
0x180017722  lea     rdx, byte_18003992F
0x180017729  mov     [rbp+57h+arg_0], eax
0x18001772c  mov     rcx, rdi
0x18001772f  mov     eax, [r8+48h]
0x180017733  add     r8, 8
0x180017737  mov     [rbp+57h+arg_8], eax
0x18001773a  lea     rax, [rbp+57h+arg_0]
0x18001773e  mov     [rsp+110h+var_E0], rax
0x180017743  lea     rax, [rbp+57h+arg_8]
0x180017747  mov     [rsp+110h+var_E8], rax
0x18001774c  lea     rax, [rbp+57h+arg_10]
0x180017750  mov     [rsp+110h+var_F0], rax
0x180017755  mov     [rbp+57h+arg_10], 0
0x18001775d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180017762  mov     rcx, rbx
0x180017765  add     rsp, 100h
0x18001776c  pop     rdi
0x18001776d  pop     rbx
0x18001776e  pop     rbp
0x18001776f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
