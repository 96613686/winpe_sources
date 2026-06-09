# LoadMediaDLLAndGetEntryPoints

- ea: `0x18000a058`
- end: `0x18000a688`
- name: `LoadMediaDLLAndGetEntryPoints`
- size: `1584`
- prototype: `__int64 __fastcall(char *String1)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000944c`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000a058`
- `0x18000c424`

## import_xrefs

- `msvcrt!_stricmp` at `0x18000a32a`
- `msvcrt!_stricmp` at `0x18000a32a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a268`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a268`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5da`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a627`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a627`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000a254`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000a254`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a2f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a348`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a36e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a394`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a3ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a3e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a406`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a42c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a452`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a478`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a49e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a4c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a4ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a510`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a532`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a554`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a576`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a2f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a348`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a36e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a394`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a3ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a3e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a406`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a42c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a452`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a478`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a49e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a4c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a4ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a510`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a532`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a554`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a576`

## string_xrefs

- `0x18000a0d6`: `PortOpen`
- `0x18000a161`: `PortCompressionSetInfo`
- `0x18000a201`: `PortReceiveComplete`
- `0x18000a23d`: `PortSetIoCompletionPort`
- `0x18000a33e`: `PortOpenExternal`
- `0x18000a3b0`: `RemovePort`
- `0x18000a494`: `SetCommSettings`
- `0x18000a46e`: `UnloadRastapiDll`
- `0x18000a4ba`: `DeviceGetDevConfigEx`
- `0x18000a54a`: `UpdateTapiService`

## pseudocode

```c
__int64 __fastcall LoadMediaDLLAndGetEntryPoints(char *String1)
{
  HMODULE Library; // rax
  HMODULE v3; // rdi
  DWORD LastError; // eax
  DWORD v5; // ebx
  struct _LIST_ENTRY *v6; // rcx
  __int64 v7; // rdx
  unsigned __int16 i; // r14
  const CHAR *v9; // r15
  FARPROC ProcAddress; // rax
  DWORD v11; // eax
  DWORD v12; // eax
  LPCSTR lpProcName; // [rsp+30h] [rbp-D0h]
  __int16 v15; // [rsp+38h] [rbp-C8h]
  const char *v16; // [rsp+40h] [rbp-C0h]
  __int16 v17; // [rsp+48h] [rbp-B8h]
  const char *v18; // [rsp+50h] [rbp-B0h]
  __int16 v19; // [rsp+58h] [rbp-A8h]
  const char *v20; // [rsp+60h] [rbp-A0h]
  __int16 v21; // [rsp+68h] [rbp-98h]
  const char *v22; // [rsp+70h] [rbp-90h]
  __int16 v23; // [rsp+78h] [rbp-88h]
  const char *v24; // [rsp+80h] [rbp-80h]
  __int16 v25; // [rsp+88h] [rbp-78h]
  const char *v26; // [rsp+90h] [rbp-70h]
  __int16 v27; // [rsp+98h] [rbp-68h]
  const char *v28; // [rsp+A0h] [rbp-60h]
  __int16 v29; // [rsp+A8h] [rbp-58h]
  const char *v30; // [rsp+B0h] [rbp-50h]
  __int16 v31; // [rsp+B8h] [rbp-48h]
  const char *v32; // [rsp+C0h] [rbp-40h]
  __int16 v33; // [rsp+C8h] [rbp-38h]
  const char *v34; // [rsp+D0h] [rbp-30h]
  __int16 v35; // [rsp+D8h] [rbp-28h]
  const char *v36; // [rsp+E0h] [rbp-20h]
  __int16 v37; // [rsp+E8h] [rbp-18h]
  const char *v38; // [rsp+F0h] [rbp-10h]
  __int16 v39; // [rsp+F8h] [rbp-8h]
  const char *v40; // [rsp+100h] [rbp+0h]
  __int16 v41; // [rsp+108h] [rbp+8h]
  const char *v42; // [rsp+110h] [rbp+10h]
  __int16 v43; // [rsp+118h] [rbp+18h]
  const char *v44; // [rsp+120h] [rbp+20h]
  __int16 v45; // [rsp+128h] [rbp+28h]
  const char *v46; // [rsp+130h] [rbp+30h]
  __int16 v47; // [rsp+138h] [rbp+38h]
  const char *v48; // [rsp+140h] [rbp+40h]
  __int16 v49; // [rsp+148h] [rbp+48h]
  const char *v50; // [rsp+150h] [rbp+50h]
  __int16 v51; // [rsp+158h] [rbp+58h]
  const char *v52; // [rsp+160h] [rbp+60h]
  __int16 v53; // [rsp+168h] [rbp+68h]

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 133, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids);
  }
  v27 = 6;
  lpProcName = "PortEnum";
  v15 = 0;
  v16 = "PortOpen";
  v17 = 1;
  v18 = "PortClose";
  v19 = 2;
  v20 = "PortGetInfo";
  v21 = 3;
  v22 = "PortSetInfo";
  v23 = 4;
  v24 = "PortDisconnect";
  v25 = 5;
  v26 = "PortConnect";
  v28 = "PortGetPortState";
  v29 = 7;
  v30 = "PortCompressionSetInfo";
  v31 = 8;
  v32 = "PortChangeCallback";
  v33 = 9;
  v34 = "PortGetStatistics";
  v35 = 10;
  v36 = "PortClearStatistics";
  v37 = 11;
  v38 = "PortSend";
  v39 = 12;
  v40 = "PortTestSignalState";
  v41 = 13;
  v42 = "PortReceive";
  v43 = 14;
  v44 = "PortInit";
  v45 = 15;
  v46 = "PortReceiveComplete";
  v47 = 16;
  v48 = "PortSetFraming";
  v49 = 17;
  v50 = "PortGetIOHandle";
  v51 = 18;
  v52 = "PortSetIoCompletionPort";
  v53 = 19;
  Library = LoadLibraryExA(String1, 0, 0x1000u);
  v3 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return v5;
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        goto LABEL_12;
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 134, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids, LastError);
    }
    v6 = WPP_GLOBAL_Control;
LABEL_12:
    if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v6[1].Blink) & 0x2000) != 0
      && BYTE1(v6[1].Blink) >= 6u )
    {
      v7 = 135;
LABEL_51:
      WPP_SF_d(v6[1].Flink, v7, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids, v5);
      return v5;
    }
    return v5;
  }
  *((_QWORD *)String1 + 23) = Library;
  for ( i = 0; i < 0x14u; ++i )
  {
    v9 = (&lpProcName)[2 * i];
    ProcAddress = GetProcAddress(v3, v9);
    *(_QWORD *)&String1[8 * i + 16] = ProcAddress;
    if ( !ProcAddress )
    {
      v12 = GetLastError();
      v5 = v12;
      if ( !v12 )
        goto LABEL_47;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control[1].Flink,
          136,
          (unsigned int)WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids,
          (_DWORD)v9,
          v12);
      }
      goto LABEL_46;
    }
  }
  v5 = 0;
  if ( !_stricmp(String1, "rastapi") )
  {
    RastapiPortOpen = (__int64)GetProcAddress(v3, "PortOpenExternal");
    if ( !RastapiPortOpen )
      goto LABEL_36;
    RastapiAddPorts = (__int64)GetProcAddress(v3, "AddPorts");
    if ( !RastapiAddPorts )
      goto LABEL_36;
    RastapiGetConnectInfo = (__int64)GetProcAddress(v3, "GetConnectInfo");
    if ( !RastapiGetConnectInfo )
      goto LABEL_36;
    RastapiRemovePort = (__int64)GetProcAddress(v3, "RemovePort");
    if ( !RastapiRemovePort )
      goto LABEL_36;
    RastapiEnableDeviceForDialIn = (__int64)GetProcAddress(v3, "EnableDeviceForDialIn");
    if ( !RastapiEnableDeviceForDialIn )
      goto LABEL_36;
    RastapiGetCalledIdInfo = (__int64)GetProcAddress(v3, "RastapiGetCalledID");
    if ( !RastapiGetCalledIdInfo )
      goto LABEL_36;
    RastapiSetCalledIdInfo = (__int64)GetProcAddress(v3, "RastapiSetCalledID");
    if ( !RastapiSetCalledIdInfo )
      goto LABEL_36;
    RastapiGetZeroDeviceInfo = (__int64)GetProcAddress(v3, "GetZeroDeviceInfo");
    if ( !RastapiGetZeroDeviceInfo )
      goto LABEL_36;
    RastapiUnload = (__int64)GetProcAddress(v3, "UnloadRastapiDll");
    if ( !RastapiUnload
      || (RastapiSetCommSettings = (__int64)GetProcAddress(v3, "SetCommSettings")) == 0
      || (RastapiGetDevConfigEx = (__int64)GetProcAddress(v3, "DeviceGetDevConfigEx")) == 0
      || (RastapiIsPulseDial = (__int64)GetProcAddress(v3, "RasTapiIsPulseDial")) == 0
      || (RastapiRefreshDevices = (__int64)GetProcAddress(v3, "RefreshDevices")) == 0
      || (RastapiInitializeDriverIoctl = (__int64)GetProcAddress(v3, "InitializeDriverIoControl")) == 0
      || (RastapiUpdateTapiService = (__int64)GetProcAddress(v3, "UpdateTapiService")) == 0
      || (RastapiCheckRasmanDependency = GetProcAddress(v3, "CheckRasmanDependency")) == 0 )
    {
LABEL_36:
      v11 = GetLastError();
      v5 = v11;
      if ( v11 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 137, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids, v11);
        }
LABEL_46:
        FreeLibrary(*((HMODULE *)String1 + 23));
        *((_QWORD *)String1 + 23) = 0;
        *String1 = 0;
      }
    }
  }
LABEL_47:
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    v7 = 138;
    goto LABEL_51;
  }
  return v5;
}

```

## disassembly

```asm
0x18000a058  push    rbp
0x18000a05a  push    rbx
0x18000a05b  push    rsi
0x18000a05c  push    rdi
0x18000a05d  push    r12
0x18000a05f  push    r13
0x18000a061  push    r14
0x18000a063  push    r15
0x18000a065  lea     rbp, [rsp-78h]
0x18000a06a  sub     rsp, 178h
0x18000a071  mov     rsi, rcx
0x18000a074  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a07b  lea     r13, WPP_GLOBAL_Control
0x18000a082  lea     r14, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids
0x18000a089  mov     r15d, 6
0x18000a08f  mov     r12d, 2000h
0x18000a095  cmp     rcx, r13
0x18000a098  jz      short loc_18000A0B6
0x18000a09a  test    [rcx+1Ch], r12d
0x18000a09e  jz      short loc_18000A0B6
0x18000a0a0  cmp     [rcx+19h], r15b
0x18000a0a4  jb      short loc_18000A0B6
0x18000a0a6  mov     rcx, [rcx+10h]
0x18000a0aa  lea     edx, [r15+7Fh]
0x18000a0ae  mov     r8, r14
0x18000a0b1  call    WPP_SF_
0x18000a0b6  lea     rax, aPortenum; "PortEnum"
0x18000a0bd  mov     [rbp+0B0h+var_118], r15w
0x18000a0c2  mov     [rsp+1B0h+lpProcName], rax
0x18000a0c7  mov     r8d, 1000h; dwFlags
0x18000a0cd  xor     eax, eax
0x18000a0cf  mov     [rsp+1B0h+var_178], ax
0x18000a0d4  xor     edx, edx; hFile
0x18000a0d6  lea     rax, aPortopen; "PortOpen"
0x18000a0dd  mov     [rsp+1B0h+var_170], rax
0x18000a0e2  mov     eax, 1
0x18000a0e7  mov     [rsp+1B0h+var_168], ax
0x18000a0ec  lea     rax, aPortclose; "PortClose"
0x18000a0f3  mov     [rsp+1B0h+var_160], rax
0x18000a0f8  mov     eax, 2
0x18000a0fd  mov     [rsp+1B0h+var_158], ax
0x18000a102  lea     rax, aPortgetinfo; "PortGetInfo"
0x18000a109  mov     [rsp+1B0h+var_150], rax
0x18000a10e  mov     eax, 3
0x18000a113  mov     [rsp+1B0h+var_148], ax
0x18000a118  lea     rax, aPortsetinfo; "PortSetInfo"
0x18000a11f  mov     [rsp+1B0h+var_140], rax
0x18000a124  mov     eax, 4
0x18000a129  mov     [rsp+1B0h+var_138], ax
0x18000a12e  lea     rax, aPortdisconnect_3; "PortDisconnect"
0x18000a135  mov     [rbp+0B0h+var_130], rax
0x18000a139  mov     eax, 5
0x18000a13e  mov     [rbp+0B0h+var_128], ax
0x18000a142  lea     rax, aPortconnect; "PortConnect"
0x18000a149  mov     [rbp+0B0h+var_120], rax
0x18000a14d  lea     rax, aPortgetportsta; "PortGetPortState"
0x18000a154  mov     [rbp+0B0h+var_110], rax
0x18000a158  mov     eax, 7
0x18000a15d  mov     [rbp+0B0h+var_108], ax
0x18000a161  lea     rax, aPortcompressio; "PortCompressionSetInfo"
0x18000a168  mov     [rbp+0B0h+var_100], rax
0x18000a16c  mov     eax, 8
0x18000a171  mov     [rbp+0B0h+var_F8], ax
0x18000a175  lea     rax, aPortchangecall; "PortChangeCallback"
0x18000a17c  mov     [rbp+0B0h+var_F0], rax
0x18000a180  mov     eax, 9
0x18000a185  mov     [rbp+0B0h+var_E8], ax
0x18000a189  lea     rax, aPortgetstatist; "PortGetStatistics"
0x18000a190  mov     [rbp+0B0h+var_E0], rax
0x18000a194  mov     eax, 0Ah
0x18000a199  mov     [rbp+0B0h+var_D8], ax
0x18000a19d  lea     rax, aPortclearstati; "PortClearStatistics"
0x18000a1a4  mov     [rbp+0B0h+var_D0], rax
0x18000a1a8  mov     eax, 0Bh
0x18000a1ad  mov     [rbp+0B0h+var_C8], ax
0x18000a1b1  lea     rax, aPortsend; "PortSend"
0x18000a1b8  mov     [rbp+0B0h+var_C0], rax
0x18000a1bc  mov     eax, 0Ch
0x18000a1c1  mov     [rbp+0B0h+var_B8], ax
0x18000a1c5  lea     rax, aPorttestsignal; "PortTestSignalState"
0x18000a1cc  mov     [rbp+0B0h+var_B0], rax
0x18000a1d0  mov     eax, 0Dh
0x18000a1d5  mov     [rbp+0B0h+var_A8], ax
0x18000a1d9  lea     rax, aPortreceive; "PortReceive"
0x18000a1e0  mov     [rbp+0B0h+var_A0], rax
0x18000a1e4  mov     eax, 0Eh
0x18000a1e9  mov     [rbp+0B0h+var_98], ax
0x18000a1ed  lea     rax, aPortinit; "PortInit"
0x18000a1f4  mov     [rbp+0B0h+var_90], rax
0x18000a1f8  mov     eax, 0Fh
0x18000a1fd  mov     [rbp+0B0h+var_88], ax
0x18000a201  lea     rax, aPortreceivecom; "PortReceiveComplete"
0x18000a208  mov     [rbp+0B0h+var_80], rax
0x18000a20c  mov     eax, 10h
0x18000a211  mov     [rbp+0B0h+var_78], ax
0x18000a215  lea     rax, aPortsetframing; "PortSetFraming"
0x18000a21c  mov     [rbp+0B0h+var_70], rax
0x18000a220  mov     eax, 11h
0x18000a225  mov     [rbp+0B0h+var_68], ax
0x18000a229  lea     rax, aPortgetiohandl; "PortGetIOHandle"
0x18000a230  mov     [rbp+0B0h+var_60], rax
0x18000a234  mov     eax, 12h
0x18000a239  mov     [rbp+0B0h+var_58], ax
0x18000a23d  lea     rax, aPortsetiocompl; "PortSetIoCompletionPort"
0x18000a244  mov     [rbp+0B0h+var_50], rax
0x18000a248  mov     eax, 13h
0x18000a24d  mov     [rbp+0B0h+var_48], ax
0x18000a251  mov     rcx, rsi; lpLibFileName
0x18000a254  call    cs:__imp_LoadLibraryExA
0x18000a25b  nop     dword ptr [rax+rax+00h]
0x18000a260  mov     rdi, rax
0x18000a263  test    rax, rax
0x18000a266  jnz     short loc_18000A2DB
0x18000a268  call    cs:__imp_GetLastError
0x18000a26f  nop     dword ptr [rax+rax+00h]
0x18000a274  mov     ebx, eax
0x18000a276  test    eax, eax
0x18000a278  jz      short loc_18000A2AA
0x18000a27a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a281  cmp     rcx, r13
0x18000a284  jz      loc_18000A671
0x18000a28a  test    [rcx+1Ch], r12d
0x18000a28e  jz      short loc_18000A2B1
0x18000a290  cmp     byte ptr [rcx+19h], 2
0x18000a294  jb      short loc_18000A2B1
0x18000a296  mov     rcx, [rcx+10h]
0x18000a29a  mov     edx, 86h
0x18000a29f  mov     r9d, eax
0x18000a2a2  mov     r8, r14
0x18000a2a5  call    WPP_SF_d
0x18000a2aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2b1  cmp     rcx, r13
0x18000a2b4  jz      loc_18000A671
0x18000a2ba  test    [rcx+1Ch], r12d
0x18000a2be  jz      loc_18000A671
0x18000a2c4  cmp     [rcx+19h], r15b
0x18000a2c8  jb      loc_18000A671
0x18000a2ce  mov     edx, 87h
0x18000a2d3  mov     r8, r14
0x18000a2d6  jmp     loc_18000A665
0x18000a2db  mov     [rsi+0B8h], rdi
0x18000a2e2  xor     r14d, r14d
0x18000a2e5  movzx   ebx, r14w
0x18000a2e9  mov     rcx, rdi; hModule
0x18000a2ec  mov     eax, ebx
0x18000a2ee  add     rax, rax
0x18000a2f1  mov     r15, [rsp+rax*8+1B0h+lpProcName]
0x18000a2f6  mov     rdx, r15; lpProcName
0x18000a2f9  call    cs:__imp_GetProcAddress
0x18000a300  nop     dword ptr [rax+rax+00h]
0x18000a305  mov     [rsi+rbx*8+10h], rax
0x18000a30a  test    rax, rax
0x18000a30d  jz      loc_18000A5DA
0x18000a313  inc     r14w
0x18000a317  cmp     r14w, 14h
0x18000a31c  jb      short loc_18000A2E5
0x18000a31e  lea     rdx, String2; "rastapi"
0x18000a325  mov     rcx, rsi; String1
0x18000a328  xor     ebx, ebx
0x18000a32a  call    cs:__imp__stricmp
0x18000a331  nop     dword ptr [rax+rax+00h]
0x18000a336  test    eax, eax
0x18000a338  jnz     loc_18000A641
0x18000a33e  lea     rdx, aPortopenextern; "PortOpenExternal"
0x18000a345  mov     rcx, rdi; hModule
0x18000a348  call    cs:__imp_GetProcAddress
0x18000a34f  nop     dword ptr [rax+rax+00h]
0x18000a354  mov     cs:RastapiPortOpen, rax
0x18000a35b  test    rax, rax
0x18000a35e  jz      loc_18000A592
0x18000a364  lea     rdx, aAddports; "AddPorts"
0x18000a36b  mov     rcx, rdi; hModule
0x18000a36e  call    cs:__imp_GetProcAddress
0x18000a375  nop     dword ptr [rax+rax+00h]
0x18000a37a  mov     cs:RastapiAddPorts, rax
0x18000a381  test    rax, rax
0x18000a384  jz      loc_18000A592
0x18000a38a  lea     rdx, aGetconnectinfo; "GetConnectInfo"
0x18000a391  mov     rcx, rdi; hModule
0x18000a394  call    cs:__imp_GetProcAddress
0x18000a39b  nop     dword ptr [rax+rax+00h]
0x18000a3a0  mov     cs:RastapiGetConnectInfo, rax
0x18000a3a7  test    rax, rax
0x18000a3aa  jz      loc_18000A592
0x18000a3b0  lea     rdx, aRemoveport; "RemovePort"
0x18000a3b7  mov     rcx, rdi; hModule
0x18000a3ba  call    cs:__imp_GetProcAddress
0x18000a3c1  nop     dword ptr [rax+rax+00h]
0x18000a3c6  mov     cs:RastapiRemovePort, rax
0x18000a3cd  test    rax, rax
0x18000a3d0  jz      loc_18000A592
0x18000a3d6  lea     rdx, aEnabledevicefo; "EnableDeviceForDialIn"
0x18000a3dd  mov     rcx, rdi; hModule
0x18000a3e0  call    cs:__imp_GetProcAddress
0x18000a3e7  nop     dword ptr [rax+rax+00h]
0x18000a3ec  mov     cs:RastapiEnableDeviceForDialIn, rax
0x18000a3f3  test    rax, rax
0x18000a3f6  jz      loc_18000A592
0x18000a3fc  lea     rdx, aRastapigetcall; "RastapiGetCalledID"
0x18000a403  mov     rcx, rdi; hModule
0x18000a406  call    cs:__imp_GetProcAddress
0x18000a40d  nop     dword ptr [rax+rax+00h]
0x18000a412  mov     cs:RastapiGetCalledIdInfo, rax
0x18000a419  test    rax, rax
0x18000a41c  jz      loc_18000A592
0x18000a422  lea     rdx, aRastapisetcall; "RastapiSetCalledID"
0x18000a429  mov     rcx, rdi; hModule
0x18000a42c  call    cs:__imp_GetProcAddress
0x18000a433  nop     dword ptr [rax+rax+00h]
0x18000a438  mov     cs:RastapiSetCalledIdInfo, rax
0x18000a43f  test    rax, rax
0x18000a442  jz      loc_18000A592
0x18000a448  lea     rdx, aGetzerodevicei; "GetZeroDeviceInfo"
0x18000a44f  mov     rcx, rdi; hModule
0x18000a452  call    cs:__imp_GetProcAddress
0x18000a459  nop     dword ptr [rax+rax+00h]
0x18000a45e  mov     cs:RastapiGetZeroDeviceInfo, rax
0x18000a465  test    rax, rax
0x18000a468  jz      loc_18000A592
0x18000a46e  lea     rdx, aUnloadrastapid; "UnloadRastapiDll"
0x18000a475  mov     rcx, rdi; hModule
0x18000a478  call    cs:__imp_GetProcAddress
0x18000a47f  nop     dword ptr [rax+rax+00h]
0x18000a484  mov     cs:RastapiUnload, rax
0x18000a48b  test    rax, rax
0x18000a48e  jz      loc_18000A592
0x18000a494  lea     rdx, aSetcommsetting; "SetCommSettings"
0x18000a49b  mov     rcx, rdi; hModule
0x18000a49e  call    cs:__imp_GetProcAddress
0x18000a4a5  nop     dword ptr [rax+rax+00h]
0x18000a4aa  mov     cs:RastapiSetCommSettings, rax
0x18000a4b1  test    rax, rax
0x18000a4b4  jz      loc_18000A592
0x18000a4ba  lea     rdx, aDevicegetdevco_0; "DeviceGetDevConfigEx"
0x18000a4c1  mov     rcx, rdi; hModule
0x18000a4c4  call    cs:__imp_GetProcAddress
0x18000a4cb  nop     dword ptr [rax+rax+00h]
0x18000a4d0  mov     cs:RastapiGetDevConfigEx, rax
0x18000a4d7  test    rax, rax
0x18000a4da  jz      loc_18000A592
0x18000a4e0  lea     rdx, aRastapiispulse; "RasTapiIsPulseDial"
0x18000a4e7  mov     rcx, rdi; hModule
0x18000a4ea  call    cs:__imp_GetProcAddress
0x18000a4f1  nop     dword ptr [rax+rax+00h]
0x18000a4f6  mov     cs:RastapiIsPulseDial, rax
0x18000a4fd  test    rax, rax
0x18000a500  jz      loc_18000A592
0x18000a506  lea     rdx, aRefreshdevices; "RefreshDevices"
0x18000a50d  mov     rcx, rdi; hModule
0x18000a510  call    cs:__imp_GetProcAddress
0x18000a517  nop     dword ptr [rax+rax+00h]
0x18000a51c  mov     cs:RastapiRefreshDevices, rax
0x18000a523  test    rax, rax
0x18000a526  jz      short loc_18000A592
0x18000a528  lea     rdx, aInitializedriv; "InitializeDriverIoControl"
0x18000a52f  mov     rcx, rdi; hModule
0x18000a532  call    cs:__imp_GetProcAddress
0x18000a539  nop     dword ptr [rax+rax+00h]
0x18000a53e  mov     cs:RastapiInitializeDriverIoctl, rax
0x18000a545  test    rax, rax
0x18000a548  jz      short loc_18000A592
0x18000a54a  lea     rdx, aUpdatetapiserv; "UpdateTapiService"
0x18000a551  mov     rcx, rdi; hModule
0x18000a554  call    cs:__imp_GetProcAddress
0x18000a55b  nop     dword ptr [rax+rax+00h]
0x18000a560  mov     cs:RastapiUpdateTapiService, rax
0x18000a567  test    rax, rax
0x18000a56a  jz      short loc_18000A592
0x18000a56c  lea     rdx, aCheckrasmandep; "CheckRasmanDependency"
0x18000a573  mov     rcx, rdi; hModule
0x18000a576  call    cs:__imp_GetProcAddress
0x18000a57d  nop     dword ptr [rax+rax+00h]
0x18000a582  mov     cs:RastapiCheckRasmanDependency, rax
0x18000a589  test    rax, rax
0x18000a58c  jnz     loc_18000A641
0x18000a592  call    cs:__imp_GetLastError
0x18000a599  nop     dword ptr [rax+rax+00h]
0x18000a59e  mov     ebx, eax
0x18000a5a0  test    eax, eax
0x18000a5a2  jz      loc_18000A641
0x18000a5a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5af  cmp     rcx, r13
0x18000a5b2  jz      short loc_18000A620
0x18000a5b4  test    [rcx+1Ch], r12d
0x18000a5b8  jz      short loc_18000A620
0x18000a5ba  cmp     byte ptr [rcx+19h], 2
0x18000a5be  jb      short loc_18000A620
0x18000a5c0  mov     rcx, [rcx+10h]
0x18000a5c4  lea     r8, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids
0x18000a5cb  mov     edx, 89h
0x18000a5d0  mov     r9d, eax
0x18000a5d3  call    WPP_SF_d
0x18000a5d8  jmp     short loc_18000A620
0x18000a5da  call    cs:__imp_GetLastError
0x18000a5e1  nop     dword ptr [rax+rax+00h]
0x18000a5e6  mov     ebx, eax
0x18000a5e8  test    eax, eax
0x18000a5ea  jz      short loc_18000A641
0x18000a5ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5f3  cmp     rcx, r13
  ... truncated ...
```
