# DeleteExpiredTemporaryLicenses(void)

- ea: `0x18004c550`
- end: `0x18004c94d`
- name: `?DeleteExpiredTemporaryLicenses@@YAIXZ`
- size: `1021`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004cc90`

## callees

- `0x180005665`
- `0x18001ad48`
- `0x18001f5bc`
- `0x1800352ec`
- `0x1800356e4`
- `0x1800357f8`
- `0x180035824`
- `0x180035c74`
- `0x180035cd0`
- `0x180036604`
- `0x180036a7c`
- `0x180036ad8`
- `0x18004c550`
- `0x1800662a0`
- `0x18007dba8`
- `0x18007dc30`
- `0x18007dc58`
- `0x18007dda4`
- `0x18007e2c0`
- `0x18007ea78`
- `0x1800a0fb0`
- `0x1800a1070`

## import_xrefs

- `msvcrt!time` at `0x18004c608`
- `msvcrt!time` at `0x18004c608`
- `ADVAPI32!RegCreateKeyExW` at `0x18004c64c`
- `ADVAPI32!RegCreateKeyExW` at `0x18004c64c`
- `ADVAPI32!RegQueryValueExW` at `0x18004c68f`
- `ADVAPI32!RegQueryValueExW` at `0x18004c68f`
- `ADVAPI32!RegCloseKey` at `0x18004c6a2`
- `ADVAPI32!RegCloseKey` at `0x18004c6a2`

## string_xrefs

- `0x18004c63e`: `SYSTEM\CurrentControlSet\Services\TermServLicensing\Parameters`
- `0x18004c683`: `EffectiveDaysToDeleteTemporary`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 DeleteExpiredTemporaryLicenses(void)
{
  int v0; // edi
  unsigned int v1; // esi
  LSTATUS Value; // ebx
  int v3; // eax
  int v4; // eax
  unsigned int v5; // edi
  struct IRdlsDBConnection *v6; // rcx
  struct IRdlsDBConnection *v7; // rbx
  struct IRdlsDBConnection *v8; // rcx
  int v9; // ecx
  struct IRdlsDBConnection *v10; // rcx
  struct IRdlsDBConnection *v11; // rcx
  struct IRdlsDBConnection *v12; // rcx
  int v13; // edx
  __int64 *v14; // rcx
  struct IRdlsDBConnection *v15; // rcx
  struct IRdlsDBConnection *v16; // rcx
  struct IRdlsDBConnection *v17; // rcx
  struct IRdlsDBConnection *v18; // rcx
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  struct IRdlsDBConnection *v22; // [rsp+60h] [rbp-A0h] BYREF
  int v23; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v24; // [rsp+78h] [rbp-88h]
  unsigned int v25; // [rsp+2D4h] [rbp+1D4h]
  _BYTE v26[604]; // [rsp+300h] [rbp+200h] BYREF
  unsigned int v27; // [rsp+55Ch] [rbp+45Ch]
  _BYTE v28[8]; // [rsp+590h] [rbp+490h] BYREF
  __int64 v29; // [rsp+598h] [rbp+498h]
  __int64 v30; // [rsp+5B8h] [rbp+4B8h]
  int v31; // [rsp+5C0h] [rbp+4C0h]
  char v32; // [rsp+DC4h] [rbp+CC4h]
  _BYTE v33[4]; // [rsp+13E0h] [rbp+12E0h] BYREF
  unsigned int v34; // [rsp+13E4h] [rbp+12E4h]
  __int64 v35; // [rsp+13E8h] [rbp+12E8h]
  __int64 v36; // [rsp+1408h] [rbp+1308h]
  int v37; // [rsp+1410h] [rbp+1310h]

  memset_0(v26, 0, 0x288u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ce43658c7bd53a1a24e5eea50cc93687_Traceguids);
  v22 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v0 = 30;
  hKey = 0;
  v1 = time(0);
  if ( !RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\TermServLicensing\\Parameters",
          0,
          0,
          0,
          0x20019u,
          0,
          &hKey,
          0) )
  {
    *(_DWORD *)Data = 0;
    *(_DWORD *)&Data[4] = 4;
    Value = RegQueryValueExW(hKey, L"EffectiveDaysToDeleteTemporary", 0, 0, Data, (LPDWORD)&Data[4]);
    RegCloseKey(hKey);
    if ( !Value )
    {
      v3 = *(_DWORD *)Data;
      if ( *(_DWORD *)Data < 7u )
        v3 = 30;
      v0 = v3;
    }
  }
  v4 = 86400 * v0;
  if ( v1 <= 86400 * v0 )
    v4 = 2592000;
  v27 = v1 - v4;
  memset_0(&v23, 0, 0x288u);
  memset_0(v33, 0, 0xE50u);
  memset_0(v28, 0, 0xE50u);
  if ( (unsigned int)AllocateDBHandle(&v22, *(unsigned int *)&g_EnumDbTimeout) )
  {
    v6 = g_RdlsDBWorkSpace;
    v7 = v22;
    if ( *(_DWORD *)&g_bUseMultipleConnections )
      v6 = v22;
    TLSDBLockKeyPackTable(v6);
    v8 = g_RdlsDBWorkSpace;
    if ( *(_DWORD *)&g_bUseMultipleConnections )
      v8 = v7;
    TLSDBLockLicenseTable(v8);
    CleanupStatement(v7);
    v9 = (int)g_RdlsDBWorkSpace;
    if ( *(_DWORD *)&g_bUseMultipleConnections )
      v9 = (int)v7;
    if ( (unsigned int)TLSDBLicenseEnumBeginEx(v9, 1, 256, (unsigned int)v26, 4, 0) )
    {
      v10 = g_RdlsDBWorkSpace;
      if ( *(_DWORD *)&g_bUseMultipleConnections )
        v10 = v7;
      TLSDBUnlockLicenseTable(v10);
      v11 = g_RdlsDBWorkSpace;
      if ( *(_DWORD *)&g_bUseMultipleConnections )
        v11 = v7;
      TLSDBUnlockKeyPackTable(v11);
      FREEDBHANDLE(v7);
      v5 = 4096;
    }
    else
    {
      while ( 1 )
      {
        v12 = g_RdlsDBWorkSpace;
        if ( *(_DWORD *)&g_bUseMultipleConnections )
          v12 = v7;
        v5 = TLSDBLicenseEnumNextEx(v12, 1, 1, &v23);
        v14 = (__int64 *)g_RdlsDBWorkSpace;
        if ( v5 )
          break;
        v34 = v24;
        if ( *(_DWORD *)&g_bUseMultipleConnections )
          v14 = (__int64 *)v7;
        if ( !(unsigned int)TLSDBKeyPackFind(v14, v13, 0x10000, (__int64)v33, (__int64)v28) && v32 == 4 )
        {
          BEGIN_TRANSACTION(v7);
          v15 = g_RdlsDBWorkSpace;
          if ( *(_DWORD *)&g_bUseMultipleConnections )
            v15 = v7;
          if ( (unsigned int)TLSDBDeleteEnumeratedLicense(v15, &v23) )
            goto LABEL_39;
          v16 = g_RdlsDBWorkSpace;
          if ( *(_DWORD *)&g_bUseMultipleConnections )
            v16 = v7;
          if ( (unsigned int)TLSDBReturnLicenseToKeyPack(v16, v24, v25) )
LABEL_39:
            ROLLBACK_TRANSACTION(v7);
          else
            COMMIT_TRANSACTION(v7);
        }
      }
      if ( *(_DWORD *)&g_bUseMultipleConnections )
        v14 = (__int64 *)v7;
      TLSDBLicenseEnumEnd(v14);
      v17 = g_RdlsDBWorkSpace;
      if ( *(_DWORD *)&g_bUseMultipleConnections )
        v17 = v7;
      TLSDBUnlockLicenseTable(v17);
      v18 = g_RdlsDBWorkSpace;
      if ( *(_DWORD *)&g_bUseMultipleConnections )
        v18 = v7;
      TLSDBUnlockKeyPackTable(v18);
      FREEDBHANDLE(v7);
    }
  }
  else
  {
    v5 = -1073676261;
  }
  __LicensePack::~__LicensePack((__LicensePack *)v28);
  __LicensePack::~__LicensePack((__LicensePack *)v33);
  return v5;
}

```

## disassembly

```asm
0x18004c550  mov     rax, rsp
0x18004c553  mov     [rax+8], rbx
0x18004c557  mov     [rax+10h], rsi
0x18004c55b  mov     [rax+18h], rdi
0x18004c55f  mov     [rax+20h], r14
0x18004c563  push    rbp
0x18004c564  lea     rbp, [rax-2148h]
0x18004c56b  mov     eax, 2240h
0x18004c570  call    _alloca_probe
0x18004c575  sub     rsp, rax
0x18004c578  mov     rax, cs:__security_cookie
0x18004c57f  xor     rax, rsp
0x18004c582  mov     [rbp+2140h+var_10], rax
0x18004c589  xor     edx, edx; Val
0x18004c58b  mov     r8d, 288h; Size
0x18004c591  lea     rcx, [rbp+2140h+var_1F40]; void *
0x18004c598  call    memset_0
0x18004c59d  lea     rax, WPP_GLOBAL_Control
0x18004c5a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c5ab  cmp     rcx, rax
0x18004c5ae  jz      short loc_18004C5CB
0x18004c5b0  test    byte ptr [rcx+1Ch], 10h
0x18004c5b4  jz      short loc_18004C5CB
0x18004c5b6  mov     edx, 0Ah
0x18004c5bb  lea     r8, WPP_ce43658c7bd53a1a24e5eea50cc93687_Traceguids
0x18004c5c2  mov     rcx, [rcx+10h]
0x18004c5c6  call    WPP_SF_
0x18004c5cb  xor     r14d, r14d
0x18004c5ce  mov     [rsp+2240h+var_21E0], r14
0x18004c5d3  mov     [rbp+2140h+var_E58], r14
0x18004c5da  mov     [rbp+2140h+var_E38], r14
0x18004c5e1  mov     [rbp+2140h+var_E30], r14d
0x18004c5e8  mov     [rbp+2140h+var_1CA8], r14
0x18004c5ef  mov     [rbp+2140h+var_1C88], r14
0x18004c5f6  mov     [rbp+2140h+var_1C80], r14d
0x18004c5fd  lea     edi, [r14+1Eh]
0x18004c601  mov     [rsp+2240h+hKey], r14
0x18004c606  xor     ecx, ecx; Time
0x18004c608  call    cs:__imp_time
0x18004c60f  nop     dword ptr [rax+rax+00h]
0x18004c614  mov     rsi, rax
0x18004c617  mov     [rsp+2240h+lpdwDisposition], r14; lpdwDisposition
0x18004c61c  lea     rax, [rsp+2240h+hKey]
0x18004c621  mov     [rsp+2240h+phkResult], rax; phkResult
0x18004c626  mov     [rsp+2240h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18004c62b  mov     [rsp+2240h+samDesired], 20019h; samDesired
0x18004c633  mov     [rsp+2240h+dwOptions], r14d; dwOptions
0x18004c638  xor     r9d, r9d; lpClass
0x18004c63b  xor     r8d, r8d; Reserved
0x18004c63e  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Te"...
0x18004c645  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004c64c  call    cs:__imp_RegCreateKeyExW
0x18004c653  nop     dword ptr [rax+rax+00h]
0x18004c658  test    eax, eax
0x18004c65a  jnz     short loc_18004C6BE
0x18004c65c  mov     dword ptr [rsp+2240h+Data], r14d
0x18004c661  mov     dword ptr [rsp+2240h+Data+4], 4
0x18004c669  lea     rax, [rsp+2240h+Data+4]
0x18004c66e  mov     qword ptr [rsp+2240h+samDesired], rax; lpcbData
0x18004c673  lea     rax, [rsp+2240h+Data]
0x18004c678  mov     qword ptr [rsp+2240h+dwOptions], rax; lpData
0x18004c67d  xor     r9d, r9d; lpType
0x18004c680  xor     r8d, r8d; lpReserved
0x18004c683  lea     rdx, aEffectivedayst; "EffectiveDaysToDeleteTemporary"
0x18004c68a  mov     rcx, [rsp+2240h+hKey]; hKey
0x18004c68f  call    cs:__imp_RegQueryValueExW
0x18004c696  nop     dword ptr [rax+rax+00h]
0x18004c69b  mov     ebx, eax
0x18004c69d  mov     rcx, [rsp+2240h+hKey]; hKey
0x18004c6a2  call    cs:__imp_RegCloseKey
0x18004c6a9  nop     dword ptr [rax+rax+00h]
0x18004c6ae  test    ebx, ebx
0x18004c6b0  jnz     short loc_18004C6BE
0x18004c6b2  mov     eax, dword ptr [rsp+2240h+Data]
0x18004c6b6  cmp     eax, 7
0x18004c6b9  cmovb   eax, edi
0x18004c6bc  mov     edi, eax
0x18004c6be  imul    eax, edi, 15180h
0x18004c6c4  mov     ecx, 278D00h
0x18004c6c9  cmp     esi, eax
0x18004c6cb  cmovbe  eax, ecx
0x18004c6ce  sub     esi, eax
0x18004c6d0  mov     [rbp+2140h+var_1CE4], esi
0x18004c6d6  xor     edx, edx; Val
0x18004c6d8  mov     r8d, 288h; Size
0x18004c6de  lea     rcx, [rsp+2240h+var_21D0]; void *
0x18004c6e3  call    memset_0
0x18004c6e8  mov     ebx, 0E50h
0x18004c6ed  mov     r8d, ebx; Size
0x18004c6f0  xor     edx, edx; Val
0x18004c6f2  lea     rcx, [rbp+2140h+var_E60]; void *
0x18004c6f9  call    memset_0
0x18004c6fe  mov     r8d, ebx; Size
0x18004c701  xor     edx, edx; Val
0x18004c703  lea     rcx, [rbp+2140h+var_1CB0]; void *
0x18004c70a  call    memset_0
0x18004c70f  mov     edx, cs:?g_EnumDbTimeout@@3KA; unsigned int
0x18004c715  lea     rcx, [rsp+2240h+var_21E0]; struct IRdlsDBConnection **
0x18004c71a  call    ?AllocateDBHandle@@YAHPEAPEAVIRdlsDBConnection@@K@Z; AllocateDBHandle(IRdlsDBConnection * *,ulong)
0x18004c71f  test    eax, eax
0x18004c721  jnz     short loc_18004C72D
0x18004c723  mov     edi, 0C001001Bh
0x18004c728  jmp     loc_18004C905
0x18004c72d  mov     rcx, cs:?g_RdlsDBWorkSpace@@3PEAVIRdlsDBConnection@@EA; IRdlsDBConnection * g_RdlsDBWorkSpace
0x18004c734  mov     rbx, [rsp+2240h+var_21E0]
0x18004c739  cmp     cs:?g_bUseMultipleConnections@@3KA, r14d; ulong g_bUseMultipleConnections
0x18004c740  cmovnz  rcx, rbx
0x18004c744  call    TLSDBLockKeyPackTable
0x18004c749  mov     rcx, cs:?g_RdlsDBWorkSpace@@3PEAVIRdlsDBConnection@@EA; IRdlsDBConnection * g_RdlsDBWorkSpace
0x18004c750  cmp     cs:?g_bUseMultipleConnections@@3KA, r14d; ulong g_bUseMultipleConnections
0x18004c757  cmovnz  rcx, rbx
0x18004c75b  call    TLSDBLockLicenseTable
0x18004c760  mov     rcx, rbx; struct IRdlsDBConnection *
0x18004c763  call    ?CleanupStatement@@YAXPEAVIRdlsDBConnection@@@Z; CleanupStatement(IRdlsDBConnection *)
0x18004c768  mov     rcx, cs:?g_RdlsDBWorkSpace@@3PEAVIRdlsDBConnection@@EA; IRdlsDBConnection * g_RdlsDBWorkSpace
0x18004c76f  cmp     cs:?g_bUseMultipleConnections@@3KA, r14d; ulong g_bUseMultipleConnections
0x18004c776  cmovnz  rcx, rbx
0x18004c77a  mov     [rsp+2240h+samDesired], r14d
0x18004c77f  mov     [rsp+2240h+dwOptions], 4
0x18004c787  lea     r9, [rbp+2140h+var_1F40]
0x18004c78e  mov     esi, 1
0x18004c793  mov     r8d, 100h
0x18004c799  mov     edx, esi
0x18004c79b  call    TLSDBLicenseEnumBeginEx
0x18004c7a0  test    eax, eax
0x18004c7a2  jz      short loc_18004C7E4
0x18004c7a4  mov     rcx, cs:?g_RdlsDBWorkSpace@@3PEAVIRdlsDBConnection@@EA; IRdlsDBConnection * g_RdlsDBWorkSpace
0x18004c7ab  cmp     cs:?g_bUseMultipleConnections@@3KA, r14d; ulong g_bUseMultipleConnections
0x18004c7b2  cmovnz  rcx, rbx
0x18004c7b6  call    TLSDBUnlockLicenseTable
0x18004c7bb  mov     rcx, cs:?g_RdlsDBWorkSpace@@3PEAVIRdlsDBConnection@@EA; IRdlsDBConnection * g_RdlsDBWorkSpace
0x18004c7c2  cmp     cs:?g_bUseMultipleConnections@@3KA, r14d; ulong g_bUseMultipleConnections
0x18004c7c9  cmovnz  rcx, rbx
0x18004c7cd  call    TLSDBUnlockKeyPackTable
0x18004c7d2  mov     rcx, rbx; struct IRdlsDBConnection *
0x18004c7d5  call    ?FREEDBHANDLE@@YAXPEAVIRdlsDBConnection@@@Z; FREEDBHANDLE(IRdlsDBConnection *)
0x18004c7da  mov     edi, 1000h
0x18004c7df  jmp     loc_18004C905
0x18004c7e4  mov     rcx, cs:?g_RdlsDBWorkSpace@@3PEAVIRdlsDBConnection@@EA; IRdlsDBConnection * g_RdlsDBWorkSpace
0x18004c7eb  cmp     cs:?g_bUseMultipleConnections@@3KA, r14d; ulong g_bUseMultipleConnections
0x18004c7f2  cmovnz  rcx, rbx
0x18004c7f6  lea     r9, [rsp+2240h+var_21D0]
0x18004c7fb  mov     r8d, esi
0x18004c7fe  mov     edx, esi
0x18004c800  call    TLSDBLicenseEnumNextEx
0x18004c805  mov     edi, eax
0x18004c807  mov     rcx, cs:?g_RdlsDBWorkSpace@@3PEAVIRdlsDBConnection@@EA; IRdlsDBConnection * g_RdlsDBWorkSpace
0x18004c80e  test    eax, eax
0x18004c810  jnz     loc_18004C8BE
0x18004c816  mov     eax, [rsp+2240h+var_21C8]
0x18004c81a  mov     [rbp+2140h+var_E5C], eax
0x18004c820  cmp     cs:?g_bUseMultipleConnections@@3KA, r14d; ulong g_bUseMultipleConnections
0x18004c827  cmovnz  rcx, rbx
0x18004c82b  lea     rax, [rbp+2140h+var_1CB0]
0x18004c832  mov     qword ptr [rsp+2240h+dwOptions], rax
0x18004c837  lea     r9, [rbp+2140h+var_E60]
0x18004c83e  mov     r8d, 10000h
0x18004c844  call    TLSDBKeyPackFind
0x18004c849  test    eax, eax
0x18004c84b  jnz     short loc_18004C7E4
0x18004c84d  cmp     [rbp+2140h+var_147C], 4
0x18004c854  jnz     short loc_18004C7E4
0x18004c856  mov     rcx, rbx; struct IRdlsDBConnection *
0x18004c859  call    ?BEGIN_TRANSACTION@@YAXPEAVIRdlsDBConnection@@@Z; BEGIN_TRANSACTION(IRdlsDBConnection *)
0x18004c85e  mov     rcx, cs:?g_RdlsDBWorkSpace@@3PEAVIRdlsDBConnection@@EA; IRdlsDBConnection * g_RdlsDBWorkSpace
0x18004c865  cmp     cs:?g_bUseMultipleConnections@@3KA, r14d; ulong g_bUseMultipleConnections
0x18004c86c  cmovnz  rcx, rbx
0x18004c870  lea     rdx, [rsp+2240h+var_21D0]
0x18004c875  call    TLSDBDeleteEnumeratedLicense
0x18004c87a  test    eax, eax
0x18004c87c  jnz     short loc_18004C8B1
0x18004c87e  mov     rcx, cs:?g_RdlsDBWorkSpace@@3PEAVIRdlsDBConnection@@EA; IRdlsDBConnection * g_RdlsDBWorkSpace
0x18004c885  cmp     cs:?g_bUseMultipleConnections@@3KA, r14d; ulong g_bUseMultipleConnections
0x18004c88c  cmovnz  rcx, rbx
0x18004c890  mov     r8d, [rbp+2140h+var_1F6C]
0x18004c897  mov     edx, [rsp+2240h+var_21C8]
0x18004c89b  call    TLSDBReturnLicenseToKeyPack
0x18004c8a0  test    eax, eax
0x18004c8a2  jnz     short loc_18004C8B1
0x18004c8a4  mov     rcx, rbx; struct IRdlsDBConnection *
0x18004c8a7  call    ?COMMIT_TRANSACTION@@YAXPEAVIRdlsDBConnection@@@Z; COMMIT_TRANSACTION(IRdlsDBConnection *)
0x18004c8ac  jmp     loc_18004C7E4
0x18004c8b1  mov     rcx, rbx; struct IRdlsDBConnection *
0x18004c8b4  call    ?ROLLBACK_TRANSACTION@@YAXPEAVIRdlsDBConnection@@@Z; ROLLBACK_TRANSACTION(IRdlsDBConnection *)
0x18004c8b9  jmp     loc_18004C7E4
0x18004c8be  cmp     cs:?g_bUseMultipleConnections@@3KA, r14d; ulong g_bUseMultipleConnections
0x18004c8c5  cmovnz  rcx, rbx
0x18004c8c9  call    TLSDBLicenseEnumEnd
0x18004c8ce  mov     rcx, cs:?g_RdlsDBWorkSpace@@3PEAVIRdlsDBConnection@@EA; IRdlsDBConnection * g_RdlsDBWorkSpace
0x18004c8d5  cmp     cs:?g_bUseMultipleConnections@@3KA, r14d; ulong g_bUseMultipleConnections
0x18004c8dc  cmovnz  rcx, rbx
0x18004c8e0  call    TLSDBUnlockLicenseTable
0x18004c8e5  mov     rcx, cs:?g_RdlsDBWorkSpace@@3PEAVIRdlsDBConnection@@EA; IRdlsDBConnection * g_RdlsDBWorkSpace
0x18004c8ec  cmp     cs:?g_bUseMultipleConnections@@3KA, r14d; ulong g_bUseMultipleConnections
0x18004c8f3  cmovnz  rcx, rbx
0x18004c8f7  call    TLSDBUnlockKeyPackTable
0x18004c8fc  mov     rcx, rbx; struct IRdlsDBConnection *
0x18004c8ff  call    ?FREEDBHANDLE@@YAXPEAVIRdlsDBConnection@@@Z; FREEDBHANDLE(IRdlsDBConnection *)
0x18004c904  nop
0x18004c905  lea     rcx, [rbp+2140h+var_1CB0]; this
0x18004c90c  call    ??1__LicensePack@@QEAA@XZ; __LicensePack::~__LicensePack(void)
0x18004c911  nop
0x18004c912  lea     rcx, [rbp+2140h+var_E60]; this
0x18004c919  call    ??1__LicensePack@@QEAA@XZ; __LicensePack::~__LicensePack(void)
0x18004c91e  mov     eax, edi
0x18004c920  mov     rcx, [rbp+2140h+var_10]
0x18004c927  xor     rcx, rsp; StackCookie
0x18004c92a  call    __security_check_cookie
0x18004c92f  lea     r11, [rsp+2240h+var_s0]
0x18004c937  mov     rbx, [r11+10h]
0x18004c93b  mov     rsi, [r11+18h]
0x18004c93f  mov     rdi, [r11+20h]
0x18004c943  mov     r14, [r11+28h]
0x18004c947  mov     rsp, r11
0x18004c94a  pop     rbp
0x18004c94b  retn
```
