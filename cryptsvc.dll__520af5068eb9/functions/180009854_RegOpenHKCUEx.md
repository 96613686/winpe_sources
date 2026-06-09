# RegOpenHKCUEx

- ea: `0x180009854`
- end: `0x180009969`
- name: `RegOpenHKCUEx`
- size: `277`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180009530`

## callees

- `0x180009854`
- `0x180009970`
- `0x18000d6a8`
- `0x18000e2f0`
- `0x1800173b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000989d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000989d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800098bb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800098bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009905`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000992d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009905`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000992d`

## pseudocode

```c
__int64 __fastcall RegOpenHKCUEx(PHKEY phkResult)
{
  wchar_t *v3; // rax
  wchar_t *v4; // rbx
  WCHAR *v5; // rdx
  unsigned int v6; // edi
  unsigned int v7[4]; // [rsp+30h] [rbp-228h] BYREF
  WCHAR SubKey[256]; // [rsp+40h] [rbp-218h] BYREF

  *phkResult = 0;
  v7[0] = 256;
  if ( (unsigned int)GetUserTextualSidHKCU(SubKey, v7) )
  {
    v4 = 0;
    v5 = SubKey;
  }
  else
  {
    if ( GetLastError() != 122 )
      return GetStatus();
    v3 = (wchar_t *)LocalAlloc(0, 2LL * v7[0]);
    v4 = v3;
    if ( !v3 )
      return GetStatus();
    if ( !(unsigned int)GetUserTextualSidHKCU(v3, v7) )
    {
      freeWithSavedLastError(v4);
      return GetStatus();
    }
    v5 = v4;
  }
  v6 = RegOpenKeyExW(HKEY_USERS, v5, 0, 0x2000000u, phkResult);
  if ( v6 )
    v6 = RegOpenKeyExW(HKEY_USERS, L".Default", 0, 0x2000000u, phkResult);
  if ( v4 )
    freeWithSavedLastError(v4);
  return v6;
}

```

## disassembly

```asm
0x180009854  mov     [rsp+arg_8], rbx
0x180009859  mov     [rsp+arg_10], rsi
0x18000985e  push    rdi
0x18000985f  sub     rsp, 250h
0x180009866  mov     rax, cs:__security_cookie
0x18000986d  xor     rax, rsp
0x180009870  mov     [rsp+258h+var_18], rax
0x180009878  mov     rsi, rcx
0x18000987b  mov     qword ptr [rcx], 0
0x180009882  lea     rcx, [rsp+258h+SubKey]; pszDest
0x180009887  mov     [rsp+258h+var_228], 100h
0x18000988f  lea     rdx, [rsp+258h+var_228]
0x180009894  call    GetUserTextualSidHKCU
0x180009899  test    eax, eax
0x18000989b  jnz     short loc_1800098E9
0x18000989d  call    cs:__imp_GetLastError
0x1800098a3  cmp     eax, 7Ah ; 'z'
0x1800098a6  jz      short loc_1800098B2
0x1800098a8  call    GetStatus
0x1800098ad  jmp     loc_180009944
0x1800098b2  mov     edx, [rsp+258h+var_228]
0x1800098b6  xor     ecx, ecx; uFlags
0x1800098b8  add     rdx, rdx; uBytes
0x1800098bb  call    cs:__imp_LocalAlloc
0x1800098c1  mov     rbx, rax
0x1800098c4  test    rax, rax
0x1800098c7  jz      short loc_1800098A8
0x1800098c9  lea     rdx, [rsp+258h+var_228]
0x1800098ce  mov     rcx, rax; pszDest
0x1800098d1  call    GetUserTextualSidHKCU
0x1800098d6  test    eax, eax
0x1800098d8  jnz     short loc_1800098E4
0x1800098da  mov     rcx, rbx; hMem
0x1800098dd  call    freeWithSavedLastError
0x1800098e2  jmp     short loc_1800098A8
0x1800098e4  mov     rdx, rbx
0x1800098e7  jmp     short loc_1800098F0
0x1800098e9  xor     ebx, ebx
0x1800098eb  lea     rdx, [rsp+258h+SubKey]; lpSubKey
0x1800098f0  mov     r9d, 2000000h; samDesired
0x1800098f6  mov     [rsp+258h+phkResult], rsi; phkResult
0x1800098fb  xor     r8d, r8d; ulOptions
0x1800098fe  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180009905  call    cs:__imp_RegOpenKeyExW
0x18000990b  mov     edi, eax
0x18000990d  test    eax, eax
0x18000990f  jz      short loc_180009935
0x180009911  mov     r9d, 2000000h; samDesired
0x180009917  mov     [rsp+258h+phkResult], rsi; phkResult
0x18000991c  xor     r8d, r8d; ulOptions
0x18000991f  lea     rdx, aDefault; ".Default"
0x180009926  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18000992d  call    cs:__imp_RegOpenKeyExW
0x180009933  mov     edi, eax
0x180009935  test    rbx, rbx
0x180009938  jz      short loc_180009942
0x18000993a  mov     rcx, rbx; hMem
0x18000993d  call    freeWithSavedLastError
0x180009942  mov     eax, edi
0x180009944  mov     rcx, [rsp+258h+var_18]
0x18000994c  xor     rcx, rsp; StackCookie
0x18000994f  call    __security_check_cookie
0x180009954  lea     r11, [rsp+258h+var_8]
0x18000995c  mov     rbx, [r11+18h]
0x180009960  mov     rsi, [r11+20h]
0x180009964  mov     rsp, r11
0x180009967  pop     rdi
0x180009968  retn
```
