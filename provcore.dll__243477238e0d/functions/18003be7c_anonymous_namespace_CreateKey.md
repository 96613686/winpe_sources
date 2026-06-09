# _anonymous_namespace_::CreateKey

- ea: `0x18003be7c`
- end: `0x18003c00e`
- name: `_anonymous_namespace_::CreateKey`
- size: `402`
- prototype: `HKEY__ *__fastcall(const Registry::Path *path, unsigned int path)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18003c014`
- `0x180046b90`

## callees

- `0x180002790`
- `0x1800032f4`
- `0x180011844`
- `0x180012748`
- `0x180012770`
- `0x18003bc8c`
- `0x18003be7c`
- `0x18003c534`
- `0x18003ce2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003bf3c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003bf3c`

## pseudocode

```c
HKEY__ *__fastcall anonymous_namespace_::CreateKey(Registry::Path *path, unsigned int a2)
{
  HKEY RootKey; // rdi
  const wchar_t *Logger; // rax
  __int64 v5; // r8
  const WCHAR *v6; // rax
  LSTATUS v7; // eax
  HRESULT v8; // ebx
  WPP_PROJECT_CONTROL_BLOCK *v9; // rcx
  unsigned __int16 v10; // dx
  Registry::Exception pExceptionObject; // [rsp+50h] [rbp-48h] BYREF
  HKEY__ *keyHandle; // [rsp+70h] [rbp-28h] BYREF
  unsigned int disposition; // [rsp+78h] [rbp-20h] BYREF

  RootKey = Registry::Path::GetRootKey(path, 0xF003Fu);
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    Logger = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&path->m_path._Mypair._Myval2);
    WPP_SF_qS(*(_QWORD *)(v5 + 16), 0xEu, (const _GUID *)v5, RootKey, Logger);
  }
  keyHandle = 0;
  disposition = 0;
  v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&path->m_path._Mypair._Myval2);
  v7 = RegCreateKeyExW(RootKey, v6, 0, 0, 0, 0xF003Fu, 0, &keyHandle, &disposition);
  v8 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0xFu, WPP_170303dbc4e93be116a24b4d7c6c7bfc_Traceguids, v7);
    }
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    Registry::Exception::Exception(&pExceptionObject, v8);
    throw &pExceptionObject;
  }
  if ( disposition == 1 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      v10 = 16;
LABEL_18:
      WPP_SF_(v9->Control.Logger, v10, WPP_170303dbc4e93be116a24b4d7c6c7bfc_Traceguids);
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      v10 = 17;
      goto LABEL_18;
    }
  }
  return keyHandle;
}

```

## disassembly

```asm
0x18003be7c  mov     [rsp+arg_8], rbx
0x18003be81  mov     [rsp+arg_10], rbp
0x18003be86  push    rdi
0x18003be87  sub     rsp, 90h
0x18003be8e  mov     rax, cs:__security_cookie
0x18003be95  xor     rax, rsp
0x18003be98  mov     [rsp+98h+var_18], rax
0x18003bea0  mov     edx, 0F003Fh; KeyAccess
0x18003bea5  mov     rbx, path
0x18003bea8  call    ?GetRootKey@Path@Registry@@QEBAPEAUHKEY__@@K@Z; Registry::Path::GetRootKey(ulong)
0x18003bead  mov     rdi, rax
0x18003beb0  mov     r8, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003beb7  lea     rbp, WPP_GLOBAL_Control
0x18003bebe  cmp     r8, rbp
0x18003bec1  jz      short loc_18003BEE9
0x18003bec3  test    byte ptr [r8+1Ch], 10h
0x18003bec8  jz      short loc_18003BEE9
0x18003beca  lea     path, [rbx+10h]; this
0x18003bece  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003bed3  mov     path, [r8+10h]; Logger
0x18003bed7  mov     edx, 0Eh; id
0x18003bedc  mov     r9, rdi; _a2
0x18003bedf  mov     [rsp+98h+Logger], rax; Logger
0x18003bee4  call    WPP_SF_qS
0x18003bee9  lea     path, [rbx+10h]; this
0x18003beed  mov     [rsp+98h+keyHandle], 0
0x18003bef6  mov     [rsp+98h+disposition], 0
0x18003befe  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003bf03  lea     path, [rsp+98h+disposition]
0x18003bf08  xor     r9d, r9d; lpClass
0x18003bf0b  mov     [rsp+98h+lpdwDisposition], path; lpdwDisposition
0x18003bf10  xor     r8d, r8d; Reserved
0x18003bf13  lea     path, [rsp+98h+keyHandle]
0x18003bf18  mov     rdx, rax; lpSubKey
0x18003bf1b  mov     [rsp+98h+phkResult], path; phkResult
0x18003bf20  mov     path, rdi; hKey
0x18003bf23  mov     [rsp+98h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003bf2c  mov     [rsp+98h+samDesired], 0F003Fh; samDesired
0x18003bf34  mov     dword ptr [rsp+98h+Logger], 0; dwOptions
0x18003bf3c  call    cs:__imp_RegCreateKeyExW
0x18003bf42  mov     ebx, eax
0x18003bf44  test    eax, eax
0x18003bf46  jz      short loc_18003BF9D
0x18003bf48  mov     path, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003bf4f  cmp     path, rbp
0x18003bf52  jz      short loc_18003BF72
0x18003bf54  test    byte ptr [path+1Ch], 2
0x18003bf58  jz      short loc_18003BF72
0x18003bf5a  mov     path, [path+10h]; Logger
0x18003bf5e  lea     r8, WPP_170303dbc4e93be116a24b4d7c6c7bfc_Traceguids; TraceGuid
0x18003bf65  mov     edx, 0Fh; id
0x18003bf6a  mov     r9d, eax; _a1
0x18003bf6d  call    WPP_SF_d
0x18003bf72  test    ebx, ebx
0x18003bf74  jle     short loc_18003BF7F
0x18003bf76  movzx   ebx, bx
0x18003bf79  or      ebx, 80070000h
0x18003bf7f  mov     edx, ebx; hr
0x18003bf81  lea     path, [rsp+98h+pExceptionObject]; this
0x18003bf86  call    ??0Exception@Registry@@QEAA@J@Z; Registry::Exception::Exception(long)
0x18003bf8b  lea     rdx, _TI3?AVException@Registry@@; pThrowInfo
0x18003bf92  lea     path, [rsp+98h+pExceptionObject]; pExceptionObject
0x18003bf97  call    _CxxThrowException_0
0x18003bf9d  cmp     [rsp+98h+disposition], 1
0x18003bfa2  jnz     short loc_18003BFBD
0x18003bfa4  mov     path, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003bfab  cmp     path, rbp
0x18003bfae  jz      short loc_18003BFE4
0x18003bfb0  test    byte ptr [path+1Ch], 10h
0x18003bfb4  jz      short loc_18003BFE4
0x18003bfb6  mov     edx, 10h
0x18003bfbb  jmp     short loc_18003BFD4
0x18003bfbd  mov     path, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003bfc4  cmp     path, rbp
0x18003bfc7  jz      short loc_18003BFE4
0x18003bfc9  test    byte ptr [path+1Ch], 10h
0x18003bfcd  jz      short loc_18003BFE4
0x18003bfcf  mov     edx, 11h; id
0x18003bfd4  mov     path, [path+10h]; Logger
0x18003bfd8  lea     r8, WPP_170303dbc4e93be116a24b4d7c6c7bfc_Traceguids; TraceGuid
0x18003bfdf  call    WPP_SF_
0x18003bfe4  mov     rax, [rsp+98h+keyHandle]
0x18003bfe9  mov     path, [rsp+98h+var_18]
0x18003bff1  xor     path, rsp; StackCookie
0x18003bff4  call    __security_check_cookie
0x18003bff9  lea     r11, [rsp+98h+var_8]
0x18003c001  mov     rbx, [r11+18h]
0x18003c005  mov     rbp, [r11+20h]
0x18003c009  mov     rsp, r11
0x18003c00c  pop     rdi
0x18003c00d  retn
```
