# helium::Container::CreateJob(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180070960`
- end: `0x180070b8d`
- name: `?CreateJob@Container@helium@@CA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `557`
- prototype: `void **__fastcall(void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180071bec`

## callees

- `0x180004f70`
- `0x180013510`
- `0x1800210fc`
- `0x180021118`
- `0x18005431c`
- `0x180070960`
- `0x180097fb8`
- `0x180098374`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180070a3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180070b04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180070a3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180070b04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070a1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070ae5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070a1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070ae5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070af6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070af6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070a30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070b26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070a30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070b26`
- `ntdll!NtCreateJobObject` at `0x180070ab2`
- `ntdll!NtCreateJobObject` at `0x180070ab2`
- `ntdll!RtlInitUnicodeString` at `0x1800709b7`
- `ntdll!RtlInitUnicodeString` at `0x1800709b7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800709f5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800709f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void **__fastcall helium::Container::CreateJob(void **a1)
{
  const WCHAR *v2; // rdx
  const char *v3; // r9
  PSECURITY_DESCRIPTOR v4; // r15
  HLOCAL *v5; // rdi
  HLOCAL v6; // r14
  DWORD LastError; // ebx
  NTSTATUS v8; // eax
  void *v9; // r15
  void **v10; // rdi
  void *v11; // r14
  DWORD v12; // ebx
  HLOCAL hMem; // [rsp+28h] [rbp-71h] BYREF
  HLOCAL *p_hMem; // [rsp+30h] [rbp-69h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-61h] BYREF
  char v17; // [rsp+40h] [rbp-59h]
  void **v18; // [rsp+48h] [rbp-51h]
  void *JobHandle; // [rsp+50h] [rbp-49h] BYREF
  char v20; // [rsp+58h] [rbp-41h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-29h] BYREF
  void **v23; // [rsp+A0h] [rbp+7h]
  PCWSTR SourceString[4]; // [rsp+A8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v23 = a1;
  helium::ContainerPath(SourceString);
  DestinationString = 0;
  v2 = (const WCHAR *)SourceString;
  if ( SourceString[3] > (PCWSTR)7 )
    v2 = SourceString[0];
  RtlInitUnicodeString(&DestinationString, v2);
  hMem = 0;
  p_hMem = &hMem;
  SecurityDescriptor = 0;
  v17 = 1;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:SYG:SYD:(A;;0x001F003F;;;SY)(A;;0x00120004;;;BA)(A;;4;;;S-1-5-80-979556362-403687129-3954533659-2335141334-1547273080)",
          1u,
          &SecurityDescriptor,
          0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xC2,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\heliumcontainer.cpp",
      v3);
  if ( v17 )
  {
    v4 = SecurityDescriptor;
    v5 = p_hMem;
    v6 = *p_hMem;
    if ( *p_hMem )
    {
      LastError = GetLastError();
      LocalFree(v6);
      SetLastError(LastError);
    }
    *v5 = v4;
  }
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 16;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.SecurityDescriptor = hMem;
  ObjectAttributes.SecurityQualityOfService = 0;
  *a1 = 0;
  ScopedPrivileges::Take(&p_hMem);
  v18 = a1;
  JobHandle = 0;
  v20 = 1;
  v8 = NtCreateJobObject(&JobHandle, 0x1F003Fu, &ObjectAttributes);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0xCF,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\heliumcontainer.cpp",
      (const char *)(unsigned int)v8,
      1);
  if ( v20 )
  {
    v9 = JobHandle;
    v10 = v18;
    v11 = *v18;
    if ( (char *)*v18 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v12 = GetLastError();
      CloseHandle(v11);
      SetLastError(v12);
    }
    *v10 = v9;
  }
  ImpersonationReverter::~ImpersonationReverter((ImpersonationReverter *)&p_hMem);
  if ( hMem )
    LocalFree(hMem);
  std::wstring::~wstring(SourceString);
  return a1;
}

```

## disassembly

```asm
0x180070960  mov     [rsp-8+arg_10], rbx
0x180070965  push    rbp
0x180070966  push    rsi
0x180070967  push    rdi
0x180070968  push    r14
0x18007096a  push    r15
0x18007096c  lea     rbp, [rsp-37h]
0x180070971  sub     rsp, 0D0h
0x180070978  mov     rax, cs:__security_cookie
0x18007097f  xor     rax, rsp
0x180070982  mov     [rbp+57h+var_28], rax
0x180070986  mov     rsi, rcx
0x180070989  mov     [rbp+57h+var_50], rcx
0x18007098d  mov     [rbp+57h+var_D0], 0
0x180070994  lea     rcx, [rbp+57h+SourceString]
0x180070998  call    ?ContainerPath@helium@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; helium::ContainerPath(std::wstring const &)
0x18007099d  nop
0x18007099e  xorps   xmm0, xmm0
0x1800709a1  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800709a5  lea     rdx, [rbp+57h+SourceString]
0x1800709a9  cmp     [rbp+57h+var_30], 7
0x1800709ae  cmova   rdx, [rbp+57h+SourceString]; SourceString
0x1800709b3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800709b7  call    cs:__imp_RtlInitUnicodeString
0x1800709be  nop     dword ptr [rax+rax+00h]
0x1800709c3  mov     [rbp+57h+hMem], 0
0x1800709cb  lea     rax, [rbp+57h+hMem]
0x1800709cf  mov     [rbp+57h+var_C0], rax
0x1800709d3  mov     [rbp+57h+SecurityDescriptor], 0
0x1800709db  mov     [rbp+57h+var_B0], 1
0x1800709df  mov     rbx, [rbp+5Fh]
0x1800709e3  xor     r9d, r9d; SecurityDescriptorSize
0x1800709e6  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800709ea  lea     edx, [r9+1]; StringSDRevision
0x1800709ee  lea     rcx, aOSygSydA0x001f; "O:SYG:SYD:(A;;0x001F003F;;;SY)(A;;0x001"...
0x1800709f5  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800709fc  nop     dword ptr [rax+rax+00h]
0x180070a01  test    eax, eax
0x180070a03  jz      loc_180070B78
0x180070a09  cmp     [rbp+57h+var_B0], 0
0x180070a0d  jz      short loc_180070A4D
0x180070a0f  mov     r15, [rbp+57h+SecurityDescriptor]
0x180070a13  mov     rdi, [rbp+57h+var_C0]
0x180070a17  mov     r14, [rdi]
0x180070a1a  test    r14, r14
0x180070a1d  jz      short loc_180070A4A
0x180070a1f  call    cs:__imp_GetLastError
0x180070a26  nop     dword ptr [rax+rax+00h]
0x180070a2b  mov     ebx, eax
0x180070a2d  mov     rcx, r14; hMem
0x180070a30  call    cs:__imp_LocalFree
0x180070a37  nop     dword ptr [rax+rax+00h]
0x180070a3c  mov     ecx, ebx; dwErrCode
0x180070a3e  call    cs:__imp_SetLastError
0x180070a45  nop     dword ptr [rax+rax+00h]
0x180070a4a  mov     [rdi], r15
0x180070a4d  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180070a55  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 10h
0x180070a5d  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180070a65  lea     rax, [rbp+57h+DestinationString]
0x180070a69  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180070a6d  mov     rax, [rbp+57h+hMem]
0x180070a71  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x180070a75  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], 0
0x180070a7d  mov     qword ptr [rsi], 0
0x180070a84  mov     [rbp+57h+var_D0], 1
0x180070a8b  lea     rcx, [rbp+57h+var_C0]
0x180070a8f  call    ?Take@ScopedPrivileges@@SA?AU1@K@Z; ScopedPrivileges::Take(ulong)
0x180070a94  nop
0x180070a95  mov     [rbp+57h+var_A8], rsi
0x180070a99  mov     [rbp+57h+JobHandle], 0
0x180070aa1  mov     [rbp+57h+var_98], 1
0x180070aa5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180070aa9  mov     edx, 1F003Fh; DesiredAccess
0x180070aae  lea     rcx, [rbp+57h+JobHandle]; JobHandle
0x180070ab2  call    cs:__imp_NtCreateJobObject
0x180070ab9  nop     dword ptr [rax+rax+00h]
0x180070abe  mov     rcx, [rbp+5Fh]; this
0x180070ac2  test    eax, eax
0x180070ac4  js      loc_180070B63
0x180070aca  cmp     [rbp+57h+var_98], 0
0x180070ace  jz      short loc_180070B13
0x180070ad0  mov     r15, [rbp+57h+JobHandle]
0x180070ad4  mov     rdi, [rbp+57h+var_A8]
0x180070ad8  mov     r14, [rdi]
0x180070adb  lea     rax, [r14-1]
0x180070adf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180070ae3  ja      short loc_180070B10
0x180070ae5  call    cs:__imp_GetLastError
0x180070aec  nop     dword ptr [rax+rax+00h]
0x180070af1  mov     ebx, eax
0x180070af3  mov     rcx, r14; hObject
0x180070af6  call    cs:__imp_CloseHandle
0x180070afd  nop     dword ptr [rax+rax+00h]
0x180070b02  mov     ecx, ebx; dwErrCode
0x180070b04  call    cs:__imp_SetLastError
0x180070b0b  nop     dword ptr [rax+rax+00h]
0x180070b10  mov     [rdi], r15
0x180070b13  lea     rcx, [rbp+57h+var_C0]; this
0x180070b17  call    ??1ImpersonationReverter@@QEAA@XZ; ImpersonationReverter::~ImpersonationReverter(void)
0x180070b1c  nop
0x180070b1d  mov     rcx, [rbp+57h+hMem]; hMem
0x180070b21  test    rcx, rcx
0x180070b24  jz      short loc_180070B33
0x180070b26  call    cs:__imp_LocalFree
0x180070b2d  nop     dword ptr [rax+rax+00h]
0x180070b32  nop
0x180070b33  lea     rcx, [rbp+57h+SourceString]; void *
0x180070b37  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180070b3c  mov     rax, rsi
0x180070b3f  mov     rcx, [rbp+57h+var_28]
0x180070b43  xor     rcx, rsp; StackCookie
0x180070b46  call    __security_check_cookie
0x180070b4b  mov     rbx, [rsp+0F0h+arg_10]
0x180070b53  add     rsp, 0D0h
0x180070b5a  pop     r15
0x180070b5c  pop     r14
0x180070b5e  pop     rdi
0x180070b5f  pop     rsi
0x180070b60  pop     rbp
0x180070b61  retn
0x180070b63  mov     r9d, eax; char *
0x180070b66  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\execmodel\\des"...
0x180070b6d  mov     edx, 0CFh; void *
0x180070b72  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x180070b78  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\execmodel\\des"...
0x180070b7f  mov     edx, 0C2h; void *
0x180070b84  mov     rcx, rbx; this
0x180070b87  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
