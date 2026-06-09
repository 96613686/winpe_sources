# KerbPurgeServiceTicketAndTgt(_KERB_CONTEXT *,unsigned __int64,_KERB_CREDMAN_CRED *)

- ea: `0x1800abf4c`
- end: `0x1800ac3d6`
- name: `?KerbPurgeServiceTicketAndTgt@@YAEPEAU_KERB_CONTEXT@@_KPEAU_KERB_CREDMAN_CRED@@@Z`
- size: `1162`
- prototype: `unsigned __int8(struct _KERB_CONTEXT *, unsigned __int64, struct _KERB_CREDMAN_CRED *)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, service_task`

## callers

- `0x180021574`
- `0x1800cbea8`

## callees

- `0x1800063e8`
- `0x180007e80`
- `0x180009afc`
- `0x18000a630`
- `0x180016600`
- `0x18002bd40`
- `0x180037aa0`
- `0x18006557c`
- `0x180070680`
- `0x18008b70c`
- `0x1800abf4c`
- `0x1800f1ea0`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x1800ac16d`
- `ntdll!RtlCopyUnicodeString` at `0x1800ac249`
- `ntdll!RtlCopyUnicodeString` at `0x1800ac16d`
- `ntdll!RtlCopyUnicodeString` at `0x1800ac249`
- `ntdll!RtlInitUnicodeString` at `0x1800ac259`
- `ntdll!RtlInitUnicodeString` at `0x1800ac259`
- `ntdll!RtlReleaseResource` at `0x1800ac0a0`
- `ntdll!RtlReleaseResource` at `0x1800ac0a0`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800ac081`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800ac081`
- `ntdll!RtlEnterCriticalSection` at `0x1800ac005`
- `ntdll!RtlEnterCriticalSection` at `0x1800ac005`
- `ntdll!RtlLeaveCriticalSection` at `0x1800ac332`
- `ntdll!RtlLeaveCriticalSection` at `0x1800ac332`

## string_xrefs

- `0x1800ac342`: `KerbPurgeServiceTicket supplied w/ bogus cred handle\n`
- `0x1800abfde`: `KerbPurgeServiceTicketAndTgt`
- `0x1800ac059`: `KerbPurgeServiceTicketAndTgt`
- `0x1800ac2ac`: `KerbPurgeServiceTicketAndTgt`
- `0x1800ac2fc`: `KerbPurgeServiceTicketAndTgt`
- `0x1800ac34f`: `KerbPurgeServiceTicketAndTgt`

## pseudocode

```c
char __fastcall KerbPurgeServiceTicketAndTgt(
        struct _KERB_CONTEXT *a1,
        struct _KERB_CREDENTIAL *a2,
        struct _KERB_CREDMAN_CRED *a3)
{
  char v5; // r12
  struct _KERB_LOGON_SESSION *LogonSession; // rax
  struct _KERB_LOGON_SESSION *v7; // r14
  char *v8; // rdi
  __int64 v9; // r13
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  struct _KERB_CREDENTIAL **v13; // rbx
  unsigned __int64 MaximumLength; // rsi
  unsigned __int64 v15; // rcx
  __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  void *v18; // rsp
  void *v19; // rsp
  _DWORD *v20; // rax
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rdx
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rsi
  struct _KERB_CREDENTIAL **v26; // rbx
  unsigned __int64 v27; // rcx
  __int64 v28; // rcx
  unsigned __int64 v29; // rcx
  void *v30; // rsp
  void *v31; // rsp
  _DWORD *v32; // rax
  struct _UNICODE_STRING *p_DestinationString; // rbx
  struct _KERB_TICKET_CACHE_ENTRY *TicketCacheEntryByRealm; // rax
  struct _KERB_TICKET_CACHE_ENTRY *v35; // rsi
  struct _KERB_TICKET_CACHE_ENTRY *v36; // rax
  struct _KERB_TICKET_CACHE_ENTRY *v37; // rsi
  _BYTE v39[32]; // [rsp+0h] [rbp-30h] BYREF
  struct _KERB_CREDENTIAL *v40; // [rsp+30h] [rbp+0h] BYREF
  __int64 v41; // [rsp+38h] [rbp+8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp+10h] BYREF
  struct _UNICODE_STRING v43; // [rsp+50h] [rbp+20h] BYREF
  struct _UNICODE_STRING v44; // [rsp+60h] [rbp+30h] BYREF

  v40 = 0;
  v5 = 0;
  if ( (int)KerbReferenceCredentialEx(a2, 0, 0, 0, &v40) >= 0 && v40 )
  {
    LogonSession = KerbLocateLogonSession((const struct _LUID *)((char *)v40 + 28), 0);
    v7 = LogonSession;
    if ( !LogonSession )
    {
      KerbTracerT::Log(
        1,
        "KerbPurgeServiceTicketAndTgt",
        8085,
        "Couldn't find LUID %#x:%#x\n",
        *((_DWORD *)v40 + 8),
        *((_DWORD *)v40 + 7));
      goto LABEL_48;
    }
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)LogonSession + 2);
    if ( v40 && (v8 = (char *)*((_QWORD *)v40 + 9)) != 0 )
    {
      KerbTracerT::Log(
        3,
        "KerbPurgeServiceTicketAndTgt",
        8097,
        "Purging tgt associated with SUPPLIED creds (%S\\%S)\n",
        *((_QWORD *)v8 + 3),
        *((_QWORD *)v8 + 1));
    }
    else if ( a3 )
    {
      v8 = (char *)*((_QWORD *)a3 + 8);
      KerbTracerT::Log(
        3,
        "KerbPurgeServiceTicketAndTgt",
        8103,
        "Purging tgt associated with CREDMAN creds (%S\\%S)\n",
        *((_QWORD *)v8 + 3),
        *((_QWORD *)v8 + 1));
    }
    else
    {
      v8 = (char *)v7 + 120;
      KerbTracerT::Log(
        3,
        "KerbPurgeServiceTicketAndTgt",
        8109,
        "Purging tgt associated with PRIMARY creds (%S\\%S)\n",
        *((_QWORD *)v7 + 18),
        *((_QWORD *)v7 + 16));
    }
    RtlAcquireResourceExclusive(&KerbContextResource, 1u);
    v9 = *((_QWORD *)a1 + 34);
    *((_QWORD *)a1 + 34) = 0;
    RtlReleaseResource(&KerbContextResource);
    v13 = 0;
    DestinationString = *(struct _UNICODE_STRING *)(v9 + 64);
    MaximumLength = DestinationString.MaximumLength;
    if ( !DestinationString.MaximumLength )
      goto LABEL_59;
    if ( DestinationString.MaximumLength > (unsigned __int64)g_ulMaxStackAllocSize )
      goto LABEL_59;
    v15 = DestinationString.MaximumLength + g_ulAdditionalProbeSize + 8;
    if ( v15 < DestinationString.MaximumLength || !(unsigned int)VerifyStackAvailable(v15, v10, v11, v12) )
      goto LABEL_59;
    v16 = MaximumLength + 23;
    if ( MaximumLength + 23 <= MaximumLength + 8 )
      v16 = 0xFFFFFFFFFFFFFF0LL;
    v17 = v16 & 0xFFFFFFFFFFFFFFF0uLL;
    v18 = alloca(v17);
    v19 = alloca(v17);
    v13 = &v40;
    if ( v39 == (_BYTE *)-48LL || (LODWORD(v40) = 1801679955, (v13 = (struct _KERB_CREDENTIAL **)&v41) == 0) )
    {
LABEL_59:
      if ( MaximumLength + 8 >= MaximumLength )
      {
        v20 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        v13 = (struct _KERB_CREDENTIAL **)v20;
        if ( v20 )
        {
          *v20 = 1885431112;
          v13 = (struct _KERB_CREDENTIAL **)(v20 + 2);
        }
      }
    }
    DestinationString.Buffer = (PWSTR)v13;
    if ( !v13 )
      goto LABEL_46;
    RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(v9 + 64));
    v23 = 0;
    v43.Length = *(_WORD *)(v9 + 80);
    v24 = *(unsigned __int16 *)(v9 + 82);
    v43.MaximumLength = *(_WORD *)(v9 + 82);
    *(_DWORD *)(&v43.MaximumLength + 1) = *(_DWORD *)(v9 + 84);
    v43.Buffer = *(PWSTR *)(v9 + 88);
    if ( v43.Buffer && (_WORD)v24 )
    {
      v25 = (unsigned int)v24;
      v26 = 0;
      if ( v24 > g_ulMaxStackAllocSize )
        goto LABEL_60;
      v27 = (unsigned int)v24 + g_ulAdditionalProbeSize + 8;
      if ( v27 < v25 || !(unsigned int)VerifyStackAvailable(v27, 0, v21, v22) )
        goto LABEL_60;
      v28 = v25 + 23;
      if ( v25 + 23 <= v25 + 8 )
        v28 = 0xFFFFFFFFFFFFFF0LL;
      v29 = v28 & 0xFFFFFFFFFFFFFFF0uLL;
      v30 = alloca(v29);
      v31 = alloca(v29);
      v26 = &v40;
      if ( v39 == (_BYTE *)-48LL || (LODWORD(v40) = 1801679955, (v26 = (struct _KERB_CREDENTIAL **)&v41) == 0) )
      {
LABEL_60:
        if ( v25 + 8 >= v25 )
        {
          v32 = (_DWORD *)((__int64 (__fastcall *)(unsigned __int64, __int64))g_pfnAllocate)(v25 + 8, v23);
          v26 = (struct _KERB_CREDENTIAL **)v32;
          if ( v32 )
          {
            *v32 = 1885431112;
            v26 = (struct _KERB_CREDENTIAL **)(v32 + 2);
          }
        }
      }
      v43.Buffer = (PWSTR)v26;
      if ( !v26 )
        goto LABEL_46;
      RtlCopyUnicodeString(&v43, (PCUNICODE_STRING)(v9 + 80));
    }
    p_DestinationString = &DestinationString;
    RtlInitUnicodeString(&v44, 0);
    KerbRemoveTicketCacheEntry((struct _KERB_TICKET_CACHE_ENTRY *)v9);
    KerbDereferenceTicketCacheEntry((struct _KERB_TICKET_CACHE_ENTRY *)v9);
    do
    {
      TicketCacheEntryByRealm = KerbLocateTicketCacheEntryByRealm(
                                  (struct _KERB_TICKET_CACHE *)(v8 + 240),
                                  p_DestinationString,
                                  1u);
      v35 = TicketCacheEntryByRealm;
      if ( TicketCacheEntryByRealm )
      {
        KerbRemoveTicketCacheEntry(TicketCacheEntryByRealm);
        KerbDereferenceTicketCacheEntry(v35);
      }
      else
      {
        KerbTracerT::Log(
          3,
          "KerbPurgeServiceTicketAndTgt",
          8167,
          "Didn't find primary TGT for %S \n",
          p_DestinationString->Buffer);
      }
      v36 = KerbLocateTicketCacheEntryByRealm((struct _KERB_TICKET_CACHE *)(v8 + 240), p_DestinationString, 2u);
      v37 = v36;
      if ( v36 )
      {
        KerbRemoveTicketCacheEntry(v36);
        KerbDereferenceTicketCacheEntry(v37);
      }
      else
      {
        KerbTracerT::Log(
          3,
          "KerbPurgeServiceTicketAndTgt",
          8183,
          "Didn't find delegation TGT for %S\n",
          p_DestinationString->Buffer);
      }
      ++p_DestinationString;
    }
    while ( p_DestinationString->Buffer );
    v5 = 1;
LABEL_46:
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v7 + 2);
    KerbDereferenceLogonSession(v7);
    goto LABEL_48;
  }
  KerbTracerT::Log(1, "KerbPurgeServiceTicketAndTgt", 8078, "KerbPurgeServiceTicket supplied w/ bogus cred handle\n");
LABEL_48:
  if ( v40 )
    KerbDereferenceCredential(v40);
  if ( DestinationString.Buffer && *((_DWORD *)DestinationString.Buffer - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v43.Buffer && *((_DWORD *)v43.Buffer - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return v5;
}

```

## disassembly

```asm
0x1800abf4c  push    rbp
0x1800abf4e  push    rsi
0x1800abf4f  push    rdi
0x1800abf50  push    r12
0x1800abf52  push    r13
0x1800abf54  push    r14
0x1800abf56  push    r15
0x1800abf58  sub     rsp, 80h
0x1800abf5f  lea     rbp, [rsp+30h]
0x1800abf64  mov     [rbp+80h+arg_18], rbx
0x1800abf6b  mov     rax, cs:__security_cookie
0x1800abf72  xor     rax, rbp
0x1800abf75  mov     [rbp+80h+var_40], rax
0x1800abf79  mov     rsi, rcx
0x1800abf7c  mov     rax, rdx
0x1800abf7f  lea     rcx, [rbp+80h+var_80]
0x1800abf83  mov     rbx, r8
0x1800abf86  mov     [rsp+0B0h+var_90], rcx; struct _KERB_CREDENTIAL **
0x1800abf8b  xor     r13d, r13d
0x1800abf8e  mov     rcx, rax; struct _KERB_CREDENTIAL *
0x1800abf91  mov     [rbp+80h+var_80], r13
0x1800abf95  xor     r9d, r9d; int
0x1800abf98  xor     r8d, r8d; unsigned __int8
0x1800abf9b  xor     edx, edx; unsigned int
0x1800abf9d  mov     r12b, r13b
0x1800abfa0  call    ?KerbReferenceCredentialEx@@YAJ_KKEHPEAPEAU_KERB_CREDENTIAL@@@Z; KerbReferenceCredentialEx(unsigned __int64,ulong,uchar,int,_KERB_CREDENTIAL * *)
0x1800abfa5  test    eax, eax
0x1800abfa7  js      loc_1800AC342
0x1800abfad  mov     rcx, [rbp+80h+var_80]
0x1800abfb1  test    rcx, rcx
0x1800abfb4  jz      loc_1800AC342
0x1800abfba  add     rcx, 1Ch; struct _LUID *
0x1800abfbe  xor     edx, edx; unsigned __int8
0x1800abfc0  call    ?KerbLocateLogonSession@@YAPEAU_KERB_LOGON_SESSION@@PEBU_LUID@@E@Z; KerbLocateLogonSession(_LUID const *,uchar)
0x1800abfc5  mov     r14, rax
0x1800abfc8  test    rax, rax
0x1800abfcb  jnz     short loc_1800AC001
0x1800abfcd  mov     rcx, [rbp+80h+var_80]
0x1800abfd1  lea     r9, aCouldnTFindLui; "Couldn't find LUID %#x:%#x\n"
0x1800abfd8  mov     r8d, 1F95h
0x1800abfde  lea     rdx, aKerbpurgeservi; "KerbPurgeServiceTicketAndTgt"
0x1800abfe5  mov     eax, [rcx+1Ch]
0x1800abfe8  mov     dword ptr [rsp+0B0h+var_88], eax
0x1800abfec  mov     eax, [rcx+20h]
0x1800abfef  lea     ecx, [r13+1]
0x1800abff3  mov     dword ptr [rsp+0B0h+var_90], eax
0x1800abff7  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800abffc  jmp     loc_1800AC360
0x1800ac001  lea     rcx, [rax+50h]; CriticalSection
0x1800ac005  call    cs:__imp_RtlEnterCriticalSection
0x1800ac00b  mov     rdi, [rbp+80h+var_80]
0x1800ac00f  test    rdi, rdi
0x1800ac012  jz      short loc_1800AC02C
0x1800ac014  mov     rdi, [rdi+48h]
0x1800ac018  test    rdi, rdi
0x1800ac01b  jz      short loc_1800AC02C
0x1800ac01d  mov     r8d, 1FA1h
0x1800ac023  lea     r9, aPurgingTgtAsso; "Purging tgt associated with SUPPLIED cr"...
0x1800ac02a  jmp     short loc_1800AC055
0x1800ac02c  test    rbx, rbx
0x1800ac02f  jz      short loc_1800AC044
0x1800ac031  mov     rdi, [rbx+40h]
0x1800ac035  lea     r9, aPurgingTgtAsso_0; "Purging tgt associated with CREDMAN cre"...
0x1800ac03c  mov     r8d, 1FA7h
0x1800ac042  jmp     short loc_1800AC055
0x1800ac044  lea     rdi, [r14+78h]
0x1800ac048  mov     r8d, 1FADh
0x1800ac04e  lea     r9, aPurgingTgtAsso_1; "Purging tgt associated with PRIMARY cre"...
0x1800ac055  mov     rcx, [rdi+8]
0x1800ac059  lea     rdx, aKerbpurgeservi; "KerbPurgeServiceTicketAndTgt"
0x1800ac060  mov     rax, [rdi+18h]
0x1800ac064  mov     [rsp+0B0h+var_88], rcx
0x1800ac069  mov     ecx, 3
0x1800ac06e  mov     [rsp+0B0h+var_90], rax
0x1800ac073  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800ac078  mov     dl, 1; Wait
0x1800ac07a  lea     rcx, ?KerbContextResource@@3U_RTL_RESOURCE@@A; Resource
0x1800ac081  call    cs:__imp_RtlAcquireResourceExclusive
0x1800ac087  mov     r13, [rsi+110h]
0x1800ac08e  lea     rcx, ?KerbContextResource@@3U_RTL_RESOURCE@@A; Resource
0x1800ac095  mov     qword ptr [rsi+110h], 0
0x1800ac0a0  call    cs:__imp_RtlReleaseResource
0x1800ac0a6  movzx   eax, word ptr [r13+40h]
0x1800ac0ab  xor     ebx, ebx
0x1800ac0ad  mov     [rbp+80h+DestinationString.Length], ax
0x1800ac0b1  movzx   ecx, word ptr [r13+42h]
0x1800ac0b6  mov     [rbp+80h+DestinationString.MaximumLength], cx
0x1800ac0ba  mov     esi, ecx
0x1800ac0bc  mov     eax, [r13+44h]
0x1800ac0c0  mov     dword ptr [rbp+80h+DestinationString+4], eax
0x1800ac0c3  mov     rax, [r13+48h]
0x1800ac0c7  mov     [rbp+80h+DestinationString.Buffer], rax
0x1800ac0cb  test    rcx, rcx
0x1800ac0ce  jz      short loc_1800AC131
0x1800ac0d0  cmp     rcx, cs:g_ulMaxStackAllocSize
0x1800ac0d7  ja      short loc_1800AC131
0x1800ac0d9  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800ac0e0  add     rcx, 8
0x1800ac0e4  add     rcx, rsi
0x1800ac0e7  cmp     rcx, rsi
0x1800ac0ea  jb      short loc_1800AC131
0x1800ac0ec  call    VerifyStackAvailable
0x1800ac0f1  test    eax, eax
0x1800ac0f3  jz      short loc_1800AC131
0x1800ac0f5  lea     rax, [rsi+8]
0x1800ac0f9  lea     rcx, [rax+0Fh]
0x1800ac0fd  cmp     rcx, rax
0x1800ac100  ja      short loc_1800AC10C
0x1800ac102  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800ac10c  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800ac110  mov     rax, rcx
0x1800ac113  call    _alloca_probe
0x1800ac118  sub     rsp, rcx
0x1800ac11b  lea     rbx, [rsp+0B0h+var_80]
0x1800ac120  test    rbx, rbx
0x1800ac123  jz      short loc_1800AC131
0x1800ac125  mov     dword ptr [rbx], 6B637453h
0x1800ac12b  add     rbx, 8
0x1800ac12f  jnz     short loc_1800AC158
0x1800ac131  lea     rcx, [rsi+8]
0x1800ac135  cmp     rcx, rsi
0x1800ac138  jb      short loc_1800AC158
0x1800ac13a  mov     rax, cs:g_pfnAllocate
0x1800ac141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac146  mov     rbx, rax
0x1800ac149  test    rax, rax
0x1800ac14c  jz      short loc_1800AC158
0x1800ac14e  mov     dword ptr [rax], 70616548h
0x1800ac154  add     rbx, 8
0x1800ac158  mov     [rbp+80h+DestinationString.Buffer], rbx
0x1800ac15c  test    rbx, rbx
0x1800ac15f  jz      loc_1800AC32E
0x1800ac165  lea     rdx, [r13+40h]; SourceString
0x1800ac169  lea     rcx, [rbp+80h+DestinationString]; DestinationString
0x1800ac16d  call    cs:__imp_RtlCopyUnicodeString
0x1800ac173  movzx   eax, word ptr [r13+50h]
0x1800ac178  xor     edx, edx
0x1800ac17a  mov     [rbp+80h+var_60.Length], ax
0x1800ac17e  movzx   ecx, word ptr [r13+52h]
0x1800ac183  mov     [rbp+80h+var_60.MaximumLength], cx
0x1800ac187  mov     eax, [r13+54h]
0x1800ac18b  mov     dword ptr [rbp+80h+var_60+4], eax
0x1800ac18e  mov     rax, [r13+58h]
0x1800ac192  mov     [rbp+80h+var_60.Buffer], rax
0x1800ac196  test    rax, rax
0x1800ac199  jz      loc_1800AC24F
0x1800ac19f  test    cx, cx
0x1800ac1a2  jz      loc_1800AC24F
0x1800ac1a8  cmp     rcx, cs:g_ulMaxStackAllocSize
0x1800ac1af  mov     esi, ecx
0x1800ac1b1  mov     ebx, edx
0x1800ac1b3  ja      short loc_1800AC20D
0x1800ac1b5  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800ac1bc  add     rcx, 8
0x1800ac1c0  add     rcx, rsi
0x1800ac1c3  cmp     rcx, rsi
0x1800ac1c6  jb      short loc_1800AC20D
0x1800ac1c8  call    VerifyStackAvailable
0x1800ac1cd  test    eax, eax
0x1800ac1cf  jz      short loc_1800AC20D
0x1800ac1d1  lea     rax, [rsi+8]
0x1800ac1d5  lea     rcx, [rax+0Fh]
0x1800ac1d9  cmp     rcx, rax
0x1800ac1dc  ja      short loc_1800AC1E8
0x1800ac1de  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800ac1e8  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800ac1ec  mov     rax, rcx
0x1800ac1ef  call    _alloca_probe
0x1800ac1f4  sub     rsp, rcx
0x1800ac1f7  lea     rbx, [rsp+0B0h+var_80]
0x1800ac1fc  test    rbx, rbx
0x1800ac1ff  jz      short loc_1800AC20D
0x1800ac201  mov     dword ptr [rbx], 6B637453h
0x1800ac207  add     rbx, 8
0x1800ac20b  jnz     short loc_1800AC234
0x1800ac20d  lea     rcx, [rsi+8]
0x1800ac211  cmp     rcx, rsi
0x1800ac214  jb      short loc_1800AC234
0x1800ac216  mov     rax, cs:g_pfnAllocate
0x1800ac21d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac222  mov     rbx, rax
0x1800ac225  test    rax, rax
0x1800ac228  jz      short loc_1800AC234
0x1800ac22a  mov     dword ptr [rax], 70616548h
0x1800ac230  add     rbx, 8
0x1800ac234  mov     [rbp+80h+var_60.Buffer], rbx
0x1800ac238  test    rbx, rbx
0x1800ac23b  jz      loc_1800AC32E
0x1800ac241  lea     rdx, [r13+50h]; SourceString
0x1800ac245  lea     rcx, [rbp+80h+var_60]; DestinationString
0x1800ac249  call    cs:__imp_RtlCopyUnicodeString
0x1800ac24f  xor     edx, edx; SourceString
0x1800ac251  lea     rcx, [rbp+80h+var_50]; DestinationString
0x1800ac255  lea     rbx, [rbp+80h+DestinationString]
0x1800ac259  call    cs:__imp_RtlInitUnicodeString
0x1800ac25f  mov     rcx, r13; struct _KERB_TICKET_CACHE_ENTRY *
0x1800ac262  call    ?KerbRemoveTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbRemoveTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x1800ac267  mov     rcx, r13; struct _KERB_TICKET_CACHE_ENTRY *
0x1800ac26a  call    ?KerbDereferenceTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbDereferenceTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x1800ac26f  xor     r13d, r13d
0x1800ac272  lea     r15, [rdi+0F0h]
0x1800ac279  lea     r12d, [r13+3]
0x1800ac27d  mov     r8d, 1; unsigned int
0x1800ac283  mov     rdx, rbx; struct _UNICODE_STRING *
0x1800ac286  mov     rcx, r15; struct _KERB_TICKET_CACHE *
0x1800ac289  call    ?KerbLocateTicketCacheEntryByRealm@@YAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KERB_TICKET_CACHE@@PEAU_UNICODE_STRING@@K@Z; KerbLocateTicketCacheEntryByRealm(_KERB_TICKET_CACHE *,_UNICODE_STRING *,ulong)
0x1800ac28e  mov     rsi, rax
0x1800ac291  test    rax, rax
0x1800ac294  jnz     short loc_1800AC2BD
0x1800ac296  mov     rax, [rbx+8]
0x1800ac29a  lea     r9, aDidnTFindPrima; "Didn't find primary TGT for %S \n"
0x1800ac2a1  mov     r8d, 1FE7h
0x1800ac2a7  mov     [rsp+0B0h+var_90], rax
0x1800ac2ac  lea     rdx, aKerbpurgeservi; "KerbPurgeServiceTicketAndTgt"
0x1800ac2b3  mov     ecx, r12d
0x1800ac2b6  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800ac2bb  jmp     short loc_1800AC2CD
0x1800ac2bd  mov     rcx, rsi; struct _KERB_TICKET_CACHE_ENTRY *
0x1800ac2c0  call    ?KerbRemoveTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbRemoveTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x1800ac2c5  mov     rcx, rsi; struct _KERB_TICKET_CACHE_ENTRY *
0x1800ac2c8  call    ?KerbDereferenceTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbDereferenceTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x1800ac2cd  mov     r8d, 2; unsigned int
0x1800ac2d3  mov     rdx, rbx; struct _UNICODE_STRING *
0x1800ac2d6  mov     rcx, r15; struct _KERB_TICKET_CACHE *
0x1800ac2d9  call    ?KerbLocateTicketCacheEntryByRealm@@YAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KERB_TICKET_CACHE@@PEAU_UNICODE_STRING@@K@Z; KerbLocateTicketCacheEntryByRealm(_KERB_TICKET_CACHE *,_UNICODE_STRING *,ulong)
0x1800ac2de  mov     rsi, rax
0x1800ac2e1  test    rax, rax
0x1800ac2e4  jnz     short loc_1800AC30D
0x1800ac2e6  mov     rax, [rbx+8]
0x1800ac2ea  lea     r9, aDidnTFindDeleg; "Didn't find delegation TGT for %S\n"
0x1800ac2f1  mov     r8d, 1FF7h
0x1800ac2f7  mov     [rsp+0B0h+var_90], rax
0x1800ac2fc  lea     rdx, aKerbpurgeservi; "KerbPurgeServiceTicketAndTgt"
0x1800ac303  mov     ecx, r12d
0x1800ac306  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800ac30b  jmp     short loc_1800AC31D
0x1800ac30d  mov     rcx, rsi; struct _KERB_TICKET_CACHE_ENTRY *
0x1800ac310  call    ?KerbRemoveTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbRemoveTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x1800ac315  mov     rcx, rsi; struct _KERB_TICKET_CACHE_ENTRY *
0x1800ac318  call    ?KerbDereferenceTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbDereferenceTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x1800ac31d  add     rbx, 10h
0x1800ac321  cmp     [rbx+8], r13
0x1800ac325  jnz     loc_1800AC27D
0x1800ac32b  mov     r12b, 1
0x1800ac32e  lea     rcx, [r14+50h]; CriticalSection
0x1800ac332  call    cs:__imp_RtlLeaveCriticalSection
0x1800ac338  mov     rcx, r14; struct _KERB_LOGON_SESSION *
0x1800ac33b  call    ?KerbDereferenceLogonSession@@YAXPEAU_KERB_LOGON_SESSION@@@Z; KerbDereferenceLogonSession(_KERB_LOGON_SESSION *)
0x1800ac340  jmp     short loc_1800AC360
0x1800ac342  lea     r9, aKerbpurgeservi_0; "KerbPurgeServiceTicket supplied w/ bogu"...
0x1800ac349  mov     r8d, 1F8Eh
0x1800ac34f  lea     rdx, aKerbpurgeservi; "KerbPurgeServiceTicketAndTgt"
0x1800ac356  mov     ecx, 1
0x1800ac35b  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800ac360  mov     rcx, [rbp+80h+var_80]; struct _KERB_CREDENTIAL *
0x1800ac364  test    rcx, rcx
0x1800ac367  jz      short loc_1800AC36E
0x1800ac369  call    ?KerbDereferenceCredential@@YAXPEAU_KERB_CREDENTIAL@@@Z; KerbDereferenceCredential(_KERB_CREDENTIAL *)
0x1800ac36e  mov     rax, [rbp+80h+DestinationString.Buffer]
0x1800ac372  test    rax, rax
0x1800ac375  jz      short loc_1800AC38F
0x1800ac377  lea     rcx, [rax-8]
0x1800ac37b  cmp     dword ptr [rcx], 70616548h
0x1800ac381  jnz     short loc_1800AC38F
0x1800ac383  mov     rax, cs:g_pfnFree
0x1800ac38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac38f  mov     rcx, [rbp+80h+var_60.Buffer]
0x1800ac393  test    rcx, rcx
0x1800ac396  jz      short loc_1800AC3B0
0x1800ac398  add     rcx, 0FFFFFFFFFFFFFFF8h
0x1800ac39c  cmp     dword ptr [rcx], 70616548h
0x1800ac3a2  jnz     short loc_1800AC3B0
0x1800ac3a4  mov     rax, cs:g_pfnFree
0x1800ac3ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac3b0  mov     al, r12b
0x1800ac3b3  mov     rcx, [rbp+80h+var_40]
0x1800ac3b7  xor     rcx, rbp; StackCookie
0x1800ac3ba  call    __security_check_cookie
0x1800ac3bf  mov     rbx, [rbp+80h+arg_18]
0x1800ac3c6  lea     rsp, [rbp+50h]
0x1800ac3ca  pop     r15
0x1800ac3cc  pop     r14
0x1800ac3ce  pop     r13
0x1800ac3d0  pop     r12
0x1800ac3d2  pop     rdi
0x1800ac3d3  pop     rsi
0x1800ac3d4  pop     rbp
0x1800ac3d5  retn
```
