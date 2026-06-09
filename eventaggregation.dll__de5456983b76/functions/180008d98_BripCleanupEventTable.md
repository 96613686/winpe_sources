# BripCleanupEventTable

- ea: `0x180008d98`
- end: `0x180008ec7`
- name: `BripCleanupEventTable`
- size: `303`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004350`
- `0x180006ec0`

## callees

- `0x1800026f0`
- `0x180002e30`
- `0x180003850`
- `0x180004270`
- `0x1800042f0`
- `0x180008d98`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008eb1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180008eb1`
- `ntdll!RtlDeleteHashTable` at `0x180008e8f`
- `ntdll!RtlDeleteHashTable` at `0x180008e8f`
- `ntdll!RtlInitEnumerationHashTable` at `0x180008de4`
- `ntdll!RtlInitEnumerationHashTable` at `0x180008de4`
- `ntdll!RtlRemoveEntryHashTable` at `0x180008e1c`
- `ntdll!RtlRemoveEntryHashTable` at `0x180008e1c`
- `ntdll!RtlEndEnumerationHashTable` at `0x180008e82`
- `ntdll!RtlEndEnumerationHashTable` at `0x180008e82`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180008dfe`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180008e2e`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180008dfe`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180008e2e`

## pseudocode

```c
__int64 BripCleanupEventTable()
{
  __int64 v0; // rbx
  __int64 v1; // rdi
  _OWORD v3[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v4; // [rsp+40h] [rbp-18h]
  __int64 v5; // [rsp+60h] [rbp+8h] BYREF

  v5 = 0;
  memset(v3, 0, sizeof(v3));
  v4 = 0;
  EaLibAcquireLockExclusive(&BrokeredEventTableLock);
  if ( BrokeredEventTable )
  {
    if ( (unsigned __int8)RtlInitEnumerationHashTable(BrokeredEventTable, v3) )
    {
      v0 = RtlEnumerateEntryHashTable(BrokeredEventTable, v3);
      while ( v0 )
      {
        v1 = v0;
        RtlRemoveEntryHashTable(BrokeredEventTable, v0, 0);
        v0 = RtlEnumerateEntryHashTable(BrokeredEventTable, v3);
        if ( !(unsigned int)BripCreateRpcBindingHandle((void *)(v1 + 40)) )
          EapSystemBriDeleteEvent(v1 + 40, v5, 3, v1 + 24);
        EapSystemBriFreeRpcBindingHandle(&v5);
        EaLibFree(v1);
      }
      RtlEndEnumerationHashTable(BrokeredEventTable, v3);
    }
    RtlDeleteHashTable(BrokeredEventTable);
    BrokeredEventTable = 0;
  }
  dword_1800121A8 = 0;
  return RtlReleaseSRWLockExclusive(&BrokeredEventTableLock);
}

```

## disassembly

```asm
0x180008d98  mov     r11, rsp
0x180008d9b  mov     [r11+10h], rbx
0x180008d9f  mov     [r11+18h], rsi
0x180008da3  push    rdi
0x180008da4  sub     rsp, 50h
0x180008da8  xorps   xmm0, xmm0
0x180008dab  mov     qword ptr [r11+8], 0
0x180008db3  xor     eax, eax
0x180008db5  lea     rcx, BrokeredEventTableLock
0x180008dbc  movups  [rsp+58h+var_38], xmm0
0x180008dc1  movups  [rsp+58h+var_28], xmm0
0x180008dc6  mov     [r11-18h], rax
0x180008dca  call    EaLibAcquireLockExclusive
0x180008dcf  mov     rcx, cs:BrokeredEventTable
0x180008dd6  test    rcx, rcx
0x180008dd9  jz      loc_180008EA0
0x180008ddf  lea     rdx, [rsp+58h+var_38]
0x180008de4  call    cs:__imp_RtlInitEnumerationHashTable
0x180008dea  test    al, al
0x180008dec  jz      loc_180008E88
0x180008df2  mov     rcx, cs:BrokeredEventTable
0x180008df9  lea     rdx, [rsp+58h+var_38]
0x180008dfe  call    cs:__imp_RtlEnumerateEntryHashTable
0x180008e04  mov     rbx, rax
0x180008e07  test    rax, rax
0x180008e0a  jz      short loc_180008E76
0x180008e0c  mov     rcx, cs:BrokeredEventTable
0x180008e13  xor     r8d, r8d
0x180008e16  mov     rdx, rbx
0x180008e19  mov     rdi, rbx
0x180008e1c  call    cs:__imp_RtlRemoveEntryHashTable
0x180008e22  mov     rcx, cs:BrokeredEventTable
0x180008e29  lea     rdx, [rsp+58h+var_38]
0x180008e2e  call    cs:__imp_RtlEnumerateEntryHashTable
0x180008e34  lea     rdx, [rsp+58h+arg_0]
0x180008e39  mov     rbx, rax
0x180008e3c  lea     rcx, [rdi+28h]; Source1
0x180008e40  call    BripCreateRpcBindingHandle
0x180008e45  test    eax, eax
0x180008e47  jnz     short loc_180008E5F
0x180008e49  mov     rdx, [rsp+58h+arg_0]
0x180008e4e  lea     r9, [rdi+18h]
0x180008e52  lea     r8d, [rax+3]
0x180008e56  lea     rcx, [rdi+28h]
0x180008e5a  call    EapSystemBriDeleteEvent
0x180008e5f  lea     rcx, [rsp+58h+arg_0]
0x180008e64  call    EapSystemBriFreeRpcBindingHandle
0x180008e69  mov     rcx, rdi
0x180008e6c  call    EaLibFree
0x180008e71  test    rbx, rbx
0x180008e74  jnz     short loc_180008E0C
0x180008e76  mov     rcx, cs:BrokeredEventTable
0x180008e7d  lea     rdx, [rsp+58h+var_38]
0x180008e82  call    cs:__imp_RtlEndEnumerationHashTable
0x180008e88  mov     rcx, cs:BrokeredEventTable
0x180008e8f  call    cs:__imp_RtlDeleteHashTable
0x180008e95  mov     cs:BrokeredEventTable, 0
0x180008ea0  lea     rcx, BrokeredEventTableLock
0x180008ea7  mov     cs:dword_1800121A8, 0
0x180008eb1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180008eb7  mov     rbx, [rsp+58h+arg_8]
0x180008ebc  mov     rsi, [rsp+58h+arg_10]
0x180008ec1  add     rsp, 50h
0x180008ec5  pop     rdi
0x180008ec6  retn
```
