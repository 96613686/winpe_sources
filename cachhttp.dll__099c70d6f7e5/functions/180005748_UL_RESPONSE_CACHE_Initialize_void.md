# UL_RESPONSE_CACHE::Initialize(void)

- ea: `0x180005748`
- end: `0x180005838`
- name: `?Initialize@UL_RESPONSE_CACHE@@QEAAJXZ`
- size: `240`
- prototype: `__int64 __fastcall(UL_RESPONSE_CACHE *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1800039d0`

## callees

- `0x180005748`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800057a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800057a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800057ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800057ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800057e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800057e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000581a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000581a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180005810`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180005810`

## string_xrefs

- `0x180005777`: `System\CurrentControlSet\Services\inetinfo\Parameters`
- `0x1800057c2`: `HttpResponseCacheTTL`

## pseudocode

```c
signed int __fastcall UL_RESPONSE_CACHE::Initialize(UL_RESPONSE_CACHE *this)
{
  void **v1; // rdi
  int v2; // ebx
  signed int result; // eax
  DWORD Type; // [rsp+60h] [rbp+20h] BYREF
  int v5; // [rsp+64h] [rbp+24h]
  int Data; // [rsp+68h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+38h] BYREF

  v5 = HIDWORD(this);
  v1 = (void **)g_pUlCache;
  Data = 0;
  Type = 0;
  cbData = 4;
  v2 = 900;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\inetinfo\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    if ( !RegQueryValueExW(hKey, L"HttpResponseCacheTTL", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      v2 = Data;
    RegCloseKey(hKey);
  }
  if ( CreateTimerQueueTimer(v1 + 9, 0, UL_RESPONSE_CACHE::ScavengerCallback, v1, 1000 * v2, 1000 * v2, 0x10u) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180005748  mov     qword ptr [rsp-18h+Type], rcx
0x18000574d  push    rbp
0x18000574e  push    rbx
0x18000574f  push    rdi
0x180005750  mov     rbp, rsp
0x180005753  sub     rsp, 40h
0x180005757  mov     rdi, cs:?g_pUlCache@@3PEAVUL_RESPONSE_CACHE@@EA; UL_RESPONSE_CACHE * g_pUlCache
0x18000575e  lea     rax, [rbp+hKey]
0x180005762  mov     r9d, 20019h; samDesired
0x180005768  mov     [rsp+40h+phkResult], rax; phkResult
0x18000576d  xor     r8d, r8d; ulOptions
0x180005770  mov     [rbp+Data], 0
0x180005777  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\in"...
0x18000577e  mov     [rbp+Type], 0
0x180005785  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000578c  mov     [rbp+cbData], 4
0x180005793  mov     ebx, 384h
0x180005798  mov     [rbp+hKey], 0
0x1800057a0  call    cs:__imp_RegOpenKeyExW
0x1800057a6  test    eax, eax
0x1800057a8  jnz     short loc_1800057EA
0x1800057aa  mov     rcx, [rbp+hKey]; hKey
0x1800057ae  lea     rax, [rbp+cbData]
0x1800057b2  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800057b7  lea     r9, [rbp+Type]; lpType
0x1800057bb  lea     rax, [rbp+Data]
0x1800057bf  xor     r8d, r8d; lpReserved
0x1800057c2  lea     rdx, aHttpresponseca; "HttpResponseCacheTTL"
0x1800057c9  mov     [rsp+40h+phkResult], rax; lpData
0x1800057ce  call    cs:__imp_RegQueryValueExW
0x1800057d4  test    eax, eax
0x1800057d6  jnz     short loc_1800057E0
0x1800057d8  cmp     [rbp+Type], 4
0x1800057dc  cmovz   ebx, [rbp+Data]
0x1800057e0  mov     rcx, [rbp+hKey]; hKey
0x1800057e4  call    cs:__imp_RegCloseKey
0x1800057ea  imul    eax, ebx, 3E8h
0x1800057f0  lea     rcx, [rdi+48h]; phNewTimer
0x1800057f4  mov     [rsp+40h+Flags], 10h; Flags
0x1800057fc  lea     r8, ?ScavengerCallback@UL_RESPONSE_CACHE@@CAXPEAXE@Z; Callback
0x180005803  mov     r9, rdi; Parameter
0x180005806  xor     edx, edx; TimerQueue
0x180005808  mov     dword ptr [rsp+40h+lpcbData], eax; Period
0x18000580c  mov     dword ptr [rsp+40h+phkResult], eax; DueTime
0x180005810  call    cs:__imp_CreateTimerQueueTimer
0x180005816  test    eax, eax
0x180005818  jnz     short loc_18000582E
0x18000581a  call    cs:__imp_GetLastError
0x180005820  test    eax, eax
0x180005822  jle     short loc_180005830
0x180005824  movzx   eax, ax
0x180005827  or      eax, 80070000h
0x18000582c  jmp     short loc_180005830
0x18000582e  xor     eax, eax
0x180005830  add     rsp, 40h
0x180005834  pop     rdi
0x180005835  pop     rbx
0x180005836  pop     rbp
0x180005837  retn
```
