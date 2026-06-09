# LoadActivityLoggingSettings

- ea: `0x14007d36c`
- end: `0x14007d649`
- name: `LoadActivityLoggingSettings`
- size: `733`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140047c20`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140065dbc`
- `0x14006f808`
- `0x140070684`
- `0x1400708c4`
- `0x14007d36c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14007d634`
- `ADVAPI32!RegCloseKey` at `0x14007d634`
- `KERNEL32!GetLastError` at `0x14007d3da`
- `KERNEL32!GetLastError` at `0x14007d3da`
- `KERNEL32!lstrcmpW` at `0x14007d5ea`
- `KERNEL32!lstrcmpW` at `0x14007d5ea`

## string_xrefs

- `0x14007d428`: `LogIncoming`

## pseudocode

```c
__int64 __fastcall LoadActivityLoggingSettings(__int64 a1)
{
  HKEY v2; // rax
  HKEY v3; // rdi
  DWORD LastError; // eax
  DWORD v5; // ebx
  unsigned int v7; // esi
  int RegistryDwordDefault; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  BYTE *RegistryStringValue; // rax
  DWORD v15; // [rsp+20h] [rbp-18h]
  int Data; // [rsp+78h] [rbp+40h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
  }
  v2 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\ActivityLogging", 0, 0x2001Fu);
  v3 = v2;
  if ( v2 )
  {
    v7 = 0;
    *(_DWORD *)a1 = 24;
    Data = 0;
    RegistryDwordDefault = GetRegistryDwordDefault(v2, L"LogIncoming", (BYTE *)&Data, 0);
    *(_DWORD *)(a1 + 4) = RegistryDwordDefault != 0 ? Data : 0;
    Data = 0;
    v9 = GetRegistryDwordDefault(v3, L"LogOutgoing", (BYTE *)&Data, 0);
    *(_DWORD *)(a1 + 8) = v9 != 0 ? Data : 0;
    Data = 0;
    v10 = GetRegistryDwordDefault(v3, L"LogLimitCriteria", (BYTE *)&Data, 0);
    *(_DWORD *)(a1 + 24) = v10 != 0 ? Data : 0;
    Data = 0;
    v11 = GetRegistryDwordDefault(v3, L"LogSizeLimit", (BYTE *)&Data, 0);
    *(_DWORD *)(a1 + 28) = v11 != 0 ? Data : 0;
    Data = 0;
    v12 = GetRegistryDwordDefault(v3, L"LogAgeLimit", (BYTE *)&Data, 0);
    *(_DWORD *)(a1 + 32) = v12 != 0 ? Data : 0;
    Data = 0;
    v13 = GetRegistryDwordDefault(v3, L"LogLimitReachedAction", (BYTE *)&Data, 0);
    *(_DWORD *)(a1 + 36) = v13 != 0 ? Data : 0;
    if ( !*(_DWORD *)(a1 + 28) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, 50);
      }
      *(_DWORD *)(a1 + 28) = 50;
    }
    if ( !*(_DWORD *)(a1 + 32) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, 1);
      }
      *(_DWORD *)(a1 + 32) = 1;
    }
    if ( *(_DWORD *)(a1 + 24) >= 3u )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
      }
      *(_DWORD *)(a1 + 24) = 0;
    }
    if ( *(_DWORD *)(a1 + 36) >= 2u )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
      }
      *(_DWORD *)(a1 + 36) = 0;
    }
    RegistryStringValue = GetRegistryStringValue(v3, 1u, L"DBFile", L"\\\\\\", v15);
    *(_QWORD *)(a1 + 16) = RegistryStringValue;
    if ( !lstrcmpW(L"\\\\\\", (LPCWSTR)RegistryStringValue) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
      }
      v7 = 13;
      pMemFree(*(LPVOID *)(a1 + 16));
      *(_QWORD *)(a1 + 16) = 0;
    }
    RegCloseKey(v3);
    return v7;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, LastError);
    }
    return v5;
  }
}

```

## disassembly

```asm
0x14007d36c  push    rbp
0x14007d36e  push    rbx
0x14007d36f  push    rsi
0x14007d370  push    rdi
0x14007d371  push    r12
0x14007d373  push    r15
0x14007d375  mov     rbp, rsp
0x14007d378  sub     rsp, 38h
0x14007d37c  mov     rbx, rcx
0x14007d37f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d386  lea     r15, WPP_GLOBAL_Control
0x14007d38d  lea     r12, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007d394  cmp     rcx, r15
0x14007d397  jz      short loc_14007D3B6
0x14007d399  test    byte ptr [rcx+1Ch], 2
0x14007d39d  jz      short loc_14007D3B6
0x14007d39f  cmp     byte ptr [rcx+19h], 5
0x14007d3a3  jb      short loc_14007D3B6
0x14007d3a5  mov     rcx, [rcx+10h]
0x14007d3a9  mov     edx, 3Ah ; ':'
0x14007d3ae  mov     r8, r12
0x14007d3b1  call    WPP_SF_
0x14007d3b6  mov     r9d, 2001Fh
0x14007d3bc  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\Fax\\ActivityLoggi"...
0x14007d3c3  xor     r8d, r8d
0x14007d3c6  mov     rcx, 0FFFFFFFF80000002h
0x14007d3cd  call    OpenRegistryKey
0x14007d3d2  mov     rdi, rax
0x14007d3d5  test    rax, rax
0x14007d3d8  jnz     short loc_14007D413
0x14007d3da  call    cs:__imp_GetLastError
0x14007d3e0  mov     ebx, eax
0x14007d3e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d3e9  cmp     rcx, r15
0x14007d3ec  jz      short loc_14007D40C
0x14007d3ee  test    byte ptr [rcx+1Ch], 2
0x14007d3f2  jz      short loc_14007D40C
0x14007d3f4  cmp     byte ptr [rcx+19h], 2
0x14007d3f8  jb      short loc_14007D40C
0x14007d3fa  mov     rcx, [rcx+10h]
0x14007d3fe  lea     edx, [rdi+3Bh]
0x14007d401  mov     r9d, eax
0x14007d404  mov     r8, r12
0x14007d407  call    WPP_SF_d
0x14007d40c  mov     eax, ebx
0x14007d40e  jmp     loc_14007D63C
0x14007d413  xor     esi, esi
0x14007d415  mov     dword ptr [rbx], 18h
0x14007d41b  xor     r9d, r9d
0x14007d41e  mov     [rbp+Data], esi
0x14007d421  lea     r8, [rbp+Data]; lpData
0x14007d425  mov     rcx, rdi; hKey
0x14007d428  lea     rdx, aLogincoming; "LogIncoming"
0x14007d42f  call    GetRegistryDwordDefault
0x14007d434  neg     eax
0x14007d436  lea     r8, [rbp+Data]; lpData
0x14007d43a  lea     rdx, aLogoutgoing; "LogOutgoing"
0x14007d441  sbb     ecx, ecx
0x14007d443  xor     r9d, r9d
0x14007d446  and     ecx, [rbp+Data]
0x14007d449  mov     [rbx+4], ecx
0x14007d44c  mov     rcx, rdi; hKey
0x14007d44f  mov     [rbp+Data], esi
0x14007d452  call    GetRegistryDwordDefault
0x14007d457  neg     eax
0x14007d459  lea     r8, [rbp+Data]; lpData
0x14007d45d  lea     rdx, aLoglimitcriter; "LogLimitCriteria"
0x14007d464  sbb     ecx, ecx
0x14007d466  xor     r9d, r9d
0x14007d469  and     ecx, [rbp+Data]
0x14007d46c  mov     [rbx+8], ecx
0x14007d46f  mov     rcx, rdi; hKey
0x14007d472  mov     [rbp+Data], esi
0x14007d475  call    GetRegistryDwordDefault
0x14007d47a  neg     eax
0x14007d47c  lea     r8, [rbp+Data]; lpData
0x14007d480  lea     rdx, aLogsizelimit; "LogSizeLimit"
0x14007d487  sbb     ecx, ecx
0x14007d489  xor     r9d, r9d
0x14007d48c  and     ecx, [rbp+Data]
0x14007d48f  mov     [rbx+18h], ecx
0x14007d492  mov     rcx, rdi; hKey
0x14007d495  mov     [rbp+Data], esi
0x14007d498  call    GetRegistryDwordDefault
0x14007d49d  neg     eax
0x14007d49f  lea     r8, [rbp+Data]; lpData
0x14007d4a3  lea     rdx, aLogagelimit; "LogAgeLimit"
0x14007d4aa  sbb     ecx, ecx
0x14007d4ac  xor     r9d, r9d
0x14007d4af  and     ecx, [rbp+Data]
0x14007d4b2  mov     [rbx+1Ch], ecx
0x14007d4b5  mov     rcx, rdi; hKey
0x14007d4b8  mov     [rbp+Data], esi
0x14007d4bb  call    GetRegistryDwordDefault
0x14007d4c0  neg     eax
0x14007d4c2  lea     r8, [rbp+Data]; lpData
0x14007d4c6  lea     rdx, aLoglimitreache; "LogLimitReachedAction"
0x14007d4cd  sbb     ecx, ecx
0x14007d4cf  xor     r9d, r9d
0x14007d4d2  and     ecx, [rbp+Data]
0x14007d4d5  mov     [rbx+20h], ecx
0x14007d4d8  mov     rcx, rdi; hKey
0x14007d4db  mov     [rbp+Data], esi
0x14007d4de  call    GetRegistryDwordDefault
0x14007d4e3  neg     eax
0x14007d4e5  sbb     ecx, ecx
0x14007d4e7  and     ecx, [rbp+Data]
0x14007d4ea  mov     [rbx+24h], ecx
0x14007d4ed  cmp     [rbx+1Ch], esi
0x14007d4f0  jnz     short loc_14007D524
0x14007d4f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d4f9  cmp     rcx, r15
0x14007d4fc  jz      short loc_14007D51D
0x14007d4fe  test    byte ptr [rcx+1Ch], 2
0x14007d502  jz      short loc_14007D51D
0x14007d504  cmp     byte ptr [rcx+19h], 2
0x14007d508  jb      short loc_14007D51D
0x14007d50a  mov     rcx, [rcx+10h]
0x14007d50e  lea     edx, [rsi+3Ch]
0x14007d511  lea     r9d, [rsi+32h]
0x14007d515  mov     r8, r12
0x14007d518  call    WPP_SF_d
0x14007d51d  mov     dword ptr [rbx+1Ch], 32h ; '2'
0x14007d524  cmp     [rbx+20h], esi
0x14007d527  jnz     short loc_14007D55D
0x14007d529  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d530  cmp     rcx, r15
0x14007d533  jz      short loc_14007D556
0x14007d535  test    byte ptr [rcx+1Ch], 2
0x14007d539  jz      short loc_14007D556
0x14007d53b  cmp     byte ptr [rcx+19h], 2
0x14007d53f  jb      short loc_14007D556
0x14007d541  mov     rcx, [rcx+10h]
0x14007d545  mov     edx, 3Dh ; '='
0x14007d54a  mov     r8, r12
0x14007d54d  lea     r9d, [rdx-3Ch]
0x14007d551  call    WPP_SF_d
0x14007d556  mov     dword ptr [rbx+20h], 1
0x14007d55d  cmp     dword ptr [rbx+18h], 3
0x14007d561  jb      short loc_14007D58F
0x14007d563  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d56a  cmp     rcx, r15
0x14007d56d  jz      short loc_14007D58C
0x14007d56f  test    byte ptr [rcx+1Ch], 2
0x14007d573  jz      short loc_14007D58C
0x14007d575  cmp     byte ptr [rcx+19h], 2
0x14007d579  jb      short loc_14007D58C
0x14007d57b  mov     rcx, [rcx+10h]
0x14007d57f  mov     edx, 3Eh ; '>'
0x14007d584  mov     r8, r12
0x14007d587  call    WPP_SF_
0x14007d58c  mov     [rbx+18h], esi
0x14007d58f  cmp     dword ptr [rbx+24h], 2
0x14007d593  jb      short loc_14007D5C1
0x14007d595  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d59c  cmp     rcx, r15
0x14007d59f  jz      short loc_14007D5BE
0x14007d5a1  test    byte ptr [rcx+1Ch], 2
0x14007d5a5  jz      short loc_14007D5BE
0x14007d5a7  cmp     byte ptr [rcx+19h], 2
0x14007d5ab  jb      short loc_14007D5BE
0x14007d5ad  mov     rcx, [rcx+10h]
0x14007d5b1  mov     edx, 3Fh ; '?'
0x14007d5b6  mov     r8, r12
0x14007d5b9  call    WPP_SF_
0x14007d5be  mov     [rbx+24h], esi
0x14007d5c1  lea     r9, asc_14008E5E8; "\\\\\\"
0x14007d5c8  mov     edx, 1; dwType
0x14007d5cd  lea     r8, aDbfile; "DBFile"
0x14007d5d4  mov     rcx, rdi; hKey
0x14007d5d7  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x14007d5dc  mov     rdx, rax; lpString2
0x14007d5df  mov     [rbx+10h], rax
0x14007d5e3  lea     rcx, asc_14008E5E8; "\\\\\\"
0x14007d5ea  call    cs:__imp_lstrcmpW
0x14007d5f0  test    eax, eax
0x14007d5f2  jnz     short loc_14007D631
0x14007d5f4  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d5fb  cmp     rcx, r15
0x14007d5fe  jz      short loc_14007D61B
0x14007d600  test    byte ptr [rcx+1Ch], 2
0x14007d604  jz      short loc_14007D61B
0x14007d606  cmp     byte ptr [rcx+19h], 2
0x14007d60a  jb      short loc_14007D61B
0x14007d60c  mov     rcx, [rcx+10h]
0x14007d610  lea     edx, [rax+40h]
0x14007d613  mov     r8, r12
0x14007d616  call    WPP_SF_
0x14007d61b  mov     rcx, [rbx+10h]; lpMem
0x14007d61f  mov     esi, 0Dh
0x14007d624  call    pMemFree
0x14007d629  mov     qword ptr [rbx+10h], 0
0x14007d631  mov     rcx, rdi; hKey
0x14007d634  call    cs:__imp_RegCloseKey
0x14007d63a  mov     eax, esi
0x14007d63c  add     rsp, 38h
0x14007d640  pop     r15
0x14007d642  pop     r12
0x14007d644  pop     rdi
0x14007d645  pop     rsi
0x14007d646  pop     rbx
0x14007d647  pop     rbp
0x14007d648  retn
```
