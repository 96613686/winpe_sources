# SetMediaTypeFile

- ea: `0x180059124`
- end: `0x1800592c6`
- name: `SetMediaTypeFile`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800580c0`

## callees

- `0x180026920`
- `0x1800388a0`
- `0x1800588f4`
- `0x180059020`
- `0x180059124`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x1800591f9`
- `KERNEL32!lstrlenW` at `0x18005923f`
- `KERNEL32!lstrlenW` at `0x1800591f9`
- `KERNEL32!lstrlenW` at `0x18005923f`
- `ADVAPI32!RegSetValueExW` at `0x180059228`
- `ADVAPI32!RegSetValueExW` at `0x180059273`
- `ADVAPI32!RegSetValueExW` at `0x180059228`
- `ADVAPI32!RegSetValueExW` at `0x180059273`
- `ADVAPI32!RegCreateKeyW` at `0x1800591b6`
- `ADVAPI32!RegCreateKeyW` at `0x1800591b6`
- `ADVAPI32!RegCloseKey` at `0x180059286`
- `ADVAPI32!RegCloseKey` at `0x180059286`
- `ole32!StringFromGUID2` at `0x180059192`
- `ole32!StringFromGUID2` at `0x180059192`

## pseudocode

```c
int __fastcall SetMediaTypeFile(
        const struct _GUID *a1,
        const struct _GUID *a2,
        __int64 a3,
        const WCHAR *a4,
        unsigned int a5)
{
  int result; // eax
  int v8; // eax
  LSTATUS v9; // ebx
  int v10; // eax
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR ValueName[12]; // [rsp+38h] [rbp-C8h] BYREF
  OLECHAR sz[104]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[200]; // [rsp+120h] [rbp+20h] BYREF

  phkResult = 0;
  if ( !a5 )
    DeleteMediaTypeFile();
  result = GetMediaTypePath(a1, a2, SubKey, (unsigned int)a4);
  if ( result >= 0 )
  {
    result = StringFromGUID2(&CLSID_AsyncReader, sz, 100);
    if ( result >= 0 )
    {
      result = RegCreateKeyW(HKEY_CLASSES_ROOT, SubKey, &phkResult);
      if ( result )
      {
        if ( result > 0 )
          return (unsigned __int16)result | 0x80070000;
      }
      else
      {
        StringCbPrintfW(ValueName, 0x14u, L"%d", a5);
        v8 = lstrlenW(a4);
        v9 = RegSetValueExW(phkResult, ValueName, 0, 1u, (const BYTE *)a4, 2 * v8 + 2);
        if ( !v9 )
        {
          v10 = lstrlenW(sz);
          v9 = RegSetValueExW(phkResult, L"Source Filter", 0, 1u, (const BYTE *)sz, 2 * v10 + 2);
        }
        RegCloseKey(phkResult);
        if ( v9 > 0 )
          return (unsigned __int16)v9 | 0x80070000;
        return v9;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180059124  mov     [rsp-8+arg_0], rbx
0x180059129  mov     [rsp-8+arg_10], rsi
0x18005912e  push    rbp
0x18005912f  lea     rbp, [rsp-1C0h]
0x180059137  sub     rsp, 2C0h
0x18005913e  mov     rax, cs:__security_cookie
0x180059145  xor     rax, rsp
0x180059148  mov     [rbp+1C0h+var_10], rax
0x18005914f  cmp     [rbp+1C0h+arg_20], 0
0x180059156  mov     rsi, r9
0x180059159  mov     rbx, rdx
0x18005915c  mov     [rsp+2C0h+phkResult], 0
0x180059165  jnz     short loc_18005916C
0x180059167  call    DeleteMediaTypeFile
0x18005916c  lea     r8, [rbp+1C0h+SubKey]; unsigned __int16 *
0x180059170  mov     rdx, rbx; struct _GUID *
0x180059173  call    ?GetMediaTypePath@@YAJPEBU_GUID@@0PEAGK@Z; GetMediaTypePath(_GUID const *,_GUID const *,ushort *,ulong)
0x180059178  test    eax, eax
0x18005917a  js      loc_1800592A1
0x180059180  mov     r8d, 64h ; 'd'; cchMax
0x180059186  lea     rdx, [rsp+2C0h+sz]; lpsz
0x18005918b  lea     rcx, CLSID_AsyncReader; rguid
0x180059192  call    cs:__imp_StringFromGUID2
0x180059199  nop     dword ptr [rax+rax+00h]
0x18005919e  test    eax, eax
0x1800591a0  js      loc_1800592A1
0x1800591a6  lea     r8, [rsp+2C0h+phkResult]; phkResult
0x1800591ab  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800591b2  lea     rdx, [rbp+1C0h+SubKey]; lpSubKey
0x1800591b6  call    cs:__imp_RegCreateKeyW
0x1800591bd  nop     dword ptr [rax+rax+00h]
0x1800591c2  test    eax, eax
0x1800591c4  jz      short loc_1800591D9
0x1800591c6  jle     loc_1800592A1
0x1800591cc  movzx   eax, ax
0x1800591cf  or      eax, 80070000h
0x1800591d4  jmp     loc_1800592A1
0x1800591d9  mov     r9d, [rbp+1C0h+arg_20]
0x1800591e0  lea     r8, aD; "%d"
0x1800591e7  mov     edx, 14h; unsigned __int64
0x1800591ec  lea     rcx, [rsp+2C0h+ValueName]; unsigned __int16 *
0x1800591f1  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800591f6  mov     rcx, rsi; lpString
0x1800591f9  call    cs:__imp_lstrlenW
0x180059200  nop     dword ptr [rax+rax+00h]
0x180059205  mov     rcx, [rsp+2C0h+phkResult]; hKey
0x18005920a  lea     rdx, [rsp+2C0h+ValueName]; lpValueName
0x18005920f  mov     r9d, 1; dwType
0x180059215  xor     r8d, r8d; Reserved
0x180059218  lea     eax, ds:2[rax*2]
0x18005921f  mov     [rsp+2C0h+cbData], eax; cbData
0x180059223  mov     [rsp+2C0h+lpData], rsi; lpData
0x180059228  call    cs:__imp_RegSetValueExW
0x18005922f  nop     dword ptr [rax+rax+00h]
0x180059234  mov     ebx, eax
0x180059236  test    eax, eax
0x180059238  jnz     short loc_180059281
0x18005923a  lea     rcx, [rsp+2C0h+sz]; lpString
0x18005923f  call    cs:__imp_lstrlenW
0x180059246  nop     dword ptr [rax+rax+00h]
0x18005924b  mov     rcx, [rsp+2C0h+phkResult]; hKey
0x180059250  lea     r9d, [rbx+1]; dwType
0x180059254  xor     r8d, r8d; Reserved
0x180059257  lea     rdx, aSourceFilter; "Source Filter"
0x18005925e  lea     eax, ds:2[rax*2]
0x180059265  mov     [rsp+2C0h+cbData], eax; cbData
0x180059269  lea     rax, [rsp+2C0h+sz]
0x18005926e  mov     [rsp+2C0h+lpData], rax; lpData
0x180059273  call    cs:__imp_RegSetValueExW
0x18005927a  nop     dword ptr [rax+rax+00h]
0x18005927f  mov     ebx, eax
0x180059281  mov     rcx, [rsp+2C0h+phkResult]; hKey
0x180059286  call    cs:__imp_RegCloseKey
0x18005928d  nop     dword ptr [rax+rax+00h]
0x180059292  test    ebx, ebx
0x180059294  jle     short loc_18005929F
0x180059296  movzx   ebx, bx
0x180059299  or      ebx, 80070000h
0x18005929f  mov     eax, ebx
0x1800592a1  mov     rcx, [rbp+1C0h+var_10]
0x1800592a8  xor     rcx, rsp; StackCookie
0x1800592ab  call    __security_check_cookie
0x1800592b0  lea     r11, [rsp+2C0h+var_s0]
0x1800592b8  mov     rbx, [r11+10h]
0x1800592bc  mov     rsi, [r11+20h]
0x1800592c0  mov     rsp, r11
0x1800592c3  pop     rbp
0x1800592c4  retn
```
