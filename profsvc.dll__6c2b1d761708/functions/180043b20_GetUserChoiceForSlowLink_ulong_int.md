# GetUserChoiceForSlowLink(ulong,int)

- ea: `0x180043b20`
- end: `0x180043c03`
- name: `?GetUserChoiceForSlowLink@@YAHKH@Z`
- size: `227`
- prototype: `__int64 __fastcall(unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008fa0`

## callees

- `0x1800172e0`
- `0x18003bc70`
- `0x180043b20`
- `0x180043c0c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043b74`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043b74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043bd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043bd5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180043bad`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180043bad`

## string_xrefs

- `0x180043b5a`: `Software\Microsoft\Windows NT\CurrentVersion\ProfileDownloadOnSlowLink`

## pseudocode

```c
__int64 __fastcall GetUserChoiceForSlowLink(unsigned int a1, int a2)
{
  unsigned int v2; // ebx
  unsigned int v6; // [rsp+30h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-40h] BYREF
  WCHAR ValueName[16]; // [rsp+40h] [rbp-38h] BYREF

  v2 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileDownloadOnSlowLink",
          0,
          a2 != 0 ? 131103 : 131097,
          &hKey) )
  {
    if ( (int)StringCchPrintfW(ValueName, 0x10u, L"%u", a1) >= 0 )
    {
      if ( a2 )
      {
        RegDeleteValueW(hKey, ValueName);
      }
      else
      {
        v6 = 0;
        if ( (int)RegQueryDword(hKey, ValueName, &v6) >= 0 )
          v2 = v6;
      }
    }
    RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x180043b20  mov     r11, rsp
0x180043b23  mov     [r11+10h], rbx
0x180043b27  mov     [r11+18h], rsi
0x180043b2b  push    rdi
0x180043b2c  sub     rsp, 70h
0x180043b30  mov     rax, cs:__security_cookie
0x180043b37  xor     rax, rsp
0x180043b3a  mov     [rsp+78h+var_18], rax
0x180043b3f  mov     eax, edx
0x180043b41  xor     ebx, ebx
0x180043b43  neg     eax
0x180043b45  mov     [r11-40h], rbx
0x180043b49  mov     edi, edx
0x180043b4b  lea     rax, [r11-40h]
0x180043b4f  sbb     r9d, r9d
0x180043b52  mov     [r11-58h], rax
0x180043b56  and     r9d, 6
0x180043b5a  lea     rdx, aSoftwareMicros_35; "Software\\Microsoft\\Windows NT\\Curren"...
0x180043b61  mov     esi, ecx
0x180043b63  add     r9d, 20019h; samDesired
0x180043b6a  xor     r8d, r8d; ulOptions
0x180043b6d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180043b74  call    cs:__imp_RegOpenKeyExW
0x180043b7b  nop     dword ptr [rax+rax+00h]
0x180043b80  test    eax, eax
0x180043b82  jnz     short loc_180043BE1
0x180043b84  mov     r9d, esi
0x180043b87  lea     r8, aU; "%u"
0x180043b8e  lea     edx, [rbx+10h]; unsigned __int64
0x180043b91  lea     rcx, [rsp+78h+ValueName]; unsigned __int16 *
0x180043b96  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180043b9b  test    eax, eax
0x180043b9d  js      short loc_180043BD0
0x180043b9f  mov     rcx, [rsp+78h+hKey]; HKEY
0x180043ba4  lea     rdx, [rsp+78h+ValueName]; unsigned __int16 *
0x180043ba9  test    edi, edi
0x180043bab  jz      short loc_180043BBB
0x180043bad  call    cs:__imp_RegDeleteValueW
0x180043bb4  nop     dword ptr [rax+rax+00h]
0x180043bb9  jmp     short loc_180043BD0
0x180043bbb  lea     r8, [rsp+78h+var_48]; unsigned int *
0x180043bc0  mov     [rsp+78h+var_48], ebx
0x180043bc4  call    ?RegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; RegQueryDword(HKEY__ *,ushort const *,ulong *)
0x180043bc9  test    eax, eax
0x180043bcb  cmovns  ebx, [rsp+78h+var_48]
0x180043bd0  mov     rcx, [rsp+78h+hKey]; hKey
0x180043bd5  call    cs:__imp_RegCloseKey
0x180043bdc  nop     dword ptr [rax+rax+00h]
0x180043be1  mov     eax, ebx
0x180043be3  mov     rcx, [rsp+78h+var_18]
0x180043be8  xor     rcx, rsp; StackCookie
0x180043beb  call    __security_check_cookie
0x180043bf0  lea     r11, [rsp+78h+var_8]
0x180043bf5  mov     rbx, [r11+18h]
0x180043bf9  mov     rsi, [r11+20h]
0x180043bfd  mov     rsp, r11
0x180043c00  pop     rdi
0x180043c01  retn
```
