# InitComPlusSupport(void)

- ea: `0x18003fc6c`
- end: `0x18003fdb1`
- name: `?InitComPlusSupport@@YAJXZ`
- size: `325`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003fac8`

## callees

- `0x18003fc6c`
- `0x180098010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x18003fcae`
- `ADVAPI32!RegOpenKeyExA` at `0x18003fcae`
- `ADVAPI32!RegCloseKey` at `0x18003fd21`
- `ADVAPI32!RegCloseKey` at `0x18003fd36`
- `ADVAPI32!RegCloseKey` at `0x18003fd21`
- `ADVAPI32!RegCloseKey` at `0x18003fd36`
- `ADVAPI32!RegQueryValueExA` at `0x18003fcfe`
- `ADVAPI32!RegQueryValueExA` at `0x18003fcfe`
- `ole32!CoCreateInstance` at `0x18003fd67`
- `ole32!CoCreateInstance` at `0x18003fd67`

## string_xrefs

- `0x18003fca0`: `Software\Microsoft\COM3`
- `0x18003fce9`: `COM+Enabled`

## pseudocode

```c
__int64 InitComPlusSupport(void)
{
  __int64 result; // rax
  HRESULT v1; // ebx
  void *v2; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-18h] BYREF
  int Data; // [rsp+60h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+20h] BYREF
  DWORD Type; // [rsp+70h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+30h] BYREF

  if ( g_fComPlusInitialized )
    return 0;
  hKey = 0;
  if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\COM3", 0, 0x20019u, &hKey) )
  {
    result = 0;
  }
  else
  {
    Data = 0;
    cbData = 4;
    Type = 0;
    if ( !RegQueryValueExA(hKey, "COM+Enabled", 0, &Type, (LPBYTE)&Data, &cbData) && !Data )
    {
      g_fComPlusInitialized = 1;
      RegCloseKey(hKey);
      return 0;
    }
    RegCloseKey(hKey);
    ppv = 0;
    v1 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &IID_IGlobalInterfaceTable, &ppv);
    if ( v1 < 0 )
    {
      v1 = 0;
    }
    else
    {
      v2 = (void *)_InterlockedExchange64((volatile __int64 *)&g_pGIT, (__int64)ppv);
      ppv = v2;
      if ( v2 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v2 + 16LL))(v2);
    }
    result = (unsigned int)v1;
  }
  g_fComPlusInitialized = 1;
  return result;
}

```

## disassembly

```asm
0x18003fc6c  push    rbp
0x18003fc6e  push    rbx
0x18003fc6f  mov     rbp, rsp
0x18003fc72  sub     rsp, 48h
0x18003fc76  cmp     cs:?g_fComPlusInitialized@@3KA, 0; ulong g_fComPlusInitialized
0x18003fc7d  jz      short loc_18003FC86
0x18003fc7f  xor     eax, eax
0x18003fc81  jmp     loc_18003FDA9
0x18003fc86  lea     rax, [rbp+hKey]
0x18003fc8a  mov     [rbp+hKey], 0
0x18003fc92  mov     r9d, 20019h; samDesired
0x18003fc98  mov     [rsp+48h+phkResult], rax; phkResult
0x18003fc9d  xor     r8d, r8d; ulOptions
0x18003fca0  lea     rdx, SubKey; "Software\\Microsoft\\COM3"
0x18003fca7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003fcae  call    cs:__imp_RegOpenKeyExA
0x18003fcb5  nop     dword ptr [rax+rax+00h]
0x18003fcba  test    eax, eax
0x18003fcbc  jz      short loc_18003FCC5
0x18003fcbe  xor     eax, eax
0x18003fcc0  jmp     loc_18003FD9F
0x18003fcc5  mov     rcx, [rbp+hKey]; hKey
0x18003fcc9  lea     rax, [rbp+cbData]
0x18003fccd  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18003fcd2  lea     r9, [rbp+Type]; lpType
0x18003fcd6  lea     rax, [rbp+Data]
0x18003fcda  mov     [rbp+Data], 0
0x18003fce1  xor     r8d, r8d; lpReserved
0x18003fce4  mov     [rsp+48h+phkResult], rax; lpData
0x18003fce9  lea     rdx, ValueName; "COM+Enabled"
0x18003fcf0  mov     [rbp+cbData], 4
0x18003fcf7  mov     [rbp+Type], 0
0x18003fcfe  call    cs:__imp_RegQueryValueExA
0x18003fd05  nop     dword ptr [rax+rax+00h]
0x18003fd0a  test    eax, eax
0x18003fd0c  jnz     short loc_18003FD32
0x18003fd0e  cmp     [rbp+Data], eax
0x18003fd11  jnz     short loc_18003FD32
0x18003fd13  mov     rcx, [rbp+hKey]; hKey
0x18003fd17  mov     cs:?g_fComPlusInitialized@@3KA, 1; ulong g_fComPlusInitialized
0x18003fd21  call    cs:__imp_RegCloseKey
0x18003fd28  nop     dword ptr [rax+rax+00h]
0x18003fd2d  jmp     loc_18003FC7F
0x18003fd32  mov     rcx, [rbp+hKey]; hKey
0x18003fd36  call    cs:__imp_RegCloseKey
0x18003fd3d  nop     dword ptr [rax+rax+00h]
0x18003fd42  xor     edx, edx; pUnkOuter
0x18003fd44  mov     [rbp+ppv], 0
0x18003fd4c  lea     rax, [rbp+ppv]
0x18003fd50  lea     r9, IID_IGlobalInterfaceTable; riid
0x18003fd57  mov     [rsp+48h+phkResult], rax; ppv
0x18003fd5c  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18003fd63  lea     r8d, [rdx+1]; dwClsContext
0x18003fd67  call    cs:__imp_CoCreateInstance
0x18003fd6e  nop     dword ptr [rax+rax+00h]
0x18003fd73  mov     ebx, eax
0x18003fd75  test    eax, eax
0x18003fd77  js      short loc_18003FD9B
0x18003fd79  mov     rcx, [rbp+ppv]
0x18003fd7d  xchg    rcx, cs:?g_pGIT@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pGIT
0x18003fd84  mov     [rbp+ppv], rcx
0x18003fd88  test    rcx, rcx
0x18003fd8b  jz      short loc_18003FD9D
0x18003fd8d  mov     rdx, [rcx]
0x18003fd90  mov     rax, [rdx+10h]
0x18003fd94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd99  jmp     short loc_18003FD9D
0x18003fd9b  xor     ebx, ebx
0x18003fd9d  mov     eax, ebx
0x18003fd9f  mov     cs:?g_fComPlusInitialized@@3KA, 1; ulong g_fComPlusInitialized
0x18003fda9  add     rsp, 48h
0x18003fdad  pop     rbx
0x18003fdae  pop     rbp
0x18003fdaf  retn
```
