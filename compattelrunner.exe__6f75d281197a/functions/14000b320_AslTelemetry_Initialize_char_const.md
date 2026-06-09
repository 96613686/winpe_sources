# AslTelemetry::Initialize(char const *)

- ea: `0x14000b320`
- end: `0x14000b639`
- name: `?Initialize@AslTelemetry@@QEAAHPEBD@Z`
- size: `793`
- prototype: `__int64 __fastcall(AslTelemetry *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400017a0`

## callees

- `0x140001ba0`
- `0x140001e80`
- `0x14000b320`
- `0x140011880`
- `0x140012764`
- `0x1400a8010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14000b368`
- `ntdll!RtlInitUnicodeString` at `0x14000b3cc`
- `ntdll!RtlInitUnicodeString` at `0x14000b368`
- `ntdll!RtlInitUnicodeString` at `0x14000b3cc`
- `ntdll!LdrGetDllHandle` at `0x14000b37a`
- `ntdll!LdrGetDllHandle` at `0x14000b3de`
- `ntdll!LdrGetDllHandle` at `0x14000b37a`
- `ntdll!LdrGetDllHandle` at `0x14000b3de`
- `ntdll!RtlInitString` at `0x14000b39a`
- `ntdll!RtlInitString` at `0x14000b3f7`
- `ntdll!RtlInitString` at `0x14000b39a`
- `ntdll!RtlInitString` at `0x14000b3f7`
- `ntdll!LdrGetProcedureAddress` at `0x14000b3b3`
- `ntdll!LdrGetProcedureAddress` at `0x14000b410`
- `ntdll!LdrGetProcedureAddress` at `0x14000b3b3`
- `ntdll!LdrGetProcedureAddress` at `0x14000b410`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x14000b4a4`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x14000b4a4`
- `ntdll!NtCreateFile` at `0x14000b537`
- `ntdll!NtCreateFile` at `0x14000b537`
- `ntdll!NtQueryInformationFile` at `0x14000b572`
- `ntdll!NtQueryInformationFile` at `0x14000b572`
- `ntdll!NtClose` at `0x14000b57d`
- `ntdll!NtClose` at `0x14000b57d`

## string_xrefs

- `0x14000b3c1`: `ntdll.dll`
- `0x14000b5a2`: `compattelrunner`
- `0x14000b347`: `kernel32.dll`
- `0x14000b3ec`: `LdrGetDllFullName`

## pseudocode

```c
_BOOL8 __fastcall AslTelemetry::Initialize(AslTelemetry *this, const char *a2)
{
  int v3; // eax
  __int64 v4; // rcx
  int v6; // ebx
  unsigned int v7; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v8; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v9; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v10; // [rsp+6Ch] [rbp-94h] BYREF
  void *FileHandle; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v12[2]; // [rsp+78h] [rbp-88h] BYREF
  PVOID DllHandle; // [rsp+88h] [rbp-78h] BYREF
  PVOID BaseAddress; // [rsp+90h] [rbp-70h] BYREF
  PVOID ProcedureAddress; // [rsp+98h] [rbp-68h] BYREF
  __int64 v16; // [rsp+A0h] [rbp-60h] BYREF
  PVOID v17; // [rsp+A8h] [rbp-58h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-50h] BYREF
  _STRING Name; // [rsp+C0h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp+0h] BYREF
  struct _IO_STATUS_BLOCK v22; // [rsp+110h] [rbp+10h] BYREF
  _DWORD v23[4]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD FileInformation[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v25; // [rsp+140h] [rbp+40h]
  __int128 v26; // [rsp+148h] [rbp+48h]
  _WORD v27[264]; // [rsp+160h] [rbp+60h] BYREF

  DllHandle = 0;
  BaseAddress = 0;
  v16 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"kernel32.dll");
  if ( LdrGetDllHandle(0, 0, &DestinationString, &DllHandle) >= 0 )
  {
    Name = 0;
    RtlInitString(&Name, "RtlPcToFileHeader");
    ProcedureAddress = 0;
    if ( LdrGetProcedureAddress(DllHandle, &Name, 0, &ProcedureAddress) >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"ntdll.dll");
      if ( LdrGetDllHandle(0, 0, &DestinationString, &BaseAddress) >= 0 )
      {
        RtlInitString(&Name, "LdrGetDllFullName");
        v17 = 0;
        if ( LdrGetProcedureAddress(BaseAddress, &Name, 0, &v17) >= 0 )
        {
          v16 = ((__int64 (__fastcall *)(_QWORD, __int64 *))ProcedureAddress)(AslTelemetryCreate, &v16);
          if ( v16 )
          {
            v12[0] = 33947648;
            v12[1] = v27;
            v3 = ((__int64 (__fastcall *)(__int64, _QWORD *))v17)(v16, v12);
            v4 = LOWORD(v12[0]) >> 1;
            if ( (unsigned __int64)(2 * v4) >= 0x208 )
              _report_rangecheckfailure(v4, v4);
            v27[v4] = 0;
            if ( v3 >= 0
              && (unsigned int)v4 <= 0x103
              && (int)RtlDosPathNameToRelativeNtPathName_U_WithStatus(v27, v12, 0, 0) >= 0 )
            {
              ObjectAttributes.ObjectName = (PUNICODE_STRING)v12;
              FileHandle = 0;
              *(_QWORD *)&ObjectAttributes.Length = 48;
              *(_QWORD *)&ObjectAttributes.Attributes = 64;
              IoStatusBlock = 0;
              v23[2] = 257;
              ObjectAttributes.RootDirectory = 0;
              ObjectAttributes.SecurityDescriptor = 0;
              v23[0] = 12;
              v23[1] = 2;
              ObjectAttributes.SecurityQualityOfService = v23;
              if ( NtCreateFile(
                     &FileHandle,
                     0x80100080,
                     &ObjectAttributes,
                     &IoStatusBlock,
                     0,
                     0x80u,
                     1u,
                     1u,
                     0x60u,
                     0,
                     0) >= 0 )
              {
                FileInformation[0] = 0;
                FileInformation[1] = 0;
                v25 = 0;
                v22 = 0;
                v26 = 0;
                NtQueryInformationFile(FileHandle, &v22, FileInformation, 0x28u, FileBasicInformation);
                NtClose(FileHandle);
                if ( v25 < MEMORY[0x7FFE0014] - 155520000000000LL )
                  return 0;
              }
            }
          }
        }
      }
    }
  }
  v6 = AslTelemetryCreate(this, "compattelrunner");
  if ( v6 >= 0 )
  {
    v7 = 0;
    v8 = 0;
    v9 = 0;
    v10 = 0;
    AslFileGetLongVersionForCurrentModule(&v7, &v8, &v9, &v10);
    if ( *(_QWORD *)this )
      *(_QWORD *)(*(_QWORD *)this + 64LL) = v10 | ((v9 | ((v8 | ((unsigned __int64)v7 << 16)) << 16)) << 16);
  }
  return v6 >= 0;
}

```

## disassembly

```asm
0x14000b320  push    rbp
0x14000b322  push    rbx
0x14000b323  push    rsi
0x14000b324  push    rdi
0x14000b325  lea     rbp, [rsp-288h]
0x14000b32d  sub     rsp, 388h
0x14000b334  mov     rax, cs:__security_cookie
0x14000b33b  xor     rax, rsp
0x14000b33e  mov     [rbp+2A0h+var_30], rax
0x14000b345  xor     esi, esi
0x14000b347  lea     rdx, SourceString; "kernel32.dll"
0x14000b34e  mov     rdi, rcx
0x14000b351  mov     [rbp+2A0h+DllHandle], rsi
0x14000b355  xorps   xmm0, xmm0
0x14000b358  mov     [rbp+2A0h+BaseAddress], rsi
0x14000b35c  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x14000b360  mov     [rbp+2A0h+var_300], rsi
0x14000b364  movups  xmmword ptr [rbp+2A0h+DestinationString.Length], xmm0
0x14000b368  call    cs:__imp_RtlInitUnicodeString
0x14000b36e  lea     r9, [rbp+2A0h+DllHandle]; DllHandle
0x14000b372  xor     edx, edx; DllCharacteristics
0x14000b374  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x14000b378  xor     ecx, ecx; DllPath
0x14000b37a  call    cs:__imp_LdrGetDllHandle
0x14000b380  test    eax, eax
0x14000b382  js      loc_14000B5A2
0x14000b388  xorps   xmm0, xmm0
0x14000b38b  lea     rdx, aRtlpctofilehea; "RtlPcToFileHeader"
0x14000b392  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x14000b396  movups  xmmword ptr [rbp+2A0h+Name.Length], xmm0
0x14000b39a  call    cs:__imp_RtlInitString
0x14000b3a0  mov     rcx, [rbp+2A0h+DllHandle]; BaseAddress
0x14000b3a4  lea     r9, [rbp+2A0h+ProcedureAddress]; ProcedureAddress
0x14000b3a8  xor     r8d, r8d; Ordinal
0x14000b3ab  mov     [rbp+2A0h+ProcedureAddress], rsi
0x14000b3af  lea     rdx, [rbp+2A0h+Name]; Name
0x14000b3b3  call    cs:__imp_LdrGetProcedureAddress
0x14000b3b9  test    eax, eax
0x14000b3bb  js      loc_14000B5A2
0x14000b3c1  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x14000b3c8  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x14000b3cc  call    cs:__imp_RtlInitUnicodeString
0x14000b3d2  lea     r9, [rbp+2A0h+BaseAddress]; DllHandle
0x14000b3d6  xor     edx, edx; DllCharacteristics
0x14000b3d8  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x14000b3dc  xor     ecx, ecx; DllPath
0x14000b3de  call    cs:__imp_LdrGetDllHandle
0x14000b3e4  test    eax, eax
0x14000b3e6  js      loc_14000B5A2
0x14000b3ec  lea     rdx, aLdrgetdllfulln; "LdrGetDllFullName"
0x14000b3f3  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x14000b3f7  call    cs:__imp_RtlInitString
0x14000b3fd  mov     rcx, [rbp+2A0h+BaseAddress]; BaseAddress
0x14000b401  lea     r9, [rbp+2A0h+var_2F8]; ProcedureAddress
0x14000b405  xor     r8d, r8d; Ordinal
0x14000b408  mov     [rbp+2A0h+var_2F8], rsi
0x14000b40c  lea     rdx, [rbp+2A0h+Name]; Name
0x14000b410  call    cs:__imp_LdrGetProcedureAddress
0x14000b416  test    eax, eax
0x14000b418  js      loc_14000B5A2
0x14000b41e  mov     rax, [rbp+2A0h+ProcedureAddress]
0x14000b422  lea     rdx, [rbp+2A0h+var_300]
0x14000b426  lea     rcx, AslTelemetryCreate
0x14000b42d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b432  mov     [rbp+2A0h+var_300], rax
0x14000b436  mov     rcx, rax
0x14000b439  test    rax, rax
0x14000b43c  jz      loc_14000B5A2
0x14000b442  lea     rax, [rbp+2A0h+var_240]
0x14000b446  mov     [rsp+3A0h+var_328], 2060000h
0x14000b44f  mov     [rbp+2A0h+var_320], rax
0x14000b453  lea     rdx, [rsp+3A0h+var_328]
0x14000b458  mov     rax, [rbp+2A0h+var_2F8]
0x14000b45c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b461  movzx   ecx, word ptr [rsp+3A0h+var_328]
0x14000b466  shr     ecx, 1
0x14000b468  mov     edx, ecx
0x14000b46a  lea     r8, [rcx+rcx]
0x14000b46e  cmp     r8, 208h
0x14000b475  jnb     loc_14000B633
0x14000b47b  mov     [rbp+r8+2A0h+var_240], si
0x14000b481  test    eax, eax
0x14000b483  js      loc_14000B5A2
0x14000b489  cmp     edx, 103h
0x14000b48f  ja      loc_14000B5A2
0x14000b495  xor     r9d, r9d
0x14000b498  lea     rdx, [rsp+3A0h+var_328]
0x14000b49d  xor     r8d, r8d
0x14000b4a0  lea     rcx, [rbp+2A0h+var_240]
0x14000b4a4  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x14000b4aa  test    eax, eax
0x14000b4ac  js      loc_14000B5A2
0x14000b4b2  mov     [rsp+3A0h+EaLength], esi; EaLength
0x14000b4b6  lea     ecx, [rsi+1]
0x14000b4b9  mov     [rsp+3A0h+EaBuffer], rsi; EaBuffer
0x14000b4be  lea     rax, [rsp+3A0h+var_328]
0x14000b4c3  mov     [rsp+3A0h+CreateOptions], 60h ; '`'; CreateOptions
0x14000b4cb  lea     r9, [rbp+2A0h+IoStatusBlock]; IoStatusBlock
0x14000b4cf  mov     [rsp+3A0h+CreateDisposition], ecx; CreateDisposition
0x14000b4d3  lea     r8, [rbp+2A0h+ObjectAttributes]; ObjectAttributes
0x14000b4d7  mov     [rsp+3A0h+ShareAccess], ecx; ShareAccess
0x14000b4db  xorps   xmm0, xmm0
0x14000b4de  mov     [rbp+2A0h+ObjectAttributes.ObjectName], rax
0x14000b4e2  lea     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x14000b4e7  lea     rax, [rbp+2A0h+var_280]
0x14000b4eb  mov     [rsp+3A0h+FileAttributes], 80h; FileAttributes
0x14000b4f3  mov     edx, 80100080h; DesiredAccess
0x14000b4f8  mov     [rsp+3A0h+AllocationSize], rsi; AllocationSize
0x14000b4fd  mov     [rsp+3A0h+FileHandle], rsi
0x14000b502  mov     qword ptr [rbp+2A0h+ObjectAttributes.Length], 30h ; '0'
0x14000b50a  mov     qword ptr [rbp+2A0h+ObjectAttributes.Attributes], 40h ; '@'
0x14000b512  movups  xmmword ptr [rbp+2A0h+IoStatusBlock], xmm0
0x14000b516  mov     [rbp+2A0h+var_278], 101h
0x14000b51d  mov     [rbp+2A0h+ObjectAttributes.RootDirectory], rsi
0x14000b521  mov     [rbp+2A0h+ObjectAttributes.SecurityDescriptor], rsi
0x14000b525  mov     [rbp+2A0h+var_280], 0Ch
0x14000b52c  mov     [rbp+2A0h+var_27C], 2
0x14000b533  mov     [rbp+2A0h+ObjectAttributes.SecurityQualityOfService], rax
0x14000b537  call    cs:__imp_NtCreateFile
0x14000b53d  test    eax, eax
0x14000b53f  js      short loc_14000B5A2
0x14000b541  mov     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x14000b546  lea     r9d, [rsi+28h]; Length
0x14000b54a  xorps   xmm0, xmm0
0x14000b54d  mov     [rbp+2A0h+FileInformation], rsi
0x14000b551  lea     r8, [rbp+2A0h+FileInformation]; FileInformation
0x14000b555  mov     [rbp+2A0h+var_268], rsi
0x14000b559  lea     rdx, [rbp+2A0h+var_290]; IoStatusBlock
0x14000b55d  mov     [rbp+2A0h+var_260], rsi
0x14000b561  movups  xmmword ptr [rbp+2A0h+var_290], xmm0
0x14000b565  mov     dword ptr [rsp+3A0h+AllocationSize], 4; FileInformationClass
0x14000b56d  movdqu  [rbp+2A0h+var_258], xmm0
0x14000b572  call    cs:__imp_NtQueryInformationFile
0x14000b578  mov     rcx, [rsp+3A0h+FileHandle]; Handle
0x14000b57d  call    cs:__imp_NtClose
0x14000b583  mov     eax, 7FFE0014h
0x14000b588  mov     rcx, 0FFFF728E2DA50000h
0x14000b592  mov     rax, [rax]
0x14000b595  add     rax, rcx
0x14000b598  cmp     [rbp+2A0h+var_260], rax
0x14000b59c  jge     short loc_14000B5A2
0x14000b59e  xor     eax, eax
0x14000b5a0  jmp     short loc_14000B618
0x14000b5a2  lea     rdx, aCompattelrunne; "compattelrunner"
0x14000b5a9  mov     rcx, rdi
0x14000b5ac  call    AslTelemetryCreate
0x14000b5b1  mov     ebx, eax
0x14000b5b3  test    eax, eax
0x14000b5b5  js      short loc_14000B611
0x14000b5b7  lea     r9, [rsp+3A0h+var_334]
0x14000b5bc  mov     [rsp+3A0h+var_340], esi
0x14000b5c0  lea     r8, [rsp+3A0h+var_338]
0x14000b5c5  mov     [rsp+3A0h+var_33C], esi
0x14000b5c9  lea     rdx, [rsp+3A0h+var_33C]
0x14000b5ce  mov     [rsp+3A0h+var_338], esi
0x14000b5d2  lea     rcx, [rsp+3A0h+var_340]
0x14000b5d7  mov     [rsp+3A0h+var_334], esi
0x14000b5db  call    AslFileGetLongVersionForCurrentModule
0x14000b5e0  mov     r8, [rdi]
0x14000b5e3  test    r8, r8
0x14000b5e6  jz      short loc_14000B611
0x14000b5e8  mov     ecx, [rsp+3A0h+var_338]
0x14000b5ec  mov     edx, [rsp+3A0h+var_340]
0x14000b5f0  mov     eax, [rsp+3A0h+var_33C]
0x14000b5f4  shl     rdx, 10h
0x14000b5f8  or      rdx, rax
0x14000b5fb  shl     rdx, 10h
0x14000b5ff  or      rdx, rcx
0x14000b602  mov     ecx, [rsp+3A0h+var_334]
0x14000b606  shl     rdx, 10h
0x14000b60a  or      rdx, rcx
0x14000b60d  mov     [r8+40h], rdx
0x14000b611  not     ebx
0x14000b613  shr     ebx, 1Fh
0x14000b616  mov     eax, ebx
0x14000b618  mov     rcx, [rbp+2A0h+var_30]
0x14000b61f  xor     rcx, rsp; StackCookie
0x14000b622  call    __security_check_cookie
0x14000b627  add     rsp, 388h
0x14000b62e  pop     rdi
0x14000b62f  pop     rsi
0x14000b630  pop     rbx
0x14000b631  pop     rbp
0x14000b632  retn
0x14000b633  call    __report_rangecheckfailure
```
