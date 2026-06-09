# winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunner,winrt::Windows::Internal::Eap::Utility::IEapMethodRunner>::remove_ResponseGenerated(winrt::event_token)

- ea: `0x180010ab0`
- end: `0x180010c47`
- name: `?remove_ResponseGenerated@?$produce@UEapMethodRunner@implementation@Utility@Eap@Internal@Windows@winrt@@UIEapMethodRunner@34567@@impl@winrt@@UEAAHUevent_token@3@@Z`
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
- `0x180010ab0`
- `0x180011030`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunner,winrt::Windows::Internal::Eap::Utility::IEapMethodRunner>::remove_ResponseGenerated(
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

  v3 = a1 + 2;
  if ( !a1 )
    v3 = (RTL_SRWLOCK *)32;
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
0x180010ab0  push    rbp
0x180010ab2  push    rbx
0x180010ab3  push    rsi
0x180010ab4  push    rdi
0x180010ab5  push    r12
0x180010ab7  push    r13
0x180010ab9  push    r14
0x180010abb  push    r15
0x180010abd  mov     rbp, rsp
0x180010ac0  sub     rsp, 38h
0x180010ac4  mov     r14, rdx
0x180010ac7  lea     r15, [rcx+10h]
0x180010acb  mov     eax, 20h ; ' '
0x180010ad0  test    rcx, rcx
0x180010ad3  cmovz   r15, rax
0x180010ad7  xor     edi, edi
0x180010ad9  mov     [rbp+arg_18], rdi
0x180010add  lea     rsi, [r15+10h]
0x180010ae1  mov     rcx, rsi; SRWLock
0x180010ae4  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180010ae9  mov     rcx, [r15]
0x180010aec  test    rcx, rcx
0x180010aef  jz      loc_180010C2B
0x180010af5  mov     eax, [rcx+4]
0x180010af8  sub     eax, 1
0x180010afb  mov     [rbp+arg_8], eax
0x180010afe  mov     ebx, edi
0x180010b00  mov     [rbp+var_18], rbx
0x180010b04  jnz     short loc_180010B12
0x180010b06  cmp     [rcx+8], r14
0x180010b0a  setz    al
0x180010b0d  jmp     loc_180010BCC
0x180010b12  mov     [rbp+arg_0], bl
0x180010b15  mov     edx, eax
0x180010b17  lea     rcx, [rbp+arg_10]
0x180010b1b  call    ??$make_event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@6@I@Z; winrt::Windows::Internal::Eap::Utility::implementation::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>(uint)
0x180010b20  xor     r13d, r13d
0x180010b23  lea     rcx, [rbp+var_18]
0x180010b27  cmp     rcx, rax
0x180010b2a  jz      short loc_180010B39
0x180010b2c  mov     rbx, [rax]
0x180010b2f  mov     [rax], rdi
0x180010b32  mov     [rbp+var_18], rbx
0x180010b36  mov     r13, rbx
0x180010b39  cmp     [rbp+arg_10], rdi
0x180010b3d  jz      short loc_180010B48
0x180010b3f  lea     rcx, [rbp+arg_10]
0x180010b43  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x180010b48  add     r13, 8
0x180010b4c  mov     rcx, [r15]
0x180010b4f  lea     r12, [rcx+8]
0x180010b53  mov     eax, [rcx+4]
0x180010b56  lea     rcx, [rcx+rax*8]
0x180010b5a  add     rcx, 8
0x180010b5e  mov     [rbp+arg_10], rcx
0x180010b62  cmp     r12, rcx
0x180010b65  jz      loc_180010C05
0x180010b6b  mov     esi, [rbp+arg_8]
0x180010b6e  mov     al, dil
0x180010b71  test    al, al
0x180010b73  jnz     short loc_180010B82
0x180010b75  cmp     r14, [r12]
0x180010b79  jnz     short loc_180010B82
0x180010b7b  mov     al, 1
0x180010b7d  mov     [rbp+arg_0], al
0x180010b80  jmp     short loc_180010BBF
0x180010b82  test    esi, esi
0x180010b84  jz      short loc_180010BC8
0x180010b86  cmp     r13, r12
0x180010b89  jz      short loc_180010BB6
0x180010b8b  cmp     [r13+0], rdi
0x180010b8f  jz      short loc_180010B99
0x180010b91  mov     rcx, r13
0x180010b94  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180010b99  mov     rcx, [r12]
0x180010b9d  mov     [r13+0], rcx
0x180010ba1  test    rcx, rcx
0x180010ba4  jz      short loc_180010BB2
0x180010ba6  mov     rax, [rcx]
0x180010ba9  mov     rax, [rax+8]
0x180010bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bb2  mov     rcx, [rbp+arg_10]
0x180010bb6  add     r13, 8
0x180010bba  dec     esi
0x180010bbc  mov     al, [rbp+arg_0]
0x180010bbf  add     r12, 8
0x180010bc3  cmp     r12, rcx
0x180010bc6  jnz     short loc_180010B71
0x180010bc8  lea     rsi, [r15+10h]
0x180010bcc  test    al, al
0x180010bce  jz      short loc_180010C05
0x180010bd0  lea     rcx, [r15+8]; SRWLock
0x180010bd4  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180010bd9  mov     rdi, [r15]
0x180010bdc  mov     qword ptr [r15], 0
0x180010be3  lea     rax, [rbp+var_18]
0x180010be7  cmp     r15, rax
0x180010bea  jz      short loc_180010BF8
0x180010bec  mov     rax, rbx
0x180010bef  xor     ebx, ebx
0x180010bf1  mov     [rbp+var_18], rbx
0x180010bf5  mov     [r15], rax
0x180010bf8  mov     [rbp+arg_18], rdi
0x180010bfc  lea     rcx, [r15+8]; SRWLock
0x180010c00  call    ReleaseSRWLockExclusive_0
0x180010c05  test    rbx, rbx
0x180010c08  jz      short loc_180010C13
0x180010c0a  lea     rcx, [rbp+var_18]
0x180010c0e  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x180010c13  mov     rcx, rsi; SRWLock
0x180010c16  call    ReleaseSRWLockExclusive_0
0x180010c1b  test    rdi, rdi
0x180010c1e  jz      short loc_180010C34
0x180010c20  lea     rcx, [rbp+arg_18]
0x180010c24  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x180010c29  jmp     short loc_180010C34
0x180010c2b  mov     rcx, rsi; SRWLock
0x180010c2e  call    ReleaseSRWLockExclusive_0
0x180010c33  nop
0x180010c34  xor     eax, eax
0x180010c36  add     rsp, 38h
0x180010c3a  pop     r15
0x180010c3c  pop     r14
0x180010c3e  pop     r13
0x180010c40  pop     r12
0x180010c42  pop     rdi
0x180010c43  pop     rsi
0x180010c44  pop     rbx
0x180010c45  pop     rbp
0x180010c46  retn
```
