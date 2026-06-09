# Pku2uRemoveTicketCacheEntry(_PKU2U_PRIMARY_CREDENTIAL *,_PKU2U_TICKET_CACHE_ENTRY *)

- ea: `0x180020afc`
- end: `0x180020b65`
- name: `?Pku2uRemoveTicketCacheEntry@@YAEPEAU_PKU2U_PRIMARY_CREDENTIAL@@PEAU_PKU2U_TICKET_CACHE_ENTRY@@@Z`
- size: `105`
- prototype: `unsigned __int8 __fastcall(PRTL_CRITICAL_SECTION CriticalSection, struct _PKU2U_TICKET_CACHE_ENTRY *)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014240`
- `0x180016ff0`
- `0x180020a94`
- `0x18002cc00`
- `0x180031ea0`
- `0x1800320e8`

## callees

- `0x180018c00`
- `0x180020afc`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180020b3f`
- `ntdll!RtlLeaveCriticalSection` at `0x180020b3f`
- `ntdll!RtlEnterCriticalSection` at `0x180020b1d`
- `ntdll!RtlEnterCriticalSection` at `0x180020b1d`

## pseudocode

```c
unsigned __int8 __fastcall Pku2uRemoveTicketCacheEntry(
        PRTL_CRITICAL_SECTION CriticalSection,
        struct _PKU2U_TICKET_CACHE_ENTRY *a2)
{
  __int64 v4; // rdx
  struct _PKU2U_TICKET_CACHE_ENTRY **v5; // rcx

  if ( !_InterlockedCompareExchange((volatile signed __int32 *)a2 + 6, 0, 1) )
    return 0;
  RtlEnterCriticalSection(CriticalSection);
  v4 = *(_QWORD *)a2;
  if ( *(struct _PKU2U_TICKET_CACHE_ENTRY **)(*(_QWORD *)a2 + 8LL) != a2
    || (v5 = (struct _PKU2U_TICKET_CACHE_ENTRY **)*((_QWORD *)a2 + 1), *v5 != a2) )
  {
    __fastfail(3u);
  }
  *v5 = (struct _PKU2U_TICKET_CACHE_ENTRY *)v4;
  *(_QWORD *)(v4 + 8) = v5;
  RtlLeaveCriticalSection(CriticalSection);
  Pku2uDereferenceTicketCacheEntry(a2);
  return 1;
}

```

## disassembly

```asm
0x180020afc  mov     [rsp+arg_0], rbx
0x180020b01  push    rdi
0x180020b02  sub     rsp, 20h
0x180020b06  xor     r8d, r8d
0x180020b09  mov     rbx, rdx
0x180020b0c  mov     rdi, rcx
0x180020b0f  lea     eax, [r8+1]
0x180020b13  lock cmpxchg [rdx+18h], r8d
0x180020b19  test    eax, eax
0x180020b1b  jz      short loc_180020B58
0x180020b1d  call    cs:__imp_RtlEnterCriticalSection
0x180020b23  mov     rdx, [rbx]
0x180020b26  cmp     [rdx+8], rbx
0x180020b2a  jnz     short loc_180020B51
0x180020b2c  mov     rcx, [rbx+8]
0x180020b30  cmp     [rcx], rbx
0x180020b33  jnz     short loc_180020B51
0x180020b35  mov     [rcx], rdx
0x180020b38  mov     [rdx+8], rcx
0x180020b3c  mov     rcx, rdi; CriticalSection
0x180020b3f  call    cs:__imp_RtlLeaveCriticalSection
0x180020b45  mov     rcx, rbx; struct _PKU2U_TICKET_CACHE_ENTRY *
0x180020b48  call    ?Pku2uDereferenceTicketCacheEntry@@YAXPEAU_PKU2U_TICKET_CACHE_ENTRY@@@Z; Pku2uDereferenceTicketCacheEntry(_PKU2U_TICKET_CACHE_ENTRY *)
0x180020b4d  mov     al, 1
0x180020b4f  jmp     short loc_180020B5A
0x180020b51  mov     ecx, 3
0x180020b56  int     29h; Win8: RtlFailFast(ecx)
0x180020b58  xor     al, al
0x180020b5a  mov     rbx, [rsp+28h+arg_0]
0x180020b5f  add     rsp, 20h
0x180020b63  pop     rdi
0x180020b64  retn
```
