# BrpInitOnceRunOnceCallback

- ea: `0x180008f10`
- end: `0x180008fa7`
- name: `BrpInitOnceRunOnceCallback`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004310`
- `0x180008f10`

## import_xrefs

- `ntdll!RtlDeleteHashTable` at `0x180008f68`
- `ntdll!RtlDeleteHashTable` at `0x180008f81`
- `ntdll!RtlDeleteHashTable` at `0x180008f68`
- `ntdll!RtlDeleteHashTable` at `0x180008f81`
- `ntdll!RtlCreateHashTable` at `0x180008f2e`
- `ntdll!RtlCreateHashTable` at `0x180008f50`
- `ntdll!RtlCreateHashTable` at `0x180008f2e`
- `ntdll!RtlCreateHashTable` at `0x180008f50`

## pseudocode

```c
__int64 BrpInitOnceRunOnceCallback()
{
  unsigned int v0; // ebx

  EaLibLockInitialize(&BrokerBindingTableLock);
  if ( (unsigned __int8)RtlCreateHashTable(&BrokerBindingTable, 0, 0)
    && (EaLibLockInitialize(&BrokeredEventTableLock), (unsigned __int8)RtlCreateHashTable(&BrokeredEventTable, 0, 0)) )
  {
    v0 = 1;
    BrokerInternalClientInitialized = 1;
  }
  else
  {
    v0 = 0;
    if ( BrokerBindingTable )
    {
      RtlDeleteHashTable();
      BrokerBindingTable = 0;
    }
    if ( BrokeredEventTable )
    {
      RtlDeleteHashTable();
      BrokeredEventTable = 0;
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180008f10  push    rbx
0x180008f12  sub     rsp, 20h
0x180008f16  lea     rcx, BrokerBindingTableLock
0x180008f1d  call    EaLibLockInitialize
0x180008f22  xor     r8d, r8d
0x180008f25  lea     rcx, BrokerBindingTable
0x180008f2c  xor     edx, edx
0x180008f2e  call    cs:__imp_RtlCreateHashTable
0x180008f34  test    al, al
0x180008f36  jz      short loc_180008F5A
0x180008f38  lea     rcx, BrokeredEventTableLock
0x180008f3f  call    EaLibLockInitialize
0x180008f44  xor     r8d, r8d
0x180008f47  lea     rcx, BrokeredEventTable
0x180008f4e  xor     edx, edx
0x180008f50  call    cs:__imp_RtlCreateHashTable
0x180008f56  test    al, al
0x180008f58  jnz     short loc_180008F94
0x180008f5a  mov     rcx, cs:BrokerBindingTable
0x180008f61  xor     ebx, ebx
0x180008f63  test    rcx, rcx
0x180008f66  jz      short loc_180008F75
0x180008f68  call    cs:__imp_RtlDeleteHashTable
0x180008f6e  mov     cs:BrokerBindingTable, rbx
0x180008f75  mov     rcx, cs:BrokeredEventTable
0x180008f7c  test    rcx, rcx
0x180008f7f  jz      short loc_180008F9F
0x180008f81  call    cs:__imp_RtlDeleteHashTable
0x180008f87  mov     cs:BrokeredEventTable, 0
0x180008f92  jmp     short loc_180008F9F
0x180008f94  mov     ebx, 1
0x180008f99  mov     cs:BrokerInternalClientInitialized, bl
0x180008f9f  mov     eax, ebx
0x180008fa1  add     rsp, 20h
0x180008fa5  pop     rbx
0x180008fa6  retn
```
