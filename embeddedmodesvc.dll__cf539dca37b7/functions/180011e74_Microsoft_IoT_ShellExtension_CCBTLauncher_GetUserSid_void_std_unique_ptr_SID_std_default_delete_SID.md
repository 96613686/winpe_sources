# Microsoft::IoT::ShellExtension::CCBTLauncher::GetUserSid(void *,std::unique_ptr<_SID,std::default_delete<_SID>> &)

- ea: `0x180011e74`
- end: `0x180012025`
- name: `?GetUserSid@CCBTLauncher@ShellExtension@IoT@Microsoft@@CAJPEAXAEAV?$unique_ptr@U_SID@@U?$default_delete@U_SID@@@std@@@std@@@Z`
- size: `433`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001245c`

## callees

- `0x180002f84`
- `0x180005fa4`
- `0x180005fc4`
- `0x180008358`
- `0x18000a9f4`
- `0x18000be7c`
- `0x18000fd90`
- `0x18001053c`
- `0x180011e74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011eed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011eed`
- `ntdll!RtlLengthSid` at `0x180011f7c`
- `ntdll!RtlLengthSid` at `0x180011f7c`
- `ntdll!RtlCopySid` at `0x180011fdb`
- `ntdll!RtlCopySid` at `0x180011fdb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180011ee3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180011f55`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180011ee3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180011f55`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::IoT::ShellExtension::CCBTLauncher::GetUserSid(HANDLE TokenHandle, PSID *a2)
{
  unsigned int v4; // ebx
  PSID v6; // rcx
  const char *v7; // r9
  PSID **v8; // rax
  PSID *v9; // rsi
  unsigned __int64 v10; // rdx
  const char *v11; // r9
  int LastError; // eax
  ULONG v13; // eax
  ULONG v14; // edi
  unsigned __int64 *v15; // rax
  unsigned __int64 v16; // rdx
  PSID v17; // rcx
  NTSTATUS v18; // eax
  int ReturnLength; // [rsp+20h] [rbp-10h]
  int ReturnLengtha; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  DWORD TokenInformationLength; // [rsp+50h] [rbp+20h] BYREF
  PSID *v23; // [rsp+60h] [rbp+30h] BYREF
  void *v24; // [rsp+68h] [rbp+38h] BYREF

  if ( !TokenHandle )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35D,
      (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
      (const char *)0x80070057LL,
      ReturnLength);
    return v4;
  }
  v6 = *a2;
  *a2 = 0;
  if ( v6 )
    operator delete(v6);
  TokenInformationLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() != 122 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x368,
             (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
             v7);
  v23 = 0;
  v8 = (PSID **)std::make_unique<unsigned char [0],0>(&v24, TokenInformationLength);
  v9 = *v8;
  *v8 = 0;
  v23 = v9;
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v24, v10);
  if ( !GetTokenInformation(TokenHandle, TokenUser, v9, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x371,
                  (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
                  v11);
LABEL_17:
    v4 = LastError;
    Microsoft::WRL::Details::MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>::~MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>((void **)&v23);
    return v4;
  }
  v13 = RtlLengthSid(*v9);
  v14 = v13;
  if ( !v13 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x374,
      (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
      (const char *)0x8000FFFFLL,
      ReturnLengtha);
  v15 = std::make_unique<unsigned char [0],0>(&v24, v13);
  v16 = *v15;
  *v15 = 0;
  v17 = *a2;
  *a2 = (PSID)v16;
  if ( v17 )
    operator delete(v17);
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v24, v16);
  v18 = RtlCopySid(v14, *a2, *v9);
  if ( v18 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x378,
                  (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
                  (const char *)(unsigned int)v18,
                  ReturnLengtha);
    goto LABEL_17;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>::~MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>((void **)&v23);
  return 0;
}

```

## disassembly

```asm
0x180011e74  mov     [rsp-18h+arg_8], rbx
0x180011e79  push    rbp
0x180011e7a  push    rsi
0x180011e7b  push    rdi
0x180011e7c  mov     rbp, rsp
0x180011e7f  sub     rsp, 30h
0x180011e83  mov     rbx, rdx
0x180011e86  mov     rdi, rcx
0x180011e89  test    rcx, rcx
0x180011e8c  jnz     short loc_180011EB2
0x180011e8e  mov     rcx, [rbp+18h]; this
0x180011e92  mov     ebx, 80070057h
0x180011e97  mov     r9d, ebx; char *
0x180011e9a  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x180011ea1  mov     edx, 35Dh; void *
0x180011ea6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011eab  mov     eax, ebx
0x180011ead  jmp     loc_180012018
0x180011eb2  mov     rcx, [rdx]; Block
0x180011eb5  mov     qword ptr [rdx], 0
0x180011ebc  test    rcx, rcx
0x180011ebf  jz      short loc_180011EC6
0x180011ec1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011ec6  mov     [rbp+TokenInformationLength], 0
0x180011ecd  lea     rax, [rbp+TokenInformationLength]
0x180011ed1  mov     qword ptr [rsp+30h+ReturnLength], rax; ReturnLength
0x180011ed6  xor     r9d, r9d; TokenInformationLength
0x180011ed9  xor     r8d, r8d; TokenInformation
0x180011edc  lea     edx, [r9+1]; TokenInformationClass
0x180011ee0  mov     rcx, rdi; TokenHandle
0x180011ee3  call    cs:__imp_GetTokenInformation
0x180011ee9  test    eax, eax
0x180011eeb  jnz     short loc_180011F12
0x180011eed  call    cs:__imp_GetLastError
0x180011ef3  cmp     eax, 7Ah ; 'z'
0x180011ef6  jz      short loc_180011F12
0x180011ef8  mov     rcx, [rbp+18h]; this
0x180011efc  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x180011f03  mov     edx, 368h; void *
0x180011f08  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011f0d  jmp     loc_180012018
0x180011f12  mov     [rbp+arg_10], 0
0x180011f1a  mov     edx, [rbp+TokenInformationLength]
0x180011f1d  lea     rcx, [rbp+arg_18]
0x180011f21  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x180011f26  mov     rsi, [rax]
0x180011f29  mov     qword ptr [rax], 0
0x180011f30  mov     [rbp+arg_10], rsi
0x180011f34  lea     rcx, [rbp+arg_18]
0x180011f38  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x180011f3d  lea     rax, [rbp+TokenInformationLength]
0x180011f41  mov     qword ptr [rsp+30h+ReturnLength], rax; int
0x180011f46  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180011f4a  mov     r8, rsi; TokenInformation
0x180011f4d  mov     edx, 1; TokenInformationClass
0x180011f52  mov     rcx, rdi; TokenHandle
0x180011f55  call    cs:__imp_GetTokenInformation
0x180011f5b  test    eax, eax
0x180011f5d  jnz     short loc_180011F79
0x180011f5f  mov     rcx, [rbp+18h]; this
0x180011f63  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x180011f6a  mov     edx, 371h; void *
0x180011f6f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011f74  jmp     loc_180011FFD
0x180011f79  mov     rcx, [rsi]; Sid
0x180011f7c  call    cs:__imp_RtlLengthSid
0x180011f82  mov     edi, eax
0x180011f84  mov     rcx, [rbp+18h]; this
0x180011f88  test    eax, eax
0x180011f8a  jnz     short loc_180011FA4
0x180011f8c  mov     r9d, 8000FFFFh; char *
0x180011f92  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x180011f99  mov     edx, 374h; void *
0x180011f9e  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180011fa4  mov     rdx, rdi
0x180011fa7  lea     rcx, [rbp+arg_18]
0x180011fab  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x180011fb0  mov     rdx, [rax]
0x180011fb3  mov     qword ptr [rax], 0
0x180011fba  mov     rcx, [rbx]; Block
0x180011fbd  mov     [rbx], rdx
0x180011fc0  test    rcx, rcx
0x180011fc3  jz      short loc_180011FCA
0x180011fc5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011fca  lea     rcx, [rbp+arg_18]
0x180011fce  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x180011fd3  mov     r8, [rsi]; SourceSid
0x180011fd6  mov     rdx, [rbx]; DestinationSid
0x180011fd9  mov     ecx, edi; DestinationSidLength
0x180011fdb  call    cs:__imp_RtlCopySid
0x180011fe1  test    eax, eax
0x180011fe3  jns     short loc_18001200D
0x180011fe5  mov     rcx, [rbp+18h]; this
0x180011fe9  mov     r9d, eax; char *
0x180011fec  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x180011ff3  mov     edx, 378h; void *
0x180011ff8  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180011ffd  mov     ebx, eax
0x180011fff  lea     rcx, [rbp+arg_10]
0x180012003  call    ??1?$MakeAllocator@VEmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>::~MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>(void)
0x180012008  jmp     loc_180011EAB
0x18001200d  lea     rcx, [rbp+arg_10]
0x180012011  call    ??1?$MakeAllocator@VEmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>::~MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>(void)
0x180012016  xor     eax, eax
0x180012018  mov     rbx, [rsp+30h+arg_8]
0x18001201d  add     rsp, 30h
0x180012021  pop     rdi
0x180012022  pop     rsi
0x180012023  pop     rbp
0x180012024  retn
```
