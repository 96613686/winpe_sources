# Microsoft::Basix::Dct::WindowsSocketToolsImpl::`scalar deleting destructor'(uint)

- ea: `0x180249570`
- end: `0x1802495ae`
- name: `??_GWindowsSocketToolsImpl@Dct@Basix@Microsoft@@UEAAPEAXI@Z`
- size: `62`
- prototype: `void *__fastcall(Microsoft::Basix::Dct::WindowsSocketToolsImpl *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180249570`
- `0x18032f050`
- `0x18032f140`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x180249588`
- `WS2_32!__imp_WSACleanup` at `0x180249588`

## pseudocode

```c
Microsoft::Basix::Dct::WindowsSocketToolsImpl *__fastcall Microsoft::Basix::Dct::WindowsSocketToolsImpl::`scalar deleting destructor'(
        Microsoft::Basix::Dct::WindowsSocketToolsImpl *this,
        char a2)
{
  WSACleanup();
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x1A0);
  return this;
}

```

## disassembly

```asm
0x180249570  mov     [rsp+arg_0], rbx
0x180249575  push    rdi
0x180249576  mov     eax, 20h
0x18024957b  call    _alloca_probe
0x180249580  sub     rsp, rax
0x180249583  mov     ebx, edx
0x180249585  mov     rdi, rcx
0x180249588  call    cs:__imp_WSACleanup
0x18024958e  test    bl, 1
0x180249591  jz      short loc_1802495A0
0x180249593  mov     edx, 1A0h; struct std::nothrow_t *
0x180249598  mov     rcx, rdi; void *
0x18024959b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1802495a0  mov     rbx, [rsp+28h+arg_0]
0x1802495a5  mov     rax, rdi
0x1802495a8  add     rsp, 20h
0x1802495ac  pop     rdi
0x1802495ad  retn
```
