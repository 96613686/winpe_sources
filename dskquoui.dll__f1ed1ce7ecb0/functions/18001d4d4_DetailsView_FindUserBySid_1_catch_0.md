# _DetailsView::FindUserBySid_::_1_::catch$0

- ea: `0x18001d4d4`
- end: `0x18001d4f8`
- name: `_DetailsView::FindUserBySid_::_1_::catch$0`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x18000f550`
- `0x18001ce34`

## pseudocode

```c
void __fastcall __noreturn DetailsView::FindUserBySid_::_1_::catch_0(__int64 a1, __int64 a2)
{
  PointerList::ReleaseLock((PointerList *)(*(_QWORD *)(a2 + 48) + 40LL));
  throw;
}

```

## disassembly

```asm
0x18001d4d4  mov     [rsp+arg_8], rdx
0x18001d4d9  push    rbp
0x18001d4da  sub     rsp, 20h
0x18001d4de  mov     rbp, rdx
0x18001d4e1  mov     rcx, [rbp+30h]
0x18001d4e5  add     rcx, 28h ; '('; this
0x18001d4e9  call    ?ReleaseLock@PointerList@@QEAAXXZ; PointerList::ReleaseLock(void)
0x18001d4ee  xor     edx, edx; pThrowInfo
0x18001d4f0  xor     ecx, ecx; pExceptionObject
0x18001d4f2  call    _CxxThrowException_0
```
