# DeviceConnect

- ea: `0x18000f810`
- end: `0x18000fe77`
- name: `DeviceConnect`
- size: `1639`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000d92c`
- `0x18000f810`
- `0x180012340`
- `0x180012f20`
- `0x180015004`
- `0x1800150f8`
- `0x1800151b4`
- `0x1800257e4`
- `0x180029266`
- `0x18002927e`
- `0x1800292b0`

## import_xrefs

- `msvcrt!_stricmp` at `0x18000f8e9`
- `msvcrt!_stricmp` at `0x18000fabe`
- `msvcrt!_stricmp` at `0x18000fae2`
- `msvcrt!_stricmp` at `0x18000fbe3`
- `msvcrt!_stricmp` at `0x18000fbf7`
- `msvcrt!_stricmp` at `0x18000fc0b`
- `msvcrt!_stricmp` at `0x18000fc2f`
- `msvcrt!_stricmp` at `0x18000fce3`
- `msvcrt!_stricmp` at `0x18000f8e9`
- `msvcrt!_stricmp` at `0x18000fabe`
- `msvcrt!_stricmp` at `0x18000fae2`
- `msvcrt!_stricmp` at `0x18000fbe3`
- `msvcrt!_stricmp` at `0x18000fbf7`
- `msvcrt!_stricmp` at `0x18000fc0b`
- `msvcrt!_stricmp` at `0x18000fc2f`
- `msvcrt!_stricmp` at `0x18000fce3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f941`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f9ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f941`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f9ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f928`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fda4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fe32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f928`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fda4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fe32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f8b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fdbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f8b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fdbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f8ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f9fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000fdb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000fe15`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f8ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f9fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000fdb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000fe15`
- `ext-ms-win-ras-tapi32-l1-1-1!lineSetDevConfigA` at `0x18000f998`
- `ext-ms-win-ras-tapi32-l1-1-1!lineSetDevConfigA` at `0x18000f998`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetDevConfigA` at `0x18000f916`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetDevConfigA` at `0x18000f916`
- `ext-ms-win-ras-tapi32-l1-1-1!lineMakeCallA` at `0x18000fd2e`
- `ext-ms-win-ras-tapi32-l1-1-1!lineMakeCallA` at `0x18000fd2e`

## string_xrefs

- `0x18000f8fc`: `comm/datamodem`
- `0x18000f97d`: `comm/datamodem`
- `0x18000f892`: `DeviceConnect: Device %s is not in PS_OPEN state state = %d`
- `0x18000f9e8`: `DeviceConnect: Underflow detected trying to compute the memory for device info: %d bytes`

## pseudocode

```c
__int64 DeviceConnect()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // rdi
  __int64 v3; // r8
  __int64 v4; // r9
  unsigned int v6; // r14d
  void *v7; // rcx
  HLOCAL v8; // rax
  unsigned int v9; // edx
  struct varstring_tag *lpCallParams; // rbx
  const CHAR *v11; // rcx
  DWORD *p_dwStringFormat; // r8
  __int64 v13; // r13
  unsigned __int64 v14; // rcx
  __int64 v15; // rax
  _BYTE *v16; // r9
  DWORD *v17; // rdx
  DWORD *v18; // rax
  __int64 v19; // r15
  __int64 v20; // rax
  _BYTE *v21; // rsi
  _BYTE *v22; // r8
  unsigned __int64 v23; // rcx
  __int64 v24; // rax
  _BYTE *v25; // rdx
  _BYTE *v26; // rax
  __int64 v27; // rax
  _BYTE *v28; // r8
  unsigned __int64 v29; // rcx
  _BYTE *v30; // rdx
  _BYTE *v31; // rax
  int v32; // eax
  LONG *v33; // rsi
  __int64 v34; // rax
  __int64 v35; // rcx
  int v36; // r14d
  unsigned int v37; // ebx
  struct varstring_tag DeviceConfig; // [rsp+40h] [rbp-C0h] BYREF

  v2 = LookUpControlBlock();
  if ( !v2 )
  {
    RasTapiTrace("DeviceConnect: %s not found");
    return 615;
  }
  GetMutex(v1, v0, v3, v4);
  if ( *(_DWORD *)(v2 + 56) != 1 )
  {
    RasTapiTrace("DeviceConnect: Device %s is not in PS_OPEN state state = %d");
    if ( !ReleaseMutex(RasTapiMutex) )
      GetLastError();
    return 633;
  }
  v6 = 2000;
  if ( *(_QWORD *)(v2 + 1064) && !_stricmp((const char *)(v2 + 64), "MODEM") )
  {
    DeviceConfig.dwTotalSize = 2000;
    DeviceConfig.dwStringSize = 0;
    lineGetDevConfigA(*(_DWORD *)(*(_QWORD *)(v2 + 216) + 8LL), &DeviceConfig, "comm/datamodem");
    v7 = *(void **)(v2 + 1080);
    if ( v7 )
    {
      LocalFree(v7);
      *(_QWORD *)(v2 + 1080) = 0;
    }
    *(_DWORD *)(v2 + 1088) = 0;
    v8 = LocalAlloc(0x40u, DeviceConfig.dwStringSize);
    *(_QWORD *)(v2 + 1080) = v8;
    if ( v8 )
    {
      *(_DWORD *)(v2 + 1088) = DeviceConfig.dwStringSize;
      memcpy_0(v8, (char *)&DeviceConfig + DeviceConfig.dwStringOffset, DeviceConfig.dwStringSize);
    }
    lineSetDevConfigA(
      *(_DWORD *)(*(_QWORD *)(v2 + 216) + 8LL),
      (const LPVOID)(*(_QWORD *)(v2 + 1064) + **(unsigned int **)(v2 + 1064)),
      *(_DWORD *)(*(_QWORD *)(v2 + 1064) + 4LL),
      "comm/datamodem");
  }
  if ( *(_QWORD *)(v2 + 864) )
  {
    v9 = *(_DWORD *)(v2 + 872);
    v6 = v9 + 2008;
    if ( v9 >= 0xFFFFF828 )
    {
      v11 = "DeviceConnect: Underflow detected trying to compute the memory for device info: %d bytes";
      goto LABEL_19;
    }
    RasTapiTrace("DeviceConnect: DevSpecificInfo of %d bytes available. Allocating new memory...");
    lpCallParams = (struct varstring_tag *)LocalAlloc(0x40u, v6);
    if ( !lpCallParams )
    {
      v11 = "DeviceConnection: Insufficient memory for allocating device specific info: %d bytes";
LABEL_19:
      RasTapiTrace(v11);
      if ( !ReleaseMutex(RasTapiMutex) )
        GetLastError();
      return 8;
    }
  }
  else
  {
    lpCallParams = &DeviceConfig;
    memset_0(&DeviceConfig, 0, 0x7D0u);
  }
  p_dwStringFormat = &lpCallParams[7].dwStringFormat;
  lpCallParams->dwTotalSize = v6;
  v13 = 2147483646;
  v14 = v6 - 180;
  if ( v6 != 180 )
  {
    if ( v14 <= 0x7FFFFFFF )
    {
      v15 = 2147483646;
      v16 = (_BYTE *)(v2 + 40);
      v17 = &lpCallParams[7].dwStringFormat;
      do
      {
        if ( !v15 )
          break;
        if ( !*v16 )
          break;
        *(_BYTE *)v17 = *v16++;
        v17 = (DWORD *)((char *)v17 + 1);
        --v15;
        --v14;
      }
      while ( v14 );
      v18 = (DWORD *)((char *)v17 - 1);
      if ( v14 )
        v18 = v17;
      *(_BYTE *)v18 = 0;
    }
    else
    {
      *(_BYTE *)p_dwStringFormat = 0;
    }
  }
  v19 = -1;
  v20 = -1;
  do
    ++v20;
  while ( *((_BYTE *)p_dwStringFormat + v20) );
  lpCallParams[2].dwTotalSize = v20;
  lpCallParams[1].dwTotalSize = 2;
  lpCallParams[2].dwNeededSize = 180;
  v21 = (char *)p_dwStringFormat + (unsigned int)v20;
  if ( !_stricmp((const char *)(v2 + 64), "ISDN") )
  {
    SetIsdnParams(v2, lpCallParams);
    goto LABEL_76;
  }
  if ( !_stricmp((const char *)(v2 + 64), "X25") )
  {
    v22 = (_BYTE *)(v2 + 560);
    if ( *(_BYTE *)(v2 + 560) )
    {
      v23 = v6 + (_DWORD)lpCallParams - (_DWORD)v21;
      if ( v6 + (_DWORD)lpCallParams - (_DWORD)v21 )
      {
        if ( v23 <= 0x7FFFFFFF )
        {
          v24 = 2147483646;
          v25 = v21;
          do
          {
            if ( !v24 )
              break;
            if ( !*v22 )
              break;
            *v25++ = *v22++;
            --v24;
            --v23;
          }
          while ( v23 );
          v26 = v25 - 1;
          if ( v23 )
            v26 = v25;
          *v26 = 0;
        }
        else
        {
          *v21 = 0;
        }
      }
      v27 = -1;
      do
        ++v27;
      while ( v21[v27] );
      lpCallParams[3].dwStringFormat = (_DWORD)v21 - (_DWORD)lpCallParams;
      lpCallParams[3].dwUsedSize = v27;
      v21 += (unsigned int)v27;
    }
    v28 = (_BYTE *)(v2 + 660);
    if ( *(_BYTE *)(v2 + 660) )
    {
      v29 = v6 + (_DWORD)lpCallParams - (_DWORD)v21;
      if ( v6 + (_DWORD)lpCallParams - (_DWORD)v21 )
      {
        if ( v29 <= 0x7FFFFFFF )
        {
          v30 = v21;
          do
          {
            if ( !v13 )
              break;
            if ( !*v28 )
              break;
            *v30++ = *v28++;
            --v13;
            --v29;
          }
          while ( v29 );
          v31 = v30 - 1;
          if ( v29 )
            v31 = v30;
          *v31 = 0;
        }
        else
        {
          *v21 = 0;
        }
      }
      do
        ++v19;
      while ( v21[v19] );
      lpCallParams[4].dwUsedSize = v19;
      lpCallParams[4].dwStringFormat = (_DWORD)v21 - (_DWORD)lpCallParams;
    }
    SetX25Params(v2, lpCallParams);
  }
  else
  {
    if ( !_stricmp((const char *)(v2 + 64), "VPN") || !_stricmp((const char *)(v2 + 64), "GRE") )
    {
      if ( *(_QWORD *)(v2 + 864) )
      {
        lpCallParams[4].dwUsedSize = *(_DWORD *)(v2 + 872);
        lpCallParams[4].dwStringFormat = (_DWORD)v21 - (_DWORD)lpCallParams;
        RasTapiTrace("DeviceConnect: calling lineMakeCall with size %d and offset %d");
        memcpy_0(v21, *(const void **)(v2 + 864), *(unsigned int *)(v2 + 872));
      }
      lpCallParams->dwNeededSize = 8;
      lpCallParams->dwStringSize = 256;
    }
    else
    {
      if ( !_stricmp((const char *)(v2 + 64), "MODEM") )
      {
        SetModemParams(v2, lpCallParams);
        goto LABEL_76;
      }
      v32 = _stricmp((const char *)(v2 + 64), "ATM");
      lpCallParams->dwNeededSize = 8;
      lpCallParams->dwStringSize = 256;
      if ( !v32 )
      {
        *(_QWORD *)&lpCallParams->dwUsedSize = 0;
        goto LABEL_76;
      }
    }
    lpCallParams->dwStringFormat = 10000000;
    lpCallParams->dwUsedSize = 64000;
  }
LABEL_76:
  *(_DWORD *)(v2 + 256) = 0;
  v33 = (LONG *)(v2 + 252);
  *(_DWORD *)(v2 + 252) = -1;
  *(_DWORD *)(v2 + 232) = -1;
  if ( !_stricmp((const char *)(v2 + 64), "MODEM") )
    RasTapiTrace("DeviceConnect: calling lineMakeCall");
  else
    RasTapiTrace("DeviceConnect: calling lineMakeCall for %s, address=%s");
  v34 = *(_QWORD *)(v2 + 216);
  v35 = *(unsigned int *)(v34 + 12);
  if ( *(_DWORD *)(v34 + 60) )
  {
    v36 = RasLineMakeCall(v35, v2 + 260);
  }
  else
  {
    v36 = 0;
    *v33 = lineMakeCallA(v35, (LPHCALL)(v2 + 232), (LPCSTR)(v2 + 260), 0, (const LPLINECALLPARAMS)lpCallParams);
  }
  if ( *(_DWORD *)(*(_QWORD *)(v2 + 216) + 60LL) )
  {
    if ( !v36 )
      goto LABEL_84;
  }
  else if ( (unsigned int)*v33 <= 0x80000000 )
  {
LABEL_84:
    RasTapiTrace("DeviceConnect: Changing state for %s from %d -> %d");
    *(_DWORD *)(v2 + 56) = 4;
    *(_DWORD *)(v2 + 1092) = 0;
    if ( lpCallParams != &DeviceConfig )
      LocalFree(lpCallParams);
    if ( !ReleaseMutex(RasTapiMutex) )
      GetLastError();
    return 600;
  }
  RasTapiTrace("DeviceConnect: lineMakeCall Failed for %s. RequestId = 0x%x, Status = 0x%x");
  if ( !ReleaseMutex(RasTapiMutex) )
    GetLastError();
  if ( lpCallParams != &DeviceConfig )
    LocalFree(lpCallParams);
  if ( *v33 == -2147483633 )
  {
    RasTapiTrace("DeviceConnect: ERROR_PORT_NOT_AVAILABLE");
    v37 = 633;
  }
  else
  {
    RasTapiTrace("DeviceConnect: ERROR_FROM_DEVICE");
    v37 = 651;
  }
  RasTapiTrace(" ");
  return v37;
}

```

## disassembly

```asm
0x18000f810  mov     [rsp-8+arg_8], rbx
0x18000f815  push    rbp
0x18000f816  push    rsi
0x18000f817  push    rdi
0x18000f818  push    r12
0x18000f81a  push    r13
0x18000f81c  push    r14
0x18000f81e  push    r15
0x18000f820  lea     rbp, [rsp-720h]
0x18000f828  sub     rsp, 820h
0x18000f82f  mov     rax, cs:__security_cookie
0x18000f836  xor     rax, rsp
0x18000f839  mov     [rbp+750h+var_40], rax
0x18000f840  mov     rbx, r8
0x18000f843  call    LookUpControlBlock
0x18000f848  xor     esi, esi
0x18000f84a  mov     rdi, rax
0x18000f84d  test    rax, rax
0x18000f850  jnz     short loc_18000F879
0x18000f852  test    rbx, rbx
0x18000f855  lea     rax, aNull_0; "NULL"
0x18000f85c  lea     rcx, aDeviceconnectS; "DeviceConnect: %s not found"
0x18000f863  cmovz   rbx, rax
0x18000f867  mov     rdx, rbx
0x18000f86a  call    RasTapiTrace
0x18000f86f  mov     eax, 267h
0x18000f874  jmp     loc_18000FDC6
0x18000f879  call    GetMutex
0x18000f87e  mov     r8d, [rdi+38h]
0x18000f882  cmp     r8d, 1
0x18000f886  jz      short loc_18000F8C6
0x18000f888  lea     rax, aNull_0; "NULL"
0x18000f88f  test    rbx, rbx
0x18000f892  lea     rcx, aDeviceconnectD; "DeviceConnect: Device %s is not in PS_O"...
0x18000f899  cmovz   rbx, rax
0x18000f89d  mov     rdx, rbx
0x18000f8a0  call    RasTapiTrace
0x18000f8a5  mov     rcx, cs:RasTapiMutex; hMutex
0x18000f8ac  call    cs:__imp_ReleaseMutex
0x18000f8b2  test    eax, eax
0x18000f8b4  jnz     short loc_18000F8BC
0x18000f8b6  call    cs:__imp_GetLastError
0x18000f8bc  mov     eax, 279h
0x18000f8c1  jmp     loc_18000FDC6
0x18000f8c6  mov     ebx, 40h ; '@'
0x18000f8cb  mov     r14d, 7D0h
0x18000f8d1  cmp     [rdi+428h], rsi
0x18000f8d8  jz      loc_18000F99E
0x18000f8de  lea     rcx, [rdi+40h]; String1
0x18000f8e2  lea     rdx, aModem; "MODEM"
0x18000f8e9  call    cs:__imp__stricmp
0x18000f8ef  test    eax, eax
0x18000f8f1  jnz     loc_18000F99E
0x18000f8f7  mov     [rsp+850h+DeviceConfig.dwTotalSize], r14d
0x18000f8fc  lea     r8, SubStr; "comm/datamodem"
0x18000f903  mov     [rsp+850h+DeviceConfig.dwStringSize], esi
0x18000f907  lea     rdx, [rsp+850h+DeviceConfig]; lpDeviceConfig
0x18000f90c  mov     rcx, [rdi+0D8h]
0x18000f913  mov     ecx, [rcx+8]; dwDeviceID
0x18000f916  call    cs:__imp_lineGetDevConfigA
0x18000f91c  mov     rcx, [rdi+438h]; hMem
0x18000f923  test    rcx, rcx
0x18000f926  jz      short loc_18000F935
0x18000f928  call    cs:__imp_LocalFree
0x18000f92e  mov     [rdi+438h], rsi
0x18000f935  mov     [rdi+440h], esi
0x18000f93b  mov     ecx, ebx; uFlags
0x18000f93d  mov     edx, [rsp+850h+DeviceConfig.dwStringSize]; uBytes
0x18000f941  call    cs:__imp_LocalAlloc
0x18000f947  mov     [rdi+438h], rax
0x18000f94e  test    rax, rax
0x18000f951  jz      short loc_18000F976
0x18000f953  mov     ecx, [rsp+850h+DeviceConfig.dwStringSize]
0x18000f957  lea     rdx, [rsp+850h+DeviceConfig]
0x18000f95c  mov     [rdi+440h], ecx
0x18000f962  mov     ecx, [rsp+850h+DeviceConfig.dwStringOffset]
0x18000f966  mov     r8d, [rsp+850h+DeviceConfig.dwStringSize]; Size
0x18000f96b  add     rdx, rcx; Src
0x18000f96e  mov     rcx, rax; void *
0x18000f971  call    memcpy_0
0x18000f976  mov     r8, [rdi+428h]
0x18000f97d  lea     r9, SubStr; "comm/datamodem"
0x18000f984  mov     rcx, [rdi+0D8h]
0x18000f98b  mov     edx, [r8]
0x18000f98e  mov     ecx, [rcx+8]; dwDeviceID
0x18000f991  add     rdx, r8; lpDeviceConfig
0x18000f994  mov     r8d, [r8+4]; dwSize
0x18000f998  call    cs:__imp_lineSetDevConfigA
0x18000f99e  cmp     [rdi+360h], rsi
0x18000f9a5  jz      short loc_18000FA15
0x18000f9a7  mov     edx, [rdi+368h]
0x18000f9ad  lea     r14d, [rdx+7D8h]
0x18000f9b4  cmp     r14d, 7D8h
0x18000f9bb  jb      short loc_18000F9E8
0x18000f9bd  lea     rcx, aDeviceconnectD_0; "DeviceConnect: DevSpecificInfo of %d by"...
0x18000f9c4  call    RasTapiTrace
0x18000f9c9  mov     edx, r14d; uBytes
0x18000f9cc  mov     ecx, ebx; uFlags
0x18000f9ce  call    cs:__imp_LocalAlloc
0x18000f9d4  mov     rbx, rax
0x18000f9d7  test    rax, rax
0x18000f9da  jnz     short loc_18000FA29
0x18000f9dc  mov     edx, r14d
0x18000f9df  lea     rcx, aDeviceconnecti; "DeviceConnection: Insufficient memory f"...
0x18000f9e6  jmp     short loc_18000F9EF
0x18000f9e8  lea     rcx, aDeviceconnectU; "DeviceConnect: Underflow detected tryin"...
0x18000f9ef  call    RasTapiTrace
0x18000f9f4  mov     rcx, cs:RasTapiMutex; hMutex
0x18000f9fb  call    cs:__imp_ReleaseMutex
0x18000fa01  test    eax, eax
0x18000fa03  jnz     short loc_18000FA0B
0x18000fa05  call    cs:__imp_GetLastError
0x18000fa0b  mov     eax, 8
0x18000fa10  jmp     loc_18000FDC6
0x18000fa15  mov     r8, r14; Size
0x18000fa18  lea     rcx, [rsp+850h+DeviceConfig]; void *
0x18000fa1d  xor     edx, edx; Val
0x18000fa1f  lea     rbx, [rsp+850h+DeviceConfig]
0x18000fa24  call    memset_0
0x18000fa29  lea     r8, [rbx+0B4h]
0x18000fa30  mov     [rbx], r14d
0x18000fa33  mov     ecx, ebx
0x18000fa35  mov     r13d, 7FFFFFFEh
0x18000fa3b  sub     ecx, r8d
0x18000fa3e  add     ecx, r14d
0x18000fa41  jz      short loc_18000FA88
0x18000fa43  cmp     rcx, 7FFFFFFFh
0x18000fa4a  jbe     short loc_18000FA51
0x18000fa4c  mov     [r8], sil
0x18000fa4f  jmp     short loc_18000FA88
0x18000fa51  mov     rax, r13
0x18000fa54  lea     r9, [rdi+28h]
0x18000fa58  mov     rdx, r8
0x18000fa5b  test    rax, rax
0x18000fa5e  jz      short loc_18000FA7A
0x18000fa60  mov     r10b, [r9]
0x18000fa63  test    r10b, r10b
0x18000fa66  jz      short loc_18000FA7A
0x18000fa68  mov     [rdx], r10b
0x18000fa6b  inc     r9
0x18000fa6e  inc     rdx
0x18000fa71  dec     rax
0x18000fa74  sub     rcx, 1
0x18000fa78  jnz     short loc_18000FA5B
0x18000fa7a  test    rcx, rcx
0x18000fa7d  lea     rax, [rdx-1]
0x18000fa81  cmovnz  rax, rdx
0x18000fa85  mov     [rax], sil
0x18000fa88  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000fa8c  mov     rax, r15
0x18000fa8f  inc     rax
0x18000fa92  cmp     [r8+rax], sil
0x18000fa96  jnz     short loc_18000FA8F
0x18000fa98  mov     ecx, eax
0x18000fa9a  lea     r12, [rdi+40h]
0x18000fa9e  mov     eax, r8d
0x18000faa1  mov     [rbx+30h], ecx
0x18000faa4  sub     eax, ebx
0x18000faa6  mov     dword ptr [rbx+18h], 2
0x18000faad  lea     rdx, aIsdn; "ISDN"
0x18000fab4  mov     [rbx+34h], eax
0x18000fab7  lea     rsi, [rcx+r8]
0x18000fabb  mov     rcx, r12; String1
0x18000fabe  call    cs:__imp__stricmp
0x18000fac4  test    eax, eax
0x18000fac6  jnz     short loc_18000FAD8
0x18000fac8  mov     rdx, rbx
0x18000facb  mov     rcx, rdi
0x18000face  call    SetIsdnParams
0x18000fad3  jmp     loc_18000FCAC
0x18000fad8  lea     rdx, aX25; "X25"
0x18000fadf  mov     rcx, r12; String1
0x18000fae2  call    cs:__imp__stricmp
0x18000fae8  xor     r11d, r11d
0x18000faeb  test    eax, eax
0x18000faed  jnz     loc_18000FBD9
0x18000faf3  lea     r8, [rdi+230h]
0x18000fafa  cmp     [r8], r11b
0x18000fafd  jz      short loc_18000FB66
0x18000faff  mov     ecx, ebx
0x18000fb01  mov     r10, rsi
0x18000fb04  sub     ecx, esi
0x18000fb06  add     ecx, r14d
0x18000fb09  jz      short loc_18000FB4C
0x18000fb0b  cmp     rcx, 7FFFFFFFh
0x18000fb12  jbe     short loc_18000FB19
0x18000fb14  mov     [rsi], r11b
0x18000fb17  jmp     short loc_18000FB4C
0x18000fb19  mov     rax, r13
0x18000fb1c  mov     rdx, rsi
0x18000fb1f  test    rax, rax
0x18000fb22  jz      short loc_18000FB3E
0x18000fb24  mov     r9b, [r8]
0x18000fb27  test    r9b, r9b
0x18000fb2a  jz      short loc_18000FB3E
0x18000fb2c  mov     [rdx], r9b
0x18000fb2f  inc     r8
0x18000fb32  inc     rdx
0x18000fb35  dec     rax
0x18000fb38  sub     rcx, 1
0x18000fb3c  jnz     short loc_18000FB1F
0x18000fb3e  test    rcx, rcx
0x18000fb41  lea     rax, [rdx-1]
0x18000fb45  cmovnz  rax, rdx
0x18000fb49  mov     [rax], r11b
0x18000fb4c  mov     rax, r15
0x18000fb4f  inc     rax
0x18000fb52  cmp     [rsi+rax], r11b
0x18000fb56  jnz     short loc_18000FB4F
0x18000fb58  mov     eax, eax
0x18000fb5a  sub     esi, ebx
0x18000fb5c  mov     [rbx+54h], esi
0x18000fb5f  mov     [rbx+50h], eax
0x18000fb62  lea     rsi, [r10+rax]
0x18000fb66  lea     r8, [rdi+294h]
0x18000fb6d  cmp     [r8], r11b
0x18000fb70  jz      short loc_18000FBC9
0x18000fb72  mov     ecx, ebx
0x18000fb74  sub     ecx, esi
0x18000fb76  add     ecx, r14d
0x18000fb79  jz      short loc_18000FBB7
0x18000fb7b  cmp     rcx, 7FFFFFFFh
0x18000fb82  jbe     short loc_18000FB89
0x18000fb84  mov     [rsi], r11b
0x18000fb87  jmp     short loc_18000FBB7
0x18000fb89  mov     rdx, rsi
0x18000fb8c  test    r13, r13
0x18000fb8f  jz      short loc_18000FBA9
0x18000fb91  mov     al, [r8]
0x18000fb94  test    al, al
0x18000fb96  jz      short loc_18000FBA9
0x18000fb98  mov     [rdx], al
0x18000fb9a  inc     r8
0x18000fb9d  inc     rdx
0x18000fba0  dec     r13
0x18000fba3  sub     rcx, 1
0x18000fba7  jnz     short loc_18000FB8C
0x18000fba9  test    rcx, rcx
0x18000fbac  lea     rax, [rdx-1]
0x18000fbb0  cmovnz  rax, rdx
0x18000fbb4  mov     [rax], r11b
0x18000fbb7  inc     r15
0x18000fbba  cmp     [rsi+r15], r11b
0x18000fbbe  jnz     short loc_18000FBB7
0x18000fbc0  sub     esi, ebx
0x18000fbc2  mov     [rbx+68h], r15d
0x18000fbc6  mov     [rbx+6Ch], esi
0x18000fbc9  mov     rdx, rbx
0x18000fbcc  mov     rcx, rdi
0x18000fbcf  call    SetX25Params
0x18000fbd4  jmp     loc_18000FCAC
0x18000fbd9  lea     rdx, aVpn; "VPN"
0x18000fbe0  mov     rcx, r12; String1
0x18000fbe3  call    cs:__imp__stricmp
0x18000fbe9  test    eax, eax
0x18000fbeb  jz      short loc_18000FC51
0x18000fbed  lea     rdx, aGre; "GRE"
0x18000fbf4  mov     rcx, r12; String1
0x18000fbf7  call    cs:__imp__stricmp
0x18000fbfd  test    eax, eax
0x18000fbff  jz      short loc_18000FC51
0x18000fc01  lea     rdx, aModem; "MODEM"
0x18000fc08  mov     rcx, r12; String1
0x18000fc0b  call    cs:__imp__stricmp
0x18000fc11  test    eax, eax
0x18000fc13  jnz     short loc_18000FC25
0x18000fc15  mov     rdx, rbx
0x18000fc18  mov     rcx, rdi
0x18000fc1b  call    SetModemParams
0x18000fc20  jmp     loc_18000FCAC
0x18000fc25  lea     rdx, aAtm; "ATM"
0x18000fc2c  mov     rcx, r12; String1
0x18000fc2f  call    cs:__imp__stricmp
0x18000fc35  mov     dword ptr [rbx+4], 8
0x18000fc3c  mov     dword ptr [rbx+10h], 100h
0x18000fc43  test    eax, eax
0x18000fc45  jnz     short loc_18000FC9E
0x18000fc47  mov     qword ptr [rbx+8], 0
0x18000fc4f  jmp     short loc_18000FCAC
0x18000fc51  cmp     qword ptr [rdi+360h], 0
0x18000fc59  jz      short loc_18000FC90
0x18000fc5b  mov     edx, [rdi+368h]
0x18000fc61  lea     rcx, aDeviceconnectC; "DeviceConnect: calling lineMakeCall wit"...
0x18000fc68  mov     r8d, esi
0x18000fc6b  mov     [rbx+68h], edx
0x18000fc6e  sub     r8d, ebx
0x18000fc71  mov     [rbx+6Ch], r8d
0x18000fc75  call    RasTapiTrace
0x18000fc7a  mov     r8d, [rdi+368h]; Size
0x18000fc81  mov     rcx, rsi; void *
0x18000fc84  mov     rdx, [rdi+360h]; Src
0x18000fc8b  call    memcpy_0
0x18000fc90  mov     dword ptr [rbx+4], 8
0x18000fc97  mov     dword ptr [rbx+10h], 100h
0x18000fc9e  mov     dword ptr [rbx+0Ch], 989680h
0x18000fca5  mov     dword ptr [rbx+8], 0FA00h
0x18000fcac  or      eax, 0FFFFFFFFh
0x18000fcaf  mov     dword ptr [rdi+100h], 0
0x18000fcb9  lea     rsi, [rdi+0FCh]
0x18000fcc0  lea     r13, [rdi+0E8h]
  ... truncated ...
```
