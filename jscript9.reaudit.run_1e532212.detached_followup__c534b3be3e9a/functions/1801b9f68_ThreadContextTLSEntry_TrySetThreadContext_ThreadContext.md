# ThreadContextTLSEntry::TrySetThreadContext(ThreadContext *)

- ea: `0x1801b9f68`
- end: `0x1801b9fe9`
- name: `?TrySetThreadContext@ThreadContextTLSEntry@@SA_NPEAVThreadContext@@@Z`
- size: `129`
- prototype: `bool __fastcall(struct ThreadContext *)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x180024e40`
- `0x180025170`
- `0x180026050`
- `0x180026460`
- `0x180141178`
- `0x180208290`
- `0x1802c8b9c`

## callees

- `0x1801b9f68`
- `0x1801b9ff0`
- `0x1801ba040`
- `0x1802cabb8`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x1801b9f94`
- `KERNEL32!TlsGetValue` at `0x1801b9f94`
- `KERNEL32!GetCurrentThreadId` at `0x1801b9f84`
- `KERNEL32!GetCurrentThreadId` at `0x1801b9f84`

## pseudocode

```c
char __fastcall ThreadContextTLSEntry::TrySetThreadContext(struct ThreadContext *a1)
{
  int v2; // ebx
  struct ThreadContextTLSEntry *Value; // rax
  struct ThreadContextTLSEntry *EntryForCurrentThread; // rcx
  __int64 v6; // rax

  v2 = *((_DWORD *)a1 + 9);
  if ( v2 == -1 || v2 == GetCurrentThreadId() )
  {
    Value = (struct ThreadContextTLSEntry *)TlsGetValue(ThreadContextTLSEntry::s_tlsSlot);
    EntryForCurrentThread = Value;
    if ( !Value )
    {
      EntryForCurrentThread = ThreadContextTLSEntry::CreateEntryForCurrentThread();
LABEL_5:
      ThreadContextTLSEntry::SetThreadContext(EntryForCurrentThread, a1);
      return 1;
    }
    v6 = *(_QWORD *)Value;
    if ( !v6 || (struct ThreadContext *)v6 == a1 )
      goto LABEL_5;
    if ( !*(_BYTE *)(v6 + 56) && !*(_DWORD *)(v6 + 88) )
    {
      ThreadContextTLSEntry::ClearThreadContext(EntryForCurrentThread, 1, 1);
      goto LABEL_5;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1801b9f68  mov     [rsp+arg_8], rbx
0x1801b9f6d  mov     [rsp+arg_0], rcx
0x1801b9f72  push    rdi
0x1801b9f73  sub     rsp, 20h
0x1801b9f77  mov     rdi, [rsp+28h+arg_0]
0x1801b9f7c  mov     ebx, [rdi+24h]
0x1801b9f7f  cmp     ebx, 0FFFFFFFFh
0x1801b9f82  jz      short loc_1801B9F8E
0x1801b9f84  call    cs:__imp_GetCurrentThreadId
0x1801b9f8a  cmp     ebx, eax
0x1801b9f8c  jnz     short loc_1801B9FE5
0x1801b9f8e  mov     ecx, cs:?s_tlsSlot@ThreadContextTLSEntry@@2KA; dwTlsIndex
0x1801b9f94  call    cs:__imp_TlsGetValue
0x1801b9f9a  mov     rcx, rax; struct ThreadContextTLSEntry *
0x1801b9f9d  test    rax, rax
0x1801b9fa0  jnz     short loc_1801B9FBF
0x1801b9fa2  call    ?CreateEntryForCurrentThread@ThreadContextTLSEntry@@SAPEAV1@XZ; ThreadContextTLSEntry::CreateEntryForCurrentThread(void)
0x1801b9fa7  mov     rcx, rax; struct ThreadContextTLSEntry *
0x1801b9faa  mov     rdx, rdi; struct ThreadContext *
0x1801b9fad  call    ?SetThreadContext@ThreadContextTLSEntry@@SAXPEAV1@PEAVThreadContext@@@Z; ThreadContextTLSEntry::SetThreadContext(ThreadContextTLSEntry *,ThreadContext *)
0x1801b9fb2  mov     al, 1
0x1801b9fb4  mov     rbx, [rsp+28h+arg_8]
0x1801b9fb9  add     rsp, 20h
0x1801b9fbd  pop     rdi
0x1801b9fbe  retn
0x1801b9fbf  mov     rax, [rax]
0x1801b9fc2  test    rax, rax
0x1801b9fc5  jz      short loc_1801B9FAA
0x1801b9fc7  cmp     rax, rdi
0x1801b9fca  jz      short loc_1801B9FAA
0x1801b9fcc  cmp     byte ptr [rax+38h], 0
0x1801b9fd0  jnz     short loc_1801B9FE5
0x1801b9fd2  cmp     dword ptr [rax+58h], 0
0x1801b9fd6  jnz     short loc_1801B9FE5
0x1801b9fd8  mov     r8b, 1; bool
0x1801b9fdb  mov     dl, r8b; bool
0x1801b9fde  call    ?ClearThreadContext@ThreadContextTLSEntry@@SA_NPEAV1@_N1@Z; ThreadContextTLSEntry::ClearThreadContext(ThreadContextTLSEntry *,bool,bool)
0x1801b9fe3  jmp     short loc_1801B9FAA
0x1801b9fe5  xor     al, al
0x1801b9fe7  jmp     short loc_1801B9FB4
```
