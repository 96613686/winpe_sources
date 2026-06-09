# SetSecurityInfo(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x1800a08b0`
- end: `0x1800a0acc`
- name: `?SetSecurityInfo@@YAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a0ad4`

## callees

- `0x180008618`
- `0x180008b1c`
- `0x18000933c`
- `0x1800a08b0`
- `0x1800a1c5c`
- `0x1800a1ea4`
- `0x1800a59f8`
- `0x1800a5a28`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800a097e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800a097e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0a6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0a9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0a6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0a9b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800a0934`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800a0934`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1800a0a41`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1800a0a41`

## string_xrefs

- `0x1800a0a84`: `C:\__w\1\s\src\DeliveryOptimization\StatePersistence\win10\AppRegistryHive.cpp`
- `0x1800a09a4`: `fDaclPresent`
- `0x1800a09bd`: `CFile::SetSecurityInfo`
- `0x1800a09fb`: `CFile::SetSecurityInfo`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SetSecurityInfo(char *a1)
{
  int v1; // ebx
  __int64 v2; // rdx
  const char *v3; // r9
  __int64 v4; // rdx
  int LastError; // eax
  DWORD v6; // eax
  int psidGroup; // [rsp+20h] [rbp-50h]
  unsigned int psidGroupa; // [rsp+20h] [rbp-50h]
  PACL pDacl; // [rsp+40h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-28h] BYREF
  WINBOOL bDaclPresent; // [rsp+50h] [rbp-20h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+54h] [rbp-1Ch] BYREF
  HANDLE handle; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  handle = (HANDLE)-1LL;
  if ( *((_QWORD *)a1 + 3) > 0xFu )
    a1 = *(char **)a1;
  v1 = CFile::Create(&handle, a1, 0x60000u, 7u, 3u, 0x80u);
  if ( v1 >= 0 )
  {
    SecurityDescriptor = 0;
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GRGWSD;;;NS)", 1u, &SecurityDescriptor, 0) )
    {
      pDacl = 0;
      bDaclPresent = 0;
      bDaclDefaulted = 0;
      if ( GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      {
        if ( !bDaclPresent )
        {
          LogMessage(2u, "CFile::SetSecurityInfo", 0x10Eu, "TelemetryAssert (%s): %s", "fDaclPresent", "Failed");
          DOTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
        }
        if ( bDaclDefaulted )
        {
          LogMessage(2u, "CFile::SetSecurityInfo", 0x10Fu, "TelemetryAssert (%s): %s", "!fDefault", "Failed");
          DOTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
        }
        v6 = SetSecurityInfo(handle, SE_FILE_OBJECT, 0x20000004u, 0, 0, pDacl, 0);
        if ( !v6 )
        {
          if ( SecurityDescriptor )
            LocalFree(SecurityDescriptor);
          goto LABEL_23;
        }
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x118,
                      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\FileSystem.cpp",
                      (const char *)v6,
                      psidGroupa);
LABEL_16:
        v1 = LastError;
        if ( SecurityDescriptor )
          LocalFree(SecurityDescriptor);
        if ( v1 < 0 )
        {
          v2 = 91;
          goto LABEL_20;
        }
LABEL_23:
        v1 = 0;
        goto LABEL_24;
      }
      v4 = 269;
    }
    else
    {
      v4 = 264;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v4,
                  (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\FileSystem.cpp",
                  v3);
    goto LABEL_16;
  }
  v2 = 90;
LABEL_20:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v2,
    (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\StatePersistence\\win10\\AppRegistryHive.cpp",
    (const char *)(unsigned int)v1,
    psidGroup);
LABEL_24:
  CFile::~CFile((CFile *)&handle);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800a08b0  mov     [rsp-8+arg_8], rbx
0x1800a08b5  mov     [rsp-8+arg_10], r15
0x1800a08ba  push    rbp
0x1800a08bb  mov     rbp, rsp
0x1800a08be  sub     rsp, 70h
0x1800a08c2  mov     rax, cs:__security_cookie
0x1800a08c9  xor     rax, rsp
0x1800a08cc  mov     [rbp+var_10], rax
0x1800a08d0  mov     [rbp+handle], 0FFFFFFFFFFFFFFFFh
0x1800a08d8  cmp     qword ptr [rcx+18h], 0Fh
0x1800a08dd  jbe     short loc_1800A08E2
0x1800a08df  mov     rcx, [rcx]
0x1800a08e2  mov     dword ptr [rsp+70h+var_48], 80h; unsigned int
0x1800a08ea  mov     dword ptr [rsp+70h+psidGroup], 3; unsigned int
0x1800a08f2  mov     r9d, 7; unsigned int
0x1800a08f8  mov     r8d, 60000h; unsigned int
0x1800a08fe  mov     rdx, rcx; char *
0x1800a0901  lea     rcx, [rbp+handle]; this
0x1800a0905  call    ?Create@CFile@@QEAAJPEBDIIII@Z; CFile::Create(char const *,uint,uint,uint,uint)
0x1800a090a  mov     ebx, eax
0x1800a090c  test    eax, eax
0x1800a090e  jns     short loc_1800A091A
0x1800a0910  mov     edx, 5Ah ; 'Z'
0x1800a0915  jmp     loc_1800A0A7D
0x1800a091a  mov     [rbp+SecurityDescriptor], 0
0x1800a0922  xor     r9d, r9d; SecurityDescriptorSize
0x1800a0925  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800a0929  lea     edx, [r9+1]; StringSDRevision
0x1800a092d  lea     rcx, StringSecurityDescriptor; "D:(A;;GRGWSD;;;NS)"
0x1800a0934  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800a093a  test    eax, eax
0x1800a093c  jnz     short loc_1800A0958
0x1800a093e  mov     edx, 108h; void *
0x1800a0943  lea     r8, aCW1SSrcDeliver_85; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800a094a  mov     rcx, [rbp+8]; this
0x1800a094e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a0953  jmp     loc_1800A0A63
0x1800a0958  mov     [rbp+pDacl], 0
0x1800a0960  mov     [rbp+bDaclPresent], 0
0x1800a0967  mov     [rbp+bDaclDefaulted], 0
0x1800a096e  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x1800a0972  lea     r8, [rbp+pDacl]; pDacl
0x1800a0976  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1800a097a  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x1800a097e  call    cs:__imp_GetSecurityDescriptorDacl
0x1800a0984  test    eax, eax
0x1800a0986  jnz     short loc_1800A098F
0x1800a0988  mov     edx, 10Dh
0x1800a098d  jmp     short loc_1800A0943
0x1800a098f  lea     r15, aFailed; "Failed"
0x1800a0996  or      ebx, 0FFFFFFFFh
0x1800a0999  cmp     [rbp+bDaclPresent], 0
0x1800a099d  jnz     short loc_1800A09D7
0x1800a099f  mov     [rsp+70h+var_48], r15
0x1800a09a4  lea     rax, aFdaclpresent; "fDaclPresent"
0x1800a09ab  mov     [rsp+70h+psidGroup], rax
0x1800a09b0  lea     r9, aTelemetryasser; "TelemetryAssert (%s): %s"
0x1800a09b7  mov     r8d, 10Eh; unsigned int
0x1800a09bd  lea     rdx, aCfileSetsecuri; "CFile::SetSecurityInfo"
0x1800a09c4  mov     ecx, 2; unsigned __int8
0x1800a09c9  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800a09ce  mov     edx, ebx; unsigned int
0x1800a09d0  mov     ecx, ebx; unsigned int
0x1800a09d2  call    ?DOTelemetryAssertTriggered@@YAXII@Z; DOTelemetryAssertTriggered(uint,uint)
0x1800a09d7  cmp     [rbp+bDaclDefaulted], 0
0x1800a09db  jz      short loc_1800A0A15
0x1800a09dd  mov     [rsp+70h+var_48], r15
0x1800a09e2  lea     rax, aFdefault; "!fDefault"
0x1800a09e9  mov     [rsp+70h+psidGroup], rax
0x1800a09ee  lea     r9, aTelemetryasser; "TelemetryAssert (%s): %s"
0x1800a09f5  mov     r8d, 10Fh; unsigned int
0x1800a09fb  lea     rdx, aCfileSetsecuri; "CFile::SetSecurityInfo"
0x1800a0a02  mov     ecx, 2; unsigned __int8
0x1800a0a07  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800a0a0c  mov     edx, ebx; unsigned int
0x1800a0a0e  mov     ecx, ebx; unsigned int
0x1800a0a10  call    ?DOTelemetryAssertTriggered@@YAXII@Z; DOTelemetryAssertTriggered(uint,uint)
0x1800a0a15  mov     rax, [rbp+pDacl]
0x1800a0a19  mov     [rsp+70h+pSacl], 0; pSacl
0x1800a0a22  mov     [rsp+70h+var_48], rax; pDacl
0x1800a0a27  mov     [rsp+70h+psidGroup], 0; int
0x1800a0a30  xor     r9d, r9d; psidOwner
0x1800a0a33  lea     edx, [r9+1]; ObjectType
0x1800a0a37  mov     r8d, 20000004h; SecurityInfo
0x1800a0a3d  mov     rcx, [rbp+handle]; handle
0x1800a0a41  call    cs:__imp_SetSecurityInfo
0x1800a0a47  test    eax, eax
0x1800a0a49  jz      short loc_1800A0A92
0x1800a0a4b  mov     rcx, [rbp+8]; this
0x1800a0a4f  mov     r9d, eax; char *
0x1800a0a52  lea     r8, aCW1SSrcDeliver_85; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800a0a59  mov     edx, 118h; void *
0x1800a0a5e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a0a63  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x1800a0a67  mov     ebx, eax
0x1800a0a69  test    rcx, rcx
0x1800a0a6c  jz      short loc_1800A0A74
0x1800a0a6e  call    cs:__imp_LocalFree
0x1800a0a74  test    ebx, ebx
0x1800a0a76  jns     short loc_1800A0AA1
0x1800a0a78  mov     edx, 5Bh ; '['; void *
0x1800a0a7d  mov     rcx, [rbp+8]; this
0x1800a0a81  mov     r9d, ebx; char *
0x1800a0a84  lea     r8, aCW1SSrcDeliver_29; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800a0a8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0a90  jmp     short loc_1800A0AA3
0x1800a0a92  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x1800a0a96  test    rcx, rcx
0x1800a0a99  jz      short loc_1800A0AA1
0x1800a0a9b  call    cs:__imp_LocalFree
0x1800a0aa1  xor     ebx, ebx
0x1800a0aa3  lea     rcx, [rbp+handle]; this
0x1800a0aa7  call    ??1CFile@@QEAA@XZ; CFile::~CFile(void)
0x1800a0aac  mov     eax, ebx
0x1800a0aae  mov     rcx, [rbp+var_10]
0x1800a0ab2  xor     rcx, rsp; StackCookie
0x1800a0ab5  call    __security_check_cookie
0x1800a0aba  lea     r11, [rsp+70h+var_s0]
0x1800a0abf  mov     rbx, [r11+18h]
0x1800a0ac3  mov     r15, [r11+20h]
0x1800a0ac7  mov     rsp, r11
0x1800a0aca  pop     rbp
0x1800a0acb  retn
```
