# Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageManager>::~ComPtr<Windows::Management::Provisioning::IPackageManager>(void)

- ea: `0x18000446c`
- end: `0x180004494`
- name: `??1?$ComPtr@UIPackageManager@Provisioning@Management@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018a38`
- `0x18003bdfc`
- `0x18003cb4b`
- `0x18003cb81`
- `0x18003cb93`
- `0x18003cbc9`
- `0x18003cc1a`
- `0x18003cc50`
- `0x18003ccf6`
- `0x18003cd31`
- `0x18003cd93`
- `0x18003cffa`
- `0x18003d2f4`
- `0x18003d318`
- `0x18003d33c`
- `0x18003d34e`
- `0x18003d360`
- `0x18003d3eb`
- `0x18003d510`
- `0x18003d56a`
- `0x18003db80`
- `0x18003dc14`

## callees

- `0x18000446c`
- `0x18003f010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageManager>::~ComPtr<Windows::Management::Provisioning::IPackageManager>(
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
0x18000446c  sub     rsp, 28h
0x180004470  mov     rax, rcx
0x180004473  mov     rcx, [rcx]
0x180004476  test    rcx, rcx
0x180004479  jz      short loc_18000448F
0x18000447b  mov     qword ptr [rax], 0
0x180004482  mov     rax, [rcx]
0x180004485  mov     rax, [rax+10h]
0x180004489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000448e  nop
0x18000448f  add     rsp, 28h
0x180004493  retn
```
