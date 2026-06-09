# Microsoft::WRL::Details::Make<EnrollmentsUpnNode,>(void)

- ea: `0x18000ff3c`
- end: `0x18000fff4`
- name: `??$Make@VEnrollmentsUpnNode@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VEnrollmentsUpnNode@@@12@XZ`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800102b0`

## callees

- `0x1800030e8`
- `0x18000ff3c`
- `0x18000fffc`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
GenericBStrNode **__fastcall Microsoft::WRL::Details::Make<EnrollmentsUpnNode,>(GenericBStrNode **a1)
{
  GenericBStrNode *v2; // rax
  GenericBStrNode *v3; // rbx

  *a1 = 0;
  v2 = (GenericBStrNode *)operator new(0x80u, (const struct std::nothrow_t *)std::nothrow);
  v3 = v2;
  if ( v2 )
  {
    GenericBStrNode::GenericBStrNode(v2);
    *(_QWORD *)v3 = &EnrollmentsUpnNode::`vftable'{for `ICSPNode'};
    *((_QWORD *)v3 + 1) = &EnrollmentsUpnNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
    *((_QWORD *)v3 + 7) = 0;
    *((_QWORD *)v3 + 8) = 0;
    *((_QWORD *)v3 + 9) = 0;
    *((_QWORD *)v3 + 10) = 0;
    *((_QWORD *)v3 + 11) = 0;
    *((_QWORD *)v3 + 12) = 0;
    *((_QWORD *)v3 + 13) = 0;
    *((_QWORD *)v3 + 14) = 0;
    *((_QWORD *)v3 + 15) = 0;
    if ( *a1 )
      (*(void (__fastcall **)(GenericBStrNode *))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v3;
  }
  return a1;
}

```

## disassembly

```asm
0x18000ff3c  mov     [rsp+arg_0], rbx
0x18000ff41  push    rdi
0x18000ff42  sub     rsp, 20h
0x18000ff46  mov     rdi, rcx
0x18000ff49  mov     qword ptr [rcx], 0
0x18000ff50  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ff57  mov     ecx, 80h; unsigned __int64
0x18000ff5c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ff61  mov     rbx, rax
0x18000ff64  test    rax, rax
0x18000ff67  jz      short loc_18000FFE5
0x18000ff69  mov     rcx, rax; this
0x18000ff6c  call    ??0GenericBStrNode@@QEAA@XZ; GenericBStrNode::GenericBStrNode(void)
0x18000ff71  lea     rax, ??_7EnrollmentsUpnNode@@6BICSPNode@@@; const EnrollmentsUpnNode::`vftable'{for `ICSPNode'}
0x18000ff78  mov     [rbx], rax
0x18000ff7b  lea     rax, ??_7EnrollmentsUpnNode@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@WRL@Microsoft@@@; const EnrollmentsUpnNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x18000ff82  mov     [rbx+8], rax
0x18000ff86  mov     qword ptr [rbx+38h], 0
0x18000ff8e  mov     qword ptr [rbx+40h], 0
0x18000ff96  mov     qword ptr [rbx+48h], 0
0x18000ff9e  mov     qword ptr [rbx+50h], 0
0x18000ffa6  mov     qword ptr [rbx+58h], 0
0x18000ffae  mov     qword ptr [rbx+60h], 0
0x18000ffb6  mov     qword ptr [rbx+68h], 0
0x18000ffbe  mov     qword ptr [rbx+70h], 0
0x18000ffc6  mov     qword ptr [rbx+78h], 0
0x18000ffce  mov     rcx, [rdi]
0x18000ffd1  test    rcx, rcx
0x18000ffd4  jz      short loc_18000FFE2
0x18000ffd6  mov     rax, [rcx]
0x18000ffd9  mov     rax, [rax+10h]
0x18000ffdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffe2  mov     [rdi], rbx
0x18000ffe5  mov     rax, rdi
0x18000ffe8  mov     rbx, [rsp+28h+arg_0]
0x18000ffed  add     rsp, 20h
0x18000fff1  pop     rdi
0x18000fff2  retn
```
