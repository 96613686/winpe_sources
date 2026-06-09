# CDPA_Base<ushort,CTContainer_PolicyCoTaskMem>::_StandardDestroyCB(ushort *,void *)

- ea: `0x14000c140`
- end: `0x14000c154`
- name: `?_StandardDestroyCB@?$CDPA_Base@GVCTContainer_PolicyCoTaskMem@@@@CAHPEAGPEAX@Z`
- size: `20`
- prototype: `int __stdcall(void *p, void *pData)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000c144`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000c144`

## pseudocode

```c
__int64 __fastcall CDPA_Base<unsigned short,CTContainer_PolicyCoTaskMem>::_StandardDestroyCB(void *p, void *pData)
{
  CoTaskMemFree(p);
  return 1;
}

```

## disassembly

```asm
0x14000c140  sub     rsp, 28h
0x14000c144  call    cs:__imp_CoTaskMemFree
0x14000c14a  mov     eax, 1
0x14000c14f  add     rsp, 28h
0x14000c153  retn
```
