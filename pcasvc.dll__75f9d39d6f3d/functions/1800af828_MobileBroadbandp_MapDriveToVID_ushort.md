# MobileBroadbandp_MapDriveToVID(ushort)

- ea: `0x1800af828`
- end: `0x1800afba5`
- name: `?MobileBroadbandp_MapDriveToVID@@YAHG@Z`
- size: `893`
- prototype: `__int64 __fastcall(unsigned __int16)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, registry_config`

## callers

- `0x18003b750`

## callees

- `0x18000dc08`
- `0x180012920`
- `0x18007a9cf`
- `0x1800af698`
- `0x1800af828`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!_wcslwr` at `0x1800afaa6`
- `msvcrt!_wcslwr` at `0x1800afaa6`
- `msvcrt!_wcsicmp` at `0x1800afa71`
- `msvcrt!_wcsicmp` at `0x1800afa71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af8db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af92b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afaeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afb1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afb35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af8db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af92b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afaeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afb1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afb35`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800af8d1`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800afa5b`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800af8d1`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800afa5b`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x1800afa95`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x1800afa95`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Parent` at `0x1800afacc`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Parent` at `0x1800afacc`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800af95d`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800af95d`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800af91c`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800af91c`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800af9c2`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800af9c2`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800afb7e`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800afb7e`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800afa1d`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800afa1d`

## string_xrefs

- `0x1800afb0b`: `Failed to format device path with stringcchprintf [%d]`
- `0x1800af931`: `Failed to create a device list [%d]`

## pseudocode

```c
__int64 __fastcall MobileBroadbandp_MapDriveToVID(WCHAR a1)
{
  unsigned int IsDeviceOnWatchlist; // r15d
  const char *v2; // r9
  int v3; // r8d
  __int64 DeviceInfoList; // rax
  __int64 v5; // rdi
  const char *v6; // r9
  int v7; // r8d
  int v8; // ecx
  unsigned int v9; // r14d
  DEVINST v10; // ecx
  int v11; // esi
  __int64 pdnDevInst; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v14; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v15; // [rsp+48h] [rbp-B8h]
  __int128 v16; // [rsp+58h] [rbp-A8h] BYREF
  DEVINST dnDevInst[4]; // [rsp+68h] [rbp-98h]
  __int128 v18; // [rsp+78h] [rbp-88h]
  WCHAR szVolumeName[56]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR String1[56]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR szVolumeMountPoint; // [rsp+170h] [rbp+70h] BYREF
  int v22; // [rsp+172h] [rbp+72h]
  __int16 v23; // [rsp+176h] [rbp+76h]
  int v24; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v25[524]; // [rsp+384h] [rbp+284h] BYREF
  WCHAR Buffer[512]; // [rsp+590h] [rbp+490h] BYREF

  szVolumeMountPoint = a1;
  pdnDevInst = 0x21000000000LL;
  v22 = 6029370;
  v23 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  *(_OWORD *)dnDevInst = 0;
  v18 = 0;
  memset_0(szVolumeName, 0, 0x64u);
  memset_0(String1, 0, 0x64u);
  memset_0(&v24, 0, 0x210u);
  IsDeviceOnWatchlist = 0;
  if ( !GetVolumeNameForVolumeMountPointW(&szVolumeMountPoint, szVolumeName, 0x32u) )
  {
    GetLastError();
    v2 = "Failed to get volume name [%d]";
    v3 = 392;
LABEL_3:
    AslLogCallPrintf(1, (unsigned int)"MobileBroadbandp_MapDriveToVID", v3, (_DWORD)v2);
    return IsDeviceOnWatchlist;
  }
  DeviceInfoList = DevObjCreateDeviceInfoList(&GUID_DEVCLASS_CDROM, 0, 0, 0, 0);
  v5 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    GetLastError();
    v2 = "Failed to create a device list [%d]";
    v3 = 399;
    goto LABEL_3;
  }
  if ( (unsigned int)DevObjGetClassDevs(
                       DeviceInfoList,
                       &GUID_DEVINTERFACE_VOLUME,
                       0,
                       18,
                       0,
                       0,
                       pdnDevInst,
                       v14,
                       *((_QWORD *)&v14 + 1),
                       v15,
                       *((_QWORD *)&v15 + 1),
                       v16,
                       *((_QWORD *)&v16 + 1),
                       *(_QWORD *)dnDevInst,
                       *(_QWORD *)&dnDevInst[2],
                       v18,
                       *((_QWORD *)&v18 + 1)) )
  {
    v9 = 0;
    while ( !IsDeviceOnWatchlist )
    {
      v14 = 0;
      LODWORD(v14) = 32;
      v15 = 0;
      if ( !(unsigned int)DevObjEnumDeviceInterfaces(v5, 0, &GUID_DEVINTERFACE_VOLUME, v9, &v14) )
      {
        if ( GetLastError() != 259 )
        {
          v6 = "Failed to devices supporting volume interface [%d]";
          v7 = 430;
          goto LABEL_8;
        }
        v7 = 432;
        v6 = "Enumerated through all devices without finding drive %S";
        v8 = 3;
        goto LABEL_29;
      }
      v24 = 8;
      v16 = 0;
      *(_OWORD *)dnDevInst = 0;
      LODWORD(v16) = 48;
      v18 = 0;
      if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(v5, &v14, &v24, 528, (char *)&pdnDevInst + 4, &v16) )
      {
        GetLastError();
        v6 = "Failed to devices interface details [%d]";
        v7 = 455;
        goto LABEL_8;
      }
      if ( StringCchPrintfW(&szVolumeMountPoint, 0x104u, L"%s\\", v25) < 0 )
      {
        v6 = "Failed to format device path with stringcchprintf [%d]";
        v7 = 469;
        goto LABEL_8;
      }
      if ( !GetVolumeNameForVolumeMountPointW(&szVolumeMountPoint, String1, 0x32u) )
      {
        GetLastError();
        v6 = "Failed to get volume name [%d]";
        v7 = 475;
        goto LABEL_8;
      }
      if ( !_wcsicmp(String1, szVolumeName) )
      {
        v10 = dnDevInst[1];
        v11 = 0;
        LODWORD(pdnDevInst) = dnDevInst[1];
        while ( !CM_Get_Device_IDW(v10, Buffer, 0x200u, 0) )
        {
          _wcslwr(Buffer);
          IsDeviceOnWatchlist = MobileBroadbandp_IsDeviceOnWatchlist(Buffer);
          if ( IsDeviceOnWatchlist == 1 )
            break;
          if ( CM_Get_Parent((PDEVINST)&pdnDevInst, pdnDevInst, 0) )
            break;
          if ( ++v11 >= 3 )
            break;
          v10 = pdnDevInst;
        }
      }
      ++v9;
    }
  }
  else
  {
    GetLastError();
    v6 = "Failed to get devices supporting volume interface [%d]";
    v7 = 410;
LABEL_8:
    v8 = 1;
LABEL_29:
    AslLogCallPrintf(v8, (unsigned int)"MobileBroadbandp_MapDriveToVID", v7, (_DWORD)v6);
  }
  DevObjDestroyDeviceInfoList(v5);
  return IsDeviceOnWatchlist;
}

```

## disassembly

```asm
0x1800af828  push    rbp
0x1800af82a  push    rsi
0x1800af82b  push    rdi
0x1800af82c  push    r14
0x1800af82e  push    r15
0x1800af830  lea     rbp, [rsp-8A0h]
0x1800af838  sub     rsp, 9A0h
0x1800af83f  mov     rax, cs:__security_cookie
0x1800af846  xor     rax, rsp
0x1800af849  mov     [rbp+8C0h+var_30], rax
0x1800af850  xorps   xmm1, xmm1
0x1800af853  mov     [rbp+8C0h+szVolumeMountPoint], cx
0x1800af857  xor     eax, eax
0x1800af859  mov     [rsp+9C0h+pdnDevInst], 0
0x1800af861  xorps   xmm0, xmm0
0x1800af864  mov     [rbp+8C0h+var_84E], 5C003Ah
0x1800af86b  xor     edx, edx; Val
0x1800af86d  mov     [rbp+8C0h+var_84A], ax
0x1800af871  lea     rcx, [rbp+8C0h+szVolumeName]; void *
0x1800af875  lea     r8d, [rax+64h]; Size
0x1800af879  movups  [rsp+9C0h+var_988], xmm0
0x1800af87e  movups  [rsp+9C0h+var_978], xmm0
0x1800af883  movups  [rsp+9C0h+var_968], xmm1
0x1800af888  movups  xmmword ptr [rsp+9C0h+dnDevInst], xmm1
0x1800af88d  movups  [rsp+9C0h+var_948], xmm1
0x1800af892  call    memset_0
0x1800af897  xor     edx, edx; Val
0x1800af899  lea     rcx, [rbp+8C0h+String1]; void *
0x1800af89d  lea     r8d, [rdx+64h]; Size
0x1800af8a1  call    memset_0
0x1800af8a6  xor     edx, edx; Val
0x1800af8a8  mov     [rsp+9C0h+var_98C], 210h
0x1800af8b0  mov     r8d, 210h; Size
0x1800af8b6  lea     rcx, [rbp+8C0h+var_640]; void *
0x1800af8bd  call    memset_0
0x1800af8c2  xor     r15d, r15d
0x1800af8c5  lea     rdx, [rbp+8C0h+szVolumeName]; lpszVolumeName
0x1800af8c9  lea     rcx, [rbp+8C0h+szVolumeMountPoint]; lpszVolumeMountPoint
0x1800af8cd  lea     r8d, [r15+32h]; cchBufferLength
0x1800af8d1  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800af8d7  test    eax, eax
0x1800af8d9  jnz     short loc_1800AF908
0x1800af8db  call    cs:__imp_GetLastError
0x1800af8e1  lea     r9, aFailedToGetVol_0; "Failed to get volume name [%d]"
0x1800af8e8  mov     r8d, 188h
0x1800af8ee  lea     rdx, aMobilebroadban_4; "MobileBroadbandp_MapDriveToVID"
0x1800af8f5  mov     dword ptr [rsp+9C0h+var_9A0], eax
0x1800af8f9  mov     ecx, 1
0x1800af8fe  call    AslLogCallPrintf
0x1800af903  jmp     loc_1800AFB84
0x1800af908  xor     r9d, r9d
0x1800af90b  mov     [rsp+9C0h+var_9A0], r15
0x1800af910  xor     r8d, r8d
0x1800af913  lea     rcx, GUID_DEVCLASS_CDROM
0x1800af91a  xor     edx, edx
0x1800af91c  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800af922  mov     rdi, rax
0x1800af925  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800af929  jnz     short loc_1800AF940
0x1800af92b  call    cs:__imp_GetLastError
0x1800af931  lea     r9, aFailedToCreate_35; "Failed to create a device list [%d]"
0x1800af938  mov     r8d, 18Fh
0x1800af93e  jmp     short loc_1800AF8EE
0x1800af940  mov     [rsp+9C0h+var_998], r15
0x1800af945  lea     rdx, GUID_DEVINTERFACE_VOLUME
0x1800af94c  mov     r9d, 12h
0x1800af952  mov     [rsp+9C0h+var_9A0], r15
0x1800af957  xor     r8d, r8d
0x1800af95a  mov     rcx, rdi
0x1800af95d  call    cs:__imp_DevObjGetClassDevs
0x1800af963  test    eax, eax
0x1800af965  jnz     short loc_1800AF988
0x1800af967  call    cs:__imp_GetLastError
0x1800af96d  lea     r9, aFailedToGetDev; "Failed to get devices supporting volume"...
0x1800af974  mov     r8d, 19Ah
0x1800af97a  mov     dword ptr [rsp+9C0h+var_9A0], eax
0x1800af97e  mov     ecx, 1
0x1800af983  jmp     loc_1800AFB6F
0x1800af988  xor     r14d, r14d
0x1800af98b  test    r15d, r15d
0x1800af98e  jnz     loc_1800AFB7B
0x1800af994  xorps   xmm0, xmm0
0x1800af997  lea     rax, [rsp+9C0h+var_988]
0x1800af99c  movups  [rsp+9C0h+var_988], xmm0
0x1800af9a1  mov     r9d, r14d
0x1800af9a4  mov     dword ptr [rsp+9C0h+var_988], 20h ; ' '
0x1800af9ac  lea     r8, GUID_DEVINTERFACE_VOLUME
0x1800af9b3  mov     [rsp+9C0h+var_9A0], rax
0x1800af9b8  xor     edx, edx
0x1800af9ba  mov     rcx, rdi
0x1800af9bd  movups  [rsp+9C0h+var_978], xmm0
0x1800af9c2  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1800af9c8  test    eax, eax
0x1800af9ca  jz      loc_1800AFB35
0x1800af9d0  xorps   xmm0, xmm0
0x1800af9d3  mov     [rbp+8C0h+var_640], 8
0x1800af9dd  lea     rax, [rsp+9C0h+var_968]
0x1800af9e2  mov     r9d, 210h
0x1800af9e8  mov     [rsp+9C0h+var_998], rax
0x1800af9ed  lea     r8, [rbp+8C0h+var_640]
0x1800af9f4  lea     rax, [rsp+9C0h+var_98C]
0x1800af9f9  mov     rcx, rdi
0x1800af9fc  movups  [rsp+9C0h+var_968], xmm0
0x1800afa01  lea     rdx, [rsp+9C0h+var_988]
0x1800afa06  mov     [rsp+9C0h+var_9A0], rax
0x1800afa0b  movups  xmmword ptr [rsp+9C0h+dnDevInst], xmm0
0x1800afa10  mov     dword ptr [rsp+9C0h+var_968], 30h ; '0'
0x1800afa18  movups  [rsp+9C0h+var_948], xmm0
0x1800afa1d  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1800afa23  test    eax, eax
0x1800afa25  jz      loc_1800AFB1D
0x1800afa2b  lea     r9, [rbp+8C0h+var_63C]
0x1800afa32  mov     edx, 104h; unsigned __int64
0x1800afa37  lea     r8, aS_0; "%s\\"
0x1800afa3e  lea     rcx, [rbp+8C0h+szVolumeMountPoint]; unsigned __int16 *
0x1800afa42  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800afa47  test    eax, eax
0x1800afa49  js      loc_1800AFB03
0x1800afa4f  lea     r8d, [r15+32h]; cchBufferLength
0x1800afa53  lea     rdx, [rbp+8C0h+String1]; lpszVolumeName
0x1800afa57  lea     rcx, [rbp+8C0h+szVolumeMountPoint]; lpszVolumeMountPoint
0x1800afa5b  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800afa61  test    eax, eax
0x1800afa63  jz      loc_1800AFAEB
0x1800afa69  lea     rdx, [rbp+8C0h+szVolumeName]; String2
0x1800afa6d  lea     rcx, [rbp+8C0h+String1]; String1
0x1800afa71  call    cs:__imp__wcsicmp
0x1800afa77  test    eax, eax
0x1800afa79  jnz     short loc_1800AFAE3
0x1800afa7b  mov     ecx, [rsp+9C0h+dnDevInst+4]; dnDevInst
0x1800afa7f  xor     esi, esi
0x1800afa81  mov     [rsp+9C0h+pdnDevInst], ecx
0x1800afa85  xor     r9d, r9d; ulFlags
0x1800afa88  lea     rdx, [rbp+8C0h+Buffer]; Buffer
0x1800afa8f  mov     r8d, 200h; BufferLen
0x1800afa95  call    cs:__imp_CM_Get_Device_IDW
0x1800afa9b  test    eax, eax
0x1800afa9d  jnz     short loc_1800AFAE3
0x1800afa9f  lea     rcx, [rbp+8C0h+Buffer]; String
0x1800afaa6  call    cs:__imp__wcslwr
0x1800afaac  lea     rcx, [rbp+8C0h+Buffer]; Str
0x1800afab3  call    ?MobileBroadbandp_IsDeviceOnWatchlist@@YAHPEAG@Z; MobileBroadbandp_IsDeviceOnWatchlist(ushort *)
0x1800afab8  mov     r15d, eax
0x1800afabb  cmp     eax, 1
0x1800afabe  jz      short loc_1800AFAE3
0x1800afac0  mov     edx, [rsp+9C0h+pdnDevInst]; dnDevInst
0x1800afac4  lea     rcx, [rsp+9C0h+pdnDevInst]; pdnDevInst
0x1800afac9  xor     r8d, r8d; ulFlags
0x1800afacc  call    cs:__imp_CM_Get_Parent
0x1800afad2  test    eax, eax
0x1800afad4  jnz     short loc_1800AFAE3
0x1800afad6  inc     esi
0x1800afad8  cmp     esi, 3
0x1800afadb  jge     short loc_1800AFAE3
0x1800afadd  mov     ecx, [rsp+9C0h+pdnDevInst]
0x1800afae1  jmp     short loc_1800AFA85
0x1800afae3  inc     r14d
0x1800afae6  jmp     loc_1800AF98B
0x1800afaeb  call    cs:__imp_GetLastError
0x1800afaf1  lea     r9, aFailedToGetVol_0; "Failed to get volume name [%d]"
0x1800afaf8  mov     r8d, 1DBh
0x1800afafe  jmp     loc_1800AF97A
0x1800afb03  mov     dword ptr [rsp+9C0h+var_9A0], 8
0x1800afb0b  lea     r9, aFailedToFormat_2; "Failed to format device path with strin"...
0x1800afb12  mov     r8d, 1D5h
0x1800afb18  jmp     loc_1800AF97E
0x1800afb1d  call    cs:__imp_GetLastError
0x1800afb23  lea     r9, aFailedToDevice_0; "Failed to devices interface details [%d"...
0x1800afb2a  mov     r8d, 1C7h
0x1800afb30  jmp     loc_1800AF97A
0x1800afb35  call    cs:__imp_GetLastError
0x1800afb3b  cmp     eax, 103h
0x1800afb40  jz      short loc_1800AFB54
0x1800afb42  lea     r9, aFailedToDevice; "Failed to devices supporting volume int"...
0x1800afb49  mov     r8d, 1AEh
0x1800afb4f  jmp     loc_1800AF97A
0x1800afb54  lea     rax, [rbp+8C0h+szVolumeMountPoint]
0x1800afb58  mov     r8d, 1B0h
0x1800afb5e  mov     [rsp+9C0h+var_9A0], rax
0x1800afb63  lea     r9, aEnumeratedThro; "Enumerated through all devices without "...
0x1800afb6a  mov     ecx, 3
0x1800afb6f  lea     rdx, aMobilebroadban_4; "MobileBroadbandp_MapDriveToVID"
0x1800afb76  call    AslLogCallPrintf
0x1800afb7b  mov     rcx, rdi
0x1800afb7e  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1800afb84  mov     eax, r15d
0x1800afb87  mov     rcx, [rbp+8C0h+var_30]
0x1800afb8e  xor     rcx, rsp; StackCookie
0x1800afb91  call    __security_check_cookie
0x1800afb96  add     rsp, 9A0h
0x1800afb9d  pop     r15
0x1800afb9f  pop     r14
0x1800afba1  pop     rdi
0x1800afba2  pop     rsi
0x1800afba3  pop     rbp
0x1800afba4  retn
```
