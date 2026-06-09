# Microsoft::WRL::ComPtr<Windows::UI::Notifications::IToastNotificationManagerStatics2>::~ComPtr<Windows::UI::Notifications::IToastNotificationManagerStatics2>(void)

- ea: `0x18000764c`
- end: `0x180007672`
- name: `??1?$ComPtr@UIToastNotificationManagerStatics2@Notifications@UI@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `38`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022183`
- `0x1800222bd`
- `0x1800222cf`
- `0x180022b42`
- `0x180022b54`
- `0x180022b78`
- `0x180022b8a`
- `0x180022b9c`
- `0x180022bae`
- `0x180022bc0`
- `0x180022bd2`

## callees

- `0x18000764c`
- `0x180024010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<Windows::UI::Notifications::IToastNotificationManagerStatics2>::~ComPtr<Windows::UI::Notifications::IToastNotificationManagerStatics2>(
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
0x18000764c  sub     rsp, 28h
0x180007650  mov     rax, rcx
0x180007653  mov     rcx, [rcx]
0x180007656  test    rcx, rcx
0x180007659  jz      short loc_18000766C
0x18000765b  and     qword ptr [rax], 0
0x18000765f  mov     rax, [rcx]
0x180007662  mov     rax, [rax+10h]
0x180007666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000766b  nop
0x18000766c  add     rsp, 28h
0x180007670  retn
```
