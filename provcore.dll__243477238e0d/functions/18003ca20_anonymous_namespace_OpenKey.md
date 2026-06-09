# _anonymous_namespace_::OpenKey

- ea: `0x18003ca20`
- end: `0x18003cb2f`
- name: `_anonymous_namespace_::OpenKey`
- size: `271`
- prototype: `HKEY__ *__fastcall(const Registry::Path *path, unsigned int KeyAccess)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003cb38`
- `0x18003cb9c`

## callees

- `0x180002790`
- `0x1800032f4`
- `0x180011844`
- `0x180012770`
- `0x18003bc8c`
- `0x18003c534`
- `0x18003ca20`
- `0x18003ce2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003caa9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003caa9`

## pseudocode

```c
HKEY__ *__fastcall anonymous_namespace_::OpenKey(Registry::Path *path, unsigned int KeyAccess)
{
  HKEY RootKey; // rdi
  const wchar_t *Logger; // rax
  __int64 v6; // r8
  const WCHAR *v7; // rax
  LSTATUS v8; // eax
  HRESULT v9; // ebx
  Registry::Exception pExceptionObject; // [rsp+30h] [rbp-48h] BYREF
  HKEY__ *keyHandle; // [rsp+50h] [rbp-28h] BYREF

  RootKey = Registry::Path::GetRootKey(path, KeyAccess);
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    Logger = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&path->m_path._Mypair._Myval2);
    WPP_SF_qS(*(_QWORD *)(v6 + 16), 0xCu, (const _GUID *)v6, RootKey, Logger);
  }
  keyHandle = 0;
  v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&path->m_path._Mypair._Myval2);
  v8 = RegOpenKeyExW(RootKey, v7, 0, KeyAccess, &keyHandle);
  v9 = v8;
  if ( (v8 & 0xFFFFFFFD) != 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0xDu, WPP_170303dbc4e93be116a24b4d7c6c7bfc_Traceguids, v8);
    }
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    Registry::Exception::Exception(&pExceptionObject, v9);
    throw &pExceptionObject;
  }
  return keyHandle;
}

```

## disassembly

```asm
0x18003ca20  mov     [rsp+arg_10], rbx
0x18003ca25  push    rbp
0x18003ca26  push    rsi
0x18003ca27  push    rdi
0x18003ca28  sub     rsp, 60h
0x18003ca2c  mov     rax, cs:__security_cookie
0x18003ca33  xor     rax, rsp
0x18003ca36  mov     [rsp+78h+var_20], rax
0x18003ca3b  mov     esi, KeyAccess
0x18003ca3d  mov     rbx, path
0x18003ca40  call    ?GetRootKey@Path@Registry@@QEBAPEAUHKEY__@@K@Z; Registry::Path::GetRootKey(ulong)
0x18003ca45  mov     rdi, rax
0x18003ca48  mov     r8, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003ca4f  lea     rbp, WPP_GLOBAL_Control
0x18003ca56  cmp     r8, rbp
0x18003ca59  jz      short loc_18003CA81
0x18003ca5b  test    byte ptr [r8+1Ch], 10h
0x18003ca60  jz      short loc_18003CA81
0x18003ca62  lea     path, [rbx+10h]; this
0x18003ca66  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003ca6b  mov     path, [r8+10h]; Logger
0x18003ca6f  mov     KeyAccess, 0Ch; id
0x18003ca74  mov     r9, rdi; _a2
0x18003ca77  mov     [rsp+78h+Logger], rax; Logger
0x18003ca7c  call    WPP_SF_qS
0x18003ca81  lea     path, [rbx+10h]; this
0x18003ca85  mov     [rsp+78h+keyHandle], 0
0x18003ca8e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003ca93  lea     path, [rsp+78h+keyHandle]
0x18003ca98  mov     r9d, esi; samDesired
0x18003ca9b  mov     [rsp+78h+Logger], path; phkResult
0x18003caa0  xor     r8d, r8d; ulOptions
0x18003caa3  mov     path, rdi; hKey
0x18003caa6  mov     rdx, rax; lpSubKey
0x18003caa9  call    cs:__imp_RegOpenKeyExW
0x18003caaf  mov     ebx, eax
0x18003cab1  test    eax, 0FFFFFFFDh
0x18003cab6  jz      short loc_18003CB0D
0x18003cab8  mov     path, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003cabf  cmp     path, rbp
0x18003cac2  jz      short loc_18003CAE2
0x18003cac4  test    byte ptr [path+1Ch], 2
0x18003cac8  jz      short loc_18003CAE2
0x18003caca  mov     path, [path+10h]; Logger
0x18003cace  lea     r8, WPP_170303dbc4e93be116a24b4d7c6c7bfc_Traceguids; TraceGuid
0x18003cad5  mov     KeyAccess, 0Dh; id
0x18003cada  mov     r9d, eax; _a1
0x18003cadd  call    WPP_SF_d
0x18003cae2  test    ebx, ebx
0x18003cae4  jle     short loc_18003CAEF
0x18003cae6  movzx   ebx, bx
0x18003cae9  or      ebx, 80070000h
0x18003caef  mov     KeyAccess, ebx; hr
0x18003caf1  lea     path, [rsp+78h+pExceptionObject]; this
0x18003caf6  call    ??0Exception@Registry@@QEAA@J@Z; Registry::Exception::Exception(long)
0x18003cafb  lea     rdx, _TI3?AVException@Registry@@; pThrowInfo
0x18003cb02  lea     path, [rsp+78h+pExceptionObject]; pExceptionObject
0x18003cb07  call    _CxxThrowException_0
0x18003cb0d  mov     rax, [rsp+78h+keyHandle]
0x18003cb12  mov     path, [rsp+78h+var_20]
0x18003cb17  xor     path, rsp; StackCookie
0x18003cb1a  call    __security_check_cookie
0x18003cb1f  mov     rbx, [rsp+78h+arg_10]
0x18003cb27  add     rsp, 60h
0x18003cb2b  pop     rdi
0x18003cb2c  pop     rsi
0x18003cb2d  pop     rbp
0x18003cb2e  retn
```
