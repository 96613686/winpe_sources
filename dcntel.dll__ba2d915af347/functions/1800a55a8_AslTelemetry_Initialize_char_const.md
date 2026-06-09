# AslTelemetry::Initialize(char const *)

- ea: `0x1800a55a8`
- end: `0x1800a58c1`
- name: `?Initialize@AslTelemetry@@QEAAHPEBD@Z`
- size: `793`
- prototype: `__int64 __fastcall(AslTelemetry *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006560`

## callees

- `0x180008dc0`
- `0x1800097c0`
- `0x1800a55a8`
- `0x1801679a4`
- `0x180169ce0`
- `0x18018e010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800a55f0`
- `ntdll!RtlInitUnicodeString` at `0x1800a5654`
- `ntdll!RtlInitUnicodeString` at `0x1800a55f0`
- `ntdll!RtlInitUnicodeString` at `0x1800a5654`
- `ntdll!LdrGetDllHandle` at `0x1800a5602`
- `ntdll!LdrGetDllHandle` at `0x1800a5666`
- `ntdll!LdrGetDllHandle` at `0x1800a5602`
- `ntdll!LdrGetDllHandle` at `0x1800a5666`
- `ntdll!RtlInitString` at `0x1800a5622`
- `ntdll!RtlInitString` at `0x1800a567f`
- `ntdll!RtlInitString` at `0x1800a5622`
- `ntdll!RtlInitString` at `0x1800a567f`
- `ntdll!LdrGetProcedureAddress` at `0x1800a563b`
- `ntdll!LdrGetProcedureAddress` at `0x1800a5698`
- `ntdll!LdrGetProcedureAddress` at `0x1800a563b`
- `ntdll!LdrGetProcedureAddress` at `0x1800a5698`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1800a572c`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1800a572c`
- `ntdll!NtCreateFile` at `0x1800a57bf`
- `ntdll!NtCreateFile` at `0x1800a57bf`
- `ntdll!NtQueryInformationFile` at `0x1800a57fa`
- `ntdll!NtQueryInformationFile` at `0x1800a57fa`
- `ntdll!NtClose` at `0x1800a5805`
- `ntdll!NtClose` at `0x1800a5805`

## string_xrefs

- `0x1800a5649`: `ntdll.dll`
- `0x1800a5674`: `LdrGetDllFullName`
- `0x1800a55cf`: `kernel32.dll`

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
  v6 = AslTelemetryCreate(this, "census");
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
0x1800a55a8  push    rbp
0x1800a55aa  push    rbx
0x1800a55ab  push    rsi
0x1800a55ac  push    rdi
0x1800a55ad  lea     rbp, [rsp-288h]
0x1800a55b5  sub     rsp, 388h
0x1800a55bc  mov     rax, cs:__security_cookie
0x1800a55c3  xor     rax, rsp
0x1800a55c6  mov     [rbp+2A0h+var_30], rax
0x1800a55cd  xor     esi, esi
0x1800a55cf  lea     rdx, SourceString; "kernel32.dll"
0x1800a55d6  mov     rdi, rcx
0x1800a55d9  mov     [rbp+2A0h+DllHandle], rsi
0x1800a55dd  xorps   xmm0, xmm0
0x1800a55e0  mov     [rbp+2A0h+BaseAddress], rsi
0x1800a55e4  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x1800a55e8  mov     [rbp+2A0h+var_300], rsi
0x1800a55ec  movups  xmmword ptr [rbp+2A0h+DestinationString.Length], xmm0
0x1800a55f0  call    cs:__imp_RtlInitUnicodeString
0x1800a55f6  lea     r9, [rbp+2A0h+DllHandle]; DllHandle
0x1800a55fa  xor     edx, edx; DllCharacteristics
0x1800a55fc  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x1800a5600  xor     ecx, ecx; DllPath
0x1800a5602  call    cs:__imp_LdrGetDllHandle
0x1800a5608  test    eax, eax
0x1800a560a  js      loc_1800A582A
0x1800a5610  xorps   xmm0, xmm0
0x1800a5613  lea     rdx, aRtlpctofilehea; "RtlPcToFileHeader"
0x1800a561a  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x1800a561e  movups  xmmword ptr [rbp+2A0h+Name.Length], xmm0
0x1800a5622  call    cs:__imp_RtlInitString
0x1800a5628  mov     rcx, [rbp+2A0h+DllHandle]; BaseAddress
0x1800a562c  lea     r9, [rbp+2A0h+ProcedureAddress]; ProcedureAddress
0x1800a5630  xor     r8d, r8d; Ordinal
0x1800a5633  mov     [rbp+2A0h+ProcedureAddress], rsi
0x1800a5637  lea     rdx, [rbp+2A0h+Name]; Name
0x1800a563b  call    cs:__imp_LdrGetProcedureAddress
0x1800a5641  test    eax, eax
0x1800a5643  js      loc_1800A582A
0x1800a5649  lea     rdx, aNtdllDll_1; "ntdll.dll"
0x1800a5650  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x1800a5654  call    cs:__imp_RtlInitUnicodeString
0x1800a565a  lea     r9, [rbp+2A0h+BaseAddress]; DllHandle
0x1800a565e  xor     edx, edx; DllCharacteristics
0x1800a5660  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x1800a5664  xor     ecx, ecx; DllPath
0x1800a5666  call    cs:__imp_LdrGetDllHandle
0x1800a566c  test    eax, eax
0x1800a566e  js      loc_1800A582A
0x1800a5674  lea     rdx, aLdrgetdllfulln; "LdrGetDllFullName"
0x1800a567b  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x1800a567f  call    cs:__imp_RtlInitString
0x1800a5685  mov     rcx, [rbp+2A0h+BaseAddress]; BaseAddress
0x1800a5689  lea     r9, [rbp+2A0h+var_2F8]; ProcedureAddress
0x1800a568d  xor     r8d, r8d; Ordinal
0x1800a5690  mov     [rbp+2A0h+var_2F8], rsi
0x1800a5694  lea     rdx, [rbp+2A0h+Name]; Name
0x1800a5698  call    cs:__imp_LdrGetProcedureAddress
0x1800a569e  test    eax, eax
0x1800a56a0  js      loc_1800A582A
0x1800a56a6  mov     rax, [rbp+2A0h+ProcedureAddress]
0x1800a56aa  lea     rdx, [rbp+2A0h+var_300]
0x1800a56ae  lea     rcx, AslTelemetryCreate
0x1800a56b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a56ba  mov     [rbp+2A0h+var_300], rax
0x1800a56be  mov     rcx, rax
0x1800a56c1  test    rax, rax
0x1800a56c4  jz      loc_1800A582A
0x1800a56ca  lea     rax, [rbp+2A0h+var_240]
0x1800a56ce  mov     [rsp+3A0h+var_328], 2060000h
0x1800a56d7  mov     [rbp+2A0h+var_320], rax
0x1800a56db  lea     rdx, [rsp+3A0h+var_328]
0x1800a56e0  mov     rax, [rbp+2A0h+var_2F8]
0x1800a56e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a56e9  movzx   ecx, word ptr [rsp+3A0h+var_328]
0x1800a56ee  shr     ecx, 1
0x1800a56f0  mov     edx, ecx
0x1800a56f2  lea     r8, [rcx+rcx]
0x1800a56f6  cmp     r8, 208h
0x1800a56fd  jnb     loc_1800A58BB
0x1800a5703  mov     [rbp+r8+2A0h+var_240], si
0x1800a5709  test    eax, eax
0x1800a570b  js      loc_1800A582A
0x1800a5711  cmp     edx, 103h
0x1800a5717  ja      loc_1800A582A
0x1800a571d  xor     r9d, r9d
0x1800a5720  lea     rdx, [rsp+3A0h+var_328]
0x1800a5725  xor     r8d, r8d
0x1800a5728  lea     rcx, [rbp+2A0h+var_240]
0x1800a572c  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x1800a5732  test    eax, eax
0x1800a5734  js      loc_1800A582A
0x1800a573a  mov     [rsp+3A0h+EaLength], esi; EaLength
0x1800a573e  lea     ecx, [rsi+1]
0x1800a5741  mov     [rsp+3A0h+EaBuffer], rsi; EaBuffer
0x1800a5746  lea     rax, [rsp+3A0h+var_328]
0x1800a574b  mov     [rsp+3A0h+CreateOptions], 60h ; '`'; CreateOptions
0x1800a5753  lea     r9, [rbp+2A0h+IoStatusBlock]; IoStatusBlock
0x1800a5757  mov     [rsp+3A0h+CreateDisposition], ecx; CreateDisposition
0x1800a575b  lea     r8, [rbp+2A0h+ObjectAttributes]; ObjectAttributes
0x1800a575f  mov     [rsp+3A0h+ShareAccess], ecx; ShareAccess
0x1800a5763  xorps   xmm0, xmm0
0x1800a5766  mov     [rbp+2A0h+ObjectAttributes.ObjectName], rax
0x1800a576a  lea     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x1800a576f  lea     rax, [rbp+2A0h+var_280]
0x1800a5773  mov     [rsp+3A0h+FileAttributes], 80h; FileAttributes
0x1800a577b  mov     edx, 80100080h; DesiredAccess
0x1800a5780  mov     [rsp+3A0h+AllocationSize], rsi; AllocationSize
0x1800a5785  mov     [rsp+3A0h+FileHandle], rsi
0x1800a578a  mov     qword ptr [rbp+2A0h+ObjectAttributes.Length], 30h ; '0'
0x1800a5792  mov     qword ptr [rbp+2A0h+ObjectAttributes.Attributes], 40h ; '@'
0x1800a579a  movups  xmmword ptr [rbp+2A0h+IoStatusBlock], xmm0
0x1800a579e  mov     [rbp+2A0h+var_278], 101h
0x1800a57a5  mov     [rbp+2A0h+ObjectAttributes.RootDirectory], rsi
0x1800a57a9  mov     [rbp+2A0h+ObjectAttributes.SecurityDescriptor], rsi
0x1800a57ad  mov     [rbp+2A0h+var_280], 0Ch
0x1800a57b4  mov     [rbp+2A0h+var_27C], 2
0x1800a57bb  mov     [rbp+2A0h+ObjectAttributes.SecurityQualityOfService], rax
0x1800a57bf  call    cs:__imp_NtCreateFile
0x1800a57c5  test    eax, eax
0x1800a57c7  js      short loc_1800A582A
0x1800a57c9  mov     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x1800a57ce  lea     r9d, [rsi+28h]; Length
0x1800a57d2  xorps   xmm0, xmm0
0x1800a57d5  mov     [rbp+2A0h+FileInformation], rsi
0x1800a57d9  lea     r8, [rbp+2A0h+FileInformation]; FileInformation
0x1800a57dd  mov     [rbp+2A0h+var_268], rsi
0x1800a57e1  lea     rdx, [rbp+2A0h+var_290]; IoStatusBlock
0x1800a57e5  mov     [rbp+2A0h+var_260], rsi
0x1800a57e9  movups  xmmword ptr [rbp+2A0h+var_290], xmm0
0x1800a57ed  mov     dword ptr [rsp+3A0h+AllocationSize], 4; FileInformationClass
0x1800a57f5  movdqu  [rbp+2A0h+var_258], xmm0
0x1800a57fa  call    cs:__imp_NtQueryInformationFile
0x1800a5800  mov     rcx, [rsp+3A0h+FileHandle]; Handle
0x1800a5805  call    cs:__imp_NtClose
0x1800a580b  mov     eax, 7FFE0014h
0x1800a5810  mov     rcx, 0FFFF728E2DA50000h
0x1800a581a  mov     rax, [rax]
0x1800a581d  add     rax, rcx
0x1800a5820  cmp     [rbp+2A0h+var_260], rax
0x1800a5824  jge     short loc_1800A582A
0x1800a5826  xor     eax, eax
0x1800a5828  jmp     short loc_1800A58A0
0x1800a582a  lea     rdx, aCensus; "census"
0x1800a5831  mov     rcx, rdi
0x1800a5834  call    AslTelemetryCreate
0x1800a5839  mov     ebx, eax
0x1800a583b  test    eax, eax
0x1800a583d  js      short loc_1800A5899
0x1800a583f  lea     r9, [rsp+3A0h+var_334]
0x1800a5844  mov     [rsp+3A0h+var_340], esi
0x1800a5848  lea     r8, [rsp+3A0h+var_338]
0x1800a584d  mov     [rsp+3A0h+var_33C], esi
0x1800a5851  lea     rdx, [rsp+3A0h+var_33C]
0x1800a5856  mov     [rsp+3A0h+var_338], esi
0x1800a585a  lea     rcx, [rsp+3A0h+var_340]
0x1800a585f  mov     [rsp+3A0h+var_334], esi
0x1800a5863  call    AslFileGetLongVersionForCurrentModule
0x1800a5868  mov     r8, [rdi]
0x1800a586b  test    r8, r8
0x1800a586e  jz      short loc_1800A5899
0x1800a5870  mov     ecx, [rsp+3A0h+var_338]
0x1800a5874  mov     edx, [rsp+3A0h+var_340]
0x1800a5878  mov     eax, [rsp+3A0h+var_33C]
0x1800a587c  shl     rdx, 10h
0x1800a5880  or      rdx, rax
0x1800a5883  shl     rdx, 10h
0x1800a5887  or      rdx, rcx
0x1800a588a  mov     ecx, [rsp+3A0h+var_334]
0x1800a588e  shl     rdx, 10h
0x1800a5892  or      rdx, rcx
0x1800a5895  mov     [r8+40h], rdx
0x1800a5899  not     ebx
0x1800a589b  shr     ebx, 1Fh
0x1800a589e  mov     eax, ebx
0x1800a58a0  mov     rcx, [rbp+2A0h+var_30]
0x1800a58a7  xor     rcx, rsp; StackCookie
0x1800a58aa  call    __security_check_cookie
0x1800a58af  add     rsp, 388h
0x1800a58b6  pop     rdi
0x1800a58b7  pop     rsi
0x1800a58b8  pop     rbx
0x1800a58b9  pop     rbp
0x1800a58ba  retn
0x1800a58bb  call    __report_rangecheckfailure
```
