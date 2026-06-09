# GetProxyDllInfo

- ea: `0x180001a10`
- end: `0x180001a34`
- name: `GetProxyDllInfo`
- size: `36`
- prototype: `PCInterfaceStubVtblList __fastcall(_QWORD *, PCInterfaceStubVtblList *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001a10`

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
0x180001a10  lea     rax, aProxyFileList
0x180001a17  mov     [rcx], rax
0x180001a1a  mov     rax, cs:aProxyFileList
0x180001a21  mov     rcx, [rax+8]
0x180001a25  mov     rax, [rcx]
0x180001a28  test    rax, rax
0x180001a2b  jz      short loc_180001A30
0x180001a2d  mov     rax, [rax]
0x180001a30  mov     [rdx], rax
0x180001a33  retn
```
