# BripCleanupBindingTable

- ea: `0x180008ca8`
- end: `0x180008d8f`
- name: `BripCleanupBindingTable`
- size: `231`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004350`
- `0x180006ec0`

## callees

- `0x180003850`
- `0x180008ca8`
- `0x180008ed0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008d7e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008d7e`
- `ntdll!RtlDeleteHashTable` at `0x180008d5c`
- `ntdll!RtlDeleteHashTable` at `0x180008d5c`
- `ntdll!RtlInitEnumerationHashTable` at `0x180008ce7`
- `ntdll!RtlInitEnumerationHashTable` at `0x180008ce7`
- `ntdll!RtlRemoveEntryHashTable` at `0x180008d1b`
- `ntdll!RtlRemoveEntryHashTable` at `0x180008d1b`
- `ntdll!RtlEndEnumerationHashTable` at `0x180008d4f`
- `ntdll!RtlEndEnumerationHashTable` at `0x180008d4f`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180008cfd`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180008d2d`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180008cfd`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180008d2d`

## pseudocode

```c
__int64 BripCleanupBindingTable()
{
  __int64 v0; // rdi
  __int64 v1; // rax
  __int64 v2; // rcx
  _OWORD v4[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v5; // [rsp+40h] [rbp-18h]

  memset(v4, 0, sizeof(v4));
  v5 = 0;
  EaLibAcquireLockExclusive(&BrokerBindingTableLock);
  if ( BrokerBindingTable )
  {
    if ( (unsigned __int8)RtlInitEnumerationHashTable(BrokerBindingTable, v4) )
    {
      v0 = RtlEnumerateEntryHashTable(BrokerBindingTable, v4);
      while ( v0 )
      {
        RtlRemoveEntryHashTable(BrokerBindingTable, v0, 0);
        v1 = RtlEnumerateEntryHashTable(BrokerBindingTable, v4);
        v2 = v0;
        v0 = v1;
        BripFreeBindingContext(v2);
      }
      RtlEndEnumerationHashTable(BrokerBindingTable, v4);
    }
    RtlDeleteHashTable(BrokerBindingTable);
    BrokerBindingTable = 0;
  }
  dword_180012198 = 0;
  return RtlReleaseSRWLockExclusive(&BrokerBindingTableLock);
}

```

## disassembly

```asm
0x180008ca8  mov     [rsp+arg_0], rbx
0x180008cad  push    rdi
0x180008cae  sub     rsp, 50h
0x180008cb2  xorps   xmm0, xmm0
0x180008cb5  lea     rcx, BrokerBindingTableLock
0x180008cbc  xor     eax, eax
0x180008cbe  movups  [rsp+58h+var_38], xmm0
0x180008cc3  mov     [rsp+58h+var_18], rax
0x180008cc8  movups  [rsp+58h+var_28], xmm0
0x180008ccd  call    EaLibAcquireLockExclusive
0x180008cd2  mov     rcx, cs:BrokerBindingTable
0x180008cd9  test    rcx, rcx
0x180008cdc  jz      loc_180008D6D
0x180008ce2  lea     rdx, [rsp+58h+var_38]
0x180008ce7  call    cs:__imp_RtlInitEnumerationHashTable
0x180008ced  test    al, al
0x180008cef  jz      short loc_180008D55
0x180008cf1  mov     rcx, cs:BrokerBindingTable
0x180008cf8  lea     rdx, [rsp+58h+var_38]
0x180008cfd  call    cs:__imp_RtlEnumerateEntryHashTable
0x180008d03  mov     rdi, rax
0x180008d06  test    rax, rax
0x180008d09  jz      short loc_180008D43
0x180008d0b  mov     rcx, cs:BrokerBindingTable
0x180008d12  xor     r8d, r8d
0x180008d15  mov     rdx, rdi
0x180008d18  mov     rbx, rdi
0x180008d1b  call    cs:__imp_RtlRemoveEntryHashTable
0x180008d21  mov     rcx, cs:BrokerBindingTable
0x180008d28  lea     rdx, [rsp+58h+var_38]
0x180008d2d  call    cs:__imp_RtlEnumerateEntryHashTable
0x180008d33  mov     rcx, rbx
0x180008d36  mov     rdi, rax
0x180008d39  call    BripFreeBindingContext
0x180008d3e  test    rdi, rdi
0x180008d41  jnz     short loc_180008D0B
0x180008d43  mov     rcx, cs:BrokerBindingTable
0x180008d4a  lea     rdx, [rsp+58h+var_38]
0x180008d4f  call    cs:__imp_RtlEndEnumerationHashTable
0x180008d55  mov     rcx, cs:BrokerBindingTable
0x180008d5c  call    cs:__imp_RtlDeleteHashTable
0x180008d62  mov     cs:BrokerBindingTable, 0
0x180008d6d  lea     rcx, BrokerBindingTableLock
0x180008d74  mov     cs:dword_180012198, 0
0x180008d7e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180008d84  mov     rbx, [rsp+58h+arg_0]
0x180008d89  add     rsp, 50h
0x180008d8d  pop     rdi
0x180008d8e  retn
```
