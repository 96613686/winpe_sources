# DeploymentServiceCom::MaintainSubscription(ushort *)

- ea: `0x1800014b0`
- end: `0x1800014cd`
- name: `?MaintainSubscription@DeploymentServiceCom@@UEAAJPEAG@Z`
- size: `29`
- prototype: `__int64 __fastcall(DeploymentServiceCom *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800014b0`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall DeploymentServiceCom::MaintainSubscription(DeploymentServiceCom *this, unsigned __int16 *a2)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 4);
  if ( v2 )
    return (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v2 + 48LL))(v2, a2);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x1800014b0  mov     rcx, [rcx+20h]
0x1800014b4  test    rcx, rcx
0x1800014b7  jnz     short loc_1800014BF
0x1800014b9  mov     eax, 80004005h
0x1800014be  retn
0x1800014bf  mov     rax, [rcx]
0x1800014c2  mov     rax, [rax+30h]
0x1800014c6  jmp     cs:__guard_dispatch_icall_fptr
```
