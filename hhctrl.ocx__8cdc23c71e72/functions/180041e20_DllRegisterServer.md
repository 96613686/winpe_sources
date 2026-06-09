# DllRegisterServer

- ea: `0x180041e20`
- end: `0x1800420c0`
- name: `DllRegisterServer`
- size: `672`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800029b8`
- `0x18000f830`
- `0x18000f93c`
- `0x18003f4ec`
- `0x18004040c`
- `0x1800408e0`
- `0x180040a4c`
- `0x1800411a0`
- `0x180041e20`
- `0x18004eea0`
- `0x180065384`
- `0x180075c90`

## import_xrefs

- `KERNEL32!GetFileAttributesA` at `0x180041ff5`
- `KERNEL32!GetFileAttributesA` at `0x180041ff5`
- `ADVAPI32!RegCloseKey` at `0x18004208c`
- `ADVAPI32!RegCloseKey` at `0x18004208c`
- `ADVAPI32!RegCreateKeyExA` at `0x180042052`
- `ADVAPI32!RegCreateKeyExA` at `0x180042052`
- `ADVAPI32!RegSetValueExA` at `0x180042081`
- `ADVAPI32!RegSetValueExA` at `0x180042081`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  unsigned __int64 v0; // r8
  unsigned __int64 v1; // r8
  unsigned __int64 v2; // r8
  HRESULT result; // eax
  int v4; // edx
  struct ATL::_ATL_MODULE *v5; // rcx
  const struct _GUID *v6; // r8
  struct _GUID v7; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  char v9[40]; // [rsp+68h] [rbp-98h] BYREF
  char v10[40]; // [rsp+90h] [rbp-70h] BYREF
  char v11[40]; // [rsp+B8h] [rbp-48h] BYREF
  CHAR FileName[272]; // [rsp+E0h] [rbp-20h] BYREF

  v7 = CLSID_OldHHCtrl1;
  StringFromGuidA(&v7, v10, v0);
  v7 = CLSID_OldHHCtrl2;
  StringFromGuidA(&v7, v9, v1);
  v7 = CLSID_HHCtrl;
  StringFromGuidA(&v7, v11, v2);
  if ( !RegisterPhoenixKeys(v10, (const BYTE *)v9) || !RegisterPhoenixKeys(v9, (const BYTE *)v11) )
    return -2147467259;
  result = RegisterAllObjects();
  if ( result >= 0 )
  {
    v7 = (struct _GUID)xmmword_18007F1E0;
    CreateComponentCategory(&v7, L"Controls that are safely scriptable");
    v7 = (struct _GUID)xmmword_18007F1D0;
    CreateComponentCategory(&v7, L"Controls safely initializable from persistent data");
    v7 = (struct _GUID)xmmword_18007F1E0;
    RegisterCLSIDInCategory(&CLSID_HHCtrl, &v7);
    v7 = (struct _GUID)xmmword_18007F1D0;
    RegisterCLSIDInCategory(&CLSID_HHCtrl, &v7);
    v7 = (struct _GUID)xmmword_18007F1E0;
    RegisterCLSIDInCategory(&CLSID_OldHHCtrl1, &v7);
    v7 = (struct _GUID)xmmword_18007F1D0;
    RegisterCLSIDInCategory(&CLSID_OldHHCtrl1, &v7);
    v7 = (struct _GUID)xmmword_18007F1E0;
    RegisterCLSIDInCategory(&CLSID_OldHHCtrl2, &v7);
    v7 = (struct _GUID)xmmword_18007F1D0;
    RegisterCLSIDInCategory(&CLSID_OldHHCtrl2, &v7);
    HHGetWindowsDirectory((LPBYTE)FileName, 0x104u, 0);
    AddTrailingBackslash(FileName, 0x104u);
    StringCchCatA(FileName, 0x104u, "hh.exe");
    if ( GetFileAttributesA(FileName) != -1 )
      RegisterHH(FileName);
    hKey = 0;
    RegCreateKeyExA(
      HKEY_LOCAL_MACHINE,
      "Software\\Microsoft\\Windows\\ITStorage\\Finders",
      0,
      0,
      0,
      0xF003Fu,
      0,
      &hKey,
      0);
    RegSetValueExA(hKey, ".chm", 0, 1u, "{adb880a4-d8ff-11cf-9377-00aa003b7a11}", 0x27u);
    RegCloseKey(hKey);
    ATL::AtlModuleRegisterServer(v5, v4, v6);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180041e20  mov     [rsp-8+arg_0], rbx
0x180041e25  push    rbp
0x180041e26  lea     rbp, [rsp-100h]
0x180041e2e  sub     rsp, 200h
0x180041e35  mov     rax, cs:__security_cookie
0x180041e3c  xor     rax, rsp
0x180041e3f  mov     [rbp+100h+var_10], rax
0x180041e46  movups  xmm0, xmmword ptr cs:CLSID_OldHHCtrl1.Data1
0x180041e4d  lea     rdx, [rbp+100h+var_170]; char *
0x180041e51  lea     rcx, [rsp+200h+var_1B0]; struct _GUID
0x180041e56  movdqu  xmmword ptr [rsp+200h+var_1B0.Data1], xmm0
0x180041e5c  call    ?StringFromGuidA@@YAHU_GUID@@PEAD_K@Z; StringFromGuidA(_GUID,char *,unsigned __int64)
0x180041e61  movups  xmm0, xmmword ptr cs:CLSID_OldHHCtrl2.Data1
0x180041e68  lea     rdx, [rsp+200h+var_198]; char *
0x180041e6d  lea     rcx, [rsp+200h+var_1B0]; struct _GUID
0x180041e72  movdqu  xmmword ptr [rsp+200h+var_1B0.Data1], xmm0
0x180041e78  call    ?StringFromGuidA@@YAHU_GUID@@PEAD_K@Z; StringFromGuidA(_GUID,char *,unsigned __int64)
0x180041e7d  movups  xmm0, xmmword ptr cs:CLSID_HHCtrl.Data1
0x180041e84  lea     rdx, [rbp+100h+var_148]; char *
0x180041e88  lea     rcx, [rsp+200h+var_1B0]; struct _GUID
0x180041e8d  movdqu  xmmword ptr [rsp+200h+var_1B0.Data1], xmm0
0x180041e93  call    ?StringFromGuidA@@YAHU_GUID@@PEAD_K@Z; StringFromGuidA(_GUID,char *,unsigned __int64)
0x180041e98  lea     rdx, [rsp+200h+var_198]; char *
0x180041e9d  lea     rcx, [rbp+100h+var_170]; char *
0x180041ea1  call    ?RegisterPhoenixKeys@@YA_NPEAD0@Z; RegisterPhoenixKeys(char *,char *)
0x180041ea6  test    al, al
0x180041ea8  jz      loc_18004209B
0x180041eae  lea     rdx, [rbp+100h+var_148]; char *
0x180041eb2  lea     rcx, [rsp+200h+var_198]; char *
0x180041eb7  call    ?RegisterPhoenixKeys@@YA_NPEAD0@Z; RegisterPhoenixKeys(char *,char *)
0x180041ebc  test    al, al
0x180041ebe  jz      loc_18004209B
0x180041ec4  call    ?RegisterAllObjects@@YAJXZ; RegisterAllObjects(void)
0x180041ec9  test    eax, eax
0x180041ecb  js      loc_1800420A0
0x180041ed1  movups  xmm0, cs:xmmword_18007F1E0
0x180041ed8  lea     rdx, aControlsThatAr; "Controls that are safely scriptable"
0x180041edf  lea     rcx, [rsp+200h+var_1B0]; struct _GUID
0x180041ee4  movdqu  xmmword ptr [rsp+200h+var_1B0.Data1], xmm0
0x180041eea  call    ?CreateComponentCategory@@YAJU_GUID@@PEBG@Z; CreateComponentCategory(_GUID,ushort const *)
0x180041eef  movups  xmm0, cs:xmmword_18007F1D0
0x180041ef6  lea     rdx, aControlsSafely; "Controls safely initializable from pers"...
0x180041efd  lea     rcx, [rsp+200h+var_1B0]; struct _GUID
0x180041f02  movdqu  xmmword ptr [rsp+200h+var_1B0.Data1], xmm0
0x180041f08  call    ?CreateComponentCategory@@YAJU_GUID@@PEBG@Z; CreateComponentCategory(_GUID,ushort const *)
0x180041f0d  movups  xmm0, cs:xmmword_18007F1E0
0x180041f14  lea     rdx, [rsp+200h+var_1B0]; struct _GUID
0x180041f19  lea     rcx, CLSID_HHCtrl; struct _GUID *
0x180041f20  movdqu  xmmword ptr [rsp+200h+var_1B0.Data1], xmm0
0x180041f26  call    ?RegisterCLSIDInCategory@@YAJAEBU_GUID@@U1@@Z; RegisterCLSIDInCategory(_GUID const &,_GUID)
0x180041f2b  movups  xmm0, cs:xmmword_18007F1D0
0x180041f32  lea     rdx, [rsp+200h+var_1B0]; struct _GUID
0x180041f37  lea     rcx, CLSID_HHCtrl; struct _GUID *
0x180041f3e  movdqu  xmmword ptr [rsp+200h+var_1B0.Data1], xmm0
0x180041f44  call    ?RegisterCLSIDInCategory@@YAJAEBU_GUID@@U1@@Z; RegisterCLSIDInCategory(_GUID const &,_GUID)
0x180041f49  movups  xmm0, cs:xmmword_18007F1E0
0x180041f50  lea     rdx, [rsp+200h+var_1B0]; struct _GUID
0x180041f55  lea     rcx, CLSID_OldHHCtrl1; struct _GUID *
0x180041f5c  movdqu  xmmword ptr [rsp+200h+var_1B0.Data1], xmm0
0x180041f62  call    ?RegisterCLSIDInCategory@@YAJAEBU_GUID@@U1@@Z; RegisterCLSIDInCategory(_GUID const &,_GUID)
0x180041f67  movups  xmm0, cs:xmmword_18007F1D0
0x180041f6e  lea     rdx, [rsp+200h+var_1B0]; struct _GUID
0x180041f73  lea     rcx, CLSID_OldHHCtrl1; struct _GUID *
0x180041f7a  movdqu  xmmword ptr [rsp+200h+var_1B0.Data1], xmm0
0x180041f80  call    ?RegisterCLSIDInCategory@@YAJAEBU_GUID@@U1@@Z; RegisterCLSIDInCategory(_GUID const &,_GUID)
0x180041f85  movups  xmm0, cs:xmmword_18007F1E0
0x180041f8c  lea     rdx, [rsp+200h+var_1B0]; struct _GUID
0x180041f91  lea     rcx, CLSID_OldHHCtrl2; struct _GUID *
0x180041f98  movdqu  xmmword ptr [rsp+200h+var_1B0.Data1], xmm0
0x180041f9e  call    ?RegisterCLSIDInCategory@@YAJAEBU_GUID@@U1@@Z; RegisterCLSIDInCategory(_GUID const &,_GUID)
0x180041fa3  movups  xmm0, cs:xmmword_18007F1D0
0x180041faa  lea     rdx, [rsp+200h+var_1B0]; struct _GUID
0x180041faf  lea     rcx, CLSID_OldHHCtrl2; struct _GUID *
0x180041fb6  movdqu  xmmword ptr [rsp+200h+var_1B0.Data1], xmm0
0x180041fbc  call    ?RegisterCLSIDInCategory@@YAJAEBU_GUID@@U1@@Z; RegisterCLSIDInCategory(_GUID const &,_GUID)
0x180041fc1  mov     ebx, 104h
0x180041fc6  lea     rcx, [rbp+100h+FileName]; lpData
0x180041fca  mov     edx, ebx; unsigned __int64
0x180041fcc  xor     r8d, r8d; unsigned int
0x180041fcf  call    ?HHGetWindowsDirectory@@YAKPEAD_KI@Z; HHGetWindowsDirectory(char *,unsigned __int64,uint)
0x180041fd4  mov     edx, ebx; unsigned __int64
0x180041fd6  lea     rcx, [rbp+100h+FileName]; lpszStart
0x180041fda  call    ?AddTrailingBackslash@@YAXPEAD_K@Z; AddTrailingBackslash(char *,unsigned __int64)
0x180041fdf  lea     r8, aHhExe; "hh.exe"
0x180041fe6  mov     edx, ebx; unsigned __int64
0x180041fe8  lea     rcx, [rbp+100h+FileName]; char *
0x180041fec  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180041ff1  lea     rcx, [rbp+100h+FileName]; lpFileName
0x180041ff5  call    cs:__imp_GetFileAttributesA
0x180041ffb  cmp     eax, 0FFFFFFFFh
0x180041ffe  jz      short loc_180042009
0x180042000  lea     rcx, [rbp+100h+FileName]; char *
0x180042004  call    ?RegisterHH@@YAXPEBD@Z; RegisterHH(char const *)
0x180042009  mov     [rsp+200h+lpdwDisposition], 0; lpdwDisposition
0x180042012  lea     rax, [rsp+200h+hKey]
0x180042017  mov     [rsp+200h+phkResult], rax; phkResult
0x18004201c  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\ITStorage"...
0x180042023  mov     [rsp+200h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18004202c  xor     r9d, r9d; lpClass
0x18004202f  mov     [rsp+200h+samDesired], 0F003Fh; samDesired
0x180042037  xor     r8d, r8d; Reserved
0x18004203a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180042041  mov     [rsp+200h+dwOptions], 0; dwOptions
0x180042049  mov     [rsp+200h+hKey], 0
0x180042052  call    cs:__imp_RegCreateKeyExA
0x180042058  mov     rcx, [rsp+200h+hKey]; hKey
0x18004205d  lea     rax, aAdb880a4D8ff11; "{adb880a4-d8ff-11cf-9377-00aa003b7a11}"
0x180042064  mov     [rsp+200h+samDesired], 27h ; '''; cbData
0x18004206c  lea     rdx, aChm_0; ".chm"
0x180042073  mov     r9d, 1; dwType
0x180042079  mov     qword ptr [rsp+200h+dwOptions], rax; lpData
0x18004207e  xor     r8d, r8d; Reserved
0x180042081  call    cs:__imp_RegSetValueExA
0x180042087  mov     rcx, [rsp+200h+hKey]; hKey
0x18004208c  call    cs:__imp_RegCloseKey
0x180042092  call    ?AtlModuleRegisterServer@ATL@@YAJPEAU_ATL_MODULE@1@HPEBU_GUID@@@Z; ATL::AtlModuleRegisterServer(ATL::_ATL_MODULE *,int,_GUID const *)
0x180042097  xor     eax, eax
0x180042099  jmp     short loc_1800420A0
0x18004209b  mov     eax, 80004005h
0x1800420a0  mov     rcx, [rbp+100h+var_10]
0x1800420a7  xor     rcx, rsp; StackCookie
0x1800420aa  call    __security_check_cookie
0x1800420af  mov     rbx, [rsp+200h+arg_0]
0x1800420b7  add     rsp, 200h
0x1800420be  pop     rbp
0x1800420bf  retn
```
