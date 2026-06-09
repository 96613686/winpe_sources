# EventAccessRemove

- ea: `0x18000bf60`
- end: `0x18000c28d`
- name: `EventAccessRemove`
- size: `813`
- prototype: `ULONG __stdcall(LPGUID Guid)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001008`
- `0x180001560`
- `0x180002ec4`
- `0x180008764`
- `0x18000bf60`
- `0x180013d90`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18000c11a`
- `ntdll!RtlGetPersistedStateLocation` at `0x18000c11a`
- `ntdll!RtlSetLastWin32Error` at `0x18000c236`
- `ntdll!RtlSetLastWin32Error` at `0x18000c236`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000bfd4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000bfd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c21b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c226`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c21b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c226`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c0dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c146`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c0dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c146`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c20c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c20c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c1d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c1d8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000c172`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000c193`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000c172`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000c193`

## string_xrefs

- `0x18000c0ce`: `SYSTEM\CurrentControlSet\Control\WMI\Security`
- `0x18000c0fd`: `ETWSecurityPath`

## pseudocode

```c
ULONG __stdcall EventAccessRemove(LPGUID Guid)
{
  GUID *v2; // rax
  ULONG v3; // ebx
  unsigned int v4; // edx
  LSTATUS v5; // eax
  unsigned int v6; // edx
  LSTATUS v7; // eax
  LSTATUS PersistedStateLocation; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  int v13; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v14[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v15; // [rsp+70h] [rbp-90h]
  int v16; // [rsp+78h] [rbp-88h] BYREF
  char v17; // [rsp+7Ch] [rbp-84h]
  GUID ActivityId; // [rsp+80h] [rbp-80h] BYREF
  GUID v19; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v20; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR v21[16]; // [rsp+C0h] [rbp-40h] BYREF
  GUID *v22; // [rsp+E0h] [rbp-20h]
  __int64 v23; // [rsp+E8h] [rbp-18h]
  WCHAR ValueName[40]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR SubKey[264]; // [rsp+160h] [rbp+60h] BYREF
  BYTE Data[1024]; // [rsp+370h] [rbp+270h] BYREF

  hKey = 0;
  phkResult = 0;
  PersistedStateLocation = 0;
  v13 = 0;
  v16 = 0;
  v17 = 0;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
    EventActivityIdControl(3u, &ActivityId);
  else
    ActivityId = 0;
  v16 = 1;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
  {
    if ( Guid )
    {
      v2 = &v19;
      v19 = *Guid;
    }
    else
    {
      v2 = (GUID *)&v20;
      v20 = 0;
    }
    v22 = v2;
    v23 = 16;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_18001D020,
      (unsigned int)word_180018F9A,
      (unsigned int)&ActivityId,
      0,
      3,
      (__int64)v21);
  }
  v15 = 1;
  v14[0] = &v16;
  v14[1] = &PersistedStateLocation;
  if ( !Guid )
  {
    v3 = 87;
    PersistedStateLocation = 87;
    goto LABEL_26;
  }
  PersistedStateLocation = RegOpenKeyExW(
                             HKEY_LOCAL_MACHINE,
                             L"SYSTEM\\CurrentControlSet\\Control\\WMI\\Security",
                             0,
                             0x2001Fu,
                             &hKey);
  v3 = PersistedStateLocation;
  if ( !PersistedStateLocation )
  {
    PersistedStateLocation = RtlGetPersistedStateLocation(L"ETWSecurityPath", 0, 0, 0, SubKey, 520, &v13);
    if ( PersistedStateLocation
      || (PersistedStateLocation = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20006u, &phkResult)) != 0 )
    {
      PersistedStateLocation = 0;
      phkResult = 0;
    }
    EtwpGuidToString(ValueName, v4, Guid);
    v5 = RegDeleteValueW(hKey, ValueName);
    PersistedStateLocation = v5;
    if ( !phkResult )
      goto LABEL_25;
    if ( v5 == 2 )
    {
      v7 = RegDeleteValueW(phkResult, ValueName);
    }
    else
    {
      cbData = 1024;
      EtwpGuidToString(v21, v6, &DefaultTraceSecurityGuid);
      PersistedStateLocation = RegQueryValueExW(hKey, v21, 0, 0, Data, &cbData);
      if ( PersistedStateLocation )
      {
LABEL_25:
        RegCloseKey(hKey);
        RegCloseKey(phkResult);
        v3 = PersistedStateLocation;
        goto LABEL_26;
      }
      v7 = RegSetValueExW(phkResult, ValueName, 0, 3u, Data, cbData);
    }
    PersistedStateLocation = v7;
    goto LABEL_25;
  }
LABEL_26:
  if ( v3 )
  {
    RtlSetLastWin32Error(v3);
    v3 = PersistedStateLocation;
  }
  if ( v15 )
    lambda_0fcd6be9e76f080246c8a97ce58053ab_::operator()(v14);
  if ( v16 == 1 )
  {
    v16 = 2;
    _tlgWriteActivityAutoStop<16,5>(&dword_18001D020, &ActivityId);
  }
  return v3;
}

```

## disassembly

```asm
0x18000bf60  push    rbp
0x18000bf62  push    rbx
0x18000bf63  push    rsi
0x18000bf64  push    rdi
0x18000bf65  lea     rbp, [rsp-688h]
0x18000bf6d  sub     rsp, 788h
0x18000bf74  mov     rax, cs:__security_cookie
0x18000bf7b  xor     rax, rsp
0x18000bf7e  mov     [rbp+6A0h+var_30], rax
0x18000bf85  mov     eax, cs:dword_18001D020
0x18000bf8b  xor     esi, esi
0x18000bf8d  mov     [rsp+7A0h+hKey], rsi
0x18000bf92  mov     rdi, rcx
0x18000bf95  mov     [rsp+7A0h+var_758], rsi
0x18000bf9a  mov     [rsp+7A0h+var_760], esi
0x18000bf9e  mov     [rsp+7A0h+var_748], esi
0x18000bfa2  mov     [rsp+7A0h+var_728], esi
0x18000bfa6  mov     [rsp+7A0h+var_724], sil
0x18000bfab  cmp     eax, 5
0x18000bfae  jbe     short loc_18000BFDC
0x18000bfb0  mov     rcx, cs:qword_18001D038
0x18000bfb7  mov     rax, cs:qword_18001D030
0x18000bfbe  test    al, 10h
0x18000bfc0  jz      short loc_18000BFDC
0x18000bfc2  mov     rax, rcx
0x18000bfc5  and     eax, 10h
0x18000bfc8  cmp     rax, rcx
0x18000bfcb  jnz     short loc_18000BFDC
0x18000bfcd  lea     rdx, [rbp+6A0h+ActivityId]; ActivityId
0x18000bfd1  lea     ecx, [rsi+3]; ControlCode
0x18000bfd4  call    cs:__imp_EventActivityIdControl
0x18000bfda  jmp     short loc_18000BFE3
0x18000bfdc  xorps   xmm0, xmm0
0x18000bfdf  movups  xmmword ptr [rbp+6A0h+ActivityId.Data1], xmm0
0x18000bfe3  mov     eax, cs:dword_18001D020
0x18000bfe9  mov     [rsp+7A0h+var_728], 1
0x18000bff1  cmp     eax, 5
0x18000bff4  jbe     loc_18000C091
0x18000bffa  mov     rcx, cs:qword_18001D038
0x18000c001  mov     rax, cs:qword_18001D030
0x18000c008  test    al, 10h
0x18000c00a  jz      loc_18000C091
0x18000c010  mov     rax, rcx
0x18000c013  and     eax, 10h
0x18000c016  cmp     rax, rcx
0x18000c019  jnz     short loc_18000C091
0x18000c01b  test    rdi, rdi
0x18000c01e  jz      short loc_18000C02E
0x18000c020  movups  xmm0, xmmword ptr [rdi]
0x18000c023  lea     rax, [rbp+6A0h+var_700]
0x18000c027  movdqu  [rbp+6A0h+var_700], xmm0
0x18000c02c  jmp     short loc_18000C039
0x18000c02e  xorps   xmm0, xmm0
0x18000c031  lea     rax, [rbp+6A0h+var_6F0]
0x18000c035  movups  [rbp+6A0h+var_6F0], xmm0
0x18000c039  cmp     [rsp+7A0h+var_724], sil
0x18000c03e  jz      short loc_18000C05A
0x18000c040  cmp     [rbp+6A0h+var_710], esi
0x18000c043  jnz     short loc_18000C054
0x18000c045  cmp     [rbp+6A0h+var_70C], esi
0x18000c048  jnz     short loc_18000C054
0x18000c04a  cmp     [rbp+6A0h+var_708], esi
0x18000c04d  jnz     short loc_18000C054
0x18000c04f  cmp     [rbp+6A0h+var_704], esi
0x18000c052  jz      short loc_18000C05A
0x18000c054  lea     r9, [rbp+6A0h+var_710]
0x18000c058  jmp     short loc_18000C05D
0x18000c05a  mov     r9, rsi
0x18000c05d  mov     [rbp+6A0h+var_6C0], rax
0x18000c061  lea     r8, [rbp+6A0h+ActivityId]
0x18000c065  lea     rax, [rbp+6A0h+var_6E0]
0x18000c069  mov     [rbp+6A0h+var_6B8], 10h
0x18000c071  mov     [rsp+7A0h+lpcbData], rax
0x18000c076  lea     rdx, word_180018F9A
0x18000c07d  lea     rcx, dword_18001D020
0x18000c084  mov     dword ptr [rsp+7A0h+phkResult], 3
0x18000c08c  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18000c091  mov     [rsp+7A0h+var_730], 1
0x18000c096  lea     rax, [rsp+7A0h+var_728]
0x18000c09b  mov     [rsp+7A0h+var_740], rax
0x18000c0a0  lea     rax, [rsp+7A0h+var_760]
0x18000c0a5  mov     [rsp+7A0h+var_738], rax
0x18000c0aa  test    rdi, rdi
0x18000c0ad  jnz     short loc_18000C0BB
0x18000c0af  lea     ebx, [rdi+57h]
0x18000c0b2  mov     [rsp+7A0h+var_760], ebx
0x18000c0b6  jmp     loc_18000C230
0x18000c0bb  lea     rax, [rsp+7A0h+hKey]
0x18000c0c0  mov     r9d, 2001Fh; samDesired
0x18000c0c6  xor     r8d, r8d; ulOptions
0x18000c0c9  mov     [rsp+7A0h+phkResult], rax; phkResult
0x18000c0ce  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\WMI"...
0x18000c0d5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c0dc  call    cs:__imp_RegOpenKeyExW
0x18000c0e2  mov     [rsp+7A0h+var_760], eax
0x18000c0e6  mov     ebx, eax
0x18000c0e8  test    eax, eax
0x18000c0ea  jnz     loc_18000C230
0x18000c0f0  lea     rax, [rsp+7A0h+var_748]
0x18000c0f5  xor     r9d, r9d
0x18000c0f8  mov     [rsp+7A0h+var_770], rax
0x18000c0fd  lea     rcx, aEtwsecuritypat; "ETWSecurityPath"
0x18000c104  lea     rax, [rbp+6A0h+SubKey]
0x18000c108  mov     dword ptr [rsp+7A0h+lpcbData], 208h
0x18000c110  xor     r8d, r8d
0x18000c113  mov     [rsp+7A0h+phkResult], rax
0x18000c118  xor     edx, edx
0x18000c11a  call    cs:__imp_RtlGetPersistedStateLocation
0x18000c120  mov     [rsp+7A0h+var_760], eax
0x18000c124  test    eax, eax
0x18000c126  jnz     short loc_18000C154
0x18000c128  lea     rax, [rsp+7A0h+var_758]
0x18000c12d  mov     r9d, 20006h; samDesired
0x18000c133  xor     r8d, r8d; ulOptions
0x18000c136  mov     [rsp+7A0h+phkResult], rax; phkResult
0x18000c13b  lea     rdx, [rbp+6A0h+SubKey]; lpSubKey
0x18000c13f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c146  call    cs:__imp_RegOpenKeyExW
0x18000c14c  mov     [rsp+7A0h+var_760], eax
0x18000c150  test    eax, eax
0x18000c152  jz      short loc_18000C15D
0x18000c154  mov     [rsp+7A0h+var_760], esi
0x18000c158  mov     [rsp+7A0h+var_758], rsi
0x18000c15d  mov     r8, rdi; struct _GUID *
0x18000c160  lea     rcx, [rbp+6A0h+ValueName]; unsigned __int16 *
0x18000c164  call    ?EtwpGuidToString@@YAPEAGPEAGKPEBU_GUID@@@Z; EtwpGuidToString(ushort *,ulong,_GUID const *)
0x18000c169  mov     rcx, [rsp+7A0h+hKey]; hKey
0x18000c16e  lea     rdx, [rbp+6A0h+ValueName]; lpValueName
0x18000c172  call    cs:__imp_RegDeleteValueW
0x18000c178  mov     rcx, [rsp+7A0h+var_758]; hKey
0x18000c17d  mov     [rsp+7A0h+var_760], eax
0x18000c181  test    rcx, rcx
0x18000c184  jz      loc_18000C216
0x18000c18a  cmp     eax, 2
0x18000c18d  jnz     short loc_18000C19B
0x18000c18f  lea     rdx, [rbp+6A0h+ValueName]; lpValueName
0x18000c193  call    cs:__imp_RegDeleteValueW
0x18000c199  jmp     short loc_18000C212
0x18000c19b  lea     r8, DefaultTraceSecurityGuid; struct _GUID *
0x18000c1a2  mov     [rsp+7A0h+cbData], 400h
0x18000c1aa  lea     rcx, [rbp+6A0h+var_6E0]; unsigned __int16 *
0x18000c1ae  call    ?EtwpGuidToString@@YAPEAGPEAGKPEBU_GUID@@@Z; EtwpGuidToString(ushort *,ulong,_GUID const *)
0x18000c1b3  mov     rcx, [rsp+7A0h+hKey]; hKey
0x18000c1b8  lea     rax, [rsp+7A0h+cbData]
0x18000c1bd  mov     [rsp+7A0h+lpcbData], rax; lpcbData
0x18000c1c2  lea     rdx, [rbp+6A0h+var_6E0]; lpValueName
0x18000c1c6  lea     rax, [rbp+6A0h+Data]
0x18000c1cd  xor     r9d, r9d; lpType
0x18000c1d0  xor     r8d, r8d; lpReserved
0x18000c1d3  mov     [rsp+7A0h+phkResult], rax; lpData
0x18000c1d8  call    cs:__imp_RegQueryValueExW
0x18000c1de  mov     [rsp+7A0h+var_760], eax
0x18000c1e2  test    eax, eax
0x18000c1e4  jnz     short loc_18000C216
0x18000c1e6  mov     eax, [rsp+7A0h+cbData]
0x18000c1ea  lea     rdx, [rbp+6A0h+ValueName]; lpValueName
0x18000c1ee  mov     rcx, [rsp+7A0h+var_758]; hKey
0x18000c1f3  mov     r9d, 3; dwType
0x18000c1f9  mov     dword ptr [rsp+7A0h+lpcbData], eax; cbData
0x18000c1fd  xor     r8d, r8d; Reserved
0x18000c200  lea     rax, [rbp+6A0h+Data]
0x18000c207  mov     [rsp+7A0h+phkResult], rax; lpData
0x18000c20c  call    cs:__imp_RegSetValueExW
0x18000c212  mov     [rsp+7A0h+var_760], eax
0x18000c216  mov     rcx, [rsp+7A0h+hKey]; hKey
0x18000c21b  call    cs:__imp_RegCloseKey
0x18000c221  mov     rcx, [rsp+7A0h+var_758]; hKey
0x18000c226  call    cs:__imp_RegCloseKey
0x18000c22c  mov     ebx, [rsp+7A0h+var_760]
0x18000c230  test    ebx, ebx
0x18000c232  jz      short loc_18000C240
0x18000c234  mov     ecx, ebx; LastError
0x18000c236  call    cs:__imp_RtlSetLastWin32Error
0x18000c23c  mov     ebx, [rsp+7A0h+var_760]
0x18000c240  cmp     [rsp+7A0h+var_730], sil
0x18000c245  jz      short loc_18000C251
0x18000c247  lea     rcx, [rsp+7A0h+var_740]
0x18000c24c  call    _lambda_0fcd6be9e76f080246c8a97ce58053ab___operator__
0x18000c251  cmp     [rsp+7A0h+var_728], 1
0x18000c256  jnz     short loc_18000C270
0x18000c258  lea     rdx, [rbp+6A0h+ActivityId]
0x18000c25c  mov     [rsp+7A0h+var_728], 2
0x18000c264  lea     rcx, dword_18001D020
0x18000c26b  call    ??$_tlgWriteActivityAutoStop@$0BA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<16,5>(_tlgProvider_t const *,_GUID const *)
0x18000c270  mov     eax, ebx
0x18000c272  mov     rcx, [rbp+6A0h+var_30]
0x18000c279  xor     rcx, rsp; StackCookie
0x18000c27c  call    __security_check_cookie
0x18000c281  add     rsp, 788h
0x18000c288  pop     rdi
0x18000c289  pop     rsi
0x18000c28a  pop     rbx
0x18000c28b  pop     rbp
0x18000c28c  retn
```
