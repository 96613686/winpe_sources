# CFveApiBase::FveQueryBootIntegrityInfoImpl(_FVE_BOOT_INTEGRITY_INFO *)

- ea: `0x18007b7a8`
- end: `0x18007c88b`
- name: `?FveQueryBootIntegrityInfoImpl@CFveApiBase@@SAJPEAU_FVE_BOOT_INTEGRITY_INFO@@@Z`
- size: `4323`
- prototype: `__int64 __fastcall(struct _FVE_BOOT_INTEGRITY_INFO *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007b684`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180019128`
- `0x18003ed0c`
- `0x18003ed44`
- `0x18004dfe4`
- `0x18005e158`
- `0x18007b7a8`
- `0x180086534`
- `0x18009019c`
- `0x18009356c`
- `0x18009f470`
- `0x18011f010`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x18007b949`
- `ntdll!NtQuerySystemInformation` at `0x18007ba4d`
- `ntdll!NtQuerySystemInformation` at `0x18007bb45`
- `ntdll!NtQuerySystemInformation` at `0x18007b949`
- `ntdll!NtQuerySystemInformation` at `0x18007ba4d`
- `ntdll!NtQuerySystemInformation` at `0x18007bb45`
- `ntdll!RtlNtStatusToDosError` at `0x18007b98a`
- `ntdll!RtlNtStatusToDosError` at `0x18007ba89`
- `ntdll!RtlNtStatusToDosError` at `0x18007bb81`
- `ntdll!RtlNtStatusToDosError` at `0x18007be53`
- `ntdll!RtlNtStatusToDosError` at `0x18007beee`
- `ntdll!RtlNtStatusToDosError` at `0x18007bf9b`
- `ntdll!RtlNtStatusToDosError` at `0x18007c095`
- `ntdll!RtlNtStatusToDosError` at `0x18007c18f`
- `ntdll!RtlNtStatusToDosError` at `0x18007c288`
- `ntdll!RtlNtStatusToDosError` at `0x18007c32f`
- `ntdll!RtlNtStatusToDosError` at `0x18007c429`
- `ntdll!RtlNtStatusToDosError` at `0x18007c523`
- `ntdll!RtlNtStatusToDosError` at `0x18007c61d`
- `ntdll!RtlNtStatusToDosError` at `0x18007c717`
- `ntdll!RtlNtStatusToDosError` at `0x18007b98a`
- `ntdll!RtlNtStatusToDosError` at `0x18007ba89`
- `ntdll!RtlNtStatusToDosError` at `0x18007bb81`
- `ntdll!RtlNtStatusToDosError` at `0x18007be53`
- `ntdll!RtlNtStatusToDosError` at `0x18007beee`
- `ntdll!RtlNtStatusToDosError` at `0x18007bf9b`
- `ntdll!RtlNtStatusToDosError` at `0x18007c095`
- `ntdll!RtlNtStatusToDosError` at `0x18007c18f`
- `ntdll!RtlNtStatusToDosError` at `0x18007c288`
- `ntdll!RtlNtStatusToDosError` at `0x18007c32f`
- `ntdll!RtlNtStatusToDosError` at `0x18007c429`
- `ntdll!RtlNtStatusToDosError` at `0x18007c523`
- `ntdll!RtlNtStatusToDosError` at `0x18007c61d`
- `ntdll!RtlNtStatusToDosError` at `0x18007c717`
- `bcd!BcdCloseObject` at `0x18007c226`
- `bcd!BcdCloseObject` at `0x18007c7b1`
- `bcd!BcdCloseObject` at `0x18007c7e3`
- `bcd!BcdCloseObject` at `0x180123bb8`
- `bcd!BcdCloseObject` at `0x18007c226`
- `bcd!BcdCloseObject` at `0x18007c7b1`
- `bcd!BcdCloseObject` at `0x18007c7e3`
- `bcd!BcdCloseObject` at `0x180123bb8`
- `bcd!BcdGetElementData` at `0x18007bf4d`
- `bcd!BcdGetElementData` at `0x18007c04d`
- `bcd!BcdGetElementData` at `0x18007c147`
- `bcd!BcdGetElementData` at `0x18007c2e7`
- `bcd!BcdGetElementData` at `0x18007c3e1`
- `bcd!BcdGetElementData` at `0x18007c4db`
- `bcd!BcdGetElementData` at `0x18007c5d5`
- `bcd!BcdGetElementData` at `0x18007c6cf`
- `bcd!BcdGetElementData` at `0x18007bf4d`
- `bcd!BcdGetElementData` at `0x18007c04d`
- `bcd!BcdGetElementData` at `0x18007c147`
- `bcd!BcdGetElementData` at `0x18007c2e7`
- `bcd!BcdGetElementData` at `0x18007c3e1`
- `bcd!BcdGetElementData` at `0x18007c4db`
- `bcd!BcdGetElementData` at `0x18007c5d5`
- `bcd!BcdGetElementData` at `0x18007c6cf`
- `bcd!BcdOpenObject` at `0x18007beb2`
- `bcd!BcdOpenObject` at `0x18007c24c`
- `bcd!BcdOpenObject` at `0x18007beb2`
- `bcd!BcdOpenObject` at `0x18007c24c`
- `bcd!BcdCloseStore` at `0x18007c80c`
- `bcd!BcdCloseStore` at `0x180123bd5`
- `bcd!BcdCloseStore` at `0x18007c80c`
- `bcd!BcdCloseStore` at `0x180123bd5`
- `bcd!BcdOpenSystemStore` at `0x18007be17`
- `bcd!BcdOpenSystemStore` at `0x18007be17`

## pseudocode

```c
__int64 __fastcall CFveApiBase::FveQueryBootIntegrityInfoImpl(struct _FVE_BOOT_INTEGRITY_INFO *a1, __int64 a2)
{
  CFveTpm *v3; // r14
  unsigned int v4; // esi
  CFveTpm *v5; // rax
  int v6; // eax
  NTSTATUS v7; // eax
  NTSTATUS v8; // r15d
  signed int v9; // eax
  PVOID *v10; // rcx
  NTSTATUS v11; // eax
  __int64 v12; // rdx
  NTSTATUS v13; // r15d
  signed int v14; // eax
  NTSTATUS v15; // eax
  NTSTATUS v16; // r15d
  signed int v17; // eax
  PVOID *v18; // rcx
  int v19; // eax
  int CanFveUsePpf; // eax
  struct _TPM_API_HASH_DATA20 *v21; // r8
  int v22; // eax
  PVOID *v23; // rcx
  int v24; // eax
  NTSTATUS v25; // r15d
  signed int v26; // eax
  __int64 v27; // rdx
  int v28; // eax
  NTSTATUS v29; // r15d
  unsigned int ElementData; // r15d
  unsigned int v31; // r15d
  unsigned int v32; // r15d
  int v33; // eax
  NTSTATUS v34; // r15d
  unsigned int v35; // r15d
  unsigned int v36; // r15d
  unsigned int v37; // r15d
  unsigned int v38; // r15d
  unsigned int v39; // r15d
  int *v41; // [rsp+28h] [rbp-C0h]
  CFveTpm *v42; // [rsp+48h] [rbp-A0h]
  __int64 v43; // [rsp+58h] [rbp-90h] BYREF
  __int64 v44; // [rsp+60h] [rbp-88h] BYREF
  bool v45[4]; // [rsp+68h] [rbp-80h] BYREF
  int v46; // [rsp+6Ch] [rbp-7Ch] BYREF
  _WORD v47[2]; // [rsp+70h] [rbp-78h] BYREF
  ULONG ReturnLength; // [rsp+74h] [rbp-74h] BYREF
  int v49; // [rsp+78h] [rbp-70h] BYREF
  int v50; // [rsp+7Ch] [rbp-6Ch] BYREF
  int v51; // [rsp+80h] [rbp-68h] BYREF
  __int128 v52; // [rsp+84h] [rbp-64h]
  unsigned int v53; // [rsp+94h] [rbp-54h]
  _DWORD SystemInformation[8]; // [rsp+98h] [rbp-50h] BYREF

  v3 = 0;
  memset(SystemInformation, 0, sizeof(SystemInformation));
  v47[0] = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  ReturnLength = 0;
  v49 = 0;
  v50 = 0;
  v44 = 0;
  v43 = 0;
  v45[0] = 0;
  if ( !a1 )
  {
    v4 = -2147467261;
    goto LABEL_290;
  }
  *(_OWORD *)a1 = 0;
  *((_OWORD *)a1 + 1) = 0;
  *((_QWORD *)a1 + 4) = 0;
  *((_WORD *)a1 + 1) = 40;
  v5 = (CFveTpm *)operator new(0x8E8u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v5 )
  {
    v3 = CFveTpm::CFveTpm(v5, 0, 1);
    v42 = v3;
  }
  else
  {
    v3 = 0;
    v42 = 0;
  }
  if ( v3 )
  {
    v6 = CFveTpm::Bindings(v3);
    *((_DWORD *)a1 + 4) = v6;
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids,
          (unsigned int)v6);
      if ( *((_DWORD *)a1 + 4) == -2144845809 )
        *((_DWORD *)a1 + 4) = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
      *((_BYTE *)a1 + 8) |= 1u;
    }
    v7 = NtQuerySystemInformation(SystemBootEnvironmentInformation, SystemInformation, 0x20u, 0);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          39,
          WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids,
          (unsigned int)v7);
      v9 = RtlNtStatusToDosError(v8);
      v4 = v9;
      if ( v9 > 0 )
        v4 = (unsigned __int16)v9 | 0x80070000;
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids, v4);
LABEL_289:
        v3 = v42;
        goto LABEL_290;
      }
LABEL_278:
      v3 = v42;
      goto LABEL_291;
    }
    if ( SystemInformation[4] == 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
      *((_BYTE *)a1 + 8) |= 2u;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids,
        SystemInformation[4]);
    }
    ReturnLength = 2;
    v11 = NtQuerySystemInformation(SystemObjectInformation|0x80, v47, 2u, &ReturnLength);
    v13 = v11;
    if ( v11 >= 0 )
    {
      if ( LOBYTE(v47[0]) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
        *((_BYTE *)a1 + 8) |= 4u;
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids,
          (unsigned int)v11);
      v14 = RtlNtStatusToDosError(v13);
      if ( v14 > 0 )
        v14 = (unsigned __int16)v14 | 0x80070000;
      *((_DWORD *)a1 + 5) = v14;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          44,
          WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids,
          (unsigned int)v14);
    }
    if ( (*((_BYTE *)a1 + 8) & 4) != 0 )
    {
      ReturnLength = 24;
      v15 = NtQuerySystemInformation(SystemNonPagedPoolInformation|0x80, &v51, 0x18u, &ReturnLength);
      v16 = v15;
      if ( v15 >= 0 )
      {
        v18 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
          v18 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( (v53 & 0x10) != 0 )
        {
          if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 4) != 0 )
            WPP_SF_D(v18[2], 51, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids, v53);
          *((_BYTE *)a1 + 8) |= 0x40u;
        }
        else if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 8) != 0 )
        {
          WPP_SF_D(v18[2], 50, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids, v53);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            47,
            WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids,
            (unsigned int)v15);
        v17 = RtlNtStatusToDosError(v16);
        if ( v17 > 0 )
          v17 = (unsigned __int16)v17 | 0x80070000;
        *((_DWORD *)a1 + 8) = v17;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            48,
            WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids,
            (unsigned int)v17);
      }
    }
    if ( (*((_BYTE *)a1 + 8) & 3) != 3 )
    {
LABEL_113:
      *(_WORD *)v45 = 0;
      v46 = 0;
      v24 = BcdOpenSystemStore(&v44, v12);
      v25 = v24;
      if ( v24 >= 0 )
      {
        v28 = BcdOpenObject(v44, &GUID_WINDOWS_BOOTMGR, &v43);
        v29 = v28;
        if ( v28 >= 0 )
        {
          v46 = 2;
          *(_WORD *)v45 = 0;
          ElementData = BcdGetElementData(v43, 369098768, v45, &v46);
          if ( (int)(ElementData + 0x80000000) < 0 || ElementData == -1073741275 )
          {
            if ( v45[0] )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
              *((_BYTE *)a1 + 8) |= 0x80u;
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
            }
            v46 = 2;
            *(_WORD *)v45 = 0;
            v31 = BcdGetElementData(v43, 369098825, v45, &v46);
            if ( (int)(v31 + 0x80000000) < 0 || v31 == -1073741275 )
            {
              if ( v45[0] )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
                *((_BYTE *)a1 + 9) |= 0x20u;
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
              }
              v46 = 2;
              *(_WORD *)v45 = 0;
              v32 = BcdGetElementData(v43, 369098878, v45, &v46);
              if ( (int)(v32 + 0x80000000) < 0 || v32 == -1073741275 )
              {
                if ( v45[0] )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
                  *((_BYTE *)a1 + 9) |= 0x40u;
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
                }
                BcdCloseObject(v43);
                v43 = 0;
                v33 = BcdOpenObject(v44, &GUID_CURRENT_BOOT_ENTRY, &v43);
                v34 = v33;
                if ( v33 >= 0 )
                {
                  v46 = 2;
                  *(_WORD *)v45 = 0;
                  v35 = BcdGetElementData(v43, 369098768, v45, &v46);
                  if ( (int)(v35 + 0x80000000) < 0 || v35 == -1073741275 )
                  {
                    if ( v45[0] )
                    {
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                        WPP_SF_(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          81,
                          WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
                      *((_BYTE *)a1 + 9) |= 1u;
                    }
                    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    {
                      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
                    }
                    v46 = 2;
                    *(_WORD *)v45 = 0;
                    v36 = BcdGetElementData(v43, 637534368, v45, &v46);
                    if ( (int)(v36 + 0x80000000) < 0 || v36 == -1073741275 )
                    {
                      if ( v45[0] )
                      {
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                          WPP_SF_(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            85,
                            WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
                        *((_BYTE *)a1 + 9) |= 2u;
                      }
                      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                      {
                        WPP_SF_(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          84,
                          WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
                      }
                      v46 = 2;
                      *(_WORD *)v45 = 0;
                      v37 = BcdGetElementData(v43, 637534450, v45, &v46);
                      if ( (int)(v37 + 0x80000000) < 0 || v37 == -1073741275 )
                      {
                        if ( v45[0] )
                        {
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                          {
                            WPP_SF_(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              89,
                              WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
                          }
                          *((_BYTE *)a1 + 9) |= 4u;
                        }
                        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                        {
                          WPP_SF_(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            88,
                            WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
                        }
                        v46 = 2;
                        *(_WORD *)v45 = 0;
                        v38 = BcdGetElementData(v43, 369098825, v45, &v46);
                        if ( (int)(v38 + 0x80000000) < 0 || v38 == -1073741275 )
                        {
                          if ( v45[0] )
                          {
                            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                            {
                              WPP_SF_(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                93,
                                WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
                            }
                            *((_BYTE *)a1 + 9) |= 8u;
                          }
                          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                          {
                            WPP_SF_(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              92,
                              WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
                          }
                          v46 = 2;
                          *(_WORD *)v45 = 0;
                          v39 = BcdGetElementData(v43, 369098878, v45, &v46);
                          if ( (int)(v39 + 0x80000000) < 0 || v39 == -1073741275 )
                          {
                            if ( v45[0] )
                            {
                              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                              {
                                WPP_SF_(
                                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                                  97,
                                  WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
                              }
                              *((_BYTE *)a1 + 9) |= 0x10u;
                            }
                            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                            {
                              WPP_SF_(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                96,
                                WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
                            }
                            BcdCloseObject(v43);
                            v43 = 0;
                            goto LABEL_288;
                          }
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                          {
                            WPP_SF_d(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              94,
                              WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids,
                              v39);
                          }
                          v26 = RtlNtStatusToDosError(v39);
                          if ( v26 > 0 )
                            v26 = (unsigned __int16)v26 | 0x80070000;
                          *((_DWORD *)a1 + 9) = v26;
                          v10 = (PVOID *)WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                          {
                            v27 = 95;
                            goto LABEL_122;
                          }
                        }
                        else
                        {
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                          {
                            WPP_SF_d(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              90,
                              WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids,
                              v38);
                          }
                          v26 = RtlNtStatusToDosError(v38);
                          if ( v26 > 0 )
                            v26 = (unsigned __int16)v26 | 0x80070000;
                          *((_DWORD *)a1 + 9) = v26;
                          v10 = (PVOID *)WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                          {
                            v27 = 91;
                            goto LABEL_122;
                          }
                        }
                      }
                      else
                      {
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                          WPP_SF_d(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            86,
                            WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids,
                            v37);
                        v26 = RtlNtStatusToDosError(v37);
                        if ( v26 > 0 )
                          v26 = (unsigned __int16)v26 | 0x80070000;
                        *((_DWORD *)a1 + 9) = v26;
                        v10 = (PVOID *)WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                        {
                          v27 = 87;
                          goto LABEL_122;
                        }
                      }
                    }
                    else
                    {
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          82,
                          WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids,
                          v36);
                      v26 = RtlNtStatusToDosError(v36);
                      if ( v26 > 0 )
                        v26 = (unsigned __int16)v26 | 0x80070000;
                      *((_DWORD *)a1 + 9) = v26;
                      v10 = (PVOID *)WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                      {
                        v27 = 83;
                        goto LABEL_122;
                      }
                    }
                  }
                  else
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        78,
                        WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids,
                        v35);
                    v26 = RtlNtStatusToDosError(v35);
                    if ( v26 > 0 )
                      v26 = (unsigned __int16)v26 | 0x80070000;
                    *((_DWORD *)a1 + 9) = v26;
                    v10 = (PVOID *)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    {
                      v27 = 79;
                      goto LABEL_122;
                    }
                  }
                }
                else
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      76,
                      WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids,
                      (unsigned int)v33);
                  v26 = RtlNtStatusToDosError(v34);
                  if ( v26 > 0 )
                    v26 = (unsigned __int16)v26 | 0x80070000;
                  *((_DWORD *)a1 + 9) = v26;
                  v10 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    v27 = 77;
                    goto LABEL_122;
                  }
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    72,
                    WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids,
                    v32);
                v26 = RtlNtStatusToDosError(v32);
                if ( v26 > 0 )
                  v26 = (unsigned __int16)v26 | 0x80070000;
                *((_DWORD *)a1 + 9) = v26;
                v10 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v27 = 73;
                  goto LABEL_122;
                }
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids, v31);
              v26 = RtlNtStatusToDosError(v31);
              if ( v26 > 0 )
                v26 = (unsigned __int16)v26 | 0x80070000;
              *((_DWORD *)a1 + 9) = v26;
              v10 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v27 = 69;
                goto LABEL_122;
              }
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                64,
                WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids,
                ElementData);
            v26 = RtlNtStatusToDosError(ElementData);
            if ( v26 > 0 )
              v26 = (unsigned __int16)v26 | 0x80070000;
            *((_DWORD *)a1 + 9) = v26;
            v10 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v27 = 65;
              goto LABEL_122;
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              62,
              WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids,
              (unsigned int)v28);
          v26 = RtlNtStatusToDosError(v29);
          if ( v26 > 0 )
            v26 = (unsigned __int16)v26 | 0x80070000;
          *((_DWORD *)a1 + 9) = v26;
          v10 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v27 = 63;
            goto LABEL_122;
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            60,
            WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids,
            (unsigned int)v24);
        v26 = RtlNtStatusToDosError(v25);
        if ( v26 > 0 )
          v26 = (unsigned __int16)v26 | 0x80070000;
        *((_DWORD *)a1 + 9) = v26;
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v27 = 61;
LABEL_122:
          WPP_SF_d(v10[2], v27, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids, (unsigned int)v26);
LABEL_288:
          v4 = 0;
          goto LABEL_289;
        }
      }
      v4 = 0;
      goto LABEL_278;
    }
    v19 = CFveTpm::CheckForUefiSecureBoot(v42);
    *((_DWORD *)a1 + 6) = v19;
    if ( v19 >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
      *((_BYTE *)a1 + 8) |= 0x10u;
    }
    else if ( v19 == -2144272198 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
      *((_DWORD *)a1 + 6) = 0;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids,
        (unsigned int)v19);
    }
    CanFveUsePpf = CFveApiBase::CanFveUsePpf(v45);
    if ( CanFveUsePpf < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids,
        (unsigned int)CanFveUsePpf);
    if ( v45[0] )
      v22 = CFveTpm::PpfCheckSecureBootForBitLocker(v42, 0, (enum BitLockerSecureBootEvalState *)&v49, 0, 0, &v50, 0);
    else
      v22 = CFveTpm::TcgCheckSecureBootForBitLocker(
              v42,
              (enum BitLockerSecureBootEvalState *)&v49,
              v21,
              0,
              &v50,
              (struct _FVE_DATUM_PCR_DATA **)v41);
    *((_DWORD *)a1 + 7) = v22;
    if ( v22 >= 0 )
    {
      if ( v49 == 3 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
        *((_BYTE *)a1 + 8) |= 8u;
        goto LABEL_107;
      }
      v23 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
        goto LABEL_107;
      }
    }
    else
    {
      v23 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          56,
          WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids,
          (unsigned int)v22);
LABEL_107:
        v23 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    if ( v50 )
    {
      if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 8) != 0 )
        WPP_SF_(v23[2], 59, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids);
      *((_BYTE *)a1 + 8) |= 0x20u;
    }
    goto LABEL_113;
  }
  v4 = -2147024882;
LABEL_290:
  v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_291:
  if ( v43 )
  {
    BcdCloseObject(v43);
    v43 = 0;
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v44 )
  {
    BcdCloseStore(v44, a2);
    v44 = 0;
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 )
  {
    CFveTpm::`scalar deleting destructor'(v3, a2);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x20) != 0 )
    WPP_SF_d(v10[2], 98, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18007b7a8  mov     r11, rsp
0x18007b7ab  mov     [r11+10h], rbx
0x18007b7af  mov     [r11+18h], rsi
0x18007b7b3  push    rdi
0x18007b7b4  push    r12
0x18007b7b6  push    r13
0x18007b7b8  push    r14
0x18007b7ba  push    r15
0x18007b7bc  sub     rsp, 0C0h
0x18007b7c3  mov     rax, cs:__security_cookie
0x18007b7ca  xor     rax, rsp
0x18007b7cd  mov     [rsp+0E8h+var_30], rax
0x18007b7d5  mov     rsi, rcx
0x18007b7d8  mov     [rsp+0E8h+var_A8], 0
0x18007b7e0  xor     r14d, r14d
0x18007b7e3  mov     [rsp+0E8h+var_98], r14
0x18007b7e8  mov     [r11-50h], r14d
0x18007b7ec  xorps   xmm0, xmm0
0x18007b7ef  xor     eax, eax
0x18007b7f1  movups  xmmword ptr [r11-4Ch], xmm0
0x18007b7f6  movups  xmmword ptr [r11-40h], xmm0
0x18007b7fb  mov     [rsp+0E8h+var_78], ax
0x18007b800  mov     [r11-68h], eax
0x18007b804  movups  xmmword ptr [r11-64h], xmm0
0x18007b809  mov     [r11-54h], eax
0x18007b80d  mov     [rsp+0E8h+ReturnLength], eax
0x18007b811  mov     [rsp+0E8h+var_70], eax
0x18007b815  mov     [rsp+0E8h+var_6C], eax
0x18007b819  mov     [rsp+0E8h+var_88], rax
0x18007b81e  mov     [rsp+0E8h+var_90], rax
0x18007b823  mov     [rsp+0E8h+var_80], al
0x18007b827  test    rcx, rcx
0x18007b82a  jnz     short loc_18007B844
0x18007b82c  mov     esi, 80004003h
0x18007b831  lea     rbx, WPP_GLOBAL_Control
0x18007b838  lea     rdi, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids
0x18007b83f  jmp     loc_18007C7CF
0x18007b844  xor     eax, eax
0x18007b846  movups  xmmword ptr [rcx], xmm0
0x18007b849  movups  xmmword ptr [rcx+10h], xmm0
0x18007b84d  mov     [rcx+20h], rax
0x18007b851  mov     eax, 28h ; '('
0x18007b856  mov     [rcx+2], ax
0x18007b85a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007b861  mov     ecx, 8E8h; unsigned __int64
0x18007b866  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18007b86b  test    rax, rax
0x18007b86e  jz      short loc_18007B887
0x18007b870  mov     r8b, 1; bool
0x18007b873  xor     edx, edx; struct CFvePolicy *
0x18007b875  mov     rcx, rax; this
0x18007b878  call    ??0CFveTpm@@QEAA@PEBVCFvePolicy@@_N@Z; CFveTpm::CFveTpm(CFvePolicy const *,bool)
0x18007b87d  mov     r14, rax
0x18007b880  mov     [rsp+0E8h+var_A0], rax
0x18007b885  jmp     short loc_18007B88F
0x18007b887  xor     r14d, r14d
0x18007b88a  mov     [rsp+0E8h+var_A0], r14
0x18007b88f  mov     [rsp+0E8h+var_98], r14
0x18007b894  test    r14, r14
0x18007b897  jnz     short loc_18007B8A0
0x18007b899  mov     esi, 8007000Eh
0x18007b89e  jmp     short loc_18007B831
0x18007b8a0  mov     rcx, r14; this
0x18007b8a3  call    ?Bindings@CFveTpm@@QEAAJXZ; CFveTpm::Bindings(void)
0x18007b8a8  mov     [rsi+10h], eax
0x18007b8ab  test    eax, eax
0x18007b8ad  js      short loc_18007B8EC
0x18007b8af  lea     rbx, WPP_GLOBAL_Control
0x18007b8b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b8bd  mov     r12b, 8
0x18007b8c0  lea     rdi, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids
0x18007b8c7  cmp     rcx, rbx
0x18007b8ca  jz      short loc_18007B8E3
0x18007b8cc  test    [rcx+1Ch], r12b
0x18007b8d0  jz      short loc_18007B8E3
0x18007b8d2  mov     edx, 26h ; '&'
0x18007b8d7  mov     r8, rdi
0x18007b8da  mov     rcx, [rcx+10h]
0x18007b8de  call    WPP_SF_
0x18007b8e3  or      byte ptr [rsi+8], 1
0x18007b8e7  mov     r13b, 4
0x18007b8ea  jmp     short loc_18007B936
0x18007b8ec  lea     rbx, WPP_GLOBAL_Control
0x18007b8f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b8fa  mov     r13b, 4
0x18007b8fd  lea     rdi, WPP_80990c6a43d238ec89f8cb6dc8894978_Traceguids
0x18007b904  cmp     rcx, rbx
0x18007b907  jz      short loc_18007B923
0x18007b909  test    [rcx+1Ch], r13b
0x18007b90d  jz      short loc_18007B923
0x18007b90f  mov     edx, 25h ; '%'
0x18007b914  mov     r9d, eax
0x18007b917  mov     r8, rdi
0x18007b91a  mov     rcx, [rcx+10h]
0x18007b91e  call    WPP_SF_d
0x18007b923  mov     r12b, 8
0x18007b926  cmp     dword ptr [rsi+10h], 8028400Fh
0x18007b92d  jnz     short loc_18007B936
0x18007b92f  mov     dword ptr [rsi+10h], 0
0x18007b936  xor     r9d, r9d; ReturnLength
0x18007b939  lea     r8d, [r9+20h]; SystemInformationLength
0x18007b93d  lea     rdx, [rsp+0E8h+SystemInformation]; SystemInformation
0x18007b945  lea     ecx, [r9+5Ah]; SystemInformationClass
0x18007b949  call    cs:__imp_NtQuerySystemInformation
0x18007b950  nop     dword ptr [rax+rax+00h]
0x18007b955  mov     r15d, eax
0x18007b958  test    eax, eax
0x18007b95a  jns     short loc_18007B9D8
0x18007b95c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b963  mov     r14d, 2
0x18007b969  cmp     rcx, rbx
0x18007b96c  jz      short loc_18007B987
0x18007b96e  test    [rcx+1Ch], r14b
0x18007b972  jz      short loc_18007B987
0x18007b974  lea     edx, [r14+25h]
0x18007b978  mov     r9d, eax
0x18007b97b  mov     r8, rdi
0x18007b97e  mov     rcx, [rcx+10h]
0x18007b982  call    WPP_SF_d
0x18007b987  mov     ecx, r15d; Status
0x18007b98a  call    cs:__imp_RtlNtStatusToDosError
0x18007b991  nop     dword ptr [rax+rax+00h]
0x18007b996  mov     esi, eax
0x18007b998  test    eax, eax
0x18007b99a  jle     short loc_18007B9A5
0x18007b99c  movzx   esi, ax
0x18007b99f  or      esi, 80070000h
0x18007b9a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b9ac  cmp     rcx, rbx
0x18007b9af  jz      loc_18007C752
0x18007b9b5  test    [rcx+1Ch], r14b
0x18007b9b9  jz      loc_18007C752
0x18007b9bf  mov     edx, 28h ; '('
0x18007b9c4  mov     r9d, esi
0x18007b9c7  mov     r8, rdi
0x18007b9ca  mov     rcx, [rcx+10h]
0x18007b9ce  call    WPP_SF_d
0x18007b9d3  jmp     loc_18007C7CA
0x18007b9d8  mov     r9d, [rsp+0E8h+var_40]
0x18007b9e0  mov     r14d, 2
0x18007b9e6  cmp     r9d, r14d
0x18007b9e9  jz      short loc_18007BA0F
0x18007b9eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b9f2  cmp     rcx, rbx
0x18007b9f5  jz      short loc_18007BA36
0x18007b9f7  test    [rcx+1Ch], r13b
0x18007b9fb  jz      short loc_18007BA36
0x18007b9fd  lea     edx, [r14+27h]
0x18007ba01  mov     r8, rdi
0x18007ba04  mov     rcx, [rcx+10h]
0x18007ba08  call    WPP_SF_D
0x18007ba0d  jmp     short loc_18007BA36
0x18007ba0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ba16  cmp     rcx, rbx
0x18007ba19  jz      short loc_18007BA32
0x18007ba1b  test    [rcx+1Ch], r12b
0x18007ba1f  jz      short loc_18007BA32
0x18007ba21  mov     edx, 2Ah ; '*'
0x18007ba26  mov     r8, rdi
0x18007ba29  mov     rcx, [rcx+10h]
0x18007ba2d  call    WPP_SF_
0x18007ba32  or      [rsi+8], r14b
0x18007ba36  mov     [rsp+0E8h+ReturnLength], r14d
0x18007ba3b  lea     r9, [rsp+0E8h+ReturnLength]; ReturnLength
0x18007ba40  mov     r8d, r14d; SystemInformationLength
0x18007ba43  lea     rdx, [rsp+0E8h+var_78]; SystemInformation
0x18007ba48  mov     ecx, 91h; SystemInformationClass
0x18007ba4d  call    cs:__imp_NtQuerySystemInformation
0x18007ba54  nop     dword ptr [rax+rax+00h]
0x18007ba59  mov     r15d, eax
0x18007ba5c  test    eax, eax
0x18007ba5e  jns     short loc_18007BACC
0x18007ba60  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ba67  cmp     rcx, rbx
0x18007ba6a  jz      short loc_18007BA86
0x18007ba6c  test    [rcx+1Ch], r14b
0x18007ba70  jz      short loc_18007BA86
0x18007ba72  mov     edx, 2Bh ; '+'
0x18007ba77  mov     r9d, eax
0x18007ba7a  mov     r8, rdi
0x18007ba7d  mov     rcx, [rcx+10h]
0x18007ba81  call    WPP_SF_d
0x18007ba86  mov     ecx, r15d; Status
0x18007ba89  call    cs:__imp_RtlNtStatusToDosError
0x18007ba90  nop     dword ptr [rax+rax+00h]
0x18007ba95  test    eax, eax
0x18007ba97  jle     short loc_18007BAA1
0x18007ba99  movzx   eax, ax
0x18007ba9c  or      eax, 80070000h
0x18007baa1  mov     [rsi+14h], eax
0x18007baa4  mov     rcx, cs:WPP_GLOBAL_Control
0x18007baab  cmp     rcx, rbx
0x18007baae  jz      short loc_18007BB1F
0x18007bab0  test    [rcx+1Ch], r14b
0x18007bab4  jz      short loc_18007BB1F
0x18007bab6  mov     edx, 2Ch ; ','
0x18007babb  mov     r9d, eax
0x18007babe  mov     r8, rdi
0x18007bac1  mov     rcx, [rcx+10h]
0x18007bac5  call    WPP_SF_d
0x18007baca  jmp     short loc_18007BB1F
0x18007bacc  cmp     byte ptr [rsp+0E8h+var_78], 0
0x18007bad1  jz      short loc_18007BAFC
0x18007bad3  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bada  cmp     rcx, rbx
0x18007badd  jz      short loc_18007BAF6
0x18007badf  test    [rcx+1Ch], r12b
0x18007bae3  jz      short loc_18007BAF6
0x18007bae5  mov     edx, 2Dh ; '-'
0x18007baea  mov     r8, rdi
0x18007baed  mov     rcx, [rcx+10h]
0x18007baf1  call    WPP_SF_
0x18007baf6  or      [rsi+8], r13b
0x18007bafa  jmp     short loc_18007BB1F
0x18007bafc  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bb03  cmp     rcx, rbx
0x18007bb06  jz      short loc_18007BB1F
0x18007bb08  test    [rcx+1Ch], r12b
0x18007bb0c  jz      short loc_18007BB1F
0x18007bb0e  mov     edx, 2Eh ; '.'
0x18007bb13  mov     r8, rdi
0x18007bb16  mov     rcx, [rcx+10h]
0x18007bb1a  call    WPP_SF_
0x18007bb1f  test    [rsi+8], r13b
0x18007bb23  jz      loc_18007BC42
0x18007bb29  mov     r8d, 18h; SystemInformationLength
0x18007bb2f  mov     [rsp+0E8h+ReturnLength], r8d
0x18007bb34  lea     r9, [rsp+0E8h+ReturnLength]; ReturnLength
0x18007bb39  lea     rdx, [rsp+0E8h+var_68]; SystemInformation
0x18007bb41  lea     ecx, [r8+77h]; SystemInformationClass
0x18007bb45  call    cs:__imp_NtQuerySystemInformation
0x18007bb4c  nop     dword ptr [rax+rax+00h]
0x18007bb51  mov     r15d, eax
0x18007bb54  test    eax, eax
0x18007bb56  jns     short loc_18007BBCC
0x18007bb58  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bb5f  cmp     rcx, rbx
0x18007bb62  jz      short loc_18007BB7E
0x18007bb64  test    [rcx+1Ch], r14b
0x18007bb68  jz      short loc_18007BB7E
0x18007bb6a  mov     edx, 2Fh ; '/'
0x18007bb6f  mov     r9d, eax
0x18007bb72  mov     r8, rdi
0x18007bb75  mov     rcx, [rcx+10h]
0x18007bb79  call    WPP_SF_d
0x18007bb7e  mov     ecx, r15d; Status
0x18007bb81  call    cs:__imp_RtlNtStatusToDosError
0x18007bb88  nop     dword ptr [rax+rax+00h]
0x18007bb8d  test    eax, eax
0x18007bb8f  jle     short loc_18007BB99
0x18007bb91  movzx   eax, ax
0x18007bb94  or      eax, 80070000h
0x18007bb99  mov     [rsi+20h], eax
0x18007bb9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bba3  cmp     rcx, rbx
0x18007bba6  jz      loc_18007BC42
0x18007bbac  test    [rcx+1Ch], r14b
0x18007bbb0  jz      loc_18007BC42
0x18007bbb6  mov     edx, 30h ; '0'
0x18007bbbb  mov     r9d, eax
0x18007bbbe  mov     r8, rdi
0x18007bbc1  mov     rcx, [rcx+10h]
0x18007bbc5  call    WPP_SF_d
0x18007bbca  jmp     short loc_18007BC42
0x18007bbcc  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bbd3  cmp     rcx, rbx
0x18007bbd6  jz      short loc_18007BBF6
0x18007bbd8  test    [rcx+1Ch], r12b
0x18007bbdc  jz      short loc_18007BBF6
0x18007bbde  mov     edx, 31h ; '1'
0x18007bbe3  mov     r8, rdi
0x18007bbe6  mov     rcx, [rcx+10h]
0x18007bbea  call    WPP_SF_
0x18007bbef  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bbf6  mov     r9d, [rsp+0E8h+var_54]
0x18007bbfe  test    r9b, 10h
0x18007bc02  jnz     short loc_18007BC22
0x18007bc04  cmp     rcx, rbx
0x18007bc07  jz      short loc_18007BC42
0x18007bc09  test    [rcx+1Ch], r12b
0x18007bc0d  jz      short loc_18007BC42
0x18007bc0f  mov     edx, 32h ; '2'
0x18007bc14  mov     r8, rdi
0x18007bc17  mov     rcx, [rcx+10h]
0x18007bc1b  call    WPP_SF_D
0x18007bc20  jmp     short loc_18007BC42
0x18007bc22  cmp     rcx, rbx
0x18007bc25  jz      short loc_18007BC3E
0x18007bc27  test    [rcx+1Ch], r13b
0x18007bc2b  jz      short loc_18007BC3E
0x18007bc2d  mov     edx, 33h ; '3'
0x18007bc32  mov     r8, rdi
0x18007bc35  mov     rcx, [rcx+10h]
0x18007bc39  call    WPP_SF_D
0x18007bc3e  or      byte ptr [rsi+8], 40h
0x18007bc42  mov     al, [rsi+8]
0x18007bc45  and     al, 3
0x18007bc47  cmp     al, 3
0x18007bc49  jnz     loc_18007BE07
0x18007bc4f  mov     r15, [rsp+0E8h+var_A0]
  ... truncated ...
```
