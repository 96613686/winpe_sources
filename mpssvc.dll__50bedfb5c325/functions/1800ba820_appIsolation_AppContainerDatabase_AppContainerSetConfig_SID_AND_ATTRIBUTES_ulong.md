# appIsolation::AppContainerDatabase::AppContainerSetConfig(_SID_AND_ATTRIBUTES *,ulong)

- ea: `0x1800ba820`
- end: `0x1800baeec`
- name: `?AppContainerSetConfig@AppContainerDatabase@appIsolation@@QEAAKPEAU_SID_AND_ATTRIBUTES@@K@Z`
- size: `1740`
- prototype: `unsigned int(appIsolation::AppContainerDatabase *__hidden this, struct _SID_AND_ATTRIBUTES *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180060150`

## callees

- `0x180008a80`
- `0x1800097b0`
- `0x18000a66c`
- `0x18000a710`
- `0x1800278ac`
- `0x18006c8ac`
- `0x1800729c0`
- `0x180073488`
- `0x18008d9c4`
- `0x1800ba820`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800baa1b`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800baa1b`
- `ntdll!RtlValidSid` at `0x1800ba92c`
- `ntdll!RtlValidSid` at `0x1800ba92c`
- `ntdll!RtlIsCapabilitySid` at `0x1800ba95f`
- `ntdll!RtlIsCapabilitySid` at `0x1800ba95f`
- `ntdll!RtlEqualSid` at `0x1800ba94b`
- `ntdll!RtlEqualSid` at `0x1800baa45`
- `ntdll!RtlEqualSid` at `0x1800ba94b`
- `ntdll!RtlEqualSid` at `0x1800baa45`
- `fwbase!FwRegSetString` at `0x1800baae7`
- `fwbase!FwRegSetString` at `0x1800baae7`
- `fwbase!FwHResultToWindowsError` at `0x1800baa8f`
- `fwbase!FwHResultToWindowsError` at `0x1800baaf5`
- `fwbase!FwHResultToWindowsError` at `0x1800badd4`
- `fwbase!FwHResultToWindowsError` at `0x1800baa8f`
- `fwbase!FwHResultToWindowsError` at `0x1800baaf5`
- `fwbase!FwHResultToWindowsError` at `0x1800badd4`
- `fwbase!FwCriticalSectionEnter` at `0x1800ba88b`
- `fwbase!FwCriticalSectionEnter` at `0x1800ba89e`
- `fwbase!FwCriticalSectionEnter` at `0x1800ba88b`
- `fwbase!FwCriticalSectionEnter` at `0x1800ba89e`
- `fwbase!FwCriticalSectionLeave` at `0x1800babb0`
- `fwbase!FwCriticalSectionLeave` at `0x1800bae17`
- `fwbase!FwCriticalSectionLeave` at `0x1800bae5b`
- `fwbase!FwCriticalSectionLeave` at `0x1800bae6a`
- `fwbase!FwCriticalSectionLeave` at `0x1800babb0`
- `fwbase!FwCriticalSectionLeave` at `0x1800bae17`
- `fwbase!FwCriticalSectionLeave` at `0x1800bae5b`
- `fwbase!FwCriticalSectionLeave` at `0x1800bae6a`
- `fwbase!FwFree` at `0x1800bae7b`
- `fwbase!FwFree` at `0x1800bae7b`
- `FWPolicyIOMgr!FwSidsToString` at `0x1800baa81`
- `FWPolicyIOMgr!FwSidsToString` at `0x1800baa81`
- `FWPolicyIOMgr!FwSidAndAttributesFree` at `0x1800bab8d`
- `FWPolicyIOMgr!FwSidAndAttributesFree` at `0x1800bae4c`
- `FWPolicyIOMgr!FwSidAndAttributesFree` at `0x1800baec3`
- `FWPolicyIOMgr!FwSidAndAttributesFree` at `0x1800bab8d`
- `FWPolicyIOMgr!FwSidAndAttributesFree` at `0x1800bae4c`
- `FWPolicyIOMgr!FwSidAndAttributesFree` at `0x1800baec3`
- `FWPolicyIOMgr!FwSidAndAttributesCopy` at `0x1800ba981`
- `FWPolicyIOMgr!FwSidAndAttributesCopy` at `0x1800bab45`
- `FWPolicyIOMgr!FwSidAndAttributesCopy` at `0x1800bae33`
- `FWPolicyIOMgr!FwSidAndAttributesCopy` at `0x1800ba981`
- `FWPolicyIOMgr!FwSidAndAttributesCopy` at `0x1800bab45`
- `FWPolicyIOMgr!FwSidAndAttributesCopy` at `0x1800bae33`

## string_xrefs

- `0x1800badbc`: `FwProfileMgrAppIsolationAppContainerConfigOnlyTransaction`
- `0x1800ba8fa`: `FwMoneisAppContainerSetConfig::StringCchPrintf`

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
  char *v9; // r12
  int v10; // eax
  unsigned int v11; // ebx
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
  v8 = (char *)this + 88;
  FwCriticalSectionEnter((char *)this + 88);
  v9 = (char *)this + 24;
  FwCriticalSectionEnter((char *)this + 24);
  v10 = StringCchPrintfW(v46, 0x104u, L"%ls\\%ls", *(_QWORD *)this, L"AppCs");
  v11 = 0;
  if ( v10 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_Ds(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        11,
        (unsigned int)WPP_202f566a5b6b3eebbc58311978cd75bc_Traceguids,
        v10,
        (__int64)"FwMoneisAppContainerSetConfig::StringCchPrintf");
    goto LABEL_77;
  }
  if ( (_DWORD)v7 )
  {
    while ( RtlValidSid(a2[v11].Sid)
         && RtlEqualSid(Sid, a2[v11].Sid) != 1
         && (unsigned __int8)RtlIsCapabilitySid(a2[v11].Sid) != 1 )
    {
      if ( ++v11 >= (unsigned int)v7 )
      {
        v3 = 0;
        goto LABEL_11;
      }
    }
    v11 = 87;
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_77;
    v14 = 12;
    v15 = 87;
LABEL_18:
    WPP_SF_d(*(_QWORD *)(v13 + 16), v14, WPP_202f566a5b6b3eebbc58311978cd75bc_Traceguids, v15);
    goto LABEL_77;
  }
LABEL_11:
  v12 = FwSidAndAttributesCopy((unsigned int)v7, a2, &Base);
  v11 = v12;
  if ( v12 )
  {
    v4 = v7;
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_77;
    v14 = 13;
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
  v11 = v19;
  if ( v19 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_77;
    v14 = 14;
    v15 = v19;
    goto LABEL_18;
  }
  v20 = FwRegSetString(-2147483646, v46, L"DebugedLoopbackApps", v45);
  v21 = FwHResultToWindowsError(v20);
  v11 = v21;
  if ( v21 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_77;
    v14 = 15;
    v15 = v21;
    goto LABEL_18;
  }
  v22 = *((_DWORD *)this + 2);
  v23 = FwSidAndAttributesCopy(v22, *((_QWORD *)this + 2), &v44);
  v11 = v23;
  if ( v23 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_77;
    v14 = 16;
    v15 = v23;
    goto LABEL_18;
  }
  FwSidAndAttributesFree(*((unsigned int *)this + 2), *((_QWORD *)this + 2));
  v24 = Base;
  *((_DWORD *)this + 2) = v4;
  v4 = 0;
  *((_QWORD *)this + 2) = v24;
  Base = 0;
  FwCriticalSectionLeave((char *)this + 24);
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
      WPP_SF_d(*(_QWORD *)(v28 + 16), v29, WPP_3d9dabe50e6b3e70315acf6b635a3004_Traceguids, v30);
LABEL_67:
      v39 = pWriterModule;
      if ( *((_DWORD *)pWriterModule + 71) == 1 )
        (*(void (__fastcall **)(IPolicyWriter *, __int64))(*(_QWORD *)pWriterModule + 64LL))(
          pWriterModule,
          2147549183LL);
      *((_DWORD *)v39 + 71) = 0;
LABEL_70:
      FwUnlockInternal(0, "FwProfileMgrAppIsolationAppContainerConfigOnlyTransaction");
      v9 = (char *)this + 24;
      v8 = (char *)this + 88;
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
    WPP_SF_d(*(_QWORD *)(v28 + 16), v36, WPP_9246bb9fff193791a74cbfd2838cb9b7_Traceguids, (unsigned int)updated);
    v28 = WPP_GLOBAL_Control;
    goto LABEL_52;
  }
LABEL_71:
  v40 = FwHResultToWindowsError((unsigned int)v25);
  v11 = v40;
  if ( !v40 )
    goto LABEL_78;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_202f566a5b6b3eebbc58311978cd75bc_Traceguids, v40);
  FwCriticalSectionLeave(v9);
  v41 = v44;
  *((_DWORD *)this + 2) = v22;
  FwSidAndAttributesCopy(v22, v41, (char *)this + 16);
  if ( v44 )
    FwSidAndAttributesFree(v22, v44);
LABEL_77:
  FwCriticalSectionLeave(v9);
LABEL_78:
  FwCriticalSectionLeave(v8);
  FwFree(v45);
  if ( Base )
    FwSidAndAttributesFree(v4, Base);
  return v11;
}

```

## disassembly

```asm
0x1800ba820  mov     r11, rsp
0x1800ba823  push    rbx
0x1800ba824  push    rbp
0x1800ba825  sub     rsp, 298h
0x1800ba82c  mov     rax, cs:__security_cookie
0x1800ba833  xor     rax, rsp
0x1800ba836  mov     [rsp+2A8h+var_48], rax
0x1800ba83e  mov     [r11+20h], rsi
0x1800ba842  mov     [r11-18h], rdi
0x1800ba846  xor     edi, edi
0x1800ba848  mov     [r11-20h], r12
0x1800ba84c  mov     ebp, edi
0x1800ba84e  mov     [r11-28h], r13
0x1800ba852  mov     [r11-30h], r14
0x1800ba856  mov     r14, rdx
0x1800ba859  mov     [r11-38h], r15
0x1800ba85d  xor     edx, edx; Val
0x1800ba85f  mov     r15, rcx
0x1800ba862  mov     esi, r8d
0x1800ba865  lea     rcx, [rsp+2A8h+var_258]; void *
0x1800ba86a  mov     [rsp+2A8h+Base], rdi
0x1800ba86f  mov     r8d, 208h; Size
0x1800ba875  mov     [rsp+2A8h+var_270], rdi
0x1800ba87a  mov     [rsp+2A8h+var_268], rdi
0x1800ba87f  call    memset_0
0x1800ba884  lea     r13, [r15+58h]
0x1800ba888  mov     rcx, r13
0x1800ba88b  call    cs:__imp_FwCriticalSectionEnter
0x1800ba892  nop     dword ptr [rax+rax+00h]
0x1800ba897  lea     r12, [r15+18h]
0x1800ba89b  mov     rcx, r12
0x1800ba89e  call    cs:__imp_FwCriticalSectionEnter
0x1800ba8a5  nop     dword ptr [rax+rax+00h]
0x1800ba8aa  mov     r9, [r15]
0x1800ba8ad  lea     rax, aAppcs; "AppCs"
0x1800ba8b4  lea     r8, aLsLs; "%ls\\%ls"
0x1800ba8bb  mov     [rsp+2A8h+var_288], rax
0x1800ba8c0  mov     edx, 104h; unsigned __int64
0x1800ba8c5  lea     rcx, [rsp+2A8h+var_258]; unsigned __int16 *
0x1800ba8ca  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ba8cf  mov     ebx, edi
0x1800ba8d1  test    eax, eax
0x1800ba8d3  jns     short loc_1800BA91F
0x1800ba8d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba8dc  lea     rdi, WPP_GLOBAL_Control
0x1800ba8e3  cmp     rcx, rdi
0x1800ba8e6  jz      loc_1800BAE58
0x1800ba8ec  test    byte ptr [rcx+1Ch], 1
0x1800ba8f0  jz      loc_1800BAE58
0x1800ba8f6  mov     rcx, [rcx+10h]
0x1800ba8fa  lea     r8, aFwmoneisappcon; "FwMoneisAppContainerSetConfig::StringCc"...
0x1800ba901  mov     [rsp+2A8h+var_288], r8
0x1800ba906  mov     edx, 0Bh
0x1800ba90b  lea     r8, WPP_202f566a5b6b3eebbc58311978cd75bc_Traceguids
0x1800ba912  mov     r9d, eax
0x1800ba915  call    WPP_SF_Ds
0x1800ba91a  jmp     loc_1800BAE58
0x1800ba91f  test    esi, esi
0x1800ba921  jz      short loc_1800BA977
0x1800ba923  mov     edi, ebx
0x1800ba925  add     rdi, rdi
0x1800ba928  mov     rcx, [r14+rdi*8]; Sid
0x1800ba92c  call    cs:__imp_RtlValidSid
0x1800ba933  nop     dword ptr [rax+rax+00h]
0x1800ba938  test    al, al
0x1800ba93a  jz      loc_1800BA9C0
0x1800ba940  mov     rdx, [r14+rdi*8]; Sid2
0x1800ba944  mov     rcx, cs:Sid; Sid1
0x1800ba94b  call    cs:__imp_RtlEqualSid
0x1800ba952  nop     dword ptr [rax+rax+00h]
0x1800ba957  cmp     al, 1
0x1800ba959  jz      short loc_1800BA9C0
0x1800ba95b  mov     rcx, [r14+rdi*8]
0x1800ba95f  call    cs:__imp_RtlIsCapabilitySid
0x1800ba966  nop     dword ptr [rax+rax+00h]
0x1800ba96b  cmp     al, 1
0x1800ba96d  jz      short loc_1800BA9C0
0x1800ba96f  inc     ebx
0x1800ba971  cmp     ebx, esi
0x1800ba973  jb      short loc_1800BA923
0x1800ba975  xor     edi, edi
0x1800ba977  lea     r8, [rsp+2A8h+Base]
0x1800ba97c  mov     rdx, r14
0x1800ba97f  mov     ecx, esi
0x1800ba981  call    cs:__imp_FwSidAndAttributesCopy
0x1800ba988  nop     dword ptr [rax+rax+00h]
0x1800ba98d  mov     ebx, eax
0x1800ba98f  test    eax, eax
0x1800ba991  jz      short loc_1800BAA03
0x1800ba993  mov     ebp, esi
0x1800ba995  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba99c  lea     rdi, WPP_GLOBAL_Control
0x1800ba9a3  cmp     rcx, rdi
0x1800ba9a6  jz      loc_1800BAE58
0x1800ba9ac  test    byte ptr [rcx+1Ch], 1
0x1800ba9b0  jz      loc_1800BAE58
0x1800ba9b6  mov     edx, 0Dh
0x1800ba9bb  mov     r9d, eax
0x1800ba9be  jmp     short loc_1800BA9EE
0x1800ba9c0  mov     ebx, 57h ; 'W'
0x1800ba9c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba9cc  lea     rdi, WPP_GLOBAL_Control
0x1800ba9d3  cmp     rcx, rdi
0x1800ba9d6  jz      loc_1800BAE58
0x1800ba9dc  test    byte ptr [rcx+1Ch], 1
0x1800ba9e0  jz      loc_1800BAE58
0x1800ba9e6  mov     edx, 0Ch
0x1800ba9eb  mov     r9d, ebx
0x1800ba9ee  mov     rcx, [rcx+10h]
0x1800ba9f2  lea     r8, WPP_202f566a5b6b3eebbc58311978cd75bc_Traceguids
0x1800ba9f9  call    WPP_SF_d
0x1800ba9fe  jmp     loc_1800BAE58
0x1800baa03  mov     rbp, [rsp+2A8h+Base]
0x1800baa08  lea     r9, ?FwSidAndAttribCompare@@YAHPEBU_SID_AND_ATTRIBUTES@@0@Z; CompareFunction
0x1800baa0f  mov     rcx, rbp; Base
0x1800baa12  mov     rdx, rsi; NumOfElements
0x1800baa15  mov     r8d, 10h; SizeOfElements
0x1800baa1b  call    cs:__imp_qsort
0x1800baa22  nop     dword ptr [rax+rax+00h]
0x1800baa27  mov     ebx, 1
0x1800baa2c  cmp     esi, ebx
0x1800baa2e  jbe     short loc_1800BAA6D
0x1800baa30  mov     r14d, ebx
0x1800baa33  mov     ecx, edi
0x1800baa35  add     r14, r14
0x1800baa38  add     rcx, rcx
0x1800baa3b  mov     rdx, [rbp+r14*8+0]; Sid2
0x1800baa40  mov     rcx, [rbp+rcx*8+0]; Sid1
0x1800baa45  call    cs:__imp_RtlEqualSid
0x1800baa4c  nop     dword ptr [rax+rax+00h]
0x1800baa51  test    al, al
0x1800baa53  jnz     short loc_1800BAA67
0x1800baa55  movups  xmm0, xmmword ptr [rbp+r14*8+0]
0x1800baa5b  inc     edi
0x1800baa5d  mov     eax, edi
0x1800baa5f  add     rax, rax
0x1800baa62  movups  xmmword ptr [rbp+rax*8+0], xmm0
0x1800baa67  inc     ebx
0x1800baa69  cmp     ebx, esi
0x1800baa6b  jb      short loc_1800BAA30
0x1800baa6d  mov     rdx, [rsp+2A8h+Base]
0x1800baa72  lea     ebp, [rdi+1]
0x1800baa75  test    esi, esi
0x1800baa77  lea     r8, [rsp+2A8h+var_268]
0x1800baa7c  cmovz   ebp, edi
0x1800baa7f  mov     ecx, ebp
0x1800baa81  call    cs:__imp_FwSidsToString
0x1800baa88  nop     dword ptr [rax+rax+00h]
0x1800baa8d  mov     ecx, eax
0x1800baa8f  call    cs:__imp_FwHResultToWindowsError
0x1800baa96  nop     dword ptr [rax+rax+00h]
0x1800baa9b  mov     ebx, eax
0x1800baa9d  test    eax, eax
0x1800baa9f  jz      short loc_1800BAACF
0x1800baaa1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800baaa8  lea     rdi, WPP_GLOBAL_Control
0x1800baaaf  cmp     rcx, rdi
0x1800baab2  jz      loc_1800BAE58
0x1800baab8  test    byte ptr [rcx+1Ch], 1
0x1800baabc  jz      loc_1800BAE58
0x1800baac2  mov     edx, 0Eh
0x1800baac7  mov     r9d, eax
0x1800baaca  jmp     loc_1800BA9EE
0x1800baacf  mov     r9, [rsp+2A8h+var_268]
0x1800baad4  lea     r8, aDebugedloopbac; "DebugedLoopbackApps"
0x1800baadb  lea     rdx, [rsp+2A8h+var_258]
0x1800baae0  mov     rcx, 0FFFFFFFF80000002h
0x1800baae7  call    cs:__imp_FwRegSetString
0x1800baaee  nop     dword ptr [rax+rax+00h]
0x1800baaf3  mov     ecx, eax
0x1800baaf5  call    cs:__imp_FwHResultToWindowsError
0x1800baafc  nop     dword ptr [rax+rax+00h]
0x1800bab01  mov     ebx, eax
0x1800bab03  test    eax, eax
0x1800bab05  jz      short loc_1800BAB35
0x1800bab07  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bab0e  lea     rdi, WPP_GLOBAL_Control
0x1800bab15  cmp     rcx, rdi
0x1800bab18  jz      loc_1800BAE58
0x1800bab1e  test    byte ptr [rcx+1Ch], 1
0x1800bab22  jz      loc_1800BAE58
0x1800bab28  mov     edx, 0Fh
0x1800bab2d  mov     r9d, eax
0x1800bab30  jmp     loc_1800BA9EE
0x1800bab35  mov     r14d, [r15+8]
0x1800bab39  lea     r8, [rsp+2A8h+var_270]
0x1800bab3e  mov     rdx, [r15+10h]
0x1800bab42  mov     ecx, r14d
0x1800bab45  call    cs:__imp_FwSidAndAttributesCopy
0x1800bab4c  nop     dword ptr [rax+rax+00h]
0x1800bab51  mov     ebx, eax
0x1800bab53  test    eax, eax
0x1800bab55  jz      short loc_1800BAB85
0x1800bab57  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bab5e  lea     rdi, WPP_GLOBAL_Control
0x1800bab65  cmp     rcx, rdi
0x1800bab68  jz      loc_1800BAE58
0x1800bab6e  test    byte ptr [rcx+1Ch], 1
0x1800bab72  jz      loc_1800BAE58
0x1800bab78  mov     edx, 10h
0x1800bab7d  mov     r9d, eax
0x1800bab80  jmp     loc_1800BA9EE
0x1800bab85  mov     rdx, [r15+10h]
0x1800bab89  mov     ecx, [r15+8]
0x1800bab8d  call    cs:__imp_FwSidAndAttributesFree
0x1800bab94  nop     dword ptr [rax+rax+00h]
0x1800bab99  mov     rax, [rsp+2A8h+Base]
0x1800bab9e  mov     rcx, r12
0x1800baba1  mov     [r15+8], ebp
0x1800baba5  xor     ebp, ebp
0x1800baba7  mov     [r15+10h], rax
0x1800babab  mov     [rsp+2A8h+Base], rbp
0x1800babb0  call    cs:__imp_FwCriticalSectionLeave
0x1800babb7  nop     dword ptr [rax+rax+00h]
0x1800babbc  call    FwLock
0x1800babc1  lea     rdi, WPP_GLOBAL_Control
0x1800babc8  mov     esi, eax
0x1800babca  test    eax, eax
0x1800babcc  js      loc_1800BADD2
0x1800babd2  mov     rbx, cs:pWriterModule
0x1800babd9  mov     rcx, rbx
0x1800babdc  mov     rax, [rbx]
0x1800babdf  mov     rax, [rax+10h]
0x1800babe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800babe8  mov     dword ptr [rbx+11Ch], 1
0x1800babf2  mov     esi, eax
0x1800babf4  test    eax, eax
0x1800babf6  jns     short loc_1800BAC1F
0x1800babf8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800babff  cmp     rcx, rdi
0x1800bac02  jz      loc_1800BAD92
0x1800bac08  test    byte ptr [rcx+1Ch], 1
0x1800bac0c  jz      loc_1800BAD92
0x1800bac12  mov     edx, 64h ; 'd'
0x1800bac17  mov     r9d, eax
0x1800bac1a  jmp     loc_1800BAD82
0x1800bac1f  mov     rcx, cs:pWriterModule; this
0x1800bac26  call    ?WriteAppCConfiguration@IPolicyWriter@@QEAAJXZ; IPolicyWriter::WriteAppCConfiguration(void)
0x1800bac2b  mov     esi, eax
0x1800bac2d  test    eax, eax
0x1800bac2f  jns     short loc_1800BAC58
0x1800bac31  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bac38  cmp     rcx, rdi
0x1800bac3b  jz      loc_1800BAD92
0x1800bac41  test    byte ptr [rcx+1Ch], 1
0x1800bac45  jz      loc_1800BAD92
0x1800bac4b  mov     edx, 65h ; 'e'
0x1800bac50  mov     r9d, eax
0x1800bac53  jmp     loc_1800BAD82
0x1800bac58  mov     rsi, cs:pWriterModule
0x1800bac5f  xor     ebx, ebx
0x1800bac61  mov     rcx, rsi
0x1800bac64  mov     rax, [rsi]
0x1800bac67  mov     rax, [rax+0C8h]
0x1800bac6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bac73  mov     rcx, [rsi]
0x1800bac76  mov     r12d, eax
0x1800bac79  mov     rax, [rcx+0B8h]
0x1800bac80  mov     rcx, rsi
0x1800bac83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bac88  mov     rcx, [rsi]
0x1800bac8b  mov     r13d, eax
0x1800bac8e  mov     rax, [rcx+0B0h]
0x1800bac95  mov     rcx, rsi
0x1800bac98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bac9d  cmp     eax, 1
0x1800baca0  jnz     short loc_1800BACE8
0x1800baca2  mov     rcx, rsi; this
0x1800baca5  call    ?WriteAppCConfiguration@IPolicyWriter@@QEAAJXZ; IPolicyWriter::WriteAppCConfiguration(void)
0x1800bacaa  mov     ebx, eax
0x1800bacac  test    eax, eax
0x1800bacae  jns     short loc_1800BACE8
0x1800bacb0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bacb7  cmp     rcx, rdi
0x1800bacba  jz      short loc_1800BACE1
0x1800bacbc  test    byte ptr [rcx+1Ch], 1
0x1800bacc0  jz      short loc_1800BACE1
0x1800bacc2  mov     edx, 16h
0x1800bacc7  mov     rcx, [rcx+10h]
0x1800baccb  lea     r8, WPP_9246bb9fff193791a74cbfd2838cb9b7_Traceguids
0x1800bacd2  mov     r9d, ebx
0x1800bacd5  call    WPP_SF_d
0x1800bacda  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bace1  mov     esi, ebx
0x1800bace3  jmp     loc_1800BAD6F
0x1800bace8  test    r12d, r12d
0x1800baceb  jnz     short loc_1800BACF3
0x1800baced  cmp     r13d, 1
0x1800bacf1  jnz     short loc_1800BAD40
0x1800bacf3  mov     rax, [rsi]
0x1800bacf6  mov     rcx, rsi
0x1800bacf9  mov     rbx, cs:g_pCurrentBatch
0x1800bad00  mov     rax, [rax+0D0h]
0x1800bad07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bad0c  xor     ecx, ecx
0x1800bad0e  mov     r9, rbx
0x1800bad11  test    r12d, r12d
0x1800bad14  mov     r8d, r13d
0x1800bad17  mov     edx, eax
0x1800bad19  setnz   cl
  ... truncated ...
```
