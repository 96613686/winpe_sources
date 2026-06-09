# winrt::Windows::Internal::Eap::Utility::implementation::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>(uint)

- ea: `0x18000e5b4`
- end: `0x18000e606`
- name: `??$make_event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@6@I@Z`
- size: `82`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned int)`
- caller_count: `14`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010210`
- `0x1800103b0`
- `0x180010550`
- `0x180010910`
- `0x180010ab0`
- `0x180010c50`
- `0x180023cd0`
- `0x180023e70`
- `0x180024a10`
- `0x180024bb0`
- `0x18002ab90`
- `0x18002ad30`
- `0x18002b460`
- `0x18002b600`

## callees

- `0x180002b78`
- `0x1800037dc`
- `0x18000e5b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::Windows::Internal::Eap::Utility::implementation::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>(
        _QWORD *a1,
        unsigned int a2)
{
  __int64 v4; // rdi
  _DWORD *v5; // rax
  _DWORD *v6; // r14

  v4 = 8LL * a2;
  v5 = operator new(v4 + 8);
  v6 = v5;
  *v5 = 1;
  v5[1] = a2;
  if ( a2 )
    memset_0(v5 + 2, 0, v4 & 0xFFFFFFFFFFFFFFF8uLL);
  *a1 = v6;
  return a1;
}

```

## disassembly

```asm
0x18000e5b4  push    rbx
0x18000e5b6  push    rsi
0x18000e5b7  push    rdi
0x18000e5b8  push    r14
0x18000e5ba  sub     rsp, 38h
0x18000e5be  mov     ebx, edx
0x18000e5c0  mov     rsi, rcx
0x18000e5c3  lea     rdi, ds:0[rbx*8]
0x18000e5cb  lea     rcx, [rdi+8]; Size
0x18000e5cf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e5d4  mov     r14, rax
0x18000e5d7  mov     dword ptr [rax], 1
0x18000e5dd  mov     [rax+4], ebx
0x18000e5e0  test    ebx, ebx
0x18000e5e2  jz      short loc_18000E5F6
0x18000e5e4  and     rdi, 0FFFFFFFFFFFFFFF8h
0x18000e5e8  lea     rcx, [rax+8]; void *
0x18000e5ec  mov     r8, rdi; Size
0x18000e5ef  xor     edx, edx; Val
0x18000e5f1  call    memset_0
0x18000e5f6  mov     [rsi], r14
0x18000e5f9  mov     rax, rsi
0x18000e5fc  add     rsp, 38h
0x18000e600  pop     r14
0x18000e602  pop     rdi
0x18000e603  pop     rsi
0x18000e604  pop     rbx
0x18000e605  retn
```
