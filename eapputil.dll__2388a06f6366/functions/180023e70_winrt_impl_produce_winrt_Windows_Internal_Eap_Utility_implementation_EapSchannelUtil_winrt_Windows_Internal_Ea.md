# winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::add_TlsHandshakeCompleted(void *,winrt::event_token *)

- ea: `0x180023e70`
- end: `0x180024005`
- name: `?add_TlsHandshakeCompleted@?$produce@UEapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@UIEapSchannelUtil@34567@@impl@winrt@@UEAAHPEAXPEAUevent_token@3@@Z`
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
- `0x180023e70`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::add_TlsHandshakeCompleted(
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
  v4 = a1 + 4;
  if ( !a1 )
    v4 = (RTL_SRWLOCK *)48;
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
0x180023e70  mov     r11, rsp
0x180023e73  mov     [r11+18h], r8
0x180023e77  push    rbx
0x180023e78  push    rsi
0x180023e79  push    rdi
0x180023e7a  push    r12
0x180023e7c  push    r13
0x180023e7e  push    r14
0x180023e80  push    r15
0x180023e82  sub     rsp, 30h
0x180023e86  mov     r15, rdx
0x180023e89  lea     rsi, [rcx+20h]
0x180023e8d  mov     eax, 30h ; '0'
0x180023e92  test    rcx, rcx
0x180023e95  cmovz   rsi, rax
0x180023e99  mov     qword ptr [r11+8], 0
0x180023ea1  lea     rdi, [rsi+10h]
0x180023ea5  mov     [r11+20h], rdi
0x180023ea9  mov     rcx, rdi; SRWLock
0x180023eac  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180023eb1  nop
0x180023eb2  mov     rdx, [rsi]
0x180023eb5  test    rdx, rdx
0x180023eb8  jz      short loc_180023EC1
0x180023eba  mov     edx, [rdx+4]
0x180023ebd  inc     edx
0x180023ebf  jmp     short loc_180023EC6
0x180023ec1  mov     edx, 1
0x180023ec6  lea     rcx, [rsp+68h+var_48]
0x180023ecb  call    ??$make_event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@6@I@Z; winrt::Windows::Internal::Eap::Utility::implementation::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>(uint)
0x180023ed0  mov     rax, [rsi]
0x180023ed3  test    rax, rax
0x180023ed6  jz      short loc_180023F29
0x180023ed8  mov     r13d, [rax+4]
0x180023edc  test    r13d, r13d
0x180023edf  jz      short loc_180023F29
0x180023ee1  lea     r12, [rax+8]
0x180023ee5  mov     rbx, [rsp+68h+var_48]
0x180023eea  lea     r14, [rbx+8]
0x180023eee  cmp     r14, r12
0x180023ef1  jz      short loc_180023F19
0x180023ef3  cmp     qword ptr [r14], 0
0x180023ef7  jz      short loc_180023F01
0x180023ef9  mov     rcx, r14
0x180023efc  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180023f01  mov     rcx, [r12]
0x180023f05  mov     [r14], rcx
0x180023f08  test    rcx, rcx
0x180023f0b  jz      short loc_180023F19
0x180023f0d  mov     rax, [rcx]
0x180023f10  mov     rax, [rax+8]
0x180023f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f19  add     r13d, 0FFFFFFFFh
0x180023f1d  jz      short loc_180023F2E
0x180023f1f  add     r14, 8
0x180023f23  add     r12, 8
0x180023f27  jmp     short loc_180023EEE
0x180023f29  mov     rbx, [rsp+68h+var_48]
0x180023f2e  mov     [rsp+68h+var_40], r15
0x180023f33  test    r15, r15
0x180023f36  jz      short loc_180023F47
0x180023f38  mov     rax, [r15]
0x180023f3b  mov     rcx, r15
0x180023f3e  mov     rax, [rax+8]
0x180023f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f47  mov     eax, [rbx+4]
0x180023f4a  lea     r14, [rbx+rax*8]
0x180023f4e  lea     rax, [rsp+68h+var_40]
0x180023f53  cmp     r14, rax
0x180023f56  jz      short loc_180023F6B
0x180023f58  cmp     qword ptr [r14], 0
0x180023f5c  jz      short loc_180023F66
0x180023f5e  mov     rcx, r14
0x180023f61  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180023f66  mov     [r14], r15
0x180023f69  jmp     short loc_180023F7A
0x180023f6b  test    r15, r15
0x180023f6e  jz      short loc_180023F7A
0x180023f70  lea     rcx, [rsp+68h+var_40]
0x180023f75  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180023f7a  mov     eax, [rbx+4]
0x180023f7d  mov     r12, [rbx+rax*8]
0x180023f81  lea     rcx, [rsi+8]; SRWLock
0x180023f85  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180023f8a  mov     r14, [rsi]
0x180023f8d  mov     qword ptr [rsi], 0
0x180023f94  lea     rax, [rsp+68h+var_48]
0x180023f99  cmp     rsi, rax
0x180023f9c  jz      short loc_180023FAB
0x180023f9e  mov     rax, rbx
0x180023fa1  xor     ebx, ebx
0x180023fa3  mov     [rsp+68h+var_48], rbx
0x180023fa8  mov     [rsi], rax
0x180023fab  mov     [rsp+68h+arg_0], r14
0x180023fb0  lea     rcx, [rsi+8]; SRWLock
0x180023fb4  call    ReleaseSRWLockExclusive_0
0x180023fb9  test    rbx, rbx
0x180023fbc  jz      short loc_180023FC9
0x180023fbe  lea     rcx, [rsp+68h+var_48]
0x180023fc3  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x180023fc8  nop
0x180023fc9  mov     rcx, rdi; SRWLock
0x180023fcc  call    ReleaseSRWLockExclusive_0
0x180023fd1  nop
0x180023fd2  test    r14, r14
0x180023fd5  jz      short loc_180023FE1
0x180023fd7  lea     rcx, [rsp+68h+arg_0]
0x180023fdc  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x180023fe1  mov     rax, [rsp+68h+arg_10]
0x180023fe9  mov     [rax], r12
0x180023fec  xor     eax, eax
0x180023fee  jmp     short loc_180023FF4
0x180023ff0  mov     eax, dword ptr [rsp+68h+arg_0]
0x180023ff4  add     rsp, 30h
0x180023ff8  pop     r15
0x180023ffa  pop     r14
0x180023ffc  pop     r13
0x180023ffe  pop     r12
0x180024000  pop     rdi
0x180024001  pop     rsi
0x180024002  pop     rbx
0x180024003  retn
```
