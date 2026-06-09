# DeploymentServiceCom::ActivateApplicationExtension(ushort *,ushort *,ushort *)

- ea: `0x180001120`
- end: `0x180001146`
- name: `?ActivateApplicationExtension@DeploymentServiceCom@@UEAAJPEAG00@Z`
- size: `38`
- prototype: `__int64 __fastcall(DeploymentServiceCom *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001120`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall DeploymentServiceCom::ActivateApplicationExtension(
        DeploymentServiceCom *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  __int64 v4; // rcx

  v4 = *((_QWORD *)this + 4);
  if ( v4 )
    return (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *))(*(_QWORD *)v4 + 40LL))(
             v4,
             a2,
             a3,
             a4);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x180001120  sub     rsp, 38h
0x180001124  mov     rcx, [rcx+20h]
0x180001128  test    rcx, rcx
0x18000112b  jnz     short loc_180001134
0x18000112d  mov     eax, 80004005h
0x180001132  jmp     short loc_180001141
0x180001134  mov     rax, [rcx]
0x180001137  mov     rax, [rax+28h]
0x18000113b  call    cs:__guard_dispatch_icall_fptr
0x180001141  add     rsp, 38h
0x180001145  retn
```
