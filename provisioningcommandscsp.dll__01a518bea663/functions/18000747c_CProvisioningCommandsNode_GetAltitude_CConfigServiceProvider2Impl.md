# CProvisioningCommandsNode::GetAltitude(CConfigServiceProvider2Impl *)

- ea: `0x18000747c`
- end: `0x1800074be`
- name: `?GetAltitude@CProvisioningCommandsNode@@CAKPEAVCConfigServiceProvider2Impl@@@Z`
- size: `66`
- prototype: `unsigned int __fastcall(struct CConfigServiceProvider2Impl *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006b10`

## callees

- `0x18000747c`
- `0x180007530`

## import_xrefs

- `msvcrt!wcstoul` at `0x1800074ae`
- `msvcrt!wcstoul` at `0x1800074ae`

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
0x18000747c  sub     rsp, 48h
0x180007480  xorps   xmm0, xmm0
0x180007483  xor     eax, eax
0x180007485  movups  xmmword ptr [rsp+48h+String], xmm0
0x18000748a  mov     [rsp+48h+var_18], rax
0x18000748f  lea     r8, [rsp+48h+String]; struct tagVARIANT *
0x180007494  mov     rdx, rcx; struct CConfigServiceProvider2Impl *
0x180007497  lea     rcx, ?gc_wszPackageAltitude@@3QBGB; "PackageAltitude"
0x18000749e  call    ?GetSessionVariableFromCsp@CProvisioningCommandsNode@@CAXPEBGPEAVCConfigServiceProvider2Impl@@PEAUtagVARIANT@@@Z; CProvisioningCommandsNode::GetSessionVariableFromCsp(ushort const *,CConfigServiceProvider2Impl *,tagVARIANT *)
0x1800074a3  xor     edx, edx; EndPtr
0x1800074a5  lea     r8d, [rdx+0Ah]; Radix
0x1800074a9  mov     rcx, [rsp+48h+String+8]; String
0x1800074ae  call    cs:__imp_wcstoul
0x1800074b4  jmp     short loc_1800074B8
0x1800074b6  xor     eax, eax
0x1800074b8  add     rsp, 48h
0x1800074bc  retn
```
