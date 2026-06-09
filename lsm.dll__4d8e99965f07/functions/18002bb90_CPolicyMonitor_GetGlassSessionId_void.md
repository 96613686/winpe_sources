# CPolicyMonitor::GetGlassSessionId(void)

- ea: `0x18002bb90`
- end: `0x18002bc67`
- name: `?GetGlassSessionId@CPolicyMonitor@@AEAAKXZ`
- size: `215`
- prototype: `unsigned int __fastcall(CPolicyMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180054be4`

## callees

- `0x1800077a0`
- `0x18002bb90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bbde`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bbde`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bc20`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bc20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bc4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bc4a`

## string_xrefs

- `0x18002bc30`: `Unable to open REG_CONTROL_TSERVER key`

## pseudocode

```c
__int64 __fastcall CPolicyMonitor::GetGlassSessionId(CPolicyMonitor *this)
{
  unsigned int v1; // ebx
  LSTATUS v2; // eax
  LSTATUS v3; // edi
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  int v6; // [rsp+54h] [rbp+24h]
  unsigned int Data; // [rsp+58h] [rbp+28h] BYREF
  DWORD Type; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  v6 = HIDWORD(this);
  Type = 0;
  cbData = 4;
  Data = 1;
  hKey = 0;
  v1 = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey);
  v3 = v2;
  if ( !hKey || v2 )
  {
    _DbgPrintMessage(4, "Unable to open REG_CONTROL_TSERVER key");
  }
  else
  {
    cbData = 4;
    v3 = RegQueryValueExW(hKey, L"GlassSessionId", 0, &Type, (LPBYTE)&Data, &cbData);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( !v3 )
    return Data;
  return v1;
}

```

## disassembly

```asm
0x18002bb90  mov     qword ptr [rsp-18h+cbData], rcx
0x18002bb95  push    rbp
0x18002bb96  push    rbx
0x18002bb97  push    rdi
0x18002bb98  mov     rbp, rsp
0x18002bb9b  sub     rsp, 30h
0x18002bb9f  lea     rax, [rbp+hKey]
0x18002bba3  mov     [rbp+Type], 0
0x18002bbaa  mov     r9d, 20019h; samDesired
0x18002bbb0  mov     [rsp+30h+phkResult], rax; phkResult
0x18002bbb5  xor     r8d, r8d; ulOptions
0x18002bbb8  mov     [rbp+cbData], 4
0x18002bbbf  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x18002bbc6  mov     [rbp+Data], 1
0x18002bbcd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002bbd4  mov     [rbp+hKey], 0
0x18002bbdc  xor     ebx, ebx
0x18002bbde  call    cs:__imp_RegOpenKeyExW
0x18002bbe5  nop     dword ptr [rax+rax+00h]
0x18002bbea  mov     rcx, [rbp+hKey]; hKey
0x18002bbee  mov     edi, eax
0x18002bbf0  test    rcx, rcx
0x18002bbf3  jz      short loc_18002BC30
0x18002bbf5  test    eax, eax
0x18002bbf7  jnz     short loc_18002BC30
0x18002bbf9  lea     rax, [rbp+cbData]
0x18002bbfd  mov     [rbp+cbData], 4
0x18002bc04  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002bc09  lea     r9, [rbp+Type]; lpType
0x18002bc0d  lea     rax, [rbp+Data]
0x18002bc11  xor     r8d, r8d; lpReserved
0x18002bc14  lea     rdx, ValueName; "GlassSessionId"
0x18002bc1b  mov     [rsp+30h+phkResult], rax; lpData
0x18002bc20  call    cs:__imp_RegQueryValueExW
0x18002bc27  nop     dword ptr [rax+rax+00h]
0x18002bc2c  mov     edi, eax
0x18002bc2e  jmp     short loc_18002BC41
0x18002bc30  lea     rdx, aUnableToOpenRe; "Unable to open REG_CONTROL_TSERVER key"
0x18002bc37  mov     ecx, 4; int
0x18002bc3c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002bc41  mov     rcx, [rbp+hKey]; hKey
0x18002bc45  test    rcx, rcx
0x18002bc48  jz      short loc_18002BC56
0x18002bc4a  call    cs:__imp_RegCloseKey
0x18002bc51  nop     dword ptr [rax+rax+00h]
0x18002bc56  test    edi, edi
0x18002bc58  cmovz   ebx, [rbp+Data]
0x18002bc5c  mov     eax, ebx
0x18002bc5e  add     rsp, 30h
0x18002bc62  pop     rdi
0x18002bc63  pop     rbx
0x18002bc64  pop     rbp
0x18002bc65  retn
```
