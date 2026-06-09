# GetCustomScriptDll

- ea: `0x18001bf40`
- end: `0x18001c209`
- name: `GetCustomScriptDll`
- size: `713`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000c3c0`
- `0x18001bf40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c103`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001bff9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001bff9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001c033`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001c0be`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001c033`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001c0be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c1b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c1b5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c06e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c06e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c197`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c197`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x18001c0f0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x18001c11d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x18001c0f0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x18001c11d`

## string_xrefs

- `0x18001bfeb`: `System\CurrentControlSet\Services\Rasman\Parameters`
- `0x18001c02c`: `CustomScriptDllPath`
- `0x18001c0a1`: `CustomScriptDllPath`

## pseudocode

```c
DWORD __fastcall GetCustomScriptDll(__int64 a1, __int64 a2, __int64 a3)
{
  struct _LIST_ENTRY *v4; // rcx
  DWORD result; // eax
  unsigned int v6; // ebx
  BYTE *v7; // rax
  CHAR *v8; // rsi
  DWORD v9; // eax
  DWORD LastError; // eax
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+40h] BYREF
  DWORD Type; // [rsp+88h] [rbp+48h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1175, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  hKey = 0;
  cbData = 0;
  Type = 0;
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v4[1].Blink) & 0x2000) != 0
    && BYTE1(v4[1].Blink) >= 4u )
  {
    WPP_SF_(v4[1].Flink, 1176, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
  }
  result = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\Rasman\\Parameters", 0, 1u, &hKey);
  v6 = result;
  if ( !result )
  {
    result = RegQueryValueExA(hKey, "CustomScriptDllPath", 0, &Type, 0, &cbData);
    v6 = result;
    if ( !result )
    {
      if ( Type == 2 )
      {
        result = cbData - 1;
        if ( cbData - 1 <= 0x103 )
        {
          v7 = (BYTE *)LocalAlloc(0x40u, cbData + 1);
          v8 = (CHAR *)v7;
          if ( !v7 )
          {
            result = GetLastError();
            v6 = result;
            *(_DWORD *)a3 = result;
            goto LABEL_33;
          }
          v7[cbData] = 0;
          v6 = RegQueryValueExA(hKey, "CustomScriptDllPath", 0, &Type, v7, &cbData);
          if ( v6 || Type != 2 || cbData - 1 > 0x103 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1177, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v6);
            }
          }
          else
          {
            v9 = ExpandEnvironmentStringsA(v8, 0, 0);
            cbData = v9;
            if ( !v9 || !ExpandEnvironmentStringsA(v8, (LPSTR)(a3 + 4), v9) )
            {
              LastError = GetLastError();
              v6 = LastError;
LABEL_30:
              *(_DWORD *)a3 = LastError;
              result = (unsigned int)LocalFree(v8);
              goto LABEL_33;
            }
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
            {
              WPP_SF_s(WPP_GLOBAL_Control[1].Flink, 1178, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, a3 + 4);
            }
          }
          LastError = v6;
          goto LABEL_30;
        }
      }
      v6 = -2147467259;
    }
  }
  *(_DWORD *)a3 = v6;
LABEL_33:
  if ( hKey )
    result = RegCloseKey(hKey);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    return WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 1179, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v6);
  }
  return result;
}

```

## disassembly

```asm
0x18001bf40  mov     [rsp-28h+arg_0], rbx
0x18001bf45  mov     [rsp-28h+arg_8], rsi
0x18001bf4a  push    rbp
0x18001bf4b  push    rdi
0x18001bf4c  push    r12
0x18001bf4e  push    r13
0x18001bf50  push    r14
0x18001bf52  mov     rbp, rsp
0x18001bf55  sub     rsp, 40h
0x18001bf59  mov     rdi, r8
0x18001bf5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf63  lea     r13, WPP_GLOBAL_Control
0x18001bf6a  mov     r12d, 2000h
0x18001bf70  cmp     rcx, r13
0x18001bf73  jz      short loc_18001BF9D
0x18001bf75  test    [rcx+1Ch], r12d
0x18001bf79  jz      short loc_18001BF9D
0x18001bf7b  cmp     byte ptr [rcx+19h], 6
0x18001bf7f  jb      short loc_18001BF9D
0x18001bf81  mov     rcx, [rcx+10h]
0x18001bf85  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x18001bf8c  mov     edx, 497h
0x18001bf91  call    WPP_SF_
0x18001bf96  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf9d  mov     [rbp+hKey], 0
0x18001bfa5  mov     [rbp+cbData], 0
0x18001bfac  mov     [rbp+Type], 0
0x18001bfb3  cmp     rcx, r13
0x18001bfb6  jz      short loc_18001BFD9
0x18001bfb8  test    [rcx+1Ch], r12d
0x18001bfbc  jz      short loc_18001BFD9
0x18001bfbe  cmp     byte ptr [rcx+19h], 4
0x18001bfc2  jb      short loc_18001BFD9
0x18001bfc4  mov     rcx, [rcx+10h]
0x18001bfc8  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x18001bfcf  mov     edx, 498h
0x18001bfd4  call    WPP_SF_
0x18001bfd9  lea     rax, [rbp+hKey]
0x18001bfdd  mov     r9d, 1; samDesired
0x18001bfe3  xor     r8d, r8d; ulOptions
0x18001bfe6  mov     [rsp+40h+phkResult], rax; phkResult
0x18001bfeb  lea     rdx, aSystemCurrentc_20; "System\\CurrentControlSet\\Services\\Ra"...
0x18001bff2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001bff9  call    cs:__imp_RegOpenKeyExA
0x18001c000  nop     dword ptr [rax+rax+00h]
0x18001c005  mov     ebx, eax
0x18001c007  test    eax, eax
0x18001c009  jnz     loc_18001C1AA
0x18001c00f  mov     rcx, [rbp+hKey]; hKey
0x18001c013  lea     rax, [rbp+cbData]
0x18001c017  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18001c01c  lea     r9, [rbp+Type]; lpType
0x18001c020  xor     r8d, r8d; lpReserved
0x18001c023  mov     [rsp+40h+phkResult], 0; lpData
0x18001c02c  lea     rdx, aCustomscriptdl; "CustomScriptDllPath"
0x18001c033  call    cs:__imp_RegQueryValueExA
0x18001c03a  nop     dword ptr [rax+rax+00h]
0x18001c03f  mov     ebx, eax
0x18001c041  test    eax, eax
0x18001c043  jnz     loc_18001C1AA
0x18001c049  cmp     [rbp+Type], 2
0x18001c04d  jnz     loc_18001C1A5
0x18001c053  mov     ecx, [rbp+cbData]
0x18001c056  mov     r14d, 103h
0x18001c05c  lea     eax, [rcx-1]
0x18001c05f  cmp     eax, r14d
0x18001c062  ja      loc_18001C1A5
0x18001c068  lea     edx, [rcx+1]; uBytes
0x18001c06b  lea     ecx, [rbx+40h]; uFlags
0x18001c06e  call    cs:__imp_LocalAlloc
0x18001c075  nop     dword ptr [rax+rax+00h]
0x18001c07a  mov     rsi, rax
0x18001c07d  test    rax, rax
0x18001c080  jnz     short loc_18001C097
0x18001c082  call    cs:__imp_GetLastError
0x18001c089  nop     dword ptr [rax+rax+00h]
0x18001c08e  mov     ebx, eax
0x18001c090  mov     [rdi], eax
0x18001c092  jmp     loc_18001C1AC
0x18001c097  mov     eax, [rbp+cbData]
0x18001c09a  lea     r9, [rbp+Type]; lpType
0x18001c09e  xor     r8d, r8d; lpReserved
0x18001c0a1  lea     rdx, aCustomscriptdl; "CustomScriptDllPath"
0x18001c0a8  mov     byte ptr [rax+rsi], 0
0x18001c0ac  lea     rax, [rbp+cbData]
0x18001c0b0  mov     rcx, [rbp+hKey]; hKey
0x18001c0b4  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18001c0b9  mov     [rsp+40h+phkResult], rsi; lpData
0x18001c0be  call    cs:__imp_RegQueryValueExA
0x18001c0c5  nop     dword ptr [rax+rax+00h]
0x18001c0ca  mov     ebx, eax
0x18001c0cc  test    eax, eax
0x18001c0ce  jnz     loc_18001C160
0x18001c0d4  cmp     [rbp+Type], 2
0x18001c0d8  jnz     loc_18001C160
0x18001c0de  mov     eax, [rbp+cbData]
0x18001c0e1  dec     eax
0x18001c0e3  cmp     eax, r14d
0x18001c0e6  ja      short loc_18001C160
0x18001c0e8  xor     r8d, r8d; nSize
0x18001c0eb  xor     edx, edx; lpDst
0x18001c0ed  mov     rcx, rsi; lpSrc
0x18001c0f0  call    cs:__imp_ExpandEnvironmentStringsA
0x18001c0f7  nop     dword ptr [rax+rax+00h]
0x18001c0fc  mov     [rbp+cbData], eax
0x18001c0ff  test    eax, eax
0x18001c101  jnz     short loc_18001C113
0x18001c103  call    cs:__imp_GetLastError
0x18001c10a  nop     dword ptr [rax+rax+00h]
0x18001c10f  mov     ebx, eax
0x18001c111  jmp     short loc_18001C192
0x18001c113  mov     r8d, eax; nSize
0x18001c116  lea     rdx, [rdi+4]; lpDst
0x18001c11a  mov     rcx, rsi; lpSrc
0x18001c11d  call    cs:__imp_ExpandEnvironmentStringsA
0x18001c124  nop     dword ptr [rax+rax+00h]
0x18001c129  test    eax, eax
0x18001c12b  jz      short loc_18001C103
0x18001c12d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c134  cmp     rcx, r13
0x18001c137  jz      short loc_18001C190
0x18001c139  test    [rcx+1Ch], r12d
0x18001c13d  jz      short loc_18001C190
0x18001c13f  cmp     byte ptr [rcx+19h], 4
0x18001c143  jb      short loc_18001C190
0x18001c145  mov     rcx, [rcx+10h]
0x18001c149  lea     r9, [rdi+4]
0x18001c14d  mov     edx, 49Ah
0x18001c152  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x18001c159  call    WPP_SF_s
0x18001c15e  jmp     short loc_18001C190
0x18001c160  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c167  cmp     rcx, r13
0x18001c16a  jz      short loc_18001C190
0x18001c16c  test    [rcx+1Ch], r12d
0x18001c170  jz      short loc_18001C190
0x18001c172  cmp     byte ptr [rcx+19h], 2
0x18001c176  jb      short loc_18001C190
0x18001c178  mov     rcx, [rcx+10h]
0x18001c17c  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x18001c183  mov     edx, 499h
0x18001c188  mov     r9d, ebx
0x18001c18b  call    WPP_SF_d
0x18001c190  mov     eax, ebx
0x18001c192  mov     rcx, rsi; hMem
0x18001c195  mov     [rdi], eax
0x18001c197  call    cs:__imp_LocalFree
0x18001c19e  nop     dword ptr [rax+rax+00h]
0x18001c1a3  jmp     short loc_18001C1AC
0x18001c1a5  mov     ebx, 80004005h
0x18001c1aa  mov     [rdi], ebx
0x18001c1ac  mov     rcx, [rbp+hKey]; hKey
0x18001c1b0  test    rcx, rcx
0x18001c1b3  jz      short loc_18001C1C1
0x18001c1b5  call    cs:__imp_RegCloseKey
0x18001c1bc  nop     dword ptr [rax+rax+00h]
0x18001c1c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c1c8  cmp     rcx, r13
0x18001c1cb  jz      short loc_18001C1F1
0x18001c1cd  test    [rcx+1Ch], r12d
0x18001c1d1  jz      short loc_18001C1F1
0x18001c1d3  cmp     byte ptr [rcx+19h], 6
0x18001c1d7  jb      short loc_18001C1F1
0x18001c1d9  mov     rcx, [rcx+10h]
0x18001c1dd  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x18001c1e4  mov     edx, 49Bh
0x18001c1e9  mov     r9d, ebx
0x18001c1ec  call    WPP_SF_d
0x18001c1f1  mov     rbx, [rsp+40h+arg_0]
0x18001c1f6  mov     rsi, [rsp+40h+arg_8]
0x18001c1fb  add     rsp, 40h
0x18001c1ff  pop     r14
0x18001c201  pop     r13
0x18001c203  pop     r12
0x18001c205  pop     rdi
0x18001c206  pop     rbp
0x18001c207  retn
```
