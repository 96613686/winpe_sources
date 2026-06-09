# winrt::impl::heap_implements<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs>::`scalar deleting destructor'(uint)

- ea: `0x18000ecf0`
- end: `0x18000ed24`
- name: `??_G?$heap_implements@UEapMethodRunnerAuthenticationCompletedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@UEAAPEAXI@Z`
- size: `52`
- prototype: `winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs *__fastcall(winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800025a0`
- `0x18000ec20`
- `0x18000ecf0`

## pseudocode

```c
winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs *__fastcall winrt::impl::heap_implements<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs>::`scalar deleting destructor'(
        winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs *a1,
        char a2)
{
  winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs::~EapMethodRunnerAuthenticationCompletedEventArgs(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000ecf0  mov     [rsp+arg_0], rbx
0x18000ecf5  push    rdi
0x18000ecf6  sub     rsp, 20h
0x18000ecfa  mov     ebx, edx
0x18000ecfc  mov     rdi, rcx
0x18000ecff  call    ??1EapMethodRunnerAuthenticationCompletedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@UEAA@XZ; winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs::~EapMethodRunnerAuthenticationCompletedEventArgs(void)
0x18000ed04  test    bl, 1
0x18000ed07  jz      short loc_18000ED16
0x18000ed09  mov     edx, 78h ; 'x'; unsigned __int64
0x18000ed0e  mov     rcx, rdi; void *
0x18000ed11  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ed16  mov     rbx, [rsp+28h+arg_0]
0x18000ed1b  mov     rax, rdi
0x18000ed1e  add     rsp, 20h
0x18000ed22  pop     rdi
0x18000ed23  retn
```
