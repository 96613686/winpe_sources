# KGT_TryGetProcessPathByOpenProcess

- ea: `0x180040bb0`
- end: `0x180040cc0`
- name: `KGT_TryGetProcessPathByOpenProcess`
- size: `272`
- prototype: `WCHAR *__fastcall(DWORD dwProcessId)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c784`

## callees

- `0x18000af80`
- `0x180040bb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040bdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040c2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040c70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040bdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040c2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040c70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040ca0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040ca0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040c18`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040c18`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180040c60`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180040c60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040c8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040c8c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180040bcb`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180040bcb`

## string_xrefs

- `0x180040bf1`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\telemetry-utils.cpp`
- `0x180040c3e`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\telemetry-utils.cpp`

## pseudocode

```c
WCHAR *__fastcall KGT_TryGetProcessPathByOpenProcess(DWORD dwProcessId)
{
  WCHAR *v1; // rdi
  HANDLE v2; // rsi
  DWORD LastError; // eax
  WCHAR *v4; // rax
  WCHAR *v5; // rbx
  DWORD v6; // eax
  __int64 v7; // r9
  DWORD dwSize; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  v2 = OpenProcess(0x1000u, 0, dwProcessId);
  if ( !v2 )
  {
    LastError = GetLastError();
    DebugTraceError(
      LastError,
      "GetLastError()",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\telemetry-utils.cpp",
      88);
    return v1;
  }
  dwSize = 261;
  v4 = (WCHAR *)LocalAlloc(0, 0x20Au);
  v5 = v4;
  if ( !v4 )
  {
    v6 = GetLastError();
    v7 = 96;
LABEL_5:
    DebugTraceError(v6, "GetLastError()", "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\telemetry-utils.cpp", v7);
    goto LABEL_9;
  }
  if ( !QueryFullProcessImageNameW(v2, 0, v4, &dwSize) )
  {
    v6 = GetLastError();
    v7 = 102;
    goto LABEL_5;
  }
  v1 = v5;
  v5 = 0;
LABEL_9:
  CloseHandle(v2);
  if ( v5 )
    LocalFree(v5);
  return v1;
}

```

## disassembly

```asm
0x180040bb0  mov     [rsp+arg_0], rbx
0x180040bb5  mov     [rsp+arg_10], rsi
0x180040bba  push    rdi
0x180040bbb  sub     rsp, 20h
0x180040bbf  mov     r8d, ecx; dwProcessId
0x180040bc2  xor     edx, edx; bInheritHandle
0x180040bc4  mov     ecx, 1000h; dwDesiredAccess
0x180040bc9  xor     edi, edi
0x180040bcb  call    cs:__imp_OpenProcess
0x180040bd2  nop     dword ptr [rax+rax+00h]
0x180040bd7  mov     rsi, rax
0x180040bda  test    rax, rax
0x180040bdd  jnz     short loc_180040C09
0x180040bdf  call    cs:__imp_GetLastError
0x180040be6  nop     dword ptr [rax+rax+00h]
0x180040beb  mov     ecx, eax
0x180040bed  lea     r9d, [rdi+58h]
0x180040bf1  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180040bf8  lea     rdx, aGetlasterror; "GetLastError()"
0x180040bff  call    DebugTraceError
0x180040c04  jmp     loc_180040CAC
0x180040c09  mov     edx, 20Ah; uBytes
0x180040c0e  mov     [rsp+28h+dwSize], 105h
0x180040c16  xor     ecx, ecx; uFlags
0x180040c18  call    cs:__imp_LocalAlloc
0x180040c1f  nop     dword ptr [rax+rax+00h]
0x180040c24  mov     rbx, rax
0x180040c27  test    rax, rax
0x180040c2a  jnz     short loc_180040C53
0x180040c2c  call    cs:__imp_GetLastError
0x180040c33  nop     dword ptr [rax+rax+00h]
0x180040c38  lea     r9d, [rbx+60h]
0x180040c3c  mov     ecx, eax
0x180040c3e  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180040c45  lea     rdx, aGetlasterror; "GetLastError()"
0x180040c4c  call    DebugTraceError
0x180040c51  jmp     short loc_180040C89
0x180040c53  lea     r9, [rsp+28h+dwSize]; lpdwSize
0x180040c58  mov     r8, rbx; lpExeName
0x180040c5b  xor     edx, edx; dwFlags
0x180040c5d  mov     rcx, rsi; hProcess
0x180040c60  call    cs:__imp_QueryFullProcessImageNameW
0x180040c67  nop     dword ptr [rax+rax+00h]
0x180040c6c  test    eax, eax
0x180040c6e  jnz     short loc_180040C84
0x180040c70  call    cs:__imp_GetLastError
0x180040c77  nop     dword ptr [rax+rax+00h]
0x180040c7c  mov     r9d, 66h ; 'f'
0x180040c82  jmp     short loc_180040C3C
0x180040c84  mov     rdi, rbx
0x180040c87  xor     ebx, ebx
0x180040c89  mov     rcx, rsi; hObject
0x180040c8c  call    cs:__imp_CloseHandle
0x180040c93  nop     dword ptr [rax+rax+00h]
0x180040c98  test    rbx, rbx
0x180040c9b  jz      short loc_180040CAC
0x180040c9d  mov     rcx, rbx; hMem
0x180040ca0  call    cs:__imp_LocalFree
0x180040ca7  nop     dword ptr [rax+rax+00h]
0x180040cac  mov     rbx, [rsp+28h+arg_0]
0x180040cb1  mov     rax, rdi
0x180040cb4  mov     rsi, [rsp+28h+arg_10]
0x180040cb9  add     rsp, 20h
0x180040cbd  pop     rdi
0x180040cbe  retn
```
