# CDtcConfig::SaveTraceSettings(_DTC_TRACE_SETTINGS)

- ea: `0x1800161e0`
- end: `0x1800164ea`
- name: `?SaveTraceSettings@CDtcConfig@@UEAAJU_DTC_TRACE_SETTINGS@@@Z`
- size: `778`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800161e0`
- `0x180018ba0`
- `0x18001c924`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800162d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016344`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800163b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800162d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016344`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800163b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001647c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001648b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001649a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800164a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001647c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001648b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001649a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800164a8`

## string_xrefs

- `0x180016210`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x18001635b`: `Failed to open options key`
- `0x1800163ce`: `Failed to open transactions key`
- `0x1800162eb`: `Failed to open modules key`
- `0x180016232`: `CDtcConfig::SaveTraceSettings`

## pseudocode

```c
__int64 __fastcall CDtcConfig::SaveTraceSettings(CDtcConfig *a1, unsigned int *a2)
{
  HKEY v2; // rsi
  signed int HKLM; // ebx
  const wchar_t *v6; // rax
  __int64 v7; // r9
  LSTATUS v8; // eax
  CDtcConfig *v9; // rcx
  LSTATUS v10; // eax
  CDtcConfig *v11; // rcx
  LSTATUS v12; // eax
  CDtcConfig *v13; // rcx
  CDtcConfig *v14; // rcx
  unsigned int v15; // r9d
  __int64 v17; // [rsp+28h] [rbp-28h]
  HKEY v18; // [rsp+40h] [rbp-10h] BYREF
  HKEY v19; // [rsp+90h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp+50h] BYREF
  HKEY phkResult; // [rsp+A8h] [rbp+58h] BYREF

  v2 = 0;
  phkResult = 0;
  v18 = 0;
  v19 = 0;
  hKey = 0;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    1299,
    L"CDtcConfig::SaveTraceSettings",
    0,
    L"In");
  if ( !*((_DWORD *)a1 + 7) )
  {
    HKLM = -2147024846;
    v6 = L"SaveTraceSettings is not supported on a remote host";
    v7 = 1305;
LABEL_30:
    LODWORD(v17) = HKLM;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
      v7,
      L"CDtcConfig::SaveTraceSettings",
      v17,
      v6);
    goto LABEL_31;
  }
  HKLM = CDtcConfig::GetHKLM(a1, &hKey);
  if ( HKLM < 0 )
  {
    LODWORD(v17) = HKLM;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
      1312,
      L"CDtcConfig::SaveTraceSettings",
      v17,
      L"GetHKLM failed");
    v2 = hKey;
    goto LABEL_31;
  }
  v2 = hKey;
  v8 = RegOpenKeyExW(
         hKey,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Tracing\\MSDTC\\Modules",
         0,
         2u,
         &phkResult);
  HKLM = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      HKLM = (unsigned __int16)v8 | 0x80070000;
    v6 = L"Failed to open modules key";
    v7 = 1324;
    goto LABEL_30;
  }
  HKLM = CDtcConfig::WriteRegDWORD(v9, phkResult, L"Active", *a2);
  if ( HKLM < 0 )
  {
    v6 = L"Failed to set active value (mod)";
    v7 = 1331;
    goto LABEL_30;
  }
  v10 = RegOpenKeyExW(
          v2,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Tracing\\MSDTC\\LoggingOptions",
          0,
          2u,
          &v18);
  HKLM = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      HKLM = (unsigned __int16)v10 | 0x80070000;
    v6 = L"Failed to open options key";
    v7 = 1343;
    goto LABEL_30;
  }
  HKLM = CDtcConfig::WriteRegDWORD(v11, v18, L"MaxBuffers", a2[6]);
  if ( HKLM < 0 )
  {
    v6 = L"Failed to set max buffer count";
    v7 = 1352;
    goto LABEL_30;
  }
  v12 = RegOpenKeyExW(
          v2,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Tracing\\MSDTC\\Modules\\Transaction_Transitions",
          0,
          2u,
          &v19);
  if ( v12 )
  {
    if ( v12 > 0 )
      HKLM = (unsigned __int16)v12 | 0x80070000;
    else
      HKLM = v12;
    LODWORD(v17) = v12;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
      1364,
      L"CDtcConfig::SaveTraceSettings",
      v17,
      L"Failed to open transactions key");
  }
  else
  {
    HKLM = CDtcConfig::WriteRegDWORD(v13, v19, L"Active", a2[1]);
    if ( HKLM < 0 )
    {
      v6 = L"Failed to set the active value (xact)";
      v7 = 1371;
      goto LABEL_30;
    }
    if ( a2[2] )
    {
      v15 = 0xFFFFFF;
    }
    else
    {
      v15 = a2[3] != 0;
      if ( a2[4] )
        v15 |= 2u;
    }
    HKLM = CDtcConfig::WriteRegDWORD(v14, v19, L"ControlFlags", v15);
    if ( HKLM < 0 )
    {
      v6 = L"Failed to set the control flags";
      v7 = 1396;
      goto LABEL_30;
    }
  }
LABEL_31:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v18 )
    RegCloseKey(v18);
  if ( v19 )
    RegCloseKey(v19);
  if ( v2 )
    RegCloseKey(v2);
  LODWORD(v17) = HKLM;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    1406,
    L"CDtcConfig::SaveTraceSettings",
    v17,
    L"Out");
  return (unsigned int)HKLM;
}

```

## disassembly

```asm
0x1800161e0  push    rbp
0x1800161e2  push    rbx
0x1800161e3  push    rsi
0x1800161e4  push    rdi
0x1800161e5  push    r12
0x1800161e7  push    r13
0x1800161e9  push    r15
0x1800161eb  mov     rbp, rsp
0x1800161ee  sub     rsp, 50h
0x1800161f2  xor     esi, esi
0x1800161f4  mov     [rbp+arg_18], 0
0x1800161fc  lea     rax, aIn_0; "In"
0x180016203  mov     [rbp+var_10], 0
0x18001620b  mov     [rsp+50h+var_20], rax
0x180016210  lea     r15, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180016217  mov     rdi, rdx
0x18001621a  mov     [rsp+50h+var_28], rsi
0x18001621f  mov     rbx, rcx
0x180016222  mov     [rbp+arg_0], 0
0x18001622a  lea     r12d, [rsi+0Fh]
0x18001622e  mov     [rbp+hKey], rsi
0x180016232  lea     r13, aCdtcconfigSave; "CDtcConfig::SaveTraceSettings"
0x180016239  mov     ecx, r12d
0x18001623c  mov     r9d, 513h
0x180016242  mov     [rsp+50h+phkResult], r13
0x180016247  mov     r8, r15
0x18001624a  lea     edx, [rsi+6]
0x18001624d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180016252  cmp     [rbx+1Ch], esi
0x180016255  jnz     short loc_18001626E
0x180016257  mov     ebx, 80070032h
0x18001625c  lea     rax, aSavetracesetti; "SaveTraceSettings is not supported on a"...
0x180016263  mov     r9d, 519h
0x180016269  jmp     loc_180016455
0x18001626e  lea     rdx, [rbp+hKey]; HKEY *
0x180016272  mov     rcx, rbx; this
0x180016275  call    ?GetHKLM@CDtcConfig@@AEAAJPEAPEAUHKEY__@@@Z; CDtcConfig::GetHKLM(HKEY__ * *)
0x18001627a  mov     ebx, eax
0x18001627c  test    eax, eax
0x18001627e  jns     short loc_1800162B4
0x180016280  lea     rax, aGethklmFailed; "GetHKLM failed"
0x180016287  mov     r9d, 520h
0x18001628d  mov     [rsp+50h+var_20], rax
0x180016292  mov     r8, r15
0x180016295  mov     dword ptr [rsp+50h+var_28], ebx
0x180016299  mov     edx, 1
0x18001629e  mov     ecx, r12d
0x1800162a1  mov     [rsp+50h+phkResult], r13
0x1800162a6  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800162ab  mov     rsi, [rbp+hKey]
0x1800162af  jmp     loc_180016473
0x1800162b4  mov     rsi, [rbp+hKey]
0x1800162b8  lea     rax, [rbp+arg_18]
0x1800162bc  mov     rcx, rsi; hKey
0x1800162bf  mov     [rsp+50h+phkResult], rax; phkResult
0x1800162c4  mov     r9d, 2; samDesired
0x1800162ca  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800162d1  xor     r8d, r8d; ulOptions
0x1800162d4  call    cs:__imp_RegOpenKeyExW
0x1800162da  mov     ebx, eax
0x1800162dc  test    eax, eax
0x1800162de  jz      short loc_1800162FD
0x1800162e0  jle     short loc_1800162EB
0x1800162e2  movzx   ebx, ax
0x1800162e5  or      ebx, 80070000h
0x1800162eb  lea     rax, aFailedToOpenMo; "Failed to open modules key"
0x1800162f2  mov     r9d, 52Ch
0x1800162f8  jmp     loc_180016455
0x1800162fd  mov     r9d, [rdi]; unsigned int
0x180016300  lea     r8, aActive; "Active"
0x180016307  mov     rdx, [rbp+arg_18]; HKEY
0x18001630b  call    ?WriteRegDWORD@CDtcConfig@@AEAAJPEAUHKEY__@@PEBGK@Z; CDtcConfig::WriteRegDWORD(HKEY__ *,ushort const *,ulong)
0x180016310  mov     ebx, eax
0x180016312  test    eax, eax
0x180016314  jns     short loc_180016328
0x180016316  lea     rax, aFailedToSetAct; "Failed to set active value (mod)"
0x18001631d  mov     r9d, 533h
0x180016323  jmp     loc_180016455
0x180016328  lea     rax, [rbp+var_10]
0x18001632c  mov     r9d, 2; samDesired
0x180016332  xor     r8d, r8d; ulOptions
0x180016335  mov     [rsp+50h+phkResult], rax; phkResult
0x18001633a  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180016341  mov     rcx, rsi; hKey
0x180016344  call    cs:__imp_RegOpenKeyExW
0x18001634a  mov     ebx, eax
0x18001634c  test    eax, eax
0x18001634e  jz      short loc_18001636D
0x180016350  jle     short loc_18001635B
0x180016352  movzx   ebx, ax
0x180016355  or      ebx, 80070000h
0x18001635b  lea     rax, aFailedToOpenOp; "Failed to open options key"
0x180016362  mov     r9d, 53Fh
0x180016368  jmp     loc_180016455
0x18001636d  mov     r9d, [rdi+18h]; unsigned int
0x180016371  lea     r8, aMaxbuffers; "MaxBuffers"
0x180016378  mov     rdx, [rbp+var_10]; HKEY
0x18001637c  call    ?WriteRegDWORD@CDtcConfig@@AEAAJPEAUHKEY__@@PEBGK@Z; CDtcConfig::WriteRegDWORD(HKEY__ *,ushort const *,ulong)
0x180016381  mov     ebx, eax
0x180016383  test    eax, eax
0x180016385  jns     short loc_180016399
0x180016387  lea     rax, aFailedToSetMax; "Failed to set max buffer count"
0x18001638e  mov     r9d, 548h
0x180016394  jmp     loc_180016455
0x180016399  lea     rax, [rbp+arg_0]
0x18001639d  mov     r9d, 2; samDesired
0x1800163a3  xor     r8d, r8d; ulOptions
0x1800163a6  mov     [rsp+50h+phkResult], rax; phkResult
0x1800163ab  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800163b2  mov     rcx, rsi; hKey
0x1800163b5  call    cs:__imp_RegOpenKeyExW
0x1800163bb  test    eax, eax
0x1800163bd  jz      short loc_1800163E6
0x1800163bf  jg      short loc_1800163C5
0x1800163c1  mov     ebx, eax
0x1800163c3  jmp     short loc_1800163CE
0x1800163c5  movzx   ebx, ax
0x1800163c8  or      ebx, 80070000h
0x1800163ce  lea     rcx, aFailedToOpenTr; "Failed to open transactions key"
0x1800163d5  mov     r9d, 554h
0x1800163db  mov     [rsp+50h+var_20], rcx
0x1800163e0  mov     dword ptr [rsp+50h+var_28], eax
0x1800163e4  jmp     short loc_18001645E
0x1800163e6  mov     r9d, [rdi+4]; unsigned int
0x1800163ea  lea     r8, aActive; "Active"
0x1800163f1  mov     rdx, [rbp+arg_0]; HKEY
0x1800163f5  call    ?WriteRegDWORD@CDtcConfig@@AEAAJPEAUHKEY__@@PEBGK@Z; CDtcConfig::WriteRegDWORD(HKEY__ *,ushort const *,ulong)
0x1800163fa  mov     ebx, eax
0x1800163fc  test    eax, eax
0x1800163fe  jns     short loc_18001640F
0x180016400  lea     rax, aFailedToSetThe_0; "Failed to set the active value (xact)"
0x180016407  mov     r9d, 55Bh
0x18001640d  jmp     short loc_180016455
0x18001640f  cmp     dword ptr [rdi+8], 0
0x180016413  jz      short loc_18001641D
0x180016415  mov     r9d, 0FFFFFFh
0x18001641b  jmp     short loc_180016432
0x18001641d  xor     r9d, r9d
0x180016420  cmp     [rdi+0Ch], r9d
0x180016424  setnz   r9b
0x180016428  cmp     dword ptr [rdi+10h], 0
0x18001642c  jz      short loc_180016432
0x18001642e  or      r9d, 2; unsigned int
0x180016432  mov     rdx, [rbp+arg_0]; HKEY
0x180016436  lea     r8, aControlflags; "ControlFlags"
0x18001643d  call    ?WriteRegDWORD@CDtcConfig@@AEAAJPEAUHKEY__@@PEBGK@Z; CDtcConfig::WriteRegDWORD(HKEY__ *,ushort const *,ulong)
0x180016442  mov     ebx, eax
0x180016444  test    eax, eax
0x180016446  jns     short loc_180016473
0x180016448  lea     rax, aFailedToSetThe; "Failed to set the control flags"
0x18001644f  mov     r9d, 574h
0x180016455  mov     [rsp+50h+var_20], rax
0x18001645a  mov     dword ptr [rsp+50h+var_28], ebx
0x18001645e  mov     r8, r15
0x180016461  mov     [rsp+50h+phkResult], r13
0x180016466  mov     edx, 1
0x18001646b  mov     ecx, r12d
0x18001646e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180016473  mov     rcx, [rbp+arg_18]; hKey
0x180016477  test    rcx, rcx
0x18001647a  jz      short loc_180016482
0x18001647c  call    cs:__imp_RegCloseKey
0x180016482  mov     rcx, [rbp+var_10]; hKey
0x180016486  test    rcx, rcx
0x180016489  jz      short loc_180016491
0x18001648b  call    cs:__imp_RegCloseKey
0x180016491  mov     rcx, [rbp+arg_0]; hKey
0x180016495  test    rcx, rcx
0x180016498  jz      short loc_1800164A0
0x18001649a  call    cs:__imp_RegCloseKey
0x1800164a0  test    rsi, rsi
0x1800164a3  jz      short loc_1800164AE
0x1800164a5  mov     rcx, rsi; hKey
0x1800164a8  call    cs:__imp_RegCloseKey
0x1800164ae  lea     rax, aOut; "Out"
0x1800164b5  mov     r9d, 57Eh
0x1800164bb  mov     [rsp+50h+var_20], rax
0x1800164c0  mov     r8, r15
0x1800164c3  mov     dword ptr [rsp+50h+var_28], ebx
0x1800164c7  mov     edx, 6
0x1800164cc  mov     ecx, r12d
0x1800164cf  mov     [rsp+50h+phkResult], r13
0x1800164d4  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800164d9  mov     eax, ebx
0x1800164db  add     rsp, 50h
0x1800164df  pop     r15
0x1800164e1  pop     r13
0x1800164e3  pop     r12
0x1800164e5  pop     rdi
0x1800164e6  pop     rsi
0x1800164e7  pop     rbx
0x1800164e8  pop     rbp
0x1800164e9  retn
```
