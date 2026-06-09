# LsaDbpLookupNamesBuildWorkList(ulong,ulong,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_SIDS_EX2 *,_LSAP_LOOKUP_LEVEL,ulong *,ulong *,_LSAP_DB_LOOKUP_WORK_LIST * *)

- ea: `0x18001b2d4`
- end: `0x18001b8d5`
- name: `?LsaDbpLookupNamesBuildWorkList@@YAJKKPEAU_LSAPR_UNICODE_STRING@@00PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SIDS_EX2@@W4_LSAP_LOOKUP_LEVEL@@PEAK4PEAPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z`
- size: `1537`
- prototype: `__int64(int, unsigned int, __int64, __int64, __int64, __int64, __int64, ...)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001d228`

## callees

- `0x18000cca4`
- `0x18000fde0`
- `0x18001a658`
- `0x18001a6d8`
- `0x18001b020`
- `0x18001b0dc`
- `0x18001b214`
- `0x18001b2d4`
- `0x18001c088`
- `0x180032de4`
- `0x180033144`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b85d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b86a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b85d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b86a`
- `RPCRT4!RpcStringBindingParseW` at `0x18001b38e`
- `RPCRT4!RpcStringBindingParseW` at `0x18001b38e`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18001b36b`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18001b36b`
- `RPCRT4!RpcBindingServerFromClient` at `0x18001b357`
- `RPCRT4!RpcBindingServerFromClient` at `0x18001b357`
- `RPCRT4!RpcBindingFree` at `0x18001b3a4`
- `RPCRT4!RpcBindingFree` at `0x18001b3a4`
- `RPCRT4!RpcStringFreeW` at `0x18001b399`
- `RPCRT4!RpcStringFreeW` at `0x18001b87a`
- `RPCRT4!RpcStringFreeW` at `0x18001b399`
- `RPCRT4!RpcStringFreeW` at `0x18001b87a`
- `LSASRV!LsapDbLookupListReferencedDomains` at `0x18001b7e1`
- `LSASRV!LsapDbLookupListReferencedDomains` at `0x18001b7e1`
- `LSASRV!LsapTraceEventWithData` at `0x18001b584`
- `LSASRV!LsapTraceEventWithData` at `0x18001b584`
- `LSASRV!LsaLookupPerfCounterIncrementCount` at `0x18001b540`
- `LSASRV!LsaLookupPerfCounterIncrementCount` at `0x18001b540`
- `LSASRV!LsapGetLookupRestrictIsolatedNameLevel` at `0x18001b507`
- `LSASRV!LsapGetLookupRestrictIsolatedNameLevel` at `0x18001b507`
- `LSASRV!LsapDbLookupAddListReferencedDomains` at `0x18001b678`
- `LSASRV!LsapDbLookupAddListReferencedDomains` at `0x18001b678`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x18001b781`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x18001b781`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18001b84e`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18001b84e`
- `LSASRV!LsapCompareDomainNames` at `0x18001b5e2`
- `LSASRV!LsapCompareDomainNames` at `0x18001b5e2`
- `ntdll!RtlInitUnicodeString` at `0x18001b570`
- `ntdll!RtlInitUnicodeString` at `0x18001b570`

## pseudocode

```c
__int64 LsaDbpLookupNamesBuildWorkList(
        int a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        ...)
{
  struct _LSAP_DB_LOOKUP_WORK_ITEM *v8; // rsi
  int WorkList; // eax
  struct _UNICODE_STRING *v11; // rcx
  HLOCAL v12; // rdi
  int LockTrustedDomainList; // ebx
  __int64 v14; // r12
  __int64 v15; // rax
  __int64 v16; // r8
  unsigned int v17; // r15d
  __int64 v18; // rax
  unsigned int v19; // edx
  __int64 v20; // rax
  RPC_WSTR *v21; // r13
  __int64 v22; // r12
  RPC_WSTR v23; // r14
  USHORT Length; // r8
  PWSTR Buffer; // rax
  USHORT v26; // r8
  unsigned int v27; // r8d
  int v28; // eax
  int HasDomainTrust; // eax
  unsigned int v30; // r8d
  struct _LSAP_DB_LOOKUP_WORK_ITEM **v31; // rax
  struct _LSAP_DB_LOOKUP_WORK_ITEM *v32; // r14
  int v33; // eax
  const UNICODE_STRING *v34; // rbx
  unsigned int v35; // r8d
  struct _LSAP_DB_LOOKUP_WORK_ITEM *v36; // r14
  struct _LSAP_DB_LOOKUP_WORK_ITEM *v37; // rcx
  int v39[2]; // [rsp+38h] [rbp-A9h] BYREF
  RPC_WSTR StringBinding; // [rsp+40h] [rbp-A1h] BYREF
  RPC_WSTR NetworkAddr; // [rsp+48h] [rbp-99h] BYREF
  RPC_BINDING_HANDLE ServerBinding[3]; // [rsp+50h] [rbp-91h] BYREF
  PCWSTR SourceString; // [rsp+68h] [rbp-79h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-71h] BYREF
  struct _LSAP_DB_LOOKUP_WORK_ITEM *v45; // [rsp+78h] [rbp-69h] BYREF
  PCUNICODE_STRING v46; // [rsp+80h] [rbp-61h] BYREF
  struct _UNICODE_STRING v47; // [rsp+88h] [rbp-59h] BYREF
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v48; // [rsp+98h] [rbp-49h] BYREF
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v49; // [rsp+A0h] [rbp-41h] BYREF
  UNICODE_STRING v50; // [rsp+A8h] [rbp-39h] BYREF
  __int64 v51; // [rsp+B8h] [rbp-29h]
  __int128 v52; // [rsp+C0h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+D0h] [rbp-11h] BYREF
  __int64 v57; // [rsp+160h] [rbp+7Fh] BYREF
  va_list va; // [rsp+160h] [rbp+7Fh]
  struct _UNICODE_STRING *v59; // [rsp+168h] [rbp+87h]
  __int64 v60; // [rsp+170h] [rbp+8Fh]
  _QWORD *v61; // [rsp+178h] [rbp+97h]
  va_list va1; // [rsp+180h] [rbp+9Fh] BYREF

  va_start(va1, a7);
  va_start(va, a7);
  v57 = va_arg(va1, _QWORD);
  v59 = va_arg(va1, struct _UNICODE_STRING *);
  v60 = va_arg(va1, _QWORD);
  v61 = va_arg(va1, _QWORD *);
  hMem = 0;
  v46 = 0;
  v39[0] = 0;
  v45 = 0;
  LOBYTE(v57) = 0;
  v8 = 0;
  v49 = 0;
  v47 = 0;
  v48 = 0;
  v51 = 0;
  v50 = 0;
  SourceString = 0;
  memset(ServerBinding, 0, sizeof(ServerBinding));
  StringBinding = 0;
  NetworkAddr = 0;
  if ( !RpcBindingServerFromClient(0, ServerBinding) )
  {
    if ( !RpcBindingToStringBindingW(ServerBinding[0], &StringBinding) )
    {
      RpcStringBindingParseW(StringBinding, 0, 0, &NetworkAddr, 0, 0);
      RpcStringFreeW(&StringBinding);
    }
    RpcBindingFree(ServerBinding);
  }
  SourceString = NetworkAddr;
  WorkList = LsaDbpLookupCreateWorkList((struct _LSAP_DB_LOOKUP_WORK_LIST **)&hMem);
  v12 = hMem;
  LockTrustedDomainList = WorkList;
  if ( WorkList < 0 )
    goto LABEL_58;
  v14 = a6;
  v11 = v59;
  v15 = v60;
  v16 = a7;
  *((_DWORD *)hMem + 8) = 0;
  *((_DWORD *)v12 + 9) = 1;
  *((_DWORD *)v12 + 10) = 2;
  *((_DWORD *)v12 + 16) = a2;
  v17 = 0;
  *((_DWORD *)v12 + 17) = 3;
  *((_QWORD *)v12 + 9) = a6;
  *((_QWORD *)v12 + 10) = v11;
  *((_QWORD *)v12 + 11) = v15;
  *((_QWORD *)v12 + 14) = a3;
  *((_QWORD *)v12 + 15) = a7;
  LODWORD(NetworkAddr) = 0;
  if ( !a2 )
    goto LABEL_42;
  v18 = 0;
  v19 = 0;
  do
  {
    v11 = (struct _UNICODE_STRING *)(3 * v18);
    if ( *(_DWORD *)(*(_QWORD *)(v16 + 8) + 24 * v18 + 16) != -1 )
      goto LABEL_40;
    v20 = a4;
    v21 = (RPC_WSTR *)*((_QWORD *)v12 + 2);
    v22 = 16LL * v19;
    v23 = *v21;
    v11 = (struct _UNICODE_STRING *)(v22 + a5);
    StringBinding = 0;
    LODWORD(ServerBinding[0]) = 0;
    if ( *(_WORD *)(v22 + a4) )
      goto LABEL_13;
    if ( !(unsigned int)LsaDbpLookupNameContainsDelimiter(v11, 0x40u, (unsigned int *)ServerBinding) )
    {
      v20 = a4;
LABEL_13:
      *(struct _UNICODE_STRING *)&ServerBinding[1] = *v11;
      v47 = *(struct _UNICODE_STRING *)(v22 + v20);
      v26 = _mm_cvtsi128_si32((__m128i)v47);
      goto LABEL_14;
    }
    Length = v11->Length;
    ServerBinding[2] = v11->Buffer;
    LOWORD(ServerBinding[1]) = 2 * LOWORD(ServerBinding[0]);
    WORD1(ServerBinding[1]) = 2 * LOWORD(ServerBinding[0]);
    Buffer = v11->Buffer;
    v26 = 2 * ((Length >> 1) - LOWORD(ServerBinding[0])) - 2;
    v47.Length = v26;
    v47.MaximumLength = v26;
    v11 = (struct _UNICODE_STRING *)&Buffer[LODWORD(ServerBinding[0]) + 1];
    v47.Buffer = &v11->Length;
LABEL_14:
    if ( v26 )
    {
      while ( v23 != (RPC_WSTR)v21 )
      {
        if ( (unsigned __int8)LsapCompareDomainNames(v23 + 12, &v47, 0) )
        {
          if ( v23 )
          {
            v14 = a6;
            goto LABEL_34;
          }
          break;
        }
        v23 = *(RPC_WSTR *)v23;
      }
      HasDomainTrust = LsaDbpDomainHasDomainTrust(1u, &v47, 0, (unsigned __int8 *)va, &v48);
      LockTrustedDomainList = HasDomainTrust;
      if ( HasDomainTrust < 0 )
      {
        if ( HasDomainTrust != -1073741601 )
          goto LABEL_58;
        LockTrustedDomainList = 0;
        goto LABEL_38;
      }
      v14 = a6;
      v51 = 0;
      v50 = 0;
      v50 = (UNICODE_STRING)*((_OWORD *)v48 + 2);
      v51 = *((_QWORD *)v48 + 6);
      v46 = &v50;
      LockTrustedDomainList = LsapDbLookupAddListReferencedDomains(a6, &v50, v39);
      if ( LockTrustedDomainList < 0 )
        goto LABEL_58;
      LockTrustedDomainList = LsaDbpLookupCreateWorkItem(
                                &v50,
                                v39[0],
                                v30,
                                (struct _LSAP_DB_LOOKUP_WORK_ITEM **)&StringBinding);
      if ( LockTrustedDomainList < 0 )
        goto LABEL_58;
      v23 = StringBinding;
      LockTrustedDomainList = LsaDbpAddWorkItemToWorkList(
                                (struct _LSAP_DB_LOOKUP_WORK_LIST *)v12,
                                (struct _LSAP_DB_LOOKUP_WORK_ITEM *)StringBinding);
      if ( LockTrustedDomainList < 0 )
        goto LABEL_58;
LABEL_34:
      LockTrustedDomainList = LsaDbpLookupAddIndicesToWorkItem(
                                (struct _LSAP_DB_LOOKUP_WORK_ITEM *)v23,
                                1u,
                                (unsigned int *)&NetworkAddr);
      if ( LockTrustedDomainList < 0 )
        goto LABEL_58;
      v17 = (unsigned int)NetworkAddr;
      v11 = *(struct _UNICODE_STRING **)(*((_QWORD *)v12 + 15) + 8LL);
      *((_DWORD *)&v11[1].Length + 6 * (unsigned int)NetworkAddr) = *((_DWORD *)v23 + 12);
    }
    else
    {
      if ( a1 >= 0 )
      {
        if ( (unsigned __int8)LsapGetLookupRestrictIsolatedNameLevel() )
        {
          v11 = (struct _UNICODE_STRING *)WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
            WPP_SF_Z(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              11,
              WPP_cdea14064fb83782dcfb43a713b43d51_Traceguids,
              &ServerBinding[1]);
        }
        else
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
            WPP_SF_Z(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              10,
              WPP_cdea14064fb83782dcfb43a713b43d51_Traceguids,
              &ServerBinding[1]);
          LsaLookupPerfCounterIncrementCount(4u);
          v52 = *(_OWORD *)&ServerBinding[1];
          RtlInitUnicodeString(&DestinationString, SourceString);
          LsapTraceEventWithData(0, 20, 2, &v52);
          if ( !v8 )
          {
            v28 = LsaDbpLookupCreateWorkItem(0, v39[0], v27, &v45);
            v8 = v45;
            LockTrustedDomainList = v28;
            if ( v28 < 0 )
              goto LABEL_58;
          }
          *((_DWORD *)v8 + 5) = 1;
          LockTrustedDomainList = LsaDbpLookupAddIndicesToWorkItem(v8, 1u, (unsigned int *)&NetworkAddr);
          if ( LockTrustedDomainList < 0 )
            goto LABEL_58;
          v17 = (unsigned int)NetworkAddr;
        }
      }
LABEL_38:
      v14 = a6;
    }
    v16 = a7;
LABEL_40:
    v19 = ++v17;
    LODWORD(NetworkAddr) = v17;
    v18 = v17;
  }
  while ( v17 < a2 );
  if ( LockTrustedDomainList < 0 )
    goto LABEL_58;
LABEL_42:
  if ( v8 )
  {
    v31 = (struct _LSAP_DB_LOOKUP_WORK_ITEM **)*((_QWORD *)v12 + 2);
    v32 = *v31;
    if ( *v31 == (struct _LSAP_DB_LOOKUP_WORK_ITEM *)v31 )
      goto LABEL_46;
    while ( 1 )
    {
      LockTrustedDomainList = LsaDbpLookupAddIndicesToWorkItem(v32, *((_DWORD *)v8 + 13), *((unsigned int **)v8 + 8));
      if ( LockTrustedDomainList < 0 )
        break;
      v32 = *(struct _LSAP_DB_LOOKUP_WORK_ITEM **)v32;
      if ( v32 == *((struct _LSAP_DB_LOOKUP_WORK_ITEM **)v12 + 2) )
      {
        while ( 1 )
        {
LABEL_46:
          if ( !(_BYTE)v57 )
          {
            LockTrustedDomainList = LsapDbExpAcquireReadLockTrustedDomainList(v11);
            if ( LockTrustedDomainList < 0 )
              goto LABEL_58;
            LOBYTE(v57) = 1;
          }
          StringBinding = 0;
          v33 = LsaDbpTraverseTrustedDomainList(&v49, (struct _LSAPR_TRUST_INFORMATION **)&v46);
          LockTrustedDomainList = v33;
          if ( v33 < 0 )
            break;
          v11 = (struct _UNICODE_STRING *)v49;
          if ( (unsigned int)(*((_DWORD *)v49 + 15) - 1) <= 1 )
          {
            if ( *((_QWORD *)v49 + 6) )
            {
              if ( (*((_BYTE *)v49 + 56) & 2) != 0 && (*((_BYTE *)v49 + 64) & 8) == 0 )
              {
                v34 = v46;
                if ( !(unsigned __int8)LsapDbLookupListReferencedDomains(v14, *(_QWORD *)&v46[1].Length, v39) )
                {
                  LockTrustedDomainList = LsaDbpLookupCreateWorkItem(
                                            v34,
                                            -1,
                                            v35,
                                            (struct _LSAP_DB_LOOKUP_WORK_ITEM **)&StringBinding);
                  if ( LockTrustedDomainList < 0 )
                    goto LABEL_58;
                  v36 = (struct _LSAP_DB_LOOKUP_WORK_ITEM *)StringBinding;
                  v37 = (struct _LSAP_DB_LOOKUP_WORK_ITEM *)StringBinding;
                  *((_DWORD *)StringBinding + 5) = 1;
                  LockTrustedDomainList = LsaDbpLookupAddIndicesToWorkItem(
                                            v37,
                                            *((_DWORD *)v8 + 13),
                                            *((unsigned int **)v8 + 8));
                  if ( LockTrustedDomainList < 0 )
                    goto LABEL_58;
                  LockTrustedDomainList = LsaDbpAddWorkItemToWorkList((struct _LSAP_DB_LOOKUP_WORK_LIST *)v12, v36);
                  if ( LockTrustedDomainList < 0 )
                    goto LABEL_58;
                }
              }
            }
          }
        }
        if ( v33 != -2147483622 )
          break;
        goto LABEL_68;
      }
    }
LABEL_58:
    if ( v12 )
    {
      LsaDbpLookupDeleteWorkList(v12);
      v12 = 0;
    }
  }
  else
  {
LABEL_68:
    LockTrustedDomainList = -1073741709;
    if ( !*((_DWORD *)v12 + 14) )
      goto LABEL_58;
    LockTrustedDomainList = 0;
    *((_DWORD *)v12 + 24) = *((_DWORD *)v12 + 14) - 1;
    LsaDbpUpdateMappedCountsWorkList((struct _LSAP_DB_LOOKUP_WORK_LIST *)v12);
  }
  if ( (_BYTE)v57 )
    LsapDbExpReleaseLockTrustedDomainList(v11);
  if ( v8 )
  {
    LocalFree(*((HLOCAL *)v8 + 8));
    *((_QWORD *)v8 + 8) = 0;
    LocalFree(v8);
  }
  if ( SourceString )
    RpcStringFreeW((RPC_WSTR *)&SourceString);
  *v61 = v12;
  return (unsigned int)LockTrustedDomainList;
}

```

## disassembly

```asm
0x18001b2d4  mov     rax, rsp
0x18001b2d7  mov     [rax+18h], rbx
0x18001b2db  mov     [rax+20h], r9
0x18001b2df  mov     [rax+10h], edx
0x18001b2e2  mov     [rax+8], ecx
0x18001b2e5  push    rbp
0x18001b2e6  push    rsi
0x18001b2e7  push    rdi
0x18001b2e8  push    r12
0x18001b2ea  push    r13
0x18001b2ec  push    r14
0x18001b2ee  push    r15
0x18001b2f0  lea     rbp, [rax-3Fh]
0x18001b2f4  sub     rsp, 0E0h
0x18001b2fb  xor     r13d, r13d
0x18001b2fe  xorps   xmm0, xmm0
0x18001b301  mov     r15d, edx
0x18001b304  mov     [rbp+37h+hMem], r13
0x18001b308  xorps   xmm1, xmm1
0x18001b30b  mov     [rbp+37h+var_98], r13
0x18001b30f  xor     eax, eax
0x18001b311  mov     [rsp+110h+var_E0], r13d
0x18001b316  lea     rdx, [rsp+110h+ServerBinding]; ServerBinding
0x18001b31b  mov     [rbp+37h+var_A0], r13
0x18001b31f  xor     ecx, ecx; ClientBinding
0x18001b321  mov     byte ptr [rbp+37h+arg_38], r13b
0x18001b325  mov     esi, r13d
0x18001b328  mov     [rbp+37h+var_78], r13
0x18001b32c  movups  xmmword ptr [rbp+37h+var_90.Length], xmm0
0x18001b330  mov     [rbp+37h+var_80], r13
0x18001b334  mov     r14, r8
0x18001b337  movups  xmmword ptr [rsp+110h+ServerBinding+8], xmm1
0x18001b33c  mov     [rbp+37h+var_60], rax
0x18001b340  movups  xmmword ptr [rbp+37h+var_70.Length], xmm0
0x18001b344  mov     [rbp+37h+SourceString], r13
0x18001b348  mov     qword ptr [rsp+110h+ServerBinding], r13
0x18001b34d  mov     [rsp+110h+StringBinding], r13
0x18001b352  mov     [rsp+110h+NetworkAddr], r13
0x18001b357  call    cs:__imp_RpcBindingServerFromClient
0x18001b35d  test    eax, eax
0x18001b35f  jnz     short loc_18001B3AA
0x18001b361  mov     rcx, qword ptr [rsp+110h+ServerBinding]; Binding
0x18001b366  lea     rdx, [rsp+110h+StringBinding]; StringBinding
0x18001b36b  call    cs:__imp_RpcBindingToStringBindingW
0x18001b371  test    eax, eax
0x18001b373  jnz     short loc_18001B39F
0x18001b375  mov     rcx, [rsp+110h+StringBinding]; StringBinding
0x18001b37a  lea     r9, [rsp+110h+NetworkAddr]; NetworkAddr
0x18001b37f  mov     [rsp+110h+NetworkOptions], r13; NetworkOptions
0x18001b384  xor     r8d, r8d; Protseq
0x18001b387  xor     edx, edx; ObjUuid
0x18001b389  mov     [rsp+110h+Endpoint], r13; Endpoint
0x18001b38e  call    cs:__imp_RpcStringBindingParseW
0x18001b394  lea     rcx, [rsp+110h+StringBinding]; String
0x18001b399  call    cs:__imp_RpcStringFreeW
0x18001b39f  lea     rcx, [rsp+110h+ServerBinding]; Binding
0x18001b3a4  call    cs:__imp_RpcBindingFree
0x18001b3aa  mov     rax, [rsp+110h+NetworkAddr]
0x18001b3af  lea     rcx, [rbp+37h+hMem]; struct _LSAP_DB_LOOKUP_WORK_LIST **
0x18001b3b3  mov     [rbp+37h+SourceString], rax
0x18001b3b7  call    ?LsaDbpLookupCreateWorkList@@YAJPEAPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z; LsaDbpLookupCreateWorkList(_LSAP_DB_LOOKUP_WORK_LIST * *)
0x18001b3bc  mov     rdi, [rbp+37h+hMem]
0x18001b3c0  mov     ebx, eax
0x18001b3c2  test    eax, eax
0x18001b3c4  js      loc_18001B838
0x18001b3ca  mov     r12, [rbp+37h+arg_28]
0x18001b3ce  mov     rcx, [rbp+37h+arg_40]
0x18001b3d5  mov     rax, [rbp+37h+arg_48]
0x18001b3dc  mov     r8, [rbp+37h+arg_30]
0x18001b3e0  mov     [rdi+20h], r13d
0x18001b3e4  mov     dword ptr [rdi+24h], 1
0x18001b3eb  mov     dword ptr [rdi+28h], 2
0x18001b3f2  mov     [rdi+40h], r15d
0x18001b3f6  mov     r15d, r13d
0x18001b3f9  mov     dword ptr [rdi+44h], 3
0x18001b400  mov     [rdi+48h], r12
0x18001b404  mov     [rdi+50h], rcx
0x18001b408  mov     [rdi+58h], rax
0x18001b40c  mov     [rdi+70h], r14
0x18001b410  mov     [rdi+78h], r8
0x18001b414  mov     dword ptr [rsp+110h+NetworkAddr], r13d
0x18001b419  cmp     [rbp+37h+arg_8], r13d
0x18001b41d  jbe     loc_18001B744
0x18001b423  mov     eax, r13d
0x18001b426  mov     edx, r13d
0x18001b429  lea     rcx, [rax+rax*2]
0x18001b42d  mov     rax, [r8+8]
0x18001b431  cmp     dword ptr [rax+rcx*8+10h], 0FFFFFFFFh
0x18001b436  jnz     loc_18001B724
0x18001b43c  mov     rax, [rbp+37h+arg_18]
0x18001b440  xor     r9d, r9d
0x18001b443  mov     r13, [rdi+10h]
0x18001b447  mov     rcx, [rbp+37h+arg_20]
0x18001b44b  mov     r12d, edx
0x18001b44e  shl     r12, 4
0x18001b452  mov     r14, [r13+0]
0x18001b456  add     rcx, r12; struct _UNICODE_STRING *
0x18001b459  mov     [rsp+110h+StringBinding], r9
0x18001b45e  mov     dword ptr [rsp+110h+ServerBinding], r9d
0x18001b463  cmp     [r12+rax], r9w
0x18001b468  jnz     short loc_18001B4D3
0x18001b46a  lea     edx, [r9+40h]; unsigned __int16
0x18001b46e  lea     r8, [rsp+110h+ServerBinding]; unsigned int *
0x18001b473  call    ?LsaDbpLookupNameContainsDelimiter@@YAHPEAU_UNICODE_STRING@@GPEAK@Z; LsaDbpLookupNameContainsDelimiter(_UNICODE_STRING *,ushort,ulong *)
0x18001b478  test    eax, eax
0x18001b47a  jz      short loc_18001B4CF
0x18001b47c  mov     rax, [rcx+8]
0x18001b480  mov     r12d, 2
0x18001b486  movzx   r8d, word ptr [rcx]
0x18001b48a  mov     edx, dword ptr [rsp+110h+ServerBinding]
0x18001b48e  mov     qword ptr [rsp+110h+ServerBinding+10h], rax
0x18001b493  movzx   eax, dx
0x18001b496  add     ax, ax
0x18001b499  shr     r8w, 1
0x18001b49d  sub     r8w, dx
0x18001b4a1  mov     word ptr [rsp+110h+ServerBinding+8], ax
0x18001b4a6  mov     word ptr [rsp+110h+ServerBinding+0Ah], ax
0x18001b4ab  add     r8w, r8w
0x18001b4af  mov     rax, [rcx+8]
0x18001b4b3  sub     r8w, r12w
0x18001b4b7  lea     rcx, [rdx+1]
0x18001b4bb  mov     [rbp+37h+var_90.Length], r8w
0x18001b4c0  mov     [rbp+37h+var_90.MaximumLength], r8w
0x18001b4c5  lea     rcx, [rax+rcx*2]
0x18001b4c9  mov     [rbp+37h+var_90.Buffer], rcx
0x18001b4cd  jmp     short loc_18001B4F0
0x18001b4cf  mov     rax, [rbp+37h+arg_18]
0x18001b4d3  movups  xmm0, xmmword ptr [rcx]
0x18001b4d6  movdqu  xmmword ptr [rsp+110h+ServerBinding+8], xmm0
0x18001b4dc  movups  xmm1, xmmword ptr [r12+rax]
0x18001b4e1  mov     r12d, 2
0x18001b4e7  movups  xmmword ptr [rbp+37h+var_90.Length], xmm1
0x18001b4eb  movd    r8d, xmm1
0x18001b4f0  test    r8w, r8w
0x18001b4f4  jnz     loc_18001B5EF
0x18001b4fa  xor     r13d, r13d
0x18001b4fd  cmp     [rbp+37h+arg_0], r13d
0x18001b501  jl      loc_18001B71C
0x18001b507  call    cs:__imp_LsapGetLookupRestrictIsolatedNameLevel
0x18001b50d  test    al, al
0x18001b50f  jnz     loc_18001B6F5
0x18001b515  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b51c  test    byte ptr [rcx+1Ch], 20h
0x18001b520  jz      short loc_18001B53B
0x18001b522  mov     rcx, [rcx+10h]
0x18001b526  lea     edx, [r13+0Ah]
0x18001b52a  lea     r9, [rsp+110h+ServerBinding+8]
0x18001b52f  lea     r8, WPP_cdea14064fb83782dcfb43a713b43d51_Traceguids
0x18001b536  call    WPP_SF_Z
0x18001b53b  mov     ecx, 4
0x18001b540  call    cs:__imp_?LsaLookupPerfCounterIncrementCount@@YAXK@Z; LsaLookupPerfCounterIncrementCount(ulong)
0x18001b546  movzx   eax, word ptr [rsp+110h+ServerBinding+8]
0x18001b54b  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x18001b54f  mov     rdx, [rbp+37h+SourceString]; SourceString
0x18001b553  mov     word ptr [rbp+37h+var_58], ax
0x18001b557  movzx   eax, word ptr [rsp+110h+ServerBinding+0Ah]
0x18001b55c  mov     word ptr [rbp+37h+var_58+2], ax
0x18001b560  mov     eax, dword ptr [rsp+110h+ServerBinding+0Ch]
0x18001b564  mov     dword ptr [rbp+37h+var_58+4], eax
0x18001b567  mov     rax, qword ptr [rsp+110h+ServerBinding+10h]
0x18001b56c  mov     [rbp+37h+var_50], rax
0x18001b570  call    cs:__imp_RtlInitUnicodeString
0x18001b576  lea     r9, [rbp+37h+var_58]
0x18001b57a  mov     r8d, r12d
0x18001b57d  mov     edx, 14h
0x18001b582  xor     ecx, ecx
0x18001b584  call    cs:__imp_LsapTraceEventWithData
0x18001b58a  test    rsi, rsi
0x18001b58d  jnz     short loc_18001B5AC
0x18001b58f  mov     edx, [rsp+110h+var_E0]; int
0x18001b593  lea     r9, [rbp+37h+var_A0]; struct _LSAP_DB_LOOKUP_WORK_ITEM **
0x18001b597  xor     ecx, ecx; SourceString
0x18001b599  call    ?LsaDbpLookupCreateWorkItem@@YAJPEAU_LSAPR_TRUST_INFORMATION@@JKPEAPEAU_LSAP_DB_LOOKUP_WORK_ITEM@@@Z; LsaDbpLookupCreateWorkItem(_LSAPR_TRUST_INFORMATION *,long,ulong,_LSAP_DB_LOOKUP_WORK_ITEM * *)
0x18001b59e  mov     rsi, [rbp+37h+var_A0]
0x18001b5a2  mov     ebx, eax
0x18001b5a4  test    eax, eax
0x18001b5a6  js      loc_18001B838
0x18001b5ac  mov     eax, 1
0x18001b5b1  lea     r8, [rsp+110h+NetworkAddr]; unsigned int *
0x18001b5b6  mov     edx, eax; unsigned int
0x18001b5b8  mov     [rsi+14h], eax
0x18001b5bb  mov     rcx, rsi; struct _LSAP_DB_LOOKUP_WORK_ITEM *
0x18001b5be  call    ?LsaDbpLookupAddIndicesToWorkItem@@YAJPEAU_LSAP_DB_LOOKUP_WORK_ITEM@@KPEAK@Z; LsaDbpLookupAddIndicesToWorkItem(_LSAP_DB_LOOKUP_WORK_ITEM *,ulong,ulong *)
0x18001b5c3  mov     ebx, eax
0x18001b5c5  test    eax, eax
0x18001b5c7  js      loc_18001B838
0x18001b5cd  mov     r15d, dword ptr [rsp+110h+NetworkAddr]
0x18001b5d2  jmp     loc_18001B71C
0x18001b5d7  lea     rcx, [r14+18h]
0x18001b5db  xor     r8d, r8d
0x18001b5de  lea     rdx, [rbp+37h+var_90]
0x18001b5e2  call    cs:__imp_LsapCompareDomainNames
0x18001b5e8  test    al, al
0x18001b5ea  jnz     short loc_18001B62D
0x18001b5ec  mov     r14, [r14]
0x18001b5ef  cmp     r14, r13
0x18001b5f2  jnz     short loc_18001B5D7
0x18001b5f4  xor     r13d, r13d
0x18001b5f7  xor     r8d, r8d; void *
0x18001b5fa  lea     rax, [rbp+37h+var_80]
0x18001b5fe  lea     r9, [rbp+37h+arg_38]; unsigned __int8 *
0x18001b602  mov     [rsp+110h+Endpoint], rax; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x18001b607  lea     rdx, [rbp+37h+var_90]; struct _UNICODE_STRING *
0x18001b60b  lea     ecx, [r8+1]; unsigned int
0x18001b60f  call    ?LsaDbpDomainHasDomainTrust@@YAJKPEAU_UNICODE_STRING@@PEAXPEAEPEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpDomainHasDomainTrust(ulong,_UNICODE_STRING *,void *,uchar *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x18001b614  mov     ebx, eax
0x18001b616  test    eax, eax
0x18001b618  jns     short loc_18001B63E
0x18001b61a  cmp     eax, 0C00000DFh
0x18001b61f  jnz     loc_18001B838
0x18001b625  mov     ebx, r13d
0x18001b628  jmp     loc_18001B71C
0x18001b62d  xor     r13d, r13d
0x18001b630  test    r14, r14
0x18001b633  jz      short loc_18001B5F7
0x18001b635  mov     r12, [rbp+37h+arg_28]
0x18001b639  jmp     loc_18001B6BE
0x18001b63e  mov     r12, [rbp+37h+arg_28]
0x18001b642  lea     r8, [rsp+110h+var_E0]
0x18001b647  xor     eax, eax
0x18001b649  lea     rdx, [rbp+37h+var_70]
0x18001b64d  mov     [rbp+37h+var_60], rax
0x18001b651  xorps   xmm0, xmm0
0x18001b654  mov     rax, [rbp+37h+var_80]
0x18001b658  mov     rcx, r12
0x18001b65b  movups  xmmword ptr [rbp+37h+var_70.Length], xmm0
0x18001b65f  movups  xmm0, xmmword ptr [rax+20h]
0x18001b663  movdqu  xmmword ptr [rbp+37h+var_70.Length], xmm0
0x18001b668  mov     rax, [rax+30h]
0x18001b66c  mov     [rbp+37h+var_60], rax
0x18001b670  lea     rax, [rbp+37h+var_70]
0x18001b674  mov     [rbp+37h+var_98], rax
0x18001b678  call    cs:__imp_LsapDbLookupAddListReferencedDomains
0x18001b67e  mov     ebx, eax
0x18001b680  test    eax, eax
0x18001b682  js      loc_18001B838
0x18001b688  mov     edx, [rsp+110h+var_E0]; int
0x18001b68c  lea     r9, [rsp+110h+StringBinding]; struct _LSAP_DB_LOOKUP_WORK_ITEM **
0x18001b691  lea     rcx, [rbp+37h+var_70]; SourceString
0x18001b695  call    ?LsaDbpLookupCreateWorkItem@@YAJPEAU_LSAPR_TRUST_INFORMATION@@JKPEAPEAU_LSAP_DB_LOOKUP_WORK_ITEM@@@Z; LsaDbpLookupCreateWorkItem(_LSAPR_TRUST_INFORMATION *,long,ulong,_LSAP_DB_LOOKUP_WORK_ITEM * *)
0x18001b69a  mov     ebx, eax
0x18001b69c  test    eax, eax
0x18001b69e  js      loc_18001B838
0x18001b6a4  mov     r14, [rsp+110h+StringBinding]
0x18001b6a9  mov     rcx, rdi; struct _LSAP_DB_LOOKUP_WORK_LIST *
0x18001b6ac  mov     rdx, r14; struct _LSAP_DB_LOOKUP_WORK_ITEM *
0x18001b6af  call    ?LsaDbpAddWorkItemToWorkList@@YAJPEAU_LSAP_DB_LOOKUP_WORK_LIST@@PEAU_LSAP_DB_LOOKUP_WORK_ITEM@@@Z; LsaDbpAddWorkItemToWorkList(_LSAP_DB_LOOKUP_WORK_LIST *,_LSAP_DB_LOOKUP_WORK_ITEM *)
0x18001b6b4  mov     ebx, eax
0x18001b6b6  test    eax, eax
0x18001b6b8  js      loc_18001B838
0x18001b6be  lea     r8, [rsp+110h+NetworkAddr]; unsigned int *
0x18001b6c3  mov     edx, 1; unsigned int
0x18001b6c8  mov     rcx, r14; struct _LSAP_DB_LOOKUP_WORK_ITEM *
0x18001b6cb  call    ?LsaDbpLookupAddIndicesToWorkItem@@YAJPEAU_LSAP_DB_LOOKUP_WORK_ITEM@@KPEAK@Z; LsaDbpLookupAddIndicesToWorkItem(_LSAP_DB_LOOKUP_WORK_ITEM *,ulong,ulong *)
0x18001b6d0  mov     ebx, eax
0x18001b6d2  test    eax, eax
0x18001b6d4  js      loc_18001B838
0x18001b6da  mov     rax, [rdi+78h]
0x18001b6de  mov     r15d, dword ptr [rsp+110h+NetworkAddr]
0x18001b6e3  mov     rcx, [rax+8]
0x18001b6e7  mov     eax, [r14+30h]
0x18001b6eb  lea     rdx, [r15+r15*2]
0x18001b6ef  mov     [rcx+rdx*8+10h], eax
0x18001b6f3  jmp     short loc_18001B720
0x18001b6f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6fc  test    byte ptr [rcx+1Ch], 20h
0x18001b700  jz      short loc_18001B71C
0x18001b702  mov     rcx, [rcx+10h]
0x18001b706  lea     r9, [rsp+110h+ServerBinding+8]
0x18001b70b  mov     edx, 0Bh
0x18001b710  lea     r8, WPP_cdea14064fb83782dcfb43a713b43d51_Traceguids
0x18001b717  call    WPP_SF_Z
0x18001b71c  mov     r12, [rbp+37h+arg_28]
0x18001b720  mov     r8, [rbp+37h+arg_30]
0x18001b724  inc     r15d
0x18001b727  mov     edx, r15d
0x18001b72a  mov     dword ptr [rsp+110h+NetworkAddr], r15d
0x18001b72f  mov     eax, r15d
0x18001b732  cmp     r15d, [rbp+37h+arg_8]
0x18001b736  jb      loc_18001B429
0x18001b73c  test    ebx, ebx
0x18001b73e  js      loc_18001B838
0x18001b744  test    rsi, rsi
0x18001b747  jz      loc_18001B8AE
0x18001b74d  mov     rax, [rdi+10h]
0x18001b751  mov     r14, [rax]
0x18001b754  cmp     r14, rax
0x18001b757  jz      short loc_18001B77B
0x18001b759  mov     r8, [rsi+40h]; unsigned int *
0x18001b75d  mov     rcx, r14; struct _LSAP_DB_LOOKUP_WORK_ITEM *
0x18001b760  mov     edx, [rsi+34h]; unsigned int
0x18001b763  call    ?LsaDbpLookupAddIndicesToWorkItem@@YAJPEAU_LSAP_DB_LOOKUP_WORK_ITEM@@KPEAK@Z; LsaDbpLookupAddIndicesToWorkItem(_LSAP_DB_LOOKUP_WORK_ITEM *,ulong,ulong *)
0x18001b768  mov     ebx, eax
0x18001b76a  test    eax, eax
0x18001b76c  js      loc_18001B838
0x18001b772  mov     r14, [r14]
0x18001b775  cmp     r14, [rdi+10h]
0x18001b779  jnz     short loc_18001B759
0x18001b77b  cmp     byte ptr [rbp+37h+arg_38], r13b
0x18001b77f  jnz     short loc_18001B795
  ... truncated ...
```
