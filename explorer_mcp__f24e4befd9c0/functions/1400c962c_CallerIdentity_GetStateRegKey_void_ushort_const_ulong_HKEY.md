# CallerIdentity::GetStateRegKey(void *,ushort const *,ulong,HKEY__ * *)

- ea: `0x1400c962c`
- end: `0x1400c97f5`
- name: `?GetStateRegKey@CallerIdentity@@YAJPEAXPEBGKPEAPEAUHKEY__@@@Z`
- size: `457`
- prototype: `int(CallerIdentity *__hidden this, void *, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14010c688`

## callees

- `0x14001c330`
- `0x140065790`
- `0x1400c962c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400c977e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400c977e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400c9726`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400c9726`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400c97a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400c97c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400c97a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400c97c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c96a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c97d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c96a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400c97d5`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x1400c9663`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x1400c96e5`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x1400c9663`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x1400c96e5`

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
0x1400c962c  mov     [rsp-18h+arg_0], rsi
0x1400c9631  mov     [rsp-18h+arg_10], r8d
0x1400c9636  mov     [rsp-18h+arg_8], rdx
0x1400c963b  push    rbp
0x1400c963c  push    rdi
0x1400c963d  push    r14
0x1400c963f  mov     rbp, rsp
0x1400c9642  sub     rsp, 60h
0x1400c9646  mov     r14, r9
0x1400c9649  mov     rsi, rcx
0x1400c964c  mov     qword ptr [r9], 0
0x1400c9653  mov     [rbp+arg_10], 0
0x1400c965a  lea     r9, [rbp+arg_10]
0x1400c965e  xor     r8d, r8d
0x1400c9661  xor     edx, edx
0x1400c9663  call    cs:__imp_GetSystemAppDataKey
0x1400c966a  nop     dword ptr [rax+rax+00h]
0x1400c966f  test    eax, eax
0x1400c9671  jz      short loc_1400C967D
0x1400c9673  mov     edi, 8000FFFFh
0x1400c9678  jmp     loc_1400C97E1
0x1400c967d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1400c9682  mov     edi, eax
0x1400c9684  cmp     eax, 8007007Ah
0x1400c9689  jnz     loc_1400C97E1
0x1400c968f  cmp     [rbp+arg_10], 0
0x1400c9693  jbe     loc_1400C97E1
0x1400c9699  mov     [rbp+lpSubKey], 0
0x1400c96a1  xor     ecx, ecx; pv
0x1400c96a3  call    cs:__imp_CoTaskMemFree
0x1400c96aa  nop     dword ptr [rax+rax+00h]
0x1400c96af  mov     r9d, [rbp+arg_10]
0x1400c96b3  lea     rax, [rbp+lpSubKey]
0x1400c96b7  mov     qword ptr [rsp+60h+samDesired], rax
0x1400c96bc  xor     r8d, r8d
0x1400c96bf  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1400c96c4  mov     edi, eax
0x1400c96c6  test    eax, eax
0x1400c96c8  js      loc_1400C97D1
0x1400c96ce  mov     [rbp+hKey], 0
0x1400c96d6  lea     r9, [rbp+arg_10]
0x1400c96da  mov     r8, [rbp+lpSubKey]
0x1400c96de  lea     rdx, [rbp+hKey]
0x1400c96e2  mov     rcx, rsi
0x1400c96e5  call    cs:__imp_GetSystemAppDataKey
0x1400c96ec  nop     dword ptr [rax+rax+00h]
0x1400c96f1  test    eax, eax
0x1400c96f3  jnz     short loc_1400C9704
0x1400c96f5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1400c96fa  mov     edi, eax
0x1400c96fc  test    eax, eax
0x1400c96fe  js      loc_1400C97B3
0x1400c9704  mov     [rbp+arg_8], 0
0x1400c970c  lea     rax, [rbp+arg_8]
0x1400c9710  mov     [rsp+60h+phkResult], rax; phkResult
0x1400c9715  mov     r9d, 2001Fh; samDesired
0x1400c971b  xor     r8d, r8d; ulOptions
0x1400c971e  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1400c9722  mov     rcx, [rbp+hKey]; hKey
0x1400c9726  call    cs:__imp_RegOpenKeyExW
0x1400c972d  nop     dword ptr [rax+rax+00h]
0x1400c9732  mov     edi, eax
0x1400c9734  mov     esi, 80070000h
0x1400c9739  test    eax, eax
0x1400c973b  jle     short loc_1400C9742
0x1400c973d  movzx   edi, ax
0x1400c9740  or      edi, esi
0x1400c9742  test    edi, edi
0x1400c9744  js      short loc_1400C9795
0x1400c9746  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x1400c974f  mov     [rsp+60h+var_28], r14; phkResult
0x1400c9754  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1400c975d  mov     [rsp+60h+samDesired], 20019h; samDesired
0x1400c9765  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x1400c976d  xor     r9d, r9d; lpClass
0x1400c9770  xor     r8d, r8d; Reserved
0x1400c9773  lea     rdx, aSplashscreen; "SplashScreen"
0x1400c977a  mov     rcx, [rbp+arg_8]; hKey
0x1400c977e  call    cs:__imp_RegCreateKeyExW
0x1400c9785  nop     dword ptr [rax+rax+00h]
0x1400c978a  mov     edi, eax
0x1400c978c  test    eax, eax
0x1400c978e  jle     short loc_1400C9795
0x1400c9790  movzx   edi, ax
0x1400c9793  or      edi, esi
0x1400c9795  mov     rcx, [rbp+arg_8]; hKey
0x1400c9799  mov     [rbp+arg_8], 0
0x1400c97a1  test    rcx, rcx
0x1400c97a4  jz      short loc_1400C97B3
0x1400c97a6  call    cs:__imp_RegCloseKey
0x1400c97ad  nop     dword ptr [rax+rax+00h]
0x1400c97b2  nop
0x1400c97b3  mov     rcx, [rbp+hKey]; hKey
0x1400c97b7  mov     [rbp+hKey], 0
0x1400c97bf  test    rcx, rcx
0x1400c97c2  jz      short loc_1400C97D1
0x1400c97c4  call    cs:__imp_RegCloseKey
0x1400c97cb  nop     dword ptr [rax+rax+00h]
0x1400c97d0  nop
0x1400c97d1  mov     rcx, [rbp+lpSubKey]; pv
0x1400c97d5  call    cs:__imp_CoTaskMemFree
0x1400c97dc  nop     dword ptr [rax+rax+00h]
0x1400c97e1  mov     eax, edi
0x1400c97e3  mov     rsi, [rsp+60h+arg_0]
0x1400c97eb  add     rsp, 60h
0x1400c97ef  pop     r14
0x1400c97f1  pop     rdi
0x1400c97f2  pop     rbp
0x1400c97f3  retn
```
