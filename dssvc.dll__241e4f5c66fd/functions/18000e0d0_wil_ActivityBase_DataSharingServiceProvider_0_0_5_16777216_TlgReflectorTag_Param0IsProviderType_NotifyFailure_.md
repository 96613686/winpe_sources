# wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x18000e0d0`
- end: `0x18000e29d`
- name: `?NotifyFailure@?$ActivityBase@VDataSharingServiceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@UEAA_NAEBUFailureInfo@2@@Z`
- size: `461`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x180001390`
- `0x180005c54`
- `0x180007e80`
- `0x18000df98`
- `0x18000e0d0`
- `0x18000e6c0`

## pseudocode

```c
char __fastcall wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(
        __int64 a1,
        int *a2)
{
  const struct _tlgProvider_t *v4; // r9
  const unsigned __int16 *v5; // rcx
  __int64 v6; // r8
  _DWORD *v7; // rax
  int v8; // edx
  int v10; // [rsp+B0h] [rbp-80h] BYREF
  int v11; // [rsp+B4h] [rbp-7Ch] BYREF
  int v12; // [rsp+B8h] [rbp-78h] BYREF
  int v13; // [rsp+BCh] [rbp-74h] BYREF
  const unsigned __int16 *v14; // [rsp+C0h] [rbp-70h] BYREF
  const WCHAR *v15; // [rsp+C8h] [rbp-68h] BYREF
  const unsigned __int16 *v16; // [rsp+D0h] [rbp-60h] BYREF
  const WCHAR *v17; // [rsp+D8h] [rbp-58h] BYREF
  const unsigned __int16 *v18; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v19; // [rsp+E8h] [rbp-48h] BYREF
  const WCHAR *v20; // [rsp+F0h] [rbp-40h] BYREF
  const unsigned __int16 *v21; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v22; // [rsp+100h] [rbp-30h] BYREF
  __int64 v23[3]; // [rsp+108h] [rbp-28h] BYREF
  RTL_SRWLOCK *v24; // [rsp+130h] [rbp+0h] BYREF
  int v25; // [rsp+138h] [rbp+8h] BYREF
  int v26; // [rsp+140h] [rbp+10h] BYREF
  int v27; // [rsp+148h] [rbp+18h] BYREF

  if ( (a2[1] & 2) == 0 )
  {
    v4 = DataSharingServiceProvider::Provider(a1);
    if ( *(_DWORD *)v4 > 2u )
    {
      v5 = (const unsigned __int16 *)*((_QWORD *)a2 + 6);
      v6 = *(_QWORD *)(a1 + 272);
      v26 = a2[26];
      v17 = (const WCHAR *)*((_QWORD *)a2 + 12);
      v18 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
      v27 = a2[20];
      v19 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
      v10 = a2[8];
      v20 = (const WCHAR *)*((_QWORD *)a2 + 3);
      v11 = *a2;
      v21 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
      v12 = a2[16];
      v22 = (const unsigned __int16 *)*((_QWORD *)a2 + 7);
      v13 = a2[2];
      v14 = v5;
      LODWORD(v24) = a2[17];
      v25 = a2[4];
      v15 = (const WCHAR *)*((_QWORD *)a2 + 15);
      v16 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
      v23[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v4,
        (__int64)word_18002595A,
        v6 + 8,
        (__int64)v4,
        (__int64)v23,
        (__int64)&v13,
        &v22,
        (__int64)&v12,
        &v21,
        (__int64)&v11,
        &v20,
        (__int64)&v10,
        &v19,
        (__int64)&v27,
        &v18,
        &v17,
        (__int64)&v26,
        &v16,
        &v15,
        (__int64)&v25,
        (__int64)&v24,
        &v14);
    }
  }
  wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v24);
  v7 = *(_DWORD **)(a1 + 272);
  v8 = a2[2];
  if ( v8 != v7[22] && (v8 != v7[18] || (int)v7[18] >= 0) )
    wil::StoredFailureInfo::SetFailureInfo((wil::StoredFailureInfo *)(v7 + 20), (const struct wil::FailureInfo *)a2);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v24);
  return 1;
}

```

## disassembly

```asm
0x18000e0d0  push    rbp
0x18000e0d2  push    rbx
0x18000e0d3  push    rdi
0x18000e0d4  lea     rbp, [rsp+20h]
0x18000e0d9  sub     rsp, 110h
0x18000e0e0  test    byte ptr [rdx+4], 2
0x18000e0e4  mov     rbx, rdx
0x18000e0e7  mov     rdi, rcx
0x18000e0ea  jnz     loc_18000E255
0x18000e0f0  call    ?Provider@DataSharingServiceProvider@@SAPEBU_tlgProvider_t@@XZ; DataSharingServiceProvider::Provider(void)
0x18000e0f5  mov     r9, rax
0x18000e0f8  mov     r8d, [rax]
0x18000e0fb  cmp     r8d, 2
0x18000e0ff  jbe     loc_18000E255
0x18000e105  mov     eax, [rbx+68h]
0x18000e108  lea     rdx, word_18002595A
0x18000e10f  mov     rcx, [rbx+30h]
0x18000e113  mov     r8, [rdi+110h]
0x18000e11a  mov     [rbp-10h+arg_10], eax
0x18000e11d  add     r8, 8
0x18000e121  mov     rax, [rbx+60h]
0x18000e125  mov     [rbp-10h+var_48], rax
0x18000e129  mov     rax, [rbx+58h]
0x18000e12d  mov     [rbp-10h+var_40], rax
0x18000e131  mov     eax, [rbx+50h]
0x18000e134  mov     [rbp-10h+arg_18], eax
0x18000e137  mov     rax, [rbx+48h]
0x18000e13b  mov     [rbp-10h+var_38], rax
0x18000e13f  mov     eax, [rbx+20h]
0x18000e142  mov     [rbp-10h+var_70], eax
0x18000e145  mov     rax, [rbx+18h]
0x18000e149  mov     [rbp-10h+var_30], rax
0x18000e14d  mov     eax, [rbx]
0x18000e14f  mov     [rbp-10h+var_6C], eax
0x18000e152  mov     rax, [rbx+80h]
0x18000e159  mov     [rbp-10h+var_28], rax
0x18000e15d  mov     eax, [rbx+40h]
0x18000e160  mov     [rbp-10h+var_68], eax
0x18000e163  mov     rax, [rbx+38h]
0x18000e167  mov     [rbp-10h+var_20], rax
0x18000e16b  mov     eax, [rbx+8]
0x18000e16e  mov     [rbp-10h+var_64], eax
0x18000e171  lea     rax, [rbp-10h+var_60]
0x18000e175  mov     [rsp+120h+var_78], rax
0x18000e17d  lea     rax, [rbp-10h+arg_0]
0x18000e181  mov     [rsp+120h+var_80], rax
0x18000e189  lea     rax, [rbp-10h+arg_8]
0x18000e18d  mov     [rsp+120h+var_88], rax
0x18000e195  lea     rax, [rbp-10h+var_58]
0x18000e199  mov     [rsp+120h+var_90], rax
0x18000e1a1  lea     rax, [rbp-10h+var_50]
0x18000e1a5  mov     [rsp+120h+var_98], rax
0x18000e1ad  lea     rax, [rbp-10h+arg_10]
0x18000e1b1  mov     [rsp+120h+var_A0], rax
0x18000e1b9  lea     rax, [rbp-10h+var_48]
0x18000e1bd  mov     [rsp+120h+var_A8], rax
0x18000e1c2  lea     rax, [rbp-10h+var_40]
0x18000e1c6  mov     [rsp+120h+var_B0], rax
0x18000e1cb  lea     rax, [rbp-10h+arg_18]
0x18000e1cf  mov     [rsp+120h+var_B8], rax
0x18000e1d4  lea     rax, [rbp-10h+var_38]
0x18000e1d8  mov     [rsp+120h+var_C0], rax
0x18000e1dd  lea     rax, [rbp-10h+var_70]
0x18000e1e1  mov     [rsp+120h+var_C8], rax
0x18000e1e6  lea     rax, [rbp-10h+var_30]
0x18000e1ea  mov     [rsp+120h+var_D0], rax
0x18000e1ef  lea     rax, [rbp-10h+var_6C]
0x18000e1f3  mov     [rsp+120h+var_D8], rax
0x18000e1f8  lea     rax, [rbp-10h+var_28]
0x18000e1fc  mov     [rsp+120h+var_E0], rax
0x18000e201  lea     rax, [rbp-10h+var_68]
0x18000e205  mov     [rsp+120h+var_E8], rax
0x18000e20a  lea     rax, [rbp-10h+var_20]
0x18000e20e  mov     [rbp-10h+var_60], rcx
0x18000e212  mov     ecx, [rbx+44h]
0x18000e215  mov     dword ptr [rbp-10h+arg_0], ecx
0x18000e218  mov     ecx, [rbx+10h]
0x18000e21b  mov     [rsp+120h+var_F0], rax
0x18000e220  lea     rax, [rbp-10h+var_64]
0x18000e224  mov     [rbp-10h+arg_8], ecx
0x18000e227  mov     rcx, [rbx+78h]
0x18000e22b  mov     [rbp-10h+var_58], rcx
0x18000e22f  mov     rcx, [rbx+70h]
0x18000e233  mov     [rsp+120h+var_F8], rax
0x18000e238  lea     rax, [rbp-10h+var_18]
0x18000e23c  mov     [rbp-10h+var_50], rcx
0x18000e240  mov     rcx, r9
0x18000e243  mov     [rsp+120h+var_100], rax
0x18000e248  mov     [rbp-10h+var_18], 1000000h
0x18000e250  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000e255  lea     rdx, [rbp-10h+arg_0]
0x18000e259  mov     rcx, rdi
0x18000e25c  call    ?LockExclusive@?$ActivityBase@VDataSharingServiceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000e261  mov     rax, [rdi+110h]
0x18000e268  mov     edx, [rbx+8]
0x18000e26b  lea     rcx, [rax+50h]; this
0x18000e26f  cmp     edx, [rcx+8]
0x18000e272  jz      short loc_18000E287
0x18000e274  cmp     edx, [rax+48h]
0x18000e277  jnz     short loc_18000E27F
0x18000e279  cmp     dword ptr [rax+48h], 0
0x18000e27d  jl      short loc_18000E287
0x18000e27f  mov     rdx, rbx; struct wil::FailureInfo *
0x18000e282  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x18000e287  lea     rcx, [rbp-10h+arg_0]
0x18000e28b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000e290  mov     al, 1
0x18000e292  add     rsp, 110h
0x18000e299  pop     rdi
0x18000e29a  pop     rbx
0x18000e29b  pop     rbp
0x18000e29c  retn
```
