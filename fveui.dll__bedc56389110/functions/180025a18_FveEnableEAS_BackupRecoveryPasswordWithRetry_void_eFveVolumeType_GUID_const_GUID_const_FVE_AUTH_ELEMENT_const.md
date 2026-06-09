# FveEnableEAS::BackupRecoveryPasswordWithRetry(void *,eFveVolumeType,_GUID const *,_GUID const *,_FVE_AUTH_ELEMENT const *)

- ea: `0x180025a18`
- end: `0x180026037`
- name: `?BackupRecoveryPasswordWithRetry@FveEnableEAS@@IEAAJPEAXW4eFveVolumeType@@PEBU_GUID@@2PEBU_FVE_AUTH_ELEMENT@@@Z`
- size: `1567`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, struct FveEasNetworkStatus *, const char *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180023fe4`

## callees

- `0x180001248`
- `0x180001394`
- `0x1800037a0`
- `0x18000e354`
- `0x180014538`
- `0x180015820`
- `0x180016628`
- `0x180023ad8`
- `0x180025a18`
- `0x180028648`
- `0x18002d010`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180025c86`
- `KERNEL32!CreateEventW` at `0x180025c86`
- `KERNEL32!CloseHandle` at `0x180025f24`
- `KERNEL32!CloseHandle` at `0x180025f24`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180025b3f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180025b3f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002601d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002601d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180025cf5`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180025cf5`
- `FVESKYBACKUP!FveBackupRecoveryPasswordToSkyDrive` at `0x180025d88`
- `FVESKYBACKUP!FveBackupRecoveryPasswordToSkyDrive` at `0x180025d88`

## string_xrefs

- `0x180025afa`: `FVE_E_MSA_BACKUP_CACHE_NOT_ALLOCATED`
- `0x180025eea`: `InitializeCom.Initialize`
- `0x180025e40`: `FveEasNetworkStatusCreate`

## pseudocode

```c
__int64 __fastcall FveEnableEAS::BackupRecoveryPasswordWithRetry(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        struct FveEasNetworkStatus *a4,
        const char *a5)
{
  __int64 v6; // r12
  char v7; // bl
  FveEasNetworkStatus *v8; // rsi
  int v9; // r13d
  PVOID *v10; // rcx
  HRESULT CurrentStatus; // edi
  int v12; // r12d
  HRESULT v13; // eax
  int v14; // eax
  PVOID *v15; // rdx
  const char *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  const char *v22; // [rsp+30h] [rbp-51h]
  char v23; // [rsp+68h] [rbp-19h] BYREF
  char v24; // [rsp+69h] [rbp-18h]
  DWORD dwindex; // [rsp+6Ch] [rbp-15h] BYREF
  BOOL v26; // [rsp+70h] [rbp-11h] BYREF
  HANDLE pHandles; // [rsp+78h] [rbp-9h] BYREF
  struct FveEasNetworkStatus *v28; // [rsp+80h] [rbp-1h] BYREF
  __int64 v29; // [rsp+88h] [rbp+7h] BYREF
  const char *v30; // [rsp+90h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+4Fh]
  __int64 v32; // [rsp+D8h] [rbp+57h] BYREF
  __int64 v33; // [rsp+E0h] [rbp+5Fh]
  unsigned int v34; // [rsp+E8h] [rbp+67h] BYREF
  struct FveEasNetworkStatus *v35; // [rsp+F0h] [rbp+6Fh]

  v35 = a4;
  v34 = a3;
  v33 = a2;
  v32 = a1;
  v6 = a1;
  v23 = 0;
  v7 = 0;
  v24 = 0;
  pHandles = 0;
  v8 = 0;
  v28 = 0;
  dwindex = 0;
  v9 = 0;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  v26 = a3 == 0;
  if ( !*(_QWORD *)(v6 + 32) )
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 )
    {
      WPP_SF_(v10[2], 55, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    CurrentStatus = -2144272131;
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 )
      WPP_SF_d(v10[2], 56, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, 2150695165LL);
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x1DD,
      (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
      (const char *)0x803100FDLL,
      (int)"FVE_E_MSA_BACKUP_CACHE_NOT_ALLOCATED",
      v22);
    goto LABEL_73;
  }
  CurrentStatus = 0;
  v12 = 0;
  while ( 1 )
  {
    if ( !v12 )
      goto LABEL_50;
    if ( !v7 )
    {
      v13 = CoInitializeEx(0, 0);
      if ( v13 < 0 )
      {
        CurrentStatus = 0;
        if ( v13 != -2147417850 )
          CurrentStatus = v13;
        if ( CurrentStatus )
        {
          v10 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              156,
              &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
              (unsigned int)CurrentStatus);
            v10 = (PVOID *)WPP_GLOBAL_Control;
          }
          goto LABEL_25;
        }
      }
      v10 = (PVOID *)WPP_GLOBAL_Control;
      v7 = 1;
      v24 = 1;
    }
    CurrentStatus = 0;
LABEL_25:
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 )
      WPP_SF_d(v10[2], 57, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, (unsigned int)CurrentStatus);
    if ( CurrentStatus < 0 )
    {
      v16 = "InitializeCom.Initialize";
      v17 = 493;
      goto LABEL_69;
    }
    if ( !v8 )
    {
      CurrentStatus = FveEasNetworkStatus::Create(&v28);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          58,
          &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
          (unsigned int)CurrentStatus);
      if ( CurrentStatus < 0 )
      {
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x1F4,
          (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
          (const char *)(unsigned int)CurrentStatus,
          (int)"FveEasNetworkStatusCreate",
          v22);
        v8 = v28;
        goto LABEL_70;
      }
      v8 = v28;
    }
    CurrentStatus = FveEasNetworkStatusImpl::GetCurrentStatus(*(_QWORD *)v8 + 8LL, &v23);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
        (unsigned int)CurrentStatus);
    if ( CurrentStatus < 0 )
    {
      v16 = "GetCurrentStatus";
      v17 = 503;
      goto LABEL_69;
    }
    if ( !v23 )
    {
      if ( !pHandles )
      {
        pHandles = CreateEventW(0, 0, 0, 0);
        v29 = (__int64)pHandles;
        CurrentStatus = FveEasNetworkStatus::RegisterForStatusChange__lambda_cbacfa1d190aca0c9e6974e5309c7bfa___(
                          v8,
                          &v29);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            60,
            &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
            (unsigned int)CurrentStatus);
        if ( CurrentStatus < 0 )
        {
          v16 = "RegisterForStatusChange";
          v17 = 527;
LABEL_69:
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)v17,
            (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
            (const char *)(unsigned int)CurrentStatus,
            (int)v16,
            v22);
          goto LABEL_70;
        }
      }
      CurrentStatus = CoWaitForMultipleHandles(0x18u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          61,
          &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
          (unsigned int)CurrentStatus);
      if ( CurrentStatus < 0 )
      {
        v16 = "RegisterForStatusChange";
        v17 = 540;
        goto LABEL_69;
      }
      if ( dwindex )
        break;
    }
LABEL_50:
    v22 = a5;
    v9 = FveBackupRecoveryPasswordToSkyDrive(v33, 0, 0, v34, v35);
    v14 = (***(__int64 (__fastcall ****)(_QWORD, _QWORD, struct FveEasNetworkStatus *, const char *, int))(v32 + 32))(
            *(_QWORD *)(v32 + 32),
            v34,
            v35,
            a5,
            v9);
    if ( v14 < 0 )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      v15 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_55;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
        (unsigned int)v14);
    }
    v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_55:
    if ( v9 < 0
      && !*(_BYTE *)(v32 + 64)
      && (unsigned int)(v9 + 2144272190) > 1
      && (v9 & 0x1FFF0000) != 0x860000
      && (unsigned int)++v12 < 3 )
    {
      continue;
    }
    goto LABEL_70;
  }
  CurrentStatus = -2147483622;
  wil::details::in1diag3::Log_HrMsg(
    retaddr,
    (void *)0x21F,
    (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
    (const char *)0x8000001ALL,
    (int)"CoWaitForMultipleHandles",
    v22);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, 2147483674LL);
LABEL_70:
  if ( v8 )
    FveEasNetworkStatus::`scalar deleting destructor'(v8, (unsigned int)v15);
  v6 = v32;
LABEL_73:
  if ( pHandles )
  {
    CloseHandle(pHandles);
    pHandles = 0;
  }
  if ( CurrentStatus >= 0 && v9 < 0 )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x256,
      (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
      (const char *)(unsigned int)v9,
      (int)"FveBackupRecoveryPasswordToSkyDrive",
      v22);
    CurrentStatus = v9;
  }
  if ( (unsigned int)dword_18003D5C8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18003D5C8) )
  {
    v29 = 0x1000000;
    LOBYTE(v34) = *(_BYTE *)(v6 + 64);
    v28 = v35;
    LODWORD(v32) = CurrentStatus;
    v30 = "BackupRecoveryPW";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
      v18,
      (__int64)byte_1800373D9,
      v19,
      v20,
      (const unsigned __int16 **)&v30,
      (__int64)&v26,
      (__int64)&v32,
      (__int64 *)&v28,
      (__int64)&v34,
      (__int64)&v29);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      64,
      &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
      (unsigned int)CurrentStatus);
  if ( v7 )
    CoUninitialize();
  return (unsigned int)CurrentStatus;
}

```

## disassembly

```asm
0x180025a18  mov     rax, rsp
0x180025a1b  mov     [rax+20h], r9
0x180025a1f  mov     [rax+18h], r8d
0x180025a23  mov     [rax+10h], rdx
0x180025a27  mov     [rax+8], rcx
0x180025a2b  push    rbp
0x180025a2c  push    rbx
0x180025a2d  push    rsi
0x180025a2e  push    rdi
0x180025a2f  push    r12
0x180025a31  push    r13
0x180025a33  push    r14
0x180025a35  lea     rbp, [rax-4Fh]
0x180025a39  sub     rsp, 90h
0x180025a40  mov     edi, r8d
0x180025a43  mov     r12, rcx
0x180025a46  mov     [rbp+47h+var_60], 0
0x180025a4a  xor     bl, bl
0x180025a4c  mov     [rbp+47h+var_5F], bl
0x180025a4f  mov     [rbp+47h+pHandles], 0
0x180025a57  xor     esi, esi
0x180025a59  mov     [rbp+47h+var_48], rsi
0x180025a5d  mov     [rbp+47h+dwindex], esi
0x180025a60  xor     r13d, r13d
0x180025a63  lea     r14, WPP_GLOBAL_Control
0x180025a6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a71  cmp     rcx, r14
0x180025a74  jz      short loc_180025A96
0x180025a76  test    byte ptr [rcx+1Ch], 20h
0x180025a7a  jz      short loc_180025A96
0x180025a7c  lea     edx, [rsi+36h]
0x180025a7f  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180025a86  mov     rcx, [rcx+10h]
0x180025a8a  call    WPP_SF_
0x180025a8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a96  xor     eax, eax
0x180025a98  test    edi, edi
0x180025a9a  setz    al
0x180025a9d  mov     [rbp+47h+var_58], eax
0x180025aa0  cmp     [r12+20h], rsi
0x180025aa5  jnz     short loc_180025B22
0x180025aa7  cmp     rcx, r14
0x180025aaa  jz      short loc_180025ACE
0x180025aac  test    byte ptr [rcx+1Ch], 2
0x180025ab0  jz      short loc_180025ACE
0x180025ab2  mov     edx, 37h ; '7'
0x180025ab7  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180025abe  mov     rcx, [rcx+10h]
0x180025ac2  call    WPP_SF_
0x180025ac7  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ace  mov     edi, 803100FDh
0x180025ad3  cmp     rcx, r14
0x180025ad6  jz      short loc_180025AF6
0x180025ad8  test    byte ptr [rcx+1Ch], 40h
0x180025adc  jz      short loc_180025AF6
0x180025ade  mov     edx, 38h ; '8'
0x180025ae3  mov     r9d, edi
0x180025ae6  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180025aed  mov     rcx, [rcx+10h]
0x180025af1  call    WPP_SF_d
0x180025af6  mov     rcx, [rbp+4Fh]; this
0x180025afa  lea     rax, aFveEMsaBackupC; "FVE_E_MSA_BACKUP_CACHE_NOT_ALLOCATED"
0x180025b01  mov     [rsp+0C0h+lpdwindex], rax; int
0x180025b06  mov     r9d, edi; char *
0x180025b09  lea     r14, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\fveeas\\fveen"...
0x180025b10  mov     r8, r14; unsigned int
0x180025b13  mov     edx, 1DDh; void *
0x180025b18  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180025b1d  jmp     loc_180025F1B
0x180025b22  xor     edi, edi
0x180025b24  xor     r12d, r12d
0x180025b27  lea     r14, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\fveeas\\fveen"...
0x180025b2e  test    r12d, r12d
0x180025b31  jz      loc_180025D40
0x180025b37  test    bl, bl
0x180025b39  jnz     short loc_180025BA1
0x180025b3b  xor     edx, edx; dwCoInit
0x180025b3d  xor     ecx, ecx; pvReserved
0x180025b3f  call    cs:__imp_CoInitializeEx
0x180025b45  test    eax, eax
0x180025b47  jns     short loc_180025B95
0x180025b49  xor     edi, edi
0x180025b4b  cmp     eax, 80010106h
0x180025b50  cmovnz  edi, eax
0x180025b53  test    edi, edi
0x180025b55  jz      short loc_180025B95
0x180025b57  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b5e  lea     rax, WPP_GLOBAL_Control
0x180025b65  cmp     rcx, rax
0x180025b68  jz      short loc_180025B8F
0x180025b6a  test    byte ptr [rcx+1Ch], 40h
0x180025b6e  jz      short loc_180025B8F
0x180025b70  mov     edx, 9Ch
0x180025b75  mov     r9d, edi
0x180025b78  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180025b7f  mov     rcx, [rcx+10h]
0x180025b83  call    WPP_SF_d
0x180025b88  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b8f  test    edi, edi
0x180025b91  jns     short loc_180025B9C
0x180025b93  jmp     short loc_180025BA3
0x180025b95  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b9c  mov     bl, 1
0x180025b9e  mov     [rbp+47h+var_5F], bl
0x180025ba1  xor     edi, edi
0x180025ba3  lea     rax, WPP_GLOBAL_Control
0x180025baa  cmp     rcx, rax
0x180025bad  jz      short loc_180025BCD
0x180025baf  test    byte ptr [rcx+1Ch], 40h
0x180025bb3  jz      short loc_180025BCD
0x180025bb5  mov     edx, 39h ; '9'
0x180025bba  mov     r9d, edi
0x180025bbd  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180025bc4  mov     rcx, [rcx+10h]
0x180025bc8  call    WPP_SF_d
0x180025bcd  test    edi, edi
0x180025bcf  js      loc_180025EEA
0x180025bd5  test    rsi, rsi
0x180025bd8  jnz     short loc_180025C20
0x180025bda  lea     rcx, [rbp+47h+var_48]; struct FveEasNetworkStatus **
0x180025bde  call    ?Create@FveEasNetworkStatus@@SAJPEAPEAV1@@Z; FveEasNetworkStatus::Create(FveEasNetworkStatus * *)
0x180025be3  mov     edi, eax
0x180025be5  mov     rcx, cs:WPP_GLOBAL_Control
0x180025bec  lea     rax, WPP_GLOBAL_Control
0x180025bf3  cmp     rcx, rax
0x180025bf6  jz      short loc_180025C14
0x180025bf8  test    byte ptr [rcx+1Ch], 40h
0x180025bfc  jz      short loc_180025C14
0x180025bfe  lea     edx, [rsi+3Ah]
0x180025c01  mov     r9d, edi
0x180025c04  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180025c0b  mov     rcx, [rcx+10h]
0x180025c0f  call    WPP_SF_d
0x180025c14  test    edi, edi
0x180025c16  js      loc_180025E3C
0x180025c1c  mov     rsi, [rbp+47h+var_48]
0x180025c20  mov     rcx, [rsi]
0x180025c23  add     rcx, 8
0x180025c27  lea     rdx, [rbp+47h+var_60]
0x180025c2b  call    ?GetCurrentStatus@FveEasNetworkStatusImpl@@SAJAEBV?$ComPtr@UINetworkInformationStatics@Connectivity@Networking@Windows@@@WRL@Microsoft@@AEAUFveEasNetworkStatusArgs@@@Z; FveEasNetworkStatusImpl::GetCurrentStatus(Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::INetworkInformationStatics> const &,FveEasNetworkStatusArgs &)
0x180025c30  mov     edi, eax
0x180025c32  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c39  lea     rax, WPP_GLOBAL_Control
0x180025c40  cmp     rcx, rax
0x180025c43  jz      short loc_180025C63
0x180025c45  test    byte ptr [rcx+1Ch], 40h
0x180025c49  jz      short loc_180025C63
0x180025c4b  mov     edx, 3Bh ; ';'
0x180025c50  mov     r9d, edi
0x180025c53  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180025c5a  mov     rcx, [rcx+10h]
0x180025c5e  call    WPP_SF_d
0x180025c63  test    edi, edi
0x180025c65  js      loc_180025EDC
0x180025c6b  cmp     [rbp+47h+var_60], 0
0x180025c6f  jnz     loc_180025D40
0x180025c75  cmp     [rbp+47h+pHandles], 0
0x180025c7a  jnz     short loc_180025CDB
0x180025c7c  xor     r9d, r9d; lpName
0x180025c7f  xor     r8d, r8d; bInitialState
0x180025c82  xor     edx, edx; bManualReset
0x180025c84  xor     ecx, ecx; lpEventAttributes
0x180025c86  call    cs:__imp_CreateEventW
0x180025c8c  mov     [rbp+47h+pHandles], rax
0x180025c90  mov     [rbp+47h+var_40], rax
0x180025c94  lea     rdx, [rbp+47h+var_40]
0x180025c98  mov     rcx, rsi
0x180025c9b  call    FveEasNetworkStatus__RegisterForStatusChange__lambda_cbacfa1d190aca0c9e6974e5309c7bfa___
0x180025ca0  mov     edi, eax
0x180025ca2  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ca9  lea     rax, WPP_GLOBAL_Control
0x180025cb0  cmp     rcx, rax
0x180025cb3  jz      short loc_180025CD3
0x180025cb5  test    byte ptr [rcx+1Ch], 40h
0x180025cb9  jz      short loc_180025CD3
0x180025cbb  mov     edx, 3Ch ; '<'
0x180025cc0  mov     r9d, edi
0x180025cc3  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180025cca  mov     rcx, [rcx+10h]
0x180025cce  call    WPP_SF_d
0x180025cd3  test    edi, edi
0x180025cd5  js      loc_180025E65
0x180025cdb  lea     rax, [rbp+47h+dwindex]
0x180025cdf  mov     [rsp+0C0h+lpdwindex], rax; lpdwindex
0x180025ce4  lea     r9, [rbp+47h+pHandles]; pHandles
0x180025ce8  mov     r8d, 1; cHandles
0x180025cee  or      edx, 0FFFFFFFFh; dwTimeout
0x180025cf1  lea     ecx, [r8+17h]; dwFlags
0x180025cf5  call    cs:__imp_CoWaitForMultipleHandles
0x180025cfb  mov     edi, eax
0x180025cfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d04  lea     rax, WPP_GLOBAL_Control
0x180025d0b  cmp     rcx, rax
0x180025d0e  jz      short loc_180025D2E
0x180025d10  test    byte ptr [rcx+1Ch], 40h
0x180025d14  jz      short loc_180025D2E
0x180025d16  mov     edx, 3Dh ; '='
0x180025d1b  mov     r9d, edi
0x180025d1e  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180025d25  mov     rcx, [rcx+10h]
0x180025d29  call    WPP_SF_d
0x180025d2e  test    edi, edi
0x180025d30  js      loc_180025ECE
0x180025d36  cmp     [rbp+47h+dwindex], 0
0x180025d3a  jnz     loc_180025E76
0x180025d40  mov     dword ptr [rsp+50h], 0
0x180025d48  mov     [rsp+0C0h+var_78], 1
0x180025d50  mov     dword ptr [rsp+0C0h+var_80], 1
0x180025d58  mov     dword ptr [rsp+0C0h+var_88], 0
0x180025d60  mov     rax, [rbp+47h+arg_28]
0x180025d64  mov     [rsp+0C0h+var_90], rax
0x180025d69  mov     rax, [rbp+47h+arg_20]
0x180025d6d  mov     [rsp+0C0h+var_98], rax
0x180025d72  mov     rax, [rbp+47h+arg_18]
0x180025d76  mov     [rsp+0C0h+lpdwindex], rax
0x180025d7b  mov     r9d, [rbp+47h+arg_10]
0x180025d7f  xor     r8d, r8d
0x180025d82  xor     edx, edx
0x180025d84  mov     rcx, [rbp+47h+arg_8]
0x180025d88  call    cs:__imp_?FveBackupRecoveryPasswordToSkyDrive@@YAJPEAXHHW4eFveVolumeType@@PEBU_GUID@@2PEBU_FVE_AUTH_ELEMENT@@HHHH@Z; FveBackupRecoveryPasswordToSkyDrive(void *,int,int,eFveVolumeType,_GUID const *,_GUID const *,_FVE_AUTH_ELEMENT const *,int,int,int,int)
0x180025d8e  mov     r13d, eax
0x180025d91  mov     rcx, [rbp+47h+arg_0]
0x180025d95  mov     rcx, [rcx+20h]
0x180025d99  mov     rdx, [rcx]
0x180025d9c  mov     rax, [rdx]
0x180025d9f  mov     dword ptr [rsp+0C0h+lpdwindex], r13d
0x180025da4  mov     r9, [rbp+47h+arg_20]
0x180025da8  mov     r8, [rbp+47h+arg_18]
0x180025dac  mov     edx, [rbp+47h+arg_10]
0x180025daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025db4  test    eax, eax
0x180025db6  jns     short loc_180025DE9
0x180025db8  mov     rcx, cs:WPP_GLOBAL_Control
0x180025dbf  lea     rdx, WPP_GLOBAL_Control
0x180025dc6  cmp     rcx, rdx
0x180025dc9  jz      short loc_180025DF0
0x180025dcb  test    byte ptr [rcx+1Ch], 2
0x180025dcf  jz      short loc_180025DF0
0x180025dd1  mov     edx, 3Fh ; '?'
0x180025dd6  mov     r9d, eax
0x180025dd9  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180025de0  mov     rcx, [rcx+10h]
0x180025de4  call    WPP_SF_d
0x180025de9  mov     rcx, cs:WPP_GLOBAL_Control
0x180025df0  test    r13d, r13d
0x180025df3  jns     loc_180025F0A
0x180025df9  mov     rax, [rbp+47h+arg_0]
0x180025dfd  cmp     byte ptr [rax+40h], 0
0x180025e01  jnz     loc_180025F0A
0x180025e07  lea     eax, [r13+7FCEFF3Eh]
0x180025e0e  cmp     eax, 1
0x180025e11  jbe     loc_180025F0A
0x180025e17  mov     eax, r13d
0x180025e1a  and     eax, 1FFF0000h
0x180025e1f  cmp     eax, 860000h
0x180025e24  jz      loc_180025F0A
0x180025e2a  inc     r12d
0x180025e2d  cmp     r12d, 3
0x180025e31  jb      loc_180025B27
0x180025e37  jmp     loc_180025F0A
0x180025e3c  mov     rcx, [rbp+4Fh]; this
0x180025e40  lea     rax, aFveeasnetworks; "FveEasNetworkStatusCreate"
0x180025e47  mov     [rsp+0C0h+lpdwindex], rax; int
0x180025e4c  mov     r9d, edi; char *
0x180025e4f  mov     r8, r14; unsigned int
0x180025e52  mov     edx, 1F4h; void *
0x180025e57  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180025e5c  mov     rsi, [rbp+47h+var_48]
0x180025e60  jmp     loc_180025F0A
0x180025e65  lea     rax, aRegisterforsta; "RegisterForStatusChange"
0x180025e6c  mov     edx, 20Fh
0x180025e71  jmp     loc_180025EF6
0x180025e76  mov     edi, 8000001Ah
0x180025e7b  mov     rcx, [rbp+4Fh]; this
0x180025e7f  lea     rax, aCowaitformulti; "CoWaitForMultipleHandles"
0x180025e86  mov     [rsp+0C0h+lpdwindex], rax; int
0x180025e8b  mov     r9d, edi; char *
0x180025e8e  mov     r8, r14; unsigned int
0x180025e91  mov     edx, 21Fh; void *
0x180025e96  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180025e9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ea2  lea     rax, WPP_GLOBAL_Control
0x180025ea9  cmp     rcx, rax
0x180025eac  jz      short loc_180025F0A
0x180025eae  test    byte ptr [rcx+1Ch], 40h
0x180025eb2  jz      short loc_180025F0A
0x180025eb4  mov     edx, 3Eh ; '>'
0x180025eb9  mov     r9d, edi
0x180025ebc  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180025ec3  mov     rcx, [rcx+10h]
0x180025ec7  call    WPP_SF_d
0x180025ecc  jmp     short loc_180025F0A
0x180025ece  lea     rax, aRegisterforsta; "RegisterForStatusChange"
0x180025ed5  mov     edx, 21Ch
0x180025eda  jmp     short loc_180025EF6
0x180025edc  lea     rax, aGetcurrentstat; "GetCurrentStatus"
0x180025ee3  mov     edx, 1F7h
0x180025ee8  jmp     short loc_180025EF6
0x180025eea  lea     rax, aInitializecomI; "InitializeCom.Initialize"
0x180025ef1  mov     edx, 1EDh; void *
  ... truncated ...
```
