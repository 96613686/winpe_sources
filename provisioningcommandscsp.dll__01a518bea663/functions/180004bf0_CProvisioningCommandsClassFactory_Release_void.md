# CProvisioningCommandsClassFactory::Release(void)

- ea: `0x180004bf0`
- end: `0x180004c11`
- name: `?Release@CProvisioningCommandsClassFactory@@UEAAKXZ`
- size: `33`
- prototype: `__int64 __fastcall(CProvisioningCommandsClassFactory *this)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004bf0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004c03`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004c03`

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
0x180004bf0  push    rbx
0x180004bf2  sub     rsp, 20h
0x180004bf6  or      ebx, 0FFFFFFFFh
0x180004bf9  lock xadd [rcx+8], ebx
0x180004bfe  sub     ebx, 1
0x180004c01  jnz     short loc_180004C09
0x180004c03  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004c09  mov     eax, ebx
0x180004c0b  add     rsp, 20h
0x180004c0f  pop     rbx
0x180004c10  retn
```
