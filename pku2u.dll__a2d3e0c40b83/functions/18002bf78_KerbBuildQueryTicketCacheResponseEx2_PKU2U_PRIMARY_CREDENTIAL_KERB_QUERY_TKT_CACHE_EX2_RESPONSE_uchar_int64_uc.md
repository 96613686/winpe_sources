# KerbBuildQueryTicketCacheResponseEx2(_PKU2U_PRIMARY_CREDENTIAL *,_KERB_QUERY_TKT_CACHE_EX2_RESPONSE *,uchar,__int64 *,uchar * *,ulong *)

- ea: `0x18002bf78`
- end: `0x18002c15f`
- name: `?KerbBuildQueryTicketCacheResponseEx2@@YAXPEAU_PKU2U_PRIMARY_CREDENTIAL@@PEAU_KERB_QUERY_TKT_CACHE_EX2_RESPONSE@@EPEA_JPEAPEAEPEAK@Z`
- size: `487`
- prototype: `void(PRTL_CRITICAL_SECTION CriticalSection, struct _KERB_QUERY_TKT_CACHE_EX2_RESPONSE *, unsigned __int8, __int64 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002c8c0`

## callees

- `0x18002bf78`
- `0x18002c224`
- `0x18002c2cc`
- `0x180044f8c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002c158`
- `ntdll!RtlEnterCriticalSection` at `0x18002bfd5`
- `ntdll!RtlEnterCriticalSection` at `0x18002bfd5`

## pseudocode

```c
void __fastcall KerbBuildQueryTicketCacheResponseEx2(
        PRTL_CRITICAL_SECTION CriticalSection,
        struct _KERB_QUERY_TKT_CACHE_EX2_RESPONSE *a2,
        char a3,
        __int64 *a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  __int64 *v6; // rdi
  char v7; // bl
  HANDLE *i; // rsi
  __int64 v11; // rcx
  __int64 v12; // rax
  LARGE_INTEGER v13; // rdx
  unsigned __int8 *v14; // rbx
  __int64 v15; // rdi
  USHORT v16; // ax
  __int64 v17; // rdx
  struct _KERB_INTERNAL_NAME *v18; // rcx
  __int64 v19; // rdx
  int v20; // ecx
  __int64 v21; // rbx
  USHORT LockCount; // ax
  void *v23; // rcx

  v6 = a4;
  v7 = a3;
  if ( !*a5 )
    *a5 = (unsigned __int8 *)a2->Tickets + a2->CountOfTickets * (a3 != 0 ? 72 : 104);
  RtlEnterCriticalSection(CriticalSection);
  _mm_lfence();
  for ( i = (HANDLE *)CriticalSection[2].OwningThread; i != &CriticalSection[2].OwningThread; *a6 = v19 + 1 )
  {
    v11 = *v6;
    v12 = *a6;
    v13.QuadPart = (LONGLONG)i[10];
    if ( v7 )
    {
      v20 = *(_DWORD *)a5 + v11;
      v21 = 9 * v12;
      *((LARGE_INTEGER *)&a2->Tickets[0].ServerName.Length + v21) = v13;
      *((_QWORD *)&a2->Tickets[0].ServerName.Buffer + v21) = i[11];
      *((_QWORD *)&a2->Tickets[0].ServerRealm.Length + v21) = i[12];
      *((_DWORD *)&a2->Tickets[0].ServerRealm.Buffer + 2 * v21) = *((_DWORD *)i + 35);
      *((_DWORD *)&a2->Tickets[0].ServerRealm.Buffer + 2 * v21 + 1) = *((_DWORD *)i + 12);
      LockCount = CriticalSection[1].LockCount;
      *(_DWORD *)(&a2->Tickets[0].ClientName.MaximumLength + 4 * v21 + 1) = v20;
      v23 = *a5;
      *(&a2->Tickets[0].ClientName.MaximumLength + 4 * v21) = LockCount;
      *(&a2->Tickets[0].ClientName.Length + 4 * v21) = LockCount;
      memcpy_0(v23, CriticalSection[1].OwningThread, LOWORD(CriticalSection[1].LockCount));
      *a5 += LOWORD(CriticalSection[1].LockCount);
      KerbPutKdcNameAsWOWString(
        (struct _KERB_INTERNAL_NAME *)i[4],
        (struct _STRING32 *)&a2->Tickets[0].ClientRealm + v21,
        *v6,
        a5);
      v19 = *a6;
      *(&a2->Tickets[0].StartTime.LowPart + 18 * v19) = *((_DWORD *)i + 14);
    }
    else
    {
      v14 = *a5;
      v15 = v12;
      a2->Tickets[v15].StartTime = v13;
      a2->Tickets[v15].EndTime.QuadPart = (LONGLONG)i[11];
      a2->Tickets[v15].RenewTime.QuadPart = (LONGLONG)i[12];
      a2->Tickets[v15].EncryptionType = *((_DWORD *)i + 35);
      a2->Tickets[v15].TicketFlags = *((_DWORD *)i + 12);
      v16 = CriticalSection[1].LockCount;
      a2->Tickets[v15].ClientName.MaximumLength = v16;
      a2->Tickets[v15].ClientName.Length = v16;
      a2->Tickets[v15].ClientName.Buffer = (PWSTR)&v14[v11];
      memcpy_0(v14, CriticalSection[1].OwningThread, LOWORD(CriticalSection[1].LockCount));
      v17 = v15 * 104 + 40;
      v6 = a4;
      v18 = (struct _KERB_INTERNAL_NAME *)i[4];
      *a5 = &v14[LOWORD(CriticalSection[1].LockCount)];
      KerbPutKdcNameAsString(v18, (struct _UNICODE_STRING *)((char *)a2 + v17), *a4, a5);
      v19 = *a6;
      a2->Tickets[v19].SessionKeyType = *((_DWORD *)i + 14);
    }
    i = (HANDLE *)*i;
    v7 = a3;
  }
  RtlLeaveCriticalSection(CriticalSection);
}

```

## disassembly

```asm
0x18002bf78  mov     [rsp+arg_0], rbx
0x18002bf7d  mov     [rsp+arg_18], r9
0x18002bf82  mov     [rsp+arg_10], r8b
0x18002bf87  push    rbp
0x18002bf88  push    rsi
0x18002bf89  push    rdi
0x18002bf8a  push    r12
0x18002bf8c  push    r13
0x18002bf8e  push    r14
0x18002bf90  push    r15
0x18002bf92  sub     rsp, 20h
0x18002bf96  mov     r15, [rsp+58h+arg_20]
0x18002bf9e  mov     al, r8b
0x18002bfa1  neg     al
0x18002bfa3  mov     rdi, r9
0x18002bfa6  mov     bl, r8b
0x18002bfa9  mov     r14, rdx
0x18002bfac  sbb     r10d, r10d
0x18002bfaf  mov     rbp, rcx
0x18002bfb2  and     r10d, 0FFFFFFE0h
0x18002bfb6  add     r10d, 68h ; 'h'
0x18002bfba  cmp     qword ptr [r15], 0
0x18002bfbe  jnz     short loc_18002BFD2
0x18002bfc0  imul    r10d, [rdx+4]
0x18002bfc5  mov     ecx, r10d
0x18002bfc8  add     rcx, 8
0x18002bfcc  add     rcx, rdx
0x18002bfcf  mov     [r15], rcx
0x18002bfd2  mov     rcx, rbp; CriticalSection
0x18002bfd5  call    cs:__imp_RtlEnterCriticalSection
0x18002bfdb  lea     r12, [rbp+60h]
0x18002bfdf  lfence
0x18002bfe2  mov     rsi, [r12]
0x18002bfe6  cmp     rsi, r12
0x18002bfe9  jz      loc_18002C141
0x18002bfef  mov     r13, [rsp+58h+arg_28]
0x18002bff7  mov     rcx, [rdi]
0x18002bffa  mov     eax, [r13+0]
0x18002bffe  mov     rdx, [rsi+50h]
0x18002c002  test    bl, bl
0x18002c004  jnz     loc_18002C0A2
0x18002c00a  mov     rbx, [r15]
0x18002c00d  imul    rdi, rax, 68h ; 'h'
0x18002c011  mov     [rdi+r14+48h], rdx
0x18002c016  mov     rax, [rsi+58h]
0x18002c01a  mov     [rdi+r14+50h], rax
0x18002c01f  mov     rax, [rsi+60h]
0x18002c023  mov     [rdi+r14+58h], rax
0x18002c028  mov     eax, [rsi+8Ch]
0x18002c02e  mov     [rdi+r14+60h], eax
0x18002c033  mov     eax, [rsi+30h]
0x18002c036  mov     [rdi+r14+64h], eax
0x18002c03b  movzx   eax, word ptr [rbp+30h]
0x18002c03f  mov     [rdi+r14+0Ah], ax
0x18002c045  mov     [rdi+r14+8], ax
0x18002c04b  lea     rax, [rcx+rbx]
0x18002c04f  mov     [rdi+r14+10h], rax
0x18002c054  mov     rcx, rbx; void *
0x18002c057  movzx   r8d, word ptr [rbp+30h]; Size
0x18002c05c  mov     rdx, [rbp+38h]; Src
0x18002c060  call    memcpy_0
0x18002c065  movzx   eax, word ptr [rbp+30h]
0x18002c069  lea     rdx, [rdi+28h]
0x18002c06d  mov     rdi, [rsp+58h+arg_18]
0x18002c072  add     rax, rbx
0x18002c075  mov     rcx, [rsi+20h]; struct _KERB_INTERNAL_NAME *
0x18002c079  add     rdx, r14; struct _UNICODE_STRING *
0x18002c07c  mov     r9, r15; unsigned __int8 **
0x18002c07f  mov     [r15], rax
0x18002c082  mov     r8, [rdi]; __int64
0x18002c085  call    ?KerbPutKdcNameAsString@@YAXPEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@_JPEAPEAE@Z; KerbPutKdcNameAsString(_KERB_INTERNAL_NAME *,_UNICODE_STRING *,__int64,uchar * *)
0x18002c08a  mov     edx, [r13+0]
0x18002c08e  lea     rax, [rdx+1]
0x18002c092  imul    rcx, rax, 68h ; 'h'
0x18002c096  mov     eax, [rsi+38h]
0x18002c099  mov     [rcx+r14], eax
0x18002c09d  jmp     loc_18002C12A
0x18002c0a2  add     ecx, [r15]
0x18002c0a5  lea     rbx, [rax+rax*8]
0x18002c0a9  mov     [r14+rbx*8+28h], rdx
0x18002c0ae  mov     rax, [rsi+58h]
0x18002c0b2  mov     [r14+rbx*8+30h], rax
0x18002c0b7  mov     rax, [rsi+60h]
0x18002c0bb  mov     [r14+rbx*8+38h], rax
0x18002c0c0  mov     eax, [rsi+8Ch]
0x18002c0c6  mov     [r14+rbx*8+40h], eax
0x18002c0cb  mov     eax, [rsi+30h]
0x18002c0ce  mov     [r14+rbx*8+44h], eax
0x18002c0d3  movzx   eax, word ptr [rbp+30h]
0x18002c0d7  mov     [r14+rbx*8+0Ch], ecx
0x18002c0dc  mov     rcx, [r15]; void *
0x18002c0df  mov     [r14+rbx*8+0Ah], ax
0x18002c0e5  mov     [r14+rbx*8+8], ax
0x18002c0eb  movzx   r8d, word ptr [rbp+30h]; Size
0x18002c0f0  mov     rdx, [rbp+38h]; Src
0x18002c0f4  call    memcpy_0
0x18002c0f9  movzx   eax, word ptr [rbp+30h]
0x18002c0fd  lea     rdx, [r14+18h]
0x18002c101  add     [r15], rax
0x18002c104  lea     rdx, [rdx+rbx*8]; struct _STRING32 *
0x18002c108  mov     r8, [rdi]; __int64
0x18002c10b  mov     r9, r15; unsigned __int8 **
0x18002c10e  mov     rcx, [rsi+20h]; struct _KERB_INTERNAL_NAME *
0x18002c112  call    ?KerbPutKdcNameAsWOWString@@YAXPEAU_KERB_INTERNAL_NAME@@PEAU_STRING32@@_JPEAPEAE@Z; KerbPutKdcNameAsWOWString(_KERB_INTERNAL_NAME *,_STRING32 *,__int64,uchar * *)
0x18002c117  mov     edx, [r13+0]
0x18002c11b  lea     rax, [rdx+1]
0x18002c11f  lea     rcx, [rax+rax*8]
0x18002c123  mov     eax, [rsi+38h]
0x18002c126  mov     [r14+rcx*8], eax
0x18002c12a  mov     rsi, [rsi]
0x18002c12d  lea     eax, [rdx+1]
0x18002c130  mov     bl, [rsp+58h+arg_10]
0x18002c134  mov     [r13+0], eax
0x18002c138  cmp     rsi, r12
0x18002c13b  jnz     loc_18002BFF7
0x18002c141  mov     rcx, rbp
0x18002c144  mov     rbx, [rsp+58h+arg_0]
0x18002c149  add     rsp, 20h
0x18002c14d  pop     r15
0x18002c14f  pop     r14
0x18002c151  pop     r13
0x18002c153  pop     r12
0x18002c155  pop     rdi
0x18002c156  pop     rsi
0x18002c157  pop     rbp
0x18002c158  jmp     cs:__imp_RtlLeaveCriticalSection
```
