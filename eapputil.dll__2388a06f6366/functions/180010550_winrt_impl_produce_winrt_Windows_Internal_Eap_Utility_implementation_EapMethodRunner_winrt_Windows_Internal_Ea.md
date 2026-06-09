# winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunner,winrt::Windows::Internal::Eap::Utility::IEapMethodRunner>::add_UINeeded(void *,winrt::event_token *)

- ea: `0x180010550`
- end: `0x1800106e5`
- name: `?add_UINeeded@?$produce@UEapMethodRunner@implementation@Utility@Eap@Internal@Windows@winrt@@UIEapMethodRunner@34567@@impl@winrt@@UEAAHPEAXPEAUevent_token@3@@Z`
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
- `0x180010550`
- `0x180011030`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunner,winrt::Windows::Internal::Eap::Utility::IEapMethodRunner>::add_UINeeded(
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
  v4 = a1 + 8;
  if ( !a1 )
    v4 = (RTL_SRWLOCK *)80;
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
0x180010550  mov     r11, rsp
0x180010553  mov     [r11+18h], r8
0x180010557  push    rbx
0x180010558  push    rsi
0x180010559  push    rdi
0x18001055a  push    r12
0x18001055c  push    r13
0x18001055e  push    r14
0x180010560  push    r15
0x180010562  sub     rsp, 30h
0x180010566  mov     r15, rdx
0x180010569  lea     rsi, [rcx+40h]
0x18001056d  mov     eax, 50h ; 'P'
0x180010572  test    rcx, rcx
0x180010575  cmovz   rsi, rax
0x180010579  mov     qword ptr [r11+8], 0
0x180010581  lea     rdi, [rsi+10h]
0x180010585  mov     [r11+20h], rdi
0x180010589  mov     rcx, rdi; SRWLock
0x18001058c  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180010591  nop
0x180010592  mov     rdx, [rsi]
0x180010595  test    rdx, rdx
0x180010598  jz      short loc_1800105A1
0x18001059a  mov     edx, [rdx+4]
0x18001059d  inc     edx
0x18001059f  jmp     short loc_1800105A6
0x1800105a1  mov     edx, 1
0x1800105a6  lea     rcx, [rsp+68h+var_48]
0x1800105ab  call    ??$make_event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@6@I@Z; winrt::Windows::Internal::Eap::Utility::implementation::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>(uint)
0x1800105b0  mov     rax, [rsi]
0x1800105b3  test    rax, rax
0x1800105b6  jz      short loc_180010609
0x1800105b8  mov     r13d, [rax+4]
0x1800105bc  test    r13d, r13d
0x1800105bf  jz      short loc_180010609
0x1800105c1  lea     r12, [rax+8]
0x1800105c5  mov     rbx, [rsp+68h+var_48]
0x1800105ca  lea     r14, [rbx+8]
0x1800105ce  cmp     r14, r12
0x1800105d1  jz      short loc_1800105F9
0x1800105d3  cmp     qword ptr [r14], 0
0x1800105d7  jz      short loc_1800105E1
0x1800105d9  mov     rcx, r14
0x1800105dc  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800105e1  mov     rcx, [r12]
0x1800105e5  mov     [r14], rcx
0x1800105e8  test    rcx, rcx
0x1800105eb  jz      short loc_1800105F9
0x1800105ed  mov     rax, [rcx]
0x1800105f0  mov     rax, [rax+8]
0x1800105f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105f9  add     r13d, 0FFFFFFFFh
0x1800105fd  jz      short loc_18001060E
0x1800105ff  add     r14, 8
0x180010603  add     r12, 8
0x180010607  jmp     short loc_1800105CE
0x180010609  mov     rbx, [rsp+68h+var_48]
0x18001060e  mov     [rsp+68h+var_40], r15
0x180010613  test    r15, r15
0x180010616  jz      short loc_180010627
0x180010618  mov     rax, [r15]
0x18001061b  mov     rcx, r15
0x18001061e  mov     rax, [rax+8]
0x180010622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010627  mov     eax, [rbx+4]
0x18001062a  lea     r14, [rbx+rax*8]
0x18001062e  lea     rax, [rsp+68h+var_40]
0x180010633  cmp     r14, rax
0x180010636  jz      short loc_18001064B
0x180010638  cmp     qword ptr [r14], 0
0x18001063c  jz      short loc_180010646
0x18001063e  mov     rcx, r14
0x180010641  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180010646  mov     [r14], r15
0x180010649  jmp     short loc_18001065A
0x18001064b  test    r15, r15
0x18001064e  jz      short loc_18001065A
0x180010650  lea     rcx, [rsp+68h+var_40]
0x180010655  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18001065a  mov     eax, [rbx+4]
0x18001065d  mov     r12, [rbx+rax*8]
0x180010661  lea     rcx, [rsi+8]; SRWLock
0x180010665  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18001066a  mov     r14, [rsi]
0x18001066d  mov     qword ptr [rsi], 0
0x180010674  lea     rax, [rsp+68h+var_48]
0x180010679  cmp     rsi, rax
0x18001067c  jz      short loc_18001068B
0x18001067e  mov     rax, rbx
0x180010681  xor     ebx, ebx
0x180010683  mov     [rsp+68h+var_48], rbx
0x180010688  mov     [rsi], rax
0x18001068b  mov     [rsp+68h+arg_0], r14
0x180010690  lea     rcx, [rsi+8]; SRWLock
0x180010694  call    ReleaseSRWLockExclusive_0
0x180010699  test    rbx, rbx
0x18001069c  jz      short loc_1800106A9
0x18001069e  lea     rcx, [rsp+68h+var_48]
0x1800106a3  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x1800106a8  nop
0x1800106a9  mov     rcx, rdi; SRWLock
0x1800106ac  call    ReleaseSRWLockExclusive_0
0x1800106b1  nop
0x1800106b2  test    r14, r14
0x1800106b5  jz      short loc_1800106C1
0x1800106b7  lea     rcx, [rsp+68h+arg_0]
0x1800106bc  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x1800106c1  mov     rax, [rsp+68h+arg_10]
0x1800106c9  mov     [rax], r12
0x1800106cc  xor     eax, eax
0x1800106ce  jmp     short loc_1800106D4
0x1800106d0  mov     eax, dword ptr [rsp+68h+arg_0]
0x1800106d4  add     rsp, 30h
0x1800106d8  pop     r15
0x1800106da  pop     r14
0x1800106dc  pop     r13
0x1800106de  pop     r12
0x1800106e0  pop     rdi
0x1800106e1  pop     rsi
0x1800106e2  pop     rbx
0x1800106e3  retn
```
