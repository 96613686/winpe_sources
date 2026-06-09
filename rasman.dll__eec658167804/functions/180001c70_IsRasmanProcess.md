# IsRasmanProcess

- ea: `0x180001c70`
- end: `0x180001e79`
- name: `IsRasmanProcess`
- size: `521`
- prototype: `__int64()`
- caller_count: `7`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180001320`
- `0x180001500`
- `0x180001760`
- `0x180002f80`
- `0x18000b010`
- `0x18001b860`
- `0x18001cd30`

## callees

- `0x180001c70`
- `0x180001e80`
- `0x180020fd8`
- `0x1800213e4`
- `0x180021bd4`

## import_xrefs

- `msvcrt!_strdup` at `0x180001d27`
- `msvcrt!_strdup` at `0x180001d27`
- `msvcrt!strstr` at `0x180001d48`
- `msvcrt!strstr` at `0x180001def`
- `msvcrt!strstr` at `0x180001d48`
- `msvcrt!strstr` at `0x180001def`
- `msvcrt!free` at `0x180001d58`
- `msvcrt!free` at `0x180001d58`
- `msvcrt!_strlwr` at `0x180001d38`
- `msvcrt!_strlwr` at `0x180001ddf`
- `msvcrt!_strlwr` at `0x180001d38`
- `msvcrt!_strlwr` at `0x180001ddf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180001e3f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180001e3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001d0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001d0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180001cf4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180001cf4`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x180001ca0`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x180001ca0`

## string_xrefs

- `0x180001ce6`: `System\CurrentControlSet\Services\rasman\parameters`

## pseudocode

```c
__int64 IsRasmanProcess()
{
  unsigned int v0; // esi
  int v1; // edi
  LPSTR CommandLineA; // rax
  const char *v3; // rdx
  char *v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  char *v7; // rax
  char *v8; // rbx
  char *v9; // rax
  const char *v11; // r9
  char *v12; // rax
  int Data; // [rsp+60h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+10h] BYREF
  DWORD Type; // [rsp+70h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  v0 = 0;
  hKey = 0;
  v1 = 0;
  CommandLineA = GetCommandLineA();
  v3 = "NULL";
  v4 = CommandLineA;
  if ( CommandLineA )
    v3 = CommandLineA;
  RasmanOutputDebug("IsRasmanProcess: CmdLine=%s\n", v3);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v11 = "<NULL>";
    if ( v4 )
      v11 = v4;
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v6, v11);
  }
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
  if ( v4 )
  {
    if ( v1 )
    {
      v12 = _strlwr(v4);
      if ( strstr(v12, "-k netsvcs") )
        v0 = 1;
    }
    else
    {
      v7 = _strdup(v4);
      v8 = v7;
      if ( v7 )
      {
        v9 = _strlwr(v7);
        LOBYTE(v0) = strstr(v9, "-k netsvcs") != 0;
        free(v8);
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_c(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids,
      (unsigned __int8)v0);
  }
  return v0;
}

```

## disassembly

```asm
0x180001c70  push    rbx
0x180001c72  push    rbp
0x180001c73  push    rsi
0x180001c74  push    rdi
0x180001c75  push    r14
0x180001c77  sub     rsp, 30h
0x180001c7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c82  lea     rbp, WPP_GLOBAL_Control
0x180001c89  cmp     rcx, rbp
0x180001c8c  jnz     loc_180001D81
0x180001c92  xor     r14d, r14d
0x180001c95  mov     esi, r14d
0x180001c98  mov     [rsp+58h+hKey], r14
0x180001c9d  mov     edi, r14d
0x180001ca0  call    cs:__imp_GetCommandLineA
0x180001ca6  test    rax, rax
0x180001ca9  lea     rdx, aNull_0; "NULL"
0x180001cb0  lea     rcx, aIsrasmanproces_0; "IsRasmanProcess: CmdLine=%s\n"
0x180001cb7  mov     rbx, rax
0x180001cba  cmovnz  rdx, rax
0x180001cbe  call    RasmanOutputDebug
0x180001cc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180001cca  cmp     rcx, rbp
0x180001ccd  jnz     loc_180001DAF
0x180001cd3  lea     rax, [rsp+58h+hKey]
0x180001cd8  mov     r9d, 20019h; samDesired
0x180001cde  xor     r8d, r8d; ulOptions
0x180001ce1  mov     [rsp+58h+phkResult], rax; phkResult
0x180001ce6  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\ra"...
0x180001ced  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001cf4  call    cs:__imp_RegOpenKeyExA
0x180001cfa  test    eax, eax
0x180001cfc  jz      loc_180001E05
0x180001d02  mov     rcx, [rsp+58h+hKey]; hKey
0x180001d07  test    rcx, rcx
0x180001d0a  jz      short loc_180001D17
0x180001d0c  call    cs:__imp_RegCloseKey
0x180001d12  mov     [rsp+58h+hKey], r14
0x180001d17  test    rbx, rbx
0x180001d1a  jz      short loc_180001D5E
0x180001d1c  mov     rcx, rbx; String
0x180001d1f  test    edi, edi
0x180001d21  jnz     loc_180001DDF
0x180001d27  call    cs:__imp__strdup
0x180001d2d  mov     rbx, rax
0x180001d30  test    rax, rax
0x180001d33  jz      short loc_180001D5E
0x180001d35  mov     rcx, rax; String
0x180001d38  call    cs:__imp__strlwr
0x180001d3e  mov     rcx, rax; Str
0x180001d41  lea     rdx, SubStr; "-k netsvcs"
0x180001d48  call    cs:__imp_strstr
0x180001d4e  test    rax, rax
0x180001d51  mov     rcx, rbx; Block
0x180001d54  setnz   sil
0x180001d58  call    cs:__imp_free
0x180001d5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d65  cmp     rcx, rbp
0x180001d68  jz      short loc_180001D74
0x180001d6a  test    byte ptr [rcx+1Ch], 40h
0x180001d6e  jnz     loc_180001E51
0x180001d74  mov     eax, esi
0x180001d76  add     rsp, 30h
0x180001d7a  pop     r14
0x180001d7c  pop     rdi
0x180001d7d  pop     rsi
0x180001d7e  pop     rbp
0x180001d7f  pop     rbx
0x180001d80  retn
0x180001d81  test    byte ptr [rcx+1Ch], 40h
0x180001d85  jz      loc_180001C92
0x180001d8b  cmp     byte ptr [rcx+19h], 6
0x180001d8f  jb      loc_180001C92
0x180001d95  mov     rcx, [rcx+10h]
0x180001d99  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180001da0  mov     edx, 10h
0x180001da5  call    WPP_SF_
0x180001daa  jmp     loc_180001C92
0x180001daf  test    byte ptr [rcx+1Ch], 40h
0x180001db3  jz      loc_180001CD3
0x180001db9  cmp     byte ptr [rcx+19h], 5
0x180001dbd  jb      loc_180001CD3
0x180001dc3  mov     rcx, [rcx+10h]
0x180001dc7  lea     r9, aNull; "<NULL>"
0x180001dce  test    rbx, rbx
0x180001dd1  cmovnz  r9, rbx
0x180001dd5  call    WPP_SF_s
0x180001dda  jmp     loc_180001CD3
0x180001ddf  call    cs:__imp__strlwr
0x180001de5  mov     rcx, rax; Str
0x180001de8  lea     rdx, SubStr; "-k netsvcs"
0x180001def  call    cs:__imp_strstr
0x180001df5  test    rax, rax
0x180001df8  mov     ecx, 1
0x180001dfd  cmovnz  esi, ecx
0x180001e00  jmp     loc_180001D5E
0x180001e05  mov     rcx, [rsp+58h+hKey]; hKey
0x180001e0a  lea     rax, [rsp+58h+cbData]
0x180001e0f  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180001e14  lea     r9, [rsp+58h+Type]; lpType
0x180001e19  lea     rax, [rsp+58h+Data]
0x180001e1e  mov     [rsp+58h+Type], r14d
0x180001e23  xor     r8d, r8d; lpReserved
0x180001e26  mov     [rsp+58h+phkResult], rax; lpData
0x180001e2b  lea     rdx, ValueName; "ForceCmdLowerCase"
0x180001e32  mov     [rsp+58h+Data], r14d
0x180001e37  mov     [rsp+58h+cbData], 4
0x180001e3f  call    cs:__imp_RegQueryValueExA
0x180001e45  test    eax, eax
0x180001e47  cmovz   edi, [rsp+58h+Data]
0x180001e4c  jmp     loc_180001D02
0x180001e51  cmp     byte ptr [rcx+19h], 6
0x180001e55  jb      loc_180001D74
0x180001e5b  mov     rcx, [rcx+10h]
0x180001e5f  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180001e66  movzx   r9d, sil
0x180001e6a  mov     edx, 12h
0x180001e6f  call    WPP_SF_c
0x180001e74  jmp     loc_180001D74
```
