# RegKeyExists(ushort *,_RAREGHIVE,bool *)

- ea: `0x140035d80`
- end: `0x140035e83`
- name: `?RegKeyExists@@YAJPEAGW4_RAREGHIVE@@PEA_N@Z`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140035d04`

## callees

- `0x140002463`
- `0x140035d80`
- `0x14004ad80`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140035e51`
- `ADVAPI32!RegCloseKey` at `0x140035e51`
- `ADVAPI32!RegOpenKeyExW` at `0x140035dd5`
- `ADVAPI32!RegOpenKeyExW` at `0x140035dd5`
- `ADVAPI32!RegEnumKeyW` at `0x140035e32`
- `ADVAPI32!RegEnumKeyW` at `0x140035e32`
- `KERNEL32!lstrcmpiW` at `0x140035e0e`
- `KERNEL32!lstrcmpiW` at `0x140035e0e`

## pseudocode

```c
__int64 __fastcall RegKeyExists(const WCHAR *a1, __int64 a2, _BYTE *a3)
{
  unsigned int v5; // ebx
  DWORD v6; // edi
  DWORD i; // edx
  HKEY hKey; // [rsp+30h] [rbp-838h] BYREF
  WCHAR String1[1024]; // [rsp+40h] [rbp-828h] BYREF

  *a3 = 0;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Clients\\Mail", 0, 8u, &hKey) )
  {
    v5 = -2147467259;
  }
  else
  {
    v5 = 0;
    v6 = 0;
    memset_0(String1, 0, sizeof(String1));
    for ( i = 0; !RegEnumKeyW(hKey, i, String1, 0x400u); i = v6 )
    {
      if ( !lstrcmpiW(String1, a1) )
      {
        *a3 = 1;
        break;
      }
      ++v6;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x140035d80  mov     [rsp+arg_8], rbx
0x140035d85  push    rbp
0x140035d86  push    rsi
0x140035d87  push    rdi
0x140035d88  sub     rsp, 850h
0x140035d8f  mov     rax, cs:__security_cookie
0x140035d96  xor     rax, rsp
0x140035d99  mov     [rsp+868h+var_28], rax
0x140035da1  mov     rsi, r8
0x140035da4  mov     byte ptr [r8], 0
0x140035da8  mov     rbp, rcx
0x140035dab  mov     [rsp+868h+hKey], 0
0x140035db4  lea     rax, [rsp+868h+hKey]
0x140035db9  xor     r8d, r8d; ulOptions
0x140035dbc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140035dc3  mov     [rsp+868h+phkResult], rax; phkResult
0x140035dc8  mov     r9d, 8; samDesired
0x140035dce  lea     rdx, aSoftwareClient; "Software\\Clients\\Mail"
0x140035dd5  call    cs:__imp_RegOpenKeyExW
0x140035ddc  nop     dword ptr [rax+rax+00h]
0x140035de1  test    eax, eax
0x140035de3  jz      short loc_140035DEC
0x140035de5  mov     ebx, 80004005h
0x140035dea  jmp     short loc_140035E47
0x140035dec  xor     edx, edx; Val
0x140035dee  lea     rcx, [rsp+868h+String1]; void *
0x140035df3  mov     r8d, 800h; Size
0x140035df9  xor     ebx, ebx
0x140035dfb  xor     edi, edi
0x140035dfd  call    memset_0
0x140035e02  xor     edx, edx
0x140035e04  jmp     short loc_140035E22
0x140035e06  mov     rdx, rbp; lpString2
0x140035e09  lea     rcx, [rsp+868h+String1]; lpString1
0x140035e0e  call    cs:__imp_lstrcmpiW
0x140035e15  nop     dword ptr [rax+rax+00h]
0x140035e1a  test    eax, eax
0x140035e1c  jz      short loc_140035E44
0x140035e1e  inc     edi
0x140035e20  mov     edx, edi; dwIndex
0x140035e22  mov     rcx, [rsp+868h+hKey]; hKey
0x140035e27  lea     r8, [rsp+868h+String1]; lpName
0x140035e2c  mov     r9d, 400h; cchName
0x140035e32  call    cs:__imp_RegEnumKeyW
0x140035e39  nop     dword ptr [rax+rax+00h]
0x140035e3e  test    eax, eax
0x140035e40  jz      short loc_140035E06
0x140035e42  jmp     short loc_140035E47
0x140035e44  mov     byte ptr [rsi], 1
0x140035e47  mov     rcx, [rsp+868h+hKey]; hKey
0x140035e4c  test    rcx, rcx
0x140035e4f  jz      short loc_140035E5D
0x140035e51  call    cs:__imp_RegCloseKey
0x140035e58  nop     dword ptr [rax+rax+00h]
0x140035e5d  mov     eax, ebx
0x140035e5f  mov     rcx, [rsp+868h+var_28]
0x140035e67  xor     rcx, rsp; StackCookie
0x140035e6a  call    __security_check_cookie
0x140035e6f  mov     rbx, [rsp+868h+arg_8]
0x140035e77  add     rsp, 850h
0x140035e7e  pop     rdi
0x140035e7f  pop     rsi
0x140035e80  pop     rbp
0x140035e81  retn
```
