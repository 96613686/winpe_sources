# GetSessionDefaultPrinter

- ea: `0x18001393c`
- end: `0x180013af9`
- name: `GetSessionDefaultPrinter`
- size: `445`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001366c`

## callees

- `0x18001393c`
- `0x180013c90`
- `0x180013f98`
- `0x18003f278`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013a9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013a9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013a0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013a0c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013a54`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013a54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013ae6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013ae6`
- `SPOOLSS!DllFreeSplMem` at `0x180013a66`
- `SPOOLSS!DllFreeSplMem` at `0x180013a8c`
- `SPOOLSS!DllFreeSplMem` at `0x180013ac0`
- `SPOOLSS!DllFreeSplMem` at `0x180013acf`
- `SPOOLSS!DllFreeSplMem` at `0x180013a66`
- `SPOOLSS!DllFreeSplMem` at `0x180013a8c`
- `SPOOLSS!DllFreeSplMem` at `0x180013ac0`
- `SPOOLSS!DllFreeSplMem` at `0x180013acf`
- `SPOOLSS!DllAllocSplMem` at `0x180013a1b`
- `SPOOLSS!DllAllocSplMem` at `0x180013a1b`
- `KERNEL32!RegOpenCurrentUser` at `0x1800139e8`
- `KERNEL32!RegOpenCurrentUser` at `0x1800139e8`

## pseudocode

```c
__int64 __fastcall GetSessionDefaultPrinter(LPCWSTR lpSubKey, __int64 a2, _QWORD *a3)
{
  int UniqueSessionKey; // eax
  unsigned int ValueW; // ebx
  const WCHAR *v7; // r14
  LSTATUS v8; // eax
  void *pvData; // rdi
  void *v10; // rcx
  HLOCAL hMem[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD pcbData; // [rsp+88h] [rbp+38h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp+40h] BYREF
  LPCWSTR lpSubKeya; // [rsp+98h] [rbp+48h] BYREF

  hMem[0] = 0;
  lpSubKeya = 0;
  *a3 = 0;
  if ( a2
    || (UniqueSessionKey = GetUniqueSessionKey(lpSubKey, hMem), ValueW = UniqueSessionKey == 0 ? 2 : 0, UniqueSessionKey) )
  {
    ValueW = StrCatAlloc(
               &lpSubKeya,
               L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Windows",
               L"\\",
               L"SessionDefaultDevices");
    if ( !ValueW )
    {
      v7 = lpSubKeya;
      pcbData = 1040;
      phkResult = 0;
      if ( lpSubKey )
        v8 = RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0x20019u, &phkResult);
      else
        v8 = RegOpenCurrentUser(0x20019u, &phkResult);
      ValueW = v8;
      if ( v8 )
      {
        pvData = 0;
      }
      else
      {
        while ( 1 )
        {
          pvData = (void *)DllAllocSplMem(pcbData);
          if ( !pvData )
            break;
          ValueW = RegGetValueW(phkResult, v7, L"Device", 2u, 0, pvData, &pcbData);
          if ( ValueW != 234 )
            goto LABEL_13;
          DllFreeSplMem(pvData);
        }
        ValueW = 8;
      }
LABEL_13:
      v10 = 0;
      if ( ValueW )
      {
        v10 = pvData;
        pvData = 0;
      }
      if ( v10 )
        DllFreeSplMem(v10);
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( ValueW || (ValueW = RemovePortInformationFromPrinterName(pvData)) != 0 )
      {
        if ( pvData )
          DllFreeSplMem(pvData);
      }
      else
      {
        *a3 = pvData;
      }
    }
  }
  if ( lpSubKeya )
  {
    DllFreeSplMem(lpSubKeya);
    lpSubKeya = 0;
  }
  if ( hMem[0] )
    LocalFree(hMem[0]);
  return ValueW;
}

```

## disassembly

```asm
0x18001393c  push    rbp
0x18001393e  push    rbx
0x18001393f  push    rsi
0x180013940  push    rdi
0x180013941  push    r14
0x180013943  mov     rbp, rsp
0x180013946  sub     rsp, 50h
0x18001394a  mov     [rbp+hMem], 0
0x180013952  mov     rsi, r8
0x180013955  mov     [rbp+lpSubKey], 0
0x18001395d  mov     rdi, rcx
0x180013960  mov     qword ptr [r8], 0
0x180013967  test    rdx, rdx
0x18001396a  jnz     short loc_18001398C
0x18001396c  lea     rdx, [rbp+hMem]
0x180013970  call    GetUniqueSessionKey
0x180013975  mov     edx, eax
0x180013977  neg     edx
0x180013979  sbb     ebx, ebx
0x18001397b  not     ebx
0x18001397d  and     ebx, 2
0x180013980  test    eax, eax
0x180013982  jz      loc_180013AC6
0x180013988  mov     rdx, [rbp+hMem]
0x18001398c  mov     [rsp+50h+pcbData], 0
0x180013995  lea     r8, SubBlock; "\\"
0x18001399c  mov     [rsp+50h+pvData], rdx
0x1800139a1  lea     r9, aSessiondefault; "SessionDefaultDevices"
0x1800139a8  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800139af  mov     [rsp+50h+var_30], r8
0x1800139b4  lea     rcx, [rbp+lpSubKey]
0x1800139b8  call    StrCatAlloc
0x1800139bd  mov     ebx, eax
0x1800139bf  test    eax, eax
0x1800139c1  jnz     loc_180013AC6
0x1800139c7  mov     r14, [rbp+lpSubKey]
0x1800139cb  mov     [rbp+arg_8], 410h
0x1800139d2  mov     [rbp+phkResult], 0
0x1800139da  test    rdi, rdi
0x1800139dd  jnz     short loc_1800139F0
0x1800139df  lea     rdx, [rbp+phkResult]; phkResult
0x1800139e3  mov     ecx, 20019h; samDesired
0x1800139e8  call    cs:__imp_RegOpenCurrentUser
0x1800139ee  jmp     short loc_180013A12
0x1800139f0  lea     rax, [rbp+phkResult]
0x1800139f4  mov     r9d, 20019h; samDesired
0x1800139fa  xor     r8d, r8d; ulOptions
0x1800139fd  mov     [rsp+50h+var_30], rax; phkResult
0x180013a02  mov     rdx, rdi; lpSubKey
0x180013a05  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180013a0c  call    cs:__imp_RegOpenKeyExW
0x180013a12  mov     ebx, eax
0x180013a14  test    eax, eax
0x180013a16  jnz     short loc_180013A75
0x180013a18  mov     ecx, [rbp+arg_8]
0x180013a1b  call    cs:__imp_DllAllocSplMem
0x180013a21  mov     rdi, rax
0x180013a24  test    rax, rax
0x180013a27  jz      short loc_180013A6E
0x180013a29  mov     rcx, [rbp+phkResult]; hkey
0x180013a2d  lea     rax, [rbp+arg_8]
0x180013a31  mov     [rsp+50h+pcbData], rax; pcbData
0x180013a36  lea     r8, Value; "Device"
0x180013a3d  mov     [rsp+50h+pvData], rdi; pvData
0x180013a42  mov     r9d, 2; dwFlags
0x180013a48  mov     rdx, r14; lpSubKey
0x180013a4b  mov     [rsp+50h+var_30], 0; pdwType
0x180013a54  call    cs:__imp_RegGetValueW
0x180013a5a  mov     ebx, eax
0x180013a5c  cmp     eax, 0EAh
0x180013a61  jnz     short loc_180013A77
0x180013a63  mov     rcx, rdi
0x180013a66  call    cs:__imp_DllFreeSplMem
0x180013a6c  jmp     short loc_180013A18
0x180013a6e  mov     ebx, 8
0x180013a73  jmp     short loc_180013A77
0x180013a75  xor     edi, edi
0x180013a77  xor     ecx, ecx
0x180013a79  test    ebx, ebx
0x180013a7b  cmovnz  rcx, rdi
0x180013a7f  xor     eax, eax
0x180013a81  test    ebx, ebx
0x180013a83  cmovnz  rdi, rax
0x180013a87  test    rcx, rcx
0x180013a8a  jz      short loc_180013A92
0x180013a8c  call    cs:__imp_DllFreeSplMem
0x180013a92  mov     rcx, [rbp+phkResult]; hKey
0x180013a96  test    rcx, rcx
0x180013a99  jz      short loc_180013AA1
0x180013a9b  call    cs:__imp_RegCloseKey
0x180013aa1  test    ebx, ebx
0x180013aa3  jnz     short loc_180013AB8
0x180013aa5  mov     rcx, rdi
0x180013aa8  call    RemovePortInformationFromPrinterName
0x180013aad  mov     ebx, eax
0x180013aaf  test    eax, eax
0x180013ab1  jnz     short loc_180013AB8
0x180013ab3  mov     [rsi], rdi
0x180013ab6  jmp     short loc_180013AC6
0x180013ab8  test    rdi, rdi
0x180013abb  jz      short loc_180013AC6
0x180013abd  mov     rcx, rdi
0x180013ac0  call    cs:__imp_DllFreeSplMem
0x180013ac6  mov     rcx, [rbp+lpSubKey]
0x180013aca  test    rcx, rcx
0x180013acd  jz      short loc_180013ADD
0x180013acf  call    cs:__imp_DllFreeSplMem
0x180013ad5  mov     [rbp+lpSubKey], 0
0x180013add  mov     rcx, [rbp+hMem]; hMem
0x180013ae1  test    rcx, rcx
0x180013ae4  jz      short loc_180013AEC
0x180013ae6  call    cs:__imp_LocalFree
0x180013aec  mov     eax, ebx
0x180013aee  add     rsp, 50h
0x180013af2  pop     r14
0x180013af4  pop     rdi
0x180013af5  pop     rsi
0x180013af6  pop     rbx
0x180013af7  pop     rbp
0x180013af8  retn
```
