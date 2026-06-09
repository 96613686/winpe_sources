# InitDebugger(void)

- ea: `0x180046c90`
- end: `0x180046da9`
- name: `?InitDebugger@@YAXXZ`
- size: `281`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18004e180`

## callees

- `0x180046c90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046d2f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046d2f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180046cdb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180046cdb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046d91`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046d91`
- `rtutils!TraceRegisterExW` at `0x180046d6d`
- `rtutils!TraceRegisterExW` at `0x180046d6d`

## pseudocode

```c
void InitDebugger(void)
{
  int v0; // ebx
  __int64 v1; // rdi
  __int64 v2; // rsi
  LSTATUS v3; // eax
  int v4; // ecx
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  int Data; // [rsp+68h] [rbp+38h] BYREF
  DWORD Type; // [rsp+70h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+48h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, g_szDebugKey, 0, 0x20019u, &hKey) )
  {
    v0 = 0;
    v1 = 0;
    do
    {
      cbData = 4;
      v2 = 328 * v1;
      v3 = RegQueryValueExW(hKey, &aDebuglevel[164 * v1], 0, &Type, (LPBYTE)&Data, &cbData);
      v4 = Data;
      if ( v3 || Type != 4 )
        *(_DWORD *)((char *)&g_DebugInfo + v2 + 4) = dword_1800AD934;
      else
        *(_DWORD *)((char *)&g_DebugInfo + v2 + 4) = Data;
      if ( v0 == 4 && v4 == 1 )
        g_uTraceId = TraceRegisterExW(g_szModule, 0);
      ++v0;
      ++v1;
    }
    while ( v0 < 5 );
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x180046c90  push    rbp
0x180046c92  push    rbx
0x180046c93  push    rsi
0x180046c94  push    rdi
0x180046c95  push    r15
0x180046c97  mov     rbp, rsp
0x180046c9a  sub     rsp, 30h
0x180046c9e  lea     rax, [rbp+hKey]
0x180046ca2  mov     [rbp+hKey], 0
0x180046caa  mov     r9d, 20019h; samDesired
0x180046cb0  mov     [rsp+30h+phkResult], rax; phkResult
0x180046cb5  xor     r8d, r8d; ulOptions
0x180046cb8  mov     [rbp+Type], 0
0x180046cbf  lea     rdx, ?g_szDebugKey@@3PAGA; "SOFTWARE\\Microsoft\\Tracing\\Beacon\\D"...
0x180046cc6  mov     [rbp+cbData], 0
0x180046ccd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180046cd4  mov     [rbp+Data], 0
0x180046cdb  call    cs:__imp_RegOpenKeyExW
0x180046ce2  nop     dword ptr [rax+rax+00h]
0x180046ce7  test    eax, eax
0x180046ce9  jnz     loc_180046D9D
0x180046cef  xor     ebx, ebx
0x180046cf1  lea     r15, ?g_DebugInfo@@3PAU_DEBUG_MODULE_INFO@@A; _DEBUG_MODULE_INFO near * g_DebugInfo
0x180046cf8  xor     edi, edi
0x180046cfa  mov     rcx, [rbp+hKey]; hKey
0x180046cfe  lea     rax, [rbp+cbData]
0x180046d02  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180046d07  lea     rdx, [r15+0A8h]
0x180046d0e  lea     rax, [rbp+Data]
0x180046d12  mov     [rbp+cbData], 4
0x180046d19  imul    rsi, rdi, 148h
0x180046d20  lea     r9, [rbp+Type]; lpType
0x180046d24  mov     [rsp+30h+phkResult], rax; lpData
0x180046d29  add     rdx, rsi; lpValueName
0x180046d2c  xor     r8d, r8d; lpReserved
0x180046d2f  call    cs:__imp_RegQueryValueExW
0x180046d36  nop     dword ptr [rax+rax+00h]
0x180046d3b  mov     ecx, [rbp+Data]
0x180046d3e  test    eax, eax
0x180046d40  jnz     short loc_180046D4F
0x180046d42  cmp     [rbp+Type], 4
0x180046d46  jnz     short loc_180046D4F
0x180046d48  mov     [rsi+r15+4], ecx
0x180046d4d  jmp     short loc_180046D5A
0x180046d4f  mov     eax, cs:dword_1800AD934
0x180046d55  mov     [rsi+r15+4], eax
0x180046d5a  cmp     ebx, 4
0x180046d5d  jnz     short loc_180046D7F
0x180046d5f  cmp     ecx, 1
0x180046d62  jnz     short loc_180046D7F
0x180046d64  xor     edx, edx; dwFlags
0x180046d66  lea     rcx, ?g_szModule@@3PAGA; "Beacon"
0x180046d6d  call    cs:__imp_TraceRegisterExW
0x180046d74  nop     dword ptr [rax+rax+00h]
0x180046d79  mov     cs:?g_uTraceId@@3KA, eax; ulong g_uTraceId
0x180046d7f  inc     ebx
0x180046d81  inc     rdi
0x180046d84  cmp     ebx, 5
0x180046d87  jl      loc_180046CFA
0x180046d8d  mov     rcx, [rbp+hKey]; hKey
0x180046d91  call    cs:__imp_RegCloseKey
0x180046d98  nop     dword ptr [rax+rax+00h]
0x180046d9d  add     rsp, 30h
0x180046da1  pop     r15
0x180046da3  pop     rdi
0x180046da4  pop     rsi
0x180046da5  pop     rbx
0x180046da6  pop     rbp
0x180046da7  retn
```
