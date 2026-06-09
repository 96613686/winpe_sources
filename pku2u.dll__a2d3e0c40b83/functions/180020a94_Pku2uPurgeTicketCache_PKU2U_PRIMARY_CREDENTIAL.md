# Pku2uPurgeTicketCache(_PKU2U_PRIMARY_CREDENTIAL *)

- ea: `0x180020a94`
- end: `0x180020af3`
- name: `?Pku2uPurgeTicketCache@@YAXPEAU_PKU2U_PRIMARY_CREDENTIAL@@@Z`
- size: `95`
- prototype: `void __fastcall(PRTL_CRITICAL_SECTION CriticalSection)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002c440`
- `0x18002e0ac`

## callees

- `0x180018c00`
- `0x180020a94`
- `0x180020afc`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180020ac2`
- `ntdll!RtlLeaveCriticalSection` at `0x180020ac2`
- `ntdll!RtlLeaveCriticalSection` at `0x180020aec`
- `ntdll!RtlEnterCriticalSection` at `0x180020aad`
- `ntdll!RtlEnterCriticalSection` at `0x180020aad`

## pseudocode

```c
void __fastcall Pku2uPurgeTicketCache(PRTL_CRITICAL_SECTION CriticalSection)
{
  HANDLE *p_OwningThread; // rsi
  volatile signed __int32 *v3; // rdi

  p_OwningThread = &CriticalSection[2].OwningThread;
  while ( 1 )
  {
    RtlEnterCriticalSection(CriticalSection);
    v3 = (volatile signed __int32 *)*p_OwningThread;
    if ( *p_OwningThread == p_OwningThread )
      break;
    _InterlockedIncrement(v3 + 4);
    RtlLeaveCriticalSection(CriticalSection);
    Pku2uRemoveTicketCacheEntry(CriticalSection, (struct _PKU2U_TICKET_CACHE_ENTRY *)v3);
    Pku2uDereferenceTicketCacheEntry((struct _PKU2U_TICKET_CACHE_ENTRY *)v3);
  }
  RtlLeaveCriticalSection(CriticalSection);
}

```

## disassembly

```asm
0x180020a94  mov     [rsp+arg_0], rbx
0x180020a99  mov     [rsp+arg_8], rsi
0x180020a9e  push    rdi
0x180020a9f  sub     rsp, 20h
0x180020aa3  mov     rbx, rcx
0x180020aa6  lea     rsi, [rcx+60h]
0x180020aaa  mov     rcx, rbx; CriticalSection
0x180020aad  call    cs:__imp_RtlEnterCriticalSection
0x180020ab3  mov     rdi, [rsi]
0x180020ab6  mov     rcx, rbx; CriticalSection
0x180020ab9  cmp     rdi, rsi
0x180020abc  jz      short loc_180020ADD
0x180020abe  lock inc dword ptr [rdi+10h]
0x180020ac2  call    cs:__imp_RtlLeaveCriticalSection
0x180020ac8  mov     rdx, rdi; struct _PKU2U_TICKET_CACHE_ENTRY *
0x180020acb  mov     rcx, rbx; CriticalSection
0x180020ace  call    ?Pku2uRemoveTicketCacheEntry@@YAEPEAU_PKU2U_PRIMARY_CREDENTIAL@@PEAU_PKU2U_TICKET_CACHE_ENTRY@@@Z; Pku2uRemoveTicketCacheEntry(_PKU2U_PRIMARY_CREDENTIAL *,_PKU2U_TICKET_CACHE_ENTRY *)
0x180020ad3  mov     rcx, rdi; struct _PKU2U_TICKET_CACHE_ENTRY *
0x180020ad6  call    ?Pku2uDereferenceTicketCacheEntry@@YAXPEAU_PKU2U_TICKET_CACHE_ENTRY@@@Z; Pku2uDereferenceTicketCacheEntry(_PKU2U_TICKET_CACHE_ENTRY *)
0x180020adb  jmp     short loc_180020AAA
0x180020add  mov     rbx, [rsp+28h+arg_0]
0x180020ae2  mov     rsi, [rsp+28h+arg_8]
0x180020ae7  add     rsp, 20h
0x180020aeb  pop     rdi
0x180020aec  jmp     cs:__imp_RtlLeaveCriticalSection
```
