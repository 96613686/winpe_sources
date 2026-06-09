# LsapGetRegistration(_LSA_REGISTRATION_INFO * *)

- ea: `0x180147ea4`
- end: `0x180148586`
- name: `?LsapGetRegistration@@YAJPEAPEAU_LSA_REGISTRATION_INFO@@@Z`
- size: `1762`
- prototype: `__int64 __fastcall(struct _LSA_REGISTRATION_INFO **)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180149b60`

## callees

- `0x18000c300`
- `0x180011278`
- `0x180016f70`
- `0x180097c3c`
- `0x1800ada18`
- `0x1800b86d0`
- `0x18014770c`
- `0x180147750`
- `0x1801478a4`
- `0x180147b10`
- `0x180147bbc`
- `0x180147c34`
- `0x180147cbc`
- `0x180147d40`
- `0x180147ea4`
- `0x180148d58`
- `0x1801490a8`
- `0x180149490`
- `0x18014962c`
- `0x180149a84`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180147f4c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18014814e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180148503`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180147f4c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18014814e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180148503`
- `ntdll!NtClose` at `0x180148346`
- `ntdll!NtClose` at `0x18014835b`
- `ntdll!NtClose` at `0x180148346`
- `ntdll!NtClose` at `0x18014835b`
- `ntdll!NtSetInformationThread` at `0x1801482f6`
- `ntdll!NtSetInformationThread` at `0x1801482f6`
- `ntdll!RtlCreateUnicodeString` at `0x180148173`
- `ntdll!RtlCreateUnicodeString` at `0x180148197`
- `ntdll!RtlCreateUnicodeString` at `0x1801481b7`
- `ntdll!RtlCreateUnicodeString` at `0x1801481d7`
- `ntdll!RtlCreateUnicodeString` at `0x180148173`
- `ntdll!RtlCreateUnicodeString` at `0x180148197`
- `ntdll!RtlCreateUnicodeString` at `0x1801481b7`
- `ntdll!RtlCreateUnicodeString` at `0x1801481d7`

## string_xrefs

- `0x180147fea`: `LsapOpenRegUsersKey`
- `0x18014800a`: `LsapOpenRegUsersKey`
- `0x180147ffc`: `\Registry\USER`
- `0x1801482c5`: `LsapRevertImpersonationHelper`
- `0x180148304`: `LsapRevertImpersonationHelper`

## pseudocode

```c
__int64 __fastcall LsapGetRegistration(struct _LSA_REGISTRATION_INFO **a1)
{
  unsigned int v2; // r13d
  struct _RTL_BALANCED_NODE *v3; // rdi
  struct _RTL_BALANCED_NODE *v4; // r14
  __int64 v5; // rbx
  struct _LSA_REGISTRATION_INFO *v6; // rax
  __int64 v7; // rcx
  LsaHandleCache *v8; // rcx
  __int64 v9; // r15
  unsigned int i; // eax
  const unsigned __int16 **v11; // r14
  __int64 v12; // rsi
  int UserHive; // eax
  int v14; // edi
  struct _UNICODE_STRING *v15; // rax
  struct _RTL_BALANCED_NODE *v16; // rdx
  HLOCAL *v17; // rsi
  void *v18; // rdx
  __int64 j; // rsi
  struct _RTL_BALANCED_NODE *v20; // rcx
  __int64 v21; // rdi
  LsaHandleCache *v23; // rcx
  PCWSTR ParentValue; // r9
  __int64 v25; // rdx
  HLOCAL *v26; // rsi
  __int64 v27; // r8
  unsigned int v28; // [rsp+20h] [rbp-89h] BYREF
  __int64 v29; // [rsp+28h] [rbp-81h]
  struct _RTL_BALANCED_NODE *v30; // [rsp+30h] [rbp-79h] BYREF
  HANDLE v31; // [rsp+38h] [rbp-71h] BYREF
  const unsigned __int16 **ThreadInformation; // [rsp+40h] [rbp-69h] BYREF
  HLOCAL *v33; // [rsp+48h] [rbp-61h]
  HANDLE Handle; // [rsp+50h] [rbp-59h] BYREF
  unsigned __int16 v35[40]; // [rsp+60h] [rbp-49h] BYREF

  v33 = (HLOCAL *)a1;
  v2 = 0;
  ThreadInformation = 0;
  v3 = 0;
  v28 = 0;
  Handle = 0;
  v30 = 0;
  v4 = 0;
  v31 = 0;
  DBG_TRACE_ENTER("LsapGetRegistration");
  *a1 = 0;
  LODWORD(v5) = LsapGenerateGUIDString(v35);
  if ( (int)v5 < 0 )
    goto LABEL_46;
  LODWORD(v5) = LsapGetUserProfileList((struct _LSAPR_USER_PROFILE_ENTRY **)&ThreadInformation, &v28);
  if ( (int)v5 < 0 )
    goto LABEL_8;
  LODWORD(v5) = LsapEnableProcessPrivileges(&Handle);
  if ( (int)v5 < 0 )
    goto LABEL_8;
  v6 = (struct _LSA_REGISTRATION_INFO *)LocalAlloc(0x40u, 0x10u);
  *a1 = v6;
  if ( !v6 )
  {
    LODWORD(v5) = -1073741801;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_9fb76bc17a8937cf5b52328af0a6340a_Traceguids);
LABEL_8:
    v2 = v28;
    goto LABEL_46;
  }
  v2 = v28;
  v7 = 8LL * v28;
  *v6 = 0;
  v29 = LsapAllocate(v7);
  v4 = (struct _RTL_BALANCED_NODE *)v29;
  if ( !v29 )
  {
    LODWORD(v5) = -1073741801;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_9fb76bc17a8937cf5b52328af0a6340a_Traceguids, v2);
    goto LABEL_46;
  }
  DBG_TRACE_ENTER("LsapOpenRegUsersKey");
  v5 = (unsigned int)LsapOpenRegSubKey(0, L"\\Registry\\USER", &v31);
  DBG_TRACE_EXIT("LsapOpenRegUsersKey", v5);
  if ( (int)v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_9fb76bc17a8937cf5b52328af0a6340a_Traceguids);
    goto LABEL_46;
  }
  v8 = WPP_GLOBAL_Control;
  v9 = 0;
  for ( i = 0; ; i = v28 + 1 )
  {
    v28 = i;
    if ( i >= v2 )
      break;
    v11 = ThreadInformation;
    v12 = 2LL * i;
    LODWORD(v5) = LsapReadUserRegistrationInfo(
                    v31,
                    ThreadInformation[2 * i],
                    (struct _LSAPR_REGISTRY_REGISTRATION_INFO **)&v30);
    if ( (int)v5 < 0 )
    {
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_9fb76bc17a8937cf5b52328af0a6340a_Traceguids, v11[v12]);
      if ( LsapLoadUserHive(v31, v11[v12 + 1], v35) < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_9fb76bc17a8937cf5b52328af0a6340a_Traceguids, v11[v12]);
          v8 = WPP_GLOBAL_Control;
        }
        v3 = v30;
        LODWORD(v5) = 0;
        goto LABEL_38;
      }
      LODWORD(v5) = LsapReadUserRegistrationInfo(v31, v35, (struct _LSAPR_REGISTRY_REGISTRATION_INFO **)&v30);
      UserHive = LsapUnLoadUserHive(v31, v35);
      v14 = UserHive;
      if ( (int)v5 < 0 )
        goto LABEL_44;
      if ( UserHive < 0 )
      {
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_9fb76bc17a8937cf5b52328af0a6340a_Traceguids, v11[v12]);
        }
        LODWORD(v5) = v14;
LABEL_44:
        v3 = v30;
LABEL_45:
        v4 = (struct _RTL_BALANCED_NODE *)v29;
        goto LABEL_46;
      }
    }
    v3 = v30;
    if ( !v30 )
    {
      v8 = WPP_GLOBAL_Control;
LABEL_38:
      v4 = (struct _RTL_BALANCED_NODE *)v29;
      continue;
    }
    v15 = (struct _UNICODE_STRING *)LocalAlloc(0x40u, 0x48u);
    *(_QWORD *)(v29 + 8 * v9) = v15;
    if ( !v15 )
    {
      LODWORD(v5) = -1073741801;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_9fb76bc17a8937cf5b52328af0a6340a_Traceguids);
      goto LABEL_45;
    }
    if ( !RtlCreateUnicodeString(v15, v11[v12]) )
    {
      LODWORD(v5) = -1073741801;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_9fb76bc17a8937cf5b52328af0a6340a_Traceguids, v11[v12]);
      goto LABEL_45;
    }
    v4 = (struct _RTL_BALANCED_NODE *)v29;
    if ( !RtlCreateUnicodeString((PUNICODE_STRING)(*(_QWORD *)(v29 + 8 * v9) + 16LL), (PCWSTR)v3->Children[0]) )
    {
      LODWORD(v5) = -1073741801;
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        ParentValue = (PCWSTR)v3->Children[0];
        v25 = 23;
        goto LABEL_74;
      }
LABEL_46:
      v17 = v33;
      if ( *v33 )
      {
        LsapFreeRegistrationInfo(*v33);
        *v17 = 0;
      }
      goto LABEL_48;
    }
    if ( !RtlCreateUnicodeString((PUNICODE_STRING)&v4->Children[v9][1].Right, (PCWSTR)v3->Children[1]) )
    {
      LODWORD(v5) = -1073741801;
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_46;
      ParentValue = (PCWSTR)v3->Children[1];
      v25 = 24;
      goto LABEL_74;
    }
    if ( !RtlCreateUnicodeString((PUNICODE_STRING)&v4->Children[v9][2], (PCWSTR)v3->ParentValue) )
    {
      LODWORD(v5) = -1073741801;
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_46;
      ParentValue = (PCWSTR)v3->ParentValue;
      v25 = 25;
LABEL_74:
      WPP_SF_S(*((_QWORD *)v23 + 2), v25, WPP_9fb76bc17a8937cf5b52328af0a6340a_Traceguids, ParentValue);
      goto LABEL_46;
    }
    v16 = v4->Children[v9];
    v9 = (unsigned int)(v9 + 1);
    v16[2].ParentValue = (ULONG_PTR)v3[1].Children[0];
    LsapFreeRegistryRegistrationInfo(v3);
    v8 = WPP_GLOBAL_Control;
    v3 = 0;
    v30 = 0;
  }
  if ( (_DWORD)v9 )
  {
    if ( v8 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)v8 + 2), 26, WPP_9fb76bc17a8937cf5b52328af0a6340a_Traceguids, (unsigned int)v9);
    v26 = v33;
    *(_DWORD *)*v33 = v9;
    *((_QWORD *)*v26 + 1) = LocalAlloc(0x40u, 8LL * (unsigned int)v9);
    if ( !*((_QWORD *)*v26 + 1) )
    {
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          WPP_9fb76bc17a8937cf5b52328af0a6340a_Traceguids,
          (unsigned int)v9);
      LODWORD(v5) = -1073741801;
      goto LABEL_46;
    }
    v27 = 0;
    do
    {
      *(_QWORD *)(*((_QWORD *)*v26 + 1) + 8 * v27) = v4->Children[v27];
      v4->Children[v27] = 0;
      v27 = (unsigned int)(v27 + 1);
    }
    while ( (unsigned int)v27 < (unsigned int)v9 );
  }
LABEL_48:
  LsapFreeUserList((struct _RTL_BALANCED_NODE *)ThreadInformation, v2);
  if ( v4 )
  {
    for ( j = 0; (unsigned int)j < v2; j = (unsigned int)(j + 1) )
    {
      v20 = v4->Children[j];
      if ( v20 )
        LsapFreeUserRegistrationInfo(v20);
    }
    LsapSubProv_FreeRoutine(v4, v18);
  }
  LsapFreeRegistryRegistrationInfo(v3);
  if ( Handle )
  {
    ThreadInformation = 0;
    DBG_TRACE_ENTER("LsapRevertImpersonationHelper");
    ThreadInformation = 0;
    v21 = (unsigned int)NtSetInformationThread(
                          (HANDLE)0xFFFFFFFFFFFFFFFELL,
                          ThreadImpersonationToken,
                          &ThreadInformation,
                          8u);
    DBG_TRACE_EXIT("LsapRevertImpersonationHelper", v21);
    if ( (int)v21 < 0 )
    {
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_9fb76bc17a8937cf5b52328af0a6340a_Traceguids);
      if ( (int)v5 >= 0 )
        LODWORD(v5) = v21;
    }
    NtClose(Handle);
  }
  if ( v31 )
    NtClose(v31);
  DBG_TRACE_EXIT("LsapGetRegistration", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180147ea4  push    rbp
0x180147ea6  push    rbx
0x180147ea7  push    rsi
0x180147ea8  push    rdi
0x180147ea9  push    r12
0x180147eab  push    r13
0x180147ead  push    r14
0x180147eaf  push    r15
0x180147eb1  lea     rbp, [rsp-1Fh]
0x180147eb6  sub     rsp, 0C8h
0x180147ebd  mov     rax, cs:__security_cookie
0x180147ec4  xor     rax, rsp
0x180147ec7  mov     [rbp+57h+var_50], rax
0x180147ecb  mov     rsi, rcx
0x180147ece  mov     [rbp+57h+var_B8], rcx
0x180147ed2  xor     r13d, r13d
0x180147ed5  mov     [rbp+57h+ThreadInformation], 0
0x180147edd  xor     edi, edi
0x180147edf  mov     [rsp+100h+var_E0], r13d
0x180147ee4  lea     rcx, aLsapgetregistr; "LsapGetRegistration"
0x180147eeb  mov     [rbp+57h+Handle], r13
0x180147eef  mov     [rbp+57h+var_D0], rdi
0x180147ef3  xor     r14d, r14d
0x180147ef6  mov     [rbp+57h+var_C8], rdi
0x180147efa  call    DBG_TRACE_ENTER
0x180147eff  lea     rcx, [rbp+57h+var_A0]; unsigned __int16 *
0x180147f03  mov     [rsi], rdi
0x180147f06  call    ?LsapGenerateGUIDString@@YAJPEAG@Z; LsapGenerateGUIDString(ushort *)
0x180147f0b  lea     r12, WPP_GLOBAL_Control
0x180147f12  mov     ebx, eax
0x180147f14  lea     r15, WPP_9fb76bc17a8937cf5b52328af0a6340a_Traceguids
0x180147f1b  test    eax, eax
0x180147f1d  js      loc_180148265
0x180147f23  lea     rdx, [rsp+100h+var_E0]; unsigned int *
0x180147f28  lea     rcx, [rbp+57h+ThreadInformation]; struct _LSAPR_USER_PROFILE_ENTRY **
0x180147f2c  call    ?LsapGetUserProfileList@@YAJPEAPEAU_LSAPR_USER_PROFILE_ENTRY@@PEAK@Z; LsapGetUserProfileList(_LSAPR_USER_PROFILE_ENTRY * *,ulong *)
0x180147f31  mov     ebx, eax
0x180147f33  test    eax, eax
0x180147f35  js      short loc_180147F86
0x180147f37  lea     rcx, [rbp+57h+Handle]; NewTokenHandle
0x180147f3b  call    ?LsapEnableProcessPrivileges@@YAJPEAPEAX@Z; LsapEnableProcessPrivileges(void * *)
0x180147f40  mov     ebx, eax
0x180147f42  test    eax, eax
0x180147f44  js      short loc_180147F86
0x180147f46  lea     edx, [rdi+10h]; uBytes
0x180147f49  lea     ecx, [rdi+40h]; uFlags
0x180147f4c  call    cs:__imp_LocalAlloc
0x180147f53  nop     dword ptr [rax+rax+00h]
0x180147f58  mov     [rsi], rax
0x180147f5b  test    rax, rax
0x180147f5e  jnz     short loc_180147F90
0x180147f60  mov     ebx, 0C0000017h
0x180147f65  mov     rcx, cs:WPP_GLOBAL_Control
0x180147f6c  cmp     rcx, r12
0x180147f6f  jz      short loc_180147F86
0x180147f71  test    byte ptr [rcx+1Ch], 1
0x180147f75  jz      short loc_180147F86
0x180147f77  mov     rcx, [rcx+10h]
0x180147f7b  lea     edx, [rdi+0Fh]
0x180147f7e  mov     r8, r15
0x180147f81  call    WPP_SF_
0x180147f86  mov     r13d, [rsp+100h+var_E0]
0x180147f8b  jmp     loc_180148265
0x180147f90  mov     r13d, [rsp+100h+var_E0]
0x180147f95  xorps   xmm0, xmm0
0x180147f98  mov     ecx, r13d
0x180147f9b  shl     rcx, 3
0x180147f9f  movups  xmmword ptr [rax], xmm0
0x180147fa2  call    LsapAllocate
0x180147fa7  mov     [rsp+100h+var_D8], rax
0x180147fac  mov     r14, rax
0x180147faf  test    rax, rax
0x180147fb2  jnz     short loc_180147FEA
0x180147fb4  mov     ebx, 0C0000017h
0x180147fb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180147fc0  cmp     rcx, r12
0x180147fc3  jz      loc_180148265
0x180147fc9  test    byte ptr [rcx+1Ch], 1
0x180147fcd  jz      loc_180148265
0x180147fd3  mov     rcx, [rcx+10h]
0x180147fd7  lea     edx, [rax+10h]
0x180147fda  mov     r9d, r13d
0x180147fdd  mov     r8, r15
0x180147fe0  call    WPP_SF_d
0x180147fe5  jmp     loc_180148265
0x180147fea  lea     rcx, aLsapopenreguse; "LsapOpenRegUsersKey"
0x180147ff1  call    DBG_TRACE_ENTER
0x180147ff6  lea     r8, [rbp+57h+var_C8]; void **
0x180147ffa  xor     ecx, ecx; void *
0x180147ffc  lea     rdx, aRegistryUser; "\\Registry\\USER"
0x180148003  call    ?LsapOpenRegSubKey@@YAJPEAXPEBGPEAPEAX@Z; LsapOpenRegSubKey(void *,ushort const *,void * *)
0x180148008  mov     edx, eax
0x18014800a  lea     rcx, aLsapopenreguse; "LsapOpenRegUsersKey"
0x180148011  mov     ebx, eax
0x180148013  call    DBG_TRACE_EXIT
0x180148018  test    ebx, ebx
0x18014801a  jns     short loc_18014804C
0x18014801c  mov     rcx, cs:WPP_GLOBAL_Control
0x180148023  cmp     rcx, r12
0x180148026  jz      loc_180148265
0x18014802c  test    byte ptr [rcx+1Ch], 1
0x180148030  jz      loc_180148265
0x180148036  mov     rcx, [rcx+10h]
0x18014803a  mov     edx, 11h
0x18014803f  mov     r8, r15
0x180148042  call    WPP_SF_
0x180148047  jmp     loc_180148265
0x18014804c  mov     rcx, cs:WPP_GLOBAL_Control
0x180148053  xor     r15d, r15d
0x180148056  xor     eax, eax
0x180148058  mov     [rsp+100h+var_E0], eax
0x18014805c  cmp     eax, r13d
0x18014805f  jnb     loc_1801484C1
0x180148065  mov     r14, [rbp+57h+ThreadInformation]
0x180148069  lea     r8, [rbp+57h+var_D0]; struct _LSAPR_REGISTRY_REGISTRATION_INFO **
0x18014806d  mov     rcx, [rbp+57h+var_C8]; void *
0x180148071  mov     esi, eax
0x180148073  add     rsi, rsi
0x180148076  mov     rdx, [r14+rsi*8]; unsigned __int16 *
0x18014807a  call    ?LsapReadUserRegistrationInfo@@YAJPEAXPEBGPEAPEAU_LSAPR_REGISTRY_REGISTRATION_INFO@@@Z; LsapReadUserRegistrationInfo(void *,ushort const *,_LSAPR_REGISTRY_REGISTRATION_INFO * *)
0x18014807f  mov     ebx, eax
0x180148081  test    eax, eax
0x180148083  jns     loc_180148139
0x180148089  mov     rcx, cs:WPP_GLOBAL_Control
0x180148090  cmp     rcx, r12
0x180148093  jz      short loc_1801480B4
0x180148095  test    byte ptr [rcx+1Ch], 4
0x180148099  jz      short loc_1801480B4
0x18014809b  mov     r9, [r14+rsi*8]
0x18014809f  lea     r8, WPP_9fb76bc17a8937cf5b52328af0a6340a_Traceguids
0x1801480a6  mov     rcx, [rcx+10h]
0x1801480aa  mov     edx, 12h
0x1801480af  call    WPP_SF_S
0x1801480b4  mov     rdx, [r14+rsi*8+8]; unsigned __int16 *
0x1801480b9  lea     r8, [rbp+57h+var_A0]; unsigned __int16 *
0x1801480bd  mov     rcx, [rbp+57h+var_C8]; void *
0x1801480c1  call    ?LsapLoadUserHive@@YAJPEAXPEBG1@Z; LsapLoadUserHive(void *,ushort const *,ushort const *)
0x1801480c6  test    eax, eax
0x1801480c8  jns     short loc_180148107
0x1801480ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1801480d1  cmp     rcx, r12
0x1801480d4  jz      short loc_1801480FC
0x1801480d6  test    byte ptr [rcx+1Ch], 1
0x1801480da  jz      short loc_1801480FC
0x1801480dc  mov     r9, [r14+rsi*8]
0x1801480e0  lea     r8, WPP_9fb76bc17a8937cf5b52328af0a6340a_Traceguids
0x1801480e7  mov     rcx, [rcx+10h]
0x1801480eb  mov     edx, 13h
0x1801480f0  call    WPP_SF_S
0x1801480f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1801480fc  mov     rdi, [rbp+57h+var_D0]
0x180148100  xor     ebx, ebx
0x180148102  jmp     loc_18014821F
0x180148107  mov     rcx, [rbp+57h+var_C8]; void *
0x18014810b  lea     r8, [rbp+57h+var_D0]; struct _LSAPR_REGISTRY_REGISTRATION_INFO **
0x18014810f  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 *
0x180148113  call    ?LsapReadUserRegistrationInfo@@YAJPEAXPEBGPEAPEAU_LSAPR_REGISTRY_REGISTRATION_INFO@@@Z; LsapReadUserRegistrationInfo(void *,ushort const *,_LSAPR_REGISTRY_REGISTRATION_INFO * *)
0x180148118  mov     rcx, [rbp+57h+var_C8]; void *
0x18014811c  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 *
0x180148120  mov     ebx, eax
0x180148122  call    ?LsapUnLoadUserHive@@YAJPEAXPEBG@Z; LsapUnLoadUserHive(void *,ushort const *)
0x180148127  mov     edi, eax
0x180148129  test    ebx, ebx
0x18014812b  js      loc_18014825C
0x180148131  test    eax, eax
0x180148133  js      loc_18014822F
0x180148139  mov     rdi, [rbp+57h+var_D0]
0x18014813d  test    rdi, rdi
0x180148140  jz      loc_180148218
0x180148146  mov     edx, 48h ; 'H'; uBytes
0x18014814b  lea     ecx, [rdx-8]; uFlags
0x18014814e  call    cs:__imp_LocalAlloc
0x180148155  nop     dword ptr [rax+rax+00h]
0x18014815a  mov     rcx, [rsp+100h+var_D8]
0x18014815f  mov     [rcx+r15*8], rax
0x180148163  test    rax, rax
0x180148166  jz      loc_180148481
0x18014816c  mov     rdx, [r14+rsi*8]; SourceString
0x180148170  mov     rcx, rax; DestinationString
0x180148173  call    cs:__imp_RtlCreateUnicodeString
0x18014817a  nop     dword ptr [rax+rax+00h]
0x18014817f  test    al, al
0x180148181  jz      loc_18014843D
0x180148187  mov     r14, [rsp+100h+var_D8]
0x18014818c  mov     rdx, [rdi]; SourceString
0x18014818f  mov     rcx, [r14+r15*8]
0x180148193  add     rcx, 10h; DestinationString
0x180148197  call    cs:__imp_RtlCreateUnicodeString
0x18014819e  nop     dword ptr [rax+rax+00h]
0x1801481a3  test    al, al
0x1801481a5  jz      loc_1801483FA
0x1801481ab  mov     rcx, [r14+r15*8]
0x1801481af  mov     rdx, [rdi+8]; SourceString
0x1801481b3  add     rcx, 20h ; ' '; DestinationString
0x1801481b7  call    cs:__imp_RtlCreateUnicodeString
0x1801481be  nop     dword ptr [rax+rax+00h]
0x1801481c3  test    al, al
0x1801481c5  jz      loc_1801483C9
0x1801481cb  mov     rcx, [r14+r15*8]
0x1801481cf  mov     rdx, [rdi+10h]; SourceString
0x1801481d3  add     rcx, 30h ; '0'; DestinationString
0x1801481d7  call    cs:__imp_RtlCreateUnicodeString
0x1801481de  nop     dword ptr [rax+rax+00h]
0x1801481e3  test    al, al
0x1801481e5  jz      loc_180148398
0x1801481eb  mov     rdx, [r14+r15*8]
0x1801481ef  mov     rcx, rdi; struct _RTL_BALANCED_NODE *
0x1801481f2  mov     rax, [rdi+18h]
0x1801481f6  inc     r15d
0x1801481f9  mov     [rdx+40h], rax
0x1801481fd  call    ?LsapFreeRegistryRegistrationInfo@@YAXPEAU_LSAPR_REGISTRY_REGISTRATION_INFO@@@Z; LsapFreeRegistryRegistrationInfo(_LSAPR_REGISTRY_REGISTRATION_INFO *)
0x180148202  mov     rcx, cs:WPP_GLOBAL_Control
0x180148209  lea     r12, WPP_GLOBAL_Control
0x180148210  xor     edi, edi
0x180148212  mov     [rbp+57h+var_D0], rdi
0x180148216  jmp     short loc_180148224
0x180148218  mov     rcx, cs:WPP_GLOBAL_Control
0x18014821f  mov     r14, [rsp+100h+var_D8]
0x180148224  mov     eax, [rsp+100h+var_E0]
0x180148228  inc     eax
0x18014822a  jmp     loc_180148058
0x18014822f  mov     rcx, cs:WPP_GLOBAL_Control
0x180148236  cmp     rcx, r12
0x180148239  jz      short loc_18014825A
0x18014823b  test    byte ptr [rcx+1Ch], 1
0x18014823f  jz      short loc_18014825A
0x180148241  mov     r9, [r14+rsi*8]
0x180148245  lea     r8, WPP_9fb76bc17a8937cf5b52328af0a6340a_Traceguids
0x18014824c  mov     rcx, [rcx+10h]
0x180148250  mov     edx, 14h
0x180148255  call    WPP_SF_S
0x18014825a  mov     ebx, edi
0x18014825c  mov     rdi, [rbp+57h+var_D0]
0x180148260  mov     r14, [rsp+100h+var_D8]
0x180148265  mov     rsi, [rbp+57h+var_B8]
0x180148269  mov     rcx, [rsi]; hMem
0x18014826c  test    rcx, rcx
0x18014826f  jz      short loc_18014827D
0x180148271  call    ?LsapFreeRegistrationInfo@@YAXPEAU_LSA_REGISTRATION_INFO@@@Z; LsapFreeRegistrationInfo(_LSA_REGISTRATION_INFO *)
0x180148276  mov     qword ptr [rsi], 0
0x18014827d  mov     rcx, [rbp+57h+ThreadInformation]; struct _RTL_BALANCED_NODE *
0x180148281  mov     edx, r13d; unsigned int
0x180148284  call    ?LsapFreeUserList@@YAXPEAU_LSAPR_USER_PROFILE_ENTRY@@K@Z; LsapFreeUserList(_LSAPR_USER_PROFILE_ENTRY *,ulong)
0x180148289  test    r14, r14
0x18014828c  jz      short loc_1801482B2
0x18014828e  xor     esi, esi
0x180148290  test    r13d, r13d
0x180148293  jz      short loc_1801482AA
0x180148295  mov     rcx, [r14+rsi*8]; hMem
0x180148299  test    rcx, rcx
0x18014829c  jz      short loc_1801482A3
0x18014829e  call    ?LsapFreeUserRegistrationInfo@@YAXPEAU_LSA_USER_REGISTRATION_INFO@@@Z; LsapFreeUserRegistrationInfo(_LSA_USER_REGISTRATION_INFO *)
0x1801482a3  inc     esi
0x1801482a5  cmp     esi, r13d
0x1801482a8  jb      short loc_180148295
0x1801482aa  mov     rcx, r14; struct _RTL_BALANCED_NODE *
0x1801482ad  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1801482b2  mov     rcx, rdi; struct _RTL_BALANCED_NODE *
0x1801482b5  call    ?LsapFreeRegistryRegistrationInfo@@YAXPEAU_LSAPR_REGISTRY_REGISTRATION_INFO@@@Z; LsapFreeRegistryRegistrationInfo(_LSAPR_REGISTRY_REGISTRATION_INFO *)
0x1801482ba  cmp     [rbp+57h+Handle], 0
0x1801482bf  jz      loc_180148352
0x1801482c5  lea     rcx, aLsaprevertimpe; "LsapRevertImpersonationHelper"
0x1801482cc  mov     [rbp+57h+ThreadInformation], 0
0x1801482d4  call    DBG_TRACE_ENTER
0x1801482d9  mov     r9d, 8; ThreadInformationLength
0x1801482df  mov     [rbp+57h+ThreadInformation], 0
0x1801482e7  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x1801482eb  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1801482f2  lea     edx, [r9-3]; ThreadInformationClass
0x1801482f6  call    cs:__imp_NtSetInformationThread
0x1801482fd  nop     dword ptr [rax+rax+00h]
0x180148302  mov     edx, eax
0x180148304  lea     rcx, aLsaprevertimpe; "LsapRevertImpersonationHelper"
0x18014830b  mov     edi, eax
0x18014830d  call    DBG_TRACE_EXIT
0x180148312  test    edi, edi
0x180148314  jns     short loc_180148342
0x180148316  mov     rcx, cs:WPP_GLOBAL_Control
0x18014831d  cmp     rcx, r12
0x180148320  jz      short loc_18014833D
0x180148322  test    byte ptr [rcx+1Ch], 1
0x180148326  jz      short loc_18014833D
0x180148328  mov     rcx, [rcx+10h]
0x18014832c  lea     r8, WPP_9fb76bc17a8937cf5b52328af0a6340a_Traceguids
0x180148333  mov     edx, 1Ch
0x180148338  call    WPP_SF_
0x18014833d  test    ebx, ebx
0x18014833f  cmovns  ebx, edi
0x180148342  mov     rcx, [rbp+57h+Handle]; Handle
0x180148346  call    cs:__imp_NtClose
0x18014834d  nop     dword ptr [rax+rax+00h]
0x180148352  mov     rcx, [rbp+57h+var_C8]; Handle
0x180148356  test    rcx, rcx
0x180148359  jz      short loc_180148367
0x18014835b  call    cs:__imp_NtClose
0x180148362  nop     dword ptr [rax+rax+00h]
0x180148367  mov     edx, ebx
0x180148369  lea     rcx, aLsapgetregistr; "LsapGetRegistration"
0x180148370  call    DBG_TRACE_EXIT
0x180148375  mov     eax, ebx
  ... truncated ...
```
