# KerbCreatePacForKerbClient(_PACTYPE * *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x1800be1c8`
- end: `0x1800be673`
- name: `?KerbCreatePacForKerbClient@@YAJPEAPEAU_PACTYPE@@PEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@2@Z`
- size: `1195`
- prototype: `__int64 __fastcall(struct _PACTYPE **, struct _KERB_INTERNAL_NAME *, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800819b0`
- `0x180082ef4`

## callees

- `0x1800068d0`
- `0x1800069a0`
- `0x18000b300`
- `0x180010e90`
- `0x180061b64`
- `0x18006cb94`
- `0x18006ee1c`
- `0x18008b70c`
- `0x1800be1c8`
- `0x1800dd968`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800be4d8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800be4d8`
- `ntdll!RtlReleaseResource` at `0x1800be36e`
- `ntdll!RtlReleaseResource` at `0x1800be380`
- `ntdll!RtlReleaseResource` at `0x1800be36e`
- `ntdll!RtlReleaseResource` at `0x1800be380`
- `ntdll!RtlAcquireResourceShared` at `0x1800be302`
- `ntdll!RtlAcquireResourceShared` at `0x1800be302`
- `SAMSRV!SamIFree_SAMPR_USER_INFO_BUFFER` at `0x1800be622`
- `SAMSRV!SamIFree_SAMPR_USER_INFO_BUFFER` at `0x1800be622`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x1800be60d`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x1800be60d`
- `SAMSRV!SamrOpenDomain` at `0x1800be2e8`
- `SAMSRV!SamrOpenDomain` at `0x1800be2e8`
- `SAMSRV!SamrGetGroupsForUser` at `0x1800be4c4`
- `SAMSRV!SamrGetGroupsForUser` at `0x1800be4c4`
- `SAMSRV!SamIAccountRestrictions` at `0x1800be536`
- `SAMSRV!SamIAccountRestrictions` at `0x1800be536`
- `SAMSRV!SamIFree_SAMPR_GET_GROUPS_BUFFER` at `0x1800be603`
- `SAMSRV!SamIFree_SAMPR_GET_GROUPS_BUFFER` at `0x1800be603`
- `SAMSRV!SamIFree_SAMPR_ULONG_ARRAY` at `0x1800be640`
- `SAMSRV!SamIFree_SAMPR_ULONG_ARRAY` at `0x1800be64a`
- `SAMSRV!SamIFree_SAMPR_ULONG_ARRAY` at `0x1800be640`
- `SAMSRV!SamIFree_SAMPR_ULONG_ARRAY` at `0x1800be64a`
- `SAMSRV!SamrCloseHandle` at `0x1800be5d2`
- `SAMSRV!SamrCloseHandle` at `0x1800be5e3`
- `SAMSRV!SamrCloseHandle` at `0x1800be5f4`
- `SAMSRV!SamrCloseHandle` at `0x1800be5d2`
- `SAMSRV!SamrCloseHandle` at `0x1800be5e3`
- `SAMSRV!SamrCloseHandle` at `0x1800be5f4`
- `SAMSRV!SamIConnect` at `0x1800be2c6`
- `SAMSRV!SamIConnect` at `0x1800be2c6`
- `SAMSRV!SamIGetUserLogonInformationEx` at `0x1800be3e7`
- `SAMSRV!SamIGetUserLogonInformationEx` at `0x1800be3e7`
- `SAMSRV!SamrOpenUser` at `0x1800be48c`
- `SAMSRV!SamrOpenUser` at `0x1800be48c`
- `SAMSRV!SamrQueryInformationUser` at `0x1800be4ab`
- `SAMSRV!SamrQueryInformationUser` at `0x1800be4ab`
- `SAMSRV!SamrLookupNamesInDomain` at `0x1800be450`
- `SAMSRV!SamrLookupNamesInDomain` at `0x1800be450`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x1800be636`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x1800be636`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x1800be2a5`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x1800be2a5`

## string_xrefs

- `0x1800be276`: `KerbCreatePacForKerbClient client has no TCB\n`
- `0x1800be283`: `KerbCreatePacForKerbClient`
- `0x1800be359`: `KerbCreatePacForKerbClient`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KerbCreatePacForKerbClient(
        struct _PACTYPE **a1,
        struct _KERB_INTERNAL_NAME *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4)
{
  PLSA_GET_CLIENT_INFO GetClientInfo; // rax
  struct _PACTYPE *v9; // rsi
  __int64 result; // rax
  int GroupsForUser; // ebx
  __int64 v12; // r9
  unsigned __int8 v13; // r8
  _KerberosSystemRole *v14; // rcx
  unsigned __int8 v15; // r8
  _KerberosSystemRole *v16; // rcx
  __int64 v17; // r8
  int v18; // eax
  int v19; // ebx
  int v20; // eax
  __int64 v21; // rax
  _KerberosSystemRole *v22; // rcx
  bool IsAnyKdc; // al
  struct _UNICODE_STRING *v24; // rcx
  size_t *Size; // [rsp+30h] [rbp-D0h]
  unsigned int v26; // [rsp+38h] [rbp-C8h]
  unsigned int v27; // [rsp+40h] [rbp-C0h]
  struct _PAC_INFO_BUFFER **v28; // [rsp+48h] [rbp-B8h]
  union _LARGE_INTEGER *v29; // [rsp+50h] [rbp-B0h]
  union _LARGE_INTEGER *v30; // [rsp+58h] [rbp-A8h]
  struct _LSA_LAST_INTER_LOGON_INFO *v31; // [rsp+60h] [rbp-A0h]
  size_t v32; // [rsp+70h] [rbp-90h] BYREF
  struct _SAMPR_USER_ALL_INFORMATION *v33; // [rsp+78h] [rbp-88h] BYREF
  __int64 v34; // [rsp+80h] [rbp-80h] BYREF
  __int64 v35; // [rsp+88h] [rbp-78h] BYREF
  __int64 v36; // [rsp+90h] [rbp-70h] BYREF
  struct _PACTYPE *v37; // [rsp+98h] [rbp-68h] BYREF
  struct _SAMPR_GET_GROUPS_BUFFER *v38; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-58h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING v41; // [rsp+C0h] [rbp-40h] BYREF
  struct _UNICODE_STRING v42; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v43; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD *v44; // [rsp+E8h] [rbp-18h]
  __int64 v45; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int *v46; // [rsp+F8h] [rbp-8h]
  __int64 v47; // [rsp+100h] [rbp+0h] BYREF
  __int64 v48; // [rsp+108h] [rbp+8h] BYREF
  __int128 v49; // [rsp+110h] [rbp+10h] BYREF
  __int128 v50; // [rsp+120h] [rbp+20h] BYREF
  __int128 v51; // [rsp+130h] [rbp+30h] BYREF
  __int128 v52; // [rsp+140h] [rbp+40h]

  v36 = 0;
  v35 = 0;
  v34 = 0;
  GetClientInfo = LsaFunctions->GetClientInfo;
  v32 = 0;
  v38 = 0;
  v50 = 0;
  v33 = 0;
  v9 = 0;
  v37 = 0;
  v45 = 0;
  v43 = 0;
  v51 = 0;
  SystemTimeAsFileTime = 0;
  v52 = 0;
  v48 = 0;
  v47 = 0;
  *(_QWORD *)&v41.Length = 0;
  *(_QWORD *)&v42.Length = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  v46 = 0;
  v44 = 0;
  v41.Buffer = 0;
  v42.Buffer = 0;
  result = ((__int64 (__fastcall *)(__int128 *))GetClientInfo)(&v51);
  if ( (int)result < 0 )
    return result;
  if ( !(_BYTE)v52 )
  {
    KerbTracerT::Log(1, "KerbCreatePacForKerbClient", 366, "KerbCreatePacForKerbClient client has no TCB\n");
    return 3221225569LL;
  }
  GroupsForUser = LsaIQueryInformationPolicyTrusted(5, &v36);
  if ( GroupsForUser >= 0 )
  {
    LOBYTE(v12) = 1;
    GroupsForUser = SamIConnect(0, &v35, 0, v12);
    if ( GroupsForUser >= 0 )
    {
      GroupsForUser = SamrOpenDomain(v35, 0, *(_QWORD *)(v36 + 16), &v34);
      if ( GroupsForUser >= 0 )
      {
        RtlAcquireResourceShared(&KerberosGlobalResource, 1u);
        GroupsForUser = KerbDuplicateStringEx(&v41, &KerbGlobalMachineName, v13);
        if ( GroupsForUser >= 0 )
        {
          if ( !_KerberosSystemRole::IsAnyKdc(v14)
            || (GroupsForUser = KerbDuplicateStringEx(&v42, &KerbGlobalDomainName, v15), GroupsForUser >= 0) )
          {
            RtlReleaseResource(&KerberosGlobalResource);
            if ( _KerberosSystemRole::IsAnyKdc(v16) )
            {
              v49 = 0;
              v18 = KerbBuildAltSecId(&v49, a2, v17, a3);
              if ( v18 )
              {
                GroupsForUser = KerbMapKerbError(v18);
                goto LABEL_40;
              }
              Size = &v32;
              v19 = SamIGetUserLogonInformationEx(v35, 16, &v49, 4190159, &v33, &v50);
              KerbFreeString(&v49);
              if ( v19 < 0 )
                goto LABEL_57;
            }
            if ( !v33 )
            {
LABEL_57:
              if ( a4 && a4->Buffer )
                v20 = KerbDuplicateStringEx(&DestinationString, a4, v17);
              else
                v20 = KerbMapClientName(&DestinationString, a2, a3);
              GroupsForUser = v20;
              if ( v20 < 0 )
                goto LABEL_40;
              GroupsForUser = SamrLookupNamesInDomain(v34, 1, &DestinationString, &v45, &v43);
              if ( GroupsForUser < 0 )
                goto LABEL_40;
              if ( ((*v44 - 1) & 0xFFFFFFF7) != 0 )
              {
                GroupsForUser = -1073741709;
                goto LABEL_40;
              }
              GroupsForUser = SamrOpenUser(v34, 0, *v46, &v32);
              if ( GroupsForUser < 0 )
                goto LABEL_40;
              GroupsForUser = SamrQueryInformationUser(v32, 21, &v33);
              if ( GroupsForUser < 0 )
                goto LABEL_40;
              GroupsForUser = SamrGetGroupsForUser(v32, &v38);
              if ( GroupsForUser < 0 )
                goto LABEL_40;
            }
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
            v21 = *((_QWORD *)v33 + 3);
            if ( v21 && v21 < *(_QWORD *)&SystemTimeAsFileTime )
            {
              GroupsForUser = -1073741421;
            }
            else if ( (*((_BYTE *)v33 + 280) & 1) != 0 )
            {
              GroupsForUser = -1073741710;
            }
            else
            {
              GroupsForUser = SamIAccountRestrictions(v32, 0, (char *)v33 + 160, (char *)v33 + 288, &v48, &v47);
              if ( GroupsForUser >= 0 )
              {
                v22 = v33;
                *((union _LARGE_INTEGER *)v33 + 5) = KerbGlobalWillNeverTime;
                IsAnyKdc = _KerberosSystemRole::IsAnyKdc(v22);
                v24 = &v41;
                if ( IsAnyKdc )
                  v24 = &v42;
                GroupsForUser = PAC_InitEx2(
                                  v33,
                                  v38,
                                  (struct _SID_AND_ATTRIBUTES_LIST *)&v50,
                                  *(void **)(v36 + 16),
                                  v24,
                                  &v41,
                                  (size_t)Size,
                                  v26,
                                  v27,
                                  v28,
                                  v29,
                                  v30,
                                  v31,
                                  &v37);
                if ( GroupsForUser < 0 )
                  v9 = v37;
                else
                  *a1 = v37;
              }
            }
            goto LABEL_40;
          }
          KerbTracerT::Log(1, "KerbCreatePacForKerbClient", 446, "Failed to duplicate KerbGlobalDomainName\n");
        }
        else
        {
          KerbTracerT::Log(1, "KerbCreatePacForKerbClient", 437, "Failed to duplicate KerbGlobalMachineName\n");
        }
        RtlReleaseResource(&KerberosGlobalResource);
      }
    }
  }
LABEL_40:
  KerbFreeString(&v41);
  KerbFreeString(&v42);
  KerbFreeString(&DestinationString);
  if ( v32 )
    SamrCloseHandle(&v32);
  if ( v34 )
    SamrCloseHandle(&v34);
  if ( v35 )
    SamrCloseHandle(&v35);
  if ( v38 )
    SamIFree_SAMPR_GET_GROUPS_BUFFER();
  SamIFreeSidAndAttributesList(&v50);
  if ( v33 )
    SamIFree_SAMPR_USER_INFO_BUFFER(v33, 21);
  if ( v36 )
    LsaIFree_LSAPR_POLICY_INFORMATION(5, v36);
  SamIFree_SAMPR_ULONG_ARRAY(&v43);
  SamIFree_SAMPR_ULONG_ARRAY(&v45);
  if ( v9 )
    KerbFree(v9);
  return (unsigned int)GroupsForUser;
}

```

## disassembly

```asm
0x1800be1c8  push    rbp
0x1800be1ca  push    rbx
0x1800be1cb  push    rsi
0x1800be1cc  push    rdi
0x1800be1cd  push    r12
0x1800be1cf  push    r13
0x1800be1d1  push    r14
0x1800be1d3  push    r15
0x1800be1d5  lea     rbp, [rsp-58h]
0x1800be1da  sub     rsp, 158h
0x1800be1e1  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x1800be1e8  xor     ebx, ebx
0x1800be1ea  xorps   xmm0, xmm0
0x1800be1ed  mov     [rbp+90h+var_100], rbx
0x1800be1f1  mov     r13, rcx
0x1800be1f4  mov     [rbp+90h+var_108], rbx
0x1800be1f8  lea     rcx, [rbp+90h+var_60]
0x1800be1fc  mov     [rbp+90h+var_110], rbx
0x1800be200  mov     rax, [rax+80h]
0x1800be207  mov     r14, r9
0x1800be20a  mov     r15, r8
0x1800be20d  mov     [rsp+190h+var_120], rbx
0x1800be212  mov     r12, rdx
0x1800be215  mov     [rbp+90h+var_F0], rbx
0x1800be219  movups  [rbp+90h+var_70], xmm0
0x1800be21d  mov     [rsp+190h+var_118], rbx
0x1800be222  mov     esi, ebx
0x1800be224  mov     [rbp+90h+var_F8], rbx
0x1800be228  mov     [rbp+90h+var_A0], rbx
0x1800be22c  mov     [rbp+90h+var_B0], rbx
0x1800be230  movups  [rbp+90h+var_60], xmm0
0x1800be234  mov     qword ptr [rbp+90h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x1800be238  movups  [rbp+90h+var_50], xmm0
0x1800be23c  mov     [rbp+90h+var_88], rbx
0x1800be240  mov     [rbp+90h+var_90], rbx
0x1800be244  mov     qword ptr [rbp+90h+var_D0.Length], rbx
0x1800be248  mov     qword ptr [rbp+90h+var_C0.Length], rbx
0x1800be24c  mov     qword ptr [rbp+90h+DestinationString.Length], rbx
0x1800be250  mov     [rbp+90h+DestinationString.Buffer], rbx
0x1800be254  mov     [rbp+90h+var_98], rbx
0x1800be258  mov     [rbp+90h+var_A8], rbx
0x1800be25c  mov     [rbp+90h+var_D0.Buffer], rbx
0x1800be260  mov     [rbp+90h+var_C0.Buffer], rbx
0x1800be264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be269  test    eax, eax
0x1800be26b  js      loc_1800BE65F
0x1800be271  cmp     byte ptr [rbp+90h+var_50], bl
0x1800be274  jnz     short loc_1800BE29C
0x1800be276  lea     r9, aKerbcreatepacf_0; "KerbCreatePacForKerbClient client has n"...
0x1800be27d  mov     r8d, 16Eh
0x1800be283  lea     rdx, aKerbcreatepacf; "KerbCreatePacForKerbClient"
0x1800be28a  lea     ecx, [rbx+1]
0x1800be28d  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800be292  mov     eax, 0C0000061h
0x1800be297  jmp     loc_1800BE65F
0x1800be29c  lea     rdx, [rbp+90h+var_100]
0x1800be2a0  mov     ecx, 5
0x1800be2a5  call    cs:__imp_LsaIQueryInformationPolicyTrusted
0x1800be2ab  mov     ebx, eax
0x1800be2ad  test    eax, eax
0x1800be2af  js      loc_1800BE5AA
0x1800be2b5  mov     edi, 1
0x1800be2ba  lea     rdx, [rbp+90h+var_108]
0x1800be2be  mov     r9b, dil
0x1800be2c1  xor     r8d, r8d
0x1800be2c4  xor     ecx, ecx
0x1800be2c6  call    cs:__imp_SamIConnect
0x1800be2cc  mov     ebx, eax
0x1800be2ce  test    eax, eax
0x1800be2d0  js      loc_1800BE5AA
0x1800be2d6  mov     r8, [rbp+90h+var_100]
0x1800be2da  lea     r9, [rbp+90h+var_110]
0x1800be2de  mov     rcx, [rbp+90h+var_108]
0x1800be2e2  xor     edx, edx
0x1800be2e4  mov     r8, [r8+10h]
0x1800be2e8  call    cs:__imp_SamrOpenDomain
0x1800be2ee  mov     ebx, eax
0x1800be2f0  test    eax, eax
0x1800be2f2  js      loc_1800BE5AA
0x1800be2f8  mov     dl, dil; Wait
0x1800be2fb  lea     rcx, ?KerberosGlobalResource@@3U_RTL_RESOURCE@@A; Resource
0x1800be302  call    cs:__imp_RtlAcquireResourceShared
0x1800be308  lea     rdx, ?KerbGlobalMachineName@@3U_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x1800be30f  lea     rcx, [rbp+90h+var_D0]; struct _UNICODE_STRING *
0x1800be313  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x1800be318  mov     ebx, eax
0x1800be31a  test    eax, eax
0x1800be31c  jns     short loc_1800BE32D
0x1800be31e  mov     r8d, 1B5h
0x1800be324  lea     r9, aFailedToDuplic; "Failed to duplicate KerbGlobalMachineNa"...
0x1800be32b  jmp     short loc_1800BE359
0x1800be32d  call    ?IsAnyKdc@_KerberosSystemRole@@QEAA_NXZ; _KerberosSystemRole::IsAnyKdc(void)
0x1800be332  test    al, al
0x1800be334  jz      short loc_1800BE379
0x1800be336  lea     rdx, ?KerbGlobalDomainName@@3U_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x1800be33d  lea     rcx, [rbp+90h+var_C0]; struct _UNICODE_STRING *
0x1800be341  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x1800be346  mov     ebx, eax
0x1800be348  test    eax, eax
0x1800be34a  jns     short loc_1800BE379
0x1800be34c  mov     r8d, 1BEh
0x1800be352  lea     r9, aFailedToDuplic_15; "Failed to duplicate KerbGlobalDomainNam"...
0x1800be359  lea     rdx, aKerbcreatepacf; "KerbCreatePacForKerbClient"
0x1800be360  mov     ecx, edi
0x1800be362  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800be367  lea     rcx, ?KerberosGlobalResource@@3U_RTL_RESOURCE@@A; Resource
0x1800be36e  call    cs:__imp_RtlReleaseResource
0x1800be374  jmp     loc_1800BE5AA
0x1800be379  lea     rcx, ?KerberosGlobalResource@@3U_RTL_RESOURCE@@A; Resource
0x1800be380  call    cs:__imp_RtlReleaseResource
0x1800be386  call    ?IsAnyKdc@_KerberosSystemRole@@QEAA_NXZ; _KerberosSystemRole::IsAnyKdc(void)
0x1800be38b  test    al, al
0x1800be38d  jz      short loc_1800BE3FC
0x1800be38f  xorps   xmm0, xmm0
0x1800be392  lea     rcx, [rbp+90h+var_80]
0x1800be396  mov     r9, r15
0x1800be399  mov     rdx, r12
0x1800be39c  movups  [rbp+90h+var_80], xmm0
0x1800be3a0  call    KerbBuildAltSecId
0x1800be3a5  test    eax, eax
0x1800be3a7  jz      short loc_1800BE3B7
0x1800be3a9  mov     ecx, eax; int
0x1800be3ab  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x1800be3b0  mov     ebx, eax
0x1800be3b2  jmp     loc_1800BE5AA
0x1800be3b7  mov     rcx, [rbp+90h+var_108]
0x1800be3bb  lea     rax, [rsp+190h+var_120]
0x1800be3c0  mov     [rsp+190h+Size], rax; Size
0x1800be3c5  lea     r8, [rbp+90h+var_80]
0x1800be3c9  lea     rax, [rbp+90h+var_70]
0x1800be3cd  mov     r9d, 3FEFCFh
0x1800be3d3  mov     [rsp+190h+var_168], rax
0x1800be3d8  mov     edx, 10h
0x1800be3dd  lea     rax, [rsp+190h+var_118]
0x1800be3e2  mov     [rsp+190h+var_170], rax
0x1800be3e7  call    cs:__imp_SamIGetUserLogonInformationEx
0x1800be3ed  lea     rcx, [rbp+90h+var_80]
0x1800be3f1  mov     ebx, eax
0x1800be3f3  call    KerbFreeString
0x1800be3f8  test    ebx, ebx
0x1800be3fa  js      short loc_1800BE407
0x1800be3fc  cmp     [rsp+190h+var_118], rsi
0x1800be401  jnz     loc_1800BE4D4
0x1800be407  test    r14, r14
0x1800be40a  jz      short loc_1800BE420
0x1800be40c  cmp     [r14+8], rsi
0x1800be410  jz      short loc_1800BE420
0x1800be412  mov     rdx, r14; struct _UNICODE_STRING *
0x1800be415  lea     rcx, [rbp+90h+DestinationString]; struct _UNICODE_STRING *
0x1800be419  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x1800be41e  jmp     short loc_1800BE42F
0x1800be420  mov     r8, r15; struct _UNICODE_STRING *
0x1800be423  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x1800be427  mov     rdx, r12; struct _KERB_INTERNAL_NAME *
0x1800be42a  call    ?KerbMapClientName@@YAJPEAU_UNICODE_STRING@@PEAU_KERB_INTERNAL_NAME@@0@Z; KerbMapClientName(_UNICODE_STRING *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *)
0x1800be42f  mov     ebx, eax
0x1800be431  test    eax, eax
0x1800be433  js      loc_1800BE5AA
0x1800be439  mov     rcx, [rbp+90h+var_110]
0x1800be43d  lea     rax, [rbp+90h+var_B0]
0x1800be441  lea     r9, [rbp+90h+var_A0]
0x1800be445  mov     [rsp+190h+var_170], rax
0x1800be44a  lea     r8, [rbp+90h+DestinationString]
0x1800be44e  mov     edx, edi
0x1800be450  call    cs:__imp_SamrLookupNamesInDomain
0x1800be456  mov     ebx, eax
0x1800be458  test    eax, eax
0x1800be45a  js      loc_1800BE5AA
0x1800be460  mov     rax, [rbp+90h+var_A8]
0x1800be464  mov     ecx, [rax]
0x1800be466  sub     ecx, edi
0x1800be468  test    ecx, 0FFFFFFF7h
0x1800be46e  jz      short loc_1800BE47A
0x1800be470  mov     ebx, 0C0000073h
0x1800be475  jmp     loc_1800BE5AA
0x1800be47a  mov     r8, [rbp+90h+var_98]
0x1800be47e  lea     r9, [rsp+190h+var_120]
0x1800be483  mov     rcx, [rbp+90h+var_110]
0x1800be487  xor     edx, edx
0x1800be489  mov     r8d, [r8]
0x1800be48c  call    cs:__imp_SamrOpenUser
0x1800be492  mov     ebx, eax
0x1800be494  test    eax, eax
0x1800be496  js      loc_1800BE5AA
0x1800be49c  mov     rcx, [rsp+190h+var_120]
0x1800be4a1  lea     r8, [rsp+190h+var_118]
0x1800be4a6  mov     edx, 15h
0x1800be4ab  call    cs:__imp_SamrQueryInformationUser
0x1800be4b1  mov     ebx, eax
0x1800be4b3  test    eax, eax
0x1800be4b5  js      loc_1800BE5AA
0x1800be4bb  mov     rcx, [rsp+190h+var_120]
0x1800be4c0  lea     rdx, [rbp+90h+var_F0]
0x1800be4c4  call    cs:__imp_SamrGetGroupsForUser
0x1800be4ca  mov     ebx, eax
0x1800be4cc  test    eax, eax
0x1800be4ce  js      loc_1800BE5AA
0x1800be4d4  lea     rcx, [rbp+90h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800be4d8  call    cs:__imp_GetSystemTimeAsFileTime
0x1800be4de  mov     r8, [rsp+190h+var_118]
0x1800be4e3  mov     rax, [r8+18h]
0x1800be4e7  test    rax, rax
0x1800be4ea  jz      short loc_1800BE4FC
0x1800be4ec  cmp     rax, qword ptr [rbp+90h+SystemTimeAsFileTime.dwLowDateTime]
0x1800be4f0  jge     short loc_1800BE4FC
0x1800be4f2  mov     ebx, 0C0000193h
0x1800be4f7  jmp     loc_1800BE5AA
0x1800be4fc  test    [r8+118h], dil
0x1800be503  jz      short loc_1800BE50F
0x1800be505  mov     ebx, 0C0000072h
0x1800be50a  jmp     loc_1800BE5AA
0x1800be50f  mov     rcx, [rsp+190h+var_120]
0x1800be514  lea     rax, [rbp+90h+var_90]
0x1800be518  mov     [rsp+190h+var_168], rax
0x1800be51d  lea     r9, [r8+120h]
0x1800be524  lea     rax, [rbp+90h+var_88]
0x1800be528  add     r8, 0A0h
0x1800be52f  xor     edx, edx
0x1800be531  mov     [rsp+190h+var_170], rax
0x1800be536  call    cs:__imp_SamIAccountRestrictions
0x1800be53c  mov     ebx, eax
0x1800be53e  test    eax, eax
0x1800be540  js      short loc_1800BE5AA
0x1800be542  mov     rcx, [rsp+190h+var_118]; this
0x1800be547  mov     rax, cs:?KerbGlobalWillNeverTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER KerbGlobalWillNeverTime
0x1800be54e  mov     [rcx+28h], rax
0x1800be552  call    ?IsAnyKdc@_KerberosSystemRole@@QEAA_NXZ; _KerberosSystemRole::IsAnyKdc(void)
0x1800be557  mov     r9, [rbp+90h+var_100]
0x1800be55b  lea     rdx, [rbp+90h+var_C0]
0x1800be55f  test    al, al
0x1800be561  lea     rcx, [rbp+90h+var_D0]
0x1800be565  lea     rax, [rbp+90h+var_F8]
0x1800be569  mov     [rsp+190h+var_128], rax; struct _PACTYPE **
0x1800be56e  lea     r8, [rbp+90h+var_70]; struct _SID_AND_ATTRIBUTES_LIST *
0x1800be572  mov     r9, [r9+10h]; void *
0x1800be576  lea     rax, [rbp+90h+var_D0]
0x1800be57a  cmovnz  rcx, rdx
0x1800be57e  mov     [rsp+190h+var_168], rax; struct _UNICODE_STRING *
0x1800be583  mov     rdx, [rbp+90h+var_F0]; struct _SAMPR_GET_GROUPS_BUFFER *
0x1800be587  mov     [rsp+190h+var_170], rcx; struct _UNICODE_STRING *
0x1800be58c  mov     rcx, [rsp+190h+var_118]; struct _SAMPR_USER_ALL_INFORMATION *
0x1800be591  call    ?PAC_InitEx2@@YAJPEAU_SAMPR_USER_ALL_INFORMATION@@PEAU_SAMPR_GET_GROUPS_BUFFER@@PEAU_SID_AND_ATTRIBUTES_LIST@@PEAXPEAU_UNICODE_STRING@@4KKKPEAPEAU_PAC_INFO_BUFFER@@PEAT_LARGE_INTEGER@@6PEAU_LSA_LAST_INTER_LOGON_INFO@@PEAPEAU_PACTYPE@@@Z; PAC_InitEx2(_SAMPR_USER_ALL_INFORMATION *,_SAMPR_GET_GROUPS_BUFFER *,_SID_AND_ATTRIBUTES_LIST *,void *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong,ulong,_PAC_INFO_BUFFER * *,_LARGE_INTEGER *,_LARGE_INTEGER *,_LSA_LAST_INTER_LOGON_INFO *,_PACTYPE * *)
0x1800be596  mov     ebx, eax
0x1800be598  test    eax, eax
0x1800be59a  js      short loc_1800BE5A6
0x1800be59c  mov     rax, [rbp+90h+var_F8]
0x1800be5a0  mov     [r13+0], rax
0x1800be5a4  jmp     short loc_1800BE5AA
0x1800be5a6  mov     rsi, [rbp+90h+var_F8]
0x1800be5aa  lea     rcx, [rbp+90h+var_D0]
0x1800be5ae  call    KerbFreeString
0x1800be5b3  lea     rcx, [rbp+90h+var_C0]
0x1800be5b7  call    KerbFreeString
0x1800be5bc  lea     rcx, [rbp+90h+DestinationString]
0x1800be5c0  call    KerbFreeString
0x1800be5c5  cmp     [rsp+190h+var_120], 0
0x1800be5cb  jz      short loc_1800BE5D8
0x1800be5cd  lea     rcx, [rsp+190h+var_120]
0x1800be5d2  call    cs:__imp_SamrCloseHandle
0x1800be5d8  cmp     [rbp+90h+var_110], 0
0x1800be5dd  jz      short loc_1800BE5E9
0x1800be5df  lea     rcx, [rbp+90h+var_110]
0x1800be5e3  call    cs:__imp_SamrCloseHandle
0x1800be5e9  cmp     [rbp+90h+var_108], 0
0x1800be5ee  jz      short loc_1800BE5FA
0x1800be5f0  lea     rcx, [rbp+90h+var_108]
0x1800be5f4  call    cs:__imp_SamrCloseHandle
0x1800be5fa  mov     rcx, [rbp+90h+var_F0]
0x1800be5fe  test    rcx, rcx
0x1800be601  jz      short loc_1800BE609
0x1800be603  call    cs:__imp_SamIFree_SAMPR_GET_GROUPS_BUFFER
0x1800be609  lea     rcx, [rbp+90h+var_70]
0x1800be60d  call    cs:__imp_SamIFreeSidAndAttributesList
0x1800be613  mov     rcx, [rsp+190h+var_118]
0x1800be618  test    rcx, rcx
0x1800be61b  jz      short loc_1800BE628
0x1800be61d  mov     edx, 15h
0x1800be622  call    cs:__imp_SamIFree_SAMPR_USER_INFO_BUFFER
0x1800be628  mov     rdx, [rbp+90h+var_100]
0x1800be62c  test    rdx, rdx
0x1800be62f  jz      short loc_1800BE63C
0x1800be631  mov     ecx, 5
0x1800be636  call    cs:__imp_LsaIFree_LSAPR_POLICY_INFORMATION
0x1800be63c  lea     rcx, [rbp+90h+var_B0]
0x1800be640  call    cs:__imp_SamIFree_SAMPR_ULONG_ARRAY
0x1800be646  lea     rcx, [rbp+90h+var_A0]
0x1800be64a  call    cs:__imp_SamIFree_SAMPR_ULONG_ARRAY
0x1800be650  test    rsi, rsi
0x1800be653  jz      short loc_1800BE65D
0x1800be655  mov     rcx, rsi
0x1800be658  call    KerbFree
0x1800be65d  mov     eax, ebx
0x1800be65f  add     rsp, 158h
0x1800be666  pop     r15
0x1800be668  pop     r14
0x1800be66a  pop     r13
0x1800be66c  pop     r12
0x1800be66e  pop     rdi
0x1800be66f  pop     rsi
0x1800be670  pop     rbx
  ... truncated ...
```
