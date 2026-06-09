# ProvResults::LazyOpenParentKey(void)

- ea: `0x18003d1b8`
- end: `0x18003d283`
- name: `?LazyOpenParentKey@ProvResults@@AEBA_NXZ`
- size: `203`
- prototype: `char __fastcall(ProvResults *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001c7fc`
- `0x18001fab8`

## callees

- `0x18002f9bc`
- `0x18003cedc`
- `0x18003d1b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d22b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d22b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d1f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d240`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d25d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d1f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d240`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d25d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d1fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d1fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d1ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d1ea`

## pseudocode

```c
char __fastcall ProvResults::LazyOpenParentKey(ProvResults *this)
{
  HKEY *v2; // rdi
  HKEY v3; // rbp
  DWORD LastError; // ebx
  const WCHAR *v5; // rdx
  unsigned int v6; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  v2 = (HKEY *)((char *)this + 72);
  if ( *((_QWORD *)this + 9) )
    return 1;
  ProvResults::GetRootKey(&hKey, 0x20019u);
  v3 = *v2;
  if ( *v2 )
  {
    LastError = GetLastError();
    RegCloseKey(v3);
    SetLastError(LastError);
  }
  *v2 = 0;
  v5 = (const WCHAR *)((char *)this + 40);
  if ( *((_QWORD *)this + 8) >= 8u )
    v5 = *(const WCHAR **)v5;
  v6 = RegOpenKeyExW(hKey, v5, 0, 0x2001Fu, v2);
  if ( v6 != 2 )
  {
    if ( v6 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x285,
        (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
        (const char *)v6,
        phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    return 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18003d1b8  push    rbx
0x18003d1ba  push    rbp
0x18003d1bb  push    rsi
0x18003d1bc  push    rdi
0x18003d1bd  sub     rsp, 38h
0x18003d1c1  mov     rsi, rcx
0x18003d1c4  lea     rdi, [rcx+48h]
0x18003d1c8  cmp     qword ptr [rdi], 0
0x18003d1cc  jnz     loc_18003D263
0x18003d1d2  mov     edx, 20019h; samDesired
0x18003d1d7  lea     rcx, [rsp+58h+hKey]; phkResult
0x18003d1dc  call    ?GetRootKey@ProvResults@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; ProvResults::GetRootKey(ulong)
0x18003d1e1  nop
0x18003d1e2  mov     rbp, [rdi]
0x18003d1e5  test    rbp, rbp
0x18003d1e8  jz      short loc_18003D203
0x18003d1ea  call    cs:__imp_GetLastError
0x18003d1f0  mov     ebx, eax
0x18003d1f2  mov     rcx, rbp; hKey
0x18003d1f5  call    cs:__imp_RegCloseKey
0x18003d1fb  mov     ecx, ebx; dwErrCode
0x18003d1fd  call    cs:__imp_SetLastError
0x18003d203  mov     qword ptr [rdi], 0
0x18003d20a  lea     rdx, [rsi+28h]
0x18003d20e  cmp     qword ptr [rdx+18h], 8
0x18003d213  jb      short loc_18003D218
0x18003d215  mov     rdx, [rdx]; lpSubKey
0x18003d218  mov     qword ptr [rsp+58h+phkResult], rdi; unsigned int
0x18003d21d  mov     r9d, 2001Fh; samDesired
0x18003d223  xor     r8d, r8d; ulOptions
0x18003d226  mov     rcx, [rsp+58h+hKey]; hKey
0x18003d22b  call    cs:__imp_RegOpenKeyExW
0x18003d231  cmp     eax, 2
0x18003d234  jnz     short loc_18003D24A
0x18003d236  mov     rcx, [rsp+58h+hKey]; hKey
0x18003d23b  test    rcx, rcx
0x18003d23e  jz      short loc_18003D246
0x18003d240  call    cs:__imp_RegCloseKey
0x18003d246  xor     al, al
0x18003d248  jmp     short loc_18003D265
0x18003d24a  mov     rcx, [rsp+58h]; this
0x18003d24f  test    eax, eax
0x18003d251  jnz     short loc_18003D26E
0x18003d253  mov     rcx, [rsp+58h+hKey]; hKey
0x18003d258  test    rcx, rcx
0x18003d25b  jz      short loc_18003D263
0x18003d25d  call    cs:__imp_RegCloseKey
0x18003d263  mov     al, 1
0x18003d265  add     rsp, 38h
0x18003d269  pop     rdi
0x18003d26a  pop     rsi
0x18003d26b  pop     rbp
0x18003d26c  pop     rbx
0x18003d26d  retn
0x18003d26e  mov     r9d, eax; char *
0x18003d271  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x18003d278  mov     edx, 285h; void *
0x18003d27d  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
