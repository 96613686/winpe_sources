# CFeatureArray::_InitializeRootKeys(void)

- ea: `0x180023824`
- end: `0x18002397b`
- name: `?_InitializeRootKeys@CFeatureArray@@AEAAJXZ`
- size: `343`
- prototype: `__int64 __fastcall(CFeatureArray *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002331c`

## callees

- `0x180023824`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800238ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800238ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002382f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002382f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002386f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800238c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002391c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002395d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002386f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800238c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002391c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002395d`

## pseudocode

```c
__int64 __fastcall CFeatureArray::_InitializeRootKeys(CFeatureArray *this)
{
  EnterCriticalSection(&stru_180298A50);
  if ( !byte_180298A78 )
  {
    if ( !phkResult
      && RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Policies\\Microsoft\\Internet Explorer\\Main\\FeatureControl",
           0,
           1u,
           &phkResult) )
    {
      phkResult = 0;
    }
    if ( !*(&phkResult + 1)
      && RegOpenKeyExW(
           HKEY_CURRENT_USER,
           L"Software\\Policies\\Microsoft\\Internet Explorer\\Main\\FeatureControl",
           0,
           1u,
           &phkResult + 1) )
    {
      *(&phkResult + 1) = 0;
    }
    if ( !xmmword_180298A90
      && RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Internet Explorer\\Main\\FeatureControl",
           0,
           1u,
           &xmmword_180298A90) )
    {
      xmmword_180298A90 = 0;
    }
    if ( !*(&xmmword_180298A90 + 1)
      && RegOpenKeyExW(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Internet Explorer\\Main\\FeatureControl",
           0,
           1u,
           &xmmword_180298A90 + 1) )
    {
      *(&xmmword_180298A90 + 1) = 0;
    }
    byte_180298A78 = 1;
  }
  LeaveCriticalSection(&stru_180298A50);
  return 0;
}

```

## disassembly

```asm
0x180023824  sub     rsp, 38h
0x180023828  lea     rcx, stru_180298A50; lpCriticalSection
0x18002382f  call    cs:__imp_EnterCriticalSection
0x180023835  cmp     cs:byte_180298A78, 0
0x18002383c  jnz     loc_1800238E5
0x180023842  cmp     qword ptr cs:phkResult, 0
0x18002384a  jnz     short loc_180023884
0x18002384c  lea     rax, phkResult
0x180023853  mov     r9d, 1; samDesired
0x180023859  xor     r8d, r8d; ulOptions
0x18002385c  mov     [rsp+38h+phkResult], rax; phkResult
0x180023861  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Internet"...
0x180023868  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002386f  call    cs:__imp_RegOpenKeyExW
0x180023875  test    eax, eax
0x180023877  jz      short loc_180023884
0x180023879  mov     qword ptr cs:phkResult, 0
0x180023884  cmp     qword ptr cs:phkResult+8, 0
0x18002388c  jz      short loc_1800238F9
0x18002388e  cmp     qword ptr cs:xmmword_180298A90, 0
0x180023896  jz      loc_18002393A
0x18002389c  cmp     qword ptr cs:xmmword_180298A90+8, 0
0x1800238a4  jnz     short loc_1800238DE
0x1800238a6  lea     rax, xmmword_180298A90+8
0x1800238ad  mov     r9d, 1; samDesired
0x1800238b3  xor     r8d, r8d; ulOptions
0x1800238b6  mov     [rsp+38h+phkResult], rax; phkResult
0x1800238bb  lea     rdx, aSoftwareMicros_34; "Software\\Microsoft\\Internet Explorer"...
0x1800238c2  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800238c9  call    cs:__imp_RegOpenKeyExW
0x1800238cf  test    eax, eax
0x1800238d1  jz      short loc_1800238DE
0x1800238d3  mov     qword ptr cs:xmmword_180298A90+8, 0
0x1800238de  mov     cs:byte_180298A78, 1
0x1800238e5  lea     rcx, stru_180298A50; lpCriticalSection
0x1800238ec  call    cs:__imp_LeaveCriticalSection
0x1800238f2  xor     eax, eax
0x1800238f4  add     rsp, 38h
0x1800238f8  retn
0x1800238f9  lea     rax, phkResult+8
0x180023900  mov     r9d, 1; samDesired
0x180023906  xor     r8d, r8d; ulOptions
0x180023909  mov     [rsp+38h+phkResult], rax; phkResult
0x18002390e  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Internet"...
0x180023915  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002391c  call    cs:__imp_RegOpenKeyExW
0x180023922  test    eax, eax
0x180023924  jz      loc_18002388E
0x18002392a  mov     qword ptr cs:phkResult+8, 0
0x180023935  jmp     loc_18002388E
0x18002393a  lea     rax, xmmword_180298A90
0x180023941  mov     r9d, 1; samDesired
0x180023947  xor     r8d, r8d; ulOptions
0x18002394a  mov     [rsp+38h+phkResult], rax; phkResult
0x18002394f  lea     rdx, aSoftwareMicros_34; "Software\\Microsoft\\Internet Explorer"...
0x180023956  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002395d  call    cs:__imp_RegOpenKeyExW
0x180023963  test    eax, eax
0x180023965  jz      loc_18002389C
0x18002396b  mov     qword ptr cs:xmmword_180298A90, 0
0x180023976  jmp     loc_18002389C
```
