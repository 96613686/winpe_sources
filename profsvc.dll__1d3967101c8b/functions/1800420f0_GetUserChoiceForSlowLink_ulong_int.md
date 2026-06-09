# GetUserChoiceForSlowLink(ulong,int)

- ea: `0x1800420f0`
- end: `0x1800421c0`
- name: `?GetUserChoiceForSlowLink@@YAHKH@Z`
- size: `208`
- prototype: `__int64 __fastcall(unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b540`

## callees

- `0x180012290`
- `0x18003a730`
- `0x1800420f0`
- `0x1800421c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042144`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042144`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042199`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042199`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180042177`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180042177`

## string_xrefs

- `0x18004212a`: `Software\Microsoft\Windows NT\CurrentVersion\ProfileDownloadOnSlowLink`

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
0x1800420f0  mov     r11, rsp
0x1800420f3  mov     [r11+10h], rbx
0x1800420f7  mov     [r11+18h], rsi
0x1800420fb  push    rdi
0x1800420fc  sub     rsp, 70h
0x180042100  mov     rax, cs:__security_cookie
0x180042107  xor     rax, rsp
0x18004210a  mov     [rsp+78h+var_18], rax
0x18004210f  mov     eax, edx
0x180042111  xor     ebx, ebx
0x180042113  neg     eax
0x180042115  mov     [r11-40h], rbx
0x180042119  mov     edi, edx
0x18004211b  lea     rax, [r11-40h]
0x18004211f  sbb     r9d, r9d
0x180042122  mov     [r11-58h], rax
0x180042126  and     r9d, 6
0x18004212a  lea     rdx, aSoftwareMicros_35; "Software\\Microsoft\\Windows NT\\Curren"...
0x180042131  mov     esi, ecx
0x180042133  add     r9d, 20019h; samDesired
0x18004213a  xor     r8d, r8d; ulOptions
0x18004213d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180042144  call    cs:__imp_RegOpenKeyExW
0x18004214a  test    eax, eax
0x18004214c  jnz     short loc_18004219F
0x18004214e  mov     r9d, esi
0x180042151  lea     r8, aU; "%u"
0x180042158  lea     edx, [rbx+10h]; unsigned __int64
0x18004215b  lea     rcx, [rsp+78h+ValueName]; unsigned __int16 *
0x180042160  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180042165  test    eax, eax
0x180042167  js      short loc_180042194
0x180042169  mov     rcx, [rsp+78h+hKey]; HKEY
0x18004216e  lea     rdx, [rsp+78h+ValueName]; unsigned __int16 *
0x180042173  test    edi, edi
0x180042175  jz      short loc_18004217F
0x180042177  call    cs:__imp_RegDeleteValueW
0x18004217d  jmp     short loc_180042194
0x18004217f  lea     r8, [rsp+78h+var_48]; unsigned int *
0x180042184  mov     [rsp+78h+var_48], ebx
0x180042188  call    ?RegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; RegQueryDword(HKEY__ *,ushort const *,ulong *)
0x18004218d  test    eax, eax
0x18004218f  cmovns  ebx, [rsp+78h+var_48]
0x180042194  mov     rcx, [rsp+78h+hKey]; hKey
0x180042199  call    cs:__imp_RegCloseKey
0x18004219f  mov     eax, ebx
0x1800421a1  mov     rcx, [rsp+78h+var_18]
0x1800421a6  xor     rcx, rsp; StackCookie
0x1800421a9  call    __security_check_cookie
0x1800421ae  lea     r11, [rsp+78h+var_8]
0x1800421b3  mov     rbx, [r11+18h]
0x1800421b7  mov     rsi, [r11+20h]
0x1800421bb  mov     rsp, r11
0x1800421be  pop     rdi
0x1800421bf  retn
```
