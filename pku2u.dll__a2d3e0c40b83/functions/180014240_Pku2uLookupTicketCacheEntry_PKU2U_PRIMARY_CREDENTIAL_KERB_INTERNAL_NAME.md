# Pku2uLookupTicketCacheEntry(_PKU2U_PRIMARY_CREDENTIAL *,_KERB_INTERNAL_NAME *)

- ea: `0x180014240`
- end: `0x180014397`
- name: `?Pku2uLookupTicketCacheEntry@@YAPEAU_PKU2U_TICKET_CACHE_ENTRY@@PEAU_PKU2U_PRIMARY_CREDENTIAL@@PEAU_KERB_INTERNAL_NAME@@@Z`
- size: `343`
- prototype: `struct _PKU2U_TICKET_CACHE_ENTRY *__fastcall(PRTL_CRITICAL_SECTION CriticalSection, struct _KERB_INTERNAL_NAME *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180031ea0`

## callees

- `0x180014240`
- `0x180018c00`
- `0x180020afc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014318`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014318`
- `ntdll!RtlEqualUnicodeString` at `0x180014362`
- `ntdll!RtlEqualUnicodeString` at `0x180014362`
- `ntdll!RtlLeaveCriticalSection` at `0x180014287`
- `ntdll!RtlLeaveCriticalSection` at `0x180014287`
- `ntdll!RtlEnterCriticalSection` at `0x180014269`
- `ntdll!RtlEnterCriticalSection` at `0x180014269`

## pseudocode

```c
struct _PKU2U_TICKET_CACHE_ENTRY *__fastcall Pku2uLookupTicketCacheEntry(
        PRTL_CRITICAL_SECTION CriticalSection,
        struct _KERB_INTERNAL_NAME *a2)
{
  struct _PKU2U_TICKET_CACHE_ENTRY *v2; // rsi
  bool v3; // r13
  HANDLE *i; // rbx
  bool v7; // bp
  _WORD *v9; // rbp
  char v10; // r12
  DWORD j; // ecx
  DWORD v12; // eax
  __int64 v13; // rdi
  __int64 v14; // rcx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  v3 = 0;
  RtlEnterCriticalSection(CriticalSection);
  for ( i = (HANDLE *)CriticalSection[2].OwningThread; ; i = (HANDLE *)*i )
  {
    if ( i == &CriticalSection[2].OwningThread )
    {
      v7 = 0;
      goto LABEL_4;
    }
    v9 = i[4];
    v2 = (struct _PKU2U_TICKET_CACHE_ENTRY *)i;
    if ( v9 )
      break;
    if ( !a2 )
      goto LABEL_16;
LABEL_15:
    ;
  }
  if ( !a2 )
    goto LABEL_15;
  if ( v9[1] == *((_WORD *)a2 + 1) )
  {
    v10 = 1;
    for ( j = 0; ; j = SystemTimeAsFileTime.dwLowDateTime + 1 )
    {
      v12 = (unsigned __int16)v9[1];
      SystemTimeAsFileTime.dwLowDateTime = j;
      if ( j >= v12 )
        break;
      if ( !RtlEqualUnicodeString((PCUNICODE_STRING)&v9[8 * j + 4], (PCUNICODE_STRING)((char *)a2 + 16 * j + 8), 1u) )
        goto LABEL_21;
    }
  }
  else
  {
LABEL_21:
    v10 = 0;
  }
  if ( !v10 )
    goto LABEL_15;
LABEL_16:
  v13 = *((int *)i + 44);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v14 = *(_QWORD *)&SystemTimeAsFileTime + 10000000 * v13;
  v7 = (__int64)i[11] < v14;
  v3 = (__int64)i[11] >= v14;
  _InterlockedIncrement((volatile signed __int32 *)i + 4);
LABEL_4:
  RtlLeaveCriticalSection(CriticalSection);
  if ( v7 )
  {
    Pku2uRemoveTicketCacheEntry(CriticalSection, v2);
    Pku2uDereferenceTicketCacheEntry(v2);
  }
  if ( !v3 )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x180014240  push    rsi
0x180014242  push    r13
0x180014244  push    r14
0x180014246  sub     rsp, 30h
0x18001424a  mov     [rsp+48h+arg_8], rbx
0x18001424f  xor     esi, esi
0x180014251  mov     [rsp+48h+arg_10], rbp
0x180014256  xor     r13b, r13b
0x180014259  mov     [rsp+48h+arg_18], rdi
0x18001425e  mov     r14, rcx
0x180014261  mov     [rsp+48h+var_28], r15
0x180014266  mov     r15, rdx
0x180014269  call    cs:__imp_RtlEnterCriticalSection
0x18001426f  mov     rbx, [r14+60h]
0x180014273  lea     rdi, [r14+60h]
0x180014277  mov     [rsp+48h+var_20], r12
0x18001427c  cmp     rbx, rdi
0x18001427f  jnz     short loc_1800142C5
0x180014281  xor     bpl, bpl
0x180014284  mov     rcx, r14; CriticalSection
0x180014287  call    cs:__imp_RtlLeaveCriticalSection
0x18001428d  mov     r15, [rsp+48h+var_28]
0x180014292  test    bpl, bpl
0x180014295  mov     rbp, [rsp+48h+arg_10]
0x18001429a  mov     r12, [rsp+48h+var_20]
0x18001429f  mov     rdi, [rsp+48h+arg_18]
0x1800142a4  mov     rbx, [rsp+48h+arg_8]
0x1800142a9  jnz     loc_18001437F
0x1800142af  xor     ecx, ecx
0x1800142b1  test    r13b, r13b
0x1800142b4  cmovz   rsi, rcx
0x1800142b8  mov     rax, rsi
0x1800142bb  add     rsp, 30h
0x1800142bf  pop     r14
0x1800142c1  pop     r13
0x1800142c3  pop     rsi
0x1800142c4  retn
0x1800142c5  mov     rbp, [rbx+20h]
0x1800142c9  mov     rsi, rbx
0x1800142cc  test    rbp, rbp
0x1800142cf  jz      short loc_180014343
0x1800142d1  test    r15, r15
0x1800142d4  jz      short loc_1800142FB
0x1800142d6  movzx   eax, word ptr [r15+2]
0x1800142db  cmp     [rbp+2], ax
0x1800142df  jnz     loc_180014377
0x1800142e5  mov     r12b, 1
0x1800142e8  xor     ecx, ecx
0x1800142ea  movzx   eax, word ptr [rbp+2]
0x1800142ee  mov     [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], ecx
0x1800142f2  cmp     ecx, eax
0x1800142f4  jb      short loc_18001434A
0x1800142f6  test    r12b, r12b
0x1800142f9  jnz     short loc_180014303
0x1800142fb  mov     rbx, [rbx]
0x1800142fe  jmp     loc_18001427C
0x180014303  movsxd  rdi, dword ptr [rbx+0B0h]
0x18001430a  lea     rcx, [rsp+48h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001430f  mov     qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180014318  call    cs:__imp_GetSystemTimeAsFileTime
0x18001431e  imul    rcx, rdi, 989680h
0x180014325  add     rcx, qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime]
0x18001432a  cmp     [rbx+58h], rcx
0x18001432e  setl    bpl
0x180014332  movzx   r13d, bpl
0x180014336  xor     r13b, 1
0x18001433a  lock inc dword ptr [rbx+10h]
0x18001433e  jmp     loc_180014284
0x180014343  test    r15, r15
0x180014346  jz      short loc_180014303
0x180014348  jmp     short loc_1800142FB
0x18001434a  mov     eax, ecx
0x18001434c  lea     rdx, [r15+8]
0x180014350  shl     rax, 4
0x180014354  movzx   r8d, r12b; CaseInsensitive
0x180014358  add     rdx, rax; String2
0x18001435b  lea     rcx, [rax+8]
0x18001435f  add     rcx, rbp; String1
0x180014362  call    cs:__imp_RtlEqualUnicodeString
0x180014368  test    al, al
0x18001436a  jz      short loc_180014377
0x18001436c  mov     ecx, [rsp+48h+SystemTimeAsFileTime.dwLowDateTime]
0x180014370  inc     ecx
0x180014372  jmp     loc_1800142EA
0x180014377  xor     r12b, r12b
0x18001437a  jmp     loc_1800142F6
0x18001437f  mov     rdx, rsi; struct _PKU2U_TICKET_CACHE_ENTRY *
0x180014382  mov     rcx, r14; CriticalSection
0x180014385  call    ?Pku2uRemoveTicketCacheEntry@@YAEPEAU_PKU2U_PRIMARY_CREDENTIAL@@PEAU_PKU2U_TICKET_CACHE_ENTRY@@@Z; Pku2uRemoveTicketCacheEntry(_PKU2U_PRIMARY_CREDENTIAL *,_PKU2U_TICKET_CACHE_ENTRY *)
0x18001438a  mov     rcx, rsi; struct _PKU2U_TICKET_CACHE_ENTRY *
0x18001438d  call    ?Pku2uDereferenceTicketCacheEntry@@YAXPEAU_PKU2U_TICKET_CACHE_ENTRY@@@Z; Pku2uDereferenceTicketCacheEntry(_PKU2U_TICKET_CACHE_ENTRY *)
0x180014392  jmp     loc_1800142AF
```
