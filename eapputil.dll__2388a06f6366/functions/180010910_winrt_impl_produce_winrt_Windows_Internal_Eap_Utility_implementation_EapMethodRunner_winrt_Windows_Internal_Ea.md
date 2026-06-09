# winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunner,winrt::Windows::Internal::Eap::Utility::IEapMethodRunner>::remove_AuthenticationCompleted(winrt::event_token)

- ea: `0x180010910`
- end: `0x180010aa7`
- name: `?remove_AuthenticationCompleted@?$produce@UEapMethodRunner@implementation@Utility@Eap@Internal@Windows@winrt@@UIEapMethodRunner@34567@@impl@winrt@@UEAAHUevent_token@3@@Z`
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
- `0x180010910`
- `0x180011030`
- `0x180033010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunner,winrt::Windows::Internal::Eap::Utility::IEapMethodRunner>::remove_AuthenticationCompleted(
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

  v3 = a1 + 5;
  if ( !a1 )
    v3 = (RTL_SRWLOCK *)56;
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
0x180010910  push    rbp
0x180010912  push    rbx
0x180010913  push    rsi
0x180010914  push    rdi
0x180010915  push    r12
0x180010917  push    r13
0x180010919  push    r14
0x18001091b  push    r15
0x18001091d  mov     rbp, rsp
0x180010920  sub     rsp, 38h
0x180010924  mov     r14, rdx
0x180010927  lea     r15, [rcx+28h]
0x18001092b  mov     eax, 38h ; '8'
0x180010930  test    rcx, rcx
0x180010933  cmovz   r15, rax
0x180010937  xor     edi, edi
0x180010939  mov     [rbp+arg_18], rdi
0x18001093d  lea     rsi, [r15+10h]
0x180010941  mov     rcx, rsi; SRWLock
0x180010944  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180010949  mov     rcx, [r15]
0x18001094c  test    rcx, rcx
0x18001094f  jz      loc_180010A8B
0x180010955  mov     eax, [rcx+4]
0x180010958  sub     eax, 1
0x18001095b  mov     [rbp+arg_8], eax
0x18001095e  mov     ebx, edi
0x180010960  mov     [rbp+var_18], rbx
0x180010964  jnz     short loc_180010972
0x180010966  cmp     [rcx+8], r14
0x18001096a  setz    al
0x18001096d  jmp     loc_180010A2C
0x180010972  mov     [rbp+arg_0], bl
0x180010975  mov     edx, eax
0x180010977  lea     rcx, [rbp+arg_10]
0x18001097b  call    ??$make_event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@6@I@Z; winrt::Windows::Internal::Eap::Utility::implementation::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>(uint)
0x180010980  xor     r13d, r13d
0x180010983  lea     rcx, [rbp+var_18]
0x180010987  cmp     rcx, rax
0x18001098a  jz      short loc_180010999
0x18001098c  mov     rbx, [rax]
0x18001098f  mov     [rax], rdi
0x180010992  mov     [rbp+var_18], rbx
0x180010996  mov     r13, rbx
0x180010999  cmp     [rbp+arg_10], rdi
0x18001099d  jz      short loc_1800109A8
0x18001099f  lea     rcx, [rbp+arg_10]
0x1800109a3  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x1800109a8  add     r13, 8
0x1800109ac  mov     rcx, [r15]
0x1800109af  lea     r12, [rcx+8]
0x1800109b3  mov     eax, [rcx+4]
0x1800109b6  lea     rcx, [rcx+rax*8]
0x1800109ba  add     rcx, 8
0x1800109be  mov     [rbp+arg_10], rcx
0x1800109c2  cmp     r12, rcx
0x1800109c5  jz      loc_180010A65
0x1800109cb  mov     esi, [rbp+arg_8]
0x1800109ce  mov     al, dil
0x1800109d1  test    al, al
0x1800109d3  jnz     short loc_1800109E2
0x1800109d5  cmp     r14, [r12]
0x1800109d9  jnz     short loc_1800109E2
0x1800109db  mov     al, 1
0x1800109dd  mov     [rbp+arg_0], al
0x1800109e0  jmp     short loc_180010A1F
0x1800109e2  test    esi, esi
0x1800109e4  jz      short loc_180010A28
0x1800109e6  cmp     r13, r12
0x1800109e9  jz      short loc_180010A16
0x1800109eb  cmp     [r13+0], rdi
0x1800109ef  jz      short loc_1800109F9
0x1800109f1  mov     rcx, r13
0x1800109f4  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800109f9  mov     rcx, [r12]
0x1800109fd  mov     [r13+0], rcx
0x180010a01  test    rcx, rcx
0x180010a04  jz      short loc_180010A12
0x180010a06  mov     rax, [rcx]
0x180010a09  mov     rax, [rax+8]
0x180010a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a12  mov     rcx, [rbp+arg_10]
0x180010a16  add     r13, 8
0x180010a1a  dec     esi
0x180010a1c  mov     al, [rbp+arg_0]
0x180010a1f  add     r12, 8
0x180010a23  cmp     r12, rcx
0x180010a26  jnz     short loc_1800109D1
0x180010a28  lea     rsi, [r15+10h]
0x180010a2c  test    al, al
0x180010a2e  jz      short loc_180010A65
0x180010a30  lea     rcx, [r15+8]; SRWLock
0x180010a34  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180010a39  mov     rdi, [r15]
0x180010a3c  mov     qword ptr [r15], 0
0x180010a43  lea     rax, [rbp+var_18]
0x180010a47  cmp     r15, rax
0x180010a4a  jz      short loc_180010A58
0x180010a4c  mov     rax, rbx
0x180010a4f  xor     ebx, ebx
0x180010a51  mov     [rbp+var_18], rbx
0x180010a55  mov     [r15], rax
0x180010a58  mov     [rbp+arg_18], rdi
0x180010a5c  lea     rcx, [r15+8]; SRWLock
0x180010a60  call    ReleaseSRWLockExclusive_0
0x180010a65  test    rbx, rbx
0x180010a68  jz      short loc_180010A73
0x180010a6a  lea     rcx, [rbp+var_18]
0x180010a6e  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x180010a73  mov     rcx, rsi; SRWLock
0x180010a76  call    ReleaseSRWLockExclusive_0
0x180010a7b  test    rdi, rdi
0x180010a7e  jz      short loc_180010A94
0x180010a80  lea     rcx, [rbp+arg_18]
0x180010a84  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x180010a89  jmp     short loc_180010A94
0x180010a8b  mov     rcx, rsi; SRWLock
0x180010a8e  call    ReleaseSRWLockExclusive_0
0x180010a93  nop
0x180010a94  xor     eax, eax
0x180010a96  add     rsp, 38h
0x180010a9a  pop     r15
0x180010a9c  pop     r14
0x180010a9e  pop     r13
0x180010aa0  pop     r12
0x180010aa2  pop     rdi
0x180010aa3  pop     rsi
0x180010aa4  pop     rbx
0x180010aa5  pop     rbp
0x180010aa6  retn
```
