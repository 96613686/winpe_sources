# DXGSESSIONDATA::DXGSESSIONDATA(ulong)

- ea: `0x140260c54`
- end: `0x140261478`
- name: `??0DXGSESSIONDATA@@QEAA@K@Z`
- size: `2084`
- prototype: `DXGSESSIONDATA *__fastcall(DXGSESSIONDATA *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1403e02d8`

## callees

- `0x140012380`
- `0x14001b890`
- `0x14002e110`
- `0x14004afe0`
- `0x14004db04`
- `0x14007b5a8`
- `0x1400a01e0`
- `0x1400a0540`
- `0x14024a028`
- `0x140260c54`
- `0x140323854`
- `0x1403e5dcc`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14026122e`
- `ntoskrnl!PsGetCurrentProcess` at `0x14026122e`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140261080`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1402610e9`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140261322`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140261080`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1402610e9`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140261322`
- `ntoskrnl!ObfReferenceObject` at `0x140261244`
- `ntoskrnl!ObfReferenceObject` at `0x140261411`
- `ntoskrnl!ObfReferenceObject` at `0x140261244`
- `ntoskrnl!ObfReferenceObject` at `0x140261411`
- `ntoskrnl!ZwClose` at `0x140261422`
- `ntoskrnl!ZwClose` at `0x140261422`
- `ntoskrnl!RtlInitUnicodeString` at `0x140260fbd`
- `ntoskrnl!RtlInitUnicodeString` at `0x140260fbd`
- `ntoskrnl!IoCreateNotificationEvent` at `0x14026137f`
- `ntoskrnl!IoCreateNotificationEvent` at `0x14026137f`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1402612f7`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140261333`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1402612f7`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140261333`
- `ntoskrnl!PsGetHostSilo` at `0x1402612e8`
- `ntoskrnl!PsGetHostSilo` at `0x1402612e8`
- `ntoskrnl!ZwQueryLicenseValue` at `0x140260fe9`
- `ntoskrnl!ZwQueryLicenseValue` at `0x140260fe9`
- `ntoskrnl!RtlGetSuiteMask` at `0x140260f7b`
- `ntoskrnl!RtlGetSuiteMask` at `0x140260f7b`
- `ntoskrnl!RtlGetNtProductType` at `0x140260f6f`
- `ntoskrnl!RtlGetNtProductType` at `0x140260f6f`
- `ntoskrnl!RtlInitializeBitMap` at `0x140261454`
- `ntoskrnl!RtlInitializeBitMap` at `0x140261454`
- `ntoskrnl!PsIsHostSilo` at `0x14026127c`
- `ntoskrnl!PsIsHostSilo` at `0x14026127c`
- `ntoskrnl!PsGetProcessServerSilo` at `0x14026126d`
- `ntoskrnl!PsGetProcessServerSilo` at `0x14026126d`
- `ntoskrnl!KeSetEvent` at `0x1402613fe`
- `ntoskrnl!KeSetEvent` at `0x1402613fe`
- `watchdog!WdLogSingleEntry2` at `0x14026117d`
- `watchdog!WdLogSingleEntry2` at `0x14026117d`
- `watchdog!WdLogSingleEntry1` at `0x14026139d`
- `watchdog!WdLogSingleEntry1` at `0x14026139d`

## string_xrefs

- `0x140260fa6`: `TerminalServices-RemoteConnectionManager-WVD-Enabled`
- `0x140261058`: `\Registry\Machine\SOFTWARE\Policies\Microsoft\Windows NT\Terminal Services`
- `0x1402610c1`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\Terminal Server\WinStations`
- `0x1402613ae`: `Failed to create PnP event object for session 0x%I64x.`

## pseudocode

```c
DXGSESSIONDATA *__fastcall DXGSESSIONDATA::DXGSESSIONDATA(DXGSESSIONDATA *this, unsigned int a2)
{
  __int64 v2; // r15
  char *v3; // r12
  char *v4; // r13
  DispBrokerClientReference *v6; // rcx
  __int64 v7; // rax
  OUTPUTDUPL_SESSION_MGR *v8; // rbx
  unsigned int v9; // edx
  OUTPUTDUPL_SESSION_MGR *v10; // rcx
  struct DXGPROCESS *Current; // rax
  _QWORD *v12; // r14
  __int64 (__fastcall *v13)(_DWORD *); // rax
  int v14; // eax
  __int64 v15; // rbx
  __int64 (*v16)(void); // rax
  __int64 (*v17)(void); // rax
  struct DXGPROCESS *v18; // rax
  void *CurrentProcess; // rax
  __int64 ProcessServerSilo; // rax
  char IsHostSilo; // al
  __int64 HostSilo; // rax
  __int64 v23; // rdi
  int v24; // ebx
  struct _KEVENT *v25; // rax
  int v27; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+54h] [rbp-ACh] BYREF
  void *EventHandle; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v30[2]; // [rsp+60h] [rbp-A0h] BYREF
  char *v31; // [rsp+68h] [rbp-98h]
  __int64 v32; // [rsp+70h] [rbp-90h] BYREF
  int v33; // [rsp+78h] [rbp-88h]
  const wchar_t *v34; // [rsp+80h] [rbp-80h]
  int *v35; // [rsp+88h] [rbp-78h]
  int v36; // [rsp+90h] [rbp-70h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  int v38; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  int v40; // [rsp+B0h] [rbp-50h]
  __int64 v41; // [rsp+B8h] [rbp-48h]
  __int128 v42; // [rsp+C0h] [rbp-40h]
  __int128 v43; // [rsp+D0h] [rbp-30h]
  struct _UNICODE_STRING DestinationString; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v45; // [rsp+F0h] [rbp-10h] BYREF
  int v46; // [rsp+F8h] [rbp-8h]
  const wchar_t *v47; // [rsp+100h] [rbp+0h]
  int *v48; // [rsp+108h] [rbp+8h]
  int v49; // [rsp+110h] [rbp+10h]
  __int64 v50; // [rsp+118h] [rbp+18h]
  int v51; // [rsp+120h] [rbp+20h]
  __int64 v52; // [rsp+128h] [rbp+28h]
  int v53; // [rsp+130h] [rbp+30h]
  __int64 v54; // [rsp+138h] [rbp+38h]
  __int128 v55; // [rsp+140h] [rbp+40h]
  __int128 v56; // [rsp+150h] [rbp+50h]
  int v57; // [rsp+1B0h] [rbp+B0h] BYREF
  char v58; // [rsp+1B8h] [rbp+B8h] BYREF
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+1C0h] [rbp+C0h] BYREF
  int v60; // [rsp+1C8h] [rbp+C8h] BYREF

  v2 = a2;
  *(_DWORD *)this = a2;
  v3 = (char *)this + 18752;
  *((_QWORD *)this + 3) = 0;
  v4 = (char *)this + 18792;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_DWORD *)this + 13) = -1;
  *((_DWORD *)this + 14) = 78;
  *((_DWORD *)this + 4624) = 0;
  *((_WORD *)this + 9250) = 0;
  *((_BYTE *)this + 18503) = 0;
  *((_DWORD *)this + 4632) = 0;
  *((_QWORD *)this + 2317) = 0;
  *((_QWORD *)this + 2318) = 0;
  *((_QWORD *)this + 2319) = 0;
  *((_QWORD *)this + 2320) = 0;
  *((_DWORD *)this + 4642) = 0;
  *((_DWORD *)this + 4643) = 61;
  *((_DWORD *)this + 4644) = 61;
  *((_DWORD *)this + 4660) = 0;
  *((_QWORD *)this + 2331) = 0;
  *((_QWORD *)this + 2335) = 0;
  *((_QWORD *)this + 2336) = 0;
  *((_QWORD *)this + 2337) = 0;
  *((_DWORD *)this + 4676) = 0;
  *((_DWORD *)this + 4677) = 81;
  *((_DWORD *)this + 4678) = 1;
  *((_QWORD *)this + 2340) = 0;
  *((_QWORD *)this + 2341) = 0;
  *((_QWORD *)this + 2345) = 0;
  *((_QWORD *)this + 2346) = 0;
  *((_DWORD *)this + 4694) = 4;
  *((_QWORD *)this + 2348) = (char *)this + 18792;
  *((_QWORD *)this + 2344) = 0;
  *((_QWORD *)this + 2366) = 0;
  *((_QWORD *)this + 2367) = 0;
  *((_QWORD *)this + 2368) = 0;
  *((_DWORD *)this + 4738) = 0;
  *((_DWORD *)this + 4739) = -1;
  *((_DWORD *)this + 4740) = 72;
  *((_DWORD *)this + 4742) = 0;
  *((_QWORD *)this + 2372) = 0;
  *((_QWORD *)this + 2373) = 0;
  *((_WORD *)this + 9496) = 0;
  *((_QWORD *)this + 2375) = 0;
  *((_QWORD *)this + 2376) = 0;
  *((_DWORD *)this + 4754) = 0;
  *((_DWORD *)this + 4755) = 1;
  *((_DWORD *)this + 4756) = -1;
  v6 = (DXGSESSIONDATA *)((char *)this + 19032);
  *(_QWORD *)v6 = 0;
  DispBrokerClientReference::Assign(v6, 0);
  *((_QWORD *)this + 2381) = 0;
  *((_QWORD *)this + 2382) = 0;
  *((_QWORD *)this + 2383) = 0;
  *((_DWORD *)this + 4768) = 0;
  *((_DWORD *)this + 4769) = -1;
  *((_DWORD *)this + 4770) = 1;
  *((_QWORD *)this + 2386) = 0;
  *((_QWORD *)this + 2387) = 0;
  *((_BYTE *)this + 19104) = 0;
  *((_QWORD *)this + 2391) = 0;
  *((_QWORD *)this + 2392) = 0;
  *((_QWORD *)this + 2393) = 0;
  *((_DWORD *)this + 4788) = 0;
  *((_DWORD *)this + 4789) = -1;
  *((_DWORD *)this + 4790) = 1;
  *((_QWORD *)this + 2396) = 0;
  *((_DWORD *)this + 4794) = 0;
  *((_DWORD *)this + 4795) = 1;
  *((_QWORD *)this + 2398) = 0;
  *((_QWORD *)this + 2400) = 0;
  *((_QWORD *)this + 2401) = 0;
  *((_QWORD *)this + 2402) = 0;
  *((_DWORD *)this + 4806) = 0;
  *((_DWORD *)this + 4807) = -1;
  *((_DWORD *)this + 4808) = 1;
  *((_QWORD *)this + 2408) = 0;
  *((_QWORD *)this + 2409) = 0;
  *((_DWORD *)this + 4820) = 0;
  *((_DWORD *)this + 4821) = 64;
  *((_DWORD *)this + 4822) = 67;
  ProductType = 0;
  v7 = operator new(520, 1733117007, 256);
  v8 = (OUTPUTDUPL_SESSION_MGR *)v7;
  if ( v7 )
  {
    *(_DWORD *)(v7 + 4) = 0;
    *(_QWORD *)(v7 + 16) = 0;
    *(_QWORD *)(v7 + 24) = 0;
    *(_QWORD *)(v7 + 32) = 0;
    *(_DWORD *)(v7 + 40) = 0;
    *(_DWORD *)(v7 + 48) = 78;
    *(_DWORD *)(v7 + 44) = 43;
    *(_QWORD *)(v7 + 56) = 0;
    *(_DWORD *)(v7 + 64) = 0;
    *(_QWORD *)(v7 + 80) = 0;
    *(_QWORD *)(v7 + 88) = 0;
    *(_DWORD *)(v7 + 112) = 78;
    *(_QWORD *)(v7 + 96) = 0;
    *(_DWORD *)(v7 + 104) = 0;
    *(_DWORD *)(v7 + 108) = 43;
    *(_QWORD *)(v7 + 120) = 0;
    OUTPUTDUPL_SESSION_MGR::InitializeMaxActiveOutputDuplApps((OUTPUTDUPL_SESSION_MGR *)v7);
    *((_DWORD *)v8 + 32) = 0;
  }
  else
  {
    v8 = 0;
  }
  *((_QWORD *)this + 1) = v8;
  if ( v8 && (int)OUTPUTDUPL_SESSION_MGR::Initialize(v8) < 0 )
  {
    v10 = (OUTPUTDUPL_SESSION_MGR *)*((_QWORD *)this + 1);
    if ( v10 )
      OUTPUTDUPL_SESSION_MGR::`scalar deleting destructor'(v10, v9);
    *((_QWORD *)this + 1) = 0;
  }
  *((_QWORD *)this + 2324) = (char *)this + 18584;
  *((_QWORD *)this + 2323) = (char *)this + 18584;
  *((_QWORD *)this + 2326) = (char *)this + 18600;
  *((_QWORD *)this + 2325) = (char *)this + 18600;
  *((_QWORD *)this + 2328) = (char *)this + 18616;
  *((_QWORD *)this + 2327) = (char *)this + 18616;
  RtlGetNtProductType(&ProductType);
  RtlGetSuiteMask();
  *((_BYTE *)this + 18505) = ProductType != NtProductServer
                          || !g_bSkuSupportMultipleUsers
                          || (v60 = 0,
                              v27 = 0,
                              v28 = 0,
                              DestinationString = 0,
                              RtlInitUnicodeString(
                                &DestinationString,
                                L"TerminalServices-RemoteConnectionManager-WVD-Enabled"),
                              (int)ZwQueryLicenseValue(&DestinationString, &v27, &v28, 4, &v60) >= 0)
                          && v60 == 4
                          && v27 == 4
                          && v28;
  v57 = 0;
  v45 = 0;
  v47 = L"bEnumerateHWBeforeSW";
  v46 = 292;
  v48 = &v57;
  v49 = 0x4000000;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  if ( (int)RtlQueryRegistryValuesEx(
              0,
              L"\\Registry\\Machine\\SOFTWARE\\Policies\\Microsoft\\Windows NT\\Terminal Services",
              &v45,
              0,
              0) >= 0 )
    goto LABEL_19;
  v32 = 0;
  v33 = 292;
  v34 = L"fUseHardwareGPU";
  v36 = 0x4000000;
  v35 = &v57;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  if ( (int)RtlQueryRegistryValuesEx(
              0,
              L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
              &v32,
              0,
              0) >= 0 )
LABEL_19:
    *((_BYTE *)this + 18505) = v57 != 0;
  v58 = 0;
  *(_QWORD *)((char *)this + 18508) = 0;
  v31 = &v58;
  *((_DWORD *)this + 4629) = 0;
  *((_QWORD *)this + 2315) = 0;
  v30[0] = 3;
  v30[1] = 1;
  Current = DXGPROCESS::GetCurrent();
  if ( Current )
  {
    v12 = (_QWORD *)*((_QWORD *)Current + 11);
    if ( v12 && (v13 = (__int64 (__fastcall *)(_DWORD *))v12[46]) != 0 && (v14 = v13(v30), v14 < 0) )
    {
      v15 = v14;
      WdLogSingleEntry2(2, v2);
      WdLogGlobalForLineNumber = 3422;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Failed to get session TTM support in session 0x%I64x (Status = 0x%I64x).",
        v2,
        v15,
        0,
        0,
        0);
      v58 = 0;
      *((_BYTE *)this + 18497) = 0;
    }
    else
    {
      *((_BYTE *)this + 18497) = v58;
      if ( !v12 )
        goto LABEL_30;
    }
    v16 = (__int64 (*)(void))v12[44];
    if ( v16 )
      *((_QWORD *)this + 2317) = v16();
    v17 = (__int64 (*)(void))v12[50];
    if ( v17 )
      *((_QWORD *)this + 2318) = v17();
  }
  else
  {
    *((_BYTE *)this + 18497) = v58;
  }
LABEL_30:
  v18 = DXGPROCESS::GetCurrent();
  *((_QWORD *)this + 2333) = v18;
  *((_DWORD *)v18 + 102) |= 1u;
  CurrentProcess = (void *)PsGetCurrentProcess();
  *((_QWORD *)this + 2332) = CurrentProcess;
  ObfReferenceObject(CurrentProcess);
  if ( *((_QWORD *)DXGGLOBAL::GetGlobal() + 38121) )
    CreateTokenManagerSessionGlobal(v3);
  ProcessServerSilo = PsGetProcessServerSilo(*((_QWORD *)this + 2332));
  IsHostSilo = PsIsHostSilo(ProcessServerSilo);
  *((_BYTE *)this + 18502) = IsHostSilo == 0;
  if ( !IsHostSilo )
  {
    v60 = 0;
    v32 = 0;
    v34 = L"DisableContainerSessionVersionCheck";
    v35 = &v60;
    v33 = 292;
    v36 = 67108868;
    v37 = 0;
    v38 = 0;
    v39 = 0;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    HostSilo = PsGetHostSilo();
    v23 = PsAttachSiloToCurrentThread(HostSilo);
    v24 = RtlQueryRegistryValuesEx(2, L"GraphicsDrivers", &v32, 0, 0);
    PsAttachSiloToCurrentThread(v23);
    if ( v24 < 0 || !v60 )
      *((_BYTE *)this + 18503) = 1;
  }
  *((_DWORD *)this + 4684) = 0;
  *((_QWORD *)this + 2343) = 0;
  *((_BYTE *)this + 18504) = 1;
  *((_QWORD *)this + 2373) = this;
  EventHandle = 0;
  v25 = IoCreateNotificationEvent(0, &EventHandle);
  *((_QWORD *)this + 2346) = v25;
  if ( v25 )
  {
    KeSetEvent(v25, 0, 0);
    ObfReferenceObject(*((PVOID *)this + 2346));
    ZwClose(EventHandle);
  }
  else
  {
    WdLogSingleEntry1(6);
    WdLogGlobalForLineNumber = 3517;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      -1,
      (unsigned int)L"Failed to create PnP event object for session 0x%I64x.",
      v2,
      0,
      0,
      0,
      0);
  }
  memset(v4, 0, 0x80u);
  *((_DWORD *)this + 4814) = 0;
  RtlInitializeBitMap((PRTL_BITMAP)((char *)this + 19240), (PULONG)this + 4814, 2u);
  return this;
}

```

## disassembly

```asm
0x140260c54  push    rbp
0x140260c56  push    rbx
0x140260c57  push    rsi
0x140260c58  push    rdi
0x140260c59  push    r12
0x140260c5b  push    r13
0x140260c5d  push    r14
0x140260c5f  push    r15
0x140260c61  lea     rbp, [rsp-68h]
0x140260c66  sub     rsp, 168h
0x140260c6d  xor     edi, edi
0x140260c6f  mov     r15d, edx
0x140260c72  mov     [rcx], r15d
0x140260c75  lea     r12, [rcx+4940h]
0x140260c7c  mov     [rcx+18h], rdi
0x140260c80  lea     r13, [rcx+4968h]
0x140260c87  mov     [rcx+20h], rdi
0x140260c8b  or      ebx, 0FFFFFFFFh
0x140260c8e  mov     [rcx+28h], rdi
0x140260c92  lea     eax, [rdi+3Dh]
0x140260c95  mov     [rcx+30h], edi
0x140260c98  lea     r14d, [rdi+1]
0x140260c9c  mov     [rcx+34h], ebx
0x140260c9f  mov     rsi, rcx
0x140260ca2  mov     dword ptr [rcx+38h], 4Eh ; 'N'
0x140260ca9  xor     edx, edx; struct DispBrokerClientHandle *
0x140260cab  mov     [rcx+4840h], edi
0x140260cb1  mov     [rcx+4844h], di
0x140260cb8  mov     [rcx+4847h], dil
0x140260cbf  mov     [rcx+4860h], edi
0x140260cc5  mov     [rcx+4868h], rdi
0x140260ccc  mov     [rcx+4870h], rdi
0x140260cd3  mov     [rcx+4878h], rdi
0x140260cda  mov     [rcx+4880h], rdi
0x140260ce1  mov     [rcx+4888h], edi
0x140260ce7  mov     [rcx+488Ch], eax
0x140260ced  mov     [rcx+4890h], eax
0x140260cf3  mov     [rcx+48D0h], edi
0x140260cf9  mov     [rcx+48D8h], rdi
0x140260d00  mov     [rcx+48F8h], rdi
0x140260d07  mov     [rcx+4900h], rdi
0x140260d0e  mov     [rcx+4908h], rdi
0x140260d15  mov     [rcx+4910h], edi
0x140260d1b  mov     dword ptr [rcx+4914h], 51h ; 'Q'
0x140260d25  mov     [rcx+4918h], r14d
0x140260d2c  mov     [rcx+4920h], rdi
0x140260d33  mov     [rcx+4928h], rdi
0x140260d3a  mov     [rcx+4948h], rdi
0x140260d41  mov     [rcx+4950h], rdi
0x140260d48  mov     dword ptr [rcx+4958h], 4
0x140260d52  mov     [rcx+4960h], r13
0x140260d59  mov     [r12], rdi
0x140260d5d  mov     [rcx+49F0h], rdi
0x140260d64  mov     [rcx+49F8h], rdi
0x140260d6b  mov     [rcx+4A00h], rdi
0x140260d72  mov     [rcx+4A08h], edi
0x140260d78  mov     [rcx+4A0Ch], ebx
0x140260d7e  mov     dword ptr [rcx+4A10h], 48h ; 'H'
0x140260d88  mov     [rcx+4A18h], edi
0x140260d8e  mov     [rcx+4A20h], rdi
0x140260d95  mov     [rcx+4A28h], rdi
0x140260d9c  mov     [rcx+4A30h], di
0x140260da3  mov     [rcx+4A38h], rdi
0x140260daa  mov     [rcx+4A40h], rdi
0x140260db1  mov     [rcx+4A48h], edi
0x140260db7  mov     [rcx+4A4Ch], r14d
0x140260dbe  mov     [rcx+4A50h], ebx
0x140260dc4  add     rcx, 4A58h; this
0x140260dcb  mov     [rcx], rdi
0x140260dce  call    ?Assign@DispBrokerClientReference@@QEAAXPEAVDispBrokerClientHandle@@@Z; DispBrokerClientReference::Assign(DispBrokerClientHandle *)
0x140260dd3  mov     [rsi+4A68h], rdi
0x140260dda  mov     [rsi+4A70h], rdi
0x140260de1  mov     [rsi+4A78h], rdi
0x140260de8  mov     [rsi+4A80h], edi
0x140260dee  mov     [rsi+4A84h], ebx
0x140260df4  mov     [rsi+4A88h], r14d
0x140260dfb  mov     [rsi+4A90h], rdi
0x140260e02  mov     [rsi+4A98h], rdi
0x140260e09  mov     [rsi+4AA0h], dil
0x140260e10  mov     [rsi+4AB8h], rdi
0x140260e17  mov     [rsi+4AC0h], rdi
0x140260e1e  mov     [rsi+4AC8h], rdi
0x140260e25  mov     [rsi+4AD0h], edi
0x140260e2b  mov     [rsi+4AD4h], ebx
0x140260e31  mov     [rsi+4AD8h], r14d
0x140260e38  mov     [rsi+4AE0h], rdi
0x140260e3f  mov     [rsi+4AE8h], edi
0x140260e45  mov     [rsi+4AECh], r14d
0x140260e4c  mov     [rsi+4AF0h], rdi
0x140260e53  mov     [rsi+4B00h], rdi
0x140260e5a  mov     [rsi+4B08h], rdi
0x140260e61  mov     [rsi+4B10h], rdi
0x140260e68  mov     edx, 674D444Fh
0x140260e6d  mov     [rsi+4B18h], edi
0x140260e73  mov     ecx, 208h
0x140260e78  mov     [rsi+4B1Ch], ebx
0x140260e7e  mov     r8d, 100h
0x140260e84  mov     [rsi+4B20h], r14d
0x140260e8b  mov     [rsi+4B40h], rdi
0x140260e92  mov     [rsi+4B48h], rdi
0x140260e99  mov     [rsi+4B50h], edi
0x140260e9f  mov     dword ptr [rsi+4B54h], 40h ; '@'
0x140260ea9  mov     dword ptr [rsi+4B58h], 43h ; 'C'
0x140260eb3  mov     [rbp+0A0h+ProductType], edi
0x140260eb9  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140260ebe  mov     rbx, rax
0x140260ec1  test    rax, rax
0x140260ec4  jz      short loc_140260F14
0x140260ec6  mov     [rax+4], edi
0x140260ec9  lea     ecx, [rdi+4Eh]
0x140260ecc  mov     [rax+10h], rdi
0x140260ed0  mov     [rax+18h], rdi
0x140260ed4  mov     [rax+20h], rdi
0x140260ed8  mov     [rax+28h], edi
0x140260edb  lea     eax, [rdi+2Bh]
0x140260ede  mov     [rbx+30h], ecx
0x140260ee1  mov     [rbx+2Ch], eax
0x140260ee4  mov     [rbx+38h], rdi
0x140260ee8  mov     [rbx+40h], edi
0x140260eeb  mov     [rbx+50h], rdi
0x140260eef  mov     [rbx+58h], rdi
0x140260ef3  mov     [rbx+70h], ecx
0x140260ef6  mov     rcx, rbx; this
0x140260ef9  mov     [rbx+60h], rdi
0x140260efd  mov     [rbx+68h], edi
0x140260f00  mov     [rbx+6Ch], eax
0x140260f03  mov     [rbx+78h], rdi
0x140260f07  call    ?InitializeMaxActiveOutputDuplApps@OUTPUTDUPL_SESSION_MGR@@AEAAXXZ; OUTPUTDUPL_SESSION_MGR::InitializeMaxActiveOutputDuplApps(void)
0x140260f0c  mov     [rbx+80h], edi
0x140260f12  jmp     short loc_140260F17
0x140260f14  mov     rbx, rdi
0x140260f17  mov     [rsi+8], rbx
0x140260f1b  test    rbx, rbx
0x140260f1e  jz      short loc_140260F3E
0x140260f20  mov     rcx, rbx; this
0x140260f23  call    ?Initialize@OUTPUTDUPL_SESSION_MGR@@QEAAJXZ; OUTPUTDUPL_SESSION_MGR::Initialize(void)
0x140260f28  test    eax, eax
0x140260f2a  jns     short loc_140260F3E
0x140260f2c  mov     rcx, [rsi+8]; this
0x140260f30  test    rcx, rcx
0x140260f33  jz      short loc_140260F3A
0x140260f35  call    ??_GOUTPUTDUPL_SESSION_MGR@@QEAAPEAXI@Z; OUTPUTDUPL_SESSION_MGR::`scalar deleting destructor'(uint)
0x140260f3a  mov     [rsi+8], rdi
0x140260f3e  lea     rax, [rsi+4898h]
0x140260f45  mov     [rax+8], rax
0x140260f49  lea     rcx, [rbp+0A0h+ProductType]; ProductType
0x140260f50  mov     [rax], rax
0x140260f53  lea     rax, [rsi+48A8h]
0x140260f5a  mov     [rax+8], rax
0x140260f5e  mov     [rax], rax
0x140260f61  lea     rax, [rsi+48B8h]
0x140260f68  mov     [rax+8], rax
0x140260f6c  mov     [rax], rax
0x140260f6f  call    cs:__imp_RtlGetNtProductType
0x140260f76  nop     dword ptr [rax+rax+00h]
0x140260f7b  call    cs:__imp_RtlGetSuiteMask
0x140260f82  nop     dword ptr [rax+rax+00h]
0x140260f87  cmp     [rbp+0A0h+ProductType], 3
0x140260f8e  jnz     loc_140261018
0x140260f94  cmp     cs:?g_bSkuSupportMultipleUsers@@3EA, dil; uchar g_bSkuSupportMultipleUsers
0x140260f9b  jz      short loc_140261018
0x140260f9d  xorps   xmm0, xmm0
0x140260fa0  mov     [rbp+0A0h+arg_18], edi
0x140260fa6  lea     rdx, aTerminalservic; "TerminalServices-RemoteConnectionManage"...
0x140260fad  mov     [rsp+1A0h+var_150], edi
0x140260fb1  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x140260fb5  mov     [rsp+1A0h+var_14C], edi
0x140260fb9  movups  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm0
0x140260fbd  call    cs:__imp_RtlInitUnicodeString
0x140260fc4  nop     dword ptr [rax+rax+00h]
0x140260fc9  lea     rax, [rbp+0A0h+arg_18]
0x140260fd0  mov     r9d, 4
0x140260fd6  lea     r8, [rsp+1A0h+var_14C]
0x140260fdb  mov     [rsp+1A0h+var_180], rax
0x140260fe0  lea     rdx, [rsp+1A0h+var_150]
0x140260fe5  lea     rcx, [rbp+0A0h+DestinationString]
0x140260fe9  call    cs:__imp_ZwQueryLicenseValue
0x140260ff0  nop     dword ptr [rax+rax+00h]
0x140260ff5  test    eax, eax
0x140260ff7  js      short loc_14026100F
0x140260ff9  cmp     [rbp+0A0h+arg_18], 4
0x140261000  jnz     short loc_14026100F
0x140261002  cmp     [rsp+1A0h+var_150], 4
0x140261007  jnz     short loc_14026100F
0x140261009  cmp     [rsp+1A0h+var_14C], edi
0x14026100d  jnz     short loc_140261018
0x14026100f  mov     [rsi+4849h], dil
0x140261016  jmp     short loc_14026101F
0x140261018  mov     [rsi+4849h], r14b
0x14026101f  xorps   xmm0, xmm0
0x140261022  mov     [rbp+0A0h+arg_0], edi
0x140261028  lea     rax, aBenumeratehwbe; "bEnumerateHWBeforeSW"
0x14026102f  mov     [rbp+0A0h+var_B0], rdi
0x140261033  mov     [rbp+0A0h+var_A0], rax
0x140261037  lea     r8, [rbp+0A0h+var_B0]
0x14026103b  lea     rax, [rbp+0A0h+arg_0]
0x140261042  mov     [rbp+0A0h+var_A8], 124h
0x140261049  mov     ebx, 4000000h
0x14026104e  mov     [rbp+0A0h+var_98], rax
0x140261052  xor     r9d, r9d
0x140261055  mov     [rbp+0A0h+var_90], ebx
0x140261058  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\SOFTWARE\\Policies"...
0x14026105f  mov     [rbp+0A0h+var_88], rdi
0x140261063  xor     ecx, ecx
0x140261065  mov     [rbp+0A0h+var_80], edi
0x140261068  mov     [rbp+0A0h+var_78], rdi
0x14026106c  mov     [rbp+0A0h+var_70], edi
0x14026106f  mov     [rbp+0A0h+var_68], rdi
0x140261073  movups  [rbp+0A0h+var_60], xmm0
0x140261077  mov     [rsp+1A0h+var_180], rdi
0x14026107c  movups  [rbp+0A0h+var_50], xmm0
0x140261080  call    cs:__imp_RtlQueryRegistryValuesEx
0x140261087  nop     dword ptr [rax+rax+00h]
0x14026108c  test    eax, eax
0x14026108e  jns     short loc_1402610F9
0x140261090  xorps   xmm0, xmm0
0x140261093  mov     [rsp+1A0h+var_130], rdi
0x140261098  lea     rax, aFusehardwaregp; "fUseHardwareGPU"
0x14026109f  mov     [rsp+1A0h+var_128], 124h
0x1402610a7  mov     [rbp+0A0h+var_120], rax
0x1402610ab  lea     r8, [rsp+1A0h+var_130]
0x1402610b0  lea     rax, [rbp+0A0h+arg_0]
0x1402610b7  mov     [rbp+0A0h+var_110], ebx
0x1402610ba  xor     r9d, r9d
0x1402610bd  mov     [rbp+0A0h+var_118], rax
0x1402610c1  lea     rdx, aRegistryMachin_26; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x1402610c8  mov     [rbp+0A0h+var_108], rdi
0x1402610cc  xor     ecx, ecx
0x1402610ce  mov     [rbp+0A0h+var_100], edi
0x1402610d1  mov     [rbp+0A0h+var_F8], rdi
0x1402610d5  mov     [rbp+0A0h+var_F0], edi
0x1402610d8  mov     [rbp+0A0h+var_E8], rdi
0x1402610dc  movups  [rbp+0A0h+var_E0], xmm0
0x1402610e0  mov     [rsp+1A0h+var_180], rdi
0x1402610e5  movups  [rbp+0A0h+var_D0], xmm0
0x1402610e9  call    cs:__imp_RtlQueryRegistryValuesEx
0x1402610f0  nop     dword ptr [rax+rax+00h]
0x1402610f5  test    eax, eax
0x1402610f7  js      short loc_140261108
0x1402610f9  cmp     [rbp+0A0h+arg_0], edi
0x1402610ff  setnz   al
0x140261102  mov     [rsi+4849h], al
0x140261108  xor     eax, eax
0x14026110a  mov     [rbp+0A0h+arg_8], dil
0x140261111  mov     [rsi+484Ch], rax
0x140261118  lea     rax, [rbp+0A0h+arg_8]
0x14026111f  mov     [rsp+1A0h+var_138], rax
0x140261124  mov     [rsi+4854h], edi
0x14026112a  mov     [rsi+4858h], rdi
0x140261131  mov     [rsp+1A0h+var_140], 3
0x140261139  mov     [rsp+1A0h+var_13C], r14d
0x14026113e  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x140261143  test    rax, rax
0x140261146  jz      loc_1402613E5
0x14026114c  mov     r14, [rax+58h]
0x140261150  test    r14, r14
0x140261153  jz      short loc_1402611D4
0x140261155  mov     rax, [r14+170h]
0x14026115c  test    rax, rax
0x14026115f  jz      short loc_1402611D4
0x140261161  lea     rcx, [rsp+1A0h+var_140]
0x140261166  call    _guard_dispatch_icall
0x14026116b  test    eax, eax
0x14026116d  jns     short loc_1402611D4
0x14026116f  movsxd  rbx, eax
0x140261172  mov     rdx, r15
0x140261175  mov     r8, rbx
0x140261178  mov     ecx, 2
0x14026117d  call    cs:__imp_WdLogSingleEntry2
0x140261184  nop     dword ptr [rax+rax+00h]
0x140261189  mov     [rsp+1A0h+var_160], rdi
0x14026118e  lea     r9, aFailedToGetSes; "Failed to get session TTM support in se"...
0x140261195  mov     [rsp+1A0h+var_168], rdi
0x14026119a  or      r8d, 0FFFFFFFFh
0x14026119e  mov     [rsp+1A0h+var_170], rdi
0x1402611a3  mov     edx, 40000h
0x1402611a8  mov     [rsp+1A0h+var_178], rbx
0x1402611ad  xor     ecx, ecx
0x1402611af  mov     [rsp+1A0h+var_180], r15
0x1402611b4  mov     cs:WdLogGlobalForLineNumber, 0D5Eh
0x1402611be  call    DxgkLogInternalTriageEvent
0x1402611c3  mov     al, dil
0x1402611c6  mov     [rbp+0A0h+arg_8], al
0x1402611cc  mov     [rsi+4841h], al
0x1402611d2  jmp     short loc_1402611E5
0x1402611d4  mov     al, [rbp+0A0h+arg_8]
0x1402611da  mov     [rsi+4841h], al
0x1402611e0  test    r14, r14
0x1402611e3  jz      short loc_140261215
0x1402611e5  mov     rax, [r14+160h]
0x1402611ec  test    rax, rax
0x1402611ef  jz      short loc_1402611FD
0x1402611f1  call    _guard_dispatch_icall
0x1402611f6  mov     [rsi+4868h], rax
0x1402611fd  mov     rax, [r14+190h]
0x140261204  test    rax, rax
0x140261207  jz      short loc_140261215
0x140261209  call    _guard_dispatch_icall
0x14026120e  mov     [rsi+4870h], rax
0x140261215  mov     r14d, 1
  ... truncated ...
```
