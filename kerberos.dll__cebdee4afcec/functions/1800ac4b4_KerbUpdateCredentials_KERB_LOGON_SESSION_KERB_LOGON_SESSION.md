# KerbUpdateCredentials(_KERB_LOGON_SESSION *,_KERB_LOGON_SESSION *)

- ea: `0x1800ac4b4`
- end: `0x1800acc76`
- name: `?KerbUpdateCredentials@@YAJPEAU_KERB_LOGON_SESSION@@0@Z`
- size: `1986`
- prototype: `__int64 __fastcall(struct _KERB_LOGON_SESSION *, struct _KERB_LOGON_SESSION *)`
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004969c`
- `0x1800acc7c`

## callees

- `0x1800063e8`
- `0x180012240`
- `0x180014b40`
- `0x180032964`
- `0x180037aa0`
- `0x180047f2c`
- `0x1800541b0`
- `0x18006517c`
- `0x1800654c8`
- `0x1800656cc`
- `0x18006e5d0`
- `0x18008b70c`
- `0x18008f410`
- `0x1800ac3dc`
- `0x1800ac4b4`

## import_xrefs

- `KerbClientShared!KerbClientFreeStoredCred` at `0x1800acab5`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x1800acace`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x1800acb11`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x1800acb27`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x1800acab5`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x1800acace`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x1800acb11`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x1800acb27`

## string_xrefs

- `0x1800ac4d9`: `KerbUpdateCredentials old logon session %#x:%#x, from %#x:%#x, for user %wZ\%wZ\n`
- `0x1800ac4ce`: `KerbUpdateCredentials`
- `0x1800ac712`: `KerbUpdateCredentials`
- `0x1800ac7df`: `KerbUpdateCredentials`
- `0x1800ac877`: `KerbUpdateCredentials`
- `0x1800ac973`: `KerbUpdateCredentials`
- `0x1800aca43`: `KerbUpdateCredentials`
- `0x1800acae7`: `KerbUpdateCredentials`
- `0x1800acb3f`: `KerbUpdateCredentials`
- `0x1800acb6c`: `KerbUpdateCredentials`
- `0x1800acc27`: `KerbUpdateCredentials`
- `0x1800ac57b`: `KerbUpdateCredentials: OldLogonSession %#x:%x and LogonSession %#x:%x have SameKeys = %d\n`
- `0x1800ac708`: `Updated flags in OldLogonSession %p to 0x%x`
- `0x1800ac865`: `Clearing ticket cache in OldLogonSession %p due to LogonSession being deferred`

## pseudocode

```c
__int64 __fastcall KerbUpdateCredentials(struct _KERB_LOGON_SESSION *a1, struct _KERB_LOGON_SESSION *a2)
{
  unsigned int v2; // r12d
  __int128 v5; // xmm6
  __int128 v6; // xmm8
  __int128 v7; // xmm7
  __int128 v8; // xmm9
  struct _KERB_STORED_CREDENTIAL *v9; // r13
  char v10; // r14
  char v11; // di
  struct _KERB_TICKET_CACHE_ENTRY *TicketCacheEntryByRealm; // rax
  struct _KERB_TICKET_CACHE_ENTRY *v13; // rax
  int v14; // edx
  unsigned int v15; // edx
  unsigned int v16; // edx
  unsigned int v17; // edx
  unsigned int v18; // edx
  unsigned int v19; // edx
  _QWORD *v20; // rdi
  const char *v21; // r9
  __int64 v22; // r8
  struct _KERB_STORED_CREDENTIAL *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  struct _KERB_STORED_CREDENTIAL *v26; // rax
  int v27; // edi
  struct _KERB_STORED_CREDENTIAL *v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v33; // [rsp+50h] [rbp-98h]
  char v34; // [rsp+F0h] [rbp+8h]
  bool v35; // [rsp+F8h] [rbp+10h]
  int v36; // [rsp+100h] [rbp+18h]
  struct _KERB_STORED_CREDENTIAL *v37; // [rsp+108h] [rbp+20h]

  v2 = 0;
  v37 = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v33 = 0;
  v34 = 0;
  v36 = 0;
  KerbTracerT::Log(
    10,
    "KerbUpdateCredentials",
    8450,
    "KerbUpdateCredentials old logon session %#x:%#x, from %#x:%#x, for user %wZ\\%wZ\n",
    *((_DWORD *)a1 + 17),
    *((_DWORD *)a1 + 16),
    *((_DWORD *)a2 + 17),
    *((_DWORD *)a2 + 16),
    (char *)a2 + 136,
    (char *)a2 + 120);
  v35 = KerbCompareKeys(*((struct _KERB_STORED_CREDENTIAL **)a1 + 33), *((struct _KERB_STORED_CREDENTIAL **)a2 + 33));
  KerbTracerT::Log(
    10,
    "KerbUpdateCredentials",
    8455,
    "KerbUpdateCredentials: OldLogonSession %#x:%x and LogonSession %#x:%x have SameKeys = %d\n",
    *((_DWORD *)a1 + 17),
    *((_DWORD *)a1 + 16),
    *((_DWORD *)a2 + 17),
    *((_DWORD *)a2 + 16),
    v35);
  v10 = 0;
  v11 = 0;
  TicketCacheEntryByRealm = KerbLocateTicketCacheEntryByRealm((struct _KERB_LOGON_SESSION *)((char *)a2 + 360), 0, 1u);
  if ( TicketCacheEntryByRealm )
  {
    v10 = 1;
    KerbDereferenceTicketCacheEntry(TicketCacheEntryByRealm);
  }
  if ( ((*((_BYTE *)a2 + 904) & 1) == 0) != v10 )
    MicrosoftTelemetryAssertTriggeredNoArgs((*((_DWORD *)a2 + 226) & 1) == 0);
  v13 = KerbLocateTicketCacheEntryByRealm((struct _KERB_LOGON_SESSION *)((char *)a1 + 360), 0, 1u);
  if ( v13 )
  {
    v11 = 1;
    KerbDereferenceTicketCacheEntry(v13);
  }
  v14 = *((_DWORD *)a1 + 226);
  if ( ((*((_BYTE *)a1 + 904) & 1) == 0) != v11 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs((*((_DWORD *)a1 + 226) & 1) == 0);
    v14 = *((_DWORD *)a1 + 226);
  }
  if ( v10 || v11 )
  {
    v15 = v14 & 0xFFFFFFFE;
    *((_DWORD *)a1 + 226) = v15;
    if ( v10 )
      goto LABEL_15;
    KerbTracerT::Log(
      2,
      "KerbUpdateCredentials",
      8506,
      "no new primary TGT in the unlock logon session, keep the old TGT\n");
  }
  else
  {
    KerbTracerT::Log(2, "KerbUpdateCredentials", 8515, "Failed to find primary TGT on *OLD* logon session\n");
    *((_DWORD *)a1 + 226) |= 1u;
  }
  v15 = *((_DWORD *)a1 + 226);
LABEL_15:
  if ( (*((_BYTE *)a2 + 904) & 0x10) != 0 )
    v16 = v15 | 0x10;
  else
    v16 = v15 & 0xFFFFFFEF;
  *((_DWORD *)a1 + 226) = v16;
  if ( (*((_BYTE *)a2 + 904) & 0x20) != 0 )
    v17 = v16 | 0x20;
  else
    v17 = v16 & 0xFFFFFFDF;
  *((_DWORD *)a1 + 226) = v17;
  if ( *((char *)a2 + 904) >= 0 )
    v18 = v17 & 0xFFFFFF7F;
  else
    v18 = v17 | 0x80;
  *((_DWORD *)a1 + 226) = v18;
  if ( (*((_DWORD *)a2 + 226) & 0x1000000) != 0 )
    v19 = v18 | 0x1000000;
  else
    v19 = v18 & 0xFEFFFFFF;
  *((_DWORD *)a1 + 226) = v19;
  if ( (*((_BYTE *)a2 + 904) & 1) != 0 )
  {
    v19 &= ~0x400000u;
    *((_DWORD *)a1 + 226) = v19;
  }
  KerbTracerT::Log(
    3,
    "KerbUpdateCredentials",
    8528,
    "Updated flags in OldLogonSession %p to 0x%x",
    (const void *)WORD1(a1),
    v19);
  if ( (*((_DWORD *)a1 + 16) == 999 || *((_DWORD *)a1 + 16) == 996) && !*((_DWORD *)a1 + 17) )
  {
    v20 = (_QWORD *)((char *)a2 + 400);
    v2 = 1;
    if ( *((_QWORD *)a2 + 50) )
    {
      v9 = (struct _KERB_STORED_CREDENTIAL *)*((_QWORD *)a1 + 33);
      v21 = "Updating OldLogonSession %p due to the present of public key credentials";
      v5 = *(_OWORD *)((char *)a1 + 152);
      *((_QWORD *)a1 + 33) = 0;
      v22 = 8554;
      v6 = *(_OWORD *)((char *)a1 + 168);
      *(_OWORD *)((char *)a1 + 152) = 0;
      *(_OWORD *)((char *)a1 + 168) = 0;
      v23 = (struct _KERB_STORED_CREDENTIAL *)*((_QWORD *)a1 + 34);
      v7 = *(_OWORD *)((char *)a1 + 184);
      *((_QWORD *)a1 + 34) = 0;
      v8 = *(_OWORD *)((char *)a1 + 200);
      *(_OWORD *)((char *)a1 + 184) = 0;
      *(_OWORD *)((char *)a1 + 200) = 0;
      goto LABEL_35;
    }
    v25 = *((_QWORD *)a1 + 50);
    v33 = v25;
    *((_QWORD *)a1 + 50) = 0;
    v34 = 1;
    if ( !v35 )
    {
      v9 = (struct _KERB_STORED_CREDENTIAL *)*((_QWORD *)a2 + 33);
      v5 = *(_OWORD *)((char *)a2 + 152);
      *((_QWORD *)a2 + 33) = 0;
      v6 = *(_OWORD *)((char *)a2 + 168);
      v36 = 1;
      *(_OWORD *)((char *)a2 + 152) = 0;
      *(_OWORD *)((char *)a2 + 168) = 0;
      v26 = (struct _KERB_STORED_CREDENTIAL *)*((_QWORD *)a1 + 33);
      v7 = *(_OWORD *)((char *)a1 + 152);
      *((_QWORD *)a1 + 33) = 0;
      v8 = *(_OWORD *)((char *)a1 + 168);
      v37 = v26;
      *(_OWORD *)((char *)a1 + 152) = 0;
      *(_OWORD *)((char *)a1 + 168) = 0;
      KerbTracerT::Log(
        3,
        "KerbUpdateCredentials",
        8576,
        "Updating OldLogonSession %p due to key mismatch",
        (const void *)WORD1(a1));
      v25 = v33;
    }
    if ( v25 )
    {
      *((_DWORD *)a1 + 226) |= 0x10u;
      v10 = 0;
    }
  }
  else
  {
    v20 = (_QWORD *)((char *)a2 + 400);
    if ( *((_QWORD *)a2 + 50) )
      goto LABEL_50;
    if ( !*((_QWORD *)a1 + 50) && !v35 )
    {
      v9 = (struct _KERB_STORED_CREDENTIAL *)*((_QWORD *)a2 + 33);
      v21 = "Updating OldLogonSession %p with new password due to key mismatch";
      v5 = *(_OWORD *)((char *)a2 + 152);
      *((_QWORD *)a2 + 33) = 0;
      v22 = 8605;
      v6 = *(_OWORD *)((char *)a2 + 168);
      *(_OWORD *)((char *)a2 + 152) = 0;
      *(_OWORD *)((char *)a2 + 168) = 0;
      v23 = (struct _KERB_STORED_CREDENTIAL *)*((_QWORD *)a1 + 33);
      v7 = *(_OWORD *)((char *)a1 + 152);
      *((_QWORD *)a1 + 33) = 0;
      v8 = *(_OWORD *)((char *)a1 + 168);
      *(_OWORD *)((char *)a1 + 152) = 0;
      *(_OWORD *)((char *)a1 + 168) = 0;
LABEL_35:
      v36 = 1;
      v37 = v23;
      KerbTracerT::Log(3, "KerbUpdateCredentials", v22, v21, WORD1(a1));
    }
  }
  if ( !*v20 && !*((_QWORD *)a1 + 50) && (*((_BYTE *)a1 + 904) & 1) == 0 && (*((_BYTE *)a2 + 904) & 1) != 0 && !v34 )
  {
    KerbPurgeTicketCache((struct _KERB_LOGON_SESSION *)((char *)a1 + 360));
    KerbPurgeTicketCache((struct _KERB_LOGON_SESSION *)((char *)a1 + 320));
    KerbPurgeTicketCache((struct _KERB_LOGON_SESSION *)((char *)a1 + 280));
    KerbTracerT::Log(
      3,
      "KerbUpdateCredentials",
      8628,
      "Clearing ticket cache in OldLogonSession %p due to LogonSession being deferred",
      (const void *)WORD1(a1));
    goto LABEL_51;
  }
LABEL_50:
  KerbFreePrimaryCredentials((struct _KERB_LOGON_SESSION *)((char *)a1 + 120), 0);
  KerbPurgeTicketCache((struct _KERB_LOGON_SESSION *)((char *)a2 + 320));
  KerbPurgeTicketCache((struct _KERB_LOGON_SESSION *)((char *)a2 + 280));
  KerbAgeS4U2ProxyCache((struct _KERB_LOGON_SESSION *)((char *)a2 + 608), 1u, 1u);
  KerbTransferPrimaryCredentials(
    (struct _KERB_LOGON_SESSION *)((char *)a1 + 120),
    (struct _KERB_LOGON_SESSION *)((char *)a2 + 120));
  KerbTracerT::Log(
    3,
    "KerbUpdateCredentials",
    8645,
    "Transferred primary credentials from LogonSession %p to OldLogonSession %p",
    (const void *)WORD1(a2),
    (const void *)WORD1(a1));
LABEL_51:
  if ( v36 )
  {
    KerbFreePlaintextPassword((struct _KERB_LOGON_SESSION *)((char *)a1 + 152));
    *(_OWORD *)((char *)a1 + 152) = v5;
    *(_OWORD *)((char *)a1 + 168) = v6;
    KerbFreePlaintextPassword((struct _KERB_LOGON_SESSION *)((char *)a1 + 184));
    *(_OWORD *)((char *)a1 + 184) = v7;
    *(_OWORD *)((char *)a1 + 200) = v8;
    v27 = KerbRebuildKeys(a1, 1, v2);
    if ( v27 >= 0 )
    {
      if ( v9 )
        KerbClientFreeStoredCred(v9);
      if ( v37 )
        KerbClientFreeStoredCred(v37);
      KerbTracerT::Log(
        3,
        "KerbUpdateCredentials",
        8691,
        "Sucessfully rebuilt keys in OldLogonSession %p with new password",
        (const void *)WORD1(a1));
    }
    else
    {
      KerbClientFreeStoredCred(*((struct _KERB_STORED_CREDENTIAL **)a1 + 33));
      v28 = (struct _KERB_STORED_CREDENTIAL *)*((_QWORD *)a1 + 34);
      *((_QWORD *)a1 + 33) = v9;
      if ( v28 )
        KerbClientFreeStoredCred(v28);
      *((_QWORD *)a1 + 34) = v37;
      KerbTracerT::Log(
        1,
        "KerbUpdateCredentials",
        8676,
        "Failed to rebuild keys in OldLogonSession %p with status 0x%x",
        (const void *)WORD1(a1),
        v27);
    }
  }
  if ( v34 )
  {
    KerbTracerT::Log(
      3,
      "KerbUpdateCredentials",
      8697,
      "Restoring public key credentials to OldLogonSession %p",
      (const void *)WORD1(a1));
    *((_QWORD *)a1 + 50) = v33;
  }
  if ( *((struct _KERB_LOGON_SESSION **)a1 + 40) != (struct _KERB_LOGON_SESSION *)((char *)a1 + 320) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v24);
  KerbInitTicketCache((struct _KERB_LOGON_SESSION *)((char *)a1 + 320));
  if ( *((struct _KERB_LOGON_SESSION **)a1 + 35) != (struct _KERB_LOGON_SESSION *)((char *)a1 + 280) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v29);
  KerbInitTicketCache((struct _KERB_LOGON_SESSION *)((char *)a1 + 280));
  if ( *((struct _KERB_LOGON_SESSION **)a2 + 40) != (struct _KERB_LOGON_SESSION *)((char *)a2 + 320) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v30);
  KerbInitTicketCache((struct _KERB_LOGON_SESSION *)((char *)a2 + 320));
  if ( *((struct _KERB_LOGON_SESSION **)a2 + 35) != (struct _KERB_LOGON_SESSION *)((char *)a2 + 280) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v31);
  KerbInitTicketCache((struct _KERB_LOGON_SESSION *)((char *)a2 + 280));
  *((_DWORD *)a1 + 233) = *((_DWORD *)a2 + 233);
  KerbCleanupLogonSessionCredentials(a1);
  if ( v10 )
  {
    KerbTransferTicketCache(
      (struct _KERB_LOGON_SESSION *)((char *)a2 + 360),
      (struct _KERB_LOGON_SESSION *)((char *)a1 + 360));
    KerbTracerT::Log(
      3,
      "KerbUpdateCredentials",
      8723,
      "Transferred TGT from LogonSession %p to OldLogonSession %p",
      (const void *)WORD1(a2),
      (const void *)WORD1(a1));
  }
  return 0;
}

```

## disassembly

```asm
0x1800ac4b4  mov     rax, rsp
0x1800ac4b7  push    rbx
0x1800ac4b8  push    rbp
0x1800ac4b9  push    rsi
0x1800ac4ba  push    rdi
0x1800ac4bb  push    r12
0x1800ac4bd  push    r13
0x1800ac4bf  push    r14
0x1800ac4c1  push    r15
0x1800ac4c3  sub     rsp, 0A8h
0x1800ac4ca  movaps  xmmword ptr [rax-58h], xmm6
0x1800ac4ce  lea     r15, aKerbupdatecred_1; "KerbUpdateCredentials"
0x1800ac4d5  movaps  xmmword ptr [rax-68h], xmm7
0x1800ac4d9  lea     r9, aKerbupdatecred; "KerbUpdateCredentials old logon session"...
0x1800ac4e0  movaps  xmmword ptr [rax-78h], xmm8
0x1800ac4e5  xor     r12d, r12d
0x1800ac4e8  mov     rsi, rcx
0x1800ac4eb  movaps  [rsp+0E8h+var_88], xmm9
0x1800ac4f1  lea     rcx, [rdx+78h]
0x1800ac4f5  mov     [rsp+0E8h+arg_18], r12
0x1800ac4fd  mov     [rsp+0E8h+var_A0], rcx
0x1800ac502  lea     rax, [rcx+10h]
0x1800ac506  mov     [rsp+0E8h+var_A8], rax
0x1800ac50b  lea     ebx, [r12+0Ah]
0x1800ac510  mov     eax, [rdx+40h]
0x1800ac513  mov     rbp, rdx
0x1800ac516  mov     [rsp+0E8h+var_B0], eax
0x1800ac51a  mov     r8d, 2102h
0x1800ac520  mov     eax, [rdx+44h]
0x1800ac523  mov     ecx, ebx
0x1800ac525  mov     [rsp+0E8h+var_B8], eax
0x1800ac529  mov     rdx, r15
0x1800ac52c  mov     eax, [rsi+40h]
0x1800ac52f  xorps   xmm6, xmm6
0x1800ac532  mov     dword ptr [rsp+0E8h+var_C0], eax
0x1800ac536  xorps   xmm8, xmm8
0x1800ac53a  mov     eax, [rsi+44h]
0x1800ac53d  xorps   xmm7, xmm7
0x1800ac540  mov     dword ptr [rsp+0E8h+var_C8], eax
0x1800ac544  xorps   xmm9, xmm9
0x1800ac548  mov     r13d, r12d
0x1800ac54b  mov     [rsp+0E8h+var_98], r12
0x1800ac550  mov     [rsp+0E8h+arg_0], r12b
0x1800ac558  mov     [rsp+0E8h+arg_10], r12d
0x1800ac560  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800ac565  mov     rdx, [rbp+108h]; struct _KERB_STORED_CREDENTIAL *
0x1800ac56c  mov     rcx, [rsi+108h]; struct _KERB_STORED_CREDENTIAL *
0x1800ac573  call    ?KerbCompareKeys@@YA_NPEAU_KERB_STORED_CREDENTIAL@@0@Z; KerbCompareKeys(_KERB_STORED_CREDENTIAL *,_KERB_STORED_CREDENTIAL *)
0x1800ac578  movzx   edx, al
0x1800ac57b  lea     r9, aKerbupdatecred_0; "KerbUpdateCredentials: OldLogonSession "...
0x1800ac582  mov     dword ptr [rsp+0E8h+var_A8], edx
0x1800ac586  mov     r8d, 2107h
0x1800ac58c  mov     edx, [rbp+40h]
0x1800ac58f  mov     ecx, ebx
0x1800ac591  mov     [rsp+0E8h+var_B0], edx
0x1800ac595  mov     edx, [rbp+44h]
0x1800ac598  mov     [rsp+0E8h+var_B8], edx
0x1800ac59c  mov     edx, [rsi+40h]
0x1800ac59f  mov     dword ptr [rsp+0E8h+var_C0], edx
0x1800ac5a3  mov     edx, [rsi+44h]
0x1800ac5a6  mov     dword ptr [rsp+0E8h+var_C8], edx
0x1800ac5aa  mov     rdx, r15
0x1800ac5ad  mov     [rsp+0E8h+arg_8], al
0x1800ac5b4  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800ac5b9  lea     ebx, [r12+1]
0x1800ac5be  xor     edx, edx; struct _UNICODE_STRING *
0x1800ac5c0  mov     r8d, ebx; unsigned int
0x1800ac5c3  lea     rcx, [rbp+168h]; struct _KERB_TICKET_CACHE *
0x1800ac5ca  mov     r14b, r12b
0x1800ac5cd  mov     dil, r12b
0x1800ac5d0  call    ?KerbLocateTicketCacheEntryByRealm@@YAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KERB_TICKET_CACHE@@PEAU_UNICODE_STRING@@K@Z; KerbLocateTicketCacheEntryByRealm(_KERB_TICKET_CACHE *,_UNICODE_STRING *,ulong)
0x1800ac5d5  test    rax, rax
0x1800ac5d8  jz      short loc_1800AC5E5
0x1800ac5da  mov     rcx, rax; struct _KERB_TICKET_CACHE_ENTRY *
0x1800ac5dd  mov     r14b, bl
0x1800ac5e0  call    ?KerbDereferenceTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbDereferenceTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x1800ac5e5  mov     ecx, [rbp+388h]
0x1800ac5eb  not     ecx
0x1800ac5ed  and     ecx, ebx
0x1800ac5ef  cmp     cl, r14b
0x1800ac5f2  jz      short loc_1800AC5F9
0x1800ac5f4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800ac5f9  lea     rcx, [rsi+168h]; struct _KERB_TICKET_CACHE *
0x1800ac600  mov     r8d, ebx; unsigned int
0x1800ac603  xor     edx, edx; struct _UNICODE_STRING *
0x1800ac605  call    ?KerbLocateTicketCacheEntryByRealm@@YAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KERB_TICKET_CACHE@@PEAU_UNICODE_STRING@@K@Z; KerbLocateTicketCacheEntryByRealm(_KERB_TICKET_CACHE *,_UNICODE_STRING *,ulong)
0x1800ac60a  test    rax, rax
0x1800ac60d  jz      short loc_1800AC61A
0x1800ac60f  mov     rcx, rax; struct _KERB_TICKET_CACHE_ENTRY *
0x1800ac612  mov     dil, bl
0x1800ac615  call    ?KerbDereferenceTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbDereferenceTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x1800ac61a  mov     edx, [rsi+388h]
0x1800ac620  mov     ecx, edx
0x1800ac622  not     ecx
0x1800ac624  and     ecx, ebx
0x1800ac626  cmp     cl, dil
0x1800ac629  jz      short loc_1800AC636
0x1800ac62b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800ac630  mov     edx, [rsi+388h]
0x1800ac636  test    r14b, r14b
0x1800ac639  jnz     short loc_1800AC662
0x1800ac63b  test    dil, dil
0x1800ac63e  jnz     short loc_1800AC662
0x1800ac640  lea     r9, aFailedToFindPr; "Failed to find primary TGT on *OLD* log"...
0x1800ac647  mov     r8d, 2143h
0x1800ac64d  mov     rdx, r15
0x1800ac650  mov     ecx, 2
0x1800ac655  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800ac65a  or      [rsi+388h], ebx
0x1800ac660  jmp     short loc_1800AC68A
0x1800ac662  and     edx, 0FFFFFFFEh
0x1800ac665  mov     [rsi+388h], edx
0x1800ac66b  test    r14b, r14b
0x1800ac66e  jnz     short loc_1800AC690
0x1800ac670  lea     r9, aNoNewPrimaryTg; "no new primary TGT in the unlock logon "...
0x1800ac677  mov     r8d, 213Ah
0x1800ac67d  mov     rdx, r15
0x1800ac680  mov     ecx, 2
0x1800ac685  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800ac68a  mov     edx, [rsi+388h]
0x1800ac690  test    byte ptr [rbp+388h], 10h
0x1800ac697  jz      short loc_1800AC69E
0x1800ac699  or      edx, 10h
0x1800ac69c  jmp     short loc_1800AC6A1
0x1800ac69e  and     edx, 0FFFFFFEFh
0x1800ac6a1  mov     [rsi+388h], edx
0x1800ac6a7  test    byte ptr [rbp+388h], 20h
0x1800ac6ae  jz      short loc_1800AC6B5
0x1800ac6b0  or      edx, 20h
0x1800ac6b3  jmp     short loc_1800AC6B8
0x1800ac6b5  and     edx, 0FFFFFFDFh
0x1800ac6b8  mov     [rsi+388h], edx
0x1800ac6be  test    byte ptr [rbp+388h], 80h
0x1800ac6c5  jz      short loc_1800AC6CD
0x1800ac6c7  bts     edx, 7
0x1800ac6cb  jmp     short loc_1800AC6D1
0x1800ac6cd  btr     edx, 7
0x1800ac6d1  mov     eax, 1000000h
0x1800ac6d6  mov     [rsi+388h], edx
0x1800ac6dc  test    [rbp+388h], eax
0x1800ac6e2  jz      short loc_1800AC6E8
0x1800ac6e4  or      edx, eax
0x1800ac6e6  jmp     short loc_1800AC6EC
0x1800ac6e8  btr     edx, 18h
0x1800ac6ec  mov     [rsi+388h], edx
0x1800ac6f2  test    [rbp+388h], bl
0x1800ac6f8  jz      short loc_1800AC704
0x1800ac6fa  btr     edx, 16h
0x1800ac6fe  mov     [rsi+388h], edx
0x1800ac704  mov     dword ptr [rsp+0E8h+var_C0], edx
0x1800ac708  lea     r9, aUpdatedFlagsIn; "Updated flags in OldLogonSession %p to "...
0x1800ac70f  mov     rax, rsi
0x1800ac712  lea     rdx, aKerbupdatecred_1; "KerbUpdateCredentials"
0x1800ac719  shr     rax, 10h
0x1800ac71d  mov     r8d, 2150h
0x1800ac723  movzx   r15d, ax
0x1800ac727  mov     ecx, 3
0x1800ac72c  mov     [rsp+0E8h+var_C8], r15
0x1800ac731  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800ac736  cmp     dword ptr [rsi+40h], 3E7h
0x1800ac73d  jnz     loc_1800AC88D
0x1800ac743  cmp     [rsi+44h], r12d
0x1800ac747  jz      loc_1800AC89F
0x1800ac74d  lea     rdi, [rbp+190h]
0x1800ac754  xor     ecx, ecx
0x1800ac756  cmp     [rdi], rcx
0x1800ac759  jnz     loc_1800AC9EC
0x1800ac75f  cmp     [rsi+190h], rcx
0x1800ac766  jnz     loc_1800AC806
0x1800ac76c  cmp     [rsp+0E8h+arg_8], cl
0x1800ac773  jnz     loc_1800AC806
0x1800ac779  mov     r13, [rbp+108h]
0x1800ac780  lea     r9, aUpdatingOldlog; "Updating OldLogonSession %p with new pa"...
0x1800ac787  movups  xmm6, xmmword ptr [rbp+98h]
0x1800ac78e  mov     [rbp+108h], rcx
0x1800ac795  mov     r8d, 219Dh
0x1800ac79b  movups  xmm8, xmmword ptr [rbp+0A8h]
0x1800ac7a3  xorps   xmm0, xmm0
0x1800ac7a6  movups  xmmword ptr [rbp+98h], xmm0
0x1800ac7ad  movups  xmmword ptr [rbp+0A8h], xmm0
0x1800ac7b4  mov     rax, [rsi+108h]
0x1800ac7bb  movups  xmm7, xmmword ptr [rsi+98h]
0x1800ac7c2  mov     [rsi+108h], rcx
0x1800ac7c9  movups  xmm9, xmmword ptr [rsi+0A8h]
0x1800ac7d1  movups  xmmword ptr [rsi+98h], xmm0
0x1800ac7d8  movups  xmmword ptr [rsi+0A8h], xmm0
0x1800ac7df  lea     rdx, aKerbupdatecred_1; "KerbUpdateCredentials"
0x1800ac7e6  mov     [rsp+0E8h+var_C8], r15
0x1800ac7eb  mov     ecx, 3
0x1800ac7f0  mov     [rsp+0E8h+arg_10], ebx
0x1800ac7f7  mov     [rsp+0E8h+arg_18], rax
0x1800ac7ff  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800ac804  xor     ecx, ecx
0x1800ac806  cmp     [rdi], rcx
0x1800ac809  jnz     loc_1800AC9EC
0x1800ac80f  cmp     [rsi+190h], rcx
0x1800ac816  jnz     loc_1800AC9EC
0x1800ac81c  test    [rsi+388h], bl
0x1800ac822  jnz     loc_1800AC9EC
0x1800ac828  test    [rbp+388h], bl
0x1800ac82e  jz      loc_1800AC9EC
0x1800ac834  cmp     [rsp+0E8h+arg_0], cl
0x1800ac83b  jnz     loc_1800AC9EC
0x1800ac841  lea     rcx, [rsi+168h]; struct _KERB_TICKET_CACHE *
0x1800ac848  call    ?KerbPurgeTicketCache@@YAXPEAU_KERB_TICKET_CACHE@@@Z; KerbPurgeTicketCache(_KERB_TICKET_CACHE *)
0x1800ac84d  lea     rcx, [rsi+140h]; struct _KERB_TICKET_CACHE *
0x1800ac854  call    ?KerbPurgeTicketCache@@YAXPEAU_KERB_TICKET_CACHE@@@Z; KerbPurgeTicketCache(_KERB_TICKET_CACHE *)
0x1800ac859  lea     rcx, [rsi+118h]; struct _KERB_TICKET_CACHE *
0x1800ac860  call    ?KerbPurgeTicketCache@@YAXPEAU_KERB_TICKET_CACHE@@@Z; KerbPurgeTicketCache(_KERB_TICKET_CACHE *)
0x1800ac865  lea     r9, aClearingTicket; "Clearing ticket cache in OldLogonSessio"...
0x1800ac86c  mov     [rsp+0E8h+var_C8], r15
0x1800ac871  mov     r8d, 21B4h
0x1800ac877  lea     rdx, aKerbupdatecred_1; "KerbUpdateCredentials"
0x1800ac87e  mov     ecx, 3
0x1800ac883  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800ac888  jmp     loc_1800ACA5F
0x1800ac88d  cmp     dword ptr [rsi+40h], 3E4h
0x1800ac894  jnz     loc_1800AC74D
0x1800ac89a  jmp     loc_1800AC743
0x1800ac89f  lea     rdi, [rbp+190h]
0x1800ac8a6  xor     ecx, ecx
0x1800ac8a8  mov     r12d, ebx
0x1800ac8ab  cmp     [rdi], rcx
0x1800ac8ae  jz      short loc_1800AC91B
0x1800ac8b0  mov     r13, [rsi+108h]
0x1800ac8b7  lea     r9, aUpdatingOldlog_0; "Updating OldLogonSession %p due to the "...
0x1800ac8be  movups  xmm6, xmmword ptr [rsi+98h]
0x1800ac8c5  mov     [rsi+108h], rcx
0x1800ac8cc  mov     r8d, 216Ah
0x1800ac8d2  movups  xmm8, xmmword ptr [rsi+0A8h]
0x1800ac8da  xorps   xmm0, xmm0
0x1800ac8dd  movups  xmmword ptr [rsi+98h], xmm0
0x1800ac8e4  movups  xmmword ptr [rsi+0A8h], xmm0
0x1800ac8eb  mov     rax, [rsi+110h]
0x1800ac8f2  movups  xmm7, xmmword ptr [rsi+0B8h]
0x1800ac8f9  mov     [rsi+110h], rcx
0x1800ac900  movups  xmm9, xmmword ptr [rsi+0C8h]
0x1800ac908  movups  xmmword ptr [rsi+0B8h], xmm0
0x1800ac90f  movups  xmmword ptr [rsi+0C8h], xmm0
0x1800ac916  jmp     loc_1800AC7DF
0x1800ac91b  mov     rax, [rsi+190h]
0x1800ac922  mov     [rsp+0E8h+var_98], rax
0x1800ac927  mov     [rsi+190h], rcx
0x1800ac92e  mov     [rsp+0E8h+arg_0], bl
0x1800ac935  cmp     [rsp+0E8h+arg_8], cl
0x1800ac93c  jnz     loc_1800AC9D4
0x1800ac942  mov     r13, [rbp+108h]
0x1800ac949  lea     r9, aUpdatingOldlog_1; "Updating OldLogonSession %p due to key "...
0x1800ac950  movups  xmm6, xmmword ptr [rbp+98h]
0x1800ac957  mov     [rbp+108h], rcx
0x1800ac95e  mov     r8d, 2180h
0x1800ac964  movups  xmm8, xmmword ptr [rbp+0A8h]
0x1800ac96c  mov     [rsp+0E8h+arg_10], ebx
0x1800ac973  lea     rdx, aKerbupdatecred_1; "KerbUpdateCredentials"
0x1800ac97a  xorps   xmm0, xmm0
0x1800ac97d  mov     [rsp+0E8h+var_C8], r15
0x1800ac982  movups  xmmword ptr [rbp+98h], xmm0
0x1800ac989  movups  xmmword ptr [rbp+0A8h], xmm0
0x1800ac990  mov     rax, [rsi+108h]
0x1800ac997  movups  xmm7, xmmword ptr [rsi+98h]
0x1800ac99e  mov     [rsi+108h], rcx
0x1800ac9a5  mov     ecx, 3
0x1800ac9aa  movups  xmm9, xmmword ptr [rsi+0A8h]
0x1800ac9b2  mov     [rsp+0E8h+arg_18], rax
0x1800ac9ba  movups  xmmword ptr [rsi+98h], xmm0
0x1800ac9c1  movups  xmmword ptr [rsi+0A8h], xmm0
0x1800ac9c8  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800ac9cd  mov     rax, [rsp+0E8h+var_98]
0x1800ac9d2  xor     ecx, ecx
0x1800ac9d4  test    rax, rax
0x1800ac9d7  jz      loc_1800AC804
0x1800ac9dd  or      dword ptr [rsi+388h], 10h
0x1800ac9e4  mov     r14b, cl
0x1800ac9e7  jmp     loc_1800AC804
0x1800ac9ec  xor     edx, edx; unsigned __int8
0x1800ac9ee  lea     rcx, [rsi+78h]; this
0x1800ac9f2  call    ?KerbFreePrimaryCredentials@@YAXPEAU_KERB_PRIMARY_CREDENTIAL@@E@Z; KerbFreePrimaryCredentials(_KERB_PRIMARY_CREDENTIAL *,uchar)
0x1800ac9f7  lea     rcx, [rbp+140h]; struct _KERB_TICKET_CACHE *
0x1800ac9fe  call    ?KerbPurgeTicketCache@@YAXPEAU_KERB_TICKET_CACHE@@@Z; KerbPurgeTicketCache(_KERB_TICKET_CACHE *)
0x1800aca03  lea     rcx, [rbp+118h]; struct _KERB_TICKET_CACHE *
0x1800aca0a  call    ?KerbPurgeTicketCache@@YAXPEAU_KERB_TICKET_CACHE@@@Z; KerbPurgeTicketCache(_KERB_TICKET_CACHE *)
0x1800aca0f  lea     rcx, [rbp+260h]; struct _KERB_S4U2PROXY_CACHE *
0x1800aca16  mov     r8b, bl; unsigned __int8
0x1800aca19  mov     dl, bl; unsigned __int8
0x1800aca1b  call    ?KerbAgeS4U2ProxyCache@@YAXPEAU_KERB_S4U2PROXY_CACHE@@EE@Z; KerbAgeS4U2ProxyCache(_KERB_S4U2PROXY_CACHE *,uchar,uchar)
0x1800aca20  lea     rdx, [rbp+78h]; struct _KERB_PRIMARY_CREDENTIAL *
0x1800aca24  lea     rcx, [rsi+78h]; this
0x1800aca28  call    ?KerbTransferPrimaryCredentials@@YAXPEAU_KERB_PRIMARY_CREDENTIAL@@0@Z; KerbTransferPrimaryCredentials(_KERB_PRIMARY_CREDENTIAL *,_KERB_PRIMARY_CREDENTIAL *)
0x1800aca2d  mov     rax, rbp
0x1800aca30  mov     [rsp+0E8h+var_C0], r15
0x1800aca35  shr     rax, 10h
0x1800aca39  lea     r9, aTransferredPri; "Transferred primary credentials from Lo"...
0x1800aca40  movzx   ecx, ax
0x1800aca43  lea     rdx, aKerbupdatecred_1; "KerbUpdateCredentials"
0x1800aca4a  mov     [rsp+0E8h+var_C8], rcx
0x1800aca4f  mov     r8d, 21C5h
0x1800aca55  mov     ecx, 3
0x1800aca5a  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800aca5f  cmp     [rsp+0E8h+arg_10], 0
0x1800aca67  jz      loc_1800ACB50
  ... truncated ...
```
