# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x18001f1d4`
- end: `0x18001f1f3`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001ef44`
- `0x18001ef74`
- `0x180020d6c`
- `0x180020e98`
- `0x18002633c`

## callees

- `0x18001f100`

## pseudocode

```c
void __fastcall wil::details_abi::SemaphoreValue::~SemaphoreValue(wil::details **this, void *a2)
{
  void *v3; // rdx

  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    this + 1,
    a2);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    this,
    v3);
}

```

## disassembly

```asm
0x18001f1d4  push    rbx
0x18001f1d6  sub     rsp, 20h
0x18001f1da  mov     rbx, rcx
0x18001f1dd  add     rcx, 8
0x18001f1e1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f1e6  mov     rcx, rbx
0x18001f1e9  add     rsp, 20h
0x18001f1ed  pop     rbx
0x18001f1ee  jmp     ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
```
