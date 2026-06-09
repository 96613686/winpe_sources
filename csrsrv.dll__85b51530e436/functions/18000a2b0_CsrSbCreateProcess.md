# CsrSbCreateProcess

- ea: `0x18000a2b0`
- end: `0x18000a847`
- name: `CsrSbCreateProcess`
- size: `1431`
- prototype: `char __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009190`

## callees

- `0x1800035c0`
- `0x18000a2b0`
- `0x18000a85c`
- `0x18000a9a0`
- `0x18000ab61`
- `0x18000ab80`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000a320`
- `ntdll!RtlInitUnicodeString` at `0x18000a332`
- `ntdll!RtlInitUnicodeString` at `0x18000a344`
- `ntdll!RtlInitUnicodeString` at `0x18000a5a5`
- `ntdll!RtlInitUnicodeString` at `0x18000a320`
- `ntdll!RtlInitUnicodeString` at `0x18000a332`
- `ntdll!RtlInitUnicodeString` at `0x18000a344`
- `ntdll!RtlInitUnicodeString` at `0x18000a5a5`
- `ntdll!NtClose` at `0x18000a652`
- `ntdll!NtClose` at `0x18000a66d`
- `ntdll!NtClose` at `0x18000a797`
- `ntdll!NtClose` at `0x18000a7a7`
- `ntdll!NtClose` at `0x18000a817`
- `ntdll!NtClose` at `0x18000a652`
- `ntdll!NtClose` at `0x18000a66d`
- `ntdll!NtClose` at `0x18000a797`
- `ntdll!NtClose` at `0x18000a7a7`
- `ntdll!NtClose` at `0x18000a817`
- `ntdll!RtlFreeHeap` at `0x18000a7c5`
- `ntdll!RtlFreeHeap` at `0x18000a7e3`
- `ntdll!RtlFreeHeap` at `0x18000a801`
- `ntdll!RtlFreeHeap` at `0x18000a7c5`
- `ntdll!RtlFreeHeap` at `0x18000a7e3`
- `ntdll!RtlFreeHeap` at `0x18000a801`
- `ntdll!NtWaitForSingleObject` at `0x18000a6a6`
- `ntdll!NtWaitForSingleObject` at `0x18000a6e9`
- `ntdll!NtWaitForSingleObject` at `0x18000a6a6`
- `ntdll!NtWaitForSingleObject` at `0x18000a6e9`
- `ntdll!NtResumeThread` at `0x18000a6bd`
- `ntdll!NtResumeThread` at `0x18000a6bd`
- `ntdll!NtTerminateProcess` at `0x18000a691`
- `ntdll!NtTerminateProcess` at `0x18000a691`
- `ntdll!NtSetInformationProcess` at `0x18000a61e`
- `ntdll!NtSetInformationProcess` at `0x18000a61e`
- `ntdll!NtAlpcOpenSenderProcess` at `0x18000a38e`
- `ntdll!NtAlpcOpenSenderProcess` at `0x18000a38e`
- `ntdll!RtlCreateProcessParametersEx` at `0x18000a457`
- `ntdll!RtlCreateProcessParametersEx` at `0x18000a457`
- `ntdll!RtlDestroyProcessParameters` at `0x18000a4e1`
- `ntdll!RtlDestroyProcessParameters` at `0x18000a4e1`
- `ntdll!NtOpenDirectoryObject` at `0x18000a5e1`
- `ntdll!NtOpenDirectoryObject` at `0x18000a5e1`
- `ntdll!NtDuplicateObject` at `0x18000a732`
- `ntdll!NtDuplicateObject` at `0x18000a76d`
- `ntdll!NtDuplicateObject` at `0x18000a732`
- `ntdll!NtDuplicateObject` at `0x18000a76d`
- `ntdll!RtlGetSuiteMask` at `0x18000a4fe`
- `ntdll!RtlGetSuiteMask` at `0x18000a4fe`
- `ntdll!RtlCreateUserProcess` at `0x18000a4ce`
- `ntdll!RtlCreateUserProcess` at `0x18000a4ce`

## string_xrefs

- `0x18000a3ad`: `CsrSbCreateProcess`
- `0x18000a633`: `CsrSbCreateProcess`
- `0x18000a787`: `CsrSbCreateProcess`

## pseudocode

```c
char __fastcall CsrSbCreateProcess(__int64 a1)
{
  NTSTATUS v2; // ebx
  char result; // al
  HANDLE v4; // r8
  HANDLE ProcessHandle; // rdx
  PSECURITY_DESCRIPTOR ThreadSecurityDescriptor; // [rsp+20h] [rbp-E0h]
  HANDLE TargetProcessHandle; // [rsp+60h] [rbp-A0h] BYREF
  PRTL_USER_PROCESS_PARAMETERS ProcessParameters; // [rsp+68h] [rbp-98h] BYREF
  void *FileHandle; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING Buffer; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING v12; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v13[48]; // [rsp+A8h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D8h] [rbp-28h] BYREF
  struct _UNICODE_STRING v15; // [rsp+108h] [rbp+8h] BYREF
  struct _RTL_USER_PROCESS_INFORMATION ProcessInfo; // [rsp+120h] [rbp+20h] BYREF
  _OWORD ProcessInformation[2]; // [rsp+190h] [rbp+90h] BYREF
  __int64 v18; // [rsp+1B0h] [rbp+B0h]
  wchar_t pszDest[256]; // [rsp+1C0h] [rbp+C0h] BYREF

  ProcessParameters = 0;
  TargetProcessHandle = 0;
  DestinationString = 0;
  Buffer = 0;
  v12 = 0;
  memset(v13, 0, 44);
  memset_0(&ProcessInfo, 0, sizeof(ProcessInfo));
  RtlInitUnicodeString(&DestinationString, 0);
  RtlInitUnicodeString(&Buffer, 0);
  RtlInitUnicodeString(&v12, 0);
  *(_DWORD *)v13 = 48;
  memset(&v13[8], 0, 20);
  *(_OWORD *)&v13[32] = 0;
  v2 = NtAlpcOpenSenderProcess(&TargetProcessHandle, CsrSbApiPort, a1, 0, 208, v13);
  if ( v2 < 0 )
  {
    TargetProcessHandle = 0;
LABEL_3:
    result = CsrpLogFailure("CsrSbCreateProcess");
    goto LABEL_30;
  }
  v2 = ReadUnicodeString(TargetProcessHandle, *(PVOID *)(a1 + 48), &DestinationString);
  if ( v2 < 0 )
    goto LABEL_3;
  v2 = ReadUnicodeString(TargetProcessHandle, *(PVOID *)(a1 + 56), &Buffer);
  if ( v2 < 0 )
    goto LABEL_3;
  v2 = ReadUnicodeString(TargetProcessHandle, *(PVOID *)(a1 + 64), &v12);
  if ( v2 < 0 )
    goto LABEL_3;
  v2 = RtlCreateProcessParametersEx(&ProcessParameters, &DestinationString, 0, &Buffer, &v12, 0, 0, 0, 0, 0, 1);
  if ( v2 < 0 )
    goto LABEL_3;
  ProcessParameters->DebugFlags = (*(_BYTE *)(a1 + 80) & 1) != 0 ? 1 : *(_DWORD *)(a1 + 84);
  ProcessInfo.Size = 104;
  v2 = RtlCreateUserProcess(
         &DestinationString,
         0x40u,
         ProcessParameters,
         0,
         0,
         TargetProcessHandle,
         0,
         0,
         0,
         &ProcessInfo);
  RtlDestroyProcessParameters(ProcessParameters);
  if ( v2 < 0 )
    goto LABEL_3;
  if ( (RtlGetSuiteMask() & 0x10) != 0 && *(_DWORD *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 704LL) != ServiceSessionId )
  {
    FileHandle = 0;
    v18 = 0;
    memset(ProcessInformation, 0, sizeof(ProcessInformation));
    v15 = 0;
    memset(&ObjectAttributes, 0, 44);
    LODWORD(ThreadSecurityDescriptor) = *(_DWORD *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 704LL);
    StringCchPrintfW(pszDest, 0x100u, L"%ws\\%ld%ws", L"\\Sessions", ThreadSecurityDescriptor, L"\\DosDevices");
    RtlInitUnicodeString(&v15, pszDest);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &v15;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v2 = NtOpenDirectoryObject(&FileHandle, 0xF000Fu, &ObjectAttributes);
    if ( v2 < 0 )
      goto LABEL_28;
    *(_QWORD *)&ProcessInformation[0] = FileHandle;
    v2 = NtSetInformationProcess(ProcessInfo.ProcessHandle, ProcessDeviceMap, ProcessInformation, 8u);
    if ( v2 < 0 )
    {
      CsrpLogFailure("CsrSbCreateProcess");
      if ( FileHandle )
        NtClose(FileHandle);
      goto LABEL_29;
    }
    if ( FileHandle )
      NtClose(FileHandle);
  }
  if ( (*(_BYTE *)(a1 + 80) & 4) != 0 )
    goto LABEL_26;
  if ( ProcessInfo.ImageInformation.SubSystemType == 1 )
  {
    v2 = NtResumeThread(ProcessInfo.ThreadHandle, 0);
    if ( v2 >= 0 )
    {
      if ( (*(_BYTE *)(a1 + 80) & 2) == 0 )
        NtWaitForSingleObject(ProcessInfo.ThreadHandle, 0, 0);
LABEL_26:
      v4 = TargetProcessHandle;
      ProcessHandle = ProcessInfo.ProcessHandle;
      *(_DWORD *)(a1 + 64) = ProcessInfo.ImageInformation.SubSystemType;
      *(CLIENT_ID *)(a1 + 72) = ProcessInfo.ClientId;
      v2 = NtDuplicateObject((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessHandle, v4, (PHANDLE)(a1 + 48), 0, 0, 2u);
      if ( v2 >= 0 )
      {
        v2 = NtDuplicateObject(
               (HANDLE)0xFFFFFFFFFFFFFFFFLL,
               ProcessInfo.ThreadHandle,
               TargetProcessHandle,
               (PHANDLE)(a1 + 56),
               0,
               0,
               2u);
        if ( v2 >= 0 )
          goto LABEL_29;
      }
    }
LABEL_28:
    CsrpLogFailure("CsrSbCreateProcess");
    goto LABEL_29;
  }
  v2 = -1073741701;
  NtTerminateProcess(ProcessInfo.ProcessHandle, -1073741701);
  NtWaitForSingleObject(ProcessInfo.ThreadHandle, 0, 0);
LABEL_29:
  NtClose(ProcessInfo.ThreadHandle);
  result = NtClose(ProcessInfo.ProcessHandle);
LABEL_30:
  if ( DestinationString.Buffer )
    result = RtlFreeHeap(CsrHeap, 0, DestinationString.Buffer);
  if ( Buffer.Buffer )
    result = RtlFreeHeap(CsrHeap, 0, Buffer.Buffer);
  if ( v12.Buffer )
    result = RtlFreeHeap(CsrHeap, 0, v12.Buffer);
  if ( TargetProcessHandle )
    result = NtClose(TargetProcessHandle);
  *(_DWORD *)(a1 + 44) = v2;
  return result;
}

```

## disassembly

```asm
0x18000a2b0  push    rbp
0x18000a2b2  push    rbx
0x18000a2b3  push    rsi
0x18000a2b4  push    rdi
0x18000a2b5  push    r14
0x18000a2b7  push    r15
0x18000a2b9  lea     rbp, [rsp-2D8h]
0x18000a2c1  sub     rsp, 3D8h
0x18000a2c8  mov     rax, cs:__security_cookie
0x18000a2cf  xor     rax, rsp
0x18000a2d2  mov     [rbp+300h+var_40], rax
0x18000a2d9  xorps   xmm0, xmm0
0x18000a2dc  xor     r15d, r15d
0x18000a2df  mov     r14, rcx
0x18000a2e2  mov     [rsp+400h+ProcessParameters], r15
0x18000a2e7  xorps   xmm1, xmm1
0x18000a2ea  mov     [rsp+400h+TargetProcessHandle], r15
0x18000a2ef  movups  [rbp+300h+var_348], xmm0
0x18000a2f3  lea     r8d, [r15+68h]; Size
0x18000a2f7  xor     eax, eax
0x18000a2f9  xor     edx, edx; Val
0x18000a2fb  lea     rcx, [rbp+300h+var_2E0]; void *
0x18000a2ff  movups  xmmword ptr [rsp+400h+DestinationString.Length], xmm0
0x18000a304  movups  xmmword ptr [rbp+300h+Buffer.Length], xmm1
0x18000a308  movups  xmmword ptr [rbp+300h+var_368.Length], xmm0
0x18000a30c  movups  [rbp+300h+var_358], xmm0
0x18000a310  movups  [rbp+300h+var_348+0Ch], xmm0
0x18000a314  call    memset_0
0x18000a319  xor     edx, edx; SourceString
0x18000a31b  lea     rcx, [rsp+400h+DestinationString]; DestinationString
0x18000a320  call    cs:__imp_RtlInitUnicodeString
0x18000a327  nop     dword ptr [rax+rax+00h]
0x18000a32c  xor     edx, edx; SourceString
0x18000a32e  lea     rcx, [rbp+300h+Buffer]; DestinationString
0x18000a332  call    cs:__imp_RtlInitUnicodeString
0x18000a339  nop     dword ptr [rax+rax+00h]
0x18000a33e  xor     edx, edx; SourceString
0x18000a340  lea     rcx, [rbp+300h+var_368]; DestinationString
0x18000a344  call    cs:__imp_RtlInitUnicodeString
0x18000a34b  nop     dword ptr [rax+rax+00h]
0x18000a350  mov     rdx, cs:CsrSbApiPort
0x18000a357  lea     rax, [rbp+300h+var_358]
0x18000a35b  xorps   xmm0, xmm0
0x18000a35e  mov     [rsp+400h+ParentProcess], rax
0x18000a363  xor     r9d, r9d
0x18000a366  mov     dword ptr [rsp+400h+ThreadSecurityDescriptor], 0D0h
0x18000a36e  mov     r8, r14
0x18000a371  mov     dword ptr [rbp+300h+var_358], 30h ; '0'
0x18000a378  lea     rcx, [rsp+400h+TargetProcessHandle]
0x18000a37d  mov     qword ptr [rbp+300h+var_358+8], r15
0x18000a381  mov     dword ptr [rbp+300h+var_348+8], r15d
0x18000a385  mov     qword ptr [rbp+300h+var_348], r15
0x18000a389  movdqu  [rbp+300h+var_338], xmm0
0x18000a38e  call    cs:__imp_NtAlpcOpenSenderProcess
0x18000a395  nop     dword ptr [rax+rax+00h]
0x18000a39a  mov     ebx, eax
0x18000a39c  test    eax, eax
0x18000a39e  jns     short loc_18000A3BE
0x18000a3a0  mov     [rsp+400h+TargetProcessHandle], r15
0x18000a3a5  mov     edx, 0E3Ah
0x18000a3aa  mov     r8d, eax
0x18000a3ad  lea     rcx, aCsrsbcreatepro; "CsrSbCreateProcess"
0x18000a3b4  call    CsrpLogFailure
0x18000a3b9  jmp     loc_18000A7B3
0x18000a3be  mov     rdx, [r14+30h]; BaseAddress
0x18000a3c2  lea     r8, [rsp+400h+DestinationString]; Buffer
0x18000a3c7  mov     rcx, [rsp+400h+TargetProcessHandle]; ProcessHandle
0x18000a3cc  call    ReadUnicodeString
0x18000a3d1  mov     ebx, eax
0x18000a3d3  test    eax, eax
0x18000a3d5  jns     short loc_18000A3DE
0x18000a3d7  mov     edx, 0E4Dh
0x18000a3dc  jmp     short loc_18000A3AA
0x18000a3de  mov     rdx, [r14+38h]; BaseAddress
0x18000a3e2  lea     r8, [rbp+300h+Buffer]; Buffer
0x18000a3e6  mov     rcx, [rsp+400h+TargetProcessHandle]; ProcessHandle
0x18000a3eb  call    ReadUnicodeString
0x18000a3f0  mov     ebx, eax
0x18000a3f2  test    eax, eax
0x18000a3f4  jns     short loc_18000A3FD
0x18000a3f6  mov     edx, 0E5Ch
0x18000a3fb  jmp     short loc_18000A3AA
0x18000a3fd  mov     rdx, [r14+40h]; BaseAddress
0x18000a401  lea     r8, [rbp+300h+var_368]; Buffer
0x18000a405  mov     rcx, [rsp+400h+TargetProcessHandle]; ProcessHandle
0x18000a40a  call    ReadUnicodeString
0x18000a40f  mov     ebx, eax
0x18000a411  test    eax, eax
0x18000a413  jns     short loc_18000A41C
0x18000a415  mov     edx, 0E6Bh
0x18000a41a  jmp     short loc_18000A3AA
0x18000a41c  mov     [rsp+400h+var_3B0], 1
0x18000a424  lea     rax, [rbp+300h+var_368]
0x18000a428  mov     [rsp+400h+ProcessInfo], r15
0x18000a42d  lea     r9, [rbp+300h+Buffer]
0x18000a431  mov     [rsp+400h+ExceptionPort], r15
0x18000a436  lea     rdx, [rsp+400h+DestinationString]
0x18000a43b  mov     [rsp+400h+DebugPort], r15
0x18000a440  lea     rcx, [rsp+400h+ProcessParameters]
0x18000a445  mov     qword ptr [rsp+400h+CurrentDirectory], r15
0x18000a44a  xor     r8d, r8d
0x18000a44d  mov     [rsp+400h+ParentProcess], r15
0x18000a452  mov     [rsp+400h+ThreadSecurityDescriptor], rax
0x18000a457  call    cs:__imp_RtlCreateProcessParametersEx
0x18000a45e  nop     dword ptr [rax+rax+00h]
0x18000a463  mov     ebx, eax
0x18000a465  test    eax, eax
0x18000a467  jns     short loc_18000A473
0x18000a469  mov     edx, 0E86h
0x18000a46e  jmp     loc_18000A3AA
0x18000a473  test    byte ptr [r14+50h], 1
0x18000a478  mov     rax, [rsp+400h+ProcessParameters]
0x18000a47d  jz      short loc_18000A488
0x18000a47f  mov     dword ptr [rax+0Ch], 1
0x18000a486  jmp     short loc_18000A48F
0x18000a488  mov     ecx, [r14+54h]
0x18000a48c  mov     [rax+0Ch], ecx
0x18000a48f  mov     r8, [rsp+400h+ProcessParameters]; ProcessParameters
0x18000a494  lea     rax, [rbp+300h+var_2E0]
0x18000a498  mov     [rsp+400h+ProcessInfo], rax; ProcessInfo
0x18000a49d  lea     rcx, [rsp+400h+DestinationString]; ImageFileName
0x18000a4a2  mov     rax, [rsp+400h+TargetProcessHandle]
0x18000a4a7  xor     r9d, r9d; ProcessSecutityDescriptor
0x18000a4aa  mov     [rsp+400h+ExceptionPort], r15; ExceptionPort
0x18000a4af  mov     [rsp+400h+DebugPort], r15; DebugPort
0x18000a4b4  mov     [rsp+400h+CurrentDirectory], r15b; CurrentDirectory
0x18000a4b9  mov     [rsp+400h+ParentProcess], rax; ParentProcess
0x18000a4be  lea     edx, [r9+40h]; Attributes
0x18000a4c2  mov     [rsp+400h+ThreadSecurityDescriptor], r15; ThreadSecurityDescriptor
0x18000a4c7  mov     [rbp+300h+var_2E0.Size], 68h ; 'h'
0x18000a4ce  call    cs:__imp_RtlCreateUserProcess
0x18000a4d5  nop     dword ptr [rax+rax+00h]
0x18000a4da  mov     rcx, [rsp+400h+ProcessParameters]; ProcessParameters
0x18000a4df  mov     ebx, eax
0x18000a4e1  call    cs:__imp_RtlDestroyProcessParameters
0x18000a4e8  nop     dword ptr [rax+rax+00h]
0x18000a4ed  test    ebx, ebx
0x18000a4ef  jns     short loc_18000A4FE
0x18000a4f1  mov     r8d, ebx
0x18000a4f4  mov     edx, 0EA9h
0x18000a4f9  jmp     loc_18000A3AD
0x18000a4fe  call    cs:__imp_RtlGetSuiteMask
0x18000a505  nop     dword ptr [rax+rax+00h]
0x18000a50a  test    al, 10h
0x18000a50c  jz      loc_18000A679
0x18000a512  mov     rcx, gs:60h
0x18000a51b  mov     eax, cs:ServiceSessionId
0x18000a521  cmp     [rcx+2C0h], eax
0x18000a527  jz      loc_18000A679
0x18000a52d  xorps   xmm0, xmm0
0x18000a530  mov     [rsp+400h+FileHandle], r15
0x18000a535  xor     eax, eax
0x18000a537  lea     rcx, aDosdevices; "\\DosDevices"
0x18000a53e  movups  xmmword ptr [rbp+300h+ObjectAttributes.ObjectName], xmm0
0x18000a542  mov     [rbp+300h+var_250], rax
0x18000a549  lea     r9, aSessions; "\\Sessions"
0x18000a550  movups  xmmword ptr [rbp+300h+ObjectAttributes+1Ch], xmm0
0x18000a554  mov     [rsp+400h+ParentProcess], rcx
0x18000a559  lea     r8, aWsLdWs; "%ws\\%ld%ws"
0x18000a560  movups  [rbp+300h+ProcessInformation], xmm0
0x18000a567  mov     edx, 100h; cchDest
0x18000a56c  lea     rcx, [rbp+300h+pszDest]; pszDest
0x18000a573  movups  [rbp+300h+var_260], xmm0
0x18000a57a  movups  xmmword ptr [rbp+300h+var_2F8.Length], xmm0
0x18000a57e  movups  xmmword ptr [rbp+300h+ObjectAttributes.Length], xmm0
0x18000a582  mov     rax, gs:60h
0x18000a58b  mov     eax, [rax+2C0h]
0x18000a591  mov     dword ptr [rsp+400h+ThreadSecurityDescriptor], eax
0x18000a595  call    StringCchPrintfW
0x18000a59a  lea     rdx, [rbp+300h+pszDest]; SourceString
0x18000a5a1  lea     rcx, [rbp+300h+var_2F8]; DestinationString
0x18000a5a5  call    cs:__imp_RtlInitUnicodeString
0x18000a5ac  nop     dword ptr [rax+rax+00h]
0x18000a5b1  lea     rax, [rbp+300h+var_2F8]
0x18000a5b5  mov     [rbp+300h+ObjectAttributes.Length], 30h ; '0'
0x18000a5bc  xorps   xmm0, xmm0
0x18000a5bf  mov     [rbp+300h+ObjectAttributes.ObjectName], rax
0x18000a5c3  lea     r8, [rbp+300h+ObjectAttributes]; ObjectAttributes
0x18000a5c7  mov     [rbp+300h+ObjectAttributes.RootDirectory], r15
0x18000a5cb  mov     edx, 0F000Fh; DesiredAccess
0x18000a5d0  mov     [rbp+300h+ObjectAttributes.Attributes], 40h ; '@'
0x18000a5d7  lea     rcx, [rsp+400h+FileHandle]; FileHandle
0x18000a5dc  movdqu  xmmword ptr [rbp+300h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000a5e1  call    cs:__imp_NtOpenDirectoryObject
0x18000a5e8  nop     dword ptr [rax+rax+00h]
0x18000a5ed  mov     ebx, eax
0x18000a5ef  test    eax, eax
0x18000a5f1  jns     short loc_18000A5FD
0x18000a5f3  mov     edx, 0ED8h
0x18000a5f8  jmp     loc_18000A784
0x18000a5fd  mov     rax, [rsp+400h+FileHandle]
0x18000a602  lea     r8, [rbp+300h+ProcessInformation]; ProcessInformation
0x18000a609  mov     rcx, [rbp+300h+var_2E0.ProcessHandle]; ProcessHandle
0x18000a60d  mov     r9d, 8; ProcessInformationLength
0x18000a613  mov     qword ptr [rbp+300h+ProcessInformation], rax
0x18000a61a  lea     edx, [r9+0Fh]; ProcessInformationClass
0x18000a61e  call    cs:__imp_NtSetInformationProcess
0x18000a625  nop     dword ptr [rax+rax+00h]
0x18000a62a  mov     ebx, eax
0x18000a62c  test    eax, eax
0x18000a62e  jns     short loc_18000A663
0x18000a630  mov     r8d, eax
0x18000a633  lea     rcx, aCsrsbcreatepro; "CsrSbCreateProcess"
0x18000a63a  mov     edx, 0EEDh
0x18000a63f  call    CsrpLogFailure
0x18000a644  mov     rcx, [rsp+400h+FileHandle]; Handle
0x18000a649  test    rcx, rcx
0x18000a64c  jz      loc_18000A793
0x18000a652  call    cs:__imp_NtClose
0x18000a659  nop     dword ptr [rax+rax+00h]
0x18000a65e  jmp     loc_18000A793
0x18000a663  mov     rcx, [rsp+400h+FileHandle]; Handle
0x18000a668  test    rcx, rcx
0x18000a66b  jz      short loc_18000A679
0x18000a66d  call    cs:__imp_NtClose
0x18000a674  nop     dword ptr [rax+rax+00h]
0x18000a679  test    byte ptr [r14+50h], 4
0x18000a67e  jnz     short loc_18000A6F5
0x18000a680  cmp     [rbp+300h+var_2E0.ImageInformation.SubSystemType], 1
0x18000a684  jz      short loc_18000A6B7
0x18000a686  mov     rcx, [rbp+300h+var_2E0.ProcessHandle]; ProcessHandle
0x18000a68a  mov     ebx, 0C000007Bh
0x18000a68f  mov     edx, ebx; ExitStatus
0x18000a691  call    cs:__imp_NtTerminateProcess
0x18000a698  nop     dword ptr [rax+rax+00h]
0x18000a69d  mov     rcx, [rbp+300h+var_2E0.ThreadHandle]; Object
0x18000a6a1  xor     r8d, r8d; Timeout
0x18000a6a4  xor     edx, edx; Alertable
0x18000a6a6  call    cs:__imp_NtWaitForSingleObject
0x18000a6ad  nop     dword ptr [rax+rax+00h]
0x18000a6b2  jmp     loc_18000A793
0x18000a6b7  mov     rcx, [rbp+300h+var_2E0.ThreadHandle]; ThreadHandle
0x18000a6bb  xor     edx, edx; SuspendCount
0x18000a6bd  call    cs:__imp_NtResumeThread
0x18000a6c4  nop     dword ptr [rax+rax+00h]
0x18000a6c9  mov     ebx, eax
0x18000a6cb  test    eax, eax
0x18000a6cd  jns     short loc_18000A6D9
0x18000a6cf  mov     edx, 0F29h
0x18000a6d4  jmp     loc_18000A784
0x18000a6d9  test    byte ptr [r14+50h], 2
0x18000a6de  jnz     short loc_18000A6F5
0x18000a6e0  mov     rcx, [rbp+300h+var_2E0.ThreadHandle]; Object
0x18000a6e4  xor     r8d, r8d; Timeout
0x18000a6e7  xor     edx, edx; Alertable
0x18000a6e9  call    cs:__imp_NtWaitForSingleObject
0x18000a6f0  nop     dword ptr [rax+rax+00h]
0x18000a6f5  mov     eax, [rbp+300h+var_2E0.ImageInformation.SubSystemType]
0x18000a6f8  lea     r9, [r14+30h]; TargetHandle
0x18000a6fc  mov     r8, [rsp+400h+TargetProcessHandle]; TargetProcessHandle
0x18000a701  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000a705  mov     rdx, [rbp+300h+var_2E0.ProcessHandle]; SourceHandle
0x18000a709  mov     rcx, rdi; SourceProcessHandle
0x18000a70c  mov     [r14+40h], eax
0x18000a710  mov     rax, [rbp+300h+var_2E0.ClientId.UniqueProcess]
0x18000a714  mov     [r14+48h], rax
0x18000a718  mov     rax, [rbp+300h+var_2E0.ClientId.UniqueThread]
0x18000a71c  mov     dword ptr [rsp+400h+CurrentDirectory], 2; Options
0x18000a724  mov     dword ptr [rsp+400h+ParentProcess], r15d; HandleAttributes
0x18000a729  mov     [r14+50h], rax
0x18000a72d  mov     dword ptr [rsp+400h+ThreadSecurityDescriptor], r15d; DesiredAccess
0x18000a732  call    cs:__imp_NtDuplicateObject
0x18000a739  nop     dword ptr [rax+rax+00h]
0x18000a73e  mov     ebx, eax
0x18000a740  test    eax, eax
0x18000a742  jns     short loc_18000A74B
0x18000a744  mov     edx, 0F4Dh
0x18000a749  jmp     short loc_18000A784
0x18000a74b  mov     r8, [rsp+400h+TargetProcessHandle]; TargetProcessHandle
0x18000a750  lea     r9, [r14+38h]; TargetHandle
0x18000a754  mov     rdx, [rbp+300h+var_2E0.ThreadHandle]; SourceHandle
0x18000a758  mov     rcx, rdi; SourceProcessHandle
0x18000a75b  mov     dword ptr [rsp+400h+CurrentDirectory], 2; Options
0x18000a763  mov     dword ptr [rsp+400h+ParentProcess], r15d; HandleAttributes
0x18000a768  mov     dword ptr [rsp+400h+ThreadSecurityDescriptor], r15d; DesiredAccess
0x18000a76d  call    cs:__imp_NtDuplicateObject
0x18000a774  nop     dword ptr [rax+rax+00h]
0x18000a779  mov     ebx, eax
0x18000a77b  test    eax, eax
0x18000a77d  jns     short loc_18000A793
0x18000a77f  mov     edx, 0F60h
0x18000a784  mov     r8d, eax
0x18000a787  lea     rcx, aCsrsbcreatepro; "CsrSbCreateProcess"
0x18000a78e  call    CsrpLogFailure
0x18000a793  mov     rcx, [rbp+300h+var_2E0.ThreadHandle]; Handle
0x18000a797  call    cs:__imp_NtClose
0x18000a79e  nop     dword ptr [rax+rax+00h]
0x18000a7a3  mov     rcx, [rbp+300h+var_2E0.ProcessHandle]; Handle
0x18000a7a7  call    cs:__imp_NtClose
0x18000a7ae  nop     dword ptr [rax+rax+00h]
0x18000a7b3  mov     r8, [rbp+300h+DestinationString.Buffer]; BaseAddress
0x18000a7b7  test    r8, r8
0x18000a7ba  jz      short loc_18000A7D1
0x18000a7bc  mov     rcx, cs:CsrHeap; HeapHandle
0x18000a7c3  xor     edx, edx; Flags
0x18000a7c5  call    cs:__imp_RtlFreeHeap
0x18000a7cc  nop     dword ptr [rax+rax+00h]
0x18000a7d1  mov     r8, [rbp+300h+Buffer.Buffer]; BaseAddress
0x18000a7d5  test    r8, r8
0x18000a7d8  jz      short loc_18000A7EF
  ... truncated ...
```
