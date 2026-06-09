# DeploymentServiceComClassFactory::`scalar deleting destructor'(uint)

- ea: `0x1800015d0`
- end: `0x1800015fb`
- name: `??_GDeploymentServiceComClassFactory@@UEAAPEAXI@Z`
- size: `43`
- prototype: `void *__fastcall(DeploymentServiceComClassFactory *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800015d0`
- `0x180012b30`

## pseudocode

```c
DeploymentServiceComClassFactory *__fastcall DeploymentServiceComClassFactory::`scalar deleting destructor'(
        DeploymentServiceComClassFactory *this,
        char a2)
{
  *(_QWORD *)this = &DeploymentServiceComClassFactory::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x10);
  return this;
}

```

## disassembly

```asm
0x1800015d0  push    rbx
0x1800015d2  sub     rsp, 20h
0x1800015d6  lea     rax, ??_7DeploymentServiceComClassFactory@@6B@; const DeploymentServiceComClassFactory::`vftable'
0x1800015dd  mov     rbx, rcx
0x1800015e0  mov     [rcx], rax
0x1800015e3  test    dl, 1
0x1800015e6  jz      short loc_1800015F2
0x1800015e8  mov     edx, 10h; struct std::nothrow_t *
0x1800015ed  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800015f2  mov     rax, rbx
0x1800015f5  add     rsp, 20h
0x1800015f9  pop     rbx
0x1800015fa  retn
```
