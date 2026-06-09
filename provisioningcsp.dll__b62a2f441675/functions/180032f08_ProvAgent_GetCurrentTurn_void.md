# ProvAgent::GetCurrentTurn(void)

- ea: `0x180032f08`
- end: `0x180033076`
- name: `?GetCurrentTurn@ProvAgent@@QEBA?AW4ProvisioningTurn@Provisioning@Management@Windows@@XZ`
- size: `366`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180023680`

## callees

- `0x18000526c`
- `0x180007834`
- `0x180032c64`
- `0x180032f08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180032f1c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180032f1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180033020`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180033020`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032f95`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032f95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003300b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003300b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032fee`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032fee`

## string_xrefs

- `0x180033064`: `onecoreuap\admin\prov\lib\provagent.cpp`
- `0x18003304f`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
  unsigned int v6; // r8d
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
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v6, v7);
  return v5;
}

```

## disassembly

```asm
0x180032f08  push    rbx
0x180032f0a  push    rdi
0x180032f0b  sub     rsp, 58h
0x180032f0f  mov     rbx, [rcx+8]
0x180032f13  xor     r8d, r8d; bAlertable
0x180032f16  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180032f19  mov     rcx, rbx; hHandle
0x180032f1c  call    cs:__imp_WaitForSingleObjectEx
0x180032f23  nop     dword ptr [rax+rax+00h]
0x180032f28  cmp     eax, 102h
0x180032f2d  jz      short loc_180032F3C
0x180032f2f  test    eax, 0FFFFFF7Fh
0x180032f34  jnz     loc_18003304A
0x180032f3a  jmp     short loc_180032F3E
0x180032f3c  xor     ebx, ebx
0x180032f3e  mov     [rsp+68h+arg_18], rbx
0x180032f46  mov     [rsp+68h+hkey], 0
0x180032f52  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x180032f5b  lea     rax, [rsp+68h+hkey]
0x180032f63  mov     [rsp+68h+phkResult], rax; phkResult
0x180032f68  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180032f71  mov     [rsp+68h+samDesired], 1; samDesired
0x180032f79  mov     [rsp+68h+dwOptions], 0; unsigned int
0x180032f81  xor     r9d, r9d; lpClass
0x180032f84  xor     r8d, r8d; Reserved
0x180032f87  mov     rdx, cs:?c_provAgentKey@@3PEBGEB; lpSubKey
0x180032f8e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180032f95  call    cs:__imp_RegCreateKeyExW
0x180032f9c  nop     dword ptr [rax+rax+00h]
0x180032fa1  mov     rcx, [rsp+68h]; this
0x180032fa6  test    eax, eax
0x180032fa8  jnz     loc_180033061
0x180032fae  mov     [rsp+68h+pvData], eax
0x180032fb2  mov     [rsp+68h+pcbData], 4
0x180032fba  lea     rax, [rsp+68h+pcbData]
0x180032fbf  mov     [rsp+68h+lpSecurityAttributes], rax; pcbData
0x180032fc4  lea     rax, [rsp+68h+pvData]
0x180032fc9  mov     qword ptr [rsp+68h+samDesired], rax; pvData
0x180032fce  mov     qword ptr [rsp+68h+dwOptions], 0; pdwType
0x180032fd7  mov     r9d, 10h; dwFlags
0x180032fdd  lea     r8, ?c_provEventValue@@3QBGB; "CurrentEvent"
0x180032fe4  xor     edx, edx; lpSubKey
0x180032fe6  mov     rcx, [rsp+68h+hkey]; hkey
0x180032fee  call    cs:__imp_RegGetValueW
0x180032ff5  nop     dword ptr [rax+rax+00h]
0x180032ffa  mov     edi, [rsp+68h+pvData]
0x180032ffe  mov     rcx, [rsp+68h+hkey]; hKey
0x180033006  test    rcx, rcx
0x180033009  jz      short loc_180033018
0x18003300b  call    cs:__imp_RegCloseKey
0x180033012  nop     dword ptr [rax+rax+00h]
0x180033017  nop
0x180033018  test    rbx, rbx
0x18003301b  jz      short loc_180033030
0x18003301d  mov     rcx, rbx; hMutex
0x180033020  call    cs:__imp_ReleaseMutex
0x180033027  nop     dword ptr [rax+rax+00h]
0x18003302c  test    eax, eax
0x18003302e  jz      short loc_18003303A
0x180033030  mov     eax, edi
0x180033032  add     rsp, 58h
0x180033036  pop     rdi
0x180033037  pop     rbx
0x180033038  retn
0x18003303a  mov     rcx, [rsp+68h]; this
0x18003303f  mov     edx, 0A15h; void *
0x180033044  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003304a  mov     rcx, [rsp+68h]; this
0x18003304f  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180033056  mov     edx, 0E01h; void *
0x18003305b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180033061  mov     r9d, eax; char *
0x180033064  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\lib\\provagent"...
0x18003306b  mov     edx, 13Fh; void *
0x180033070  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
