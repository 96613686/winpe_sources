# CMDMPushConfiguration::SaveToRegistry(ushort const *,tagVARIANT)

- ea: `0x1800ca524`
- end: `0x1800ca6d8`
- name: `?SaveToRegistry@CMDMPushConfiguration@@AEAAJPEBGUtagVARIANT@@@Z`
- size: `436`
- prototype: `int(CMDMPushConfiguration *__hidden this, const unsigned __int16 *, struct tagVARIANT *__struct_ptr)`
- caller_count: `7`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ca028`
- `0x1800ca128`
- `0x1800ca1f0`
- `0x1800ca294`
- `0x1800ca35c`
- `0x1800ca45c`
- `0x1800ca6e0`

## callees

- `0x180008de0`
- `0x180009cc4`
- `0x18000d4d4`
- `0x18000db4c`
- `0x180025ac0`
- `0x180025d20`
- `0x18002aed0`
- `0x18002dcc8`
- `0x1800ca524`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x1800ca601`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800ca601`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ca676`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ca676`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ca648`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ca648`

## pseudocode

```c
__int64 __fastcall CMDMPushConfiguration::SaveToRegistry(
        CMDMPushConfiguration *this,
        const unsigned __int16 *a2,
        struct tagVARIANT *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rbx
  const unsigned __int16 *v9; // rax
  UINT cbData; // ebx
  OLECHAR *bstrVal; // rdi
  DWORD v12; // esi
  unsigned int v13; // eax
  __int64 v14; // rdx
  int phkResult; // [rsp+20h] [rbp-258h]
  unsigned int phkResulta; // [rsp+20h] [rbp-258h]
  HKEY hKey[2]; // [rsp+30h] [rbp-248h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( a2 )
  {
    memset_0(SubKey, 0, 0x208u);
    v8 = *((_QWORD *)this + 1);
    v9 = DMGetNonVolatileRegPrefix();
    phkResult = v8;
    v6 = StringCchPrintfW(SubKey, 0x104u, L"%sSoftware\\Microsoft\\Enrollments\\%s\\Push", v9);
    if ( (v6 & 0x80000000) != 0 )
    {
      v7 = 808;
      goto LABEL_3;
    }
    cbData = 8;
    switch ( a3->vt )
    {
      case 8u:
        bstrVal = a3->bstrVal;
        cbData = SysStringByteLen(bstrVal);
        v12 = 1;
        break;
      case 0x13u:
        bstrVal = &a3->uiVal;
        cbData = 4;
        v12 = 4;
        break;
      case 0x15u:
        bstrVal = &a3->uiVal;
        v12 = 11;
        break;
      default:
        v6 = -2147418113;
        v7 = 834;
        goto LABEL_3;
    }
    hKey[0] = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      hKey,
      0);
    v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0xF003Fu, hKey);
    if ( v13 )
    {
      v14 = 843;
    }
    else
    {
      v13 = RegSetValueExW(hKey[0], a2, 0, v12, (const BYTE *)bstrVal, cbData);
      if ( !v13 )
      {
        v6 = 0;
        goto LABEL_19;
      }
      v14 = 851;
    }
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v14,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
           (const char *)v13,
           phkResulta);
LABEL_19:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
    return v6;
  }
  v6 = -2147024809;
  v7 = 800;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
    (const char *)v6,
    phkResult);
  return v6;
}

```

## disassembly

```asm
0x1800ca524  mov     [rsp+arg_18], rbx
0x1800ca529  push    rbp
0x1800ca52a  push    rsi
0x1800ca52b  push    rdi
0x1800ca52c  sub     rsp, 260h
0x1800ca533  mov     rax, cs:__security_cookie
0x1800ca53a  xor     rax, rsp
0x1800ca53d  mov     [rsp+278h+var_28], rax
0x1800ca545  mov     rdi, r8
0x1800ca548  mov     rbp, rdx
0x1800ca54b  mov     rbx, rcx
0x1800ca54e  test    rdx, rdx
0x1800ca551  jnz     short loc_1800CA579
0x1800ca553  mov     ebx, 80070057h
0x1800ca558  mov     edx, 320h; void *
0x1800ca55d  mov     rcx, [rsp+278h]; this
0x1800ca565  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x1800ca56c  mov     r9d, ebx; char *
0x1800ca56f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ca574  jmp     loc_1800CA6B2
0x1800ca579  xor     edx, edx; Val
0x1800ca57b  lea     rcx, [rsp+278h+SubKey]; void *
0x1800ca580  mov     r8d, 208h; Size
0x1800ca586  call    memset_0
0x1800ca58b  mov     rbx, [rbx+8]
0x1800ca58f  call    ?DMGetNonVolatileRegPrefix@@YAPEBGXZ; DMGetNonVolatileRegPrefix(void)
0x1800ca594  mov     r9, rax
0x1800ca597  mov     [rsp+278h+phkResult], rbx
0x1800ca59c  lea     r8, aSsoftwareMicro; "%sSoftware\\Microsoft\\Enrollments\\%s"...
0x1800ca5a3  mov     edx, 104h; unsigned __int64
0x1800ca5a8  lea     rcx, [rsp+278h+SubKey]; unsigned __int16 *
0x1800ca5ad  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ca5b2  mov     ebx, eax
0x1800ca5b4  test    eax, eax
0x1800ca5b6  jns     short loc_1800CA5BF
0x1800ca5b8  mov     edx, 328h
0x1800ca5bd  jmp     short loc_1800CA55D
0x1800ca5bf  mov     ebx, 8
0x1800ca5c4  cmp     [rdi], bx
0x1800ca5c7  jz      short loc_1800CA5FA
0x1800ca5c9  cmp     word ptr [rdi], 13h
0x1800ca5cd  jz      short loc_1800CA5EE
0x1800ca5cf  cmp     word ptr [rdi], 15h
0x1800ca5d3  jz      short loc_1800CA5E4
0x1800ca5d5  mov     ebx, 8000FFFFh
0x1800ca5da  mov     edx, 342h
0x1800ca5df  jmp     loc_1800CA55D
0x1800ca5e4  add     rdi, rbx
0x1800ca5e7  mov     esi, 0Bh
0x1800ca5ec  jmp     short loc_1800CA614
0x1800ca5ee  add     rdi, rbx
0x1800ca5f1  mov     ebx, 4
0x1800ca5f6  mov     esi, ebx
0x1800ca5f8  jmp     short loc_1800CA614
0x1800ca5fa  mov     rdi, [rdi+8]
0x1800ca5fe  mov     rcx, rdi; bstr
0x1800ca601  call    cs:__imp_SysStringByteLen
0x1800ca608  nop     dword ptr [rax+rax+00h]
0x1800ca60d  mov     ebx, eax
0x1800ca60f  mov     esi, 1
0x1800ca614  xor     edx, edx
0x1800ca616  mov     [rsp+278h+hKey], 0
0x1800ca61f  lea     rcx, [rsp+278h+hKey]
0x1800ca624  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800ca629  lea     rax, [rsp+278h+hKey]
0x1800ca62e  mov     r9d, 0F003Fh; samDesired
0x1800ca634  xor     r8d, r8d; ulOptions
0x1800ca637  mov     [rsp+278h+phkResult], rax; phkResult
0x1800ca63c  lea     rdx, [rsp+278h+SubKey]; lpSubKey
0x1800ca641  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ca648  call    cs:__imp_RegOpenKeyExW
0x1800ca64f  nop     dword ptr [rax+rax+00h]
0x1800ca654  test    eax, eax
0x1800ca656  jz      short loc_1800CA65F
0x1800ca658  mov     edx, 34Bh
0x1800ca65d  jmp     short loc_1800CA68B
0x1800ca65f  mov     rcx, [rsp+278h+hKey]; hKey
0x1800ca664  mov     r9d, esi; dwType
0x1800ca667  mov     [rsp+278h+cbData], ebx; cbData
0x1800ca66b  xor     r8d, r8d; Reserved
0x1800ca66e  mov     rdx, rbp; lpValueName
0x1800ca671  mov     [rsp+278h+phkResult], rdi; unsigned int
0x1800ca676  call    cs:__imp_RegSetValueExW
0x1800ca67d  nop     dword ptr [rax+rax+00h]
0x1800ca682  test    eax, eax
0x1800ca684  jz      short loc_1800CA6A6
0x1800ca686  mov     edx, 353h; void *
0x1800ca68b  mov     rcx, [rsp+278h]; this
0x1800ca693  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x1800ca69a  mov     r9d, eax; char *
0x1800ca69d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800ca6a2  mov     ebx, eax
0x1800ca6a4  jmp     short loc_1800CA6A8
0x1800ca6a6  xor     ebx, ebx
0x1800ca6a8  lea     rcx, [rsp+278h+hKey]
0x1800ca6ad  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ca6b2  mov     eax, ebx
0x1800ca6b4  mov     rcx, [rsp+278h+var_28]
0x1800ca6bc  xor     rcx, rsp; StackCookie
0x1800ca6bf  call    __security_check_cookie
0x1800ca6c4  mov     rbx, [rsp+278h+arg_18]
0x1800ca6cc  add     rsp, 260h
0x1800ca6d3  pop     rdi
0x1800ca6d4  pop     rsi
0x1800ca6d5  pop     rbp
0x1800ca6d6  retn
```
