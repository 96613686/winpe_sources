# Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>(Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> &&)

- ea: `0x18000d1a8`
- end: `0x18000d1c5`
- name: `??0?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z`
- size: `29`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c888`
- `0x18000d130`
- `0x18000d16c`
- `0x18000d82c`
- `0x18000ea34`

## callees

- `0x18000d1a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>(
        _QWORD *a1,
        _QWORD *a2)
{
  *a1 = 0;
  if ( a1 != a2 )
  {
    *a1 = *a2;
    *a2 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18000d1a8  mov     qword ptr [rcx], 0
0x18000d1af  cmp     rcx, rdx
0x18000d1b2  jz      short loc_18000D1C1
0x18000d1b4  mov     rax, [rdx]
0x18000d1b7  mov     [rcx], rax
0x18000d1ba  mov     qword ptr [rdx], 0
0x18000d1c1  mov     rax, rcx
0x18000d1c4  retn
```
