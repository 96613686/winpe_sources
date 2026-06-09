# CscDclpRunRdbssScavenger

- ea: `0x14004e95c`
- end: `0x14004ece1`
- name: `CscDclpRunRdbssScavenger`
- size: `901`
- prototype: `__int64 __fastcall(UNICODE_STRING *String2)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14004ce14`

## callees

- `0x1400190ec`
- `0x14001a46c`
- `0x14004e95c`

## import_xrefs

- `ntoskrnl!ZwCreateFile` at `0x14004eb12`
- `ntoskrnl!ZwCreateFile` at `0x14004eb12`
- `ntoskrnl!ObfDereferenceObject` at `0x14004ebcb`
- `ntoskrnl!ObfDereferenceObject` at `0x14004ebcb`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14004e9be`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14004e9be`
- `ntoskrnl!IoFileObjectType` at `0x14004eb2f`
- `ntoskrnl!ExAllocatePool2` at `0x14004ea3f`
- `ntoskrnl!ExAllocatePool2` at `0x14004ea3f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004eb50`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004eb50`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ec66`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ec66`
- `ntoskrnl!ZwClose` at `0x14004ebdb`
- `ntoskrnl!ZwClose` at `0x14004ec7f`
- `ntoskrnl!ZwClose` at `0x14004ebdb`
- `ntoskrnl!ZwClose` at `0x14004ec7f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004ea6c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004ea94`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004ea6c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004ea94`
- `rdbss!RxScavengeRelatedFobxs` at `0x14004ec19`
- `rdbss!RxScavengeRelatedFobxs` at `0x14004ec19`
- `rdbss!RxpTrackDereference` at `0x14004ec4f`
- `rdbss!RxpTrackDereference` at `0x14004ec4f`
- `rdbss!RxDereference` at `0x14004ec2a`
- `rdbss!RxDereference` at `0x14004ec2a`
- `rdbss!RxGetDeviceObjectOfInstance` at `0x14004eb78`
- `rdbss!RxGetDeviceObjectOfInstance` at `0x14004eb78`
- `rdbss!RxReference` at `0x14004eb96`
- `rdbss!RxReference` at `0x14004eb96`
- `rdbss!RxScavengeRelatedClosePendingFobxs` at `0x14004ebfc`
- `rdbss!RxScavengeRelatedClosePendingFobxs` at `0x14004ebfc`
- `rdbss!RxpTrackReference` at `0x14004ebbb`
- `rdbss!RxpTrackReference` at `0x14004ebbb`

## pseudocode

```c
__int64 __fastcall CscDclpRunRdbssScavenger(UNICODE_STRING *String2)
{
  BOOLEAN v2; // al
  UNICODE_STRING v3; // xmm0
  WCHAR *v4; // rax
  NTSTATUS appended; // esi
  __int64 v6; // r9
  int v7; // r14d
  char v8; // r15
  struct _FCB *DeviceObjectOfInstance; // rbx
  void *v10; // rdi
  __int64 v11; // r8
  USHORT pusResult[8]; // [rsp+60h] [rbp-49h] BYREF
  UNICODE_STRING v14; // [rsp+70h] [rbp-39h] BYREF
  UNICODE_STRING String1; // [rsp+80h] [rbp-29h] BYREF
  UNICODE_STRING Source; // [rsp+90h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp+7h] BYREF
  void *FileHandle; // [rsp+118h] [rbp+6Fh] BYREF
  PVOID Object; // [rsp+120h] [rbp+77h] BYREF

  *(_QWORD *)&String1.Length = 393220;
  String1.Buffer = L"\\\\";
  FileHandle = 0;
  Object = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  *(_OWORD *)pusResult = 0;
  v2 = RtlPrefixUnicodeString(&String1, String2, 1u);
  v3 = *String2;
  if ( v2 )
  {
    v14 = *String2;
    Source.Buffer = L"\\Device\\Mup";
    v4 = String2->Buffer + 1;
    *(_QWORD *)&Source.Length = 1572886;
    v14.Buffer = v4;
    v14.MaximumLength = v3.MaximumLength - 2;
    v14.Length = v3.Length - 2;
    appended = RtlUShortAdd(v3.Length - 2, 0x16u, &pusResult[1]);
    if ( appended < 0 )
    {
      v7 = 2112;
      goto LABEL_18;
    }
    pusResult[0] = 0;
    *(_QWORD *)&pusResult[4] = ExAllocatePool2(258, pusResult[1], 1061124178, v6);
    if ( !*(_QWORD *)&pusResult[4] )
    {
      appended = -1073741670;
      v7 = 2119;
      goto LABEL_18;
    }
    appended = RtlAppendUnicodeStringToString((PUNICODE_STRING)pusResult, &Source);
    if ( appended < 0 )
    {
      v7 = 2125;
LABEL_17:
      ExFreePoolWithTag(*(PVOID *)&pusResult[4], 0);
      *(_QWORD *)&pusResult[4] = 0;
      goto LABEL_18;
    }
    v8 = 1;
    appended = RtlAppendUnicodeStringToString((PUNICODE_STRING)pusResult, &v14);
    if ( appended < 0 )
    {
      v7 = 2128;
      goto LABEL_17;
    }
  }
  else
  {
    v8 = 0;
    *(UNICODE_STRING *)pusResult = *String2;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)pusResult;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  appended = ZwCreateFile(&FileHandle, 0, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 1u, 0, 0, 0);
  if ( appended >= 0 )
  {
    appended = ObReferenceObjectByHandle(FileHandle, 0, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
    if ( appended >= 0 )
    {
      v7 = 0;
      DeviceObjectOfInstance = (struct _FCB *)RxGetDeviceObjectOfInstance(*((_QWORD *)Object + 3));
      v10 = *(void **)(*((_QWORD *)Object + 3) + 120LL);
      RxReference(v10);
      RxpTrackReference(2u, "CscDclpRunRdbssScavenger", 0x885u, v10);
      ObfDereferenceObject(Object);
      ZwClose(FileHandle);
      FileHandle = 0;
      LOBYTE(v11) = 1;
      RxScavengeRelatedClosePendingFobxs(DeviceObjectOfInstance, v10, v11);
      RxScavengeRelatedFobxs(DeviceObjectOfInstance);
      RxDereference(v10, LHS_LockNotHeld);
      RxpTrackDereference(2u, "CscDclpRunRdbssScavenger", 0x8A2u, v10);
    }
    else
    {
      v7 = 2173;
    }
  }
  else
  {
    v7 = 2161;
  }
  if ( v8 )
    goto LABEL_17;
LABEL_18:
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      40,
      WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids,
      (unsigned int)appended,
      v7);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14004e95c  mov     [rsp-8+arg_0], rbx
0x14004e961  mov     [rsp-8+arg_18], rsi
0x14004e966  push    rbp
0x14004e967  push    rdi
0x14004e968  push    r12
0x14004e96a  push    r14
0x14004e96c  push    r15
0x14004e96e  lea     rbp, [rsp-37h]
0x14004e973  sub     rsp, 0E0h
0x14004e97a  xorps   xmm0, xmm0
0x14004e97d  mov     qword ptr [rbp+57h+String1.Length], 60004h
0x14004e985  xor     eax, eax
0x14004e987  mov     rbx, rcx
0x14004e98a  lea     rax, asc_1400317E4; "\\\\"
0x14004e991  xor     r12d, r12d
0x14004e994  mov     rdx, rcx; String2
0x14004e997  mov     [rbp+57h+String1.Buffer], rax
0x14004e99b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14004e99f  mov     r8b, 1; CaseInSensitive
0x14004e9a2  mov     [rbp+57h+FileHandle], r12
0x14004e9a6  lea     rcx, [rbp+57h+String1]; String1
0x14004e9aa  mov     [rbp+57h+Object], r12
0x14004e9ae  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14004e9b2  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14004e9b6  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14004e9ba  movups  xmmword ptr [rbp+57h+pusResult], xmm0
0x14004e9be  call    cs:__imp_RtlPrefixUnicodeString
0x14004e9c5  nop     dword ptr [rax+rax+00h]
0x14004e9ca  movups  xmm0, xmmword ptr [rbx]
0x14004e9cd  test    al, al
0x14004e9cf  jz      loc_14004EAB1
0x14004e9d5  movups  xmmword ptr [rbp+57h+var_90.Length], xmm0
0x14004e9d9  movzx   ecx, [rbp+57h+var_90.Length]
0x14004e9dd  lea     rax, aDeviceMup; "\\Device\\Mup"
0x14004e9e4  mov     [rbp+57h+Source.Buffer], rax
0x14004e9e8  lea     edx, [r12+16h]; usAddend
0x14004e9ed  mov     rax, [rbx+8]
0x14004e9f1  lea     r8, [rbp+57h+pusResult+2]; pusResult
0x14004e9f5  add     rax, 2
0x14004e9f9  mov     qword ptr [rbp+57h+Source.Length], 180016h
0x14004ea01  mov     [rbp+57h+var_90.Buffer], rax
0x14004ea05  mov     eax, 0FFFEh
0x14004ea0a  add     [rbp+57h+var_90.MaximumLength], ax
0x14004ea0e  add     cx, ax; usAugend
0x14004ea11  mov     [rbp+57h+var_90.Length], cx
0x14004ea15  call    RtlUShortAdd
0x14004ea1a  mov     esi, eax
0x14004ea1c  test    eax, eax
0x14004ea1e  jns     short loc_14004EA2B
0x14004ea20  mov     r14d, 840h
0x14004ea26  jmp     loc_14004EC76
0x14004ea2b  movzx   edx, [rbp+57h+pusResult+2]
0x14004ea2f  mov     ecx, 102h
0x14004ea34  mov     r8d, 3F3F7852h
0x14004ea3a  mov     [rbp+57h+pusResult], r12w
0x14004ea3f  call    cs:__imp_ExAllocatePool2
0x14004ea46  nop     dword ptr [rax+rax+00h]
0x14004ea4b  mov     qword ptr [rbp+57h+pusResult+8], rax
0x14004ea4f  test    rax, rax
0x14004ea52  jnz     short loc_14004EA64
0x14004ea54  mov     esi, 0C000009Ah
0x14004ea59  mov     r14d, 847h
0x14004ea5f  jmp     loc_14004EC76
0x14004ea64  lea     rdx, [rbp+57h+Source]; Source
0x14004ea68  lea     rcx, [rbp+57h+pusResult]; Destination
0x14004ea6c  call    cs:__imp_RtlAppendUnicodeStringToString
0x14004ea73  nop     dword ptr [rax+rax+00h]
0x14004ea78  mov     esi, eax
0x14004ea7a  test    eax, eax
0x14004ea7c  jns     short loc_14004EA89
0x14004ea7e  mov     r14d, 84Dh
0x14004ea84  jmp     loc_14004EC60
0x14004ea89  lea     rdx, [rbp+57h+var_90]; Source
0x14004ea8d  mov     r15b, 1
0x14004ea90  lea     rcx, [rbp+57h+pusResult]; Destination
0x14004ea94  call    cs:__imp_RtlAppendUnicodeStringToString
0x14004ea9b  nop     dword ptr [rax+rax+00h]
0x14004eaa0  mov     esi, eax
0x14004eaa2  test    eax, eax
0x14004eaa4  jns     short loc_14004EAB9
0x14004eaa6  mov     r14d, 850h
0x14004eaac  jmp     loc_14004EC60
0x14004eab1  mov     r15b, r12b
0x14004eab4  movdqu  xmmword ptr [rbp+57h+pusResult], xmm0
0x14004eab9  mov     [rsp+100h+EaLength], r12d; EaLength
0x14004eabe  lea     rax, [rbp+57h+pusResult]
0x14004eac2  mov     [rsp+100h+EaBuffer], r12; EaBuffer
0x14004eac7  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14004eacb  mov     [rsp+100h+CreateOptions], r12d; CreateOptions
0x14004ead0  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14004ead4  mov     [rsp+100h+CreateDisposition], 1; CreateDisposition
0x14004eadc  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14004eae0  mov     [rsp+100h+ShareAccess], 7; ShareAccess
0x14004eae8  xorps   xmm0, xmm0
0x14004eaeb  mov     [rsp+100h+FileAttributes], r12d; FileAttributes
0x14004eaf0  xor     edx, edx; DesiredAccess
0x14004eaf2  mov     [rsp+100h+AllocationSize], r12; AllocationSize
0x14004eaf7  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14004eafe  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x14004eb02  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x14004eb09  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14004eb0d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14004eb12  call    cs:__imp_ZwCreateFile
0x14004eb19  nop     dword ptr [rax+rax+00h]
0x14004eb1e  mov     esi, eax
0x14004eb20  test    eax, eax
0x14004eb22  jns     short loc_14004EB2F
0x14004eb24  mov     r14d, 871h
0x14004eb2a  jmp     loc_14004EC5B
0x14004eb2f  mov     r8, cs:__imp_IoFileObjectType
0x14004eb36  lea     rax, [rbp+57h+Object]
0x14004eb3a  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14004eb3e  xor     r9d, r9d; AccessMode
0x14004eb41  mov     qword ptr [rsp+100h+FileAttributes], r12; HandleInformation
0x14004eb46  xor     edx, edx; DesiredAccess
0x14004eb48  mov     [rsp+100h+AllocationSize], rax; Object
0x14004eb4d  mov     r8, [r8]; ObjectType
0x14004eb50  call    cs:__imp_ObReferenceObjectByHandle
0x14004eb57  nop     dword ptr [rax+rax+00h]
0x14004eb5c  mov     esi, eax
0x14004eb5e  test    eax, eax
0x14004eb60  jns     short loc_14004EB6D
0x14004eb62  mov     r14d, 87Dh
0x14004eb68  jmp     loc_14004EC5B
0x14004eb6d  mov     rcx, [rbp+57h+Object]
0x14004eb71  mov     r14d, r12d
0x14004eb74  mov     rcx, [rcx+18h]
0x14004eb78  call    cs:__imp_RxGetDeviceObjectOfInstance
0x14004eb7f  nop     dword ptr [rax+rax+00h]
0x14004eb84  mov     rcx, [rbp+57h+Object]
0x14004eb88  mov     rbx, rax
0x14004eb8b  mov     rdx, [rcx+18h]
0x14004eb8f  mov     rdi, [rdx+78h]
0x14004eb93  mov     rcx, rdi; Instance
0x14004eb96  call    cs:__imp_RxReference
0x14004eb9d  nop     dword ptr [rax+rax+00h]
0x14004eba2  mov     r9, rdi; Instance
0x14004eba5  lea     rdx, aCscdclprunrdbs; "CscDclpRunRdbssScavenger"
0x14004ebac  mov     r8d, 885h; Line
0x14004ebb2  mov     dword ptr [rsp+100h+AllocationSize], eax
0x14004ebb6  mov     ecx, 2; TraceType
0x14004ebbb  call    cs:__imp_RxpTrackReference
0x14004ebc2  nop     dword ptr [rax+rax+00h]
0x14004ebc7  mov     rcx, [rbp+57h+Object]; Object
0x14004ebcb  call    cs:__imp_ObfDereferenceObject
0x14004ebd2  nop     dword ptr [rax+rax+00h]
0x14004ebd7  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14004ebdb  call    cs:__imp_ZwClose
0x14004ebe2  nop     dword ptr [rax+rax+00h]
0x14004ebe7  mov     r9b, 1
0x14004ebea  mov     [rbp+57h+FileHandle], r12
0x14004ebee  mov     r8b, r9b
0x14004ebf1  mov     [rsp+100h+AllocationSize], r12
0x14004ebf6  mov     rdx, rdi
0x14004ebf9  mov     rcx, rbx
0x14004ebfc  call    cs:__imp_RxScavengeRelatedClosePendingFobxs
0x14004ec03  nop     dword ptr [rax+rax+00h]
0x14004ec08  mov     r9b, 1
0x14004ec0b  mov     [rsp+100h+AllocationSize], r12
0x14004ec10  mov     r8b, r9b
0x14004ec13  mov     rdx, rdi
0x14004ec16  mov     rcx, rbx; Fcb
0x14004ec19  call    cs:__imp_RxScavengeRelatedFobxs
0x14004ec20  nop     dword ptr [rax+rax+00h]
0x14004ec25  xor     edx, edx; LockHoldingState
0x14004ec27  mov     rcx, rdi; Instance
0x14004ec2a  call    cs:__imp_RxDereference
0x14004ec31  nop     dword ptr [rax+rax+00h]
0x14004ec36  mov     r9, rdi; Instance
0x14004ec39  lea     rdx, aCscdclprunrdbs; "CscDclpRunRdbssScavenger"
0x14004ec40  mov     r8d, 8A2h; Line
0x14004ec46  mov     dword ptr [rsp+100h+AllocationSize], eax
0x14004ec4a  mov     ecx, 2; TraceType
0x14004ec4f  call    cs:__imp_RxpTrackDereference
0x14004ec56  nop     dword ptr [rax+rax+00h]
0x14004ec5b  test    r15b, r15b
0x14004ec5e  jz      short loc_14004EC76
0x14004ec60  mov     rcx, qword ptr [rbp+57h+pusResult+8]; P
0x14004ec64  xor     edx, edx; Tag
0x14004ec66  call    cs:__imp_ExFreePoolWithTag
0x14004ec6d  nop     dword ptr [rax+rax+00h]
0x14004ec72  mov     qword ptr [rbp+57h+pusResult+8], r12
0x14004ec76  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14004ec7a  test    rcx, rcx
0x14004ec7d  jz      short loc_14004EC8B
0x14004ec7f  call    cs:__imp_ZwClose
0x14004ec86  nop     dword ptr [rax+rax+00h]
0x14004ec8b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ec92  lea     rax, WPP_GLOBAL_Control
0x14004ec99  cmp     rcx, rax
0x14004ec9c  jz      short loc_14004ECC2
0x14004ec9e  mov     eax, [rcx+2Ch]
0x14004eca1  test    al, 20h
0x14004eca3  jz      short loc_14004ECC2
0x14004eca5  mov     rcx, [rcx+18h]
0x14004eca9  lea     r8, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids
0x14004ecb0  mov     edx, 28h ; '('
0x14004ecb5  mov     dword ptr [rsp+100h+AllocationSize], r14d
0x14004ecba  mov     r9d, esi
0x14004ecbd  call    WPP_SF_Dd
0x14004ecc2  lea     r11, [rsp+100h+var_20]
0x14004ecca  mov     eax, esi
0x14004eccc  mov     rbx, [r11+30h]
0x14004ecd0  mov     rsi, [r11+48h]
0x14004ecd4  mov     rsp, r11
0x14004ecd7  pop     r15
0x14004ecd9  pop     r14
0x14004ecdb  pop     r12
0x14004ecdd  pop     rdi
0x14004ecde  pop     rbp
0x14004ecdf  retn
```
