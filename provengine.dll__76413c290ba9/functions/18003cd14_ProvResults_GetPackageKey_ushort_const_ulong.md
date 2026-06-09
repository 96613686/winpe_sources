# ProvResults::GetPackageKey(ushort const *,ulong)

- ea: `0x18003cd14`
- end: `0x18003cdfa`
- name: `?GetPackageKey@ProvResults@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGK@Z`
- size: `230`
- prototype: `PHKEY __fastcall(PHKEY phkResult, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003d048`

## callees

- `0x18002f9bc`
- `0x18003cd14`
- `0x18003cedc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cd63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cdcc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cd63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cdcc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003cdb0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003cdb0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cd6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cd6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cd58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cd58`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PHKEY __fastcall ProvResults::GetPackageKey(PHKEY phkResult, LPCWSTR lpSubKey)
{
  HKEY v4; // rsi
  DWORD LastError; // ebx
  unsigned int Key; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  HKEY hKey; // [rsp+98h] [rbp+20h] BYREF

  *phkResult = 0;
  ProvResults::GetRootKey(&hKey, 4u);
  v4 = *phkResult;
  if ( *phkResult )
  {
    LastError = GetLastError();
    RegCloseKey(v4);
    SetLastError(LastError);
  }
  *phkResult = 0;
  Key = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x2001Fu, 0, phkResult, 0);
  if ( Key )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x26D,
      (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      (const char *)Key,
      dwOptions);
  if ( hKey )
    RegCloseKey(hKey);
  return phkResult;
}

```

## disassembly

```asm
0x18003cd14  mov     rax, rsp
0x18003cd17  mov     [rax+10h], rbx
0x18003cd1b  mov     [rax+8], rcx
0x18003cd1f  push    rbp
0x18003cd20  push    rsi
0x18003cd21  push    rdi
0x18003cd22  sub     rsp, 60h
0x18003cd26  mov     rbp, rdx
0x18003cd29  mov     rdi, rcx
0x18003cd2c  mov     dword ptr [rax-28h], 0
0x18003cd33  mov     qword ptr [rcx], 0
0x18003cd3a  mov     dword ptr [rax-28h], 1
0x18003cd41  mov     edx, 4; samDesired
0x18003cd46  lea     rcx, [rax+20h]; phkResult
0x18003cd4a  call    ?GetRootKey@ProvResults@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; ProvResults::GetRootKey(ulong)
0x18003cd4f  nop
0x18003cd50  mov     rsi, [rdi]
0x18003cd53  test    rsi, rsi
0x18003cd56  jz      short loc_18003CD71
0x18003cd58  call    cs:__imp_GetLastError
0x18003cd5e  mov     ebx, eax
0x18003cd60  mov     rcx, rsi; hKey
0x18003cd63  call    cs:__imp_RegCloseKey
0x18003cd69  mov     ecx, ebx; dwErrCode
0x18003cd6b  call    cs:__imp_SetLastError
0x18003cd71  mov     qword ptr [rdi], 0
0x18003cd78  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x18003cd81  mov     [rsp+78h+phkResult], rdi; phkResult
0x18003cd86  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003cd8f  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x18003cd97  mov     [rsp+78h+dwOptions], 0; unsigned int
0x18003cd9f  xor     r9d, r9d; lpClass
0x18003cda2  xor     r8d, r8d; Reserved
0x18003cda5  mov     rdx, rbp; lpSubKey
0x18003cda8  mov     rcx, [rsp+78h+hKey]; hKey
0x18003cdb0  call    cs:__imp_RegCreateKeyExW
0x18003cdb6  mov     rcx, [rsp+78h]; this
0x18003cdbb  test    eax, eax
0x18003cdbd  jnz     short loc_18003CDE5
0x18003cdbf  mov     rcx, [rsp+78h+hKey]; hKey
0x18003cdc7  test    rcx, rcx
0x18003cdca  jz      short loc_18003CDD2
0x18003cdcc  call    cs:__imp_RegCloseKey
0x18003cdd2  mov     rax, rdi
0x18003cdd5  mov     rbx, [rsp+78h+arg_8]
0x18003cddd  add     rsp, 60h
0x18003cde1  pop     rdi
0x18003cde2  pop     rsi
0x18003cde3  pop     rbp
0x18003cde4  retn
0x18003cde5  mov     r9d, eax; char *
0x18003cde8  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x18003cdef  mov     edx, 26Dh; void *
0x18003cdf4  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
