# CreateShellSessionSubKey(ushort const *,ulong,bool *,HKEY__ * *)

- ea: `0x18000ad30`
- end: `0x18000aea7`
- name: `?CreateShellSessionSubKey@@YAJPEBGKPEA_NPEAPEAUHKEY__@@@Z`
- size: `375`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, REGSAM samDesired, bool *, HKEY *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000c470`
- `0x18000c6d0`
- `0x1800632a0`

## callees

- `0x18000ad30`
- `0x18000aeb0`
- `0x18002a3d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000ad7a`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000ad7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ad6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ad6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ae6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ae9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ae6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ae9f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ae01`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ae49`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ae01`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ae49`

## pseudocode

```c
int __fastcall CreateShellSessionSubKey(LPCWSTR lpSubKey, REGSAM samDesired, bool *a3, HKEY *a4)
{
  DWORD CurrentProcessId; // eax
  int result; // eax
  bool v9; // sf
  LSTATUS v10; // eax
  signed int v11; // edi
  DWORD dwDisposition; // [rsp+50h] [rbp-E8h] BYREF
  DWORD pSessionId[2]; // [rsp+58h] [rbp-E0h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-D8h] BYREF
  WCHAR SubKey[80]; // [rsp+70h] [rbp-C8h] BYREF

  if ( a4 )
    *a4 = 0;
  hKey = 0;
  pSessionId[0] = 0;
  CurrentProcessId = GetCurrentProcessId();
  ProcessIdToSessionId(CurrentProcessId, pSessionId);
  result = StringCchPrintfW(
             SubKey,
             0x4Bu,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\SessionInfo\\%d",
             pSessionId[0]);
  if ( result >= 0 )
  {
    dwDisposition = 0;
    result = RegCreateKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0, 1u, 4u, 0, &hKey, &dwDisposition);
    v9 = result < 0;
    if ( result > 0 )
    {
      result = (unsigned __int16)result | 0x80070000;
      v9 = result < 0;
    }
    if ( !v9 )
    {
      *(_QWORD *)pSessionId = 0;
      dwDisposition = 0;
      v10 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 1u, samDesired, 0, (PHKEY)pSessionId, &dwDisposition);
      v11 = v10;
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
      if ( v11 >= 0 )
      {
        if ( a4 )
          *a4 = *(HKEY *)pSessionId;
        else
          RegCloseKey(*(HKEY *)pSessionId);
      }
      RegCloseKey(hKey);
      return v11;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ad30  mov     [rsp+arg_10], rbx
0x18000ad35  push    rbp
0x18000ad36  push    rsi
0x18000ad37  push    rdi
0x18000ad38  sub     rsp, 120h
0x18000ad3f  mov     rax, cs:__security_cookie
0x18000ad46  xor     rax, rsp
0x18000ad49  mov     [rsp+138h+var_28], rax
0x18000ad51  xor     ebp, ebp
0x18000ad53  mov     rbx, r9
0x18000ad56  mov     esi, edx
0x18000ad58  mov     rdi, rcx
0x18000ad5b  test    r9, r9
0x18000ad5e  jnz     loc_18000AE78
0x18000ad64  mov     [rsp+138h+hKey], rbp
0x18000ad69  mov     [rsp+138h+pSessionId], ebp
0x18000ad6d  call    cs:__imp_GetCurrentProcessId
0x18000ad73  mov     ecx, eax; dwProcessId
0x18000ad75  lea     rdx, [rsp+138h+pSessionId]; pSessionId
0x18000ad7a  call    cs:__imp_ProcessIdToSessionId
0x18000ad80  mov     r9d, [rsp+138h+pSessionId]
0x18000ad85  lea     r8, ?shellSessionKeyFormat@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000ad8c  mov     edx, 4Bh ; 'K'; unsigned __int64
0x18000ad91  lea     rcx, [rsp+138h+SubKey]; unsigned __int16 *
0x18000ad96  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ad9b  test    eax, eax
0x18000ad9d  jns     short loc_18000ADC2
0x18000ad9f  mov     rcx, [rsp+138h+var_28]
0x18000ada7  xor     rcx, rsp; StackCookie
0x18000adaa  call    __security_check_cookie
0x18000adaf  mov     rbx, [rsp+138h+arg_10]
0x18000adb7  add     rsp, 120h
0x18000adbe  pop     rdi
0x18000adbf  pop     rsi
0x18000adc0  pop     rbp
0x18000adc1  retn
0x18000adc2  lea     rax, [rsp+138h+dwDisposition]
0x18000adc7  mov     [rsp+138h+dwDisposition], ebp
0x18000adcb  mov     [rsp+138h+lpdwDisposition], rax; lpdwDisposition
0x18000add0  lea     rdx, [rsp+138h+SubKey]; lpSubKey
0x18000add5  lea     rax, [rsp+138h+hKey]
0x18000adda  xor     r9d, r9d; lpClass
0x18000addd  mov     [rsp+138h+phkResult], rax; phkResult
0x18000ade2  xor     r8d, r8d; Reserved
0x18000ade5  mov     [rsp+138h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x18000adea  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000adf1  mov     [rsp+138h+samDesired], 4; samDesired
0x18000adf9  mov     [rsp+138h+dwOptions], 1; dwOptions
0x18000ae01  call    cs:__imp_RegCreateKeyExW
0x18000ae07  test    eax, eax
0x18000ae09  jg      short loc_18000AE80
0x18000ae0b  js      short loc_18000AD9F
0x18000ae0d  mov     rcx, [rsp+138h+hKey]; hKey
0x18000ae12  lea     rax, [rsp+138h+dwDisposition]
0x18000ae17  mov     [rsp+138h+lpdwDisposition], rax; lpdwDisposition
0x18000ae1c  xor     r9d, r9d; lpClass
0x18000ae1f  lea     rax, [rsp+138h+pSessionId]
0x18000ae24  mov     qword ptr [rsp+138h+pSessionId], rbp
0x18000ae29  mov     [rsp+138h+phkResult], rax; phkResult
0x18000ae2e  xor     r8d, r8d; Reserved
0x18000ae31  mov     [rsp+138h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x18000ae36  mov     rdx, rdi; lpSubKey
0x18000ae39  mov     [rsp+138h+samDesired], esi; samDesired
0x18000ae3d  mov     [rsp+138h+dwOptions], 1; dwOptions
0x18000ae45  mov     [rsp+138h+dwDisposition], ebp
0x18000ae49  call    cs:__imp_RegCreateKeyExW
0x18000ae4f  mov     edi, eax
0x18000ae51  test    eax, eax
0x18000ae53  jg      short loc_18000AE8F
0x18000ae55  test    edi, edi
0x18000ae57  js      short loc_18000AE66
0x18000ae59  test    rbx, rbx
0x18000ae5c  jz      short loc_18000AE9A
0x18000ae5e  mov     rax, qword ptr [rsp+138h+pSessionId]
0x18000ae63  mov     [rbx], rax
0x18000ae66  mov     rcx, [rsp+138h+hKey]; hKey
0x18000ae6b  call    cs:__imp_RegCloseKey
0x18000ae71  mov     eax, edi
0x18000ae73  jmp     loc_18000AD9F
0x18000ae78  mov     [r9], rbp
0x18000ae7b  jmp     loc_18000AD64
0x18000ae80  movzx   eax, ax
0x18000ae83  or      eax, 80070000h
0x18000ae88  test    eax, eax
0x18000ae8a  jmp     loc_18000AE0B
0x18000ae8f  movzx   edi, ax
0x18000ae92  or      edi, 80070000h
0x18000ae98  jmp     short loc_18000AE55
0x18000ae9a  mov     rcx, qword ptr [rsp+138h+pSessionId]; hKey
0x18000ae9f  call    cs:__imp_RegCloseKey
0x18000aea5  jmp     short loc_18000AE66
```
