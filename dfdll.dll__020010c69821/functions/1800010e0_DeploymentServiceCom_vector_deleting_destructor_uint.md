# DeploymentServiceCom::`vector deleting destructor'(uint)

- ea: `0x1800010e0`
- end: `0x180001114`
- name: `??_EDeploymentServiceCom@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(DeploymentServiceCom *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18000108c`
- `0x1800010e0`
- `0x180012b30`

## pseudocode

```c
DeploymentServiceCom *__fastcall DeploymentServiceCom::`vector deleting destructor'(
        DeploymentServiceCom *this,
        char a2)
{
  DeploymentServiceCom::~DeploymentServiceCom(this);
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x28);
  return this;
}

```

## disassembly

```asm
0x1800010e0  mov     [rsp+arg_0], rbx
0x1800010e5  push    rdi
0x1800010e6  sub     rsp, 20h
0x1800010ea  mov     ebx, edx
0x1800010ec  mov     rdi, rcx
0x1800010ef  call    ??1DeploymentServiceCom@@UEAA@XZ; DeploymentServiceCom::~DeploymentServiceCom(void)
0x1800010f4  test    bl, 1
0x1800010f7  jz      short loc_180001106
0x1800010f9  mov     edx, 28h ; '('; struct std::nothrow_t *
0x1800010fe  mov     rcx, rdi; void *
0x180001101  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180001106  mov     rbx, [rsp+28h+arg_0]
0x18000110b  mov     rax, rdi
0x18000110e  add     rsp, 20h
0x180001112  pop     rdi
0x180001113  retn
```
