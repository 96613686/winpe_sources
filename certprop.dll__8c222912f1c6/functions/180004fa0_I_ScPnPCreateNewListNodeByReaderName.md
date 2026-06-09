# I_ScPnPCreateNewListNodeByReaderName

- ea: `0x180004fa0`
- end: `0x180005826`
- name: `I_ScPnPCreateNewListNodeByReaderName`
- size: `2182`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x180006a40`

## callees

- `0x180004600`
- `0x180004fa0`
- `0x180016090`
- `0x180016a66`
- `0x180018b58`
- `0x180018bb4`
- `0x180018d78`
- `0x1800197a4`
- `0x18001add8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005226`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005300`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005226`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005300`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180005312`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180005312`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800053be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005479`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005496`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005517`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800056d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800053be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005479`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005496`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005517`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800056d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000511b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000535a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000511b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000535a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005682`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000549f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000578c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000549f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000578c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180005350`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180005350`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800052b0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800052b0`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x1800051be`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x1800051be`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x1800051e9`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x180005277`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x1800051e9`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x180005277`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800056be`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180005775`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800056be`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180005775`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x18000510c`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x18000510c`

## string_xrefs

- `0x1800050d4`: `NULL != pwszReaderName`

## pseudocode

```c
__int64 __fastcall I_ScPnPCreateNewListNodeByReaderName(__int64 a1, _QWORD *a2)
{
  STRSAFE_LPSTR v4; // rcx
  int v5; // r8d
  int v6; // r9d
  DWORD LastError; // ebx
  STRSAFE_LPSTR v8; // rcx
  int v9; // r8d
  int v10; // r9d
  HDEVINFO ClassDevsW; // rsi
  __int64 v12; // rcx
  DWORD v13; // ebp
  __int64 FileW; // r12
  __int64 v15; // rcx
  DWORD v16; // eax
  DWORD v17; // ebx
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v18; // rax
  __int64 v19; // rcx
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v20; // r13
  __int64 v21; // rcx
  unsigned int v22; // r14d
  DWORD v23; // ebp
  void *v24; // rcx
  void *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rcx
  void *v28; // r8
  unsigned __int16 *i; // r10
  unsigned __int16 *v30; // rax
  int v31; // ecx
  int v32; // edx
  __int64 v33; // rax
  __int64 v35; // rcx
  char v36; // bl
  __int64 v37; // rcx
  DWORD v38; // eax
  int v39; // r9d
  int v40; // r9d
  void *lpMem; // [rsp+40h] [rbp-88h]
  DWORD RequiredSize; // [rsp+48h] [rbp-80h] BYREF
  int v44; // [rsp+4Ch] [rbp-7Ch]
  int v45; // [rsp+50h] [rbp-78h]
  DWORD BytesReturned; // [rsp+54h] [rbp-74h] BYREF
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+58h] [rbp-70h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+78h] [rbp-50h] BYREF

  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  BytesReturned = 0;
  RequiredSize = 0;
  memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
  WppTraceIndent(a1, 0);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids, WPP_pszIndent);
  }
  if ( !a2 )
  {
    WppTraceIndent(v4, 2);
    LastError = -2146435068;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_ss(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, v5, v6, (__int64)"NULL != ppScPnPDeviceListNode");
    }
    goto LABEL_102;
  }
  if ( !a1 )
  {
    WppTraceIndent(v4, 2);
    LastError = -2146435068;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_ss(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, v9, v10, (__int64)"NULL != pwszReaderName");
    }
    goto LABEL_102;
  }
  *a2 = 0;
  ClassDevsW = SetupDiGetClassDevsW(&GUID_DEVINTERFACE_SCFILTER, 0, 0, 0x12u);
  if ( ClassDevsW == (HDEVINFO)-1LL )
  {
    LastError = GetLastError();
    WppTraceIndent(v12, 2);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
        WPP_pszIndent,
        LastError);
    }
    goto LABEL_102;
  }
  LastError = 0;
  v13 = 0;
  FileW = -1;
  v44 = 0;
  v45 = 0;
  DeviceInterfaceData.cbSize = 32;
  while ( 1 )
  {
    if ( !SetupDiEnumDeviceInterfaces(ClassDevsW, 0, &GUID_DEVINTERFACE_SCFILTER, v13, &DeviceInterfaceData) )
    {
      if ( !v45 )
        LastError = 1168;
      goto LABEL_99;
    }
    if ( !SetupDiGetDeviceInterfaceDetailW(ClassDevsW, &DeviceInterfaceData, 0, 0, &RequiredSize, 0) )
    {
      v16 = GetLastError();
      LastError = 0;
      if ( v16 != 122 )
        LastError = v16;
      if ( LastError )
      {
        WppTraceIndent(v15, 2);
        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0
          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
        {
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            40,
            (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
            WPP_pszIndent,
            LastError);
        }
        goto LABEL_99;
      }
    }
    v17 = RequiredSize;
    if ( RequiredSize < 8 )
    {
      LastError = 24;
      WppTraceIndent(v15, 2);
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          41,
          (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
          v40,
          RequiredSize);
      }
      goto LABEL_99;
    }
    v18 = (struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *)HeapAlloc(g_hHeap, 8u, RequiredSize);
    v20 = v18;
    if ( !v18 )
    {
      WppTraceIndent(v19, 2);
      LastError = 8;
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          42,
          &WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
          WPP_pszIndent);
      }
LABEL_99:
      SetupDiDestroyDeviceInfoList(ClassDevsW);
      goto LABEL_100;
    }
    memset_0(v18, 0, v17);
    v20->cbSize = 8;
    DeviceInfoData.cbSize = 32;
    if ( !SetupDiGetDeviceInterfaceDetailW(ClassDevsW, &DeviceInterfaceData, v20, v17, &RequiredSize, &DeviceInfoData) )
      break;
    FileW = (__int64)CreateFileW(v20->DevicePath, 0xC0000000, 3u, 0, 3u, 0, 0);
    if ( FileW != -1 )
    {
      v22 = 0;
      v23 = 194;
      v24 = 0;
      LastError = 122;
      lpMem = 0;
      while ( LastError )
      {
        if ( v22 >= 0xA )
        {
          WppTraceIndent(v24, 2);
          if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[28] & 1) != 0
            && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              46,
              &WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
              WPP_pszIndent);
          }
          LastError = 322;
          goto LABEL_82;
        }
        if ( v24 )
          v25 = HeapReAlloc(g_hHeap, 8u, v24, v23);
        else
          v25 = HeapAlloc(g_hHeap, 8u, v23);
        lpMem = v25;
        if ( !v25 )
        {
          WppTraceIndent(v26, 2);
          LastError = 8;
          if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[28] & 1) != 0
            && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              44,
              &WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
              WPP_pszIndent);
          }
          goto LABEL_88;
        }
        if ( DeviceIoControl((HANDLE)FileW, 0x310FACu, 0, 0, v25, v23, &BytesReturned, 0) )
        {
          LastError = 0;
        }
        else
        {
          LastError = GetLastError();
          if ( LastError != 122 )
          {
            WppTraceIndent(v27, 2);
            if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control[28] & 1) != 0
              && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
            {
              WPP_SF_sD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                45,
                (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
                WPP_pszIndent,
                LastError);
            }
            v28 = lpMem;
            goto LABEL_44;
          }
        }
        v24 = lpMem;
        v23 += 192;
        ++v22;
      }
      for ( i = (unsigned __int16 *)v24; ; i += v33 + 1 )
      {
        if ( !*i )
        {
          HeapFree(g_hHeap, 0, lpMem);
          CloseHandle((HANDLE)FileW);
          FileW = -1;
          goto LABEL_64;
        }
        v30 = i;
        do
        {
          v31 = *(unsigned __int16 *)((char *)v30 + a1 - (_QWORD)i);
          v32 = *v30 - v31;
          if ( v32 )
            break;
          ++v30;
        }
        while ( v31 );
        if ( !v32 )
          break;
        v33 = -1;
        while ( i[++v33] != 0 )
          ;
      }
      LastError = I_ScPnPCreateNewListNode(FileW, DeviceInfoData.DevInst, i, v20->DevicePath, a2);
      if ( !LastError )
      {
        FileW = -1;
        v45 = 1;
        HeapFree(g_hHeap, 0, lpMem);
        goto LABEL_64;
      }
      WppTraceIndent(v35, 2);
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          47,
          (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
          WPP_pszIndent,
          LastError);
      }
LABEL_82:
      v28 = lpMem;
      if ( !lpMem )
        goto LABEL_88;
LABEL_44:
      HeapFree(g_hHeap, 0, v28);
      goto LABEL_88;
    }
    v36 = GetLastError();
    WppTraceIndent(v37, 2);
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
        WPP_pszIndent,
        v36);
    }
    LastError = 0;
LABEL_64:
    v13 = ++v44;
    HeapFree(g_hHeap, 0, v20);
  }
  WppTraceIndent(v21, 2);
  v38 = GetLastError();
  LastError = v38;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      43,
      (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
      v39,
      v38);
  }
LABEL_88:
  SetupDiDestroyDeviceInfoList(ClassDevsW);
  HeapFree(g_hHeap, 0, v20);
LABEL_100:
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
LABEL_102:
  WppTraceIndent(v8, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      49,
      (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180004fa0  mov     r11, rsp
0x180004fa3  sub     rsp, 0C8h
0x180004faa  mov     rax, cs:__security_cookie
0x180004fb1  xor     rax, rsp
0x180004fb4  mov     [rsp+0C8h+var_30], rax
0x180004fbc  mov     [r11-8], rdi
0x180004fc0  xorps   xmm1, xmm1
0x180004fc3  mov     [r11-18h], r13
0x180004fc7  xorps   xmm0, xmm0
0x180004fca  xor     r13d, r13d
0x180004fcd  mov     [r11-20h], r14
0x180004fd1  mov     rdi, rdx
0x180004fd4  mov     [r11-28h], r15
0x180004fd8  movups  xmmword ptr [rsp+0C8h+var_50.cbSize], xmm1
0x180004fdd  xor     edx, edx
0x180004fdf  mov     [r11-74h], r13d
0x180004fe3  mov     r15, rcx
0x180004fe6  mov     [r11-80h], r13d
0x180004fea  movups  xmmword ptr [rsp+0C8h+var_70.cbSize], xmm0
0x180004fef  movups  xmmword ptr [rsp+0C8h+var_70.InterfaceClassGuid.Data4+4], xmm0
0x180004ff4  movups  xmmword ptr [r11-40h], xmm1
0x180004ff9  call    WppTraceIndent
0x180004ffe  mov     rcx, cs:WPP_GLOBAL_Control
0x180005005  lea     r14, WPP_GLOBAL_Control
0x18000500c  cmp     rcx, r14
0x18000500f  jz      short loc_180005039
0x180005011  test    byte ptr [rcx+1Ch], 2
0x180005015  jz      short loc_180005039
0x180005017  cmp     byte ptr [rcx+19h], 5
0x18000501b  jb      short loc_180005039
0x18000501d  mov     r9, cs:WPP_pszIndent
0x180005024  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18000502b  mov     rcx, [rcx+10h]
0x18000502f  mov     edx, 24h ; '$'
0x180005034  call    WPP_SF_s
0x180005039  mov     [rsp+0C8h+arg_0], rbx
0x180005041  test    rdi, rdi
0x180005044  jnz     short loc_180005098
0x180005046  mov     edx, 2
0x18000504b  call    WppTraceIndent
0x180005050  mov     ebx, 80100004h
0x180005055  mov     rcx, cs:WPP_GLOBAL_Control
0x18000505c  cmp     rcx, r14
0x18000505f  jz      loc_1800057A2
0x180005065  test    byte ptr [rcx+1Ch], 1
0x180005069  jz      loc_1800057A2
0x18000506f  cmp     byte ptr [rcx+19h], 2
0x180005073  jb      loc_1800057A2
0x180005079  mov     rcx, [rcx+10h]
0x18000507d  lea     rax, aNullPpscpnpdev; "NULL != ppScPnPDeviceListNode"
0x180005084  mov     edx, 25h ; '%'
0x180005089  mov     [rsp+0C8h+DeviceInterfaceData], rax
0x18000508e  call    WPP_SF_ss
0x180005093  jmp     loc_1800057A2
0x180005098  test    r15, r15
0x18000509b  jnz     short loc_1800050EF
0x18000509d  mov     edx, 2
0x1800050a2  call    WppTraceIndent
0x1800050a7  mov     ebx, 80100004h
0x1800050ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800050b3  cmp     rcx, r14
0x1800050b6  jz      loc_1800057A2
0x1800050bc  test    byte ptr [rcx+1Ch], 1
0x1800050c0  jz      loc_1800057A2
0x1800050c6  cmp     byte ptr [rcx+19h], 2
0x1800050ca  jb      loc_1800057A2
0x1800050d0  mov     rcx, [rcx+10h]
0x1800050d4  lea     rax, aNullPwszreader; "NULL != pwszReaderName"
0x1800050db  mov     edx, 26h ; '&'
0x1800050e0  mov     [rsp+0C8h+DeviceInterfaceData], rax
0x1800050e5  call    WPP_SF_ss
0x1800050ea  jmp     loc_1800057A2
0x1800050ef  mov     r9d, 12h; Flags
0x1800050f5  mov     [rsp+0C8h+arg_18], rsi
0x1800050fd  xor     r8d, r8d; hwndParent
0x180005100  mov     [rdi], r13
0x180005103  xor     edx, edx; Enumerator
0x180005105  lea     rcx, GUID_DEVINTERFACE_SCFILTER; ClassGuid
0x18000510c  call    cs:__imp_SetupDiGetClassDevsW
0x180005112  mov     rsi, rax
0x180005115  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005119  jnz     short loc_180005176
0x18000511b  call    cs:__imp_GetLastError
0x180005121  mov     edx, 2
0x180005126  mov     ebx, eax
0x180005128  call    WppTraceIndent
0x18000512d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005134  cmp     rcx, r14
0x180005137  jz      loc_18000579A
0x18000513d  test    byte ptr [rcx+1Ch], 1
0x180005141  jz      loc_18000579A
0x180005147  cmp     byte ptr [rcx+19h], 2
0x18000514b  jb      loc_18000579A
0x180005151  mov     r9, cs:WPP_pszIndent
0x180005158  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18000515f  mov     rcx, [rcx+10h]
0x180005163  mov     edx, 27h ; '''
0x180005168  mov     dword ptr [rsp+0C8h+DeviceInterfaceData], ebx
0x18000516c  call    WPP_SF_sD
0x180005171  jmp     loc_18000579A
0x180005176  mov     [rsp+0C8h+arg_10], rbp
0x18000517e  mov     ebx, r13d
0x180005181  mov     [rsp+0C8h+var_10], r12
0x180005189  mov     ebp, r13d
0x18000518c  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180005193  mov     [rsp+0C8h+var_7C], r13d
0x180005198  mov     [rsp+0C8h+var_78], r13d
0x18000519d  mov     [rsp+0C8h+var_70.cbSize], 20h ; ' '
0x1800051a5  lea     rax, [rsp+0C8h+var_70]
0x1800051aa  mov     r9d, ebp; MemberIndex
0x1800051ad  lea     r8, GUID_DEVINTERFACE_SCFILTER; InterfaceClassGuid
0x1800051b4  mov     [rsp+0C8h+DeviceInterfaceData], rax; DeviceInterfaceData
0x1800051b9  xor     edx, edx; DeviceInfoData
0x1800051bb  mov     rcx, rsi; DeviceInfoSet
0x1800051be  call    cs:__imp_SetupDiEnumDeviceInterfaces
0x1800051c4  test    eax, eax
0x1800051c6  jz      loc_180005766
0x1800051cc  lea     rax, [rsp+0C8h+RequiredSize]
0x1800051d1  mov     [rsp+0C8h+DeviceInfoData], r13; DeviceInfoData
0x1800051d6  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x1800051d9  mov     [rsp+0C8h+DeviceInterfaceData], rax; RequiredSize
0x1800051de  xor     r8d, r8d; DeviceInterfaceDetailData
0x1800051e1  lea     rdx, [rsp+0C8h+var_70]; DeviceInterfaceData
0x1800051e6  mov     rcx, rsi; DeviceInfoSet
0x1800051e9  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x1800051ef  test    eax, eax
0x1800051f1  jnz     short loc_18000520A
0x1800051f3  call    cs:__imp_GetLastError
0x1800051f9  cmp     eax, 7Ah ; 'z'
0x1800051fc  mov     ebx, r13d
0x1800051ff  cmovnz  ebx, eax
0x180005202  test    ebx, ebx
0x180005204  jnz     loc_180005525
0x18000520a  mov     ebx, [rsp+0C8h+RequiredSize]
0x18000520e  cmp     ebx, 8
0x180005211  jb      loc_180005720
0x180005217  mov     rcx, cs:g_hHeap; hHeap
0x18000521e  mov     r8d, ebx; dwBytes
0x180005221  mov     edx, 8; dwFlags
0x180005226  call    cs:__imp_HeapAlloc
0x18000522c  mov     r13, rax
0x18000522f  test    rax, rax
0x180005232  jz      loc_1800056DB
0x180005238  mov     r8d, ebx; Size
0x18000523b  xor     edx, edx; Val
0x18000523d  mov     rcx, rax; void *
0x180005240  call    memset_0
0x180005245  lea     rax, [rsp+0C8h+var_50]
0x18000524a  mov     dword ptr [r13+0], 8
0x180005252  mov     [rsp+0C8h+DeviceInfoData], rax; DeviceInfoData
0x180005257  lea     rdx, [rsp+0C8h+var_70]; DeviceInterfaceData
0x18000525c  lea     rax, [rsp+0C8h+RequiredSize]
0x180005261  mov     [rsp+0C8h+var_50.cbSize], 20h ; ' '
0x180005269  mov     r9d, ebx; DeviceInterfaceDetailDataSize
0x18000526c  mov     [rsp+0C8h+DeviceInterfaceData], rax; RequiredSize
0x180005271  mov     r8, r13; DeviceInterfaceDetailData
0x180005274  mov     rcx, rsi; DeviceInfoSet
0x180005277  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x18000527d  test    eax, eax
0x18000527f  jz      loc_180005678
0x180005285  mov     [rsp+0C8h+hTemplateFile], 0; hTemplateFile
0x18000528e  lea     rcx, [r13+4]; lpFileName
0x180005292  mov     dword ptr [rsp+0C8h+DeviceInfoData], 0; dwFlagsAndAttributes
0x18000529a  xor     r9d, r9d; lpSecurityAttributes
0x18000529d  mov     edx, 0C0000000h; dwDesiredAccess
0x1800052a2  mov     dword ptr [rsp+0C8h+DeviceInterfaceData], 3; dwCreationDisposition
0x1800052aa  mov     r8d, 3; dwShareMode
0x1800052b0  call    cs:__imp_CreateFileW
0x1800052b6  mov     r12, rax
0x1800052b9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800052bd  jz      loc_1800054B5
0x1800052c3  xor     r14d, r14d
0x1800052c6  mov     ebp, 0C2h
0x1800052cb  xor     ecx, ecx
0x1800052cd  mov     ebx, 7Ah ; 'z'
0x1800052d2  mov     [rsp+0C8h+lpMem], rcx
0x1800052d7  test    ebx, ebx
0x1800052d9  jz      loc_1800053DE
0x1800052df  cmp     r14d, 0Ah
0x1800052e3  jnb     loc_1800055D3
0x1800052e9  mov     r9d, ebp; dwBytes
0x1800052ec  mov     edx, 8; dwFlags
0x1800052f1  test    rcx, rcx
0x1800052f4  jnz     short loc_180005308
0x1800052f6  mov     rcx, cs:g_hHeap; hHeap
0x1800052fd  mov     r8d, r9d; dwBytes
0x180005300  call    cs:__imp_HeapAlloc
0x180005306  jmp     short loc_180005318
0x180005308  mov     r8, rcx; lpMem
0x18000530b  mov     rcx, cs:g_hHeap; hHeap
0x180005312  call    cs:__imp_HeapReAlloc
0x180005318  mov     [rsp+0C8h+lpMem], rax
0x18000531d  test    rax, rax
0x180005320  jz      loc_180005578
0x180005326  mov     [rsp+0C8h+lpOverlapped], 0; lpOverlapped
0x18000532f  lea     rcx, [rsp+0C8h+BytesReturned]
0x180005334  mov     [rsp+0C8h+hTemplateFile], rcx; lpBytesReturned
0x180005339  xor     r9d, r9d; nInBufferSize
0x18000533c  mov     dword ptr [rsp+0C8h+DeviceInfoData], ebp; nOutBufferSize
0x180005340  mov     rcx, r12; hDevice
0x180005343  xor     r8d, r8d; lpInBuffer
0x180005346  mov     [rsp+0C8h+DeviceInterfaceData], rax; lpOutBuffer
0x18000534b  mov     edx, 310FACh; dwIoControlCode
0x180005350  call    cs:__imp_DeviceIoControl
0x180005356  test    eax, eax
0x180005358  jnz     short loc_1800053C9
0x18000535a  call    cs:__imp_GetLastError
0x180005360  mov     ebx, eax
0x180005362  cmp     eax, 7Ah ; 'z'
0x180005365  jz      short loc_1800053CB
0x180005367  mov     edx, 2
0x18000536c  call    WppTraceIndent
0x180005371  mov     rcx, cs:WPP_GLOBAL_Control
0x180005378  lea     r14, WPP_GLOBAL_Control
0x18000537f  cmp     rcx, r14
0x180005382  jz      short loc_1800053B0
0x180005384  test    byte ptr [rcx+1Ch], 1
0x180005388  jz      short loc_1800053B0
0x18000538a  cmp     byte ptr [rcx+19h], 2
0x18000538e  jb      short loc_1800053B0
0x180005390  mov     r9, cs:WPP_pszIndent
0x180005397  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18000539e  mov     rcx, [rcx+10h]
0x1800053a2  mov     edx, 2Dh ; '-'
0x1800053a7  mov     dword ptr [rsp+0C8h+DeviceInterfaceData], ebx
0x1800053ab  call    WPP_SF_sD
0x1800053b0  mov     r8, [rsp+0C8h+lpMem]; lpMem
0x1800053b5  mov     rcx, cs:g_hHeap; hHeap
0x1800053bc  xor     edx, edx; dwFlags
0x1800053be  call    cs:__imp_HeapFree
0x1800053c4  jmp     loc_1800056BB
0x1800053c9  xor     ebx, ebx
0x1800053cb  mov     rcx, [rsp+0C8h+lpMem]
0x1800053d0  add     ebp, 0C0h
0x1800053d6  inc     r14d
0x1800053d9  jmp     loc_1800052D7
0x1800053de  mov     r10, rcx
0x1800053e1  xor     eax, eax
0x1800053e3  cmp     ax, [r10]
0x1800053e7  jz      loc_180005488
0x1800053ed  mov     r8, r15
0x1800053f0  mov     rax, r10
0x1800053f3  sub     r8, r10
0x1800053f6  nop     word ptr [rax+rax+00000000h]
0x180005400  movzx   edx, word ptr [rax]
0x180005403  movzx   ecx, word ptr [rax+r8]
0x180005408  sub     edx, ecx
0x18000540a  jnz     short loc_180005414
0x18000540c  add     rax, 2
0x180005410  test    ecx, ecx
0x180005412  jnz     short loc_180005400
0x180005414  test    edx, edx
0x180005416  jz      short loc_180005437
0x180005418  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000541f  nop
0x180005420  cmp     word ptr [r10+rax*2+2], 0
0x180005427  lea     rax, [rax+1]
0x18000542b  jnz     short loc_180005420
0x18000542d  lea     r10, [r10+rax*2]
0x180005431  add     r10, 2
0x180005435  jmp     short loc_1800053E1
0x180005437  mov     edx, [rsp+0C8h+var_50.DevInst]
0x18000543e  lea     r9, [r13+4]
0x180005442  mov     r8, r10
0x180005445  mov     [rsp+0C8h+DeviceInterfaceData], rdi
0x18000544a  mov     rcx, r12
0x18000544d  call    I_ScPnPCreateNewListNode
0x180005452  mov     ebx, eax
0x180005454  test    eax, eax
0x180005456  jnz     loc_18000561F
0x18000545c  mov     r8, [rsp+0C8h+lpMem]; lpMem
0x180005461  xor     edx, edx; dwFlags
0x180005463  mov     rcx, cs:g_hHeap; hHeap
0x18000546a  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180005471  mov     [rsp+0C8h+var_78], 1
0x180005479  call    cs:__imp_HeapFree
0x18000547f  lea     r14, WPP_GLOBAL_Control
0x180005486  jmp     short loc_180005501
0x180005488  mov     r8, [rsp+0C8h+lpMem]; lpMem
0x18000548d  xor     edx, edx; dwFlags
0x18000548f  mov     rcx, cs:g_hHeap; hHeap
0x180005496  call    cs:__imp_HeapFree
0x18000549c  mov     rcx, r12; hObject
0x18000549f  call    cs:__imp_CloseHandle
0x1800054a5  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800054ac  lea     r14, WPP_GLOBAL_Control
0x1800054b3  jmp     short loc_180005501
0x1800054b5  call    cs:__imp_GetLastError
0x1800054bb  mov     edx, 2
0x1800054c0  mov     ebx, eax
0x1800054c2  call    WppTraceIndent
0x1800054c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800054ce  cmp     rcx, r14
0x1800054d1  jz      short loc_1800054FF
0x1800054d3  test    byte ptr [rcx+1Ch], 1
0x1800054d7  jz      short loc_1800054FF
0x1800054d9  cmp     byte ptr [rcx+19h], 3
0x1800054dd  jb      short loc_1800054FF
0x1800054df  mov     r9, cs:WPP_pszIndent
0x1800054e6  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
  ... truncated ...
```
