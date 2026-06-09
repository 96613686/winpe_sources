# AslTelemetry::Initialize(char const *)

- ea: `0x1800605c0`
- end: `0x1800608d9`
- name: `?Initialize@AslTelemetry@@QEAAHPEBD@Z`
- size: `793`
- prototype: `__int64 __fastcall(AslTelemetry *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800045c0`

## callees

- `0x180005e40`
- `0x1800062d0`
- `0x1800605c0`
- `0x180066c84`
- `0x180068e60`
- `0x180116010`

## import_xrefs

- `ntdll!NtClose` at `0x18006081d`
- `ntdll!NtClose` at `0x18006081d`
- `ntdll!NtQueryInformationFile` at `0x180060812`
- `ntdll!NtQueryInformationFile` at `0x180060812`
- `ntdll!NtCreateFile` at `0x1800607d7`
- `ntdll!NtCreateFile` at `0x1800607d7`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x180060744`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x180060744`
- `ntdll!LdrGetProcedureAddress` at `0x180060653`
- `ntdll!LdrGetProcedureAddress` at `0x1800606b0`
- `ntdll!LdrGetProcedureAddress` at `0x180060653`
- `ntdll!LdrGetProcedureAddress` at `0x1800606b0`
- `ntdll!RtlInitString` at `0x18006063a`
- `ntdll!RtlInitString` at `0x180060697`
- `ntdll!RtlInitString` at `0x18006063a`
- `ntdll!RtlInitString` at `0x180060697`
- `ntdll!LdrGetDllHandle` at `0x18006061a`
- `ntdll!LdrGetDllHandle` at `0x18006067e`
- `ntdll!LdrGetDllHandle` at `0x18006061a`
- `ntdll!LdrGetDllHandle` at `0x18006067e`
- `ntdll!RtlInitUnicodeString` at `0x180060608`
- `ntdll!RtlInitUnicodeString` at `0x18006066c`
- `ntdll!RtlInitUnicodeString` at `0x180060608`
- `ntdll!RtlInitUnicodeString` at `0x18006066c`

## string_xrefs

- `0x180060661`: `ntdll.dll`
- `0x1800605e7`: `kernel32.dll`
- `0x18006068c`: `LdrGetDllFullName`

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
  v6 = AslTelemetryCreate(this, "devinv");
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
0x1800605c0  push    rbp
0x1800605c2  push    rbx
0x1800605c3  push    rsi
0x1800605c4  push    rdi
0x1800605c5  lea     rbp, [rsp-288h]
0x1800605cd  sub     rsp, 388h
0x1800605d4  mov     rax, cs:__security_cookie
0x1800605db  xor     rax, rsp
0x1800605de  mov     [rbp+2A0h+var_30], rax
0x1800605e5  xor     esi, esi
0x1800605e7  lea     rdx, SourceString; "kernel32.dll"
0x1800605ee  mov     rdi, rcx
0x1800605f1  mov     [rbp+2A0h+DllHandle], rsi
0x1800605f5  xorps   xmm0, xmm0
0x1800605f8  mov     [rbp+2A0h+BaseAddress], rsi
0x1800605fc  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x180060600  mov     [rbp+2A0h+var_300], rsi
0x180060604  movups  xmmword ptr [rbp+2A0h+DestinationString.Length], xmm0
0x180060608  call    cs:__imp_RtlInitUnicodeString
0x18006060e  lea     r9, [rbp+2A0h+DllHandle]; DllHandle
0x180060612  xor     edx, edx; DllCharacteristics
0x180060614  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x180060618  xor     ecx, ecx; DllPath
0x18006061a  call    cs:__imp_LdrGetDllHandle
0x180060620  test    eax, eax
0x180060622  js      loc_180060842
0x180060628  xorps   xmm0, xmm0
0x18006062b  lea     rdx, aRtlpctofilehea; "RtlPcToFileHeader"
0x180060632  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x180060636  movups  xmmword ptr [rbp+2A0h+Name.Length], xmm0
0x18006063a  call    cs:__imp_RtlInitString
0x180060640  mov     rcx, [rbp+2A0h+DllHandle]; BaseAddress
0x180060644  lea     r9, [rbp+2A0h+ProcedureAddress]; ProcedureAddress
0x180060648  xor     r8d, r8d; Ordinal
0x18006064b  mov     [rbp+2A0h+ProcedureAddress], rsi
0x18006064f  lea     rdx, [rbp+2A0h+Name]; Name
0x180060653  call    cs:__imp_LdrGetProcedureAddress
0x180060659  test    eax, eax
0x18006065b  js      loc_180060842
0x180060661  lea     rdx, LibFileName; "ntdll.dll"
0x180060668  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x18006066c  call    cs:__imp_RtlInitUnicodeString
0x180060672  lea     r9, [rbp+2A0h+BaseAddress]; DllHandle
0x180060676  xor     edx, edx; DllCharacteristics
0x180060678  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x18006067c  xor     ecx, ecx; DllPath
0x18006067e  call    cs:__imp_LdrGetDllHandle
0x180060684  test    eax, eax
0x180060686  js      loc_180060842
0x18006068c  lea     rdx, aLdrgetdllfulln; "LdrGetDllFullName"
0x180060693  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x180060697  call    cs:__imp_RtlInitString
0x18006069d  mov     rcx, [rbp+2A0h+BaseAddress]; BaseAddress
0x1800606a1  lea     r9, [rbp+2A0h+var_2F8]; ProcedureAddress
0x1800606a5  xor     r8d, r8d; Ordinal
0x1800606a8  mov     [rbp+2A0h+var_2F8], rsi
0x1800606ac  lea     rdx, [rbp+2A0h+Name]; Name
0x1800606b0  call    cs:__imp_LdrGetProcedureAddress
0x1800606b6  test    eax, eax
0x1800606b8  js      loc_180060842
0x1800606be  mov     rax, [rbp+2A0h+ProcedureAddress]
0x1800606c2  lea     rdx, [rbp+2A0h+var_300]
0x1800606c6  lea     rcx, AslTelemetryCreate
0x1800606cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800606d2  mov     [rbp+2A0h+var_300], rax
0x1800606d6  mov     rcx, rax
0x1800606d9  test    rax, rax
0x1800606dc  jz      loc_180060842
0x1800606e2  lea     rax, [rbp+2A0h+var_240]
0x1800606e6  mov     [rsp+3A0h+var_328], 2060000h
0x1800606ef  mov     [rbp+2A0h+var_320], rax
0x1800606f3  lea     rdx, [rsp+3A0h+var_328]
0x1800606f8  mov     rax, [rbp+2A0h+var_2F8]
0x1800606fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060701  movzx   ecx, word ptr [rsp+3A0h+var_328]
0x180060706  shr     ecx, 1
0x180060708  mov     edx, ecx
0x18006070a  lea     r8, [rcx+rcx]
0x18006070e  cmp     r8, 208h
0x180060715  jnb     loc_1800608D3
0x18006071b  mov     [rbp+r8+2A0h+var_240], si
0x180060721  test    eax, eax
0x180060723  js      loc_180060842
0x180060729  cmp     edx, 103h
0x18006072f  ja      loc_180060842
0x180060735  xor     r9d, r9d
0x180060738  lea     rdx, [rsp+3A0h+var_328]
0x18006073d  xor     r8d, r8d
0x180060740  lea     rcx, [rbp+2A0h+var_240]
0x180060744  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x18006074a  test    eax, eax
0x18006074c  js      loc_180060842
0x180060752  mov     [rsp+3A0h+EaLength], esi; EaLength
0x180060756  lea     ecx, [rsi+1]
0x180060759  mov     [rsp+3A0h+EaBuffer], rsi; EaBuffer
0x18006075e  lea     rax, [rsp+3A0h+var_328]
0x180060763  mov     [rsp+3A0h+CreateOptions], 60h ; '`'; CreateOptions
0x18006076b  lea     r9, [rbp+2A0h+IoStatusBlock]; IoStatusBlock
0x18006076f  mov     [rsp+3A0h+CreateDisposition], ecx; CreateDisposition
0x180060773  lea     r8, [rbp+2A0h+ObjectAttributes]; ObjectAttributes
0x180060777  mov     [rsp+3A0h+ShareAccess], ecx; ShareAccess
0x18006077b  xorps   xmm0, xmm0
0x18006077e  mov     [rbp+2A0h+ObjectAttributes.ObjectName], rax
0x180060782  lea     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x180060787  lea     rax, [rbp+2A0h+var_280]
0x18006078b  mov     [rsp+3A0h+FileAttributes], 80h; FileAttributes
0x180060793  mov     edx, 80100080h; DesiredAccess
0x180060798  mov     [rsp+3A0h+AllocationSize], rsi; AllocationSize
0x18006079d  mov     [rsp+3A0h+FileHandle], rsi
0x1800607a2  mov     qword ptr [rbp+2A0h+ObjectAttributes.Length], 30h ; '0'
0x1800607aa  mov     qword ptr [rbp+2A0h+ObjectAttributes.Attributes], 40h ; '@'
0x1800607b2  movups  xmmword ptr [rbp+2A0h+IoStatusBlock], xmm0
0x1800607b6  mov     [rbp+2A0h+var_278], 101h
0x1800607bd  mov     [rbp+2A0h+ObjectAttributes.RootDirectory], rsi
0x1800607c1  mov     [rbp+2A0h+ObjectAttributes.SecurityDescriptor], rsi
0x1800607c5  mov     [rbp+2A0h+var_280], 0Ch
0x1800607cc  mov     [rbp+2A0h+var_27C], 2
0x1800607d3  mov     [rbp+2A0h+ObjectAttributes.SecurityQualityOfService], rax
0x1800607d7  call    cs:__imp_NtCreateFile
0x1800607dd  test    eax, eax
0x1800607df  js      short loc_180060842
0x1800607e1  mov     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x1800607e6  lea     r9d, [rsi+28h]; Length
0x1800607ea  xorps   xmm0, xmm0
0x1800607ed  mov     [rbp+2A0h+FileInformation], rsi
0x1800607f1  lea     r8, [rbp+2A0h+FileInformation]; FileInformation
0x1800607f5  mov     [rbp+2A0h+var_268], rsi
0x1800607f9  lea     rdx, [rbp+2A0h+var_290]; IoStatusBlock
0x1800607fd  mov     [rbp+2A0h+var_260], rsi
0x180060801  movups  xmmword ptr [rbp+2A0h+var_290], xmm0
0x180060805  mov     dword ptr [rsp+3A0h+AllocationSize], 4; FileInformationClass
0x18006080d  movdqu  [rbp+2A0h+var_258], xmm0
0x180060812  call    cs:__imp_NtQueryInformationFile
0x180060818  mov     rcx, [rsp+3A0h+FileHandle]; Handle
0x18006081d  call    cs:__imp_NtClose
0x180060823  mov     eax, 7FFE0014h
0x180060828  mov     rcx, 0FFFF728E2DA50000h
0x180060832  mov     rax, [rax]
0x180060835  add     rax, rcx
0x180060838  cmp     [rbp+2A0h+var_260], rax
0x18006083c  jge     short loc_180060842
0x18006083e  xor     eax, eax
0x180060840  jmp     short loc_1800608B8
0x180060842  lea     rdx, aDevinv; "devinv"
0x180060849  mov     rcx, rdi
0x18006084c  call    AslTelemetryCreate
0x180060851  mov     ebx, eax
0x180060853  test    eax, eax
0x180060855  js      short loc_1800608B1
0x180060857  lea     r9, [rsp+3A0h+var_334]
0x18006085c  mov     [rsp+3A0h+var_340], esi
0x180060860  lea     r8, [rsp+3A0h+var_338]
0x180060865  mov     [rsp+3A0h+var_33C], esi
0x180060869  lea     rdx, [rsp+3A0h+var_33C]
0x18006086e  mov     [rsp+3A0h+var_338], esi
0x180060872  lea     rcx, [rsp+3A0h+var_340]
0x180060877  mov     [rsp+3A0h+var_334], esi
0x18006087b  call    AslFileGetLongVersionForCurrentModule
0x180060880  mov     r8, [rdi]
0x180060883  test    r8, r8
0x180060886  jz      short loc_1800608B1
0x180060888  mov     ecx, [rsp+3A0h+var_338]
0x18006088c  mov     edx, [rsp+3A0h+var_340]
0x180060890  mov     eax, [rsp+3A0h+var_33C]
0x180060894  shl     rdx, 10h
0x180060898  or      rdx, rax
0x18006089b  shl     rdx, 10h
0x18006089f  or      rdx, rcx
0x1800608a2  mov     ecx, [rsp+3A0h+var_334]
0x1800608a6  shl     rdx, 10h
0x1800608aa  or      rdx, rcx
0x1800608ad  mov     [r8+40h], rdx
0x1800608b1  not     ebx
0x1800608b3  shr     ebx, 1Fh
0x1800608b6  mov     eax, ebx
0x1800608b8  mov     rcx, [rbp+2A0h+var_30]
0x1800608bf  xor     rcx, rsp; StackCookie
0x1800608c2  call    __security_check_cookie
0x1800608c7  add     rsp, 388h
0x1800608ce  pop     rdi
0x1800608cf  pop     rsi
0x1800608d0  pop     rbx
0x1800608d1  pop     rbp
0x1800608d2  retn
0x1800608d3  call    __report_rangecheckfailure
```
