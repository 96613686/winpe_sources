# KdInstallDebugDriver

- ea: `0x1801d1b24`
- end: `0x1801d1cf1`
- name: `KdInstallDebugDriver`
- size: `461`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1804306f0`
- `0x180431030`

## callees

- `0x1800727b8`
- `0x18008e740`
- `0x180098628`
- `0x1800c12b8`
- `0x1800f0f40`
- `0x1801d1b24`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801d1b99`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801d1c46`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801d1b99`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801d1c46`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x1801d1b83`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x1801d1c30`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x1801d1b83`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x1801d1c30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d1c01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d1c7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d1ca6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d1cbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d1c01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d1c7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d1ca6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d1cbd`

## string_xrefs

- `0x1801d1b7a`: `setupapi.dll`
- `0x1801d1b92`: `SetupCopyOEMInfW`
- `0x1801d1bb2`: `Unable to find SetupCopyOEMInf API.\n%s drivers can not be installed.\n`
- `0x1801d1c0d`: `Failed to copy %s device driver inf. The debugger must be run elevated for the first use of this transport.  Error 0x%X.\n`
- `0x1801d1c27`: `newdev.dll`
- `0x1801d1c3f`: `UpdateDriverForPlugAndPlayDevicesW`
- `0x1801d1c8a`: `Failed to install %s device driver.  Error 0x%X.\n`
- `0x1801d1c97`: `Unable to find UpdateDriverForPlugAndPlayDevices API.\n%s drivers can not be installed.\n`

## pseudocode

```c
signed int __fastcall KdInstallDebugDriver(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // r8
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  DWORD v9; // eax
  HMODULE v10; // rax
  FARPROC v11; // rax
  DWORD LastError; // eax
  signed int result; // eax
  unsigned __int16 v14[264]; // [rsp+60h] [rbp-448h] BYREF
  _BYTE v15[528]; // [rsp+270h] [rbp-238h] BYREF

  if ( (unsigned int)GetEngineDirectory(v14, a2) && (unsigned int)CatNStringW(v14, a2, v6, 260) )
  {
    Library = LoadLibraryExA("setupapi.dll", 0, 0);
    ProcAddress = GetProcAddress(Library, "SetupCopyOEMInfW");
    if ( ProcAddress )
    {
      if ( ((__int64 (__fastcall *)(unsigned __int16 *, _QWORD, __int64))ProcAddress)(v14, 0, 1) )
      {
        v10 = LoadLibraryExA("newdev.dll", 0, 0);
        v11 = GetProcAddress(v10, "UpdateDriverForPlugAndPlayDevicesW");
        if ( v11 )
        {
          if ( !a3 || ((unsigned int (__fastcall *)(_QWORD, __int64, _BYTE *, __int64, _QWORD))v11)(0, a3, v15, 1, 0) )
            return 0;
          LastError = GetLastError();
          dprintf(L"Failed to install %s device driver.  Error 0x%X.\n", a1, LastError);
        }
        else
        {
          WarnOut(L"Unable to find UpdateDriverForPlugAndPlayDevices API.\n%s drivers can not be installed.\n", a1);
        }
      }
      else
      {
        v9 = GetLastError();
        dprintf(
          L"Failed to copy %s device driver inf. The debugger must be run elevated for the first use of this transport.  Error 0x%X.\n",
          a1,
          v9);
      }
    }
    else
    {
      WarnOut(L"Unable to find SetupCopyOEMInf API.\n%s drivers can not be installed.\n", a1);
    }
  }
  if ( !GetLastError() )
    return -2147467259;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1801d1b24  push    rbx
0x1801d1b26  push    rsi
0x1801d1b27  push    rdi
0x1801d1b28  sub     rsp, 490h
0x1801d1b2f  mov     rax, cs:__security_cookie
0x1801d1b36  xor     rax, rsp
0x1801d1b39  mov     [rsp+4A8h+var_28], rax
0x1801d1b41  mov     rbx, rcx
0x1801d1b44  mov     rdi, r8
0x1801d1b47  lea     rcx, [rsp+4A8h+var_448]; unsigned __int16 *
0x1801d1b4c  mov     rsi, rdx
0x1801d1b4f  call    ?GetEngineDirectory@@YAHPEAGK@Z; GetEngineDirectory(ushort *,ulong)
0x1801d1b54  test    eax, eax
0x1801d1b56  jz      loc_1801D1CA6
0x1801d1b5c  mov     r9d, 104h
0x1801d1b62  lea     rcx, [rsp+4A8h+var_448]
0x1801d1b67  mov     rdx, rsi
0x1801d1b6a  call    CatNStringW
0x1801d1b6f  test    eax, eax
0x1801d1b71  jz      loc_1801D1CA6
0x1801d1b77  xor     r8d, r8d; dwFlags
0x1801d1b7a  lea     rcx, aSetupapiDll; "setupapi.dll"
0x1801d1b81  xor     edx, edx; hFile
0x1801d1b83  call    cs:__imp_LoadLibraryExA
0x1801d1b8a  nop     dword ptr [rax+rax+00h]
0x1801d1b8f  mov     rcx, rax; hModule
0x1801d1b92  lea     rdx, aSetupcopyoemin; "SetupCopyOEMInfW"
0x1801d1b99  call    cs:__imp_GetProcAddress
0x1801d1ba0  nop     dword ptr [rax+rax+00h]
0x1801d1ba5  mov     [rsp+4A8h+var_458], 0
0x1801d1bad  test    rax, rax
0x1801d1bb0  jnz     short loc_1801D1BBE
0x1801d1bb2  lea     rcx, aUnableToFindSe; "Unable to find SetupCopyOEMInf API.\n%s"...
0x1801d1bb9  jmp     loc_1801D1C9E
0x1801d1bbe  mov     [rsp+4A8h+var_470], 0
0x1801d1bc7  lea     rcx, [rsp+4A8h+var_458]
0x1801d1bcc  mov     [rsp+4A8h+var_478], rcx
0x1801d1bd1  xor     r9d, r9d
0x1801d1bd4  lea     rcx, [rsp+4A8h+var_238]
0x1801d1bdc  mov     [rsp+4A8h+var_480], 104h
0x1801d1be4  mov     [rsp+4A8h+var_488], rcx
0x1801d1be9  xor     edx, edx
0x1801d1beb  lea     rcx, [rsp+4A8h+var_448]
0x1801d1bf0  lea     esi, [r9+1]
0x1801d1bf4  mov     r8d, esi
0x1801d1bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d1bfc  test    rax, rax
0x1801d1bff  jnz     short loc_1801D1C24
0x1801d1c01  call    cs:__imp_GetLastError
0x1801d1c08  nop     dword ptr [rax+rax+00h]
0x1801d1c0d  lea     rcx, aFailedToCopySD; "Failed to copy %s device driver inf. Th"...
0x1801d1c14  mov     rdx, rbx
0x1801d1c17  mov     r8d, eax
0x1801d1c1a  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1801d1c1f  jmp     loc_1801D1CA6
0x1801d1c24  xor     r8d, r8d; dwFlags
0x1801d1c27  lea     rcx, aNewdevDll; "newdev.dll"
0x1801d1c2e  xor     edx, edx; hFile
0x1801d1c30  call    cs:__imp_LoadLibraryExA
0x1801d1c37  nop     dword ptr [rax+rax+00h]
0x1801d1c3c  mov     rcx, rax; hModule
0x1801d1c3f  lea     rdx, aUpdatedriverfo; "UpdateDriverForPlugAndPlayDevicesW"
0x1801d1c46  call    cs:__imp_GetProcAddress
0x1801d1c4d  nop     dword ptr [rax+rax+00h]
0x1801d1c52  test    rax, rax
0x1801d1c55  jz      short loc_1801D1C97
0x1801d1c57  test    rdi, rdi
0x1801d1c5a  jz      short loc_1801D1C93
0x1801d1c5c  mov     r9d, esi
0x1801d1c5f  mov     [rsp+4A8h+var_488], 0
0x1801d1c68  lea     r8, [rsp+4A8h+var_238]
0x1801d1c70  mov     rdx, rdi
0x1801d1c73  xor     ecx, ecx
0x1801d1c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d1c7a  test    eax, eax
0x1801d1c7c  jnz     short loc_1801D1C93
0x1801d1c7e  call    cs:__imp_GetLastError
0x1801d1c85  nop     dword ptr [rax+rax+00h]
0x1801d1c8a  lea     rcx, aFailedToInstal; "Failed to install %s device driver.  Er"...
0x1801d1c91  jmp     short loc_1801D1C14
0x1801d1c93  xor     eax, eax
0x1801d1c95  jmp     short loc_1801D1CD5
0x1801d1c97  lea     rcx, aUnableToFindUp; "Unable to find UpdateDriverForPlugAndPl"...
0x1801d1c9e  mov     rdx, rbx
0x1801d1ca1  call    ?WarnOut@@YAXPEBGZZ; WarnOut(ushort const *,...)
0x1801d1ca6  call    cs:__imp_GetLastError
0x1801d1cad  nop     dword ptr [rax+rax+00h]
0x1801d1cb2  test    eax, eax
0x1801d1cb4  jnz     short loc_1801D1CBD
0x1801d1cb6  mov     eax, 80004005h
0x1801d1cbb  jmp     short loc_1801D1CD5
0x1801d1cbd  call    cs:__imp_GetLastError
0x1801d1cc4  nop     dword ptr [rax+rax+00h]
0x1801d1cc9  test    eax, eax
0x1801d1ccb  jle     short loc_1801D1CD5
0x1801d1ccd  movzx   eax, ax
0x1801d1cd0  or      eax, 80070000h
0x1801d1cd5  mov     rcx, [rsp+4A8h+var_28]
0x1801d1cdd  xor     rcx, rsp; StackCookie
0x1801d1ce0  call    __security_check_cookie
0x1801d1ce5  add     rsp, 490h
0x1801d1cec  pop     rdi
0x1801d1ced  pop     rsi
0x1801d1cee  pop     rbx
0x1801d1cef  retn
```
