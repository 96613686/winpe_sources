# winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::IEapServerSchannelUtil>::remove_TlsHandshakeCompleted(winrt::event_token)

- ea: `0x18002b600`
- end: `0x18002b79a`
- name: `?remove_TlsHandshakeCompleted@?$produce@UEapServerSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@UIEapServerSchannelUtil@34567@@impl@winrt@@UEAAHUevent_token@3@@Z`
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
- `0x18002b600`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::IEapServerSchannelUtil>::remove_TlsHandshakeCompleted(
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

  v3 = a1 + 24;
  if ( !a1 )
    v3 = (RTL_SRWLOCK *)208;
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
0x18002b600  push    rbp
0x18002b602  push    rbx
0x18002b603  push    rsi
0x18002b604  push    rdi
0x18002b605  push    r12
0x18002b607  push    r13
0x18002b609  push    r14
0x18002b60b  push    r15
0x18002b60d  mov     rbp, rsp
0x18002b610  sub     rsp, 38h
0x18002b614  mov     r14, rdx
0x18002b617  lea     r15, [rcx+0C0h]
0x18002b61e  mov     eax, 0D0h
0x18002b623  test    rcx, rcx
0x18002b626  cmovz   r15, rax
0x18002b62a  xor     edi, edi
0x18002b62c  mov     [rbp+arg_18], rdi
0x18002b630  lea     rsi, [r15+10h]
0x18002b634  mov     rcx, rsi; SRWLock
0x18002b637  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18002b63c  mov     rcx, [r15]
0x18002b63f  test    rcx, rcx
0x18002b642  jz      loc_18002B77E
0x18002b648  mov     eax, [rcx+4]
0x18002b64b  sub     eax, 1
0x18002b64e  mov     [rbp+arg_8], eax
0x18002b651  mov     ebx, edi
0x18002b653  mov     [rbp+var_18], rbx
0x18002b657  jnz     short loc_18002B665
0x18002b659  cmp     [rcx+8], r14
0x18002b65d  setz    al
0x18002b660  jmp     loc_18002B71F
0x18002b665  mov     [rbp+arg_0], bl
0x18002b668  mov     edx, eax
0x18002b66a  lea     rcx, [rbp+arg_10]
0x18002b66e  call    ??$make_event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@6@I@Z; winrt::Windows::Internal::Eap::Utility::implementation::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>(uint)
0x18002b673  xor     r13d, r13d
0x18002b676  lea     rcx, [rbp+var_18]
0x18002b67a  cmp     rcx, rax
0x18002b67d  jz      short loc_18002B68C
0x18002b67f  mov     rbx, [rax]
0x18002b682  mov     [rax], rdi
0x18002b685  mov     [rbp+var_18], rbx
0x18002b689  mov     r13, rbx
0x18002b68c  cmp     [rbp+arg_10], rdi
0x18002b690  jz      short loc_18002B69B
0x18002b692  lea     rcx, [rbp+arg_10]
0x18002b696  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x18002b69b  add     r13, 8
0x18002b69f  mov     rcx, [r15]
0x18002b6a2  lea     r12, [rcx+8]
0x18002b6a6  mov     eax, [rcx+4]
0x18002b6a9  lea     rcx, [rcx+rax*8]
0x18002b6ad  add     rcx, 8
0x18002b6b1  mov     [rbp+arg_10], rcx
0x18002b6b5  cmp     r12, rcx
0x18002b6b8  jz      loc_18002B758
0x18002b6be  mov     esi, [rbp+arg_8]
0x18002b6c1  mov     al, dil
0x18002b6c4  test    al, al
0x18002b6c6  jnz     short loc_18002B6D5
0x18002b6c8  cmp     r14, [r12]
0x18002b6cc  jnz     short loc_18002B6D5
0x18002b6ce  mov     al, 1
0x18002b6d0  mov     [rbp+arg_0], al
0x18002b6d3  jmp     short loc_18002B712
0x18002b6d5  test    esi, esi
0x18002b6d7  jz      short loc_18002B71B
0x18002b6d9  cmp     r13, r12
0x18002b6dc  jz      short loc_18002B709
0x18002b6de  cmp     [r13+0], rdi
0x18002b6e2  jz      short loc_18002B6EC
0x18002b6e4  mov     rcx, r13
0x18002b6e7  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18002b6ec  mov     rcx, [r12]
0x18002b6f0  mov     [r13+0], rcx
0x18002b6f4  test    rcx, rcx
0x18002b6f7  jz      short loc_18002B705
0x18002b6f9  mov     rax, [rcx]
0x18002b6fc  mov     rax, [rax+8]
0x18002b700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b705  mov     rcx, [rbp+arg_10]
0x18002b709  add     r13, 8
0x18002b70d  dec     esi
0x18002b70f  mov     al, [rbp+arg_0]
0x18002b712  add     r12, 8
0x18002b716  cmp     r12, rcx
0x18002b719  jnz     short loc_18002B6C4
0x18002b71b  lea     rsi, [r15+10h]
0x18002b71f  test    al, al
0x18002b721  jz      short loc_18002B758
0x18002b723  lea     rcx, [r15+8]; SRWLock
0x18002b727  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18002b72c  mov     rdi, [r15]
0x18002b72f  mov     qword ptr [r15], 0
0x18002b736  lea     rax, [rbp+var_18]
0x18002b73a  cmp     r15, rax
0x18002b73d  jz      short loc_18002B74B
0x18002b73f  mov     rax, rbx
0x18002b742  xor     ebx, ebx
0x18002b744  mov     [rbp+var_18], rbx
0x18002b748  mov     [r15], rax
0x18002b74b  mov     [rbp+arg_18], rdi
0x18002b74f  lea     rcx, [r15+8]; SRWLock
0x18002b753  call    ReleaseSRWLockExclusive_0
0x18002b758  test    rbx, rbx
0x18002b75b  jz      short loc_18002B766
0x18002b75d  lea     rcx, [rbp+var_18]
0x18002b761  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x18002b766  mov     rcx, rsi; SRWLock
0x18002b769  call    ReleaseSRWLockExclusive_0
0x18002b76e  test    rdi, rdi
0x18002b771  jz      short loc_18002B787
0x18002b773  lea     rcx, [rbp+arg_18]
0x18002b777  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x18002b77c  jmp     short loc_18002B787
0x18002b77e  mov     rcx, rsi; SRWLock
0x18002b781  call    ReleaseSRWLockExclusive_0
0x18002b786  nop
0x18002b787  xor     eax, eax
0x18002b789  add     rsp, 38h
0x18002b78d  pop     r15
0x18002b78f  pop     r14
0x18002b791  pop     r13
0x18002b793  pop     r12
0x18002b795  pop     rdi
0x18002b796  pop     rsi
0x18002b797  pop     rbx
0x18002b798  pop     rbp
0x18002b799  retn
```
