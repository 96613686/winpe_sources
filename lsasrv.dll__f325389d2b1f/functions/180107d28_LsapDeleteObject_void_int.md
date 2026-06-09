# LsapDeleteObject(void * *,int)

- ea: `0x180107d28`
- end: `0x18010820a`
- name: `?LsapDeleteObject@@YAJPEAPEAXH@Z`
- size: `1250`
- prototype: `__int64 __fastcall(void **, int)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180108270`
- `0x180111d00`

## callees

- `0x180009470`
- `0x18000c300`
- `0x18000ddc0`
- `0x180010ba0`
- `0x180011278`
- `0x180016f70`
- `0x18001ddc0`
- `0x180021580`
- `0x180083210`
- `0x18008d370`
- `0x1800a0590`
- `0x1800bc040`
- `0x1800bd6e0`
- `0x180107d28`
- `0x1801082a8`
- `0x18010bf74`
- `0x180115c44`
- `0x18011b488`
- `0x18014d010`

## import_xrefs

- `LSAADT!__imp_LsapAuditFailed` at `0x180108194`
- `LSAADT!__imp_LsapAuditFailed` at `0x180108194`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180107e5e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180107e5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801080a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801080a0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801081da`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801081da`
- `ntdll!NtDeleteObjectAuditAlarm` at `0x1801081b1`
- `ntdll!NtDeleteObjectAuditAlarm` at `0x1801081b1`
- `ntdll!RtlReleaseResource` at `0x180107f48`
- `ntdll!RtlReleaseResource` at `0x180107f48`
- `ntdll!RtlAcquireResourceShared` at `0x180107e73`
- `ntdll!RtlAcquireResourceShared` at `0x180107e73`
- `ntdll!RtlLengthSid` at `0x180107dd5`
- `ntdll!RtlLengthSid` at `0x180107dd5`
- `ntdll!RtlLeaveCriticalSection` at `0x180107e31`
- `ntdll!RtlLeaveCriticalSection` at `0x180107e31`
- `ntdll!RtlEnterCriticalSection` at `0x180107e18`
- `ntdll!RtlEnterCriticalSection` at `0x180107e18`
- `RPCRT4!RpcRevertToSelf` at `0x1801081eb`
- `RPCRT4!RpcRevertToSelf` at `0x1801081eb`
- `RPCRT4!I_RpcMapWin32Status` at `0x180108168`
- `RPCRT4!I_RpcMapWin32Status` at `0x1801081f9`
- `RPCRT4!I_RpcMapWin32Status` at `0x180108168`
- `RPCRT4!I_RpcMapWin32Status` at `0x1801081f9`
- `RPCRT4!RpcImpersonateClient` at `0x18010815a`
- `RPCRT4!RpcImpersonateClient` at `0x18010815a`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledHint` at `0x180107fec`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledHint` at `0x180107fec`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtGenerateLsaAuditEvent` at `0x18010808f`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtGenerateLsaAuditEvent` at `0x18010808f`

## pseudocode

```c
__int64 __fastcall LsapDeleteObject(struct _LSAP_DB_HANDLE **a1, int a2)
{
  struct _LSAP_DB_HANDLE *v2; // rsi
  struct _RTL_BALANCED_NODE *v3; // r12
  int v4; // r13d
  BOOL v7; // ebp
  unsigned int v8; // r14d
  __int64 v9; // rbx
  struct _RTL_BALANCED_NODE *v10; // rax
  void *v11; // rdx
  unsigned int v12; // ebx
  signed int v13; // edi
  __int64 v14; // rcx
  __int64 result; // rax
  struct _LSAP_DB_HANDLE *v16; // rbx
  int v17; // eax
  __int64 v18; // rcx
  int LsaDbExtensionDll; // eax
  int v20; // ebx
  LsaAccountCache *v21; // rcx
  int v22; // eax
  RPC_STATUS v23; // eax
  RPC_STATUS v24; // eax
  unsigned int v25; // [rsp+50h] [rbp-58h]
  HLOCAL hMem; // [rsp+58h] [rbp-50h] BYREF
  _QWORD v27[9]; // [rsp+60h] [rbp-48h] BYREF
  char v28; // [rsp+B0h] [rbp+8h]
  char v29; // [rsp+C0h] [rbp+18h]
  char v30; // [rsp+C8h] [rbp+20h]

  v2 = *a1;
  v3 = 0;
  v4 = 0;
  v28 = 0;
  v30 = 0;
  v29 = 0;
  v25 = 5;
  if ( *((_DWORD *)*a1 + 26) == 3 )
  {
    LOBYTE(v4) = 1;
    v7 = *((_DWORD *)v2 + 26) == 3;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 12));
  }
  else
  {
    v7 = 0;
  }
  v8 = *((_DWORD *)v2 + 26);
  if ( !*((_BYTE *)v2 + 49) && !*((_BYTE *)v2 + 50) )
  {
    if ( v8 != 1 )
    {
      if ( v8 != 3 )
        goto LABEL_15;
      v9 = RtlLengthSid(*((PSID *)v2 + 11));
      v10 = (struct _RTL_BALANCED_NODE *)LsapAllocate(v9);
      v3 = v10;
      if ( !v10 )
      {
        v13 = -1073741670;
        goto LABEL_21;
      }
      memcpy_0(v10, *((const void **)v2 + 11), (unsigned int)v9);
      v25 = 7;
    }
    if ( a2 )
    {
      RtlEnterCriticalSection(&stru_18019F2D8);
      v12 = dword_18019F308;
      RtlLeaveCriticalSection(&stru_18019F2D8);
      v13 = v12 > 0x1F4 ? 0xC0000129 : 0;
      if ( v12 > 0x1F4 )
        goto LABEL_21;
      WaitForSingleObject(hHandle, 0xFFFFFFFF);
      RtlAcquireResourceShared((PRTL_RESOURCE)&stru_18019F2D8, 1u);
      v30 = 1;
    }
    v29 = 1;
  }
LABEL_15:
  v13 = LsapDbReferenceObject(*a1, 0x10000u, v8, v8, 9);
  if ( v13 < 0 )
    goto LABEL_21;
  v28 = 1;
  if ( v8 == 1 )
  {
LABEL_20:
    v13 = -1073741811;
    goto LABEL_21;
  }
  if ( v8 == 2 )
  {
    LsaDbExtensionDll = LsapLoadLsaDbExtensionDll();
    if ( LsaDbExtensionDll >= 0 )
      LsaDbExtensionDll = (*((__int64 (__fastcall **)(struct _LSAP_DB_HANDLE **))g_pLsaExtensionTableLsaDb + 5))(a1);
    v13 = 0;
    if ( LsaDbExtensionDll != -1073741637 )
      v13 = LsaDbExtensionDll;
    goto LABEL_48;
  }
  if ( v8 != 3 )
  {
    if ( v8 != 4 )
      goto LABEL_20;
    goto LABEL_50;
  }
  if ( !(unsigned __int8)IsLsapAdtInitializeCrashOnAuditFailPresent(v14)
    || (v16 = *a1,
        v27[0] = 0,
        hMem = 0,
        v27[0] = *((_QWORD *)v16 + 11),
        !(unsigned __int8)LsapAdtAuditingEnabledHint(141, 8)) )
  {
LABEL_48:
    if ( v13 < 0 )
      goto LABEL_21;
    if ( v8 == 2 )
      goto LABEL_52;
    goto LABEL_50;
  }
  v17 = LsarQueryInformationAccount(v16, 2, &hMem);
  v13 = v17;
  if ( v17 >= 0 )
  {
    if ( (unsigned __int8)IsLsapAdtInitializeCrashOnAuditFailPresent(v18) )
      LsapAdtGenerateLsaAuditEvent(v16, 6, 4705, hMem, 1, v27, 0, 0, 0, 0);
    LocalFree(hMem);
LABEL_50:
    v13 = LsapDbDeleteObject(*a1);
    if ( v13 < 0 )
      goto LABEL_21;
    LsapDbDereferenceHandle(*a1);
LABEL_52:
    v20 = 0;
    if ( v8 == 3 && dword_18019F50C == 4 )
    {
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights>::GetImpl'::`2'::impl) )
      {
        if ( gpLsaAccountCache )
          LsaAccountCache::Delete(v21, *((void **)v2 + 11));
      }
      else
      {
        LsapDbDeleteAccount(*((struct _LSAPR_SID **)v2 + 11));
      }
    }
    if ( !*((_BYTE *)v2 + 133) )
    {
      if ( (*((_DWORD *)v2 + 34) & 0x8000) != 0 )
      {
        v22 = LsapImpersonateClientEx(0);
      }
      else
      {
        v23 = RpcImpersonateClient(0);
        v22 = I_RpcMapWin32Status(v23);
      }
      if ( v22 < 0 )
      {
        if ( v22 != -1073610726 && (unsigned int)(v22 + 1073610687) > 1 )
          LsapAuditFailed((unsigned int)v22);
      }
      else
      {
        v20 = 1;
      }
    }
    NtDeleteObjectAuditAlarm(&SubsystemName, *a1, *((_BYTE *)v2 + 132));
    if ( !*((_BYTE *)v2 + 133) && v20 )
    {
      if ( (*((_DWORD *)v2 + 34) & 0x8000) != 0 )
      {
        RevertToSelf();
      }
      else
      {
        v24 = RpcRevertToSelf();
        I_RpcMapWin32Status(v24);
      }
    }
    goto LABEL_21;
  }
  if ( v7 && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      13,
      WPP_f35f81c4a0243c354351a072c5a50f96_Traceguids,
      (unsigned int)v17);
  do
  {
LABEL_21:
    if ( !v28 )
      break;
    v28 = 0;
    v13 = LsapDbDereferenceObject((_DWORD)a1, v8, v8, 273, 3, v13);
  }
  while ( v13 < 0 );
  if ( v29 && v13 >= 0 )
    LsapSceNotify(3, v25, v3);
  if ( v30 )
    RtlReleaseResource((PRTL_RESOURCE)&stru_18019F2D8);
  if ( v3 )
    LsapSubProv_FreeRoutine(v3, v11);
  if ( v4 && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      14,
      WPP_f35f81c4a0243c354351a072c5a50f96_Traceguids,
      (unsigned int)v13);
  result = (unsigned int)v13;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180107d28  mov     [rsp+arg_8], rbx
0x180107d2d  push    rbp
0x180107d2e  push    rsi
0x180107d2f  push    rdi
0x180107d30  push    r12
0x180107d32  push    r13
0x180107d34  push    r14
0x180107d36  push    r15
0x180107d38  sub     rsp, 70h
0x180107d3c  mov     rsi, [rcx]
0x180107d3f  xor     r12d, r12d
0x180107d42  xor     r13d, r13d
0x180107d45  mov     [rsp+0A8h+arg_0], 0
0x180107d4d  mov     edi, edx
0x180107d4f  mov     [rsp+0A8h+arg_18], 0
0x180107d57  mov     r15, rcx
0x180107d5a  mov     [rsp+0A8h+arg_10], 0
0x180107d62  cmp     dword ptr [rsi+68h], 3
0x180107d66  mov     [rsp+0A8h+var_58], 5
0x180107d6e  jnz     short loc_180107DA6
0x180107d70  setz    r13b
0x180107d74  xor     ebp, ebp
0x180107d76  cmp     dword ptr [rsi+68h], 3
0x180107d7a  setz    bpl
0x180107d7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180107d85  test    byte ptr [rcx+6Ch], 1
0x180107d89  jz      short loc_180107DA8
0x180107d8b  mov     r9, [rsi+58h]
0x180107d8f  lea     edx, [r12+0Ch]
0x180107d94  mov     rcx, [rcx+60h]; LoggerHandle
0x180107d98  lea     r8, WPP_f35f81c4a0243c354351a072c5a50f96_Traceguids
0x180107d9f  call    WPP_SF__sid_
0x180107da4  jmp     short loc_180107DA8
0x180107da6  xor     ebp, ebp
0x180107da8  mov     r14d, [rsi+68h]
0x180107dac  cmp     [rsi+31h], r12b
0x180107db0  jnz     loc_180107E8F
0x180107db6  cmp     [rsi+32h], r12b
0x180107dba  jnz     loc_180107E8F
0x180107dc0  mov     ecx, r14d
0x180107dc3  sub     ecx, 1
0x180107dc6  jz      short loc_180107E0D
0x180107dc8  cmp     ecx, 2
0x180107dcb  jnz     loc_180107E8F
0x180107dd1  mov     rcx, [rsi+58h]; Sid
0x180107dd5  call    cs:__imp_RtlLengthSid
0x180107ddc  nop     dword ptr [rax+rax+00h]
0x180107de1  mov     ecx, eax
0x180107de3  mov     ebx, eax
0x180107de5  call    LsapAllocate
0x180107dea  mov     r12, rax
0x180107ded  test    rax, rax
0x180107df0  jz      loc_180107FAD
0x180107df6  mov     rdx, [rsi+58h]; Src
0x180107dfa  mov     r8d, ebx; Size
0x180107dfd  mov     rcx, rax; void *
0x180107e00  call    memcpy_0
0x180107e05  mov     [rsp+0A8h+var_58], 7
0x180107e0d  test    edi, edi
0x180107e0f  jz      short loc_180107E87
0x180107e11  lea     rcx, stru_18019F2D8; CriticalSection
0x180107e18  call    cs:__imp_RtlEnterCriticalSection
0x180107e1f  nop     dword ptr [rax+rax+00h]
0x180107e24  mov     ebx, cs:dword_18019F308
0x180107e2a  lea     rcx, stru_18019F2D8; CriticalSection
0x180107e31  call    cs:__imp_RtlLeaveCriticalSection
0x180107e38  nop     dword ptr [rax+rax+00h]
0x180107e3d  mov     eax, 1F4h
0x180107e42  cmp     eax, ebx
0x180107e44  sbb     edi, edi
0x180107e46  and     edi, 0C0000129h
0x180107e4c  cmp     ebx, eax
0x180107e4e  ja      loc_180107EE0
0x180107e54  mov     rcx, cs:hHandle; hHandle
0x180107e5b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180107e5e  call    cs:__imp_WaitForSingleObject
0x180107e65  nop     dword ptr [rax+rax+00h]
0x180107e6a  mov     dl, 1; Wait
0x180107e6c  lea     rcx, stru_18019F2D8; Resource
0x180107e73  call    cs:__imp_RtlAcquireResourceShared
0x180107e7a  nop     dword ptr [rax+rax+00h]
0x180107e7f  mov     [rsp+0A8h+arg_18], 1
0x180107e87  mov     [rsp+0A8h+arg_10], 1
0x180107e8f  mov     rcx, [r15]; struct _LSAP_DB_HANDLE *
0x180107e92  mov     r9d, r14d
0x180107e95  mov     r8d, r14d
0x180107e98  mov     [rsp+0A8h+var_88], 9; int
0x180107ea0  mov     edx, 10000h; DesiredAccess
0x180107ea5  call    LsapDbReferenceObject
0x180107eaa  mov     edi, eax
0x180107eac  test    eax, eax
0x180107eae  js      short loc_180107EE0
0x180107eb0  mov     eax, r14d
0x180107eb3  mov     [rsp+0A8h+arg_0], 1
0x180107ebb  sub     eax, 1
0x180107ebe  jz      short loc_180107EDB
0x180107ec0  sub     eax, 1
0x180107ec3  jz      loc_1801080AE
0x180107ec9  sub     eax, 1
0x180107ecc  jz      loc_180107FB7
0x180107ed2  cmp     eax, 1
0x180107ed5  jz      loc_1801080E2
0x180107edb  mov     edi, 0C000000Dh
0x180107ee0  cmp     [rsp+0A8h+arg_0], 0
0x180107ee8  jz      short loc_180107F18
0x180107eea  mov     dword ptr [rsp+0A8h+var_80], edi
0x180107eee  mov     r9d, 111h
0x180107ef4  mov     r8d, r14d
0x180107ef7  mov     [rsp+0A8h+var_88], 3
0x180107eff  mov     edx, r14d
0x180107f02  mov     rcx, r15
0x180107f05  call    LsapDbDereferenceObject
0x180107f0a  mov     [rsp+0A8h+arg_0], 0
0x180107f12  mov     edi, eax
0x180107f14  test    eax, eax
0x180107f16  js      short loc_180107EE0
0x180107f18  cmp     [rsp+0A8h+arg_10], 0
0x180107f20  jz      short loc_180107F37
0x180107f22  test    edi, edi
0x180107f24  js      short loc_180107F37
0x180107f26  mov     edx, [rsp+0A8h+var_58]
0x180107f2a  mov     r8, r12
0x180107f2d  mov     ecx, 3
0x180107f32  call    ?LsapSceNotify@@YAJW4_SECURITY_DB_DELTA_TYPE@@W4_SECURITY_DB_OBJECT_TYPE@@PEAX@Z; LsapSceNotify(_SECURITY_DB_DELTA_TYPE,_SECURITY_DB_OBJECT_TYPE,void *)
0x180107f37  cmp     [rsp+0A8h+arg_18], 0
0x180107f3f  jz      short loc_180107F54
0x180107f41  lea     rcx, stru_18019F2D8; Resource
0x180107f48  call    cs:__imp_RtlReleaseResource
0x180107f4f  nop     dword ptr [rax+rax+00h]
0x180107f54  test    r12, r12
0x180107f57  jz      short loc_180107F61
0x180107f59  mov     rcx, r12; struct _RTL_BALANCED_NODE *
0x180107f5c  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x180107f61  test    r13d, r13d
0x180107f64  jz      short loc_180107F8B
0x180107f66  mov     rcx, cs:WPP_GLOBAL_Control
0x180107f6d  test    byte ptr [rcx+6Ch], 1
0x180107f71  jz      short loc_180107F8B
0x180107f73  mov     rcx, [rcx+60h]
0x180107f77  lea     r8, WPP_f35f81c4a0243c354351a072c5a50f96_Traceguids
0x180107f7e  mov     edx, 0Eh
0x180107f83  mov     r9d, edi
0x180107f86  call    WPP_SF_d
0x180107f8b  mov     rbx, [rsp+0A8h+arg_8]
0x180107f93  mov     eax, edi
0x180107f95  mov     qword ptr [r15], 0
0x180107f9c  add     rsp, 70h
0x180107fa0  pop     r15
0x180107fa2  pop     r14
0x180107fa4  pop     r13
0x180107fa6  pop     r12
0x180107fa8  pop     rdi
0x180107fa9  pop     rsi
0x180107faa  pop     rbp
0x180107fab  retn
0x180107fad  mov     edi, 0C000009Ah
0x180107fb2  jmp     loc_180107EE0
0x180107fb7  call    IsLsapAdtInitializeCrashOnAuditFailPresent
0x180107fbc  test    al, al
0x180107fbe  jz      loc_1801080D4
0x180107fc4  mov     rbx, [r15]
0x180107fc7  mov     edx, 8
0x180107fcc  mov     [rsp+0A8h+var_48], 0
0x180107fd5  mov     ecx, 8Dh
0x180107fda  mov     [rsp+0A8h+hMem], 0
0x180107fe3  mov     rax, [rbx+58h]
0x180107fe7  mov     [rsp+0A8h+var_48], rax
0x180107fec  call    cs:__imp_LsapAdtAuditingEnabledHint
0x180107ff3  nop     dword ptr [rax+rax+00h]
0x180107ff8  test    al, al
0x180107ffa  jz      loc_1801080D4
0x180108000  lea     r8, [rsp+0A8h+hMem]
0x180108005  mov     edx, 2
0x18010800a  mov     rcx, rbx
0x18010800d  call    ?LsarQueryInformationAccount@@YAJPEAXW4_ACCOUNT_INFORMATION_CLASS@@PEAPEAT_LSAPR_ACCOUNT_INFO@@@Z; LsarQueryInformationAccount(void *,_ACCOUNT_INFORMATION_CLASS,_LSAPR_ACCOUNT_INFO * *)
0x180108012  mov     edi, eax
0x180108014  test    eax, eax
0x180108016  jns     short loc_18010804E
0x180108018  test    ebp, ebp
0x18010801a  jz      loc_180107EE0
0x180108020  mov     rcx, cs:WPP_GLOBAL_Control
0x180108027  test    byte ptr [rcx+6Ch], 1
0x18010802b  jz      loc_180107EE0
0x180108031  mov     rcx, [rcx+60h]
0x180108035  lea     r8, WPP_f35f81c4a0243c354351a072c5a50f96_Traceguids
0x18010803c  mov     edx, 0Dh
0x180108041  mov     r9d, eax
0x180108044  call    WPP_SF_d
0x180108049  jmp     loc_180107EE0
0x18010804e  call    IsLsapAdtInitializeCrashOnAuditFailPresent
0x180108053  xor     ecx, ecx
0x180108055  test    al, al
0x180108057  jz      short loc_18010809B
0x180108059  mov     r9, [rsp+0A8h+hMem]
0x18010805e  lea     rax, [rsp+0A8h+var_48]
0x180108063  mov     [rsp+0A8h+var_60], rcx
0x180108068  lea     edx, [rcx+6]
0x18010806b  mov     [rsp+0A8h+var_68], rcx
0x180108070  mov     r8d, 1261h
0x180108076  mov     [rsp+0A8h+var_70], rcx
0x18010807b  mov     [rsp+0A8h+var_78], ecx
0x18010807f  mov     rcx, rbx
0x180108082  mov     [rsp+0A8h+var_80], rax
0x180108087  mov     [rsp+0A8h+var_88], 1
0x18010808f  call    cs:__imp_LsapAdtGenerateLsaAuditEvent
0x180108096  nop     dword ptr [rax+rax+00h]
0x18010809b  mov     rcx, [rsp+0A8h+hMem]; hMem
0x1801080a0  call    cs:__imp_LocalFree
0x1801080a7  nop     dword ptr [rax+rax+00h]
0x1801080ac  jmp     short loc_1801080E2
0x1801080ae  call    ?LsapLoadLsaDbExtensionDll@@YAJXZ; LsapLoadLsaDbExtensionDll(void)
0x1801080b3  test    eax, eax
0x1801080b5  js      short loc_1801080CA
0x1801080b7  mov     rax, cs:?g_pLsaExtensionTableLsaDb@@3PEAU_LSA_EXTENSION_TABLE_LSADB@@EA; _LSA_EXTENSION_TABLE_LSADB * g_pLsaExtensionTableLsaDb
0x1801080be  mov     rcx, r15
0x1801080c1  mov     rax, [rax+28h]
0x1801080c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801080ca  xor     edi, edi
0x1801080cc  cmp     eax, 0C00000BBh
0x1801080d1  cmovnz  edi, eax
0x1801080d4  test    edi, edi
0x1801080d6  js      loc_180107EE0
0x1801080dc  cmp     r14d, 2
0x1801080e0  jz      short loc_1801080FE
0x1801080e2  mov     rcx, [r15]; void *
0x1801080e5  call    LsapDbDeleteObject
0x1801080ea  mov     edi, eax
0x1801080ec  test    eax, eax
0x1801080ee  js      loc_180107EE0
0x1801080f4  mov     rcx, [r15]; struct _LSAP_DB_HANDLE *
0x1801080f7  mov     dl, 1
0x1801080f9  call    LsapDbDereferenceHandle
0x1801080fe  xor     ebx, ebx
0x180108100  cmp     r14d, 3
0x180108104  jnz     short loc_18010813C
0x180108106  cmp     cs:dword_18019F50C, 4
0x18010810d  jnz     short loc_18010813C
0x18010810f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights> `wil::Feature<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights>::GetImpl(void)'::`2'::impl
0x180108116  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LocalSystemAccessRights>::__private_IsEnabled(void)
0x18010811b  test    al, al
0x18010811d  jz      short loc_180108133
0x18010811f  cmp     cs:?gpLsaAccountCache@@3PEAVLsaAccountCache@@EA, rbx; LsaAccountCache * gpLsaAccountCache
0x180108126  jz      short loc_18010813C
0x180108128  mov     rdx, [rsi+58h]; void *
0x18010812c  call    ?Delete@LsaAccountCache@@QEAAJPEAX@Z; LsaAccountCache::Delete(void *)
0x180108131  jmp     short loc_18010813C
0x180108133  mov     rcx, [rsi+58h]; struct _LSAPR_SID *
0x180108137  call    ?LsapDbDeleteAccount@@YAJPEAU_LSAPR_SID@@@Z; LsapDbDeleteAccount(_LSAPR_SID *)
0x18010813c  mov     ebp, 8000h
0x180108141  cmp     [rsi+85h], bl
0x180108147  jnz     short loc_1801081A0
0x180108149  xor     ecx, ecx; int *
0x18010814b  test    [rsi+88h], ebp
0x180108151  jz      short loc_18010815A
0x180108153  call    ?LsapImpersonateClientEx@@YAJPEAH@Z; LsapImpersonateClientEx(int *)
0x180108158  jmp     short loc_180108174
0x18010815a  call    cs:__imp_RpcImpersonateClient
0x180108161  nop     dword ptr [rax+rax+00h]
0x180108166  mov     ecx, eax; Status
0x180108168  call    cs:__imp_I_RpcMapWin32Status
0x18010816f  nop     dword ptr [rax+rax+00h]
0x180108174  mov     ecx, eax
0x180108176  test    eax, eax
0x180108178  js      short loc_180108181
0x18010817a  mov     ebx, 1
0x18010817f  jmp     short loc_1801081A0
0x180108181  cmp     ecx, 0C002001Ah
0x180108187  jz      short loc_1801081A0
0x180108189  lea     eax, [rcx+3FFDFFBFh]
0x18010818f  cmp     eax, 1
0x180108192  jbe     short loc_1801081A0
0x180108194  call    cs:__imp_LsapAuditFailed
0x18010819b  nop     dword ptr [rax+rax+00h]
0x1801081a0  mov     r8b, [rsi+84h]; GenerateOnClose
0x1801081a7  lea     rcx, SubsystemName; SubsystemName
0x1801081ae  mov     rdx, [r15]; HandleId
0x1801081b1  call    cs:__imp_NtDeleteObjectAuditAlarm
0x1801081b8  nop     dword ptr [rax+rax+00h]
0x1801081bd  cmp     byte ptr [rsi+85h], 0
0x1801081c4  jnz     loc_180107EE0
0x1801081ca  test    ebx, ebx
0x1801081cc  jz      loc_180107EE0
0x1801081d2  test    [rsi+88h], ebp
0x1801081d8  jz      short loc_1801081EB
0x1801081da  call    cs:__imp_RevertToSelf
0x1801081e1  nop     dword ptr [rax+rax+00h]
0x1801081e6  jmp     loc_180107EE0
0x1801081eb  call    cs:__imp_RpcRevertToSelf
0x1801081f2  nop     dword ptr [rax+rax+00h]
0x1801081f7  mov     ecx, eax; Status
0x1801081f9  call    cs:__imp_I_RpcMapWin32Status
0x180108200  nop     dword ptr [rax+rax+00h]
0x180108205  jmp     loc_180107EE0
```
