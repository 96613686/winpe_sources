# Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>::~ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>(void)

- ea: `0x18000a96c`
- end: `0x18000a994`
- name: `??1?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180019198`
- `0x1800191f2`
- `0x180019282`
- `0x1800193e5`

## callees

- `0x18000a96c`
- `0x18001b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>::~ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>(
        _QWORD *a1)
{
  _QWORD *result; // rax
  __int64 v2; // rcx

  result = a1;
  v2 = *a1;
  if ( v2 )
  {
    *result = 0;
    return (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x18000a96c  sub     rsp, 28h
0x18000a970  mov     rax, rcx
0x18000a973  mov     rcx, [rcx]
0x18000a976  test    rcx, rcx
0x18000a979  jz      short loc_18000A98F
0x18000a97b  mov     qword ptr [rax], 0
0x18000a982  mov     rax, [rcx]
0x18000a985  mov     rax, [rax+10h]
0x18000a989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a98e  nop
0x18000a98f  add     rsp, 28h
0x18000a993  retn
```
