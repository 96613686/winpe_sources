# I_SchemeGetCryptnetUrlCacheDir(void)

- ea: `0x1800063b0`
- end: `0x18000640d`
- name: `?I_SchemeGetCryptnetUrlCacheDir@@YAPEAGXZ`
- size: `93`
- prototype: `unsigned __int16 *(void)`
- caller_count: `10`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001154`
- `0x180001460`
- `0x180001808`
- `0x180002460`
- `0x180003274`
- `0x180004b40`
- `0x180005b30`
- `0x180005f10`
- `0x180019334`
- `0x18001ff84`

## callees

- `0x1800063b0`
- `0x180006640`
- `0x180006710`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800063f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800063f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800063ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800063ea`

## string_xrefs

- `0x1800063c8`: `\Microsoft\CryptnetUrlCache\`

## pseudocode

```c
unsigned __int16 *I_SchemeGetCryptnetUrlCacheDir(void)
{
  unsigned __int16 *result; // rax
  unsigned __int16 *v1; // rbx
  __int64 LowIntegrityUserPath; // rsi
  DWORD LastError; // edi

  result = (unsigned __int16 *)I_SchemeGetToken();
  v1 = result;
  if ( result )
  {
    LowIntegrityUserPath = I_CryptGetLowIntegrityUserPath(result, L"\\Microsoft\\CryptnetUrlCache\\");
    LastError = GetLastError();
    CloseHandle(v1);
    SetLastError(LastError);
    return (unsigned __int16 *)LowIntegrityUserPath;
  }
  return result;
}

```

## disassembly

```asm
0x1800063b0  push    rbx
0x1800063b2  sub     rsp, 20h
0x1800063b6  call    ?I_SchemeGetToken@@YAPEAXXZ; I_SchemeGetToken(void)
0x1800063bb  mov     rbx, rax
0x1800063be  test    rax, rax
0x1800063c1  jz      short loc_18000640B
0x1800063c3  mov     [rsp+28h+arg_0], rsi
0x1800063c8  lea     rdx, aMicrosoftCrypt_0; "\\Microsoft\\CryptnetUrlCache\\"
0x1800063cf  mov     rcx, rax
0x1800063d2  mov     [rsp+28h+arg_8], rdi
0x1800063d7  call    I_CryptGetLowIntegrityUserPath
0x1800063dc  mov     rsi, rax
0x1800063df  call    cs:__imp_GetLastError
0x1800063e5  mov     rcx, rbx; hObject
0x1800063e8  mov     edi, eax
0x1800063ea  call    cs:__imp_CloseHandle
0x1800063f0  mov     ecx, edi; dwErrCode
0x1800063f2  call    cs:__imp_SetLastError
0x1800063f8  mov     rdi, [rsp+28h+arg_8]
0x1800063fd  mov     rax, rsi
0x180006400  mov     rsi, [rsp+28h+arg_0]
0x180006405  add     rsp, 20h
0x180006409  pop     rbx
0x18000640a  retn
0x18000640b  jmp     short loc_180006405
```
