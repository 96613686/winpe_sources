# DeploymentServiceCom::~DeploymentServiceCom(void)

- ea: `0x18000108c`
- end: `0x1800010dd`
- name: `??1DeploymentServiceCom@@UEAA@XZ`
- size: `81`
- prototype: `void __fastcall(DeploymentServiceCom *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800010e0`

## callees

- `0x18000108c`
- `0x18001efd0`

## pseudocode

```c
void __fastcall DeploymentServiceCom::~DeploymentServiceCom(DeploymentServiceCom *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &DeploymentServiceCom::`vftable'{for `IDeploymentServiceCom'};
  *((_QWORD *)this + 1) = &DeploymentServiceCom::`vftable'{for `IDispatch'};
  v2 = *((_QWORD *)this + 4);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 3);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
}

```

## disassembly

```asm
0x18000108c  push    rbx
0x18000108e  sub     rsp, 20h
0x180001092  mov     rbx, rcx
0x180001095  lea     rax, ??_7DeploymentServiceCom@@6BIDeploymentServiceCom@@@; const DeploymentServiceCom::`vftable'{for `IDeploymentServiceCom'}
0x18000109c  mov     [rcx], rax
0x18000109f  lea     rax, ??_7DeploymentServiceCom@@6BIDispatch@@@; const DeploymentServiceCom::`vftable'{for `IDispatch'}
0x1800010a6  mov     [rcx+8], rax
0x1800010aa  mov     rcx, [rcx+20h]
0x1800010ae  test    rcx, rcx
0x1800010b1  jz      short loc_1800010C0
0x1800010b3  mov     rax, [rcx]
0x1800010b6  mov     rax, [rax+10h]
0x1800010ba  call    cs:__guard_dispatch_icall_fptr
0x1800010c0  mov     rcx, [rbx+18h]
0x1800010c4  test    rcx, rcx
0x1800010c7  jz      short loc_1800010D7
0x1800010c9  mov     rax, [rcx]
0x1800010cc  mov     rax, [rax+10h]
0x1800010d0  call    cs:__guard_dispatch_icall_fptr
0x1800010d6  nop
0x1800010d7  add     rsp, 20h
0x1800010db  pop     rbx
0x1800010dc  retn
```
