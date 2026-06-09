# CProvisioningCommandsNode::GetAltitude(CConfigServiceProvider2Impl *)

- ea: `0x1800077cc`
- end: `0x180007814`
- name: `?GetAltitude@CProvisioningCommandsNode@@CAKPEAVCConfigServiceProvider2Impl@@@Z`
- size: `72`
- prototype: `unsigned int __fastcall(struct CConfigServiceProvider2Impl *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006e40`

## callees

- `0x1800077cc`
- `0x180007888`

## import_xrefs

- `msvcrt!wcstoul` at `0x1800077fe`
- `msvcrt!wcstoul` at `0x1800077fe`

## pseudocode

```c
unsigned int __fastcall CProvisioningCommandsNode::GetAltitude(struct CConfigServiceProvider2Impl *a1)
{
  unsigned int result; // eax
  struct tagVARIANT String; // [rsp+20h] [rbp-28h] BYREF

  memset(&String, 0, sizeof(String));
  try
  {
    CProvisioningCommandsNode::GetSessionVariableFromCsp((OLECHAR *)L"PackageAltitude", a1, &String);
    result = wcstoul(String.bstrVal, 0, 10);
  }
  catch ( ... )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800077cc  sub     rsp, 48h
0x1800077d0  xorps   xmm0, xmm0
0x1800077d3  xor     eax, eax
0x1800077d5  movups  xmmword ptr [rsp+48h+String], xmm0
0x1800077da  mov     [rsp+48h+var_18], rax
0x1800077df  lea     r8, [rsp+48h+String]; struct tagVARIANT *
0x1800077e4  mov     rdx, rcx; struct CConfigServiceProvider2Impl *
0x1800077e7  lea     rcx, ?gc_wszPackageAltitude@@3QBGB; "PackageAltitude"
0x1800077ee  call    ?GetSessionVariableFromCsp@CProvisioningCommandsNode@@CAXPEBGPEAVCConfigServiceProvider2Impl@@PEAUtagVARIANT@@@Z; CProvisioningCommandsNode::GetSessionVariableFromCsp(ushort const *,CConfigServiceProvider2Impl *,tagVARIANT *)
0x1800077f3  xor     edx, edx; EndPtr
0x1800077f5  lea     r8d, [rdx+0Ah]; Radix
0x1800077f9  mov     rcx, [rsp+48h+String+8]; String
0x1800077fe  call    cs:__imp_wcstoul
0x180007805  nop     dword ptr [rax+rax+00h]
0x18000780a  jmp     short loc_18000780E
0x18000780c  xor     eax, eax
0x18000780e  add     rsp, 48h
0x180007812  retn
```
