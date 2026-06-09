# FREB_LOG_NT_EVENT_TABLE::ScavengerCallback(void *,uchar)

- ea: `0x18000a8d0`
- end: `0x18000a90c`
- name: `?ScavengerCallback@FREB_LOG_NT_EVENT_TABLE@@CAXPEAXE@Z`
- size: `60`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x18000a901`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x18000a901`

## pseudocode

```c
void __fastcall FREB_LOG_NT_EVENT_TABLE::ScavengerCallback(char *a1)
{
  _QWORD v1[5]; // [rsp+20h] [rbp-28h] BYREF

  v1[1] = 0;
  v1[0] = &FREB_LOG_NT_EVENT_TABLE::CacheFlushByTTL;
  v1[2] = 0;
  CLKRHashTable::DeleteIf(
    (CLKRHashTable *)(a1 + 8),
    (enum LK_PREDICATE (__high *)(const void *, void *))CTypedHashTable<FREB_LOG_NT_EVENT_TABLE,FREB_LOG_NT_EVENT,unsigned short const *,CLKRHashTable>::_Pred,
    v1);
}

```

## disassembly

```asm
0x18000a8d0  mov     r11, rsp
0x18000a8d3  sub     rsp, 48h
0x18000a8d7  lea     rax, ?CacheFlushByTTL@FREB_LOG_NT_EVENT_TABLE@@CA?AW4LK_PREDICATE@@PEAVFREB_LOG_NT_EVENT@@PEAX@Z; FREB_LOG_NT_EVENT_TABLE::CacheFlushByTTL(FREB_LOG_NT_EVENT *,void *)
0x18000a8de  mov     qword ptr [r11-20h], 0
0x18000a8e6  add     rcx, 8
0x18000a8ea  mov     [r11-28h], rax
0x18000a8ee  lea     r8, [r11-28h]
0x18000a8f2  mov     qword ptr [r11-18h], 0
0x18000a8fa  lea     rdx, ?_Pred@?$CTypedHashTable@VFREB_LOG_NT_EVENT_TABLE@@VFREB_LOG_NT_EVENT@@PEBGVCLKRHashTable@@@@CA?AW4LK_PREDICATE@@PEBXPEAX@Z; CTypedHashTable<FREB_LOG_NT_EVENT_TABLE,FREB_LOG_NT_EVENT,ushort const *,CLKRHashTable>::_Pred(void const *,void *)
0x18000a901  call    cs:__imp_?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z; CLKRHashTable::DeleteIf(LK_PREDICATE (*)(void const *,void *),void *)
0x18000a907  add     rsp, 48h
0x18000a90b  retn
```
