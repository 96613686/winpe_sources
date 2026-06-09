# ThreadContextTLSEntry::TrySetThreadContext(ThreadContext *)

- ea: `0x1802eede0`
- end: `0x1802eee8f`
- name: `?TrySetThreadContext@ThreadContextTLSEntry@@SA_NPEAVThreadContext@@@Z`
- size: `175`
- prototype: `bool __fastcall(struct ThreadContext *)`
- caller_count: `10`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c630`
- `0x1801676a0`
- `0x1802eeaa0`
- `0x1802eed18`
- `0x18032e8c4`
- `0x18032ea30`
- `0x18032edc0`
- `0x18032ef2c`
- `0x18032f058`
- `0x1803a6b58`

## callees

- `0x1802eede0`
- `0x1802eee98`
- `0x1802eef50`
- `0x18039e4b0`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1802eee05`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1802eee05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802eee34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802eee34`

## pseudocode

```c
char __fastcall ThreadContextTLSEntry::TrySetThreadContext(struct ThreadContext *a1)
{
  int v2; // ebx
  struct ThreadContextTLSEntry *Value; // rax
  struct ThreadContextTLSEntry *EntryForCurrentThread; // rbx
  struct ThreadContext *v5; // rcx

  v2 = *((_DWORD *)a1 + 68);
  if ( v2 != -1 && v2 != GetCurrentThreadId() )
    return 0;
  Value = (struct ThreadContextTLSEntry *)TlsGetValue(ThreadContextTLSEntry::s_tlsSlot);
  EntryForCurrentThread = Value;
  if ( !Value )
  {
    EntryForCurrentThread = ThreadContextTLSEntry::CreateEntryForCurrentThread();
    goto LABEL_10;
  }
  v5 = *(struct ThreadContext **)Value;
  if ( !*(_QWORD *)Value )
  {
LABEL_10:
    ThreadContextTLSEntry::SetThreadContext(EntryForCurrentThread, a1);
    return 1;
  }
  if ( v5 == a1 )
    return 1;
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD *))(*((_QWORD *)v5 + 2) + 8LL))((_QWORD *)v5 + 2)
    && !*(_DWORD *)(*(_QWORD *)EntryForCurrentThread + 904LL) )
  {
    ThreadContextTLSEntry::ClearThreadContext(EntryForCurrentThread, 1, 1);
    goto LABEL_10;
  }
  return 0;
}

```

## disassembly

```asm
0x1802eede0  mov     [rsp+arg_8], rbx
0x1802eede5  mov     [rsp+arg_0], rcx
0x1802eedea  push    rdi
0x1802eedeb  sub     rsp, 20h
0x1802eedef  mov     rdi, [rsp+28h+arg_0]
0x1802eedf4  mov     ebx, [rdi+110h]
0x1802eedfa  cmp     ebx, 0FFFFFFFFh
0x1802eedfd  jnz     short loc_1802EEE34
0x1802eedff  mov     ecx, cs:?s_tlsSlot@ThreadContextTLSEntry@@2IA; dwTlsIndex
0x1802eee05  call    cs:__imp_TlsGetValue
0x1802eee0c  nop     dword ptr [rax+rax+00h]
0x1802eee11  mov     rbx, rax
0x1802eee14  test    rax, rax
0x1802eee17  jz      short loc_1802EEE6D
0x1802eee19  mov     rcx, [rax]
0x1802eee1c  test    rcx, rcx
0x1802eee1f  jz      short loc_1802EEE60
0x1802eee21  cmp     rcx, rdi
0x1802eee24  jnz     short loc_1802EEE77
0x1802eee26  mov     al, 1
0x1802eee28  mov     rbx, [rsp+28h+arg_8]
0x1802eee2d  add     rsp, 20h
0x1802eee31  pop     rdi
0x1802eee32  retn
0x1802eee34  call    cs:__imp_GetCurrentThreadId
0x1802eee3b  nop     dword ptr [rax+rax+00h]
0x1802eee40  cmp     ebx, eax
0x1802eee42  jz      short loc_1802EEDFF
0x1802eee44  jmp     short loc_1802EEE8B
0x1802eee46  mov     rax, [rbx]
0x1802eee49  cmp     dword ptr [rax+388h], 0
0x1802eee50  jnz     short loc_1802EEE8B
0x1802eee52  mov     r8b, 1; bool
0x1802eee55  mov     rcx, rbx; struct ThreadContextTLSEntry *
0x1802eee58  mov     dl, r8b; bool
0x1802eee5b  call    ?ClearThreadContext@ThreadContextTLSEntry@@SA_NPEAV1@_N1@Z; ThreadContextTLSEntry::ClearThreadContext(ThreadContextTLSEntry *,bool,bool)
0x1802eee60  mov     rdx, rdi; struct ThreadContext *
0x1802eee63  mov     rcx, rbx; struct ThreadContextTLSEntry *
0x1802eee66  call    ?SetThreadContext@ThreadContextTLSEntry@@SAXPEAV1@PEAVThreadContext@@@Z; ThreadContextTLSEntry::SetThreadContext(ThreadContextTLSEntry *,ThreadContext *)
0x1802eee6b  jmp     short loc_1802EEE26
0x1802eee6d  call    ?CreateEntryForCurrentThread@ThreadContextTLSEntry@@SAPEAV1@XZ; ThreadContextTLSEntry::CreateEntryForCurrentThread(void)
0x1802eee72  mov     rbx, rax
0x1802eee75  jmp     short loc_1802EEE60
0x1802eee77  add     rcx, 10h
0x1802eee7b  mov     rax, [rcx]
0x1802eee7e  mov     rax, [rax+8]
0x1802eee82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802eee87  test    al, al
0x1802eee89  jz      short loc_1802EEE46
0x1802eee8b  xor     al, al
0x1802eee8d  jmp     short loc_1802EEE28
```
