# EtwpRemovePlaybackEngineBufferReference(_TRACELOG_CONTEXT *,_WMI_BUFFER_HEADER *)

- ea: `0x1800060b4`
- end: `0x180006178`
- name: `?EtwpRemovePlaybackEngineBufferReference@@YAJPEAU_TRACELOG_CONTEXT@@PEAU_WMI_BUFFER_HEADER@@@Z`
- size: `196`
- prototype: `__int64 __fastcall(struct _TRACELOG_CONTEXT *, struct _WMI_BUFFER_HEADER *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f384`
- `0x18000fc74`
- `0x18000ff6c`
- `0x1800108d0`
- `0x180014b10`

## callees

- `0x180002f34`
- `0x1800060b4`
- `0x180006480`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800060e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800060e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006160`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006160`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180006151`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180006151`

## pseudocode

```c
__int64 __fastcall EtwpRemovePlaybackEngineBufferReference(struct _TRACELOG_CONTEXT *a1, struct _WMI_BUFFER_HEADER *a2)
{
  __int64 v5; // rcx
  __int64 v6; // r8
  unsigned int v7; // ebx
  unsigned int v8; // esi
  struct _WMI_BUFFER_HEADER *v9; // [rsp+40h] [rbp+18h] BYREF
  __int64 v10; // [rsp+48h] [rbp+20h] BYREF

  if ( off_18001D060 == &off_18001D060 )
    return 0;
  AcquireSRWLockExclusive(&SRWLock);
  v9 = a2;
  utl::_HashTable<ETW_BUFFER_HEADER const *,utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>,utl::hash<ETW_BUFFER_HEADER const *>,utl::equal_to<ETW_BUFFER_HEADER const *>,utl::allocator<utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>>,0>::find<void>(
    v5,
    &v10,
    &v9);
  v6 = v10;
  if ( (void **)v10 == &off_18001D060 )
  {
    v7 = 0;
  }
  else
  {
    --*(_DWORD *)(v10 + 40);
    v8 = *(_DWORD *)(v6 + 40);
    if ( v8 )
    {
      if ( _InterlockedIncrement((volatile signed __int32 *)a1 + 242) == 1 )
        ResetEvent(*((HANDLE *)a1 + 122));
    }
    else if ( *((_BYTE *)a1 + 552) == 1 )
    {
      utl::_HashTable<ETW_BUFFER_HEADER const *,utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>,utl::hash<ETW_BUFFER_HEADER const *>,utl::equal_to<ETW_BUFFER_HEADER const *>,utl::allocator<utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>>,0>::erase(
        1,
        &v9);
    }
    v7 = v8;
  }
  ReleaseSRWLockExclusive(&SRWLock);
  return v7;
}

```

## disassembly

```asm
0x1800060b4  mov     [rsp+arg_0], rbx
0x1800060b9  mov     [rsp+arg_8], rsi
0x1800060be  push    rdi
0x1800060bf  sub     rsp, 20h
0x1800060c3  lea     rsi, off_18001D060
0x1800060ca  mov     rbx, rdx
0x1800060cd  cmp     cs:off_18001D060, rsi
0x1800060d4  mov     rdi, rcx
0x1800060d7  jnz     short loc_1800060E0
0x1800060d9  xor     eax, eax
0x1800060db  jmp     loc_180006168
0x1800060e0  lea     rcx, SRWLock; SRWLock
0x1800060e7  call    cs:__imp_AcquireSRWLockExclusive
0x1800060ed  lea     r8, [rsp+28h+arg_10]
0x1800060f2  mov     [rsp+28h+arg_10], rbx
0x1800060f7  lea     rdx, [rsp+28h+arg_18]
0x1800060fc  call    ??$find@X@?$_HashTable@PEBUETW_BUFFER_HEADER@@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@utl@@U?$hash@PEBUETW_BUFFER_HEADER@@@3@U?$equal_to@PEBUETW_BUFFER_HEADER@@@3@V?$allocator@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@utl@@@3@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@utl@@@utl@@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@2@@1@AEBQEBUETW_BUFFER_HEADER@@@Z; utl::_HashTable<ETW_BUFFER_HEADER const *,utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>,utl::hash<ETW_BUFFER_HEADER const *>,utl::equal_to<ETW_BUFFER_HEADER const *>,utl::allocator<utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>>,0>::find<void>(ETW_BUFFER_HEADER const * const &)
0x180006101  mov     r8, [rsp+28h+arg_18]
0x180006106  cmp     r8, rsi
0x180006109  jnz     short loc_18000610F
0x18000610b  xor     ebx, ebx
0x18000610d  jmp     short loc_180006159
0x18000610f  mov     eax, [r8+28h]
0x180006113  mov     ecx, 1
0x180006118  sub     eax, ecx
0x18000611a  mov     [r8+28h], eax
0x18000611e  mov     esi, [r8+28h]
0x180006122  test    esi, esi
0x180006124  jnz     short loc_18000613A
0x180006126  cmp     [rdi+228h], cl
0x18000612c  jnz     short loc_180006157
0x18000612e  lea     rdx, [rsp+28h+arg_10]
0x180006133  call    ?erase@?$_HashTable@PEBUETW_BUFFER_HEADER@@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@utl@@U?$hash@PEBUETW_BUFFER_HEADER@@@3@U?$equal_to@PEBUETW_BUFFER_HEADER@@@3@V?$allocator@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@utl@@@3@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@utl@@@utl@@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@2@@2@V?$_DlistConstIt@U?$_HashNode@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@utl@@@utl@@U?$pair@QEBUETW_BUFFER_HEADER@@UPROCESS_TRACE_BUFFER_REF_ENTRY@@@2@@2@@Z; utl::_HashTable<ETW_BUFFER_HEADER const *,utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>,utl::hash<ETW_BUFFER_HEADER const *>,utl::equal_to<ETW_BUFFER_HEADER const *>,utl::allocator<utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>>,0>::erase(utl::_DlistConstIt<utl::_HashNode<utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>>,utl::pair<ETW_BUFFER_HEADER const * const,PROCESS_TRACE_BUFFER_REF_ENTRY>>)
0x180006138  jmp     short loc_180006157
0x18000613a  mov     eax, ecx
0x18000613c  lock xadd [rdi+3C8h], eax
0x180006144  add     eax, ecx
0x180006146  cmp     eax, ecx
0x180006148  jnz     short loc_180006157
0x18000614a  mov     rcx, [rdi+3D0h]; hEvent
0x180006151  call    cs:__imp_ResetEvent
0x180006157  mov     ebx, esi
0x180006159  lea     rcx, SRWLock; SRWLock
0x180006160  call    cs:__imp_ReleaseSRWLockExclusive
0x180006166  mov     eax, ebx
0x180006168  mov     rbx, [rsp+28h+arg_0]
0x18000616d  mov     rsi, [rsp+28h+arg_8]
0x180006172  add     rsp, 20h
0x180006176  pop     rdi
0x180006177  retn
```
