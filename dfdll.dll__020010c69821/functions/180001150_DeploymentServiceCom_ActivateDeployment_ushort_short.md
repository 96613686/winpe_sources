# DeploymentServiceCom::ActivateDeployment(ushort *,short)

- ea: `0x180001150`
- end: `0x18000116d`
- name: `?ActivateDeployment@DeploymentServiceCom@@UEAAJPEAGF@Z`
- size: `29`
- prototype: `__int64 __fastcall(DeploymentServiceCom *this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001150`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall DeploymentServiceCom::ActivateDeployment(DeploymentServiceCom *this, unsigned __int16 *a2)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 4);
  if ( v2 )
    return (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v2 + 24LL))(v2, a2);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x180001150  mov     rcx, [rcx+20h]
0x180001154  test    rcx, rcx
0x180001157  jnz     short loc_18000115F
0x180001159  mov     eax, 80004005h
0x18000115e  retn
0x18000115f  mov     rax, [rcx]
0x180001162  mov     rax, [rax+18h]
0x180001166  jmp     cs:__guard_dispatch_icall_fptr
```
