# GetPlatformFromEnvironmentString

- ea: `0x18001e264`
- end: `0x18001e3b8`
- name: `GetPlatformFromEnvironmentString`
- size: `340`
- prototype: `__int64 __fastcall(PCNZWCH lpString1)`
- caller_count: `5`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180011c70`
- `0x18001a5e0`
- `0x18001e3c0`
- `0x18002143c`
- `0x180027a50`

## callees

- `0x18000d57c`
- `0x18001e264`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001e2b2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001e2e1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001e313`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001e345`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001e374`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001e2b2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001e2e1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001e313`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001e345`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001e374`

## pseudocode

```c
__int64 __fastcall GetPlatformFromEnvironmentString(PCNZWCH lpString1, _DWORD *a2)
{
  unsigned int v4; // esi

  if ( lpString1 && a2 )
  {
    v4 = 0;
    if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"Windows NT x86", -1) == 2 )
    {
      *a2 = 1;
    }
    else if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"Windows IA64", -1) == 2 )
    {
      *a2 = 5;
    }
    else if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"Windows x64", -1) == 2 )
    {
      *a2 = 7;
    }
    else if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"Windows ARM", -1) == 2 )
    {
      *a2 = 8;
    }
    else if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"Windows ARM64", -1) == 2 )
    {
      *a2 = 9;
    }
    else
    {
      ClassInstallerTelemetry::WriteDbgTraceError(
        "GetPlatformFromEnvironmentString",
        L"%ws is an invalid environment.",
        lpString1);
      return (unsigned int)-2147023091;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x18001e264  push    rbx
0x18001e266  push    rbp
0x18001e267  push    rsi
0x18001e268  push    rdi
0x18001e269  push    r14
0x18001e26b  push    r15
0x18001e26d  sub     rsp, 38h
0x18001e271  mov     rbx, rdx
0x18001e274  mov     rdi, rcx
0x18001e277  test    rcx, rcx
0x18001e27a  jz      loc_18001E3A4
0x18001e280  test    rdx, rdx
0x18001e283  jz      loc_18001E3A4
0x18001e289  xor     esi, esi
0x18001e28b  lea     rax, aWindowsNtX86; "Windows NT x86"
0x18001e292  or      ebp, 0FFFFFFFFh
0x18001e295  mov     r8, rcx; lpString1
0x18001e298  mov     [rsp+68h+cchCount2], ebp; cchCount2
0x18001e29c  mov     r9d, ebp; cchCount1
0x18001e29f  mov     [rsp+68h+lpString2], rax; lpString2
0x18001e2a4  lea     r14d, [rsi+1]
0x18001e2a8  lea     r15d, [rsi+7Fh]
0x18001e2ac  mov     edx, r14d; dwCmpFlags
0x18001e2af  mov     ecx, r15d; Locale
0x18001e2b2  call    cs:__imp_CompareStringW
0x18001e2b8  cmp     eax, 2
0x18001e2bb  jnz     short loc_18001E2C5
0x18001e2bd  mov     [rbx], r14d
0x18001e2c0  jmp     loc_18001E3A9
0x18001e2c5  lea     rax, aWindowsIa64; "Windows IA64"
0x18001e2cc  mov     [rsp+68h+cchCount2], ebp; cchCount2
0x18001e2d0  mov     r9d, ebp; cchCount1
0x18001e2d3  mov     [rsp+68h+lpString2], rax; lpString2
0x18001e2d8  mov     r8, rdi; lpString1
0x18001e2db  mov     edx, r14d; dwCmpFlags
0x18001e2de  mov     ecx, r15d; Locale
0x18001e2e1  call    cs:__imp_CompareStringW
0x18001e2e7  cmp     eax, 2
0x18001e2ea  jnz     short loc_18001E2F7
0x18001e2ec  mov     dword ptr [rbx], 5
0x18001e2f2  jmp     loc_18001E3A9
0x18001e2f7  lea     rax, aWindowsX64_0; "Windows x64"
0x18001e2fe  mov     [rsp+68h+cchCount2], ebp; cchCount2
0x18001e302  mov     r9d, ebp; cchCount1
0x18001e305  mov     [rsp+68h+lpString2], rax; lpString2
0x18001e30a  mov     r8, rdi; lpString1
0x18001e30d  mov     edx, r14d; dwCmpFlags
0x18001e310  mov     ecx, r15d; Locale
0x18001e313  call    cs:__imp_CompareStringW
0x18001e319  cmp     eax, 2
0x18001e31c  jnz     short loc_18001E329
0x18001e31e  mov     dword ptr [rbx], 7
0x18001e324  jmp     loc_18001E3A9
0x18001e329  lea     rax, aWindowsArm; "Windows ARM"
0x18001e330  mov     [rsp+68h+cchCount2], ebp; cchCount2
0x18001e334  mov     r9d, ebp; cchCount1
0x18001e337  mov     [rsp+68h+lpString2], rax; lpString2
0x18001e33c  mov     r8, rdi; lpString1
0x18001e33f  mov     edx, r14d; dwCmpFlags
0x18001e342  mov     ecx, r15d; Locale
0x18001e345  call    cs:__imp_CompareStringW
0x18001e34b  cmp     eax, 2
0x18001e34e  jnz     short loc_18001E358
0x18001e350  mov     dword ptr [rbx], 8
0x18001e356  jmp     short loc_18001E3A9
0x18001e358  lea     rax, aWindowsArm64; "Windows ARM64"
0x18001e35f  mov     [rsp+68h+cchCount2], ebp; cchCount2
0x18001e363  mov     r9d, ebp; cchCount1
0x18001e366  mov     [rsp+68h+lpString2], rax; lpString2
0x18001e36b  mov     r8, rdi; lpString1
0x18001e36e  mov     edx, r14d; dwCmpFlags
0x18001e371  mov     ecx, r15d; Locale
0x18001e374  call    cs:__imp_CompareStringW
0x18001e37a  cmp     eax, 2
0x18001e37d  jnz     short loc_18001E387
0x18001e37f  mov     dword ptr [rbx], 9
0x18001e385  jmp     short loc_18001E3A9
0x18001e387  mov     r8, rdi
0x18001e38a  lea     rdx, aWsIsAnInvalidE; "%ws is an invalid environment."
0x18001e391  lea     rcx, aGetplatformfro; "GetPlatformFromEnvironmentString"
0x18001e398  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001e39d  mov     esi, 8007070Dh
0x18001e3a2  jmp     short loc_18001E3A9
0x18001e3a4  mov     esi, 80070057h
0x18001e3a9  mov     eax, esi
0x18001e3ab  add     rsp, 38h
0x18001e3af  pop     r15
0x18001e3b1  pop     r14
0x18001e3b3  pop     rdi
0x18001e3b4  pop     rsi
0x18001e3b5  pop     rbp
0x18001e3b6  pop     rbx
0x18001e3b7  retn
```
