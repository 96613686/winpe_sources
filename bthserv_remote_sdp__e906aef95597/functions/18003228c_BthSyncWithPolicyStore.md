# BthSyncWithPolicyStore

- ea: `0x18003228c`
- end: `0x180032783`
- name: `BthSyncWithPolicyStore`
- size: `1271`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800327e0`

## callees

- `0x1800026d0`
- `0x18000270c`
- `0x180031bc8`
- `0x18003228c`
- `0x18003284c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18003231a`
- `ntdll!RtlInitUnicodeString` at `0x180032364`
- `ntdll!RtlInitUnicodeString` at `0x1800323ac`
- `ntdll!RtlInitUnicodeString` at `0x1800323ed`
- `ntdll!RtlInitUnicodeString` at `0x18003242f`
- `ntdll!RtlInitUnicodeString` at `0x180032471`
- `ntdll!RtlInitUnicodeString` at `0x1800324b3`
- `ntdll!RtlInitUnicodeString` at `0x18003252d`
- `ntdll!RtlInitUnicodeString` at `0x180032599`
- `ntdll!RtlInitUnicodeString` at `0x180032601`
- `ntdll!RtlInitUnicodeString` at `0x180032644`
- `ntdll!RtlInitUnicodeString` at `0x180032687`
- `ntdll!RtlInitUnicodeString` at `0x18003231a`
- `ntdll!RtlInitUnicodeString` at `0x180032364`
- `ntdll!RtlInitUnicodeString` at `0x1800323ac`
- `ntdll!RtlInitUnicodeString` at `0x1800323ed`
- `ntdll!RtlInitUnicodeString` at `0x18003242f`
- `ntdll!RtlInitUnicodeString` at `0x180032471`
- `ntdll!RtlInitUnicodeString` at `0x1800324b3`
- `ntdll!RtlInitUnicodeString` at `0x18003252d`
- `ntdll!RtlInitUnicodeString` at `0x180032599`
- `ntdll!RtlInitUnicodeString` at `0x180032601`
- `ntdll!RtlInitUnicodeString` at `0x180032644`
- `ntdll!RtlInitUnicodeString` at `0x180032687`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800326ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800326ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032747`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032747`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800322f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800322f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003275c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003275c`

## string_xrefs

- `0x180032466`: `PM_LinkSecurityLevel`
- `0x18003258e`: `PM_ServicesAllowedList`
- `0x180032639`: `PM_AllowPrepairing`

## pseudocode

```c
__int64 BthSyncWithPolicyStore()
{
  unsigned int v1; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-19h] BYREF
  __int128 v3; // [rsp+40h] [rbp-9h] BYREF
  __m256 v4; // [rsp+50h] [rbp+7h] BYREF
  void *v5[2]; // [rsp+70h] [rbp+27h] BYREF
  __int128 v6; // [rsp+80h] [rbp+37h] BYREF
  unsigned int v7; // [rsp+B0h] [rbp+67h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+6Fh] BYREF

  hKey = 0;
  v7 = 0;
  DestinationString = 0;
  memset_0(&v3, 0, 0x50u);
  if ( !lpSubKey )
    return 3221225473LL;
  v1 = -1073741823;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey) )
  {
    v1 = 0;
    RtlInitUnicodeString(&DestinationString, L"PM_AllowBluetooth");
    if ( (int)QueryKeyValueEx(hKey, &DestinationString, 4u, &v3, 4u, 0) >= 0 && (v3 & 0xFFFFFFFD) == 0 )
      DWORD1(v6) |= 1u;
    RtlInitUnicodeString(&DestinationString, L"PM_AllowDiscoverableMode");
    if ( (int)QueryKeyValueEx(hKey, &DestinationString, 4u, (char *)&v3 + 4, 4u, 0) >= 0 && DWORD1(v3) <= 1 )
      DWORD1(v6) |= 2u;
    RtlInitUnicodeString(&DestinationString, L"PM_AllowConnectableMode");
    if ( (int)QueryKeyValueEx(hKey, &DestinationString, 4u, (char *)&v3 + 8, 4u, 0) >= 0 && DWORD2(v3) <= 1 )
      DWORD1(v6) |= 4u;
    RtlInitUnicodeString(&DestinationString, L"PM_AllowAdvertising");
    if ( (int)QueryKeyValueEx(hKey, &DestinationString, 4u, (char *)&v3 + 12, 4u, 0) >= 0 && HIDWORD(v3) <= 1 )
      DWORD1(v6) |= 8u;
    RtlInitUnicodeString(&DestinationString, L"PM_AllowOutOfBandPairing");
    if ( (int)QueryKeyValueEx(hKey, &DestinationString, 4u, &v4, 4u, 0) >= 0 && LODWORD(v4.m256_f32[0]) <= 1 )
      DWORD1(v6) |= 0x10u;
    RtlInitUnicodeString(&DestinationString, L"PM_LinkSecurityLevel");
    if ( (int)QueryKeyValueEx(hKey, &DestinationString, 4u, &v4.m256_f32[1], 4u, 0) >= 0 && LODWORD(v4.m256_f32[1]) <= 2 )
      DWORD1(v6) |= 0x20u;
    RtlInitUnicodeString(&DestinationString, L"PM_LocalDeviceName");
    if ( (int)((__int64 (__fastcall *)(HKEY, struct _UNICODE_STRING *, __int64, __int64, float *, unsigned int *))ReadVariableLengthPolicy)(
                hKey,
                &DestinationString,
                2,
                1,
                &v4.m256_f32[4],
                &v7) < 0
      || v7 > 0xFFFF )
    {
      if ( *(_QWORD *)&v4.m256_f32[4] )
      {
        free(*(void **)&v4.m256_f32[4]);
        *(_OWORD *)&v4.m256_f32[2] = 0;
      }
    }
    else
    {
      HIWORD(v4.m256_f32[2]) = v7;
      if ( (unsigned __int16)v7 >= 2u )
      {
        DWORD1(v6) |= 0x40u;
        LOWORD(v4.m256_f32[2]) = v7 - 2;
      }
    }
    RtlInitUnicodeString(&DestinationString, L"PM_DevicesAllowedList");
    if ( (int)((__int64 (__fastcall *)(HKEY, struct _UNICODE_STRING *, __int64, __int64, float *, unsigned int *))ReadVariableLengthPolicy)(
                hKey,
                &DestinationString,
                8,
                3,
                &v4.m256_f32[6],
                &v7) < 0 )
    {
      if ( *(_QWORD *)&v4.m256_f32[6] )
      {
        free(*(void **)&v4.m256_f32[6]);
        *(_QWORD *)&v4.m256_f32[6] = 0;
        DWORD2(v6) = 0;
      }
    }
    else
    {
      DWORD1(v6) |= 0x80u;
      DWORD2(v6) = v7 >> 3;
    }
    RtlInitUnicodeString(&DestinationString, L"PM_ServicesAllowedList");
    if ( (int)((__int64 (__fastcall *)(HKEY, struct _UNICODE_STRING *, __int64, __int64, void **, unsigned int *))ReadVariableLengthPolicy)(
                hKey,
                &DestinationString,
                16,
                3,
                v5,
                &v7) < 0 )
    {
      if ( v5[0] )
      {
        free(v5[0]);
        v5[0] = 0;
        HIDWORD(v6) = 0;
      }
    }
    else
    {
      DWORD1(v6) |= 0x100u;
      HIDWORD(v6) = v7 >> 4;
    }
    RtlInitUnicodeString(&DestinationString, L"PM_RequireRestrictedMode");
    if ( (int)QueryKeyValueEx(hKey, &DestinationString, 4u, &v5[1], 4u, 0) >= 0 && LODWORD(v5[1]) <= 1 )
      DWORD1(v6) |= 0x200u;
    RtlInitUnicodeString(&DestinationString, L"PM_AllowPrepairing");
    if ( (int)QueryKeyValueEx(hKey, &DestinationString, 4u, (char *)&v5[1] + 4, 4u, 0) >= 0 && HIDWORD(v5[1]) <= 1 )
      DWORD1(v6) |= 0x400u;
    RtlInitUnicodeString(&DestinationString, L"PM_SetMinimumEncryptionKeySize");
    if ( (int)QueryKeyValueEx(hKey, &DestinationString, 4u, &v6, 4u, 0) >= 0 && (unsigned int)(v6 - 1) <= 0xF )
      DWORD1(v6) |= 0x800u;
    EnterCriticalSection(&g_PolicyLock);
    if ( *(_QWORD *)&ymmword_180046F70.m256_f32[4] )
      free(*(void **)&ymmword_180046F70.m256_f32[4]);
    if ( *(_QWORD *)&ymmword_180046F70.m256_f32[6] )
      free(*(void **)&ymmword_180046F70.m256_f32[6]);
    if ( Src )
      free(Src);
    g_Policies = v3;
    ymmword_180046F70 = v4;
    *(_OWORD *)byte_180046FA0 = v6;
    *(_OWORD *)&Src = *(_OWORD *)v5;
    LeaveCriticalSection(&g_PolicyLock);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x18003228c  mov     [rsp-8+arg_10], rbx
0x180032291  mov     [rsp-8+arg_18], rsi
0x180032296  push    rbp
0x180032297  push    rdi
0x180032298  push    r15
0x18003229a  lea     rbp, [rsp-47h]
0x18003229f  sub     rsp, 90h
0x1800322a6  xor     edi, edi
0x1800322a8  lea     rcx, [rbp+57h+var_60]; void *
0x1800322ac  xorps   xmm0, xmm0
0x1800322af  mov     [rbp+57h+hKey], rdi
0x1800322b3  xor     edx, edx; Val
0x1800322b5  mov     [rbp+57h+arg_0], edi
0x1800322b8  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800322bc  lea     r8d, [rdi+50h]; Size
0x1800322c0  call    memset_0
0x1800322c5  mov     rdx, cs:lpSubKey; lpSubKey
0x1800322cc  test    rdx, rdx
0x1800322cf  jnz     short loc_1800322DB
0x1800322d1  mov     eax, 0C0000001h
0x1800322d6  jmp     loc_18003276A
0x1800322db  lea     rax, [rbp+57h+hKey]
0x1800322df  mov     r9d, 20019h; samDesired
0x1800322e5  xor     r8d, r8d; ulOptions
0x1800322e8  mov     [rsp+0A0h+phkResult], rax; phkResult
0x1800322ed  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800322f4  mov     ebx, 0C0000001h
0x1800322f9  call    cs:__imp_RegOpenKeyExW
0x180032300  nop     dword ptr [rax+rax+00h]
0x180032305  test    eax, eax
0x180032307  jnz     loc_180032753
0x18003230d  lea     rdx, aPmAllowbluetoo; "PM_AllowBluetooth"
0x180032314  mov     ebx, edi
0x180032316  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003231a  call    cs:__imp_RtlInitUnicodeString
0x180032321  nop     dword ptr [rax+rax+00h]
0x180032326  mov     rcx, [rbp+57h+hKey]; HKEY
0x18003232a  lea     r9, [rbp+57h+var_60]; void *
0x18003232e  mov     esi, 4
0x180032333  mov     [rsp+0A0h+var_78], rdi; unsigned int *
0x180032338  mov     r8d, esi; unsigned int
0x18003233b  mov     dword ptr [rsp+0A0h+phkResult], esi; unsigned int
0x18003233f  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x180032343  call    ?QueryKeyValueEx@@YAJPEAUHKEY__@@PEAU_UNICODE_STRING@@KPEAXKPEAK@Z; QueryKeyValueEx(HKEY__ *,_UNICODE_STRING *,ulong,void *,ulong,ulong *)
0x180032348  test    eax, eax
0x18003234a  js      short loc_180032359
0x18003234c  test    dword ptr [rbp+57h+var_60], 0FFFFFFFDh
0x180032353  jnz     short loc_180032359
0x180032355  or      dword ptr [rbp+57h+var_20+4], 1
0x180032359  lea     rdx, aPmAllowdiscove; "PM_AllowDiscoverableMode"
0x180032360  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180032364  call    cs:__imp_RtlInitUnicodeString
0x18003236b  nop     dword ptr [rax+rax+00h]
0x180032370  mov     rcx, [rbp+57h+hKey]; HKEY
0x180032374  lea     r9, [rbp+57h+var_60+4]; void *
0x180032378  mov     r8d, esi; unsigned int
0x18003237b  mov     [rsp+0A0h+var_78], rdi; unsigned int *
0x180032380  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x180032384  mov     dword ptr [rsp+0A0h+phkResult], esi; unsigned int
0x180032388  call    ?QueryKeyValueEx@@YAJPEAUHKEY__@@PEAU_UNICODE_STRING@@KPEAXKPEAK@Z; QueryKeyValueEx(HKEY__ *,_UNICODE_STRING *,ulong,void *,ulong,ulong *)
0x18003238d  mov     r15d, 2
0x180032393  test    eax, eax
0x180032395  js      short loc_1800323A1
0x180032397  cmp     dword ptr [rbp+57h+var_60+4], 1
0x18003239b  ja      short loc_1800323A1
0x18003239d  or      dword ptr [rbp+57h+var_20+4], r15d
0x1800323a1  lea     rdx, aPmAllowconnect; "PM_AllowConnectableMode"
0x1800323a8  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800323ac  call    cs:__imp_RtlInitUnicodeString
0x1800323b3  nop     dword ptr [rax+rax+00h]
0x1800323b8  mov     rcx, [rbp+57h+hKey]; HKEY
0x1800323bc  lea     r9, [rbp+57h+var_60+8]; void *
0x1800323c0  mov     r8d, esi; unsigned int
0x1800323c3  mov     [rsp+0A0h+var_78], rdi; unsigned int *
0x1800323c8  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x1800323cc  mov     dword ptr [rsp+0A0h+phkResult], esi; unsigned int
0x1800323d0  call    ?QueryKeyValueEx@@YAJPEAUHKEY__@@PEAU_UNICODE_STRING@@KPEAXKPEAK@Z; QueryKeyValueEx(HKEY__ *,_UNICODE_STRING *,ulong,void *,ulong,ulong *)
0x1800323d5  test    eax, eax
0x1800323d7  js      short loc_1800323E2
0x1800323d9  cmp     dword ptr [rbp+57h+var_60+8], 1
0x1800323dd  ja      short loc_1800323E2
0x1800323df  or      dword ptr [rbp+57h+var_20+4], esi
0x1800323e2  lea     rdx, aPmAllowadverti; "PM_AllowAdvertising"
0x1800323e9  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800323ed  call    cs:__imp_RtlInitUnicodeString
0x1800323f4  nop     dword ptr [rax+rax+00h]
0x1800323f9  mov     rcx, [rbp+57h+hKey]; HKEY
0x1800323fd  lea     r9, [rbp+57h+var_60+0Ch]; void *
0x180032401  mov     r8d, esi; unsigned int
0x180032404  mov     [rsp+0A0h+var_78], rdi; unsigned int *
0x180032409  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x18003240d  mov     dword ptr [rsp+0A0h+phkResult], esi; unsigned int
0x180032411  call    ?QueryKeyValueEx@@YAJPEAUHKEY__@@PEAU_UNICODE_STRING@@KPEAXKPEAK@Z; QueryKeyValueEx(HKEY__ *,_UNICODE_STRING *,ulong,void *,ulong,ulong *)
0x180032416  test    eax, eax
0x180032418  js      short loc_180032424
0x18003241a  cmp     dword ptr [rbp+57h+var_60+0Ch], 1
0x18003241e  ja      short loc_180032424
0x180032420  or      dword ptr [rbp+57h+var_20+4], 8
0x180032424  lea     rdx, aPmAllowoutofba; "PM_AllowOutOfBandPairing"
0x18003242b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003242f  call    cs:__imp_RtlInitUnicodeString
0x180032436  nop     dword ptr [rax+rax+00h]
0x18003243b  mov     rcx, [rbp+57h+hKey]; HKEY
0x18003243f  lea     r9, [rbp+57h+var_50]; void *
0x180032443  mov     r8d, esi; unsigned int
0x180032446  mov     [rsp+0A0h+var_78], rdi; unsigned int *
0x18003244b  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x18003244f  mov     dword ptr [rsp+0A0h+phkResult], esi; unsigned int
0x180032453  call    ?QueryKeyValueEx@@YAJPEAUHKEY__@@PEAU_UNICODE_STRING@@KPEAXKPEAK@Z; QueryKeyValueEx(HKEY__ *,_UNICODE_STRING *,ulong,void *,ulong,ulong *)
0x180032458  test    eax, eax
0x18003245a  js      short loc_180032466
0x18003245c  cmp     dword ptr [rbp+57h+var_50], 1
0x180032460  ja      short loc_180032466
0x180032462  or      dword ptr [rbp+57h+var_20+4], 10h
0x180032466  lea     rdx, aPmLinksecurity; "PM_LinkSecurityLevel"
0x18003246d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180032471  call    cs:__imp_RtlInitUnicodeString
0x180032478  nop     dword ptr [rax+rax+00h]
0x18003247d  mov     rcx, [rbp+57h+hKey]; HKEY
0x180032481  lea     r9, [rbp+57h+var_50+4]; void *
0x180032485  mov     r8d, esi; unsigned int
0x180032488  mov     [rsp+0A0h+var_78], rdi; unsigned int *
0x18003248d  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x180032491  mov     dword ptr [rsp+0A0h+phkResult], esi; unsigned int
0x180032495  call    ?QueryKeyValueEx@@YAJPEAUHKEY__@@PEAU_UNICODE_STRING@@KPEAXKPEAK@Z; QueryKeyValueEx(HKEY__ *,_UNICODE_STRING *,ulong,void *,ulong,ulong *)
0x18003249a  test    eax, eax
0x18003249c  js      short loc_1800324A8
0x18003249e  cmp     dword ptr [rbp+57h+var_50+4], r15d
0x1800324a2  ja      short loc_1800324A8
0x1800324a4  or      dword ptr [rbp+57h+var_20+4], 20h
0x1800324a8  lea     rdx, aPmLocaldevicen; "PM_LocalDeviceName"
0x1800324af  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800324b3  call    cs:__imp_RtlInitUnicodeString
0x1800324ba  nop     dword ptr [rax+rax+00h]
0x1800324bf  mov     rcx, [rbp+57h+hKey]
0x1800324c3  lea     rax, [rbp+57h+arg_0]
0x1800324c7  mov     [rsp+0A0h+var_78], rax
0x1800324cc  lea     rdx, [rbp+57h+DestinationString]
0x1800324d0  lea     rax, [rbp+57h+Block]
0x1800324d4  mov     r9d, 1
0x1800324da  mov     r8d, r15d
0x1800324dd  mov     [rsp+0A0h+phkResult], rax
0x1800324e2  call    ReadVariableLengthPolicy
0x1800324e7  test    eax, eax
0x1800324e9  js      short loc_18003250D
0x1800324eb  mov     eax, [rbp+57h+arg_0]
0x1800324ee  cmp     eax, 0FFFFh
0x1800324f3  ja      short loc_18003250D
0x1800324f5  mov     word ptr [rbp+57h+var_50+0Ah], ax
0x1800324f9  cmp     ax, r15w
0x1800324fd  jb      short loc_180032522
0x1800324ff  sub     ax, r15w
0x180032503  or      dword ptr [rbp+57h+var_20+4], 40h
0x180032507  mov     word ptr [rbp+57h+var_50+8], ax
0x18003250b  jmp     short loc_180032522
0x18003250d  mov     rcx, [rbp+57h+Block]; Block
0x180032511  test    rcx, rcx
0x180032514  jz      short loc_180032522
0x180032516  call    free
0x18003251b  xorps   xmm0, xmm0
0x18003251e  movups  [rbp+57h+var_50+8], xmm0
0x180032522  lea     rdx, aPmDevicesallow; "PM_DevicesAllowedList"
0x180032529  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003252d  call    cs:__imp_RtlInitUnicodeString
0x180032534  nop     dword ptr [rax+rax+00h]
0x180032539  mov     rcx, [rbp+57h+hKey]
0x18003253d  lea     rax, [rbp+57h+arg_0]
0x180032541  mov     [rsp+0A0h+var_78], rax
0x180032546  lea     rdx, [rbp+57h+DestinationString]
0x18003254a  mov     r15d, 3
0x180032550  lea     rax, [rbp+57h+Block+8]
0x180032554  mov     r9d, r15d
0x180032557  mov     [rsp+0A0h+phkResult], rax
0x18003255c  lea     r8d, [r15+5]
0x180032560  call    ReadVariableLengthPolicy
0x180032565  test    eax, eax
0x180032567  js      short loc_180032579
0x180032569  mov     eax, [rbp+57h+arg_0]
0x18003256c  shr     eax, 3
0x18003256f  bts     dword ptr [rbp+57h+var_20+4], 7
0x180032574  mov     dword ptr [rbp+57h+var_20+8], eax
0x180032577  jmp     short loc_18003258E
0x180032579  mov     rcx, [rbp+57h+Block+8]; Block
0x18003257d  test    rcx, rcx
0x180032580  jz      short loc_18003258E
0x180032582  call    free
0x180032587  mov     [rbp+57h+Block+8], rdi
0x18003258b  mov     dword ptr [rbp+57h+var_20+8], edi
0x18003258e  lea     rdx, aPmServicesallo; "PM_ServicesAllowedList"
0x180032595  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180032599  call    cs:__imp_RtlInitUnicodeString
0x1800325a0  nop     dword ptr [rax+rax+00h]
0x1800325a5  mov     rcx, [rbp+57h+hKey]
0x1800325a9  lea     rax, [rbp+57h+arg_0]
0x1800325ad  mov     [rsp+0A0h+var_78], rax
0x1800325b2  lea     rdx, [rbp+57h+DestinationString]
0x1800325b6  lea     rax, [rbp+57h+var_30]
0x1800325ba  mov     r9d, r15d
0x1800325bd  mov     r8d, 10h
0x1800325c3  mov     [rsp+0A0h+phkResult], rax
0x1800325c8  call    ReadVariableLengthPolicy
0x1800325cd  test    eax, eax
0x1800325cf  js      short loc_1800325E1
0x1800325d1  mov     eax, [rbp+57h+arg_0]
0x1800325d4  shr     eax, 4
0x1800325d7  bts     dword ptr [rbp+57h+var_20+4], 8
0x1800325dc  mov     dword ptr [rbp+57h+var_20+0Ch], eax
0x1800325df  jmp     short loc_1800325F6
0x1800325e1  mov     rcx, [rbp+57h+var_30]; Block
0x1800325e5  test    rcx, rcx
0x1800325e8  jz      short loc_1800325F6
0x1800325ea  call    free
0x1800325ef  mov     [rbp+57h+var_30], rdi
0x1800325f3  mov     dword ptr [rbp+57h+var_20+0Ch], edi
0x1800325f6  lea     rdx, aPmRequirerestr; "PM_RequireRestrictedMode"
0x1800325fd  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180032601  call    cs:__imp_RtlInitUnicodeString
0x180032608  nop     dword ptr [rax+rax+00h]
0x18003260d  mov     rcx, [rbp+57h+hKey]; HKEY
0x180032611  lea     r9, [rbp+57h+var_30+8]; void *
0x180032615  mov     r8d, esi; unsigned int
0x180032618  mov     [rsp+0A0h+var_78], rdi; unsigned int *
0x18003261d  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x180032621  mov     dword ptr [rsp+0A0h+phkResult], esi; unsigned int
0x180032625  call    ?QueryKeyValueEx@@YAJPEAUHKEY__@@PEAU_UNICODE_STRING@@KPEAXKPEAK@Z; QueryKeyValueEx(HKEY__ *,_UNICODE_STRING *,ulong,void *,ulong,ulong *)
0x18003262a  test    eax, eax
0x18003262c  js      short loc_180032639
0x18003262e  cmp     dword ptr [rbp+57h+var_30+8], 1
0x180032632  ja      short loc_180032639
0x180032634  bts     dword ptr [rbp+57h+var_20+4], 9
0x180032639  lea     rdx, aPmAllowprepair; "PM_AllowPrepairing"
0x180032640  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180032644  call    cs:__imp_RtlInitUnicodeString
0x18003264b  nop     dword ptr [rax+rax+00h]
0x180032650  mov     rcx, [rbp+57h+hKey]; HKEY
0x180032654  lea     r9, [rbp+57h+var_30+0Ch]; void *
0x180032658  mov     r8d, esi; unsigned int
0x18003265b  mov     [rsp+0A0h+var_78], rdi; unsigned int *
0x180032660  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x180032664  mov     dword ptr [rsp+0A0h+phkResult], esi; unsigned int
0x180032668  call    ?QueryKeyValueEx@@YAJPEAUHKEY__@@PEAU_UNICODE_STRING@@KPEAXKPEAK@Z; QueryKeyValueEx(HKEY__ *,_UNICODE_STRING *,ulong,void *,ulong,ulong *)
0x18003266d  test    eax, eax
0x18003266f  js      short loc_18003267C
0x180032671  cmp     dword ptr [rbp+57h+var_30+0Ch], 1
0x180032675  ja      short loc_18003267C
0x180032677  bts     dword ptr [rbp+57h+var_20+4], 0Ah
0x18003267c  lea     rdx, aPmSetminimumen; "PM_SetMinimumEncryptionKeySize"
0x180032683  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180032687  call    cs:__imp_RtlInitUnicodeString
0x18003268e  nop     dword ptr [rax+rax+00h]
0x180032693  mov     rcx, [rbp+57h+hKey]; HKEY
0x180032697  lea     r9, [rbp+57h+var_20]; void *
0x18003269b  mov     r8d, esi; unsigned int
0x18003269e  mov     [rsp+0A0h+var_78], rdi; unsigned int *
0x1800326a3  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x1800326a7  mov     dword ptr [rsp+0A0h+phkResult], esi; unsigned int
0x1800326ab  call    ?QueryKeyValueEx@@YAJPEAUHKEY__@@PEAU_UNICODE_STRING@@KPEAXKPEAK@Z; QueryKeyValueEx(HKEY__ *,_UNICODE_STRING *,ulong,void *,ulong,ulong *)
0x1800326b0  test    eax, eax
0x1800326b2  js      short loc_1800326C3
0x1800326b4  mov     eax, dword ptr [rbp+57h+var_20]
0x1800326b7  dec     eax
0x1800326b9  cmp     eax, 0Fh
0x1800326bc  ja      short loc_1800326C3
0x1800326be  bts     dword ptr [rbp+57h+var_20+4], 0Bh
0x1800326c3  lea     rcx, ?g_PolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800326ca  call    cs:__imp_EnterCriticalSection
0x1800326d1  nop     dword ptr [rax+rax+00h]
0x1800326d6  mov     rcx, qword ptr cs:ymmword_180046F70+10h; Block
0x1800326dd  test    rcx, rcx
0x1800326e0  jz      short loc_1800326E7
0x1800326e2  call    free
0x1800326e7  mov     rcx, qword ptr cs:ymmword_180046F70+18h; Block
0x1800326ee  test    rcx, rcx
0x1800326f1  jz      short loc_1800326F8
0x1800326f3  call    free
0x1800326f8  mov     rcx, qword ptr cs:Src; Block
0x1800326ff  test    rcx, rcx
0x180032702  jz      short loc_180032709
0x180032704  call    free
0x180032709  movaps  xmm0, [rbp+57h+var_60]
0x18003270d  lea     rcx, ?g_PolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180032714  movaps  xmm1, [rbp+57h+var_50]
0x180032718  movaps  cs:?g_Policies@@3UPolicies@@A, xmm0; Policies g_Policies
0x18003271f  movaps  xmm0, xmmword ptr [rbp+57h+Block]
0x180032723  movaps  xmmword ptr cs:ymmword_180046F70+10h, xmm0
0x18003272a  movaps  xmm0, [rbp+57h+var_20]
0x18003272e  movaps  xmmword ptr cs:ymmword_180046F70, xmm1
0x180032735  movaps  xmm1, xmmword ptr [rbp+57h+var_30]
0x180032739  movaps  xmmword ptr cs:byte_180046FA0, xmm0
0x180032740  movaps  cs:Src, xmm1
0x180032747  call    cs:__imp_LeaveCriticalSection
0x18003274e  nop     dword ptr [rax+rax+00h]
0x180032753  mov     rcx, [rbp+57h+hKey]; hKey
0x180032757  test    rcx, rcx
0x18003275a  jz      short loc_180032768
0x18003275c  call    cs:__imp_RegCloseKey
0x180032763  nop     dword ptr [rax+rax+00h]
0x180032768  mov     eax, ebx
0x18003276a  lea     r11, [rsp+0A0h+var_10]
0x180032772  mov     rbx, [r11+30h]
  ... truncated ...
```
