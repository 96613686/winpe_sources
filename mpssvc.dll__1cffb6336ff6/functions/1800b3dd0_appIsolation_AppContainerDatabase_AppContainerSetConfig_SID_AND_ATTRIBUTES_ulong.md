# appIsolation::AppContainerDatabase::AppContainerSetConfig(_SID_AND_ATTRIBUTES *,ulong)

- ea: `0x1800b3dd0`
- end: `0x1800b4413`
- name: `?AppContainerSetConfig@AppContainerDatabase@appIsolation@@QEAAKPEAU_SID_AND_ATTRIBUTES@@K@Z`
- size: `1603`
- prototype: `__int64 __fastcall(appIsolation::AppContainerDatabase *this, struct _SID_AND_ATTRIBUTES *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005b094`

## callees

- `0x180009460`
- `0x18000a0c0`
- `0x18000ae9c`
- `0x18000af3c`
- `0x180025368`
- `0x180069bb4`
- `0x18006f520`
- `0x18006ffc8`
- `0x18008924c`
- `0x1800b3dd0`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800b3fa9`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800b3fa9`
- `ntdll!RtlValidSid` at `0x1800b3ed9`
- `ntdll!RtlValidSid` at `0x1800b3ed9`
- `ntdll!RtlIsCapabilitySid` at `0x1800b3ef9`
- `ntdll!RtlIsCapabilitySid` at `0x1800b3ef9`
- `ntdll!RtlEqualSid` at `0x1800b3eeb`
- `ntdll!RtlEqualSid` at `0x1800b3fd5`
- `ntdll!RtlEqualSid` at `0x1800b3eeb`
- `ntdll!RtlEqualSid` at `0x1800b3fd5`
- `fwbase!FwRegSetString` at `0x1800b4065`
- `fwbase!FwRegSetString` at `0x1800b4065`
- `fwbase!FwHResultToWindowsError` at `0x1800b4013`
- `fwbase!FwHResultToWindowsError` at `0x1800b406d`
- `fwbase!FwHResultToWindowsError` at `0x1800b4330`
- `fwbase!FwHResultToWindowsError` at `0x1800b4013`
- `fwbase!FwHResultToWindowsError` at `0x1800b406d`
- `fwbase!FwHResultToWindowsError` at `0x1800b4330`
- `fwbase!FwCriticalSectionEnter` at `0x1800b3e3b`
- `fwbase!FwCriticalSectionEnter` at `0x1800b3e44`
- `fwbase!FwCriticalSectionEnter` at `0x1800b3e3b`
- `fwbase!FwCriticalSectionEnter` at `0x1800b3e44`
- `fwbase!FwCriticalSectionLeave` at `0x1800b4116`
- `fwbase!FwCriticalSectionLeave` at `0x1800b4369`
- `fwbase!FwCriticalSectionLeave` at `0x1800b439b`
- `fwbase!FwCriticalSectionLeave` at `0x1800b43a4`
- `fwbase!FwCriticalSectionLeave` at `0x1800b4116`
- `fwbase!FwCriticalSectionLeave` at `0x1800b4369`
- `fwbase!FwCriticalSectionLeave` at `0x1800b439b`
- `fwbase!FwCriticalSectionLeave` at `0x1800b43a4`
- `fwbase!FwFree` at `0x1800b43af`
- `fwbase!FwFree` at `0x1800b43af`
- `FWPolicyIOMgr!FwSidsToString` at `0x1800b400b`
- `FWPolicyIOMgr!FwSidsToString` at `0x1800b400b`
- `FWPolicyIOMgr!FwSidAndAttributesFree` at `0x1800b40f9`
- `FWPolicyIOMgr!FwSidAndAttributesFree` at `0x1800b4392`
- `FWPolicyIOMgr!FwSidAndAttributesFree` at `0x1800b43f1`
- `FWPolicyIOMgr!FwSidAndAttributesFree` at `0x1800b40f9`
- `FWPolicyIOMgr!FwSidAndAttributesFree` at `0x1800b4392`
- `FWPolicyIOMgr!FwSidAndAttributesFree` at `0x1800b43f1`
- `FWPolicyIOMgr!FwSidAndAttributesCopy` at `0x1800b3f15`
- `FWPolicyIOMgr!FwSidAndAttributesCopy` at `0x1800b40b7`
- `FWPolicyIOMgr!FwSidAndAttributesCopy` at `0x1800b437f`
- `FWPolicyIOMgr!FwSidAndAttributesCopy` at `0x1800b3f15`
- `FWPolicyIOMgr!FwSidAndAttributesCopy` at `0x1800b40b7`
- `FWPolicyIOMgr!FwSidAndAttributesCopy` at `0x1800b437f`

## string_xrefs

- `0x1800b431c`: `FwProfileMgrAppIsolationAppContainerConfigOnlyTransaction`
- `0x1800b3e9b`: `FwMoneisAppContainerSetConfig::StringCchPrintf`

## pseudocode

```c
__int64 __fastcall appIsolation::AppContainerDatabase::AppContainerSetConfig(
        appIsolation::AppContainerDatabase *this,
        struct _SID_AND_ATTRIBUTES *a2,
        unsigned int a3)
{
  unsigned int v3; // edi
  unsigned int v4; // ebp
  size_t v7; // rsi
  char *v8; // r13
  int v9; // eax
  unsigned int v10; // ebx
  PSID *v11; // r12
  unsigned int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  _OWORD *v16; // rbp
  unsigned int i; // ebx
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // r14d
  unsigned int v23; // eax
  void *v24; // rax
  int v25; // esi
  IPolicyWriter *v26; // rbx
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r9
  int v31; // eax
  IPolicyWriter *v32; // rsi
  int updated; // ebx
  int v34; // r12d
  unsigned int v35; // r13d
  __int64 v36; // rdx
  __int64 v37; // rbx
  unsigned int v38; // eax
  IPolicyWriter *v39; // rbx
  unsigned int v40; // eax
  __int64 v41; // rdx
  void *Base; // [rsp+30h] [rbp-278h] BYREF
  __int64 v44; // [rsp+38h] [rbp-270h] BYREF
  __int64 v45; // [rsp+40h] [rbp-268h] BYREF
  unsigned __int16 v46[264]; // [rsp+50h] [rbp-258h] BYREF

  v3 = 0;
  v4 = 0;
  v7 = a3;
  Base = 0;
  v44 = 0;
  v45 = 0;
  memset_0(v46, 0, 0x208u);
  v8 = (char *)this + 48;
  FwCriticalSectionEnter((char *)this + 48);
  FwCriticalSectionEnter(this);
  v9 = StringCchPrintfW(v46, 0x104u, L"%ls\\%ls", *((_QWORD *)this + 13), L"AppCs");
  v10 = 0;
  if ( v9 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_Ds(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        15,
        (unsigned int)WPP_0cc1b8e921193136af39b3da6a1b6f83_Traceguids,
        v9,
        (__int64)"FwMoneisAppContainerSetConfig::StringCchPrintf");
    goto LABEL_77;
  }
  v11 = gSidManager;
  if ( (_DWORD)v7 )
  {
    while ( RtlValidSid(a2[v10].Sid)
         && RtlEqualSid(*v11, a2[v10].Sid) != 1
         && (unsigned __int8)RtlIsCapabilitySid(a2[v10].Sid) != 1 )
    {
      if ( ++v10 >= (unsigned int)v7 )
      {
        v3 = 0;
        goto LABEL_11;
      }
    }
    v10 = 87;
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_77;
    v14 = 16;
    v15 = 87;
LABEL_18:
    WPP_SF_d(*(_QWORD *)(v13 + 16), v14, WPP_0cc1b8e921193136af39b3da6a1b6f83_Traceguids, v15);
    goto LABEL_77;
  }
LABEL_11:
  v12 = FwSidAndAttributesCopy((unsigned int)v7, a2, &Base);
  v10 = v12;
  if ( v12 )
  {
    v4 = v7;
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_77;
    v14 = 17;
    v15 = v12;
    goto LABEL_18;
  }
  v16 = Base;
  qsort(Base, v7, 0x10u, FwSidAndAttribCompare);
  for ( i = 1; i < (unsigned int)v7; ++i )
  {
    if ( !RtlEqualSid(*(PSID *)&v16[v3], *(PSID *)&v16[i]) )
      v16[++v3] = v16[i];
  }
  v4 = v3 + 1;
  if ( !(_DWORD)v7 )
    v4 = v3;
  v18 = FwSidsToString(v4, Base, &v45);
  v19 = FwHResultToWindowsError(v18);
  v10 = v19;
  if ( v19 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_77;
    v14 = 18;
    v15 = v19;
    goto LABEL_18;
  }
  v20 = FwRegSetString(-2147483646, v46, L"DebugedLoopbackApps", v45);
  v21 = FwHResultToWindowsError(v20);
  v10 = v21;
  if ( v21 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_77;
    v14 = 19;
    v15 = v21;
    goto LABEL_18;
  }
  v22 = *((_DWORD *)this + 30);
  v23 = FwSidAndAttributesCopy(v22, *((_QWORD *)this + 14), &v44);
  v10 = v23;
  if ( v23 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_77;
    v14 = 20;
    v15 = v23;
    goto LABEL_18;
  }
  FwSidAndAttributesFree(*((unsigned int *)this + 30), *((_QWORD *)this + 14));
  v24 = Base;
  *((_DWORD *)this + 30) = v4;
  v4 = 0;
  *((_QWORD *)this + 14) = v24;
  Base = 0;
  FwCriticalSectionLeave(this);
  v25 = FwLock();
  if ( v25 >= 0 )
  {
    v26 = pWriterModule;
    v27 = (*(__int64 (__fastcall **)(IPolicyWriter *))(*(_QWORD *)pWriterModule + 16LL))(pWriterModule);
    *((_DWORD *)v26 + 71) = 1;
    v25 = v27;
    if ( v27 < 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_67;
      v29 = 100;
      v30 = (unsigned int)v27;
LABEL_66:
      WPP_SF_d(*(_QWORD *)(v28 + 16), v29, WPP_e2321870bb8f37110138dfc56d389809_Traceguids, v30);
LABEL_67:
      v39 = pWriterModule;
      if ( *((_DWORD *)pWriterModule + 71) == 1 )
        (*(void (__fastcall **)(IPolicyWriter *, __int64))(*(_QWORD *)pWriterModule + 64LL))(
          pWriterModule,
          2147549183LL);
      *((_DWORD *)v39 + 71) = 0;
LABEL_70:
      FwUnlockInternal(0, "FwProfileMgrAppIsolationAppContainerConfigOnlyTransaction");
      v8 = (char *)this + 48;
      goto LABEL_71;
    }
    v31 = IPolicyWriter::WriteAppCConfiguration(pWriterModule);
    v25 = v31;
    if ( v31 < 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_67;
      v29 = 101;
      v30 = (unsigned int)v31;
      goto LABEL_66;
    }
    v32 = pWriterModule;
    updated = 0;
    v34 = (*(__int64 (__fastcall **)(IPolicyWriter *))(*(_QWORD *)pWriterModule + 200LL))(pWriterModule);
    v35 = (*(__int64 (__fastcall **)(IPolicyWriter *))(*(_QWORD *)v32 + 184LL))(v32);
    if ( (*(unsigned int (__fastcall **)(IPolicyWriter *))(*(_QWORD *)v32 + 176LL))(v32) == 1
      && (updated = IPolicyWriter::WriteAppCConfiguration(v32), updated < 0) )
    {
      v28 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_52;
      v36 = 22;
    }
    else
    {
      if ( !v34 && v35 != 1
        || (v37 = g_pCurrentBatch,
            v38 = (*(__int64 (__fastcall **)(IPolicyWriter *))(*(_QWORD *)v32 + 208LL))(v32),
            updated = FwProfMgrUpdateTransactionRemenants(v34 != 0, v38, v35, v37),
            updated >= 0) )
      {
        if ( *((_DWORD *)v32 + 71) == 1 )
          updated = (*(__int64 (__fastcall **)(IPolicyWriter *, _QWORD))(*(_QWORD *)v32 + 64LL))(v32, 0);
        *((_DWORD *)v32 + 71) = 0;
        v25 = updated;
        if ( updated >= 0 )
          goto LABEL_70;
        v28 = WPP_GLOBAL_Control;
        goto LABEL_63;
      }
      v28 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
LABEL_52:
        v25 = updated;
LABEL_63:
        if ( (_UNKNOWN *)v28 == &WPP_GLOBAL_Control || (*(_BYTE *)(v28 + 28) & 1) == 0 )
          goto LABEL_67;
        v29 = 102;
        v30 = (unsigned int)updated;
        goto LABEL_66;
      }
      v36 = 23;
    }
    WPP_SF_d(*(_QWORD *)(v28 + 16), v36, WPP_e5185af2dab037bd3b14417321eb8906_Traceguids, (unsigned int)updated);
    v28 = WPP_GLOBAL_Control;
    goto LABEL_52;
  }
LABEL_71:
  v40 = FwHResultToWindowsError((unsigned int)v25);
  v10 = v40;
  if ( !v40 )
    goto LABEL_78;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 21, WPP_0cc1b8e921193136af39b3da6a1b6f83_Traceguids, v40);
  FwCriticalSectionLeave(this);
  v41 = v44;
  *((_DWORD *)this + 30) = v22;
  FwSidAndAttributesCopy(v22, v41, (char *)this + 112);
  if ( v44 )
    FwSidAndAttributesFree(v22, v44);
LABEL_77:
  FwCriticalSectionLeave(this);
LABEL_78:
  FwCriticalSectionLeave(v8);
  FwFree(v45);
  if ( Base )
    FwSidAndAttributesFree(v4, Base);
  return v10;
}

```

## disassembly

```asm
0x1800b3dd0  mov     r11, rsp
0x1800b3dd3  push    rbx
0x1800b3dd4  push    rbp
0x1800b3dd5  sub     rsp, 298h
0x1800b3ddc  mov     rax, cs:__security_cookie
0x1800b3de3  xor     rax, rsp
0x1800b3de6  mov     [rsp+2A8h+var_48], rax
0x1800b3dee  mov     [r11+20h], rsi
0x1800b3df2  mov     [r11-18h], rdi
0x1800b3df6  xor     edi, edi
0x1800b3df8  mov     [r11-20h], r12
0x1800b3dfc  mov     ebp, edi
0x1800b3dfe  mov     [r11-28h], r13
0x1800b3e02  mov     [r11-30h], r14
0x1800b3e06  mov     r14, rdx
0x1800b3e09  mov     [r11-38h], r15
0x1800b3e0d  xor     edx, edx; Val
0x1800b3e0f  mov     r15, rcx
0x1800b3e12  mov     esi, r8d
0x1800b3e15  lea     rcx, [rsp+2A8h+var_258]; void *
0x1800b3e1a  mov     [rsp+2A8h+Base], rdi
0x1800b3e1f  mov     r8d, 208h; Size
0x1800b3e25  mov     [rsp+2A8h+var_270], rdi
0x1800b3e2a  mov     [rsp+2A8h+var_268], rdi
0x1800b3e2f  call    memset_0
0x1800b3e34  lea     r13, [r15+30h]
0x1800b3e38  mov     rcx, r13
0x1800b3e3b  call    cs:__imp_FwCriticalSectionEnter
0x1800b3e41  mov     rcx, r15
0x1800b3e44  call    cs:__imp_FwCriticalSectionEnter
0x1800b3e4a  mov     r9, [r15+68h]
0x1800b3e4e  lea     rax, aAppcs; "AppCs"
0x1800b3e55  lea     r8, aLsLs; "%ls\\%ls"
0x1800b3e5c  mov     [rsp+2A8h+var_288], rax
0x1800b3e61  mov     edx, 104h; unsigned __int64
0x1800b3e66  lea     rcx, [rsp+2A8h+var_258]; unsigned __int16 *
0x1800b3e6b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b3e70  mov     ebx, edi
0x1800b3e72  test    eax, eax
0x1800b3e74  jns     short loc_1800B3EC0
0x1800b3e76  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3e7d  lea     rdi, WPP_GLOBAL_Control
0x1800b3e84  cmp     rcx, rdi
0x1800b3e87  jz      loc_1800B4398
0x1800b3e8d  test    byte ptr [rcx+1Ch], 1
0x1800b3e91  jz      loc_1800B4398
0x1800b3e97  mov     rcx, [rcx+10h]
0x1800b3e9b  lea     r8, aFwmoneisappcon; "FwMoneisAppContainerSetConfig::StringCc"...
0x1800b3ea2  mov     [rsp+2A8h+var_288], r8
0x1800b3ea7  mov     edx, 0Fh
0x1800b3eac  lea     r8, WPP_0cc1b8e921193136af39b3da6a1b6f83_Traceguids
0x1800b3eb3  mov     r9d, eax
0x1800b3eb6  call    WPP_SF_Ds
0x1800b3ebb  jmp     loc_1800B4398
0x1800b3ec0  mov     r12, cs:?gSidManager@@3V?$unique_ptr@VSidManagement@appIsolation@@U?$default_delete@VSidManagement@appIsolation@@@wistd@@@wistd@@A; wistd::unique_ptr<appIsolation::SidManagement,wistd::default_delete<appIsolation::SidManagement>> gSidManager
0x1800b3ec7  test    esi, esi
0x1800b3ec9  jz      short loc_1800B3F0B
0x1800b3ecb  nop     dword ptr [rax+rax+00h]
0x1800b3ed0  mov     edi, ebx
0x1800b3ed2  add     rdi, rdi
0x1800b3ed5  mov     rcx, [r14+rdi*8]; Sid
0x1800b3ed9  call    cs:__imp_RtlValidSid
0x1800b3edf  test    al, al
0x1800b3ee1  jz      short loc_1800B3F4E
0x1800b3ee3  mov     rdx, [r14+rdi*8]; Sid2
0x1800b3ee7  mov     rcx, [r12]; Sid1
0x1800b3eeb  call    cs:__imp_RtlEqualSid
0x1800b3ef1  cmp     al, 1
0x1800b3ef3  jz      short loc_1800B3F4E
0x1800b3ef5  mov     rcx, [r14+rdi*8]
0x1800b3ef9  call    cs:__imp_RtlIsCapabilitySid
0x1800b3eff  cmp     al, 1
0x1800b3f01  jz      short loc_1800B3F4E
0x1800b3f03  inc     ebx
0x1800b3f05  cmp     ebx, esi
0x1800b3f07  jb      short loc_1800B3ED0
0x1800b3f09  xor     edi, edi
0x1800b3f0b  lea     r8, [rsp+2A8h+Base]
0x1800b3f10  mov     rdx, r14
0x1800b3f13  mov     ecx, esi
0x1800b3f15  call    cs:__imp_FwSidAndAttributesCopy
0x1800b3f1b  mov     ebx, eax
0x1800b3f1d  test    eax, eax
0x1800b3f1f  jz      short loc_1800B3F91
0x1800b3f21  mov     ebp, esi
0x1800b3f23  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3f2a  lea     rdi, WPP_GLOBAL_Control
0x1800b3f31  cmp     rcx, rdi
0x1800b3f34  jz      loc_1800B4398
0x1800b3f3a  test    byte ptr [rcx+1Ch], 1
0x1800b3f3e  jz      loc_1800B4398
0x1800b3f44  mov     edx, 11h
0x1800b3f49  mov     r9d, eax
0x1800b3f4c  jmp     short loc_1800B3F7C
0x1800b3f4e  mov     ebx, 57h ; 'W'
0x1800b3f53  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3f5a  lea     rdi, WPP_GLOBAL_Control
0x1800b3f61  cmp     rcx, rdi
0x1800b3f64  jz      loc_1800B4398
0x1800b3f6a  test    byte ptr [rcx+1Ch], 1
0x1800b3f6e  jz      loc_1800B4398
0x1800b3f74  mov     edx, 10h
0x1800b3f79  mov     r9d, ebx
0x1800b3f7c  mov     rcx, [rcx+10h]
0x1800b3f80  lea     r8, WPP_0cc1b8e921193136af39b3da6a1b6f83_Traceguids
0x1800b3f87  call    WPP_SF_d
0x1800b3f8c  jmp     loc_1800B4398
0x1800b3f91  mov     rbp, [rsp+2A8h+Base]
0x1800b3f96  lea     r9, ?FwSidAndAttribCompare@@YAHPEBU_SID_AND_ATTRIBUTES@@0@Z; CompareFunction
0x1800b3f9d  mov     rcx, rbp; Base
0x1800b3fa0  mov     rdx, rsi; NumOfElements
0x1800b3fa3  mov     r8d, 10h; SizeOfElements
0x1800b3fa9  call    cs:__imp_qsort
0x1800b3faf  mov     ebx, 1
0x1800b3fb4  cmp     esi, ebx
0x1800b3fb6  jbe     short loc_1800B3FF7
0x1800b3fb8  nop     dword ptr [rax+rax+00000000h]
0x1800b3fc0  mov     r14d, ebx
0x1800b3fc3  mov     ecx, edi
0x1800b3fc5  add     r14, r14
0x1800b3fc8  add     rcx, rcx
0x1800b3fcb  mov     rdx, [rbp+r14*8+0]; Sid2
0x1800b3fd0  mov     rcx, [rbp+rcx*8+0]; Sid1
0x1800b3fd5  call    cs:__imp_RtlEqualSid
0x1800b3fdb  test    al, al
0x1800b3fdd  jnz     short loc_1800B3FF1
0x1800b3fdf  movups  xmm0, xmmword ptr [rbp+r14*8+0]
0x1800b3fe5  inc     edi
0x1800b3fe7  mov     eax, edi
0x1800b3fe9  add     rax, rax
0x1800b3fec  movups  xmmword ptr [rbp+rax*8+0], xmm0
0x1800b3ff1  inc     ebx
0x1800b3ff3  cmp     ebx, esi
0x1800b3ff5  jb      short loc_1800B3FC0
0x1800b3ff7  mov     rdx, [rsp+2A8h+Base]
0x1800b3ffc  lea     ebp, [rdi+1]
0x1800b3fff  test    esi, esi
0x1800b4001  lea     r8, [rsp+2A8h+var_268]
0x1800b4006  cmovz   ebp, edi
0x1800b4009  mov     ecx, ebp
0x1800b400b  call    cs:__imp_FwSidsToString
0x1800b4011  mov     ecx, eax
0x1800b4013  call    cs:__imp_FwHResultToWindowsError
0x1800b4019  mov     ebx, eax
0x1800b401b  test    eax, eax
0x1800b401d  jz      short loc_1800B404D
0x1800b401f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4026  lea     rdi, WPP_GLOBAL_Control
0x1800b402d  cmp     rcx, rdi
0x1800b4030  jz      loc_1800B4398
0x1800b4036  test    byte ptr [rcx+1Ch], 1
0x1800b403a  jz      loc_1800B4398
0x1800b4040  mov     edx, 12h
0x1800b4045  mov     r9d, eax
0x1800b4048  jmp     loc_1800B3F7C
0x1800b404d  mov     r9, [rsp+2A8h+var_268]
0x1800b4052  lea     r8, aDebugedloopbac; "DebugedLoopbackApps"
0x1800b4059  lea     rdx, [rsp+2A8h+var_258]
0x1800b405e  mov     rcx, 0FFFFFFFF80000002h
0x1800b4065  call    cs:__imp_FwRegSetString
0x1800b406b  mov     ecx, eax
0x1800b406d  call    cs:__imp_FwHResultToWindowsError
0x1800b4073  mov     ebx, eax
0x1800b4075  test    eax, eax
0x1800b4077  jz      short loc_1800B40A7
0x1800b4079  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4080  lea     rdi, WPP_GLOBAL_Control
0x1800b4087  cmp     rcx, rdi
0x1800b408a  jz      loc_1800B4398
0x1800b4090  test    byte ptr [rcx+1Ch], 1
0x1800b4094  jz      loc_1800B4398
0x1800b409a  mov     edx, 13h
0x1800b409f  mov     r9d, eax
0x1800b40a2  jmp     loc_1800B3F7C
0x1800b40a7  mov     r14d, [r15+78h]
0x1800b40ab  lea     r8, [rsp+2A8h+var_270]
0x1800b40b0  mov     rdx, [r15+70h]
0x1800b40b4  mov     ecx, r14d
0x1800b40b7  call    cs:__imp_FwSidAndAttributesCopy
0x1800b40bd  mov     ebx, eax
0x1800b40bf  test    eax, eax
0x1800b40c1  jz      short loc_1800B40F1
0x1800b40c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b40ca  lea     rdi, WPP_GLOBAL_Control
0x1800b40d1  cmp     rcx, rdi
0x1800b40d4  jz      loc_1800B4398
0x1800b40da  test    byte ptr [rcx+1Ch], 1
0x1800b40de  jz      loc_1800B4398
0x1800b40e4  mov     edx, 14h
0x1800b40e9  mov     r9d, eax
0x1800b40ec  jmp     loc_1800B3F7C
0x1800b40f1  mov     rdx, [r15+70h]
0x1800b40f5  mov     ecx, [r15+78h]
0x1800b40f9  call    cs:__imp_FwSidAndAttributesFree
0x1800b40ff  mov     rax, [rsp+2A8h+Base]
0x1800b4104  mov     rcx, r15
0x1800b4107  mov     [r15+78h], ebp
0x1800b410b  xor     ebp, ebp
0x1800b410d  mov     [r15+70h], rax
0x1800b4111  mov     [rsp+2A8h+Base], rbp
0x1800b4116  call    cs:__imp_FwCriticalSectionLeave
0x1800b411c  call    FwLock
0x1800b4121  lea     rdi, WPP_GLOBAL_Control
0x1800b4128  mov     esi, eax
0x1800b412a  test    eax, eax
0x1800b412c  js      loc_1800B432E
0x1800b4132  mov     rbx, cs:pWriterModule
0x1800b4139  mov     rcx, rbx
0x1800b413c  mov     rax, [rbx]
0x1800b413f  mov     rax, [rax+10h]
0x1800b4143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4148  mov     dword ptr [rbx+11Ch], 1
0x1800b4152  mov     esi, eax
0x1800b4154  test    eax, eax
0x1800b4156  jns     short loc_1800B417F
0x1800b4158  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b415f  cmp     rcx, rdi
0x1800b4162  jz      loc_1800B42F2
0x1800b4168  test    byte ptr [rcx+1Ch], 1
0x1800b416c  jz      loc_1800B42F2
0x1800b4172  mov     edx, 64h ; 'd'
0x1800b4177  mov     r9d, eax
0x1800b417a  jmp     loc_1800B42E2
0x1800b417f  mov     rcx, cs:pWriterModule; this
0x1800b4186  call    ?WriteAppCConfiguration@IPolicyWriter@@QEAAJXZ; IPolicyWriter::WriteAppCConfiguration(void)
0x1800b418b  mov     esi, eax
0x1800b418d  test    eax, eax
0x1800b418f  jns     short loc_1800B41B8
0x1800b4191  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4198  cmp     rcx, rdi
0x1800b419b  jz      loc_1800B42F2
0x1800b41a1  test    byte ptr [rcx+1Ch], 1
0x1800b41a5  jz      loc_1800B42F2
0x1800b41ab  mov     edx, 65h ; 'e'
0x1800b41b0  mov     r9d, eax
0x1800b41b3  jmp     loc_1800B42E2
0x1800b41b8  mov     rsi, cs:pWriterModule
0x1800b41bf  xor     ebx, ebx
0x1800b41c1  mov     rcx, rsi
0x1800b41c4  mov     rax, [rsi]
0x1800b41c7  mov     rax, [rax+0C8h]
0x1800b41ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b41d3  mov     rcx, [rsi]
0x1800b41d6  mov     r12d, eax
0x1800b41d9  mov     rax, [rcx+0B8h]
0x1800b41e0  mov     rcx, rsi
0x1800b41e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b41e8  mov     rcx, [rsi]
0x1800b41eb  mov     r13d, eax
0x1800b41ee  mov     rax, [rcx+0B0h]
0x1800b41f5  mov     rcx, rsi
0x1800b41f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b41fd  cmp     eax, 1
0x1800b4200  jnz     short loc_1800B4248
0x1800b4202  mov     rcx, rsi; this
0x1800b4205  call    ?WriteAppCConfiguration@IPolicyWriter@@QEAAJXZ; IPolicyWriter::WriteAppCConfiguration(void)
0x1800b420a  mov     ebx, eax
0x1800b420c  test    eax, eax
0x1800b420e  jns     short loc_1800B4248
0x1800b4210  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4217  cmp     rcx, rdi
0x1800b421a  jz      short loc_1800B4241
0x1800b421c  test    byte ptr [rcx+1Ch], 1
0x1800b4220  jz      short loc_1800B4241
0x1800b4222  mov     edx, 16h
0x1800b4227  mov     rcx, [rcx+10h]
0x1800b422b  lea     r8, WPP_e5185af2dab037bd3b14417321eb8906_Traceguids
0x1800b4232  mov     r9d, ebx
0x1800b4235  call    WPP_SF_d
0x1800b423a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4241  mov     esi, ebx
0x1800b4243  jmp     loc_1800B42CF
0x1800b4248  test    r12d, r12d
0x1800b424b  jnz     short loc_1800B4253
0x1800b424d  cmp     r13d, 1
0x1800b4251  jnz     short loc_1800B42A0
0x1800b4253  mov     rax, [rsi]
0x1800b4256  mov     rcx, rsi
0x1800b4259  mov     rbx, cs:g_pCurrentBatch
0x1800b4260  mov     rax, [rax+0D0h]
0x1800b4267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b426c  xor     ecx, ecx
0x1800b426e  mov     r9, rbx
0x1800b4271  test    r12d, r12d
0x1800b4274  mov     r8d, r13d
0x1800b4277  mov     edx, eax
0x1800b4279  setnz   cl
0x1800b427c  call    FwProfMgrUpdateTransactionRemenants
0x1800b4281  mov     ebx, eax
0x1800b4283  test    eax, eax
0x1800b4285  jns     short loc_1800B42A0
0x1800b4287  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b428e  cmp     rcx, rdi
0x1800b4291  jz      short loc_1800B4241
0x1800b4293  test    byte ptr [rcx+1Ch], 1
0x1800b4297  jz      short loc_1800B4241
0x1800b4299  mov     edx, 17h
0x1800b429e  jmp     short loc_1800B4227
0x1800b42a0  cmp     dword ptr [rsi+11Ch], 1
0x1800b42a7  jnz     short loc_1800B42BC
  ... truncated ...
```
