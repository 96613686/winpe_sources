# wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x180008960`
- end: `0x180008c8c`
- name: `?NotifyFailure@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@UEAA_NAEBUFailureInfo@2@@Z`
- size: `812`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001010`
- `0x18000156c`
- `0x1800019bc`
- `0x1800061ac`
- `0x180008710`
- `0x1800088d0`
- `0x180008960`
- `0x180008ca0`
- `0x18001b010`

## pseudocode

```c
char __fastcall wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(
        _QWORD *a1,
        int *a2)
{
  __int64 v4; // rcx
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // r9
  const unsigned __int16 *v11; // rcx
  __int64 v12; // r8
  _DWORD *v13; // rax
  int v14; // edx
  int v16; // [rsp+B0h] [rbp-80h] BYREF
  int v17; // [rsp+B4h] [rbp-7Ch] BYREF
  const unsigned __int16 *v18; // [rsp+B8h] [rbp-78h] BYREF
  __int64 *v19; // [rsp+C0h] [rbp-70h] BYREF
  __int64 *v20; // [rsp+C8h] [rbp-68h] BYREF
  const unsigned __int16 *v21; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v22; // [rsp+D8h] [rbp-58h] BYREF
  __int64 *v23; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v24; // [rsp+E8h] [rbp-48h] BYREF
  __int64 *v25; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v26; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v27; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v28; // [rsp+108h] [rbp-28h] BYREF
  __int64 v29[4]; // [rsp+110h] [rbp-20h] BYREF
  RTL_SRWLOCK *v30; // [rsp+140h] [rbp+10h] BYREF
  int v31; // [rsp+148h] [rbp+18h] BYREF
  int v32; // [rsp+150h] [rbp+20h] BYREF
  int v33; // [rsp+158h] [rbp+28h] BYREF

  if ( (a2[1] & 2) == 0 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD))(*a1 + 16LL))(a1, (unsigned int)a2[4]) )
    {
      v10 = Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(v4);
      if ( *(_DWORD *)v10 > 2u )
      {
        v11 = (const unsigned __int16 *)*((_QWORD *)a2 + 6);
        v12 = a1[34];
        v32 = a2[26];
        v23 = (__int64 *)*((_QWORD *)a2 + 12);
        v22 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
        v33 = a2[20];
        v21 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
        v17 = a2[8];
        v20 = (__int64 *)*((_QWORD *)a2 + 3);
        v16 = *a2;
        v27 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
        LODWORD(v18) = a2[16];
        v28 = (const unsigned __int16 *)*((_QWORD *)a2 + 7);
        LODWORD(v19) = a2[2];
        v26 = (__int64)v11;
        LODWORD(v30) = a2[17];
        v31 = a2[4];
        v25 = (__int64 *)*((_QWORD *)a2 + 15);
        v24 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
        v29[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (__int64)v10,
          (__int64)&unk_18001F518,
          v12 + 8,
          (__int64)v10,
          (__int64)v29,
          (__int64)&v19,
          &v28,
          (__int64)&v18,
          &v27,
          (__int64)&v16,
          &v20,
          (__int64)&v17,
          &v21,
          (__int64)&v33,
          &v22,
          &v23,
          (__int64)&v32,
          &v24,
          &v25,
          (__int64)&v31,
          (__int64)&v30,
          (const unsigned __int16 **)&v26);
      }
    }
    else
    {
      v5 = Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(v4);
      if ( *(_DWORD *)v5 > 2u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v6, v5) )
      {
        v8 = (__int64 *)*((_QWORD *)a2 + 15);
        v9 = a1[34];
        v18 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
        LODWORD(v30) = a2[26];
        v20 = (__int64 *)*((_QWORD *)a2 + 12);
        v21 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
        v31 = a2[20];
        v22 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
        v32 = a2[8];
        v23 = (__int64 *)*((_QWORD *)a2 + 3);
        v33 = *a2;
        v24 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
        v16 = a2[16];
        v25 = (__int64 *)*((_QWORD *)a2 + 7);
        v17 = a2[2];
        v19 = v8;
        v26 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v7,
          (__int64)byte_18001F403,
          v9 + 8,
          v7,
          (__int64)&v26,
          (__int64)&v17,
          (const unsigned __int16 **)&v25,
          (__int64)&v16,
          &v24,
          (__int64)&v33,
          &v23,
          (__int64)&v32,
          &v22,
          (__int64)&v31,
          &v21,
          &v20,
          (__int64)&v30,
          &v18,
          &v19);
      }
    }
  }
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v30);
  v13 = (_DWORD *)a1[34];
  v14 = a2[2];
  if ( v14 != v13[22] && (v14 != v13[18] || (int)v13[18] >= 0) )
    wil::StoredFailureInfo::SetFailureInfo((wil::StoredFailureInfo *)(v13 + 20), (const struct wil::FailureInfo *)a2);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v30);
  return 1;
}

```

## disassembly

```asm
0x180008960  push    rbp
0x180008962  push    rbx
0x180008963  push    rdi
0x180008964  lea     rbp, [rsp+10h]
0x180008969  sub     rsp, 120h
0x180008970  test    byte ptr [rdx+4], 2
0x180008974  mov     rbx, rdx
0x180008977  mov     rdi, rcx
0x18000897a  jnz     loc_180008C44
0x180008980  mov     rax, [rcx]
0x180008983  mov     edx, [rdx+10h]
0x180008986  mov     rax, [rax+10h]
0x18000898a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000898f  test    al, al
0x180008991  jnz     loc_180008AE1
0x180008997  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x18000899c  mov     r9, rax
0x18000899f  mov     ecx, [rax]
0x1800089a1  cmp     ecx, 2
0x1800089a4  jbe     loc_180008C44
0x1800089aa  mov     rdx, 200000000000h
0x1800089b4  mov     rcx, rax
0x1800089b7  call    _tlgKeywordOn
0x1800089bc  test    al, al
0x1800089be  jz      loc_180008C44
0x1800089c4  mov     rax, [rbx+70h]
0x1800089c8  lea     rdx, byte_18001F403
0x1800089cf  mov     rcx, [rbx+78h]
0x1800089d3  mov     r8, [rdi+110h]
0x1800089da  mov     [rbp+var_78], rax
0x1800089de  add     r8, 8
0x1800089e2  mov     eax, [rbx+68h]
0x1800089e5  mov     dword ptr [rbp+arg_0], eax
0x1800089e8  mov     rax, [rbx+60h]
0x1800089ec  mov     [rbp+var_68], rax
0x1800089f0  mov     rax, [rbx+58h]
0x1800089f4  mov     [rbp+var_60], rax
0x1800089f8  mov     eax, [rbx+50h]
0x1800089fb  mov     [rbp+arg_8], eax
0x1800089fe  mov     rax, [rbx+48h]
0x180008a02  mov     [rbp+var_58], rax
0x180008a06  mov     eax, [rbx+20h]
0x180008a09  mov     [rbp+arg_10], eax
0x180008a0c  mov     rax, [rbx+18h]
0x180008a10  mov     [rbp+var_50], rax
0x180008a14  mov     eax, [rbx]
0x180008a16  mov     [rbp+arg_18], eax
0x180008a19  mov     rax, [rbx+80h]
0x180008a20  mov     [rbp+var_48], rax
0x180008a24  mov     eax, [rbx+40h]
0x180008a27  mov     [rbp+var_80], eax
0x180008a2a  mov     rax, [rbx+38h]
0x180008a2e  mov     [rbp+var_40], rax
0x180008a32  mov     eax, [rbx+8]
0x180008a35  mov     [rbp+var_7C], eax
0x180008a38  lea     rax, [rbp+var_70]
0x180008a3c  mov     [rsp+130h+var_A0], rax
0x180008a44  lea     rax, [rbp+var_78]
0x180008a48  mov     [rsp+130h+var_A8], rax
0x180008a50  lea     rax, [rbp+arg_0]
0x180008a54  mov     [rsp+130h+var_B0], rax
0x180008a5c  lea     rax, [rbp+var_68]
0x180008a60  mov     [rsp+130h+var_B8], rax
0x180008a65  lea     rax, [rbp+var_60]
0x180008a69  mov     [rsp+130h+var_C0], rax
0x180008a6e  lea     rax, [rbp+arg_8]
0x180008a72  mov     [rsp+130h+var_C8], rax
0x180008a77  lea     rax, [rbp+var_58]
0x180008a7b  mov     [rsp+130h+var_D0], rax
0x180008a80  lea     rax, [rbp+arg_10]
0x180008a84  mov     [rsp+130h+var_D8], rax
0x180008a89  lea     rax, [rbp+var_50]
0x180008a8d  mov     [rsp+130h+var_E0], rax
0x180008a92  lea     rax, [rbp+arg_18]
0x180008a96  mov     [rsp+130h+var_E8], rax
0x180008a9b  lea     rax, [rbp+var_48]
0x180008a9f  mov     [rsp+130h+var_F0], rax
0x180008aa4  lea     rax, [rbp+var_80]
0x180008aa8  mov     [rsp+130h+var_F8], rax
0x180008aad  lea     rax, [rbp+var_40]
0x180008ab1  mov     [rsp+130h+var_100], rax
0x180008ab6  lea     rax, [rbp+var_7C]
0x180008aba  mov     [rsp+130h+var_108], rax
0x180008abf  lea     rax, [rbp+var_38]
0x180008ac3  mov     [rbp+var_70], rcx
0x180008ac7  mov     rcx, r9
0x180008aca  mov     [rsp+130h+var_110], rax
0x180008acf  mov     [rbp+var_38], 1000000h
0x180008ad7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180008adc  jmp     loc_180008C44
0x180008ae1  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x180008ae6  mov     r9, rax
0x180008ae9  mov     ecx, [rax]
0x180008aeb  cmp     ecx, 2
0x180008aee  jbe     loc_180008C44
0x180008af4  mov     eax, [rbx+68h]
0x180008af7  lea     rdx, unk_18001F518
0x180008afe  mov     rcx, [rbx+30h]
0x180008b02  mov     r8, [rdi+110h]
0x180008b09  mov     [rbp+arg_10], eax
0x180008b0c  add     r8, 8
0x180008b10  mov     rax, [rbx+60h]
0x180008b14  mov     [rbp+var_50], rax
0x180008b18  mov     rax, [rbx+58h]
0x180008b1c  mov     [rbp+var_58], rax
0x180008b20  mov     eax, [rbx+50h]
0x180008b23  mov     [rbp+arg_18], eax
0x180008b26  mov     rax, [rbx+48h]
0x180008b2a  mov     [rbp+var_60], rax
0x180008b2e  mov     eax, [rbx+20h]
0x180008b31  mov     [rbp+var_7C], eax
0x180008b34  mov     rax, [rbx+18h]
0x180008b38  mov     [rbp+var_68], rax
0x180008b3c  mov     eax, [rbx]
0x180008b3e  mov     [rbp+var_80], eax
0x180008b41  mov     rax, [rbx+80h]
0x180008b48  mov     [rbp+var_30], rax
0x180008b4c  mov     eax, [rbx+40h]
0x180008b4f  mov     dword ptr [rbp+var_78], eax
0x180008b52  mov     rax, [rbx+38h]
0x180008b56  mov     [rbp+var_28], rax
0x180008b5a  mov     eax, [rbx+8]
0x180008b5d  mov     dword ptr [rbp+var_70], eax
0x180008b60  lea     rax, [rbp+var_38]
0x180008b64  mov     [rsp+130h+var_88], rax
0x180008b6c  lea     rax, [rbp+arg_0]
0x180008b70  mov     [rsp+130h+var_90], rax
0x180008b78  lea     rax, [rbp+arg_8]
0x180008b7c  mov     [rsp+130h+var_98], rax
0x180008b84  lea     rax, [rbp+var_40]
0x180008b88  mov     [rsp+130h+var_A0], rax
0x180008b90  lea     rax, [rbp+var_48]
0x180008b94  mov     [rsp+130h+var_A8], rax
0x180008b9c  lea     rax, [rbp+arg_10]
0x180008ba0  mov     [rsp+130h+var_B0], rax
0x180008ba8  lea     rax, [rbp+var_50]
0x180008bac  mov     [rsp+130h+var_B8], rax
0x180008bb1  lea     rax, [rbp+var_58]
0x180008bb5  mov     [rsp+130h+var_C0], rax
0x180008bba  lea     rax, [rbp+arg_18]
0x180008bbe  mov     [rsp+130h+var_C8], rax
0x180008bc3  lea     rax, [rbp+var_60]
0x180008bc7  mov     [rsp+130h+var_D0], rax
0x180008bcc  lea     rax, [rbp+var_7C]
0x180008bd0  mov     [rsp+130h+var_D8], rax
0x180008bd5  lea     rax, [rbp+var_68]
0x180008bd9  mov     [rsp+130h+var_E0], rax
0x180008bde  lea     rax, [rbp+var_80]
0x180008be2  mov     [rsp+130h+var_E8], rax
0x180008be7  lea     rax, [rbp+var_30]
0x180008beb  mov     [rsp+130h+var_F0], rax
0x180008bf0  lea     rax, [rbp+var_78]
0x180008bf4  mov     [rsp+130h+var_F8], rax
0x180008bf9  lea     rax, [rbp+var_28]
0x180008bfd  mov     [rbp+var_38], rcx
0x180008c01  mov     ecx, [rbx+44h]
0x180008c04  mov     dword ptr [rbp+arg_0], ecx
0x180008c07  mov     ecx, [rbx+10h]
0x180008c0a  mov     [rsp+130h+var_100], rax
0x180008c0f  lea     rax, [rbp+var_70]
0x180008c13  mov     [rbp+arg_8], ecx
0x180008c16  mov     rcx, [rbx+78h]
0x180008c1a  mov     [rbp+var_40], rcx
0x180008c1e  mov     rcx, [rbx+70h]
0x180008c22  mov     [rsp+130h+var_108], rax
0x180008c27  lea     rax, [rbp+var_20]
0x180008c2b  mov     [rbp+var_48], rcx
0x180008c2f  mov     rcx, r9
0x180008c32  mov     [rsp+130h+var_110], rax
0x180008c37  mov     [rbp+var_20], 1000000h
0x180008c3f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180008c44  lea     rdx, [rbp+arg_0]
0x180008c48  mov     rcx, rdi
0x180008c4b  call    ?LockExclusive@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180008c50  mov     rax, [rdi+110h]
0x180008c57  mov     edx, [rbx+8]
0x180008c5a  lea     rcx, [rax+50h]; this
0x180008c5e  cmp     edx, [rcx+8]
0x180008c61  jz      short loc_180008C76
0x180008c63  cmp     edx, [rax+48h]
0x180008c66  jnz     short loc_180008C6E
0x180008c68  cmp     dword ptr [rax+48h], 0
0x180008c6c  jl      short loc_180008C76
0x180008c6e  mov     rdx, rbx; struct wil::FailureInfo *
0x180008c71  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x180008c76  lea     rcx, [rbp+arg_0]
0x180008c7a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180008c7f  mov     al, 1
0x180008c81  add     rsp, 120h
0x180008c88  pop     rdi
0x180008c89  pop     rbx
0x180008c8a  pop     rbp
0x180008c8b  retn
```
