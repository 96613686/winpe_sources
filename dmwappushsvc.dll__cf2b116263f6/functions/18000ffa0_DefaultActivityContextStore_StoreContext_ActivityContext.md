# DefaultActivityContextStore::StoreContext(ActivityContext &)

- ea: `0x18000ffa0`
- end: `0x180010217`
- name: `?StoreContext@DefaultActivityContextStore@@UEAAJAEAVActivityContext@@@Z`
- size: `631`
- prototype: `__int64 __fastcall(DefaultActivityContextStore *__hidden this, struct ActivityContext *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180001a70`
- `0x180005aec`
- `0x18000dd1c`
- `0x18000deb0`
- `0x18000e938`
- `0x18000ee14`
- `0x18000eecc`
- `0x18000ffa0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001000f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001000f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010099`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010099`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800100dd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800100dd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001013b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010170`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800101a1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001013b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010170`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800101a1`

## string_xrefs

- `0x18001014b`: `AttemptCounter`
- `0x18001017c`: `Rollback`

## pseudocode

```c
__int64 __fastcall DefaultActivityContextStore::StoreContext(
        DefaultActivityContextStore *this,
        struct ActivityContext *a2)
{
  signed int v3; // edi
  const unsigned __int16 *EnrollmentsRootKey; // rax
  LSTATUS v5; // eax
  bool v6; // cc
  const unsigned __int16 *v7; // r8
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  BYTE v11[4]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE v12[4]; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  OLECHAR sz[40]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v15[40]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR SubKey[264]; // [rsp+110h] [rbp+10h] BYREF

  *(_DWORD *)Data = 32;
  *(_DWORD *)v11 = 0;
  *(_DWORD *)v12 = 0;
  hKey = 0;
  phkResult = 0;
  SubKey[0] = 0;
  v15[0] = 0;
  sz[0] = 0;
  if ( StringFromGUID2((const GUID *const)((char *)a2 + 8), sz, 39) == 39 )
  {
    v3 = EEDBTrimGuidBracket(sz, v15);
    if ( v3 >= 0 )
    {
      EnrollmentsRootKey = EEDBManager::GetEnrollmentsRootKey();
      v3 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s\\%s", EnrollmentsRootKey, L"Context", v15);
      if ( v3 >= 0 )
      {
        v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0xF003Fu, &phkResult);
        if ( v5 == 2 )
          v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
        v6 = v5 <= 0;
        if ( v5
          || (wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
                &hKey,
                phkResult),
              *(_DWORD *)Data = *((_DWORD *)a2 + 8),
              v5 = RegSetValueExW(hKey, L"ActivityType", 0, 4u, Data, 4u),
              v6 = v5 <= 0,
              v5) )
        {
          if ( v6 )
            v3 = v5;
          else
            v3 = (unsigned __int16)v5 | 0x80070000;
        }
        else
        {
          *(_DWORD *)v11 = *((_DWORD *)a2 + 242);
          RegSetValueExW(hKey, L"AttemptCounter", 0, 4u, v11, 4u);
          *(_DWORD *)v12 = *((_DWORD *)a2 + 108);
          RegSetValueExW(hKey, L"Rollback", 0, 4u, v12, 4u);
          if ( a2 != (struct ActivityContext *)-448LL )
            v3 = WriteStringToRegistry(hKey, L"OrchestratorType", (const unsigned __int16 *)a2 + 224);
          v7 = (&off_18001C088)[2 * *(int *)Data];
          if ( v7 )
            WriteStringToRegistry(hKey, L"ActivityTypeName", v7);
        }
      }
    }
  }
  else
  {
    v3 = -2147418113;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000ffa0  push    rbp
0x18000ffa2  push    rsi
0x18000ffa3  push    rdi
0x18000ffa4  push    r15
0x18000ffa6  lea     rbp, [rsp-238h]
0x18000ffae  sub     rsp, 338h
0x18000ffb5  mov     rax, cs:__security_cookie
0x18000ffbc  xor     rax, rsp
0x18000ffbf  mov     [rbp+250h+var_30], rax
0x18000ffc6  xor     eax, eax
0x18000ffc8  mov     dword ptr [rsp+350h+Data], 20h ; ' '
0x18000ffd0  mov     rsi, rdx
0x18000ffd3  mov     dword ptr [rsp+350h+var_2F0], 0
0x18000ffdb  lea     rcx, [rdx+8]; rguid
0x18000ffdf  mov     dword ptr [rsp+350h+var_2EC], 0
0x18000ffe7  lea     rdx, [rsp+350h+sz]; lpsz
0x18000ffec  mov     [rsp+350h+hKey], 0
0x18000fff5  lea     r8d, [rax+27h]; cchMax
0x18000fff9  mov     [rsp+350h+var_2E8], 0
0x180010002  mov     [rbp+250h+SubKey], ax
0x180010006  mov     [rbp+250h+var_290], ax
0x18001000a  mov     [rsp+350h+sz], ax
0x18001000f  call    cs:__imp_StringFromGUID2
0x180010015  cmp     eax, 27h ; '''
0x180010018  jz      short loc_180010024
0x18001001a  mov     edi, 8000FFFFh
0x18001001f  jmp     loc_1800101EF
0x180010024  lea     rdx, [rbp+250h+var_290]; unsigned __int16 *
0x180010028  lea     rcx, [rsp+350h+sz]; unsigned __int16 *
0x18001002d  call    ?EEDBTrimGuidBracket@@YAJPEBGPEAG@Z; EEDBTrimGuidBracket(ushort const *,ushort *)
0x180010032  mov     edi, eax
0x180010034  test    eax, eax
0x180010036  js      loc_1800101EF
0x18001003c  call    ?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ; EEDBManager::GetEnrollmentsRootKey(void)
0x180010041  lea     rcx, [rbp+250h+var_290]
0x180010045  mov     r9, rax
0x180010048  mov     qword ptr [rsp+350h+samDesired], rcx
0x18001004d  lea     r8, aSSS; "%s\\%s\\%s"
0x180010054  lea     rcx, aContext; "Context"
0x18001005b  mov     edx, 104h; unsigned __int64
0x180010060  mov     [rsp+350h+phkResult], rcx
0x180010065  lea     rcx, [rbp+250h+SubKey]; unsigned __int16 *
0x180010069  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001006e  mov     edi, eax
0x180010070  test    eax, eax
0x180010072  js      loc_1800101EF
0x180010078  lea     rax, [rsp+350h+var_2E8]
0x18001007d  mov     r15, 0FFFFFFFF80000002h
0x180010084  mov     rcx, r15; hKey
0x180010087  mov     [rsp+350h+phkResult], rax; phkResult
0x18001008c  mov     r9d, 0F003Fh; samDesired
0x180010092  lea     rdx, [rbp+250h+SubKey]; lpSubKey
0x180010096  xor     r8d, r8d; ulOptions
0x180010099  call    cs:__imp_RegOpenKeyExW
0x18001009f  cmp     eax, 2
0x1800100a2  jnz     short loc_1800100E3
0x1800100a4  mov     [rsp+350h+lpdwDisposition], 0; lpdwDisposition
0x1800100ad  lea     rax, [rsp+350h+var_2E8]
0x1800100b2  mov     [rsp+350h+var_318], rax; phkResult
0x1800100b7  lea     rdx, [rbp+250h+SubKey]; lpSubKey
0x1800100bb  mov     [rsp+350h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800100c4  xor     r9d, r9d; lpClass
0x1800100c7  mov     [rsp+350h+samDesired], 0F003Fh; samDesired
0x1800100cf  xor     r8d, r8d; Reserved
0x1800100d2  mov     rcx, r15; hKey
0x1800100d5  mov     dword ptr [rsp+350h+phkResult], 0; dwOptions
0x1800100dd  call    cs:__imp_RegCreateKeyExW
0x1800100e3  test    eax, eax
0x1800100e5  jz      short loc_1800100FE
0x1800100e7  jg      short loc_1800100F0
0x1800100e9  mov     edi, eax
0x1800100eb  jmp     loc_1800101EF
0x1800100f0  movzx   edi, ax
0x1800100f3  or      edi, 80070000h
0x1800100f9  jmp     loc_1800101EF
0x1800100fe  mov     rdx, [rsp+350h+var_2E8]
0x180010103  lea     rcx, [rsp+350h+hKey]
0x180010108  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001010d  mov     eax, [rsi+20h]
0x180010110  lea     rdx, aActivitytype; "ActivityType"
0x180010117  mov     rcx, [rsp+350h+hKey]; hKey
0x18001011c  mov     r15d, 4
0x180010122  mov     dword ptr [rsp+350h+Data], eax
0x180010126  mov     r9d, r15d; dwType
0x180010129  lea     rax, [rsp+350h+Data]
0x18001012e  mov     [rsp+350h+samDesired], r15d; cbData
0x180010133  xor     r8d, r8d; Reserved
0x180010136  mov     [rsp+350h+phkResult], rax; lpData
0x18001013b  call    cs:__imp_RegSetValueExW
0x180010141  test    eax, eax
0x180010143  jnz     short loc_1800100E7
0x180010145  mov     eax, [rsi+3C8h]
0x18001014b  lea     rdx, aAttemptcounter; "AttemptCounter"
0x180010152  mov     rcx, [rsp+350h+hKey]; hKey
0x180010157  mov     r9d, r15d; dwType
0x18001015a  mov     dword ptr [rsp+350h+var_2F0], eax
0x18001015e  xor     r8d, r8d; Reserved
0x180010161  lea     rax, [rsp+350h+var_2F0]
0x180010166  mov     [rsp+350h+samDesired], r15d; cbData
0x18001016b  mov     [rsp+350h+phkResult], rax; lpData
0x180010170  call    cs:__imp_RegSetValueExW
0x180010176  mov     eax, [rsi+1B0h]
0x18001017c  lea     rdx, aRollback; "Rollback"
0x180010183  mov     rcx, [rsp+350h+hKey]; hKey
0x180010188  mov     r9d, r15d; dwType
0x18001018b  mov     dword ptr [rsp+350h+var_2EC], eax
0x18001018f  xor     r8d, r8d; Reserved
0x180010192  lea     rax, [rsp+350h+var_2EC]
0x180010197  mov     [rsp+350h+samDesired], r15d; cbData
0x18001019c  mov     [rsp+350h+phkResult], rax; lpData
0x1800101a1  call    cs:__imp_RegSetValueExW
0x1800101a7  lea     r8, [rsi+1C0h]; unsigned __int16 *
0x1800101ae  test    r8, r8
0x1800101b1  jz      short loc_1800101C6
0x1800101b3  mov     rcx, [rsp+350h+hKey]; hKey
0x1800101b8  lea     rdx, aOrchestratorty; "OrchestratorType"
0x1800101bf  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x1800101c4  mov     edi, eax
0x1800101c6  movsxd  rax, dword ptr [rsp+350h+Data]
0x1800101cb  lea     r8, off_18001C088; "AT_MDM_RENEWAL_DISCOVERY"
0x1800101d2  add     rax, rax
0x1800101d5  mov     r8, [r8+rax*8]; unsigned __int16 *
0x1800101d9  test    r8, r8
0x1800101dc  jz      short loc_1800101EF
0x1800101de  mov     rcx, [rsp+350h+hKey]; hKey
0x1800101e3  lea     rdx, aActivitytypena; "ActivityTypeName"
0x1800101ea  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x1800101ef  lea     rcx, [rsp+350h+hKey]
0x1800101f4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800101f9  mov     eax, edi
0x1800101fb  mov     rcx, [rbp+250h+var_30]
0x180010202  xor     rcx, rsp; StackCookie
0x180010205  call    __security_check_cookie
0x18001020a  add     rsp, 338h
0x180010211  pop     r15
0x180010213  pop     rdi
0x180010214  pop     rsi
0x180010215  pop     rbp
0x180010216  retn
```
