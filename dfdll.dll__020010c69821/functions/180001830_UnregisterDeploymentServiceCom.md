# UnregisterDeploymentServiceCom

- ea: `0x180001830`
- end: `0x180001872`
- name: `UnregisterDeploymentServiceCom`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800015ac`
- `0x180001830`
- `0x18001efd0`

## import_xrefs

- `ole32!CoRevokeClassObject` at `0x180001842`
- `ole32!CoRevokeClassObject` at `0x180001842`

## pseudocode

```c
__int64 UnregisterDeploymentServiceCom()
{
  unsigned int v0; // ebx

  v0 = 0;
  if ( regID )
    v0 = CoRevokeClassObject(regID);
  if ( iCF )
    ((void (__fastcall *)(LPUNKNOWN))iCF->lpVtbl->Release)(iCF);
  DeploymentServiceCom::SetCreateManagedDeploymentServiceComFunction(0);
  return v0;
}

```

## disassembly

```asm
0x180001830  push    rbx
0x180001832  sub     rsp, 20h
0x180001836  mov     ecx, cs:?regID@@3KA; dwRegister
0x18000183c  xor     ebx, ebx
0x18000183e  test    ecx, ecx
0x180001840  jz      short loc_18000184A
0x180001842  call    cs:__imp_CoRevokeClassObject
0x180001848  mov     ebx, eax
0x18000184a  mov     rcx, cs:?iCF@@3PEAUIClassFactory@@EA; IClassFactory * iCF
0x180001851  test    rcx, rcx
0x180001854  jz      short loc_180001863
0x180001856  mov     rdx, [rcx]
0x180001859  mov     rax, [rdx+10h]
0x18000185d  call    cs:__guard_dispatch_icall_fptr
0x180001863  xor     ecx, ecx; struct IManagedDeploymentServiceCom *(*)(void)
0x180001865  call    ?SetCreateManagedDeploymentServiceComFunction@DeploymentServiceCom@@SAXP6APEAUIManagedDeploymentServiceCom@@XZ@Z; DeploymentServiceCom::SetCreateManagedDeploymentServiceComFunction(IManagedDeploymentServiceCom * (*)(void))
0x18000186a  mov     eax, ebx
0x18000186c  add     rsp, 20h
0x180001870  pop     rbx
0x180001871  retn
```
