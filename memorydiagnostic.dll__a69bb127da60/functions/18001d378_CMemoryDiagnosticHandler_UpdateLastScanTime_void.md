# CMemoryDiagnosticHandler::UpdateLastScanTime(void)

- ea: `0x18001d378`
- end: `0x18001d4eb`
- name: `?UpdateLastScanTime@CMemoryDiagnosticHandler@@AEAAJXZ`
- size: `371`
- prototype: `__int64 __fastcall(CMemoryDiagnosticHandler *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001d7a0`

## callees

- `0x18001d378`
- `0x18001e24c`
- `0x18001e290`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001d3a4`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001d3a4`
- `ADVAPI32!RegOpenKeyExW` at `0x18001d3fc`
- `ADVAPI32!RegOpenKeyExW` at `0x18001d3fc`
- `ADVAPI32!RegSetValueExW` at `0x18001d435`
- `ADVAPI32!RegSetValueExW` at `0x18001d435`
- `ADVAPI32!RegCloseKey` at `0x18001d4b1`
- `ADVAPI32!RegCloseKey` at `0x18001d4b1`

## pseudocode

```c
__int64 __fastcall CMemoryDiagnosticHandler::UpdateLastScanTime(CMemoryDiagnosticHandler *this)
{
  __int64 v1; // r8
  LSTATUS v2; // eax
  __int64 v3; // r8
  unsigned int v4; // ebx
  CMemoryDiagnosticHandler *v5; // rcx
  __int64 v6; // rdx
  struct _FILETIME Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  struct _FILETIME v10; // [rsp+50h] [rbp+18h] BYREF

  v10 = 0;
  Data = 0;
  hKey = 0;
  GetSystemTimeAsFileTime(&v10);
  Data = v10;
  if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_P)(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, v1, v10);
  }
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\MemoryDiagnostic", 0, 2u, &hKey);
  if ( v2 )
  {
    if ( v2 > 0 )
    {
      v4 = (unsigned __int16)v2 | 0x80070000;
      goto LABEL_17;
    }
  }
  else if ( hKey )
  {
    v2 = RegSetValueExW(hKey, L"LastScanTime", 0, 0xBu, (const BYTE *)&Data, 8u);
    if ( !v2 )
    {
      v4 = 0;
LABEL_21:
      v5 = WPP_GLOBAL_Control;
      goto LABEL_22;
    }
    if ( v2 > 0 )
      v4 = (unsigned __int16)v2 | 0x80070000;
    else
      v4 = v2;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 80;
LABEL_20:
      WPP_SF_d(*((_QWORD *)v5 + 2), v6, v3, (unsigned int)v2);
      goto LABEL_21;
    }
    goto LABEL_22;
  }
  v4 = v2;
LABEL_17:
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v6 = 79;
    goto LABEL_20;
  }
LABEL_22:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v5 = WPP_GLOBAL_Control;
  }
  if ( (v4 & 0x80000000) != 0 && v5 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v5 + 2), 10, v3, v4);
  return v4;
}

```

## disassembly

```asm
0x18001d378  mov     rax, rsp
0x18001d37b  mov     [rax+20h], rbx
0x18001d37f  mov     [rax+8], rcx
0x18001d383  push    rsi
0x18001d384  sub     rsp, 30h
0x18001d388  lea     rcx, [rax+18h]; lpSystemTimeAsFileTime
0x18001d38c  mov     qword ptr [rax+18h], 0
0x18001d394  mov     qword ptr [rax+8], 0
0x18001d39c  mov     qword ptr [rax+10h], 0
0x18001d3a4  call    cs:__imp_GetSystemTimeAsFileTime
0x18001d3aa  mov     r9, [rsp+38h+arg_10]
0x18001d3af  mov     [rsp+38h+Data], r9
0x18001d3b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d3bb  lea     rsi, WPP_GLOBAL_Control
0x18001d3c2  cmp     rcx, rsi
0x18001d3c5  jz      short loc_18001D3DB
0x18001d3c7  test    byte ptr [rcx+1Ch], 4
0x18001d3cb  jz      short loc_18001D3DB
0x18001d3cd  mov     rcx, [rcx+10h]
0x18001d3d1  mov     edx, 4Eh ; 'N'
0x18001d3d6  call    WPP_SF_P
0x18001d3db  lea     rax, [rsp+38h+hKey]
0x18001d3e0  mov     r9d, 2; samDesired
0x18001d3e6  xor     r8d, r8d; ulOptions
0x18001d3e9  mov     [rsp+38h+phkResult], rax; phkResult
0x18001d3ee  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\MemoryDiagnostic"
0x18001d3f5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d3fc  call    cs:__imp_RegOpenKeyExW
0x18001d402  test    eax, eax
0x18001d404  jnz     short loc_18001D46B
0x18001d406  mov     r10, [rsp+38h+hKey]
0x18001d40b  test    r10, r10
0x18001d40e  jz      short loc_18001D46D
0x18001d410  lea     rax, [rsp+38h+Data]
0x18001d415  mov     [rsp+38h+cbData], 8; cbData
0x18001d41d  mov     r9d, 0Bh; dwType
0x18001d423  mov     [rsp+38h+phkResult], rax; lpData
0x18001d428  xor     r8d, r8d; Reserved
0x18001d42b  lea     rdx, aLastscantime; "LastScanTime"
0x18001d432  mov     rcx, r10; hKey
0x18001d435  call    cs:__imp_RegSetValueExW
0x18001d43b  test    eax, eax
0x18001d43d  jz      short loc_18001D467
0x18001d43f  jg      short loc_18001D445
0x18001d441  mov     ebx, eax
0x18001d443  jmp     short loc_18001D44E
0x18001d445  movzx   ebx, ax
0x18001d448  or      ebx, 80070000h
0x18001d44e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d455  cmp     rcx, rsi
0x18001d458  jz      short loc_18001D4A4
0x18001d45a  test    byte ptr [rcx+1Ch], 1
0x18001d45e  jz      short loc_18001D4A4
0x18001d460  mov     edx, 50h ; 'P'
0x18001d465  jmp     short loc_18001D491
0x18001d467  xor     ebx, ebx
0x18001d469  jmp     short loc_18001D49D
0x18001d46b  jg      short loc_18001D471
0x18001d46d  mov     ebx, eax
0x18001d46f  jmp     short loc_18001D47A
0x18001d471  movzx   ebx, ax
0x18001d474  or      ebx, 80070000h
0x18001d47a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d481  cmp     rcx, rsi
0x18001d484  jz      short loc_18001D4A4
0x18001d486  test    byte ptr [rcx+1Ch], 1
0x18001d48a  jz      short loc_18001D4A4
0x18001d48c  mov     edx, 4Fh ; 'O'
0x18001d491  mov     rcx, [rcx+10h]
0x18001d495  mov     r9d, eax
0x18001d498  call    WPP_SF_d
0x18001d49d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4a4  mov     r10, [rsp+38h+hKey]
0x18001d4a9  test    r10, r10
0x18001d4ac  jz      short loc_18001D4BE
0x18001d4ae  mov     rcx, r10; hKey
0x18001d4b1  call    cs:__imp_RegCloseKey
0x18001d4b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4be  test    ebx, ebx
0x18001d4c0  jns     short loc_18001D4DE
0x18001d4c2  cmp     rcx, rsi
0x18001d4c5  jz      short loc_18001D4DE
0x18001d4c7  test    byte ptr [rcx+1Ch], 1
0x18001d4cb  jz      short loc_18001D4DE
0x18001d4cd  mov     rcx, [rcx+10h]
0x18001d4d1  mov     edx, 0Ah
0x18001d4d6  mov     r9d, ebx
0x18001d4d9  call    WPP_SF_d
0x18001d4de  mov     eax, ebx
0x18001d4e0  mov     rbx, [rsp+38h+arg_18]
0x18001d4e5  add     rsp, 30h
0x18001d4e9  pop     rsi
0x18001d4ea  retn
```
