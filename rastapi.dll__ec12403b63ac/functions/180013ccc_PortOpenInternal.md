# PortOpenInternal

- ea: `0x180013ccc`
- end: `0x180014235`
- name: `PortOpenInternal`
- size: `1385`
- prototype: `__int64 __usercall@<rax>(char *String1@<rcx>, char)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013ca0`
- `0x180013cc0`

## callees

- `0x18000d92c`
- `0x1800108a0`
- `0x180012340`
- `0x180012f64`
- `0x180013ccc`
- `0x18002619c`
- `0x1800292b0`

## import_xrefs

- `msvcrt!_stricmp` at `0x180013d31`
- `msvcrt!_stricmp` at `0x180013daf`
- `msvcrt!_stricmp` at `0x180013faf`
- `msvcrt!_stricmp` at `0x180013d31`
- `msvcrt!_stricmp` at `0x180013daf`
- `msvcrt!_stricmp` at `0x180013faf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001411e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001411e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001415f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014165`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001415f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014165`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013d8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013dfe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013f72`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014155`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800141ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800141e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013d8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013dfe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013f72`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014155`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800141ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800141e7`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetDevCapsA` at `0x180013e7c`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetDevCapsA` at `0x180013e7c`
- `ext-ms-win-ras-tapi32-l1-1-1!lineSetStatusMessages` at `0x180013f9e`
- `ext-ms-win-ras-tapi32-l1-1-1!lineSetStatusMessages` at `0x180013f9e`
- `ext-ms-win-ras-tapi32-l1-1-1!lineSetDevConfigA` at `0x180014017`
- `ext-ms-win-ras-tapi32-l1-1-1!lineSetDevConfigA` at `0x180014017`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetDevConfigA` at `0x180013fdf`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetDevConfigA` at `0x180013fdf`
- `ext-ms-win-ras-tapi32-l1-1-1!lineOpenA` at `0x180013f32`
- `ext-ms-win-ras-tapi32-l1-1-1!lineOpenA` at `0x180013f32`

## string_xrefs

- `0x180013fc3`: `comm/datamodem`
- `0x180014008`: `comm/datamodem`
- `0x180013d0e`: `PortOpen: %s`
- `0x180013d60`: `PortOpen: state = PS_UNINITIALIZED, returning %d`
- `0x180013d77`: `PortOpen: Port is already open. state = %d != PS_CLOSED`
- `0x180013dd6`: `PortOpen: Failed to CreateFile asyncmac. %d`
- `0x180013de6`: `Failed to open asyncmac but no error!!!`
- `0x180013ea3`: `Opening line in monitor mode`
- `0x180013ec8`: `Opening line in owner mode`
- `0x180013f54`: `PortOpen: lineOpen Failed. 0x%x`
- `0x180014142`: `PortOpen: LocalAlloc Failed. %d, port %s, state = %d`
- `0x1800141c0`: `PortOpen: successfully opened %s`
- `0x1800141d4`: `PortOpen: Port %s not found`

## pseudocode

```c
DWORD __fastcall PortOpenInternal(char *String1, _QWORD *a2, __int64 a3, __int64 a4, char a5)
{
  int v5; // r13d
  __int64 v6; // rsi
  char *v9; // rdi
  int v10; // edx
  int v11; // ebx
  __int64 v12; // rcx
  int v13; // ebp
  int v14; // eax
  DWORD dwPrivileges; // esi
  unsigned int *dwCallbackInstance; // rcx
  unsigned int dwMediaModes; // r8d
  int v18; // eax
  int v19; // esi
  HANDLE v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  _WORD *v23; // rdx
  _BYTE *v24; // rcx
  const char *v25; // r8
  __int64 v26; // rax
  __int64 v27; // rdx
  _BYTE *v28; // rax
  __int64 v29; // rax
  _DWORD *v30; // rax
  struct linedevcaps_tag LineDevCaps; // [rsp+60h] [rbp-438h] BYREF

  v5 = a4;
  v6 = a3;
  GetMutex(String1, a2, a3, a4);
  RasTapiTrace("PortOpen: %s");
  v9 = (char *)RasPortsList;
  if ( !RasPortsList )
    goto LABEL_62;
  do
  {
    if ( !_stricmp(String1, v9 + 24) && *((_DWORD *)v9 + 14) != 7 )
      break;
    v9 = (char *)*((_QWORD *)v9 + 1);
  }
  while ( v9 );
  if ( !v9 )
  {
LABEL_62:
    RasTapiTrace("PortOpen: Port %s not found");
    if ( !ReleaseMutex(RasTapiMutex) )
      GetLastError();
    v11 = 665;
    goto LABEL_65;
  }
  v10 = *((_DWORD *)v9 + 14);
  if ( v10 == 6 )
  {
    v11 = 615;
    RasTapiTrace("PortOpen: state = PS_UNINITIALIZED, returning %d");
LABEL_17:
    if ( !ReleaseMutex(RasTapiMutex) )
      GetLastError();
LABEL_65:
    RasTapiTrace(" ");
    return v11;
  }
  if ( v10 )
  {
    RasTapiTrace("PortOpen: Port is already open. state = %d != PS_CLOSED");
    if ( !ReleaseMutex(RasTapiMutex) )
      GetLastError();
    v11 = 602;
    goto LABEL_65;
  }
  if ( !_stricmp(v9 + 64, "MODEM") && g_hAsyMac == (HANDLE)-1LL )
  {
    v11 = OpenAsyncMac();
    if ( g_hAsyMac == (HANDLE)-1LL )
    {
      RasTapiTrace("PortOpen: Failed to CreateFile asyncmac. %d");
      if ( !v11 )
      {
        RasTapiTrace("Failed to open asyncmac but no error!!!");
        v11 = 2;
      }
      goto LABEL_17;
    }
  }
  v12 = *((_QWORD *)v9 + 27);
  v13 = 0;
  v14 = (unsigned __int16)*(_DWORD *)(*(_QWORD *)(v12 + 40) + 96LL);
  if ( (v14 == 8 || (unsigned int)(v14 - 14) <= 1) && (a5 & 2) != 0 )
    v13 = 1;
  if ( !*(_DWORD *)(v12 + 16) )
  {
    if ( *(_DWORD *)(v12 + 60) )
    {
      *(_DWORD *)(v12 + 56) = 258;
    }
    else
    {
      LineDevCaps.dwTotalSize = 400;
      lineGetDevCapsA(RasLine, *(_DWORD *)(v12 + 8), *(_DWORD *)(v12 + 24), *(_DWORD *)(v12 + 28), &LineDevCaps);
      *(_DWORD *)(*((_QWORD *)v9 + 27) + 56LL) = LineDevCaps.dwMediaModes & 0xFFFFFFF3;
    }
    if ( v13 )
    {
      dwPrivileges = 2;
      RasTapiTrace("Opening line in monitor mode");
      *(_DWORD *)(*((_QWORD *)v9 + 27) + 48LL) |= 1u;
      ++*(_DWORD *)(*((_QWORD *)v9 + 27) + 52LL);
    }
    else
    {
      RasTapiTrace("Opening line in owner mode");
      dwPrivileges = 4;
      *(_DWORD *)(*((_QWORD *)v9 + 27) + 48LL) &= ~1u;
      *(_DWORD *)(*((_QWORD *)v9 + 27) + 48LL) &= ~2u;
    }
    dwCallbackInstance = (unsigned int *)*((_QWORD *)v9 + 27);
    dwMediaModes = dwCallbackInstance[14];
    if ( dwCallbackInstance[15] )
      v18 = RasLineOpen(
              dwCallbackInstance[2],
              dwPrivileges,
              dwMediaModes,
              (__int64)dwCallbackInstance,
              (__int64)(dwCallbackInstance + 3));
    else
      v18 = lineOpenA(
              RasLine,
              dwCallbackInstance[2],
              dwCallbackInstance + 3,
              dwCallbackInstance[6],
              dwCallbackInstance[7],
              (DWORD_PTR)dwCallbackInstance,
              dwPrivileges,
              dwMediaModes,
              0);
    v19 = v18;
    if ( v18 )
    {
      RasTapiTrace("PortOpen: lineOpen Failed. 0x%x");
      v20 = RasTapiMutex;
      *(_DWORD *)(*((_QWORD *)v9 + 27) + 48LL) &= ~1u;
      if ( !ReleaseMutex(v20) )
        GetLastError();
      v11 = v19;
      goto LABEL_65;
    }
    v21 = *((_QWORD *)v9 + 27);
    if ( !*(_DWORD *)(v21 + 60) )
      lineSetStatusMessages(*(_DWORD *)(v21 + 12), 2u, 0);
    if ( !_stricmp(v9 + 64, "MODEM") )
    {
      v22 = *((_QWORD *)v9 + 27);
      LineDevCaps.dwTotalSize = 1000;
      LineDevCaps.dwProviderInfoOffset = 0;
      lineGetDevConfigA(*(_DWORD *)(v22 + 8), (LPVARSTRING)&LineDevCaps, "comm/datamodem");
      v23 = (_WORD *)((char *)&LineDevCaps + LineDevCaps.dwSwitchInfoSize);
      if ( LineDevCaps.dwSwitchInfoSize <= 0x3DC )
        v23[4] &= ~8u;
      lineSetDevConfigA(
        *(_DWORD *)(*((_QWORD *)v9 + 27) + 8LL),
        v23,
        LineDevCaps.dwProviderInfoOffset,
        "comm/datamodem");
      DwEnableModemDiagnostics(v9);
      RasTapiTrace("DwEnableModemDiagnostics returned 0x%x");
    }
    v6 = a3;
    *(_DWORD *)(*((_QWORD *)v9 + 27) + 16LL) = 1;
  }
  v24 = v9 + 360;
  v9[260] = 0;
  v9[360] = 0;
  v25 = "64000";
  v9[460] = 0;
  v26 = 2147483646;
  v9[560] = 0;
  v27 = 100;
  v9[660] = 0;
  do
  {
    if ( !v26 )
      break;
    if ( !*v25 )
      break;
    *v24++ = *v25++;
    --v26;
    --v27;
  }
  while ( v27 );
  v28 = v24 - 1;
  if ( v27 )
    v28 = v24;
  *v28 = 0;
  ++*(_DWORD *)(*((_QWORD *)v9 + 27) + 20LL);
  v29 = *((_QWORD *)v9 + 27);
  *((_DWORD *)v9 + 14) = 1;
  *((_DWORD *)v9 + 273) = 0;
  *((_QWORD *)v9 + 111) = -1;
  *((_QWORD *)v9 + 30) = v6;
  *((_DWORD *)v9 + 62) = v5;
  if ( !*(_DWORD *)(v29 + 32)
    || (*((_DWORD *)v9 + 298) = 0, *((_DWORD *)v9 + 284) = -1, *((_DWORD *)v9 + 280) = -1, *((_QWORD *)v9 + 146)) )
  {
LABEL_57:
    *a2 = v9;
    if ( v13 )
      *((_DWORD *)v9 + 276) |= 0x10u;
    if ( !ReleaseMutex(RasTapiMutex) )
      GetLastError();
    RasTapiTrace("PortOpen: successfully opened %s");
    v11 = 0;
    goto LABEL_65;
  }
  v30 = LocalAlloc(0x40u, 0x5F0u);
  *((_QWORD *)v9 + 146) = v30;
  if ( v30 )
  {
    *v30 = 0;
    *(_DWORD *)(*((_QWORD *)v9 + 146) + 8LL) = 0;
    *(_DWORD *)(*((_QWORD *)v9 + 146) + 4LL) = 0;
    *(_DWORD *)(*((_QWORD *)v9 + 146) + 12LL) = 1500;
    goto LABEL_57;
  }
  GetLastError();
  RasTapiTrace("PortOpen: LocalAlloc Failed. %d, port %s, state = %d");
  if ( !ReleaseMutex(RasTapiMutex) )
    GetLastError();
  return GetLastError();
}

```

## disassembly

```asm
0x180013ccc  mov     [rsp+arg_10], rbx
0x180013cd1  push    rbp
0x180013cd2  push    rsi
0x180013cd3  push    rdi
0x180013cd4  push    r12
0x180013cd6  push    r13
0x180013cd8  push    r14
0x180013cda  push    r15
0x180013cdc  sub     rsp, 460h
0x180013ce3  mov     rax, cs:__security_cookie
0x180013cea  xor     rax, rsp
0x180013ced  mov     [rsp+498h+var_48], rax
0x180013cf5  mov     r13d, r9d
0x180013cf8  mov     [rsp+498h+var_448], r8
0x180013cfd  mov     rsi, r8
0x180013d00  mov     r12, rdx
0x180013d03  mov     r14, rcx
0x180013d06  call    GetMutex
0x180013d0b  mov     rdx, r14
0x180013d0e  lea     rcx, aPortopenS; "PortOpen: %s"
0x180013d15  call    RasTapiTrace
0x180013d1a  mov     rdi, cs:RasPortsList
0x180013d21  test    rdi, rdi
0x180013d24  jz      loc_1800141D1
0x180013d2a  lea     rdx, [rdi+18h]; String2
0x180013d2e  mov     rcx, r14; String1
0x180013d31  call    cs:__imp__stricmp
0x180013d37  test    eax, eax
0x180013d39  jnz     short loc_180013D41
0x180013d3b  cmp     dword ptr [rdi+38h], 7
0x180013d3f  jnz     short loc_180013D4A
0x180013d41  mov     rdi, [rdi+8]
0x180013d45  test    rdi, rdi
0x180013d48  jnz     short loc_180013D2A
0x180013d4a  test    rdi, rdi
0x180013d4d  jz      loc_1800141D1
0x180013d53  mov     edx, [rdi+38h]
0x180013d56  cmp     edx, 6
0x180013d59  jnz     short loc_180013D73
0x180013d5b  mov     ebx, 267h
0x180013d60  lea     rcx, aPortopenStateP; "PortOpen: state = PS_UNINITIALIZED, ret"...
0x180013d67  mov     edx, ebx
0x180013d69  call    RasTapiTrace
0x180013d6e  jmp     loc_180013DF7
0x180013d73  test    edx, edx
0x180013d75  jz      short loc_180013DA4
0x180013d77  lea     rcx, aPortopenPortIs; "PortOpen: Port is already open. state ="...
0x180013d7e  call    RasTapiTrace
0x180013d83  mov     rcx, cs:RasTapiMutex; hMutex
0x180013d8a  call    cs:__imp_ReleaseMutex
0x180013d90  test    eax, eax
0x180013d92  jnz     short loc_180013D9A
0x180013d94  call    cs:__imp_GetLastError
0x180013d9a  mov     ebx, 25Ah
0x180013d9f  jmp     loc_1800141FC
0x180013da4  lea     rdx, aModem; "MODEM"
0x180013dab  lea     rcx, [rdi+40h]; String1
0x180013daf  call    cs:__imp__stricmp
0x180013db5  test    eax, eax
0x180013db7  jnz     short loc_180013E17
0x180013db9  cmp     cs:g_hAsyMac, 0FFFFFFFFFFFFFFFFh
0x180013dc1  jnz     short loc_180013E17
0x180013dc3  call    OpenAsyncMac
0x180013dc8  cmp     cs:g_hAsyMac, 0FFFFFFFFFFFFFFFFh
0x180013dd0  mov     ebx, eax
0x180013dd2  jnz     short loc_180013E17
0x180013dd4  mov     edx, eax
0x180013dd6  lea     rcx, aPortopenFailed; "PortOpen: Failed to CreateFile asyncmac"...
0x180013ddd  call    RasTapiTrace
0x180013de2  test    ebx, ebx
0x180013de4  jnz     short loc_180013DF7
0x180013de6  lea     rcx, aFailedToOpenAs; "Failed to open asyncmac but no error!!!"
0x180013ded  call    RasTapiTrace
0x180013df2  mov     ebx, 2
0x180013df7  mov     rcx, cs:RasTapiMutex; hMutex
0x180013dfe  call    cs:__imp_ReleaseMutex
0x180013e04  test    eax, eax
0x180013e06  jnz     loc_1800141FC
0x180013e0c  call    cs:__imp_GetLastError
0x180013e12  jmp     loc_1800141FC
0x180013e17  mov     rcx, [rdi+0D8h]
0x180013e1e  xor     ebp, ebp
0x180013e20  mov     rax, [rcx+28h]
0x180013e24  lea     ebx, [rbp+2]
0x180013e27  lea     r10d, [rbp+1]
0x180013e2b  mov     eax, [rax+60h]
0x180013e2e  movzx   eax, ax
0x180013e31  cmp     eax, 8
0x180013e34  jz      short loc_180013E3E
0x180013e36  add     eax, 0FFFFFFF2h
0x180013e39  cmp     eax, r10d
0x180013e3c  ja      short loc_180013E49
0x180013e3e  test    [rsp+498h+arg_20], bl
0x180013e45  cmovnz  ebp, r10d
0x180013e49  cmp     dword ptr [rcx+10h], 0
0x180013e4d  jnz     loc_18001404B
0x180013e53  cmp     dword ptr [rcx+3Ch], 0
0x180013e57  jnz     short loc_180013E98
0x180013e59  mov     [rsp+498h+LineDevCaps.dwTotalSize], 190h
0x180013e61  lea     rax, [rsp+498h+LineDevCaps]
0x180013e66  mov     r9d, [rcx+1Ch]; dwExtVersion
0x180013e6a  mov     r8d, [rcx+18h]; dwAPIVersion
0x180013e6e  mov     edx, [rcx+8]; dwDeviceID
0x180013e71  mov     ecx, cs:RasLine; hLineApp
0x180013e77  mov     [rsp+498h+lpLineDevCaps], rax; lpLineDevCaps
0x180013e7c  call    cs:__imp_lineGetDevCapsA
0x180013e82  mov     ecx, [rsp+498h+LineDevCaps.dwMediaModes]
0x180013e89  mov     rax, [rdi+0D8h]
0x180013e90  and     ecx, 0FFFFFFF3h
0x180013e93  mov     [rax+38h], ecx
0x180013e96  jmp     short loc_180013E9F
0x180013e98  mov     dword ptr [rcx+38h], 102h
0x180013e9f  test    ebp, ebp
0x180013ea1  jz      short loc_180013EC8
0x180013ea3  lea     rcx, aOpeningLineInM; "Opening line in monitor mode"
0x180013eaa  mov     esi, ebx
0x180013eac  call    RasTapiTrace
0x180013eb1  mov     rax, [rdi+0D8h]
0x180013eb8  or      dword ptr [rax+30h], 1
0x180013ebc  mov     rax, [rdi+0D8h]
0x180013ec3  inc     dword ptr [rax+34h]
0x180013ec6  jmp     short loc_180013EEF
0x180013ec8  lea     rcx, aOpeningLineInO; "Opening line in owner mode"
0x180013ecf  call    RasTapiTrace
0x180013ed4  mov     rax, [rdi+0D8h]
0x180013edb  mov     esi, 4
0x180013ee0  and     dword ptr [rax+30h], 0FFFFFFFEh
0x180013ee4  mov     rax, [rdi+0D8h]
0x180013eeb  and     dword ptr [rax+30h], 0FFFFFFFDh
0x180013eef  mov     rcx, [rdi+0D8h]
0x180013ef6  cmp     dword ptr [rcx+3Ch], 0
0x180013efa  lea     rdx, [rcx+0Ch]
0x180013efe  mov     r8d, [rcx+38h]
0x180013f02  jnz     short loc_180013F3A
0x180013f04  mov     eax, [rcx+1Ch]
0x180013f07  mov     r9d, [rcx+18h]; dwAPIVersion
0x180013f0b  mov     [rsp+498h+lpCallParams], 0; lpCallParams
0x180013f14  mov     [rsp+498h+dwMediaModes], r8d; dwMediaModes
0x180013f19  mov     r8, rdx; lphLine
0x180013f1c  mov     edx, [rcx+8]; dwDeviceID
0x180013f1f  mov     [rsp+498h+dwPrivileges], esi; dwPrivileges
0x180013f23  mov     [rsp+498h+dwCallbackInstance], rcx; dwCallbackInstance
0x180013f28  mov     ecx, cs:RasLine; hLineApp
0x180013f2e  mov     dword ptr [rsp+498h+lpLineDevCaps], eax; dwExtVersion
0x180013f32  call    cs:__imp_lineOpenA
0x180013f38  jmp     short loc_180013F4C
0x180013f3a  mov     [rsp+498h+lpLineDevCaps], rdx
0x180013f3f  mov     r9, rcx
0x180013f42  mov     ecx, [rcx+8]
0x180013f45  mov     edx, esi
0x180013f47  call    RasLineOpen
0x180013f4c  mov     esi, eax
0x180013f4e  test    eax, eax
0x180013f50  jz      short loc_180013F89
0x180013f52  mov     edx, eax
0x180013f54  lea     rcx, aPortopenLineop; "PortOpen: lineOpen Failed. 0x%x"
0x180013f5b  call    RasTapiTrace
0x180013f60  mov     rax, [rdi+0D8h]
0x180013f67  mov     rcx, cs:RasTapiMutex; hMutex
0x180013f6e  and     dword ptr [rax+30h], 0FFFFFFFEh
0x180013f72  call    cs:__imp_ReleaseMutex
0x180013f78  test    eax, eax
0x180013f7a  jnz     short loc_180013F82
0x180013f7c  call    cs:__imp_GetLastError
0x180013f82  mov     ebx, esi
0x180013f84  jmp     loc_1800141FC
0x180013f89  mov     rcx, [rdi+0D8h]
0x180013f90  cmp     dword ptr [rcx+3Ch], 0
0x180013f94  jnz     short loc_180013FA4
0x180013f96  mov     ecx, [rcx+0Ch]; hLine
0x180013f99  xor     r8d, r8d; dwAddressStates
0x180013f9c  mov     edx, ebx; dwLineStates
0x180013f9e  call    cs:__imp_lineSetStatusMessages
0x180013fa4  lea     rdx, aModem; "MODEM"
0x180013fab  lea     rcx, [rdi+40h]; String1
0x180013faf  call    cs:__imp__stricmp
0x180013fb5  xor     r15d, r15d
0x180013fb8  test    eax, eax
0x180013fba  jnz     short loc_180014033
0x180013fbc  mov     rcx, [rdi+0D8h]
0x180013fc3  lea     r8, SubStr; "comm/datamodem"
0x180013fca  mov     [rsp+498h+LineDevCaps.dwTotalSize], 3E8h
0x180013fd2  lea     rdx, [rsp+498h+LineDevCaps]; lpDeviceConfig
0x180013fd7  mov     [rsp+498h+LineDevCaps.dwProviderInfoOffset], r15d
0x180013fdc  mov     ecx, [rcx+8]; dwDeviceID
0x180013fdf  call    cs:__imp_lineGetDevConfigA
0x180013fe5  mov     eax, [rsp+498h+LineDevCaps.dwSwitchInfoSize]
0x180013fe9  lea     rdx, [rsp+498h+LineDevCaps]
0x180013fee  add     rdx, rax; lpDeviceConfig
0x180013ff1  cmp     eax, 3DCh
0x180013ff6  ja      short loc_180014001
0x180013ff8  mov     eax, 0FFF7h
0x180013ffd  and     [rdx+8], ax
0x180014001  mov     rcx, [rdi+0D8h]
0x180014008  lea     r9, SubStr; "comm/datamodem"
0x18001400f  mov     r8d, [rsp+498h+LineDevCaps.dwProviderInfoOffset]; dwSize
0x180014014  mov     ecx, [rcx+8]; dwDeviceID
0x180014017  call    cs:__imp_lineSetDevConfigA
0x18001401d  mov     rcx, rdi
0x180014020  call    DwEnableModemDiagnostics
0x180014025  mov     edx, eax
0x180014027  lea     rcx, aDwenablemodemd_0; "DwEnableModemDiagnostics returned 0x%x"
0x18001402e  call    RasTapiTrace
0x180014033  mov     rax, [rdi+0D8h]
0x18001403a  mov     r10d, 1
0x180014040  mov     rsi, [rsp+498h+var_448]
0x180014045  mov     [rax+10h], r10d
0x180014049  jmp     short loc_18001404E
0x18001404b  xor     r15d, r15d
0x18001404e  lea     rcx, [rdi+168h]
0x180014055  mov     [rdi+104h], r15b
0x18001405c  mov     [rcx], r15b
0x18001405f  lea     r8, a64000; "64000"
0x180014066  mov     [rdi+1CCh], r15b
0x18001406d  mov     eax, 7FFFFFFEh
0x180014072  mov     [rdi+230h], r15b
0x180014079  mov     edx, 64h ; 'd'
0x18001407e  mov     [rdi+294h], r15b
0x180014085  test    rax, rax
0x180014088  jz      short loc_1800140A3
0x18001408a  mov     r9b, [r8]
0x18001408d  test    r9b, r9b
0x180014090  jz      short loc_1800140A3
0x180014092  mov     [rcx], r9b
0x180014095  add     r8, r10
0x180014098  add     rcx, r10
0x18001409b  sub     rax, r10
0x18001409e  sub     rdx, r10
0x1800140a1  jnz     short loc_180014085
0x1800140a3  test    rdx, rdx
0x1800140a6  lea     rax, [rcx-1]
0x1800140aa  cmovnz  rax, rcx
0x1800140ae  mov     [rax], r15b
0x1800140b1  mov     rax, [rdi+0D8h]
0x1800140b8  add     [rax+14h], r10d
0x1800140bc  mov     rax, [rdi+0D8h]
0x1800140c3  mov     [rdi+38h], r10d
0x1800140c7  mov     [rdi+444h], r15d
0x1800140ce  mov     qword ptr [rdi+378h], 0FFFFFFFFFFFFFFFFh
0x1800140d9  mov     [rdi+0F0h], rsi
0x1800140e0  mov     [rdi+0F8h], r13d
0x1800140e7  cmp     [rax+20h], r15d
0x1800140eb  jz      loc_180014197
0x1800140f1  or      eax, 0FFFFFFFFh
0x1800140f4  mov     [rdi+4A8h], r15d
0x1800140fb  mov     [rdi+470h], eax
0x180014101  mov     [rdi+460h], eax
0x180014107  cmp     [rdi+490h], r15
0x18001410e  jnz     loc_180014197
0x180014114  mov     edx, 5F0h; uBytes
0x180014119  mov     ecx, 40h ; '@'; uFlags
0x18001411e  call    cs:__imp_LocalAlloc
0x180014124  mov     [rdi+490h], rax
0x18001412b  test    rax, rax
0x18001412e  jnz     short loc_180014170
0x180014130  mov     ebx, [rdi+38h]
0x180014133  call    cs:__imp_GetLastError
0x180014139  mov     r9d, ebx
0x18001413c  lea     r8, [rdi+18h]
0x180014140  mov     edx, eax
0x180014142  lea     rcx, aPortopenLocala; "PortOpen: LocalAlloc Failed. %d, port %"...
0x180014149  call    RasTapiTrace
0x18001414e  mov     rcx, cs:RasTapiMutex; hMutex
0x180014155  call    cs:__imp_ReleaseMutex
0x18001415b  test    eax, eax
0x18001415d  jnz     short loc_180014165
0x18001415f  call    cs:__imp_GetLastError
0x180014165  call    cs:__imp_GetLastError
0x18001416b  jmp     loc_18001420A
0x180014170  mov     [rax], r15d
0x180014173  mov     rax, [rdi+490h]
0x18001417a  mov     [rax+8], r15d
0x18001417e  mov     rax, [rdi+490h]
0x180014185  mov     [rax+4], r15d
0x180014189  mov     rax, [rdi+490h]
0x180014190  mov     dword ptr [rax+0Ch], 5DCh
0x180014197  mov     [r12], rdi
0x18001419b  test    ebp, ebp
0x18001419d  jz      short loc_1800141A6
0x18001419f  or      dword ptr [rdi+450h], 10h
0x1800141a6  mov     rcx, cs:RasTapiMutex; hMutex
0x1800141ad  call    cs:__imp_ReleaseMutex
0x1800141b3  test    eax, eax
0x1800141b5  jnz     short loc_1800141BD
0x1800141b7  call    cs:__imp_GetLastError
0x1800141bd  mov     rdx, r14
0x1800141c0  lea     rcx, aPortopenSucces; "PortOpen: successfully opened %s"
0x1800141c7  call    RasTapiTrace
0x1800141cc  mov     ebx, r15d
0x1800141cf  jmp     short loc_1800141FC
0x1800141d1  mov     rdx, r14
0x1800141d4  lea     rcx, aPortopenPortSN; "PortOpen: Port %s not found"
0x1800141db  call    RasTapiTrace
0x1800141e0  mov     rcx, cs:RasTapiMutex; hMutex
0x1800141e7  call    cs:__imp_ReleaseMutex
0x1800141ed  test    eax, eax
0x1800141ef  jnz     short loc_1800141F7
0x1800141f1  call    cs:__imp_GetLastError
0x1800141f7  mov     ebx, 299h
0x1800141fc  lea     rcx, asc_18002C0B8; " "
  ... truncated ...
```
