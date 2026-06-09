# _anonymous_namespace_::CreateKeyWithSecurityDescriptor

- ea: `0x18003c06c`
- end: `0x18003c289`
- name: `_anonymous_namespace_::CreateKeyWithSecurityDescriptor`
- size: `541`
- prototype: `HKEY__ *__fastcall(const Registry::Path *path, unsigned int path, const Registry::REGISTRY_ACCESS_PERMISSIONS KeyAccess)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003c040`

## callees

- `0x180002790`
- `0x1800032f4`
- `0x180011844`
- `0x180012748`
- `0x180012770`
- `0x180012bc8`
- `0x18003bc8c`
- `0x18003c06c`
- `0x18003c534`
- `0x18003c5dc`
- `0x18003ce2c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c123`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c1bc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c1bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HKEY__ *__fastcall anonymous_namespace_::CreateKeyWithSecurityDescriptor(
        Registry::Path *path,
        unsigned int a2,
        const Registry::REGISTRY_ACCESS_PERMISSIONS KeyAccess)
{
  HKEY RootKey; // rsi
  Registry::REGISTRY_ACCESS_PERMISSIONS v5; // ecx
  int SecurityDescriptor; // eax
  HRESULT v7; // ebx
  std::wstring *p_m_path; // rbx
  const wchar_t *Logger; // rax
  __int64 v10; // r8
  const WCHAR *v11; // rax
  LSTATUS v12; // eax
  HRESULT v13; // ebx
  WPP_PROJECT_CONTROL_BLOCK *v14; // rcx
  unsigned __int16 v15; // dx
  HKEY__ *v16; // rbx
  Registry::Exception pExceptionObject; // [rsp+50h] [rbp-39h] BYREF
  Registry::Exception v19; // [rsp+70h] [rbp-19h] BYREF
  HKEY__ *keyHandle; // [rsp+90h] [rbp+7h] BYREF
  _SECURITY_ATTRIBUTES sa; // [rsp+98h] [rbp+Fh] BYREF
  unsigned int disposition; // [rsp+B0h] [rbp+27h] BYREF

  RootKey = Registry::Path::GetRootKey(path, 0xF003Fu);
  memset(&sa, 0, sizeof(sa));
  sa.nLength = 24;
  SecurityDescriptor = anonymous_namespace_::GetSecurityDescriptor(v5, &sa.lpSecurityDescriptor);
  v7 = SecurityDescriptor;
  if ( SecurityDescriptor )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->Control.Logger,
        0x12u,
        WPP_170303dbc4e93be116a24b4d7c6c7bfc_Traceguids,
        SecurityDescriptor);
    }
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    Registry::Exception::Exception(&pExceptionObject, v7);
    throw &pExceptionObject;
  }
  p_m_path = &path->m_path;
  LOBYTE(pExceptionObject.__vftable) = 0;
  pExceptionObject._Data._What = (const char *)LocalFree;
  *(_QWORD *)&pExceptionObject._Data._DoFree = sa.lpSecurityDescriptor;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    Logger = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&p_m_path->_Mypair._Myval2);
    WPP_SF_qS(*(_QWORD *)(v10 + 16), 0x13u, (const _GUID *)v10, RootKey, Logger);
  }
  keyHandle = 0;
  disposition = 0;
  v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&p_m_path->_Mypair._Myval2);
  v12 = RegCreateKeyExW(RootKey, v11, 0, 0, 0, 0xF003Fu, &sa, &keyHandle, &disposition);
  v13 = v12;
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x14u, WPP_170303dbc4e93be116a24b4d7c6c7bfc_Traceguids, v12);
    }
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    Registry::Exception::Exception(&v19, v13);
    throw &v19;
  }
  if ( disposition == 1 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      v15 = 21;
LABEL_25:
      WPP_SF_(v14->Control.Logger, v15, WPP_170303dbc4e93be116a24b4d7c6c7bfc_Traceguids);
    }
  }
  else
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      v15 = 22;
      goto LABEL_25;
    }
  }
  v16 = keyHandle;
  ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>((ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> *)&pExceptionObject);
  return v16;
}

```

## disassembly

```asm
0x18003c06c  push    rbp
0x18003c06e  push    rbx
0x18003c06f  push    rsi
0x18003c070  push    rdi
0x18003c071  lea     rbp, [rsp-3Fh]
0x18003c076  sub     rsp, 0C8h
0x18003c07d  mov     rax, cs:__security_cookie
0x18003c084  xor     rax, rsp
0x18003c087  mov     [rbp+57h+var_28], rax
0x18003c08b  mov     rdi, path
0x18003c08e  mov     edx, 0F003Fh; KeyAccess
0x18003c093  call    ?GetRootKey@Path@Registry@@QEBAPEAUHKEY__@@K@Z; Registry::Path::GetRootKey(ulong)
0x18003c098  mov     rsi, rax
0x18003c09b  xorps   xmm0, xmm0
0x18003c09e  xor     eax, eax
0x18003c0a0  movups  xmmword ptr [rbp+57h+sa.nLength], xmm0
0x18003c0a4  mov     qword ptr [rbp+57h+sa.bInheritHandle], rax
0x18003c0a8  mov     [rbp+57h+sa.nLength], 18h
0x18003c0af  mov     [rbp+57h+sa.bInheritHandle], eax
0x18003c0b2  lea     rdx, [rbp+57h+sa.lpSecurityDescriptor]; AccessPermissions
0x18003c0b6  call    _anonymous_namespace___GetSecurityDescriptor
0x18003c0bb  mov     ebx, eax
0x18003c0bd  test    eax, eax
0x18003c0bf  jz      short loc_18003C11B
0x18003c0c1  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x18003c0c8  mov     path, cs:WPP_GLOBAL_Control
0x18003c0cf  cmp     path, rdi
0x18003c0d2  jz      short loc_18003C0F2
0x18003c0d4  test    byte ptr [path+1Ch], 2
0x18003c0d8  jz      short loc_18003C0F2
0x18003c0da  mov     edx, 12h; id
0x18003c0df  mov     r9d, eax; _a1
0x18003c0e2  lea     r8, WPP_170303dbc4e93be116a24b4d7c6c7bfc_Traceguids; TraceGuid
0x18003c0e9  mov     path, [path+10h]; Logger
0x18003c0ed  call    WPP_SF_d
0x18003c0f2  test    ebx, ebx
0x18003c0f4  jle     short loc_18003C0FF
0x18003c0f6  movzx   ebx, bx
0x18003c0f9  or      ebx, 80070000h
0x18003c0ff  mov     edx, ebx; hr
0x18003c101  lea     path, [rbp+57h+pExceptionObject]; this
0x18003c105  call    ??0Exception@Registry@@QEAA@J@Z; Registry::Exception::Exception(long)
0x18003c10a  lea     rdx, _TI3?AVException@Registry@@; pThrowInfo
0x18003c111  lea     path, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003c115  call    _CxxThrowException_0
0x18003c11b  lea     rbx, [rdi+10h]
0x18003c11f  mov     path, [rbp+57h+sa.lpSecurityDescriptor]
0x18003c123  mov     rax, cs:__imp_LocalFree
0x18003c12a  mov     byte ptr [rbp+57h+pExceptionObject.__vftable], 0
0x18003c12e  mov     [rbp+57h+pExceptionObject._Data._What], rax
0x18003c132  mov     qword ptr [rbp+57h+pExceptionObject._Data._DoFree], path
0x18003c136  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x18003c13d  mov     r8, cs:WPP_GLOBAL_Control
0x18003c144  cmp     r8, rdi
0x18003c147  jz      short loc_18003C16E
0x18003c149  test    byte ptr [r8+1Ch], 10h
0x18003c14e  jz      short loc_18003C16E
0x18003c150  mov     path, rbx; this
0x18003c153  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003c158  mov     edx, 13h; id
0x18003c15d  mov     [rsp+0E0h+Logger], rax; Logger
0x18003c162  mov     r9, rsi; _a2
0x18003c165  mov     path, [r8+10h]; Logger
0x18003c169  call    WPP_SF_qS
0x18003c16e  mov     [rbp+57h+keyHandle], 0
0x18003c176  mov     [rbp+57h+disposition], 0
0x18003c17d  mov     path, rbx; this
0x18003c180  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003c185  lea     path, [rbp+57h+disposition]
0x18003c189  mov     [rsp+0E0h+lpdwDisposition], path; lpdwDisposition
0x18003c18e  lea     path, [rbp+57h+keyHandle]
0x18003c192  mov     [rsp+0E0h+phkResult], path; phkResult
0x18003c197  lea     path, [rbp+57h+sa]
0x18003c19b  mov     [rsp+0E0h+lpSecurityAttributes], path; lpSecurityAttributes
0x18003c1a0  mov     [rsp+0E0h+samDesired], 0F003Fh; samDesired
0x18003c1a8  mov     dword ptr [rsp+0E0h+Logger], 0; dwOptions
0x18003c1b0  xor     r9d, r9d; lpClass
0x18003c1b3  xor     r8d, r8d; Reserved
0x18003c1b6  mov     rdx, rax; lpSubKey
0x18003c1b9  mov     path, rsi; hKey
0x18003c1bc  call    cs:__imp_RegCreateKeyExW
0x18003c1c2  mov     ebx, eax
0x18003c1c4  test    eax, eax
0x18003c1c6  jz      short loc_18003C21B
0x18003c1c8  mov     path, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003c1cf  cmp     path, rdi
0x18003c1d2  jz      short loc_18003C1F2
0x18003c1d4  test    byte ptr [path+1Ch], 2
0x18003c1d8  jz      short loc_18003C1F2
0x18003c1da  mov     edx, 14h; id
0x18003c1df  mov     r9d, eax; _a1
0x18003c1e2  lea     r8, WPP_170303dbc4e93be116a24b4d7c6c7bfc_Traceguids; TraceGuid
0x18003c1e9  mov     path, [path+10h]; Logger
0x18003c1ed  call    WPP_SF_d
0x18003c1f2  test    ebx, ebx
0x18003c1f4  jle     short loc_18003C1FF
0x18003c1f6  movzx   ebx, bx
0x18003c1f9  or      ebx, 80070000h
0x18003c1ff  mov     edx, ebx; hr
0x18003c201  lea     path, [rbp+57h+var_70]; this
0x18003c205  call    ??0Exception@Registry@@QEAA@J@Z; Registry::Exception::Exception(long)
0x18003c20a  lea     rdx, _TI3?AVException@Registry@@; pThrowInfo
0x18003c211  lea     path, [rbp+57h+var_70]; pExceptionObject
0x18003c215  call    _CxxThrowException_0
0x18003c21b  cmp     [rbp+57h+disposition], 1
0x18003c21f  jnz     short loc_18003C23A
0x18003c221  mov     path, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003c228  cmp     path, rdi
0x18003c22b  jz      short loc_18003C261
0x18003c22d  test    byte ptr [path+1Ch], 10h
0x18003c231  jz      short loc_18003C261
0x18003c233  mov     edx, 15h
0x18003c238  jmp     short loc_18003C251
0x18003c23a  mov     path, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003c241  cmp     path, rdi
0x18003c244  jz      short loc_18003C261
0x18003c246  test    byte ptr [path+1Ch], 10h
0x18003c24a  jz      short loc_18003C261
0x18003c24c  mov     edx, 16h; id
0x18003c251  lea     r8, WPP_170303dbc4e93be116a24b4d7c6c7bfc_Traceguids; TraceGuid
0x18003c258  mov     path, [path+10h]; Logger
0x18003c25c  call    WPP_SF_
0x18003c261  mov     rbx, [rbp+57h+keyHandle]
0x18003c265  lea     path, [rbp+57h+pExceptionObject]; j
0x18003c269  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x18003c26e  mov     rax, rbx
0x18003c271  mov     path, [rbp+57h+var_28]
0x18003c275  xor     path, rsp; StackCookie
0x18003c278  call    __security_check_cookie
0x18003c27d  add     rsp, 0C8h
0x18003c284  pop     rdi
0x18003c285  pop     rsi
0x18003c286  pop     rbx
0x18003c287  pop     rbp
0x18003c288  retn
```
