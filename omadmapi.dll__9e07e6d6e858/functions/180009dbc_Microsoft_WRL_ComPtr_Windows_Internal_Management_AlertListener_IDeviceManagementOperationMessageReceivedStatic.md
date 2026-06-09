# Microsoft::WRL::ComPtr<Windows::Internal::Management::AlertListener::IDeviceManagementOperationMessageReceivedStatics>::~ComPtr<Windows::Internal::Management::AlertListener::IDeviceManagementOperationMessageReceivedStatics>(void)

- ea: `0x180009dbc`
- end: `0x180009de5`
- name: `??1?$ComPtr@UIDeviceManagementOperationMessageReceivedStatics@AlertListener@Management@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180023141`

## callees

- `0x180009dbc`
- `0x180024010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<Windows::Internal::Management::AlertListener::IDeviceManagementOperationMessageReceivedStatics>::~ComPtr<Windows::Internal::Management::AlertListener::IDeviceManagementOperationMessageReceivedStatics>(
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
0x180009dbc  sub     rsp, 28h
0x180009dc0  mov     rax, rcx
0x180009dc3  mov     rcx, [rcx]
0x180009dc6  test    rcx, rcx
0x180009dc9  jz      short loc_180009DDF
0x180009dcb  mov     qword ptr [rax], 0
0x180009dd2  mov     rax, [rcx]
0x180009dd5  mov     rax, [rax+10h]
0x180009dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dde  nop
0x180009ddf  add     rsp, 28h
0x180009de3  retn
```
