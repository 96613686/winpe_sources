# IsRasmanProcess

- ea: `0x180001c40`
- end: `0x180001e86`
- name: `IsRasmanProcess`
- size: `582`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180001250`
- `0x180001450`
- `0x1800016f0`
- `0x1800030d0`
- `0x18000b230`
- `0x18001c280`
- `0x18001d770`

## callees

- `0x180001c40`
- `0x180001e8c`
- `0x180021ae4`
- `0x180021f24`
- `0x1800227a8`

## import_xrefs

- `msvcrt!_strdup` at `0x180001d09`
- `msvcrt!_strdup` at `0x180001d09`
- `msvcrt!strstr` at `0x180001d36`
- `msvcrt!strstr` at `0x180001df0`
- `msvcrt!strstr` at `0x180001d36`
- `msvcrt!strstr` at `0x180001df0`
- `msvcrt!free` at `0x180001d4c`
- `msvcrt!free` at `0x180001d4c`
- `msvcrt!_strlwr` at `0x180001d20`
- `msvcrt!_strlwr` at `0x180001dda`
- `msvcrt!_strlwr` at `0x180001d20`
- `msvcrt!_strlwr` at `0x180001dda`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180001e46`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180001e46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001ce8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001ce8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180001cca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180001cca`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x180001c70`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x180001c70`

## string_xrefs

- `0x180001cbc`: `System\CurrentControlSet\Services\rasman\parameters`

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
0x180001c40  push    rbx
0x180001c42  push    rbp
0x180001c43  push    rsi
0x180001c44  push    rdi
0x180001c45  push    r14
0x180001c47  sub     rsp, 30h
0x180001c4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c52  lea     rbp, WPP_GLOBAL_Control
0x180001c59  cmp     rcx, rbp
0x180001c5c  jnz     loc_180001D7C
0x180001c62  xor     r14d, r14d
0x180001c65  mov     esi, r14d
0x180001c68  mov     [rsp+58h+hKey], r14
0x180001c6d  mov     edi, r14d
0x180001c70  call    cs:__imp_GetCommandLineA
0x180001c77  nop     dword ptr [rax+rax+00h]
0x180001c7c  test    rax, rax
0x180001c7f  lea     rdx, aNull_0; "NULL"
0x180001c86  lea     rcx, aIsrasmanproces_0; "IsRasmanProcess: CmdLine=%s\n"
0x180001c8d  mov     rbx, rax
0x180001c90  cmovnz  rdx, rax
0x180001c94  call    RasmanOutputDebug
0x180001c99  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ca0  cmp     rcx, rbp
0x180001ca3  jnz     loc_180001DAA
0x180001ca9  lea     rax, [rsp+58h+hKey]
0x180001cae  mov     r9d, 20019h; samDesired
0x180001cb4  xor     r8d, r8d; ulOptions
0x180001cb7  mov     [rsp+58h+phkResult], rax; phkResult
0x180001cbc  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\ra"...
0x180001cc3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001cca  call    cs:__imp_RegOpenKeyExA
0x180001cd1  nop     dword ptr [rax+rax+00h]
0x180001cd6  test    eax, eax
0x180001cd8  jz      loc_180001E0C
0x180001cde  mov     rcx, [rsp+58h+hKey]; hKey
0x180001ce3  test    rcx, rcx
0x180001ce6  jz      short loc_180001CF9
0x180001ce8  call    cs:__imp_RegCloseKey
0x180001cef  nop     dword ptr [rax+rax+00h]
0x180001cf4  mov     [rsp+58h+hKey], r14
0x180001cf9  test    rbx, rbx
0x180001cfc  jz      short loc_180001D58
0x180001cfe  mov     rcx, rbx; String
0x180001d01  test    edi, edi
0x180001d03  jnz     loc_180001DDA
0x180001d09  call    cs:__imp__strdup
0x180001d10  nop     dword ptr [rax+rax+00h]
0x180001d15  mov     rbx, rax
0x180001d18  test    rax, rax
0x180001d1b  jz      short loc_180001D58
0x180001d1d  mov     rcx, rax; String
0x180001d20  call    cs:__imp__strlwr
0x180001d27  nop     dword ptr [rax+rax+00h]
0x180001d2c  mov     rcx, rax; Str
0x180001d2f  lea     rdx, SubStr; "-k netsvcs"
0x180001d36  call    cs:__imp_strstr
0x180001d3d  nop     dword ptr [rax+rax+00h]
0x180001d42  test    rax, rax
0x180001d45  mov     rcx, rbx; Block
0x180001d48  setnz   sil
0x180001d4c  call    cs:__imp_free
0x180001d53  nop     dword ptr [rax+rax+00h]
0x180001d58  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d5f  cmp     rcx, rbp
0x180001d62  jz      short loc_180001D6E
0x180001d64  test    byte ptr [rcx+1Ch], 40h
0x180001d68  jnz     loc_180001E5E
0x180001d6e  mov     eax, esi
0x180001d70  add     rsp, 30h
0x180001d74  pop     r14
0x180001d76  pop     rdi
0x180001d77  pop     rsi
0x180001d78  pop     rbp
0x180001d79  pop     rbx
0x180001d7a  retn
0x180001d7c  test    byte ptr [rcx+1Ch], 40h
0x180001d80  jz      loc_180001C62
0x180001d86  cmp     byte ptr [rcx+19h], 6
0x180001d8a  jb      loc_180001C62
0x180001d90  mov     rcx, [rcx+10h]
0x180001d94  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180001d9b  mov     edx, 10h
0x180001da0  call    WPP_SF_
0x180001da5  jmp     loc_180001C62
0x180001daa  test    byte ptr [rcx+1Ch], 40h
0x180001dae  jz      loc_180001CA9
0x180001db4  cmp     byte ptr [rcx+19h], 5
0x180001db8  jb      loc_180001CA9
0x180001dbe  mov     rcx, [rcx+10h]
0x180001dc2  lea     r9, aNull; "<NULL>"
0x180001dc9  test    rbx, rbx
0x180001dcc  cmovnz  r9, rbx
0x180001dd0  call    WPP_SF_s
0x180001dd5  jmp     loc_180001CA9
0x180001dda  call    cs:__imp__strlwr
0x180001de1  nop     dword ptr [rax+rax+00h]
0x180001de6  mov     rcx, rax; Str
0x180001de9  lea     rdx, SubStr; "-k netsvcs"
0x180001df0  call    cs:__imp_strstr
0x180001df7  nop     dword ptr [rax+rax+00h]
0x180001dfc  test    rax, rax
0x180001dff  mov     ecx, 1
0x180001e04  cmovnz  esi, ecx
0x180001e07  jmp     loc_180001D58
0x180001e0c  mov     rcx, [rsp+58h+hKey]; hKey
0x180001e11  lea     rax, [rsp+58h+cbData]
0x180001e16  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180001e1b  lea     r9, [rsp+58h+Type]; lpType
0x180001e20  lea     rax, [rsp+58h+Data]
0x180001e25  mov     [rsp+58h+Type], r14d
0x180001e2a  xor     r8d, r8d; lpReserved
0x180001e2d  mov     [rsp+58h+phkResult], rax; lpData
0x180001e32  lea     rdx, ValueName; "ForceCmdLowerCase"
0x180001e39  mov     [rsp+58h+Data], r14d
0x180001e3e  mov     [rsp+58h+cbData], 4
0x180001e46  call    cs:__imp_RegQueryValueExA
0x180001e4d  nop     dword ptr [rax+rax+00h]
0x180001e52  test    eax, eax
0x180001e54  cmovz   edi, [rsp+58h+Data]
0x180001e59  jmp     loc_180001CDE
0x180001e5e  cmp     byte ptr [rcx+19h], 6
0x180001e62  jb      loc_180001D6E
0x180001e68  mov     rcx, [rcx+10h]
0x180001e6c  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180001e73  movzx   r9d, sil
0x180001e77  mov     edx, 12h
0x180001e7c  call    WPP_SF_c
0x180001e81  jmp     loc_180001D6E
```
