# wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x180012110`
- end: `0x180012456`
- name: `?NotifyFailure@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@UEAA_NAEBUFailureInfo@2@@Z`
- size: `838`
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
- `0x180008ca0`
- `0x180012110`
- `0x18001b010`

## pseudocode

```c
char __fastcall wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(
        _QWORD *a1,
        int *a2)
{
  __int64 v4; // rcx
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  const unsigned __int16 *v13; // rcx
  __int64 v14; // r8
  _DWORD *v15; // rax
  int v16; // edx
  int v18; // [rsp+B0h] [rbp-80h] BYREF
  int v19; // [rsp+B4h] [rbp-7Ch] BYREF
  const unsigned __int16 *v20; // [rsp+B8h] [rbp-78h] BYREF
  __int64 *v21; // [rsp+C0h] [rbp-70h] BYREF
  __int64 *v22; // [rsp+C8h] [rbp-68h] BYREF
  const unsigned __int16 *v23; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v24; // [rsp+D8h] [rbp-58h] BYREF
  __int64 *v25; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v26; // [rsp+E8h] [rbp-48h] BYREF
  __int64 *v27; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v28; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v29; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v30; // [rsp+108h] [rbp-28h] BYREF
  __int64 v31[4]; // [rsp+110h] [rbp-20h] BYREF
  RTL_SRWLOCK *v32; // [rsp+140h] [rbp+10h] BYREF
  int v33; // [rsp+148h] [rbp+18h] BYREF
  int v34; // [rsp+150h] [rbp+20h] BYREF
  int v35; // [rsp+158h] [rbp+28h] BYREF

  if ( (a2[1] & 2) == 0 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD))(*a1 + 16LL))(a1, (unsigned int)a2[4]) )
    {
      v10 = Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(v4);
      if ( *(_DWORD *)v10 > 2u && (unsigned __int8)tlgKeywordOn(v10, 0x200000000000LL, v11, v10) )
      {
        LODWORD(v32) = a2[17];
        v33 = a2[4];
        v13 = (const unsigned __int16 *)*((_QWORD *)a2 + 6);
        v27 = (__int64 *)*((_QWORD *)a2 + 15);
        v14 = a1[34];
        v26 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
        v34 = a2[26];
        v25 = (__int64 *)*((_QWORD *)a2 + 12);
        v24 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
        v35 = a2[20];
        v23 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
        v19 = a2[8];
        v22 = (__int64 *)*((_QWORD *)a2 + 3);
        v18 = *a2;
        v29 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
        LODWORD(v20) = a2[16];
        v30 = (const unsigned __int16 *)*((_QWORD *)a2 + 7);
        LODWORD(v21) = a2[2];
        v28 = (__int64)v13;
        v31[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v12,
          (__int64)byte_180020E21,
          v14 + 8,
          v12,
          (__int64)v31,
          (__int64)&v21,
          &v30,
          (__int64)&v20,
          &v29,
          (__int64)&v18,
          &v22,
          (__int64)&v19,
          &v23,
          (__int64)&v35,
          &v24,
          &v25,
          (__int64)&v34,
          &v26,
          &v27,
          (__int64)&v33,
          (__int64)&v32,
          (const unsigned __int16 **)&v28);
      }
    }
    else
    {
      v5 = Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(v4);
      if ( *(_DWORD *)v5 > 2u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v6, v5) )
      {
        v8 = (__int64 *)*((_QWORD *)a2 + 15);
        v9 = a1[34];
        v20 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
        LODWORD(v32) = a2[26];
        v22 = (__int64 *)*((_QWORD *)a2 + 12);
        v23 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
        v33 = a2[20];
        v24 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
        v34 = a2[8];
        v25 = (__int64 *)*((_QWORD *)a2 + 3);
        v35 = *a2;
        v26 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
        v18 = a2[16];
        v27 = (__int64 *)*((_QWORD *)a2 + 7);
        v19 = a2[2];
        v21 = v8;
        v28 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v7,
          (__int64)&dword_180020D0C,
          v9 + 8,
          v7,
          (__int64)&v28,
          (__int64)&v19,
          (const unsigned __int16 **)&v27,
          (__int64)&v18,
          &v26,
          (__int64)&v35,
          &v25,
          (__int64)&v34,
          &v24,
          (__int64)&v33,
          &v23,
          &v22,
          (__int64)&v32,
          &v20,
          &v21);
      }
    }
  }
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v32);
  v15 = (_DWORD *)a1[34];
  v16 = a2[2];
  if ( v16 != v15[22] && (v16 != v15[18] || (int)v15[18] >= 0) )
    wil::StoredFailureInfo::SetFailureInfo((wil::StoredFailureInfo *)(v15 + 20), (const struct wil::FailureInfo *)a2);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v32);
  return 1;
}

```

## disassembly

```asm
0x180012110  push    rbp
0x180012112  push    rbx
0x180012113  push    rdi
0x180012114  lea     rbp, [rsp+10h]
0x180012119  sub     rsp, 120h
0x180012120  test    byte ptr [rdx+4], 2
0x180012124  mov     rbx, rdx
0x180012127  mov     rdi, rcx
0x18001212a  jnz     loc_18001240E
0x180012130  mov     rax, [rcx]
0x180012133  mov     edx, [rdx+10h]
0x180012136  mov     rax, [rax+10h]
0x18001213a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001213f  test    al, al
0x180012141  jnz     loc_180012291
0x180012147  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x18001214c  mov     r9, rax
0x18001214f  mov     ecx, [rax]
0x180012151  cmp     ecx, 2
0x180012154  jbe     loc_18001240E
0x18001215a  mov     rdx, 200000000000h
0x180012164  mov     rcx, rax
0x180012167  call    _tlgKeywordOn
0x18001216c  test    al, al
0x18001216e  jz      loc_18001240E
0x180012174  mov     rax, [rbx+70h]
0x180012178  lea     rdx, dword_180020D0C
0x18001217f  mov     rcx, [rbx+78h]
0x180012183  mov     r8, [rdi+110h]
0x18001218a  mov     [rbp+var_78], rax
0x18001218e  add     r8, 8
0x180012192  mov     eax, [rbx+68h]
0x180012195  mov     dword ptr [rbp+arg_0], eax
0x180012198  mov     rax, [rbx+60h]
0x18001219c  mov     [rbp+var_68], rax
0x1800121a0  mov     rax, [rbx+58h]
0x1800121a4  mov     [rbp+var_60], rax
0x1800121a8  mov     eax, [rbx+50h]
0x1800121ab  mov     [rbp+arg_8], eax
0x1800121ae  mov     rax, [rbx+48h]
0x1800121b2  mov     [rbp+var_58], rax
0x1800121b6  mov     eax, [rbx+20h]
0x1800121b9  mov     [rbp+arg_10], eax
0x1800121bc  mov     rax, [rbx+18h]
0x1800121c0  mov     [rbp+var_50], rax
0x1800121c4  mov     eax, [rbx]
0x1800121c6  mov     [rbp+arg_18], eax
0x1800121c9  mov     rax, [rbx+80h]
0x1800121d0  mov     [rbp+var_48], rax
0x1800121d4  mov     eax, [rbx+40h]
0x1800121d7  mov     [rbp+var_80], eax
0x1800121da  mov     rax, [rbx+38h]
0x1800121de  mov     [rbp+var_40], rax
0x1800121e2  mov     eax, [rbx+8]
0x1800121e5  mov     [rbp+var_7C], eax
0x1800121e8  lea     rax, [rbp+var_70]
0x1800121ec  mov     [rsp+130h+var_A0], rax
0x1800121f4  lea     rax, [rbp+var_78]
0x1800121f8  mov     [rsp+130h+var_A8], rax
0x180012200  lea     rax, [rbp+arg_0]
0x180012204  mov     [rsp+130h+var_B0], rax
0x18001220c  lea     rax, [rbp+var_68]
0x180012210  mov     [rsp+130h+var_B8], rax
0x180012215  lea     rax, [rbp+var_60]
0x180012219  mov     [rsp+130h+var_C0], rax
0x18001221e  lea     rax, [rbp+arg_8]
0x180012222  mov     [rsp+130h+var_C8], rax
0x180012227  lea     rax, [rbp+var_58]
0x18001222b  mov     [rsp+130h+var_D0], rax
0x180012230  lea     rax, [rbp+arg_10]
0x180012234  mov     [rsp+130h+var_D8], rax
0x180012239  lea     rax, [rbp+var_50]
0x18001223d  mov     [rsp+130h+var_E0], rax
0x180012242  lea     rax, [rbp+arg_18]
0x180012246  mov     [rsp+130h+var_E8], rax
0x18001224b  lea     rax, [rbp+var_48]
0x18001224f  mov     [rsp+130h+var_F0], rax
0x180012254  lea     rax, [rbp+var_80]
0x180012258  mov     [rsp+130h+var_F8], rax
0x18001225d  lea     rax, [rbp+var_40]
0x180012261  mov     [rsp+130h+var_100], rax
0x180012266  lea     rax, [rbp+var_7C]
0x18001226a  mov     [rsp+130h+var_108], rax
0x18001226f  lea     rax, [rbp+var_38]
0x180012273  mov     [rbp+var_70], rcx
0x180012277  mov     rcx, r9
0x18001227a  mov     [rsp+130h+var_110], rax
0x18001227f  mov     [rbp+var_38], 1000000h
0x180012287  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001228c  jmp     loc_18001240E
0x180012291  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x180012296  mov     r9, rax
0x180012299  mov     ecx, [rax]
0x18001229b  cmp     ecx, 2
0x18001229e  jbe     loc_18001240E
0x1800122a4  mov     rdx, 200000000000h
0x1800122ae  mov     rcx, rax
0x1800122b1  call    _tlgKeywordOn
0x1800122b6  test    al, al
0x1800122b8  jz      loc_18001240E
0x1800122be  mov     eax, [rbx+44h]
0x1800122c1  lea     rdx, byte_180020E21
0x1800122c8  mov     dword ptr [rbp+arg_0], eax
0x1800122cb  mov     eax, [rbx+10h]
0x1800122ce  mov     [rbp+arg_8], eax
0x1800122d1  mov     rax, [rbx+78h]
0x1800122d5  mov     rcx, [rbx+30h]
0x1800122d9  mov     [rbp+var_40], rax
0x1800122dd  mov     rax, [rbx+70h]
0x1800122e1  mov     r8, [rdi+110h]
0x1800122e8  mov     [rbp+var_48], rax
0x1800122ec  add     r8, 8
0x1800122f0  mov     eax, [rbx+68h]
0x1800122f3  mov     [rbp+arg_10], eax
0x1800122f6  mov     rax, [rbx+60h]
0x1800122fa  mov     [rbp+var_50], rax
0x1800122fe  mov     rax, [rbx+58h]
0x180012302  mov     [rbp+var_58], rax
0x180012306  mov     eax, [rbx+50h]
0x180012309  mov     [rbp+arg_18], eax
0x18001230c  mov     rax, [rbx+48h]
0x180012310  mov     [rbp+var_60], rax
0x180012314  mov     eax, [rbx+20h]
0x180012317  mov     [rbp+var_7C], eax
0x18001231a  mov     rax, [rbx+18h]
0x18001231e  mov     [rbp+var_68], rax
0x180012322  mov     eax, [rbx]
0x180012324  mov     [rbp+var_80], eax
0x180012327  mov     rax, [rbx+80h]
0x18001232e  mov     [rbp+var_30], rax
0x180012332  mov     eax, [rbx+40h]
0x180012335  mov     dword ptr [rbp+var_78], eax
0x180012338  mov     rax, [rbx+38h]
0x18001233c  mov     [rbp+var_28], rax
0x180012340  mov     eax, [rbx+8]
0x180012343  mov     dword ptr [rbp+var_70], eax
0x180012346  lea     rax, [rbp+var_38]
0x18001234a  mov     [rsp+130h+var_88], rax
0x180012352  lea     rax, [rbp+arg_0]
0x180012356  mov     [rsp+130h+var_90], rax
0x18001235e  lea     rax, [rbp+arg_8]
0x180012362  mov     [rsp+130h+var_98], rax
0x18001236a  lea     rax, [rbp+var_40]
0x18001236e  mov     [rsp+130h+var_A0], rax
0x180012376  lea     rax, [rbp+var_48]
0x18001237a  mov     [rsp+130h+var_A8], rax
0x180012382  lea     rax, [rbp+arg_10]
0x180012386  mov     [rsp+130h+var_B0], rax
0x18001238e  lea     rax, [rbp+var_50]
0x180012392  mov     [rsp+130h+var_B8], rax
0x180012397  lea     rax, [rbp+var_58]
0x18001239b  mov     [rsp+130h+var_C0], rax
0x1800123a0  lea     rax, [rbp+arg_18]
0x1800123a4  mov     [rsp+130h+var_C8], rax
0x1800123a9  lea     rax, [rbp+var_60]
0x1800123ad  mov     [rsp+130h+var_D0], rax
0x1800123b2  lea     rax, [rbp+var_7C]
0x1800123b6  mov     [rsp+130h+var_D8], rax
0x1800123bb  lea     rax, [rbp+var_68]
0x1800123bf  mov     [rsp+130h+var_E0], rax
0x1800123c4  lea     rax, [rbp+var_80]
0x1800123c8  mov     [rsp+130h+var_E8], rax
0x1800123cd  lea     rax, [rbp+var_30]
0x1800123d1  mov     [rsp+130h+var_F0], rax
0x1800123d6  lea     rax, [rbp+var_78]
0x1800123da  mov     [rsp+130h+var_F8], rax
0x1800123df  lea     rax, [rbp+var_28]
0x1800123e3  mov     [rsp+130h+var_100], rax
0x1800123e8  lea     rax, [rbp+var_70]
0x1800123ec  mov     [rsp+130h+var_108], rax
0x1800123f1  lea     rax, [rbp+var_20]
0x1800123f5  mov     [rbp+var_38], rcx
0x1800123f9  mov     rcx, r9
0x1800123fc  mov     [rsp+130h+var_110], rax
0x180012401  mov     [rbp+var_20], 1000000h
0x180012409  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001240e  lea     rdx, [rbp+arg_0]
0x180012412  mov     rcx, rdi
0x180012415  call    ?LockExclusive@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001241a  mov     rax, [rdi+110h]
0x180012421  mov     edx, [rbx+8]
0x180012424  lea     rcx, [rax+50h]; this
0x180012428  cmp     edx, [rcx+8]
0x18001242b  jz      short loc_180012440
0x18001242d  cmp     edx, [rax+48h]
0x180012430  jnz     short loc_180012438
0x180012432  cmp     dword ptr [rax+48h], 0
0x180012436  jl      short loc_180012440
0x180012438  mov     rdx, rbx; struct wil::FailureInfo *
0x18001243b  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x180012440  lea     rcx, [rbp+arg_0]
0x180012444  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180012449  mov     al, 1
0x18001244b  add     rsp, 120h
0x180012452  pop     rdi
0x180012453  pop     rbx
0x180012454  pop     rbp
0x180012455  retn
```
