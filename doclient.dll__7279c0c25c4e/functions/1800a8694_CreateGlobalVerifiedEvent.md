# _CreateGlobalVerifiedEvent

- ea: `0x1800a8694`
- end: `0x1800a8978`
- name: `_CreateGlobalVerifiedEvent`
- size: `740`
- prototype: `__int64 __fastcall(HANDLE *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002cdb8`

## callees

- `0x180008618`
- `0x1800089f8`
- `0x180008b1c`
- `0x1800095a0`
- `0x18000d228`
- `0x18000ef98`
- `0x180019010`
- `0x1800199fc`
- `0x1800a8694`
- `0x1800a979c`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800a88a5`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800a88a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a870b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a886c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a888e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a88e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a890b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8922`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8944`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a870b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a886c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a888e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a88e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a890b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8922`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8944`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800a86db`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800a86db`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1800a8837`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1800a8837`

## string_xrefs

- `0x1800a88b7`: `Owner SID for the refresh request event is not Network Service`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CreateGlobalVerifiedEvent(HANDLE *a1, __int64 a2, unsigned int a3)
{
  const char *v5; // r9
  unsigned int LastError; // ebx
  __int128 *p_Src; // rdx
  _QWORD *v9; // r8
  DWORD SecurityInfo; // eax
  unsigned int v11; // ebx
  unsigned int ppsidGroup; // [rsp+20h] [rbp-B8h]
  PACL *ppDacl; // [rsp+28h] [rbp-B0h]
  _BYTE v14[8]; // [rsp+40h] [rbp-98h] BYREF
  _QWORD v15[4]; // [rsp+48h] [rbp-90h] BYREF
  PSID ppsidOwner; // [rsp+68h] [rbp-70h] BYREF
  _QWORD v17[3]; // [rsp+70h] [rbp-68h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-50h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+90h] [rbp-48h] BYREF
  __int128 Src; // [rsp+98h] [rbp-40h] BYREF
  __int128 v21; // [rsp+A8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v14[0] = 0;
  hMem = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GA;;;S-1-5-20)", 1u, &hMem, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x57,
                  (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\Event.cpp",
                  v5);
    if ( hMem )
      LocalFree(hMem);
    return LastError;
  }
  v17[0] = 24;
  v17[1] = hMem;
  v17[2] = 0;
  Src = 0;
  v21 = 0;
  std::string::_Construct<1,char const *>(&Src, "Global\\");
  std::string::append(&Src);
  p_Src = &Src;
  if ( *((_QWORD *)&v21 + 1) > 0xFu )
    p_Src = (__int128 *)Src;
  UTF8toWstr(v15, p_Src, v21);
  v9 = v15;
  if ( v15[3] > 7u )
    v9 = (_QWORD *)v15[0];
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    a1,
    a3,
    v9,
    v17,
    v14);
  std::wstring::~wstring(v15);
  if ( v14[0] )
  {
    ppsidOwner = 0;
    ppSecurityDescriptor = 0;
    SecurityInfo = GetSecurityInfo(*a1, SE_KERNEL_OBJECT, 1u, &ppsidOwner, 0, 0, 0, &ppSecurityDescriptor);
    if ( SecurityInfo )
    {
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x63,
              (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\Event.cpp",
              (const char *)SecurityInfo,
              ppsidGroup);
      if ( ppSecurityDescriptor )
        LocalFree(ppSecurityDescriptor);
      std::string::~string(&Src);
      if ( hMem )
        LocalFree(hMem);
      return v11;
    }
    if ( !IsWellKnownSid(ppsidOwner, WinNetworkServiceSid) )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x67,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\Event.cpp",
        (const char *)0x80040207LL,
        (int)"Owner SID for the refresh request event is not Network Service",
        (const char *)ppDacl);
      if ( ppSecurityDescriptor )
        LocalFree(ppSecurityDescriptor);
      std::string::~string(&Src);
      if ( hMem )
        LocalFree(hMem);
      return 2147746311LL;
    }
    if ( ppSecurityDescriptor )
      LocalFree(ppSecurityDescriptor);
  }
  std::string::~string(&Src);
  if ( hMem )
    LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x1800a8694  mov     r11, rsp
0x1800a8697  push    rbx
0x1800a8698  push    rsi
0x1800a8699  push    rdi
0x1800a869a  sub     rsp, 0C0h
0x1800a86a1  mov     rax, cs:__security_cookie
0x1800a86a8  xor     rax, rsp
0x1800a86ab  mov     [rsp+0D8h+var_20], rax
0x1800a86b3  mov     esi, r8d
0x1800a86b6  mov     rbx, rdx
0x1800a86b9  mov     rdi, rcx
0x1800a86bc  mov     [rsp+0D8h+var_98], 0
0x1800a86c1  mov     qword ptr [r11-50h], 0
0x1800a86c9  xor     r9d, r9d; SecurityDescriptorSize
0x1800a86cc  lea     r8, [r11-50h]; SecurityDescriptor
0x1800a86d0  lea     edx, [r9+1]; StringSDRevision
0x1800a86d4  lea     rcx, aDAGaS1520; "D:(A;;GA;;;S-1-5-20)"
0x1800a86db  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800a86e1  test    eax, eax
0x1800a86e3  jnz     short loc_1800A8718
0x1800a86e5  mov     rcx, [rsp+0D8h]; this
0x1800a86ed  lea     r8, aCW1SSrcDeliver_36; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800a86f4  lea     edx, [rax+57h]; void *
0x1800a86f7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a86fc  mov     ebx, eax
0x1800a86fe  mov     rcx, [rsp+0D8h+hMem]; hMem
0x1800a8706  test    rcx, rcx
0x1800a8709  jz      short loc_1800A8711
0x1800a870b  call    cs:__imp_LocalFree
0x1800a8711  mov     eax, ebx
0x1800a8713  jmp     loc_1800A895C
0x1800a8718  mov     [rsp+0D8h+var_68], 18h
0x1800a8721  mov     rax, [rsp+0D8h+hMem]
0x1800a8729  mov     [rsp+0D8h+var_60], rax
0x1800a872e  mov     [rsp+0D8h+var_58], 0
0x1800a873a  xorps   xmm0, xmm0
0x1800a873d  movups  [rsp+0D8h+Src], xmm0
0x1800a8745  xorps   xmm1, xmm1
0x1800a8748  movdqu  [rsp+0D8h+var_30], xmm1
0x1800a8751  mov     r8d, 7
0x1800a8757  lea     rdx, aGlobal; "Global\\"
0x1800a875e  lea     rcx, [rsp+0D8h+Src]
0x1800a8766  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800a876b  nop
0x1800a876c  mov     rdx, rbx
0x1800a876f  lea     rcx, [rsp+0D8h+Src]; Src
0x1800a8777  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::append(char const * const)
0x1800a877c  lea     rdx, [rsp+0D8h+Src]
0x1800a8784  cmp     qword ptr [rsp+0D8h+var_30+8], 0Fh
0x1800a878d  cmova   rdx, qword ptr [rsp+0D8h+Src]
0x1800a8796  mov     r8, qword ptr [rsp+0D8h+var_30]
0x1800a879e  lea     rcx, [rsp+0D8h+var_90]
0x1800a87a3  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x1800a87a8  nop
0x1800a87a9  lea     r8, [rsp+0D8h+var_90]
0x1800a87ae  cmp     [rsp+0D8h+var_78], 7
0x1800a87b4  cmova   r8, [rsp+0D8h+var_90]
0x1800a87ba  lea     rax, [rsp+0D8h+var_98]
0x1800a87bf  mov     [rsp+0D8h+ppsidGroup], rax
0x1800a87c4  lea     r9, [rsp+0D8h+var_68]
0x1800a87c9  mov     edx, esi
0x1800a87cb  mov     rcx, rdi
0x1800a87ce  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800a87d3  nop
0x1800a87d4  lea     rcx, [rsp+0D8h+var_90]
0x1800a87d9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a87de  cmp     [rsp+0D8h+var_98], 0
0x1800a87e3  jz      loc_1800A8929
0x1800a87e9  mov     [rsp+0D8h+ppsidOwner], 0
0x1800a87f2  mov     [rsp+0D8h+var_48], 0
0x1800a87fe  lea     rax, [rsp+0D8h+var_48]
0x1800a8806  mov     [rsp+0D8h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1800a880b  mov     [rsp+0D8h+ppSacl], 0; ppSacl
0x1800a8814  mov     [rsp+0D8h+ppDacl], 0; char *
0x1800a881d  mov     [rsp+0D8h+ppsidGroup], 0; unsigned int
0x1800a8826  lea     r9, [rsp+0D8h+ppsidOwner]; ppsidOwner
0x1800a882b  mov     edx, 6; ObjectType
0x1800a8830  lea     r8d, [rdx-5]; SecurityInfo
0x1800a8834  mov     rcx, [rdi]; handle
0x1800a8837  call    cs:__imp_GetSecurityInfo
0x1800a883d  test    eax, eax
0x1800a883f  jz      short loc_1800A889B
0x1800a8841  mov     rcx, [rsp+0D8h]; this
0x1800a8849  mov     r9d, eax; char *
0x1800a884c  lea     r8, aCW1SSrcDeliver_36; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800a8853  mov     edx, 63h ; 'c'; void *
0x1800a8858  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a885d  mov     ebx, eax
0x1800a885f  mov     rcx, [rsp+0D8h+var_48]; hMem
0x1800a8867  test    rcx, rcx
0x1800a886a  jz      short loc_1800A8873
0x1800a886c  call    cs:__imp_LocalFree
0x1800a8872  nop
0x1800a8873  lea     rcx, [rsp+0D8h+Src]; void *
0x1800a887b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800a8880  nop
0x1800a8881  mov     rcx, [rsp+0D8h+hMem]; hMem
0x1800a8889  test    rcx, rcx
0x1800a888c  jz      short loc_1800A8894
0x1800a888e  call    cs:__imp_LocalFree
0x1800a8894  mov     eax, ebx
0x1800a8896  jmp     loc_1800A895C
0x1800a889b  mov     edx, 18h; WellKnownSidType
0x1800a88a0  mov     rcx, [rsp+0D8h+ppsidOwner]; pSid
0x1800a88a5  call    cs:__imp_IsWellKnownSid
0x1800a88ab  test    eax, eax
0x1800a88ad  jnz     short loc_1800A8915
0x1800a88af  mov     rcx, [rsp+0D8h]; this
0x1800a88b7  lea     rax, aOwnerSidForThe; "Owner SID for the refresh request event"...
0x1800a88be  mov     [rsp+0D8h+ppsidGroup], rax; int
0x1800a88c3  mov     ebx, 80040207h
0x1800a88c8  mov     r9d, ebx; char *
0x1800a88cb  lea     r8, aCW1SSrcDeliver_36; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800a88d2  mov     edx, 67h ; 'g'; void *
0x1800a88d7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a88dc  mov     rcx, [rsp+0D8h+var_48]; hMem
0x1800a88e4  test    rcx, rcx
0x1800a88e7  jz      short loc_1800A88F0
0x1800a88e9  call    cs:__imp_LocalFree
0x1800a88ef  nop
0x1800a88f0  lea     rcx, [rsp+0D8h+Src]; void *
0x1800a88f8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800a88fd  nop
0x1800a88fe  mov     rcx, [rsp+0D8h+hMem]; hMem
0x1800a8906  test    rcx, rcx
0x1800a8909  jz      short loc_1800A8911
0x1800a890b  call    cs:__imp_LocalFree
0x1800a8911  mov     eax, ebx
0x1800a8913  jmp     short loc_1800A895C
0x1800a8915  mov     rcx, [rsp+0D8h+var_48]; hMem
0x1800a891d  test    rcx, rcx
0x1800a8920  jz      short loc_1800A8929
0x1800a8922  call    cs:__imp_LocalFree
0x1800a8928  nop
0x1800a8929  lea     rcx, [rsp+0D8h+Src]; void *
0x1800a8931  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800a8936  nop
0x1800a8937  mov     rcx, [rsp+0D8h+hMem]; hMem
0x1800a893f  test    rcx, rcx
0x1800a8942  jz      short loc_1800A894A
0x1800a8944  call    cs:__imp_LocalFree
0x1800a894a  xor     eax, eax
0x1800a894c  jmp     short loc_1800A895C
0x1800a894e  mov     eax, 8007000Eh
0x1800a8953  jmp     short loc_1800A895C
0x1800a8955  mov     eax, dword ptr [rsp+0D8h+hMem]
0x1800a895c  mov     rcx, [rsp+0D8h+var_20]
0x1800a8964  xor     rcx, rsp; StackCookie
0x1800a8967  call    __security_check_cookie
0x1800a896c  add     rsp, 0C0h
0x1800a8973  pop     rdi
0x1800a8974  pop     rsi
0x1800a8975  pop     rbx
0x1800a8976  retn
```
