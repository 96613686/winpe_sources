# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEASConsentPopup,IPopupCommandHandler>::Release(void)

- ea: `0x1800024f0`
- end: `0x180002551`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIEASConsentPopup@@UIPopupCommandHandler@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002560`

## callees

- `0x1800024f0`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEASConsentPopup,IPopupCommandHandler>::Release(
        volatile signed __int32 *a1)
{
  __int64 v1; // r9
  __int64 v2; // r8
  unsigned int v3; // ebx

  v1 = 0x7FFFFFFF;
  do
    v2 = *((unsigned int *)a1 + 5);
  while ( (_DWORD)v2 != 0x7FFFFFFF && (_DWORD)v2 != _InterlockedCompareExchange(a1 + 5, v2 - 1, v2) );
  v3 = v2 - 1;
  if ( (_DWORD)v2 == 1 )
  {
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64, __int64, __int64))(*(_QWORD *)a1 + 40LL))(
        a1,
        1,
        v2,
        0x7FFFFFFF);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, _QWORD, __int64, __int64))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL))(
        Microsoft::WRL::Details::ModuleBase::module_,
        *(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_,
        v2,
        v1);
  }
  return v3;
}

```

## disassembly

```asm
0x1800024f0  push    rbx
0x1800024f2  sub     rsp, 20h
0x1800024f6  mov     r9d, 7FFFFFFFh
0x1800024fc  jmp     short loc_18000250C
0x1800024fe  lea     edx, [r8-1]
0x180002502  mov     eax, r8d
0x180002505  lock cmpxchg [rcx+14h], edx
0x18000250a  jz      short loc_180002515
0x18000250c  mov     r8d, [rcx+14h]
0x180002510  cmp     r8d, r9d
0x180002513  jnz     short loc_1800024FE
0x180002515  lea     ebx, [r8-1]
0x180002519  test    ebx, ebx
0x18000251b  jnz     short loc_180002549
0x18000251d  test    rcx, rcx
0x180002520  jz      short loc_180002531
0x180002522  mov     rax, [rcx]
0x180002525  lea     edx, [rbx+1]
0x180002528  mov     rax, [rax+28h]
0x18000252c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002531  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180002538  test    rcx, rcx
0x18000253b  jz      short loc_180002549
0x18000253d  mov     rdx, [rcx]
0x180002540  mov     rax, [rdx+10h]
0x180002544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002549  mov     eax, ebx
0x18000254b  add     rsp, 20h
0x18000254f  pop     rbx
0x180002550  retn
```
