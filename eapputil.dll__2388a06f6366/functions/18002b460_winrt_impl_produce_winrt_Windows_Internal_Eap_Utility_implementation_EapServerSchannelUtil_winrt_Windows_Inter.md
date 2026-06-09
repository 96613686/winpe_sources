# winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::IEapServerSchannelUtil>::remove_TlsDataGenerated(winrt::event_token)

- ea: `0x18002b460`
- end: `0x18002b5fa`
- name: `?remove_TlsDataGenerated@?$produce@UEapServerSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@UIEapServerSchannelUtil@34567@@impl@winrt@@UEAAHUevent_token@3@@Z`
- size: `410`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002cf3`
- `0x180002cff`
- `0x1800083ec`
- `0x18000e5b4`
- `0x180011030`
- `0x18002b460`
- `0x180033010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::IEapServerSchannelUtil>::remove_TlsDataGenerated(
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

  v3 = a1 + 21;
  if ( !a1 )
    v3 = (RTL_SRWLOCK *)184;
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
0x18002b460  push    rbp
0x18002b462  push    rbx
0x18002b463  push    rsi
0x18002b464  push    rdi
0x18002b465  push    r12
0x18002b467  push    r13
0x18002b469  push    r14
0x18002b46b  push    r15
0x18002b46d  mov     rbp, rsp
0x18002b470  sub     rsp, 38h
0x18002b474  mov     r14, rdx
0x18002b477  lea     r15, [rcx+0A8h]
0x18002b47e  mov     eax, 0B8h
0x18002b483  test    rcx, rcx
0x18002b486  cmovz   r15, rax
0x18002b48a  xor     edi, edi
0x18002b48c  mov     [rbp+arg_18], rdi
0x18002b490  lea     rsi, [r15+10h]
0x18002b494  mov     rcx, rsi; SRWLock
0x18002b497  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18002b49c  mov     rcx, [r15]
0x18002b49f  test    rcx, rcx
0x18002b4a2  jz      loc_18002B5DE
0x18002b4a8  mov     eax, [rcx+4]
0x18002b4ab  sub     eax, 1
0x18002b4ae  mov     [rbp+arg_8], eax
0x18002b4b1  mov     ebx, edi
0x18002b4b3  mov     [rbp+var_18], rbx
0x18002b4b7  jnz     short loc_18002B4C5
0x18002b4b9  cmp     [rcx+8], r14
0x18002b4bd  setz    al
0x18002b4c0  jmp     loc_18002B57F
0x18002b4c5  mov     [rbp+arg_0], bl
0x18002b4c8  mov     edx, eax
0x18002b4ca  lea     rcx, [rbp+arg_10]
0x18002b4ce  call    ??$make_event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@6@I@Z; winrt::Windows::Internal::Eap::Utility::implementation::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>(uint)
0x18002b4d3  xor     r13d, r13d
0x18002b4d6  lea     rcx, [rbp+var_18]
0x18002b4da  cmp     rcx, rax
0x18002b4dd  jz      short loc_18002B4EC
0x18002b4df  mov     rbx, [rax]
0x18002b4e2  mov     [rax], rdi
0x18002b4e5  mov     [rbp+var_18], rbx
0x18002b4e9  mov     r13, rbx
0x18002b4ec  cmp     [rbp+arg_10], rdi
0x18002b4f0  jz      short loc_18002B4FB
0x18002b4f2  lea     rcx, [rbp+arg_10]
0x18002b4f6  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x18002b4fb  add     r13, 8
0x18002b4ff  mov     rcx, [r15]
0x18002b502  lea     r12, [rcx+8]
0x18002b506  mov     eax, [rcx+4]
0x18002b509  lea     rcx, [rcx+rax*8]
0x18002b50d  add     rcx, 8
0x18002b511  mov     [rbp+arg_10], rcx
0x18002b515  cmp     r12, rcx
0x18002b518  jz      loc_18002B5B8
0x18002b51e  mov     esi, [rbp+arg_8]
0x18002b521  mov     al, dil
0x18002b524  test    al, al
0x18002b526  jnz     short loc_18002B535
0x18002b528  cmp     r14, [r12]
0x18002b52c  jnz     short loc_18002B535
0x18002b52e  mov     al, 1
0x18002b530  mov     [rbp+arg_0], al
0x18002b533  jmp     short loc_18002B572
0x18002b535  test    esi, esi
0x18002b537  jz      short loc_18002B57B
0x18002b539  cmp     r13, r12
0x18002b53c  jz      short loc_18002B569
0x18002b53e  cmp     [r13+0], rdi
0x18002b542  jz      short loc_18002B54C
0x18002b544  mov     rcx, r13
0x18002b547  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18002b54c  mov     rcx, [r12]
0x18002b550  mov     [r13+0], rcx
0x18002b554  test    rcx, rcx
0x18002b557  jz      short loc_18002B565
0x18002b559  mov     rax, [rcx]
0x18002b55c  mov     rax, [rax+8]
0x18002b560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b565  mov     rcx, [rbp+arg_10]
0x18002b569  add     r13, 8
0x18002b56d  dec     esi
0x18002b56f  mov     al, [rbp+arg_0]
0x18002b572  add     r12, 8
0x18002b576  cmp     r12, rcx
0x18002b579  jnz     short loc_18002B524
0x18002b57b  lea     rsi, [r15+10h]
0x18002b57f  test    al, al
0x18002b581  jz      short loc_18002B5B8
0x18002b583  lea     rcx, [r15+8]; SRWLock
0x18002b587  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18002b58c  mov     rdi, [r15]
0x18002b58f  mov     qword ptr [r15], 0
0x18002b596  lea     rax, [rbp+var_18]
0x18002b59a  cmp     r15, rax
0x18002b59d  jz      short loc_18002B5AB
0x18002b59f  mov     rax, rbx
0x18002b5a2  xor     ebx, ebx
0x18002b5a4  mov     [rbp+var_18], rbx
0x18002b5a8  mov     [r15], rax
0x18002b5ab  mov     [rbp+arg_18], rdi
0x18002b5af  lea     rcx, [r15+8]; SRWLock
0x18002b5b3  call    ReleaseSRWLockExclusive_0
0x18002b5b8  test    rbx, rbx
0x18002b5bb  jz      short loc_18002B5C6
0x18002b5bd  lea     rcx, [rbp+var_18]
0x18002b5c1  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x18002b5c6  mov     rcx, rsi; SRWLock
0x18002b5c9  call    ReleaseSRWLockExclusive_0
0x18002b5ce  test    rdi, rdi
0x18002b5d1  jz      short loc_18002B5E7
0x18002b5d3  lea     rcx, [rbp+arg_18]
0x18002b5d7  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x18002b5dc  jmp     short loc_18002B5E7
0x18002b5de  mov     rcx, rsi; SRWLock
0x18002b5e1  call    ReleaseSRWLockExclusive_0
0x18002b5e6  nop
0x18002b5e7  xor     eax, eax
0x18002b5e9  add     rsp, 38h
0x18002b5ed  pop     r15
0x18002b5ef  pop     r14
0x18002b5f1  pop     r13
0x18002b5f3  pop     r12
0x18002b5f5  pop     rdi
0x18002b5f6  pop     rsi
0x18002b5f7  pop     rbx
0x18002b5f8  pop     rbp
0x18002b5f9  retn
```
