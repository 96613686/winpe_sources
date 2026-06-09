# DeploymentServiceCom::AddRef(void)

- ea: `0x1800011a0`
- end: `0x1800011ad`
- name: `?AddRef@DeploymentServiceCom@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(DeploymentServiceCom *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800011b0`

## pseudocode

```c
__int64 __fastcall DeploymentServiceCom::AddRef(DeploymentServiceCom *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 4);
}

```

## disassembly

```asm
0x1800011a0  mov     eax, 1
0x1800011a5  lock xadd [rcx+10h], eax
0x1800011aa  inc     eax
0x1800011ac  retn
```
