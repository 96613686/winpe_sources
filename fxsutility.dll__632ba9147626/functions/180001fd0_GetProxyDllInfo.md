# GetProxyDllInfo

- ea: `0x180001fd0`
- end: `0x180001ff4`
- name: `GetProxyDllInfo`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001fd0`

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
0x180001fd0  lea     rax, aProxyFileList
0x180001fd7  mov     [rcx], rax
0x180001fda  mov     rax, cs:aProxyFileList
0x180001fe1  mov     rcx, [rax+8]
0x180001fe5  mov     rax, [rcx]
0x180001fe8  test    rax, rax
0x180001feb  jz      short loc_180001FF0
0x180001fed  mov     rax, [rax]
0x180001ff0  mov     [rdx], rax
0x180001ff3  retn
```
