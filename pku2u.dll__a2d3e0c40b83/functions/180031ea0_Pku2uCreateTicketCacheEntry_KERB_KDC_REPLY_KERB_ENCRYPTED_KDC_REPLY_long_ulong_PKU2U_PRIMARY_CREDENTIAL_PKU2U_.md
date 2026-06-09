# Pku2uCreateTicketCacheEntry(KERB_KDC_REPLY *,KERB_ENCRYPTED_KDC_REPLY *,long,ulong,_PKU2U_PRIMARY_CREDENTIAL *,_PKU2U_TICKET_CACHE_ENTRY * *)

- ea: `0x180031ea0`
- end: `0x1800320c9`
- name: `?Pku2uCreateTicketCacheEntry@@YAJPEAUKERB_KDC_REPLY@@PEAUKERB_ENCRYPTED_KDC_REPLY@@JKPEAU_PKU2U_PRIMARY_CREDENTIAL@@PEAPEAU_PKU2U_TICKET_CACHE_ENTRY@@@Z`
- size: `553`
- prototype: `__int64 __fastcall(struct KERB_KDC_REPLY *, struct KERB_ENCRYPTED_KDC_REPLY *, int, unsigned int, PRTL_CRITICAL_SECTION CriticalSection, union _LARGE_INTEGER)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800355cc`

## callees

- `0x180014240`
- `0x180014f70`
- `0x180016a10`
- `0x180017940`
- `0x180018870`
- `0x180018c00`
- `0x180018df0`
- `0x180019928`
- `0x180020afc`
- `0x180023cb8`
- `0x1800311f0`
- `0x180031ea0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180031f12`
- `ntdll!RtlLeaveCriticalSection` at `0x1800320a5`
- `ntdll!RtlLeaveCriticalSection` at `0x180031f12`
- `ntdll!RtlLeaveCriticalSection` at `0x1800320a5`
- `ntdll!RtlEnterCriticalSection` at `0x180031efe`
- `ntdll!RtlEnterCriticalSection` at `0x18003207a`
- `ntdll!RtlEnterCriticalSection` at `0x180031efe`
- `ntdll!RtlEnterCriticalSection` at `0x18003207a`

## pseudocode

```c
__int64 __fastcall Pku2uCreateTicketCacheEntry(
        struct KERB_KDC_REPLY *a1,
        struct KERB_ENCRYPTED_KDC_REPLY *a2,
        int a3,
        int a4,
        PRTL_CRITICAL_SECTION CriticalSection,
        union _LARGE_INTEGER a6)
{
  _QWORD *QuadPart; // r15
  basessp::BaseSSP *v9; // rcx
  _DWORD *v12; // rax
  _DWORD *v13; // rdi
  unsigned int v14; // ebx
  int v15; // edx
  struct _PKU2U_TICKET_CACHE_ENTRY *v16; // rax
  struct _PKU2U_TICKET_CACHE_ENTRY *v17; // rsi
  HANDLE *p_OwningThread; // rax
  PRTL_CRITICAL_SECTION *OwningThread; // rcx

  QuadPart = (_QWORD *)a6.QuadPart;
  v9 = Pku2uGlobalBaseSSP;
  *(_QWORD *)a6.QuadPart = 0;
  v12 = basessp::BaseSSP::WSTAllocate(v9, 0xB8u);
  v13 = v12;
  if ( !v12 )
    return (unsigned int)-1073741670;
  v12[4] = 1;
  RtlEnterCriticalSection(&Pku2uGlobalTicketListLock);
  ++Pku2uGlobalTicketListSize;
  RtlLeaveCriticalSection(&Pku2uGlobalTicketListLock);
  v13[44] = a3;
  v13[45] = a4;
  if ( a2 )
  {
    v13[12] = KerbConvertFlagsToUlong((char *)a2 + 64);
    if ( (unsigned int)KerbDuplicateKey(
                         (struct KERB_ENCRYPTION_KEY *)(v13 + 14),
                         (struct KERB_ENCRYPTED_KDC_REPLY *)((char *)a2 + 8)) )
    {
LABEL_16:
      v14 = -1073741670;
LABEL_17:
      Pku2uDereferenceTicketCacheEntry((struct _PKU2U_TICKET_CACHE_ENTRY *)v13);
      return v14;
    }
    KerbConvertGeneralizedTimeToLargeInt(
      (PLARGE_INTEGER)v13 + 10,
      (struct KERB_ENCRYPTED_KDC_REPLY *)((char *)a2 + ((*(_BYTE *)a2 & 0x40) != 0 ? 94LL : 80LL)),
      0);
    KerbConvertGeneralizedTimeToLargeInt(
      (PLARGE_INTEGER)v13 + 11,
      (struct KERB_ENCRYPTED_KDC_REPLY *)((char *)a2 + 108),
      0);
    if ( (*(_BYTE *)a2 & 0x20) != 0 )
      KerbConvertGeneralizedTimeToLargeInt(
        (PLARGE_INTEGER)v13 + 12,
        (struct KERB_ENCRYPTED_KDC_REPLY *)((char *)a2 + 122),
        0);
    v15 = v13[44];
    a6.QuadPart = -Pku2uGlobalSkewTime.QuadPart;
    if ( Pku2uIsExpiring((union _LARGE_INTEGER *)v13 + 11, v15, &a6) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e620118210cc360496f33e71fb07ec1b_Traceguids);
      v14 = -1073741517;
      goto LABEL_17;
    }
  }
  if ( (unsigned int)KerbConvertPrincipalNameToKdcName(
                       (struct _KERB_INTERNAL_NAME **)v13 + 4,
                       (struct KERB_KDC_REPLY *)((char *)a1 + 64))
    || *((_QWORD *)a1 + 5)
    && (unsigned int)KerbConvertPrincipalNameToKdcName(
                       (struct _KERB_INTERNAL_NAME **)v13 + 5,
                       (struct KERB_KDC_REPLY *)((char *)a1 + 32))
    || (unsigned int)KerbDuplicateTicket((struct KERB_TICKET *)(v13 + 26), (struct KERB_KDC_REPLY *)((char *)a1 + 48)) )
  {
    goto LABEL_16;
  }
  if ( CriticalSection )
  {
    v16 = Pku2uLookupTicketCacheEntry(CriticalSection, *((struct _KERB_INTERNAL_NAME **)v13 + 4));
    v17 = v16;
    if ( v16 )
    {
      Pku2uRemoveTicketCacheEntry(CriticalSection, v16);
      Pku2uDereferenceTicketCacheEntry(v17);
    }
    _InterlockedAdd(v13 + 4, 1u);
    RtlEnterCriticalSection(CriticalSection);
    p_OwningThread = &CriticalSection[2].OwningThread;
    OwningThread = (PRTL_CRITICAL_SECTION *)CriticalSection[2].OwningThread;
    if ( OwningThread[1] != (PRTL_CRITICAL_SECTION)&CriticalSection[2].OwningThread )
      __fastfail(3u);
    *(_QWORD *)v13 = OwningThread;
    *((_QWORD *)v13 + 1) = p_OwningThread;
    OwningThread[1] = (PRTL_CRITICAL_SECTION)v13;
    *p_OwningThread = v13;
    RtlLeaveCriticalSection(CriticalSection);
    _InterlockedCompareExchange(v13 + 6, 1, 0);
  }
  *QuadPart = v13;
  return 0;
}

```

## disassembly

```asm
0x180031ea0  push    rbx
0x180031ea2  push    rbp
0x180031ea3  push    rsi
0x180031ea4  push    rdi
0x180031ea5  push    r12
0x180031ea7  push    r14
0x180031ea9  push    r15
0x180031eab  sub     rsp, 20h
0x180031eaf  mov     r15, qword ptr [rsp+58h+arg_28]
0x180031eb7  mov     rbx, rdx
0x180031eba  mov     rbp, rcx
0x180031ebd  mov     edx, 0B8h; unsigned __int64
0x180031ec2  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x180031ec9  mov     esi, r9d
0x180031ecc  mov     r14d, r8d
0x180031ecf  mov     qword ptr [r15], 0
0x180031ed6  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x180031edb  mov     rdi, rax
0x180031ede  test    rax, rax
0x180031ee1  jnz     short loc_180031EED
0x180031ee3  mov     ebx, 0C000009Ah
0x180031ee8  jmp     loc_1800320B8
0x180031eed  mov     r12d, 1
0x180031ef3  lea     rcx, ?Pku2uGlobalTicketListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180031efa  mov     [rax+10h], r12d
0x180031efe  call    cs:__imp_RtlEnterCriticalSection
0x180031f04  add     cs:?Pku2uGlobalTicketListSize@@3JA, r12d; long Pku2uGlobalTicketListSize
0x180031f0b  lea     rcx, ?Pku2uGlobalTicketListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180031f12  call    cs:__imp_RtlLeaveCriticalSection
0x180031f18  mov     [rdi+0B0h], r14d
0x180031f1f  mov     [rdi+0B4h], esi
0x180031f25  test    rbx, rbx
0x180031f28  jz      loc_180031FF5
0x180031f2e  lea     rcx, [rbx+40h]; void *
0x180031f32  call    ?KerbConvertFlagsToUlong@@YAKPEAX@Z; KerbConvertFlagsToUlong(void *)
0x180031f37  lea     rdx, [rbx+8]; struct KERB_ENCRYPTION_KEY *
0x180031f3b  mov     [rdi+30h], eax
0x180031f3e  lea     rcx, [rdi+38h]; struct KERB_ENCRYPTION_KEY *
0x180031f42  call    ?KerbDuplicateKey@@YAJPEAUKERB_ENCRYPTION_KEY@@0@Z; KerbDuplicateKey(KERB_ENCRYPTION_KEY *,KERB_ENCRYPTION_KEY *)
0x180031f47  test    eax, eax
0x180031f49  jnz     loc_18003202F
0x180031f4f  mov     al, [rbx]
0x180031f51  lea     rcx, [rdi+50h]; Time
0x180031f55  and     al, 40h
0x180031f57  neg     al
0x180031f59  sbb     rdx, rdx
0x180031f5c  xor     r8d, r8d; int
0x180031f5f  and     edx, 0Eh
0x180031f62  add     rdx, 50h ; 'P'
0x180031f66  add     rdx, rbx; struct tagASN1generalizedtime_t *
0x180031f69  call    ?KerbConvertGeneralizedTimeToLargeInt@@YAXPEAT_LARGE_INTEGER@@PEAUtagASN1generalizedtime_t@@H@Z; KerbConvertGeneralizedTimeToLargeInt(_LARGE_INTEGER *,tagASN1generalizedtime_t *,int)
0x180031f6e  lea     rdx, [rbx+6Ch]; struct tagASN1generalizedtime_t *
0x180031f72  xor     r8d, r8d; int
0x180031f75  lea     rcx, [rdi+58h]; Time
0x180031f79  call    ?KerbConvertGeneralizedTimeToLargeInt@@YAXPEAT_LARGE_INTEGER@@PEAUtagASN1generalizedtime_t@@H@Z; KerbConvertGeneralizedTimeToLargeInt(_LARGE_INTEGER *,tagASN1generalizedtime_t *,int)
0x180031f7e  test    byte ptr [rbx], 20h
0x180031f81  jz      short loc_180031F93
0x180031f83  lea     rdx, [rbx+7Ah]; struct tagASN1generalizedtime_t *
0x180031f87  xor     r8d, r8d; int
0x180031f8a  lea     rcx, [rdi+60h]; Time
0x180031f8e  call    ?KerbConvertGeneralizedTimeToLargeInt@@YAXPEAT_LARGE_INTEGER@@PEAUtagASN1generalizedtime_t@@H@Z; KerbConvertGeneralizedTimeToLargeInt(_LARGE_INTEGER *,tagASN1generalizedtime_t *,int)
0x180031f93  mov     rax, cs:?Pku2uGlobalSkewTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER Pku2uGlobalSkewTime
0x180031f9a  lea     r8, [rsp+58h+arg_28]; union _LARGE_INTEGER *
0x180031fa2  mov     edx, [rdi+0B0h]; int
0x180031fa8  lea     rcx, [rdi+58h]; union _LARGE_INTEGER *
0x180031fac  neg     rax
0x180031faf  mov     qword ptr [rsp+58h+arg_28], rax
0x180031fb7  call    ?Pku2uIsExpiring@@YAEPEAT_LARGE_INTEGER@@J0@Z; Pku2uIsExpiring(_LARGE_INTEGER *,long,_LARGE_INTEGER *)
0x180031fbc  test    al, al
0x180031fbe  jz      short loc_180031FF5
0x180031fc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180031fc7  lea     rax, WPP_GLOBAL_Control
0x180031fce  cmp     rcx, rax
0x180031fd1  jz      short loc_180031FEE
0x180031fd3  test    [rcx+1Ch], r12b
0x180031fd7  jz      short loc_180031FEE
0x180031fd9  mov     rcx, [rcx+10h]
0x180031fdd  lea     r8, WPP_e620118210cc360496f33e71fb07ec1b_Traceguids
0x180031fe4  mov     edx, 0Ah
0x180031fe9  call    WPP_SF_
0x180031fee  mov     ebx, 0C0000133h
0x180031ff3  jmp     short loc_180032034
0x180031ff5  lea     rdx, [rbp+40h]; struct KERB_PRINCIPAL_NAME *
0x180031ff9  lea     rcx, [rdi+20h]; struct _KERB_INTERNAL_NAME **
0x180031ffd  call    ?KerbConvertPrincipalNameToKdcName@@YAJPEAPEAU_KERB_INTERNAL_NAME@@PEAUKERB_PRINCIPAL_NAME@@@Z; KerbConvertPrincipalNameToKdcName(_KERB_INTERNAL_NAME * *,KERB_PRINCIPAL_NAME *)
0x180032002  test    eax, eax
0x180032004  jnz     short loc_18003202F
0x180032006  lea     rdx, [rbp+20h]; struct KERB_PRINCIPAL_NAME *
0x18003200a  cmp     qword ptr [rdx+8], 0
0x18003200f  jz      short loc_18003201E
0x180032011  lea     rcx, [rdi+28h]; struct _KERB_INTERNAL_NAME **
0x180032015  call    ?KerbConvertPrincipalNameToKdcName@@YAJPEAPEAU_KERB_INTERNAL_NAME@@PEAUKERB_PRINCIPAL_NAME@@@Z; KerbConvertPrincipalNameToKdcName(_KERB_INTERNAL_NAME * *,KERB_PRINCIPAL_NAME *)
0x18003201a  test    eax, eax
0x18003201c  jnz     short loc_18003202F
0x18003201e  lea     rcx, [rdi+68h]; struct KERB_TICKET *
0x180032022  lea     rdx, [rbp+30h]; struct KERB_TICKET *
0x180032026  call    ?KerbDuplicateTicket@@YAJPEAUKERB_TICKET@@0@Z; KerbDuplicateTicket(KERB_TICKET *,KERB_TICKET *)
0x18003202b  test    eax, eax
0x18003202d  jz      short loc_18003203E
0x18003202f  mov     ebx, 0C000009Ah
0x180032034  mov     rcx, rdi; struct _PKU2U_TICKET_CACHE_ENTRY *
0x180032037  call    ?Pku2uDereferenceTicketCacheEntry@@YAXPEAU_PKU2U_TICKET_CACHE_ENTRY@@@Z; Pku2uDereferenceTicketCacheEntry(_PKU2U_TICKET_CACHE_ENTRY *)
0x18003203c  jmp     short loc_1800320B8
0x18003203e  mov     rbx, [rsp+58h+CriticalSection]
0x180032046  test    rbx, rbx
0x180032049  jz      short loc_1800320B3
0x18003204b  mov     rdx, [rdi+20h]; struct _KERB_INTERNAL_NAME *
0x18003204f  mov     rcx, rbx; CriticalSection
0x180032052  call    ?Pku2uLookupTicketCacheEntry@@YAPEAU_PKU2U_TICKET_CACHE_ENTRY@@PEAU_PKU2U_PRIMARY_CREDENTIAL@@PEAU_KERB_INTERNAL_NAME@@@Z; Pku2uLookupTicketCacheEntry(_PKU2U_PRIMARY_CREDENTIAL *,_KERB_INTERNAL_NAME *)
0x180032057  mov     rsi, rax
0x18003205a  test    rax, rax
0x18003205d  jz      short loc_180032072
0x18003205f  mov     rdx, rax; struct _PKU2U_TICKET_CACHE_ENTRY *
0x180032062  mov     rcx, rbx; CriticalSection
0x180032065  call    ?Pku2uRemoveTicketCacheEntry@@YAEPEAU_PKU2U_PRIMARY_CREDENTIAL@@PEAU_PKU2U_TICKET_CACHE_ENTRY@@@Z; Pku2uRemoveTicketCacheEntry(_PKU2U_PRIMARY_CREDENTIAL *,_PKU2U_TICKET_CACHE_ENTRY *)
0x18003206a  mov     rcx, rsi; struct _PKU2U_TICKET_CACHE_ENTRY *
0x18003206d  call    ?Pku2uDereferenceTicketCacheEntry@@YAXPEAU_PKU2U_TICKET_CACHE_ENTRY@@@Z; Pku2uDereferenceTicketCacheEntry(_PKU2U_TICKET_CACHE_ENTRY *)
0x180032072  lock add [rdi+10h], r12d
0x180032077  mov     rcx, rbx; CriticalSection
0x18003207a  call    cs:__imp_RtlEnterCriticalSection
0x180032080  lea     rax, [rbx+60h]
0x180032084  mov     rcx, [rax]
0x180032087  cmp     [rcx+8], rax
0x18003208b  jz      short loc_180032094
0x18003208d  mov     ecx, 3
0x180032092  int     29h; Win8: RtlFailFast(ecx)
0x180032094  mov     [rdi], rcx
0x180032097  mov     [rdi+8], rax
0x18003209b  mov     [rcx+8], rdi
0x18003209f  mov     rcx, rbx; CriticalSection
0x1800320a2  mov     [rax], rdi
0x1800320a5  call    cs:__imp_RtlLeaveCriticalSection
0x1800320ab  xor     eax, eax
0x1800320ad  lock cmpxchg [rdi+18h], r12d
0x1800320b3  mov     [r15], rdi
0x1800320b6  xor     ebx, ebx
0x1800320b8  mov     eax, ebx
0x1800320ba  add     rsp, 20h
0x1800320be  pop     r15
0x1800320c0  pop     r14
0x1800320c2  pop     r12
0x1800320c4  pop     rdi
0x1800320c5  pop     rsi
0x1800320c6  pop     rbp
0x1800320c7  pop     rbx
0x1800320c8  retn
```
