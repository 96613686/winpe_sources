# Microsoft::WRL::ComPtr<Windows::UI::Notifications::IToastNotification>::~ComPtr<Windows::UI::Notifications::IToastNotification>(void)

- ea: `0x180002778`
- end: `0x1800027a0`
- name: `??1?$ComPtr@UIToastNotification@Notifications@UI@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800096fc`
- `0x18000970e`
- `0x180009720`
- `0x180009732`
- `0x180009744`
- `0x180009b7e`
- `0x180009b90`

## callees

- `0x180002778`
- `0x18000a010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<Windows::UI::Notifications::IToastNotification>::~ComPtr<Windows::UI::Notifications::IToastNotification>(
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
0x180002778  sub     rsp, 28h
0x18000277c  mov     rax, rcx
0x18000277f  mov     rcx, [rcx]
0x180002782  test    rcx, rcx
0x180002785  jz      short loc_18000279B
0x180002787  mov     qword ptr [rax], 0
0x18000278e  mov     rax, [rcx]
0x180002791  mov     rax, [rax+10h]
0x180002795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000279a  nop
0x18000279b  add     rsp, 28h
0x18000279f  retn
```
