# ATL::CComModule::UnregisterClassHelper(_GUID const &,ushort const *,ushort const *)

- ea: `0x180004ae4`
- end: `0x180004bc0`
- name: `?UnregisterClassHelper@CComModule@ATL@@QEAAJAEBU_GUID@@PEBG1@Z`
- size: `220`
- prototype: `int(ATL::CComModule *__hidden this, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180007710`
- `0x180007750`
- `0x180007790`
- `0x1800077d0`
- `0x180007810`
- `0x180007850`

## callees

- `0x180004570`
- `0x1800045d4`
- `0x180004ae4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004ba0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004ba0`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180004b6e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180004b6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004baf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004baf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004b24`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004b49`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004b24`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004b49`

## string_xrefs

- `0x180004b78`: `CLSID`

## pseudocode

```c
__int64 __fastcall ATL::CComModule::UnregisterClassHelper(
        OLECHAR *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  const unsigned __int16 *v7; // rbx
  unsigned int v8; // r9d
  HKEY hKey[5]; // [rsp+20h] [rbp-28h] BYREF
  LPOLESTR lpsz; // [rsp+70h] [rbp+28h] BYREF

  lpsz = this;
  hKey[1] = 0;
  hKey[2] = 0;
  hKey[0] = HKEY_CLASSES_ROOT;
  if ( a3 && lstrcmpiW(a3, &String2) )
    ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, a3);
  if ( a4 && lstrcmpiW(a4, &String2) )
    ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, a4);
  lpsz = 0;
  StringFromCLSID(a2, &lpsz);
  v7 = lpsz;
  if ( !ATL::CRegKey::Open((ATL::CRegKey *)hKey, hKey[0], L"CLSID", v8) )
    ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, v7);
  CoTaskMemFree(lpsz);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return 0;
}

```

## disassembly

```asm
0x180004ae4  mov     [rsp-20h+lpsz], rcx
0x180004ae9  push    rbp
0x180004aea  push    rbx
0x180004aeb  push    rsi
0x180004aec  push    rdi
0x180004aed  mov     rbp, rsp
0x180004af0  sub     rsp, 48h
0x180004af4  mov     [rbp+var_20], 0
0x180004afc  mov     rbx, r9
0x180004aff  mov     [rbp+var_18], 0
0x180004b07  mov     rdi, r8
0x180004b0a  mov     [rbp+hKey], 0FFFFFFFF80000000h
0x180004b12  mov     rsi, rdx
0x180004b15  test    r8, r8
0x180004b18  jz      short loc_180004B3A
0x180004b1a  lea     rdx, String2; lpString2
0x180004b21  mov     rcx, r8; lpString1
0x180004b24  call    cs:__imp_lstrcmpiW
0x180004b2a  test    eax, eax
0x180004b2c  jz      short loc_180004B3A
0x180004b2e  mov     rdx, rdi; unsigned __int16 *
0x180004b31  lea     rcx, [rbp+hKey]; this
0x180004b35  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180004b3a  test    rbx, rbx
0x180004b3d  jz      short loc_180004B5F
0x180004b3f  lea     rdx, String2; lpString2
0x180004b46  mov     rcx, rbx; lpString1
0x180004b49  call    cs:__imp_lstrcmpiW
0x180004b4f  test    eax, eax
0x180004b51  jz      short loc_180004B5F
0x180004b53  mov     rdx, rbx; unsigned __int16 *
0x180004b56  lea     rcx, [rbp+hKey]; this
0x180004b5a  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180004b5f  lea     rdx, [rbp+lpsz]; lplpsz
0x180004b63  mov     [rbp+lpsz], 0
0x180004b6b  mov     rcx, rsi; rclsid
0x180004b6e  call    cs:__imp_StringFromCLSID
0x180004b74  mov     rdx, [rbp+hKey]; HKEY
0x180004b78  lea     r8, aClsid; "CLSID"
0x180004b7f  mov     rbx, [rbp+lpsz]
0x180004b83  lea     rcx, [rbp+hKey]; this
0x180004b87  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180004b8c  test    eax, eax
0x180004b8e  jnz     short loc_180004B9C
0x180004b90  mov     rdx, rbx; unsigned __int16 *
0x180004b93  lea     rcx, [rbp+hKey]; this
0x180004b97  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180004b9c  mov     rcx, [rbp+lpsz]; pv
0x180004ba0  call    cs:__imp_CoTaskMemFree
0x180004ba6  mov     rcx, [rbp+hKey]; hKey
0x180004baa  test    rcx, rcx
0x180004bad  jz      short loc_180004BB5
0x180004baf  call    cs:__imp_RegCloseKey
0x180004bb5  xor     eax, eax
0x180004bb7  add     rsp, 48h
0x180004bbb  pop     rdi
0x180004bbc  pop     rsi
0x180004bbd  pop     rbx
0x180004bbe  pop     rbp
0x180004bbf  retn
```
