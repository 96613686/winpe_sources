# DeploymentServiceCom::DeploymentServiceCom(void)

- ea: `0x180001040`
- end: `0x180001089`
- name: `??0DeploymentServiceCom@@QEAA@XZ`
- size: `73`
- prototype: `DeploymentServiceCom *__fastcall(DeploymentServiceCom *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180001610`

## callees

- `0x180001040`
- `0x18001efd0`

## pseudocode

```c
DeploymentServiceCom *__fastcall DeploymentServiceCom::DeploymentServiceCom(DeploymentServiceCom *this)
{
  struct IManagedDeploymentServiceCom *ManagedDeploymentServiceComFunction; // rax

  *(_QWORD *)this = &DeploymentServiceCom::`vftable'{for `IDeploymentServiceCom'};
  *((_QWORD *)this + 1) = &DeploymentServiceCom::`vftable'{for `IDispatch'};
  ManagedDeploymentServiceComFunction = 0;
  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 3) = 0;
  if ( DeploymentServiceCom::s_pCreateManagedDeploymentServiceComFunction )
    ManagedDeploymentServiceComFunction = DeploymentServiceCom::s_pCreateManagedDeploymentServiceComFunction();
  *((_QWORD *)this + 4) = ManagedDeploymentServiceComFunction;
  return this;
}

```

## disassembly

```asm
0x180001040  push    rbx
0x180001042  sub     rsp, 20h
0x180001046  lea     rax, ??_7DeploymentServiceCom@@6BIDeploymentServiceCom@@@; const DeploymentServiceCom::`vftable'{for `IDeploymentServiceCom'}
0x18000104d  mov     rbx, rcx
0x180001050  mov     [rcx], rax
0x180001053  lea     rax, ??_7DeploymentServiceCom@@6BIDispatch@@@; const DeploymentServiceCom::`vftable'{for `IDispatch'}
0x18000105a  mov     [rcx+8], rax
0x18000105e  xor     eax, eax
0x180001060  mov     [rcx+10h], eax
0x180001063  mov     [rcx+18h], rax
0x180001067  mov     rcx, cs:?s_pCreateManagedDeploymentServiceComFunction@DeploymentServiceCom@@0P6APEAUIManagedDeploymentServiceCom@@XZEA; IManagedDeploymentServiceCom * (*DeploymentServiceCom::s_pCreateManagedDeploymentServiceComFunction)(void)
0x18000106e  test    rcx, rcx
0x180001071  jz      short loc_18000107C
0x180001073  mov     rax, rcx
0x180001076  call    cs:__guard_dispatch_icall_fptr
0x18000107c  mov     [rbx+20h], rax
0x180001080  mov     rax, rbx
0x180001083  add     rsp, 20h
0x180001087  pop     rbx
0x180001088  retn
```
