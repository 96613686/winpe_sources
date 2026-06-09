# RemovePathFromInProcServerEntry

- ea: `0x180005dbc`
- end: `0x18000606e`
- name: `RemovePathFromInProcServerEntry`
- size: `690`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006840`

## callees

- `0x180002c40`
- `0x180004240`
- `0x180005dbc`
- `0x180006118`
- `0x180008f5c`
- `0x180009054`
- `0x18000931c`
- `0x18000a582`
- `0x18000a5b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000601c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000601c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005ebe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005ebe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006048`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006048`
- `KERNEL32!GetVersionExW` at `0x180005fe7`
- `KERNEL32!GetVersionExW` at `0x180005fe7`
- `ole32!StringFromCLSID` at `0x180005df2`
- `ole32!StringFromCLSID` at `0x180005df2`
- `ole32!CoTaskMemFree` at `0x180005e92`
- `ole32!CoTaskMemFree` at `0x180005e92`

## string_xrefs

- `0x180005e13`: `CLSID\`
- `0x180005ee4`: `mmcshext.dll`

## pseudocode

```c
void __fastcall RemovePathFromInProcServerEntry(const IID *a1)
{
  const unsigned __int16 *v1; // r8
  __int64 v2; // rcx
  const wchar_t *v3; // r9
  unsigned __int64 v4; // rdx
  WCHAR *v5; // rax
  WCHAR *v6; // rcx
  unsigned __int64 v7; // rdx
  HKEY v8; // rbx
  int v9; // eax
  int AbsoluteModulePath; // eax
  int v11; // eax
  LPOLESTR lpsz; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  void **v14; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *lpData; // [rsp+48h] [rbp-B8h]
  __int64 v16; // [rsp+50h] [rbp-B0h]
  int v17; // [rsp+58h] [rbp-A8h]
  _QWORD v18[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+70h] [rbp-90h]
  int v20; // [rsp+78h] [rbp-88h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SubKey[264]; // [rsp+1A0h] [rbp+A0h] BYREF

  lpsz = 0;
  if ( StringFromCLSID(a1, &lpsz) >= 0 )
  {
    v1 = lpsz;
    if ( lpsz )
    {
      v2 = 2147483646;
      v3 = L"CLSID\\";
      v4 = 260;
      v5 = SubKey;
      do
      {
        if ( !v2 )
          break;
        if ( !*v3 )
          break;
        *v5++ = *v3++;
        --v2;
        --v4;
      }
      while ( v4 );
      v6 = v5 - 1;
      if ( v4 )
        v6 = v5;
      *v6 = 0;
      if ( v4 )
      {
        if ( (int)StringCchCatW(SubKey, v4, v1) >= 0 && (int)StringCchCatW(SubKey, v7, L"\\InprocServer32") >= 0 )
        {
          CoTaskMemFree(lpsz);
          hKey = 0;
          if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0xF003Fu, &hKey) )
          {
            v8 = hKey;
            v14 = &CStr::`vftable';
            lpData = (BYTE *)&CStr::s_rgwchEmptyStringBuffer;
            v16 = 0;
            v17 = 0;
            v9 = CStr::Assign((CStr *)&v14, L"mmcshext.dll");
            if ( v9 < 0
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                10,
                WPP_0d5b40d92d823826e0ab8bc5f62745dc_Traceguids,
                (unsigned int)v9);
            }
            v18[0] = &CStr::`vftable';
            v18[1] = &CStr::s_rgwchEmptyStringBuffer;
            v19 = 0;
            v20 = 0;
            AbsoluteModulePath = CModulePath::MakeAbsoluteModulePath((const struct CStr *)&v14, (struct CStr *)v18);
            if ( AbsoluteModulePath < 0
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                11,
                WPP_0d5b40d92d823826e0ab8bc5f62745dc_Traceguids,
                (unsigned int)AbsoluteModulePath);
            }
            if ( (_DWORD)v19 )
            {
              v11 = CStr::Assign((CStr *)&v14, (const struct CStr *)v18);
              if ( v11 < 0
                && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  12,
                  WPP_0d5b40d92d823826e0ab8bc5f62745dc_Traceguids,
                  (unsigned int)v11);
              }
            }
            memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
            VersionInformation.dwOSVersionInfoSize = 276;
            GetVersionExW(&VersionInformation);
            RegSetValueExW(v8, 0, 0, (VersionInformation.dwPlatformId == 2) + 1, lpData, 2 * v16 + 2);
            v18[0] = &CStr::`vftable';
            CStr::Empty((CStr *)v18);
            v14 = &CStr::`vftable';
            CStr::Empty((CStr *)&v14);
            if ( v8 )
              RegCloseKey(v8);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180005dbc  push    rbp
0x180005dbe  push    rbx
0x180005dbf  push    rdi
0x180005dc0  push    r12
0x180005dc2  push    r13
0x180005dc4  push    r14
0x180005dc6  lea     rbp, [rsp-2C8h]
0x180005dce  sub     rsp, 3C8h
0x180005dd5  mov     rax, cs:__security_cookie
0x180005ddc  xor     rax, rsp
0x180005ddf  mov     [rbp+2F0h+var_40], rax
0x180005de6  xor     edi, edi
0x180005de8  lea     rdx, [rsp+3F0h+lpsz]; lplpsz
0x180005ded  mov     [rsp+3F0h+lpsz], rdi
0x180005df2  call    cs:__imp_StringFromCLSID
0x180005df8  test    eax, eax
0x180005dfa  js      loc_18000604E
0x180005e00  mov     r8, [rsp+3F0h+lpsz]; unsigned __int16 *
0x180005e05  test    r8, r8
0x180005e08  jz      loc_18000604E
0x180005e0e  mov     ecx, 7FFFFFFEh
0x180005e13  lea     r9, aClsid; "CLSID\\"
0x180005e1a  mov     edx, 104h
0x180005e1f  lea     rax, [rbp+2F0h+SubKey]
0x180005e26  test    rcx, rcx
0x180005e29  jz      short loc_180005E4A
0x180005e2b  movzx   r10d, word ptr [r9]
0x180005e2f  test    r10w, r10w
0x180005e33  jz      short loc_180005E4A
0x180005e35  mov     [rax], r10w
0x180005e39  add     r9, 2
0x180005e3d  add     rax, 2
0x180005e41  dec     rcx
0x180005e44  sub     rdx, 1; unsigned __int64
0x180005e48  jnz     short loc_180005E26
0x180005e4a  test    rdx, rdx
0x180005e4d  lea     rcx, [rax-2]
0x180005e51  cmovnz  rcx, rax
0x180005e55  mov     [rcx], di
0x180005e58  jz      loc_18000604E
0x180005e5e  lea     rcx, [rbp+2F0h+SubKey]; unsigned __int16 *
0x180005e65  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005e6a  test    eax, eax
0x180005e6c  js      loc_18000604E
0x180005e72  lea     r8, aInprocserver32; "\\InprocServer32"
0x180005e79  lea     rcx, [rbp+2F0h+SubKey]; unsigned __int16 *
0x180005e80  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005e85  test    eax, eax
0x180005e87  js      loc_18000604E
0x180005e8d  mov     rcx, [rsp+3F0h+lpsz]; pv
0x180005e92  call    cs:__imp_CoTaskMemFree
0x180005e98  lea     rax, [rsp+3F0h+hKey]
0x180005e9d  mov     [rsp+3F0h+hKey], rdi
0x180005ea2  mov     r9d, 0F003Fh; samDesired
0x180005ea8  mov     [rsp+3F0h+phkResult], rax; phkResult
0x180005ead  xor     r8d, r8d; ulOptions
0x180005eb0  lea     rdx, [rbp+2F0h+SubKey]; lpSubKey
0x180005eb7  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180005ebe  call    cs:__imp_RegOpenKeyExW
0x180005ec4  test    eax, eax
0x180005ec6  jnz     loc_18000604E
0x180005ecc  mov     rbx, [rsp+3F0h+hKey]
0x180005ed1  lea     r13, ??_7CStr@@6B@; const CStr::`vftable'
0x180005ed8  lea     r12, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x180005edf  mov     [rsp+3F0h+var_3B0], r13
0x180005ee4  lea     rdx, aMmcshextDll_0; "mmcshext.dll"
0x180005eeb  mov     [rsp+3F0h+lpData], r12
0x180005ef0  lea     rcx, [rsp+3F0h+var_3B0]; this
0x180005ef5  mov     [rsp+3F0h+var_3A0], rdi
0x180005efa  mov     [rsp+3F0h+var_398], edi
0x180005efe  call    ?Assign@CStr@@QEAAJPEBG@Z; CStr::Assign(ushort const *)
0x180005f03  lea     r14, WPP_GLOBAL_Control
0x180005f0a  test    eax, eax
0x180005f0c  jns     short loc_180005F38
0x180005f0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f15  cmp     rcx, r14
0x180005f18  jz      short loc_180005F38
0x180005f1a  cmp     byte ptr [rcx+19h], 3
0x180005f1e  jb      short loc_180005F38
0x180005f20  mov     rcx, [rcx+10h]
0x180005f24  lea     r8, WPP_0d5b40d92d823826e0ab8bc5f62745dc_Traceguids
0x180005f2b  mov     edx, 0Ah
0x180005f30  mov     r9d, eax
0x180005f33  call    WPP_SF_d
0x180005f38  lea     rdx, [rsp+3F0h+var_390]; this
0x180005f3d  mov     [rsp+3F0h+var_390], r13
0x180005f42  lea     rcx, [rsp+3F0h+var_3B0]; struct CStr *
0x180005f47  mov     [rsp+3F0h+var_388], r12
0x180005f4c  mov     [rsp+3F0h+var_380], rdi
0x180005f51  mov     [rsp+3F0h+var_378], edi
0x180005f55  call    ?MakeAbsoluteModulePath@CModulePath@@SAJAEBVCStr@@AEAV2@@Z; CModulePath::MakeAbsoluteModulePath(CStr const &,CStr &)
0x180005f5a  test    eax, eax
0x180005f5c  jns     short loc_180005F88
0x180005f5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f65  cmp     rcx, r14
0x180005f68  jz      short loc_180005F88
0x180005f6a  cmp     byte ptr [rcx+19h], 3
0x180005f6e  jb      short loc_180005F88
0x180005f70  mov     rcx, [rcx+10h]
0x180005f74  lea     r8, WPP_0d5b40d92d823826e0ab8bc5f62745dc_Traceguids
0x180005f7b  mov     edx, 0Bh
0x180005f80  mov     r9d, eax
0x180005f83  call    WPP_SF_d
0x180005f88  cmp     dword ptr [rsp+3F0h+var_380], edi
0x180005f8c  jbe     short loc_180005FCB
0x180005f8e  lea     rdx, [rsp+3F0h+var_390]; struct CStr *
0x180005f93  lea     rcx, [rsp+3F0h+var_3B0]; this
0x180005f98  call    ?Assign@CStr@@QEAAJAEBV1@@Z; CStr::Assign(CStr const &)
0x180005f9d  test    eax, eax
0x180005f9f  jns     short loc_180005FCB
0x180005fa1  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fa8  cmp     rcx, r14
0x180005fab  jz      short loc_180005FCB
0x180005fad  cmp     byte ptr [rcx+19h], 3
0x180005fb1  jb      short loc_180005FCB
0x180005fb3  mov     rcx, [rcx+10h]
0x180005fb7  lea     r8, WPP_0d5b40d92d823826e0ab8bc5f62745dc_Traceguids
0x180005fbe  mov     edx, 0Ch
0x180005fc3  mov     r9d, eax
0x180005fc6  call    WPP_SF_d
0x180005fcb  xor     edx, edx; Val
0x180005fcd  lea     rcx, [rbp+2F0h+VersionInformation.dwMajorVersion]; void *
0x180005fd1  mov     r8d, 110h; Size
0x180005fd7  call    memset_0
0x180005fdc  lea     rcx, [rbp+2F0h+VersionInformation]; lpVersionInformation
0x180005fe0  mov     [rbp+2F0h+VersionInformation.dwOSVersionInfoSize], 114h
0x180005fe7  call    cs:__imp_GetVersionExW
0x180005fed  mov     eax, dword ptr [rsp+3F0h+var_3A0]
0x180005ff1  mov     r9d, edi
0x180005ff4  cmp     [rbp+2F0h+VersionInformation.dwPlatformId], 2
0x180005ff8  mov     rcx, rbx; hKey
0x180005ffb  setz    r9b
0x180005fff  xor     r8d, r8d; Reserved
0x180006002  lea     eax, ds:2[rax*2]
0x180006009  inc     r9d; dwType
0x18000600c  mov     [rsp+3F0h+cbData], eax; cbData
0x180006010  xor     edx, edx; lpValueName
0x180006012  mov     rax, [rsp+3F0h+lpData]
0x180006017  mov     [rsp+3F0h+phkResult], rax; lpData
0x18000601c  call    cs:__imp_RegSetValueExW
0x180006022  lea     rcx, [rsp+3F0h+var_390]; this
0x180006027  mov     [rsp+3F0h+var_390], r13
0x18000602c  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x180006031  lea     rcx, [rsp+3F0h+var_3B0]; this
0x180006036  mov     [rsp+3F0h+var_3B0], r13
0x18000603b  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x180006040  test    rbx, rbx
0x180006043  jz      short loc_18000604E
0x180006045  mov     rcx, rbx; hKey
0x180006048  call    cs:__imp_RegCloseKey
0x18000604e  mov     rcx, [rbp+2F0h+var_40]
0x180006055  xor     rcx, rsp; StackCookie
0x180006058  call    __security_check_cookie
0x18000605d  add     rsp, 3C8h
0x180006064  pop     r14
0x180006066  pop     r13
0x180006068  pop     r12
0x18000606a  pop     rdi
0x18000606b  pop     rbx
0x18000606c  pop     rbp
0x18000606d  retn
```
