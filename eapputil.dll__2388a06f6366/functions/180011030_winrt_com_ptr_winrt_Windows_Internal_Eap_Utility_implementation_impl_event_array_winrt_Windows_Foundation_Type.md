# winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)

- ea: `0x180011030`
- end: `0x180011095`
- name: `?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ`
- size: `101`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `22`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000ead4`
- `0x18000ebb8`
- `0x18000f900`
- `0x180010210`
- `0x1800103b0`
- `0x180010550`
- `0x180010910`
- `0x180010ab0`
- `0x180010c50`
- `0x18001392c`
- `0x1800178dc`
- `0x180023cd0`
- `0x180023e70`
- `0x180024a10`
- `0x180024bb0`
- `0x18002609c`
- `0x1800294d0`
- `0x1800296e4`
- `0x18002ab90`
- `0x18002ad30`
- `0x18002b460`
- `0x18002b600`

## callees

- `0x180002a4c`
- `0x1800083ec`
- `0x180011030`

## pseudocode

```c
void __fastcall winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(
        unsigned int **a1)
{
  unsigned int *v1; // rdi
  __int64 *v2; // rbx
  __int64 *v3; // rsi

  v1 = *a1;
  *a1 = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v1, 0xFFFFFFFF) == 1 )
  {
    v2 = (__int64 *)(v1 + 2);
    v3 = (__int64 *)&v1[2 * v1[1] + 2];
    while ( v2 != v3 )
    {
      if ( *v2 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v2);
      ++v2;
    }
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x180011030  mov     [rsp+arg_0], rbx
0x180011035  mov     [rsp+arg_8], rsi
0x18001103a  push    rdi
0x18001103b  sub     rsp, 20h
0x18001103f  mov     rdi, [rcx]
0x180011042  or      eax, 0FFFFFFFFh
0x180011045  mov     qword ptr [rcx], 0
0x18001104c  lock xadd [rdi], eax
0x180011050  cmp     eax, 1
0x180011053  jnz     short loc_180011085
0x180011055  nop
0x180011056  lea     rbx, [rdi+8]
0x18001105a  mov     esi, [rdi+4]
0x18001105d  inc     rsi
0x180011060  lea     rsi, [rdi+rsi*8]
0x180011064  jmp     short loc_180011078
0x180011066  cmp     qword ptr [rbx], 0
0x18001106a  jz      short loc_180011074
0x18001106c  mov     rcx, rbx
0x18001106f  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180011074  add     rbx, 8
0x180011078  cmp     rbx, rsi
0x18001107b  jnz     short loc_180011066
0x18001107d  mov     rcx, rdi; Block
0x180011080  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011085  mov     rbx, [rsp+28h+arg_0]
0x18001108a  mov     rsi, [rsp+28h+arg_8]
0x18001108f  add     rsp, 20h
0x180011093  pop     rdi
0x180011094  retn
```
