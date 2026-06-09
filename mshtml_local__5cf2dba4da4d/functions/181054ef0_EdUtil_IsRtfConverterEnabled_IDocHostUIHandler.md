# EdUtil::IsRtfConverterEnabled(IDocHostUIHandler *)

- ea: `0x181054ef0`
- end: `0x181055110`
- name: `?IsRtfConverterEnabled@EdUtil@@YAHPEAUIDocHostUIHandler@@@Z`
- size: `544`
- prototype: `__int64 __fastcall(EdUtil *__hidden this, struct IDocHostUIHandler *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180805db4`

## callees

- `0x181054ef0`
- `0x1810f659a`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `KERNEL32!GetCPInfo` at `0x181055093`
- `KERNEL32!GetCPInfo` at `0x181055093`
- `KERNEL32!GetACP` at `0x181055080`
- `KERNEL32!GetACP` at `0x181055080`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x181055053`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x181055053`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x181054fe9`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x181055017`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x181054fe9`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x181055017`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1810550cb`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1810550e1`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1810550cb`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1810550e1`
- `iertutil!__imp_GetKeyPath` at `0x181054f8b`
- `iertutil!__imp_GetKeyPath` at `0x181054f8b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1810550b5`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1810550b5`

## pseudocode

```c
__int64 __fastcall EdUtil::IsRtfConverterEnabled(EdUtil *this, struct IDocHostUIHandler *a2)
{
  unsigned int v2; // ebx
  const WCHAR *v3; // rdx
  UINT ACP; // eax
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  struct _cpinfo CPInfo; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t String1[264]; // [rsp+70h] [rbp-90h] BYREF

  v2 = 0;
  hKey = 0;
  phkResult = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  pv = 0;
  memset(&CPInfo, 0, sizeof(CPInfo));
  if ( !this
    || ((*(void (__fastcall **)(EdUtil *, LPVOID *, _QWORD))(*(_QWORD *)this + 104LL))(this, &pv, 0),
        (v3 = (const WCHAR *)pv) == 0) )
  {
    if ( (unsigned int)GetKeyPath(IEKEY_GUID_Browser_RootHint, 2, String1, 260)
      || wcsncmp_0(String1, L"HKCU\\", (unsigned int)dword_1815B7DE8) )
    {
      goto LABEL_15;
    }
    v3 = &String1[(int)dword_1815B7DE8];
  }
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, v3, 0, 0x20019u, &hKey) && !RegOpenKeyExW(hKey, 0, 0, 0x20019u, &phkResult) )
  {
    v2 = 1;
    if ( !RegQueryValueExW(phkResult, L"RtfConverterFlags", 0, &Type, Data, &cbData) && Type - 3 <= 1 )
    {
      if ( (Data[0] & 1) == 0 )
      {
LABEL_14:
        v2 = 0;
        goto LABEL_15;
      }
      if ( (Data[0] & 2) != 0 )
        goto LABEL_15;
    }
    ACP = GetACP();
    if ( !GetCPInfo(ACP, &CPInfo) || CPInfo.MaxCharSize != 1 )
      goto LABEL_14;
  }
LABEL_15:
  if ( pv )
    CoTaskMemFree(pv);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x181054ef0  mov     [rsp-8+arg_8], rbx
0x181054ef5  mov     [rsp-8+arg_0], rcx
0x181054efa  push    rbp
0x181054efb  lea     rbp, [rsp-190h]
0x181054f03  sub     rsp, 290h
0x181054f0a  mov     rax, cs:__security_cookie
0x181054f11  xor     rax, rsp
0x181054f14  mov     [rbp+190h+var_10], rax
0x181054f1b  mov     rcx, [rbp+190h+arg_0]
0x181054f22  xor     eax, eax
0x181054f24  xor     ebx, ebx
0x181054f26  mov     dword ptr [rsp+290h+CPInfo.LeadByte+0Ah], eax
0x181054f2a  mov     [rsp+290h+hKey], rax
0x181054f2f  xorps   xmm0, xmm0
0x181054f32  mov     [rsp+290h+var_248], rax
0x181054f37  mov     [rsp+290h+Type], eax
0x181054f3b  mov     dword ptr [rsp+290h+Data], eax
0x181054f3f  mov     [rsp+290h+cbData], 4
0x181054f47  mov     [rsp+290h+pv], rax
0x181054f4c  movups  xmmword ptr [rsp+290h+CPInfo.MaxCharSize], xmm0
0x181054f51  test    rcx, rcx
0x181054f54  jz      short loc_181054F74
0x181054f56  mov     rax, [rcx]
0x181054f59  lea     rdx, [rsp+290h+pv]
0x181054f5e  xor     r8d, r8d
0x181054f61  mov     rax, [rax+68h]
0x181054f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181054f6a  mov     rdx, [rsp+290h+pv]
0x181054f6f  test    rdx, rdx
0x181054f72  jnz     short loc_181054FCF
0x181054f74  mov     r9d, 104h
0x181054f7a  lea     r8, [rsp+290h+String1]
0x181054f7f  mov     edx, 2
0x181054f84  lea     rcx, IEKEY_GUID_Browser_RootHint
0x181054f8b  call    cs:__imp_GetKeyPath
0x181054f92  nop     dword ptr [rax+rax+00h]
0x181054f97  test    eax, eax
0x181054f99  jnz     loc_1810550AB
0x181054f9f  mov     r8d, cs:dword_1815B7DE8; MaxCount
0x181054fa6  lea     rdx, aHkcu; "HKCU\\"
0x181054fad  lea     rcx, [rsp+290h+String1]; String1
0x181054fb2  call    wcsncmp_0
0x181054fb7  test    eax, eax
0x181054fb9  jnz     loc_1810550AB
0x181054fbf  movsxd  rax, cs:dword_1815B7DE8
0x181054fc6  lea     rdx, [rsp+290h+String1]
0x181054fcb  lea     rdx, [rdx+rax*2]; lpSubKey
0x181054fcf  lea     rax, [rsp+290h+hKey]
0x181054fd4  mov     r9d, 20019h; samDesired
0x181054fda  xor     r8d, r8d; ulOptions
0x181054fdd  mov     [rsp+290h+phkResult], rax; phkResult
0x181054fe2  mov     rcx, 0FFFFFFFF80000001h; hKey
0x181054fe9  call    cs:__imp_RegOpenKeyExW
0x181054ff0  nop     dword ptr [rax+rax+00h]
0x181054ff5  test    eax, eax
0x181054ff7  jnz     loc_1810550AB
0x181054ffd  mov     rcx, [rsp+290h+hKey]; hKey
0x181055002  lea     rax, [rsp+290h+var_248]
0x181055007  mov     r9d, 20019h; samDesired
0x18105500d  mov     [rsp+290h+phkResult], rax; phkResult
0x181055012  xor     r8d, r8d; ulOptions
0x181055015  xor     edx, edx; lpSubKey
0x181055017  call    cs:__imp_RegOpenKeyExW
0x18105501e  nop     dword ptr [rax+rax+00h]
0x181055023  test    eax, eax
0x181055025  jnz     loc_1810550AB
0x18105502b  mov     rcx, [rsp+290h+var_248]; hKey
0x181055030  lea     rax, [rsp+290h+cbData]
0x181055035  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18105503a  lea     r9, [rsp+290h+Type]; lpType
0x18105503f  lea     rax, [rsp+290h+Data]
0x181055044  xor     r8d, r8d; lpReserved
0x181055047  lea     rdx, aRtfconverterfl; "RtfConverterFlags"
0x18105504e  mov     [rsp+290h+phkResult], rax; lpData
0x181055053  call    cs:__imp_RegQueryValueExW
0x18105505a  nop     dword ptr [rax+rax+00h]
0x18105505f  mov     ebx, 1
0x181055064  test    eax, eax
0x181055066  jnz     short loc_181055080
0x181055068  mov     eax, [rsp+290h+Type]
0x18105506c  add     eax, 0FFFFFFFDh
0x18105506f  cmp     eax, ebx
0x181055071  ja      short loc_181055080
0x181055073  test    [rsp+290h+Data], bl
0x181055077  jz      short loc_1810550A9
0x181055079  test    [rsp+290h+Data], 2
0x18105507e  jnz     short loc_1810550AB
0x181055080  call    cs:__imp_GetACP
0x181055087  nop     dword ptr [rax+rax+00h]
0x18105508c  mov     ecx, eax; CodePage
0x18105508e  lea     rdx, [rsp+290h+CPInfo]; lpCPInfo
0x181055093  call    cs:__imp_GetCPInfo
0x18105509a  nop     dword ptr [rax+rax+00h]
0x18105509f  test    eax, eax
0x1810550a1  jz      short loc_1810550A9
0x1810550a3  cmp     [rsp+290h+CPInfo.MaxCharSize], ebx
0x1810550a7  jz      short loc_1810550AB
0x1810550a9  xor     ebx, ebx
0x1810550ab  mov     rcx, [rsp+290h+pv]; pv
0x1810550b0  test    rcx, rcx
0x1810550b3  jz      short loc_1810550C1
0x1810550b5  call    cs:__imp_CoTaskMemFree
0x1810550bc  nop     dword ptr [rax+rax+00h]
0x1810550c1  mov     rcx, [rsp+290h+var_248]; hKey
0x1810550c6  test    rcx, rcx
0x1810550c9  jz      short loc_1810550D7
0x1810550cb  call    cs:__imp_RegCloseKey
0x1810550d2  nop     dword ptr [rax+rax+00h]
0x1810550d7  mov     rcx, [rsp+290h+hKey]; hKey
0x1810550dc  test    rcx, rcx
0x1810550df  jz      short loc_1810550ED
0x1810550e1  call    cs:__imp_RegCloseKey
0x1810550e8  nop     dword ptr [rax+rax+00h]
0x1810550ed  mov     eax, ebx
0x1810550ef  mov     rcx, [rbp+190h+var_10]
0x1810550f6  xor     rcx, rsp; StackCookie
0x1810550f9  call    __security_check_cookie
0x1810550fe  mov     rbx, [rsp+290h+arg_8]
0x181055106  add     rsp, 290h
0x18105510d  pop     rbp
0x18105510e  retn
```
