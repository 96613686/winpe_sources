# AMovieSetupRegisterServer

- ea: `0x180033510`
- end: `0x180033829`
- name: `AMovieSetupRegisterServer`
- size: `793`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180059a90`

## callees

- `0x180004924`
- `0x180026490`
- `0x180033510`
- `0x1800388a0`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x1800335ba`
- `ADVAPI32!RegCreateKeyExW` at `0x1800336c0`
- `ADVAPI32!RegCreateKeyExW` at `0x1800335ba`
- `ADVAPI32!RegCreateKeyExW` at `0x1800336c0`
- `ADVAPI32!RegSetValueExW` at `0x180033634`
- `ADVAPI32!RegSetValueExW` at `0x180033734`
- `ADVAPI32!RegSetValueExW` at `0x1800337c6`
- `ADVAPI32!RegSetValueExW` at `0x180033634`
- `ADVAPI32!RegSetValueExW` at `0x180033734`
- `ADVAPI32!RegSetValueExW` at `0x1800337c6`
- `ADVAPI32!RegCloseKey` at `0x18003364b`
- `ADVAPI32!RegCloseKey` at `0x18003374b`
- `ADVAPI32!RegCloseKey` at `0x1800337d9`
- `ADVAPI32!RegCloseKey` at `0x1800337ea`
- `ADVAPI32!RegCloseKey` at `0x18003364b`
- `ADVAPI32!RegCloseKey` at `0x18003374b`
- `ADVAPI32!RegCloseKey` at `0x1800337d9`
- `ADVAPI32!RegCloseKey` at `0x1800337ea`
- `ole32!StringFromGUID2` at `0x18003354a`
- `ole32!StringFromGUID2` at `0x18003354a`

## string_xrefs

- `0x18003379d`: `ThreadingModel`
- `0x18003356d`: `CLSID\%ls`

## pseudocode

```c
__int64 __fastcall AMovieSetupRegisterServer(const GUID *a1, __int64 a2, __int64 a3)
{
  LSTATUS v5; // eax
  __int64 result; // rax
  LSTATUS v7; // ebx
  HKEY v8; // rcx
  LSTATUS v9; // ebx
  unsigned __int64 v10; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR sz[40]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+C0h] [rbp-40h] BYREF

  StringFromGUID2(a1, sz, 39);
  hKey = 0;
  StringCchPrintfW(SubKey, 0x104u, L"CLSID\\%ls", sz);
  v5 = RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0x2000000u, 0, &hKey, 0);
  if ( v5 )
    return v5 | 0x80070000;
  StringCchPrintfW(SubKey, 0x104u, L"%ls", a2);
  v10 = 0;
  result = StringCchLengthW(SubKey, 0x104u, &v10);
  if ( (int)result >= 0 )
  {
    v7 = RegSetValueExW(hKey, 0, 0, 1u, (const BYTE *)SubKey, 2 * v10 + 2);
    if ( v7
      || (phkResult = 0,
          StringCchPrintfW(SubKey, 0x104u, L"%ls", L"InprocServer32"),
          (v7 = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x2000000u, 0, &phkResult, 0)) != 0) )
    {
      v8 = hKey;
    }
    else
    {
      StringCchPrintfW(SubKey, 0x104u, L"%ls", a3);
      v10 = 0;
      result = StringCchLengthW(SubKey, 0x104u, &v10);
      if ( (int)result < 0 )
        return result;
      v7 = RegSetValueExW(phkResult, 0, 0, v7 + 1, (const BYTE *)SubKey, 2 * v10 + 2);
      if ( !v7 )
      {
        StringCchPrintfW(SubKey, 0x104u, L"%ls", L"Both");
        v10 = 0;
        result = StringCchLengthW(SubKey, 0x104u, &v10);
        if ( (int)result < 0 )
          return result;
        v9 = RegSetValueExW(phkResult, L"ThreadingModel", 0, 1u, (const BYTE *)SubKey, 2 * v10 + 2);
        RegCloseKey(hKey);
        RegCloseKey(phkResult);
        if ( v9 > 0 )
          return (unsigned __int16)v9 | 0x80070000;
        return (unsigned int)v9;
      }
      RegCloseKey(hKey);
      v8 = phkResult;
    }
    RegCloseKey(v8);
    return v7 | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180033510  mov     [rsp-8+arg_18], rbx
0x180033515  push    rbp
0x180033516  push    rdi
0x180033517  push    r14
0x180033519  lea     rbp, [rsp-1E0h]
0x180033521  sub     rsp, 2E0h
0x180033528  mov     rax, cs:__security_cookie
0x18003352f  xor     rax, rsp
0x180033532  mov     [rbp+1F0h+var_20], rax
0x180033539  mov     rdi, r8
0x18003353c  mov     rbx, rdx
0x18003353f  mov     r8d, 27h ; '''; cchMax
0x180033545  lea     rdx, [rsp+2F0h+sz]; lpsz
0x18003354a  call    cs:__imp_StringFromGUID2
0x180033551  nop     dword ptr [rax+rax+00h]
0x180033556  mov     r14d, 104h
0x18003355c  mov     [rsp+2F0h+hKey], 0
0x180033565  mov     edx, r14d; unsigned __int64
0x180033568  lea     r9, [rsp+2F0h+sz]
0x18003356d  lea     r8, aClsidLs; "CLSID\\%ls"
0x180033574  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x180033578  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003357d  mov     [rsp+2F0h+lpdwDisposition], 0; lpdwDisposition
0x180033586  lea     rax, [rsp+2F0h+hKey]
0x18003358b  mov     [rsp+2F0h+phkResult], rax; phkResult
0x180033590  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x180033594  mov     [rsp+2F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003359d  xor     r9d, r9d; lpClass
0x1800335a0  mov     [rsp+2F0h+samDesired], 2000000h; samDesired
0x1800335a8  xor     r8d, r8d; Reserved
0x1800335ab  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800335b2  mov     [rsp+2F0h+dwOptions], 0; dwOptions
0x1800335ba  call    cs:__imp_RegCreateKeyExW
0x1800335c1  nop     dword ptr [rax+rax+00h]
0x1800335c6  test    eax, eax
0x1800335c8  jz      short loc_1800335D4
0x1800335ca  or      eax, 80070000h
0x1800335cf  jmp     loc_180033805
0x1800335d4  mov     r9, rbx
0x1800335d7  lea     r8, aLs; "%ls"
0x1800335de  mov     rdx, r14; unsigned __int64
0x1800335e1  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x1800335e5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800335ea  lea     r8, [rsp+2F0h+var_2A0]; unsigned __int64 *
0x1800335ef  mov     [rsp+2F0h+var_2A0], 0
0x1800335f8  mov     rdx, r14; unsigned __int64
0x1800335fb  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x1800335ff  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180033604  test    eax, eax
0x180033606  js      loc_180033805
0x18003360c  mov     eax, dword ptr [rsp+2F0h+var_2A0]
0x180033610  mov     r9d, 1; dwType
0x180033616  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18003361b  xor     r8d, r8d; Reserved
0x18003361e  xor     edx, edx; lpValueName
0x180033620  lea     eax, ds:2[rax*2]
0x180033627  mov     [rsp+2F0h+samDesired], eax; cbData
0x18003362b  lea     rax, [rbp+1F0h+SubKey]
0x18003362f  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x180033634  call    cs:__imp_RegSetValueExW
0x18003363b  nop     dword ptr [rax+rax+00h]
0x180033640  mov     ebx, eax
0x180033642  test    eax, eax
0x180033644  jz      short loc_180033662
0x180033646  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18003364b  call    cs:__imp_RegCloseKey
0x180033652  nop     dword ptr [rax+rax+00h]
0x180033657  or      ebx, 80070000h
0x18003365d  jmp     loc_180033803
0x180033662  lea     r9, aInprocserver32; "InprocServer32"
0x180033669  mov     [rsp+2F0h+var_290], 0
0x180033672  lea     r8, aLs; "%ls"
0x180033679  mov     rdx, r14; unsigned __int64
0x18003367c  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x180033680  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033685  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18003368a  lea     rax, [rsp+2F0h+var_290]
0x18003368f  mov     [rsp+2F0h+lpdwDisposition], 0; lpdwDisposition
0x180033698  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x18003369c  mov     [rsp+2F0h+phkResult], rax; phkResult
0x1800336a1  xor     r9d, r9d; lpClass
0x1800336a4  mov     [rsp+2F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800336ad  xor     r8d, r8d; Reserved
0x1800336b0  mov     [rsp+2F0h+samDesired], 2000000h; samDesired
0x1800336b8  mov     [rsp+2F0h+dwOptions], 0; dwOptions
0x1800336c0  call    cs:__imp_RegCreateKeyExW
0x1800336c7  nop     dword ptr [rax+rax+00h]
0x1800336cc  mov     ebx, eax
0x1800336ce  test    eax, eax
0x1800336d0  jnz     loc_180033646
0x1800336d6  mov     r9, rdi
0x1800336d9  lea     r8, aLs; "%ls"
0x1800336e0  mov     rdx, r14; unsigned __int64
0x1800336e3  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x1800336e7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800336ec  lea     r8, [rsp+2F0h+var_2A0]; unsigned __int64 *
0x1800336f1  mov     [rsp+2F0h+var_2A0], 0
0x1800336fa  mov     rdx, r14; unsigned __int64
0x1800336fd  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x180033701  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180033706  test    eax, eax
0x180033708  js      loc_180033805
0x18003370e  mov     eax, dword ptr [rsp+2F0h+var_2A0]
0x180033712  lea     r9d, [rbx+1]; dwType
0x180033716  mov     rcx, [rsp+2F0h+var_290]; hKey
0x18003371b  xor     r8d, r8d; Reserved
0x18003371e  xor     edx, edx; lpValueName
0x180033720  lea     eax, ds:2[rax*2]
0x180033727  mov     [rsp+2F0h+samDesired], eax; cbData
0x18003372b  lea     rax, [rbp+1F0h+SubKey]
0x18003372f  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x180033734  call    cs:__imp_RegSetValueExW
0x18003373b  nop     dword ptr [rax+rax+00h]
0x180033740  mov     ebx, eax
0x180033742  test    eax, eax
0x180033744  jz      short loc_180033761
0x180033746  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18003374b  call    cs:__imp_RegCloseKey
0x180033752  nop     dword ptr [rax+rax+00h]
0x180033757  mov     rcx, [rsp+2F0h+var_290]
0x18003375c  jmp     loc_18003364B
0x180033761  lea     r9, aBoth; "Both"
0x180033768  mov     rdx, r14; unsigned __int64
0x18003376b  lea     r8, aLs; "%ls"
0x180033772  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x180033776  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003377b  lea     r8, [rsp+2F0h+var_2A0]; unsigned __int64 *
0x180033780  mov     [rsp+2F0h+var_2A0], 0
0x180033789  mov     rdx, r14; unsigned __int64
0x18003378c  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x180033790  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180033795  test    eax, eax
0x180033797  js      short loc_180033805
0x180033799  mov     eax, dword ptr [rsp+2F0h+var_2A0]
0x18003379d  lea     rdx, aThreadingmodel; "ThreadingModel"
0x1800337a4  mov     rcx, [rsp+2F0h+var_290]; hKey
0x1800337a9  mov     r9d, 1; dwType
0x1800337af  xor     r8d, r8d; Reserved
0x1800337b2  lea     eax, ds:2[rax*2]
0x1800337b9  mov     [rsp+2F0h+samDesired], eax; cbData
0x1800337bd  lea     rax, [rbp+1F0h+SubKey]
0x1800337c1  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x1800337c6  call    cs:__imp_RegSetValueExW
0x1800337cd  nop     dword ptr [rax+rax+00h]
0x1800337d2  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1800337d7  mov     ebx, eax
0x1800337d9  call    cs:__imp_RegCloseKey
0x1800337e0  nop     dword ptr [rax+rax+00h]
0x1800337e5  mov     rcx, [rsp+2F0h+var_290]; hKey
0x1800337ea  call    cs:__imp_RegCloseKey
0x1800337f1  nop     dword ptr [rax+rax+00h]
0x1800337f6  test    ebx, ebx
0x1800337f8  jle     short loc_180033803
0x1800337fa  movzx   ebx, bx
0x1800337fd  or      ebx, 80070000h
0x180033803  mov     eax, ebx
0x180033805  mov     rcx, [rbp+1F0h+var_20]
0x18003380c  xor     rcx, rsp; StackCookie
0x18003380f  call    __security_check_cookie
0x180033814  mov     rbx, [rsp+2F0h+arg_18]
0x18003381c  add     rsp, 2E0h
0x180033823  pop     r14
0x180033825  pop     rdi
0x180033826  pop     rbp
0x180033827  retn
```
