# CProvisioningCommandsCSP::CreateInstance(void)

- ea: `0x1800061f0`
- end: `0x18000624a`
- name: `?CreateInstance@CProvisioningCommandsCSP@@SAPEAUIUnknown@@XZ`
- size: `90`
- prototype: `struct IUnknown *(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800016a4`
- `0x1800061f0`

## pseudocode

```c
struct IUnknown *CProvisioningCommandsCSP::CreateInstance(void)
{
  struct IUnknown *result; // rax

  result = (struct IUnknown *)operator new(0x30u);
  if ( result )
  {
    result[2].lpVtbl = 0;
    result[4].lpVtbl = (struct IUnknownVtbl *)nodeMap;
    result->lpVtbl = (struct IUnknownVtbl *)&CProvisioningCommandsCSP::`vftable'{for `IConfigServiceProvider2'};
    result[1].lpVtbl = (struct IUnknownVtbl *)&CProvisioningCommandsCSP::`vftable'{for `ICSPValidate'};
    LODWORD(result[3].lpVtbl) = 0;
    LODWORD(result[5].lpVtbl) = 1;
    _InterlockedIncrement(&dword_180014AB8);
  }
  return result;
}

```

## disassembly

```asm
0x1800061f0  sub     rsp, 28h
0x1800061f4  mov     ecx, 30h ; '0'; Size
0x1800061f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800061fe  mov     [rsp+28h+arg_0], rax
0x180006203  test    rax, rax
0x180006206  jz      short loc_180006245
0x180006208  lea     rcx, ?nodeMap@@3VProvisioningCommandsMap@@A; ProvisioningCommandsMap nodeMap
0x18000620f  mov     qword ptr [rax+10h], 0
0x180006217  mov     [rax+20h], rcx
0x18000621b  lea     rcx, ??_7CProvisioningCommandsCSP@@6BIConfigServiceProvider2@@@; const CProvisioningCommandsCSP::`vftable'{for `IConfigServiceProvider2'}
0x180006222  mov     [rax], rcx
0x180006225  lea     rcx, ??_7CProvisioningCommandsCSP@@6BICSPValidate@@@; const CProvisioningCommandsCSP::`vftable'{for `ICSPValidate'}
0x18000622c  mov     [rax+8], rcx
0x180006230  mov     dword ptr [rax+18h], 0
0x180006237  mov     dword ptr [rax+28h], 1
0x18000623e  lock inc cs:dword_180014AB8
0x180006245  add     rsp, 28h
0x180006249  retn
```
