# _dynamic_initializer_for__FhServiceApi_NDR64__table__

- ea: `0x180001010`
- end: `0x18000105e`
- name: `_dynamic_initializer_for__FhServiceApi_NDR64__table__`
- size: `78`
- prototype: `void (__stdcall *())(PRPC_MESSAGE pRpcMsg)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `RPCRT4!NdrServerCallAll` at `0x180001010`

## pseudocode

```c
void (__stdcall *dynamic_initializer_for__FhServiceApi_NDR64__table__())(PRPC_MESSAGE pRpcMsg)
{
  void (__stdcall *result)(PRPC_MESSAGE); // rax

  result = NdrServerCallAll;
  qword_180019B80 = (__int64)NdrServerCallAll;
  qword_180019B88 = (__int64)NdrServerCallAll;
  qword_180019B90 = (__int64)NdrServerCallAll;
  qword_180019B98 = (__int64)NdrServerCallAll;
  qword_180019BA0 = (__int64)NdrServerCallAll;
  qword_180019BA8 = (__int64)NdrServerCallAll;
  qword_180019BB0 = (__int64)NdrServerCallAll;
  qword_180019BB8 = (__int64)NdrServerCallAll;
  qword_180019BC0 = (__int64)NdrServerCallAll;
  qword_180019BC8 = (__int64)NdrServerCallAll;
  return result;
}

```

## disassembly

```asm
0x180001010  mov     rax, cs:__imp_NdrServerCallAll
0x180001017  mov     cs:qword_180019B80, rax
0x18000101e  mov     cs:qword_180019B88, rax
0x180001025  mov     cs:qword_180019B90, rax
0x18000102c  mov     cs:qword_180019B98, rax
0x180001033  mov     cs:qword_180019BA0, rax
0x18000103a  mov     cs:qword_180019BA8, rax
0x180001041  mov     cs:qword_180019BB0, rax
0x180001048  mov     cs:qword_180019BB8, rax
0x18000104f  mov     cs:qword_180019BC0, rax
0x180001056  mov     cs:qword_180019BC8, rax
0x18000105d  retn
```
