# ProvAgent::GetCurrentTurn(void)

- ea: `0x18003ac5c`
- end: `0x18003adab`
- name: `?GetCurrentTurn@ProvAgent@@QEBA?AW4ProvisioningTurn@Provisioning@Management@Windows@@XZ`
- size: `335`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18001eeec`

## callees

- `0x1800083c4`
- `0x18000ad18`
- `0x18002f9bc`
- `0x18003ac5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ad36`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ad36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ad4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ad4d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003ace3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003ace3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18003ad5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18003ad5c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003ac70`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003ac70`

## string_xrefs

- `0x18003ad84`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18003ad99`: `onecoreuap\admin\prov\lib\provagent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall ProvAgent::GetCurrentTurn(__int64 a1)
{
  void *v1; // rbx
  DWORD v2; // eax
  const char *v3; // r9
  unsigned int v4; // eax
  unsigned int v5; // edi
  __int64 v6; // r8
  const char *v7; // r9
  unsigned int dwOptions; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  unsigned int pvData; // [rsp+70h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+80h] [rbp+18h] BYREF
  void *v14; // [rsp+88h] [rbp+20h]

  v1 = *(void **)(a1 + 8);
  v2 = WaitForSingleObjectEx(v1, 0xFFFFFFFF, 0);
  if ( v2 == 258 )
  {
    v1 = 0;
  }
  else if ( (v2 & 0xFFFFFF7F) != 0 )
  {
    wil::details::in1diag3::FailFast_Unexpected(
      retaddr,
      (void *)0xE01,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v3);
  }
  v14 = v1;
  hkey = 0;
  v4 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, c_provAgentKey, 0, 0, 0, 1u, 0, &hkey, 0);
  if ( v4 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x13F,
      (int)"onecoreuap\\admin\\prov\\lib\\provagent.cpp",
      (const char *)v4,
      dwOptions);
  pvData = 0;
  pcbData = 4;
  RegGetValueW(hkey, 0, L"CurrentEvent", 0x10u, 0, &pvData, &pcbData);
  v5 = pvData;
  if ( hkey )
    RegCloseKey(hkey);
  if ( v1 && !ReleaseMutex(v1) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v6, v7);
  return v5;
}

```

## disassembly

```asm
0x18003ac5c  push    rbx
0x18003ac5e  push    rdi
0x18003ac5f  sub     rsp, 58h
0x18003ac63  mov     rbx, [rcx+8]
0x18003ac67  xor     r8d, r8d; bAlertable
0x18003ac6a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003ac6d  mov     rcx, rbx; hHandle
0x18003ac70  call    cs:__imp_WaitForSingleObjectEx
0x18003ac76  cmp     eax, 102h
0x18003ac7b  jz      short loc_18003AC8A
0x18003ac7d  test    eax, 0FFFFFF7Fh
0x18003ac82  jnz     loc_18003AD7F
0x18003ac88  jmp     short loc_18003AC8C
0x18003ac8a  xor     ebx, ebx
0x18003ac8c  mov     [rsp+68h+arg_18], rbx
0x18003ac94  mov     [rsp+68h+hkey], 0
0x18003aca0  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x18003aca9  lea     rax, [rsp+68h+hkey]
0x18003acb1  mov     [rsp+68h+phkResult], rax; phkResult
0x18003acb6  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003acbf  mov     [rsp+68h+samDesired], 1; samDesired
0x18003acc7  mov     [rsp+68h+dwOptions], 0; unsigned int
0x18003accf  xor     r9d, r9d; lpClass
0x18003acd2  xor     r8d, r8d; Reserved
0x18003acd5  mov     rdx, cs:?c_provAgentKey@@3PEBGEB; lpSubKey
0x18003acdc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003ace3  call    cs:__imp_RegCreateKeyExW
0x18003ace9  mov     rcx, [rsp+68h]; this
0x18003acee  test    eax, eax
0x18003acf0  jnz     loc_18003AD96
0x18003acf6  mov     [rsp+68h+pvData], eax
0x18003acfa  mov     [rsp+68h+pcbData], 4
0x18003ad02  lea     rax, [rsp+68h+pcbData]
0x18003ad07  mov     [rsp+68h+lpSecurityAttributes], rax; pcbData
0x18003ad0c  lea     rax, [rsp+68h+pvData]
0x18003ad11  mov     qword ptr [rsp+68h+samDesired], rax; pvData
0x18003ad16  mov     qword ptr [rsp+68h+dwOptions], 0; pdwType
0x18003ad1f  mov     r9d, 10h; dwFlags
0x18003ad25  lea     r8, ?c_provEventValue@@3QBGB; "CurrentEvent"
0x18003ad2c  xor     edx, edx; lpSubKey
0x18003ad2e  mov     rcx, [rsp+68h+hkey]; hkey
0x18003ad36  call    cs:__imp_RegGetValueW
0x18003ad3c  mov     edi, [rsp+68h+pvData]
0x18003ad40  mov     rcx, [rsp+68h+hkey]; hKey
0x18003ad48  test    rcx, rcx
0x18003ad4b  jz      short loc_18003AD54
0x18003ad4d  call    cs:__imp_RegCloseKey
0x18003ad53  nop
0x18003ad54  test    rbx, rbx
0x18003ad57  jz      short loc_18003AD66
0x18003ad59  mov     rcx, rbx; hMutex
0x18003ad5c  call    cs:__imp_ReleaseMutex
0x18003ad62  test    eax, eax
0x18003ad64  jz      short loc_18003AD6F
0x18003ad66  mov     eax, edi
0x18003ad68  add     rsp, 58h
0x18003ad6c  pop     rdi
0x18003ad6d  pop     rbx
0x18003ad6e  retn
0x18003ad6f  mov     rcx, [rsp+68h]; this
0x18003ad74  mov     edx, 0A15h; void *
0x18003ad79  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003ad7f  mov     rcx, [rsp+68h]; this
0x18003ad84  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003ad8b  mov     edx, 0E01h; void *
0x18003ad90  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18003ad96  mov     r9d, eax; char *
0x18003ad99  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\lib\\provagent"...
0x18003ada0  mov     edx, 13Fh; void *
0x18003ada5  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
