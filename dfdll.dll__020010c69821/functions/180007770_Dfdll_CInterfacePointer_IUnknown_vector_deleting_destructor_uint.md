# Dfdll::CInterfacePointer<IUnknown>::`vector deleting destructor'(uint)

- ea: `0x180007770`
- end: `0x1800077cf`
- name: `??_E?$CInterfacePointer@UIUnknown@@@Dfdll@@UEAAPEAXI@Z`
- size: `95`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x180007770`
- `0x180012b30`
- `0x18001efd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Dfdll::CInterfacePointer<IUnknown>::`vector deleting destructor'(_QWORD *a1, char a2)
{
  __int64 v4; // rcx

  *a1 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  v4 = a1[1];
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  a1[1] = 0;
  *a1 = &Dfdll::CObject::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1, (const struct std::nothrow_t *)0x10);
  return a1;
}

```

## disassembly

```asm
0x180007770  mov     [rsp+arg_0], rbx
0x180007775  push    rdi
0x180007776  sub     rsp, 20h
0x18000777a  mov     edi, edx
0x18000777c  mov     rbx, rcx
0x18000777f  lea     rax, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x180007786  mov     [rcx], rax
0x180007789  mov     rcx, [rcx+8]
0x18000778d  test    rcx, rcx
0x180007790  jz      short loc_18000779F
0x180007792  mov     rax, [rcx]
0x180007795  mov     rax, [rax+10h]
0x180007799  call    cs:__guard_dispatch_icall_fptr
0x18000779f  and     qword ptr [rbx+8], 0
0x1800077a4  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x1800077ab  mov     [rbx], rax
0x1800077ae  test    dil, 1
0x1800077b2  jz      short loc_1800077C1
0x1800077b4  mov     edx, 10h; struct std::nothrow_t *
0x1800077b9  mov     rcx, rbx; void *
0x1800077bc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800077c1  mov     rax, rbx
0x1800077c4  mov     rbx, [rsp+28h+arg_0]
0x1800077c9  add     rsp, 20h
0x1800077cd  pop     rdi
0x1800077ce  retn
```
