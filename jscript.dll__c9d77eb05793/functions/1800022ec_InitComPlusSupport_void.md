# InitComPlusSupport(void)

- ea: `0x1800022ec`
- end: `0x180002412`
- name: `?InitComPlusSupport@@YAJXZ`
- size: `294`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002160`

## callees

- `0x1800022ec`
- `0x180096010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x18000232e`
- `ADVAPI32!RegOpenKeyExA` at `0x18000232e`
- `ADVAPI32!RegCloseKey` at `0x180002395`
- `ADVAPI32!RegCloseKey` at `0x1800023a4`
- `ADVAPI32!RegCloseKey` at `0x180002395`
- `ADVAPI32!RegCloseKey` at `0x1800023a4`
- `ADVAPI32!RegQueryValueExA` at `0x180002378`
- `ADVAPI32!RegQueryValueExA` at `0x180002378`
- `ole32!CoCreateInstance` at `0x1800023cf`
- `ole32!CoCreateInstance` at `0x1800023cf`

## string_xrefs

- `0x180002320`: `Software\Microsoft\COM3`
- `0x180002363`: `COM+Enabled`

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
0x1800022ec  push    rbp
0x1800022ee  push    rbx
0x1800022ef  mov     rbp, rsp
0x1800022f2  sub     rsp, 48h
0x1800022f6  cmp     cs:?g_fComPlusInitialized@@3KA, 0; ulong g_fComPlusInitialized
0x1800022fd  jz      short loc_180002306
0x1800022ff  xor     eax, eax
0x180002301  jmp     loc_18000240B
0x180002306  lea     rax, [rbp+hKey]
0x18000230a  mov     [rbp+hKey], 0
0x180002312  mov     r9d, 20019h; samDesired
0x180002318  mov     [rsp+48h+phkResult], rax; phkResult
0x18000231d  xor     r8d, r8d; ulOptions
0x180002320  lea     rdx, SubKey; "Software\\Microsoft\\COM3"
0x180002327  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000232e  call    cs:__imp_RegOpenKeyExA
0x180002334  test    eax, eax
0x180002336  jz      short loc_18000233F
0x180002338  xor     eax, eax
0x18000233a  jmp     loc_180002401
0x18000233f  mov     rcx, [rbp+hKey]; hKey
0x180002343  lea     rax, [rbp+cbData]
0x180002347  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000234c  lea     r9, [rbp+Type]; lpType
0x180002350  lea     rax, [rbp+Data]
0x180002354  mov     [rbp+Data], 0
0x18000235b  xor     r8d, r8d; lpReserved
0x18000235e  mov     [rsp+48h+phkResult], rax; lpData
0x180002363  lea     rdx, ValueName; "COM+Enabled"
0x18000236a  mov     [rbp+cbData], 4
0x180002371  mov     [rbp+Type], 0
0x180002378  call    cs:__imp_RegQueryValueExA
0x18000237e  test    eax, eax
0x180002380  jnz     short loc_1800023A0
0x180002382  cmp     [rbp+Data], eax
0x180002385  jnz     short loc_1800023A0
0x180002387  mov     rcx, [rbp+hKey]; hKey
0x18000238b  mov     cs:?g_fComPlusInitialized@@3KA, 1; ulong g_fComPlusInitialized
0x180002395  call    cs:__imp_RegCloseKey
0x18000239b  jmp     loc_1800022FF
0x1800023a0  mov     rcx, [rbp+hKey]; hKey
0x1800023a4  call    cs:__imp_RegCloseKey
0x1800023aa  xor     edx, edx; pUnkOuter
0x1800023ac  mov     [rbp+ppv], 0
0x1800023b4  lea     rax, [rbp+ppv]
0x1800023b8  lea     r9, IID_IGlobalInterfaceTable; riid
0x1800023bf  mov     [rsp+48h+phkResult], rax; ppv
0x1800023c4  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1800023cb  lea     r8d, [rdx+1]; dwClsContext
0x1800023cf  call    cs:__imp_CoCreateInstance
0x1800023d5  mov     ebx, eax
0x1800023d7  test    eax, eax
0x1800023d9  js      short loc_1800023FD
0x1800023db  mov     rcx, [rbp+ppv]
0x1800023df  xchg    rcx, cs:?g_pGIT@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pGIT
0x1800023e6  mov     [rbp+ppv], rcx
0x1800023ea  test    rcx, rcx
0x1800023ed  jz      short loc_1800023FF
0x1800023ef  mov     rdx, [rcx]
0x1800023f2  mov     rax, [rdx+10h]
0x1800023f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023fb  jmp     short loc_1800023FF
0x1800023fd  xor     ebx, ebx
0x1800023ff  mov     eax, ebx
0x180002401  mov     cs:?g_fComPlusInitialized@@3KA, 1; ulong g_fComPlusInitialized
0x18000240b  add     rsp, 48h
0x18000240f  pop     rbx
0x180002410  pop     rbp
0x180002411  retn
```
