# DeploymentServiceCom::CleanOnlineAppCache(void)

- ea: `0x1800011e0`
- end: `0x1800011fd`
- name: `?CleanOnlineAppCache@DeploymentServiceCom@@UEAAJXZ`
- size: `29`
- prototype: `__int64 __fastcall(DeploymentServiceCom *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800011e0`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall DeploymentServiceCom::CleanOnlineAppCache(DeploymentServiceCom *this)
{
  __int64 v1; // rcx

  v1 = *((_QWORD *)this + 4);
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 72LL))(v1);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x1800011e0  mov     rcx, [rcx+20h]
0x1800011e4  test    rcx, rcx
0x1800011e7  jnz     short loc_1800011EF
0x1800011e9  mov     eax, 80004005h
0x1800011ee  retn
0x1800011ef  mov     rax, [rcx]
0x1800011f2  mov     rax, [rax+48h]
0x1800011f6  jmp     cs:__guard_dispatch_icall_fptr
```
