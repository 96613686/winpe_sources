# GetInstalledBrowserChannelInfo(BrowserChannels::ChannelId,BrowserChannels::InstallationLevel,BrowserChannels::Info *)

- ea: `0x1400751d8`
- end: `0x140075395`
- name: `?GetInstalledBrowserChannelInfo@@YA_NW4ChannelId@BrowserChannels@@W4InstallationLevel@2@PEAUInfo@2@@Z`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x140013150`

## callees

- `0x1400751d8`
- `0x14007b354`
- `0x1401040e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14007524e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14007524e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14007523d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14007523d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140075302`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140075302`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007531a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007531a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007528a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007528a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400752d6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400752d6`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1400752f1`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1400752f1`

## string_xrefs

- `0x14007522e`: `Software\Microsoft\EdgeUpdate\Clients\`

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
0x1400751d8  push    rbp
0x1400751da  push    rbx
0x1400751db  push    rsi
0x1400751dc  push    rdi
0x1400751dd  push    r14
0x1400751df  lea     rbp, [rsp-380h]
0x1400751e7  sub     rsp, 480h
0x1400751ee  mov     rax, cs:__security_cookie
0x1400751f5  xor     rax, rsp
0x1400751f8  mov     [rbp+3A0h+var_30], rax
0x1400751ff  xor     bl, bl
0x140075201  xor     edi, edi
0x140075203  mov     esi, edx
0x140075205  test    ecx, ecx
0x140075207  jz      loc_140075367
0x14007520d  sub     ecx, 1
0x140075210  jz      loc_14007535B
0x140075216  sub     ecx, 1
0x140075219  jz      loc_14007534F
0x14007521f  cmp     ecx, 1
0x140075222  jz      loc_140075343
0x140075228  mov     r14d, 104h
0x14007522e  lea     r8, aSoftwareMicros_143; "Software\\Microsoft\\EdgeUpdate\\Client"...
0x140075235  mov     edx, r14d
0x140075238  lea     rcx, [rsp+4A0h+SubKey]
0x14007523d  call    cs:__imp__o_wcscpy_s
0x140075243  mov     r8, rdi
0x140075246  lea     rcx, [rsp+4A0h+SubKey]
0x14007524b  mov     edx, r14d
0x14007524e  call    cs:__imp__o_wcscat_s
0x140075254  mov     edi, 1
0x140075259  test    dil, sil
0x14007525c  jz      loc_140075373
0x140075262  lea     rax, [rsp+4A0h+hkey]
0x140075267  mov     [rsp+4A0h+hkey], 0
0x140075270  mov     r9d, 20219h; samDesired
0x140075276  mov     [rsp+4A0h+phkResult], rax; phkResult
0x14007527b  xor     r8d, r8d; ulOptions
0x14007527e  lea     rdx, [rsp+4A0h+SubKey]; lpSubKey
0x140075283  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14007528a  call    cs:__imp_RegOpenKeyExW
0x140075290  test    eax, eax
0x140075292  jnz     loc_140075320
0x140075298  mov     rcx, [rsp+4A0h+hkey]; hkey
0x14007529d  lea     r9d, [rdi+1]; dwFlags
0x1400752a1  mov     [rsp+4A0h+pdwType], eax
0x1400752a5  lea     r8, aLocation; "location"
0x1400752ac  lea     rax, [rsp+4A0h+var_460]
0x1400752b1  mov     [rsp+4A0h+var_460], 208h
0x1400752b9  mov     [rsp+4A0h+pcbData], rax; pcbData
0x1400752be  xor     edx, edx; lpSubKey
0x1400752c0  lea     rax, [rbp+3A0h+pszPath]
0x1400752c7  mov     [rsp+4A0h+pvData], rax; pvData
0x1400752cc  lea     rax, [rsp+4A0h+pdwType]
0x1400752d1  mov     [rsp+4A0h+phkResult], rax; pdwType
0x1400752d6  call    cs:__imp_RegGetValueW
0x1400752dc  test    eax, eax
0x1400752de  jnz     short loc_140075315
0x1400752e0  lea     r8, pszMore; "msedge.exe"
0x1400752e7  mov     edx, r14d; cchPath
0x1400752ea  lea     rcx, [rbp+3A0h+pszPath]; pszPath
0x1400752f1  call    cs:__imp_PathCchAppend
0x1400752f7  test    eax, eax
0x1400752f9  jnz     short loc_140075315
0x1400752fb  lea     rcx, [rbp+3A0h+pszPath]; lpFileName
0x140075302  call    cs:__imp_GetFileAttributesW
0x140075308  cmp     eax, 0FFFFFFFFh
0x14007530b  jz      short loc_140075315
0x14007530d  test    al, 10h
0x14007530f  movzx   ebx, bl
0x140075312  cmovz   ebx, edi
0x140075315  mov     rcx, [rsp+4A0h+hkey]; hKey
0x14007531a  call    cs:__imp_RegCloseKey
0x140075320  test    bl, bl
0x140075322  jz      short loc_140075373
0x140075324  mov     al, bl
0x140075326  mov     rcx, [rbp+3A0h+var_30]
0x14007532d  xor     rcx, rsp; StackCookie
0x140075330  call    __security_check_cookie
0x140075335  add     rsp, 480h
0x14007533c  pop     r14
0x14007533e  pop     rdi
0x14007533f  pop     rsi
0x140075340  pop     rbx
0x140075341  pop     rbp
0x140075342  retn
0x140075343  lea     rdi, a65c35b146c1d41; "{65C35B14-6C1D-4122-AC46-7148CC9D6497}"
0x14007534a  jmp     loc_140075228
0x14007534f  lea     rdi, a0d50bfecCd6a4f; "{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}"
0x140075356  jmp     loc_140075228
0x14007535b  lea     rdi, a2cd8a007E18940; "{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}"
0x140075362  jmp     loc_140075228
0x140075367  lea     rdi, a56eb18f8B0084c; "{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}"
0x14007536e  jmp     loc_140075228
0x140075373  test    sil, 2
0x140075377  jz      short loc_140075324
0x140075379  lea     r8, [rbp+3A0h+pszPath]; unsigned __int16 *
0x140075380  mov     rcx, 0FFFFFFFF80000001h; this
0x140075387  lea     rdx, [rsp+4A0h+SubKey]; HKEY
0x14007538c  call    ?GetInstalledInfo@Private@BrowserChannels@@YA_NPEAUHKEY__@@PEAG1KPEAUInfo@2@@Z; BrowserChannels::Private::GetInstalledInfo(HKEY__ *,ushort *,ushort *,ulong,BrowserChannels::Info *)
0x140075391  mov     bl, al
0x140075393  jmp     short loc_140075324
```
