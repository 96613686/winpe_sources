# ProvAgent::SetCurrentTurn(Windows::Management::Provisioning::ProvisioningTurn)

- ea: `0x18002ad64`
- end: `0x18002af73`
- name: `?SetCurrentTurn@ProvAgent@@QEAAXW4ProvisioningTurn@Provisioning@Management@Windows@@@Z`
- size: `527`
- prototype: `unsigned int __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000f8d0`
- `0x180010b40`

## callees

- `0x180005bb8`
- `0x18000864c`
- `0x18001b388`
- `0x18001b3a8`
- `0x18002ad64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002aeaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002aec5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002aeaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002aec5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002ada2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002add3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002ada2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002add3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ae43`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ae43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ae9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ae9b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ae7b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ae7b`

## string_xrefs

- `0x18002aedf`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002af61`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002aef6`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18002af0d`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18002af25`: `onecoreuap\admin\prov\lib\provagent.cpp`
- `0x18002af3a`: `onecoreuap\admin\prov\lib\provagent.cpp`
- `0x18002af4f`: `onecoreuap\admin\prov\lib\provagent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned int __fastcall ProvAgent::SetCurrentTurn(__int64 a1, int a2)
{
  HANDLE v3; // rbx
  DWORD v4; // eax
  const char *v5; // r9
  void *v6; // rdi
  DWORD v7; // eax
  const char *v8; // r9
  unsigned int v9; // eax
  unsigned int result; // eax
  const char *v11; // r9
  const char *v12; // r9
  int dwOptions; // [rsp+20h] [rbp-48h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-48h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int Data; // [rsp+78h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF
  HANDLE v19; // [rsp+88h] [rbp+20h]

  Data = a2;
  if ( a2 >= 9 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14A,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provagent.cpp",
      (const char *)0x80070057LL,
      dwOptions);
  v3 = 0;
  v19 = 0;
  if ( !*(_QWORD *)(a1 + 16) )
  {
    v3 = *(HANDLE *)a1;
    v4 = WaitForSingleObjectEx(*(HANDLE *)a1, 0xFFFFFFFF, 0);
    if ( v4 == 258 )
    {
      v3 = 0;
    }
    else if ( (v4 & 0xFFFFFF7F) != 0 )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v5);
    }
    v19 = v3;
  }
  v6 = *(void **)(a1 + 8);
  v7 = WaitForSingleObjectEx(v6, 0xFFFFFFFF, 0);
  if ( v7 == 258 )
  {
    v6 = 0;
  }
  else if ( (v7 & 0xFFFFFF7F) != 0 )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xE01,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v8);
  }
  hKey = 0;
  v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, c_provAgentKey, 0, 0, 0, 2u, 0, &hKey, 0);
  if ( v9 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x15B,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provagent.cpp",
      (const char *)v9,
      dwOptionsa);
  result = RegSetValueExW(hKey, L"CurrentEvent", 0, 4u, (const BYTE *)&Data, 4u);
  if ( result )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x15F,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provagent.cpp",
      (const char *)result,
      dwOptionsb);
  if ( hKey )
    result = RegCloseKey(hKey);
  if ( v6 )
  {
    result = ReleaseMutex(v6);
    if ( !result )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v11);
  }
  if ( v3 )
  {
    result = ReleaseMutex(v3);
    if ( !result )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v12);
  }
  return result;
}

```

## disassembly

```asm
0x18002ad64  mov     r11, rsp
0x18002ad67  mov     [r11+8], rbx
0x18002ad6b  mov     [rsp+Data], edx
0x18002ad6f  push    rdi
0x18002ad70  sub     rsp, 60h
0x18002ad74  mov     rdi, rcx
0x18002ad77  cmp     edx, 9
0x18002ad7a  setl    al
0x18002ad7d  mov     rcx, [rsp+68h]; this
0x18002ad82  test    al, al
0x18002ad84  jz      loc_18002AF1F
0x18002ad8a  xor     ebx, ebx
0x18002ad8c  mov     [r11+20h], rbx
0x18002ad90  cmp     [rdi+10h], rbx
0x18002ad94  jnz     short loc_18002ADC6
0x18002ad96  mov     rbx, [rdi]
0x18002ad99  xor     r8d, r8d; bAlertable
0x18002ad9c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002ad9f  mov     rcx, rbx; hHandle
0x18002ada2  call    cs:__imp_WaitForSingleObjectEx
0x18002ada8  cmp     eax, 102h
0x18002adad  jz      short loc_18002ADBC
0x18002adaf  test    eax, 0FFFFFF7Fh
0x18002adb4  jnz     loc_18002AEF1
0x18002adba  jmp     short loc_18002ADBE
0x18002adbc  xor     ebx, ebx
0x18002adbe  mov     [rsp+68h+arg_18], rbx
0x18002adc6  mov     rdi, [rdi+8]
0x18002adca  xor     r8d, r8d; bAlertable
0x18002adcd  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002add0  mov     rcx, rdi; hHandle
0x18002add3  call    cs:__imp_WaitForSingleObjectEx
0x18002add9  cmp     eax, 102h
0x18002adde  jz      short loc_18002ADED
0x18002ade0  test    eax, 0FFFFFF7Fh
0x18002ade5  jnz     loc_18002AF08
0x18002adeb  jmp     short loc_18002ADEF
0x18002aded  xor     edi, edi
0x18002adef  mov     [rsp+68h+var_18], rdi
0x18002adf4  mov     [rsp+68h+hKey], 0
0x18002ae00  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x18002ae09  lea     rax, [rsp+68h+hKey]
0x18002ae11  mov     [rsp+68h+phkResult], rax; phkResult
0x18002ae16  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002ae1f  mov     [rsp+68h+samDesired], 2; samDesired
0x18002ae27  mov     [rsp+68h+dwOptions], 0; unsigned int
0x18002ae2f  xor     r9d, r9d; lpClass
0x18002ae32  xor     r8d, r8d; Reserved
0x18002ae35  mov     rdx, cs:?c_provAgentKey@@3PEBGEB; lpSubKey
0x18002ae3c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ae43  call    cs:__imp_RegCreateKeyExW
0x18002ae49  mov     rcx, [rsp+68h]; this
0x18002ae4e  test    eax, eax
0x18002ae50  jnz     loc_18002AF37
0x18002ae56  lea     r9d, [rax+4]; dwType
0x18002ae5a  mov     [rsp+68h+samDesired], r9d; cbData
0x18002ae5f  lea     rax, [rsp+68h+Data]
0x18002ae64  mov     qword ptr [rsp+68h+dwOptions], rax; unsigned int
0x18002ae69  xor     r8d, r8d; Reserved
0x18002ae6c  lea     rdx, ?c_provEventValue@@3QBGB; "CurrentEvent"
0x18002ae73  mov     rcx, [rsp+68h+hKey]; hKey
0x18002ae7b  call    cs:__imp_RegSetValueExW
0x18002ae81  mov     rcx, [rsp+68h]; this
0x18002ae86  test    eax, eax
0x18002ae88  jnz     loc_18002AF4C
0x18002ae8e  mov     rcx, [rsp+68h+hKey]; hKey
0x18002ae96  test    rcx, rcx
0x18002ae99  jz      short loc_18002AEA2
0x18002ae9b  call    cs:__imp_RegCloseKey
0x18002aea1  nop
0x18002aea2  test    rdi, rdi
0x18002aea5  jz      short loc_18002AEBD
0x18002aea7  mov     rcx, rdi; hMutex
0x18002aeaa  call    cs:__imp_ReleaseMutex
0x18002aeb0  mov     rcx, [rsp+68h]; this
0x18002aeb5  test    eax, eax
0x18002aeb7  jz      loc_18002AF61
0x18002aebd  test    rbx, rbx
0x18002aec0  jz      short loc_18002AECF
0x18002aec2  mov     rcx, rbx; hMutex
0x18002aec5  call    cs:__imp_ReleaseMutex
0x18002aecb  test    eax, eax
0x18002aecd  jz      short loc_18002AEDA
0x18002aecf  mov     rbx, [rsp+68h+arg_0]
0x18002aed4  add     rsp, 60h
0x18002aed8  pop     rdi
0x18002aed9  retn
0x18002aeda  mov     rcx, [rsp+68h]; this
0x18002aedf  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002aee6  mov     edx, 0A15h; void *
0x18002aeeb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002aef1  mov     rcx, [rsp+68h]; this
0x18002aef6  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002aefd  mov     edx, 0E01h; void *
0x18002af02  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002af08  mov     rcx, [rsp+68h]; this
0x18002af0d  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002af14  mov     edx, 0E01h; void *
0x18002af19  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002af1f  mov     r9d, 80070057h; char *
0x18002af25  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\provagent"...
0x18002af2c  mov     edx, 14Ah; void *
0x18002af31  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002af37  mov     r9d, eax; char *
0x18002af3a  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\provagent"...
0x18002af41  mov     edx, 15Bh; void *
0x18002af46  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002af4c  mov     r9d, eax; char *
0x18002af4f  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\provagent"...
0x18002af56  mov     edx, 15Fh; void *
0x18002af5b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002af61  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002af68  mov     edx, 0A15h; void *
0x18002af6d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
