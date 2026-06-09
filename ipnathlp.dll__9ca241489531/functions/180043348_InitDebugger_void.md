# InitDebugger(void)

- ea: `0x180043348`
- end: `0x180043448`
- name: `?InitDebugger@@YAXXZ`
- size: `256`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18004a4fc`

## callees

- `0x180043348`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800433e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800433e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043393`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043393`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043437`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043437`
- `rtutils!TraceRegisterExW` at `0x180043419`
- `rtutils!TraceRegisterExW` at `0x180043419`

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
        *(_DWORD *)((char *)&g_DebugInfo + v2 + 4) = dword_1800A6874;
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
0x180043348  push    rbp
0x18004334a  push    rbx
0x18004334b  push    rsi
0x18004334c  push    rdi
0x18004334d  push    r15
0x18004334f  mov     rbp, rsp
0x180043352  sub     rsp, 30h
0x180043356  lea     rax, [rbp+hKey]
0x18004335a  mov     [rbp+hKey], 0
0x180043362  mov     r9d, 20019h; samDesired
0x180043368  mov     [rsp+30h+phkResult], rax; phkResult
0x18004336d  xor     r8d, r8d; ulOptions
0x180043370  mov     [rbp+Type], 0
0x180043377  lea     rdx, ?g_szDebugKey@@3PAGA; "SOFTWARE\\Microsoft\\Tracing\\Beacon\\D"...
0x18004337e  mov     [rbp+cbData], 0
0x180043385  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004338c  mov     [rbp+Data], 0
0x180043393  call    cs:__imp_RegOpenKeyExW
0x180043399  test    eax, eax
0x18004339b  jnz     loc_18004343D
0x1800433a1  xor     ebx, ebx
0x1800433a3  lea     r15, ?g_DebugInfo@@3PAU_DEBUG_MODULE_INFO@@A; _DEBUG_MODULE_INFO near * g_DebugInfo
0x1800433aa  xor     edi, edi
0x1800433ac  mov     rcx, [rbp+hKey]; hKey
0x1800433b0  lea     rax, [rbp+cbData]
0x1800433b4  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800433b9  lea     rdx, [r15+0A8h]
0x1800433c0  lea     rax, [rbp+Data]
0x1800433c4  mov     [rbp+cbData], 4
0x1800433cb  imul    rsi, rdi, 148h
0x1800433d2  lea     r9, [rbp+Type]; lpType
0x1800433d6  mov     [rsp+30h+phkResult], rax; lpData
0x1800433db  add     rdx, rsi; lpValueName
0x1800433de  xor     r8d, r8d; lpReserved
0x1800433e1  call    cs:__imp_RegQueryValueExW
0x1800433e7  mov     ecx, [rbp+Data]
0x1800433ea  test    eax, eax
0x1800433ec  jnz     short loc_1800433FB
0x1800433ee  cmp     [rbp+Type], 4
0x1800433f2  jnz     short loc_1800433FB
0x1800433f4  mov     [rsi+r15+4], ecx
0x1800433f9  jmp     short loc_180043406
0x1800433fb  mov     eax, cs:dword_1800A6874
0x180043401  mov     [rsi+r15+4], eax
0x180043406  cmp     ebx, 4
0x180043409  jnz     short loc_180043425
0x18004340b  cmp     ecx, 1
0x18004340e  jnz     short loc_180043425
0x180043410  xor     edx, edx; dwFlags
0x180043412  lea     rcx, ?g_szModule@@3PAGA; "Beacon"
0x180043419  call    cs:__imp_TraceRegisterExW
0x18004341f  mov     cs:?g_uTraceId@@3KA, eax; ulong g_uTraceId
0x180043425  inc     ebx
0x180043427  inc     rdi
0x18004342a  cmp     ebx, 5
0x18004342d  jl      loc_1800433AC
0x180043433  mov     rcx, [rbp+hKey]; hKey
0x180043437  call    cs:__imp_RegCloseKey
0x18004343d  add     rsp, 30h
0x180043441  pop     r15
0x180043443  pop     rdi
0x180043444  pop     rsi
0x180043445  pop     rbx
0x180043446  pop     rbp
0x180043447  retn
```
