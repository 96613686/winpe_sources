# winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunner,winrt::Windows::Internal::Eap::Utility::IEapMethodRunner>::remove_UINeeded(winrt::event_token)

- ea: `0x180010c50`
- end: `0x180010de7`
- name: `?remove_UINeeded@?$produce@UEapMethodRunner@implementation@Utility@Eap@Internal@Windows@winrt@@UIEapMethodRunner@34567@@impl@winrt@@UEAAHUevent_token@3@@Z`
- size: `407`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002cf3`
- `0x180002cff`
- `0x1800083ec`
- `0x18000e5b4`
- `0x180010c50`
- `0x180011030`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunner,winrt::Windows::Internal::Eap::Utility::IEapMethodRunner>::remove_UINeeded(
        RTL_SRWLOCK *a1,
        __int64 a2)
{
  RTL_SRWLOCK *v3; // r15
  unsigned int *v4; // rdi
  RTL_SRWLOCK *v5; // rsi
  _DWORD *Ptr; // rcx
  unsigned int v7; // eax
  unsigned int *v8; // rbx
  bool v9; // al
  unsigned int **v10; // rax
  unsigned int *v11; // r13
  __int64 *v12; // r13
  __int64 *v13; // r12
  unsigned int *v14; // rcx
  unsigned int v15; // esi
  __int64 v16; // rcx
  unsigned int *v17; // rax
  unsigned int *v19[3]; // [rsp+20h] [rbp-18h] BYREF
  char v20; // [rsp+80h] [rbp+48h]
  unsigned int v21; // [rsp+88h] [rbp+50h]
  unsigned int *v22; // [rsp+90h] [rbp+58h] BYREF
  unsigned int *v23; // [rsp+98h] [rbp+60h] BYREF

  v3 = a1 + 8;
  if ( !a1 )
    v3 = (RTL_SRWLOCK *)80;
  v4 = 0;
  v23 = 0;
  v5 = v3 + 2;
  WINRT_IMPL_AcquireSRWLockExclusive(v3 + 2);
  Ptr = v3->Ptr;
  if ( !v3->Ptr )
  {
    ReleaseSRWLockExclusive_0(v3 + 2);
    return 0;
  }
  v7 = Ptr[1] - 1;
  v21 = v7;
  v8 = 0;
  v19[0] = 0;
  if ( v7 )
  {
    v20 = 0;
    v10 = (unsigned int **)winrt::Windows::Internal::Eap::Utility::implementation::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>(
                             &v22,
                             v7);
    v11 = 0;
    if ( v19 != v10 )
    {
      v8 = *v10;
      *v10 = 0;
      v19[0] = v8;
      v11 = v8;
    }
    if ( v22 )
      winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(&v22);
    v12 = (__int64 *)(v11 + 2);
    v13 = (__int64 *)((char *)v3->Ptr + 8);
    v14 = (unsigned int *)((char *)v3->Ptr + 8 * *((unsigned int *)v3->Ptr + 1) + 8);
    v22 = v14;
    if ( v13 == (__int64 *)v14 )
      goto LABEL_29;
    v15 = v21;
    v9 = 0;
    do
    {
      if ( v9 || a2 != *v13 )
      {
        if ( !v15 )
          break;
        if ( v12 != v13 )
        {
          if ( *v12 )
            winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v12);
          v16 = *v13;
          *v12 = *v13;
          if ( v16 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
          v14 = v22;
        }
        ++v12;
        --v15;
        v9 = v20;
      }
      else
      {
        v9 = 1;
        v20 = 1;
      }
      ++v13;
    }
    while ( v13 != (__int64 *)v14 );
    v5 = v3 + 2;
  }
  else
  {
    v9 = *((_QWORD *)Ptr + 1) == a2;
  }
  if ( v9 )
  {
    WINRT_IMPL_AcquireSRWLockExclusive(v3 + 1);
    v4 = (unsigned int *)v3->Ptr;
    v3->Ptr = 0;
    if ( v3 != (RTL_SRWLOCK *)v19 )
    {
      v17 = v8;
      v8 = 0;
      v19[0] = 0;
      v3->Ptr = v17;
    }
    v23 = v4;
    ReleaseSRWLockExclusive_0(v3 + 1);
  }
LABEL_29:
  if ( v8 )
    winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(v19);
  ReleaseSRWLockExclusive_0(v5);
  if ( v4 )
    winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(&v23);
  return 0;
}

```

## disassembly

```asm
0x180010c50  push    rbp
0x180010c52  push    rbx
0x180010c53  push    rsi
0x180010c54  push    rdi
0x180010c55  push    r12
0x180010c57  push    r13
0x180010c59  push    r14
0x180010c5b  push    r15
0x180010c5d  mov     rbp, rsp
0x180010c60  sub     rsp, 38h
0x180010c64  mov     r14, rdx
0x180010c67  lea     r15, [rcx+40h]
0x180010c6b  mov     eax, 50h ; 'P'
0x180010c70  test    rcx, rcx
0x180010c73  cmovz   r15, rax
0x180010c77  xor     edi, edi
0x180010c79  mov     [rbp+arg_18], rdi
0x180010c7d  lea     rsi, [r15+10h]
0x180010c81  mov     rcx, rsi; SRWLock
0x180010c84  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180010c89  mov     rcx, [r15]
0x180010c8c  test    rcx, rcx
0x180010c8f  jz      loc_180010DCB
0x180010c95  mov     eax, [rcx+4]
0x180010c98  sub     eax, 1
0x180010c9b  mov     [rbp+arg_8], eax
0x180010c9e  mov     ebx, edi
0x180010ca0  mov     [rbp+var_18], rbx
0x180010ca4  jnz     short loc_180010CB2
0x180010ca6  cmp     [rcx+8], r14
0x180010caa  setz    al
0x180010cad  jmp     loc_180010D6C
0x180010cb2  mov     [rbp+arg_0], bl
0x180010cb5  mov     edx, eax
0x180010cb7  lea     rcx, [rbp+arg_10]
0x180010cbb  call    ??$make_event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@6@I@Z; winrt::Windows::Internal::Eap::Utility::implementation::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>(uint)
0x180010cc0  xor     r13d, r13d
0x180010cc3  lea     rcx, [rbp+var_18]
0x180010cc7  cmp     rcx, rax
0x180010cca  jz      short loc_180010CD9
0x180010ccc  mov     rbx, [rax]
0x180010ccf  mov     [rax], rdi
0x180010cd2  mov     [rbp+var_18], rbx
0x180010cd6  mov     r13, rbx
0x180010cd9  cmp     [rbp+arg_10], rdi
0x180010cdd  jz      short loc_180010CE8
0x180010cdf  lea     rcx, [rbp+arg_10]
0x180010ce3  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x180010ce8  add     r13, 8
0x180010cec  mov     rcx, [r15]
0x180010cef  lea     r12, [rcx+8]
0x180010cf3  mov     eax, [rcx+4]
0x180010cf6  lea     rcx, [rcx+rax*8]
0x180010cfa  add     rcx, 8
0x180010cfe  mov     [rbp+arg_10], rcx
0x180010d02  cmp     r12, rcx
0x180010d05  jz      loc_180010DA5
0x180010d0b  mov     esi, [rbp+arg_8]
0x180010d0e  mov     al, dil
0x180010d11  test    al, al
0x180010d13  jnz     short loc_180010D22
0x180010d15  cmp     r14, [r12]
0x180010d19  jnz     short loc_180010D22
0x180010d1b  mov     al, 1
0x180010d1d  mov     [rbp+arg_0], al
0x180010d20  jmp     short loc_180010D5F
0x180010d22  test    esi, esi
0x180010d24  jz      short loc_180010D68
0x180010d26  cmp     r13, r12
0x180010d29  jz      short loc_180010D56
0x180010d2b  cmp     [r13+0], rdi
0x180010d2f  jz      short loc_180010D39
0x180010d31  mov     rcx, r13
0x180010d34  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180010d39  mov     rcx, [r12]
0x180010d3d  mov     [r13+0], rcx
0x180010d41  test    rcx, rcx
0x180010d44  jz      short loc_180010D52
0x180010d46  mov     rax, [rcx]
0x180010d49  mov     rax, [rax+8]
0x180010d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d52  mov     rcx, [rbp+arg_10]
0x180010d56  add     r13, 8
0x180010d5a  dec     esi
0x180010d5c  mov     al, [rbp+arg_0]
0x180010d5f  add     r12, 8
0x180010d63  cmp     r12, rcx
0x180010d66  jnz     short loc_180010D11
0x180010d68  lea     rsi, [r15+10h]
0x180010d6c  test    al, al
0x180010d6e  jz      short loc_180010DA5
0x180010d70  lea     rcx, [r15+8]; SRWLock
0x180010d74  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180010d79  mov     rdi, [r15]
0x180010d7c  mov     qword ptr [r15], 0
0x180010d83  lea     rax, [rbp+var_18]
0x180010d87  cmp     r15, rax
0x180010d8a  jz      short loc_180010D98
0x180010d8c  mov     rax, rbx
0x180010d8f  xor     ebx, ebx
0x180010d91  mov     [rbp+var_18], rbx
0x180010d95  mov     [r15], rax
0x180010d98  mov     [rbp+arg_18], rdi
0x180010d9c  lea     rcx, [r15+8]; SRWLock
0x180010da0  call    ReleaseSRWLockExclusive_0
0x180010da5  test    rbx, rbx
0x180010da8  jz      short loc_180010DB3
0x180010daa  lea     rcx, [rbp+var_18]
0x180010dae  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x180010db3  mov     rcx, rsi; SRWLock
0x180010db6  call    ReleaseSRWLockExclusive_0
0x180010dbb  test    rdi, rdi
0x180010dbe  jz      short loc_180010DD4
0x180010dc0  lea     rcx, [rbp+arg_18]
0x180010dc4  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x180010dc9  jmp     short loc_180010DD4
0x180010dcb  mov     rcx, rsi; SRWLock
0x180010dce  call    ReleaseSRWLockExclusive_0
0x180010dd3  nop
0x180010dd4  xor     eax, eax
0x180010dd6  add     rsp, 38h
0x180010dda  pop     r15
0x180010ddc  pop     r14
0x180010dde  pop     r13
0x180010de0  pop     r12
0x180010de2  pop     rdi
0x180010de3  pop     rsi
0x180010de4  pop     rbx
0x180010de5  pop     rbp
0x180010de6  retn
```
