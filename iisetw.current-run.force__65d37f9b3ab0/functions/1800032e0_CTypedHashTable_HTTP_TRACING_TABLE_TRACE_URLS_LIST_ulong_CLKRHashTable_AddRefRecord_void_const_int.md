# CTypedHashTable<HTTP_TRACING_TABLE,TRACE_URLS_LIST,ulong,CLKRHashTable>::_AddRefRecord(void const *,int)

- ea: `0x1800032e0`
- end: `0x1800032f3`
- name: `?_AddRefRecord@?$CTypedHashTable@VHTTP_TRACING_TABLE@@VTRACE_URLS_LIST@@KVCLKRHashTable@@@@CAXPEBXH@Z`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002428`
- `0x1800032e0`

## pseudocode

```c
void __fastcall CTypedHashTable<HTTP_TRACING_TABLE,TRACE_URLS_LIST,unsigned long,CLKRHashTable>::_AddRefRecord(
        volatile signed __int32 *a1,
        int a2)
{
  if ( a2 == -1 )
  {
    TRACE_URLS_LIST::Dereference((TRACE_URLS_LIST *)a1);
  }
  else if ( a2 == 1 )
  {
    _InterlockedIncrement(a1 + 4);
  }
}

```

## disassembly

```asm
0x1800032e0  cmp     edx, 0FFFFFFFFh
0x1800032e3  jz      ?Dereference@TRACE_URLS_LIST@@QEAAXXZ; TRACE_URLS_LIST::Dereference(void)
0x1800032e9  cmp     edx, 1
0x1800032ec  jnz     short locret_1800032F2
0x1800032ee  lock inc dword ptr [rcx+10h]
0x1800032f2  retn
```
