# winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunner,winrt::Windows::Internal::Eap::Utility::IEapMethodRunner>::add_AuthenticationCompleted(void *,winrt::event_token *)

- ea: `0x180010210`
- end: `0x1800103a5`
- name: `?add_AuthenticationCompleted@?$produce@UEapMethodRunner@implementation@Utility@Eap@Internal@Windows@winrt@@UIEapMethodRunner@34567@@impl@winrt@@UEAAHPEAXPEAUevent_token@3@@Z`
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
- `0x180010210`
- `0x180011030`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunner,winrt::Windows::Internal::Eap::Utility::IEapMethodRunner>::add_AuthenticationCompleted(
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
  __int64 result; // rax
  __int64 v17; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v18[8]; // [rsp+28h] [rbp-40h] BYREF
  PVOID v19; // [rsp+70h] [rbp+8h] BYREF
  _QWORD *v20; // [rsp+80h] [rbp+18h]
  RTL_SRWLOCK *v21; // [rsp+88h] [rbp+20h]

  v20 = a3;
  v4 = a1 + 5;
  if ( !a1 )
    v4 = (RTL_SRWLOCK *)56;
  v19 = 0;
  v21 = v4 + 2;
  WINRT_IMPL_AcquireSRWLockExclusive(v4 + 2);
  if ( v4->Ptr )
    v5 = *((_DWORD *)v4->Ptr + 1) + 1;
  else
    v5 = 1;
  try
  {
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
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v19) = *(_DWORD *)winrt::to_hresult(&v19);
    return (unsigned int)v19;
  }
  return result;
}

```

## disassembly

```asm
0x180010210  mov     r11, rsp
0x180010213  mov     [r11+18h], r8
0x180010217  push    rbx
0x180010218  push    rsi
0x180010219  push    rdi
0x18001021a  push    r12
0x18001021c  push    r13
0x18001021e  push    r14
0x180010220  push    r15
0x180010222  sub     rsp, 30h
0x180010226  mov     r15, rdx
0x180010229  lea     rsi, [rcx+28h]
0x18001022d  mov     eax, 38h ; '8'
0x180010232  test    rcx, rcx
0x180010235  cmovz   rsi, rax
0x180010239  mov     qword ptr [r11+8], 0
0x180010241  lea     rdi, [rsi+10h]
0x180010245  mov     [r11+20h], rdi
0x180010249  mov     rcx, rdi; SRWLock
0x18001024c  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180010251  nop
0x180010252  mov     rdx, [rsi]
0x180010255  test    rdx, rdx
0x180010258  jz      short loc_180010261
0x18001025a  mov     edx, [rdx+4]
0x18001025d  inc     edx
0x18001025f  jmp     short loc_180010266
0x180010261  mov     edx, 1
0x180010266  lea     rcx, [rsp+68h+var_48]
0x18001026b  call    ??$make_event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@6@I@Z; winrt::Windows::Internal::Eap::Utility::implementation::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>(uint)
0x180010270  mov     rax, [rsi]
0x180010273  test    rax, rax
0x180010276  jz      short loc_1800102C9
0x180010278  mov     r13d, [rax+4]
0x18001027c  test    r13d, r13d
0x18001027f  jz      short loc_1800102C9
0x180010281  lea     r12, [rax+8]
0x180010285  mov     rbx, [rsp+68h+var_48]
0x18001028a  lea     r14, [rbx+8]
0x18001028e  cmp     r14, r12
0x180010291  jz      short loc_1800102B9
0x180010293  cmp     qword ptr [r14], 0
0x180010297  jz      short loc_1800102A1
0x180010299  mov     rcx, r14
0x18001029c  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800102a1  mov     rcx, [r12]
0x1800102a5  mov     [r14], rcx
0x1800102a8  test    rcx, rcx
0x1800102ab  jz      short loc_1800102B9
0x1800102ad  mov     rax, [rcx]
0x1800102b0  mov     rax, [rax+8]
0x1800102b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102b9  add     r13d, 0FFFFFFFFh
0x1800102bd  jz      short loc_1800102CE
0x1800102bf  add     r14, 8
0x1800102c3  add     r12, 8
0x1800102c7  jmp     short loc_18001028E
0x1800102c9  mov     rbx, [rsp+68h+var_48]
0x1800102ce  mov     [rsp+68h+var_40], r15
0x1800102d3  test    r15, r15
0x1800102d6  jz      short loc_1800102E7
0x1800102d8  mov     rax, [r15]
0x1800102db  mov     rcx, r15
0x1800102de  mov     rax, [rax+8]
0x1800102e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102e7  mov     eax, [rbx+4]
0x1800102ea  lea     r14, [rbx+rax*8]
0x1800102ee  lea     rax, [rsp+68h+var_40]
0x1800102f3  cmp     r14, rax
0x1800102f6  jz      short loc_18001030B
0x1800102f8  cmp     qword ptr [r14], 0
0x1800102fc  jz      short loc_180010306
0x1800102fe  mov     rcx, r14
0x180010301  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180010306  mov     [r14], r15
0x180010309  jmp     short loc_18001031A
0x18001030b  test    r15, r15
0x18001030e  jz      short loc_18001031A
0x180010310  lea     rcx, [rsp+68h+var_40]
0x180010315  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18001031a  mov     eax, [rbx+4]
0x18001031d  mov     r12, [rbx+rax*8]
0x180010321  lea     rcx, [rsi+8]; SRWLock
0x180010325  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18001032a  mov     r14, [rsi]
0x18001032d  mov     qword ptr [rsi], 0
0x180010334  lea     rax, [rsp+68h+var_48]
0x180010339  cmp     rsi, rax
0x18001033c  jz      short loc_18001034B
0x18001033e  mov     rax, rbx
0x180010341  xor     ebx, ebx
0x180010343  mov     [rsp+68h+var_48], rbx
0x180010348  mov     [rsi], rax
0x18001034b  mov     [rsp+68h+arg_0], r14
0x180010350  lea     rcx, [rsi+8]; SRWLock
0x180010354  call    ReleaseSRWLockExclusive_0
0x180010359  test    rbx, rbx
0x18001035c  jz      short loc_180010369
0x18001035e  lea     rcx, [rsp+68h+var_48]
0x180010363  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x180010368  nop
0x180010369  mov     rcx, rdi; SRWLock
0x18001036c  call    ReleaseSRWLockExclusive_0
0x180010371  nop
0x180010372  test    r14, r14
0x180010375  jz      short loc_180010381
0x180010377  lea     rcx, [rsp+68h+arg_0]
0x18001037c  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x180010381  mov     rax, [rsp+68h+arg_10]
0x180010389  mov     [rax], r12
0x18001038c  xor     eax, eax
0x18001038e  jmp     short loc_180010394
0x180010390  mov     eax, dword ptr [rsp+68h+arg_0]
0x180010394  add     rsp, 30h
0x180010398  pop     r15
0x18001039a  pop     r14
0x18001039c  pop     r13
0x18001039e  pop     r12
0x1800103a0  pop     rdi
0x1800103a1  pop     rsi
0x1800103a2  pop     rbx
0x1800103a3  retn
```
