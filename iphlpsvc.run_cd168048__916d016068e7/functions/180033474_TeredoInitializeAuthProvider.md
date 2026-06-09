# TeredoInitializeAuthProvider

- ea: `0x180033474`
- end: `0x1800336ec`
- name: `TeredoInitializeAuthProvider`
- size: `632`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800331b0`

## callees

- `0x180033474`
- `0x18004b630`
- `0x18004c1c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180033534`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180033534`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800335a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800335a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800334d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800334d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800335e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003360d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033633`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033659`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800335e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003360d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033633`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033659`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800335c1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800335c1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180033680`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180033680`

## string_xrefs

- `0x1800334c4`: `System\CurrentControlSet\Services\iphlpsvc\Teredo`
- `0x1800335dd`: `CreateClientAuthContext`

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
0x180033474  mov     [rsp-8+arg_0], rbx
0x180033479  push    rbp
0x18003347a  lea     rbp, [rsp-160h]
0x180033482  sub     rsp, 260h
0x180033489  mov     rax, cs:__security_cookie
0x180033490  xor     rax, rsp
0x180033493  mov     [rbp+160h+var_10], rax
0x18003349a  xor     ebx, ebx
0x18003349c  lea     rcx, [rsp+260h+Data]; void *
0x1800334a1  xor     edx, edx; Val
0x1800334a3  mov     [rsp+260h+hKey], rbx
0x1800334a8  mov     r8d, 208h; Size
0x1800334ae  call    memset_0
0x1800334b3  lea     rax, [rsp+260h+hKey]
0x1800334b8  xor     r8d, r8d; ulOptions
0x1800334bb  lea     r9d, [rbx+1]; samDesired
0x1800334bf  mov     [rsp+260h+phkResult], rax; phkResult
0x1800334c4  lea     rdx, aSystemCurrentc_17; "System\\CurrentControlSet\\Services\\ip"...
0x1800334cb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800334d2  call    cs:__imp_RegOpenKeyExW
0x1800334d9  nop     dword ptr [rax+rax+00h]
0x1800334de  test    eax, eax
0x1800334e0  jnz     loc_180033671
0x1800334e6  xor     edx, edx; Val
0x1800334e8  mov     [rsp+260h+Type], ebx
0x1800334ec  mov     r8d, 208h; Size
0x1800334f2  lea     rcx, [rsp+260h+Data]; void *
0x1800334f7  call    memset_0
0x1800334fc  cmp     [rsp+260h+hKey], 0FFFFFFFFFFFFFFFFh
0x180033502  jz      short loc_180033560
0x180033504  mov     rcx, [rsp+260h+hKey]; hKey
0x180033509  lea     rax, [rsp+260h+cbData]
0x18003350e  mov     [rsp+260h+lpcbData], rax; lpcbData
0x180033513  lea     r9, [rsp+260h+Type]; lpType
0x180033518  lea     rax, [rsp+260h+Data]
0x18003351d  mov     [rsp+260h+cbData], 206h
0x180033525  xor     r8d, r8d; lpReserved
0x180033528  mov     [rsp+260h+phkResult], rax; lpData
0x18003352d  lea     rdx, aAuthprovider; "AuthProvider"
0x180033534  call    cs:__imp_RegQueryValueExW
0x18003353b  nop     dword ptr [rax+rax+00h]
0x180033540  test    eax, eax
0x180033542  jnz     short loc_180033560
0x180033544  cmp     [rsp+260h+Type], 1
0x180033549  jnz     short loc_180033560
0x18003354b  cmp     [rsp+260h+Data], bx
0x180033550  jz      short loc_180033560
0x180033552  mov     ecx, [rsp+260h+cbData]
0x180033556  shr     rcx, 1
0x180033559  mov     [rsp+rcx*2+260h+Data], bx
0x18003355e  jmp     short loc_18003359B
0x180033560  lea     rcx, word_180087660
0x180033567  mov     edx, 104h
0x18003356c  lea     rax, [rsp+260h+Data]
0x180033571  movzx   r8d, word ptr [rcx]
0x180033575  test    r8w, r8w
0x180033579  jz      short loc_18003358D
0x18003357b  mov     [rax], r8w
0x18003357f  add     rcx, 2
0x180033583  add     rax, 2
0x180033587  sub     rdx, 1
0x18003358b  jnz     short loc_180033571
0x18003358d  test    rdx, rdx
0x180033590  lea     rcx, [rax-2]
0x180033594  cmovnz  rcx, rax
0x180033598  mov     [rcx], bx
0x18003359b  mov     rcx, [rsp+260h+hKey]; hKey
0x1800335a0  call    cs:__imp_RegCloseKey
0x1800335a7  nop     dword ptr [rax+rax+00h]
0x1800335ac  cmp     [rsp+260h+Data], bx
0x1800335b1  jz      loc_180033671
0x1800335b7  xor     r8d, r8d; dwFlags
0x1800335ba  lea     rcx, [rsp+260h+Data]; lpLibFileName
0x1800335bf  xor     edx, edx; hFile
0x1800335c1  call    cs:__imp_LoadLibraryExW
0x1800335c8  nop     dword ptr [rax+rax+00h]
0x1800335cd  mov     cs:hLibModule, rax
0x1800335d4  test    rax, rax
0x1800335d7  jz      loc_180033693
0x1800335dd  lea     rdx, ProcName; "CreateClientAuthContext"
0x1800335e4  mov     rcx, rax; hModule
0x1800335e7  call    cs:__imp_GetProcAddress
0x1800335ee  nop     dword ptr [rax+rax+00h]
0x1800335f3  mov     qword ptr cs:xmmword_1800CC5B0, rax
0x1800335fa  test    rax, rax
0x1800335fd  jz      short loc_180033671
0x1800335ff  mov     rcx, cs:hLibModule; hModule
0x180033606  lea     rdx, aGetauthinfosiz; "GetAuthInfoSize"
0x18003360d  call    cs:__imp_GetProcAddress
0x180033614  nop     dword ptr [rax+rax+00h]
0x180033619  mov     qword ptr cs:xmmword_1800CC5B0+8, rax
0x180033620  test    rax, rax
0x180033623  jz      short loc_180033671
0x180033625  mov     rcx, cs:hLibModule; hModule
0x18003362c  lea     rdx, aFillinauthinfo; "FillInAuthInfo"
0x180033633  call    cs:__imp_GetProcAddress
0x18003363a  nop     dword ptr [rax+rax+00h]
0x18003363f  mov     qword ptr cs:xmmword_1800CC5C0, rax
0x180033646  test    rax, rax
0x180033649  jz      short loc_180033671
0x18003364b  mov     rcx, cs:hLibModule; hModule
0x180033652  lea     rdx, aVerifyauthinfo; "VerifyAuthInfo"
0x180033659  call    cs:__imp_GetProcAddress
0x180033660  nop     dword ptr [rax+rax+00h]
0x180033665  mov     qword ptr cs:xmmword_1800CC5C0+8, rax
0x18003366c  test    rax, rax
0x18003366f  jnz     short loc_1800336CB
0x180033671  mov     rax, cs:hLibModule
0x180033678  test    rax, rax
0x18003367b  jz      short loc_180033693
0x18003367d  mov     rcx, rax; hLibModule
0x180033680  call    cs:__imp_FreeLibrary
0x180033687  nop     dword ptr [rax+rax+00h]
0x18003368c  mov     cs:hLibModule, rbx
0x180033693  lea     rax, CreateClientAuthContext
0x18003369a  mov     qword ptr cs:xmmword_1800CC5B0, rax
0x1800336a1  lea     rax, ?Release@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::Release(void)
0x1800336a8  mov     qword ptr cs:xmmword_1800CC5B0+8, rax
0x1800336af  lea     rax, SplTunMgrAddressDeletion
0x1800336b6  mov     qword ptr cs:xmmword_1800CC5C0, rax
0x1800336bd  lea     rax, VerifyAuthInfo
0x1800336c4  mov     qword ptr cs:xmmword_1800CC5C0+8, rax
0x1800336cb  mov     rcx, [rbp+160h+var_10]
0x1800336d2  xor     rcx, rsp; StackCookie
0x1800336d5  call    __security_check_cookie
0x1800336da  mov     rbx, [rsp+260h+arg_0]
0x1800336e2  add     rsp, 260h
0x1800336e9  pop     rbp
0x1800336ea  retn
```
