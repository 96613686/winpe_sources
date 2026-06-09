# SetKeyAndValue

- ea: `0x18006aa38`
- end: `0x18006ab94`
- name: `SetKeyAndValue`
- size: `348`
- prototype: `void __fastcall(HKEY__ *i_hKey, const wchar_t *i_szKey, const wchar_t *i_szVal, HKEY__ **o_phkOut, int fForceKeyCreation)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18006a28c`
- `0x18006a46c`

## callees

- `0x18006aa38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006ab52`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006ab52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ab24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ab24`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006aab3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006aab3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006aafe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006aafe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ab18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ab77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ab18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ab77`

## pseudocode

```c
void __fastcall SetKeyAndValue(
        HKEY i_hKey,
        const wchar_t *i_szKey,
        const BYTE *i_szVal,
        HKEY__ **o_phkOut,
        int fForceKeyCreation)
{
  __int64 v7; // rax
  signed int LastError; // eax
  ULONG_PTR dwDisposition; // [rsp+60h] [rbp+8h] BYREF
  HKEY__ *hKey; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  if ( o_phkOut )
    *o_phkOut = 0;
  if ( i_hKey && i_szKey && (i_szVal || fForceKeyCreation) )
  {
    LODWORD(dwDisposition) = 0;
    if ( RegCreateKeyExW(i_hKey, i_szKey, 0, (LPWSTR)&value, 0, 0xF003Fu, 0, &hKey, (LPDWORD)&dwDisposition) )
      goto LABEL_12;
    if ( i_szVal )
    {
      v7 = -1;
      do
        ++v7;
      while ( *(_WORD *)&i_szVal[2 * v7] );
      if ( RegSetValueExW(hKey, &value, 0, 1u, i_szVal, 2 * v7 + 2) )
      {
LABEL_12:
        if ( hKey )
          RegCloseKey(hKey);
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        dwDisposition = LastError;
        RaiseException(0, 1u, 1u, &dwDisposition);
      }
    }
    if ( o_phkOut )
    {
      *o_phkOut = hKey;
    }
    else if ( hKey )
    {
      RegCloseKey(hKey);
    }
  }
}

```

## disassembly

```asm
0x18006aa38  mov     [rsp+arg_8], rbx
0x18006aa3d  mov     [rsp+arg_10], rsi
0x18006aa42  push    rdi
0x18006aa43  sub     rsp, 50h
0x18006aa47  xor     esi, esi
0x18006aa49  mov     rbx, o_phkOut
0x18006aa4c  mov     [rsp+58h+hKey], rsi
0x18006aa51  mov     rdi, i_szVal
0x18006aa54  test    o_phkOut, o_phkOut
0x18006aa57  jz      short loc_18006AA5C
0x18006aa59  mov     [o_phkOut], rsi
0x18006aa5c  test    i_hKey, i_hKey
0x18006aa5f  jz      loc_18006AB83
0x18006aa65  test    i_szKey, i_szKey
0x18006aa68  jz      loc_18006AB83
0x18006aa6e  test    rdi, rdi
0x18006aa71  jnz     short loc_18006AA80
0x18006aa73  cmp     [rsp+58h+arg_20], esi
0x18006aa7a  jz      loc_18006AB83
0x18006aa80  lea     rax, [rsp+58h+dwDisposition]
0x18006aa85  mov     dword ptr [rsp+58h+dwDisposition], esi
0x18006aa89  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18006aa8e  lea     o_phkOut, value; lpClass
0x18006aa95  lea     rax, [rsp+58h+hKey]
0x18006aa9a  xor     r8d, r8d; Reserved
0x18006aa9d  mov     [rsp+58h+phkResult], rax; phkResult
0x18006aaa2  mov     [rsp+58h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18006aaa7  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18006aaaf  mov     [rsp+58h+dwOptions], esi; dwOptions
0x18006aab3  call    cs:__imp_RegCreateKeyExW
0x18006aaba  nop     dword ptr [rax+rax+00h]
0x18006aabf  test    eax, eax
0x18006aac1  jnz     short loc_18006AB0E
0x18006aac3  test    rdi, rdi
0x18006aac6  jz      loc_18006AB5E
0x18006aacc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006aad0  inc     rax
0x18006aad3  cmp     [rdi+rax*2], si
0x18006aad7  jnz     short loc_18006AAD0
0x18006aad9  mov     i_hKey, [rsp+58h+hKey]; hKey
0x18006aade  lea     eax, ds:2[rax*2]
0x18006aae5  mov     [rsp+58h+samDesired], eax; cbData
0x18006aae9  lea     i_szKey, value; lpValueName
0x18006aaf0  mov     r9d, 1; dwType
0x18006aaf6  mov     qword ptr [rsp+58h+dwOptions], rdi; lpData
0x18006aafb  xor     r8d, r8d; Reserved
0x18006aafe  call    cs:__imp_RegSetValueExW
0x18006ab05  nop     dword ptr [rax+rax+00h]
0x18006ab0a  test    eax, eax
0x18006ab0c  jz      short loc_18006AB5E
0x18006ab0e  mov     i_hKey, [rsp+58h+hKey]; hKey
0x18006ab13  test    i_hKey, i_hKey
0x18006ab16  jz      short loc_18006AB24
0x18006ab18  call    cs:__imp_RegCloseKey
0x18006ab1f  nop     dword ptr [rax+rax+00h]
0x18006ab24  call    cs:__imp_GetLastError
0x18006ab2b  nop     dword ptr [rax+rax+00h]
0x18006ab30  test    eax, eax
0x18006ab32  jle     short loc_18006AB3C
0x18006ab34  movzx   eax, ax
0x18006ab37  or      eax, 80070000h
0x18006ab3c  mov     edx, 1; dwExceptionFlags
0x18006ab41  cdqe
0x18006ab43  mov     r8d, edx; nNumberOfArguments
0x18006ab46  mov     [rsp+58h+dwDisposition], rax
0x18006ab4b  lea     o_phkOut, [rsp+58h+dwDisposition]; lpArguments
0x18006ab50  xor     ecx, ecx; dwExceptionCode
0x18006ab52  call    cs:__imp_RaiseException
0x18006ab59  nop     dword ptr [rax+rax+00h]
0x18006ab5e  test    rbx, rbx
0x18006ab61  jz      short loc_18006AB6D
0x18006ab63  mov     rax, [rsp+58h+hKey]
0x18006ab68  mov     [rbx], rax
0x18006ab6b  jmp     short loc_18006AB83
0x18006ab6d  mov     i_hKey, [rsp+58h+hKey]; hKey
0x18006ab72  test    i_hKey, i_hKey
0x18006ab75  jz      short loc_18006AB83
0x18006ab77  call    cs:__imp_RegCloseKey
0x18006ab7e  nop     dword ptr [rax+rax+00h]
0x18006ab83  mov     rbx, [rsp+58h+arg_8]
0x18006ab88  mov     rsi, [rsp+58h+arg_10]
0x18006ab8d  add     rsp, 50h
0x18006ab91  pop     rdi
0x18006ab92  retn
```
