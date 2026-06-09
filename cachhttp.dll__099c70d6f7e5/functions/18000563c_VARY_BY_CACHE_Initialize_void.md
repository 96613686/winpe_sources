# VARY_BY_CACHE::Initialize(void)

- ea: `0x18000563c`
- end: `0x180005742`
- name: `?Initialize@VARY_BY_CACHE@@QEAAJXZ`
- size: `262`
- prototype: `__int64 __fastcall(VARY_BY_CACHE *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1800039d0`

## callees

- `0x18000563c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800056aa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800056aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800056d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800056d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800056ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800056ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005724`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000571a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000571a`
- `iisutil!?Initialize@TREE_HASH_TABLE@@QEAAJK@Z` at `0x180005677`
- `iisutil!?Initialize@TREE_HASH_TABLE@@QEAAJK@Z` at `0x180005677`

## string_xrefs

- `0x180005697`: `System\CurrentControlSet\Services\inetinfo\Parameters`
- `0x1800056cc`: `OutputCacheTTL`

## pseudocode

```c
signed int __fastcall VARY_BY_CACHE::Initialize(VARY_BY_CACHE *this)
{
  void **v1; // rdi
  signed int result; // eax
  int v3; // ebx
  DWORD Type; // [rsp+60h] [rbp+20h] BYREF
  int v5; // [rsp+64h] [rbp+24h]
  int Data; // [rsp+68h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+38h] BYREF

  v5 = HIDWORD(this);
  v1 = (void **)g_pVaryByCache;
  Data = 0;
  Type = 0;
  cbData = 4;
  hKey = 0;
  result = TREE_HASH_TABLE::Initialize((TREE_HASH_TABLE *)g_pVaryByCache, 0x1A5u);
  if ( result >= 0 )
  {
    v3 = 900;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\inetinfo\\Parameters",
            0,
            0x20019u,
            &hKey) )
    {
      if ( !RegQueryValueExW(hKey, L"OutputCacheTTL", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
        v3 = Data;
      RegCloseKey(hKey);
    }
    if ( CreateTimerQueueTimer(v1 + 5, 0, VARY_BY_CACHE::ScavengerCallback, v1, 1000 * v3, 1000 * v3, 0x10u) )
    {
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000563c  mov     qword ptr [rsp-18h+Type], rcx
0x180005641  push    rbp
0x180005642  push    rbx
0x180005643  push    rdi
0x180005644  mov     rbp, rsp
0x180005647  sub     rsp, 40h
0x18000564b  mov     rdi, cs:?g_pVaryByCache@@3PEAVVARY_BY_CACHE@@EA; VARY_BY_CACHE * g_pVaryByCache
0x180005652  mov     edx, 1A5h
0x180005657  mov     rcx, rdi
0x18000565a  mov     [rbp+Data], 0
0x180005661  mov     [rbp+Type], 0
0x180005668  mov     [rbp+cbData], 4
0x18000566f  mov     [rbp+hKey], 0
0x180005677  call    cs:__imp_?Initialize@TREE_HASH_TABLE@@QEAAJK@Z; TREE_HASH_TABLE::Initialize(ulong)
0x18000567d  test    eax, eax
0x18000567f  js      loc_18000573A
0x180005685  lea     rax, [rbp+hKey]
0x180005689  mov     r9d, 20019h; samDesired
0x18000568f  xor     r8d, r8d; ulOptions
0x180005692  mov     [rsp+40h+phkResult], rax; phkResult
0x180005697  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\in"...
0x18000569e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800056a5  mov     ebx, 384h
0x1800056aa  call    cs:__imp_RegOpenKeyExW
0x1800056b0  test    eax, eax
0x1800056b2  jnz     short loc_1800056F4
0x1800056b4  mov     rcx, [rbp+hKey]; hKey
0x1800056b8  lea     rax, [rbp+cbData]
0x1800056bc  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800056c1  lea     r9, [rbp+Type]; lpType
0x1800056c5  lea     rax, [rbp+Data]
0x1800056c9  xor     r8d, r8d; lpReserved
0x1800056cc  lea     rdx, ValueName; "OutputCacheTTL"
0x1800056d3  mov     [rsp+40h+phkResult], rax; lpData
0x1800056d8  call    cs:__imp_RegQueryValueExW
0x1800056de  test    eax, eax
0x1800056e0  jnz     short loc_1800056EA
0x1800056e2  cmp     [rbp+Type], 4
0x1800056e6  cmovz   ebx, [rbp+Data]
0x1800056ea  mov     rcx, [rbp+hKey]; hKey
0x1800056ee  call    cs:__imp_RegCloseKey
0x1800056f4  imul    eax, ebx, 3E8h
0x1800056fa  lea     rcx, [rdi+28h]; phNewTimer
0x1800056fe  mov     [rsp+40h+Flags], 10h; Flags
0x180005706  lea     r8, ?ScavengerCallback@VARY_BY_CACHE@@CAXPEAXE@Z; Callback
0x18000570d  mov     r9, rdi; Parameter
0x180005710  xor     edx, edx; TimerQueue
0x180005712  mov     dword ptr [rsp+40h+lpcbData], eax; Period
0x180005716  mov     dword ptr [rsp+40h+phkResult], eax; DueTime
0x18000571a  call    cs:__imp_CreateTimerQueueTimer
0x180005720  test    eax, eax
0x180005722  jnz     short loc_180005738
0x180005724  call    cs:__imp_GetLastError
0x18000572a  test    eax, eax
0x18000572c  jle     short loc_18000573A
0x18000572e  movzx   eax, ax
0x180005731  or      eax, 80070000h
0x180005736  jmp     short loc_18000573A
0x180005738  xor     eax, eax
0x18000573a  add     rsp, 40h
0x18000573e  pop     rdi
0x18000573f  pop     rbx
0x180005740  pop     rbp
0x180005741  retn
```
