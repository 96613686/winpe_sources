# TeredoInitializeAuthProvider

- ea: `0x180033484`
- end: `0x1800336fc`
- name: `TeredoInitializeAuthProvider`
- size: `632`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800331c0`

## callees

- `0x180033484`
- `0x18004b5f0`
- `0x18004c188`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180033544`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180033544`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800335b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800335b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800334e2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800334e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800335f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003361d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033643`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033669`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800335f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003361d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033643`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033669`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800335d1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800335d1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180033690`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180033690`

## string_xrefs

- `0x1800334d4`: `System\CurrentControlSet\Services\iphlpsvc\Teredo`
- `0x1800335ed`: `CreateClientAuthContext`

## pseudocode

```c
FARPROC TeredoInitializeAuthProvider()
{
  const OLECHAR *v0; // rcx
  __int64 v1; // rdx
  BYTE *v2; // rax
  BYTE *v3; // rcx
  HMODULE Library; // rax
  FARPROC result; // rax
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Data[264]; // [rsp+40h] [rbp-C0h] BYREF

  hKey = 0;
  memset_0(Data, 0, 0x208u);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\iphlpsvc\\Teredo", 0, 1u, &hKey) )
    goto LABEL_19;
  Type = 0;
  memset_0(Data, 0, 0x208u);
  if ( hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL
    || (cbData = 518, RegQueryValueExW(hKey, L"AuthProvider", 0, &Type, (LPBYTE)Data, &cbData))
    || Type != 1
    || !Data[0] )
  {
    v0 = &word_180087660;
    v1 = 260;
    v2 = (BYTE *)Data;
    do
    {
      if ( !*v0 )
        break;
      *(_WORD *)v2 = *v0++;
      v2 += 2;
      --v1;
    }
    while ( v1 );
    v3 = v2 - 2;
    if ( v1 )
      v3 = v2;
    *(_WORD *)v3 = 0;
  }
  else
  {
    Data[(unsigned __int64)cbData >> 1] = 0;
  }
  RegCloseKey(hKey);
  if ( !Data[0] )
    goto LABEL_19;
  Library = LoadLibraryExW(Data, 0, 0);
  hLibModule = Library;
  if ( !Library )
  {
LABEL_21:
    *(_QWORD *)&xmmword_1800CC5B0 = CreateClientAuthContext;
    *((_QWORD *)&xmmword_1800CC5B0 + 1) = ATL::CRegObject::Release;
    *(_QWORD *)&xmmword_1800CC5C0 = SplTunMgrAddressDeletion;
    result = VerifyAuthInfo;
    *((_QWORD *)&xmmword_1800CC5C0 + 1) = VerifyAuthInfo;
    return result;
  }
  *(_QWORD *)&xmmword_1800CC5B0 = GetProcAddress(Library, "CreateClientAuthContext");
  if ( !(_QWORD)xmmword_1800CC5B0
    || (*((_QWORD *)&xmmword_1800CC5B0 + 1) = GetProcAddress(hLibModule, "GetAuthInfoSize")) == 0
    || (*(_QWORD *)&xmmword_1800CC5C0 = GetProcAddress(hLibModule, "FillInAuthInfo"), !(_QWORD)xmmword_1800CC5C0)
    || (result = GetProcAddress(hLibModule, "VerifyAuthInfo"), (*((_QWORD *)&xmmword_1800CC5C0 + 1) = result) == 0) )
  {
LABEL_19:
    if ( hLibModule )
    {
      FreeLibrary(hLibModule);
      hLibModule = 0;
    }
    goto LABEL_21;
  }
  return result;
}

```

## disassembly

```asm
0x180033484  mov     [rsp-8+arg_0], rbx
0x180033489  push    rbp
0x18003348a  lea     rbp, [rsp-160h]
0x180033492  sub     rsp, 260h
0x180033499  mov     rax, cs:__security_cookie
0x1800334a0  xor     rax, rsp
0x1800334a3  mov     [rbp+160h+var_10], rax
0x1800334aa  xor     ebx, ebx
0x1800334ac  lea     rcx, [rsp+260h+Data]; void *
0x1800334b1  xor     edx, edx; Val
0x1800334b3  mov     [rsp+260h+hKey], rbx
0x1800334b8  mov     r8d, 208h; Size
0x1800334be  call    memset_0
0x1800334c3  lea     rax, [rsp+260h+hKey]
0x1800334c8  xor     r8d, r8d; ulOptions
0x1800334cb  lea     r9d, [rbx+1]; samDesired
0x1800334cf  mov     [rsp+260h+phkResult], rax; phkResult
0x1800334d4  lea     rdx, aSystemCurrentc_17; "System\\CurrentControlSet\\Services\\ip"...
0x1800334db  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800334e2  call    cs:__imp_RegOpenKeyExW
0x1800334e9  nop     dword ptr [rax+rax+00h]
0x1800334ee  test    eax, eax
0x1800334f0  jnz     loc_180033681
0x1800334f6  xor     edx, edx; Val
0x1800334f8  mov     [rsp+260h+Type], ebx
0x1800334fc  mov     r8d, 208h; Size
0x180033502  lea     rcx, [rsp+260h+Data]; void *
0x180033507  call    memset_0
0x18003350c  cmp     [rsp+260h+hKey], 0FFFFFFFFFFFFFFFFh
0x180033512  jz      short loc_180033570
0x180033514  mov     rcx, [rsp+260h+hKey]; hKey
0x180033519  lea     rax, [rsp+260h+cbData]
0x18003351e  mov     [rsp+260h+lpcbData], rax; lpcbData
0x180033523  lea     r9, [rsp+260h+Type]; lpType
0x180033528  lea     rax, [rsp+260h+Data]
0x18003352d  mov     [rsp+260h+cbData], 206h
0x180033535  xor     r8d, r8d; lpReserved
0x180033538  mov     [rsp+260h+phkResult], rax; lpData
0x18003353d  lea     rdx, aAuthprovider; "AuthProvider"
0x180033544  call    cs:__imp_RegQueryValueExW
0x18003354b  nop     dword ptr [rax+rax+00h]
0x180033550  test    eax, eax
0x180033552  jnz     short loc_180033570
0x180033554  cmp     [rsp+260h+Type], 1
0x180033559  jnz     short loc_180033570
0x18003355b  cmp     [rsp+260h+Data], bx
0x180033560  jz      short loc_180033570
0x180033562  mov     ecx, [rsp+260h+cbData]
0x180033566  shr     rcx, 1
0x180033569  mov     [rsp+rcx*2+260h+Data], bx
0x18003356e  jmp     short loc_1800335AB
0x180033570  lea     rcx, word_180087660
0x180033577  mov     edx, 104h
0x18003357c  lea     rax, [rsp+260h+Data]
0x180033581  movzx   r8d, word ptr [rcx]
0x180033585  test    r8w, r8w
0x180033589  jz      short loc_18003359D
0x18003358b  mov     [rax], r8w
0x18003358f  add     rcx, 2
0x180033593  add     rax, 2
0x180033597  sub     rdx, 1
0x18003359b  jnz     short loc_180033581
0x18003359d  test    rdx, rdx
0x1800335a0  lea     rcx, [rax-2]
0x1800335a4  cmovnz  rcx, rax
0x1800335a8  mov     [rcx], bx
0x1800335ab  mov     rcx, [rsp+260h+hKey]; hKey
0x1800335b0  call    cs:__imp_RegCloseKey
0x1800335b7  nop     dword ptr [rax+rax+00h]
0x1800335bc  cmp     [rsp+260h+Data], bx
0x1800335c1  jz      loc_180033681
0x1800335c7  xor     r8d, r8d; dwFlags
0x1800335ca  lea     rcx, [rsp+260h+Data]; lpLibFileName
0x1800335cf  xor     edx, edx; hFile
0x1800335d1  call    cs:__imp_LoadLibraryExW
0x1800335d8  nop     dword ptr [rax+rax+00h]
0x1800335dd  mov     cs:hLibModule, rax
0x1800335e4  test    rax, rax
0x1800335e7  jz      loc_1800336A3
0x1800335ed  lea     rdx, ProcName; "CreateClientAuthContext"
0x1800335f4  mov     rcx, rax; hModule
0x1800335f7  call    cs:__imp_GetProcAddress
0x1800335fe  nop     dword ptr [rax+rax+00h]
0x180033603  mov     qword ptr cs:xmmword_1800CC5B0, rax
0x18003360a  test    rax, rax
0x18003360d  jz      short loc_180033681
0x18003360f  mov     rcx, cs:hLibModule; hModule
0x180033616  lea     rdx, aGetauthinfosiz; "GetAuthInfoSize"
0x18003361d  call    cs:__imp_GetProcAddress
0x180033624  nop     dword ptr [rax+rax+00h]
0x180033629  mov     qword ptr cs:xmmword_1800CC5B0+8, rax
0x180033630  test    rax, rax
0x180033633  jz      short loc_180033681
0x180033635  mov     rcx, cs:hLibModule; hModule
0x18003363c  lea     rdx, aFillinauthinfo; "FillInAuthInfo"
0x180033643  call    cs:__imp_GetProcAddress
0x18003364a  nop     dword ptr [rax+rax+00h]
0x18003364f  mov     qword ptr cs:xmmword_1800CC5C0, rax
0x180033656  test    rax, rax
0x180033659  jz      short loc_180033681
0x18003365b  mov     rcx, cs:hLibModule; hModule
0x180033662  lea     rdx, aVerifyauthinfo; "VerifyAuthInfo"
0x180033669  call    cs:__imp_GetProcAddress
0x180033670  nop     dword ptr [rax+rax+00h]
0x180033675  mov     qword ptr cs:xmmword_1800CC5C0+8, rax
0x18003367c  test    rax, rax
0x18003367f  jnz     short loc_1800336DB
0x180033681  mov     rax, cs:hLibModule
0x180033688  test    rax, rax
0x18003368b  jz      short loc_1800336A3
0x18003368d  mov     rcx, rax; hLibModule
0x180033690  call    cs:__imp_FreeLibrary
0x180033697  nop     dword ptr [rax+rax+00h]
0x18003369c  mov     cs:hLibModule, rbx
0x1800336a3  lea     rax, CreateClientAuthContext
0x1800336aa  mov     qword ptr cs:xmmword_1800CC5B0, rax
0x1800336b1  lea     rax, ?Release@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::Release(void)
0x1800336b8  mov     qword ptr cs:xmmword_1800CC5B0+8, rax
0x1800336bf  lea     rax, SplTunMgrAddressDeletion
0x1800336c6  mov     qword ptr cs:xmmword_1800CC5C0, rax
0x1800336cd  lea     rax, VerifyAuthInfo
0x1800336d4  mov     qword ptr cs:xmmword_1800CC5C0+8, rax
0x1800336db  mov     rcx, [rbp+160h+var_10]
0x1800336e2  xor     rcx, rsp; StackCookie
0x1800336e5  call    __security_check_cookie
0x1800336ea  mov     rbx, [rsp+260h+arg_0]
0x1800336f2  add     rsp, 260h
0x1800336f9  pop     rbp
0x1800336fa  retn
```
