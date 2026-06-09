# wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x18000be70`
- end: `0x18000c1b8`
- name: `?NotifyFailure@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@UEAA_NAEBUFailureInfo@2@@Z`
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
- `0x18000be70`
- `0x18000c3bc`
- `0x18000ce90`
- `0x180022010`

## pseudocode

```c
char __fastcall wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(
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
      if ( *(_DWORD *)v6 > 2u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL) )
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
          (__int64)byte_180028C31,
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
      if ( *(_DWORD *)v4 > 2u && (unsigned __int8)tlgKeywordOn(v4, 0x600000000000LL) )
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
          (__int64)&word_180028E7E,
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
0x18000be70  push    rbp
0x18000be72  push    rbx
0x18000be73  push    rdi
0x18000be74  lea     rbp, [rsp+10h]
0x18000be79  sub     rsp, 120h
0x18000be80  mov     rbx, rdx
0x18000be83  mov     rdi, rcx
0x18000be86  test    byte ptr [rdx+4], 2
0x18000be8a  jnz     loc_18000C16E
0x18000be90  mov     rax, [rcx]
0x18000be93  mov     edx, [rdx+10h]
0x18000be96  mov     rax, [rax+10h]
0x18000be9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be9f  test    al, al
0x18000bea1  jnz     loc_18000BFF1
0x18000bea7  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18000beac  mov     r9, rax
0x18000beaf  mov     ecx, [rax]
0x18000beb1  cmp     ecx, 2
0x18000beb4  jbe     loc_18000C16E
0x18000beba  mov     rdx, 600000000000h
0x18000bec4  mov     rcx, rax
0x18000bec7  call    _tlgKeywordOn
0x18000becc  test    al, al
0x18000bece  jz      loc_18000C16E
0x18000bed4  mov     rcx, [rbx+78h]
0x18000bed8  mov     [rbp+var_70], rcx
0x18000bedc  mov     rax, [rbx+70h]
0x18000bee0  mov     [rbp+var_78], rax
0x18000bee4  mov     eax, [rbx+68h]
0x18000bee7  mov     [rbp+arg_0], eax
0x18000beea  mov     rax, [rbx+60h]
0x18000beee  mov     [rbp+var_68], rax
0x18000bef2  mov     rax, [rbx+58h]
0x18000bef6  mov     [rbp+var_60], rax
0x18000befa  mov     eax, [rbx+50h]
0x18000befd  mov     [rbp+arg_8], eax
0x18000bf00  mov     rax, [rbx+48h]
0x18000bf04  mov     [rbp+var_58], rax
0x18000bf08  mov     eax, [rbx+20h]
0x18000bf0b  mov     [rbp+arg_10], eax
0x18000bf0e  mov     rax, [rbx+18h]
0x18000bf12  mov     [rbp+var_50], rax
0x18000bf16  mov     eax, [rbx]
0x18000bf18  mov     [rbp+arg_18], eax
0x18000bf1b  mov     rax, [rbx+80h]
0x18000bf22  mov     [rbp+var_48], rax
0x18000bf26  mov     eax, [rbx+40h]
0x18000bf29  mov     [rbp+var_80], eax
0x18000bf2c  mov     rax, [rbx+38h]
0x18000bf30  mov     [rbp+var_40], rax
0x18000bf34  mov     eax, [rbx+8]
0x18000bf37  mov     [rbp+var_7C], eax
0x18000bf3a  mov     [rbp+var_38], 1000000h
0x18000bf42  mov     r8, [rdi+110h]
0x18000bf49  add     r8, 8
0x18000bf4d  lea     rax, [rbp+var_70]
0x18000bf51  mov     [rsp+130h+var_A0], rax
0x18000bf59  lea     rax, [rbp+var_78]
0x18000bf5d  mov     [rsp+130h+var_A8], rax
0x18000bf65  lea     rax, [rbp+arg_0]
0x18000bf69  mov     [rsp+130h+var_B0], rax
0x18000bf71  lea     rax, [rbp+var_68]
0x18000bf75  mov     [rsp+130h+var_B8], rax
0x18000bf7a  lea     rax, [rbp+var_60]
0x18000bf7e  mov     [rsp+130h+var_C0], rax
0x18000bf83  lea     rax, [rbp+arg_8]
0x18000bf87  mov     [rsp+130h+var_C8], rax
0x18000bf8c  lea     rax, [rbp+var_58]
0x18000bf90  mov     [rsp+130h+var_D0], rax
0x18000bf95  lea     rax, [rbp+arg_10]
0x18000bf99  mov     [rsp+130h+var_D8], rax
0x18000bf9e  lea     rax, [rbp+var_50]
0x18000bfa2  mov     [rsp+130h+var_E0], rax
0x18000bfa7  lea     rax, [rbp+arg_18]
0x18000bfab  mov     [rsp+130h+var_E8], rax
0x18000bfb0  lea     rax, [rbp+var_48]
0x18000bfb4  mov     [rsp+130h+var_F0], rax
0x18000bfb9  lea     rax, [rbp+var_80]
0x18000bfbd  mov     [rsp+130h+var_F8], rax
0x18000bfc2  lea     rax, [rbp+var_40]
0x18000bfc6  mov     [rsp+130h+var_100], rax
0x18000bfcb  lea     rax, [rbp+var_7C]
0x18000bfcf  mov     [rsp+130h+var_108], rax
0x18000bfd4  lea     rax, [rbp+var_38]
0x18000bfd8  mov     [rsp+130h+var_110], rax
0x18000bfdd  lea     rdx, word_180028E7E
0x18000bfe4  mov     rcx, r9
0x18000bfe7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000bfec  jmp     loc_18000C16E
0x18000bff1  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18000bff6  mov     r9, rax
0x18000bff9  mov     ecx, [rax]
0x18000bffb  cmp     ecx, 2
0x18000bffe  jbe     loc_18000C16E
0x18000c004  mov     rdx, 400000000000h
0x18000c00e  mov     rcx, rax
0x18000c011  call    _tlgKeywordOn
0x18000c016  test    al, al
0x18000c018  jz      loc_18000C16E
0x18000c01e  mov     rcx, [rbx+30h]
0x18000c022  mov     [rbp+var_38], rcx
0x18000c026  mov     eax, [rbx+44h]
0x18000c029  mov     [rbp+arg_0], eax
0x18000c02c  mov     eax, [rbx+10h]
0x18000c02f  mov     [rbp+arg_8], eax
0x18000c032  mov     rax, [rbx+78h]
0x18000c036  mov     [rbp+var_40], rax
0x18000c03a  mov     rax, [rbx+70h]
0x18000c03e  mov     [rbp+var_48], rax
0x18000c042  mov     eax, [rbx+68h]
0x18000c045  mov     [rbp+arg_10], eax
0x18000c048  mov     rax, [rbx+60h]
0x18000c04c  mov     [rbp+var_50], rax
0x18000c050  mov     rax, [rbx+58h]
0x18000c054  mov     [rbp+var_58], rax
0x18000c058  mov     eax, [rbx+50h]
0x18000c05b  mov     [rbp+arg_18], eax
0x18000c05e  mov     rax, [rbx+48h]
0x18000c062  mov     [rbp+var_60], rax
0x18000c066  mov     eax, [rbx+20h]
0x18000c069  mov     [rbp+var_7C], eax
0x18000c06c  mov     rax, [rbx+18h]
0x18000c070  mov     [rbp+var_68], rax
0x18000c074  mov     eax, [rbx]
0x18000c076  mov     [rbp+var_80], eax
0x18000c079  mov     rax, [rbx+80h]
0x18000c080  mov     [rbp+var_30], rax
0x18000c084  mov     eax, [rbx+40h]
0x18000c087  mov     dword ptr [rbp+var_78], eax
0x18000c08a  mov     rax, [rbx+38h]
0x18000c08e  mov     [rbp+var_28], rax
0x18000c092  mov     eax, [rbx+8]
0x18000c095  mov     dword ptr [rbp+var_70], eax
0x18000c098  mov     [rbp+var_20], 1000000h
0x18000c0a0  mov     r8, [rdi+110h]
0x18000c0a7  add     r8, 8
0x18000c0ab  lea     rax, [rbp+var_38]
0x18000c0af  mov     [rsp+130h+var_88], rax
0x18000c0b7  lea     rax, [rbp+arg_0]
0x18000c0bb  mov     [rsp+130h+var_90], rax
0x18000c0c3  lea     rax, [rbp+arg_8]
0x18000c0c7  mov     [rsp+130h+var_98], rax
0x18000c0cf  lea     rax, [rbp+var_40]
0x18000c0d3  mov     [rsp+130h+var_A0], rax
0x18000c0db  lea     rax, [rbp+var_48]
0x18000c0df  mov     [rsp+130h+var_A8], rax
0x18000c0e7  lea     rax, [rbp+arg_10]
0x18000c0eb  mov     [rsp+130h+var_B0], rax
0x18000c0f3  lea     rax, [rbp+var_50]
0x18000c0f7  mov     [rsp+130h+var_B8], rax
0x18000c0fc  lea     rax, [rbp+var_58]
0x18000c100  mov     [rsp+130h+var_C0], rax
0x18000c105  lea     rax, [rbp+arg_18]
0x18000c109  mov     [rsp+130h+var_C8], rax
0x18000c10e  lea     rax, [rbp+var_60]
0x18000c112  mov     [rsp+130h+var_D0], rax
0x18000c117  lea     rax, [rbp+var_7C]
0x18000c11b  mov     [rsp+130h+var_D8], rax
0x18000c120  lea     rax, [rbp+var_68]
0x18000c124  mov     [rsp+130h+var_E0], rax
0x18000c129  lea     rax, [rbp+var_80]
0x18000c12d  mov     [rsp+130h+var_E8], rax
0x18000c132  lea     rax, [rbp+var_30]
0x18000c136  mov     [rsp+130h+var_F0], rax
0x18000c13b  lea     rax, [rbp+var_78]
0x18000c13f  mov     [rsp+130h+var_F8], rax
0x18000c144  lea     rax, [rbp+var_28]
0x18000c148  mov     [rsp+130h+var_100], rax
0x18000c14d  lea     rax, [rbp+var_70]
0x18000c151  mov     [rsp+130h+var_108], rax
0x18000c156  lea     rax, [rbp+var_20]
0x18000c15a  mov     [rsp+130h+var_110], rax
0x18000c15f  lea     rdx, byte_180028C31
0x18000c166  mov     rcx, r9
0x18000c169  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000c16e  lea     rdx, [rbp+var_18]
0x18000c172  mov     rcx, rdi
0x18000c175  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000c17a  nop
0x18000c17b  mov     rax, [rdi+110h]
0x18000c182  lea     rcx, [rax+50h]; this
0x18000c186  mov     edx, [rbx+8]
0x18000c189  cmp     edx, [rcx+8]
0x18000c18c  jz      short loc_18000C1A2
0x18000c18e  cmp     edx, [rax+48h]
0x18000c191  jnz     short loc_18000C199
0x18000c193  cmp     dword ptr [rax+48h], 0
0x18000c197  jl      short loc_18000C1A2
0x18000c199  mov     rdx, rbx; struct wil::FailureInfo *
0x18000c19c  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x18000c1a1  nop
0x18000c1a2  lea     rcx, [rbp+var_18]
0x18000c1a6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000c1ab  mov     al, 1
0x18000c1ad  add     rsp, 120h
0x18000c1b4  pop     rdi
0x18000c1b5  pop     rbx
0x18000c1b6  pop     rbp
0x18000c1b7  retn
```
