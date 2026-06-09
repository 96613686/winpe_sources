# DeploymentServiceCom::QueryInterface(_GUID const &,void * *)

- ea: `0x1800014d0`
- end: `0x18000155c`
- name: `?QueryInterface@DeploymentServiceCom@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `140`
- prototype: `__int64 __fastcall(DeploymentServiceCom *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180001560`

## callees

- `0x1800014d0`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall DeploymentServiceCom::QueryInterface(DeploymentServiceCom *this, const struct _GUID *a2, void **a3)
{
  if ( !a3 )
    return 2147500035LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
    goto LABEL_10;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IDispatch.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IDispatch.Data4 )
  {
    this = (DeploymentServiceCom *)(((unsigned __int64)this + 8) & -(__int64)(this != 0));
LABEL_10:
    *a3 = this;
    (*(void (__fastcall **)(DeploymentServiceCom *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IDeploymentServiceCom.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IDeploymentServiceCom.Data4 )
  {
    goto LABEL_10;
  }
  *a3 = 0;
  return 2147500034LL;
}

```

## disassembly

```asm
0x1800014d0  sub     rsp, 28h
0x1800014d4  test    r8, r8
0x1800014d7  jnz     short loc_1800014E0
0x1800014d9  mov     eax, 80004003h
0x1800014de  jmp     short loc_180001557
0x1800014e0  mov     rax, [rdx]
0x1800014e3  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1800014ea  jnz     short loc_1800014F9
0x1800014ec  mov     rax, [rdx+8]
0x1800014f0  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1800014f7  jz      short loc_18000153A
0x1800014f9  mov     rax, [rdx]
0x1800014fc  cmp     rax, qword ptr cs:IID_IDispatch.Data1
0x180001503  jnz     short loc_180001521
0x180001505  mov     rax, [rdx+8]
0x180001509  cmp     rax, qword ptr cs:IID_IDispatch.Data4
0x180001510  jnz     short loc_180001521
0x180001512  lea     rax, [rcx+8]
0x180001516  neg     rcx
0x180001519  sbb     rcx, rcx
0x18000151c  and     rcx, rax
0x18000151f  jmp     short loc_18000153A
0x180001521  mov     rax, [rdx]
0x180001524  cmp     rax, qword ptr cs:IID_IDeploymentServiceCom.Data1
0x18000152b  jnz     short loc_18000154E
0x18000152d  mov     rax, [rdx+8]
0x180001531  cmp     rax, qword ptr cs:IID_IDeploymentServiceCom.Data4
0x180001538  jnz     short loc_18000154E
0x18000153a  mov     [r8], rcx
0x18000153d  mov     rax, [rcx]
0x180001540  mov     rax, [rax+8]
0x180001544  call    cs:__guard_dispatch_icall_fptr
0x18000154a  xor     eax, eax
0x18000154c  jmp     short loc_180001557
0x18000154e  and     qword ptr [r8], 0
0x180001552  mov     eax, 80004002h
0x180001557  add     rsp, 28h
0x18000155b  retn
```
