# Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator::`scalar deleting destructor'(uint)

- ea: `0x1800203d0`
- end: `0x180020429`
- name: `??_GThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@UEAAPEAXI@Z`
- size: `89`
- prototype: `void *__fastcall(Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001b94`
- `0x1800203d0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800203e8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800203e8`

## pseudocode

```c
Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator *__fastcall Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator::`scalar deleting destructor'(
        Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator *this,
        char a2)
{
  struct _TP_CLEANUP_GROUP *v4; // rcx
  void *v5; // rcx

  v4 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 2);
  if ( v4 )
    CloseThreadpoolCleanupGroup(v4);
  v5 = (void *)*((_QWORD *)this + 1);
  if ( v5 )
    operator delete(v5, (const struct std::nothrow_t *)0x48);
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x18);
  return this;
}

```

## disassembly

```asm
0x1800203d0  mov     [rsp+arg_0], rbx
0x1800203d5  push    rdi
0x1800203d6  sub     rsp, 20h
0x1800203da  mov     rbx, rcx
0x1800203dd  mov     edi, edx
0x1800203df  mov     rcx, [rcx+10h]; ptpcg
0x1800203e3  test    rcx, rcx
0x1800203e6  jz      short loc_1800203F4
0x1800203e8  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1800203ef  nop     dword ptr [rax+rax+00h]
0x1800203f4  mov     rcx, [rbx+8]; void *
0x1800203f8  test    rcx, rcx
0x1800203fb  jz      short loc_180020407
0x1800203fd  mov     edx, 48h ; 'H'; struct std::nothrow_t *
0x180020402  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180020407  test    dil, 1
0x18002040b  jz      short loc_18002041A
0x18002040d  mov     edx, 18h; struct std::nothrow_t *
0x180020412  mov     rcx, rbx; void *
0x180020415  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002041a  mov     rax, rbx
0x18002041d  mov     rbx, [rsp+28h+arg_0]
0x180020422  add     rsp, 20h
0x180020426  pop     rdi
0x180020427  retn
```
