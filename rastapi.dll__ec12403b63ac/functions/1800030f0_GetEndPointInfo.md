# GetEndPointInfo

- ea: `0x1800030f0`
- end: `0x1800033c7`
- name: `GetEndPointInfo`
- size: `727`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18000de88`
- `0x18000f670`

## callees

- `0x180003088`
- `0x1800030f0`
- `0x18000c7ec`
- `0x18000d92c`
- `0x18000d98c`
- `0x18000da3c`
- `0x18000dad8`
- `0x18000db80`
- `0x180016b30`
- `0x180016d40`
- `0x1800173a4`
- `0x180020b58`
- `0x1800292b0`

## import_xrefs

- `msvcrt!_stricmp` at `0x180003241`
- `msvcrt!_stricmp` at `0x180003241`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003155`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003155`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003393`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003393`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003163`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003163`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800031fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800031fc`

## string_xrefs

- `0x18000313a`: `GetEndPointInfo: Device already present`

## pseudocode

```c
__int64 __fastcall GetEndPointInfo(__int64 *a1, char *a2, int a3, unsigned int a4)
{
  __int64 DeviceInfo; // rdi
  unsigned int SetInfo; // ebx
  HLOCAL v10; // rax
  unsigned int RegKeyFromGuid; // eax
  HKEY v12; // rsi
  DWORD v13; // r8d
  unsigned int SetMaxEndPoints; // eax
  bool v15; // zf
  const char *v16; // rsi
  size_t v17; // rdx
  _BYTE *v18; // rax
  __int64 v19; // r8
  __int64 v20; // r9
  char *v21; // r8
  __int64 v22; // rax
  _BYTE *v23; // rcx
  __int64 v24; // rdx
  _BYTE *v25; // rax
  unsigned int v27; // [rsp+20h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+28h] [rbp-C0h] BYREF
  char pszDest[48]; // [rsp+30h] [rbp-B8h] BYREF
  wchar_t pszSrc[40]; // [rsp+60h] [rbp-88h] BYREF

  if ( !a3 )
  {
    DeviceInfo = GetDeviceInfo(a2);
    if ( DeviceInfo )
    {
      SetInfo = 0;
      RasTapiTrace("GetEndPointInfo: Device already present");
      goto LABEL_37;
    }
  }
  v10 = LocalAlloc(0x40u, 0x208u);
  DeviceInfo = (__int64)v10;
  if ( v10 )
  {
    MapNdiswanDTtoRasDT(v10, a4);
    hKey = 0;
    v27 = 0;
    RegKeyFromGuid = lrGetRegKeyFromGuid((WCHAR *)a2, &hKey, &v27, 0);
    v12 = hKey;
    SetInfo = RegKeyFromGuid;
    if ( !RegKeyFromGuid )
    {
      SetInfo = lrGetSetInfo(hKey, (struct DeviceInfo *)DeviceInfo);
      if ( !SetInfo )
      {
        SetMaxEndPoints = lrGetSetMaxEndPoints((LPBYTE)(DeviceInfo + 80), (LPBYTE)(DeviceInfo + 84), v13);
        v15 = *(_QWORD *)(DeviceInfo + 40) == 0;
        SetInfo = SetMaxEndPoints;
        *(_DWORD *)(DeviceInfo + 20) = v27;
        if ( v15 )
          SetInfo = DwGetCalledIdInfo(v12, DeviceInfo);
      }
    }
    if ( v12 )
      RegCloseKey(v12);
    if ( SetInfo )
    {
      RasTapiTrace("GetEndPpointInfo: DwGetEndPointInfo failed. 0x%x");
LABEL_36:
      LocalFree((HLOCAL)DeviceInfo);
      DeviceInfo = 0;
      goto LABEL_37;
    }
    v16 = (const char *)g_pDeviceInfoList;
    *(_DWORD *)(DeviceInfo + 8) = 1;
    if ( v16 )
    {
      while ( _stricmp(v16 + 133, (const char *)(DeviceInfo + 133)) )
      {
        v16 = *(const char **)v16;
        if ( !v16 )
          goto LABEL_32;
      }
      RasTapiTrace("GetEndPointInfo: found another device with the same name %s");
      StringCchPrintfA(pszDest, 0x28u, " (%d)", *(_DWORD *)(DeviceInfo + 20));
      StringCchPrintfW(pszSrc, 0x28u, L" (%d)", *(unsigned int *)(DeviceInfo + 20));
      v17 = 129;
      v18 = (_BYTE *)(DeviceInfo + 133);
      v19 = 129;
      do
      {
        if ( !*v18 )
          break;
        ++v18;
        --v19;
      }
      while ( v19 );
      SetInfo = v19 == 0 ? 0x80070057 : 0;
      v20 = (129 - v19) & -(__int64)(v19 != 0);
      if ( v19 )
      {
        v21 = pszDest;
        v22 = 2147483646;
        v23 = (_BYTE *)(DeviceInfo + 133 + v20);
        v24 = 129 - v20;
        if ( 129 != v20 )
        {
          do
          {
            if ( !v22 )
              break;
            if ( !*v21 )
              break;
            *v23++ = *v21++;
            --v22;
            --v24;
          }
          while ( v24 );
        }
        v25 = v23 - 1;
        if ( v24 )
          v25 = v23;
        v17 = -v24;
        SetInfo = v17 == 0 ? 0x8007007A : 0;
        *v25 = 0;
      }
      if ( SetInfo )
        goto LABEL_36;
      SetInfo = StringCchCatW((STRSAFE_LPWSTR)(DeviceInfo + 262), v17, pszSrc);
      if ( SetInfo )
        goto LABEL_36;
      RasTapiTrace("New DeviceName=%s");
      RasTapiTrace("New WDeviceName=%s");
    }
LABEL_32:
    if ( !a3 )
    {
      *(_QWORD *)DeviceInfo = g_pDeviceInfoList;
      g_pDeviceInfoList = (HLOCAL)DeviceInfo;
      TraceEndPointInfo(DeviceInfo);
    }
  }
  else
  {
    SetInfo = GetLastError();
    RasTapiTrace("GetEndPointInfo: Failed to alloc. %d");
  }
  if ( SetInfo && DeviceInfo )
    goto LABEL_36;
LABEL_37:
  *a1 = DeviceInfo;
  return SetInfo;
}

```

## disassembly

```asm
0x1800030f0  mov     [rsp+arg_10], rbx
0x1800030f5  push    rbp
0x1800030f6  push    rsi
0x1800030f7  push    rdi
0x1800030f8  push    r14
0x1800030fa  push    r15
0x1800030fc  sub     rsp, 0C0h
0x180003103  mov     rax, cs:__security_cookie
0x18000310a  xor     rax, rsp
0x18000310d  mov     [rsp+0E8h+var_38], rax
0x180003115  mov     esi, r9d
0x180003118  mov     ebp, r8d
0x18000311b  mov     rbx, rdx
0x18000311e  mov     r15, rcx
0x180003121  test    r8d, r8d
0x180003124  jnz     short loc_18000314B
0x180003126  xor     edx, edx
0x180003128  mov     rcx, rbx; String1
0x18000312b  call    GetDeviceInfo
0x180003130  mov     rdi, rax
0x180003133  test    rax, rax
0x180003136  jz      short loc_18000314B
0x180003138  xor     ebx, ebx
0x18000313a  lea     rcx, aGetendpointinf; "GetEndPointInfo: Device already present"
0x180003141  call    RasTapiTrace
0x180003146  jmp     loc_18000339B
0x18000314b  mov     edx, 208h; uBytes
0x180003150  mov     ecx, 40h ; '@'; uFlags
0x180003155  call    cs:__imp_LocalAlloc
0x18000315b  mov     rdi, rax
0x18000315e  test    rax, rax
0x180003161  jnz     short loc_18000317E
0x180003163  call    cs:__imp_GetLastError
0x180003169  mov     edx, eax
0x18000316b  lea     rcx, aGetendpointinf_0; "GetEndPointInfo: Failed to alloc. %d"
0x180003172  mov     ebx, eax
0x180003174  call    RasTapiTrace
0x180003179  jmp     loc_180003387
0x18000317e  mov     edx, esi
0x180003180  mov     rcx, rdi
0x180003183  call    MapNdiswanDTtoRasDT
0x180003188  lea     rdx, [rsp+0E8h+hKey]; HKEY *
0x18000318d  mov     [rsp+0E8h+hKey], 0
0x180003196  xor     r9d, r9d; int
0x180003199  mov     [rsp+0E8h+var_C8], 0
0x1800031a1  lea     r8, [rsp+0E8h+var_C8]; unsigned int *
0x1800031a6  mov     rcx, rbx; unsigned __int8 *
0x1800031a9  call    ?lrGetRegKeyFromGuid@@YAJPEAEPEAPEAUHKEY__@@PEAKH@Z; lrGetRegKeyFromGuid(uchar *,HKEY__ * *,ulong *,int)
0x1800031ae  mov     rsi, [rsp+0E8h+hKey]
0x1800031b3  mov     ebx, eax
0x1800031b5  test    eax, eax
0x1800031b7  jnz     short loc_1800031F4
0x1800031b9  mov     rdx, rdi; struct DeviceInfo *
0x1800031bc  mov     rcx, rsi; hKey
0x1800031bf  call    ?lrGetSetInfo@@YAJPEAUHKEY__@@PEAUDeviceInfo@@H@Z; lrGetSetInfo(HKEY__ *,DeviceInfo *,int)
0x1800031c4  mov     ebx, eax
0x1800031c6  test    eax, eax
0x1800031c8  jnz     short loc_1800031F4
0x1800031ca  lea     rdx, [rdi+54h]; LPBYTE
0x1800031ce  lea     rcx, [rdi+50h]; lpData
0x1800031d2  call    lrGetSetMaxEndPoints
0x1800031d7  cmp     qword ptr [rdi+28h], 0
0x1800031dc  mov     ebx, eax
0x1800031de  mov     eax, [rsp+0E8h+var_C8]
0x1800031e2  mov     [rdi+14h], eax
0x1800031e5  jnz     short loc_1800031F4
0x1800031e7  mov     rdx, rdi
0x1800031ea  mov     rcx, rsi; hKey
0x1800031ed  call    DwGetCalledIdInfo
0x1800031f2  mov     ebx, eax
0x1800031f4  test    rsi, rsi
0x1800031f7  jz      short loc_180003202
0x1800031f9  mov     rcx, rsi; hKey
0x1800031fc  call    cs:__imp_RegCloseKey
0x180003202  test    ebx, ebx
0x180003204  jz      short loc_180003219
0x180003206  mov     edx, ebx
0x180003208  lea     rcx, aGetendppointin; "GetEndPpointInfo: DwGetEndPointInfo fai"...
0x18000320f  call    RasTapiTrace
0x180003214  jmp     loc_180003390
0x180003219  mov     rsi, cs:g_pDeviceInfoList
0x180003220  mov     dword ptr [rdi+8], 1
0x180003227  test    rsi, rsi
0x18000322a  jz      loc_18000336A
0x180003230  lea     r14, [rdi+85h]
0x180003237  lea     rcx, [rsi+85h]; String1
0x18000323e  mov     rdx, r14; String2
0x180003241  call    cs:__imp__stricmp
0x180003247  test    eax, eax
0x180003249  jz      short loc_180003258
0x18000324b  mov     rsi, [rsi]
0x18000324e  test    rsi, rsi
0x180003251  jnz     short loc_180003237
0x180003253  jmp     loc_18000336A
0x180003258  mov     rdx, r14
0x18000325b  lea     rcx, aGetendpointinf_1; "GetEndPointInfo: found another device w"...
0x180003262  call    RasTapiTrace
0x180003267  test    rsi, rsi
0x18000326a  jz      loc_18000336A
0x180003270  mov     r9d, [rdi+14h]
0x180003274  lea     r8, pszFormat; " (%d)"
0x18000327b  mov     ebx, 28h ; '('
0x180003280  lea     rcx, [rsp+0E8h+pszDest]; pszDest
0x180003285  mov     edx, ebx; cchDest
0x180003287  call    StringCchPrintfA
0x18000328c  mov     r9d, [rdi+14h]
0x180003290  lea     r8, aD; " (%d)"
0x180003297  mov     edx, ebx; cchDest
0x180003299  lea     rcx, [rsp+0E8h+pszSrc]; pszDest
0x18000329e  call    StringCchPrintfW
0x1800032a3  lea     edx, [rbx+59h]
0x1800032a6  mov     rax, r14
0x1800032a9  mov     r8d, edx
0x1800032ac  cmp     byte ptr [rax], 0
0x1800032af  jz      short loc_1800032BA
0x1800032b1  inc     rax
0x1800032b4  sub     r8, 1
0x1800032b8  jnz     short loc_1800032AC
0x1800032ba  mov     rax, r8
0x1800032bd  mov     rcx, rdx
0x1800032c0  neg     rax
0x1800032c3  mov     rax, r8
0x1800032c6  sbb     ebx, ebx
0x1800032c8  sub     rcx, r8
0x1800032cb  not     ebx
0x1800032cd  and     ebx, 80070057h
0x1800032d3  neg     rax
0x1800032d6  sbb     r9, r9
0x1800032d9  and     r9, rcx
0x1800032dc  test    r8, r8
0x1800032df  jz      short loc_18000332E
0x1800032e1  lea     r8, [rsp+0E8h+pszDest]
0x1800032e6  mov     eax, 7FFFFFFEh
0x1800032eb  lea     rcx, [r14+r9]
0x1800032ef  sub     rdx, r9
0x1800032f2  jz      short loc_180003313
0x1800032f4  test    rax, rax
0x1800032f7  jz      short loc_180003313
0x1800032f9  mov     r9b, [r8]
0x1800032fc  test    r9b, r9b
0x1800032ff  jz      short loc_180003313
0x180003301  mov     [rcx], r9b
0x180003304  inc     r8
0x180003307  inc     rcx
0x18000330a  dec     rax
0x18000330d  sub     rdx, 1
0x180003311  jnz     short loc_1800032F4
0x180003313  test    rdx, rdx
0x180003316  lea     rax, [rcx-1]
0x18000331a  cmovnz  rax, rcx
0x18000331e  neg     rdx; cchDest
0x180003321  sbb     ebx, ebx
0x180003323  not     ebx
0x180003325  and     ebx, 8007007Ah
0x18000332b  mov     byte ptr [rax], 0
0x18000332e  test    ebx, ebx
0x180003330  jnz     short loc_180003390
0x180003332  lea     rsi, [rdi+106h]
0x180003339  mov     rcx, rsi; pszDest
0x18000333c  lea     r8, [rsp+0E8h+pszSrc]; pszSrc
0x180003341  call    StringCchCatW
0x180003346  mov     ebx, eax
0x180003348  test    eax, eax
0x18000334a  jnz     short loc_180003390
0x18000334c  mov     rdx, r14
0x18000334f  lea     rcx, aNewDevicenameS; "New DeviceName=%s"
0x180003356  call    RasTapiTrace
0x18000335b  mov     rdx, rsi
0x18000335e  lea     rcx, aNewWdevicename; "New WDeviceName=%s"
0x180003365  call    RasTapiTrace
0x18000336a  test    ebp, ebp
0x18000336c  jnz     short loc_180003387
0x18000336e  mov     rax, cs:g_pDeviceInfoList
0x180003375  mov     rcx, rdi
0x180003378  mov     [rdi], rax
0x18000337b  mov     cs:g_pDeviceInfoList, rdi
0x180003382  call    TraceEndPointInfo
0x180003387  test    ebx, ebx
0x180003389  jz      short loc_18000339B
0x18000338b  test    rdi, rdi
0x18000338e  jz      short loc_18000339B
0x180003390  mov     rcx, rdi; hMem
0x180003393  call    cs:__imp_LocalFree
0x180003399  xor     edi, edi
0x18000339b  mov     [r15], rdi
0x18000339e  mov     eax, ebx
0x1800033a0  mov     rcx, [rsp+0E8h+var_38]
0x1800033a8  xor     rcx, rsp; StackCookie
0x1800033ab  call    __security_check_cookie
0x1800033b0  mov     rbx, [rsp+0E8h+arg_10]
0x1800033b8  add     rsp, 0C0h
0x1800033bf  pop     r15
0x1800033c1  pop     r14
0x1800033c3  pop     rdi
0x1800033c4  pop     rsi
0x1800033c5  pop     rbp
0x1800033c6  retn
```
