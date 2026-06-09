# DeploymentServiceCom::EndServiceRightNow(void)

- ea: `0x180001200`
- end: `0x18000121d`
- name: `?EndServiceRightNow@DeploymentServiceCom@@UEAAJXZ`
- size: `29`
- prototype: `__int64 __fastcall(DeploymentServiceCom *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001200`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall DeploymentServiceCom::EndServiceRightNow(DeploymentServiceCom *this)
{
  __int64 v1; // rcx

  v1 = *((_QWORD *)this + 4);
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 64LL))(v1);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x180001200  mov     rcx, [rcx+20h]
0x180001204  test    rcx, rcx
0x180001207  jnz     short loc_18000120F
0x180001209  mov     eax, 80004005h
0x18000120e  retn
0x18000120f  mov     rax, [rcx]
0x180001212  mov     rax, [rax+40h]
0x180001216  jmp     cs:__guard_dispatch_icall_fptr
```
