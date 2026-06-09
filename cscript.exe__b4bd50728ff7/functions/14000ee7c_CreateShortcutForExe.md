# CreateShortcutForExe

- ea: `0x14000ee7c`
- end: `0x14000f084`
- name: `CreateShortcutForExe`
- size: `520`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000f08c`

## callees

- `0x14000c2ec`
- `0x14000ee7c`
- `0x14000f1f4`
- `0x14000f274`
- `0x1400161d0`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x14000eed2`
- `KERNEL32!GetFileAttributesW` at `0x14000eed2`
- `ole32!CoCreateInstance` at `0x14000ef15`
- `ole32!CoCreateInstance` at `0x14000ef15`
- `ole32!PropVariantClear` at `0x14000efcf`
- `ole32!PropVariantClear` at `0x14000efcf`

## pseudocode

```c
__int64 __fastcall CreateShortcutForExe(__int64 a1, __int64 a2, __int64 a3, const unsigned __int16 *a4)
{
  __int64 result; // rax
  HRESULT inited; // ebx
  LPVOID v8; // rbx
  __int64 (__fastcall *v9)(LPVOID, GUID *, __int64 *); // rdi
  LPVOID v10; // rbx
  __int64 (__fastcall *v11)(LPVOID, GUID *, __int64 *); // rdi
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  PROPVARIANT pvar; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF

  result = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", a1, a2);
  if ( (int)result >= 0 )
  {
    if ( GetFileAttributesW(FileName) == -1 )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&ppv);
      inited = CoCreateInstance(&CLSID_ShellLink, 0, 1u, &GUID_000214f9_0000_0000_c000_000000000046, &ppv);
      if ( inited >= 0 )
      {
        inited = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 160LL))(ppv, a3);
        if ( inited >= 0 )
        {
          v8 = ppv;
          v13 = 0;
          v9 = **(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv;
          Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v13);
          inited = v9(v8, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v13);
          if ( inited >= 0 )
          {
            memset(&pvar, 0, sizeof(pvar));
            inited = InitPropVariantFromString(a4, &pvar);
            if ( inited >= 0 )
            {
              inited = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v13 + 48LL))(
                         v13,
                         &PKEY_AppUserModel_ID,
                         &pvar);
              PropVariantClear(&pvar);
              if ( inited >= 0 )
              {
                inited = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 56LL))(v13);
                if ( inited >= 0 )
                {
                  v10 = ppv;
                  v14 = 0;
                  v11 = **(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv;
                  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v14);
                  inited = v11(v10, &GUID_0000010b_0000_0000_c000_000000000046, &v14);
                  if ( inited >= 0 )
                    inited = (*(__int64 (__fastcall **)(__int64, WCHAR *, __int64))(*(_QWORD *)v14 + 48LL))(
                               v14,
                               FileName,
                               1);
                  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v14);
                }
              }
            }
          }
          Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v13);
        }
      }
      Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&ppv);
      return (unsigned int)inited;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000ee7c  push    rbp
0x14000ee7e  push    rbx
0x14000ee7f  push    rsi
0x14000ee80  push    rdi
0x14000ee81  lea     rbp, [rsp-188h]
0x14000ee89  sub     rsp, 288h
0x14000ee90  mov     rax, cs:__security_cookie
0x14000ee97  xor     rax, rsp
0x14000ee9a  mov     [rbp+1A0h+var_30], rax
0x14000eea1  mov     rsi, r9
0x14000eea4  mov     [rsp+2A0h+ppv], rdx
0x14000eea9  mov     r9, rcx
0x14000eeac  mov     rdi, r8
0x14000eeaf  lea     rcx, [rsp+2A0h+FileName]; unsigned __int16 *
0x14000eeb4  mov     edx, 104h; unsigned __int64
0x14000eeb9  lea     r8, aSS; "%s\\%s"
0x14000eec0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000eec5  test    eax, eax
0x14000eec7  js      loc_14000F069
0x14000eecd  lea     rcx, [rsp+2A0h+FileName]; lpFileName
0x14000eed2  call    cs:__imp_GetFileAttributesW
0x14000eed8  cmp     eax, 0FFFFFFFFh
0x14000eedb  jz      short loc_14000EEE4
0x14000eedd  xor     eax, eax
0x14000eedf  jmp     loc_14000F069
0x14000eee4  lea     rcx, [rsp+2A0h+var_270]
0x14000eee9  mov     [rsp+2A0h+var_270], 0
0x14000eef2  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x14000eef7  xor     edx, edx; pUnkOuter
0x14000eef9  lea     rax, [rsp+2A0h+var_270]
0x14000eefe  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046; riid
0x14000ef05  mov     [rsp+2A0h+ppv], rax; ppv
0x14000ef0a  lea     rcx, CLSID_ShellLink; rclsid
0x14000ef11  lea     r8d, [rdx+1]; dwClsContext
0x14000ef15  call    cs:__imp_CoCreateInstance
0x14000ef1b  mov     ebx, eax
0x14000ef1d  test    eax, eax
0x14000ef1f  js      loc_14000F05D
0x14000ef25  mov     rcx, [rsp+2A0h+var_270]
0x14000ef2a  mov     rdx, rdi
0x14000ef2d  mov     rax, [rcx]
0x14000ef30  mov     rax, [rax+0A0h]
0x14000ef37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ef3c  mov     ebx, eax
0x14000ef3e  test    eax, eax
0x14000ef40  js      loc_14000F05D
0x14000ef46  mov     rbx, [rsp+2A0h+var_270]
0x14000ef4b  lea     rcx, [rsp+2A0h+var_268]
0x14000ef50  mov     [rsp+2A0h+var_268], 0
0x14000ef59  mov     rax, [rbx]
0x14000ef5c  mov     rdi, [rax]
0x14000ef5f  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x14000ef64  lea     r8, [rsp+2A0h+var_268]
0x14000ef69  mov     rcx, rbx
0x14000ef6c  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x14000ef73  mov     rax, rdi
0x14000ef76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ef7b  mov     ebx, eax
0x14000ef7d  test    eax, eax
0x14000ef7f  js      loc_14000F053
0x14000ef85  xorps   xmm0, xmm0
0x14000ef88  lea     rdx, [rsp+2A0h+pvar]; struct tagPROPVARIANT *
0x14000ef8d  xor     eax, eax
0x14000ef8f  mov     rcx, rsi; Source
0x14000ef92  movups  xmmword ptr [rsp+2A0h+pvar], xmm0
0x14000ef97  mov     qword ptr [rsp+2A0h+pvar+10h], rax
0x14000ef9c  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x14000efa1  mov     ebx, eax
0x14000efa3  test    eax, eax
0x14000efa5  js      loc_14000F053
0x14000efab  mov     rcx, [rsp+2A0h+var_268]
0x14000efb0  lea     r8, [rsp+2A0h+pvar]
0x14000efb5  lea     rdx, PKEY_AppUserModel_ID
0x14000efbc  mov     rax, [rcx]
0x14000efbf  mov     rax, [rax+30h]
0x14000efc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000efc8  lea     rcx, [rsp+2A0h+pvar]; pvar
0x14000efcd  mov     ebx, eax
0x14000efcf  call    cs:__imp_PropVariantClear
0x14000efd5  test    ebx, ebx
0x14000efd7  js      short loc_14000F053
0x14000efd9  mov     rcx, [rsp+2A0h+var_268]
0x14000efde  mov     rax, [rcx]
0x14000efe1  mov     rax, [rax+38h]
0x14000efe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000efea  mov     ebx, eax
0x14000efec  test    eax, eax
0x14000efee  js      short loc_14000F053
0x14000eff0  mov     rbx, [rsp+2A0h+var_270]
0x14000eff5  lea     rcx, [rsp+2A0h+var_260]
0x14000effa  mov     [rsp+2A0h+var_260], 0
0x14000f003  mov     rax, [rbx]
0x14000f006  mov     rdi, [rax]
0x14000f009  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x14000f00e  lea     r8, [rsp+2A0h+var_260]
0x14000f013  mov     rcx, rbx
0x14000f016  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x14000f01d  mov     rax, rdi
0x14000f020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f025  mov     ebx, eax
0x14000f027  test    eax, eax
0x14000f029  js      short loc_14000F049
0x14000f02b  mov     rcx, [rsp+2A0h+var_260]
0x14000f030  lea     rdx, [rsp+2A0h+FileName]
0x14000f035  mov     r8d, 1
0x14000f03b  mov     rax, [rcx]
0x14000f03e  mov     rax, [rax+30h]
0x14000f042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f047  mov     ebx, eax
0x14000f049  lea     rcx, [rsp+2A0h+var_260]
0x14000f04e  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x14000f053  lea     rcx, [rsp+2A0h+var_268]
0x14000f058  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x14000f05d  lea     rcx, [rsp+2A0h+var_270]
0x14000f062  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x14000f067  mov     eax, ebx
0x14000f069  mov     rcx, [rbp+1A0h+var_30]
0x14000f070  xor     rcx, rsp; StackCookie
0x14000f073  call    __security_check_cookie
0x14000f078  add     rsp, 288h
0x14000f07f  pop     rdi
0x14000f080  pop     rsi
0x14000f081  pop     rbx
0x14000f082  pop     rbp
0x14000f083  retn
```
