# WicaPostInstallp_PopulateExeInfo(HKEY__ *,ushort const *)

- ea: `0x18005190c`
- end: `0x18005218f`
- name: `?WicaPostInstallp_PopulateExeInfo@@YAKPEAUHKEY__@@PEBG@Z`
- size: `2179`
- prototype: `unsigned int __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800af3d0`

## callees

- `0x180012920`
- `0x1800212b0`
- `0x18005190c`
- `0x180056256`
- `0x18007a9cf`
- `0x1800f1f10`
- `0x1800f1fd0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180051d42`
- `msvcrt!_wcsicmp` at `0x180051d65`
- `msvcrt!_wcsicmp` at `0x180051d89`
- `msvcrt!_wcsicmp` at `0x180051dad`
- `msvcrt!_wcsicmp` at `0x180051dd1`
- `msvcrt!_wcsicmp` at `0x180051d42`
- `msvcrt!_wcsicmp` at `0x180051d65`
- `msvcrt!_wcsicmp` at `0x180051d89`
- `msvcrt!_wcsicmp` at `0x180051dad`
- `msvcrt!_wcsicmp` at `0x180051dd1`
- `ntdll!RtlReAllocateHeap` at `0x18005206c`
- `ntdll!RtlReAllocateHeap` at `0x18005206c`
- `ntdll!RtlAllocateHeap` at `0x18005204c`
- `ntdll!RtlAllocateHeap` at `0x18005204c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800519c2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051a2a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051a7e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051ab3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051ae6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051b31`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051b6b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051bb8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051c21`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051c77`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051cc5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051d16`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051e22`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051e73`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051ed7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051f3b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051f8f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800519c2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051a2a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051a7e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051ab3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051ae6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051b31`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051b6b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051bb8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051c21`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051c77`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051cc5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051d16`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051e22`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051e73`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051ed7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051f3b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051f8f`

## string_xrefs

- `0x1800519db`: `WicaPostInstallp_PopulateExeInfo`
- `0x180051bbe`: `WicaPostInstallp_PopulateExeInfo`
- `0x180052152`: `WicaPostInstallp_PopulateExeInfo`
- `0x180051a54`: `FwLink`
- `0x180051c00`: `ExeFullPath`
- `0x180051c2d`: `RegGetValue Failed for ExeFullPath [%d] [%ls]`
- `0x180051b97`: `ArpFullPath`
- `0x180051bd3`: `RegGetValue Failed for ArpPath [%d] [%ls]`
- `0x180051dc3`: `MigXmlNotifyUser`
- `0x180051d7b`: `HBCompatibleUpdateAvailable`
- `0x180051d9f`: `InstallAfterUpgrade`
- `0x180051d34`: `ReinstallAfterUpgrade`
- `0x180051d57`: `SBCompatibleUpdateAvailable`

## pseudocode

```c
__int64 __fastcall WicaPostInstallp_PopulateExeInfo(HKEY a1, const unsigned __int16 *a2)
{
  unsigned int ValueW; // ebx
  const char *v5; // r9
  int v6; // r8d
  ULONGLONG v7; // r15
  __int64 v8; // rbx
  __int64 v9; // r9
  ULONGLONG v10; // rbx
  size_t v11; // r12
  PVOID v12; // rax
  PVOID Heap; // rdi
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+44h] [rbp-BCh] BYREF
  ULONGLONG Size; // [rsp+48h] [rbp-B8h] BYREF
  ULONGLONG pullResult[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE Src[2048]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pvData[2048]; // [rsp+860h] [rbp+760h] BYREF
  _BYTE v21[4]; // [rsp+1060h] [rbp+F60h] BYREF
  _BYTE v22[4]; // [rsp+1064h] [rbp+F64h] BYREF
  BOOL v23; // [rsp+1068h] [rbp+F68h]
  _BYTE v24[2048]; // [rsp+106Ch] [rbp+F6Ch] BYREF
  _BYTE v25[520]; // [rsp+186Ch] [rbp+176Ch] BYREF
  _BYTE v26[520]; // [rsp+1A74h] [rbp+1974h] BYREF
  _BYTE v27[520]; // [rsp+1C7Ch] [rbp+1B7Ch] BYREF
  _BYTE v28[256]; // [rsp+1E84h] [rbp+1D84h] BYREF
  _BYTE v29[256]; // [rsp+1F84h] [rbp+1E84h] BYREF
  int v30; // [rsp+2084h] [rbp+1F84h]
  _BYTE v31[4]; // [rsp+2088h] [rbp+1F88h] BYREF
  int v32; // [rsp+208Ch] [rbp+1F8Ch] BYREF
  int v33; // [rsp+2090h] [rbp+1F90h] BYREF
  _BYTE v34[4]; // [rsp+2094h] [rbp+1F94h] BYREF
  _BYTE v35[8]; // [rsp+2098h] [rbp+1F98h] BYREF
  wchar_t String1[128]; // [rsp+20A0h] [rbp+1FA0h] BYREF

  memset_0(String1, 0, sizeof(String1));
  memset_0(Src, 0, 0x203Cu);
  v16 = 0;
  if ( !a1 || !a2 )
  {
    ValueW = 1359;
    v5 = "Null arguments passed in.";
    v6 = 691;
    goto LABEL_62;
  }
  pcbData = 2048;
  ValueW = RegGetValueW(a1, a2, L"AppName", 0x20000002u, 0, Src, &pcbData);
  if ( ValueW )
  {
    v5 = "RegGetValue Failed for AppName [%d] [%ls]";
    v6 = 715;
LABEL_62:
    AslLogCallPrintf(1, (unsigned int)"WicaPostInstallp_PopulateExeInfo", v6, (_DWORD)v5);
    return ValueW;
  }
  pcbData = 2048;
  ValueW = RegGetValueW(a1, a2, L"VendorName", 0x20000002u, 0, pvData, &pcbData);
  if ( ValueW )
  {
    v5 = "RegGetValue Failed for VendorName [%d] [%ls]";
    v6 = 733;
    goto LABEL_62;
  }
  pcbData = 4;
  RegGetValueW(a1, a2, L"FwLink", 0x20000010u, 0, v21, &pcbData);
  pcbData = 4;
  RegGetValueW(a1, a2, L"KbArticle", 0x20000010u, 0, v22, &pcbData);
  pcbData = 4;
  if ( !RegGetValueW(a1, a2, L"IsAntiMalware", 0x20000010u, 0, &v16, &pcbData) )
    v23 = v16 != 0;
  pcbData = 2048;
  RegGetValueW(a1, a2, L"StoreId", 0x20000002u, 0, v24, &pcbData);
  pcbData = 520;
  ValueW = RegGetValueW(a1, a2, L"ExeName", 0x20000002u, 0, v25, &pcbData);
  if ( ValueW )
  {
    v5 = "RegGetValue Failed for ExeName [%d] [%ls]";
    v6 = 813;
    goto LABEL_62;
  }
  pcbData = 520;
  if ( RegGetValueW(a1, a2, L"ArpFullPath", 0x20000002u, 0, v26, &pcbData) )
    AslLogCallPrintf(
      1,
      (unsigned int)"WicaPostInstallp_PopulateExeInfo",
      831,
      (unsigned int)"RegGetValue Failed for ArpPath [%d] [%ls]");
  pcbData = 520;
  ValueW = RegGetValueW(a1, a2, L"ExeFullPath", 0x20000002u, 0, v27, &pcbData);
  if ( ValueW )
  {
    v5 = "RegGetValue Failed for ExeFullPath [%d] [%ls]";
    v6 = 849;
    goto LABEL_62;
  }
  pcbData = 256;
  ValueW = RegGetValueW(a1, a2, L"ExeGuid", 0x20000002u, 0, v28, &pcbData);
  if ( ValueW )
  {
    v5 = "RegGetValue Failed for ExeGuid [%d] [%ls]";
    v6 = 867;
    goto LABEL_62;
  }
  pcbData = 256;
  ValueW = RegGetValueW(a1, a2, L"DbGuid", 0x20000002u, 0, v29, &pcbData);
  if ( ValueW )
  {
    v5 = "RegGetValue Failed for DB GUID [%d] [%ls]";
    v6 = 885;
    goto LABEL_62;
  }
  pcbData = 256;
  ValueW = RegGetValueW(a1, a2, L"ActionType", 0x20000002u, 0, String1, &pcbData);
  if ( ValueW )
  {
    v5 = "RegGetValue Failed for Action [%d] [%ls]";
    v6 = 903;
    goto LABEL_62;
  }
  if ( _wcsicmp(String1, L"ReinstallAfterUpgrade") )
  {
    if ( _wcsicmp(String1, L"SBCompatibleUpdateAvailable") )
    {
      if ( _wcsicmp(String1, L"HBCompatibleUpdateAvailable") )
      {
        if ( _wcsicmp(String1, L"InstallAfterUpgrade") )
        {
          if ( _wcsicmp(String1, L"MigXmlNotifyUser") )
          {
            v5 = "Error in action for given EXE, type is unknown.";
            v6 = 921;
            goto LABEL_62;
          }
          v30 = 16;
        }
        else
        {
          v30 = 8;
        }
      }
      else
      {
        v30 = 4;
      }
    }
    else
    {
      v30 = 2;
    }
  }
  else
  {
    v30 = 1;
  }
  pcbData = 4;
  ValueW = RegGetValueW(a1, a2, L"ExeIndexInApp", 0x20000010u, 0, v31, &pcbData);
  if ( ValueW )
  {
    v5 = "RegGetValue Failed for ExeIndexInApp [%d] [%ls]";
    v6 = 936;
    goto LABEL_62;
  }
  pcbData = 4;
  if ( RegGetValueW(a1, a2, L"NTFSFileIdLow", 0x20000010u, 0, &v32, &pcbData) )
  {
    v32 = 0;
    AslLogCallPrintf(
      1,
      (unsigned int)"WicaPostInstallp_PopulateExeInfo",
      955,
      (unsigned int)"RegGetValue Failed for FileIdLow [%d] [%ls]");
  }
  pcbData = 4;
  if ( RegGetValueW(a1, a2, L"NTFSFileIdHigh", 0x20000010u, 0, &v33, &pcbData) )
  {
    v33 = 0;
    AslLogCallPrintf(
      1,
      (unsigned int)"WicaPostInstallp_PopulateExeInfo",
      970,
      (unsigned int)"RegGetValue Failed for FileIdHigh [%d] [%ls]");
  }
  pcbData = 4;
  ValueW = RegGetValueW(a1, a2, L"CentralNotificationInit", 0x20000010u, 0, v34, &pcbData);
  if ( (ValueW & 0xFFFFFFFD) != 0 )
  {
    v5 = "RegGetValue Failed for CentralNotificationInit [%d] [%ls]";
    v6 = 989;
    goto LABEL_62;
  }
  pcbData = 4;
  ValueW = RegGetValueW(a1, a2, L"RuntimeNotificationInit", 0x20000010u, 0, v35, &pcbData);
  if ( (ValueW & 0xFFFFFFFD) != 0 )
  {
    v5 = "RegGetValue Failed for runtimeNotificationInit [%d] [%ls]";
    v6 = 1010;
    goto LABEL_62;
  }
  v7 = xmmword_1801598D8;
  if ( xmmword_1801598D8 >= *(&xmmword_1801598D8 + 1) )
  {
    if ( xmmword_1801598D8 + 1 <= *(&xmmword_1801598D8 + 1) )
    {
      ValueW = -1073741811;
LABEL_59:
      AslLogCallPrintf(
        1,
        (unsigned int)"WicaPostInstallp_PopulateExeInfo",
        1021,
        (unsigned int)"ExeEntries.Append Failed [%d]");
      return ValueW;
    }
    v8 = xmmword_1801598E8 - 1;
    if ( (unsigned __int64)xmmword_1801598E8 + xmmword_1801598D8 < xmmword_1801598D8 + 1
      || (Size = 0, ULongLongMult(*(&xmmword_1801598D8 + 1), (ULONGLONG)*(&xmmword_1801598C8 + 1), pullResult) < 0)
      || (v10 = v9 & ~v8, ULongLongMult(v10, (ULONGLONG)*(&xmmword_1801598C8 + 1), &Size) < 0) )
    {
      ValueW = -1073741675;
      goto LABEL_59;
    }
    v11 = Size;
    if ( *((_QWORD *)&xmmword_1801598E8 + 1) )
    {
      Heap = RtlReAllocateHeap(xmmword_1801598C8, 0, *((PVOID *)&xmmword_1801598E8 + 1), Size);
    }
    else
    {
      v12 = RtlAllocateHeap(xmmword_1801598C8, 0, Size);
      Heap = v12;
      if ( v12 )
        memset_0(v12, 0, v11);
    }
    if ( !Heap )
    {
      ValueW = -1073741801;
      goto LABEL_59;
    }
    *((_QWORD *)&xmmword_1801598E8 + 1) = Heap;
    *(&xmmword_1801598D8 + 1) = v10;
  }
  Size = 0;
  if ( ULongLongMult((ULONGLONG)*(&xmmword_1801598C8 + 1), v7, &Size) < 0
    || *((_QWORD *)&xmmword_1801598E8 + 1) + Size < *((_QWORD *)&xmmword_1801598E8 + 1) )
  {
    ValueW = -1073741675;
    goto LABEL_59;
  }
  memcpy_0((void *)(*((_QWORD *)&xmmword_1801598E8 + 1) + Size), Src, 0x203Cu);
  ++xmmword_1801598D8;
  AslLogCallPrintf(
    3,
    (unsigned int)"WicaPostInstallp_PopulateExeInfo",
    1026,
    (unsigned int)"Added new Exe entry for %ls to global list.");
  return 0;
}

```

## disassembly

```asm
0x18005190c  mov     [rsp-8+arg_10], rbx
0x180051911  push    rbp
0x180051912  push    rsi
0x180051913  push    rdi
0x180051914  push    r12
0x180051916  push    r13
0x180051918  push    r14
0x18005191a  push    r15
0x18005191c  lea     rbp, [rsp-20B0h]
0x180051924  mov     eax, 21B0h
0x180051929  call    _alloca_probe
0x18005192e  sub     rsp, rax
0x180051931  mov     rax, cs:__security_cookie
0x180051938  xor     rax, rsp
0x18005193b  mov     [rbp+20E0h+var_40], rax
0x180051942  mov     rdi, rdx
0x180051945  mov     r15, rcx
0x180051948  xor     edx, edx; Val
0x18005194a  lea     rcx, [rbp+20E0h+String1]; void *
0x180051951  mov     r8d, 100h; Size
0x180051957  call    memset_0
0x18005195c  xor     edx, edx; Val
0x18005195e  lea     rcx, [rsp+21E0h+Src]; void *
0x180051963  mov     r8d, 203Ch; Size
0x180051969  call    memset_0
0x18005196e  xor     r13d, r13d
0x180051971  mov     [rsp+21E0h+var_219C], r13d
0x180051976  test    r15, r15
0x180051979  jz      loc_180052140
0x18005197f  test    rdi, rdi
0x180051982  jz      loc_180052140
0x180051988  lea     rax, [rsp+21E0h+var_21A0]
0x18005198d  mov     r12d, 20000002h
0x180051993  mov     [rsp+21E0h+pcbData], rax; pcbData
0x180051998  lea     r8, aAppname; "AppName"
0x18005199f  lea     rax, [rsp+21E0h+Src]
0x1800519a4  mov     r14d, 800h
0x1800519aa  mov     [rsp+21E0h+pvData], rax; pvData
0x1800519af  mov     r9d, r12d; dwFlags
0x1800519b2  mov     rdx, rdi; lpSubKey
0x1800519b5  mov     [rsp+21E0h+pdwType], r13; pdwType
0x1800519ba  mov     rcx, r15; hkey
0x1800519bd  mov     [rsp+21E0h+var_21A0], r14d
0x1800519c2  call    cs:__imp_RegGetValueW
0x1800519c8  mov     ebx, eax
0x1800519ca  test    eax, eax
0x1800519cc  jz      short loc_1800519FA
0x1800519ce  lea     r9, aReggetvalueFai_12; "RegGetValue Failed for AppName [%d] [%l"...
0x1800519d5  mov     r8d, 2CBh
0x1800519db  lea     rdx, aWicapostinstal_8; "WicaPostInstallp_PopulateExeInfo"
0x1800519e2  mov     ecx, 1
0x1800519e7  mov     [rsp+21E0h+pvData], rdi
0x1800519ec  mov     dword ptr [rsp+21E0h+pdwType], eax
0x1800519f0  call    AslLogCallPrintf
0x1800519f5  jmp     loc_180052163
0x1800519fa  lea     rax, [rsp+21E0h+var_21A0]
0x1800519ff  mov     [rsp+21E0h+var_21A0], r14d
0x180051a04  mov     [rsp+21E0h+pcbData], rax; pcbData
0x180051a09  lea     r8, aVendorname; "VendorName"
0x180051a10  lea     rax, [rbp+20E0h+var_1980]
0x180051a17  mov     r9d, r12d; dwFlags
0x180051a1a  mov     [rsp+21E0h+pvData], rax; pvData
0x180051a1f  mov     rdx, rdi; lpSubKey
0x180051a22  mov     rcx, r15; hkey
0x180051a25  mov     [rsp+21E0h+pdwType], r13; pdwType
0x180051a2a  call    cs:__imp_RegGetValueW
0x180051a30  mov     ebx, eax
0x180051a32  test    eax, eax
0x180051a34  jz      short loc_180051A45
0x180051a36  lea     r9, aReggetvalueFai_2; "RegGetValue Failed for VendorName [%d] "...
0x180051a3d  mov     r8d, 2DDh
0x180051a43  jmp     short loc_1800519DB
0x180051a45  lea     rax, [rsp+21E0h+var_21A0]
0x180051a4a  mov     esi, 20000010h
0x180051a4f  mov     [rsp+21E0h+pcbData], rax; pcbData
0x180051a54  lea     r8, aFwlink; "FwLink"
0x180051a5b  lea     rax, [rbp+20E0h+var_1180]
0x180051a62  mov     ebx, 4
0x180051a67  mov     [rsp+21E0h+pvData], rax; pvData
0x180051a6c  mov     r9d, esi; dwFlags
0x180051a6f  mov     rdx, rdi; lpSubKey
0x180051a72  mov     [rsp+21E0h+pdwType], r13; pdwType
0x180051a77  mov     rcx, r15; hkey
0x180051a7a  mov     [rsp+21E0h+var_21A0], ebx
0x180051a7e  call    cs:__imp_RegGetValueW
0x180051a84  lea     rax, [rsp+21E0h+var_21A0]
0x180051a89  mov     [rsp+21E0h+var_21A0], ebx
0x180051a8d  mov     [rsp+21E0h+pcbData], rax; pcbData
0x180051a92  lea     r8, aKbarticle; "KbArticle"
0x180051a99  lea     rax, [rbp+20E0h+var_117C]
0x180051aa0  mov     r9d, esi; dwFlags
0x180051aa3  mov     [rsp+21E0h+pvData], rax; pvData
0x180051aa8  mov     rdx, rdi; lpSubKey
0x180051aab  mov     rcx, r15; hkey
0x180051aae  mov     [rsp+21E0h+pdwType], r13; pdwType
0x180051ab3  call    cs:__imp_RegGetValueW
0x180051ab9  lea     rax, [rsp+21E0h+var_21A0]
0x180051abe  mov     [rsp+21E0h+var_21A0], ebx
0x180051ac2  mov     [rsp+21E0h+pcbData], rax; pcbData
0x180051ac7  lea     r8, aIsantimalware; "IsAntiMalware"
0x180051ace  lea     rax, [rsp+21E0h+var_219C]
0x180051ad3  mov     r9d, esi; dwFlags
0x180051ad6  mov     [rsp+21E0h+pvData], rax; pvData
0x180051adb  mov     rdx, rdi; lpSubKey
0x180051ade  mov     rcx, r15; hkey
0x180051ae1  mov     [rsp+21E0h+pdwType], r13; pdwType
0x180051ae6  call    cs:__imp_RegGetValueW
0x180051aec  test    eax, eax
0x180051aee  jnz     short loc_180051B01
0x180051af0  cmp     [rsp+21E0h+var_219C], r13d
0x180051af5  mov     eax, r13d
0x180051af8  setnz   al
0x180051afb  mov     [rbp+20E0h+var_1178], eax
0x180051b01  lea     rax, [rsp+21E0h+var_21A0]
0x180051b06  mov     [rsp+21E0h+var_21A0], r14d
0x180051b0b  mov     [rsp+21E0h+pcbData], rax; pcbData
0x180051b10  lea     r8, aStoreid; "StoreId"
0x180051b17  lea     rax, [rbp+20E0h+var_1174]
0x180051b1e  mov     r9d, r12d; dwFlags
0x180051b21  mov     [rsp+21E0h+pvData], rax; pvData
0x180051b26  mov     rdx, rdi; lpSubKey
0x180051b29  mov     rcx, r15; hkey
0x180051b2c  mov     [rsp+21E0h+pdwType], r13; pdwType
0x180051b31  call    cs:__imp_RegGetValueW
0x180051b37  lea     rax, [rsp+21E0h+var_21A0]
0x180051b3c  mov     esi, 208h
0x180051b41  mov     [rsp+21E0h+pcbData], rax; pcbData
0x180051b46  lea     r8, aExename; "ExeName"
0x180051b4d  lea     rax, [rbp+20E0h+var_974]
0x180051b54  mov     [rsp+21E0h+var_21A0], esi
0x180051b58  mov     [rsp+21E0h+pvData], rax; pvData
0x180051b5d  mov     r9d, r12d; dwFlags
0x180051b60  mov     rdx, rdi; lpSubKey
0x180051b63  mov     [rsp+21E0h+pdwType], r13; pdwType
0x180051b68  mov     rcx, r15; hkey
0x180051b6b  call    cs:__imp_RegGetValueW
0x180051b71  mov     ebx, eax
0x180051b73  test    eax, eax
0x180051b75  jz      short loc_180051B89
0x180051b77  lea     r9, aReggetvalueFai_3; "RegGetValue Failed for ExeName [%d] [%l"...
0x180051b7e  mov     r8d, 32Dh
0x180051b84  jmp     loc_1800519DB
0x180051b89  lea     rax, [rsp+21E0h+var_21A0]
0x180051b8e  mov     [rsp+21E0h+var_21A0], esi
0x180051b92  mov     [rsp+21E0h+pcbData], rax; pcbData
0x180051b97  lea     r8, aArpfullpath; "ArpFullPath"
0x180051b9e  lea     rax, [rbp+20E0h+var_76C]
0x180051ba5  mov     r9d, r12d; dwFlags
0x180051ba8  mov     [rsp+21E0h+pvData], rax; pvData
0x180051bad  mov     rdx, rdi; lpSubKey
0x180051bb0  mov     rcx, r15; hkey
0x180051bb3  mov     [rsp+21E0h+pdwType], r13; pdwType
0x180051bb8  call    cs:__imp_RegGetValueW
0x180051bbe  lea     r14, aWicapostinstal_8; "WicaPostInstallp_PopulateExeInfo"
0x180051bc5  mov     esi, 1
0x180051bca  test    eax, eax
0x180051bcc  jz      short loc_180051BEE
0x180051bce  mov     [rsp+21E0h+pvData], rdi
0x180051bd3  lea     r9, aReggetvalueFai_8; "RegGetValue Failed for ArpPath [%d] [%l"...
0x180051bda  mov     r8d, 33Fh
0x180051be0  mov     dword ptr [rsp+21E0h+pdwType], eax
0x180051be4  mov     rdx, r14
0x180051be7  mov     ecx, esi
0x180051be9  call    AslLogCallPrintf
0x180051bee  lea     rax, [rsp+21E0h+var_21A0]
0x180051bf3  mov     [rsp+21E0h+var_21A0], 208h
0x180051bfb  mov     [rsp+21E0h+pcbData], rax; pcbData
0x180051c00  lea     r8, aExefullpath; "ExeFullPath"
0x180051c07  lea     rax, [rbp+20E0h+var_564]
0x180051c0e  mov     r9d, r12d; dwFlags
0x180051c11  mov     [rsp+21E0h+pvData], rax; pvData
0x180051c16  mov     rdx, rdi; lpSubKey
0x180051c19  mov     rcx, r15; hkey
0x180051c1c  mov     [rsp+21E0h+pdwType], r13; pdwType
0x180051c21  call    cs:__imp_RegGetValueW
0x180051c27  mov     ebx, eax
0x180051c29  test    eax, eax
0x180051c2b  jz      short loc_180051C44
0x180051c2d  lea     r9, aReggetvalueFai_9; "RegGetValue Failed for ExeFullPath [%d]"...
0x180051c34  mov     r8d, 351h
0x180051c3a  mov     rdx, r14
0x180051c3d  mov     ecx, esi
0x180051c3f  jmp     loc_1800519E7
0x180051c44  lea     rax, [rsp+21E0h+var_21A0]
0x180051c49  mov     [rsp+21E0h+var_21A0], 100h
0x180051c51  mov     [rsp+21E0h+pcbData], rax; pcbData
0x180051c56  lea     r8, aExeguid; "ExeGuid"
0x180051c5d  lea     rax, [rbp+20E0h+var_35C]
0x180051c64  mov     r9d, r12d; dwFlags
0x180051c67  mov     [rsp+21E0h+pvData], rax; pvData
0x180051c6c  mov     rdx, rdi; lpSubKey
0x180051c6f  mov     rcx, r15; hkey
0x180051c72  mov     [rsp+21E0h+pdwType], r13; pdwType
0x180051c77  call    cs:__imp_RegGetValueW
0x180051c7d  mov     ebx, eax
0x180051c7f  test    eax, eax
0x180051c81  jz      short loc_180051C92
0x180051c83  lea     r9, aReggetvalueFai_10; "RegGetValue Failed for ExeGuid [%d] [%l"...
0x180051c8a  mov     r8d, 363h
0x180051c90  jmp     short loc_180051C3A
0x180051c92  lea     rax, [rsp+21E0h+var_21A0]
0x180051c97  mov     [rsp+21E0h+var_21A0], 100h
0x180051c9f  mov     [rsp+21E0h+pcbData], rax; pcbData
0x180051ca4  lea     r8, aDbguid; "DbGuid"
0x180051cab  lea     rax, [rbp+20E0h+var_25C]
0x180051cb2  mov     r9d, r12d; dwFlags
0x180051cb5  mov     [rsp+21E0h+pvData], rax; pvData
0x180051cba  mov     rdx, rdi; lpSubKey
0x180051cbd  mov     rcx, r15; hkey
0x180051cc0  mov     [rsp+21E0h+pdwType], r13; pdwType
0x180051cc5  call    cs:__imp_RegGetValueW
0x180051ccb  mov     ebx, eax
0x180051ccd  test    eax, eax
0x180051ccf  jz      short loc_180051CE3
0x180051cd1  lea     r9, aReggetvalueFai; "RegGetValue Failed for DB GUID [%d] [%l"...
0x180051cd8  mov     r8d, 375h
0x180051cde  jmp     loc_180051C3A
0x180051ce3  lea     rax, [rsp+21E0h+var_21A0]
0x180051ce8  mov     [rsp+21E0h+var_21A0], 100h
0x180051cf0  mov     [rsp+21E0h+pcbData], rax; pcbData
0x180051cf5  lea     r8, aActiontype; "ActionType"
0x180051cfc  lea     rax, [rbp+20E0h+String1]
0x180051d03  mov     r9d, r12d; dwFlags
0x180051d06  mov     [rsp+21E0h+pvData], rax; pvData
0x180051d0b  mov     rdx, rdi; lpSubKey
0x180051d0e  mov     rcx, r15; hkey
0x180051d11  mov     [rsp+21E0h+pdwType], r13; pdwType
0x180051d16  call    cs:__imp_RegGetValueW
0x180051d1c  mov     ebx, eax
0x180051d1e  test    eax, eax
0x180051d20  jz      short loc_180051D34
0x180051d22  lea     r9, aReggetvalueFai_7; "RegGetValue Failed for Action [%d] [%ls"...
0x180051d29  mov     r8d, 387h
0x180051d2f  jmp     loc_180051C3A
0x180051d34  lea     rdx, aReinstallafter; "ReinstallAfterUpgrade"
0x180051d3b  lea     rcx, [rbp+20E0h+String1]; String1
0x180051d42  call    cs:__imp__wcsicmp
0x180051d48  test    eax, eax
0x180051d4a  jnz     short loc_180051D57
0x180051d4c  mov     [rbp+20E0h+var_15C], esi
0x180051d52  jmp     loc_180051DE9
0x180051d57  lea     rdx, aSbcompatibleup; "SBCompatibleUpdateAvailable"
0x180051d5e  lea     rcx, [rbp+20E0h+String1]; String1
0x180051d65  call    cs:__imp__wcsicmp
0x180051d6b  test    eax, eax
0x180051d6d  jnz     short loc_180051D7B
0x180051d6f  mov     [rbp+20E0h+var_15C], 2
0x180051d79  jmp     short loc_180051DE9
0x180051d7b  lea     rdx, aHbcompatibleup; "HBCompatibleUpdateAvailable"
0x180051d82  lea     rcx, [rbp+20E0h+String1]; String1
0x180051d89  call    cs:__imp__wcsicmp
0x180051d8f  test    eax, eax
0x180051d91  jnz     short loc_180051D9F
0x180051d93  mov     [rbp+20E0h+var_15C], 4
0x180051d9d  jmp     short loc_180051DE9
0x180051d9f  lea     rdx, aInstallafterup; "InstallAfterUpgrade"
0x180051da6  lea     rcx, [rbp+20E0h+String1]; String1
0x180051dad  call    cs:__imp__wcsicmp
0x180051db3  test    eax, eax
0x180051db5  jnz     short loc_180051DC3
0x180051db7  mov     [rbp+20E0h+var_15C], 8
0x180051dc1  jmp     short loc_180051DE9
0x180051dc3  lea     rdx, aMigxmlnotifyus; "MigXmlNotifyUser"
0x180051dca  lea     rcx, [rbp+20E0h+String1]; String1
0x180051dd1  call    cs:__imp__wcsicmp
0x180051dd7  test    eax, eax
0x180051dd9  jnz     loc_18005212C
0x180051ddf  mov     [rbp+20E0h+var_15C], 10h
0x180051de9  lea     rax, [rsp+21E0h+var_21A0]
0x180051dee  mov     [rsp+21E0h+var_21A0], 4
0x180051df6  mov     [rsp+21E0h+pcbData], rax; pcbData
0x180051dfb  lea     r8, aExeindexinapp; "ExeIndexInApp"
0x180051e02  lea     rax, [rbp+20E0h+var_158]
0x180051e09  mov     r12d, 20000010h
0x180051e0f  mov     [rsp+21E0h+pvData], rax; pvData
0x180051e14  mov     r9d, r12d; dwFlags
0x180051e17  mov     rdx, rdi; lpSubKey
0x180051e1a  mov     [rsp+21E0h+pdwType], r13; pdwType
0x180051e1f  mov     rcx, r15; hkey
0x180051e22  call    cs:__imp_RegGetValueW
0x180051e28  mov     ebx, eax
0x180051e2a  test    eax, eax
0x180051e2c  jz      short loc_180051E40
0x180051e2e  lea     r9, aReggetvalueFai_5; "RegGetValue Failed for ExeIndexInApp [%"...
0x180051e35  mov     r8d, 3A8h
0x180051e3b  jmp     loc_180051C3A
0x180051e40  lea     rax, [rsp+21E0h+var_21A0]
0x180051e45  mov     [rsp+21E0h+var_21A0], 4
0x180051e4d  mov     [rsp+21E0h+pcbData], rax; pcbData
0x180051e52  lea     r8, aNtfsfileidlow; "NTFSFileIdLow"
0x180051e59  lea     rax, [rbp+20E0h+var_154]
0x180051e60  mov     r9d, r12d; dwFlags
0x180051e63  mov     [rsp+21E0h+pvData], rax; pvData
0x180051e68  mov     rdx, rdi; lpSubKey
0x180051e6b  mov     rcx, r15; hkey
0x180051e6e  mov     [rsp+21E0h+pdwType], r13; pdwType
0x180051e73  call    cs:__imp_RegGetValueW
0x180051e79  test    eax, eax
0x180051e7b  jz      short loc_180051EA4
0x180051e7d  mov     [rsp+21E0h+pvData], rdi
  ... truncated ...
```
