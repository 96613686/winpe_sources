# ProvAgent::GetCurrentTurn(void)

- ea: `0x18002a488`
- end: `0x18002a5de`
- name: `?GetCurrentTurn@ProvAgent@@QEBA?AW4ProvisioningTurn@Provisioning@Management@Windows@@XZ`
- size: `342`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180010b40`

## callees

- `0x180005bb8`
- `0x18000864c`
- `0x18001b3a8`
- `0x18002a488`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002a588`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002a588`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002a49c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002a49c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002a50f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002a50f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a579`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a579`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a562`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a562`

## string_xrefs

- `0x18002a5a0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002a5b7`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18002a5cc`: `onecoreuap\admin\prov\lib\provagent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ProvAgent::GetCurrentTurn(__int64 a1)
{
  void *v1; // rbx
  DWORD v2; // eax
  const char *v3; // r9
  unsigned int v4; // eax
  unsigned int v5; // edi
  const char *v6; // r9
  unsigned int dwOptions; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  unsigned int pvData; // [rsp+70h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+80h] [rbp+18h] BYREF
  void *v13; // [rsp+88h] [rbp+20h]

  v1 = *(void **)(a1 + 8);
  v2 = WaitForSingleObjectEx(v1, 0xFFFFFFFF, 0);
  if ( v2 == 258 )
  {
    v1 = 0;
  }
  else if ( (v2 & 0xFFFFFF7F) != 0 )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xE01,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v3);
  }
  v13 = v1;
  hkey = 0;
  v4 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, c_provAgentKey, 0, 0, 0, 1u, 0, &hkey, 0);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x13F,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provagent.cpp",
      (const char *)v4,
      dwOptions);
  pvData = 0;
  pcbData = 4;
  RegGetValueW(hkey, 0, L"CurrentEvent", 0x10u, 0, &pvData, &pcbData);
  v5 = pvData;
  if ( hkey )
    RegCloseKey(hkey);
  if ( v1 && !ReleaseMutex(v1) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v6);
  return v5;
}

```

## disassembly

```asm
0x18002a488  push    rbx
0x18002a48a  push    rdi
0x18002a48b  sub     rsp, 58h
0x18002a48f  mov     rbx, [rcx+8]
0x18002a493  xor     r8d, r8d; bAlertable
0x18002a496  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002a499  mov     rcx, rbx; hHandle
0x18002a49c  call    cs:__imp_WaitForSingleObjectEx
0x18002a4a2  cmp     eax, 102h
0x18002a4a7  jz      short loc_18002A4B6
0x18002a4a9  test    eax, 0FFFFFF7Fh
0x18002a4ae  jnz     loc_18002A5B2
0x18002a4b4  jmp     short loc_18002A4B8
0x18002a4b6  xor     ebx, ebx
0x18002a4b8  mov     [rsp+68h+arg_18], rbx
0x18002a4c0  mov     [rsp+68h+hkey], 0
0x18002a4cc  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x18002a4d5  lea     rax, [rsp+68h+hkey]
0x18002a4dd  mov     [rsp+68h+phkResult], rax; phkResult
0x18002a4e2  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002a4eb  mov     [rsp+68h+samDesired], 1; samDesired
0x18002a4f3  mov     [rsp+68h+dwOptions], 0; unsigned int
0x18002a4fb  xor     r9d, r9d; lpClass
0x18002a4fe  xor     r8d, r8d; Reserved
0x18002a501  mov     rdx, cs:?c_provAgentKey@@3PEBGEB; lpSubKey
0x18002a508  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a50f  call    cs:__imp_RegCreateKeyExW
0x18002a515  mov     rcx, [rsp+68h]; this
0x18002a51a  test    eax, eax
0x18002a51c  jnz     loc_18002A5C9
0x18002a522  mov     [rsp+68h+pvData], eax
0x18002a526  mov     [rsp+68h+pcbData], 4
0x18002a52e  lea     rax, [rsp+68h+pcbData]
0x18002a533  mov     [rsp+68h+lpSecurityAttributes], rax; pcbData
0x18002a538  lea     rax, [rsp+68h+pvData]
0x18002a53d  mov     qword ptr [rsp+68h+samDesired], rax; pvData
0x18002a542  mov     qword ptr [rsp+68h+dwOptions], 0; pdwType
0x18002a54b  mov     r9d, 10h; dwFlags
0x18002a551  lea     r8, ?c_provEventValue@@3QBGB; "CurrentEvent"
0x18002a558  xor     edx, edx; lpSubKey
0x18002a55a  mov     rcx, [rsp+68h+hkey]; hkey
0x18002a562  call    cs:__imp_RegGetValueW
0x18002a568  mov     edi, [rsp+68h+pvData]
0x18002a56c  mov     rcx, [rsp+68h+hkey]; hKey
0x18002a574  test    rcx, rcx
0x18002a577  jz      short loc_18002A580
0x18002a579  call    cs:__imp_RegCloseKey
0x18002a57f  nop
0x18002a580  test    rbx, rbx
0x18002a583  jz      short loc_18002A592
0x18002a585  mov     rcx, rbx; hMutex
0x18002a588  call    cs:__imp_ReleaseMutex
0x18002a58e  test    eax, eax
0x18002a590  jz      short loc_18002A59B
0x18002a592  mov     eax, edi
0x18002a594  add     rsp, 58h
0x18002a598  pop     rdi
0x18002a599  pop     rbx
0x18002a59a  retn
0x18002a59b  mov     rcx, [rsp+68h]; this
0x18002a5a0  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002a5a7  mov     edx, 0A15h; void *
0x18002a5ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002a5b2  mov     rcx, [rsp+68h]; this
0x18002a5b7  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002a5be  mov     edx, 0E01h; void *
0x18002a5c3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002a5c9  mov     r9d, eax; char *
0x18002a5cc  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\provagent"...
0x18002a5d3  mov     edx, 13Fh; void *
0x18002a5d8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
