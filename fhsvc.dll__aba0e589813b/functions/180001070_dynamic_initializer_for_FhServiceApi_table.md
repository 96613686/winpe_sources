# _dynamic_initializer_for__FhServiceApi_table__

- ea: `0x180001070`
- end: `0x1800010be`
- name: `_dynamic_initializer_for__FhServiceApi_table__`
- size: `78`
- prototype: `void (__stdcall *())(PRPC_MESSAGE pRpcMsg)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `RPCRT4!NdrServerCall2` at `0x180001070`

## pseudocode

```c
void (__stdcall *dynamic_initializer_for__FhServiceApi_table__())(PRPC_MESSAGE pRpcMsg)
{
  void (__stdcall *result)(PRPC_MESSAGE); // rax

  result = NdrServerCall2;
  qword_180019B20 = (__int64)NdrServerCall2;
  qword_180019B28 = (__int64)NdrServerCall2;
  qword_180019B30 = (__int64)NdrServerCall2;
  qword_180019B38 = (__int64)NdrServerCall2;
  qword_180019B40 = (__int64)NdrServerCall2;
  qword_180019B48 = (__int64)NdrServerCall2;
  qword_180019B50 = (__int64)NdrServerCall2;
  qword_180019B58 = (__int64)NdrServerCall2;
  qword_180019B60 = (__int64)NdrServerCall2;
  qword_180019B68 = (__int64)NdrServerCall2;
  return result;
}

```

## disassembly

```asm
0x180001070  mov     rax, cs:__imp_NdrServerCall2
0x180001077  mov     cs:qword_180019B20, rax
0x18000107e  mov     cs:qword_180019B28, rax
0x180001085  mov     cs:qword_180019B30, rax
0x18000108c  mov     cs:qword_180019B38, rax
0x180001093  mov     cs:qword_180019B40, rax
0x18000109a  mov     cs:qword_180019B48, rax
0x1800010a1  mov     cs:qword_180019B50, rax
0x1800010a8  mov     cs:qword_180019B58, rax
0x1800010af  mov     cs:qword_180019B60, rax
0x1800010b6  mov     cs:qword_180019B68, rax
0x1800010bd  retn
```
