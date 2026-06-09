# DsRolepGetRegStringValue

- ea: `0x18000ad2c`
- end: `0x18000ae91`
- name: `DsRolepGetRegStringValue`
- size: `357`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180003ff0`

## callees

- `0x18000ad2c`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000add7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ae3c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000add7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ae3c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ad84`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ad84`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ae7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ae7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae68`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000adf3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000adf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae01`

## string_xrefs

- `0x18000ad6f`: `System\CurrentControlSet\Services\NTDS\Parameters`
- `0x18000ad93`: `RegOpenKeyEx failed with %d\n`

## pseudocode

```c
__int64 __fastcall DsRolepGetRegStringValue(__int64 a1, __int64 a2, _QWORD *a3)
{
  LSTATUS v4; // eax
  DWORD LastError; // ebx
  LSTATUS ValueW; // eax
  HLOCAL pvData; // rdi
  DWORD pdwType; // [rsp+60h] [rbp+20h] BYREF
  int v10; // [rsp+64h] [rbp+24h]
  DWORD pcbData; // [rsp+68h] [rbp+28h] BYREF
  int v12; // [rsp+6Ch] [rbp+2Ch]
  HKEY hkey; // [rsp+70h] [rbp+30h] BYREF

  v12 = HIDWORD(a2);
  v10 = HIDWORD(a1);
  *a3 = 0;
  hkey = 0;
  pdwType = 0;
  pcbData = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\NTDS\\Parameters", 0, 0x2000000u, &hkey);
  LastError = v4;
  if ( v4 )
  {
    DsRolepLogPrintRoutine(1, "RegOpenKeyEx failed with %d\n", v4);
    return LastError;
  }
  ValueW = RegGetValueW(hkey, 0, L"ReturnedSite", 2u, &pdwType, 0, &pcbData);
  LastError = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = LocalAlloc(0, pcbData);
    if ( !pvData )
    {
      LastError = GetLastError();
      DsRolepLogPrintRoutine(1, "LocalAlloc() failed with %d\n", LastError);
      goto LABEL_10;
    }
    LastError = RegGetValueW(hkey, 0, L"ReturnedSite", 2u, &pdwType, pvData, &pcbData);
    if ( !LastError )
      goto LABEL_13;
  }
  else
  {
    pvData = 0;
  }
  DsRolepLogPrintRoutine(1, "RegQueryValueEx failed with %d\n", LastError);
LABEL_10:
  if ( LastError )
  {
    if ( pvData )
      LocalFree(pvData);
    goto LABEL_14;
  }
LABEL_13:
  *a3 = pvData;
LABEL_14:
  if ( hkey )
    RegCloseKey(hkey);
  return LastError;
}

```

## disassembly

```asm
0x18000ad2c  mov     r11, rsp
0x18000ad2f  mov     [r11+20h], rbx
0x18000ad33  mov     [r11+10h], rdx
0x18000ad37  mov     [r11+8], rcx
0x18000ad3b  push    rbp
0x18000ad3c  push    rsi
0x18000ad3d  push    rdi
0x18000ad3e  mov     rbp, rsp
0x18000ad41  sub     rsp, 40h
0x18000ad45  mov     rsi, r8
0x18000ad48  mov     qword ptr [r8], 0
0x18000ad4f  lea     rax, [rbp+hkey]
0x18000ad53  mov     [rbp+hkey], 0
0x18000ad5b  xor     r8d, r8d; ulOptions
0x18000ad5e  mov     [r11-38h], rax
0x18000ad62  mov     r9d, 2000000h; samDesired
0x18000ad68  mov     [rbp+arg_0], 0
0x18000ad6f  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\NT"...
0x18000ad76  mov     [rbp+arg_8], 0
0x18000ad7d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ad84  call    cs:__imp_RegOpenKeyExW
0x18000ad8a  mov     ebx, eax
0x18000ad8c  test    eax, eax
0x18000ad8e  jz      short loc_18000ADA9
0x18000ad90  mov     r8d, eax
0x18000ad93  lea     rdx, aRegopenkeyexFa; "RegOpenKeyEx failed with %d\n"
0x18000ad9a  mov     ecx, 1
0x18000ad9f  call    DsRolepLogPrintRoutine
0x18000ada4  jmp     loc_18000AE82
0x18000ada9  mov     rcx, [rbp+hkey]; hkey
0x18000adad  lea     rax, [rbp+arg_8]
0x18000adb1  mov     [rsp+40h+pcbData], rax; pcbData
0x18000adb6  lea     r8, Value; "ReturnedSite"
0x18000adbd  lea     rax, [rbp+arg_0]
0x18000adc1  mov     [rsp+40h+pvData], 0; pvData
0x18000adca  mov     r9d, 2; dwFlags
0x18000add0  mov     [rsp+40h+pdwType], rax; pdwType
0x18000add5  xor     edx, edx; lpSubKey
0x18000add7  call    cs:__imp_RegGetValueW
0x18000addd  mov     ebx, eax
0x18000addf  test    eax, eax
0x18000ade1  jz      short loc_18000ADEE
0x18000ade3  cmp     eax, 0EAh
0x18000ade8  jz      short loc_18000ADEE
0x18000adea  xor     edi, edi
0x18000adec  jmp     short loc_18000AE48
0x18000adee  mov     edx, [rbp+arg_8]; uBytes
0x18000adf1  xor     ecx, ecx; uFlags
0x18000adf3  call    cs:__imp_LocalAlloc
0x18000adf9  mov     rdi, rax
0x18000adfc  test    rax, rax
0x18000adff  jnz     short loc_18000AE12
0x18000ae01  call    cs:__imp_GetLastError
0x18000ae07  mov     ebx, eax
0x18000ae09  lea     rdx, aLocalallocFail; "LocalAlloc() failed with %d\n"
0x18000ae10  jmp     short loc_18000AE4F
0x18000ae12  mov     rcx, [rbp+hkey]; hkey
0x18000ae16  lea     rax, [rbp+arg_8]
0x18000ae1a  mov     [rsp+40h+pcbData], rax; pcbData
0x18000ae1f  lea     r8, Value; "ReturnedSite"
0x18000ae26  lea     rax, [rbp+arg_0]
0x18000ae2a  mov     [rsp+40h+pvData], rdi; pvData
0x18000ae2f  mov     r9d, 2; dwFlags
0x18000ae35  mov     [rsp+40h+pdwType], rax; pdwType
0x18000ae3a  xor     edx, edx; lpSubKey
0x18000ae3c  call    cs:__imp_RegGetValueW
0x18000ae42  mov     ebx, eax
0x18000ae44  test    eax, eax
0x18000ae46  jz      short loc_18000AE70
0x18000ae48  lea     rdx, aRegqueryvaluee; "RegQueryValueEx failed with %d\n"
0x18000ae4f  mov     ecx, 1
0x18000ae54  mov     r8d, ebx
0x18000ae57  call    DsRolepLogPrintRoutine
0x18000ae5c  test    ebx, ebx
0x18000ae5e  jz      short loc_18000AE70
0x18000ae60  test    rdi, rdi
0x18000ae63  jz      short loc_18000AE73
0x18000ae65  mov     rcx, rdi; hMem
0x18000ae68  call    cs:__imp_LocalFree
0x18000ae6e  jmp     short loc_18000AE73
0x18000ae70  mov     [rsi], rdi
0x18000ae73  mov     rcx, [rbp+hkey]; hKey
0x18000ae77  test    rcx, rcx
0x18000ae7a  jz      short loc_18000AE82
0x18000ae7c  call    cs:__imp_RegCloseKey
0x18000ae82  mov     eax, ebx
0x18000ae84  mov     rbx, [rsp+40h+arg_18]
0x18000ae89  add     rsp, 40h
0x18000ae8d  pop     rdi
0x18000ae8e  pop     rsi
0x18000ae8f  pop     rbp
0x18000ae90  retn
```
