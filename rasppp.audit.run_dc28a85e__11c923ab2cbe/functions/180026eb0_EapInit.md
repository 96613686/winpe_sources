# EapInit

- ea: `0x180026eb0`
- end: `0x180026f8f`
- name: `EapInit`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0x180026eb0`
- `0x18002dfa8`
- `0x18002e058`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026ef8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026ef8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026f3d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026f3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026f60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026f60`

## string_xrefs

- `0x180026eea`: `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Rasman\PPP\EAP`

## pseudocode

```c
__int64 __fastcall EapInit(int a1)
{
  DWORD Type; // [rsp+40h] [rbp+10h] BYREF
  int Data; // [rsp+48h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  if ( a1 )
  {
    hKey = 0;
    DebugInitEx();
    g_dwMaxRetryCount = 3;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"HKEY_LOCAL_MACHINE\\System\\CurrentControlSet\\Services\\Rasman\\PPP\\EAP",
            0,
            0x20019u,
            &hKey) )
    {
      Data = 0;
      Type = 4;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"MaxAuthRetryCount", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
        g_dwMaxRetryCount = Data;
      RegCloseKey(hKey);
    }
  }
  else if ( g_dwTraceIdEap != -1 )
  {
    DebugTermEx();
    g_dwTraceIdEap = -1;
  }
  return 0;
}

```

## disassembly

```asm
0x180026eb0  push    rbp
0x180026eb2  mov     rbp, rsp
0x180026eb5  sub     rsp, 30h
0x180026eb9  test    ecx, ecx
0x180026ebb  jz      loc_180026F6E
0x180026ec1  mov     [rbp+hKey], 0
0x180026ec9  call    DebugInitEx
0x180026ece  lea     rax, [rbp+hKey]
0x180026ed2  mov     cs:g_dwMaxRetryCount, 3
0x180026edc  mov     r9d, 20019h; samDesired
0x180026ee2  mov     [rsp+30h+phkResult], rax; phkResult
0x180026ee7  xor     r8d, r8d; ulOptions
0x180026eea  lea     rdx, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\System\\CurrentCont"...
0x180026ef1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026ef8  call    cs:__imp_RegOpenKeyExW
0x180026eff  nop     dword ptr [rax+rax+00h]
0x180026f04  test    eax, eax
0x180026f06  jnz     short loc_180026F86
0x180026f08  mov     rcx, [rbp+hKey]; hKey
0x180026f0c  lea     r9, [rbp+Type]; lpType
0x180026f10  mov     [rbp+Data], eax
0x180026f13  lea     rdx, aMaxauthretryco; "MaxAuthRetryCount"
0x180026f1a  lea     rax, [rbp+cbData]
0x180026f1e  mov     [rbp+Type], 4
0x180026f25  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180026f2a  xor     r8d, r8d; lpReserved
0x180026f2d  lea     rax, [rbp+Data]
0x180026f31  mov     [rbp+cbData], 4
0x180026f38  mov     [rsp+30h+phkResult], rax; lpData
0x180026f3d  call    cs:__imp_RegQueryValueExW
0x180026f44  nop     dword ptr [rax+rax+00h]
0x180026f49  test    eax, eax
0x180026f4b  jnz     short loc_180026F5C
0x180026f4d  cmp     [rbp+Type], 4
0x180026f51  jnz     short loc_180026F5C
0x180026f53  mov     eax, [rbp+Data]
0x180026f56  mov     cs:g_dwMaxRetryCount, eax
0x180026f5c  mov     rcx, [rbp+hKey]; hKey
0x180026f60  call    cs:__imp_RegCloseKey
0x180026f67  nop     dword ptr [rax+rax+00h]
0x180026f6c  jmp     short loc_180026F86
0x180026f6e  cmp     cs:g_dwTraceIdEap, 0FFFFFFFFh
0x180026f75  jz      short loc_180026F86
0x180026f77  call    DebugTermEx
0x180026f7c  mov     cs:g_dwTraceIdEap, 0FFFFFFFFh
0x180026f86  xor     eax, eax
0x180026f88  add     rsp, 30h
0x180026f8c  pop     rbp
0x180026f8d  retn
```
