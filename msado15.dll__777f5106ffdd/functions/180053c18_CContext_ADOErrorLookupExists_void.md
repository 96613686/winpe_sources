# CContext::ADOErrorLookupExists(void)

- ea: `0x180053c18`
- end: `0x180053d0b`
- name: `?ADOErrorLookupExists@CContext@@QEAA_NXZ`
- size: `243`
- prototype: `bool __fastcall(CContext *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800cb624`

## callees

- `0x180053c18`
- `0x1800ccaa4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180053cdb`
- `ADVAPI32!RegCloseKey` at `0x180053cfa`
- `ADVAPI32!RegCloseKey` at `0x180053cdb`
- `ADVAPI32!RegCloseKey` at `0x180053cfa`
- `ADVAPI32!RegOpenKeyExW` at `0x180053c7c`
- `ADVAPI32!RegOpenKeyExW` at `0x180053cc3`
- `ADVAPI32!RegOpenKeyExW` at `0x180053c7c`
- `ADVAPI32!RegOpenKeyExW` at `0x180053cc3`

## string_xrefs

- `0x180053c4c`: `CLSID`

## pseudocode

```c
bool __fastcall CContext::ADOErrorLookupExists(CContext *this)
{
  const struct _GUID *v2; // rdx
  int v3; // r8d
  int v4; // r9d
  const WCHAR *v5; // rax
  _BYTE v6[104]; // [rsp+30h] [rbp-68h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+A8h] [rbp+10h] BYREF

  hKey = (HKEY)this;
  if ( *((_BYTE *)g_pStaticGlobals + 16) == 0xFF )
  {
    *((_BYTE *)g_pStaticGlobals + 16) = 0;
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0x20019u, &hKey) )
    {
      phkResult = 0;
      v5 = (const WCHAR *)CStrOfGUID::CStrOfGUID((CStrOfGUID *)v6, v2, v3, v4);
      if ( !RegOpenKeyExW(hKey, v5, 0, 0x20019u, &phkResult) )
      {
        RegCloseKey(phkResult);
        *((_BYTE *)g_pStaticGlobals + 16) = 1;
      }
      RegCloseKey(hKey);
    }
  }
  return *((_BYTE *)g_pStaticGlobals + 16) != 0;
}

```

## disassembly

```asm
0x180053c18  mov     [rsp+hKey], rcx
0x180053c1d  sub     rsp, 98h
0x180053c24  mov     rax, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180053c2b  cmp     byte ptr [rax+10h], 0FFh
0x180053c2f  jz      short loc_180053C48
0x180053c31  mov     rax, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180053c38  cmp     byte ptr [rax+10h], 0
0x180053c3c  setnz   al
0x180053c3f  add     rsp, 98h
0x180053c46  retn
0x180053c48  mov     byte ptr [rax+10h], 0
0x180053c4c  lea     rdx, SubKey; "CLSID"
0x180053c53  lea     rax, [rsp+98h+hKey]
0x180053c5b  mov     [rsp+98h+hKey], 0
0x180053c67  mov     r9d, 20019h; samDesired
0x180053c6d  mov     [rsp+98h+phkResult], rax; phkResult
0x180053c72  xor     r8d, r8d; ulOptions
0x180053c75  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180053c7c  call    cs:__imp_RegOpenKeyExW
0x180053c83  nop     dword ptr [rax+rax+00h]
0x180053c88  test    eax, eax
0x180053c8a  jnz     short loc_180053C31
0x180053c8c  lea     rcx, [rsp+98h+var_68]; this
0x180053c91  mov     [rsp+98h+arg_8], 0
0x180053c9d  call    ??0CStrOfGUID@@QEAA@AEBU_GUID@@HH@Z; CStrOfGUID::CStrOfGUID(_GUID const &,int,int)
0x180053ca2  lea     rcx, [rsp+98h+arg_8]
0x180053caa  mov     r9d, 20019h; samDesired
0x180053cb0  mov     [rsp+98h+phkResult], rcx; phkResult
0x180053cb5  xor     r8d, r8d; ulOptions
0x180053cb8  mov     rcx, [rsp+98h+hKey]; hKey
0x180053cc0  mov     rdx, rax; lpSubKey
0x180053cc3  call    cs:__imp_RegOpenKeyExW
0x180053cca  nop     dword ptr [rax+rax+00h]
0x180053ccf  test    eax, eax
0x180053cd1  jnz     short loc_180053CF2
0x180053cd3  mov     rcx, [rsp+98h+arg_8]; hKey
0x180053cdb  call    cs:__imp_RegCloseKey
0x180053ce2  nop     dword ptr [rax+rax+00h]
0x180053ce7  mov     rax, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180053cee  mov     byte ptr [rax+10h], 1
0x180053cf2  mov     rcx, [rsp+98h+hKey]; hKey
0x180053cfa  call    cs:__imp_RegCloseKey
0x180053d01  nop     dword ptr [rax+rax+00h]
0x180053d06  jmp     loc_180053C31
```
