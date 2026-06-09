# DXGSESSIONDATA::DXGSESSIONDATA(ulong)

- ea: `0x140266208`
- end: `0x140266a2c`
- name: `??0DXGSESSIONDATA@@QEAA@K@Z`
- size: `2084`
- prototype: `DXGSESSIONDATA *__fastcall(DXGSESSIONDATA *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1403e09b8`

## callees

- `0x140012540`
- `0x14001b9c0`
- `0x14002e2e0`
- `0x14004b1e0`
- `0x14004dd04`
- `0x14007be40`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x14024d608`
- `0x140266208`
- `0x14032a5c4`
- `0x1403e60fc`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1402667e2`
- `ntoskrnl!PsGetCurrentProcess` at `0x1402667e2`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140266634`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14026669d`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1402668d6`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140266634`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14026669d`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1402668d6`
- `ntoskrnl!ObfReferenceObject` at `0x1402667f8`
- `ntoskrnl!ObfReferenceObject` at `0x1402669c5`
- `ntoskrnl!ObfReferenceObject` at `0x1402667f8`
- `ntoskrnl!ObfReferenceObject` at `0x1402669c5`
- `ntoskrnl!ZwClose` at `0x1402669d6`
- `ntoskrnl!ZwClose` at `0x1402669d6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140266571`
- `ntoskrnl!RtlInitUnicodeString` at `0x140266571`
- `ntoskrnl!IoCreateNotificationEvent` at `0x140266933`
- `ntoskrnl!IoCreateNotificationEvent` at `0x140266933`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1402668ab`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1402668e7`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1402668ab`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1402668e7`
- `ntoskrnl!PsGetHostSilo` at `0x14026689c`
- `ntoskrnl!PsGetHostSilo` at `0x14026689c`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14026659d`
- `ntoskrnl!ZwQueryLicenseValue` at `0x14026659d`
- `ntoskrnl!RtlGetSuiteMask` at `0x14026652f`
- `ntoskrnl!RtlGetSuiteMask` at `0x14026652f`
- `ntoskrnl!RtlGetNtProductType` at `0x140266523`
- `ntoskrnl!RtlGetNtProductType` at `0x140266523`
- `ntoskrnl!RtlInitializeBitMap` at `0x140266a08`
- `ntoskrnl!RtlInitializeBitMap` at `0x140266a08`
- `ntoskrnl!PsIsHostSilo` at `0x140266830`
- `ntoskrnl!PsIsHostSilo` at `0x140266830`
- `ntoskrnl!PsGetProcessServerSilo` at `0x140266821`
- `ntoskrnl!PsGetProcessServerSilo` at `0x140266821`
- `ntoskrnl!KeSetEvent` at `0x1402669b2`
- `ntoskrnl!KeSetEvent` at `0x1402669b2`
- `watchdog!WdLogSingleEntry2` at `0x140266731`
- `watchdog!WdLogSingleEntry2` at `0x140266731`
- `watchdog!WdLogSingleEntry1` at `0x140266951`
- `watchdog!WdLogSingleEntry1` at `0x140266951`

## string_xrefs

- `0x14026655a`: `TerminalServices-RemoteConnectionManager-WVD-Enabled`
- `0x14026660c`: `\Registry\Machine\SOFTWARE\Policies\Microsoft\Windows NT\Terminal Services`
- `0x140266675`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\Terminal Server\WinStations`
- `0x140266962`: `Failed to create PnP event object for session 0x%I64x.`

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
  __int64 v11; // rcx
  struct DXGPROCESS *Current; // rax
  __int64 v13; // rcx
  _QWORD *v14; // r14
  __int64 (__fastcall *v15)(_DWORD *); // rax
  int v16; // eax
  __int64 v17; // rbx
  __int64 (__fastcall *v18)(__int64); // rax
  __int64 (__fastcall *v19)(__int64); // rax
  struct DXGPROCESS *v20; // rax
  __int64 v21; // rcx
  void *CurrentProcess; // rax
  __int64 ProcessServerSilo; // rax
  char IsHostSilo; // al
  __int64 v25; // rcx
  __int64 HostSilo; // rax
  __int64 v27; // rdi
  int v28; // ebx
  struct _KEVENT *v29; // rax
  int v31; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+54h] [rbp-ACh] BYREF
  void *EventHandle; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v34[2]; // [rsp+60h] [rbp-A0h] BYREF
  char *v35; // [rsp+68h] [rbp-98h]
  __int64 v36; // [rsp+70h] [rbp-90h] BYREF
  int v37; // [rsp+78h] [rbp-88h]
  const wchar_t *v38; // [rsp+80h] [rbp-80h]
  int *v39; // [rsp+88h] [rbp-78h]
  int v40; // [rsp+90h] [rbp-70h]
  __int64 v41; // [rsp+98h] [rbp-68h]
  int v42; // [rsp+A0h] [rbp-60h]
  __int64 v43; // [rsp+A8h] [rbp-58h]
  int v44; // [rsp+B0h] [rbp-50h]
  __int64 v45; // [rsp+B8h] [rbp-48h]
  __int128 v46; // [rsp+C0h] [rbp-40h]
  __int128 v47; // [rsp+D0h] [rbp-30h]
  struct _UNICODE_STRING DestinationString; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v49; // [rsp+F0h] [rbp-10h] BYREF
  int v50; // [rsp+F8h] [rbp-8h]
  const wchar_t *v51; // [rsp+100h] [rbp+0h]
  int *v52; // [rsp+108h] [rbp+8h]
  int v53; // [rsp+110h] [rbp+10h]
  __int64 v54; // [rsp+118h] [rbp+18h]
  int v55; // [rsp+120h] [rbp+20h]
  __int64 v56; // [rsp+128h] [rbp+28h]
  int v57; // [rsp+130h] [rbp+30h]
  __int64 v58; // [rsp+138h] [rbp+38h]
  __int128 v59; // [rsp+140h] [rbp+40h]
  __int128 v60; // [rsp+150h] [rbp+50h]
  int v61; // [rsp+1B0h] [rbp+B0h] BYREF
  char v62; // [rsp+1B8h] [rbp+B8h] BYREF
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+1C0h] [rbp+C0h] BYREF
  int v64; // [rsp+1C8h] [rbp+C8h] BYREF

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
  RtlGetSuiteMask(v11);
  *((_BYTE *)this + 18505) = ProductType != NtProductServer
                          || !g_bSkuSupportMultipleUsers
                          || (v64 = 0,
                              v31 = 0,
                              v32 = 0,
                              DestinationString = 0,
                              RtlInitUnicodeString(
                                &DestinationString,
                                L"TerminalServices-RemoteConnectionManager-WVD-Enabled"),
                              (int)ZwQueryLicenseValue(&DestinationString, &v31, &v32, 4, &v64) >= 0)
                          && v64 == 4
                          && v31 == 4
                          && v32;
  v61 = 0;
  v49 = 0;
  v51 = L"bEnumerateHWBeforeSW";
  v50 = 292;
  v52 = &v61;
  v53 = 0x4000000;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  if ( (int)RtlQueryRegistryValuesEx(
              0,
              L"\\Registry\\Machine\\SOFTWARE\\Policies\\Microsoft\\Windows NT\\Terminal Services",
              &v49) >= 0 )
    goto LABEL_19;
  v36 = 0;
  v37 = 292;
  v38 = L"fUseHardwareGPU";
  v40 = 0x4000000;
  v39 = &v61;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  if ( (int)RtlQueryRegistryValuesEx(
              0,
              L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
              &v36) >= 0 )
LABEL_19:
    *((_BYTE *)this + 18505) = v61 != 0;
  v62 = 0;
  *(_QWORD *)((char *)this + 18508) = 0;
  v35 = &v62;
  *((_DWORD *)this + 4629) = 0;
  *((_QWORD *)this + 2315) = 0;
  v34[0] = 3;
  v34[1] = 1;
  Current = DXGPROCESS::GetCurrent();
  if ( Current )
  {
    v14 = (_QWORD *)*((_QWORD *)Current + 11);
    if ( v14 && (v15 = (__int64 (__fastcall *)(_DWORD *))v14[46]) != 0 && (v16 = v15(v34), v16 < 0) )
    {
      v17 = v16;
      WdLogSingleEntry2(2, v2, v16);
      WdLogGlobalForLineNumber = 3422;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Failed to get session TTM support in session 0x%I64x (Status = 0x%I64x).",
        v2,
        v17,
        0,
        0,
        0);
      v62 = 0;
      *((_BYTE *)this + 18497) = 0;
    }
    else
    {
      *((_BYTE *)this + 18497) = v62;
      if ( !v14 )
        goto LABEL_30;
    }
    v18 = (__int64 (__fastcall *)(__int64))v14[44];
    if ( v18 )
      *((_QWORD *)this + 2317) = v18(v13);
    v19 = (__int64 (__fastcall *)(__int64))v14[50];
    if ( v19 )
      *((_QWORD *)this + 2318) = v19(v13);
  }
  else
  {
    *((_BYTE *)this + 18497) = v62;
  }
LABEL_30:
  v20 = DXGPROCESS::GetCurrent();
  *((_QWORD *)this + 2333) = v20;
  *((_DWORD *)v20 + 102) |= 1u;
  CurrentProcess = (void *)PsGetCurrentProcess(v21);
  *((_QWORD *)this + 2332) = CurrentProcess;
  ObfReferenceObject(CurrentProcess);
  if ( *((_QWORD *)DXGGLOBAL::GetGlobal() + 38121) )
    CreateTokenManagerSessionGlobal(v3);
  ProcessServerSilo = PsGetProcessServerSilo(*((_QWORD *)this + 2332));
  IsHostSilo = PsIsHostSilo(ProcessServerSilo);
  *((_BYTE *)this + 18502) = IsHostSilo == 0;
  if ( !IsHostSilo )
  {
    v64 = 0;
    v36 = 0;
    v38 = L"DisableContainerSessionVersionCheck";
    v39 = &v64;
    v37 = 292;
    v40 = 67108868;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    LOBYTE(v25) = 1;
    HostSilo = PsGetHostSilo(v25);
    v27 = PsAttachSiloToCurrentThread(HostSilo);
    v28 = RtlQueryRegistryValuesEx(2, L"GraphicsDrivers", &v36);
    PsAttachSiloToCurrentThread(v27);
    if ( v28 < 0 || !v64 )
      *((_BYTE *)this + 18503) = 1;
  }
  *((_DWORD *)this + 4684) = 0;
  *((_QWORD *)this + 2343) = 0;
  *((_BYTE *)this + 18504) = 1;
  *((_QWORD *)this + 2373) = this;
  EventHandle = 0;
  v29 = IoCreateNotificationEvent(0, &EventHandle);
  *((_QWORD *)this + 2346) = v29;
  if ( v29 )
  {
    KeSetEvent(v29, 0, 0);
    ObfReferenceObject(*((PVOID *)this + 2346));
    ZwClose(EventHandle);
  }
  else
  {
    WdLogSingleEntry1(6, v2);
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
0x140266208  push    rbp
0x14026620a  push    rbx
0x14026620b  push    rsi
0x14026620c  push    rdi
0x14026620d  push    r12
0x14026620f  push    r13
0x140266211  push    r14
0x140266213  push    r15
0x140266215  lea     rbp, [rsp-68h]
0x14026621a  sub     rsp, 168h
0x140266221  xor     edi, edi
0x140266223  mov     r15d, edx
0x140266226  mov     [rcx], r15d
0x140266229  lea     r12, [rcx+4940h]
0x140266230  mov     [rcx+18h], rdi
0x140266234  lea     r13, [rcx+4968h]
0x14026623b  mov     [rcx+20h], rdi
0x14026623f  or      ebx, 0FFFFFFFFh
0x140266242  mov     [rcx+28h], rdi
0x140266246  lea     eax, [rdi+3Dh]
0x140266249  mov     [rcx+30h], edi
0x14026624c  lea     r14d, [rdi+1]
0x140266250  mov     [rcx+34h], ebx
0x140266253  mov     rsi, rcx
0x140266256  mov     dword ptr [rcx+38h], 4Eh ; 'N'
0x14026625d  xor     edx, edx; struct DispBrokerClientHandle *
0x14026625f  mov     [rcx+4840h], edi
0x140266265  mov     [rcx+4844h], di
0x14026626c  mov     [rcx+4847h], dil
0x140266273  mov     [rcx+4860h], edi
0x140266279  mov     [rcx+4868h], rdi
0x140266280  mov     [rcx+4870h], rdi
0x140266287  mov     [rcx+4878h], rdi
0x14026628e  mov     [rcx+4880h], rdi
0x140266295  mov     [rcx+4888h], edi
0x14026629b  mov     [rcx+488Ch], eax
0x1402662a1  mov     [rcx+4890h], eax
0x1402662a7  mov     [rcx+48D0h], edi
0x1402662ad  mov     [rcx+48D8h], rdi
0x1402662b4  mov     [rcx+48F8h], rdi
0x1402662bb  mov     [rcx+4900h], rdi
0x1402662c2  mov     [rcx+4908h], rdi
0x1402662c9  mov     [rcx+4910h], edi
0x1402662cf  mov     dword ptr [rcx+4914h], 51h ; 'Q'
0x1402662d9  mov     [rcx+4918h], r14d
0x1402662e0  mov     [rcx+4920h], rdi
0x1402662e7  mov     [rcx+4928h], rdi
0x1402662ee  mov     [rcx+4948h], rdi
0x1402662f5  mov     [rcx+4950h], rdi
0x1402662fc  mov     dword ptr [rcx+4958h], 4
0x140266306  mov     [rcx+4960h], r13
0x14026630d  mov     [r12], rdi
0x140266311  mov     [rcx+49F0h], rdi
0x140266318  mov     [rcx+49F8h], rdi
0x14026631f  mov     [rcx+4A00h], rdi
0x140266326  mov     [rcx+4A08h], edi
0x14026632c  mov     [rcx+4A0Ch], ebx
0x140266332  mov     dword ptr [rcx+4A10h], 48h ; 'H'
0x14026633c  mov     [rcx+4A18h], edi
0x140266342  mov     [rcx+4A20h], rdi
0x140266349  mov     [rcx+4A28h], rdi
0x140266350  mov     [rcx+4A30h], di
0x140266357  mov     [rcx+4A38h], rdi
0x14026635e  mov     [rcx+4A40h], rdi
0x140266365  mov     [rcx+4A48h], edi
0x14026636b  mov     [rcx+4A4Ch], r14d
0x140266372  mov     [rcx+4A50h], ebx
0x140266378  add     rcx, 4A58h; this
0x14026637f  mov     [rcx], rdi
0x140266382  call    ?Assign@DispBrokerClientReference@@QEAAXPEAVDispBrokerClientHandle@@@Z; DispBrokerClientReference::Assign(DispBrokerClientHandle *)
0x140266387  mov     [rsi+4A68h], rdi
0x14026638e  mov     [rsi+4A70h], rdi
0x140266395  mov     [rsi+4A78h], rdi
0x14026639c  mov     [rsi+4A80h], edi
0x1402663a2  mov     [rsi+4A84h], ebx
0x1402663a8  mov     [rsi+4A88h], r14d
0x1402663af  mov     [rsi+4A90h], rdi
0x1402663b6  mov     [rsi+4A98h], rdi
0x1402663bd  mov     [rsi+4AA0h], dil
0x1402663c4  mov     [rsi+4AB8h], rdi
0x1402663cb  mov     [rsi+4AC0h], rdi
0x1402663d2  mov     [rsi+4AC8h], rdi
0x1402663d9  mov     [rsi+4AD0h], edi
0x1402663df  mov     [rsi+4AD4h], ebx
0x1402663e5  mov     [rsi+4AD8h], r14d
0x1402663ec  mov     [rsi+4AE0h], rdi
0x1402663f3  mov     [rsi+4AE8h], edi
0x1402663f9  mov     [rsi+4AECh], r14d
0x140266400  mov     [rsi+4AF0h], rdi
0x140266407  mov     [rsi+4B00h], rdi
0x14026640e  mov     [rsi+4B08h], rdi
0x140266415  mov     [rsi+4B10h], rdi
0x14026641c  mov     edx, 674D444Fh
0x140266421  mov     [rsi+4B18h], edi
0x140266427  mov     ecx, 208h
0x14026642c  mov     [rsi+4B1Ch], ebx
0x140266432  mov     r8d, 100h
0x140266438  mov     [rsi+4B20h], r14d
0x14026643f  mov     [rsi+4B40h], rdi
0x140266446  mov     [rsi+4B48h], rdi
0x14026644d  mov     [rsi+4B50h], edi
0x140266453  mov     dword ptr [rsi+4B54h], 40h ; '@'
0x14026645d  mov     dword ptr [rsi+4B58h], 43h ; 'C'
0x140266467  mov     [rbp+0A0h+ProductType], edi
0x14026646d  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140266472  mov     rbx, rax
0x140266475  test    rax, rax
0x140266478  jz      short loc_1402664C8
0x14026647a  mov     [rax+4], edi
0x14026647d  lea     ecx, [rdi+4Eh]
0x140266480  mov     [rax+10h], rdi
0x140266484  mov     [rax+18h], rdi
0x140266488  mov     [rax+20h], rdi
0x14026648c  mov     [rax+28h], edi
0x14026648f  lea     eax, [rdi+2Bh]
0x140266492  mov     [rbx+30h], ecx
0x140266495  mov     [rbx+2Ch], eax
0x140266498  mov     [rbx+38h], rdi
0x14026649c  mov     [rbx+40h], edi
0x14026649f  mov     [rbx+50h], rdi
0x1402664a3  mov     [rbx+58h], rdi
0x1402664a7  mov     [rbx+70h], ecx
0x1402664aa  mov     rcx, rbx; this
0x1402664ad  mov     [rbx+60h], rdi
0x1402664b1  mov     [rbx+68h], edi
0x1402664b4  mov     [rbx+6Ch], eax
0x1402664b7  mov     [rbx+78h], rdi
0x1402664bb  call    ?InitializeMaxActiveOutputDuplApps@OUTPUTDUPL_SESSION_MGR@@AEAAXXZ; OUTPUTDUPL_SESSION_MGR::InitializeMaxActiveOutputDuplApps(void)
0x1402664c0  mov     [rbx+80h], edi
0x1402664c6  jmp     short loc_1402664CB
0x1402664c8  mov     rbx, rdi
0x1402664cb  mov     [rsi+8], rbx
0x1402664cf  test    rbx, rbx
0x1402664d2  jz      short loc_1402664F2
0x1402664d4  mov     rcx, rbx; this
0x1402664d7  call    ?Initialize@OUTPUTDUPL_SESSION_MGR@@QEAAJXZ; OUTPUTDUPL_SESSION_MGR::Initialize(void)
0x1402664dc  test    eax, eax
0x1402664de  jns     short loc_1402664F2
0x1402664e0  mov     rcx, [rsi+8]; this
0x1402664e4  test    rcx, rcx
0x1402664e7  jz      short loc_1402664EE
0x1402664e9  call    ??_GOUTPUTDUPL_SESSION_MGR@@QEAAPEAXI@Z; OUTPUTDUPL_SESSION_MGR::`scalar deleting destructor'(uint)
0x1402664ee  mov     [rsi+8], rdi
0x1402664f2  lea     rax, [rsi+4898h]
0x1402664f9  mov     [rax+8], rax
0x1402664fd  lea     rcx, [rbp+0A0h+ProductType]; ProductType
0x140266504  mov     [rax], rax
0x140266507  lea     rax, [rsi+48A8h]
0x14026650e  mov     [rax+8], rax
0x140266512  mov     [rax], rax
0x140266515  lea     rax, [rsi+48B8h]
0x14026651c  mov     [rax+8], rax
0x140266520  mov     [rax], rax
0x140266523  call    cs:__imp_RtlGetNtProductType
0x14026652a  nop     dword ptr [rax+rax+00h]
0x14026652f  call    cs:__imp_RtlGetSuiteMask
0x140266536  nop     dword ptr [rax+rax+00h]
0x14026653b  cmp     [rbp+0A0h+ProductType], 3
0x140266542  jnz     loc_1402665CC
0x140266548  cmp     cs:?g_bSkuSupportMultipleUsers@@3EA, dil; uchar g_bSkuSupportMultipleUsers
0x14026654f  jz      short loc_1402665CC
0x140266551  xorps   xmm0, xmm0
0x140266554  mov     [rbp+0A0h+arg_18], edi
0x14026655a  lea     rdx, aTerminalservic; "TerminalServices-RemoteConnectionManage"...
0x140266561  mov     [rsp+1A0h+var_150], edi
0x140266565  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x140266569  mov     [rsp+1A0h+var_14C], edi
0x14026656d  movups  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm0
0x140266571  call    cs:__imp_RtlInitUnicodeString
0x140266578  nop     dword ptr [rax+rax+00h]
0x14026657d  lea     rax, [rbp+0A0h+arg_18]
0x140266584  mov     r9d, 4
0x14026658a  lea     r8, [rsp+1A0h+var_14C]
0x14026658f  mov     [rsp+1A0h+var_180], rax
0x140266594  lea     rdx, [rsp+1A0h+var_150]
0x140266599  lea     rcx, [rbp+0A0h+DestinationString]
0x14026659d  call    cs:__imp_ZwQueryLicenseValue
0x1402665a4  nop     dword ptr [rax+rax+00h]
0x1402665a9  test    eax, eax
0x1402665ab  js      short loc_1402665C3
0x1402665ad  cmp     [rbp+0A0h+arg_18], 4
0x1402665b4  jnz     short loc_1402665C3
0x1402665b6  cmp     [rsp+1A0h+var_150], 4
0x1402665bb  jnz     short loc_1402665C3
0x1402665bd  cmp     [rsp+1A0h+var_14C], edi
0x1402665c1  jnz     short loc_1402665CC
0x1402665c3  mov     [rsi+4849h], dil
0x1402665ca  jmp     short loc_1402665D3
0x1402665cc  mov     [rsi+4849h], r14b
0x1402665d3  xorps   xmm0, xmm0
0x1402665d6  mov     [rbp+0A0h+arg_0], edi
0x1402665dc  lea     rax, aBenumeratehwbe; "bEnumerateHWBeforeSW"
0x1402665e3  mov     [rbp+0A0h+var_B0], rdi
0x1402665e7  mov     [rbp+0A0h+var_A0], rax
0x1402665eb  lea     r8, [rbp+0A0h+var_B0]
0x1402665ef  lea     rax, [rbp+0A0h+arg_0]
0x1402665f6  mov     [rbp+0A0h+var_A8], 124h
0x1402665fd  mov     ebx, 4000000h
0x140266602  mov     [rbp+0A0h+var_98], rax
0x140266606  xor     r9d, r9d
0x140266609  mov     [rbp+0A0h+var_90], ebx
0x14026660c  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\SOFTWARE\\Policies"...
0x140266613  mov     [rbp+0A0h+var_88], rdi
0x140266617  xor     ecx, ecx
0x140266619  mov     [rbp+0A0h+var_80], edi
0x14026661c  mov     [rbp+0A0h+var_78], rdi
0x140266620  mov     [rbp+0A0h+var_70], edi
0x140266623  mov     [rbp+0A0h+var_68], rdi
0x140266627  movups  [rbp+0A0h+var_60], xmm0
0x14026662b  mov     [rsp+1A0h+var_180], rdi
0x140266630  movups  [rbp+0A0h+var_50], xmm0
0x140266634  call    cs:__imp_RtlQueryRegistryValuesEx
0x14026663b  nop     dword ptr [rax+rax+00h]
0x140266640  test    eax, eax
0x140266642  jns     short loc_1402666AD
0x140266644  xorps   xmm0, xmm0
0x140266647  mov     [rsp+1A0h+var_130], rdi
0x14026664c  lea     rax, aFusehardwaregp; "fUseHardwareGPU"
0x140266653  mov     [rsp+1A0h+var_128], 124h
0x14026665b  mov     [rbp+0A0h+var_120], rax
0x14026665f  lea     r8, [rsp+1A0h+var_130]
0x140266664  lea     rax, [rbp+0A0h+arg_0]
0x14026666b  mov     [rbp+0A0h+var_110], ebx
0x14026666e  xor     r9d, r9d
0x140266671  mov     [rbp+0A0h+var_118], rax
0x140266675  lea     rdx, aRegistryMachin_26; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x14026667c  mov     [rbp+0A0h+var_108], rdi
0x140266680  xor     ecx, ecx
0x140266682  mov     [rbp+0A0h+var_100], edi
0x140266685  mov     [rbp+0A0h+var_F8], rdi
0x140266689  mov     [rbp+0A0h+var_F0], edi
0x14026668c  mov     [rbp+0A0h+var_E8], rdi
0x140266690  movups  [rbp+0A0h+var_E0], xmm0
0x140266694  mov     [rsp+1A0h+var_180], rdi
0x140266699  movups  [rbp+0A0h+var_D0], xmm0
0x14026669d  call    cs:__imp_RtlQueryRegistryValuesEx
0x1402666a4  nop     dword ptr [rax+rax+00h]
0x1402666a9  test    eax, eax
0x1402666ab  js      short loc_1402666BC
0x1402666ad  cmp     [rbp+0A0h+arg_0], edi
0x1402666b3  setnz   al
0x1402666b6  mov     [rsi+4849h], al
0x1402666bc  xor     eax, eax
0x1402666be  mov     [rbp+0A0h+arg_8], dil
0x1402666c5  mov     [rsi+484Ch], rax
0x1402666cc  lea     rax, [rbp+0A0h+arg_8]
0x1402666d3  mov     [rsp+1A0h+var_138], rax
0x1402666d8  mov     [rsi+4854h], edi
0x1402666de  mov     [rsi+4858h], rdi
0x1402666e5  mov     [rsp+1A0h+var_140], 3
0x1402666ed  mov     [rsp+1A0h+var_13C], r14d
0x1402666f2  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x1402666f7  test    rax, rax
0x1402666fa  jz      loc_140266999
0x140266700  mov     r14, [rax+58h]
0x140266704  test    r14, r14
0x140266707  jz      short loc_140266788
0x140266709  mov     rax, [r14+170h]
0x140266710  test    rax, rax
0x140266713  jz      short loc_140266788
0x140266715  lea     rcx, [rsp+1A0h+var_140]
0x14026671a  call    _guard_dispatch_icall
0x14026671f  test    eax, eax
0x140266721  jns     short loc_140266788
0x140266723  movsxd  rbx, eax
0x140266726  mov     rdx, r15
0x140266729  mov     r8, rbx
0x14026672c  mov     ecx, 2
0x140266731  call    cs:__imp_WdLogSingleEntry2
0x140266738  nop     dword ptr [rax+rax+00h]
0x14026673d  mov     [rsp+1A0h+var_160], rdi
0x140266742  lea     r9, aFailedToGetSes; "Failed to get session TTM support in se"...
0x140266749  mov     [rsp+1A0h+var_168], rdi
0x14026674e  or      r8d, 0FFFFFFFFh
0x140266752  mov     [rsp+1A0h+var_170], rdi
0x140266757  mov     edx, 40000h
0x14026675c  mov     [rsp+1A0h+var_178], rbx
0x140266761  xor     ecx, ecx
0x140266763  mov     [rsp+1A0h+var_180], r15
0x140266768  mov     cs:WdLogGlobalForLineNumber, 0D5Eh
0x140266772  call    DxgkLogInternalTriageEvent
0x140266777  mov     al, dil
0x14026677a  mov     [rbp+0A0h+arg_8], al
0x140266780  mov     [rsi+4841h], al
0x140266786  jmp     short loc_140266799
0x140266788  mov     al, [rbp+0A0h+arg_8]
0x14026678e  mov     [rsi+4841h], al
0x140266794  test    r14, r14
0x140266797  jz      short loc_1402667C9
0x140266799  mov     rax, [r14+160h]
0x1402667a0  test    rax, rax
0x1402667a3  jz      short loc_1402667B1
0x1402667a5  call    _guard_dispatch_icall
0x1402667aa  mov     [rsi+4868h], rax
0x1402667b1  mov     rax, [r14+190h]
0x1402667b8  test    rax, rax
0x1402667bb  jz      short loc_1402667C9
0x1402667bd  call    _guard_dispatch_icall
0x1402667c2  mov     [rsi+4870h], rax
0x1402667c9  mov     r14d, 1
  ... truncated ...
```
