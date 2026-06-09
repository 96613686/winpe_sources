# GetInstalledBrowserChannelInfo(BrowserChannels::ChannelId,BrowserChannels::InstallationLevel,BrowserChannels::Info *)

- ea: `0x14007a684`
- end: `0x14007a86c`
- name: `?GetInstalledBrowserChannelInfo@@YA_NW4ChannelId@BrowserChannels@@W4InstallationLevel@2@PEAUInfo@2@@Z`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x14001db00`

## callees

- `0x14007a684`
- `0x140080924`
- `0x14010e160`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14007a700`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14007a700`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14007a6e9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14007a6e9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14007a7cc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14007a7cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007a742`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007a742`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007a7ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007a7ea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14007a794`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14007a794`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x14007a7b5`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x14007a7b5`

## string_xrefs

- `0x14007a6da`: `Software\Microsoft\EdgeUpdate\Clients\`

## pseudocode

```c
bool __fastcall GetInstalledBrowserChannelInfo(int a1, char a2)
{
  bool v2; // bl
  const wchar_t *v3; // rdi
  int v5; // ecx
  int v6; // ecx
  unsigned __int16 *v7; // r9
  DWORD FileAttributesW; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  struct BrowserChannels::Info *pvData; // [rsp+28h] [rbp-D8h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pdwType; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  struct HKEY__ SubKey[132]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPath[264]; // [rsp+260h] [rbp+160h] BYREF

  v2 = 0;
  v3 = 0;
  if ( a1 )
  {
    v5 = a1 - 1;
    if ( v5 )
    {
      v6 = v5 - 1;
      if ( v6 )
      {
        if ( v6 == 1 )
          v3 = L"{65C35B14-6C1D-4122-AC46-7148CC9D6497}";
      }
      else
      {
        v3 = L"{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}";
      }
    }
    else
    {
      v3 = L"{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}";
    }
  }
  else
  {
    v3 = L"{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}";
  }
  _o_wcscpy_s(SubKey, 260, L"Software\\Microsoft\\EdgeUpdate\\Clients\\");
  _o_wcscat_s(SubKey, 260, v3);
  if ( (a2 & 1) == 0 )
    goto LABEL_18;
  hkey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)SubKey, 0, 0x20219u, &hkey) )
  {
    pdwType = 0;
    pcbData = 520;
    if ( !RegGetValueW(hkey, 0, L"location", 2u, &pdwType, pszPath, &pcbData)
      && !PathCchAppend(pszPath, 0x104u, L"msedge.exe") )
    {
      FileAttributesW = GetFileAttributesW(pszPath);
      if ( FileAttributesW != -1 )
        v2 = (FileAttributesW & 0x10) == 0;
    }
    RegCloseKey(hkey);
  }
  if ( !v2 )
  {
LABEL_18:
    if ( (a2 & 2) != 0 )
      return BrowserChannels::Private::GetInstalledInfo(
               (BrowserChannels::Private *)0xFFFFFFFF80000001LL,
               SubKey,
               pszPath,
               v7,
               phkResult,
               pvData);
  }
  return v2;
}

```

## disassembly

```asm
0x14007a684  push    rbp
0x14007a686  push    rbx
0x14007a687  push    rsi
0x14007a688  push    rdi
0x14007a689  push    r14
0x14007a68b  lea     rbp, [rsp-380h]
0x14007a693  sub     rsp, 480h
0x14007a69a  mov     rax, cs:__security_cookie
0x14007a6a1  xor     rax, rsp
0x14007a6a4  mov     [rbp+3A0h+var_30], rax
0x14007a6ab  xor     bl, bl
0x14007a6ad  xor     edi, edi
0x14007a6af  mov     esi, edx
0x14007a6b1  test    ecx, ecx
0x14007a6b3  jz      loc_14007A83E
0x14007a6b9  sub     ecx, 1
0x14007a6bc  jz      loc_14007A832
0x14007a6c2  sub     ecx, 1
0x14007a6c5  jz      loc_14007A826
0x14007a6cb  cmp     ecx, 1
0x14007a6ce  jz      loc_14007A81A
0x14007a6d4  mov     r14d, 104h
0x14007a6da  lea     r8, aSoftwareMicros_144; "Software\\Microsoft\\EdgeUpdate\\Client"...
0x14007a6e1  mov     edx, r14d
0x14007a6e4  lea     rcx, [rsp+4A0h+SubKey]
0x14007a6e9  call    cs:__imp__o_wcscpy_s
0x14007a6f0  nop     dword ptr [rax+rax+00h]
0x14007a6f5  mov     r8, rdi
0x14007a6f8  lea     rcx, [rsp+4A0h+SubKey]
0x14007a6fd  mov     edx, r14d
0x14007a700  call    cs:__imp__o_wcscat_s
0x14007a707  nop     dword ptr [rax+rax+00h]
0x14007a70c  mov     edi, 1
0x14007a711  test    dil, sil
0x14007a714  jz      loc_14007A84A
0x14007a71a  lea     rax, [rsp+4A0h+hkey]
0x14007a71f  mov     [rsp+4A0h+hkey], 0
0x14007a728  mov     r9d, 20219h; samDesired
0x14007a72e  mov     [rsp+4A0h+phkResult], rax; phkResult
0x14007a733  xor     r8d, r8d; ulOptions
0x14007a736  lea     rdx, [rsp+4A0h+SubKey]; lpSubKey
0x14007a73b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14007a742  call    cs:__imp_RegOpenKeyExW
0x14007a749  nop     dword ptr [rax+rax+00h]
0x14007a74e  test    eax, eax
0x14007a750  jnz     loc_14007A7F6
0x14007a756  mov     rcx, [rsp+4A0h+hkey]; hkey
0x14007a75b  lea     r9d, [rdi+1]; dwFlags
0x14007a75f  mov     [rsp+4A0h+pdwType], eax
0x14007a763  lea     r8, aLocation; "location"
0x14007a76a  lea     rax, [rsp+4A0h+var_460]
0x14007a76f  mov     [rsp+4A0h+var_460], 208h
0x14007a777  mov     [rsp+4A0h+pcbData], rax; pcbData
0x14007a77c  xor     edx, edx; lpSubKey
0x14007a77e  lea     rax, [rbp+3A0h+pszPath]
0x14007a785  mov     [rsp+4A0h+pvData], rax; pvData
0x14007a78a  lea     rax, [rsp+4A0h+pdwType]
0x14007a78f  mov     [rsp+4A0h+phkResult], rax; pdwType
0x14007a794  call    cs:__imp_RegGetValueW
0x14007a79b  nop     dword ptr [rax+rax+00h]
0x14007a7a0  test    eax, eax
0x14007a7a2  jnz     short loc_14007A7E5
0x14007a7a4  lea     r8, pszMore; "msedge.exe"
0x14007a7ab  mov     edx, r14d; cchPath
0x14007a7ae  lea     rcx, [rbp+3A0h+pszPath]; pszPath
0x14007a7b5  call    cs:__imp_PathCchAppend
0x14007a7bc  nop     dword ptr [rax+rax+00h]
0x14007a7c1  test    eax, eax
0x14007a7c3  jnz     short loc_14007A7E5
0x14007a7c5  lea     rcx, [rbp+3A0h+pszPath]; lpFileName
0x14007a7cc  call    cs:__imp_GetFileAttributesW
0x14007a7d3  nop     dword ptr [rax+rax+00h]
0x14007a7d8  cmp     eax, 0FFFFFFFFh
0x14007a7db  jz      short loc_14007A7E5
0x14007a7dd  test    al, 10h
0x14007a7df  movzx   ebx, bl
0x14007a7e2  cmovz   ebx, edi
0x14007a7e5  mov     rcx, [rsp+4A0h+hkey]; hKey
0x14007a7ea  call    cs:__imp_RegCloseKey
0x14007a7f1  nop     dword ptr [rax+rax+00h]
0x14007a7f6  test    bl, bl
0x14007a7f8  jz      short loc_14007A84A
0x14007a7fa  mov     al, bl
0x14007a7fc  mov     rcx, [rbp+3A0h+var_30]
0x14007a803  xor     rcx, rsp; StackCookie
0x14007a806  call    __security_check_cookie
0x14007a80b  add     rsp, 480h
0x14007a812  pop     r14
0x14007a814  pop     rdi
0x14007a815  pop     rsi
0x14007a816  pop     rbx
0x14007a817  pop     rbp
0x14007a818  retn
0x14007a81a  lea     rdi, a65c35b146c1d41; "{65C35B14-6C1D-4122-AC46-7148CC9D6497}"
0x14007a821  jmp     loc_14007A6D4
0x14007a826  lea     rdi, a0d50bfecCd6a4f; "{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}"
0x14007a82d  jmp     loc_14007A6D4
0x14007a832  lea     rdi, a2cd8a007E18940; "{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}"
0x14007a839  jmp     loc_14007A6D4
0x14007a83e  lea     rdi, a56eb18f8B0084c; "{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}"
0x14007a845  jmp     loc_14007A6D4
0x14007a84a  test    sil, 2
0x14007a84e  jz      short loc_14007A7FA
0x14007a850  lea     r8, [rbp+3A0h+pszPath]; unsigned __int16 *
0x14007a857  mov     rcx, 0FFFFFFFF80000001h; this
0x14007a85e  lea     rdx, [rsp+4A0h+SubKey]; HKEY
0x14007a863  call    ?GetInstalledInfo@Private@BrowserChannels@@YA_NPEAUHKEY__@@PEAG1KPEAUInfo@2@@Z; BrowserChannels::Private::GetInstalledInfo(HKEY__ *,ushort *,ushort *,ulong,BrowserChannels::Info *)
0x14007a868  mov     bl, al
0x14007a86a  jmp     short loc_14007A7FA
```
