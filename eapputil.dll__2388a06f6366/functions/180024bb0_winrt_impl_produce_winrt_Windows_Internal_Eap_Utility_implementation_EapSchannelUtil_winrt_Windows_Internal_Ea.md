# winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::remove_TlsHandshakeCompleted(winrt::event_token)

- ea: `0x180024bb0`
- end: `0x180024d47`
- name: `?remove_TlsHandshakeCompleted@?$produce@UEapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@UIEapSchannelUtil@34567@@impl@winrt@@UEAAHUevent_token@3@@Z`
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
- `0x180011030`
- `0x180024bb0`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::remove_TlsHandshakeCompleted(
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

  v3 = a1 + 4;
  if ( !a1 )
    v3 = (RTL_SRWLOCK *)48;
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
0x180024bb0  push    rbp
0x180024bb2  push    rbx
0x180024bb3  push    rsi
0x180024bb4  push    rdi
0x180024bb5  push    r12
0x180024bb7  push    r13
0x180024bb9  push    r14
0x180024bbb  push    r15
0x180024bbd  mov     rbp, rsp
0x180024bc0  sub     rsp, 38h
0x180024bc4  mov     r14, rdx
0x180024bc7  lea     r15, [rcx+20h]
0x180024bcb  mov     eax, 30h ; '0'
0x180024bd0  test    rcx, rcx
0x180024bd3  cmovz   r15, rax
0x180024bd7  xor     edi, edi
0x180024bd9  mov     [rbp+arg_18], rdi
0x180024bdd  lea     rsi, [r15+10h]
0x180024be1  mov     rcx, rsi; SRWLock
0x180024be4  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180024be9  mov     rcx, [r15]
0x180024bec  test    rcx, rcx
0x180024bef  jz      loc_180024D2B
0x180024bf5  mov     eax, [rcx+4]
0x180024bf8  sub     eax, 1
0x180024bfb  mov     [rbp+arg_8], eax
0x180024bfe  mov     ebx, edi
0x180024c00  mov     [rbp+var_18], rbx
0x180024c04  jnz     short loc_180024C12
0x180024c06  cmp     [rcx+8], r14
0x180024c0a  setz    al
0x180024c0d  jmp     loc_180024CCC
0x180024c12  mov     [rbp+arg_0], bl
0x180024c15  mov     edx, eax
0x180024c17  lea     rcx, [rbp+arg_10]
0x180024c1b  call    ??$make_event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@6@I@Z; winrt::Windows::Internal::Eap::Utility::implementation::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>(uint)
0x180024c20  xor     r13d, r13d
0x180024c23  lea     rcx, [rbp+var_18]
0x180024c27  cmp     rcx, rax
0x180024c2a  jz      short loc_180024C39
0x180024c2c  mov     rbx, [rax]
0x180024c2f  mov     [rax], rdi
0x180024c32  mov     [rbp+var_18], rbx
0x180024c36  mov     r13, rbx
0x180024c39  cmp     [rbp+arg_10], rdi
0x180024c3d  jz      short loc_180024C48
0x180024c3f  lea     rcx, [rbp+arg_10]
0x180024c43  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x180024c48  add     r13, 8
0x180024c4c  mov     rcx, [r15]
0x180024c4f  lea     r12, [rcx+8]
0x180024c53  mov     eax, [rcx+4]
0x180024c56  lea     rcx, [rcx+rax*8]
0x180024c5a  add     rcx, 8
0x180024c5e  mov     [rbp+arg_10], rcx
0x180024c62  cmp     r12, rcx
0x180024c65  jz      loc_180024D05
0x180024c6b  mov     esi, [rbp+arg_8]
0x180024c6e  mov     al, dil
0x180024c71  test    al, al
0x180024c73  jnz     short loc_180024C82
0x180024c75  cmp     r14, [r12]
0x180024c79  jnz     short loc_180024C82
0x180024c7b  mov     al, 1
0x180024c7d  mov     [rbp+arg_0], al
0x180024c80  jmp     short loc_180024CBF
0x180024c82  test    esi, esi
0x180024c84  jz      short loc_180024CC8
0x180024c86  cmp     r13, r12
0x180024c89  jz      short loc_180024CB6
0x180024c8b  cmp     [r13+0], rdi
0x180024c8f  jz      short loc_180024C99
0x180024c91  mov     rcx, r13
0x180024c94  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180024c99  mov     rcx, [r12]
0x180024c9d  mov     [r13+0], rcx
0x180024ca1  test    rcx, rcx
0x180024ca4  jz      short loc_180024CB2
0x180024ca6  mov     rax, [rcx]
0x180024ca9  mov     rax, [rax+8]
0x180024cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cb2  mov     rcx, [rbp+arg_10]
0x180024cb6  add     r13, 8
0x180024cba  dec     esi
0x180024cbc  mov     al, [rbp+arg_0]
0x180024cbf  add     r12, 8
0x180024cc3  cmp     r12, rcx
0x180024cc6  jnz     short loc_180024C71
0x180024cc8  lea     rsi, [r15+10h]
0x180024ccc  test    al, al
0x180024cce  jz      short loc_180024D05
0x180024cd0  lea     rcx, [r15+8]; SRWLock
0x180024cd4  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180024cd9  mov     rdi, [r15]
0x180024cdc  mov     qword ptr [r15], 0
0x180024ce3  lea     rax, [rbp+var_18]
0x180024ce7  cmp     r15, rax
0x180024cea  jz      short loc_180024CF8
0x180024cec  mov     rax, rbx
0x180024cef  xor     ebx, ebx
0x180024cf1  mov     [rbp+var_18], rbx
0x180024cf5  mov     [r15], rax
0x180024cf8  mov     [rbp+arg_18], rdi
0x180024cfc  lea     rcx, [r15+8]; SRWLock
0x180024d00  call    ReleaseSRWLockExclusive_0
0x180024d05  test    rbx, rbx
0x180024d08  jz      short loc_180024D13
0x180024d0a  lea     rcx, [rbp+var_18]
0x180024d0e  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x180024d13  mov     rcx, rsi; SRWLock
0x180024d16  call    ReleaseSRWLockExclusive_0
0x180024d1b  test    rdi, rdi
0x180024d1e  jz      short loc_180024D34
0x180024d20  lea     rcx, [rbp+arg_18]
0x180024d24  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x180024d29  jmp     short loc_180024D34
0x180024d2b  mov     rcx, rsi; SRWLock
0x180024d2e  call    ReleaseSRWLockExclusive_0
0x180024d33  nop
0x180024d34  xor     eax, eax
0x180024d36  add     rsp, 38h
0x180024d3a  pop     r15
0x180024d3c  pop     r14
0x180024d3e  pop     r13
0x180024d40  pop     r12
0x180024d42  pop     rdi
0x180024d43  pop     rsi
0x180024d44  pop     rbx
0x180024d45  pop     rbp
0x180024d46  retn
```
