# CIVIAudioCodec::Init(long *)

- ea: `0x18001c2f0`
- end: `0x18001c8de`
- name: `?Init@CIVIAudioCodec@@QEAAXPEAJ@Z`
- size: `1518`
- prototype: `void __fastcall(CIVIAudioCodec *__hidden this, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000a140`

## callees

- `0x1800021a8`
- `0x18001c2f0`
- `0x180032f00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x18001c80d`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x18001c80d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c4b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c5bf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c4b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c5bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c4c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c5d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c4c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c5d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c477`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c581`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c477`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c581`

## pseudocode

```c
void __fastcall CIVIAudioCodec::Init(CIVIAudioCodec *this, int *a2)
{
  bool v4; // zf
  __int64 v5; // rax
  int v6; // esi
  const WCHAR *v7; // rdx
  LSTATUS v8; // ebx
  __int64 v9; // rax
  int v10; // esi
  const WCHAR *v11; // rdx
  LSTATUS v12; // ebx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  void *v16; // rax
  HKEY hKey; // [rsp+30h] [rbp-58h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-50h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-48h] BYREF
  BYTE v20[64]; // [rsp+48h] [rbp-40h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+8h] BYREF
  DWORD lpcbData; // [rsp+98h] [rbp+10h] BYREF
  DWORD Type; // [rsp+A0h] [rbp+18h] BYREF
  DWORD v24; // [rsp+A8h] [rbp+20h] BYREF

  *((_DWORD *)this + 96) = -1;
  *((_DWORD *)this + 1715) = 0;
  *(_QWORD *)((char *)this + 5900) = 0;
  *((_DWORD *)this + 94) = 0;
  *((_DWORD *)this + 3780) = 0;
  *((_QWORD *)this + 710) = 0;
  *((_BYTE *)this + 5720) = 0;
  *((_DWORD *)this + 1552) = 0;
  *((_DWORD *)this + 1417) = 0;
  *((_DWORD *)this + 1484) = 0;
  *((_DWORD *)this + 1429) = 0;
  memset_0((char *)this + 6864, 0, 0x2040u);
  *((_QWORD *)this + 739) = 0;
  *((_DWORD *)this + 1477) = 0;
  *((_DWORD *)this + 1436) = 0;
  memset_0((char *)this + 388, 0, 0x14A0u);
  v4 = lpSubKey == 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 713) = 0;
  *((_DWORD *)this + 1586) = 0;
  *((_DWORD *)this + 1564) = 3;
  *((_DWORD *)this + 1565) = 99;
  *((_DWORD *)this + 1566) = 2;
  *((_DWORD *)this + 1567) = 100;
  *((_DWORD *)this + 1568) = 100;
  *((_DWORD *)this + 1574) = 0;
  *((_QWORD *)this + 791) = 0;
  *((_DWORD *)this + 1584) = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( v4 )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(&xmmword_1800ADB00 + v5) );
    if ( v5 || (int)UTIL_REGGetModuleBase() >= 0 )
      lpSubKey = &xmmword_1800ADB00;
  }
  cbData = 8;
  v6 = 0;
  while ( 1 )
  {
    v7 = (const WCHAR *)qword_1800ADAF0;
    if ( v6 < 2 )
      v7 = lpSubKey;
    if ( v7 )
    {
      if ( !RegOpenKeyExW((HKEY)qword_180095458[v6], v7, 0, 0x20019u, &hKey) )
      {
        v8 = RegQueryValueExW(hKey, L"dolby_rf_on", 0, &Type, Data, &cbData);
        RegCloseKey(hKey);
        if ( !v8 )
          break;
      }
    }
    if ( !qword_180095458[++v6] )
      goto LABEL_17;
  }
  if ( !*(_DWORD *)Data )
    *((_DWORD *)this + 1566) = 1;
LABEL_17:
  phkResult = 0;
  v24 = 0;
  lpcbData = 0;
  if ( !lpSubKey )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(&xmmword_1800ADB00 + v9) );
    if ( v9 || (int)UTIL_REGGetModuleBase() >= 0 )
      lpSubKey = &xmmword_1800ADB00;
  }
  lpcbData = 8;
  v10 = 0;
  while ( 1 )
  {
    v11 = (const WCHAR *)qword_1800ADAF0;
    if ( v10 < 2 )
      v11 = lpSubKey;
    if ( v11 )
    {
      if ( !RegOpenKeyExW((HKEY)qword_180095458[v10], v11, 0, 0x20019u, &phkResult) )
      {
        v12 = RegQueryValueExW(phkResult, L"dolby_drc_on", 0, &v24, v20, &lpcbData);
        RegCloseKey(phkResult);
        if ( !v12 )
          break;
      }
    }
    if ( !qword_180095458[++v10] )
      goto LABEL_33;
  }
  if ( !*(_DWORD *)v20 )
    *(_QWORD *)((char *)this + 6268) = 0;
LABEL_33:
  v13 = *((_DWORD *)this + 1566);
  *((_DWORD *)this + 1569) = 1;
  *(_QWORD *)((char *)this + 6220) = 0;
  *((_DWORD *)this + 1557) = 48000;
  *((_QWORD *)this + 790) = 0;
  *((_DWORD *)this + 1576) = 0;
  *((_QWORD *)this + 789) = 0;
  *((_DWORD *)this + 1577) = 1;
  *((_DWORD *)this + 5) = 7;
  *((_DWORD *)this + 92) = 6;
  *((_QWORD *)this + 781) = 0;
  *((_DWORD *)this + 1435) = 0;
  *((_DWORD *)this + 1418) = 0;
  *((_QWORD *)this + 1) = 1;
  *((_DWORD *)this + 4) = 1;
  *((_DWORD *)this + 89) = 1000;
  *((_BYTE *)this + 352) = 0;
  *((_DWORD *)this + 1554) = 0;
  *((_DWORD *)this + 75) = 3;
  *((_DWORD *)this + 91) = 0;
  *((_DWORD *)this + 1713) = -1;
  *((_DWORD *)this + 1714) = 0;
  *((_DWORD *)this + 95) = 0;
  *((_DWORD *)this + 3781) = 0;
  *((_QWORD *)this + 720) = 0;
  *((_DWORD *)this + 93) = 0;
  *((_DWORD *)this + 74) = 0;
  *((_QWORD *)this + 795) = 0;
  *((_QWORD *)this + 780) = 0;
  *((_DWORD *)this + 1422) = 96;
  *((_DWORD *)this + 1513) = 2;
  *((_DWORD *)this + 1510) = 6;
  *((_QWORD *)this + 712) = 0;
  v14 = v13 - 1;
  if ( !v14 )
  {
    *((_DWORD *)this + 1501) = 2;
    goto LABEL_39;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    *((_DWORD *)this + 1501) = 3;
LABEL_39:
    *((_DWORD *)this + 1507) = 1065353216;
    goto LABEL_40;
  }
  if ( v15 == 1 )
  {
    *((_DWORD *)this + 1505) = 0;
    *((_DWORD *)this + 1501) = 3;
    *((_DWORD *)this + 1507) = 1045220557;
  }
LABEL_40:
  *((_DWORD *)this + 1419) = 0;
  *((_DWORD *)this + 1423) = 1;
  *((_DWORD *)this + 1481) = 16;
  *((_QWORD *)this + 741) = 48000;
  *((_DWORD *)this + 1474) = 0;
  *((_DWORD *)this + 1480) = 16;
  *(_QWORD *)((char *)this + 5724) = 0;
  *(_QWORD *)((char *)this + 5732) = 0;
  *((_DWORD *)this + 3782) = 0;
  *((_DWORD *)this + 1442) = 0;
  *((_QWORD *)this + 722) = 0;
  *((_DWORD *)this + 1446) = 0;
  *((_QWORD *)this + 724) = 0;
  *((_DWORD *)this + 1450) = 0;
  *((_QWORD *)this + 726) = 0;
  *((_DWORD *)this + 1454) = 0;
  *((_QWORD *)this + 728) = 0;
  *((_DWORD *)this + 1458) = 0;
  *((_QWORD *)this + 730) = 0;
  *((_DWORD *)this + 1462) = 0;
  *((_QWORD *)this + 732) = 0;
  *((_DWORD *)this + 1466) = 0;
  *((_QWORD *)this + 734) = 0;
  *((_DWORD *)this + 1470) = 0;
  *((_QWORD *)this + 736) = 0;
  *((_QWORD *)this + 719) = 0;
  if ( *a2 >= 0 )
  {
    v16 = _aligned_malloc(0x1C333u, 0x10u);
    *((_QWORD *)this + 794) = v16;
    if ( v16 )
      memset_0(v16, 0, 0x1C333u);
    else
      *a2 = -2147024882;
  }
  *(_OWORD *)((char *)this + 6376) = 0;
  *(_OWORD *)((char *)this + 6392) = 0;
  *((_QWORD *)this + 801) = 0;
  *((_QWORD *)this + 806) = 0;
  *((_QWORD *)this + 796) = 0;
  *((_DWORD *)this + 1604) = -1;
  *((_DWORD *)this + 1712) = 1;
  *((_QWORD *)this + 805) = 0;
  *((_QWORD *)this + 807) = 0;
  *((_QWORD *)this + 803) = 0;
  *((_QWORD *)this + 804) = 0;
  *((_QWORD *)this + 808) = 0;
  *((_WORD *)this + 3236) = 0;
  *((_QWORD *)this + 855) = 0;
  memset_0((char *)this + 6476, 0, 0x16Cu);
  *((_DWORD *)this + 1620) = 1;
  *((_QWORD *)this + 1892) = 0;
}

```

## disassembly

```asm
0x18001c2f0  push    rbx
0x18001c2f2  push    rbp
0x18001c2f3  push    rsi
0x18001c2f4  push    rdi
0x18001c2f5  push    r12
0x18001c2f7  push    r14
0x18001c2f9  push    r15
0x18001c2fb  sub     rsp, 50h
0x18001c2ff  xor     ebp, ebp
0x18001c301  mov     dword ptr [rcx+180h], 0FFFFFFFFh
0x18001c30b  mov     [rcx+1ACCh], ebp
0x18001c311  mov     r14, rdx
0x18001c314  mov     [rcx+170Ch], rbp
0x18001c31b  mov     rdi, rcx
0x18001c31e  mov     [rcx+178h], ebp
0x18001c324  xor     edx, edx; Val
0x18001c326  mov     [rcx+3B10h], ebp
0x18001c32c  mov     r8d, 2040h; Size
0x18001c332  mov     [rcx+1630h], rbp
0x18001c339  mov     [rcx+1658h], bpl
0x18001c340  mov     [rcx+1840h], ebp
0x18001c346  mov     [rcx+1624h], ebp
0x18001c34c  mov     [rcx+1730h], ebp
0x18001c352  mov     [rcx+1654h], ebp
0x18001c358  add     rcx, 1AD0h; void *
0x18001c35f  call    memset_0
0x18001c364  lea     rcx, [rdi+184h]; void *
0x18001c36b  mov     [rdi+1718h], rbp
0x18001c372  xor     edx, edx; Val
0x18001c374  mov     [rdi+1714h], ebp
0x18001c37a  mov     r8d, 14A0h; Size
0x18001c380  mov     [rdi+1670h], ebp
0x18001c386  call    memset_0
0x18001c38b  cmp     cs:lpSubKey, rbp
0x18001c392  lea     r15, xmmword_1800ADB00
0x18001c399  mov     [rdi+58h], rbp
0x18001c39d  mov     [rdi+68h], rbp
0x18001c3a1  mov     [rdi+60h], rbp
0x18001c3a5  mov     [rdi+1648h], rbp
0x18001c3ac  mov     [rdi+18C8h], ebp
0x18001c3b2  mov     dword ptr [rdi+1870h], 3
0x18001c3bc  mov     dword ptr [rdi+1874h], 63h ; 'c'
0x18001c3c6  mov     dword ptr [rdi+1878h], 2
0x18001c3d0  mov     dword ptr [rdi+187Ch], 64h ; 'd'
0x18001c3da  mov     dword ptr [rdi+1880h], 64h ; 'd'
0x18001c3e4  mov     [rdi+1898h], ebp
0x18001c3ea  mov     [rdi+18B8h], rbp
0x18001c3f1  mov     [rdi+18C0h], ebp
0x18001c3f7  mov     [rsp+88h+hKey], rbp
0x18001c3fc  mov     [rsp+88h+Type], ebp
0x18001c403  mov     [rsp+88h+cbData], ebp
0x18001c40a  jnz     short loc_18001C432
0x18001c40c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001c413  inc     rax
0x18001c416  cmp     [r15+rax*2], bp
0x18001c41b  jnz     short loc_18001C413
0x18001c41d  test    rax, rax
0x18001c420  jnz     short loc_18001C42B
0x18001c422  call    ?UTIL_REGGetModuleBase@@YAHW4ERegModule@@PEAG_K_N@Z; UTIL_REGGetModuleBase(ERegModule,ushort *,unsigned __int64,bool)
0x18001c427  test    eax, eax
0x18001c429  js      short loc_18001C432
0x18001c42b  mov     cs:lpSubKey, r15
0x18001c432  mov     [rsp+88h+cbData], 8
0x18001c43d  lea     r12, qword_180095458
0x18001c444  mov     esi, ebp
0x18001c446  mov     rdx, cs:qword_1800ADAF0
0x18001c44d  cmp     esi, 2
0x18001c450  cmovl   rdx, cs:lpSubKey; lpSubKey
0x18001c458  test    rdx, rdx
0x18001c45b  jz      short loc_18001C4D8
0x18001c45d  lea     rax, [rsp+88h+hKey]
0x18001c462  movsxd  rcx, esi
0x18001c465  mov     r9d, 20019h; samDesired
0x18001c46b  mov     [rsp+88h+phkResult], rax; phkResult
0x18001c470  xor     r8d, r8d; ulOptions
0x18001c473  mov     rcx, [r12+rcx*8]; hKey
0x18001c477  call    cs:__imp_RegOpenKeyExW
0x18001c47e  nop     dword ptr [rax+rax+00h]
0x18001c483  test    eax, eax
0x18001c485  jnz     short loc_18001C4D8
0x18001c487  mov     rcx, [rsp+88h+hKey]; hKey
0x18001c48c  lea     rax, [rsp+88h+cbData]
0x18001c494  mov     [rsp+88h+lpcbData], rax; lpcbData
0x18001c499  lea     r9, [rsp+88h+Type]; lpType
0x18001c4a1  lea     rax, [rsp+88h+Data]
0x18001c4a6  xor     r8d, r8d; lpReserved
0x18001c4a9  lea     rdx, aDolbyRfOn; "dolby_rf_on"
0x18001c4b0  mov     [rsp+88h+phkResult], rax; lpData
0x18001c4b5  call    cs:__imp_RegQueryValueExW
0x18001c4bc  nop     dword ptr [rax+rax+00h]
0x18001c4c1  mov     rcx, [rsp+88h+hKey]; hKey
0x18001c4c6  mov     ebx, eax
0x18001c4c8  call    cs:__imp_RegCloseKey
0x18001c4cf  nop     dword ptr [rax+rax+00h]
0x18001c4d4  test    ebx, ebx
0x18001c4d6  jz      short loc_18001C4E9
0x18001c4d8  inc     esi
0x18001c4da  movsxd  rax, esi
0x18001c4dd  cmp     [r12+rax*8], rbp
0x18001c4e1  jnz     loc_18001C446
0x18001c4e7  jmp     short loc_18001C4F9
0x18001c4e9  cmp     dword ptr [rsp+88h+Data], ebp
0x18001c4ed  jnz     short loc_18001C4F9
0x18001c4ef  mov     dword ptr [rdi+1878h], 1
0x18001c4f9  cmp     cs:lpSubKey, rbp
0x18001c500  mov     [rsp+88h+var_50], rbp
0x18001c505  mov     [rsp+88h+arg_18], ebp
0x18001c50c  mov     [rsp+88h+arg_8], ebp
0x18001c513  jnz     short loc_18001C53F
0x18001c515  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001c51c  nop     dword ptr [rax+00h]
0x18001c520  inc     rax
0x18001c523  cmp     [r15+rax*2], bp
0x18001c528  jnz     short loc_18001C520
0x18001c52a  test    rax, rax
0x18001c52d  jnz     short loc_18001C538
0x18001c52f  call    ?UTIL_REGGetModuleBase@@YAHW4ERegModule@@PEAG_K_N@Z; UTIL_REGGetModuleBase(ERegModule,ushort *,unsigned __int64,bool)
0x18001c534  test    eax, eax
0x18001c536  js      short loc_18001C53F
0x18001c538  mov     cs:lpSubKey, r15
0x18001c53f  mov     [rsp+88h+arg_8], 8
0x18001c54a  mov     esi, ebp
0x18001c54c  nop     dword ptr [rax+00h]
0x18001c550  mov     rdx, cs:qword_1800ADAF0
0x18001c557  cmp     esi, 2
0x18001c55a  cmovl   rdx, cs:lpSubKey; lpSubKey
0x18001c562  test    rdx, rdx
0x18001c565  jz      short loc_18001C5E2
0x18001c567  lea     rax, [rsp+88h+var_50]
0x18001c56c  movsxd  rcx, esi
0x18001c56f  mov     r9d, 20019h; samDesired
0x18001c575  mov     [rsp+88h+phkResult], rax; phkResult
0x18001c57a  xor     r8d, r8d; ulOptions
0x18001c57d  mov     rcx, [r12+rcx*8]; hKey
0x18001c581  call    cs:__imp_RegOpenKeyExW
0x18001c588  nop     dword ptr [rax+rax+00h]
0x18001c58d  test    eax, eax
0x18001c58f  jnz     short loc_18001C5E2
0x18001c591  mov     rcx, [rsp+88h+var_50]; hKey
0x18001c596  lea     rax, [rsp+88h+arg_8]
0x18001c59e  mov     [rsp+88h+lpcbData], rax; lpcbData
0x18001c5a3  lea     r9, [rsp+88h+arg_18]; lpType
0x18001c5ab  lea     rax, [rsp+88h+var_40]
0x18001c5b0  xor     r8d, r8d; lpReserved
0x18001c5b3  lea     rdx, aDolbyDrcOn; "dolby_drc_on"
0x18001c5ba  mov     [rsp+88h+phkResult], rax; lpData
0x18001c5bf  call    cs:__imp_RegQueryValueExW
0x18001c5c6  nop     dword ptr [rax+rax+00h]
0x18001c5cb  mov     rcx, [rsp+88h+var_50]; hKey
0x18001c5d0  mov     ebx, eax
0x18001c5d2  call    cs:__imp_RegCloseKey
0x18001c5d9  nop     dword ptr [rax+rax+00h]
0x18001c5de  test    ebx, ebx
0x18001c5e0  jz      short loc_18001C5F3
0x18001c5e2  inc     esi
0x18001c5e4  movsxd  rax, esi
0x18001c5e7  cmp     [r12+rax*8], rbp
0x18001c5eb  jnz     loc_18001C550
0x18001c5f1  jmp     short loc_18001C600
0x18001c5f3  cmp     dword ptr [rsp+88h+var_40], ebp
0x18001c5f7  jnz     short loc_18001C600
0x18001c5f9  mov     [rdi+187Ch], rbp
0x18001c600  mov     ecx, [rdi+1878h]
0x18001c606  mov     dword ptr [rdi+1884h], 1
0x18001c610  mov     [rdi+184Ch], rbp
0x18001c617  mov     dword ptr [rdi+1854h], 0BB80h
0x18001c621  mov     [rdi+18B0h], rbp
0x18001c628  mov     [rdi+18A0h], ebp
0x18001c62e  mov     [rdi+18A8h], rbp
0x18001c635  mov     dword ptr [rdi+18A4h], 1
0x18001c63f  mov     dword ptr [rdi+14h], 7
0x18001c646  mov     dword ptr [rdi+170h], 6
0x18001c650  mov     [rdi+1868h], rbp
0x18001c657  mov     [rdi+166Ch], ebp
0x18001c65d  mov     [rdi+1628h], ebp
0x18001c663  mov     qword ptr [rdi+8], 1
0x18001c66b  mov     dword ptr [rdi+10h], 1
0x18001c672  mov     dword ptr [rdi+164h], 3E8h
0x18001c67c  mov     [rdi+160h], bpl
0x18001c683  mov     [rdi+1848h], ebp
0x18001c689  mov     dword ptr [rdi+12Ch], 3
0x18001c693  mov     [rdi+16Ch], ebp
0x18001c699  mov     dword ptr [rdi+1AC4h], 0FFFFFFFFh
0x18001c6a3  mov     [rdi+1AC8h], ebp
0x18001c6a9  mov     [rdi+17Ch], ebp
0x18001c6af  mov     [rdi+3B14h], ebp
0x18001c6b5  mov     [rdi+1680h], rbp
0x18001c6bc  mov     [rdi+174h], ebp
0x18001c6c2  mov     [rdi+128h], ebp
0x18001c6c8  mov     [rdi+18D8h], rbp
0x18001c6cf  mov     [rdi+1860h], rbp
0x18001c6d6  mov     dword ptr [rdi+1638h], 60h ; '`'
0x18001c6e0  mov     dword ptr [rdi+17A4h], 2
0x18001c6ea  mov     dword ptr [rdi+1798h], 6
0x18001c6f4  mov     [rdi+1640h], rbp
0x18001c6fb  sub     ecx, 1
0x18001c6fe  jz      short loc_18001C732
0x18001c700  sub     ecx, 1
0x18001c703  jz      short loc_18001C726
0x18001c705  cmp     ecx, 1
0x18001c708  jnz     short loc_18001C746
0x18001c70a  mov     [rdi+1784h], ebp
0x18001c710  mov     dword ptr [rdi+1774h], 3
0x18001c71a  mov     dword ptr [rdi+178Ch], 3E4CCCCDh
0x18001c724  jmp     short loc_18001C746
0x18001c726  mov     dword ptr [rdi+1774h], 3
0x18001c730  jmp     short loc_18001C73C
0x18001c732  mov     dword ptr [rdi+1774h], 2
0x18001c73c  mov     dword ptr [rdi+178Ch], 3F800000h
0x18001c746  mov     [rdi+162Ch], ebp
0x18001c74c  mov     dword ptr [rdi+163Ch], 1
0x18001c756  mov     dword ptr [rdi+1724h], 10h
0x18001c760  mov     qword ptr [rdi+1728h], 0BB80h
0x18001c76b  mov     [rdi+1708h], ebp
0x18001c771  mov     dword ptr [rdi+1720h], 10h
0x18001c77b  mov     [rdi+165Ch], rbp
0x18001c782  mov     [rdi+1664h], rbp
0x18001c789  mov     [rdi+3B18h], ebp
0x18001c78f  mov     [rdi+1688h], ebp
0x18001c795  mov     [rdi+1690h], rbp
0x18001c79c  mov     [rdi+1698h], ebp
0x18001c7a2  mov     [rdi+16A0h], rbp
0x18001c7a9  mov     [rdi+16A8h], ebp
0x18001c7af  mov     [rdi+16B0h], rbp
0x18001c7b6  mov     [rdi+16B8h], ebp
0x18001c7bc  mov     [rdi+16C0h], rbp
0x18001c7c3  mov     [rdi+16C8h], ebp
0x18001c7c9  mov     [rdi+16D0h], rbp
0x18001c7d0  mov     [rdi+16D8h], ebp
0x18001c7d6  mov     [rdi+16E0h], rbp
0x18001c7dd  mov     [rdi+16E8h], ebp
0x18001c7e3  mov     [rdi+16F0h], rbp
0x18001c7ea  mov     [rdi+16F8h], ebp
0x18001c7f0  mov     [rdi+1700h], rbp
0x18001c7f7  mov     [rdi+1678h], rbp
0x18001c7fe  cmp     [r14], ebp
0x18001c801  jl      short loc_18001C83E
0x18001c803  mov     edx, 10h; Alignment
0x18001c808  mov     ecx, 1C333h; Size
0x18001c80d  call    cs:__imp__aligned_malloc
0x18001c814  nop     dword ptr [rax+rax+00h]
0x18001c819  mov     [rdi+18D0h], rax
0x18001c820  test    rax, rax
0x18001c823  jz      short loc_18001C837
0x18001c825  xor     edx, edx; Val
0x18001c827  mov     r8d, 1C333h; Size
0x18001c82d  mov     rcx, rax; void *
0x18001c830  call    memset_0
0x18001c835  jmp     short loc_18001C83E
0x18001c837  mov     dword ptr [r14], 8007000Eh
0x18001c83e  xorps   xmm0, xmm0
0x18001c841  lea     rcx, [rdi+194Ch]; void *
0x18001c848  movups  xmmword ptr [rdi+18E8h], xmm0
0x18001c84f  xor     edx, edx; Val
0x18001c851  mov     r8d, 16Ch; Size
0x18001c857  movups  xmmword ptr [rdi+18F8h], xmm0
0x18001c85e  mov     [rdi+1908h], rbp
0x18001c865  mov     [rdi+1930h], rbp
0x18001c86c  mov     [rdi+18E0h], rbp
0x18001c873  mov     dword ptr [rdi+1910h], 0FFFFFFFFh
0x18001c87d  mov     dword ptr [rdi+1AC0h], 1
0x18001c887  mov     [rdi+1928h], rbp
0x18001c88e  mov     [rdi+1938h], rbp
0x18001c895  mov     [rdi+1918h], rbp
0x18001c89c  mov     [rdi+1920h], rbp
0x18001c8a3  mov     [rdi+1940h], rbp
0x18001c8aa  mov     [rdi+1948h], bp
0x18001c8b1  mov     [rdi+1AB8h], rbp
0x18001c8b8  call    memset_0
0x18001c8bd  mov     dword ptr [rdi+1950h], 1
0x18001c8c7  mov     [rdi+3B20h], rbp
0x18001c8ce  add     rsp, 50h
0x18001c8d2  pop     r15
0x18001c8d4  pop     r14
0x18001c8d6  pop     r12
0x18001c8d8  pop     rdi
0x18001c8d9  pop     rsi
0x18001c8da  pop     rbp
0x18001c8db  pop     rbx
0x18001c8dc  retn
```
