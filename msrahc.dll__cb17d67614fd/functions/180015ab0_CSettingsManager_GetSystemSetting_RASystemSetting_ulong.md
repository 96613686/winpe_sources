# CSettingsManager::GetSystemSetting(_RASystemSetting,ulong *)

- ea: `0x180015ab0`
- end: `0x180015ba9`
- name: `?GetSystemSetting@CSettingsManager@@QEAAJW4_RASystemSetting@@PEAK@Z`
- size: `249`
- prototype: `__int64 __fastcall(HANDLE *, DWORD, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180011170`

## callees

- `0x180015ab0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180015b65`
- `ADVAPI32!RegQueryValueExW` at `0x180015b65`
- `ADVAPI32!RegOpenKeyExW` at `0x180015b34`
- `ADVAPI32!RegOpenKeyExW` at `0x180015b34`
- `ADVAPI32!RegCloseKey` at `0x180015b80`
- `ADVAPI32!RegCloseKey` at `0x180015b80`
- `KERNEL32!ReleaseMutex` at `0x180015b96`
- `KERNEL32!ReleaseMutex` at `0x180015b96`
- `KERNEL32!WaitForSingleObject` at `0x180015afc`
- `KERNEL32!WaitForSingleObject` at `0x180015afc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSettingsManager::GetSystemSetting(HANDLE *a1, DWORD a2, _DWORD *a3)
{
  HANDLE v4; // rcx
  unsigned int v6; // ebx
  int v7; // edi
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  int Data; // [rsp+70h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF
  DWORD Type; // [rsp+88h] [rbp+48h] BYREF

  cbData = a2;
  hKey = 0;
  v4 = *a1;
  cbData = 0;
  Data = 0;
  Type = 4;
  if ( !v4 )
    return (unsigned int)-2147418113;
  if ( WaitForSingleObject(v4, 0x64u) == 258 )
  {
    v7 = 0;
  }
  else
  {
    v7 = 1;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Remote Assistance", 0, 1u, &hKey) )
    {
      cbData = 4;
      if ( !RegQueryValueExW(hKey, RA_SYSTEM_SETTINGS, 0, &Type, (LPBYTE)&Data, &cbData) )
      {
        v6 = 0;
        *a3 = Data;
        goto LABEL_9;
      }
    }
  }
  v6 = -2147467259;
LABEL_9:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v7 == 1 )
    ReleaseMutex(*a1);
  return v6;
}

```

## disassembly

```asm
0x180015ab0  mov     [rsp-28h+cbData], edx
0x180015ab4  push    rbp
0x180015ab5  push    rbx
0x180015ab6  push    rsi
0x180015ab7  push    rdi
0x180015ab8  push    r14
0x180015aba  mov     rbp, rsp
0x180015abd  sub     rsp, 40h
0x180015ac1  mov     rsi, rcx
0x180015ac4  mov     [rbp+hKey], 0
0x180015acc  mov     rcx, [rcx]; hHandle
0x180015acf  mov     ebx, 4
0x180015ad4  mov     [rbp+cbData], 0
0x180015adb  mov     r14, r8
0x180015ade  mov     [rbp+Data], 0
0x180015ae5  mov     [rbp+Type], ebx
0x180015ae8  test    rcx, rcx
0x180015aeb  jnz     short loc_180015AF7
0x180015aed  mov     ebx, 8000FFFFh
0x180015af2  jmp     loc_180015B9C
0x180015af7  mov     edx, 64h ; 'd'; dwMilliseconds
0x180015afc  call    cs:__imp_WaitForSingleObject
0x180015b02  cmp     eax, 102h
0x180015b07  jnz     short loc_180015B12
0x180015b09  xor     edi, edi
0x180015b0b  mov     ebx, 80004005h
0x180015b10  jmp     short loc_180015B77
0x180015b12  lea     rax, [rbp+hKey]
0x180015b16  mov     edi, 1
0x180015b1b  mov     r9d, edi; samDesired
0x180015b1e  mov     [rsp+40h+phkResult], rax; phkResult
0x180015b23  xor     r8d, r8d; ulOptions
0x180015b26  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Rem"...
0x180015b2d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015b34  call    cs:__imp_RegOpenKeyExW
0x180015b3a  test    eax, eax
0x180015b3c  jnz     short loc_180015B0B
0x180015b3e  mov     rdx, cs:?RA_SYSTEM_SETTINGS@@3PAPEBGA; lpValueName
0x180015b45  lea     rax, [rbp+cbData]
0x180015b49  mov     rcx, [rbp+hKey]; hKey
0x180015b4d  lea     r9, [rbp+Type]; lpType
0x180015b51  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180015b56  xor     r8d, r8d; lpReserved
0x180015b59  lea     rax, [rbp+Data]
0x180015b5d  mov     [rbp+cbData], ebx
0x180015b60  mov     [rsp+40h+phkResult], rax; lpData
0x180015b65  call    cs:__imp_RegQueryValueExW
0x180015b6b  test    eax, eax
0x180015b6d  jnz     short loc_180015B0B
0x180015b6f  mov     eax, [rbp+Data]
0x180015b72  xor     ebx, ebx
0x180015b74  mov     [r14], eax
0x180015b77  mov     rcx, [rbp+hKey]; hKey
0x180015b7b  test    rcx, rcx
0x180015b7e  jz      short loc_180015B8E
0x180015b80  call    cs:__imp_RegCloseKey
0x180015b86  mov     [rbp+hKey], 0
0x180015b8e  cmp     edi, 1
0x180015b91  jnz     short loc_180015B9C
0x180015b93  mov     rcx, [rsi]; hMutex
0x180015b96  call    cs:__imp_ReleaseMutex
0x180015b9c  mov     eax, ebx
0x180015b9e  add     rsp, 40h
0x180015ba2  pop     r14
0x180015ba4  pop     rdi
0x180015ba5  pop     rsi
0x180015ba6  pop     rbx
0x180015ba7  pop     rbp
0x180015ba8  retn
```
