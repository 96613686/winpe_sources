# NotifyFirmwareUpdateStagedInt(void)

- ea: `0x18004f9ac`
- end: `0x18004fe91`
- name: `?NotifyFirmwareUpdateStagedInt@@YAJXZ`
- size: `1253`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18001b080`

## callees

- `0x180003270`
- `0x180009c44`
- `0x180009c64`
- `0x18002d5ec`
- `0x18004f9ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004fbf8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004fbf8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004fd06`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004fd06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fcab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fd62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fdd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fe41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fcab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fd62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fdd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fe41`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18004fc91`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18004fd48`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18004fdb9`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18004fe27`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18004fc91`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18004fd48`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18004fdb9`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18004fe27`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18004fc59`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18004fc59`

## string_xrefs

- `0x18004fc75`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`
- `0x18004fcef`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`
- `0x18004fe05`: `DevCreateObjectQuery finished`
- `0x18004f9d5`: `NotifyFirmwareUpdateStagedInt`
- `0x18004fce0`: `Waiting on DevCreateObjectQuery callback to finish`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 NotifyFirmwareUpdateStagedInt(void)
{
  char *EventW; // rbx
  int ObjectQuery; // eax
  unsigned int v2; // esi
  DWORD v4; // eax
  const char *v5; // r9
  unsigned int LastError; // edi
  char v7; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v8; // [rsp+58h] [rbp-A8h]
  int v9; // [rsp+60h] [rbp-A0h] BYREF
  int v10; // [rsp+64h] [rbp-9Ch] BYREF
  int v11; // [rsp+68h] [rbp-98h] BYREF
  char *v12; // [rsp+70h] [rbp-90h]
  const char *v13; // [rsp+78h] [rbp-88h]
  char *v14; // [rsp+80h] [rbp-80h]
  int v15; // [rsp+90h] [rbp-70h]
  __int128 v16; // [rsp+98h] [rbp-68h]
  __int128 v17; // [rsp+A8h] [rbp-58h]
  __int128 v18; // [rsp+B8h] [rbp-48h]
  int v19; // [rsp+C8h] [rbp-38h]
  DEVPROPKEY v20; // [rsp+D0h] [rbp-30h]
  int v21; // [rsp+E4h] [rbp-1Ch]
  __int64 v22; // [rsp+E8h] [rbp-18h]
  int v23; // [rsp+F0h] [rbp-10h]
  int v24; // [rsp+F4h] [rbp-Ch]
  GUID *v25; // [rsp+F8h] [rbp-8h]
  int v26; // [rsp+100h] [rbp+0h]
  __int128 v27; // [rsp+108h] [rbp+8h]
  __int128 v28; // [rsp+118h] [rbp+18h]
  __int128 v29; // [rsp+128h] [rbp+28h]
  int v30; // [rsp+138h] [rbp+38h]
  __int128 v31; // [rsp+140h] [rbp+40h]
  int v32; // [rsp+150h] [rbp+50h]
  int v33; // [rsp+154h] [rbp+54h]
  __int64 v34; // [rsp+158h] [rbp+58h]
  int v35; // [rsp+160h] [rbp+60h]
  int v36; // [rsp+164h] [rbp+64h]
  int *v37; // [rsp+168h] [rbp+68h]
  int v38; // [rsp+170h] [rbp+70h]
  __int128 v39; // [rsp+178h] [rbp+78h]
  int v40; // [rsp+188h] [rbp+88h]
  int v41; // [rsp+18Ch] [rbp+8Ch]
  __int64 v42; // [rsp+190h] [rbp+90h]
  int v43; // [rsp+198h] [rbp+98h]
  int v44; // [rsp+19Ch] [rbp+9Ch]
  int *v45; // [rsp+1A0h] [rbp+A0h]
  int v46; // [rsp+1A8h] [rbp+A8h]
  __int128 v47; // [rsp+1B0h] [rbp+B0h]
  __int128 v48; // [rsp+1C0h] [rbp+C0h]
  __int128 v49; // [rsp+1D0h] [rbp+D0h]
  int v50; // [rsp+1E0h] [rbp+E0h]
  DEVPROPKEY v51; // [rsp+1E8h] [rbp+E8h]
  int v52; // [rsp+1FCh] [rbp+FCh]
  __int64 v53; // [rsp+200h] [rbp+100h]
  int v54; // [rsp+208h] [rbp+108h]
  int v55; // [rsp+20Ch] [rbp+10Ch]
  char *v56; // [rsp+210h] [rbp+110h]
  int v57; // [rsp+218h] [rbp+118h]
  DEVPROPKEY v58; // [rsp+220h] [rbp+120h]
  int v59; // [rsp+234h] [rbp+134h]
  __int64 v60; // [rsp+238h] [rbp+138h]
  int v61; // [rsp+240h] [rbp+140h]
  int v62; // [rsp+244h] [rbp+144h]
  int *v63; // [rsp+248h] [rbp+148h]
  int v64; // [rsp+250h] [rbp+150h]
  __int128 v65; // [rsp+258h] [rbp+158h]
  __int128 v66; // [rsp+268h] [rbp+168h]
  __int128 v67; // [rsp+278h] [rbp+178h]
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v13 = "NotifyFirmwareUpdateStagedInt";
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x84u,
    "PpfTraceFunctionEntryExit::PpfTraceFunctionEntryExit",
    "Entering %hs",
    "NotifyFirmwareUpdateStagedInt");
  v7 = -1;
  v9 = 1;
  v10 = 2;
  v11 = 14;
  v15 = 0x100000;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 2;
  v20 = DEVPKEY_Device_ClassGuid;
  v21 = 0;
  v22 = 0;
  v23 = 13;
  v24 = 16;
  v25 = &GUID_DEVCLASS_FIRMWARE;
  v26 = 3145728;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 2;
  v31 = DEVPKEY_FirmwareResource_Type;
  v32 = 3;
  v33 = 0;
  v34 = 0;
  v35 = 7;
  v36 = 4;
  v37 = &v9;
  v38 = 2;
  v39 = DEVPKEY_FirmwareResource_Type;
  v40 = 3;
  v41 = 0;
  v42 = 0;
  v43 = 7;
  v44 = 4;
  v45 = &v10;
  v46 = 0x400000;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 2;
  v51 = DEVPKEY_Device_IsPresent;
  v52 = 0;
  v53 = 0;
  v54 = 17;
  v55 = 1;
  v56 = &v7;
  v57 = 2;
  v58 = DEVPKEY_Device_ProblemCode;
  v59 = 0;
  v60 = 0;
  v61 = 7;
  v62 = 4;
  v63 = &v11;
  v64 = 0x200000;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  v14 = EventW;
  v12 = EventW;
  v8 = 0;
  ObjectQuery = DevCreateObjectQuery(3, 0, 4, &g_propertiesQueried);
  v2 = ObjectQuery;
  if ( ObjectQuery < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DC,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
      (const char *)(unsigned int)ObjectQuery,
      9);
    if ( v8 )
      DevCloseObjectQuery();
    if ( (unsigned __int64)(EventW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(EventW);
LABEL_6:
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "NotifyFirmwareUpdateStagedInt");
    return v2;
  }
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
    0x1DDu,
    "NotifyFirmwareUpdateStagedInt",
    "Waiting on DevCreateObjectQuery callback to finish");
  v4 = WaitForSingleObject(EventW, 0xFFFFFFFF);
  switch ( v4 )
  {
    case 0u:
      goto LABEL_20;
    case 0x80u:
      v2 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E1,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
        (const char *)0x8000FFFFLL,
        9);
      if ( v8 )
        DevCloseObjectQuery();
      if ( (unsigned __int64)(EventW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(EventW);
      goto LABEL_6;
    case 0xFFFFFFFF:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1E2,
                    (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
                    v5);
      if ( v8 )
        DevCloseObjectQuery();
      if ( (unsigned __int64)(EventW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(EventW);
      PpfTraceLogFormat(
        "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
        0x89u,
        "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
        "Leaving %hs",
        "NotifyFirmwareUpdateStagedInt");
      return LastError;
    default:
LABEL_20:
      PpfTraceLogFormat(
        "onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
        0x1E4u,
        "NotifyFirmwareUpdateStagedInt",
        "DevCreateObjectQuery finished");
      if ( v8 )
        DevCloseObjectQuery();
      if ( (unsigned __int64)(EventW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(EventW);
      PpfTraceLogFormat(
        "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
        0x89u,
        "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
        "Leaving %hs",
        "NotifyFirmwareUpdateStagedInt");
      return 0;
  }
}

```

## disassembly

```asm
0x18004f9ac  push    rbp
0x18004f9ae  push    rbx
0x18004f9af  push    rsi
0x18004f9b0  push    rdi
0x18004f9b1  push    r12
0x18004f9b3  push    r15
0x18004f9b5  lea     rbp, [rsp-1A8h]
0x18004f9bd  sub     rsp, 2A8h
0x18004f9c4  mov     rax, cs:__security_cookie
0x18004f9cb  xor     rax, rsp
0x18004f9ce  mov     [rbp+1D0h+var_40], rax
0x18004f9d5  lea     r15, aNotifyfirmware_0; "NotifyFirmwareUpdateStagedInt"
0x18004f9dc  mov     [rsp+2D0h+var_258], r15
0x18004f9e1  mov     qword ptr [rsp+2D0h+var_2B0], r15
0x18004f9e6  lea     r9, aEnteringHs; "Entering %hs"
0x18004f9ed  lea     r8, aPpftracefuncti; "PpfTraceFunctionEntryExit::PpfTraceFunc"...
0x18004f9f4  mov     edx, 84h; unsigned int
0x18004f9f9  lea     r12, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18004fa00  mov     rcx, r12; char *
0x18004fa03  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18004fa08  nop
0x18004fa09  mov     [rsp+2D0h+var_280], 0FFh
0x18004fa0e  mov     r10d, 1
0x18004fa14  mov     [rsp+2D0h+var_270], r10d
0x18004fa19  lea     edx, [r10+1]
0x18004fa1d  mov     [rsp+2D0h+var_26C], edx
0x18004fa21  mov     [rsp+2D0h+var_268], 0Eh
0x18004fa29  mov     [rbp+1D0h+var_240], 100000h
0x18004fa30  xorps   xmm0, xmm0
0x18004fa33  movups  [rbp+1D0h+var_238], xmm0
0x18004fa37  movups  [rbp+1D0h+var_228], xmm0
0x18004fa3b  movups  [rbp+1D0h+var_218], xmm0
0x18004fa3f  mov     [rbp+1D0h+var_208], edx
0x18004fa42  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ClassGuid.fmtid.Data1
0x18004fa49  movaps  [rbp+1D0h+var_200], xmm0
0x18004fa4d  mov     eax, cs:DEVPKEY_Device_ClassGuid.pid
0x18004fa53  mov     [rbp+1D0h+var_1F0], eax
0x18004fa56  mov     [rbp+1D0h+var_1EC], 0
0x18004fa5d  mov     [rbp+1D0h+var_1E8], 0
0x18004fa65  mov     [rbp+1D0h+var_1E0], 0Dh
0x18004fa6c  mov     [rbp+1D0h+var_1DC], 10h
0x18004fa73  lea     rax, GUID_DEVCLASS_FIRMWARE
0x18004fa7a  mov     [rbp+1D0h+var_1D8], rax
0x18004fa7e  mov     [rbp+1D0h+var_1D0], 300000h
0x18004fa85  xorps   xmm0, xmm0
0x18004fa88  movups  [rbp+1D0h+var_1C8], xmm0
0x18004fa8c  movups  [rbp+1D0h+var_1B8], xmm0
0x18004fa90  movups  [rbp+1D0h+var_1A8], xmm0
0x18004fa94  mov     [rbp+1D0h+var_198], edx
0x18004fa97  movups  xmm1, cs:DEVPKEY_FirmwareResource_Type
0x18004fa9e  movaps  [rbp+1D0h+var_190], xmm1
0x18004faa2  mov     eax, cs:dword_1800668F0
0x18004faa8  mov     [rbp+1D0h+var_180], eax
0x18004faab  mov     [rbp+1D0h+var_17C], 0
0x18004fab2  mov     [rbp+1D0h+var_178], 0
0x18004faba  lea     r8d, [r10+6]
0x18004fabe  mov     [rbp+1D0h+var_170], r8d
0x18004fac2  lea     edi, [rdx+2]
0x18004fac5  mov     [rbp+1D0h+var_16C], edi
0x18004fac8  lea     rcx, [rsp+2D0h+var_270]
0x18004facd  mov     [rbp+1D0h+var_168], rcx
0x18004fad1  mov     [rbp+1D0h+var_160], edx
0x18004fad4  movups  [rbp+1D0h+var_158], xmm1
0x18004fad8  mov     [rbp+1D0h+var_148], eax
0x18004fade  mov     [rbp+1D0h+var_144], 0
0x18004fae8  mov     [rbp+1D0h+var_140], 0
0x18004faf3  mov     [rbp+1D0h+var_138], r8d
0x18004fafa  mov     [rbp+1D0h+var_134], edi
0x18004fb00  lea     rax, [rsp+2D0h+var_26C]
0x18004fb05  mov     [rbp+1D0h+var_130], rax
0x18004fb0c  mov     [rbp+1D0h+var_128], 400000h
0x18004fb16  movups  [rbp+1D0h+var_120], xmm0
0x18004fb1d  movups  [rbp+1D0h+var_110], xmm0
0x18004fb24  movups  [rbp+1D0h+var_100], xmm0
0x18004fb2b  mov     [rbp+1D0h+var_F0], edx
0x18004fb31  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_IsPresent.fmtid.Data1
0x18004fb38  movups  [rbp+1D0h+var_E8], xmm0
0x18004fb3f  mov     eax, cs:DEVPKEY_Device_IsPresent.pid
0x18004fb45  mov     [rbp+1D0h+var_D8], eax
0x18004fb4b  mov     [rbp+1D0h+var_D4], 0
0x18004fb55  mov     [rbp+1D0h+var_D0], 0
0x18004fb60  mov     [rbp+1D0h+var_C8], 11h
0x18004fb6a  mov     [rbp+1D0h+var_C4], r10d
0x18004fb71  lea     rax, [rsp+2D0h+var_280]
0x18004fb76  mov     [rbp+1D0h+var_C0], rax
0x18004fb7d  mov     [rbp+1D0h+var_B8], edx
0x18004fb83  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ProblemCode.fmtid.Data1
0x18004fb8a  movaps  [rbp+1D0h+var_B0], xmm0
0x18004fb91  mov     eax, cs:DEVPKEY_Device_ProblemCode.pid
0x18004fb97  mov     [rbp+1D0h+var_A0], eax
0x18004fb9d  mov     [rbp+1D0h+var_9C], 0
0x18004fba7  mov     [rbp+1D0h+var_98], 0
0x18004fbb2  mov     [rbp+1D0h+var_90], r8d
0x18004fbb9  mov     [rbp+1D0h+var_8C], edi
0x18004fbbf  lea     rax, [rsp+2D0h+var_268]
0x18004fbc4  mov     [rbp+1D0h+var_88], rax
0x18004fbcb  mov     [rbp+1D0h+var_80], 200000h
0x18004fbd5  xorps   xmm0, xmm0
0x18004fbd8  movups  [rbp+1D0h+var_78], xmm0
0x18004fbdf  movups  [rbp+1D0h+var_68], xmm0
0x18004fbe6  movups  [rbp+1D0h+var_58], xmm0
0x18004fbed  xor     r9d, r9d; lpName
0x18004fbf0  xor     r8d, r8d; bInitialState
0x18004fbf3  mov     edx, r10d; bManualReset
0x18004fbf6  xor     ecx, ecx; lpEventAttributes
0x18004fbf8  call    cs:__imp_CreateEventW
0x18004fbff  nop     dword ptr [rax+rax+00h]
0x18004fc04  mov     rbx, rax
0x18004fc07  mov     [rbp+1D0h+var_250], rax
0x18004fc0b  mov     [rsp+2D0h+var_260], rax
0x18004fc10  mov     [rsp+2D0h+var_278], 0
0x18004fc19  lea     rax, [rsp+2D0h+var_278]
0x18004fc1e  mov     [rsp+2D0h+var_290], rax
0x18004fc23  lea     rax, [rsp+2D0h+var_260]
0x18004fc28  mov     [rsp+2D0h+var_298], rax
0x18004fc2d  lea     rax, ?FirmwareDeviceQueryCallback@@YAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; FirmwareDeviceQueryCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x18004fc34  mov     [rsp+2D0h+var_2A0], rax
0x18004fc39  lea     rax, [rbp+1D0h+var_240]
0x18004fc3d  mov     [rsp+2D0h+var_2A8], rax
0x18004fc42  mov     [rsp+2D0h+var_2B0], 9; int
0x18004fc4a  lea     r9, ?g_propertiesQueried@@3PAU_DEVPROPCOMPKEY@@A; _DEVPROPCOMPKEY near * g_propertiesQueried
0x18004fc51  mov     r8d, edi
0x18004fc54  xor     edx, edx
0x18004fc56  lea     ecx, [rdi-1]
0x18004fc59  call    cs:__imp_DevCreateObjectQuery
0x18004fc60  nop     dword ptr [rax+rax+00h]
0x18004fc65  mov     esi, eax
0x18004fc67  test    eax, eax
0x18004fc69  jns     short loc_18004FCE0
0x18004fc6b  mov     rcx, [rbp+1D8h]; this
0x18004fc72  mov     r9d, eax; char *
0x18004fc75  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18004fc7c  mov     edx, 1DCh; void *
0x18004fc81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fc86  nop
0x18004fc87  mov     rcx, [rsp+2D0h+var_278]
0x18004fc8c  test    rcx, rcx
0x18004fc8f  jz      short loc_18004FC9E
0x18004fc91  call    cs:__imp_DevCloseObjectQuery
0x18004fc98  nop     dword ptr [rax+rax+00h]
0x18004fc9d  nop
0x18004fc9e  lea     rax, [rbx-1]
0x18004fca2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004fca6  ja      short loc_18004FCB8
0x18004fca8  mov     rcx, rbx; hObject
0x18004fcab  call    cs:__imp_CloseHandle
0x18004fcb2  nop     dword ptr [rax+rax+00h]
0x18004fcb7  nop
0x18004fcb8  mov     qword ptr [rsp+2D0h+var_2B0], r15
0x18004fcbd  lea     r9, aLeavingHs; "Leaving %hs"
0x18004fcc4  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18004fccb  mov     edx, 89h; unsigned int
0x18004fcd0  mov     rcx, r12; char *
0x18004fcd3  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18004fcd8  nop
0x18004fcd9  mov     eax, esi
0x18004fcdb  jmp     loc_18004FE71
0x18004fce0  lea     r9, aWaitingOnDevcr; "Waiting on DevCreateObjectQuery callbac"...
0x18004fce7  mov     r8, r15; char *
0x18004fcea  mov     edx, 1DDh; unsigned int
0x18004fcef  lea     rdi, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18004fcf6  mov     rcx, rdi; char *
0x18004fcf9  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18004fcfe  or      esi, 0FFFFFFFFh
0x18004fd01  mov     edx, esi; dwMilliseconds
0x18004fd03  mov     rcx, rbx; hHandle
0x18004fd06  call    cs:__imp_WaitForSingleObject
0x18004fd0d  nop     dword ptr [rax+rax+00h]
0x18004fd12  test    eax, eax
0x18004fd14  jz      loc_18004FE05
0x18004fd1a  cmp     eax, 80h
0x18004fd1f  jnz     short loc_18004FD95
0x18004fd21  mov     rcx, [rbp+1D8h]; this
0x18004fd28  mov     esi, 8000FFFFh
0x18004fd2d  mov     r9d, esi; char *
0x18004fd30  mov     r8, rdi; unsigned int
0x18004fd33  mov     edx, 1E1h; void *
0x18004fd38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fd3d  nop
0x18004fd3e  mov     rcx, [rsp+2D0h+var_278]
0x18004fd43  test    rcx, rcx
0x18004fd46  jz      short loc_18004FD55
0x18004fd48  call    cs:__imp_DevCloseObjectQuery
0x18004fd4f  nop     dword ptr [rax+rax+00h]
0x18004fd54  nop
0x18004fd55  lea     rax, [rbx-1]
0x18004fd59  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004fd5d  ja      short loc_18004FD6F
0x18004fd5f  mov     rcx, rbx; hObject
0x18004fd62  call    cs:__imp_CloseHandle
0x18004fd69  nop     dword ptr [rax+rax+00h]
0x18004fd6e  nop
0x18004fd6f  mov     qword ptr [rsp+2D0h+var_2B0], r15
0x18004fd74  lea     r9, aLeavingHs; "Leaving %hs"
0x18004fd7b  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18004fd82  mov     edx, 89h; unsigned int
0x18004fd87  mov     rcx, r12; char *
0x18004fd8a  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18004fd8f  nop
0x18004fd90  jmp     loc_18004FCD9
0x18004fd95  cmp     eax, esi
0x18004fd97  jnz     short loc_18004FE05
0x18004fd99  mov     rcx, [rbp+1D8h]; this
0x18004fda0  mov     r8, rdi; unsigned int
0x18004fda3  mov     edx, 1E2h; void *
0x18004fda8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004fdad  mov     edi, eax
0x18004fdaf  mov     rcx, [rsp+2D0h+var_278]
0x18004fdb4  test    rcx, rcx
0x18004fdb7  jz      short loc_18004FDC6
0x18004fdb9  call    cs:__imp_DevCloseObjectQuery
0x18004fdc0  nop     dword ptr [rax+rax+00h]
0x18004fdc5  nop
0x18004fdc6  lea     rcx, [rbx-1]
0x18004fdca  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18004fdce  ja      short loc_18004FDE0
0x18004fdd0  mov     rcx, rbx; hObject
0x18004fdd3  call    cs:__imp_CloseHandle
0x18004fdda  nop     dword ptr [rax+rax+00h]
0x18004fddf  nop
0x18004fde0  mov     qword ptr [rsp+2D0h+var_2B0], r15
0x18004fde5  lea     r9, aLeavingHs; "Leaving %hs"
0x18004fdec  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18004fdf3  mov     edx, 89h; unsigned int
0x18004fdf8  mov     rcx, r12; char *
0x18004fdfb  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18004fe00  nop
0x18004fe01  mov     eax, edi
0x18004fe03  jmp     short loc_18004FE71
0x18004fe05  lea     r9, aDevcreateobjec; "DevCreateObjectQuery finished"
0x18004fe0c  mov     r8, r15; char *
0x18004fe0f  mov     edx, 1E4h; unsigned int
0x18004fe14  mov     rcx, rdi; char *
0x18004fe17  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18004fe1c  nop
0x18004fe1d  mov     rcx, [rsp+2D0h+var_278]
0x18004fe22  test    rcx, rcx
0x18004fe25  jz      short loc_18004FE34
0x18004fe27  call    cs:__imp_DevCloseObjectQuery
0x18004fe2e  nop     dword ptr [rax+rax+00h]
0x18004fe33  nop
0x18004fe34  lea     rax, [rbx-1]
0x18004fe38  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004fe3c  ja      short loc_18004FE4E
0x18004fe3e  mov     rcx, rbx; hObject
0x18004fe41  call    cs:__imp_CloseHandle
0x18004fe48  nop     dword ptr [rax+rax+00h]
0x18004fe4d  nop
0x18004fe4e  mov     qword ptr [rsp+2D0h+var_2B0], r15
0x18004fe53  lea     r9, aLeavingHs; "Leaving %hs"
0x18004fe5a  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18004fe61  mov     edx, 89h; unsigned int
0x18004fe66  mov     rcx, r12; char *
0x18004fe69  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18004fe6e  nop
0x18004fe6f  xor     eax, eax
0x18004fe71  mov     rcx, [rbp+1D0h+var_40]
0x18004fe78  xor     rcx, rsp; StackCookie
0x18004fe7b  call    __security_check_cookie
0x18004fe80  add     rsp, 2A8h
0x18004fe87  pop     r15
0x18004fe89  pop     r12
0x18004fe8b  pop     rdi
0x18004fe8c  pop     rsi
0x18004fe8d  pop     rbx
0x18004fe8e  pop     rbp
0x18004fe8f  retn
```
