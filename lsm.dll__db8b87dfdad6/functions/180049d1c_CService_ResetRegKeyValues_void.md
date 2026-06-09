# CService::ResetRegKeyValues(void)

- ea: `0x180049d1c`
- end: `0x180049ec5`
- name: `?ResetRegKeyValues@CService@@IEAAJXZ`
- size: `425`
- prototype: `__int64 __fastcall(CService *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002ae4c`

## callees

- `0x1800074c0`
- `0x180017da0`
- `0x18001ea44`
- `0x18002cd9c`
- `0x180049d1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049dfd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049dfd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049e38`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049e38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049eab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049eab`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049e6e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049e6e`

## string_xrefs

- `0x180049e8e`: `CService::ResetRegKeyValues`
- `0x180049d98`: `RegOpenKey failed: 0x%x in %s`
- `0x180049dce`: `WriteRegString failed: 0x%x in %s`
- `0x180049e87`: `RegSetValueEx - TSServerDrainMode failed: 0x%x in %s`

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
0x180049d1c  mov     qword ptr [rsp-18h+Data], rcx
0x180049d21  push    rbp
0x180049d22  push    rbx
0x180049d23  push    rsi
0x180049d24  mov     rbp, rsp
0x180049d27  sub     rsp, 60h
0x180049d2b  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x180049d32  mov     [rbp+var_28], rax
0x180049d36  mov     [rbp+var_20], 0
0x180049d3e  mov     [rbp+var_18], 0
0x180049d45  mov     [rbp+var_10], 0
0x180049d4d  or      eax, 0FFFFFFFFh
0x180049d50  mov     [rbp+var_8], eax
0x180049d53  mov     [rbp+var_4], eax
0x180049d56  mov     [rbp+Data], 0
0x180049d5d  mov     [rbp+hKey], 0
0x180049d65  mov     r9d, 20006h; unsigned int
0x180049d6b  lea     r8, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180049d72  mov     rsi, 0FFFFFFFF80000002h
0x180049d79  mov     rdx, rsi; HKEY
0x180049d7c  lea     rcx, [rbp+var_28]; this
0x180049d80  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x180049d85  mov     ebx, eax
0x180049d87  test    eax, eax
0x180049d89  jle     short loc_180049D94
0x180049d8b  movzx   ebx, ax
0x180049d8e  or      ebx, 80070000h
0x180049d94  test    ebx, ebx
0x180049d96  jns     short loc_180049DA4
0x180049d98  lea     rdx, aRegopenkeyFail; "RegOpenKey failed: 0x%x in %s"
0x180049d9f  jmp     loc_180049E8E
0x180049da4  lea     r8, a0; "0"
0x180049dab  lea     rdx, aWinstationsdis; "WinStationsDisabled"
0x180049db2  lea     rcx, [rbp+var_28]; this
0x180049db6  call    ?WriteRegString@CRegistry@@QEAAKPEBG0@Z; CRegistry::WriteRegString(ushort const *,ushort const *)
0x180049dbb  mov     ebx, eax
0x180049dbd  test    eax, eax
0x180049dbf  jle     short loc_180049DCA
0x180049dc1  movzx   ebx, ax
0x180049dc4  or      ebx, 80070000h
0x180049dca  test    ebx, ebx
0x180049dcc  jns     short loc_180049DDA
0x180049dce  lea     rdx, aWriteregstring; "WriteRegString failed: 0x%x in %s"
0x180049dd5  jmp     loc_180049E8E
0x180049dda  mov     [rbp+Data], 0
0x180049de1  lea     rax, [rbp+hKey]
0x180049de5  mov     [rsp+60h+phkResult], rax; phkResult
0x180049dea  mov     r9d, 0F003Fh; samDesired
0x180049df0  xor     r8d, r8d; ulOptions
0x180049df3  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x180049dfa  mov     rcx, rsi; hKey
0x180049dfd  call    cs:__imp_RegOpenKeyExW
0x180049e03  test    eax, eax
0x180049e05  jnz     loc_180049EA2
0x180049e0b  mov     [rbp+Type], eax
0x180049e0e  lea     esi, [rax+4]
0x180049e11  mov     [rbp+cbData], esi
0x180049e14  lea     rax, [rbp+cbData]
0x180049e18  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180049e1d  lea     rax, [rbp+Data]
0x180049e21  mov     [rsp+60h+phkResult], rax; lpData
0x180049e26  lea     r9, [rbp+Type]; lpType
0x180049e2a  xor     r8d, r8d; lpReserved
0x180049e2d  lea     rdx, aTsserverdrainm; "TSServerDrainMode"
0x180049e34  mov     rcx, [rbp+hKey]; hKey
0x180049e38  call    cs:__imp_RegQueryValueExW
0x180049e3e  test    eax, eax
0x180049e40  jnz     short loc_180049EA2
0x180049e42  cmp     [rbp+Type], esi
0x180049e45  jnz     short loc_180049EA2
0x180049e47  cmp     [rbp+Data], 1
0x180049e4b  jnz     short loc_180049EA2
0x180049e4d  mov     [rbp+arg_18], eax
0x180049e50  mov     dword ptr [rsp+60h+lpcbData], esi; cbData
0x180049e54  lea     rax, [rbp+arg_18]
0x180049e58  mov     [rsp+60h+phkResult], rax; lpData
0x180049e5d  mov     r9d, esi; dwType
0x180049e60  xor     r8d, r8d; Reserved
0x180049e63  lea     rdx, aTsserverdrainm; "TSServerDrainMode"
0x180049e6a  mov     rcx, [rbp+hKey]; hKey
0x180049e6e  call    cs:__imp_RegSetValueExW
0x180049e74  mov     ebx, eax
0x180049e76  test    eax, eax
0x180049e78  jle     short loc_180049E83
0x180049e7a  movzx   ebx, ax
0x180049e7d  or      ebx, 80070000h
0x180049e83  test    ebx, ebx
0x180049e85  jns     short loc_180049EA2
0x180049e87  lea     rdx, aRegsetvalueexT; "RegSetValueEx - TSServerDrainMode faile"...
0x180049e8e  lea     r9, aCserviceResetr; "CService::ResetRegKeyValues"
0x180049e95  mov     r8d, ebx
0x180049e98  mov     ecx, 8; int
0x180049e9d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180049ea2  mov     rcx, [rbp+hKey]; hKey
0x180049ea6  test    rcx, rcx
0x180049ea9  jz      short loc_180049EB2
0x180049eab  call    cs:__imp_RegCloseKey
0x180049eb1  nop
0x180049eb2  lea     rcx, [rbp+var_28]; this
0x180049eb6  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180049ebb  mov     eax, ebx
0x180049ebd  add     rsp, 60h
0x180049ec1  pop     rsi
0x180049ec2  pop     rbx
0x180049ec3  pop     rbp
0x180049ec4  retn
```
