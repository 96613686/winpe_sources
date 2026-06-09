# _ux::CLauncherMainTaskDialog::operator()_::_1_::catch$3

- ea: `0x18001066e`
- end: `0x18001069f`
- name: `_ux::CLauncherMainTaskDialog::operator()_::_1_::catch$3`
- size: `49`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000a148`

## pseudocode

```c
__int64 __fastcall ux::CLauncherMainTaskDialog::operator()_::_1_::catch_3(__int64 a1, __int64 a2)
{
  *(_BYTE *)(a2 + 128) = ux::CLauncherMainTaskDialog::HandleException(
                           *(ux::CLauncherMainTaskDialog **)(a2 + 112),
                           *(const struct ATL::CAtlException **)(a2 + 32));
  return 0;
}

```

## disassembly

```asm
0x18001066e  mov     [rsp+arg_8], rdx
0x180010673  push    rbp
0x180010674  sub     rsp, 20h
0x180010678  mov     rbp, rdx
0x18001067b  mov     rdx, [rbp+20h]; struct ATL::CAtlException *
0x18001067f  mov     rcx, [rbp+70h]; this
0x180010683  call    ?HandleException@CLauncherMainTaskDialog@ux@@AEBA_NAEBVCAtlException@ATL@@@Z; ux::CLauncherMainTaskDialog::HandleException(ATL::CAtlException const &)
0x180010688  mov     [rbp+80h], al
0x18001068e  mov     rax, 0
0x180010698  add     rsp, 20h
0x18001069c  pop     rbp
0x18001069d  retn
```
