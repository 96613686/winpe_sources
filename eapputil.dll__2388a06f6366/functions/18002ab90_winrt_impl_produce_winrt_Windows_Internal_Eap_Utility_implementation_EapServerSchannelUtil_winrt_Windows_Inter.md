# winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::IEapServerSchannelUtil>::add_TlsDataGenerated(void *,winrt::event_token *)

- ea: `0x18002ab90`
- end: `0x18002ad28`
- name: `?add_TlsDataGenerated@?$produce@UEapServerSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@UIEapServerSchannelUtil@34567@@impl@winrt@@UEAAHPEAXPEAUevent_token@3@@Z`
- size: `408`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002cf3`
- `0x180002cff`
- `0x1800083ec`
- `0x18000e5b4`
- `0x180011030`
- `0x18002ab90`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::IEapServerSchannelUtil>::add_TlsDataGenerated(
        RTL_SRWLOCK *a1,
        __int64 a2,
        _QWORD *a3)
{
  RTL_SRWLOCK *v4; // rsi
  unsigned int v5; // edx
  char *Ptr; // rax
  int v7; // r13d
  __int64 *v8; // r12
  unsigned int *v9; // rbx
  __int64 *i; // r14
  __int64 v11; // rcx
  unsigned int *v12; // r14
  __int64 v13; // r12
  PVOID v14; // r14
  unsigned int *v15; // rax
  __int64 result; // rax
  __int64 v17; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v18[8]; // [rsp+28h] [rbp-40h] BYREF
  PVOID v19; // [rsp+70h] [rbp+8h] BYREF
  _QWORD *v20; // [rsp+80h] [rbp+18h]
  RTL_SRWLOCK *v21; // [rsp+88h] [rbp+20h]

  v20 = a3;
  v4 = a1 + 21;
  if ( !a1 )
    v4 = (RTL_SRWLOCK *)184;
  v19 = 0;
  v21 = v4 + 2;
  WINRT_IMPL_AcquireSRWLockExclusive(v4 + 2);
  if ( v4->Ptr )
    v5 = *((_DWORD *)v4->Ptr + 1) + 1;
  else
    v5 = 1;
  try
  {
    winrt::Windows::Internal::Eap::Utility::implementation::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>(
      &v17,
      v5);
    Ptr = (char *)v4->Ptr;
    if ( v4->Ptr && (v7 = *((_DWORD *)Ptr + 1)) != 0 )
    {
      v8 = (__int64 *)(Ptr + 8);
      v9 = (unsigned int *)v17;
      for ( i = (__int64 *)(v17 + 8); ; ++i )
      {
        if ( i != v8 )
        {
          if ( *i )
            winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(i);
          v11 = *v8;
          *i = *v8;
          if ( v11 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
        }
        if ( !--v7 )
          break;
        ++v8;
      }
    }
    else
    {
      v9 = (unsigned int *)v17;
    }
    v18[0] = a2;
    if ( a2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    v12 = &v9[2 * v9[1]];
    if ( v12 == (unsigned int *)v18 )
    {
      if ( a2 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v18);
    }
    else
    {
      if ( *(_QWORD *)v12 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v9[2 * v9[1]]);
      *(_QWORD *)v12 = a2;
    }
    v13 = *(_QWORD *)&v9[2 * v9[1]];
    WINRT_IMPL_AcquireSRWLockExclusive(v4 + 1);
    v14 = v4->Ptr;
    v4->Ptr = 0;
    if ( v4 != (RTL_SRWLOCK *)&v17 )
    {
      v15 = v9;
      v9 = 0;
      v17 = 0;
      v4->Ptr = v15;
    }
    v19 = v14;
    ReleaseSRWLockExclusive_0(v4 + 1);
    if ( v9 )
      winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(&v17);
    ReleaseSRWLockExclusive_0(v4 + 2);
    if ( v14 )
      winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(&v19);
    *v20 = v13;
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v19) = *(_DWORD *)winrt::to_hresult(&v19);
    return (unsigned int)v19;
  }
  return result;
}

```

## disassembly

```asm
0x18002ab90  mov     r11, rsp
0x18002ab93  mov     [r11+18h], r8
0x18002ab97  push    rbx
0x18002ab98  push    rsi
0x18002ab99  push    rdi
0x18002ab9a  push    r12
0x18002ab9c  push    r13
0x18002ab9e  push    r14
0x18002aba0  push    r15
0x18002aba2  sub     rsp, 30h
0x18002aba6  mov     r15, rdx
0x18002aba9  lea     rsi, [rcx+0A8h]
0x18002abb0  mov     eax, 0B8h
0x18002abb5  test    rcx, rcx
0x18002abb8  cmovz   rsi, rax
0x18002abbc  mov     qword ptr [r11+8], 0
0x18002abc4  lea     rdi, [rsi+10h]
0x18002abc8  mov     [r11+20h], rdi
0x18002abcc  mov     rcx, rdi; SRWLock
0x18002abcf  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18002abd4  nop
0x18002abd5  mov     rdx, [rsi]
0x18002abd8  test    rdx, rdx
0x18002abdb  jz      short loc_18002ABE4
0x18002abdd  mov     edx, [rdx+4]
0x18002abe0  inc     edx
0x18002abe2  jmp     short loc_18002ABE9
0x18002abe4  mov     edx, 1
0x18002abe9  lea     rcx, [rsp+68h+var_48]
0x18002abee  call    ??$make_event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@6@I@Z; winrt::Windows::Internal::Eap::Utility::implementation::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>(uint)
0x18002abf3  mov     rax, [rsi]
0x18002abf6  test    rax, rax
0x18002abf9  jz      short loc_18002AC4C
0x18002abfb  mov     r13d, [rax+4]
0x18002abff  test    r13d, r13d
0x18002ac02  jz      short loc_18002AC4C
0x18002ac04  lea     r12, [rax+8]
0x18002ac08  mov     rbx, [rsp+68h+var_48]
0x18002ac0d  lea     r14, [rbx+8]
0x18002ac11  cmp     r14, r12
0x18002ac14  jz      short loc_18002AC3C
0x18002ac16  cmp     qword ptr [r14], 0
0x18002ac1a  jz      short loc_18002AC24
0x18002ac1c  mov     rcx, r14
0x18002ac1f  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18002ac24  mov     rcx, [r12]
0x18002ac28  mov     [r14], rcx
0x18002ac2b  test    rcx, rcx
0x18002ac2e  jz      short loc_18002AC3C
0x18002ac30  mov     rax, [rcx]
0x18002ac33  mov     rax, [rax+8]
0x18002ac37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac3c  add     r13d, 0FFFFFFFFh
0x18002ac40  jz      short loc_18002AC51
0x18002ac42  add     r14, 8
0x18002ac46  add     r12, 8
0x18002ac4a  jmp     short loc_18002AC11
0x18002ac4c  mov     rbx, [rsp+68h+var_48]
0x18002ac51  mov     [rsp+68h+var_40], r15
0x18002ac56  test    r15, r15
0x18002ac59  jz      short loc_18002AC6A
0x18002ac5b  mov     rax, [r15]
0x18002ac5e  mov     rcx, r15
0x18002ac61  mov     rax, [rax+8]
0x18002ac65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac6a  mov     eax, [rbx+4]
0x18002ac6d  lea     r14, [rbx+rax*8]
0x18002ac71  lea     rax, [rsp+68h+var_40]
0x18002ac76  cmp     r14, rax
0x18002ac79  jz      short loc_18002AC8E
0x18002ac7b  cmp     qword ptr [r14], 0
0x18002ac7f  jz      short loc_18002AC89
0x18002ac81  mov     rcx, r14
0x18002ac84  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18002ac89  mov     [r14], r15
0x18002ac8c  jmp     short loc_18002AC9D
0x18002ac8e  test    r15, r15
0x18002ac91  jz      short loc_18002AC9D
0x18002ac93  lea     rcx, [rsp+68h+var_40]
0x18002ac98  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18002ac9d  mov     eax, [rbx+4]
0x18002aca0  mov     r12, [rbx+rax*8]
0x18002aca4  lea     rcx, [rsi+8]; SRWLock
0x18002aca8  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18002acad  mov     r14, [rsi]
0x18002acb0  mov     qword ptr [rsi], 0
0x18002acb7  lea     rax, [rsp+68h+var_48]
0x18002acbc  cmp     rsi, rax
0x18002acbf  jz      short loc_18002ACCE
0x18002acc1  mov     rax, rbx
0x18002acc4  xor     ebx, ebx
0x18002acc6  mov     [rsp+68h+var_48], rbx
0x18002accb  mov     [rsi], rax
0x18002acce  mov     [rsp+68h+arg_0], r14
0x18002acd3  lea     rcx, [rsi+8]; SRWLock
0x18002acd7  call    ReleaseSRWLockExclusive_0
0x18002acdc  test    rbx, rbx
0x18002acdf  jz      short loc_18002ACEC
0x18002ace1  lea     rcx, [rsp+68h+var_48]
0x18002ace6  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x18002aceb  nop
0x18002acec  mov     rcx, rdi; SRWLock
0x18002acef  call    ReleaseSRWLockExclusive_0
0x18002acf4  nop
0x18002acf5  test    r14, r14
0x18002acf8  jz      short loc_18002AD04
0x18002acfa  lea     rcx, [rsp+68h+arg_0]
0x18002acff  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x18002ad04  mov     rax, [rsp+68h+arg_10]
0x18002ad0c  mov     [rax], r12
0x18002ad0f  xor     eax, eax
0x18002ad11  jmp     short loc_18002AD17
0x18002ad13  mov     eax, dword ptr [rsp+68h+arg_0]
0x18002ad17  add     rsp, 30h
0x18002ad1b  pop     r15
0x18002ad1d  pop     r14
0x18002ad1f  pop     r13
0x18002ad21  pop     r12
0x18002ad23  pop     rdi
0x18002ad24  pop     rsi
0x18002ad25  pop     rbx
0x18002ad26  retn
```
