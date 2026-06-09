# SetUpLimitedCertRequest(HKEY__ *,ushort *,ulong,IX509CertificateRequestPkcs7 * *)

- ea: `0x180038cf4`
- end: `0x1800392a9`
- name: `?SetUpLimitedCertRequest@@YAJPEAUHKEY__@@PEAGKPEAPEAUIX509CertificateRequestPkcs7@@@Z`
- size: `1461`
- prototype: `__int64 __fastcall(HKEY, unsigned __int16 *, unsigned int, struct IX509CertificateRequestPkcs7 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180037f5c`

## callees

- `0x1800026d0`
- `0x18000b0f4`
- `0x180036bec`
- `0x180038cf4`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038d53`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038e5d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038f25`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038d53`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038e5d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038f25`
- `OLEAUT32!__imp_SysAllocString` at `0x180038df3`
- `OLEAUT32!__imp_SysAllocString` at `0x180038df3`
- `OLEAUT32!__imp_SysFreeString` at `0x180038ebc`
- `OLEAUT32!__imp_SysFreeString` at `0x180038f84`
- `OLEAUT32!__imp_SysFreeString` at `0x180039014`
- `OLEAUT32!__imp_SysFreeString` at `0x1800390a6`
- `OLEAUT32!__imp_SysFreeString` at `0x18003913b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800391f1`
- `OLEAUT32!__imp_SysFreeString` at `0x18003925c`
- `OLEAUT32!__imp_SysFreeString` at `0x180038ebc`
- `OLEAUT32!__imp_SysFreeString` at `0x180038f84`
- `OLEAUT32!__imp_SysFreeString` at `0x180039014`
- `OLEAUT32!__imp_SysFreeString` at `0x1800390a6`
- `OLEAUT32!__imp_SysFreeString` at `0x18003913b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800391f1`
- `OLEAUT32!__imp_SysFreeString` at `0x18003925c`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall SetUpLimitedCertRequest(
        HKEY a1,
        unsigned __int16 *a2,
        char a3,
        struct IX509CertificateRequestPkcs7 **a4)
{
  HRESULT v8; // eax
  bool v9; // dl
  unsigned int v10; // r9d
  unsigned int v11; // ebx
  int CryptoProvider; // eax
  BSTR v14; // rbx
  HRESULT Instance; // eax
  unsigned int v16; // edi
  LPVOID v17; // rcx
  HRESULT v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  struct IX509CertificateRequestPkcs7 *v23; // rax
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  int ppvb; // [rsp+20h] [rbp-E0h]
  LPVOID v27; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v28; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v29[2]; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR psz[256]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v27 = 0;
  v8 = CoCreateInstance(
         &GUID_884e2044_217d_11da_b2a4_000e7bbb2b09,
         0,
         1u,
         &GUID_728ab344_217d_11da_b2a4_000e7bbb2b09,
         &v27);
  v11 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E9,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
      (const char *)(unsigned int)v8,
      ppv);
    if ( v27 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
    return v11;
  }
  psz[0] = 0;
  CryptoProvider = GetCryptoProvider(a1, v9, psz, v10);
  v11 = CryptoProvider;
  if ( CryptoProvider < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8ED,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
      (const char *)(unsigned int)CryptoProvider,
      ppv);
    if ( v27 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
    return v11;
  }
  v14 = SysAllocString(psz);
  v29[1] = v14;
  if ( !v14 )
  {
    if ( v27 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
    return 2147942414LL;
  }
  v28 = 0;
  v29[0] = 0;
  Instance = CoCreateInstance(
               &GUID_884e2007_217d_11da_b2a4_000e7bbb2b09,
               0,
               1u,
               &GUID_728ab307_217d_11da_b2a4_000e7bbb2b09,
               v29);
  v16 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8FB,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
    if ( v28 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
    if ( v29[0] )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29[0] + 16LL))(v29[0]);
    SysFreeString(v14);
    if ( v27 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
    return v16;
  }
  v17 = v28;
  v28 = 0;
  if ( v17 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
  v18 = CoCreateInstance(
          &GUID_884e2008_217d_11da_b2a4_000e7bbb2b09,
          0,
          1u,
          &GUID_728ab308_217d_11da_b2a4_000e7bbb2b09,
          &v28);
  v16 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x902,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
      (const char *)(unsigned int)v18,
      ppvb);
    if ( v28 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
    if ( v29[0] )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29[0] + 16LL))(v29[0]);
    SysFreeString(v14);
    if ( v27 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
    return v16;
  }
  v19 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)v29[0] + 56LL))(v29[0], v14);
  v16 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x904,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
      (const char *)(unsigned int)v19,
      ppvb);
    if ( v28 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
    if ( v29[0] )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29[0] + 16LL))(v29[0]);
    SysFreeString(v14);
    if ( v27 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
    return v16;
  }
  v20 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)v28 + 80LL))(v28, v29[0]);
  v16 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x905,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
      (const char *)(unsigned int)v20,
      ppvb);
    if ( v28 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
    if ( v29[0] )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29[0] + 16LL))(v29[0]);
    SysFreeString(v14);
    if ( v27 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
    return v16;
  }
  v21 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)v27 + 208LL))(v27, v28);
  v16 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x906,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
      (const char *)(unsigned int)v21,
      ppvb);
    if ( v28 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
    if ( v29[0] )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29[0] + 16LL))(v29[0]);
    SysFreeString(v14);
    if ( v27 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
    return v16;
  }
  v22 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, unsigned __int16 *))(*(_QWORD *)v27 + 264LL))(
          v27,
          (unsigned int)((a3 & 4) != 0) + 1,
          1,
          a2);
  v16 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x90C,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
      (const char *)(unsigned int)v22,
      12);
    if ( v28 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
    if ( v29[0] )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29[0] + 16LL))(v29[0]);
    SysFreeString(v14);
    if ( v27 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
    return v16;
  }
  v23 = (struct IX509CertificateRequestPkcs7 *)v27;
  v27 = 0;
  *a4 = v23;
  if ( v28 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
  if ( v29[0] )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29[0] + 16LL))(v29[0]);
  SysFreeString(v14);
  if ( v27 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
  return 0;
}

```

## disassembly

```asm
0x180038cf4  mov     [rsp-8+arg_10], rbx
0x180038cf9  push    rbp
0x180038cfa  push    rsi
0x180038cfb  push    rdi
0x180038cfc  push    r14
0x180038cfe  push    r15
0x180038d00  lea     rbp, [rsp-170h]
0x180038d08  sub     rsp, 270h
0x180038d0f  mov     rax, cs:__security_cookie
0x180038d16  xor     rax, rsp
0x180038d19  mov     [rbp+190h+var_30], rax
0x180038d20  mov     r14, r9
0x180038d23  mov     esi, r8d
0x180038d26  mov     r15, rdx
0x180038d29  mov     rdi, rcx
0x180038d2c  mov     [rsp+290h+var_250], 0
0x180038d35  lea     rax, [rsp+290h+var_250]
0x180038d3a  mov     [rsp+290h+ppv], rax; int
0x180038d3f  lea     r9, _GUID_728ab344_217d_11da_b2a4_000e7bbb2b09; riid
0x180038d46  xor     edx, edx; pUnkOuter
0x180038d48  lea     r8d, [rdx+1]; dwClsContext
0x180038d4c  lea     rcx, _GUID_884e2044_217d_11da_b2a4_000e7bbb2b09; rclsid
0x180038d53  call    cs:__imp_CoCreateInstance
0x180038d5a  nop     dword ptr [rax+rax+00h]
0x180038d5f  mov     ebx, eax
0x180038d61  test    eax, eax
0x180038d63  jns     short loc_180038D9F
0x180038d65  mov     rcx, [rbp+198h]; this
0x180038d6c  mov     r9d, eax; char *
0x180038d6f  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180038d76  mov     edx, 8E9h; void *
0x180038d7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038d80  nop
0x180038d81  mov     rcx, [rsp+290h+var_250]
0x180038d86  test    rcx, rcx
0x180038d89  jz      short loc_180038D98
0x180038d8b  mov     rax, [rcx]
0x180038d8e  mov     rax, [rax+10h]
0x180038d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d97  nop
0x180038d98  mov     eax, ebx
0x180038d9a  jmp     loc_180039282
0x180038d9f  xor     eax, eax
0x180038da1  mov     [rsp+290h+psz], ax
0x180038da6  lea     r8, [rsp+290h+psz]; unsigned __int16 *
0x180038dab  mov     rcx, rdi; HKEY
0x180038dae  call    ?GetCryptoProvider@@YAJPEAUHKEY__@@_NPEAGK@Z; GetCryptoProvider(HKEY__ *,bool,ushort *,ulong)
0x180038db3  mov     ebx, eax
0x180038db5  test    eax, eax
0x180038db7  jns     short loc_180038DEE
0x180038db9  mov     rcx, [rbp+198h]; this
0x180038dc0  mov     r9d, eax; char *
0x180038dc3  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180038dca  mov     edx, 8EDh; void *
0x180038dcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038dd4  nop
0x180038dd5  mov     rcx, [rsp+290h+var_250]
0x180038dda  test    rcx, rcx
0x180038ddd  jz      short loc_180038DEC
0x180038ddf  mov     rax, [rcx]
0x180038de2  mov     rax, [rax+10h]
0x180038de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038deb  nop
0x180038dec  jmp     short loc_180038D98
0x180038dee  lea     rcx, [rsp+290h+psz]; psz
0x180038df3  call    cs:__imp_SysAllocString
0x180038dfa  nop     dword ptr [rax+rax+00h]
0x180038dff  mov     rbx, rax
0x180038e02  mov     [rsp+290h+var_238], rax
0x180038e07  test    rax, rax
0x180038e0a  jnz     short loc_180038E2D
0x180038e0c  mov     rcx, [rsp+290h+var_250]
0x180038e11  test    rcx, rcx
0x180038e14  jz      short loc_180038E23
0x180038e16  mov     rax, [rcx]
0x180038e19  mov     rax, [rax+10h]
0x180038e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e22  nop
0x180038e23  mov     eax, 8007000Eh
0x180038e28  jmp     loc_180039282
0x180038e2d  mov     [rsp+290h+var_248], 0
0x180038e36  mov     [rsp+290h+var_240], 0
0x180038e3f  lea     rax, [rsp+290h+var_240]
0x180038e44  mov     [rsp+290h+ppv], rax; int
0x180038e49  lea     r9, _GUID_728ab307_217d_11da_b2a4_000e7bbb2b09; riid
0x180038e50  xor     edx, edx; pUnkOuter
0x180038e52  lea     r8d, [rdx+1]; dwClsContext
0x180038e56  lea     rcx, _GUID_884e2007_217d_11da_b2a4_000e7bbb2b09; rclsid
0x180038e5d  call    cs:__imp_CoCreateInstance
0x180038e64  nop     dword ptr [rax+rax+00h]
0x180038e69  mov     edi, eax
0x180038e6b  test    eax, eax
0x180038e6d  jns     short loc_180038EE7
0x180038e6f  mov     rcx, [rbp+198h]; this
0x180038e76  mov     r9d, eax; char *
0x180038e79  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180038e80  mov     edx, 8FBh; void *
0x180038e85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038e8a  nop
0x180038e8b  mov     rcx, [rsp+290h+var_248]
0x180038e90  test    rcx, rcx
0x180038e93  jz      short loc_180038EA2
0x180038e95  mov     rax, [rcx]
0x180038e98  mov     rax, [rax+10h]
0x180038e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ea1  nop
0x180038ea2  mov     rcx, [rsp+290h+var_240]
0x180038ea7  test    rcx, rcx
0x180038eaa  jz      short loc_180038EB9
0x180038eac  mov     rax, [rcx]
0x180038eaf  mov     rax, [rax+10h]
0x180038eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038eb8  nop
0x180038eb9  mov     rcx, rbx; bstrString
0x180038ebc  call    cs:__imp_SysFreeString
0x180038ec3  nop     dword ptr [rax+rax+00h]
0x180038ec8  nop
0x180038ec9  mov     rcx, [rsp+290h+var_250]
0x180038ece  test    rcx, rcx
0x180038ed1  jz      short loc_180038EE0
0x180038ed3  mov     rax, [rcx]
0x180038ed6  mov     rax, [rax+10h]
0x180038eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038edf  nop
0x180038ee0  mov     eax, edi
0x180038ee2  jmp     loc_180039282
0x180038ee7  mov     rcx, [rsp+290h+var_248]
0x180038eec  mov     [rsp+290h+var_248], 0
0x180038ef5  test    rcx, rcx
0x180038ef8  jz      short loc_180038F07
0x180038efa  mov     rax, [rcx]
0x180038efd  mov     rax, [rax+10h]
0x180038f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f06  nop
0x180038f07  lea     rax, [rsp+290h+var_248]
0x180038f0c  mov     [rsp+290h+ppv], rax; int
0x180038f11  lea     r9, _GUID_728ab308_217d_11da_b2a4_000e7bbb2b09; riid
0x180038f18  xor     edx, edx; pUnkOuter
0x180038f1a  lea     r8d, [rdx+1]; dwClsContext
0x180038f1e  lea     rcx, _GUID_884e2008_217d_11da_b2a4_000e7bbb2b09; rclsid
0x180038f25  call    cs:__imp_CoCreateInstance
0x180038f2c  nop     dword ptr [rax+rax+00h]
0x180038f31  mov     edi, eax
0x180038f33  test    eax, eax
0x180038f35  jns     short loc_180038FAD
0x180038f37  mov     rcx, [rbp+198h]; this
0x180038f3e  mov     r9d, eax; char *
0x180038f41  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180038f48  mov     edx, 902h; void *
0x180038f4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038f52  nop
0x180038f53  mov     rcx, [rsp+290h+var_248]
0x180038f58  test    rcx, rcx
0x180038f5b  jz      short loc_180038F6A
0x180038f5d  mov     rax, [rcx]
0x180038f60  mov     rax, [rax+10h]
0x180038f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f69  nop
0x180038f6a  mov     rcx, [rsp+290h+var_240]
0x180038f6f  test    rcx, rcx
0x180038f72  jz      short loc_180038F81
0x180038f74  mov     rax, [rcx]
0x180038f77  mov     rax, [rax+10h]
0x180038f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f80  nop
0x180038f81  mov     rcx, rbx; bstrString
0x180038f84  call    cs:__imp_SysFreeString
0x180038f8b  nop     dword ptr [rax+rax+00h]
0x180038f90  nop
0x180038f91  mov     rcx, [rsp+290h+var_250]
0x180038f96  test    rcx, rcx
0x180038f99  jz      short loc_180038FA8
0x180038f9b  mov     rax, [rcx]
0x180038f9e  mov     rax, [rax+10h]
0x180038fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038fa7  nop
0x180038fa8  jmp     loc_180038EE0
0x180038fad  mov     rcx, [rsp+290h+var_240]
0x180038fb2  mov     rax, [rcx]
0x180038fb5  mov     rdx, rbx
0x180038fb8  mov     rax, [rax+38h]
0x180038fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038fc1  mov     edi, eax
0x180038fc3  test    eax, eax
0x180038fc5  jns     short loc_18003903D
0x180038fc7  mov     rcx, [rbp+198h]; this
0x180038fce  mov     r9d, eax; char *
0x180038fd1  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180038fd8  mov     edx, 904h; void *
0x180038fdd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038fe2  nop
0x180038fe3  mov     rcx, [rsp+290h+var_248]
0x180038fe8  test    rcx, rcx
0x180038feb  jz      short loc_180038FFA
0x180038fed  mov     rax, [rcx]
0x180038ff0  mov     rax, [rax+10h]
0x180038ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ff9  nop
0x180038ffa  mov     rcx, [rsp+290h+var_240]
0x180038fff  test    rcx, rcx
0x180039002  jz      short loc_180039011
0x180039004  mov     rax, [rcx]
0x180039007  mov     rax, [rax+10h]
0x18003900b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039010  nop
0x180039011  mov     rcx, rbx; bstrString
0x180039014  call    cs:__imp_SysFreeString
0x18003901b  nop     dword ptr [rax+rax+00h]
0x180039020  nop
0x180039021  mov     rcx, [rsp+290h+var_250]
0x180039026  test    rcx, rcx
0x180039029  jz      short loc_180039038
0x18003902b  mov     rax, [rcx]
0x18003902e  mov     rax, [rax+10h]
0x180039032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039037  nop
0x180039038  jmp     loc_180038EE0
0x18003903d  mov     rcx, [rsp+290h+var_248]
0x180039042  mov     rax, [rcx]
0x180039045  mov     rdx, [rsp+290h+var_240]
0x18003904a  mov     rax, [rax+50h]
0x18003904e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039053  mov     edi, eax
0x180039055  test    eax, eax
0x180039057  jns     short loc_1800390CF
0x180039059  mov     rcx, [rbp+198h]; this
0x180039060  mov     r9d, eax; char *
0x180039063  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003906a  mov     edx, 905h; void *
0x18003906f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039074  nop
0x180039075  mov     rcx, [rsp+290h+var_248]
0x18003907a  test    rcx, rcx
0x18003907d  jz      short loc_18003908C
0x18003907f  mov     rax, [rcx]
0x180039082  mov     rax, [rax+10h]
0x180039086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003908b  nop
0x18003908c  mov     rcx, [rsp+290h+var_240]
0x180039091  test    rcx, rcx
0x180039094  jz      short loc_1800390A3
0x180039096  mov     rax, [rcx]
0x180039099  mov     rax, [rax+10h]
0x18003909d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800390a2  nop
0x1800390a3  mov     rcx, rbx; bstrString
0x1800390a6  call    cs:__imp_SysFreeString
0x1800390ad  nop     dword ptr [rax+rax+00h]
0x1800390b2  nop
0x1800390b3  mov     rcx, [rsp+290h+var_250]
0x1800390b8  test    rcx, rcx
0x1800390bb  jz      short loc_1800390CA
0x1800390bd  mov     rax, [rcx]
0x1800390c0  mov     rax, [rax+10h]
0x1800390c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800390c9  nop
0x1800390ca  jmp     loc_180038EE0
0x1800390cf  mov     rcx, [rsp+290h+var_250]
0x1800390d4  mov     rax, [rcx]
0x1800390d7  mov     rdx, [rsp+290h+var_248]
0x1800390dc  mov     rax, [rax+0D0h]
0x1800390e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800390e8  mov     edi, eax
0x1800390ea  test    eax, eax
0x1800390ec  jns     short loc_180039164
0x1800390ee  mov     rcx, [rbp+198h]; this
0x1800390f5  mov     r9d, eax; char *
0x1800390f8  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800390ff  mov     edx, 906h; void *
0x180039104  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039109  nop
0x18003910a  mov     rcx, [rsp+290h+var_248]
0x18003910f  test    rcx, rcx
0x180039112  jz      short loc_180039121
0x180039114  mov     rax, [rcx]
0x180039117  mov     rax, [rax+10h]
0x18003911b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039120  nop
0x180039121  mov     rcx, [rsp+290h+var_240]
0x180039126  test    rcx, rcx
0x180039129  jz      short loc_180039138
0x18003912b  mov     rax, [rcx]
0x18003912e  mov     rax, [rax+10h]
0x180039132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039137  nop
0x180039138  mov     rcx, rbx; bstrString
0x18003913b  call    cs:__imp_SysFreeString
0x180039142  nop     dword ptr [rax+rax+00h]
0x180039147  nop
0x180039148  mov     rcx, [rsp+290h+var_250]
0x18003914d  test    rcx, rcx
0x180039150  jz      short loc_18003915F
0x180039152  mov     rax, [rcx]
0x180039155  mov     rax, [rax+10h]
0x180039159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003915e  nop
0x18003915f  jmp     loc_180038EE0
0x180039164  mov     rcx, [rsp+290h+var_250]
0x180039169  mov     rax, [rcx]
0x18003916c  mov     r8d, 1
  ... truncated ...
```
