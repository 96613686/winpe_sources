# _SetPinRulesLastError

- ea: `0x180002220`
- end: `0x180002376`
- name: `_SetPinRulesLastError`
- size: `342`
- prototype: `struct _FILETIME *__fastcall(DWORD, _WORD *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180008a10`
- `0x180008df0`

## callees

- `0x180002220`
- `0x1800033a0`
- `0x1800068b0`
- `0x1800174fc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000226d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000226d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000234e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000234e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800022cb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800022cb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002340`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002340`

## string_xrefs

- `0x180002290`: `Software\Microsoft\SystemCertificates\AuthRoot\AutoUpdate`

## pseudocode

```c
struct _FILETIME *__fastcall SetPinRulesLastError(DWORD a1, _WORD *a2, __int64 a3)
{
  const void *v3; // rsi
  unsigned int v5; // ebx
  struct _FILETIME *result; // rax
  BYTE *v7; // rdi
  __int64 v8; // rbx
  DWORD dwDisposition; // [rsp+88h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+20h] BYREF

  v3 = a2;
  if ( a2 && *a2 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    v5 = 2 * v8;
  }
  else
  {
    if ( !a3 )
    {
      v3 = 0;
      v5 = 0;
      goto LABEL_4;
    }
    v3 = *(const void **)(a3 + 8);
    v5 = *(_DWORD *)a3;
  }
  if ( v5 >= 0x800 )
    v5 = 2048;
LABEL_4:
  result = (struct _FILETIME *)PkiZeroAlloc(v5 + 16);
  v7 = (BYTE *)result;
  if ( result )
  {
    result->dwLowDateTime = a1;
    result->dwHighDateTime = v5;
    GetSystemTimeAsFileTime(result + 1);
    if ( v5 )
      memcpy_0(v7 + 16, v3, v5);
    dwDisposition = 0;
    hKey = 0;
    if ( !RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\SystemCertificates\\AuthRoot\\AutoUpdate",
            0,
            0,
            0,
            0x2011Fu,
            0,
            &hKey,
            &dwDisposition) )
    {
      RegSetValueExW(hKey, L"PinRulesLastError", 0, 3u, v7, v5 + 16);
      RegCloseKey(hKey);
    }
    return (struct _FILETIME *)PkiFree(v7);
  }
  return result;
}

```

## disassembly

```asm
0x180002220  mov     [rsp+arg_0], rbx
0x180002225  push    rbp
0x180002226  push    rsi
0x180002227  push    rdi
0x180002228  push    r14
0x18000222a  push    r15
0x18000222c  sub     rsp, 50h
0x180002230  xor     r15d, r15d
0x180002233  mov     rsi, rdx
0x180002236  mov     r14d, ecx
0x180002239  test    rdx, rdx
0x18000223c  jnz     loc_1800022F1
0x180002242  test    r8, r8
0x180002245  jnz     loc_180002359
0x18000224b  mov     rsi, r15
0x18000224e  mov     ebx, r15d
0x180002251  lea     ebp, [rbx+10h]
0x180002254  mov     ecx, ebp; uBytes
0x180002256  call    PkiZeroAlloc
0x18000225b  mov     rdi, rax
0x18000225e  test    rax, rax
0x180002261  jz      short loc_1800022DD
0x180002263  lea     rcx, [rax+8]; lpSystemTimeAsFileTime
0x180002267  mov     [rax], r14d
0x18000226a  mov     [rax+4], ebx
0x18000226d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002273  test    ebx, ebx
0x180002275  jnz     loc_180002362
0x18000227b  lea     rax, [rsp+78h+dwDisposition]
0x180002283  mov     [rsp+78h+dwDisposition], r15d
0x18000228b  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x180002290  lea     rdx, SubKey; "Software\\Microsoft\\SystemCertificates"...
0x180002297  lea     rax, [rsp+78h+hKey]
0x18000229f  mov     [rsp+78h+hKey], r15
0x1800022a7  mov     [rsp+78h+phkResult], rax; phkResult
0x1800022ac  xor     r9d, r9d; lpClass
0x1800022af  mov     [rsp+78h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800022b4  xor     r8d, r8d; Reserved
0x1800022b7  mov     [rsp+78h+samDesired], 2011Fh; samDesired
0x1800022bf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800022c6  mov     [rsp+78h+dwOptions], r15d; dwOptions
0x1800022cb  call    cs:__imp_RegCreateKeyExW
0x1800022d1  test    eax, eax
0x1800022d3  jz      short loc_18000231F
0x1800022d5  mov     rcx, rdi; hMem
0x1800022d8  call    PkiFree
0x1800022dd  mov     rbx, [rsp+78h+arg_0]
0x1800022e5  add     rsp, 50h
0x1800022e9  pop     r15
0x1800022eb  pop     r14
0x1800022ed  pop     rdi
0x1800022ee  pop     rsi
0x1800022ef  pop     rbp
0x1800022f0  retn
0x1800022f1  cmp     r15w, [rdx]
0x1800022f5  jz      loc_180002242
0x1800022fb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800022ff  inc     rbx
0x180002302  cmp     [rdx+rbx*2], r15w
0x180002307  jnz     short loc_1800022FF
0x180002309  add     ebx, ebx
0x18000230b  mov     eax, 800h
0x180002310  cmp     ebx, eax
0x180002312  jb      loc_180002251
0x180002318  mov     ebx, eax
0x18000231a  jmp     loc_180002251
0x18000231f  mov     rcx, [rsp+78h+hKey]; hKey
0x180002327  lea     rdx, aPinruleslaster; "PinRulesLastError"
0x18000232e  mov     [rsp+78h+samDesired], ebp; cbData
0x180002332  mov     r9d, 3; dwType
0x180002338  xor     r8d, r8d; Reserved
0x18000233b  mov     qword ptr [rsp+78h+dwOptions], rdi; lpData
0x180002340  call    cs:__imp_RegSetValueExW
0x180002346  mov     rcx, [rsp+78h+hKey]; hKey
0x18000234e  call    cs:__imp_RegCloseKey
0x180002354  jmp     loc_1800022D5
0x180002359  mov     rsi, [r8+8]
0x18000235d  mov     ebx, [r8]
0x180002360  jmp     short loc_18000230B
0x180002362  mov     r8d, ebx; Size
0x180002365  lea     rcx, [rdi+10h]; void *
0x180002369  mov     rdx, rsi; Src
0x18000236c  call    memcpy_0
0x180002371  jmp     loc_18000227B
```
