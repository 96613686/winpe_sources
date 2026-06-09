# CPolicyMonitor::GetGlassSessionId(void)

- ea: `0x180029808`
- end: `0x1800298cc`
- name: `?GetGlassSessionId@CPolicyMonitor@@AEAAKXZ`
- size: `196`
- prototype: `unsigned int __fastcall(CPolicyMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180051464`

## callees

- `0x1800074c0`
- `0x180029808`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029856`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029856`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029892`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029892`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800298b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800298b6`

## string_xrefs

- `0x18002989c`: `Unable to open REG_CONTROL_TSERVER key`

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
0x180029808  mov     qword ptr [rsp-18h+cbData], rcx
0x18002980d  push    rbp
0x18002980e  push    rbx
0x18002980f  push    rdi
0x180029810  mov     rbp, rsp
0x180029813  sub     rsp, 30h
0x180029817  lea     rax, [rbp+hKey]
0x18002981b  mov     [rbp+Type], 0
0x180029822  mov     r9d, 20019h; samDesired
0x180029828  mov     [rsp+30h+phkResult], rax; phkResult
0x18002982d  xor     r8d, r8d; ulOptions
0x180029830  mov     [rbp+cbData], 4
0x180029837  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x18002983e  mov     [rbp+Data], 1
0x180029845  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002984c  mov     [rbp+hKey], 0
0x180029854  xor     ebx, ebx
0x180029856  call    cs:__imp_RegOpenKeyExW
0x18002985c  mov     rcx, [rbp+hKey]; hKey
0x180029860  mov     edi, eax
0x180029862  test    rcx, rcx
0x180029865  jz      short loc_18002989C
0x180029867  test    eax, eax
0x180029869  jnz     short loc_18002989C
0x18002986b  lea     rax, [rbp+cbData]
0x18002986f  mov     [rbp+cbData], 4
0x180029876  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002987b  lea     r9, [rbp+Type]; lpType
0x18002987f  lea     rax, [rbp+Data]
0x180029883  xor     r8d, r8d; lpReserved
0x180029886  lea     rdx, aGlasssessionid; "GlassSessionId"
0x18002988d  mov     [rsp+30h+phkResult], rax; lpData
0x180029892  call    cs:__imp_RegQueryValueExW
0x180029898  mov     edi, eax
0x18002989a  jmp     short loc_1800298AD
0x18002989c  lea     rdx, aUnableToOpenRe; "Unable to open REG_CONTROL_TSERVER key"
0x1800298a3  mov     ecx, 4; int
0x1800298a8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800298ad  mov     rcx, [rbp+hKey]; hKey
0x1800298b1  test    rcx, rcx
0x1800298b4  jz      short loc_1800298BC
0x1800298b6  call    cs:__imp_RegCloseKey
0x1800298bc  test    edi, edi
0x1800298be  cmovz   ebx, [rbp+Data]
0x1800298c2  mov     eax, ebx
0x1800298c4  add     rsp, 30h
0x1800298c8  pop     rdi
0x1800298c9  pop     rbx
0x1800298ca  pop     rbp
0x1800298cb  retn
```
