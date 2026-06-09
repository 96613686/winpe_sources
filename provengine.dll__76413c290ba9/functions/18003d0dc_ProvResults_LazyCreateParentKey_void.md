# ProvResults::LazyCreateParentKey(void)

- ea: `0x18003d0dc`
- end: `0x18003d1b2`
- name: `?LazyCreateParentKey@ProvResults@@AEBAXXZ`
- size: `214`
- prototype: `void __fastcall(ProvResults *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003c030`
- `0x18003c438`

## callees

- `0x18002f9bc`
- `0x18003cedc`
- `0x18003d0dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d11a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d18e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d11a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d18e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003d172`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003d172`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d122`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d122`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d10f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d10f`

## pseudocode

```c
void __fastcall ProvResults::LazyCreateParentKey(ProvResults *this)
{
  HKEY *phkResult; // rdi
  HKEY v3; // rbp
  DWORD LastError; // ebx
  const WCHAR *v5; // rdx
  unsigned int Key; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  HKEY hKey; // [rsp+80h] [rbp+8h] BYREF

  phkResult = (HKEY *)((char *)this + 72);
  if ( !*((_QWORD *)this + 9) )
  {
    ProvResults::GetRootKey(&hKey, 4u);
    v3 = *phkResult;
    if ( *phkResult )
    {
      LastError = GetLastError();
      RegCloseKey(v3);
      SetLastError(LastError);
    }
    *phkResult = 0;
    v5 = (const WCHAR *)((char *)this + 40);
    if ( *((_QWORD *)this + 8) >= 8u )
      v5 = *(const WCHAR **)v5;
    Key = RegCreateKeyExW(hKey, v5, 0, 0, 0, 0x2001Fu, 0, phkResult, 0);
    if ( Key )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x291,
        (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
        (const char *)Key,
        dwOptions);
    if ( hKey )
      RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x18003d0dc  mov     rax, rsp
0x18003d0df  push    rbx
0x18003d0e0  push    rbp
0x18003d0e1  push    rsi
0x18003d0e2  push    rdi
0x18003d0e3  sub     rsp, 58h
0x18003d0e7  mov     rsi, rcx
0x18003d0ea  lea     rdi, [rcx+48h]
0x18003d0ee  cmp     qword ptr [rdi], 0
0x18003d0f2  jnz     loc_18003D194
0x18003d0f8  mov     edx, 4; samDesired
0x18003d0fd  lea     rcx, [rax+8]; phkResult
0x18003d101  call    ?GetRootKey@ProvResults@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; ProvResults::GetRootKey(ulong)
0x18003d106  nop
0x18003d107  mov     rbp, [rdi]
0x18003d10a  test    rbp, rbp
0x18003d10d  jz      short loc_18003D128
0x18003d10f  call    cs:__imp_GetLastError
0x18003d115  mov     ebx, eax
0x18003d117  mov     rcx, rbp; hKey
0x18003d11a  call    cs:__imp_RegCloseKey
0x18003d120  mov     ecx, ebx; dwErrCode
0x18003d122  call    cs:__imp_SetLastError
0x18003d128  mov     qword ptr [rdi], 0
0x18003d12f  lea     rdx, [rsi+28h]
0x18003d133  cmp     qword ptr [rdx+18h], 8
0x18003d138  jb      short loc_18003D13D
0x18003d13a  mov     rdx, [rdx]; lpSubKey
0x18003d13d  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x18003d146  mov     [rsp+78h+phkResult], rdi; phkResult
0x18003d14b  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003d154  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x18003d15c  mov     [rsp+78h+dwOptions], 0; unsigned int
0x18003d164  xor     r9d, r9d; lpClass
0x18003d167  xor     r8d, r8d; Reserved
0x18003d16a  mov     rcx, [rsp+78h+hKey]; hKey
0x18003d172  call    cs:__imp_RegCreateKeyExW
0x18003d178  mov     rcx, [rsp+78h]; this
0x18003d17d  test    eax, eax
0x18003d17f  jnz     short loc_18003D19D
0x18003d181  mov     rcx, [rsp+78h+hKey]; hKey
0x18003d189  test    rcx, rcx
0x18003d18c  jz      short loc_18003D194
0x18003d18e  call    cs:__imp_RegCloseKey
0x18003d194  add     rsp, 58h
0x18003d198  pop     rdi
0x18003d199  pop     rsi
0x18003d19a  pop     rbp
0x18003d19b  pop     rbx
0x18003d19c  retn
0x18003d19d  mov     r9d, eax; char *
0x18003d1a0  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x18003d1a7  mov     edx, 291h; void *
0x18003d1ac  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
