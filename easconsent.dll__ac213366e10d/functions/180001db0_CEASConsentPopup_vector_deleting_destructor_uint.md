# CEASConsentPopup::`vector deleting destructor'(uint)

- ea: `0x180001db0`
- end: `0x180001e14`
- name: `??_ECEASConsentPopup@@EEAAPEAXI@Z`
- size: `100`
- prototype: `CEASConsentPopup *__fastcall(CEASConsentPopup *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001070`
- `0x180001db0`
- `0x180004010`

## pseudocode

```c
CEASConsentPopup *__fastcall CEASConsentPopup::`vector deleting destructor'(CEASConsentPopup *this, char a2)
{
  __int64 v4; // rcx

  *(_QWORD *)this = &CEASConsentPopup::`vftable'{for `IEASConsentPopup'};
  *((_QWORD *)this + 1) = &CEASConsentPopup::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IPopupCommandHandler>'};
  v4 = *((_QWORD *)this + 4);
  if ( v4 )
  {
    *((_QWORD *)this + 4) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  *((_DWORD *)this + 5) = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180001db0  mov     [rsp+arg_0], rbx
0x180001db5  push    rdi
0x180001db6  sub     rsp, 20h
0x180001dba  lea     rax, ??_7CEASConsentPopup@@6BIEASConsentPopup@@@; const CEASConsentPopup::`vftable'{for `IEASConsentPopup'}
0x180001dc1  mov     rbx, rcx
0x180001dc4  mov     [rcx], rax
0x180001dc7  mov     edi, edx
0x180001dc9  lea     rax, ??_7CEASConsentPopup@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIPopupCommandHandler@@@Details@WRL@Microsoft@@@; const CEASConsentPopup::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IPopupCommandHandler>'}
0x180001dd0  mov     [rcx+8], rax
0x180001dd4  mov     rcx, [rcx+20h]
0x180001dd8  test    rcx, rcx
0x180001ddb  jz      short loc_180001DF1
0x180001ddd  mov     qword ptr [rbx+20h], 0
0x180001de5  mov     rax, [rcx]
0x180001de8  mov     rax, [rax+10h]
0x180001dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001df1  mov     dword ptr [rbx+14h], 0C0000001h
0x180001df8  test    dil, 1
0x180001dfc  jz      short loc_180001E06
0x180001dfe  mov     rcx, rbx; Block
0x180001e01  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001e06  mov     rax, rbx
0x180001e09  mov     rbx, [rsp+28h+arg_0]
0x180001e0e  add     rsp, 20h
0x180001e12  pop     rdi
0x180001e13  retn
```
