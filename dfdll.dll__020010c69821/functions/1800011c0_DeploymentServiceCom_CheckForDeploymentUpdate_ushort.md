# DeploymentServiceCom::CheckForDeploymentUpdate(ushort *)

- ea: `0x1800011c0`
- end: `0x1800011dd`
- name: `?CheckForDeploymentUpdate@DeploymentServiceCom@@UEAAJPEAG@Z`
- size: `29`
- prototype: `__int64 __fastcall(DeploymentServiceCom *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800011c0`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall DeploymentServiceCom::CheckForDeploymentUpdate(DeploymentServiceCom *this, unsigned __int16 *a2)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 4);
  if ( v2 )
    return (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v2 + 56LL))(v2, a2);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x1800011c0  mov     rcx, [rcx+20h]
0x1800011c4  test    rcx, rcx
0x1800011c7  jnz     short loc_1800011CF
0x1800011c9  mov     eax, 80004005h
0x1800011ce  retn
0x1800011cf  mov     rax, [rcx]
0x1800011d2  mov     rax, [rax+38h]
0x1800011d6  jmp     cs:__guard_dispatch_icall_fptr
```
