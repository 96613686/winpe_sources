# RegisterClassW(ushort const *,tagCLASS_DATA const *)

- ea: `0x1800b8b4c`
- end: `0x1800b8cdf`
- name: `?RegisterClassW@@YAJPEBGPEBUtagCLASS_DATA@@@Z`
- size: `403`
- prototype: `HRESULT __fastcall(const wchar_t *pclassdata, const tagCLASS_DATA *wszDllName)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b8e64`

## callees

- `0x180046460`
- `0x1800b8aa8`
- `0x1800b8b4c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b8c95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b8cab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b8c95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b8cab`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b8b8f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b8b8f`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800b8baa`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800b8c51`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800b8baa`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800b8c51`

## string_xrefs

- `0x1800b8bd3`: `CLSID`
- `0x1800b8c78`: `CLSID`

## pseudocode

```c
__int64 __fastcall RegisterClassW(const wchar_t *pclassdata, const tagCLASS_DATA *wszDllName)
{
  LSTATUS v3; // eax
  signed int v4; // ebx
  LSTATUS KeyW; // eax
  HKEY__ *hk; // [rsp+28h] [rbp-19h] BYREF
  wchar_t rgwchClsid[39]; // [rsp+30h] [rbp-11h] BYREF

  *(_QWORD *)rgwchClsid = -1;
  hk = (HKEY__ *)-1LL;
  StringFromGUID2(wszDllName->pclsid, &rgwchClsid[4], 39);
  v3 = RegCreateKeyW(g_hkClsid, &rgwchClsid[4], &hk);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
  {
    v4 = HrRegSetValueW(hk, L"CLSID", wszDllName->wszName);
    if ( v4 >= 0 )
    {
      v4 = HrRegSetValueW(hk, &value, wszDllName->wszName);
      if ( v4 >= 0 )
      {
        v4 = HrRegSetValueW(hk, L"InprocServer32", wszDllFileName);
        if ( v4 >= 0 )
        {
          v4 = HrRegSetValueW(hk, L"ProgID", wszDllName->wszProgId);
          if ( v4 >= 0 )
          {
            KeyW = RegCreateKeyW(g_hkRoot, wszDllName->wszProgId, (PHKEY)rgwchClsid);
            v4 = KeyW;
            if ( KeyW > 0 )
              v4 = (unsigned __int16)KeyW | 0x80070000;
            if ( v4 >= 0 )
            {
              v4 = HrRegSetValueW(*(HKEY__ **)rgwchClsid, L"CLSID", &rgwchClsid[4]);
              if ( v4 >= 0 )
                v4 = 0;
            }
          }
        }
      }
    }
  }
  if ( *(_QWORD *)rgwchClsid != -1 )
    RegCloseKey(*(HKEY *)rgwchClsid);
  if ( hk != (HKEY__ *)-1LL )
    RegCloseKey(hk);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800b8b4c  mov     rax, rsp
0x1800b8b4f  mov     [rax+8], rbx
0x1800b8b53  mov     [rax+18h], rsi
0x1800b8b57  mov     [rax+20h], rdi
0x1800b8b5b  push    rbp
0x1800b8b5c  lea     rbp, [rax-5Fh]
0x1800b8b60  sub     rsp, 90h
0x1800b8b67  mov     rax, cs:__security_cookie
0x1800b8b6e  xor     rax, rsp
0x1800b8b71  mov     [rbp+57h+var_10], rax
0x1800b8b75  or      qword ptr [rbp+57h+rgwchClsid], 0FFFFFFFFFFFFFFFFh
0x1800b8b7a  mov     rdi, pclassdata
0x1800b8b7d  or      [rbp+57h+hk], 0FFFFFFFFFFFFFFFFh
0x1800b8b82  lea     pclassdata, [rbp+57h+rgwchClsid+8]; lpsz
0x1800b8b86  mov     r8d, 27h ; '''; cchMax
0x1800b8b8c  mov     rcx, [rdi]; rguid
0x1800b8b8f  call    cs:__imp_StringFromGUID2
0x1800b8b96  nop     dword ptr [rax+rax+00h]
0x1800b8b9b  mov     rcx, cs:?g_hkClsid@@3PEAUHKEY__@@EA; hKey
0x1800b8ba2  lea     r8, [rbp+57h+hk]; phkResult
0x1800b8ba6  lea     pclassdata, [rbp+57h+rgwchClsid+8]; lpSubKey
0x1800b8baa  call    cs:__imp_RegCreateKeyW
0x1800b8bb1  nop     dword ptr [rax+rax+00h]
0x1800b8bb6  xor     esi, esi
0x1800b8bb8  mov     ebx, eax
0x1800b8bba  test    eax, eax
0x1800b8bbc  jle     short loc_1800B8BC7
0x1800b8bbe  movzx   ebx, ax
0x1800b8bc1  or      ebx, 80070000h
0x1800b8bc7  test    ebx, ebx
0x1800b8bc9  js      $Error_7
0x1800b8bcf  mov     r8, [rdi+8]; wszVal
0x1800b8bd3  lea     pclassdata, aClsid_1; "CLSID"
0x1800b8bda  mov     rcx, [rbp+57h+hk]; hk
0x1800b8bde  call    ?HrRegSetValueW@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetValueW(HKEY__ *,ushort const *,ushort const *)
0x1800b8be3  mov     ebx, eax
0x1800b8be5  test    eax, eax
0x1800b8be7  js      $Error_7
0x1800b8bed  mov     r8, [rdi+8]; wszVal
0x1800b8bf1  lea     pclassdata, value; wszSubKey
0x1800b8bf8  mov     rcx, [rbp+57h+hk]; hk
0x1800b8bfc  call    ?HrRegSetValueW@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetValueW(HKEY__ *,ushort const *,ushort const *)
0x1800b8c01  mov     ebx, eax
0x1800b8c03  test    eax, eax
0x1800b8c05  js      $Error_7
0x1800b8c0b  mov     rcx, [rbp+57h+hk]; hk
0x1800b8c0f  lea     r8, wszDllFileName; wszVal
0x1800b8c16  lea     pclassdata, aInprocserver32; "InprocServer32"
0x1800b8c1d  call    ?HrRegSetValueW@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetValueW(HKEY__ *,ushort const *,ushort const *)
0x1800b8c22  mov     ebx, eax
0x1800b8c24  test    eax, eax
0x1800b8c26  js      short $Error_7
0x1800b8c28  mov     r8, [rdi+10h]; wszVal
0x1800b8c2c  lea     pclassdata, aProgid; "ProgID"
0x1800b8c33  mov     rcx, [rbp+57h+hk]; hk
0x1800b8c37  call    ?HrRegSetValueW@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetValueW(HKEY__ *,ushort const *,ushort const *)
0x1800b8c3c  mov     ebx, eax
0x1800b8c3e  test    eax, eax
0x1800b8c40  js      short $Error_7
0x1800b8c42  mov     pclassdata, [rdi+10h]; lpSubKey
0x1800b8c46  lea     r8, [rbp+57h+rgwchClsid]; phkResult
0x1800b8c4a  mov     rcx, cs:?g_hkRoot@@3PEAUHKEY__@@EA; hKey
0x1800b8c51  call    cs:__imp_RegCreateKeyW
0x1800b8c58  nop     dword ptr [rax+rax+00h]
0x1800b8c5d  mov     ebx, eax
0x1800b8c5f  test    eax, eax
0x1800b8c61  jle     short loc_1800B8C6C
0x1800b8c63  movzx   ebx, ax
0x1800b8c66  or      ebx, 80070000h
0x1800b8c6c  test    ebx, ebx
0x1800b8c6e  js      short $Error_7
0x1800b8c70  mov     rcx, qword ptr [rbp+57h+rgwchClsid]; hk
0x1800b8c74  lea     r8, [rbp+57h+rgwchClsid+8]; wszVal
0x1800b8c78  lea     pclassdata, aClsid_1; "CLSID"
0x1800b8c7f  call    ?HrRegSetValueW@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetValueW(HKEY__ *,ushort const *,ushort const *)
0x1800b8c84  test    eax, eax
0x1800b8c86  mov     ebx, eax
0x1800b8c88  cmovns  ebx, esi
0x1800b8c8b  mov     rcx, qword ptr [rbp+57h+rgwchClsid]; hKey
0x1800b8c8f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b8c93  jz      short loc_1800B8CA1
0x1800b8c95  call    cs:__imp_RegCloseKey
0x1800b8c9c  nop     dword ptr [rax+rax+00h]
0x1800b8ca1  mov     rcx, [rbp+57h+hk]; hKey
0x1800b8ca5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b8ca9  jz      short loc_1800B8CB7
0x1800b8cab  call    cs:__imp_RegCloseKey
0x1800b8cb2  nop     dword ptr [rax+rax+00h]
0x1800b8cb7  mov     eax, ebx
0x1800b8cb9  mov     rcx, [rbp+57h+var_10]
0x1800b8cbd  xor     rcx, rsp; StackCookie
0x1800b8cc0  call    __security_check_cookie
0x1800b8cc5  lea     r11, [rsp+90h+var_s0]
0x1800b8ccd  mov     rbx, [r11+10h]
0x1800b8cd1  mov     rsi, [r11+20h]
0x1800b8cd5  mov     rdi, [r11+28h]
0x1800b8cd9  mov     rsp, r11
0x1800b8cdc  pop     rbp
0x1800b8cdd  retn
```
