# ReportErrorToDebugOutput(ushort const *,ulong)

- ea: `0x140007110`
- end: `0x14000736d`
- name: `?ReportErrorToDebugOutput@@YAXPEBGK@Z`
- size: `605`
- prototype: `void __fastcall(BYTE *lpData, unsigned int)`
- caller_count: `7`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400011e4`
- `0x140004768`
- `0x1400066d8`
- `0x140007374`
- `0x140007820`
- `0x1400078f0`
- `0x140008690`

## callees

- `0x140003883`
- `0x140003cbc`
- `0x14000669c`
- `0x140007110`
- `0x1400088c0`
- `0x140009820`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1400071c2`
- `ADVAPI32!RegQueryValueExW` at `0x1400071c2`
- `ADVAPI32!RegSetValueExW` at `0x140007298`
- `ADVAPI32!RegSetValueExW` at `0x1400072cc`
- `ADVAPI32!RegSetValueExW` at `0x140007298`
- `ADVAPI32!RegSetValueExW` at `0x1400072cc`
- `ADVAPI32!RegCreateKeyExW` at `0x14000726c`
- `ADVAPI32!RegCreateKeyExW` at `0x14000726c`
- `ADVAPI32!RegCloseKey` at `0x1400071e1`
- `ADVAPI32!RegCloseKey` at `0x1400072d7`
- `ADVAPI32!RegCloseKey` at `0x1400071e1`
- `ADVAPI32!RegCloseKey` at `0x1400072d7`
- `KERNEL32!SetLastError` at `0x140007343`
- `KERNEL32!SetLastError` at `0x140007343`
- `KERNEL32!lstrlenW` at `0x1400072a1`
- `KERNEL32!lstrlenW` at `0x1400072a1`
- `KERNEL32!GetLastError` at `0x140007142`
- `KERNEL32!GetLastError` at `0x140007142`
- `KERNEL32!OutputDebugStringW` at `0x14000733b`
- `KERNEL32!OutputDebugStringW` at `0x14000733b`
- `KERNEL32!GlobalFree` at `0x1400071f3`
- `KERNEL32!GlobalFree` at `0x1400071f3`

## string_xrefs

- `0x140007166`: `Software\Policies\Microsoft\Windows\Installer`
- `0x14000723f`: `Software\Microsoft\Windows\CurrentVersion\Installer\CA`

## pseudocode

```c
void __fastcall ReportErrorToDebugOutput(const WCHAR *lpData, int a2)
{
  HKEY v3; // rcx
  DWORD LastError; // edi
  unsigned int v5; // r8d
  unsigned int v6; // r9d
  int v7; // eax
  int v8; // eax
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  BYTE v11[16]; // [rsp+60h] [rbp-A0h] BYREF
  HGLOBAL hMem; // [rsp+70h] [rbp-90h]
  int v13; // [rsp+78h] [rbp-88h]
  BYTE Data[80]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR OutputString; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v16[2062]; // [rsp+D2h] [rbp-2Eh] BYREF

  *(_DWORD *)v11 = a2;
  LastError = GetLastError();
  if ( dword_140010198 == -1 )
  {
    dword_140010198 = 0;
    hKey = 0;
    if ( !MsiRegOpen64bitKey(v3, L"Software\\Policies\\Microsoft\\Windows\\Installer", v5, v6, &hKey) )
    {
      hMem = Data;
      v13 = 40;
      cbData = 80;
      if ( !RegQueryValueExW(hKey, L"Debug", 0, 0, Data, &cbData) )
        dword_140010198 = *(_DWORD *)hMem & 3;
      RegCloseKey(hKey);
      if ( v13 > 40 )
        GlobalFree(hMem);
    }
  }
  if ( g_fCustomActionServer )
  {
    if ( *(_DWORD *)v11 )
    {
      hKey = 0;
      cbData = 131078;
      AdjustREGSAM(&cbData);
      if ( !RegCreateKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Installer\\CA",
              0,
              0,
              0,
              cbData,
              0,
              &hKey,
              0) )
      {
        RegSetValueExW(hKey, L"LastError", 0, 4u, v11, 4u);
        v7 = lstrlenW(lpData);
        RegSetValueExW(hKey, L"LastErrorMessage", 0, 1u, (const BYTE *)lpData, 2 * v7 + 2);
        RegCloseKey(hKey);
      }
    }
  }
  if ( (dword_140010198 & 3) != 0 )
  {
    OutputString = 0;
    memset_0(v16, 0, 0x800u);
    if ( *(_DWORD *)v11 )
      v8 = StringCchPrintfW(&OutputString, 0x401u, L"Error: %d. %s.\r\n");
    else
      v8 = StringCchPrintfW(&OutputString, 0x401u, L"%s\r\n", lpData);
    if ( v8 >= 0 )
      OutputDebugStringW(&OutputString);
  }
  SetLastError(LastError);
}

```

## disassembly

```asm
0x140007110  mov     [rsp-8+arg_10], rbx
0x140007115  mov     [rsp-8+arg_18], rdi
0x14000711a  push    rbp
0x14000711b  lea     rbp, [rsp-7F0h]
0x140007123  sub     rsp, 8F0h
0x14000712a  mov     rax, cs:__security_cookie
0x140007131  xor     rax, rsp
0x140007134  mov     [rbp+7F0h+var_10], rax
0x14000713b  mov     rbx, rcx
0x14000713e  mov     dword ptr [rsp+8F0h+var_890], edx
0x140007142  call    cs:__imp_GetLastError
0x140007148  cmp     cs:dword_140010198, 0FFFFFFFFh
0x14000714f  mov     edi, eax
0x140007151  jnz     loc_1400071F9
0x140007157  lea     rax, [rsp+8F0h+hKey]
0x14000715c  mov     cs:dword_140010198, 0
0x140007166  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x14000716d  mov     [rsp+8F0h+lpData], rax; HKEY *
0x140007172  mov     [rsp+8F0h+hKey], 0
0x14000717b  call    ?MsiRegOpen64bitKey@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; MsiRegOpen64bitKey(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x140007180  test    eax, eax
0x140007182  jnz     short loc_1400071F9
0x140007184  mov     rcx, [rsp+8F0h+hKey]; hKey
0x140007189  lea     rax, [rbp+7F0h+Data]
0x14000718d  mov     [rsp+8F0h+hMem], rax
0x140007192  lea     rdx, ValueName; "Debug"
0x140007199  lea     rax, [rsp+8F0h+cbData]
0x14000719e  mov     [rsp+8F0h+var_878], 28h ; '('
0x1400071a6  mov     [rsp+8F0h+lpcbData], rax; lpcbData
0x1400071ab  xor     r9d, r9d; lpType
0x1400071ae  lea     rax, [rbp+7F0h+Data]
0x1400071b2  mov     [rsp+8F0h+cbData], 50h ; 'P'
0x1400071ba  xor     r8d, r8d; lpReserved
0x1400071bd  mov     [rsp+8F0h+lpData], rax; lpData
0x1400071c2  call    cs:__imp_RegQueryValueExW
0x1400071c8  test    eax, eax
0x1400071ca  jnz     short loc_1400071DC
0x1400071cc  mov     rax, [rsp+8F0h+hMem]
0x1400071d1  mov     ecx, [rax]
0x1400071d3  and     ecx, 3
0x1400071d6  mov     cs:dword_140010198, ecx
0x1400071dc  mov     rcx, [rsp+8F0h+hKey]; hKey
0x1400071e1  call    cs:__imp_RegCloseKey
0x1400071e7  cmp     [rsp+8F0h+var_878], 28h ; '('
0x1400071ec  jle     short loc_1400071F9
0x1400071ee  mov     rcx, [rsp+8F0h+hMem]; hMem
0x1400071f3  call    cs:__imp_GlobalFree
0x1400071f9  cmp     cs:?g_fCustomActionServer@@3W4Bool@@A, 0; Bool g_fCustomActionServer
0x140007200  jz      loc_1400072DD
0x140007206  cmp     dword ptr [rsp+8F0h+var_890], 0
0x14000720b  jz      loc_1400072DD
0x140007211  lea     rcx, [rsp+8F0h+cbData]; unsigned int *
0x140007216  mov     [rsp+8F0h+hKey], 0
0x14000721f  mov     [rsp+8F0h+cbData], 20006h
0x140007227  call    ?AdjustREGSAM@@YAXAEAK@Z; AdjustREGSAM(ulong &)
0x14000722c  mov     [rsp+8F0h+lpdwDisposition], 0; lpdwDisposition
0x140007235  lea     rax, [rsp+8F0h+hKey]
0x14000723a  mov     [rsp+8F0h+phkResult], rax; phkResult
0x14000723f  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140007246  mov     eax, [rsp+8F0h+cbData]
0x14000724a  xor     r9d, r9d; lpClass
0x14000724d  mov     [rsp+8F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140007256  xor     r8d, r8d; Reserved
0x140007259  mov     dword ptr [rsp+8F0h+lpcbData], eax; samDesired
0x14000725d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140007264  mov     dword ptr [rsp+8F0h+lpData], 0; dwOptions
0x14000726c  call    cs:__imp_RegCreateKeyExW
0x140007272  test    eax, eax
0x140007274  jnz     short loc_1400072DD
0x140007276  mov     rcx, [rsp+8F0h+hKey]; hKey
0x14000727b  lea     r9d, [rax+4]; dwType
0x14000727f  lea     rax, [rsp+8F0h+var_890]
0x140007284  mov     dword ptr [rsp+8F0h+lpcbData], r9d; cbData
0x140007289  xor     r8d, r8d; Reserved
0x14000728c  mov     [rsp+8F0h+lpData], rax; lpData
0x140007291  lea     rdx, aLasterror; "LastError"
0x140007298  call    cs:__imp_RegSetValueExW
0x14000729e  mov     rcx, rbx; lpString
0x1400072a1  call    cs:__imp_lstrlenW
0x1400072a7  mov     rcx, [rsp+8F0h+hKey]; hKey
0x1400072ac  lea     rdx, aLasterrormessa; "LastErrorMessage"
0x1400072b3  mov     r9d, 1; dwType
0x1400072b9  xor     r8d, r8d; Reserved
0x1400072bc  lea     eax, ds:2[rax*2]
0x1400072c3  mov     dword ptr [rsp+8F0h+lpcbData], eax; cbData
0x1400072c7  mov     [rsp+8F0h+lpData], rbx; lpData
0x1400072cc  call    cs:__imp_RegSetValueExW
0x1400072d2  mov     rcx, [rsp+8F0h+hKey]; hKey
0x1400072d7  call    cs:__imp_RegCloseKey
0x1400072dd  mov     eax, cs:dword_140010198
0x1400072e3  test    al, 3
0x1400072e5  jz      short loc_140007341
0x1400072e7  xor     eax, eax
0x1400072e9  lea     rcx, [rbp+7F0h+var_81E]; void *
0x1400072ed  xor     edx, edx; Val
0x1400072ef  mov     [rbp+7F0h+OutputString], ax
0x1400072f3  mov     r8d, 800h; Size
0x1400072f9  call    memset_0
0x1400072fe  mov     r9d, dword ptr [rsp+8F0h+var_890]
0x140007303  lea     rcx, [rbp+7F0h+OutputString]; unsigned __int16 *
0x140007307  mov     edx, 401h; unsigned __int64
0x14000730c  test    r9d, r9d
0x14000730f  jz      short loc_140007324
0x140007311  lea     r8, aErrorDS; "Error: %d. %s.\r\n"
0x140007318  mov     [rsp+8F0h+lpData], rbx
0x14000731d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140007322  jmp     short loc_140007333
0x140007324  mov     r9, rbx
0x140007327  lea     r8, aS; "%s\r\n"
0x14000732e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140007333  test    eax, eax
0x140007335  js      short loc_140007341
0x140007337  lea     rcx, [rbp+7F0h+OutputString]; lpOutputString
0x14000733b  call    cs:__imp_OutputDebugStringW
0x140007341  mov     ecx, edi; dwErrCode
0x140007343  call    cs:__imp_SetLastError
0x140007349  mov     rcx, [rbp+7F0h+var_10]
0x140007350  xor     rcx, rsp; StackCookie
0x140007353  call    __security_check_cookie
0x140007358  lea     r11, [rsp+8F0h+var_s0]
0x140007360  mov     rbx, [r11+20h]
0x140007364  mov     rdi, [r11+28h]
0x140007368  mov     rsp, r11
0x14000736b  pop     rbp
0x14000736c  retn
```
