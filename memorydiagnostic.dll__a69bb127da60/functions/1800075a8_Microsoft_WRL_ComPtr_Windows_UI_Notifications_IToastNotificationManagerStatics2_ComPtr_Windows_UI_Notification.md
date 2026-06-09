# Microsoft::WRL::ComPtr<Windows::UI::Notifications::IToastNotificationManagerStatics2>::~ComPtr<Windows::UI::Notifications::IToastNotificationManagerStatics2>(void)

- ea: `0x1800075a8`
- end: `0x1800075d0`
- name: `??1?$ComPtr@UIToastNotificationManagerStatics2@Notifications@UI@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800209d9`
- `0x180020b13`
- `0x180020b25`
- `0x1800211d6`
- `0x1800211e8`
- `0x18002120c`
- `0x18002121e`
- `0x180021230`
- `0x180021242`

## callees

- `0x1800075a8`
- `0x180023010`

## pseudocode

```c
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
0x1800075a8  sub     rsp, 28h
0x1800075ac  mov     rax, rcx
0x1800075af  mov     rcx, [rcx]
0x1800075b2  test    rcx, rcx
0x1800075b5  jz      short loc_1800075CB
0x1800075b7  mov     qword ptr [rax], 0
0x1800075be  mov     rax, [rcx]
0x1800075c1  mov     rax, [rax+10h]
0x1800075c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075ca  nop
0x1800075cb  add     rsp, 28h
0x1800075cf  retn
```
