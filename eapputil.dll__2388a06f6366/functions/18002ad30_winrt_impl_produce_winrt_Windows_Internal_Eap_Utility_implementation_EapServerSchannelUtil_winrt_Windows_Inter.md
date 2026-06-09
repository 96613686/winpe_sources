# winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::IEapServerSchannelUtil>::add_TlsHandshakeCompleted(void *,winrt::event_token *)

- ea: `0x18002ad30`
- end: `0x18002aec8`
- name: `?add_TlsHandshakeCompleted@?$produce@UEapServerSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@UIEapServerSchannelUtil@34567@@impl@winrt@@UEAAHPEAXPEAUevent_token@3@@Z`
- size: `408`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002cf3`
- `0x180002cff`
- `0x1800083ec`
- `0x18000e5b4`
- `0x180011030`
- `0x18002ad30`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::IEapServerSchannelUtil>::add_TlsHandshakeCompleted(
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
  v4 = a1 + 24;
  if ( !a1 )
    v4 = (RTL_SRWLOCK *)208;
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
0x18002ad30  mov     r11, rsp
0x18002ad33  mov     [r11+18h], r8
0x18002ad37  push    rbx
0x18002ad38  push    rsi
0x18002ad39  push    rdi
0x18002ad3a  push    r12
0x18002ad3c  push    r13
0x18002ad3e  push    r14
0x18002ad40  push    r15
0x18002ad42  sub     rsp, 30h
0x18002ad46  mov     r15, rdx
0x18002ad49  lea     rsi, [rcx+0C0h]
0x18002ad50  mov     eax, 0D0h
0x18002ad55  test    rcx, rcx
0x18002ad58  cmovz   rsi, rax
0x18002ad5c  mov     qword ptr [r11+8], 0
0x18002ad64  lea     rdi, [rsi+10h]
0x18002ad68  mov     [r11+20h], rdi
0x18002ad6c  mov     rcx, rdi; SRWLock
0x18002ad6f  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18002ad74  nop
0x18002ad75  mov     rdx, [rsi]
0x18002ad78  test    rdx, rdx
0x18002ad7b  jz      short loc_18002AD84
0x18002ad7d  mov     edx, [rdx+4]
0x18002ad80  inc     edx
0x18002ad82  jmp     short loc_18002AD89
0x18002ad84  mov     edx, 1
0x18002ad89  lea     rcx, [rsp+68h+var_48]
0x18002ad8e  call    ??$make_event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@6@I@Z; winrt::Windows::Internal::Eap::Utility::implementation::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>(uint)
0x18002ad93  mov     rax, [rsi]
0x18002ad96  test    rax, rax
0x18002ad99  jz      short loc_18002ADEC
0x18002ad9b  mov     r13d, [rax+4]
0x18002ad9f  test    r13d, r13d
0x18002ada2  jz      short loc_18002ADEC
0x18002ada4  lea     r12, [rax+8]
0x18002ada8  mov     rbx, [rsp+68h+var_48]
0x18002adad  lea     r14, [rbx+8]
0x18002adb1  cmp     r14, r12
0x18002adb4  jz      short loc_18002ADDC
0x18002adb6  cmp     qword ptr [r14], 0
0x18002adba  jz      short loc_18002ADC4
0x18002adbc  mov     rcx, r14
0x18002adbf  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18002adc4  mov     rcx, [r12]
0x18002adc8  mov     [r14], rcx
0x18002adcb  test    rcx, rcx
0x18002adce  jz      short loc_18002ADDC
0x18002add0  mov     rax, [rcx]
0x18002add3  mov     rax, [rax+8]
0x18002add7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002addc  add     r13d, 0FFFFFFFFh
0x18002ade0  jz      short loc_18002ADF1
0x18002ade2  add     r14, 8
0x18002ade6  add     r12, 8
0x18002adea  jmp     short loc_18002ADB1
0x18002adec  mov     rbx, [rsp+68h+var_48]
0x18002adf1  mov     [rsp+68h+var_40], r15
0x18002adf6  test    r15, r15
0x18002adf9  jz      short loc_18002AE0A
0x18002adfb  mov     rax, [r15]
0x18002adfe  mov     rcx, r15
0x18002ae01  mov     rax, [rax+8]
0x18002ae05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae0a  mov     eax, [rbx+4]
0x18002ae0d  lea     r14, [rbx+rax*8]
0x18002ae11  lea     rax, [rsp+68h+var_40]
0x18002ae16  cmp     r14, rax
0x18002ae19  jz      short loc_18002AE2E
0x18002ae1b  cmp     qword ptr [r14], 0
0x18002ae1f  jz      short loc_18002AE29
0x18002ae21  mov     rcx, r14
0x18002ae24  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18002ae29  mov     [r14], r15
0x18002ae2c  jmp     short loc_18002AE3D
0x18002ae2e  test    r15, r15
0x18002ae31  jz      short loc_18002AE3D
0x18002ae33  lea     rcx, [rsp+68h+var_40]
0x18002ae38  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18002ae3d  mov     eax, [rbx+4]
0x18002ae40  mov     r12, [rbx+rax*8]
0x18002ae44  lea     rcx, [rsi+8]; SRWLock
0x18002ae48  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18002ae4d  mov     r14, [rsi]
0x18002ae50  mov     qword ptr [rsi], 0
0x18002ae57  lea     rax, [rsp+68h+var_48]
0x18002ae5c  cmp     rsi, rax
0x18002ae5f  jz      short loc_18002AE6E
0x18002ae61  mov     rax, rbx
0x18002ae64  xor     ebx, ebx
0x18002ae66  mov     [rsp+68h+var_48], rbx
0x18002ae6b  mov     [rsi], rax
0x18002ae6e  mov     [rsp+68h+arg_0], r14
0x18002ae73  lea     rcx, [rsi+8]; SRWLock
0x18002ae77  call    ReleaseSRWLockExclusive_0
0x18002ae7c  test    rbx, rbx
0x18002ae7f  jz      short loc_18002AE8C
0x18002ae81  lea     rcx, [rsp+68h+var_48]
0x18002ae86  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x18002ae8b  nop
0x18002ae8c  mov     rcx, rdi; SRWLock
0x18002ae8f  call    ReleaseSRWLockExclusive_0
0x18002ae94  nop
0x18002ae95  test    r14, r14
0x18002ae98  jz      short loc_18002AEA4
0x18002ae9a  lea     rcx, [rsp+68h+arg_0]
0x18002ae9f  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x18002aea4  mov     rax, [rsp+68h+arg_10]
0x18002aeac  mov     [rax], r12
0x18002aeaf  xor     eax, eax
0x18002aeb1  jmp     short loc_18002AEB7
0x18002aeb3  mov     eax, dword ptr [rsp+68h+arg_0]
0x18002aeb7  add     rsp, 30h
0x18002aebb  pop     r15
0x18002aebd  pop     r14
0x18002aebf  pop     r13
0x18002aec1  pop     r12
0x18002aec3  pop     rdi
0x18002aec4  pop     rsi
0x18002aec5  pop     rbx
0x18002aec6  retn
```
