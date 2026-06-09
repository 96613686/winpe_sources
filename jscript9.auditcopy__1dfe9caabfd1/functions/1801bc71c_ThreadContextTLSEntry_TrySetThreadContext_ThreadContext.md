# ThreadContextTLSEntry::TrySetThreadContext(ThreadContext *)

- ea: `0x1801bc71c`
- end: `0x1801bc7aa`
- name: `?TrySetThreadContext@ThreadContextTLSEntry@@SA_NPEAVThreadContext@@@Z`
- size: `142`
- prototype: `char __fastcall(struct ThreadContext *)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x180030680`
- `0x1800309c0`
- `0x1800318c0`
- `0x180031cf0`
- `0x18014422c`
- `0x18020b810`
- `0x1802ce304`

## callees

- `0x1801bc71c`
- `0x1801bc7b0`
- `0x1801bc804`
- `0x1802d03d0`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x1801bc74e`
- `KERNEL32!TlsGetValue` at `0x1801bc74e`
- `KERNEL32!GetCurrentThreadId` at `0x1801bc738`
- `KERNEL32!GetCurrentThreadId` at `0x1801bc738`

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
0x1801bc71c  mov     [rsp+arg_8], rbx
0x1801bc721  mov     [rsp+arg_0], rcx
0x1801bc726  push    rdi
0x1801bc727  sub     rsp, 20h
0x1801bc72b  mov     rdi, [rsp+28h+arg_0]
0x1801bc730  mov     ebx, [rdi+24h]
0x1801bc733  cmp     ebx, 0FFFFFFFFh
0x1801bc736  jz      short loc_1801BC748
0x1801bc738  call    cs:__imp_GetCurrentThreadId
0x1801bc73f  nop     dword ptr [rax+rax+00h]
0x1801bc744  cmp     ebx, eax
0x1801bc746  jnz     short loc_1801BC7A6
0x1801bc748  mov     ecx, cs:?s_tlsSlot@ThreadContextTLSEntry@@2KA; dwTlsIndex
0x1801bc74e  call    cs:__imp_TlsGetValue
0x1801bc755  nop     dword ptr [rax+rax+00h]
0x1801bc75a  mov     rcx, rax; struct ThreadContextTLSEntry *
0x1801bc75d  test    rax, rax
0x1801bc760  jnz     short loc_1801BC780
0x1801bc762  call    ?CreateEntryForCurrentThread@ThreadContextTLSEntry@@SAPEAV1@XZ; ThreadContextTLSEntry::CreateEntryForCurrentThread(void)
0x1801bc767  mov     rcx, rax; struct ThreadContextTLSEntry *
0x1801bc76a  mov     rdx, rdi; struct ThreadContext *
0x1801bc76d  call    ?SetThreadContext@ThreadContextTLSEntry@@SAXPEAV1@PEAVThreadContext@@@Z; ThreadContextTLSEntry::SetThreadContext(ThreadContextTLSEntry *,ThreadContext *)
0x1801bc772  mov     al, 1
0x1801bc774  mov     rbx, [rsp+28h+arg_8]
0x1801bc779  add     rsp, 20h
0x1801bc77d  pop     rdi
0x1801bc77e  retn
0x1801bc780  mov     rax, [rax]
0x1801bc783  test    rax, rax
0x1801bc786  jz      short loc_1801BC76A
0x1801bc788  cmp     rax, rdi
0x1801bc78b  jz      short loc_1801BC76A
0x1801bc78d  cmp     byte ptr [rax+38h], 0
0x1801bc791  jnz     short loc_1801BC7A6
0x1801bc793  cmp     dword ptr [rax+58h], 0
0x1801bc797  jnz     short loc_1801BC7A6
0x1801bc799  mov     r8b, 1; bool
0x1801bc79c  mov     dl, r8b; bool
0x1801bc79f  call    ?ClearThreadContext@ThreadContextTLSEntry@@SA_NPEAV1@_N1@Z; ThreadContextTLSEntry::ClearThreadContext(ThreadContextTLSEntry *,bool,bool)
0x1801bc7a4  jmp     short loc_1801BC76A
0x1801bc7a6  xor     al, al
0x1801bc7a8  jmp     short loc_1801BC774
```
