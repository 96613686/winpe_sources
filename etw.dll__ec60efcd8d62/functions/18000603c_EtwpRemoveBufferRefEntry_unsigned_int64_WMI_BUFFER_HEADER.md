# EtwpRemoveBufferRefEntry(unsigned __int64,_WMI_BUFFER_HEADER *)

- ea: `0x18000603c`
- end: `0x1800060ab`
- name: `?EtwpRemoveBufferRefEntry@@YAX_KPEAU_WMI_BUFFER_HEADER@@@Z`
- size: `111`
- prototype: `void __fastcall(unsigned __int64, struct _WMI_BUFFER_HEADER *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000416c`
- `0x180010c5c`

## callees

- `0x180002f34`
- `0x18000603c`
- `0x180006480`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006065`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006065`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000609a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000609a`

## pseudocode

```c
void __fastcall EtwpRemoveBufferRefEntry(struct _WMI_BUFFER_HEADER *a1, struct _WMI_BUFFER_HEADER *a2)
{
  __int64 v3; // rcx
  __int64 v4; // rcx
  struct _WMI_BUFFER_HEADER *v5; // [rsp+30h] [rbp+8h] BYREF
  void **v6; // [rsp+40h] [rbp+18h] BYREF

  v5 = a1;
  if ( off_18001D060 != &off_18001D060 )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v5 = a2;
    utl::_HashTable<ETW_BUFFER_HEADER const *,utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>,utl::hash<ETW_BUFFER_HEADER const *>,utl::equal_to<ETW_BUFFER_HEADER const *>,utl::allocator<utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>>,0>::find<void>(
      v3,
      &v6,
      &v5);
    if ( v6 != &off_18001D060 )
      utl::_HashTable<ETW_BUFFER_HEADER const *,utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>,utl::hash<ETW_BUFFER_HEADER const *>,utl::equal_to<ETW_BUFFER_HEADER const *>,utl::allocator<utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>>,0>::erase(
        v4,
        &v5);
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x18000603c  mov     [rsp+arg_8], rbx
0x180006041  mov     [rsp+arg_0], rcx
0x180006046  push    rsi
0x180006047  sub     rsp, 20h
0x18000604b  lea     rsi, off_18001D060
0x180006052  mov     rbx, rdx
0x180006055  cmp     cs:off_18001D060, rsi
0x18000605c  jz      short loc_1800060A0
0x18000605e  lea     rcx, SRWLock; SRWLock
0x180006065  call    cs:__imp_AcquireSRWLockExclusive
0x18000606b  lea     r8, [rsp+28h+arg_0]
0x180006070  mov     [rsp+28h+arg_0], rbx
0x180006075  lea     rdx, [rsp+28h+arg_10]
0x18000607a  call    ??$find@X@?$_HashTable@PEBUETW_BUFFER_HEADER@@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@utl@@U?$hash@PEBUETW_BUFFER_HEADER@@@3@U?$equal_to@PEBUETW_BUFFER_HEADER@@@3@V?$allocator@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@utl@@@3@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@utl@@@utl@@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@2@@1@AEBQEBUETW_BUFFER_HEADER@@@Z; utl::_HashTable<ETW_BUFFER_HEADER const *,utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>,utl::hash<ETW_BUFFER_HEADER const *>,utl::equal_to<ETW_BUFFER_HEADER const *>,utl::allocator<utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>>,0>::find<void>(ETW_BUFFER_HEADER const * const &)
0x18000607f  mov     r8, [rsp+28h+arg_10]
0x180006084  cmp     r8, rsi
0x180006087  jz      short loc_180006093
0x180006089  lea     rdx, [rsp+28h+arg_0]
0x18000608e  call    ?erase@?$_HashTable@PEBUETW_BUFFER_HEADER@@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@utl@@U?$hash@PEBUETW_BUFFER_HEADER@@@3@U?$equal_to@PEBUETW_BUFFER_HEADER@@@3@V?$allocator@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@utl@@@3@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@utl@@@utl@@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@2@@2@V?$_DlistConstIt@U?$_HashNode@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@utl@@@utl@@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@2@@2@@Z; utl::_HashTable<ETW_BUFFER_HEADER const *,utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>,utl::hash<ETW_BUFFER_HEADER const *>,utl::equal_to<ETW_BUFFER_HEADER const *>,utl::allocator<utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>>,0>::erase(utl::_DlistConstIt<utl::_HashNode<utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>>,utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>>)
0x180006093  lea     rcx, SRWLock; SRWLock
0x18000609a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800060a0  mov     rbx, [rsp+28h+arg_8]
0x1800060a5  add     rsp, 20h
0x1800060a9  pop     rsi
0x1800060aa  retn
```
