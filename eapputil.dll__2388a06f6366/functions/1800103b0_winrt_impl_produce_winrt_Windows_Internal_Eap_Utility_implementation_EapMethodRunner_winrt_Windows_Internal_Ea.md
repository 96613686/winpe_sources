# winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunner,winrt::Windows::Internal::Eap::Utility::IEapMethodRunner>::add_ResponseGenerated(void *,winrt::event_token *)

- ea: `0x1800103b0`
- end: `0x180010545`
- name: `?add_ResponseGenerated@?$produce@UEapMethodRunner@implementation@Utility@Eap@Internal@Windows@winrt@@UIEapMethodRunner@34567@@impl@winrt@@UEAAHPEAXPEAUevent_token@3@@Z`
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
- `0x1800103b0`
- `0x180011030`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunner,winrt::Windows::Internal::Eap::Utility::IEapMethodRunner>::add_ResponseGenerated(
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
  v4 = a1 + 2;
  if ( !a1 )
    v4 = (RTL_SRWLOCK *)32;
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
0x1800103b0  mov     r11, rsp
0x1800103b3  mov     [r11+18h], r8
0x1800103b7  push    rbx
0x1800103b8  push    rsi
0x1800103b9  push    rdi
0x1800103ba  push    r12
0x1800103bc  push    r13
0x1800103be  push    r14
0x1800103c0  push    r15
0x1800103c2  sub     rsp, 30h
0x1800103c6  mov     r15, rdx
0x1800103c9  lea     rsi, [rcx+10h]
0x1800103cd  mov     eax, 20h ; ' '
0x1800103d2  test    rcx, rcx
0x1800103d5  cmovz   rsi, rax
0x1800103d9  mov     qword ptr [r11+8], 0
0x1800103e1  lea     rdi, [rsi+10h]
0x1800103e5  mov     [r11+20h], rdi
0x1800103e9  mov     rcx, rdi; SRWLock
0x1800103ec  call    WINRT_IMPL_AcquireSRWLockExclusive
0x1800103f1  nop
0x1800103f2  mov     rdx, [rsi]
0x1800103f5  test    rdx, rdx
0x1800103f8  jz      short loc_180010401
0x1800103fa  mov     edx, [rdx+4]
0x1800103fd  inc     edx
0x1800103ff  jmp     short loc_180010406
0x180010401  mov     edx, 1
0x180010406  lea     rcx, [rsp+68h+var_48]
0x18001040b  call    ??$make_event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@6@I@Z; winrt::Windows::Internal::Eap::Utility::implementation::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>(uint)
0x180010410  mov     rax, [rsi]
0x180010413  test    rax, rax
0x180010416  jz      short loc_180010469
0x180010418  mov     r13d, [rax+4]
0x18001041c  test    r13d, r13d
0x18001041f  jz      short loc_180010469
0x180010421  lea     r12, [rax+8]
0x180010425  mov     rbx, [rsp+68h+var_48]
0x18001042a  lea     r14, [rbx+8]
0x18001042e  cmp     r14, r12
0x180010431  jz      short loc_180010459
0x180010433  cmp     qword ptr [r14], 0
0x180010437  jz      short loc_180010441
0x180010439  mov     rcx, r14
0x18001043c  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180010441  mov     rcx, [r12]
0x180010445  mov     [r14], rcx
0x180010448  test    rcx, rcx
0x18001044b  jz      short loc_180010459
0x18001044d  mov     rax, [rcx]
0x180010450  mov     rax, [rax+8]
0x180010454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010459  add     r13d, 0FFFFFFFFh
0x18001045d  jz      short loc_18001046E
0x18001045f  add     r14, 8
0x180010463  add     r12, 8
0x180010467  jmp     short loc_18001042E
0x180010469  mov     rbx, [rsp+68h+var_48]
0x18001046e  mov     [rsp+68h+var_40], r15
0x180010473  test    r15, r15
0x180010476  jz      short loc_180010487
0x180010478  mov     rax, [r15]
0x18001047b  mov     rcx, r15
0x18001047e  mov     rax, [rax+8]
0x180010482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010487  mov     eax, [rbx+4]
0x18001048a  lea     r14, [rbx+rax*8]
0x18001048e  lea     rax, [rsp+68h+var_40]
0x180010493  cmp     r14, rax
0x180010496  jz      short loc_1800104AB
0x180010498  cmp     qword ptr [r14], 0
0x18001049c  jz      short loc_1800104A6
0x18001049e  mov     rcx, r14
0x1800104a1  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800104a6  mov     [r14], r15
0x1800104a9  jmp     short loc_1800104BA
0x1800104ab  test    r15, r15
0x1800104ae  jz      short loc_1800104BA
0x1800104b0  lea     rcx, [rsp+68h+var_40]
0x1800104b5  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800104ba  mov     eax, [rbx+4]
0x1800104bd  mov     r12, [rbx+rax*8]
0x1800104c1  lea     rcx, [rsi+8]; SRWLock
0x1800104c5  call    WINRT_IMPL_AcquireSRWLockExclusive
0x1800104ca  mov     r14, [rsi]
0x1800104cd  mov     qword ptr [rsi], 0
0x1800104d4  lea     rax, [rsp+68h+var_48]
0x1800104d9  cmp     rsi, rax
0x1800104dc  jz      short loc_1800104EB
0x1800104de  mov     rax, rbx
0x1800104e1  xor     ebx, ebx
0x1800104e3  mov     [rsp+68h+var_48], rbx
0x1800104e8  mov     [rsi], rax
0x1800104eb  mov     [rsp+68h+arg_0], r14
0x1800104f0  lea     rcx, [rsi+8]; SRWLock
0x1800104f4  call    ReleaseSRWLockExclusive_0
0x1800104f9  test    rbx, rbx
0x1800104fc  jz      short loc_180010509
0x1800104fe  lea     rcx, [rsp+68h+var_48]
0x180010503  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x180010508  nop
0x180010509  mov     rcx, rdi; SRWLock
0x18001050c  call    ReleaseSRWLockExclusive_0
0x180010511  nop
0x180010512  test    r14, r14
0x180010515  jz      short loc_180010521
0x180010517  lea     rcx, [rsp+68h+arg_0]
0x18001051c  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x180010521  mov     rax, [rsp+68h+arg_10]
0x180010529  mov     [rax], r12
0x18001052c  xor     eax, eax
0x18001052e  jmp     short loc_180010534
0x180010530  mov     eax, dword ptr [rsp+68h+arg_0]
0x180010534  add     rsp, 30h
0x180010538  pop     r15
0x18001053a  pop     r14
0x18001053c  pop     r13
0x18001053e  pop     r12
0x180010540  pop     rdi
0x180010541  pop     rsi
0x180010542  pop     rbx
0x180010543  retn
```
