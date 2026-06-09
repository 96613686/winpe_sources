# Pku2uLookupTicketCacheEntryFromCredentials(_PKU2U_SECONDARY_CREDENTIAL *,_PKU2U_ASSOCIATED_CREDENTIAL *,_KERB_INTERNAL_NAME *,_PKU2U_TICKET_CACHE_ENTRY * *)

- ea: `0x180016ff0`
- end: `0x180017194`
- name: `?Pku2uLookupTicketCacheEntryFromCredentials@@YAJPEAU_PKU2U_SECONDARY_CREDENTIAL@@PEAU_PKU2U_ASSOCIATED_CREDENTIAL@@PEAU_KERB_INTERNAL_NAME@@PEAPEAU_PKU2U_TICKET_CACHE_ENTRY@@@Z`
- size: `420`
- prototype: `__int64 __fastcall(struct _PKU2U_SECONDARY_CREDENTIAL *, struct _PKU2U_ASSOCIATED_CREDENTIAL *, struct _KERB_INTERNAL_NAME *, struct _PKU2U_TICKET_CACHE_ENTRY **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001cc90`

## callees

- `0x180016ff0`
- `0x180018c00`
- `0x180020afc`
- `0x180023cb8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800170b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800170b3`
- `ntdll!RtlEqualUnicodeString` at `0x180017114`
- `ntdll!RtlEqualUnicodeString` at `0x180017114`
- `ntdll!RtlLeaveCriticalSection` at `0x180017143`
- `ntdll!RtlLeaveCriticalSection` at `0x180017143`
- `ntdll!RtlEnterCriticalSection` at `0x180017072`
- `ntdll!RtlEnterCriticalSection` at `0x180017072`

## pseudocode

```c
__int64 __fastcall Pku2uLookupTicketCacheEntryFromCredentials(
        struct _RTL_CRITICAL_SECTION *a1,
        struct _RTL_CRITICAL_SECTION *a2,
        struct _KERB_INTERNAL_NAME *a3,
        struct _PKU2U_TICKET_CACHE_ENTRY **a4)
{
  __int64 result; // rax
  struct _PKU2U_TICKET_CACHE_ENTRY *v7; // rsi
  struct _RTL_CRITICAL_SECTION *v8; // r14
  HANDLE *i; // rbx
  _WORD *v10; // rbp
  __int64 v11; // rdi
  __int64 v12; // rcx
  bool v13; // r12
  bool v14; // bp
  char v15; // r12
  DWORD j; // ecx
  DWORD v17; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp+8h] BYREF

  *a4 = 0;
  if ( LODWORD(a1->SpinCount) )
  {
    if ( !a2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_e620118210cc360496f33e71fb07ec1b_Traceguids);
      return 2148074254LL;
    }
  }
  else
  {
    a2 = a1;
  }
  v7 = 0;
  v8 = a2 + 1;
  RtlEnterCriticalSection(a2 + 1);
  for ( i = (HANDLE *)v8[2].OwningThread; i != &v8[2].OwningThread; i = (HANDLE *)*i )
  {
    v10 = i[4];
    v7 = (struct _PKU2U_TICKET_CACHE_ENTRY *)i;
    if ( v10 )
    {
      if ( a3 )
      {
        if ( v10[1] == *((_WORD *)a3 + 1) )
        {
          v15 = 1;
          for ( j = 0; ; j = SystemTimeAsFileTime.dwLowDateTime + 1 )
          {
            v17 = (unsigned __int16)v10[1];
            SystemTimeAsFileTime.dwLowDateTime = j;
            if ( j >= v17 )
              break;
            if ( !RtlEqualUnicodeString(
                    (PCUNICODE_STRING)&v10[8 * j + 4],
                    (PCUNICODE_STRING)((char *)a3 + 16 * j + 8),
                    1u) )
              goto LABEL_19;
          }
        }
        else
        {
LABEL_19:
          v15 = 0;
        }
        if ( v15 )
        {
LABEL_12:
          v11 = *((int *)i + 44);
          SystemTimeAsFileTime = 0;
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          v12 = *(_QWORD *)&SystemTimeAsFileTime + 10000000 * v11;
          v13 = (__int64)i[11] < v12;
          v14 = (__int64)i[11] >= v12;
          _InterlockedIncrement((volatile signed __int32 *)i + 4);
          goto LABEL_23;
        }
      }
    }
    else if ( !a3 )
    {
      goto LABEL_12;
    }
  }
  v14 = 0;
  v13 = 0;
LABEL_23:
  RtlLeaveCriticalSection(v8);
  if ( v13 )
  {
    Pku2uRemoveTicketCacheEntry(v8, v7);
    Pku2uDereferenceTicketCacheEntry(v7);
  }
  result = 0;
  if ( !v14 )
    v7 = 0;
  *a4 = v7;
  return result;
}

```

## disassembly

```asm
0x180016ff0  push    r13
0x180016ff2  push    r15
0x180016ff4  sub     rsp, 38h
0x180016ff8  mov     qword ptr [r9], 0
0x180016fff  mov     r15, r9
0x180017002  cmp     dword ptr [rcx+20h], 0
0x180017006  mov     r13, r8
0x180017009  jz      short loc_180017048
0x18001700b  test    rdx, rdx
0x18001700e  jnz     short loc_18001704B
0x180017010  mov     rcx, cs:WPP_GLOBAL_Control
0x180017017  lea     rdx, WPP_GLOBAL_Control
0x18001701e  cmp     rcx, rdx
0x180017021  jz      short loc_18001703E
0x180017023  test    byte ptr [rcx+1Ch], 1
0x180017027  jz      short loc_18001703E
0x180017029  mov     rcx, [rcx+10h]
0x18001702d  lea     r8, WPP_e620118210cc360496f33e71fb07ec1b_Traceguids
0x180017034  mov     edx, 0Bh
0x180017039  call    WPP_SF_
0x18001703e  mov     eax, 8009030Eh
0x180017043  jmp     loc_18001718B
0x180017048  mov     rdx, rcx
0x18001704b  mov     [rsp+48h+arg_8], rbx
0x180017050  mov     [rsp+48h+arg_10], rbp
0x180017055  mov     [rsp+48h+arg_18], rsi
0x18001705a  xor     esi, esi
0x18001705c  mov     [rsp+48h+var_18], rdi
0x180017061  mov     [rsp+48h+var_20], r12
0x180017066  mov     [rsp+48h+var_28], r14
0x18001706b  lea     r14, [rdx+28h]
0x18001706f  mov     rcx, r14; CriticalSection
0x180017072  call    cs:__imp_RtlEnterCriticalSection
0x180017078  mov     rbx, [r14+60h]
0x18001707c  lea     rdi, [r14+60h]
0x180017080  cmp     rbx, rdi
0x180017083  jz      loc_18001713A
0x180017089  mov     rbp, [rbx+20h]
0x18001708d  mov     rsi, rbx
0x180017090  test    rbp, rbp
0x180017093  jnz     short loc_1800170DB
0x180017095  test    r13, r13
0x180017098  jnz     loc_180017132
0x18001709e  movsxd  rdi, dword ptr [rbx+0B0h]
0x1800170a5  lea     rcx, [rsp+48h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800170aa  mov     qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800170b3  call    cs:__imp_GetSystemTimeAsFileTime
0x1800170b9  imul    rcx, rdi, 989680h
0x1800170c0  add     rcx, qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime]
0x1800170c5  cmp     [rbx+58h], rcx
0x1800170c9  setl    r12b
0x1800170cd  movzx   ebp, r12b
0x1800170d1  xor     bpl, 1
0x1800170d5  lock inc dword ptr [rbx+10h]
0x1800170d9  jmp     short loc_180017140
0x1800170db  test    r13, r13
0x1800170de  jz      short loc_180017132
0x1800170e0  movzx   eax, word ptr [r13+2]
0x1800170e5  cmp     [rbp+2], ax
0x1800170e9  jnz     short loc_180017126
0x1800170eb  mov     r12b, 1
0x1800170ee  xor     ecx, ecx
0x1800170f0  movzx   eax, word ptr [rbp+2]
0x1800170f4  mov     [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], ecx
0x1800170f8  cmp     ecx, eax
0x1800170fa  jnb     short loc_180017129
0x1800170fc  mov     eax, ecx
0x1800170fe  lea     rdx, [r13+8]
0x180017102  shl     rax, 4
0x180017106  movzx   r8d, r12b; CaseInsensitive
0x18001710a  add     rdx, rax; String2
0x18001710d  lea     rcx, [rax+8]
0x180017111  add     rcx, rbp; String1
0x180017114  call    cs:__imp_RtlEqualUnicodeString
0x18001711a  test    al, al
0x18001711c  jz      short loc_180017126
0x18001711e  mov     ecx, [rsp+48h+SystemTimeAsFileTime.dwLowDateTime]
0x180017122  inc     ecx
0x180017124  jmp     short loc_1800170F0
0x180017126  xor     r12b, r12b
0x180017129  test    r12b, r12b
0x18001712c  jnz     loc_18001709E
0x180017132  mov     rbx, [rbx]
0x180017135  jmp     loc_180017080
0x18001713a  xor     bpl, bpl
0x18001713d  xor     r12b, r12b
0x180017140  mov     rcx, r14; CriticalSection
0x180017143  call    cs:__imp_RtlLeaveCriticalSection
0x180017149  mov     rdi, [rsp+48h+var_18]
0x18001714e  test    r12b, r12b
0x180017151  mov     r12, [rsp+48h+var_20]
0x180017156  mov     rbx, [rsp+48h+arg_8]
0x18001715b  jz      short loc_180017170
0x18001715d  mov     rdx, rsi; struct _PKU2U_TICKET_CACHE_ENTRY *
0x180017160  mov     rcx, r14; CriticalSection
0x180017163  call    ?Pku2uRemoveTicketCacheEntry@@YAEPEAU_PKU2U_PRIMARY_CREDENTIAL@@PEAU_PKU2U_TICKET_CACHE_ENTRY@@@Z; Pku2uRemoveTicketCacheEntry(_PKU2U_PRIMARY_CREDENTIAL *,_PKU2U_TICKET_CACHE_ENTRY *)
0x180017168  mov     rcx, rsi; struct _PKU2U_TICKET_CACHE_ENTRY *
0x18001716b  call    ?Pku2uDereferenceTicketCacheEntry@@YAXPEAU_PKU2U_TICKET_CACHE_ENTRY@@@Z; Pku2uDereferenceTicketCacheEntry(_PKU2U_TICKET_CACHE_ENTRY *)
0x180017170  mov     r14, [rsp+48h+var_28]
0x180017175  xor     eax, eax
0x180017177  test    bpl, bpl
0x18001717a  mov     rbp, [rsp+48h+arg_10]
0x18001717f  cmovz   rsi, rax
0x180017183  mov     [r15], rsi
0x180017186  mov     rsi, [rsp+48h+arg_18]
0x18001718b  add     rsp, 38h
0x18001718f  pop     r15
0x180017191  pop     r13
0x180017193  retn
```
