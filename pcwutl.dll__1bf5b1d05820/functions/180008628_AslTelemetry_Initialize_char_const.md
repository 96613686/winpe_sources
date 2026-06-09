# AslTelemetry::Initialize(char const *)

- ea: `0x180008628`
- end: `0x180008941`
- name: `?Initialize@AslTelemetry@@QEAAHPEBD@Z`
- size: `793`
- prototype: `__int64 __fastcall(AslTelemetry *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800014c0`

## callees

- `0x180002538`
- `0x180008628`
- `0x18000d788`
- `0x1800171d0`
- `0x1800191f0`
- `0x18001a010`

## import_xrefs

- `ntdll!LdrGetDllHandle` at `0x180008682`
- `ntdll!LdrGetDllHandle` at `0x1800086e6`
- `ntdll!LdrGetDllHandle` at `0x180008682`
- `ntdll!LdrGetDllHandle` at `0x1800086e6`
- `ntdll!RtlInitString` at `0x1800086a2`
- `ntdll!RtlInitString` at `0x1800086ff`
- `ntdll!RtlInitString` at `0x1800086a2`
- `ntdll!RtlInitString` at `0x1800086ff`
- `ntdll!LdrGetProcedureAddress` at `0x1800086bb`
- `ntdll!LdrGetProcedureAddress` at `0x180008718`
- `ntdll!LdrGetProcedureAddress` at `0x1800086bb`
- `ntdll!LdrGetProcedureAddress` at `0x180008718`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1800087ac`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1800087ac`
- `ntdll!NtCreateFile` at `0x18000883f`
- `ntdll!NtCreateFile` at `0x18000883f`
- `ntdll!NtClose` at `0x180008885`
- `ntdll!NtClose` at `0x180008885`
- `ntdll!NtQueryInformationFile` at `0x18000887a`
- `ntdll!NtQueryInformationFile` at `0x18000887a`
- `ntdll!RtlInitUnicodeString` at `0x180008670`
- `ntdll!RtlInitUnicodeString` at `0x1800086d4`
- `ntdll!RtlInitUnicodeString` at `0x180008670`
- `ntdll!RtlInitUnicodeString` at `0x1800086d4`

## string_xrefs

- `0x1800086c9`: `ntdll.dll`
- `0x1800088aa`: `CompatTroubleShooter`
- `0x18000864f`: `kernel32.dll`
- `0x1800086f4`: `LdrGetDllFullName`

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
  v6 = AslTelemetryCreate(this, "CompatTroubleShooter");
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
0x180008628  push    rbp
0x18000862a  push    rbx
0x18000862b  push    rsi
0x18000862c  push    rdi
0x18000862d  lea     rbp, [rsp-288h]
0x180008635  sub     rsp, 388h
0x18000863c  mov     rax, cs:__security_cookie
0x180008643  xor     rax, rsp
0x180008646  mov     [rbp+2A0h+var_30], rax
0x18000864d  xor     esi, esi
0x18000864f  lea     rdx, SourceString; "kernel32.dll"
0x180008656  mov     rdi, rcx
0x180008659  mov     [rbp+2A0h+DllHandle], rsi
0x18000865d  xorps   xmm0, xmm0
0x180008660  mov     [rbp+2A0h+BaseAddress], rsi
0x180008664  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x180008668  mov     [rbp+2A0h+var_300], rsi
0x18000866c  movups  xmmword ptr [rbp+2A0h+DestinationString.Length], xmm0
0x180008670  call    cs:__imp_RtlInitUnicodeString
0x180008676  lea     r9, [rbp+2A0h+DllHandle]; DllHandle
0x18000867a  xor     edx, edx; DllCharacteristics
0x18000867c  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x180008680  xor     ecx, ecx; DllPath
0x180008682  call    cs:__imp_LdrGetDllHandle
0x180008688  test    eax, eax
0x18000868a  js      loc_1800088AA
0x180008690  xorps   xmm0, xmm0
0x180008693  lea     rdx, aRtlpctofilehea; "RtlPcToFileHeader"
0x18000869a  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x18000869e  movups  xmmword ptr [rbp+2A0h+Name.Length], xmm0
0x1800086a2  call    cs:__imp_RtlInitString
0x1800086a8  mov     rcx, [rbp+2A0h+DllHandle]; BaseAddress
0x1800086ac  lea     r9, [rbp+2A0h+ProcedureAddress]; ProcedureAddress
0x1800086b0  xor     r8d, r8d; Ordinal
0x1800086b3  mov     [rbp+2A0h+ProcedureAddress], rsi
0x1800086b7  lea     rdx, [rbp+2A0h+Name]; Name
0x1800086bb  call    cs:__imp_LdrGetProcedureAddress
0x1800086c1  test    eax, eax
0x1800086c3  js      loc_1800088AA
0x1800086c9  lea     rdx, LibFileName; "ntdll.dll"
0x1800086d0  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x1800086d4  call    cs:__imp_RtlInitUnicodeString
0x1800086da  lea     r9, [rbp+2A0h+BaseAddress]; DllHandle
0x1800086de  xor     edx, edx; DllCharacteristics
0x1800086e0  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x1800086e4  xor     ecx, ecx; DllPath
0x1800086e6  call    cs:__imp_LdrGetDllHandle
0x1800086ec  test    eax, eax
0x1800086ee  js      loc_1800088AA
0x1800086f4  lea     rdx, aLdrgetdllfulln; "LdrGetDllFullName"
0x1800086fb  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x1800086ff  call    cs:__imp_RtlInitString
0x180008705  mov     rcx, [rbp+2A0h+BaseAddress]; BaseAddress
0x180008709  lea     r9, [rbp+2A0h+var_2F8]; ProcedureAddress
0x18000870d  xor     r8d, r8d; Ordinal
0x180008710  mov     [rbp+2A0h+var_2F8], rsi
0x180008714  lea     rdx, [rbp+2A0h+Name]; Name
0x180008718  call    cs:__imp_LdrGetProcedureAddress
0x18000871e  test    eax, eax
0x180008720  js      loc_1800088AA
0x180008726  mov     rax, [rbp+2A0h+ProcedureAddress]
0x18000872a  lea     rdx, [rbp+2A0h+var_300]
0x18000872e  lea     rcx, AslTelemetryCreate
0x180008735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000873a  mov     [rbp+2A0h+var_300], rax
0x18000873e  mov     rcx, rax
0x180008741  test    rax, rax
0x180008744  jz      loc_1800088AA
0x18000874a  lea     rax, [rbp+2A0h+var_240]
0x18000874e  mov     [rsp+3A0h+var_328], 2060000h
0x180008757  mov     [rbp+2A0h+var_320], rax
0x18000875b  lea     rdx, [rsp+3A0h+var_328]
0x180008760  mov     rax, [rbp+2A0h+var_2F8]
0x180008764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008769  movzx   ecx, word ptr [rsp+3A0h+var_328]
0x18000876e  shr     ecx, 1
0x180008770  mov     edx, ecx
0x180008772  lea     r8, [rcx+rcx]
0x180008776  cmp     r8, 208h
0x18000877d  jnb     loc_18000893B
0x180008783  mov     [rbp+r8+2A0h+var_240], si
0x180008789  test    eax, eax
0x18000878b  js      loc_1800088AA
0x180008791  cmp     edx, 103h
0x180008797  ja      loc_1800088AA
0x18000879d  xor     r9d, r9d
0x1800087a0  lea     rdx, [rsp+3A0h+var_328]
0x1800087a5  xor     r8d, r8d
0x1800087a8  lea     rcx, [rbp+2A0h+var_240]
0x1800087ac  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x1800087b2  test    eax, eax
0x1800087b4  js      loc_1800088AA
0x1800087ba  mov     [rsp+3A0h+EaLength], esi; EaLength
0x1800087be  lea     ecx, [rsi+1]
0x1800087c1  mov     [rsp+3A0h+EaBuffer], rsi; EaBuffer
0x1800087c6  lea     rax, [rsp+3A0h+var_328]
0x1800087cb  mov     [rsp+3A0h+CreateOptions], 60h ; '`'; CreateOptions
0x1800087d3  lea     r9, [rbp+2A0h+IoStatusBlock]; IoStatusBlock
0x1800087d7  mov     [rsp+3A0h+CreateDisposition], ecx; CreateDisposition
0x1800087db  lea     r8, [rbp+2A0h+ObjectAttributes]; ObjectAttributes
0x1800087df  mov     [rsp+3A0h+ShareAccess], ecx; ShareAccess
0x1800087e3  xorps   xmm0, xmm0
0x1800087e6  mov     [rbp+2A0h+ObjectAttributes.ObjectName], rax
0x1800087ea  lea     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x1800087ef  lea     rax, [rbp+2A0h+var_280]
0x1800087f3  mov     [rsp+3A0h+FileAttributes], 80h; FileAttributes
0x1800087fb  mov     edx, 80100080h; DesiredAccess
0x180008800  mov     [rsp+3A0h+AllocationSize], rsi; AllocationSize
0x180008805  mov     [rsp+3A0h+FileHandle], rsi
0x18000880a  mov     qword ptr [rbp+2A0h+ObjectAttributes.Length], 30h ; '0'
0x180008812  mov     qword ptr [rbp+2A0h+ObjectAttributes.Attributes], 40h ; '@'
0x18000881a  movups  xmmword ptr [rbp+2A0h+IoStatusBlock], xmm0
0x18000881e  mov     [rbp+2A0h+var_278], 101h
0x180008825  mov     [rbp+2A0h+ObjectAttributes.RootDirectory], rsi
0x180008829  mov     [rbp+2A0h+ObjectAttributes.SecurityDescriptor], rsi
0x18000882d  mov     [rbp+2A0h+var_280], 0Ch
0x180008834  mov     [rbp+2A0h+var_27C], 2
0x18000883b  mov     [rbp+2A0h+ObjectAttributes.SecurityQualityOfService], rax
0x18000883f  call    cs:__imp_NtCreateFile
0x180008845  test    eax, eax
0x180008847  js      short loc_1800088AA
0x180008849  mov     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x18000884e  lea     r9d, [rsi+28h]; Length
0x180008852  xorps   xmm0, xmm0
0x180008855  mov     [rbp+2A0h+FileInformation], rsi
0x180008859  lea     r8, [rbp+2A0h+FileInformation]; FileInformation
0x18000885d  mov     [rbp+2A0h+var_268], rsi
0x180008861  lea     rdx, [rbp+2A0h+var_290]; IoStatusBlock
0x180008865  mov     [rbp+2A0h+var_260], rsi
0x180008869  movups  xmmword ptr [rbp+2A0h+var_290], xmm0
0x18000886d  mov     dword ptr [rsp+3A0h+AllocationSize], 4; FileInformationClass
0x180008875  movdqu  [rbp+2A0h+var_258], xmm0
0x18000887a  call    cs:__imp_NtQueryInformationFile
0x180008880  mov     rcx, [rsp+3A0h+FileHandle]; Handle
0x180008885  call    cs:__imp_NtClose
0x18000888b  mov     eax, 7FFE0014h
0x180008890  mov     rcx, 0FFFF728E2DA50000h
0x18000889a  mov     rax, [rax]
0x18000889d  add     rax, rcx
0x1800088a0  cmp     [rbp+2A0h+var_260], rax
0x1800088a4  jge     short loc_1800088AA
0x1800088a6  xor     eax, eax
0x1800088a8  jmp     short loc_180008920
0x1800088aa  lea     rdx, aCompattroubles; "CompatTroubleShooter"
0x1800088b1  mov     rcx, rdi
0x1800088b4  call    AslTelemetryCreate
0x1800088b9  mov     ebx, eax
0x1800088bb  test    eax, eax
0x1800088bd  js      short loc_180008919
0x1800088bf  lea     r9, [rsp+3A0h+var_334]
0x1800088c4  mov     [rsp+3A0h+var_340], esi
0x1800088c8  lea     r8, [rsp+3A0h+var_338]
0x1800088cd  mov     [rsp+3A0h+var_33C], esi
0x1800088d1  lea     rdx, [rsp+3A0h+var_33C]
0x1800088d6  mov     [rsp+3A0h+var_338], esi
0x1800088da  lea     rcx, [rsp+3A0h+var_340]
0x1800088df  mov     [rsp+3A0h+var_334], esi
0x1800088e3  call    AslFileGetLongVersionForCurrentModule
0x1800088e8  mov     r8, [rdi]
0x1800088eb  test    r8, r8
0x1800088ee  jz      short loc_180008919
0x1800088f0  mov     ecx, [rsp+3A0h+var_338]
0x1800088f4  mov     edx, [rsp+3A0h+var_340]
0x1800088f8  mov     eax, [rsp+3A0h+var_33C]
0x1800088fc  shl     rdx, 10h
0x180008900  or      rdx, rax
0x180008903  shl     rdx, 10h
0x180008907  or      rdx, rcx
0x18000890a  mov     ecx, [rsp+3A0h+var_334]
0x18000890e  shl     rdx, 10h
0x180008912  or      rdx, rcx
0x180008915  mov     [r8+40h], rdx
0x180008919  not     ebx
0x18000891b  shr     ebx, 1Fh
0x18000891e  mov     eax, ebx
0x180008920  mov     rcx, [rbp+2A0h+var_30]
0x180008927  xor     rcx, rsp; StackCookie
0x18000892a  call    __security_check_cookie
0x18000892f  add     rsp, 388h
0x180008936  pop     rdi
0x180008937  pop     rsi
0x180008938  pop     rbx
0x180008939  pop     rbp
0x18000893a  retn
0x18000893b  call    __report_rangecheckfailure
```
