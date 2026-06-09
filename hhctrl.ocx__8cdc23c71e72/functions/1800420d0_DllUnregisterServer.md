# DllUnregisterServer

- ea: `0x1800420d0`
- end: `0x180042293`
- name: `DllUnregisterServer`
- size: `451`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18003f8d4`
- `0x1800411a0`
- `0x180041290`
- `0x1800414e4`
- `0x1800420d0`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180042182`
- `ADVAPI32!RegCloseKey` at `0x1800421fa`
- `ADVAPI32!RegCloseKey` at `0x180042182`
- `ADVAPI32!RegCloseKey` at `0x1800421fa`
- `ADVAPI32!RegDeleteKeyA` at `0x180042151`
- `ADVAPI32!RegDeleteKeyA` at `0x180042178`
- `ADVAPI32!RegDeleteKeyA` at `0x1800421f0`
- `ADVAPI32!RegDeleteKeyA` at `0x180042151`
- `ADVAPI32!RegDeleteKeyA` at `0x180042178`
- `ADVAPI32!RegDeleteKeyA` at `0x1800421f0`
- `ADVAPI32!RegCreateKeyExA` at `0x1800421df`
- `ADVAPI32!RegCreateKeyExA` at `0x1800421df`
- `ADVAPI32!RegOpenKeyExA` at `0x18004211f`
- `ADVAPI32!RegOpenKeyExA` at `0x18004211f`

## string_xrefs

- `0x18004210e`: `Software\Microsoft\Internet Explorer\ActiveX Compatibility\`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  unsigned __int64 v0; // r8
  unsigned __int64 v1; // r8
  HRESULT result; // eax
  HRESULT v3; // edi
  __int64 v4; // rbx
  __int64 (*v5)(void); // rax
  __int64 (*v6)(void); // rax
  const struct ATL::_ATL_CATMAP_ENTRY *v7; // rax
  HKEY hKey; // [rsp+50h] [rbp+7h] BYREF
  HKEY v9; // [rsp+58h] [rbp+Fh] BYREF
  struct _GUID v10; // [rsp+60h] [rbp+17h] BYREF
  CHAR SubKey[40]; // [rsp+70h] [rbp+27h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExA(
          HKEY_LOCAL_MACHINE,
          "Software\\Microsoft\\Internet Explorer\\ActiveX Compatibility\\",
          0,
          0xF003Fu,
          &hKey)
    && hKey )
  {
    v10 = CLSID_OldHHCtrl1;
    StringFromGuidA(&v10, SubKey, v0);
    RegDeleteKeyA(hKey, SubKey);
    v10 = CLSID_OldHHCtrl2;
    StringFromGuidA(&v10, SubKey, v1);
    RegDeleteKeyA(hKey, SubKey);
    RegCloseKey(hKey);
  }
  result = UnregisterAllObjects();
  if ( result >= 0 )
  {
    v3 = UnregisterData();
    v9 = 0;
    RegCreateKeyExA(
      HKEY_LOCAL_MACHINE,
      "Software\\Microsoft\\Windows\\ITStorage\\Finders",
      0,
      0,
      0,
      0xF003Fu,
      0,
      &v9,
      0);
    RegDeleteKeyA(v9, ".chm");
    RegCloseKey(v9);
    v4 = qword_18008B3E0;
    if ( qword_18008B3E0 )
    {
      while ( 1 )
      {
        if ( !*(_QWORD *)v4 )
          return v3;
        v5 = *(__int64 (**)(void))(v4 + 48);
        if ( !v5 || !v5() )
        {
          (*(void (__fastcall **)(_QWORD))(v4 + 8))(0);
          if ( _Module == 248 )
          {
            v6 = *(__int64 (**)(void))(v4 + 56);
            if ( !v6 )
              goto LABEL_14;
            v7 = (const struct ATL::_ATL_CATMAP_ENTRY *)v6();
            ATL::AtlRegisterClassCategoriesHelper(*(const struct _GUID **)v4, v7, 0);
          }
        }
        if ( _Module == 176 )
          v4 += 56;
        else
LABEL_14:
          v4 += 72;
      }
    }
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x1800420d0  mov     [rsp-8+arg_0], rbx
0x1800420d5  mov     [rsp-8+arg_8], rdi
0x1800420da  push    rbp
0x1800420db  lea     rbp, [rsp-57h]
0x1800420e0  sub     rsp, 0A0h
0x1800420e7  mov     rax, cs:__security_cookie
0x1800420ee  xor     rax, rsp
0x1800420f1  mov     [rbp+57h+var_8], rax
0x1800420f5  lea     rax, [rbp+57h+hKey]
0x1800420f9  mov     [rbp+57h+hKey], 0
0x180042101  mov     ebx, 0F003Fh
0x180042106  mov     [rsp+0A0h+phkResult], rax; phkResult
0x18004210b  mov     r9d, ebx; samDesired
0x18004210e  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Internet Explorer"...
0x180042115  xor     r8d, r8d; ulOptions
0x180042118  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004211f  call    cs:__imp_RegOpenKeyExA
0x180042125  test    eax, eax
0x180042127  jnz     short loc_180042188
0x180042129  cmp     [rbp+57h+hKey], 0
0x18004212e  jz      short loc_180042188
0x180042130  movups  xmm0, xmmword ptr cs:CLSID_OldHHCtrl1.Data1
0x180042137  lea     rdx, [rbp+57h+SubKey]; char *
0x18004213b  lea     rcx, [rbp+57h+var_40]; struct _GUID
0x18004213f  movdqu  xmmword ptr [rbp+57h+var_40.Data1], xmm0
0x180042144  call    ?StringFromGuidA@@YAHU_GUID@@PEAD_K@Z; StringFromGuidA(_GUID,char *,unsigned __int64)
0x180042149  mov     rcx, [rbp+57h+hKey]; hKey
0x18004214d  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180042151  call    cs:__imp_RegDeleteKeyA
0x180042157  movups  xmm0, xmmword ptr cs:CLSID_OldHHCtrl2.Data1
0x18004215e  lea     rdx, [rbp+57h+SubKey]; char *
0x180042162  lea     rcx, [rbp+57h+var_40]; struct _GUID
0x180042166  movdqu  xmmword ptr [rbp+57h+var_40.Data1], xmm0
0x18004216b  call    ?StringFromGuidA@@YAHU_GUID@@PEAD_K@Z; StringFromGuidA(_GUID,char *,unsigned __int64)
0x180042170  mov     rcx, [rbp+57h+hKey]; hKey
0x180042174  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180042178  call    cs:__imp_RegDeleteKeyA
0x18004217e  mov     rcx, [rbp+57h+hKey]; hKey
0x180042182  call    cs:__imp_RegCloseKey
0x180042188  call    ?UnregisterAllObjects@@YAJXZ; UnregisterAllObjects(void)
0x18004218d  test    eax, eax
0x18004218f  js      loc_180042272
0x180042195  call    ?UnregisterData@@YAJXZ; UnregisterData(void)
0x18004219a  mov     [rsp+0A0h+lpdwDisposition], 0; lpdwDisposition
0x1800421a3  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\ITStorage"...
0x1800421aa  mov     edi, eax
0x1800421ac  mov     [rbp+57h+var_48], 0
0x1800421b4  lea     rax, [rbp+57h+var_48]
0x1800421b8  xor     r9d, r9d; lpClass
0x1800421bb  mov     [rsp+0A0h+var_68], rax; phkResult
0x1800421c0  xor     r8d, r8d; Reserved
0x1800421c3  mov     [rsp+0A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800421cc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800421d3  mov     [rsp+0A0h+samDesired], ebx; samDesired
0x1800421d7  mov     dword ptr [rsp+0A0h+phkResult], 0; dwOptions
0x1800421df  call    cs:__imp_RegCreateKeyExA
0x1800421e5  mov     rcx, [rbp+57h+var_48]; hKey
0x1800421e9  lea     rdx, aChm_0; ".chm"
0x1800421f0  call    cs:__imp_RegDeleteKeyA
0x1800421f6  mov     rcx, [rbp+57h+var_48]; hKey
0x1800421fa  call    cs:__imp_RegCloseKey
0x180042200  mov     rbx, cs:qword_18008B3E0
0x180042207  test    rbx, rbx
0x18004220a  jz      short loc_180042270
0x18004220c  jmp     short loc_18004226A
0x18004220e  mov     rax, [rbx+30h]
0x180042212  test    rax, rax
0x180042215  jz      short loc_180042221
0x180042217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004221c  test    rax, rax
0x18004221f  jnz     short loc_180042254
0x180042221  mov     rax, [rbx+8]
0x180042225  xor     ecx, ecx
0x180042227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004222c  cmp     cs:?_Module@@3VCHtmlHelpModule@@A, 0F8h; CHtmlHelpModule _Module
0x180042236  jnz     short loc_180042254
0x180042238  mov     rax, [rbx+38h]
0x18004223c  test    rax, rax
0x18004223f  jz      short loc_180042266
0x180042241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042246  mov     rcx, [rbx]; struct _GUID *
0x180042249  xor     r8d, r8d; int
0x18004224c  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18004224f  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180042254  cmp     cs:?_Module@@3VCHtmlHelpModule@@A, 0B0h; CHtmlHelpModule _Module
0x18004225e  jnz     short loc_180042266
0x180042260  add     rbx, 38h ; '8'
0x180042264  jmp     short loc_18004226A
0x180042266  add     rbx, 48h ; 'H'
0x18004226a  cmp     qword ptr [rbx], 0
0x18004226e  jnz     short loc_18004220E
0x180042270  mov     eax, edi
0x180042272  mov     rcx, [rbp+57h+var_8]
0x180042276  xor     rcx, rsp; StackCookie
0x180042279  call    __security_check_cookie
0x18004227e  lea     r11, [rsp+0A0h+var_s0]
0x180042286  mov     rbx, [r11+10h]
0x18004228a  mov     rdi, [r11+18h]
0x18004228e  mov     rsp, r11
0x180042291  pop     rbp
0x180042292  retn
```
