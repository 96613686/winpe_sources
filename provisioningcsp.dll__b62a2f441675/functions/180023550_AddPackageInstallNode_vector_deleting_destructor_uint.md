# AddPackageInstallNode::`vector deleting destructor'(uint)

- ea: `0x180023550`
- end: `0x1800235d2`
- name: `??_EAddPackageInstallNode@@EEAAPEAXI@Z`
- size: `130`
- prototype: `void *__fastcall(AddPackageInstallNode *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180023550`
- `0x180038010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800235b7`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800235b7`

## pseudocode

```c
AddPackageInstallNode *__fastcall AddPackageInstallNode::`vector deleting destructor'(
        AddPackageInstallNode *this,
        char a2)
{
  __int64 v4; // rcx

  *(_QWORD *)this = &AddPackageInstallNode::`vftable'{for `ICSPNode'};
  *((_QWORD *)this + 1) = &GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
  v4 = *((_QWORD *)this + 4);
  if ( v4 )
  {
    *((_QWORD *)this + 4) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  *(_QWORD *)this = &NodeBase::`vftable'{for `ICSPNode'};
  *((_QWORD *)this + 1) = &GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
  *((_DWORD *)this + 5) = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180023550  mov     [rsp+arg_0], rbx
0x180023555  push    rdi
0x180023556  sub     rsp, 20h
0x18002355a  mov     edi, edx
0x18002355c  mov     rbx, rcx
0x18002355f  lea     rax, ??_7AddPackageInstallNode@@6BICSPNode@@@; const AddPackageInstallNode::`vftable'{for `ICSPNode'}
0x180023566  mov     [rcx], rax
0x180023569  lea     rax, ??_7GenericIntNode@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@WRL@Microsoft@@@; const GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x180023570  mov     [rcx+8], rax
0x180023574  mov     rcx, [rcx+20h]
0x180023578  test    rcx, rcx
0x18002357b  jz      short loc_180023592
0x18002357d  mov     qword ptr [rbx+20h], 0
0x180023585  mov     rax, [rcx]
0x180023588  mov     rax, [rax+10h]
0x18002358c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023591  nop
0x180023592  lea     rax, ??_7NodeBase@@6BICSPNode@@@; const NodeBase::`vftable'{for `ICSPNode'}
0x180023599  mov     [rbx], rax
0x18002359c  lea     rax, ??_7GenericIntNode@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@WRL@Microsoft@@@; const GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x1800235a3  mov     [rbx+8], rax
0x1800235a7  mov     dword ptr [rbx+14h], 0C0000001h
0x1800235ae  test    dil, 1
0x1800235b2  jz      short loc_1800235C3
0x1800235b4  mov     rcx, rbx
0x1800235b7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800235be  nop     dword ptr [rax+rax+00h]
0x1800235c3  mov     rax, rbx
0x1800235c6  mov     rbx, [rsp+28h+arg_0]
0x1800235cb  add     rsp, 20h
0x1800235cf  pop     rdi
0x1800235d0  retn
```
