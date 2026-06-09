# GetProxyDllInfo

- ea: `0x1800021d0`
- end: `0x1800021f4`
- name: `GetProxyDllInfo`
- size: `36`
- prototype: `PCInterfaceStubVtblList __fastcall(_QWORD *, PCInterfaceStubVtblList *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800021d0`

## pseudocode

```c
PCInterfaceStubVtblList __fastcall GetProxyDllInfo(_QWORD *a1, PCInterfaceStubVtblList *a2)
{
  PCInterfaceStubVtblList result; // rax

  *a1 = &aProxyFileList;
  result = *aProxyFileList->pStubVtblList;
  if ( result )
    result = (PCInterfaceStubVtblList)result->header.piid;
  *a2 = result;
  return result;
}

```

## disassembly

```asm
0x1800021d0  lea     rax, aProxyFileList
0x1800021d7  mov     [rcx], rax
0x1800021da  mov     rax, cs:aProxyFileList
0x1800021e1  mov     rcx, [rax+8]
0x1800021e5  mov     rax, [rcx]
0x1800021e8  test    rax, rax
0x1800021eb  jz      short loc_1800021F0
0x1800021ed  mov     rax, [rax]
0x1800021f0  mov     [rdx], rax
0x1800021f3  retn
```
