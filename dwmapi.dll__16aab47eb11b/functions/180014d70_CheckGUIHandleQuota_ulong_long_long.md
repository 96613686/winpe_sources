# CheckGUIHandleQuota(ulong,long,long)

- ea: `0x180014d70`
- end: `0x180014e62`
- name: `?CheckGUIHandleQuota@@YAJKJJ@Z`
- size: `242`
- prototype: `__int64 __fastcall(unsigned int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008ab4`

## callees

- `0x180014d70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014d8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014d8d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014e1e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014e1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014de3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014de3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014e3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014e3a`
- `USER32!GetGuiResources` at `0x180014d98`
- `USER32!GetGuiResources` at `0x180014d98`

## pseudocode

```c
__int64 __fastcall CheckGUIHandleQuota(DWORD a1, unsigned int a2, DWORD a3)
{
  unsigned int v3; // edi
  HANDLE CurrentProcess; // rax
  DWORD GuiResources; // eax
  unsigned int v6; // ebx
  DWORD v7; // esi
  unsigned int v8; // ebx
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  unsigned int Data; // [rsp+68h] [rbp+30h] BYREF
  DWORD Type; // [rsp+70h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+40h] BYREF

  Type = a3;
  Data = a2;
  cbData = a1;
  v3 = -2003304445;
  CurrentProcess = GetCurrentProcess();
  GuiResources = GetGuiResources(CurrentProcess, 0);
  v6 = (unsigned int)g_GUIHandleQuota;
  v7 = GuiResources;
  if ( GuiResources >= (unsigned int)g_GUIHandleQuota )
  {
    if ( !(_DWORD)g_GUIHandleQuota )
    {
      hKey = 0;
      v8 = 10000;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Windows", 0, 1u, &hKey) )
      {
        Type = 0;
        Data = 0;
        cbData = 4;
        if ( !RegQueryValueExW(hKey, lpValueName, 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data )
          v8 = Data;
        RegCloseKey(hKey);
      }
      v6 = v8 - (v8 >> 3);
      LODWORD(g_GUIHandleQuota) = v6;
    }
    if ( v7 >= v6 )
      return (unsigned int)-2147024882;
  }
  return v3;
}

```

## disassembly

```asm
0x180014d70  mov     [rsp-20h+Type], r8d
0x180014d75  mov     [rsp-20h+Data], edx
0x180014d79  mov     [rsp-20h+cbData], ecx
0x180014d7d  push    rbp
0x180014d7e  push    rbx
0x180014d7f  push    rsi
0x180014d80  push    rdi
0x180014d81  mov     rbp, rsp
0x180014d84  sub     rsp, 38h
0x180014d88  mov     edi, 88980003h
0x180014d8d  call    cs:__imp_GetCurrentProcess
0x180014d93  mov     rcx, rax; hProcess
0x180014d96  xor     edx, edx; uiFlags
0x180014d98  call    cs:__imp_GetGuiResources
0x180014d9e  mov     ebx, cs:?g_GUIHandleQuota@@3PAUGUIHandleQuotaInfo@@A; GUIHandleQuotaInfo near * g_GUIHandleQuota
0x180014da4  mov     esi, eax
0x180014da6  cmp     eax, ebx
0x180014da8  jb      loc_180014E57
0x180014dae  test    ebx, ebx
0x180014db0  jnz     loc_180014E4D
0x180014db6  lea     rax, [rbp+hKey]
0x180014dba  mov     [rbp+hKey], 0
0x180014dc2  mov     r9d, 1; samDesired
0x180014dc8  mov     [rsp+38h+phkResult], rax; phkResult
0x180014dcd  xor     r8d, r8d; ulOptions
0x180014dd0  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x180014dd7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014dde  mov     ebx, 2710h
0x180014de3  call    cs:__imp_RegOpenKeyExW
0x180014de9  test    eax, eax
0x180014deb  jnz     short loc_180014E40
0x180014ded  mov     rdx, cs:lpValueName; lpValueName
0x180014df4  lea     r9, [rbp+Type]; lpType
0x180014df8  mov     rcx, [rbp+hKey]; hKey
0x180014dfc  xor     r8d, r8d; lpReserved
0x180014dff  mov     [rbp+Type], eax
0x180014e02  mov     [rbp+Data], eax
0x180014e05  lea     rax, [rbp+cbData]
0x180014e09  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180014e0e  lea     rax, [rbp+Data]
0x180014e12  mov     [rsp+38h+phkResult], rax; lpData
0x180014e17  mov     [rbp+cbData], 4
0x180014e1e  call    cs:__imp_RegQueryValueExW
0x180014e24  test    eax, eax
0x180014e26  jnz     short loc_180014E36
0x180014e28  cmp     [rbp+Type], 4
0x180014e2c  jnz     short loc_180014E36
0x180014e2e  mov     eax, [rbp+Data]
0x180014e31  test    eax, eax
0x180014e33  cmovnz  ebx, eax
0x180014e36  mov     rcx, [rbp+hKey]; hKey
0x180014e3a  call    cs:__imp_RegCloseKey
0x180014e40  mov     ecx, ebx
0x180014e42  shr     ecx, 3
0x180014e45  sub     ebx, ecx
0x180014e47  mov     cs:?g_GUIHandleQuota@@3PAUGUIHandleQuotaInfo@@A, ebx; GUIHandleQuotaInfo near * g_GUIHandleQuota
0x180014e4d  cmp     esi, ebx
0x180014e4f  mov     eax, 8007000Eh
0x180014e54  cmovnb  edi, eax
0x180014e57  mov     eax, edi
0x180014e59  add     rsp, 38h
0x180014e5d  pop     rdi
0x180014e5e  pop     rsi
0x180014e5f  pop     rbx
0x180014e60  pop     rbp
0x180014e61  retn
```
