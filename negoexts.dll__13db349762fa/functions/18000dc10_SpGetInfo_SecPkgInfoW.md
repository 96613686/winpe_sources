# SpGetInfo(_SecPkgInfoW *)

- ea: `0x18000dc10`
- end: `0x18000dc3f`
- name: `?SpGetInfo@@YAJPEAU_SecPkgInfoW@@@Z`
- size: `47`
- prototype: `__int64 __fastcall(struct _SecPkgInfoW *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x18000dc31`: `NegoExtender Security Package`

## pseudocode

```c
__int64 __fastcall SpGetInfo(struct _SecPkgInfoW *a1)
{
  *(_DWORD *)&a1->wVersion = 1966081;
  a1->fCapabilities = 9517331;
  a1->cbMaxToken = WSTGlobalMaxTokenSize;
  a1->Name = (SEC_WCHAR *)L"NegoExtender";
  a1->Comment = L"NegoExtender Security Package";
  return 0;
}

```

## disassembly

```asm
0x18000dc10  mov     dword ptr [rcx+4], 1E0001h
0x18000dc17  mov     dword ptr [rcx], 913913h
0x18000dc1d  mov     eax, cs:?WSTGlobalMaxTokenSize@@3KA; ulong WSTGlobalMaxTokenSize
0x18000dc23  mov     [rcx+8], eax
0x18000dc26  lea     rax, SourceString; "NegoExtender"
0x18000dc2d  mov     [rcx+10h], rax
0x18000dc31  lea     rax, aNegoextenderSe; "NegoExtender Security Package"
0x18000dc38  mov     [rcx+18h], rax
0x18000dc3c  xor     eax, eax
0x18000dc3e  retn
```
