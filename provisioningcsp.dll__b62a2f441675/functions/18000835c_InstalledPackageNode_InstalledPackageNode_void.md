# InstalledPackageNode::~InstalledPackageNode(void)

- ea: `0x18000835c`
- end: `0x1800083e2`
- name: `??1InstalledPackageNode@@EEAA@XZ`
- size: `134`
- prototype: `void __fastcall(InstalledPackageNode *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180008580`

## callees

- `0x18000835c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008370`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000839d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008370`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000839d`

## pseudocode

```c
void __fastcall InstalledPackageNode::~InstalledPackageNode(void **this)
{
  if ( (unsigned __int64)this[10] >= 8 )
    operator delete(this[7]);
  this[10] = (void *)7;
  this[9] = 0;
  *((_WORD *)this + 28) = 0;
  if ( (unsigned __int64)this[6] >= 8 )
    operator delete(this[3]);
  this[6] = (void *)7;
  this[5] = 0;
  *((_WORD *)this + 12) = 0;
  *this = &NodeBase::`vftable'{for `ICSPNode'};
  this[1] = &GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
  *((_DWORD *)this + 5) = -1073741823;
}

```

## disassembly

```asm
0x18000835c  push    rbx
0x18000835e  sub     rsp, 20h
0x180008362  cmp     qword ptr [rcx+50h], 8
0x180008367  mov     rbx, rcx
0x18000836a  jb      short loc_18000837C
0x18000836c  mov     rcx, [rcx+38h]
0x180008370  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008377  nop     dword ptr [rax+rax+00h]
0x18000837c  xor     eax, eax
0x18000837e  mov     qword ptr [rbx+50h], 7
0x180008386  mov     qword ptr [rbx+48h], 0
0x18000838e  mov     [rbx+38h], ax
0x180008392  cmp     qword ptr [rbx+30h], 8
0x180008397  jb      short loc_1800083A9
0x180008399  mov     rcx, [rbx+18h]
0x18000839d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800083a4  nop     dword ptr [rax+rax+00h]
0x1800083a9  mov     qword ptr [rbx+30h], 7
0x1800083b1  xor     eax, eax
0x1800083b3  mov     qword ptr [rbx+28h], 0
0x1800083bb  mov     [rbx+18h], ax
0x1800083bf  lea     rax, ??_7NodeBase@@6BICSPNode@@@; const NodeBase::`vftable'{for `ICSPNode'}
0x1800083c6  mov     [rbx], rax
0x1800083c9  lea     rax, ??_7GenericIntNode@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@WRL@Microsoft@@@; const GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x1800083d0  mov     [rbx+8], rax
0x1800083d4  mov     dword ptr [rbx+14h], 0C0000001h
0x1800083db  add     rsp, 20h
0x1800083df  pop     rbx
0x1800083e0  retn
```
