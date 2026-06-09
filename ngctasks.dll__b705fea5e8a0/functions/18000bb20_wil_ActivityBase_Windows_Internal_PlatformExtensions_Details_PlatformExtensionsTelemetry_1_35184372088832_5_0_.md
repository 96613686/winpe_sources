# wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x18000bb20`
- end: `0x18000be68`
- name: `?NotifyFailure@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@UEAA_NAEBUFailureInfo@2@@Z`
- size: `840`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x180001bec`
- `0x180001e90`
- `0x18000247c`
- `0x180008c94`
- `0x18000b39c`
- `0x18000bb20`
- `0x18000c3bc`
- `0x18000ce90`
- `0x180022010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(
        _QWORD *a1,
        int *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r9
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r9
  _DWORD *v8; // rax
  int v9; // edx
  int v11; // [rsp+B0h] [rbp-80h] BYREF
  int v12; // [rsp+B4h] [rbp-7Ch] BYREF
  __int64 v13; // [rsp+B8h] [rbp-78h] BYREF
  __int64 v14; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v15; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v16; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v17; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v18; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v19; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v20; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v21; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v22; // [rsp+100h] [rbp-30h] BYREF
  __int64 v23; // [rsp+108h] [rbp-28h] BYREF
  __int64 v24; // [rsp+110h] [rbp-20h] BYREF
  RTL_SRWLOCK *v25[3]; // [rsp+118h] [rbp-18h] BYREF
  int v26; // [rsp+140h] [rbp+10h] BYREF
  int v27; // [rsp+148h] [rbp+18h] BYREF
  int v28; // [rsp+150h] [rbp+20h] BYREF
  int v29; // [rsp+158h] [rbp+28h] BYREF

  if ( (a2[1] & 2) == 0 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD))(*a1 + 16LL))(a1, (unsigned int)a2[4]) )
    {
      v6 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
      if ( *(_DWORD *)v6 > 2u && (unsigned __int8)tlgKeywordOn(v6, 0x200000000000LL) )
      {
        v21 = *((_QWORD *)a2 + 6);
        v26 = a2[17];
        v27 = a2[4];
        v20 = *((_QWORD *)a2 + 15);
        v19 = *((_QWORD *)a2 + 14);
        v28 = a2[26];
        v18 = *((_QWORD *)a2 + 12);
        v17 = *((_QWORD *)a2 + 11);
        v29 = a2[20];
        v16 = *((_QWORD *)a2 + 9);
        v12 = a2[8];
        v15 = *((_QWORD *)a2 + 3);
        v11 = *a2;
        v22 = *((_QWORD *)a2 + 16);
        LODWORD(v13) = a2[16];
        v23 = *((_QWORD *)a2 + 7);
        LODWORD(v14) = a2[2];
        v24 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v7,
          (__int64)&dword_180028664,
          a1[34] + 8LL,
          v7,
          (__int64)&v24,
          (__int64)&v14,
          &v23,
          (__int64)&v13,
          &v22,
          (__int64)&v11,
          &v15,
          (__int64)&v12,
          &v16,
          (__int64)&v29,
          &v17,
          &v18,
          (__int64)&v28,
          &v19,
          &v20,
          (__int64)&v27,
          (__int64)&v26,
          &v21);
      }
    }
    else
    {
      v4 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
      if ( *(_DWORD *)v4 > 2u && (unsigned __int8)tlgKeywordOn(v4, 0x200000000000LL) )
      {
        v14 = *((_QWORD *)a2 + 15);
        v13 = *((_QWORD *)a2 + 14);
        v26 = a2[26];
        v15 = *((_QWORD *)a2 + 12);
        v16 = *((_QWORD *)a2 + 11);
        v27 = a2[20];
        v17 = *((_QWORD *)a2 + 9);
        v28 = a2[8];
        v18 = *((_QWORD *)a2 + 3);
        v29 = *a2;
        v19 = *((_QWORD *)a2 + 16);
        v11 = a2[16];
        v20 = *((_QWORD *)a2 + 7);
        v12 = a2[2];
        v21 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v5,
          (__int64)byte_180028D69,
          a1[34] + 8LL,
          v5,
          (__int64)&v21,
          (__int64)&v12,
          &v20,
          (__int64)&v11,
          &v19,
          (__int64)&v29,
          &v18,
          (__int64)&v28,
          &v17,
          (__int64)&v27,
          &v16,
          &v15,
          (__int64)&v26,
          &v13,
          &v14);
      }
    }
  }
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    v25);
  v8 = (_DWORD *)a1[34];
  v9 = a2[2];
  if ( v9 != v8[22] && (v9 != v8[18] || (int)v8[18] >= 0) )
    wil::StoredFailureInfo::SetFailureInfo((wil::StoredFailureInfo *)(v8 + 20), (const struct wil::FailureInfo *)a2);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v25);
  return 1;
}

```

## disassembly

```asm
0x18000bb20  push    rbp
0x18000bb22  push    rbx
0x18000bb23  push    rdi
0x18000bb24  lea     rbp, [rsp+10h]
0x18000bb29  sub     rsp, 120h
0x18000bb30  mov     rbx, rdx
0x18000bb33  mov     rdi, rcx
0x18000bb36  test    byte ptr [rdx+4], 2
0x18000bb3a  jnz     loc_18000BE1E
0x18000bb40  mov     rax, [rcx]
0x18000bb43  mov     edx, [rdx+10h]
0x18000bb46  mov     rax, [rax+10h]
0x18000bb4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb4f  test    al, al
0x18000bb51  jnz     loc_18000BCA1
0x18000bb57  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18000bb5c  mov     r9, rax
0x18000bb5f  mov     ecx, [rax]
0x18000bb61  cmp     ecx, 2
0x18000bb64  jbe     loc_18000BE1E
0x18000bb6a  mov     rdx, 200000000000h
0x18000bb74  mov     rcx, rax
0x18000bb77  call    _tlgKeywordOn
0x18000bb7c  test    al, al
0x18000bb7e  jz      loc_18000BE1E
0x18000bb84  mov     rcx, [rbx+78h]
0x18000bb88  mov     [rbp+var_70], rcx
0x18000bb8c  mov     rax, [rbx+70h]
0x18000bb90  mov     [rbp+var_78], rax
0x18000bb94  mov     eax, [rbx+68h]
0x18000bb97  mov     [rbp+arg_0], eax
0x18000bb9a  mov     rax, [rbx+60h]
0x18000bb9e  mov     [rbp+var_68], rax
0x18000bba2  mov     rax, [rbx+58h]
0x18000bba6  mov     [rbp+var_60], rax
0x18000bbaa  mov     eax, [rbx+50h]
0x18000bbad  mov     [rbp+arg_8], eax
0x18000bbb0  mov     rax, [rbx+48h]
0x18000bbb4  mov     [rbp+var_58], rax
0x18000bbb8  mov     eax, [rbx+20h]
0x18000bbbb  mov     [rbp+arg_10], eax
0x18000bbbe  mov     rax, [rbx+18h]
0x18000bbc2  mov     [rbp+var_50], rax
0x18000bbc6  mov     eax, [rbx]
0x18000bbc8  mov     [rbp+arg_18], eax
0x18000bbcb  mov     rax, [rbx+80h]
0x18000bbd2  mov     [rbp+var_48], rax
0x18000bbd6  mov     eax, [rbx+40h]
0x18000bbd9  mov     [rbp+var_80], eax
0x18000bbdc  mov     rax, [rbx+38h]
0x18000bbe0  mov     [rbp+var_40], rax
0x18000bbe4  mov     eax, [rbx+8]
0x18000bbe7  mov     [rbp+var_7C], eax
0x18000bbea  mov     [rbp+var_38], 1000000h
0x18000bbf2  mov     r8, [rdi+110h]
0x18000bbf9  add     r8, 8
0x18000bbfd  lea     rax, [rbp+var_70]
0x18000bc01  mov     [rsp+130h+var_A0], rax
0x18000bc09  lea     rax, [rbp+var_78]
0x18000bc0d  mov     [rsp+130h+var_A8], rax
0x18000bc15  lea     rax, [rbp+arg_0]
0x18000bc19  mov     [rsp+130h+var_B0], rax
0x18000bc21  lea     rax, [rbp+var_68]
0x18000bc25  mov     [rsp+130h+var_B8], rax
0x18000bc2a  lea     rax, [rbp+var_60]
0x18000bc2e  mov     [rsp+130h+var_C0], rax
0x18000bc33  lea     rax, [rbp+arg_8]
0x18000bc37  mov     [rsp+130h+var_C8], rax
0x18000bc3c  lea     rax, [rbp+var_58]
0x18000bc40  mov     [rsp+130h+var_D0], rax
0x18000bc45  lea     rax, [rbp+arg_10]
0x18000bc49  mov     [rsp+130h+var_D8], rax
0x18000bc4e  lea     rax, [rbp+var_50]
0x18000bc52  mov     [rsp+130h+var_E0], rax
0x18000bc57  lea     rax, [rbp+arg_18]
0x18000bc5b  mov     [rsp+130h+var_E8], rax
0x18000bc60  lea     rax, [rbp+var_48]
0x18000bc64  mov     [rsp+130h+var_F0], rax
0x18000bc69  lea     rax, [rbp+var_80]
0x18000bc6d  mov     [rsp+130h+var_F8], rax
0x18000bc72  lea     rax, [rbp+var_40]
0x18000bc76  mov     [rsp+130h+var_100], rax
0x18000bc7b  lea     rax, [rbp+var_7C]
0x18000bc7f  mov     [rsp+130h+var_108], rax
0x18000bc84  lea     rax, [rbp+var_38]
0x18000bc88  mov     [rsp+130h+var_110], rax
0x18000bc8d  lea     rdx, byte_180028D69
0x18000bc94  mov     rcx, r9
0x18000bc97  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000bc9c  jmp     loc_18000BE1E
0x18000bca1  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18000bca6  mov     r9, rax
0x18000bca9  mov     ecx, [rax]
0x18000bcab  cmp     ecx, 2
0x18000bcae  jbe     loc_18000BE1E
0x18000bcb4  mov     rdx, 200000000000h
0x18000bcbe  mov     rcx, rax
0x18000bcc1  call    _tlgKeywordOn
0x18000bcc6  test    al, al
0x18000bcc8  jz      loc_18000BE1E
0x18000bcce  mov     rcx, [rbx+30h]
0x18000bcd2  mov     [rbp+var_38], rcx
0x18000bcd6  mov     eax, [rbx+44h]
0x18000bcd9  mov     [rbp+arg_0], eax
0x18000bcdc  mov     eax, [rbx+10h]
0x18000bcdf  mov     [rbp+arg_8], eax
0x18000bce2  mov     rax, [rbx+78h]
0x18000bce6  mov     [rbp+var_40], rax
0x18000bcea  mov     rax, [rbx+70h]
0x18000bcee  mov     [rbp+var_48], rax
0x18000bcf2  mov     eax, [rbx+68h]
0x18000bcf5  mov     [rbp+arg_10], eax
0x18000bcf8  mov     rax, [rbx+60h]
0x18000bcfc  mov     [rbp+var_50], rax
0x18000bd00  mov     rax, [rbx+58h]
0x18000bd04  mov     [rbp+var_58], rax
0x18000bd08  mov     eax, [rbx+50h]
0x18000bd0b  mov     [rbp+arg_18], eax
0x18000bd0e  mov     rax, [rbx+48h]
0x18000bd12  mov     [rbp+var_60], rax
0x18000bd16  mov     eax, [rbx+20h]
0x18000bd19  mov     [rbp+var_7C], eax
0x18000bd1c  mov     rax, [rbx+18h]
0x18000bd20  mov     [rbp+var_68], rax
0x18000bd24  mov     eax, [rbx]
0x18000bd26  mov     [rbp+var_80], eax
0x18000bd29  mov     rax, [rbx+80h]
0x18000bd30  mov     [rbp+var_30], rax
0x18000bd34  mov     eax, [rbx+40h]
0x18000bd37  mov     dword ptr [rbp+var_78], eax
0x18000bd3a  mov     rax, [rbx+38h]
0x18000bd3e  mov     [rbp+var_28], rax
0x18000bd42  mov     eax, [rbx+8]
0x18000bd45  mov     dword ptr [rbp+var_70], eax
0x18000bd48  mov     [rbp+var_20], 1000000h
0x18000bd50  mov     r8, [rdi+110h]
0x18000bd57  add     r8, 8
0x18000bd5b  lea     rax, [rbp+var_38]
0x18000bd5f  mov     [rsp+130h+var_88], rax
0x18000bd67  lea     rax, [rbp+arg_0]
0x18000bd6b  mov     [rsp+130h+var_90], rax
0x18000bd73  lea     rax, [rbp+arg_8]
0x18000bd77  mov     [rsp+130h+var_98], rax
0x18000bd7f  lea     rax, [rbp+var_40]
0x18000bd83  mov     [rsp+130h+var_A0], rax
0x18000bd8b  lea     rax, [rbp+var_48]
0x18000bd8f  mov     [rsp+130h+var_A8], rax
0x18000bd97  lea     rax, [rbp+arg_10]
0x18000bd9b  mov     [rsp+130h+var_B0], rax
0x18000bda3  lea     rax, [rbp+var_50]
0x18000bda7  mov     [rsp+130h+var_B8], rax
0x18000bdac  lea     rax, [rbp+var_58]
0x18000bdb0  mov     [rsp+130h+var_C0], rax
0x18000bdb5  lea     rax, [rbp+arg_18]
0x18000bdb9  mov     [rsp+130h+var_C8], rax
0x18000bdbe  lea     rax, [rbp+var_60]
0x18000bdc2  mov     [rsp+130h+var_D0], rax
0x18000bdc7  lea     rax, [rbp+var_7C]
0x18000bdcb  mov     [rsp+130h+var_D8], rax
0x18000bdd0  lea     rax, [rbp+var_68]
0x18000bdd4  mov     [rsp+130h+var_E0], rax
0x18000bdd9  lea     rax, [rbp+var_80]
0x18000bddd  mov     [rsp+130h+var_E8], rax
0x18000bde2  lea     rax, [rbp+var_30]
0x18000bde6  mov     [rsp+130h+var_F0], rax
0x18000bdeb  lea     rax, [rbp+var_78]
0x18000bdef  mov     [rsp+130h+var_F8], rax
0x18000bdf4  lea     rax, [rbp+var_28]
0x18000bdf8  mov     [rsp+130h+var_100], rax
0x18000bdfd  lea     rax, [rbp+var_70]
0x18000be01  mov     [rsp+130h+var_108], rax
0x18000be06  lea     rax, [rbp+var_20]
0x18000be0a  mov     [rsp+130h+var_110], rax
0x18000be0f  lea     rdx, dword_180028664
0x18000be16  mov     rcx, r9
0x18000be19  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000be1e  lea     rdx, [rbp+var_18]
0x18000be22  mov     rcx, rdi
0x18000be25  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000be2a  nop
0x18000be2b  mov     rax, [rdi+110h]
0x18000be32  lea     rcx, [rax+50h]; this
0x18000be36  mov     edx, [rbx+8]
0x18000be39  cmp     edx, [rcx+8]
0x18000be3c  jz      short loc_18000BE52
0x18000be3e  cmp     edx, [rax+48h]
0x18000be41  jnz     short loc_18000BE49
0x18000be43  cmp     dword ptr [rax+48h], 0
0x18000be47  jl      short loc_18000BE52
0x18000be49  mov     rdx, rbx; struct wil::FailureInfo *
0x18000be4c  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x18000be51  nop
0x18000be52  lea     rcx, [rbp+var_18]
0x18000be56  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000be5b  mov     al, 1
0x18000be5d  add     rsp, 120h
0x18000be64  pop     rdi
0x18000be65  pop     rbx
0x18000be66  pop     rbp
0x18000be67  retn
```
