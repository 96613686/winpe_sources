# CProvisioningCommandsClassFactory::Release(void)

- ea: `0x180004d30`
- end: `0x180004d58`
- name: `?Release@CProvisioningCommandsClassFactory@@UEAAKXZ`
- size: `40`
- prototype: `unsigned int __fastcall(CProvisioningCommandsClassFactory *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004d30`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004d43`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004d43`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsClassFactory::Release(CProvisioningCommandsClassFactory *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 )
    operator delete(this);
  return v1;
}

```

## disassembly

```asm
0x180004d30  push    rbx
0x180004d32  sub     rsp, 20h
0x180004d36  or      ebx, 0FFFFFFFFh
0x180004d39  lock xadd [rcx+8], ebx
0x180004d3e  sub     ebx, 1
0x180004d41  jnz     short loc_180004D4F
0x180004d43  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004d4a  nop     dword ptr [rax+rax+00h]
0x180004d4f  mov     eax, ebx
0x180004d51  add     rsp, 20h
0x180004d55  pop     rbx
0x180004d56  retn
```
