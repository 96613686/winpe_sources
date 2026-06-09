# IsRasmanProcess

- ea: `0x1800b1060`
- end: `0x1800b1167`
- name: `IsRasmanProcess`
- size: `263`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180029cd0`
- `0x1800b2318`

## callees

- `0x1800b1060`

## import_xrefs

- `msvcrt!strstr` at `0x1800b1124`
- `msvcrt!strstr` at `0x1800b114b`
- `msvcrt!strstr` at `0x1800b1124`
- `msvcrt!strstr` at `0x1800b114b`
- `msvcrt!_strlwr` at `0x1800b1114`
- `msvcrt!_strlwr` at `0x1800b113b`
- `msvcrt!_strlwr` at `0x1800b1114`
- `msvcrt!_strlwr` at `0x1800b113b`
- `msvcrt!_strdup` at `0x1800b1103`
- `msvcrt!_strdup` at `0x1800b1103`
- `msvcrt!free` at `0x1800b1133`
- `msvcrt!free` at `0x1800b1133`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b109d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b109d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800b10d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800b10d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b10ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b10ed`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x1800b1074`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x1800b1074`

## string_xrefs

- `0x1800b1080`: `System\CurrentControlSet\Services\rasman\parameters`

## pseudocode

```c
__int64 IsRasmanProcess()
{
  unsigned int v0; // ebx
  int v1; // esi
  char *CommandLineA; // rdi
  char *v3; // rax
  char *v4; // rdi
  char *v5; // rax
  char *v6; // rax
  int Data; // [rsp+60h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+30h] BYREF
  DWORD Type; // [rsp+70h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+40h] BYREF

  v0 = 0;
  v1 = 0;
  hKey = 0;
  CommandLineA = GetCommandLineA();
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\rasman\\parameters", 0, 0x20019u, &hKey) )
  {
    Type = 0;
    Data = 0;
    cbData = 4;
    if ( !RegQueryValueExA(hKey, "ForceCmdLowerCase", 0, &Type, (LPBYTE)&Data, &cbData) )
      v1 = Data;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( CommandLineA )
  {
    if ( v1 )
    {
      v6 = _strlwr(CommandLineA);
      if ( strstr(v6, "-k netsvcs") )
        return 1;
    }
    else
    {
      v3 = _strdup(CommandLineA);
      v4 = v3;
      if ( v3 )
      {
        v5 = _strlwr(v3);
        LOBYTE(v0) = strstr(v5, "-k netsvcs") != 0;
        free(v4);
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x1800b1060  push    rbp
0x1800b1062  push    rbx
0x1800b1063  push    rsi
0x1800b1064  push    rdi
0x1800b1065  mov     rbp, rsp
0x1800b1068  sub     rsp, 38h
0x1800b106c  xor     ebx, ebx
0x1800b106e  xor     esi, esi
0x1800b1070  mov     [rbp+hKey], rbx
0x1800b1074  call    cs:__imp_GetCommandLineA
0x1800b107a  mov     r9d, 20019h; samDesired
0x1800b1080  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\ra"...
0x1800b1087  mov     rdi, rax
0x1800b108a  xor     r8d, r8d; ulOptions
0x1800b108d  lea     rax, [rbp+hKey]
0x1800b1091  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b1098  mov     [rsp+38h+phkResult], rax; phkResult
0x1800b109d  call    cs:__imp_RegOpenKeyExA
0x1800b10a3  test    eax, eax
0x1800b10a5  jnz     short loc_1800B10E4
0x1800b10a7  mov     rcx, [rbp+hKey]; hKey
0x1800b10ab  lea     rax, [rbp+cbData]
0x1800b10af  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800b10b4  lea     r9, [rbp+Type]; lpType
0x1800b10b8  lea     rax, [rbp+Data]
0x1800b10bc  mov     [rbp+Type], ebx
0x1800b10bf  xor     r8d, r8d; lpReserved
0x1800b10c2  mov     [rsp+38h+phkResult], rax; lpData
0x1800b10c7  lea     rdx, aForcecmdlowerc; "ForceCmdLowerCase"
0x1800b10ce  mov     [rbp+Data], ebx
0x1800b10d1  mov     [rbp+cbData], 4
0x1800b10d8  call    cs:__imp_RegQueryValueExA
0x1800b10de  test    eax, eax
0x1800b10e0  cmovz   esi, [rbp+Data]
0x1800b10e4  mov     rcx, [rbp+hKey]; hKey
0x1800b10e8  test    rcx, rcx
0x1800b10eb  jz      short loc_1800B10F7
0x1800b10ed  call    cs:__imp_RegCloseKey
0x1800b10f3  mov     [rbp+hKey], rbx
0x1800b10f7  test    rdi, rdi
0x1800b10fa  jz      short loc_1800B115C
0x1800b10fc  mov     rcx, rdi; String
0x1800b10ff  test    esi, esi
0x1800b1101  jnz     short loc_1800B113B
0x1800b1103  call    cs:__imp__strdup
0x1800b1109  mov     rdi, rax
0x1800b110c  test    rax, rax
0x1800b110f  jz      short loc_1800B115C
0x1800b1111  mov     rcx, rax; String
0x1800b1114  call    cs:__imp__strlwr
0x1800b111a  mov     rcx, rax; Str
0x1800b111d  lea     rdx, aKNetsvcs; "-k netsvcs"
0x1800b1124  call    cs:__imp_strstr
0x1800b112a  test    rax, rax
0x1800b112d  mov     rcx, rdi; Block
0x1800b1130  setnz   bl
0x1800b1133  call    cs:__imp_free
0x1800b1139  jmp     short loc_1800B115C
0x1800b113b  call    cs:__imp__strlwr
0x1800b1141  mov     rcx, rax; Str
0x1800b1144  lea     rdx, aKNetsvcs; "-k netsvcs"
0x1800b114b  call    cs:__imp_strstr
0x1800b1151  test    rax, rax
0x1800b1154  mov     ecx, 1
0x1800b1159  cmovnz  ebx, ecx
0x1800b115c  mov     eax, ebx
0x1800b115e  add     rsp, 38h
0x1800b1162  pop     rdi
0x1800b1163  pop     rsi
0x1800b1164  pop     rbx
0x1800b1165  pop     rbp
0x1800b1166  retn
```
