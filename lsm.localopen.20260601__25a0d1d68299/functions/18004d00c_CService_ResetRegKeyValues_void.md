# CService::ResetRegKeyValues(void)

- ea: `0x18004d00c`
- end: `0x18004d1ce`
- name: `?ResetRegKeyValues@CService@@IEAAJXZ`
- size: `450`
- prototype: `__int64 __fastcall(CService *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002cf00`

## callees

- `0x1800077a0`
- `0x18000af60`
- `0x18000bcc8`
- `0x18002ea48`
- `0x18004d00c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004d0ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004d0ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004d12e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004d12e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d1ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d1ad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004d16a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004d16a`

## string_xrefs

- `0x18004d190`: `CService::ResetRegKeyValues`
- `0x18004d088`: `RegOpenKey failed: 0x%x in %s`
- `0x18004d0be`: `WriteRegString failed: 0x%x in %s`
- `0x18004d189`: `RegSetValueEx - TSServerDrainMode failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CService::ResetRegKeyValues(CService *this)
{
  int v1; // eax
  signed int v2; // ebx
  int v3; // eax
  LSTATUS v4; // eax
  const unsigned __int16 *phkResult; // [rsp+20h] [rbp-40h]
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v8[2]; // [rsp+38h] [rbp-28h] BYREF
  int v9; // [rsp+48h] [rbp-18h]
  __int64 v10; // [rsp+50h] [rbp-10h]
  int v11; // [rsp+58h] [rbp-8h]
  int v12; // [rsp+5Ch] [rbp-4h]
  int Data; // [rsp+80h] [rbp+20h] BYREF
  int v14; // [rsp+84h] [rbp+24h]
  DWORD Type; // [rsp+88h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+30h] BYREF
  int v17; // [rsp+98h] [rbp+38h] BYREF

  v14 = HIDWORD(this);
  v8[0] = &CRegistry::`vftable';
  v8[1] = 0;
  v9 = 0;
  v10 = 0;
  v11 = -1;
  v12 = -1;
  Data = 0;
  hKey = 0;
  v1 = CRegistry::OpenKey(
         (CRegistry *)v8,
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
         0x20006u,
         phkResult);
  v2 = v1;
  if ( v1 > 0 )
    v2 = (unsigned __int16)v1 | 0x80070000;
  if ( v2 >= 0 )
  {
    v3 = CRegistry::WriteRegString((CRegistry *)v8, L"WinStationsDisabled", L"0");
    v2 = v3;
    if ( v3 > 0 )
      v2 = (unsigned __int16)v3 | 0x80070000;
    if ( v2 >= 0 )
    {
      Data = 0;
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"System\\CurrentControlSet\\Control\\Terminal Server",
              0,
              0xF003Fu,
              &hKey) )
      {
        Type = 0;
        cbData = 4;
        if ( !RegQueryValueExW(hKey, L"TSServerDrainMode", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data == 1 )
        {
          v17 = 0;
          v4 = RegSetValueExW(hKey, L"TSServerDrainMode", 0, 4u, (const BYTE *)&v17, 4u);
          v2 = v4;
          if ( v4 > 0 )
            v2 = (unsigned __int16)v4 | 0x80070000;
          if ( v2 < 0 )
            _DbgPrintMessage(
              8,
              "RegSetValueEx - TSServerDrainMode failed: 0x%x in %s",
              (unsigned int)v2,
              "CService::ResetRegKeyValues");
        }
      }
    }
    else
    {
      _DbgPrintMessage(8, "WriteRegString failed: 0x%x in %s", (unsigned int)v2, "CService::ResetRegKeyValues");
    }
  }
  else
  {
    _DbgPrintMessage(8, "RegOpenKey failed: 0x%x in %s", (unsigned int)v2, "CService::ResetRegKeyValues");
  }
  if ( hKey )
    RegCloseKey(hKey);
  CRegistry::~CRegistry((CRegistry *)v8);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18004d00c  mov     qword ptr [rsp-18h+Data], rcx
0x18004d011  push    rbp
0x18004d012  push    rbx
0x18004d013  push    rsi
0x18004d014  mov     rbp, rsp
0x18004d017  sub     rsp, 60h
0x18004d01b  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18004d022  mov     [rbp+var_28], rax
0x18004d026  mov     [rbp+var_20], 0
0x18004d02e  mov     [rbp+var_18], 0
0x18004d035  mov     [rbp+var_10], 0
0x18004d03d  or      eax, 0FFFFFFFFh
0x18004d040  mov     [rbp+var_8], eax
0x18004d043  mov     [rbp+var_4], eax
0x18004d046  mov     [rbp+Data], 0
0x18004d04d  mov     [rbp+hKey], 0
0x18004d055  mov     r9d, 20006h; unsigned int
0x18004d05b  lea     r8, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18004d062  mov     rsi, 0FFFFFFFF80000002h
0x18004d069  mov     rdx, rsi; HKEY
0x18004d06c  lea     rcx, [rbp+var_28]; this
0x18004d070  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x18004d075  mov     ebx, eax
0x18004d077  test    eax, eax
0x18004d079  jle     short loc_18004D084
0x18004d07b  movzx   ebx, ax
0x18004d07e  or      ebx, 80070000h
0x18004d084  test    ebx, ebx
0x18004d086  jns     short loc_18004D094
0x18004d088  lea     rdx, aRegopenkeyFail; "RegOpenKey failed: 0x%x in %s"
0x18004d08f  jmp     loc_18004D190
0x18004d094  lea     r8, a0; "0"
0x18004d09b  lea     rdx, aWinstationsdis; "WinStationsDisabled"
0x18004d0a2  lea     rcx, [rbp+var_28]; this
0x18004d0a6  call    ?WriteRegString@CRegistry@@QEAAKPEBG0@Z; CRegistry::WriteRegString(ushort const *,ushort const *)
0x18004d0ab  mov     ebx, eax
0x18004d0ad  test    eax, eax
0x18004d0af  jle     short loc_18004D0BA
0x18004d0b1  movzx   ebx, ax
0x18004d0b4  or      ebx, 80070000h
0x18004d0ba  test    ebx, ebx
0x18004d0bc  jns     short loc_18004D0CA
0x18004d0be  lea     rdx, aWriteregstring; "WriteRegString failed: 0x%x in %s"
0x18004d0c5  jmp     loc_18004D190
0x18004d0ca  mov     [rbp+Data], 0
0x18004d0d1  lea     rax, [rbp+hKey]
0x18004d0d5  mov     [rsp+60h+phkResult], rax; phkResult
0x18004d0da  mov     r9d, 0F003Fh; samDesired
0x18004d0e0  xor     r8d, r8d; ulOptions
0x18004d0e3  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x18004d0ea  mov     rcx, rsi; hKey
0x18004d0ed  call    cs:__imp_RegOpenKeyExW
0x18004d0f4  nop     dword ptr [rax+rax+00h]
0x18004d0f9  test    eax, eax
0x18004d0fb  jnz     loc_18004D1A4
0x18004d101  mov     [rbp+Type], eax
0x18004d104  lea     esi, [rax+4]
0x18004d107  mov     [rbp+cbData], esi
0x18004d10a  lea     rax, [rbp+cbData]
0x18004d10e  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18004d113  lea     rax, [rbp+Data]
0x18004d117  mov     [rsp+60h+phkResult], rax; lpData
0x18004d11c  lea     r9, [rbp+Type]; lpType
0x18004d120  xor     r8d, r8d; lpReserved
0x18004d123  lea     rdx, aTsserverdrainm; "TSServerDrainMode"
0x18004d12a  mov     rcx, [rbp+hKey]; hKey
0x18004d12e  call    cs:__imp_RegQueryValueExW
0x18004d135  nop     dword ptr [rax+rax+00h]
0x18004d13a  test    eax, eax
0x18004d13c  jnz     short loc_18004D1A4
0x18004d13e  cmp     [rbp+Type], esi
0x18004d141  jnz     short loc_18004D1A4
0x18004d143  cmp     [rbp+Data], 1
0x18004d147  jnz     short loc_18004D1A4
0x18004d149  mov     [rbp+arg_18], eax
0x18004d14c  mov     dword ptr [rsp+60h+lpcbData], esi; cbData
0x18004d150  lea     rax, [rbp+arg_18]
0x18004d154  mov     [rsp+60h+phkResult], rax; lpData
0x18004d159  mov     r9d, esi; dwType
0x18004d15c  xor     r8d, r8d; Reserved
0x18004d15f  lea     rdx, aTsserverdrainm; "TSServerDrainMode"
0x18004d166  mov     rcx, [rbp+hKey]; hKey
0x18004d16a  call    cs:__imp_RegSetValueExW
0x18004d171  nop     dword ptr [rax+rax+00h]
0x18004d176  mov     ebx, eax
0x18004d178  test    eax, eax
0x18004d17a  jle     short loc_18004D185
0x18004d17c  movzx   ebx, ax
0x18004d17f  or      ebx, 80070000h
0x18004d185  test    ebx, ebx
0x18004d187  jns     short loc_18004D1A4
0x18004d189  lea     rdx, aRegsetvalueexT; "RegSetValueEx - TSServerDrainMode faile"...
0x18004d190  lea     r9, aCserviceResetr; "CService::ResetRegKeyValues"
0x18004d197  mov     r8d, ebx
0x18004d19a  mov     ecx, 8; int
0x18004d19f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004d1a4  mov     rcx, [rbp+hKey]; hKey
0x18004d1a8  test    rcx, rcx
0x18004d1ab  jz      short loc_18004D1BA
0x18004d1ad  call    cs:__imp_RegCloseKey
0x18004d1b4  nop     dword ptr [rax+rax+00h]
0x18004d1b9  nop
0x18004d1ba  lea     rcx, [rbp+var_28]; this
0x18004d1be  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18004d1c3  mov     eax, ebx
0x18004d1c5  add     rsp, 60h
0x18004d1c9  pop     rsi
0x18004d1ca  pop     rbx
0x18004d1cb  pop     rbp
0x18004d1cc  retn
```
