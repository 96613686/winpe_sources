# _GetAppContainerProperty(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x180001d3c`
- end: `0x180001fb1`
- name: `?_GetAppContainerProperty@@YAJPEBG00PEAPEAG@Z`
- size: `629`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800017e4`

## callees

- `0x180001ab8`
- `0x180001ae0`
- `0x180001d3c`
- `0x1800023d8`
- `0x180002484`
- `0x180004990`
- `0x180004c10`
- `0x180005b60`
- `0x180005b90`
- `0x1800091f0`
- `0x18000d5fc`
- `0x18000dc34`
- `0x18000dcf8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001f21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001f21`
- `ntdll!RtlGetAppContainerParent` at `0x180001e20`
- `ntdll!RtlGetAppContainerParent` at `0x180001e20`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180001e54`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180001e54`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180001dac`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180001dac`

## string_xrefs

- `0x180001f36`: `SubKeyPath: %ws, PropertyName: %ws`

## pseudocode

```c
__int64 __fastcall _GetAppContainerProperty(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  int v7; // eax
  int LastError; // ebx
  const char *v9; // r9
  int IsChildAppContainerSid; // eax
  __int64 v11; // rdx
  int AppContainerParent; // eax
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  const char *v16; // rdi
  int v18; // [rsp+20h] [rbp-39h]
  PSID Sid; // [rsp+40h] [rbp-19h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-11h] BYREF
  unsigned __int16 *v21; // [rsp+50h] [rbp-9h] BYREF
  __int64 v22; // [rsp+58h] [rbp-1h]
  __int64 v23; // [rsp+60h] [rbp+7h]
  char *v24[9]; // [rsp+68h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  PSID v26; // [rsp+D8h] [rbp+7Fh] BYREF

  *a4 = 0;
  memset(v24, 0, 24);
  v7 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
         v24,
         L"%s\\Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppContainer\\Mappings\\",
         a1);
  LastError = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"minio\\profapi\\appcontainer.cpp",
      (const char *)(unsigned int)v7,
      v18);
    goto LABEL_28;
  }
  Sid = 0;
  if ( !ConvertStringSidToSidW(a2, &Sid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x50,
                  (unsigned int)"minio\\profapi\\appcontainer.cpp",
                  v9);
LABEL_5:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&Sid);
    goto LABEL_28;
  }
  LODWORD(v26) = 0;
  IsChildAppContainerSid = _IsChildAppContainerSid(Sid, (int *)&v26);
  LastError = IsChildAppContainerSid;
  if ( IsChildAppContainerSid < 0 )
  {
    v11 = 83;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"minio\\profapi\\appcontainer.cpp",
      (const char *)(unsigned int)IsChildAppContainerSid,
      v18);
    goto LABEL_5;
  }
  if ( (_DWORD)v26 )
  {
    v26 = 0;
    AppContainerParent = RtlGetAppContainerParent(Sid, &v26);
    if ( AppContainerParent < 0 )
    {
      LastError = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x58,
                    v13,
                    (const char *)(unsigned int)AppContainerParent,
                    v18);
LABEL_12:
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v26);
      goto LABEL_5;
    }
    StringSid = 0;
    if ( !ConvertSidToStringSidW(v26, &StringSid) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x5B,
                    (unsigned int)"minio\\profapi\\appcontainer.cpp",
                    v14);
LABEL_15:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>((void **)&StringSid);
      goto LABEL_12;
    }
    v15 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::ConcatFormat(
            v24,
            L"%s\\Children\\",
            StringSid);
    LastError = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"minio\\profapi\\appcontainer.cpp",
        (const char *)(unsigned int)v15,
        v18);
      goto LABEL_15;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>((void **)&StringSid);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v26);
  }
  IsChildAppContainerSid = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Concat(
                             v24,
                             a2);
  LastError = IsChildAppContainerSid;
  if ( IsChildAppContainerSid < 0 )
  {
    v11 = 97;
    goto LABEL_8;
  }
  v16 = v24[0];
  v21 = 0;
  v22 = 0;
  v23 = 0;
  LastError = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
                (__int64)&v21,
                HKEY_USERS,
                (const WCHAR *)v24[0],
                a3);
  if ( LastError != -2147024877 )
  {
    if ( LastError >= 0 )
    {
      *a4 = v21;
      v21 = 0;
      v23 = 0;
      v22 = 0;
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v21);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&Sid);
      LastError = 0;
      goto LABEL_28;
    }
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x66,
      (unsigned int)"minio\\profapi\\appcontainer.cpp",
      (const char *)(unsigned int)LastError,
      (int)"SubKeyPath: %ws, PropertyName: %ws",
      v16,
      a3);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v21);
    goto LABEL_5;
  }
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v21);
  if ( Sid )
    LocalFree(Sid);
  LastError = -2147024877;
LABEL_28:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v24);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180001d3c  push    rbp
0x180001d3e  push    rbx
0x180001d3f  push    rsi
0x180001d40  push    rdi
0x180001d41  push    r14
0x180001d43  push    r15
0x180001d45  lea     rbp, [rsp-2Fh]
0x180001d4a  sub     rsp, 88h
0x180001d51  xor     r15d, r15d
0x180001d54  mov     r14, r8
0x180001d57  mov     r8, rcx
0x180001d5a  mov     [r9], r15
0x180001d5d  mov     rdi, rdx
0x180001d60  mov     [rbp+57h+var_48], r15
0x180001d64  lea     rcx, [rbp+57h+var_48]
0x180001d68  mov     [rbp+57h+var_40], r15
0x180001d6c  lea     rdx, aSSoftwareClass; "%s\\Software\\Classes\\Local Settings\\"...
0x180001d73  mov     [rbp+57h+var_38], r15
0x180001d77  mov     rsi, r9
0x180001d7a  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180001d7f  mov     ebx, eax
0x180001d81  test    eax, eax
0x180001d83  jns     short loc_180001DA1
0x180001d85  mov     rcx, [rbp+5Fh]; this
0x180001d89  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x180001d90  mov     r9d, eax; char *
0x180001d93  lea     edx, [r15+4Ch]; void *
0x180001d97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001d9c  jmp     loc_180001F96
0x180001da1  lea     rdx, [rbp+57h+Sid]; Sid
0x180001da5  mov     [rbp+57h+Sid], r15
0x180001da9  mov     rcx, rdi; StringSid
0x180001dac  call    cs:__imp_ConvertStringSidToSidW
0x180001db2  test    eax, eax
0x180001db4  jnz     short loc_180001DD9
0x180001db6  mov     rcx, [rbp+5Fh]; this
0x180001dba  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x180001dc1  lea     edx, [rax+50h]; void *
0x180001dc4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180001dc9  mov     ebx, eax
0x180001dcb  lea     rcx, [rbp+57h+Sid]
0x180001dcf  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x180001dd4  jmp     loc_180001F96
0x180001dd9  mov     rcx, [rbp+57h+Sid]; void *
0x180001ddd  lea     rdx, [rbp+57h+arg_18]; int *
0x180001de1  mov     dword ptr [rbp+57h+arg_18], r15d
0x180001de5  call    ?_IsChildAppContainerSid@@YAJQEAXPEAH@Z; _IsChildAppContainerSid(void * const,int *)
0x180001dea  mov     ebx, eax
0x180001dec  test    eax, eax
0x180001dee  jns     short loc_180001E0A
0x180001df0  mov     edx, 53h ; 'S'; void *
0x180001df5  mov     rcx, [rbp+5Fh]; this
0x180001df9  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x180001e00  mov     r9d, eax; char *
0x180001e03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001e08  jmp     short loc_180001DCB
0x180001e0a  cmp     dword ptr [rbp+57h+arg_18], r15d
0x180001e0e  jz      loc_180001EC4
0x180001e14  mov     rcx, [rbp+57h+Sid]
0x180001e18  lea     rdx, [rbp+57h+arg_18]
0x180001e1c  mov     [rbp+57h+arg_18], r15
0x180001e20  call    cs:__imp_RtlGetAppContainerParent
0x180001e26  test    eax, eax
0x180001e28  jns     short loc_180001E48
0x180001e2a  mov     rcx, [rbp+5Fh]; this
0x180001e2e  mov     r9d, eax; char *
0x180001e31  mov     edx, 58h ; 'X'; void *
0x180001e36  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180001e3b  mov     ebx, eax
0x180001e3d  lea     rcx, [rbp+57h+arg_18]
0x180001e41  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180001e46  jmp     short loc_180001DCB
0x180001e48  mov     rcx, [rbp+57h+arg_18]; Sid
0x180001e4c  lea     rdx, [rbp+57h+StringSid]; StringSid
0x180001e50  mov     [rbp+57h+StringSid], r15
0x180001e54  call    cs:__imp_ConvertSidToStringSidW
0x180001e5a  test    eax, eax
0x180001e5c  jnz     short loc_180001E7E
0x180001e5e  mov     rcx, [rbp+5Fh]; this
0x180001e62  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x180001e69  lea     edx, [rax+5Bh]; void *
0x180001e6c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180001e71  mov     ebx, eax
0x180001e73  lea     rcx, [rbp+57h+StringSid]
0x180001e77  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x180001e7c  jmp     short loc_180001E3D
0x180001e7e  mov     r8, [rbp+57h+StringSid]
0x180001e82  lea     rdx, aSChildren; "%s\\Children\\"
0x180001e89  lea     rcx, [rbp+57h+var_48]
0x180001e8d  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x180001e92  mov     ebx, eax
0x180001e94  test    eax, eax
0x180001e96  jns     short loc_180001EB2
0x180001e98  mov     rcx, [rbp+5Fh]; this
0x180001e9c  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x180001ea3  mov     r9d, eax; char *
0x180001ea6  mov     edx, 5Dh ; ']'; void *
0x180001eab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001eb0  jmp     short loc_180001E73
0x180001eb2  lea     rcx, [rbp+57h+StringSid]
0x180001eb6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x180001ebb  lea     rcx, [rbp+57h+arg_18]
0x180001ebf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180001ec4  mov     rdx, rdi
0x180001ec7  lea     rcx, [rbp+57h+var_48]
0x180001ecb  call    ?Concat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Concat(ushort const *)
0x180001ed0  mov     ebx, eax
0x180001ed2  test    eax, eax
0x180001ed4  jns     short loc_180001EE0
0x180001ed6  mov     edx, 61h ; 'a'
0x180001edb  jmp     loc_180001DF5
0x180001ee0  mov     rdi, [rbp+57h+var_48]
0x180001ee4  lea     rcx, [rbp+57h+var_60]
0x180001ee8  mov     r8, rdi
0x180001eeb  mov     [rbp+57h+var_60], r15
0x180001eef  mov     r9, r14
0x180001ef2  mov     [rbp+57h+var_58], r15
0x180001ef6  mov     rdx, 0FFFFFFFF80000003h
0x180001efd  mov     [rbp+57h+var_50], r15
0x180001f01  call    ?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x180001f06  mov     ebx, eax
0x180001f08  cmp     eax, 80070013h
0x180001f0d  jnz     short loc_180001F2E
0x180001f0f  lea     rcx, [rbp+57h+var_60]
0x180001f13  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180001f18  mov     rcx, [rbp+57h+Sid]; hMem
0x180001f1c  test    rcx, rcx
0x180001f1f  jz      short loc_180001F27
0x180001f21  call    cs:__imp_LocalFree
0x180001f27  mov     ebx, 80070013h
0x180001f2c  jmp     short loc_180001F96
0x180001f2e  test    ebx, ebx
0x180001f30  jns     short loc_180001F6E
0x180001f32  mov     rcx, [rbp+5Fh]; this
0x180001f36  lea     rax, aSubkeypathWsPr; "SubKeyPath: %ws, PropertyName: %ws"
0x180001f3d  mov     [rsp+0B0h+var_80], r14
0x180001f42  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x180001f49  mov     [rsp+0B0h+var_88], rdi; char *
0x180001f4e  mov     r9d, ebx; char *
0x180001f51  mov     edx, 66h ; 'f'; void *
0x180001f56  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x180001f5b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180001f60  lea     rcx, [rbp+57h+var_60]
0x180001f64  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180001f69  jmp     loc_180001DCB
0x180001f6e  mov     rax, [rbp+57h+var_60]
0x180001f72  lea     rcx, [rbp+57h+var_60]
0x180001f76  mov     [rsi], rax
0x180001f79  mov     [rbp+57h+var_60], r15
0x180001f7d  mov     [rbp+57h+var_50], r15
0x180001f81  mov     [rbp+57h+var_58], r15
0x180001f85  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180001f8a  lea     rcx, [rbp+57h+Sid]
0x180001f8e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x180001f93  mov     ebx, r15d
0x180001f96  lea     rcx, [rbp+57h+var_48]
0x180001f9a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180001f9f  mov     eax, ebx
0x180001fa1  add     rsp, 88h
0x180001fa8  pop     r15
0x180001faa  pop     r14
0x180001fac  pop     rdi
0x180001fad  pop     rsi
0x180001fae  pop     rbx
0x180001faf  pop     rbp
0x180001fb0  retn
```
