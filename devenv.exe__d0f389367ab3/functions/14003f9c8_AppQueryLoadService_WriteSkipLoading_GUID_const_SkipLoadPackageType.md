# AppQueryLoadService::WriteSkipLoading(_GUID const &,SkipLoadPackageType)

- ea: `0x14003f9c8`
- end: `0x14003fae6`
- name: `?WriteSkipLoading@AppQueryLoadService@@AEAAJAEBU_GUID@@W4SkipLoadPackageType@@@Z`
- size: `286`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x140004ce8`
- `0x14003f760`

## callees

- `0x140001020`
- `0x140004f28`
- `0x14003f9c8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14003fac3`
- `ADVAPI32!RegCloseKey` at `0x14003fac3`
- `ADVAPI32!RegCreateKeyExW` at `0x14003fa43`
- `ADVAPI32!RegCreateKeyExW` at `0x14003fa43`
- `ADVAPI32!RegSetValueExW` at `0x14003fa95`
- `ADVAPI32!RegSetValueExW` at `0x14003fa95`
- `OLEAUT32!__imp_SysFreeString` at `0x14003fab5`
- `OLEAUT32!__imp_SysFreeString` at `0x14003fab5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AppQueryLoadService::WriteSkipLoading(__int64 a1, const struct _GUID *a2, int a3)
{
  HKEY v4; // rbx
  LSTATUS v5; // eax
  signed int v6; // ecx
  unsigned int v7; // esi
  LSTATUS v8; // eax
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-20h] BYREF

  v4 = 0;
  hKey = 0;
  lpSubKey = 0;
  util_GetPackageRegKey(**(const unsigned __int16 ***)(a1 + 72), a2, (unsigned __int16 **)&lpSubKey);
  if ( !lpSubKey )
    goto LABEL_12;
  hKey = 0;
  v5 = RegCreateKeyExW(HKEY_CURRENT_USER, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
  if ( !v5 )
    v4 = hKey;
  v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v5 <= 0 )
    v6 = v5;
  if ( v6 >= 0 )
  {
    LODWORD(hKey) = a3;
    if ( v4 )
    {
      v8 = RegSetValueExW(v4, L"SkipLoading", 0, 4u, (const BYTE *)&hKey, 4u);
      v7 = (unsigned __int16)v8 | 0x80070000;
      if ( v8 <= 0 )
        v7 = v8;
    }
    else
    {
      v7 = -2147418113;
    }
  }
  else
  {
LABEL_12:
    v7 = -2147467259;
  }
  SysFreeString((BSTR)lpSubKey);
  if ( v4 )
    RegCloseKey(v4);
  return v7;
}

```

## disassembly

```asm
0x14003f9c8  mov     [rsp+arg_18], rbx
0x14003f9cd  push    rsi
0x14003f9ce  sub     rsp, 70h
0x14003f9d2  mov     rax, cs:__security_cookie
0x14003f9d9  xor     rax, rsp
0x14003f9dc  mov     [rsp+78h+var_18], rax
0x14003f9e1  mov     esi, r8d
0x14003f9e4  xor     ebx, ebx
0x14003f9e6  mov     [rsp+78h+hKey], rbx
0x14003f9eb  and     [rsp+78h+lpSubKey], rbx
0x14003f9f0  mov     rcx, [rcx+48h]
0x14003f9f4  lea     r8, [rsp+78h+lpSubKey]; unsigned __int16 **
0x14003f9f9  mov     rcx, [rcx]; unsigned __int16 *
0x14003f9fc  call    ?util_GetPackageRegKey@@YAJPEBGAEBU_GUID@@PEAPEAG@Z; util_GetPackageRegKey(ushort const *,_GUID const &,ushort * *)
0x14003fa01  cmp     [rsp+78h+lpSubKey], rbx
0x14003fa06  jz      loc_14003FAAB
0x14003fa0c  and     [rsp+78h+hKey], rbx
0x14003fa11  and     [rsp+78h+var_38], rbx
0x14003fa16  lea     rax, [rsp+78h+hKey]
0x14003fa1b  mov     [rsp+78h+phkResult], rax; phkResult
0x14003fa20  and     [rsp+78h+var_48], rbx
0x14003fa25  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x14003fa2d  and     dword ptr [rsp+78h+lpData], ebx
0x14003fa31  xor     r9d, r9d; lpClass
0x14003fa34  xor     r8d, r8d; Reserved
0x14003fa37  mov     rdx, [rsp+78h+lpSubKey]; lpSubKey
0x14003fa3c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14003fa43  call    cs:__imp_RegCreateKeyExW
0x14003fa49  test    eax, eax
0x14003fa4b  cmovz   rbx, [rsp+78h+hKey]
0x14003fa51  movzx   ecx, ax
0x14003fa54  or      ecx, 80070000h
0x14003fa5a  test    eax, eax
0x14003fa5c  cmovle  ecx, eax
0x14003fa5f  test    ecx, ecx
0x14003fa61  js      short loc_14003FAAB
0x14003fa63  mov     dword ptr [rsp+78h+hKey], esi
0x14003fa67  test    rbx, rbx
0x14003fa6a  jnz     short loc_14003FA73
0x14003fa6c  mov     esi, 8000FFFFh
0x14003fa71  jmp     short loc_14003FAB0
0x14003fa73  mov     r9d, 4; dwType
0x14003fa79  mov     [rsp+78h+samDesired], r9d; cbData
0x14003fa7e  lea     rax, [rsp+78h+hKey]
0x14003fa83  mov     [rsp+78h+lpData], rax; lpData
0x14003fa88  xor     r8d, r8d; Reserved
0x14003fa8b  lea     rdx, aSkiploading; "SkipLoading"
0x14003fa92  mov     rcx, rbx; hKey
0x14003fa95  call    cs:__imp_RegSetValueExW
0x14003fa9b  movzx   esi, ax
0x14003fa9e  or      esi, 80070000h
0x14003faa4  test    eax, eax
0x14003faa6  cmovle  esi, eax
0x14003faa9  jmp     short loc_14003FAB0
0x14003faab  mov     esi, 80004005h
0x14003fab0  mov     rcx, [rsp+78h+lpSubKey]; bstrString
0x14003fab5  call    cs:__imp_SysFreeString
0x14003fabb  test    rbx, rbx
0x14003fabe  jz      short loc_14003FAC9
0x14003fac0  mov     rcx, rbx; hKey
0x14003fac3  call    cs:__imp_RegCloseKey
0x14003fac9  mov     eax, esi
0x14003facb  mov     rcx, [rsp+78h+var_18]
0x14003fad0  xor     rcx, rsp; StackCookie
0x14003fad3  call    __security_check_cookie
0x14003fad8  mov     rbx, [rsp+78h+arg_18]
0x14003fae0  add     rsp, 70h
0x14003fae4  pop     rsi
0x14003fae5  retn
```
