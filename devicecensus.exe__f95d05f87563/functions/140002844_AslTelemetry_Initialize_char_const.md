# AslTelemetry::Initialize(char const *)

- ea: `0x140002844`
- end: `0x140002b5d`
- name: `?Initialize@AslTelemetry@@QEAAHPEBD@Z`
- size: `793`
- prototype: `_BOOL8 __fastcall(AslTelemetry *this, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400014c0`

## callees

- `0x140001d68`
- `0x140002844`
- `0x1400060c0`
- `0x1400070e8`
- `0x1400115f0`
- `0x140012010`

## import_xrefs

- `ntdll!NtCreateFile` at `0x140002a5b`
- `ntdll!NtCreateFile` at `0x140002a5b`
- `ntdll!RtlInitString` at `0x1400028be`
- `ntdll!RtlInitString` at `0x14000291b`
- `ntdll!RtlInitString` at `0x1400028be`
- `ntdll!RtlInitString` at `0x14000291b`
- `ntdll!NtQueryInformationFile` at `0x140002a96`
- `ntdll!NtQueryInformationFile` at `0x140002a96`
- `ntdll!NtClose` at `0x140002aa1`
- `ntdll!NtClose` at `0x140002aa1`
- `ntdll!RtlInitUnicodeString` at `0x14000288c`
- `ntdll!RtlInitUnicodeString` at `0x1400028f0`
- `ntdll!RtlInitUnicodeString` at `0x14000288c`
- `ntdll!RtlInitUnicodeString` at `0x1400028f0`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1400029c8`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1400029c8`
- `ntdll!LdrGetDllHandle` at `0x14000289e`
- `ntdll!LdrGetDllHandle` at `0x140002902`
- `ntdll!LdrGetDllHandle` at `0x14000289e`
- `ntdll!LdrGetDllHandle` at `0x140002902`
- `ntdll!LdrGetProcedureAddress` at `0x1400028d7`
- `ntdll!LdrGetProcedureAddress` at `0x140002934`
- `ntdll!LdrGetProcedureAddress` at `0x1400028d7`
- `ntdll!LdrGetProcedureAddress` at `0x140002934`

## string_xrefs

- `0x14000286b`: `kernel32.dll`
- `0x1400028e5`: `ntdll.dll`
- `0x140002910`: `LdrGetDllFullName`

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
  v6 = AslTelemetryCreate(this, "census_exe");
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
0x140002844  push    rbp
0x140002846  push    rbx
0x140002847  push    rsi
0x140002848  push    rdi
0x140002849  lea     rbp, [rsp-288h]
0x140002851  sub     rsp, 388h
0x140002858  mov     rax, cs:__security_cookie
0x14000285f  xor     rax, rsp
0x140002862  mov     [rbp+2A0h+var_30], rax
0x140002869  xor     esi, esi
0x14000286b  lea     rdx, SourceString; "kernel32.dll"
0x140002872  mov     rdi, rcx
0x140002875  mov     [rbp+2A0h+DllHandle], rsi
0x140002879  xorps   xmm0, xmm0
0x14000287c  mov     [rbp+2A0h+BaseAddress], rsi
0x140002880  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x140002884  mov     [rbp+2A0h+var_300], rsi
0x140002888  movups  xmmword ptr [rbp+2A0h+DestinationString.Length], xmm0
0x14000288c  call    cs:__imp_RtlInitUnicodeString
0x140002892  lea     r9, [rbp+2A0h+DllHandle]; DllHandle
0x140002896  xor     edx, edx; DllCharacteristics
0x140002898  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x14000289c  xor     ecx, ecx; DllPath
0x14000289e  call    cs:__imp_LdrGetDllHandle
0x1400028a4  test    eax, eax
0x1400028a6  js      loc_140002AC6
0x1400028ac  xorps   xmm0, xmm0
0x1400028af  lea     rdx, aRtlpctofilehea; "RtlPcToFileHeader"
0x1400028b6  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x1400028ba  movups  xmmword ptr [rbp+2A0h+Name.Length], xmm0
0x1400028be  call    cs:__imp_RtlInitString
0x1400028c4  mov     rcx, [rbp+2A0h+DllHandle]; BaseAddress
0x1400028c8  lea     r9, [rbp+2A0h+ProcedureAddress]; ProcedureAddress
0x1400028cc  xor     r8d, r8d; Ordinal
0x1400028cf  mov     [rbp+2A0h+ProcedureAddress], rsi
0x1400028d3  lea     rdx, [rbp+2A0h+Name]; Name
0x1400028d7  call    cs:__imp_LdrGetProcedureAddress
0x1400028dd  test    eax, eax
0x1400028df  js      loc_140002AC6
0x1400028e5  lea     rdx, LibFileName; "ntdll.dll"
0x1400028ec  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x1400028f0  call    cs:__imp_RtlInitUnicodeString
0x1400028f6  lea     r9, [rbp+2A0h+BaseAddress]; DllHandle
0x1400028fa  xor     edx, edx; DllCharacteristics
0x1400028fc  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x140002900  xor     ecx, ecx; DllPath
0x140002902  call    cs:__imp_LdrGetDllHandle
0x140002908  test    eax, eax
0x14000290a  js      loc_140002AC6
0x140002910  lea     rdx, aLdrgetdllfulln; "LdrGetDllFullName"
0x140002917  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x14000291b  call    cs:__imp_RtlInitString
0x140002921  mov     rcx, [rbp+2A0h+BaseAddress]; BaseAddress
0x140002925  lea     r9, [rbp+2A0h+var_2F8]; ProcedureAddress
0x140002929  xor     r8d, r8d; Ordinal
0x14000292c  mov     [rbp+2A0h+var_2F8], rsi
0x140002930  lea     rdx, [rbp+2A0h+Name]; Name
0x140002934  call    cs:__imp_LdrGetProcedureAddress
0x14000293a  test    eax, eax
0x14000293c  js      loc_140002AC6
0x140002942  mov     rax, [rbp+2A0h+ProcedureAddress]
0x140002946  lea     rdx, [rbp+2A0h+var_300]
0x14000294a  lea     rcx, AslTelemetryCreate
0x140002951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002956  mov     [rbp+2A0h+var_300], rax
0x14000295a  mov     rcx, rax
0x14000295d  test    rax, rax
0x140002960  jz      loc_140002AC6
0x140002966  lea     rax, [rbp+2A0h+var_240]
0x14000296a  mov     [rsp+3A0h+var_328], 2060000h
0x140002973  mov     [rbp+2A0h+var_320], rax
0x140002977  lea     rdx, [rsp+3A0h+var_328]
0x14000297c  mov     rax, [rbp+2A0h+var_2F8]
0x140002980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002985  movzx   ecx, word ptr [rsp+3A0h+var_328]
0x14000298a  shr     ecx, 1
0x14000298c  mov     edx, ecx
0x14000298e  lea     r8, [rcx+rcx]
0x140002992  cmp     r8, 208h
0x140002999  jnb     loc_140002B57
0x14000299f  mov     [rbp+r8+2A0h+var_240], si
0x1400029a5  test    eax, eax
0x1400029a7  js      loc_140002AC6
0x1400029ad  cmp     edx, 103h
0x1400029b3  ja      loc_140002AC6
0x1400029b9  xor     r9d, r9d
0x1400029bc  lea     rdx, [rsp+3A0h+var_328]
0x1400029c1  xor     r8d, r8d
0x1400029c4  lea     rcx, [rbp+2A0h+var_240]
0x1400029c8  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x1400029ce  test    eax, eax
0x1400029d0  js      loc_140002AC6
0x1400029d6  mov     [rsp+3A0h+EaLength], esi; EaLength
0x1400029da  lea     ecx, [rsi+1]
0x1400029dd  mov     [rsp+3A0h+EaBuffer], rsi; EaBuffer
0x1400029e2  lea     rax, [rsp+3A0h+var_328]
0x1400029e7  mov     [rsp+3A0h+CreateOptions], 60h ; '`'; CreateOptions
0x1400029ef  lea     r9, [rbp+2A0h+IoStatusBlock]; IoStatusBlock
0x1400029f3  mov     [rsp+3A0h+CreateDisposition], ecx; CreateDisposition
0x1400029f7  lea     r8, [rbp+2A0h+ObjectAttributes]; ObjectAttributes
0x1400029fb  mov     [rsp+3A0h+ShareAccess], ecx; ShareAccess
0x1400029ff  xorps   xmm0, xmm0
0x140002a02  mov     [rbp+2A0h+ObjectAttributes.ObjectName], rax
0x140002a06  lea     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x140002a0b  lea     rax, [rbp+2A0h+var_280]
0x140002a0f  mov     [rsp+3A0h+FileAttributes], 80h; FileAttributes
0x140002a17  mov     edx, 80100080h; DesiredAccess
0x140002a1c  mov     [rsp+3A0h+AllocationSize], rsi; AllocationSize
0x140002a21  mov     [rsp+3A0h+FileHandle], rsi
0x140002a26  mov     qword ptr [rbp+2A0h+ObjectAttributes.Length], 30h ; '0'
0x140002a2e  mov     qword ptr [rbp+2A0h+ObjectAttributes.Attributes], 40h ; '@'
0x140002a36  movups  xmmword ptr [rbp+2A0h+IoStatusBlock], xmm0
0x140002a3a  mov     [rbp+2A0h+var_278], 101h
0x140002a41  mov     [rbp+2A0h+ObjectAttributes.RootDirectory], rsi
0x140002a45  mov     [rbp+2A0h+ObjectAttributes.SecurityDescriptor], rsi
0x140002a49  mov     [rbp+2A0h+var_280], 0Ch
0x140002a50  mov     [rbp+2A0h+var_27C], 2
0x140002a57  mov     [rbp+2A0h+ObjectAttributes.SecurityQualityOfService], rax
0x140002a5b  call    cs:__imp_NtCreateFile
0x140002a61  test    eax, eax
0x140002a63  js      short loc_140002AC6
0x140002a65  mov     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x140002a6a  lea     r9d, [rsi+28h]; Length
0x140002a6e  xorps   xmm0, xmm0
0x140002a71  mov     [rbp+2A0h+FileInformation], rsi
0x140002a75  lea     r8, [rbp+2A0h+FileInformation]; FileInformation
0x140002a79  mov     [rbp+2A0h+var_268], rsi
0x140002a7d  lea     rdx, [rbp+2A0h+var_290]; IoStatusBlock
0x140002a81  mov     [rbp+2A0h+var_260], rsi
0x140002a85  movups  xmmword ptr [rbp+2A0h+var_290], xmm0
0x140002a89  mov     dword ptr [rsp+3A0h+AllocationSize], 4; FileInformationClass
0x140002a91  movdqu  [rbp+2A0h+var_258], xmm0
0x140002a96  call    cs:__imp_NtQueryInformationFile
0x140002a9c  mov     rcx, [rsp+3A0h+FileHandle]; Handle
0x140002aa1  call    cs:__imp_NtClose
0x140002aa7  mov     eax, 7FFE0014h
0x140002aac  mov     rcx, 0FFFF728E2DA50000h
0x140002ab6  mov     rax, [rax]
0x140002ab9  add     rax, rcx
0x140002abc  cmp     [rbp+2A0h+var_260], rax
0x140002ac0  jge     short loc_140002AC6
0x140002ac2  xor     eax, eax
0x140002ac4  jmp     short loc_140002B3C
0x140002ac6  lea     rdx, aCensusExe; "census_exe"
0x140002acd  mov     rcx, rdi
0x140002ad0  call    AslTelemetryCreate
0x140002ad5  mov     ebx, eax
0x140002ad7  test    eax, eax
0x140002ad9  js      short loc_140002B35
0x140002adb  lea     r9, [rsp+3A0h+var_334]
0x140002ae0  mov     [rsp+3A0h+var_340], esi
0x140002ae4  lea     r8, [rsp+3A0h+var_338]
0x140002ae9  mov     [rsp+3A0h+var_33C], esi
0x140002aed  lea     rdx, [rsp+3A0h+var_33C]
0x140002af2  mov     [rsp+3A0h+var_338], esi
0x140002af6  lea     rcx, [rsp+3A0h+var_340]
0x140002afb  mov     [rsp+3A0h+var_334], esi
0x140002aff  call    AslFileGetLongVersionForCurrentModule
0x140002b04  mov     r8, [rdi]
0x140002b07  test    r8, r8
0x140002b0a  jz      short loc_140002B35
0x140002b0c  mov     ecx, [rsp+3A0h+var_338]
0x140002b10  mov     edx, [rsp+3A0h+var_340]
0x140002b14  mov     eax, [rsp+3A0h+var_33C]
0x140002b18  shl     rdx, 10h
0x140002b1c  or      rdx, rax
0x140002b1f  shl     rdx, 10h
0x140002b23  or      rdx, rcx
0x140002b26  mov     ecx, [rsp+3A0h+var_334]
0x140002b2a  shl     rdx, 10h
0x140002b2e  or      rdx, rcx
0x140002b31  mov     [r8+40h], rdx
0x140002b35  not     ebx
0x140002b37  shr     ebx, 1Fh
0x140002b3a  mov     eax, ebx
0x140002b3c  mov     rcx, [rbp+2A0h+var_30]
0x140002b43  xor     rcx, rsp; StackCookie
0x140002b46  call    __security_check_cookie
0x140002b4b  add     rsp, 388h
0x140002b52  pop     rdi
0x140002b53  pop     rsi
0x140002b54  pop     rbx
0x140002b55  pop     rbp
0x140002b56  retn
0x140002b57  call    __report_rangecheckfailure
```
