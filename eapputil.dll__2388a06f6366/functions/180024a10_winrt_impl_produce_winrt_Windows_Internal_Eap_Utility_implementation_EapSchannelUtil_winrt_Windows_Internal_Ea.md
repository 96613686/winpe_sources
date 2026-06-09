# winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::remove_TlsDataGenerated(winrt::event_token)

- ea: `0x180024a10`
- end: `0x180024ba7`
- name: `?remove_TlsDataGenerated@?$produce@UEapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@UIEapSchannelUtil@34567@@impl@winrt@@UEAAHUevent_token@3@@Z`
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
- `0x180024a10`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::IEapSchannelUtil>::remove_TlsDataGenerated(
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

  v3 = a1 + 1;
  if ( !a1 )
    v3 = (RTL_SRWLOCK *)24;
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
0x180024a10  push    rbp
0x180024a12  push    rbx
0x180024a13  push    rsi
0x180024a14  push    rdi
0x180024a15  push    r12
0x180024a17  push    r13
0x180024a19  push    r14
0x180024a1b  push    r15
0x180024a1d  mov     rbp, rsp
0x180024a20  sub     rsp, 38h
0x180024a24  mov     r14, rdx
0x180024a27  lea     r15, [rcx+8]
0x180024a2b  mov     eax, 18h
0x180024a30  test    rcx, rcx
0x180024a33  cmovz   r15, rax
0x180024a37  xor     edi, edi
0x180024a39  mov     [rbp+arg_18], rdi
0x180024a3d  lea     rsi, [r15+10h]
0x180024a41  mov     rcx, rsi; SRWLock
0x180024a44  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180024a49  mov     rcx, [r15]
0x180024a4c  test    rcx, rcx
0x180024a4f  jz      loc_180024B8B
0x180024a55  mov     eax, [rcx+4]
0x180024a58  sub     eax, 1
0x180024a5b  mov     [rbp+arg_8], eax
0x180024a5e  mov     ebx, edi
0x180024a60  mov     [rbp+var_18], rbx
0x180024a64  jnz     short loc_180024A72
0x180024a66  cmp     [rcx+8], r14
0x180024a6a  setz    al
0x180024a6d  jmp     loc_180024B2C
0x180024a72  mov     [rbp+arg_0], bl
0x180024a75  mov     edx, eax
0x180024a77  lea     rcx, [rbp+arg_10]
0x180024a7b  call    ??$make_event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@6@I@Z; winrt::Windows::Internal::Eap::Utility::implementation::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>(uint)
0x180024a80  xor     r13d, r13d
0x180024a83  lea     rcx, [rbp+var_18]
0x180024a87  cmp     rcx, rax
0x180024a8a  jz      short loc_180024A99
0x180024a8c  mov     rbx, [rax]
0x180024a8f  mov     [rax], rdi
0x180024a92  mov     [rbp+var_18], rbx
0x180024a96  mov     r13, rbx
0x180024a99  cmp     [rbp+arg_10], rdi
0x180024a9d  jz      short loc_180024AA8
0x180024a9f  lea     rcx, [rbp+arg_10]
0x180024aa3  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x180024aa8  add     r13, 8
0x180024aac  mov     rcx, [r15]
0x180024aaf  lea     r12, [rcx+8]
0x180024ab3  mov     eax, [rcx+4]
0x180024ab6  lea     rcx, [rcx+rax*8]
0x180024aba  add     rcx, 8
0x180024abe  mov     [rbp+arg_10], rcx
0x180024ac2  cmp     r12, rcx
0x180024ac5  jz      loc_180024B65
0x180024acb  mov     esi, [rbp+arg_8]
0x180024ace  mov     al, dil
0x180024ad1  test    al, al
0x180024ad3  jnz     short loc_180024AE2
0x180024ad5  cmp     r14, [r12]
0x180024ad9  jnz     short loc_180024AE2
0x180024adb  mov     al, 1
0x180024add  mov     [rbp+arg_0], al
0x180024ae0  jmp     short loc_180024B1F
0x180024ae2  test    esi, esi
0x180024ae4  jz      short loc_180024B28
0x180024ae6  cmp     r13, r12
0x180024ae9  jz      short loc_180024B16
0x180024aeb  cmp     [r13+0], rdi
0x180024aef  jz      short loc_180024AF9
0x180024af1  mov     rcx, r13
0x180024af4  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180024af9  mov     rcx, [r12]
0x180024afd  mov     [r13+0], rcx
0x180024b01  test    rcx, rcx
0x180024b04  jz      short loc_180024B12
0x180024b06  mov     rax, [rcx]
0x180024b09  mov     rax, [rax+8]
0x180024b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b12  mov     rcx, [rbp+arg_10]
0x180024b16  add     r13, 8
0x180024b1a  dec     esi
0x180024b1c  mov     al, [rbp+arg_0]
0x180024b1f  add     r12, 8
0x180024b23  cmp     r12, rcx
0x180024b26  jnz     short loc_180024AD1
0x180024b28  lea     rsi, [r15+10h]
0x180024b2c  test    al, al
0x180024b2e  jz      short loc_180024B65
0x180024b30  lea     rcx, [r15+8]; SRWLock
0x180024b34  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180024b39  mov     rdi, [r15]
0x180024b3c  mov     qword ptr [r15], 0
0x180024b43  lea     rax, [rbp+var_18]
0x180024b47  cmp     r15, rax
0x180024b4a  jz      short loc_180024B58
0x180024b4c  mov     rax, rbx
0x180024b4f  xor     ebx, ebx
0x180024b51  mov     [rbp+var_18], rbx
0x180024b55  mov     [r15], rax
0x180024b58  mov     [rbp+arg_18], rdi
0x180024b5c  lea     rcx, [r15+8]; SRWLock
0x180024b60  call    ReleaseSRWLockExclusive_0
0x180024b65  test    rbx, rbx
0x180024b68  jz      short loc_180024B73
0x180024b6a  lea     rcx, [rbp+var_18]
0x180024b6e  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x180024b73  mov     rcx, rsi; SRWLock
0x180024b76  call    ReleaseSRWLockExclusive_0
0x180024b7b  test    rdi, rdi
0x180024b7e  jz      short loc_180024B94
0x180024b80  lea     rcx, [rbp+arg_18]
0x180024b84  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x180024b89  jmp     short loc_180024B94
0x180024b8b  mov     rcx, rsi; SRWLock
0x180024b8e  call    ReleaseSRWLockExclusive_0
0x180024b93  nop
0x180024b94  xor     eax, eax
0x180024b96  add     rsp, 38h
0x180024b9a  pop     r15
0x180024b9c  pop     r14
0x180024b9e  pop     r13
0x180024ba0  pop     r12
0x180024ba2  pop     rdi
0x180024ba3  pop     rsi
0x180024ba4  pop     rbx
0x180024ba5  pop     rbp
0x180024ba6  retn
```
