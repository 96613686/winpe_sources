# KappxGetSecurityDescriptorStringForPackageFullName

- ea: `0x140011a30`
- end: `0x140011d3b`
- name: `KappxGetSecurityDescriptorStringForPackageFullName`
- size: `779`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140010f90`

## callees

- `0x140011a30`
- `0x140011d50`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140011aad`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011aad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011c42`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011c58`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011d2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011c42`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011c58`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011d2a`
- `ntoskrnl!ExAllocatePool2` at `0x140011bb8`
- `ntoskrnl!ExAllocatePool2` at `0x140011ca3`
- `ntoskrnl!ExAllocatePool2` at `0x140011bb8`
- `ntoskrnl!ExAllocatePool2` at `0x140011ca3`
- `ntoskrnl!PsGetHostSilo` at `0x140011af7`
- `ntoskrnl!PsGetHostSilo` at `0x140011af7`
- `ntoskrnl!IoCreateFileEx` at `0x140011b5c`
- `ntoskrnl!IoCreateFileEx` at `0x140011b5c`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140011b95`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140011be9`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140011b95`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140011be9`
- `ntoskrnl!SeConvertSecurityDescriptorToStringSecurityDescriptor` at `0x140011c15`
- `ntoskrnl!SeConvertSecurityDescriptorToStringSecurityDescriptor` at `0x140011c15`
- `ntoskrnl!ZwClose` at `0x140011c2c`
- `ntoskrnl!ZwClose` at `0x140011c2c`

## pseudocode

```c
__int64 __fastcall KappxGetSecurityDescriptorStringForPackageFullName(__int64 a1, __int64 *a2)
{
  void *v3; // rdi
  void *v4; // r14
  int PackageRootPathForPackageFullName; // eax
  WCHAR *v6; // rsi
  NTSTATUS v7; // ebx
  NTSTATUS v8; // eax
  __int64 Pool2; // rax
  __int64 v11; // rcx
  const wchar_t *v12; // rdx
  __int64 v13; // r8
  _WORD *v14; // r9
  _WORD *v15; // rcx
  void *FileHandle; // [rsp+80h] [rbp-80h] BYREF
  PCWSTR SourceString; // [rsp+88h] [rbp-78h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+90h] [rbp-70h] BYREF
  __int64 HostSilo; // [rsp+B0h] [rbp-50h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+E8h] [rbp-18h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F8h] [rbp-8h] BYREF
  ULONG LengthNeeded; // [rsp+150h] [rbp+50h] BYREF
  int v24; // [rsp+158h] [rbp+58h] BYREF

  SourceString = 0;
  FileHandle = 0;
  LengthNeeded = 0;
  v3 = 0;
  v24 = 0;
  DestinationString = 0;
  v4 = 0;
  HostSilo = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  PackageRootPathForPackageFullName = KappxGetPackageRootPathForPackageFullName(a1, &SourceString);
  v6 = (WCHAR *)SourceString;
  v7 = PackageRootPathForPackageFullName;
  if ( PackageRootPathForPackageFullName >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    memset(&DriverContext, 0, sizeof(DriverContext));
    DriverContext.Size = 40;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    HostSilo = 1;
    HostSilo = PsGetHostSilo();
    v8 = IoCreateFileEx(
           &FileHandle,
           0x20000u,
           &ObjectAttributes,
           &IoStatusBlock,
           0,
           0,
           7u,
           1u,
           0x200009u,
           0,
           0,
           CreateFileTypeNone,
           0,
           0,
           &DriverContext);
    v7 = v8;
    if ( v8 == -1073741772 )
    {
      Pool2 = ExAllocatePool2(256, 570, 1483763777);
      v4 = (void *)Pool2;
      if ( Pool2 )
      {
        v11 = 2147483646;
        v12 = L"D:AI(A;OICI;0x1200a9;;;BU)(A;ID;FA;;;S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464)(A;CII"
               "OID;FA;;;S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464)(A;ID;FA;;;SY)(A;OICIIOID;FA;;;SY"
               ")(A;OICIID;0x1200a9;;;BA)(A;OICIID;0x1200a9;;;LS)(A;OICIID;0x1200a9;;;NS)";
        v13 = 285;
        v14 = (_WORD *)Pool2;
        do
        {
          if ( !v11 )
            break;
          if ( !*v12 )
            break;
          *v14++ = *v12++;
          --v11;
          --v13;
        }
        while ( v13 );
        v15 = v14 - 1;
        v7 = -2147483643;
        if ( v13 )
        {
          v15 = v14;
          v7 = 0;
        }
        *v15 = 0;
        if ( v13 )
        {
          *a2 = Pool2;
          v4 = 0;
        }
      }
      else
      {
        v7 = -1073741801;
      }
    }
    else if ( v8 >= 0 )
    {
      v7 = ZwQuerySecurityObject(FileHandle, 0xCu, 0, 0, &LengthNeeded);
      if ( v7 == -1073741789 )
      {
        v3 = (void *)ExAllocatePool2(256, LengthNeeded, 1483763777);
        if ( v3 )
        {
          v7 = ZwQuerySecurityObject(FileHandle, 0xCu, v3, LengthNeeded, &LengthNeeded);
          if ( v7 >= 0 )
            v7 = SeConvertSecurityDescriptorToStringSecurityDescriptor(v3, 1, 12, a2, &v24);
        }
        else
        {
          v7 = -1073741801;
        }
      }
    }
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140011a30  mov     [rsp-8+arg_0], rbx
0x140011a35  mov     [rsp-8+arg_8], rsi
0x140011a3a  push    rbp
0x140011a3b  push    rdi
0x140011a3c  push    r12
0x140011a3e  push    r14
0x140011a40  push    r15
0x140011a42  lea     rbp, [rsp-10h]
0x140011a47  sub     rsp, 110h
0x140011a4e  xorps   xmm0, xmm0
0x140011a51  xor     r12d, r12d
0x140011a54  mov     r15, rdx
0x140011a57  mov     [rbp+30h+SourceString], r12
0x140011a5b  xor     eax, eax
0x140011a5d  mov     [rbp+30h+FileHandle], r12
0x140011a61  movups  xmmword ptr [rbp+30h+ObjectAttributes.ObjectName], xmm0
0x140011a65  lea     rdx, [rbp+30h+SourceString]
0x140011a69  mov     [rbp+30h+LengthNeeded], r12d
0x140011a6d  movups  xmmword ptr [rbp+30h+ObjectAttributes+1Ch], xmm0
0x140011a71  mov     edi, r12d
0x140011a74  mov     [rbp+30h+arg_18], r12d
0x140011a78  movups  xmmword ptr [rbp+30h+DestinationString.Length], xmm0
0x140011a7c  mov     r14d, r12d
0x140011a7f  mov     [rbp+30h+var_80], rax
0x140011a83  movups  xmmword ptr [rbp+30h+ObjectAttributes.Length], xmm0
0x140011a87  movups  xmmword ptr [rbp+30h+IoStatusBlock], xmm0
0x140011a8b  movups  xmmword ptr [rbp+30h+var_A0.Size], xmm0
0x140011a8f  movups  xmmword ptr [rbp+30h+var_A0.DeviceObjectHint], xmm0
0x140011a93  call    KappxGetPackageRootPathForPackageFullName
0x140011a98  mov     rsi, [rbp+30h+SourceString]
0x140011a9c  mov     ebx, eax
0x140011a9e  test    eax, eax
0x140011aa0  js      loc_140011C23
0x140011aa6  mov     rdx, rsi; SourceString
0x140011aa9  lea     rcx, [rbp+30h+DestinationString]; DestinationString
0x140011aad  call    cs:__imp_RtlInitUnicodeString
0x140011ab4  nop     dword ptr [rax+rax+00h]
0x140011ab9  lea     rax, [rbp+30h+DestinationString]
0x140011abd  mov     [rbp+30h+ObjectAttributes.Length], 30h ; '0'
0x140011ac4  xorps   xmm1, xmm1
0x140011ac7  mov     [rbp+30h+ObjectAttributes.ObjectName], rax
0x140011acb  mov     eax, 28h ; '('
0x140011ad0  mov     [rbp+30h+ObjectAttributes.RootDirectory], r12
0x140011ad4  xorps   xmm0, xmm0
0x140011ad7  mov     [rbp+30h+ObjectAttributes.Attributes], 240h
0x140011ade  movups  xmmword ptr [rbp+30h+var_A0.Size], xmm1
0x140011ae2  mov     [rbp+30h+var_A0.Size], ax
0x140011ae6  movdqu  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm0
0x140011aeb  mov     [rbp+30h+var_80], 1
0x140011af3  movups  xmmword ptr [rbp+30h+var_A0.DeviceObjectHint], xmm1
0x140011af7  call    cs:__imp_PsGetHostSilo
0x140011afe  nop     dword ptr [rax+rax+00h]
0x140011b03  mov     [rbp+30h+var_80], rax
0x140011b07  lea     r9, [rbp+30h+IoStatusBlock]; IoStatusBlock
0x140011b0b  lea     rax, [rbp+30h+var_A0]
0x140011b0f  mov     edx, 20000h; DesiredAccess
0x140011b14  mov     [rsp+130h+DriverContext], rax; DriverContext
0x140011b19  lea     r8, [rbp+30h+ObjectAttributes]; ObjectAttributes
0x140011b1d  mov     [rsp+130h+Options], r12d; Options
0x140011b22  lea     rcx, [rbp+30h+FileHandle]; FileHandle
0x140011b26  mov     [rsp+130h+InternalParameters], r12; InternalParameters
0x140011b2b  mov     [rsp+130h+CreateFileType], r12d; CreateFileType
0x140011b30  mov     [rsp+130h+EaLength], r12d; EaLength
0x140011b35  mov     [rsp+130h+EaBuffer], r12; EaBuffer
0x140011b3a  mov     [rsp+130h+CreateOptions], 200009h; CreateOptions
0x140011b42  mov     [rsp+130h+Disposition], 1; Disposition
0x140011b4a  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x140011b52  mov     [rsp+130h+FileAttributes], r12d; FileAttributes
0x140011b57  mov     [rsp+130h+AllocationSize], r12; AllocationSize
0x140011b5c  call    cs:__imp_IoCreateFileEx
0x140011b63  nop     dword ptr [rax+rax+00h]
0x140011b68  mov     ebx, eax
0x140011b6a  cmp     eax, 0C0000034h
0x140011b6f  jz      loc_140011C93
0x140011b75  test    eax, eax
0x140011b77  js      loc_140011C23
0x140011b7d  mov     rcx, [rbp+30h+FileHandle]; Handle
0x140011b81  lea     rax, [rbp+30h+LengthNeeded]
0x140011b85  xor     r9d, r9d; Length
0x140011b88  mov     [rsp+130h+AllocationSize], rax; LengthNeeded
0x140011b8d  xor     r8d, r8d; SecurityDescriptor
0x140011b90  mov     edx, 0Ch; SecurityInformation
0x140011b95  call    cs:__imp_ZwQuerySecurityObject
0x140011b9c  nop     dword ptr [rax+rax+00h]
0x140011ba1  mov     ebx, eax
0x140011ba3  cmp     eax, 0C0000023h
0x140011ba8  jnz     short loc_140011C23
0x140011baa  mov     edx, [rbp+30h+LengthNeeded]
0x140011bad  mov     ecx, 100h
0x140011bb2  mov     r8d, 58707041h
0x140011bb8  call    cs:__imp_ExAllocatePool2
0x140011bbf  nop     dword ptr [rax+rax+00h]
0x140011bc4  mov     rdi, rax
0x140011bc7  test    rax, rax
0x140011bca  jz      loc_140011C8C
0x140011bd0  mov     r9d, [rbp+30h+LengthNeeded]; Length
0x140011bd4  lea     rax, [rbp+30h+LengthNeeded]
0x140011bd8  mov     rcx, [rbp+30h+FileHandle]; Handle
0x140011bdc  mov     r8, rdi; SecurityDescriptor
0x140011bdf  mov     edx, 0Ch; SecurityInformation
0x140011be4  mov     [rsp+130h+AllocationSize], rax; LengthNeeded
0x140011be9  call    cs:__imp_ZwQuerySecurityObject
0x140011bf0  nop     dword ptr [rax+rax+00h]
0x140011bf5  mov     ebx, eax
0x140011bf7  test    eax, eax
0x140011bf9  js      short loc_140011C23
0x140011bfb  lea     rax, [rbp+30h+arg_18]
0x140011bff  mov     r9, r15
0x140011c02  mov     edx, 1
0x140011c07  mov     [rsp+130h+AllocationSize], rax
0x140011c0c  mov     r8d, 0Ch
0x140011c12  mov     rcx, rdi
0x140011c15  call    cs:__imp_SeConvertSecurityDescriptorToStringSecurityDescriptor
0x140011c1c  nop     dword ptr [rax+rax+00h]
0x140011c21  mov     ebx, eax
0x140011c23  mov     rcx, [rbp+30h+FileHandle]; Handle
0x140011c27  test    rcx, rcx
0x140011c2a  jz      short loc_140011C38
0x140011c2c  call    cs:__imp_ZwClose
0x140011c33  nop     dword ptr [rax+rax+00h]
0x140011c38  test    rsi, rsi
0x140011c3b  jz      short loc_140011C4E
0x140011c3d  xor     edx, edx; Tag
0x140011c3f  mov     rcx, rsi; P
0x140011c42  call    cs:__imp_ExFreePoolWithTag
0x140011c49  nop     dword ptr [rax+rax+00h]
0x140011c4e  test    rdi, rdi
0x140011c51  jz      short loc_140011C64
0x140011c53  xor     edx, edx; Tag
0x140011c55  mov     rcx, rdi; P
0x140011c58  call    cs:__imp_ExFreePoolWithTag
0x140011c5f  nop     dword ptr [rax+rax+00h]
0x140011c64  test    r14, r14
0x140011c67  jnz     loc_140011D25
0x140011c6d  lea     r11, [rsp+130h+var_20]
0x140011c75  mov     eax, ebx
0x140011c77  mov     rbx, [r11+30h]
0x140011c7b  mov     rsi, [r11+38h]
0x140011c7f  mov     rsp, r11
0x140011c82  pop     r15
0x140011c84  pop     r14
0x140011c86  pop     r12
0x140011c88  pop     rdi
0x140011c89  pop     rbp
0x140011c8a  retn
0x140011c8c  mov     ebx, 0C0000017h
0x140011c91  jmp     short loc_140011C23
0x140011c93  mov     edx, 23Ah
0x140011c98  mov     ecx, 100h
0x140011c9d  mov     r8d, 58707041h
0x140011ca3  call    cs:__imp_ExAllocatePool2
0x140011caa  nop     dword ptr [rax+rax+00h]
0x140011caf  mov     r14, rax
0x140011cb2  test    rax, rax
0x140011cb5  jz      short loc_140011D1B
0x140011cb7  mov     ecx, 7FFFFFFEh
0x140011cbc  lea     rdx, aDAiAOici0x1200; "D:AI(A;OICI;0x1200a9;;;BU)(A;ID;FA;;;S-"...
0x140011cc3  mov     r8d, 11Dh
0x140011cc9  mov     r9, rax
0x140011ccc  nop     dword ptr [rax+00h]
0x140011cd0  test    rcx, rcx
0x140011cd3  jz      short loc_140011CF2
0x140011cd5  movzx   eax, word ptr [rdx]
0x140011cd8  test    ax, ax
0x140011cdb  jz      short loc_140011CF2
0x140011cdd  mov     [r9], ax
0x140011ce1  add     rdx, 2
0x140011ce5  add     r9, 2
0x140011ce9  dec     rcx
0x140011cec  sub     r8, 1
0x140011cf0  jnz     short loc_140011CD0
0x140011cf2  test    r8, r8
0x140011cf5  lea     rcx, [r9-2]
0x140011cf9  mov     ebx, 80000005h
0x140011cfe  cmovnz  rcx, r9
0x140011d02  cmovnz  ebx, r12d
0x140011d06  mov     [rcx], r12w
0x140011d0a  jz      loc_140011C23
0x140011d10  mov     [r15], r14
0x140011d13  mov     r14, r12
0x140011d16  jmp     loc_140011C23
0x140011d1b  mov     ebx, 0C0000017h
0x140011d20  jmp     loc_140011C23
0x140011d25  xor     edx, edx; Tag
0x140011d27  mov     rcx, r14; P
0x140011d2a  call    cs:__imp_ExFreePoolWithTag
0x140011d31  nop     dword ptr [rax+rax+00h]
0x140011d36  jmp     loc_140011C6D
```
