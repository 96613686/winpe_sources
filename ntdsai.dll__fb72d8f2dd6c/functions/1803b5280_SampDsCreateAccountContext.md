# SampDsCreateAccountContext

- ea: `0x1803b5280`
- end: `0x1803b5936`
- name: `SampDsCreateAccountContext`
- size: `1718`
- prototype: `__int64 __fastcall(int, int, int, int, char, char, char, int, char, struct _SAMP_OBJECT *, __int64, __int64, int, char, int, __int64)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x180030af8`
- `0x180166f10`
- `0x1803af360`
- `0x1803af3c8`
- `0x1803af580`
- `0x1803af854`
- `0x1803aff80`
- `0x1803b0860`
- `0x1803b1a18`
- `0x1803b4fc4`
- `0x1803b5280`
- `0x1803d99e8`
- `0x1803db8bc`
- `0x1803dedec`
- `0x1803defa0`
- `0x1803e6580`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1803b52b2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1803b54c5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1803b52b2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1803b54c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803b52d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803b52d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803b531e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803b58e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803b58f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803b5905`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803b5913`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803b531e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803b58e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803b58f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803b5905`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803b5913`
- `SAMSRV!SampCreateFullSid` at `0x1803b52fc`
- `SAMSRV!SampCreateFullSid` at `0x1803b58c9`
- `SAMSRV!SampCreateFullSid` at `0x1803b52fc`
- `SAMSRV!SampCreateFullSid` at `0x1803b58c9`
- `SAMSRV!SampGetDomainSidFromIndex` at `0x1803b58b7`
- `SAMSRV!SampGetDomainSidFromIndex` at `0x1803b58b7`
- `SAMSRV!SampIsBuiltinDomain` at `0x1803b55e3`
- `SAMSRV!SampIsBuiltinDomain` at `0x1803b55e3`
- `SAMSRV!SampCheckGroupTypeBits` at `0x1803b5572`
- `SAMSRV!SampCheckGroupTypeBits` at `0x1803b5572`
- `SAMSRV!SampGetCurrentOwnerAndPrimaryGroup` at `0x1803b584e`
- `SAMSRV!SampGetCurrentOwnerAndPrimaryGroup` at `0x1803b584e`

## pseudocode

```c
__int64 __fastcall SampDsCreateAccountContext(
        unsigned int a1,
        unsigned int a2,
        _DWORD *a3,
        __int64 a4,
        char a5,
        char a6,
        char a7,
        int a8,
        char a9,
        struct _SAMP_OBJECT *a10,
        __int64 a11,
        __int64 a12,
        unsigned int a13,
        char a14,
        int a15,
        unsigned int *a16)
{
  unsigned __int64 v19; // r12
  HLOCAL v20; // r14
  int AccountObjectDsName; // ebx
  struct _SAMP_OBJECT *v22; // rdx
  char v23; // al
  __int64 v24; // rdx
  __int64 v25; // rcx
  int v26; // edi
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // r8
  __int64 v30; // r9
  BOOL v31; // r15d
  void *v32; // rcx
  int exists; // eax
  char v34; // r14
  _QWORD *v35; // rax
  struct _SAMP_OBJECT *v36; // rsi
  __int64 v37; // r8
  int DefaultSecurityDescriptorForClass; // eax
  int v39; // edi
  __int64 v40; // rdx
  int v41; // ebx
  int v42; // ecx
  char IsBuiltinDomain; // al
  __int64 v44; // rcx
  int v45; // edx
  char v46; // r15
  __int64 v47; // rcx
  bool v48; // cf
  __int64 v49; // rax
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // r8
  __int64 v53; // r9
  __int64 v54; // r8
  __int64 v55; // r9
  BOOL v56; // r14d
  __int64 v57; // rcx
  void *Sid; // rbx
  int v59; // edx
  void *SecurityDescriptor; // rax
  __int64 DomainSidFromIndex; // rax
  HLOCAL v63; // [rsp+58h] [rbp-49h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-41h] BYREF
  HLOCAL Value; // [rsp+68h] [rbp-39h] BYREF
  _OWORD v66[6]; // [rsp+70h] [rbp-31h] BYREF
  int v67; // [rsp+F0h] [rbp+4Fh] BYREF
  __int64 v68; // [rsp+100h] [rbp+5Fh]

  v68 = a4;
  v67 = a2;
  v19 = 0;
  Value = TlsGetValue(dwTSindex);
  v63 = 0;
  LODWORD(hMem) = 0;
  if ( !(_BYTE)a8 )
  {
    exists = SampExistsDsLoopback(&a14);
    v34 = a7;
    if ( !exists || a7 )
    {
      v36 = a10;
      if ( a1 == 4 && a3 && (*a3 & 0x1C0) != 0 )
        *((_DWORD *)a10 + 49) = 196638;
      AccountObjectDsName = SampMaybeBeginDsTransaction((unsigned int)SampDsTransactionType);
      if ( AccountObjectDsName >= 0 )
      {
        LOBYTE(v37) = a5;
        DefaultSecurityDescriptorForClass = SampGetDefaultSecurityDescriptorForClass(
                                              *((unsigned int *)v36 + 49),
                                              &hMem,
                                              v37,
                                              &v63);
        v19 = (unsigned __int64)v63;
        AccountObjectDsName = DefaultSecurityDescriptorForClass;
      }
    }
    else
    {
      AccountObjectDsName = 0;
      v35 = TlsGetValue(dwTSindex);
      v36 = a10;
      *((_DWORD *)a10 + 49) = *(_DWORD *)(v35[714] + 48LL);
    }
    v39 = 1;
    if ( a1 - 2 > 1 )
    {
      if ( AccountObjectDsName < 0 )
        goto LABEL_87;
    }
    else
    {
      if ( AccountObjectDsName < 0 )
        goto LABEL_87;
      LODWORD(v63) = 0;
      LODWORD(hMem) = 0;
      v40 = *a16;
      LOBYTE(a8) = 1;
      AccountObjectDsName = SampCheckGroupTypeBits(a13, v40);
      if ( AccountObjectDsName < 0 )
        goto LABEL_87;
      v41 = *a16;
      SampDeriveMostBasicDsClass(*((unsigned int *)v36 + 49));
      AccountObjectDsName = SampComputeGroupType(v42, v41, (unsigned int)&v63, (unsigned int)&hMem, (__int64)&a8);
      if ( AccountObjectDsName < 0 )
        goto LABEL_87;
      *((_DWORD *)v36 + 63) = (_DWORD)v63;
      *((_DWORD *)v36 + 64) = (_DWORD)hMem;
      *((_BYTE *)v36 + 260) = a8;
    }
    IsBuiltinDomain = SampIsBuiltinDomain(a13);
    AccountObjectDsName = SampDsCreateAccountObjectDsName(
                            *(_QWORD *)(a11 + 176),
                            a12,
                            a1,
                            v68,
                            (__int64)&v67,
                            (__int64)a3,
                            IsBuiltinDomain,
                            (__int64)v36 + 176);
    if ( AccountObjectDsName < 0 )
      goto LABEL_87;
    LOBYTE(v44) = a5 != 0;
    SampSetDsa(v44);
    v46 = a6;
    if ( a6 && *((_DWORD *)v36 + 49) == 196638 )
    {
      a8 = 0;
      memset(v66, 0, 48);
      LODWORD(v66[0]) = 8;
      AccountObjectDsName = SampDsControl(v66, &a8);
      if ( AccountObjectDsName < 0 )
      {
LABEL_53:
        if ( AccountObjectDsName != -1073741790 )
          goto LABEL_87;
        goto LABEL_54;
      }
      if ( a8 )
      {
        AccountObjectDsName = -1073741790;
LABEL_54:
        if ( v34 )
        {
          if ( Value && *((_DWORD *)Value + 1390) == 4 && (v49 = *((_QWORD *)Value + 696)) != 0 && *(_DWORD *)(v49 + 8) )
          {
            if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
              || (unsigned int)THStateCheckForTraceOverride(v51, v50)
              || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)
              || gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v51, v50)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier(v51, v50, v52, v53)
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13)) )
            {
              v56 = gfTraceToSecondProvider
                 && ((unsigned int)THStateCheckForTraceOverride(v51, v50)
                  || (unsigned int)ThStateCheckIfTraceToSecondProvier(v51, v50, v54, v55)
                  && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13));
              if ( !(unsigned int)THStateCheckForTraceOverride(v51, v50)
                && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13) )
              {
                v39 = 0;
              }
              WPP_SF_(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                522847385,
                3,
                13,
                v39,
                v56,
                12,
                &WPP_935640dc42de31df20c225250686cb27_Traceguids);
            }
          }
          else
          {
            THClearErrors(v47);
            AccountObjectDsName = SampCheckQuotaForPrivilegeMachineAccountCreation();
            if ( AccountObjectDsName >= 0 )
            {
              v63 = 0;
              Value = 0;
              AccountObjectDsName = SampGetCurrentOwnerAndPrimaryGroup(&v63, &Value);
              if ( AccountObjectDsName >= 0 )
              {
                LOBYTE(v57) = v46 == 0;
                Sid = *(void **)v63;
                SampSetDsa(v57);
                SecurityDescriptor = 0;
                if ( !v46 )
                  SecurityDescriptor = (void *)v19;
                AccountObjectDsName = SampDsCreateInitialAccountObject(
                                        (int)v36,
                                        v59,
                                        v67,
                                        v68,
                                        Sid,
                                        SecurityDescriptor,
                                        (__int64)a3,
                                        (__int64)a16);
                if ( AccountObjectDsName >= 0 )
                {
                  hMem = 0;
                  DomainSidFromIndex = SampGetDomainSidFromIndex(3);
                  AccountObjectDsName = SampCreateFullSid(DomainSidFromIndex, 512, &hMem);
                  if ( AccountObjectDsName >= 0 )
                  {
                    AccountObjectDsName = SampSetMachineAccountOwner(v36, hMem);
                    LocalFree(hMem);
                  }
                }
              }
              if ( v63 )
                LocalFree(v63);
              if ( Value )
                LocalFree(Value);
            }
          }
        }
        goto LABEL_87;
      }
    }
    v48 = a5 != 0;
    a5 = -a5;
    AccountObjectDsName = SampDsCreateInitialAccountObject(
                            (int)v36,
                            v45,
                            v67,
                            v68,
                            0,
                            (PSECURITY_DESCRIPTOR)(v19 & -(__int64)v48),
                            (__int64)a3,
                            (__int64)a16);
    if ( AccountObjectDsName >= 0 )
    {
      if ( v34 )
        *((_BYTE *)v36 + 326) = 0;
LABEL_87:
      if ( v19 )
      {
        v32 = (void *)v19;
        goto LABEL_89;
      }
      return (unsigned int)AccountObjectDsName;
    }
    goto LABEL_53;
  }
  v20 = LocalAlloc(0x40u, 0x3Cu);
  if ( !v20 )
    return (unsigned int)-1073741670;
  hMem = 0;
  AccountObjectDsName = SampCreateFullSid(a12, a2, &hMem);
  if ( AccountObjectDsName < 0 )
  {
LABEL_27:
    v32 = v20;
LABEL_89:
    LocalFree(v32);
    return (unsigned int)AccountObjectDsName;
  }
  AccountObjectDsName = SampBuildDsNameFromSidNew(hMem);
  LocalFree(hMem);
  if ( AccountObjectDsName < 0 )
  {
    v26 = 1;
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v25, v24)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v25, v24)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v25, v24, v27, v28)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
    {
      v31 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v25, v24)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v25, v24, v29, v30)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
      if ( !(unsigned int)THStateCheckForTraceOverride(v25, v24)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) )
      {
        v26 = 0;
      }
      WPP_SF__ATTRTYP_LOG_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        522847088,
        2,
        13,
        v26,
        v31,
        11,
        (__int64)&WPP_935640dc42de31df20c225250686cb27_Traceguids);
    }
    goto LABEL_27;
  }
  AccountObjectDsName = SampMaybeBeginDsTransaction((unsigned int)SampDsTransactionType);
  if ( AccountObjectDsName >= 0 )
  {
    v22 = a10;
    v23 = a9;
    *((_QWORD *)a10 + 22) = v20;
    AccountObjectDsName = SampDsCheckObjectTypeAndFillContextWithClaims(a1, v22, 0, 0, v23, 0, 0, 0);
    if ( (unsigned int)(AccountObjectDsName + 1073741773) > 1 )
      return (unsigned int)AccountObjectDsName;
    AccountObjectDsName = a15;
    v20 = 0;
  }
  if ( v20 )
    goto LABEL_27;
  return (unsigned int)AccountObjectDsName;
}

```

## disassembly

```asm
0x1803b5280  mov     rax, rsp
0x1803b5283  mov     [rax+8], rbx
0x1803b5287  mov     [rax+20h], r9
0x1803b528b  mov     [rax+10h], edx
0x1803b528e  push    rbp
0x1803b528f  push    rsi
0x1803b5290  push    rdi
0x1803b5291  push    r12
0x1803b5293  push    r13
0x1803b5295  push    r14
0x1803b5297  push    r15
0x1803b5299  lea     rbp, [rax-3Fh]
0x1803b529d  sub     rsp, 0A0h
0x1803b52a4  mov     r15d, ecx
0x1803b52a7  mov     r13, r8
0x1803b52aa  mov     ecx, cs:dwTSindex; dwTlsIndex
0x1803b52b0  mov     ebx, edx
0x1803b52b2  call    cs:__imp_TlsGetValue
0x1803b52b8  xor     r12d, r12d
0x1803b52bb  mov     [rbp+37h+var_70], rax
0x1803b52bf  mov     [rbp+37h+var_80], r12
0x1803b52c3  mov     dword ptr [rbp+37h+hMem], r12d
0x1803b52c7  cmp     byte ptr [rbp+37h+arg_38], r12b
0x1803b52cb  jz      loc_1803B54A4
0x1803b52d1  lea     edx, [r12+3Ch]; uBytes
0x1803b52d6  lea     ecx, [rdx+4]; uFlags
0x1803b52d9  call    cs:__imp_LocalAlloc
0x1803b52df  mov     r14, rax
0x1803b52e2  test    rax, rax
0x1803b52e5  jz      loc_1803B549A
0x1803b52eb  mov     rcx, [rbp+37h+arg_58]
0x1803b52f2  lea     r8, [rbp+37h+hMem]
0x1803b52f6  mov     edx, ebx
0x1803b52f8  mov     [rbp+37h+hMem], r12
0x1803b52fc  call    cs:__imp_SampCreateFullSid
0x1803b5302  mov     ebx, eax
0x1803b5304  test    eax, eax
0x1803b5306  js      loc_1803B5492
0x1803b530c  mov     rcx, [rbp+37h+hMem]; Src
0x1803b5310  mov     rdx, r14
0x1803b5313  call    SampBuildDsNameFromSidNew
0x1803b5318  mov     rcx, [rbp+37h+hMem]; hMem
0x1803b531c  mov     ebx, eax
0x1803b531e  call    cs:__imp_LocalFree
0x1803b5324  test    ebx, ebx
0x1803b5326  js      short loc_1803B5399
0x1803b5328  mov     ecx, cs:SampDsTransactionType
0x1803b532e  call    SampMaybeBeginDsTransaction
0x1803b5333  mov     ebx, eax
0x1803b5335  test    eax, eax
0x1803b5337  js      short loc_1803B538B
0x1803b5339  mov     rdx, [rbp+37h+arg_48]
0x1803b5340  xor     r9d, r9d
0x1803b5343  mov     al, [rbp+37h+arg_40]
0x1803b5349  xor     r8d, r8d
0x1803b534c  mov     [rsp+0D0h+var_98], r12
0x1803b5351  mov     ecx, r15d
0x1803b5354  mov     qword ptr [rsp+0D0h+var_A0], r12
0x1803b5359  mov     [rsp+0D0h+SecurityDescriptor], r12
0x1803b535e  mov     [rdx+0B0h], r14
0x1803b5365  mov     byte ptr [rsp+0D0h+Sid], al
0x1803b5369  call    ?SampDsCheckObjectTypeAndFillContextWithClaims@@YAJW4_SAMP_OBJECT_TYPE@@PEAU_SAMP_OBJECT@@KKEPEAU_SAMP_CLAIM_CONFIG_SET@@PEAU_SAM_CLAIMS_ARRAY@@3@Z; SampDsCheckObjectTypeAndFillContextWithClaims(_SAMP_OBJECT_TYPE,_SAMP_OBJECT *,ulong,ulong,uchar,_SAMP_CLAIM_CONFIG_SET *,_SAM_CLAIMS_ARRAY *,_SAM_CLAIMS_ARRAY *)
0x1803b536e  mov     ebx, eax
0x1803b5370  lea     edi, [r12+1]
0x1803b5375  add     eax, 3FFFFFCDh
0x1803b537a  cmp     eax, edi
0x1803b537c  ja      loc_1803B5919
0x1803b5382  mov     ebx, [rbp+37h+arg_70]
0x1803b5388  mov     r14d, r12d
0x1803b538b  test    r14, r14
0x1803b538e  jz      loc_1803B5919
0x1803b5394  jmp     loc_1803B5492
0x1803b5399  mov     r13d, 2
0x1803b539f  mov     ecx, r13d
0x1803b53a2  call    IncrementWPPPerfCountersForLevel
0x1803b53a7  lea     edi, [r13-1]
0x1803b53ab  lea     esi, [rdi+0Ch]
0x1803b53ae  test    eax, eax
0x1803b53b0  jnz     short loc_1803B5405
0x1803b53b2  call    THStateCheckForTraceOverride
0x1803b53b7  test    eax, eax
0x1803b53b9  jnz     short loc_1803B5405
0x1803b53bb  mov     r8d, esi
0x1803b53be  mov     edx, r13d
0x1803b53c1  xor     ecx, ecx
0x1803b53c3  call    CheckWPPLevelFlagsEnabledForProvider
0x1803b53c8  test    eax, eax
0x1803b53ca  jnz     short loc_1803B5405
0x1803b53cc  mov     eax, cs:gfTraceToSecondProvider
0x1803b53d2  test    eax, eax
0x1803b53d4  jz      loc_1803B5492
0x1803b53da  call    THStateCheckForTraceOverride
0x1803b53df  test    eax, eax
0x1803b53e1  jnz     short loc_1803B5405
0x1803b53e3  call    ThStateCheckIfTraceToSecondProvier
0x1803b53e8  test    eax, eax
0x1803b53ea  jz      loc_1803B5492
0x1803b53f0  mov     r8d, esi
0x1803b53f3  mov     edx, r13d
0x1803b53f6  mov     ecx, edi
0x1803b53f8  call    CheckWPPLevelFlagsEnabledForProvider
0x1803b53fd  test    eax, eax
0x1803b53ff  jz      loc_1803B5492
0x1803b5405  mov     eax, cs:gfTraceToSecondProvider
0x1803b540b  test    eax, eax
0x1803b540d  jz      short loc_1803B5437
0x1803b540f  call    THStateCheckForTraceOverride
0x1803b5414  test    eax, eax
0x1803b5416  jnz     short loc_1803B5432
0x1803b5418  call    ThStateCheckIfTraceToSecondProvier
0x1803b541d  test    eax, eax
0x1803b541f  jz      short loc_1803B5437
0x1803b5421  mov     r8d, esi
0x1803b5424  mov     edx, r13d
0x1803b5427  mov     ecx, edi
0x1803b5429  call    CheckWPPLevelFlagsEnabledForProvider
0x1803b542e  test    eax, eax
0x1803b5430  jz      short loc_1803B5437
0x1803b5432  mov     r15d, edi
0x1803b5435  jmp     short loc_1803B543A
0x1803b5437  mov     r15d, r12d
0x1803b543a  call    THStateCheckForTraceOverride
0x1803b543f  test    eax, eax
0x1803b5441  jnz     short loc_1803B5457
0x1803b5443  mov     r8d, esi
0x1803b5446  mov     edx, r13d
0x1803b5449  xor     ecx, ecx
0x1803b544b  call    CheckWPPLevelFlagsEnabledForProvider
0x1803b5450  test    eax, eax
0x1803b5452  jnz     short loc_1803B5457
0x1803b5454  mov     edi, r12d
0x1803b5457  mov     rcx, cs:WPP_GLOBAL_Control
0x1803b545e  lea     rax, WPP_935640dc42de31df20c225250686cb27_Traceguids
0x1803b5465  mov     [rsp+40h], ebx
0x1803b5469  mov     r9d, esi
0x1803b546c  mov     [rsp+0D0h+var_98], rax
0x1803b5471  mov     r8d, r13d
0x1803b5474  mov     [rsp+0D0h+var_A0], 0Bh
0x1803b547b  mov     edx, 1F2A0370h
0x1803b5480  mov     rcx, [rcx+10h]
0x1803b5484  mov     dword ptr [rsp+0D0h+SecurityDescriptor], r15d
0x1803b5489  mov     dword ptr [rsp+0D0h+Sid], edi
0x1803b548d  call    WPP_SF__ATTRTYP_LOG_
0x1803b5492  mov     rcx, r14
0x1803b5495  jmp     loc_1803B5913
0x1803b549a  mov     ebx, 0C000009Ah
0x1803b549f  jmp     loc_1803B5919
0x1803b54a4  lea     rcx, [rbp+37h+arg_68]
0x1803b54ab  call    SampExistsDsLoopback
0x1803b54b0  mov     r14b, [rbp+37h+arg_30]
0x1803b54b4  test    eax, eax
0x1803b54b6  jz      short loc_1803B54E4
0x1803b54b8  test    r14b, r14b
0x1803b54bb  jnz     short loc_1803B54E4
0x1803b54bd  mov     ecx, cs:dwTSindex; dwTlsIndex
0x1803b54c3  xor     ebx, ebx
0x1803b54c5  call    cs:__imp_TlsGetValue
0x1803b54cb  mov     rsi, [rbp+37h+arg_48]
0x1803b54d2  mov     rcx, [rax+1650h]
0x1803b54d9  mov     eax, [rcx+30h]
0x1803b54dc  mov     [rsi+0C4h], eax
0x1803b54e2  jmp     short loc_1803B5538
0x1803b54e4  mov     rsi, [rbp+37h+arg_48]
0x1803b54eb  cmp     r15d, 4
0x1803b54ef  jnz     short loc_1803B550A
0x1803b54f1  test    r13, r13
0x1803b54f4  jz      short loc_1803B550A
0x1803b54f6  test    dword ptr [r13+0], 1C0h
0x1803b54fe  jz      short loc_1803B550A
0x1803b5500  mov     dword ptr [rsi+0C4h], 3001Eh
0x1803b550a  mov     ecx, cs:SampDsTransactionType
0x1803b5510  call    SampMaybeBeginDsTransaction
0x1803b5515  mov     ebx, eax
0x1803b5517  test    eax, eax
0x1803b5519  js      short loc_1803B5538
0x1803b551b  mov     r8b, [rbp+37h+arg_20]
0x1803b551f  lea     r9, [rbp+37h+var_80]
0x1803b5523  mov     ecx, [rsi+0C4h]
0x1803b5529  lea     rdx, [rbp+37h+hMem]
0x1803b552d  call    SampGetDefaultSecurityDescriptorForClass
0x1803b5532  mov     r12, [rbp+37h+var_80]
0x1803b5536  mov     ebx, eax
0x1803b5538  lea     eax, [r15-2]
0x1803b553c  mov     edi, 1
0x1803b5541  cmp     eax, edi
0x1803b5543  ja      loc_1803B55D5
0x1803b5549  test    ebx, ebx
0x1803b554b  js      loc_1803B590B
0x1803b5551  mov     rax, [rbp+37h+arg_78]
0x1803b5558  mov     ecx, [rbp+37h+arg_60]
0x1803b555e  mov     dword ptr [rbp+37h+var_80], 0
0x1803b5565  mov     dword ptr [rbp+37h+hMem], 0
0x1803b556c  mov     edx, [rax]
0x1803b556e  mov     byte ptr [rbp+37h+arg_38], dil
0x1803b5572  call    cs:__imp_SampCheckGroupTypeBits
0x1803b5578  mov     ebx, eax
0x1803b557a  test    eax, eax
0x1803b557c  js      loc_1803B590B
0x1803b5582  mov     rax, [rbp+37h+arg_78]
0x1803b5589  mov     ecx, [rsi+0C4h]
0x1803b558f  mov     ebx, [rax]
0x1803b5591  call    SampDeriveMostBasicDsClass
0x1803b5596  lea     rax, [rbp+37h+arg_38]
0x1803b559a  mov     edx, ebx
0x1803b559c  lea     r9, [rbp+37h+hMem]
0x1803b55a0  mov     [rsp+0D0h+Sid], rax
0x1803b55a5  lea     r8, [rbp+37h+var_80]
0x1803b55a9  call    SampComputeGroupType
0x1803b55ae  mov     ebx, eax
0x1803b55b0  test    eax, eax
0x1803b55b2  js      loc_1803B590B
0x1803b55b8  mov     eax, dword ptr [rbp+37h+var_80]
0x1803b55bb  mov     [rsi+0FCh], eax
0x1803b55c1  mov     eax, dword ptr [rbp+37h+hMem]
0x1803b55c4  mov     [rsi+100h], eax
0x1803b55ca  mov     al, byte ptr [rbp+37h+arg_38]
0x1803b55cd  mov     [rsi+104h], al
0x1803b55d3  jmp     short loc_1803B55DD
0x1803b55d5  test    ebx, ebx
0x1803b55d7  js      loc_1803B590B
0x1803b55dd  mov     ecx, [rbp+37h+arg_60]
0x1803b55e3  call    cs:__imp_SampIsBuiltinDomain
0x1803b55e9  mov     r9, [rbp+37h+arg_18]
0x1803b55ed  lea     rcx, [rsi+0B0h]
0x1803b55f4  mov     rdx, [rbp+37h+arg_58]
0x1803b55fb  mov     r8d, r15d
0x1803b55fe  mov     [rsp+0D0h+var_98], rcx
0x1803b5603  mov     rcx, [rbp+37h+arg_50]
0x1803b560a  mov     byte ptr [rsp+0D0h+var_A0], al
0x1803b560e  lea     rax, [rbp+37h+arg_8]
0x1803b5612  mov     [rsp+0D0h+SecurityDescriptor], r13
0x1803b5617  mov     [rsp+0D0h+Sid], rax
0x1803b561c  mov     rcx, [rcx+0B0h]
0x1803b5623  call    SampDsCreateAccountObjectDsName
0x1803b5628  mov     ebx, eax
0x1803b562a  test    eax, eax
0x1803b562c  js      loc_1803B590B
0x1803b5632  cmp     [rbp+37h+arg_20], 0
0x1803b5636  setnz   cl
0x1803b5639  call    SampSetDsa
0x1803b563e  mov     r15b, [rbp+37h+arg_28]
0x1803b5642  test    r15b, r15b
0x1803b5645  jz      short loc_1803B5690
0x1803b5647  cmp     dword ptr [rsi+0C4h], 3001Eh
0x1803b5651  jnz     short loc_1803B5690
0x1803b5653  xorps   xmm0, xmm0
0x1803b5656  mov     [rbp+37h+arg_38], 0
0x1803b565d  movups  [rbp+37h+var_68], xmm0
0x1803b5661  lea     rdx, [rbp+37h+arg_38]
0x1803b5665  mov     dword ptr [rbp+37h+var_68], 8
0x1803b566c  lea     rcx, [rbp+37h+var_68]
0x1803b5670  movups  [rbp+37h+var_58], xmm0
0x1803b5674  movups  [rbp+37h+var_48], xmm0
0x1803b5678  call    SampDsControl
0x1803b567d  mov     ebx, eax
0x1803b567f  test    eax, eax
0x1803b5681  js      short loc_1803B56E3
0x1803b5683  cmp     [rbp+37h+arg_38], 0
0x1803b5687  jz      short loc_1803B5690
0x1803b5689  mov     ebx, 0C0000022h
0x1803b568e  jmp     short loc_1803B56EF
0x1803b5690  mov     rcx, [rbp+37h+arg_78]
0x1803b5697  neg     [rbp+37h+arg_20]
0x1803b569a  mov     r9, [rbp+37h+arg_18]; int
0x1803b569e  mov     r8d, [rbp+37h+arg_8]; int
0x1803b56a2  sbb     rax, rax
0x1803b56a5  mov     [rsp+0D0h+var_98], rcx; __int64
0x1803b56aa  and     rax, r12
0x1803b56ad  mov     qword ptr [rsp+0D0h+var_A0], r13; __int64
0x1803b56b2  mov     rcx, rsi; int
0x1803b56b5  mov     [rsp+0D0h+SecurityDescriptor], rax; SecurityDescriptor
0x1803b56ba  mov     [rsp+0D0h+Sid], 0; Sid
0x1803b56c3  call    SampDsCreateInitialAccountObject
0x1803b56c8  mov     ebx, eax
0x1803b56ca  test    eax, eax
0x1803b56cc  js      short loc_1803B56E3
0x1803b56ce  test    r14b, r14b
0x1803b56d1  jz      loc_1803B590B
0x1803b56d7  mov     byte ptr [rsi+146h], 0
0x1803b56de  jmp     loc_1803B590B
0x1803b56e3  cmp     ebx, 0C0000022h
0x1803b56e9  jnz     loc_1803B590B
0x1803b56ef  test    r14b, r14b
0x1803b56f2  jz      loc_1803B590B
0x1803b56f8  mov     rax, [rbp+37h+var_70]
0x1803b56fc  test    rax, rax
0x1803b56ff  jz      loc_1803B5822
0x1803b5705  cmp     dword ptr [rax+15B8h], 4
0x1803b570c  jnz     loc_1803B5822
0x1803b5712  mov     rax, [rax+15C0h]
0x1803b5719  test    rax, rax
0x1803b571c  jz      loc_1803B5822
0x1803b5722  cmp     dword ptr [rax+8], 0
0x1803b5726  jz      loc_1803B5822
0x1803b572c  mov     r15d, 3
0x1803b5732  mov     ecx, r15d
0x1803b5735  call    IncrementWPPPerfCountersForLevel
0x1803b573a  lea     esi, [r15+0Ah]
0x1803b573e  test    eax, eax
0x1803b5740  jnz     short loc_1803B5795
  ... truncated ...
```
