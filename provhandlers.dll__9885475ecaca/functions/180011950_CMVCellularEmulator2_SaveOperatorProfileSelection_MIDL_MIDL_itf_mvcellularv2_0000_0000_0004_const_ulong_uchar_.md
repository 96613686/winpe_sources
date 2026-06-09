# CMVCellularEmulator2::SaveOperatorProfileSelection(__MIDL___MIDL_itf_mvcellularv2_0000_0000_0004 const *,ulong,uchar const *)

- ea: `0x180011950`
- end: `0x180011bff`
- name: `?SaveOperatorProfileSelection@CMVCellularEmulator2@@UEAAJPEBU__MIDL___MIDL_itf_mvcellularv2_0000_0000_0004@@KPEBE@Z`
- size: `687`
- prototype: `int(CMVCellularEmulator2 *__hidden this, const struct __MIDL___MIDL_itf_mvcellularv2_0000_0000_0004 *, unsigned int, const unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x1800076a4`
- `0x18001192c`
- `0x180011950`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011a09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011a83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011a96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011bac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011bc0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011bd0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011be3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011a09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011a83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011a96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011bac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011bc0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011bd0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011be3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011b57`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011b57`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800119d4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011a51`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011ad7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800119d4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011a51`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011ad7`

## pseudocode

```c
__int64 __fastcall CMVCellularEmulator2::SaveOperatorProfileSelection(
        CMVCellularEmulator2 *this,
        const WCHAR *a2,
        DWORD a3,
        const unsigned __int8 *a4)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  unsigned int v12; // eax
  unsigned int v13; // ebx
  unsigned int v14; // eax
  unsigned int v15; // ebx
  int dwOptions; // [rsp+20h] [rbp-68h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-68h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-68h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-68h]
  unsigned int dwOptionsd; // [rsp+20h] [rbp-68h]
  HKEY phkResult; // [rsp+50h] [rbp-38h] BYREF
  HKEY v22; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  HKEY hKey; // [rsp+90h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 2) )
  {
    hKey = 0;
    v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, gc_wszRegCellularEmulator, 0, 0, 0, 0x20006u, 0, &hKey, 0);
    if ( v8 )
    {
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x14C,
             (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
             (const char *)v8,
             dwOptionsa);
      if ( hKey )
        RegCloseKey(hKey);
      return v9;
    }
    else
    {
      phkResult = 0;
      v10 = RegCreateKeyExW(hKey, L"Datastore", 0, 0, 0, 0x20006u, 0, &phkResult, 0);
      if ( v10 )
      {
        v11 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x150,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
                (const char *)v10,
                dwOptionsb);
        if ( phkResult )
          RegCloseKey(phkResult);
        if ( hKey )
          RegCloseKey(hKey);
        return v11;
      }
      else
      {
        v22 = 0;
        v12 = RegCreateKeyExW(phkResult, a2, 0, 0, 0, 2u, 0, &v22, 0);
        if ( v12 )
        {
          v13 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x155,
                  (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
                  (const char *)v12,
                  dwOptionsc);
          if ( v22 )
            RegCloseKey(v22);
          if ( phkResult )
            RegCloseKey(phkResult);
          if ( hKey )
            RegCloseKey(hKey);
          return v13;
        }
        else
        {
          v14 = RegSetValueExW(v22, L"ProfileSelection", 0, 3u, a4, a3);
          if ( v14 )
          {
            v15 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x158,
                    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
                    (const char *)v14,
                    dwOptionsd);
            if ( v22 )
              RegCloseKey(v22);
            if ( phkResult )
              RegCloseKey(phkResult);
            if ( hKey )
              RegCloseKey(hKey);
            return v15;
          }
          else
          {
            if ( v22 )
              RegCloseKey(v22);
            if ( phkResult )
              RegCloseKey(phkResult);
            if ( hKey )
              RegCloseKey(hKey);
            return 0;
          }
        }
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
      (const char *)0x8007139FLL,
      dwOptions);
    return 2147947423LL;
  }
}

```

## disassembly

```asm
0x180011950  push    rbx
0x180011952  push    rsi
0x180011953  push    rdi
0x180011954  push    r14
0x180011956  sub     rsp, 68h
0x18001195a  mov     rbx, r9
0x18001195d  mov     edi, r8d
0x180011960  mov     rsi, rdx
0x180011963  xor     r14d, r14d
0x180011966  cmp     [rcx+10h], r14
0x18001196a  jnz     short loc_180011994
0x18001196c  mov     rcx, [rsp+88h]; this
0x180011974  mov     ebx, 8007139Fh
0x180011979  mov     r9d, ebx; char *
0x18001197c  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180011983  mov     edx, 147h; void *
0x180011988  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001198d  mov     eax, ebx
0x18001198f  jmp     loc_180011BF4
0x180011994  mov     [rsp+88h+hKey], r14
0x18001199c  mov     [rsp+88h+lpdwDisposition], r14; lpdwDisposition
0x1800119a1  lea     rax, [rsp+88h+hKey]
0x1800119a9  mov     [rsp+88h+phkResult], rax; phkResult
0x1800119ae  mov     [rsp+88h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800119b3  mov     [rsp+88h+samDesired], 20006h; samDesired
0x1800119bb  mov     [rsp+88h+dwOptions], r14d; unsigned int
0x1800119c0  xor     r9d, r9d; lpClass
0x1800119c3  xor     r8d, r8d; Reserved
0x1800119c6  mov     rdx, cs:?gc_wszRegCellularEmulator@@3PEBGEB; lpSubKey
0x1800119cd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800119d4  call    cs:__imp_RegCreateKeyExW
0x1800119da  test    eax, eax
0x1800119dc  jz      short loc_180011A16
0x1800119de  mov     rcx, [rsp+88h]; this
0x1800119e6  mov     r9d, eax; char *
0x1800119e9  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800119f0  mov     edx, 14Ch; void *
0x1800119f5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800119fa  mov     ebx, eax
0x1800119fc  mov     rcx, [rsp+88h+hKey]; hKey
0x180011a04  test    rcx, rcx
0x180011a07  jz      short loc_180011A0F
0x180011a09  call    cs:__imp_RegCloseKey
0x180011a0f  mov     eax, ebx
0x180011a11  jmp     loc_180011BF4
0x180011a16  mov     [rsp+88h+var_38], r14
0x180011a1b  mov     [rsp+88h+lpdwDisposition], r14; lpdwDisposition
0x180011a20  lea     rax, [rsp+88h+var_38]
0x180011a25  mov     [rsp+88h+phkResult], rax; phkResult
0x180011a2a  mov     [rsp+88h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180011a2f  mov     [rsp+88h+samDesired], 20006h; samDesired
0x180011a37  mov     [rsp+88h+dwOptions], r14d; unsigned int
0x180011a3c  xor     r9d, r9d; lpClass
0x180011a3f  xor     r8d, r8d; Reserved
0x180011a42  lea     rdx, ?c_datastoreKeyName@@3QBGB; "Datastore"
0x180011a49  mov     rcx, [rsp+88h+hKey]; hKey
0x180011a51  call    cs:__imp_RegCreateKeyExW
0x180011a57  test    eax, eax
0x180011a59  jz      short loc_180011AA3
0x180011a5b  mov     rcx, [rsp+88h]; this
0x180011a63  mov     r9d, eax; char *
0x180011a66  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180011a6d  mov     edx, 150h; void *
0x180011a72  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180011a77  mov     ebx, eax
0x180011a79  mov     rcx, [rsp+88h+var_38]; hKey
0x180011a7e  test    rcx, rcx
0x180011a81  jz      short loc_180011A89
0x180011a83  call    cs:__imp_RegCloseKey
0x180011a89  mov     rcx, [rsp+88h+hKey]; hKey
0x180011a91  test    rcx, rcx
0x180011a94  jz      short loc_180011A9C
0x180011a96  call    cs:__imp_RegCloseKey
0x180011a9c  mov     eax, ebx
0x180011a9e  jmp     loc_180011BF4
0x180011aa3  mov     [rsp+88h+var_30], r14
0x180011aa8  mov     [rsp+88h+lpdwDisposition], r14; lpdwDisposition
0x180011aad  lea     rax, [rsp+88h+var_30]
0x180011ab2  mov     [rsp+88h+phkResult], rax; phkResult
0x180011ab7  mov     [rsp+88h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180011abc  mov     [rsp+88h+samDesired], 2; samDesired
0x180011ac4  mov     [rsp+88h+dwOptions], r14d; unsigned int
0x180011ac9  xor     r9d, r9d; lpClass
0x180011acc  xor     r8d, r8d; Reserved
0x180011acf  mov     rdx, rsi; lpSubKey
0x180011ad2  mov     rcx, [rsp+88h+var_38]; hKey
0x180011ad7  call    cs:__imp_RegCreateKeyExW
0x180011add  test    eax, eax
0x180011adf  jz      short loc_180011B39
0x180011ae1  mov     rcx, [rsp+88h]; this
0x180011ae9  mov     r9d, eax; char *
0x180011aec  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180011af3  mov     edx, 155h; void *
0x180011af8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180011afd  mov     ebx, eax
0x180011aff  mov     rcx, [rsp+88h+var_30]; hKey
0x180011b04  test    rcx, rcx
0x180011b07  jz      short loc_180011B0F
0x180011b09  call    cs:__imp_RegCloseKey
0x180011b0f  mov     rcx, [rsp+88h+var_38]; hKey
0x180011b14  test    rcx, rcx
0x180011b17  jz      short loc_180011B1F
0x180011b19  call    cs:__imp_RegCloseKey
0x180011b1f  mov     rcx, [rsp+88h+hKey]; hKey
0x180011b27  test    rcx, rcx
0x180011b2a  jz      short loc_180011B32
0x180011b2c  call    cs:__imp_RegCloseKey
0x180011b32  mov     eax, ebx
0x180011b34  jmp     loc_180011BF4
0x180011b39  mov     [rsp+88h+samDesired], edi; cbData
0x180011b3d  mov     qword ptr [rsp+88h+dwOptions], rbx; unsigned int
0x180011b42  mov     r9d, 3; dwType
0x180011b48  xor     r8d, r8d; Reserved
0x180011b4b  lea     rdx, ?gc_wszProfileSelection@@3QBGB; "ProfileSelection"
0x180011b52  mov     rcx, [rsp+88h+var_30]; hKey
0x180011b57  call    cs:__imp_RegSetValueExW
0x180011b5d  test    eax, eax
0x180011b5f  jz      short loc_180011BB6
0x180011b61  mov     rcx, [rsp+88h]; this
0x180011b69  mov     r9d, eax; char *
0x180011b6c  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180011b73  mov     edx, 158h; void *
0x180011b78  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180011b7d  mov     ebx, eax
0x180011b7f  mov     rcx, [rsp+88h+var_30]; hKey
0x180011b84  test    rcx, rcx
0x180011b87  jz      short loc_180011B8F
0x180011b89  call    cs:__imp_RegCloseKey
0x180011b8f  mov     rcx, [rsp+88h+var_38]; hKey
0x180011b94  test    rcx, rcx
0x180011b97  jz      short loc_180011B9F
0x180011b99  call    cs:__imp_RegCloseKey
0x180011b9f  mov     rcx, [rsp+88h+hKey]; hKey
0x180011ba7  test    rcx, rcx
0x180011baa  jz      short loc_180011BB2
0x180011bac  call    cs:__imp_RegCloseKey
0x180011bb2  mov     eax, ebx
0x180011bb4  jmp     short loc_180011BF4
0x180011bb6  mov     rcx, [rsp+88h+var_30]; hKey
0x180011bbb  test    rcx, rcx
0x180011bbe  jz      short loc_180011BC6
0x180011bc0  call    cs:__imp_RegCloseKey
0x180011bc6  mov     rcx, [rsp+88h+var_38]; hKey
0x180011bcb  test    rcx, rcx
0x180011bce  jz      short loc_180011BD6
0x180011bd0  call    cs:__imp_RegCloseKey
0x180011bd6  mov     rcx, [rsp+88h+hKey]; hKey
0x180011bde  test    rcx, rcx
0x180011be1  jz      short loc_180011BE9
0x180011be3  call    cs:__imp_RegCloseKey
0x180011be9  xor     eax, eax
0x180011beb  jmp     short loc_180011BF4
0x180011bed  mov     eax, dword ptr [rsp+88h+hKey]
0x180011bf4  add     rsp, 68h
0x180011bf8  pop     r14
0x180011bfa  pop     rdi
0x180011bfb  pop     rsi
0x180011bfc  pop     rbx
0x180011bfd  retn
```
