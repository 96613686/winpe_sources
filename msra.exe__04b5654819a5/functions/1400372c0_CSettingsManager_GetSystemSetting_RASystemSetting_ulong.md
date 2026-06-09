# CSettingsManager::GetSystemSetting(_RASystemSetting,ulong *)

- ea: `0x1400372c0`
- end: `0x1400373ee`
- name: `?GetSystemSetting@CSettingsManager@@QEAAJW4_RASystemSetting@@PEAK@Z`
- size: `302`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400223c4`
- `0x140022c68`
- `0x14002981c`
- `0x14002ceb0`

## callees

- `0x1400372c0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400373b0`
- `ADVAPI32!RegCloseKey` at `0x1400373b0`
- `ADVAPI32!RegOpenKeyExW` at `0x140037350`
- `ADVAPI32!RegOpenKeyExW` at `0x140037350`
- `ADVAPI32!RegQueryValueExW` at `0x14003738f`
- `ADVAPI32!RegQueryValueExW` at `0x14003738f`
- `KERNEL32!ReleaseMutex` at `0x1400373cc`
- `KERNEL32!ReleaseMutex` at `0x1400373cc`
- `KERNEL32!WaitForSingleObject` at `0x140037312`
- `KERNEL32!WaitForSingleObject` at `0x140037312`

## pseudocode

```c
__int64 __fastcall CSettingsManager::GetSystemSetting(HANDLE *a1, int a2, _DWORD *a3)
{
  __int64 v4; // rbx
  HANDLE v5; // rcx
  unsigned int v7; // ebx
  int v8; // edi
  DWORD Type; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  int Data; // [rsp+78h] [rbp+38h] BYREF

  v4 = a2;
  v5 = *a1;
  hKey = 0;
  cbData = 0;
  Data = 0;
  Type = 4;
  if ( !v5 )
    return (unsigned int)-2147418113;
  if ( WaitForSingleObject(v5, 0x64u) == 258 )
  {
    v8 = 0;
  }
  else
  {
    v8 = 1;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Remote Assistance", 0, 1u, &hKey) )
    {
      cbData = 4;
      if ( !RegQueryValueExW(hKey, (LPCWSTR)(&RA_SYSTEM_SETTINGS)[v4], 0, &Type, (LPBYTE)&Data, &cbData) )
      {
        v7 = 0;
        *a3 = Data;
        goto LABEL_9;
      }
    }
  }
  v7 = -2147467259;
LABEL_9:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v8 == 1 )
    ReleaseMutex(*a1);
  return v7;
}

```

## disassembly

```asm
0x1400372c0  mov     [rsp-18h+arg_8], rbx
0x1400372c5  mov     [rsp-18h+arg_10], rsi
0x1400372ca  push    rbp
0x1400372cb  push    rdi
0x1400372cc  push    r14
0x1400372ce  mov     rbp, rsp
0x1400372d1  sub     rsp, 40h
0x1400372d5  mov     rsi, rcx
0x1400372d8  movsxd  rbx, edx
0x1400372db  mov     rcx, [rcx]; hHandle
0x1400372de  mov     r14, r8
0x1400372e1  mov     [rbp+hKey], 0
0x1400372e9  mov     [rbp+cbData], 0
0x1400372f0  mov     [rbp+Data], 0
0x1400372f7  mov     [rbp+Type], 4
0x1400372fe  test    rcx, rcx
0x140037301  jnz     short loc_14003730D
0x140037303  mov     ebx, 8000FFFFh
0x140037308  jmp     loc_1400373D8
0x14003730d  mov     edx, 64h ; 'd'; dwMilliseconds
0x140037312  call    cs:__imp_WaitForSingleObject
0x140037319  nop     dword ptr [rax+rax+00h]
0x14003731e  cmp     eax, 102h
0x140037323  jnz     short loc_14003732E
0x140037325  xor     edi, edi
0x140037327  mov     ebx, 80004005h
0x14003732c  jmp     short loc_1400373A7
0x14003732e  lea     rax, [rbp+hKey]
0x140037332  mov     edi, 1
0x140037337  mov     r9d, edi; samDesired
0x14003733a  mov     [rsp+40h+phkResult], rax; phkResult
0x14003733f  xor     r8d, r8d; ulOptions
0x140037342  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Rem"...
0x140037349  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140037350  call    cs:__imp_RegOpenKeyExW
0x140037357  nop     dword ptr [rax+rax+00h]
0x14003735c  test    eax, eax
0x14003735e  jnz     short loc_140037327
0x140037360  lea     rax, [rbp+cbData]
0x140037364  mov     [rbp+cbData], 4
0x14003736b  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140037370  lea     rcx, ?RA_SYSTEM_SETTINGS@@3PAPEBGA; ushort const * near * RA_SYSTEM_SETTINGS
0x140037377  mov     rdx, [rcx+rbx*8]; lpValueName
0x14003737b  lea     rax, [rbp+Data]
0x14003737f  mov     rcx, [rbp+hKey]; hKey
0x140037383  lea     r9, [rbp+Type]; lpType
0x140037387  xor     r8d, r8d; lpReserved
0x14003738a  mov     [rsp+40h+phkResult], rax; lpData
0x14003738f  call    cs:__imp_RegQueryValueExW
0x140037396  nop     dword ptr [rax+rax+00h]
0x14003739b  test    eax, eax
0x14003739d  jnz     short loc_140037327
0x14003739f  mov     eax, [rbp+Data]
0x1400373a2  xor     ebx, ebx
0x1400373a4  mov     [r14], eax
0x1400373a7  mov     rcx, [rbp+hKey]; hKey
0x1400373ab  test    rcx, rcx
0x1400373ae  jz      short loc_1400373C4
0x1400373b0  call    cs:__imp_RegCloseKey
0x1400373b7  nop     dword ptr [rax+rax+00h]
0x1400373bc  mov     [rbp+hKey], 0
0x1400373c4  cmp     edi, 1
0x1400373c7  jnz     short loc_1400373D8
0x1400373c9  mov     rcx, [rsi]; hMutex
0x1400373cc  call    cs:__imp_ReleaseMutex
0x1400373d3  nop     dword ptr [rax+rax+00h]
0x1400373d8  mov     rsi, [rsp+40h+arg_10]
0x1400373dd  mov     eax, ebx
0x1400373df  mov     rbx, [rsp+40h+arg_8]
0x1400373e4  add     rsp, 40h
0x1400373e8  pop     r14
0x1400373ea  pop     rdi
0x1400373eb  pop     rbp
0x1400373ec  retn
```
