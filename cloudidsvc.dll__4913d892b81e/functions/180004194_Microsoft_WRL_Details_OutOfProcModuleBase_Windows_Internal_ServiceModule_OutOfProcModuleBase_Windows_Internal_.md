# Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::~OutOfProcModuleBase<Windows::Internal::ServiceModule>(void)

- ea: `0x180004194`
- end: `0x1800041db`
- name: `??1?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@UEAA@XZ`
- size: `71`
- prototype: `bool __fastcall(Microsoft::WRL::Details *, __int64, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004678`
- `0x180004ae0`

## callees

- `0x180004124`
- `0x180004194`
- `0x180012010`

## pseudocode

```c
bool __fastcall Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::~OutOfProcModuleBase<Windows::Internal::ServiceModule>(
        Microsoft::WRL::Details *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        bool a4)
{
  __int64 v5; // rcx

  *(_QWORD *)a1 = &Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::`vftable';
  v5 = *((_QWORD *)a1 + 1);
  if ( v5 )
  {
    if ( *(_BYTE *)(v5 + 8) )
      (**(void (__fastcall ***)(__int64, __int64))v5)(v5, 1);
    *((_QWORD *)a1 + 1) = 0;
  }
  return Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::~Module<1,Windows::Internal::ServiceModule>(
           a1,
           a2,
           a3,
           a4);
}

```

## disassembly

```asm
0x180004194  push    rbx
0x180004196  sub     rsp, 20h
0x18000419a  lea     rax, ??_7?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::`vftable'
0x1800041a1  mov     rbx, rcx
0x1800041a4  mov     [rcx], rax
0x1800041a7  mov     rcx, [rcx+8]
0x1800041ab  test    rcx, rcx
0x1800041ae  jz      short loc_1800041CE
0x1800041b0  cmp     byte ptr [rcx+8], 0
0x1800041b4  jz      short loc_1800041C6
0x1800041b6  mov     rax, [rcx]
0x1800041b9  mov     edx, 1
0x1800041be  mov     rax, [rax]
0x1800041c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041c6  mov     qword ptr [rbx+8], 0
0x1800041ce  mov     rcx, rbx
0x1800041d1  add     rsp, 20h
0x1800041d5  pop     rbx
0x1800041d6  jmp     ??1?$Module@$00VServiceModule@Internal@Windows@@@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::~Module<1,Windows::Internal::ServiceModule>(void)
```
