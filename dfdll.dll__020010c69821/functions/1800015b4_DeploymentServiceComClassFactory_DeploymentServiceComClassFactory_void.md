# DeploymentServiceComClassFactory::DeploymentServiceComClassFactory(void)

- ea: `0x1800015b4`
- end: `0x1800015c6`
- name: `??0DeploymentServiceComClassFactory@@QEAA@XZ`
- size: `18`
- prototype: `DeploymentServiceComClassFactory *__fastcall(DeploymentServiceComClassFactory *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180001770`

## pseudocode

```c
DeploymentServiceComClassFactory *__fastcall DeploymentServiceComClassFactory::DeploymentServiceComClassFactory(
        DeploymentServiceComClassFactory *this)
{
  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &DeploymentServiceComClassFactory::`vftable';
  return this;
}

```

## disassembly

```asm
0x1800015b4  and     dword ptr [rcx+8], 0
0x1800015b8  lea     rax, ??_7DeploymentServiceComClassFactory@@6B@; const DeploymentServiceComClassFactory::`vftable'
0x1800015bf  mov     [rcx], rax
0x1800015c2  mov     rax, rcx
0x1800015c5  retn
```
