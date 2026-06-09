# winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::add_TlsDataGenerated(void *,winrt::event_token *)

- ea: `0x180023cd0`
- end: `0x180023e65`
- name: `?add_TlsDataGenerated@?$produce@UEapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@UIEapSchannelUtil@34567@@impl@winrt@@UEAAHPEAXPEAUevent_token@3@@Z`
- size: `405`
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
- `0x180023cd0`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::add_TlsDataGenerated(
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
  __int64 v17; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v18[8]; // [rsp+28h] [rbp-40h] BYREF
  PVOID v19; // [rsp+70h] [rbp+8h] BYREF
  _QWORD *v20; // [rsp+80h] [rbp+18h]
  RTL_SRWLOCK *v21; // [rsp+88h] [rbp+20h]

  v20 = a3;
  v4 = a1 + 1;
  if ( !a1 )
    v4 = (RTL_SRWLOCK *)24;
  v19 = 0;
  v21 = v4 + 2;
  WINRT_IMPL_AcquireSRWLockExclusive(v4 + 2);
  if ( v4->Ptr )
    v5 = *((_DWORD *)v4->Ptr + 1) + 1;
  else
    v5 = 1;
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
  return 0;
}

```

## disassembly

```asm
0x180023cd0  mov     r11, rsp
0x180023cd3  mov     [r11+18h], r8
0x180023cd7  push    rbx
0x180023cd8  push    rsi
0x180023cd9  push    rdi
0x180023cda  push    r12
0x180023cdc  push    r13
0x180023cde  push    r14
0x180023ce0  push    r15
0x180023ce2  sub     rsp, 30h
0x180023ce6  mov     r15, rdx
0x180023ce9  lea     rsi, [rcx+8]
0x180023ced  mov     eax, 18h
0x180023cf2  test    rcx, rcx
0x180023cf5  cmovz   rsi, rax
0x180023cf9  mov     qword ptr [r11+8], 0
0x180023d01  lea     rdi, [rsi+10h]
0x180023d05  mov     [r11+20h], rdi
0x180023d09  mov     rcx, rdi; SRWLock
0x180023d0c  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180023d11  nop
0x180023d12  mov     rdx, [rsi]
0x180023d15  test    rdx, rdx
0x180023d18  jz      short loc_180023D21
0x180023d1a  mov     edx, [rdx+4]
0x180023d1d  inc     edx
0x180023d1f  jmp     short loc_180023D26
0x180023d21  mov     edx, 1
0x180023d26  lea     rcx, [rsp+68h+var_48]
0x180023d2b  call    ??$make_event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@6@I@Z; winrt::Windows::Internal::Eap::Utility::implementation::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>(uint)
0x180023d30  mov     rax, [rsi]
0x180023d33  test    rax, rax
0x180023d36  jz      short loc_180023D89
0x180023d38  mov     r13d, [rax+4]
0x180023d3c  test    r13d, r13d
0x180023d3f  jz      short loc_180023D89
0x180023d41  lea     r12, [rax+8]
0x180023d45  mov     rbx, [rsp+68h+var_48]
0x180023d4a  lea     r14, [rbx+8]
0x180023d4e  cmp     r14, r12
0x180023d51  jz      short loc_180023D79
0x180023d53  cmp     qword ptr [r14], 0
0x180023d57  jz      short loc_180023D61
0x180023d59  mov     rcx, r14
0x180023d5c  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180023d61  mov     rcx, [r12]
0x180023d65  mov     [r14], rcx
0x180023d68  test    rcx, rcx
0x180023d6b  jz      short loc_180023D79
0x180023d6d  mov     rax, [rcx]
0x180023d70  mov     rax, [rax+8]
0x180023d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d79  add     r13d, 0FFFFFFFFh
0x180023d7d  jz      short loc_180023D8E
0x180023d7f  add     r14, 8
0x180023d83  add     r12, 8
0x180023d87  jmp     short loc_180023D4E
0x180023d89  mov     rbx, [rsp+68h+var_48]
0x180023d8e  mov     [rsp+68h+var_40], r15
0x180023d93  test    r15, r15
0x180023d96  jz      short loc_180023DA7
0x180023d98  mov     rax, [r15]
0x180023d9b  mov     rcx, r15
0x180023d9e  mov     rax, [rax+8]
0x180023da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023da7  mov     eax, [rbx+4]
0x180023daa  lea     r14, [rbx+rax*8]
0x180023dae  lea     rax, [rsp+68h+var_40]
0x180023db3  cmp     r14, rax
0x180023db6  jz      short loc_180023DCB
0x180023db8  cmp     qword ptr [r14], 0
0x180023dbc  jz      short loc_180023DC6
0x180023dbe  mov     rcx, r14
0x180023dc1  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180023dc6  mov     [r14], r15
0x180023dc9  jmp     short loc_180023DDA
0x180023dcb  test    r15, r15
0x180023dce  jz      short loc_180023DDA
0x180023dd0  lea     rcx, [rsp+68h+var_40]
0x180023dd5  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180023dda  mov     eax, [rbx+4]
0x180023ddd  mov     r12, [rbx+rax*8]
0x180023de1  lea     rcx, [rsi+8]; SRWLock
0x180023de5  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180023dea  mov     r14, [rsi]
0x180023ded  mov     qword ptr [rsi], 0
0x180023df4  lea     rax, [rsp+68h+var_48]
0x180023df9  cmp     rsi, rax
0x180023dfc  jz      short loc_180023E0B
0x180023dfe  mov     rax, rbx
0x180023e01  xor     ebx, ebx
0x180023e03  mov     [rsp+68h+var_48], rbx
0x180023e08  mov     [rsi], rax
0x180023e0b  mov     [rsp+68h+arg_0], r14
0x180023e10  lea     rcx, [rsi+8]; SRWLock
0x180023e14  call    ReleaseSRWLockExclusive_0
0x180023e19  test    rbx, rbx
0x180023e1c  jz      short loc_180023E29
0x180023e1e  lea     rcx, [rsp+68h+var_48]
0x180023e23  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x180023e28  nop
0x180023e29  mov     rcx, rdi; SRWLock
0x180023e2c  call    ReleaseSRWLockExclusive_0
0x180023e31  nop
0x180023e32  test    r14, r14
0x180023e35  jz      short loc_180023E41
0x180023e37  lea     rcx, [rsp+68h+arg_0]
0x180023e3c  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x180023e41  mov     rax, [rsp+68h+arg_10]
0x180023e49  mov     [rax], r12
0x180023e4c  xor     eax, eax
0x180023e4e  jmp     short loc_180023E54
0x180023e50  mov     eax, dword ptr [rsp+68h+arg_0]
0x180023e54  add     rsp, 30h
0x180023e58  pop     r15
0x180023e5a  pop     r14
0x180023e5c  pop     r13
0x180023e5e  pop     r12
0x180023e60  pop     rdi
0x180023e61  pop     rsi
0x180023e62  pop     rbx
0x180023e63  retn
```
