# CallerIdentity::GetStateRegKey(void *,ushort const *,ulong,HKEY__ * *)

- ea: `0x1400c2be0`
- end: `0x1400c2d78`
- name: `?GetStateRegKey@CallerIdentity@@YAJPEAXPEBGKPEAPEAUHKEY__@@@Z`
- size: `408`
- prototype: `int(CallerIdentity *__hidden this, void *, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14010268c`

## callees

- `0x140016b10`
- `0x140061fb0`
- `0x1400c2be0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400c2d1a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400c2d1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400c2d3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400c2d54`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400c2d3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400c2d54`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400c2cc8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400c2cc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c2c51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c2d5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c2c51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c2d5f`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x1400c2c17`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x1400c2c8d`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x1400c2c17`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x1400c2c8d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CallerIdentity::GetStateRegKey(CallerIdentity *this, HKEY a2, const unsigned __int16 *a3, HKEY *a4)
{
  int Error; // edi
  int v7; // edx
  int v8; // ecx
  LSTATUS v9; // eax
  LSTATUS Key; // eax
  HKEY v11; // rcx
  HKEY v12; // rcx
  HKEY phkResult; // [rsp+88h] [rbp+28h] BYREF
  int v15; // [rsp+90h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+38h] BYREF

  phkResult = a2;
  *a4 = 0;
  v15 = 0;
  if ( (unsigned int)GetSystemAppDataKey(this, 0, 0, &v15) )
  {
    return (unsigned int)-2147418113;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 && v15 )
    {
      CoTaskMemFree(0);
      Error = _AllocStringWorker<CTCoAllocPolicy>(v8, v7, 0, v15);
      if ( Error >= 0 )
      {
        hKey = 0;
        if ( (unsigned int)GetSystemAppDataKey(this, &hKey, 0, &v15) || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          phkResult = 0;
          v9 = RegOpenKeyExW(hKey, 0, 0, 0x2001Fu, &phkResult);
          Error = v9;
          if ( v9 > 0 )
            Error = (unsigned __int16)v9 | 0x80070000;
          if ( Error >= 0 )
          {
            Key = RegCreateKeyExW(phkResult, L"SplashScreen", 0, 0, 0, 0x20019u, 0, a4, 0);
            Error = Key;
            if ( Key > 0 )
              Error = (unsigned __int16)Key | 0x80070000;
          }
          v11 = phkResult;
          phkResult = 0;
          if ( v11 )
            RegCloseKey(v11);
        }
        v12 = hKey;
        hKey = 0;
        if ( v12 )
          RegCloseKey(v12);
      }
      CoTaskMemFree(0);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1400c2be0  mov     [rsp-18h+arg_0], rsi
0x1400c2be5  mov     [rsp-18h+arg_10], r8d
0x1400c2bea  mov     [rsp-18h+arg_8], rdx
0x1400c2bef  push    rbp
0x1400c2bf0  push    rdi
0x1400c2bf1  push    r14
0x1400c2bf3  mov     rbp, rsp
0x1400c2bf6  sub     rsp, 60h
0x1400c2bfa  mov     r14, r9
0x1400c2bfd  mov     rsi, rcx
0x1400c2c00  mov     qword ptr [r9], 0
0x1400c2c07  mov     [rbp+arg_10], 0
0x1400c2c0e  lea     r9, [rbp+arg_10]
0x1400c2c12  xor     r8d, r8d
0x1400c2c15  xor     edx, edx
0x1400c2c17  call    cs:__imp_GetSystemAppDataKey
0x1400c2c1d  test    eax, eax
0x1400c2c1f  jz      short loc_1400C2C2B
0x1400c2c21  mov     edi, 8000FFFFh
0x1400c2c26  jmp     loc_1400C2D65
0x1400c2c2b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1400c2c30  mov     edi, eax
0x1400c2c32  cmp     eax, 8007007Ah
0x1400c2c37  jnz     loc_1400C2D65
0x1400c2c3d  cmp     [rbp+arg_10], 0
0x1400c2c41  jbe     loc_1400C2D65
0x1400c2c47  mov     [rbp+lpSubKey], 0
0x1400c2c4f  xor     ecx, ecx; pv
0x1400c2c51  call    cs:__imp_CoTaskMemFree
0x1400c2c57  mov     r9d, [rbp+arg_10]
0x1400c2c5b  lea     rax, [rbp+lpSubKey]
0x1400c2c5f  mov     qword ptr [rsp+60h+samDesired], rax
0x1400c2c64  xor     r8d, r8d
0x1400c2c67  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1400c2c6c  mov     edi, eax
0x1400c2c6e  test    eax, eax
0x1400c2c70  js      loc_1400C2D5B
0x1400c2c76  mov     [rbp+hKey], 0
0x1400c2c7e  lea     r9, [rbp+arg_10]
0x1400c2c82  mov     r8, [rbp+lpSubKey]
0x1400c2c86  lea     rdx, [rbp+hKey]
0x1400c2c8a  mov     rcx, rsi
0x1400c2c8d  call    cs:__imp_GetSystemAppDataKey
0x1400c2c93  test    eax, eax
0x1400c2c95  jnz     short loc_1400C2CA6
0x1400c2c97  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1400c2c9c  mov     edi, eax
0x1400c2c9e  test    eax, eax
0x1400c2ca0  js      loc_1400C2D43
0x1400c2ca6  mov     [rbp+arg_8], 0
0x1400c2cae  lea     rax, [rbp+arg_8]
0x1400c2cb2  mov     [rsp+60h+phkResult], rax; phkResult
0x1400c2cb7  mov     r9d, 2001Fh; samDesired
0x1400c2cbd  xor     r8d, r8d; ulOptions
0x1400c2cc0  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1400c2cc4  mov     rcx, [rbp+hKey]; hKey
0x1400c2cc8  call    cs:__imp_RegOpenKeyExW
0x1400c2cce  mov     edi, eax
0x1400c2cd0  mov     esi, 80070000h
0x1400c2cd5  test    eax, eax
0x1400c2cd7  jle     short loc_1400C2CDE
0x1400c2cd9  movzx   edi, ax
0x1400c2cdc  or      edi, esi
0x1400c2cde  test    edi, edi
0x1400c2ce0  js      short loc_1400C2D2B
0x1400c2ce2  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x1400c2ceb  mov     [rsp+60h+var_28], r14; phkResult
0x1400c2cf0  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1400c2cf9  mov     [rsp+60h+samDesired], 20019h; samDesired
0x1400c2d01  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x1400c2d09  xor     r9d, r9d; lpClass
0x1400c2d0c  xor     r8d, r8d; Reserved
0x1400c2d0f  lea     rdx, aSplashscreen; "SplashScreen"
0x1400c2d16  mov     rcx, [rbp+arg_8]; hKey
0x1400c2d1a  call    cs:__imp_RegCreateKeyExW
0x1400c2d20  mov     edi, eax
0x1400c2d22  test    eax, eax
0x1400c2d24  jle     short loc_1400C2D2B
0x1400c2d26  movzx   edi, ax
0x1400c2d29  or      edi, esi
0x1400c2d2b  mov     rcx, [rbp+arg_8]; hKey
0x1400c2d2f  mov     [rbp+arg_8], 0
0x1400c2d37  test    rcx, rcx
0x1400c2d3a  jz      short loc_1400C2D43
0x1400c2d3c  call    cs:__imp_RegCloseKey
0x1400c2d42  nop
0x1400c2d43  mov     rcx, [rbp+hKey]; hKey
0x1400c2d47  mov     [rbp+hKey], 0
0x1400c2d4f  test    rcx, rcx
0x1400c2d52  jz      short loc_1400C2D5B
0x1400c2d54  call    cs:__imp_RegCloseKey
0x1400c2d5a  nop
0x1400c2d5b  mov     rcx, [rbp+lpSubKey]; pv
0x1400c2d5f  call    cs:__imp_CoTaskMemFree
0x1400c2d65  mov     eax, edi
0x1400c2d67  mov     rsi, [rsp+60h+arg_0]
0x1400c2d6f  add     rsp, 60h
0x1400c2d73  pop     r14
0x1400c2d75  pop     rdi
0x1400c2d76  pop     rbp
0x1400c2d77  retn
```
