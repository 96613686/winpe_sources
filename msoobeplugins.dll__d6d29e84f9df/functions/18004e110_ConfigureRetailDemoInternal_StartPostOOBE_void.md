# ConfigureRetailDemoInternal::StartPostOOBE(void)

- ea: `0x18004e110`
- end: `0x18004e5a0`
- name: `?StartPostOOBE@ConfigureRetailDemoInternal@@UEAAJXZ`
- size: `1168`
- prototype: `__int64 __fastcall(ConfigureRetailDemoInternal *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004e5b0`

## callees

- `0x180003470`
- `0x180007bbc`
- `0x180008544`
- `0x180008a60`
- `0x18001de58`
- `0x18001e9a4`
- `0x180021988`
- `0x1800230b0`
- `0x180023574`
- `0x180031ff0`
- `0x18004d7f4`
- `0x18004dbc4`
- `0x18004e110`
- `0x18004e628`
- `0x18004e83c`
- `0x1800b3cb4`
- `0x1800b3d74`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004e2c0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004e2f1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004e2c0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004e2f1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004e1ab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004e1ab`
- `USER32!ExitWindowsEx` at `0x18004e54f`
- `USER32!ExitWindowsEx` at `0x18004e54f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e481`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e4f7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e481`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e4f7`
- `samcli!NetUserEnum` at `0x18004e178`
- `samcli!NetUserEnum` at `0x18004e178`
- `samcli!NetUserSetInfo` at `0x18004e328`
- `samcli!NetUserSetInfo` at `0x18004e328`
- `netutils!NetApiBufferFree` at `0x18004e579`
- `netutils!NetApiBufferFree` at `0x18004e579`

## string_xrefs

- `0x18004e1fc`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x18004e3ee`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x18004e18a`: `shell\oobe\machine\plugins\retaildemo\retaildemoplugin.cpp`
- `0x18004e338`: `shell\oobe\machine\plugins\retaildemo\retaildemoplugin.cpp`
- `0x18004e372`: `shell\oobe\machine\plugins\retaildemo\retaildemoplugin.cpp`
- `0x18004e3a2`: `shell\oobe\machine\plugins\retaildemo\retaildemoplugin.cpp`
- `0x18004e3c3`: `shell\oobe\machine\plugins\retaildemo\retaildemoplugin.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ConfigureRetailDemoInternal::StartPostOOBE(ConfigureRetailDemoInternal *this)
{
  DWORD v1; // eax
  LPBYTE *p_bufptr; // rcx
  void *v3; // rdx
  unsigned __int16 *v4; // rbx
  unsigned int v5; // r8d
  const char *v6; // r9
  int v7; // eax
  int v8; // eax
  ConfigureRetailDemoInternal *v9; // rcx
  int v10; // r15d
  DWORD v11; // r14d
  const WCHAR *v12; // rdi
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int started; // eax
  ConfigureRetailDemoInternal *v17; // rcx
  unsigned int v18; // ebx
  __int64 v19; // rdx
  HRESULT v20; // eax
  __int64 v21; // rdx
  HRESULT v22; // eax
  const unsigned __int16 *v23; // rdx
  int prefmaxlen; // [rsp+20h] [rbp-89h]
  int prefmaxlena; // [rsp+20h] [rbp-89h]
  int prefmaxlenb; // [rsp+20h] [rbp-89h]
  int prefmaxlenc; // [rsp+20h] [rbp-89h]
  DWORD entriesread; // [rsp+40h] [rbp-69h] BYREF
  LPBYTE bufptr; // [rsp+48h] [rbp-61h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-59h] BYREF
  LPCWCH v32; // [rsp+58h] [rbp-51h] BYREF
  LPVOID v33; // [rsp+60h] [rbp-49h] BYREF
  LPCWCH lpString2; // [rsp+68h] [rbp-41h] BYREF
  DWORD resume_handle; // [rsp+70h] [rbp-39h] BYREF
  DWORD totalentries; // [rsp+74h] [rbp-35h] BYREF
  BYTE buf[8]; // [rsp+78h] [rbp-31h] BYREF
  unsigned __int64 v38; // [rsp+80h] [rbp-29h]
  _QWORD v39[2]; // [rsp+88h] [rbp-21h] BYREF
  char v40; // [rsp+98h] [rbp-11h]
  _BYTE v41[32]; // [rsp+A0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  bufptr = 0;
  entriesread = 0;
  totalentries = 0;
  resume_handle = 0;
  v1 = NetUserEnum(0, 0, 2u, &bufptr, 0xFFFFFFFF, &entriesread, &totalentries, &resume_handle);
  p_bufptr = &bufptr;
  v39[1] = &bufptr;
  v40 = 1;
  if ( !v1 )
  {
    v38 = entriesread << 8;
    v4 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v38);
    v39[0] = v4;
    if ( v4 )
    {
      lpString2 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &lpString2,
        0);
      v7 = SHRegAllocData(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
             L"AdminAccount",
             2u,
             (void **)&lpString2,
             0);
      if ( v7 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x117,
          (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemoplugin.cpp",
          (const char *)(unsigned int)v7,
          prefmaxlena);
      v32 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v32,
        0);
      v8 = SHRegAllocData(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
             L"DefaultAccountSAMName",
             2u,
             (void **)&v32,
             0);
      v9 = retaddr;
      if ( v8 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x119,
          (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemoplugin.cpp",
          (const char *)(unsigned int)v8,
          prefmaxlen);
      v10 = 0;
      v11 = 0;
      if ( entriesread )
      {
        v12 = lpString2;
        do
        {
          if ( !ConfigureRetailDemoInternal::IsBuiltInUser(v9, *(const unsigned __int16 **)&bufptr[8 * v11])
            && (!v12 || CompareStringOrdinal(*(LPCWCH *)&bufptr[8 * v11], -1, v12, -1, 1) != 2)
            && (!v32 || CompareStringOrdinal(*(LPCWCH *)&bufptr[8 * v11], -1, v32, -1, 1) != 2) )
          {
            *(_DWORD *)buf = 3;
            if ( NetUserSetInfo(0, *(LPCWSTR *)&bufptr[8 * v11], 0x3F0u, buf, 0) )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x126,
                (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemoplugin.cpp",
                (const char *)0x8000FFFFLL,
                prefmaxlen);
            if ( v10 > 0 )
            {
              v13 = StringCchCatW(v4, v38, L",");
              if ( v13 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x12A,
                  (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemoplugin.cpp",
                  (const char *)(unsigned int)v13,
                  prefmaxlen);
            }
            v14 = StringCchCatW(v4, v38, *(const unsigned __int16 **)&bufptr[8 * v11]);
            v9 = retaddr;
            if ( v14 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x12C,
                (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemoplugin.cpp",
                (const char *)(unsigned int)v14,
                prefmaxlen);
            ++v10;
          }
          ++v11;
        }
        while ( v11 < entriesread );
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v32);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpString2);
    }
    else
    {
      wil::details::in1diag3::_Log_NullAlloc(retaddr, v3, v5, v6);
    }
    v15 = SHRegSetString(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
            L"PostOOBEAccounts",
            v4);
    if ( v15 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x131,
        (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemoplugin.cpp",
        (const char *)(unsigned int)v15,
        prefmaxlen);
    wil::details::unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>(v39);
  }
  started = ConfigureRetailDemoInternal::SetRegistryInfo((ConfigureRetailDemoInternal *)p_bufptr);
  v18 = started;
  if ( started >= 0 )
  {
    started = ConfigureRetailDemoInternal::StartRetailDemoService(v17, 1);
    v18 = started;
    if ( started < 0 )
    {
      v19 = 309;
      goto LABEL_32;
    }
    ppv = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    v20 = CoCreateInstance(
            &GUID_a8d93b39_2113_492e_b014_801d01c95eca,
            0,
            0x17u,
            &GUID_b1857662_f8e5_4ba3_8eb9_c08097932bae,
            &ppv);
    v18 = v20;
    if ( v20 >= 0 )
    {
      v20 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 24LL))(ppv);
      v18 = v20;
      if ( v20 >= 0 )
      {
        v33 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
        v22 = CoCreateInstance(
                &GUID_54337179_c8b2_4ed4_95e4_95601c850d8c,
                0,
                1u,
                &GUID_30e038f9_64c9_4a5c_ba4c_f9f7df30849c,
                &v33);
        v18 = v22;
        if ( v22 >= 0 )
        {
          (*(void (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v33 + 32LL))(v33, 0, 0, 0);
          CAutoPrivilegeEnable::CAutoPrivilegeEnable((CAutoPrivilegeEnable *)v41, v23);
          ExitWindowsEx(2u, 0x10u);
          CAutoPrivilegeEnable::~CAutoPrivilegeEnable((CAutoPrivilegeEnable *)v41);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
          v18 = 0;
          goto LABEL_42;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x13B,
          (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemoplugin.cpp",
          (const char *)(unsigned int)v22,
          prefmaxlenc);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
        goto LABEL_36;
      }
      v21 = 312;
    }
    else
    {
      v21 = 311;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemoplugin.cpp",
      (const char *)(unsigned int)v20,
      prefmaxlenb);
LABEL_36:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    goto LABEL_42;
  }
  v19 = 308;
LABEL_32:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v19,
    (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemoplugin.cpp",
    (const char *)(unsigned int)started,
    prefmaxlen);
LABEL_42:
  NetApiBufferFree(bufptr);
  return v18;
}

```

## disassembly

```asm
0x18004e110  push    rbp
0x18004e112  push    rbx
0x18004e113  push    rdi
0x18004e114  push    r12
0x18004e116  push    r13
0x18004e118  push    r14
0x18004e11a  push    r15
0x18004e11c  lea     rbp, [rsp-27h]
0x18004e121  sub     rsp, 0D0h
0x18004e128  mov     rax, cs:__security_cookie
0x18004e12f  xor     rax, rsp
0x18004e132  mov     [rbp+57h+var_40], rax
0x18004e136  xor     r13d, r13d
0x18004e139  mov     [rbp+57h+bufptr], r13
0x18004e13d  mov     [rbp+57h+var_C0], r13d
0x18004e141  mov     [rbp+57h+var_8C], r13d
0x18004e145  mov     [rbp+57h+var_90], r13d
0x18004e149  lea     rax, [rbp+57h+var_90]
0x18004e14d  mov     [rsp+100h+resume_handle], rax; resume_handle
0x18004e152  lea     rax, [rbp+57h+var_8C]
0x18004e156  mov     [rsp+100h+totalentries], rax; totalentries
0x18004e15b  lea     rax, [rbp+57h+var_C0]
0x18004e15f  mov     [rsp+100h+entriesread], rax; entriesread
0x18004e164  mov     [rsp+100h+prefmaxlen], 0FFFFFFFFh; prefmaxlen
0x18004e16c  lea     r9, [rbp+57h+bufptr]; bufptr
0x18004e170  xor     edx, edx; level
0x18004e172  xor     ecx, ecx; servername
0x18004e174  lea     r8d, [r13+2]; filter
0x18004e178  call    cs:__imp_NetUserEnum
0x18004e17e  lea     rcx, [rbp+57h+bufptr]
0x18004e182  mov     [rbp+57h+var_70], rcx
0x18004e186  mov     [rbp+57h+var_68], 1
0x18004e18a  lea     rdi, aShellOobeMachi_50; "shell\\oobe\\machine\\plugins\\retailde"...
0x18004e191  test    eax, eax
0x18004e193  jnz     loc_18004E41F
0x18004e199  mov     eax, [rbp+57h+var_C0]
0x18004e19c  shl     eax, 8
0x18004e19f  mov     [rbp+57h+var_80], rax
0x18004e1a3  lea     rdx, [rax+rax]; uBytes
0x18004e1a7  lea     ecx, [r13+40h]; uFlags
0x18004e1ab  call    cs:__imp_LocalAlloc
0x18004e1b1  mov     rbx, rax
0x18004e1b4  mov     [rbp+57h+var_78], rax
0x18004e1b8  mov     rcx, [rbp+5Fh]; this
0x18004e1bc  mov     r12, 0FFFFFFFF80000002h
0x18004e1c3  test    rax, rax
0x18004e1c6  jnz     short loc_18004E1D2
0x18004e1c8  call    ?_Log_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_NullAlloc(void *,uint,char const *)
0x18004e1cd  jmp     loc_18004E3E4
0x18004e1d2  mov     [rbp+57h+lpString2], r13
0x18004e1d6  xor     edx, edx
0x18004e1d8  lea     rcx, [rbp+57h+lpString2]
0x18004e1dc  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004e1e1  mov     [rsp+100h+entriesread], r13; unsigned int *
0x18004e1e6  lea     rax, [rbp+57h+lpString2]
0x18004e1ea  mov     qword ptr [rsp+100h+prefmaxlen], rax; int
0x18004e1ef  mov     r9d, 2; int
0x18004e1f5  lea     r8, ?c_retailDemoValueAdminAccountName@@3QBGB; "AdminAccount"
0x18004e1fc  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004e203  mov     rcx, r12; HKEY
0x18004e206  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x18004e20b  mov     rcx, [rbp+5Fh]; this
0x18004e20f  test    eax, eax
0x18004e211  jns     short loc_18004E223
0x18004e213  mov     r9d, eax; char *
0x18004e216  mov     r8, rdi; unsigned int
0x18004e219  mov     edx, 117h; void *
0x18004e21e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004e223  mov     [rbp+57h+var_A8], r13
0x18004e227  xor     edx, edx
0x18004e229  lea     rcx, [rbp+57h+var_A8]
0x18004e22d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004e232  mov     [rsp+100h+entriesread], r13; unsigned int *
0x18004e237  lea     rax, [rbp+57h+var_A8]
0x18004e23b  mov     qword ptr [rsp+100h+prefmaxlen], rax; int
0x18004e240  mov     r9d, 2; int
0x18004e246  lea     r8, aDefaultaccount_0; "DefaultAccountSAMName"
0x18004e24d  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18004e254  mov     rcx, r12; HKEY
0x18004e257  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x18004e25c  mov     rcx, [rbp+5Fh]; this
0x18004e260  test    eax, eax
0x18004e262  jns     short loc_18004E274
0x18004e264  mov     r9d, eax; char *
0x18004e267  mov     r8, rdi; unsigned int
0x18004e26a  mov     edx, 119h; void *
0x18004e26f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004e274  mov     r15d, r13d
0x18004e277  mov     r14d, r13d
0x18004e27a  cmp     [rbp+57h+var_C0], r13d
0x18004e27e  jbe     loc_18004E3D1
0x18004e284  mov     rdi, [rbp+57h+lpString2]
0x18004e288  mov     r12d, r14d
0x18004e28b  mov     rdx, [rbp+57h+bufptr]
0x18004e28f  mov     rdx, [rdx+r12*8]; unsigned __int16 *
0x18004e293  call    ?IsBuiltInUser@ConfigureRetailDemoInternal@@IEAAHPEBG@Z; ConfigureRetailDemoInternal::IsBuiltInUser(ushort const *)
0x18004e298  test    eax, eax
0x18004e29a  jnz     loc_18004E3B6
0x18004e2a0  test    rdi, rdi
0x18004e2a3  jz      short loc_18004E2CF
0x18004e2a5  mov     [rsp+100h+prefmaxlen], 1; bIgnoreCase
0x18004e2ad  or      eax, 0FFFFFFFFh
0x18004e2b0  mov     r9d, eax; cchCount2
0x18004e2b3  mov     r8, rdi; lpString2
0x18004e2b6  mov     edx, eax; cchCount1
0x18004e2b8  mov     rcx, [rbp+57h+bufptr]
0x18004e2bc  mov     rcx, [rcx+r12*8]; lpString1
0x18004e2c0  call    cs:__imp_CompareStringOrdinal
0x18004e2c6  cmp     eax, 2
0x18004e2c9  jz      loc_18004E3B6
0x18004e2cf  cmp     [rbp+57h+var_A8], r13
0x18004e2d3  jz      short loc_18004E300
0x18004e2d5  mov     [rsp+100h+prefmaxlen], 1; bIgnoreCase
0x18004e2dd  or      eax, 0FFFFFFFFh
0x18004e2e0  mov     r9d, eax; cchCount2
0x18004e2e3  mov     r8, [rbp+57h+var_A8]; lpString2
0x18004e2e7  mov     edx, eax; cchCount1
0x18004e2e9  mov     rcx, [rbp+57h+bufptr]
0x18004e2ed  mov     rcx, [rcx+r12*8]; lpString1
0x18004e2f1  call    cs:__imp_CompareStringOrdinal
0x18004e2f7  cmp     eax, 2
0x18004e2fa  jz      loc_18004E3B6
0x18004e300  mov     dword ptr [rbp+57h+buf], 3
0x18004e307  mov     r13, [rbp+5Fh]
0x18004e30b  mov     qword ptr [rsp+100h+prefmaxlen], 0; int
0x18004e314  lea     r9, [rbp+57h+buf]; buf
0x18004e318  mov     r8d, 3F0h; level
0x18004e31e  mov     rdx, [rbp+57h+bufptr]
0x18004e322  mov     rdx, [rdx+r12*8]; username
0x18004e326  xor     ecx, ecx; servername
0x18004e328  call    cs:__imp_NetUserSetInfo
0x18004e32e  test    eax, eax
0x18004e330  jz      short loc_18004E34C
0x18004e332  mov     r9d, 8000FFFFh; char *
0x18004e338  lea     r8, aShellOobeMachi_50; "shell\\oobe\\machine\\plugins\\retailde"...
0x18004e33f  mov     edx, 126h; void *
0x18004e344  mov     rcx, r13; this
0x18004e347  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004e34c  xor     r13d, r13d
0x18004e34f  test    r15d, r15d
0x18004e352  jle     short loc_18004E383
0x18004e354  lea     r8, asc_1800E7590; ","
0x18004e35b  mov     rdx, [rbp+57h+var_80]; unsigned __int64
0x18004e35f  mov     rcx, rbx; unsigned __int16 *
0x18004e362  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004e367  mov     rcx, [rbp+5Fh]; this
0x18004e36b  test    eax, eax
0x18004e36d  jns     short loc_18004E383
0x18004e36f  mov     r9d, eax; char *
0x18004e372  lea     r8, aShellOobeMachi_50; "shell\\oobe\\machine\\plugins\\retailde"...
0x18004e379  mov     edx, 12Ah; void *
0x18004e37e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004e383  mov     r8, [rbp+57h+bufptr]
0x18004e387  mov     r8, [r8+r12*8]; unsigned __int16 *
0x18004e38b  mov     rdx, [rbp+57h+var_80]; unsigned __int64
0x18004e38f  mov     rcx, rbx; unsigned __int16 *
0x18004e392  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004e397  mov     rcx, [rbp+5Fh]; this
0x18004e39b  test    eax, eax
0x18004e39d  jns     short loc_18004E3B3
0x18004e39f  mov     r9d, eax; char *
0x18004e3a2  lea     r8, aShellOobeMachi_50; "shell\\oobe\\machine\\plugins\\retailde"...
0x18004e3a9  mov     edx, 12Ch; void *
0x18004e3ae  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004e3b3  inc     r15d
0x18004e3b6  inc     r14d
0x18004e3b9  cmp     r14d, [rbp+57h+var_C0]
0x18004e3bd  jb      loc_18004E288
0x18004e3c3  lea     rdi, aShellOobeMachi_50; "shell\\oobe\\machine\\plugins\\retailde"...
0x18004e3ca  mov     r12, 0FFFFFFFF80000002h
0x18004e3d1  lea     rcx, [rbp+57h+var_A8]
0x18004e3d5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004e3da  nop
0x18004e3db  lea     rcx, [rbp+57h+lpString2]
0x18004e3df  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004e3e4  mov     r9, rbx; unsigned __int16 *
0x18004e3e7  lea     r8, ?c_retailDemoValuePostOOBEAccounts@@3QBGB; "PostOOBEAccounts"
0x18004e3ee  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004e3f5  mov     rcx, r12; HKEY
0x18004e3f8  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18004e3fd  mov     rcx, [rbp+5Fh]; this
0x18004e401  test    eax, eax
0x18004e403  jns     short loc_18004E416
0x18004e405  mov     r9d, eax; char *
0x18004e408  mov     r8, rdi; unsigned int
0x18004e40b  mov     edx, 131h; void *
0x18004e410  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004e415  nop
0x18004e416  lea     rcx, [rbp+57h+var_78]
0x18004e41a  call    ??1?$unique_storage@U?$resource_policy@PEAU_STORAGE_DEVICE_DESCRIPTOR@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>(void)
0x18004e41f  call    ?SetRegistryInfo@ConfigureRetailDemoInternal@@IEAAJXZ; ConfigureRetailDemoInternal::SetRegistryInfo(void)
0x18004e424  mov     ebx, eax
0x18004e426  test    eax, eax
0x18004e428  jns     short loc_18004E431
0x18004e42a  mov     edx, 134h
0x18004e42f  jmp     short loc_18004E443
0x18004e431  mov     dl, 1; bool
0x18004e433  call    ?StartRetailDemoService@ConfigureRetailDemoInternal@@IEAAJ_N@Z; ConfigureRetailDemoInternal::StartRetailDemoService(bool)
0x18004e438  mov     ebx, eax
0x18004e43a  test    eax, eax
0x18004e43c  jns     short loc_18004E457
0x18004e43e  mov     edx, 135h; void *
0x18004e443  mov     r8, rdi; unsigned int
0x18004e446  mov     r9d, eax; char *
0x18004e449  mov     rcx, [rbp+5Fh]; this
0x18004e44d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e452  jmp     loc_18004E575
0x18004e457  mov     [rbp+57h+ppv], r13
0x18004e45b  lea     rcx, [rbp+57h+ppv]
0x18004e45f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e464  lea     rax, [rbp+57h+ppv]
0x18004e468  mov     qword ptr [rsp+100h+prefmaxlen], rax; int
0x18004e46d  lea     r9, _GUID_b1857662_f8e5_4ba3_8eb9_c08097932bae; riid
0x18004e474  xor     edx, edx; pUnkOuter
0x18004e476  lea     r8d, [rdx+17h]; dwClsContext
0x18004e47a  lea     rcx, _GUID_a8d93b39_2113_492e_b014_801d01c95eca; rclsid
0x18004e481  call    cs:__imp_CoCreateInstance
0x18004e487  mov     ebx, eax
0x18004e489  test    eax, eax
0x18004e48b  jns     short loc_18004E4B0
0x18004e48d  mov     edx, 137h; void *
0x18004e492  mov     r8, rdi; unsigned int
0x18004e495  mov     r9d, eax; char *
0x18004e498  mov     rcx, [rbp+5Fh]; this
0x18004e49c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e4a1  nop
0x18004e4a2  lea     rcx, [rbp+57h+ppv]
0x18004e4a6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e4ab  jmp     loc_18004E575
0x18004e4b0  mov     rcx, [rbp+57h+ppv]
0x18004e4b4  mov     rax, [rcx]
0x18004e4b7  mov     rax, [rax+18h]
0x18004e4bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e4c0  mov     ebx, eax
0x18004e4c2  test    eax, eax
0x18004e4c4  jns     short loc_18004E4CD
0x18004e4c6  mov     edx, 138h
0x18004e4cb  jmp     short loc_18004E492
0x18004e4cd  mov     [rbp+57h+var_A0], r13
0x18004e4d1  lea     rcx, [rbp+57h+var_A0]
0x18004e4d5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e4da  lea     rax, [rbp+57h+var_A0]
0x18004e4de  mov     qword ptr [rsp+100h+prefmaxlen], rax; int
0x18004e4e3  lea     r9, _GUID_30e038f9_64c9_4a5c_ba4c_f9f7df30849c; riid
0x18004e4ea  xor     edx, edx; pUnkOuter
0x18004e4ec  lea     r8d, [rdx+1]; dwClsContext
0x18004e4f0  lea     rcx, _GUID_54337179_c8b2_4ed4_95e4_95601c850d8c; rclsid
0x18004e4f7  call    cs:__imp_CoCreateInstance
0x18004e4fd  mov     ebx, eax
0x18004e4ff  test    eax, eax
0x18004e501  jns     short loc_18004E526
0x18004e503  mov     rcx, [rbp+5Fh]; this
0x18004e507  mov     r9d, eax; char *
0x18004e50a  mov     r8, rdi; unsigned int
0x18004e50d  mov     edx, 13Bh; void *
0x18004e512  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e517  nop
0x18004e518  lea     rcx, [rbp+57h+var_A0]
0x18004e51c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e521  jmp     loc_18004E4A2
0x18004e526  mov     rcx, [rbp+57h+var_A0]
0x18004e52a  mov     rax, [rcx]
0x18004e52d  xor     r9d, r9d
0x18004e530  xor     r8d, r8d
0x18004e533  xor     edx, edx
0x18004e535  mov     rax, [rax+20h]
0x18004e539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e53e  lea     rcx, [rbp+57h+var_60]; this
0x18004e542  call    ??0CAutoPrivilegeEnable@@QEAA@PEBG@Z; CAutoPrivilegeEnable::CAutoPrivilegeEnable(ushort const *)
0x18004e547  mov     edx, 10h; dwReason
0x18004e54c  lea     ecx, [rdx-0Eh]; uFlags
0x18004e54f  call    cs:__imp_ExitWindowsEx
0x18004e555  lea     rcx, [rbp+57h+var_60]; this
0x18004e559  call    ??1CAutoPrivilegeEnable@@QEAA@XZ; CAutoPrivilegeEnable::~CAutoPrivilegeEnable(void)
0x18004e55e  nop
0x18004e55f  lea     rcx, [rbp+57h+var_A0]
0x18004e563  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e568  nop
0x18004e569  lea     rcx, [rbp+57h+ppv]
0x18004e56d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e572  mov     ebx, r13d
0x18004e575  mov     rcx, [rbp+57h+bufptr]; Buffer
0x18004e579  call    cs:__imp_NetApiBufferFree
0x18004e57f  mov     eax, ebx
0x18004e581  mov     rcx, [rbp+57h+var_40]
0x18004e585  xor     rcx, rsp; StackCookie
0x18004e588  call    __security_check_cookie
0x18004e58d  add     rsp, 0D0h
0x18004e594  pop     r15
0x18004e596  pop     r14
0x18004e598  pop     r13
0x18004e59a  pop     r12
0x18004e59c  pop     rdi
0x18004e59d  pop     rbx
0x18004e59e  pop     rbp
0x18004e59f  retn
```
