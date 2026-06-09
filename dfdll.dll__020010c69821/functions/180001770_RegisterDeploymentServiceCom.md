# RegisterDeploymentServiceCom

- ea: `0x180001770`
- end: `0x180001826`
- name: `RegisterDeploymentServiceCom`
- size: `182`
- prototype: `__int64 __fastcall(struct IManagedDeploymentServiceCom *(*)(void))`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800015ac`
- `0x1800015b4`
- `0x180001770`
- `0x180012bf4`
- `0x18001efd0`

## import_xrefs

- `ole32!CoRegisterClassObject` at `0x1800017fe`
- `ole32!CoRegisterClassObject` at `0x1800017fe`

## pseudocode

```c
__int64 __fastcall RegisterDeploymentServiceCom(struct IManagedDeploymentServiceCom *(*a1)(void))
{
  DeploymentServiceComClassFactory *v2; // rax
  DeploymentServiceComClassFactory *v3; // rcx
  HRESULT v4; // ebx

  if ( !a1 )
    return 2147942487LL;
  DeploymentServiceCom::SetCreateManagedDeploymentServiceComFunction(a1);
  v2 = (DeploymentServiceComClassFactory *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v2 )
    v3 = DeploymentServiceComClassFactory::DeploymentServiceComClassFactory(v2);
  else
    v3 = 0;
  if ( !v3 )
    return 2147942414LL;
  (**(void (__fastcall ***)(DeploymentServiceComClassFactory *, GUID *, LPUNKNOWN *))v3)(v3, &IID_IClassFactory, &iCF);
  v4 = CoRegisterClassObject(&CLSID_DeploymentServiceComClass, iCF, 4u, 1u, &regID);
  if ( v4 < 0 )
    ((void (__fastcall *)(LPUNKNOWN))iCF->lpVtbl->Release)(iCF);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180001770  push    rbx
0x180001772  sub     rsp, 30h
0x180001776  test    rcx, rcx
0x180001779  jnz     short loc_180001785
0x18000177b  mov     eax, 80070057h
0x180001780  jmp     loc_180001820
0x180001785  call    ?SetCreateManagedDeploymentServiceComFunction@DeploymentServiceCom@@SAXP6APEAUIManagedDeploymentServiceCom@@XZ@Z; DeploymentServiceCom::SetCreateManagedDeploymentServiceComFunction(IManagedDeploymentServiceCom * (*)(void))
0x18000178a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180001791  mov     ecx, 10h; unsigned __int64
0x180001796  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000179b  mov     [rsp+38h+arg_0], rax
0x1800017a0  test    rax, rax
0x1800017a3  jz      short loc_1800017B2
0x1800017a5  mov     rcx, rax; this
0x1800017a8  call    ??0DeploymentServiceComClassFactory@@QEAA@XZ; DeploymentServiceComClassFactory::DeploymentServiceComClassFactory(void)
0x1800017ad  mov     rcx, rax
0x1800017b0  jmp     short loc_1800017B4
0x1800017b2  xor     ecx, ecx
0x1800017b4  test    rcx, rcx
0x1800017b7  jnz     short loc_1800017C0
0x1800017b9  mov     eax, 8007000Eh
0x1800017be  jmp     short loc_180001820
0x1800017c0  mov     rax, [rcx]
0x1800017c3  lea     r8, ?iCF@@3PEAUIClassFactory@@EA; IClassFactory * iCF
0x1800017ca  lea     rdx, IID_IClassFactory
0x1800017d1  mov     rax, [rax]
0x1800017d4  call    cs:__guard_dispatch_icall_fptr
0x1800017da  lea     rax, ?regID@@3KA; ulong regID
0x1800017e1  mov     [rsp+38h+lpdwRegister], rax; lpdwRegister
0x1800017e6  mov     r9d, 1; flags
0x1800017ec  lea     r8d, [r9+3]; dwClsContext
0x1800017f0  mov     rdx, cs:?iCF@@3PEAUIClassFactory@@EA; pUnk
0x1800017f7  lea     rcx, CLSID_DeploymentServiceComClass; rclsid
0x1800017fe  call    cs:__imp_CoRegisterClassObject
0x180001804  mov     ebx, eax
0x180001806  test    eax, eax
0x180001808  jns     short loc_18000181E
0x18000180a  mov     rcx, cs:?iCF@@3PEAUIClassFactory@@EA; IClassFactory * iCF
0x180001811  mov     rdx, [rcx]
0x180001814  mov     rax, [rdx+10h]
0x180001818  call    cs:__guard_dispatch_icall_fptr
0x18000181e  mov     eax, ebx
0x180001820  add     rsp, 30h
0x180001824  pop     rbx
0x180001825  retn
```
