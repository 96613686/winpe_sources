# DeploymentServiceCom::ActivateDeploymentEx(ushort *,long,long)

- ea: `0x180001170`
- end: `0x180001196`
- name: `?ActivateDeploymentEx@DeploymentServiceCom@@UEAAJPEAGJJ@Z`
- size: `38`
- prototype: `__int64 __fastcall(DeploymentServiceCom *__hidden this, unsigned __int16 *, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001170`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall DeploymentServiceCom::ActivateDeploymentEx(DeploymentServiceCom *this, unsigned __int16 *a2)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 4);
  if ( v2 )
    return (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v2 + 32LL))(v2, a2);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x180001170  sub     rsp, 38h
0x180001174  mov     rcx, [rcx+20h]
0x180001178  test    rcx, rcx
0x18000117b  jnz     short loc_180001184
0x18000117d  mov     eax, 80004005h
0x180001182  jmp     short loc_180001191
0x180001184  mov     rax, [rcx]
0x180001187  mov     rax, [rax+20h]
0x18000118b  call    cs:__guard_dispatch_icall_fptr
0x180001191  add     rsp, 38h
0x180001195  retn
```
