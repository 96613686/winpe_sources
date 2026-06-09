# DeleteSystemDataRegistryKeyForUser(void *)

- ea: `0x1800bda90`
- end: `0x1800bdb42`
- name: `?DeleteSystemDataRegistryKeyForUser@@YAJPEAX@Z`
- size: `178`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180053a64`
- `0x18005400c`

## callees

- `0x180003470`
- `0x180008b98`
- `0x18000ac48`
- `0x1800bda90`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800bdab9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800bdab9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bdb21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bdb21`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800bdb07`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800bdb07`

## string_xrefs

- `0x1800bdad3`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

## pseudocode

```c
__int64 __fastcall DeleteSystemDataRegistryKeyForUser(void *a1)
{
  signed int Error; // ebx
  LSTATUS v2; // eax
  LPWSTR StringSid; // [rsp+30h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-228h] BYREF

  StringSid = 0;
  if ( ConvertSidToStringSidW(a1, &StringSid) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    Error = StringCchPrintfW(
              SubKey,
              0x104u,
              L"%s\\%s",
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
              StringSid);
    if ( Error >= 0 )
    {
      v2 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, SubKey);
      Error = v2;
      if ( v2 > 0 )
        Error = (unsigned __int16)v2 | 0x80070000;
    }
    LocalFree(StringSid);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800bda90  push    rbx
0x1800bda92  sub     rsp, 260h
0x1800bda99  mov     rax, cs:__security_cookie
0x1800bdaa0  xor     rax, rsp
0x1800bdaa3  mov     [rsp+268h+var_18], rax
0x1800bdaab  lea     rdx, [rsp+268h+StringSid]; StringSid
0x1800bdab0  mov     [rsp+268h+StringSid], 0
0x1800bdab9  call    cs:__imp_ConvertSidToStringSidW
0x1800bdabf  test    eax, eax
0x1800bdac1  jnz     short loc_1800BDACE
0x1800bdac3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800bdac8  mov     ebx, eax
0x1800bdaca  test    eax, eax
0x1800bdacc  js      short loc_1800BDB27
0x1800bdace  mov     rax, [rsp+268h+StringSid]
0x1800bdad3  lea     r9, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800bdada  lea     r8, aSS_0; "%s\\%s"
0x1800bdae1  mov     [rsp+268h+var_248], rax
0x1800bdae6  mov     edx, 104h; unsigned __int64
0x1800bdaeb  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x1800bdaf0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800bdaf5  mov     ebx, eax
0x1800bdaf7  test    eax, eax
0x1800bdaf9  js      short loc_1800BDB1C
0x1800bdafb  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x1800bdb00  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bdb07  call    cs:__imp_RegDeleteTreeW
0x1800bdb0d  mov     ebx, eax
0x1800bdb0f  test    eax, eax
0x1800bdb11  jle     short loc_1800BDB1C
0x1800bdb13  movzx   ebx, ax
0x1800bdb16  or      ebx, 80070000h
0x1800bdb1c  mov     rcx, [rsp+268h+StringSid]; hMem
0x1800bdb21  call    cs:__imp_LocalFree
0x1800bdb27  mov     eax, ebx
0x1800bdb29  mov     rcx, [rsp+268h+var_18]
0x1800bdb31  xor     rcx, rsp; StackCookie
0x1800bdb34  call    __security_check_cookie
0x1800bdb39  add     rsp, 260h
0x1800bdb40  pop     rbx
0x1800bdb41  retn
```
