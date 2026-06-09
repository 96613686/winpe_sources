# EfsConfig_SetRmsOwnerEmail(ushort const *)

- ea: `0x180061bb4`
- end: `0x180061e7b`
- name: `?EfsConfig_SetRmsOwnerEmail@@YAJPEBG@Z`
- size: `711`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006e29c`

## callees

- `0x18000b12c`
- `0x18000ef44`
- `0x1800124d8`
- `0x18001312c`
- `0x18004d12c`
- `0x180061748`
- `0x180061bb4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180061e1d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180061e1d`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180061bea`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180061bea`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180061ce1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180061ce1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180061c89`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180061c89`

## string_xrefs

- `0x180061c06`: `onecoreuap\ds\security\efs\common\lib\efsenv.cxx`
- `0x180061ca5`: `onecoreuap\ds\security\efs\common\lib\efsenv.cxx`
- `0x180061cf6`: `onecoreuap\ds\security\efs\common\lib\efsenv.cxx`
- `0x180061d48`: `onecoreuap\ds\security\efs\common\lib\efsenv.cxx`
- `0x180061d94`: `onecoreuap\ds\security\efs\common\lib\efsenv.cxx`
- `0x180061dd5`: `onecoreuap\ds\security\efs\common\lib\efsenv.cxx`
- `0x180061e2e`: `onecoreuap\ds\security\efs\common\lib\efsenv.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EfsConfig_SetRmsOwnerEmail(const unsigned __int16 *a1)
{
  unsigned int v2; // ebx
  unsigned int v3; // ebx
  unsigned int v5; // ebx
  unsigned int v6; // eax
  int v7; // eax
  int v8; // eax
  unsigned int v9; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-60h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-60h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-60h]
  HKEY hKey; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int64 v14; // [rsp+58h] [rbp-28h] BYREF
  HKEY *p_hKey; // [rsp+60h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-18h] BYREF
  char v17; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  unsigned int v19; // [rsp+A8h] [rbp+28h] BYREF
  DWORD dwDisposition; // [rsp+B0h] [rbp+30h] BYREF
  HKEY v21; // [rsp+B8h] [rbp+38h] BYREF

  hKey = 0;
  p_hKey = &hKey;
  phkResult = 0;
  v17 = 1;
  v2 = RegOpenCurrentUser(0x20019u, &phkResult);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( v2 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x2E2,
           (unsigned int)"onecoreuap\\ds\\security\\efs\\common\\lib\\efsenv.cxx",
           (const char *)v2,
           dwOptions);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v3;
  }
  v21 = 0;
  dwDisposition = 0;
  p_hKey = &v21;
  phkResult = 0;
  v17 = 1;
  v5 = RegCreateKeyExW(
         hKey,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\EFS\\RMS",
         0,
         0,
         0,
         2u,
         0,
         &phkResult,
         &dwDisposition);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( v5 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x2EE,
           (unsigned int)"onecoreuap\\ds\\security\\efs\\common\\lib\\efsenv.cxx",
           (const char *)v5,
           dwOptionsa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v21);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v3;
  }
  if ( a1 )
  {
    v14 = 0;
    v7 = StringCbLengthW(a1, 0xFFFFFFFE, &v14);
    v3 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F7,
        (unsigned int)"onecoreuap\\ds\\security\\efs\\common\\lib\\efsenv.cxx",
        (const char *)(unsigned int)v7,
        dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v21);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v3;
    }
    v19 = 0;
    v8 = ULongLongToULong(v14, &v19);
    v3 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F9,
        (unsigned int)"onecoreuap\\ds\\security\\efs\\common\\lib\\efsenv.cxx",
        (const char *)(unsigned int)v8,
        dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v21);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v3;
    }
    if ( v19 + 2 < v19 )
    {
      v3 = -2147024362;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2FA,
        (unsigned int)"onecoreuap\\ds\\security\\efs\\common\\lib\\efsenv.cxx",
        (const char *)0x80070216LL,
        dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v21);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v3;
    }
    v9 = RegSetValueExW(v21, L"OwnerEmailId", 0, 1u, (const BYTE *)a1, v19 + 2);
    if ( v9 )
    {
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x301,
             (unsigned int)"onecoreuap\\ds\\security\\efs\\common\\lib\\efsenv.cxx",
             (const char *)v9,
             dwOptionsb);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v21);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v3;
    }
  }
  else
  {
    v6 = RegDeleteValueW(v21, L"OwnerEmailId");
    if ( v6 )
    {
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x2F2,
             (unsigned int)"onecoreuap\\ds\\security\\efs\\common\\lib\\efsenv.cxx",
             (const char *)v6,
             dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v21);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v3;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v21);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x180061bb4  push    rbp
0x180061bb6  push    rbx
0x180061bb7  push    rdi
0x180061bb8  mov     rbp, rsp
0x180061bbb  sub     rsp, 80h
0x180061bc2  mov     rdi, rcx
0x180061bc5  mov     [rbp+hKey], 0
0x180061bcd  lea     rax, [rbp+hKey]
0x180061bd1  mov     [rbp+var_20], rax
0x180061bd5  mov     [rbp+phkResult], 0
0x180061bdd  mov     [rbp+var_10], 1
0x180061be1  lea     rdx, [rbp+phkResult]; phkResult
0x180061be5  mov     ecx, 20019h; samDesired
0x180061bea  call    cs:__imp_RegOpenCurrentUser
0x180061bf0  mov     ebx, eax
0x180061bf2  lea     rcx, [rbp+var_20]
0x180061bf6  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180061bfb  test    ebx, ebx
0x180061bfd  jz      short loc_180061C2A
0x180061bff  mov     rcx, [rbp+18h]; this
0x180061c03  mov     r9d, ebx; char *
0x180061c06  lea     r8, aOnecoreuapDsSe_6; "onecoreuap\\ds\\security\\efs\\common\\"...
0x180061c0d  mov     edx, 2E2h; void *
0x180061c12  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180061c17  mov     ebx, eax
0x180061c19  lea     rcx, [rbp+hKey]
0x180061c1d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180061c22  nop
0x180061c23  mov     eax, ebx
0x180061c25  jmp     loc_180061E70
0x180061c2a  mov     [rbp+arg_18], 0
0x180061c32  mov     [rbp+dwDisposition], 0
0x180061c39  lea     rax, [rbp+arg_18]
0x180061c3d  mov     [rbp+var_20], rax
0x180061c41  mov     [rbp+phkResult], 0
0x180061c49  mov     [rbp+var_10], 1
0x180061c4d  lea     rax, [rbp+dwDisposition]
0x180061c51  mov     [rsp+80h+lpdwDisposition], rax; lpdwDisposition
0x180061c56  lea     rax, [rbp+phkResult]
0x180061c5a  mov     [rsp+80h+var_48], rax; phkResult
0x180061c5f  mov     [rsp+80h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180061c68  mov     [rsp+80h+samDesired], 2; samDesired
0x180061c70  mov     [rsp+80h+dwOptions], 0; int
0x180061c78  xor     r9d, r9d; lpClass
0x180061c7b  xor     r8d, r8d; Reserved
0x180061c7e  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x180061c85  mov     rcx, [rbp+hKey]; hKey
0x180061c89  call    cs:__imp_RegCreateKeyExW
0x180061c8f  mov     ebx, eax
0x180061c91  lea     rcx, [rbp+var_20]
0x180061c95  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180061c9a  test    ebx, ebx
0x180061c9c  jz      short loc_180061CD1
0x180061c9e  mov     rcx, [rbp+18h]; this
0x180061ca2  mov     r9d, ebx; char *
0x180061ca5  lea     r8, aOnecoreuapDsSe_6; "onecoreuap\\ds\\security\\efs\\common\\"...
0x180061cac  mov     edx, 2EEh; void *
0x180061cb1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180061cb6  mov     ebx, eax
0x180061cb8  lea     rcx, [rbp+arg_18]
0x180061cbc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180061cc1  nop
0x180061cc2  lea     rcx, [rbp+hKey]
0x180061cc6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180061ccb  nop
0x180061ccc  jmp     loc_180061C23
0x180061cd1  test    rdi, rdi
0x180061cd4  jnz     short loc_180061D22
0x180061cd6  lea     rdx, aOwneremailid; "OwnerEmailId"
0x180061cdd  mov     rcx, [rbp+arg_18]; hKey
0x180061ce1  call    cs:__imp_RegDeleteValueW
0x180061ce7  test    eax, eax
0x180061ce9  jz      loc_180061E5A
0x180061cef  mov     rcx, [rbp+18h]; this
0x180061cf3  mov     r9d, eax; char *
0x180061cf6  lea     r8, aOnecoreuapDsSe_6; "onecoreuap\\ds\\security\\efs\\common\\"...
0x180061cfd  mov     edx, 2F2h; void *
0x180061d02  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180061d07  mov     ebx, eax
0x180061d09  lea     rcx, [rbp+arg_18]
0x180061d0d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180061d12  nop
0x180061d13  lea     rcx, [rbp+hKey]
0x180061d17  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180061d1c  nop
0x180061d1d  jmp     loc_180061C23
0x180061d22  mov     [rbp+var_28], 0
0x180061d2a  lea     r8, [rbp+var_28]; unsigned __int64 *
0x180061d2e  mov     edx, 0FFFFFFFEh; unsigned __int64
0x180061d33  mov     rcx, rdi; unsigned __int16 *
0x180061d36  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180061d3b  mov     ebx, eax
0x180061d3d  test    eax, eax
0x180061d3f  jns     short loc_180061D73
0x180061d41  mov     rcx, [rbp+18h]; this
0x180061d45  mov     r9d, eax; char *
0x180061d48  lea     r8, aOnecoreuapDsSe_6; "onecoreuap\\ds\\security\\efs\\common\\"...
0x180061d4f  mov     edx, 2F7h; void *
0x180061d54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061d59  nop
0x180061d5a  lea     rcx, [rbp+arg_18]
0x180061d5e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180061d63  nop
0x180061d64  lea     rcx, [rbp+hKey]
0x180061d68  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180061d6d  nop
0x180061d6e  jmp     loc_180061C23
0x180061d73  mov     [rbp+arg_8], 0
0x180061d7a  lea     rdx, [rbp+arg_8]; unsigned int *
0x180061d7e  mov     rcx, [rbp+var_28]; unsigned __int64
0x180061d82  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180061d87  mov     ebx, eax
0x180061d89  test    eax, eax
0x180061d8b  jns     short loc_180061DBF
0x180061d8d  mov     rcx, [rbp+18h]; this
0x180061d91  mov     r9d, eax; char *
0x180061d94  lea     r8, aOnecoreuapDsSe_6; "onecoreuap\\ds\\security\\efs\\common\\"...
0x180061d9b  mov     edx, 2F9h; void *
0x180061da0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061da5  nop
0x180061da6  lea     rcx, [rbp+arg_18]
0x180061daa  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180061daf  nop
0x180061db0  lea     rcx, [rbp+hKey]
0x180061db4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180061db9  nop
0x180061dba  jmp     loc_180061C23
0x180061dbf  mov     eax, [rbp+arg_8]
0x180061dc2  lea     ecx, [rax+2]
0x180061dc5  cmp     ecx, eax
0x180061dc7  jnb     short loc_180061E00
0x180061dc9  mov     rcx, [rbp+18h]; this
0x180061dcd  mov     ebx, 80070216h
0x180061dd2  mov     r9d, ebx; char *
0x180061dd5  lea     r8, aOnecoreuapDsSe_6; "onecoreuap\\ds\\security\\efs\\common\\"...
0x180061ddc  mov     edx, 2FAh; void *
0x180061de1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061de6  nop
0x180061de7  lea     rcx, [rbp+arg_18]
0x180061deb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180061df0  nop
0x180061df1  lea     rcx, [rbp+hKey]
0x180061df5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180061dfa  nop
0x180061dfb  jmp     loc_180061C23
0x180061e00  mov     [rsp+80h+samDesired], ecx; cbData
0x180061e04  mov     qword ptr [rsp+80h+dwOptions], rdi; unsigned int
0x180061e09  mov     r9d, 1; dwType
0x180061e0f  xor     r8d, r8d; Reserved
0x180061e12  lea     rdx, aOwneremailid; "OwnerEmailId"
0x180061e19  mov     rcx, [rbp+arg_18]; hKey
0x180061e1d  call    cs:__imp_RegSetValueExW
0x180061e23  test    eax, eax
0x180061e25  jz      short loc_180061E5A
0x180061e27  mov     rcx, [rbp+18h]; this
0x180061e2b  mov     r9d, eax; char *
0x180061e2e  lea     r8, aOnecoreuapDsSe_6; "onecoreuap\\ds\\security\\efs\\common\\"...
0x180061e35  mov     edx, 301h; void *
0x180061e3a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180061e3f  mov     ebx, eax
0x180061e41  lea     rcx, [rbp+arg_18]
0x180061e45  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180061e4a  nop
0x180061e4b  lea     rcx, [rbp+hKey]
0x180061e4f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180061e54  nop
0x180061e55  jmp     loc_180061C23
0x180061e5a  lea     rcx, [rbp+arg_18]
0x180061e5e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180061e63  nop
0x180061e64  lea     rcx, [rbp+hKey]
0x180061e68  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180061e6d  nop
0x180061e6e  xor     eax, eax
0x180061e70  add     rsp, 80h
0x180061e77  pop     rdi
0x180061e78  pop     rbx
0x180061e79  pop     rbp
0x180061e7a  retn
```
