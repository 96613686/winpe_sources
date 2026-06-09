# CAccountData::_ReadLocation(void)

- ea: `0x1800085b8`
- end: `0x1800086c6`
- name: `?_ReadLocation@CAccountData@@AEAAXXZ`
- size: `270`
- prototype: `void __fastcall(CAccountData *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180008184`

## callees

- `0x1800085b8`
- `0x18002a112`
- `0x18002a150`

## import_xrefs

- `SHLWAPI!StrToIntW` at `0x180008683`
- `SHLWAPI!StrToIntW` at `0x180008683`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x1800085e8`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x1800085e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008628`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008628`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008674`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008674`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008695`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008695`

## pseudocode

```c
void __fastcall CAccountData::_ReadLocation(CAccountData *this)
{
  GEOID UserGeoID; // eax
  BOOL v3; // edi
  HKEY v4; // rcx
  DWORD cbData; // [rsp+30h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C0h] BYREF
  WCHAR Data[80]; // [rsp+40h] [rbp-B8h] BYREF

  if ( !*((_DWORD *)this + 150) )
  {
    UserGeoID = GetUserGeoID(0x10u);
    *(_DWORD *)this = UserGeoID;
    v3 = UserGeoID != -1;
    goto LABEL_7;
  }
  v4 = (HKEY)*((_QWORD *)this + 77);
  hKey = 0;
  if ( !RegOpenKeyExW(v4, L"Control Panel\\International\\Geo", 0, 0x20019u, &hKey) )
  {
    v3 = 0;
    memset_0(Data, 0, sizeof(Data));
    cbData = 160;
    if ( !RegQueryValueExW(hKey, L"Nation", 0, 0, (LPBYTE)Data, &cbData) )
    {
      *(_DWORD *)this = StrToIntW(Data);
      v3 = 1;
    }
    RegCloseKey(hKey);
LABEL_7:
    if ( v3 )
      return;
  }
  *(_DWORD *)this = 0;
}

```

## disassembly

```asm
0x1800085b8  mov     [rsp+arg_8], rbx
0x1800085bd  push    rdi
0x1800085be  sub     rsp, 0F0h
0x1800085c5  mov     rax, cs:__security_cookie
0x1800085cc  xor     rax, rsp
0x1800085cf  mov     [rsp+0F8h+var_18], rax
0x1800085d7  cmp     dword ptr [rcx+258h], 0
0x1800085de  mov     rbx, rcx
0x1800085e1  jnz     short loc_1800085FE
0x1800085e3  mov     ecx, 10h; GeoClass
0x1800085e8  call    cs:__imp_GetUserGeoID
0x1800085ee  xor     edi, edi
0x1800085f0  mov     [rbx], eax
0x1800085f2  cmp     eax, 0FFFFFFFFh
0x1800085f5  setnz   dil
0x1800085f9  jmp     loc_18000869B
0x1800085fe  mov     rcx, [rcx+268h]; hKey
0x180008605  lea     rax, [rsp+0F8h+hKey]
0x18000860a  mov     r9d, 20019h; samDesired
0x180008610  mov     [rsp+0F8h+phkResult], rax; phkResult
0x180008615  xor     r8d, r8d; ulOptions
0x180008618  mov     [rsp+0F8h+hKey], 0
0x180008621  lea     rdx, aControlPanelIn_0; "Control Panel\\International\\Geo"
0x180008628  call    cs:__imp_RegOpenKeyExW
0x18000862e  test    eax, eax
0x180008630  jnz     short loc_18000869F
0x180008632  xor     edx, edx; Val
0x180008634  lea     rcx, [rsp+0F8h+Data]; void *
0x180008639  mov     r8d, 0A0h; Size
0x18000863f  xor     edi, edi
0x180008641  call    memset_0
0x180008646  mov     rcx, [rsp+0F8h+hKey]; hKey
0x18000864b  lea     rax, [rsp+0F8h+cbData]
0x180008650  mov     [rsp+0F8h+lpcbData], rax; lpcbData
0x180008655  lea     rdx, aNation; "Nation"
0x18000865c  lea     rax, [rsp+0F8h+Data]
0x180008661  mov     [rsp+0F8h+cbData], 0A0h
0x180008669  xor     r9d, r9d; lpType
0x18000866c  mov     [rsp+0F8h+phkResult], rax; lpData
0x180008671  xor     r8d, r8d; lpReserved
0x180008674  call    cs:__imp_RegQueryValueExW
0x18000867a  test    eax, eax
0x18000867c  jnz     short loc_180008690
0x18000867e  lea     rcx, [rsp+0F8h+Data]; pszSrc
0x180008683  call    cs:__imp_StrToIntW
0x180008689  mov     [rbx], eax
0x18000868b  mov     edi, 1
0x180008690  mov     rcx, [rsp+0F8h+hKey]; hKey
0x180008695  call    cs:__imp_RegCloseKey
0x18000869b  test    edi, edi
0x18000869d  jnz     short loc_1800086A5
0x18000869f  mov     dword ptr [rbx], 0
0x1800086a5  mov     rcx, [rsp+0F8h+var_18]
0x1800086ad  xor     rcx, rsp; StackCookie
0x1800086b0  call    __security_check_cookie
0x1800086b5  mov     rbx, [rsp+0F8h+arg_8]
0x1800086bd  add     rsp, 0F0h
0x1800086c4  pop     rdi
0x1800086c5  retn
```
