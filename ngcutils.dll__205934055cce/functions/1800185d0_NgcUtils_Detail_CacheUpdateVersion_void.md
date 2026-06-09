# NgcUtils::Detail::CacheUpdateVersion(void)

- ea: `0x1800185d0`
- end: `0x18001879d`
- name: `?CacheUpdateVersion@Detail@NgcUtils@@YAJXZ`
- size: `461`
- prototype: `__int64 __fastcall(NgcUtils::Detail *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180019374`
- `0x18001a1fc`

## callees

- `0x18000a5b4`
- `0x180013dc8`
- `0x180015ca4`
- `0x180016be4`
- `0x180017718`
- `0x1800185d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018625`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018696`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001878d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018625`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018696`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001878d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001865a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001865a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018761`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018761`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800186df`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800186df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018687`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001877e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018687`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001877e`

## string_xrefs

- `0x18001860a`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18001866c`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x1800186fe`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x1800186d2`: `CacheVersion`
- `0x180018756`: `CacheVersion`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NgcUtils::Detail::CacheUpdateVersion(NgcUtils::Detail *this)
{
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v2; // ebx
  HLOCAL v4; // rbx
  unsigned int v5; // eax
  __int64 v6; // rdx
  int v7; // edi
  LSTATUS ValueW; // eax
  NgcUtils::Detail *v9; // rcx
  __int64 v10; // rdx
  NgcUtils::Detail *v11; // rcx
  unsigned __int16 **phkResult; // [rsp+20h] [rbp-20h]
  int phkResulta; // [rsp+20h] [rbp-20h]
  unsigned int phkResultb; // [rsp+20h] [rbp-20h]
  int phkResultc; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  unsigned int pvData; // [rsp+60h] [rbp+20h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+30h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+38h] BYREF

  hMem = 0;
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        (NgcUtils *)L"NgcCredprov",
                                        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Provide"
                                         "rs\\{D6886603-9D2F-4EB2-B667-1971041FA96B}",
                                        0,
                                        (const unsigned __int16 *)&hMem,
                                        phkResult);
  v2 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x685,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
      (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
      phkResulta);
    if ( hMem )
      LocalFree(hMem);
    return v2;
  }
  hKey = 0;
  v4 = hMem;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)hMem, 0, 0x2001Fu, &hKey);
  if ( v5 )
  {
    v6 = 1678;
LABEL_7:
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v6,
           (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
           (const char *)v5,
           phkResultb);
LABEL_8:
    if ( hKey )
      RegCloseKey(hKey);
    if ( v4 )
      LocalFree(v4);
    return (unsigned int)v7;
  }
  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(hKey, 0, L"CacheVersion", 0x10u, 0, &pvData, &pcbData);
  v7 = ValueW;
  if ( (ValueW & 0xFFFFFFFD) != 0 )
  {
    if ( ValueW >= 0 )
      goto LABEL_8;
    v10 = 1694;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
      (const char *)(unsigned int)v7,
      phkResultc);
    goto LABEL_8;
  }
  if ( pvData < 2 )
  {
    v7 = NgcUtils::Detail::CacheCleanupMultipleSidsForUser(v9);
    if ( v7 < 0 )
    {
      v10 = 1703;
      goto LABEL_16;
    }
    v7 = NgcUtils::Detail::CacheCleanupMultipleUsersForSid(v11);
    if ( v7 < 0 )
    {
      v10 = 1706;
      goto LABEL_16;
    }
    v5 = RegSetValueExW(hKey, L"CacheVersion", 0, 4u, &Data, 4u);
    if ( v5 )
    {
      v6 = 1716;
      goto LABEL_7;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 )
    LocalFree(v4);
  return 0;
}

```

## disassembly

```asm
0x1800185d0  push    rbp
0x1800185d2  push    rbx
0x1800185d3  push    rdi
0x1800185d4  mov     rbp, rsp
0x1800185d7  sub     rsp, 40h
0x1800185db  mov     [rbp+hMem], 0
0x1800185e3  lea     r9, [rbp+hMem]; unsigned __int16 *
0x1800185e7  xor     r8d, r8d; unsigned __int16 *
0x1800185ea  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800185f1  lea     rcx, aNgccredprov; "NgcCredprov"
0x1800185f8  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x1800185fd  mov     ebx, eax
0x1800185ff  test    eax, eax
0x180018601  jns     short loc_180018632
0x180018603  mov     rcx, [rbp+18h]; this
0x180018607  mov     r9d, eax; char *
0x18001860a  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180018611  mov     edx, 685h; void *
0x180018616  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001861b  nop
0x18001861c  mov     rcx, [rbp+hMem]; hMem
0x180018620  test    rcx, rcx
0x180018623  jz      short loc_18001862B
0x180018625  call    cs:__imp_LocalFree
0x18001862b  mov     eax, ebx
0x18001862d  jmp     loc_180018795
0x180018632  mov     [rbp+hKey], 0
0x18001863a  lea     rax, [rbp+hKey]
0x18001863e  mov     [rsp+40h+phkResult], rax; unsigned int
0x180018643  mov     r9d, 2001Fh; samDesired
0x180018649  xor     r8d, r8d; ulOptions
0x18001864c  mov     rbx, [rbp+hMem]
0x180018650  mov     rdx, rbx; lpSubKey
0x180018653  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001865a  call    cs:__imp_RegOpenKeyExW
0x180018660  test    eax, eax
0x180018662  jz      short loc_1800186A3
0x180018664  mov     edx, 68Eh; void *
0x180018669  mov     r9d, eax; char *
0x18001866c  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180018673  mov     rcx, [rbp+18h]; this
0x180018677  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001867c  mov     edi, eax
0x18001867e  mov     rcx, [rbp+hKey]; hKey
0x180018682  test    rcx, rcx
0x180018685  jz      short loc_18001868E
0x180018687  call    cs:__imp_RegCloseKey
0x18001868d  nop
0x18001868e  test    rbx, rbx
0x180018691  jz      short loc_18001869C
0x180018693  mov     rcx, rbx; hMem
0x180018696  call    cs:__imp_LocalFree
0x18001869c  mov     eax, edi
0x18001869e  jmp     loc_180018795
0x1800186a3  mov     [rbp+arg_0], 0
0x1800186aa  mov     [rbp+arg_8], 4
0x1800186b1  lea     rax, [rbp+arg_8]
0x1800186b5  mov     [rsp+40h+pcbData], rax; pcbData
0x1800186ba  lea     rax, [rbp+arg_0]
0x1800186be  mov     [rsp+40h+pvData], rax; pvData
0x1800186c3  mov     [rsp+40h+phkResult], 0; int
0x1800186cc  mov     r9d, 10h; dwFlags
0x1800186d2  lea     r8, ValueName; "CacheVersion"
0x1800186d9  xor     edx, edx; lpSubKey
0x1800186db  mov     rcx, [rbp+hKey]; hkey
0x1800186df  call    cs:__imp_RegGetValueW
0x1800186e5  mov     edi, eax
0x1800186e7  test    eax, 0FFFFFFFDh
0x1800186ec  jz      short loc_18001870F
0x1800186ee  test    eax, eax
0x1800186f0  jns     short loc_18001867E
0x1800186f2  mov     edx, 69Eh; void *
0x1800186f7  mov     rcx, [rbp+18h]; this
0x1800186fb  mov     r9d, edi; char *
0x1800186fe  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180018705  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001870a  jmp     loc_18001867E
0x18001870f  cmp     [rbp+arg_0], 2
0x180018713  jnb     short loc_180018775
0x180018715  call    ?CacheCleanupMultipleSidsForUser@Detail@NgcUtils@@YAJXZ; NgcUtils::Detail::CacheCleanupMultipleSidsForUser(void)
0x18001871a  mov     edi, eax
0x18001871c  test    eax, eax
0x18001871e  jns     short loc_180018727
0x180018720  mov     edx, 6A7h
0x180018725  jmp     short loc_1800186F7
0x180018727  call    ?CacheCleanupMultipleUsersForSid@Detail@NgcUtils@@YAJXZ; NgcUtils::Detail::CacheCleanupMultipleUsersForSid(void)
0x18001872c  mov     edi, eax
0x18001872e  test    eax, eax
0x180018730  jns     short loc_180018739
0x180018732  mov     edx, 6AAh
0x180018737  jmp     short loc_1800186F7
0x180018739  mov     dword ptr [rsp+40h+pvData], 4; cbData
0x180018741  lea     rax, Data
0x180018748  mov     [rsp+40h+phkResult], rax; lpData
0x18001874d  mov     r9d, 4; dwType
0x180018753  xor     r8d, r8d; Reserved
0x180018756  lea     rdx, ValueName; "CacheVersion"
0x18001875d  mov     rcx, [rbp+hKey]; hKey
0x180018761  call    cs:__imp_RegSetValueExW
0x180018767  test    eax, eax
0x180018769  jz      short loc_180018775
0x18001876b  mov     edx, 6B4h
0x180018770  jmp     loc_180018669
0x180018775  mov     rcx, [rbp+hKey]; hKey
0x180018779  test    rcx, rcx
0x18001877c  jz      short loc_180018785
0x18001877e  call    cs:__imp_RegCloseKey
0x180018784  nop
0x180018785  test    rbx, rbx
0x180018788  jz      short loc_180018793
0x18001878a  mov     rcx, rbx; hMem
0x18001878d  call    cs:__imp_LocalFree
0x180018793  xor     eax, eax
0x180018795  add     rsp, 40h
0x180018799  pop     rdi
0x18001879a  pop     rbx
0x18001879b  pop     rbp
0x18001879c  retn
```
