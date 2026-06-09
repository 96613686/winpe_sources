# CRasDiagHelper::GetRepairInfo(tagPROBLEM_TYPE,ulong *,tagRepairInfo * *)

- ea: `0x180006fa0`
- end: `0x180006fbd`
- name: `?GetRepairInfo@CRasDiagHelper@@UEAAJW4tagPROBLEM_TYPE@@PEAKPEAPEAUtagRepairInfo@@@Z`
- size: `29`
- prototype: `int __fastcall(CRasDiagHelper *this, enum tagPROBLEM_TYPE, unsigned int *, struct tagRepairInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180006fa0`
- `0x180007f20`

## pseudocode

```c
int __fastcall CRasDiagHelper::GetRepairInfo(
        CRasDiagHelper *this,
        enum tagPROBLEM_TYPE a2,
        unsigned int *a3,
        struct tagRepairInfo **a4)
{
  int result; // eax

  result = -2147467263;
  if ( *((_DWORD *)this + 33) )
    return CRasDiagHelper::ShowInternetConnectWizard(this, a2, a3, a4);
  return result;
}

```

## disassembly

```asm
0x180006fa0  sub     rsp, 28h
0x180006fa4  cmp     dword ptr [rcx+84h], 0
0x180006fab  mov     eax, 80004001h
0x180006fb0  jz      short loc_180006FB7
0x180006fb2  call    ?ShowInternetConnectWizard@CRasDiagHelper@@AEAAJW4tagPROBLEM_TYPE@@PEAKPEAPEAUtagRepairInfo@@@Z; CRasDiagHelper::ShowInternetConnectWizard(tagPROBLEM_TYPE,ulong *,tagRepairInfo * *)
0x180006fb7  add     rsp, 28h
0x180006fbb  retn
```
