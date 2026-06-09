# Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::~CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>(void)

- ea: `0x18000fb68`
- end: `0x18000fb95`
- name: `??1?$CFileChannel@VCCompletionPortIo@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@QEAA@XZ`
- size: `45`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fd10`
- `0x180028c7b`
- `0x180028c94`

## callees

- `0x180005130`
- `0x18000fc90`
- `0x18000fcac`
- `0x180010218`

## pseudocode

```c
__int64 __fastcall Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::~CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>(
        __int64 a1)
{
  Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::Close(a1);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(a1 + 96);
  std::unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo>::~unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo>(a1 + 8);
  return wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(a1);
}

```

## disassembly

```asm
0x18000fb68  push    rbx
0x18000fb6a  sub     rsp, 20h
0x18000fb6e  mov     rbx, rcx
0x18000fb71  call    ?Close@?$CFileChannel@VCCompletionPortIo@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@QEAAXXZ; Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::Close(void)
0x18000fb76  lea     rcx, [rbx+60h]
0x18000fb7a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000fb7f  lea     rcx, [rbx+8]
0x18000fb83  call    ??1?$unique_ptr@VCCompletionPortIo@details@TP@Utils@Rdp@@U?$default_delete@VCCompletionPortIo@details@TP@Utils@Rdp@@@std@@@std@@QEAA@XZ; std::unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo>::~unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo>(void)
0x18000fb88  mov     rcx, rbx
0x18000fb8b  add     rsp, 20h
0x18000fb8f  pop     rbx
0x18000fb90  jmp     ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
```
