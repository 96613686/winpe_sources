# Pku2uDereferenceTicketCacheEntry(_PKU2U_TICKET_CACHE_ENTRY *)

- ea: `0x180018c00`
- end: `0x180018c6f`
- name: `?Pku2uDereferenceTicketCacheEntry@@YAXPEAU_PKU2U_TICKET_CACHE_ENTRY@@@Z`
- size: `111`
- prototype: `void __fastcall(struct _PKU2U_TICKET_CACHE_ENTRY *)`
- caller_count: `7`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180005300`
- `0x180014240`
- `0x180016ff0`
- `0x18001cc90`
- `0x180020a94`
- `0x180020afc`
- `0x180031ea0`

## callees

- `0x1800057f0`
- `0x180010e50`
- `0x180015190`
- `0x180018c00`
- `0x180031458`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180018c32`
- `ntdll!RtlLeaveCriticalSection` at `0x180018c32`
- `ntdll!RtlEnterCriticalSection` at `0x180018c1f`
- `ntdll!RtlEnterCriticalSection` at `0x180018c1f`

## pseudocode

```c
void __fastcall Pku2uDereferenceTicketCacheEntry(struct _PKU2U_TICKET_CACHE_ENTRY *a1)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 4, 0xFFFFFFFF) == 1 )
  {
    RtlEnterCriticalSection(&Pku2uGlobalTicketListLock);
    --Pku2uGlobalTicketListSize;
    RtlLeaveCriticalSection(&Pku2uGlobalTicketListLock);
    KerbFreeKdcName((struct _KERB_INTERNAL_NAME **)a1 + 4);
    KerbFreeKdcName((struct _KERB_INTERNAL_NAME **)a1 + 5);
    KerbFreeDuplicatedTicket((struct _PKU2U_TICKET_CACHE_ENTRY *)((char *)a1 + 104));
    KerbFreeKey((struct _PKU2U_TICKET_CACHE_ENTRY *)((char *)a1 + 56));
    Pku2uFree(a1);
  }
}

```

## disassembly

```asm
0x180018c00  push    rbx
0x180018c02  sub     rsp, 20h
0x180018c06  mov     rbx, rcx
0x180018c09  mov     eax, 0FFFFFFFFh
0x180018c0e  lock xadd [rcx+10h], eax
0x180018c13  cmp     eax, 1
0x180018c16  jnz     short loc_180018C69
0x180018c18  lea     rcx, ?Pku2uGlobalTicketListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180018c1f  call    cs:__imp_RtlEnterCriticalSection
0x180018c25  dec     cs:?Pku2uGlobalTicketListSize@@3JA; long Pku2uGlobalTicketListSize
0x180018c2b  lea     rcx, ?Pku2uGlobalTicketListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180018c32  call    cs:__imp_RtlLeaveCriticalSection
0x180018c38  lea     rcx, [rbx+20h]; struct _KERB_INTERNAL_NAME **
0x180018c3c  call    ?KerbFreeKdcName@@YAXPEAPEAU_KERB_INTERNAL_NAME@@@Z; KerbFreeKdcName(_KERB_INTERNAL_NAME * *)
0x180018c41  lea     rcx, [rbx+28h]; struct _KERB_INTERNAL_NAME **
0x180018c45  call    ?KerbFreeKdcName@@YAXPEAPEAU_KERB_INTERNAL_NAME@@@Z; KerbFreeKdcName(_KERB_INTERNAL_NAME * *)
0x180018c4a  lea     rcx, [rbx+68h]; struct KERB_TICKET *
0x180018c4e  call    ?KerbFreeDuplicatedTicket@@YAXPEAUKERB_TICKET@@@Z; KerbFreeDuplicatedTicket(KERB_TICKET *)
0x180018c53  lea     rcx, [rbx+38h]; struct KERB_ENCRYPTION_KEY *
0x180018c57  call    ?KerbFreeKey@@YAXPEAUKERB_ENCRYPTION_KEY@@@Z; KerbFreeKey(KERB_ENCRYPTION_KEY *)
0x180018c5c  mov     rcx, rbx; void *
0x180018c5f  add     rsp, 20h
0x180018c63  pop     rbx
0x180018c64  jmp     ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x180018c69  add     rsp, 20h
0x180018c6d  pop     rbx
0x180018c6e  retn
```
