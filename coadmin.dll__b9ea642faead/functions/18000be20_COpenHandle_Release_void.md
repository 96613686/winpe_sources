# COpenHandle::Release(void *)

- ea: `0x18000be20`
- end: `0x18000be5e`
- name: `?Release@COpenHandle@@QEAAXPEAX@Z`
- size: `62`
- prototype: `void(COpenHandle *__hidden this, void *)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003160`
- `0x180004dd0`
- `0x180005048`
- `0x1800063c0`
- `0x18000716c`
- `0x180007f40`
- `0x18000f30c`

## callees

- `0x1800042bc`
- `0x18000b08c`
- `0x18000be20`

## pseudocode

```c
void __fastcall COpenHandle::Release(COpenHandle *this, void *a2)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 3, 0xFFFFFFFF) == 1 )
  {
    AdminAclNotifyClose(a2, *((_DWORD *)this + 2));
    CADMCOMW::DeleteNode((CADMCOMW *)a2, *((_DWORD *)this + 2));
  }
}

```

## disassembly

```asm
0x18000be20  mov     [rsp+arg_0], rbx
0x18000be25  push    rdi
0x18000be26  sub     rsp, 20h
0x18000be2a  mov     rdi, rdx
0x18000be2d  mov     rbx, rcx
0x18000be30  or      eax, 0FFFFFFFFh
0x18000be33  lock xadd [rcx+0Ch], eax
0x18000be38  cmp     eax, 1
0x18000be3b  jnz     short loc_18000BE53
0x18000be3d  mov     edx, [rcx+8]; unsigned int
0x18000be40  mov     rcx, rdi; void *
0x18000be43  call    ?AdminAclNotifyClose@@YAHPEAXK@Z; AdminAclNotifyClose(void *,ulong)
0x18000be48  mov     edx, [rbx+8]; unsigned int
0x18000be4b  mov     rcx, rdi; this
0x18000be4e  call    ?DeleteNode@CADMCOMW@@QEAAKK@Z; CADMCOMW::DeleteNode(ulong)
0x18000be53  mov     rbx, [rsp+28h+arg_0]
0x18000be58  add     rsp, 20h
0x18000be5c  pop     rdi
0x18000be5d  retn
```
