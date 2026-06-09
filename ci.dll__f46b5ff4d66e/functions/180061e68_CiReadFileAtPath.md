# CiReadFileAtPath

- ea: `0x180061e68`
- end: `0x1800620a6`
- name: `CiReadFileAtPath`
- size: `574`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180063038`
- `0x180074b9c`

## callees

- `0x18002bef0`
- `0x180061e68`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180061fe8`
- `ntoskrnl!ExAllocatePool2` at `0x180061fe8`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062058`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062058`
- `ntoskrnl!ZwOpenFile` at `0x180061ef1`
- `ntoskrnl!ZwOpenFile` at `0x180061ef1`
- `ntoskrnl!ZwClose` at `0x180062074`
- `ntoskrnl!ZwClose` at `0x180062074`
- `ntoskrnl!ObfDereferenceObject` at `0x180061f5d`
- `ntoskrnl!ObfDereferenceObject` at `0x180061f5d`
- `ntoskrnl!IoFileObjectType` at `0x180061f0d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180061f3c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180061f3c`
- `ntoskrnl!ZwQueryInformationFile` at `0x180061f93`
- `ntoskrnl!ZwQueryInformationFile` at `0x180061f93`
- `ntoskrnl!ZwReadFile` at `0x180062036`
- `ntoskrnl!ZwReadFile` at `0x180062036`

## pseudocode

```c
__int64 __fastcall CiReadFileAtPath(struct _UNICODE_STRING *a1, char a2, unsigned int a3, _QWORD *a4, _DWORD *a5)
{
  __int64 v5; // rsi
  NTSTATUS v8; // ebx
  int v9; // ebx
  void *Pool2; // rdi
  void *FileHandle; // [rsp+50h] [rbp-41h] BYREF
  PVOID Object; // [rsp+58h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-21h] BYREF
  __int128 FileInformation; // [rsp+A0h] [rbp+Fh] BYREF
  __int64 v17; // [rsp+B0h] [rbp+1Fh]

  v5 = a3;
  ObjectAttributes.ObjectName = a1;
  v17 = 0;
  ObjectAttributes.RootDirectory = 0;
  FileHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  FileInformation = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = ZwOpenFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 7u, 0x60u);
  if ( v8 >= 0 )
  {
    if ( (a2 & 8) == 0 )
      goto LABEL_6;
    Object = 0;
    v8 = ObReferenceObjectByHandle(FileHandle, 1u, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
    if ( v8 < 0 )
      goto LABEL_17;
    v9 = *(_DWORD *)(*((_QWORD *)Object + 1) + 48LL);
    ObfDereferenceObject(Object);
    if ( (v9 & 0x100) != 0 )
    {
LABEL_6:
      v8 = ZwQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
      if ( v8 >= 0 )
      {
        if ( *((_QWORD *)&FileInformation + 1) )
        {
          if ( HIDWORD(FileInformation) || DWORD2(FileInformation) > v5 )
          {
            v8 = -1073739516;
          }
          else
          {
            Pool2 = (void *)ExAllocatePool2(
                              (unsigned __int64)(a2 & 0x10 | 0x1020u) >> 4,
                              DWORD2(FileInformation),
                              1668499779);
            if ( Pool2 )
            {
              v8 = ZwReadFile(FileHandle, 0, 0, 0, &IoStatusBlock, Pool2, DWORD2(FileInformation), 0, 0);
              if ( v8 < 0 )
              {
                ExFreePoolWithTag(Pool2, 0x63734943u);
              }
              else
              {
                *a5 = DWORD2(FileInformation);
                *a4 = Pool2;
              }
            }
            else
            {
              v8 = -1073741801;
            }
          }
        }
        else
        {
          v8 = -1073741538;
        }
      }
    }
    else
    {
      v8 = -1073741501;
    }
  }
LABEL_17:
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180061e68  mov     [rsp-8+arg_8], rbx
0x180061e6d  push    rbp
0x180061e6e  push    rsi
0x180061e6f  push    rdi
0x180061e70  push    r14
0x180061e72  push    r15
0x180061e74  lea     rbp, [rsp-2Fh]
0x180061e79  sub     rsp, 0C0h
0x180061e80  mov     rax, cs:__security_cookie
0x180061e87  xor     rax, rsp
0x180061e8a  mov     [rbp+4Fh+var_28], rax
0x180061e8e  mov     r15, [rbp+4Fh+arg_20]
0x180061e92  xorps   xmm0, xmm0
0x180061e95  xor     eax, eax
0x180061e97  mov     esi, r8d
0x180061e9a  mov     r14, r9
0x180061e9d  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rcx
0x180061ea1  mov     edi, edx
0x180061ea3  mov     [rsp+0E0h+OpenOptions], 60h ; '`'; OpenOptions
0x180061eab  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x180061eaf  mov     [rbp+4Fh+var_30], rax
0x180061eb3  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x180061eb7  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rax
0x180061ebb  mov     edx, 120089h; DesiredAccess
0x180061ec0  mov     [rbp+4Fh+FileHandle], 0
0x180061ec8  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x180061ecc  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x180061ed4  movups  [rbp+4Fh+FileInformation], xmm0
0x180061ed8  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x180061ee0  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x180061ee4  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x180061eec  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180061ef1  call    cs:__imp_ZwOpenFile
0x180061ef8  nop     dword ptr [rax+rax+00h]
0x180061efd  mov     ebx, eax
0x180061eff  test    eax, eax
0x180061f01  js      loc_18006206B
0x180061f07  test    dil, 8
0x180061f0b  jz      short loc_180061F79
0x180061f0d  mov     r8, cs:__imp_IoFileObjectType
0x180061f14  lea     rax, [rbp+4Fh+Object]
0x180061f18  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x180061f1c  xor     r9d, r9d; AccessMode
0x180061f1f  mov     qword ptr [rsp+0E0h+OpenOptions], 0; HandleInformation
0x180061f28  mov     [rbp+4Fh+Object], 0
0x180061f30  mov     r8, [r8]; ObjectType
0x180061f33  lea     edx, [r9+1]; DesiredAccess
0x180061f37  mov     qword ptr [rsp+0E0h+ShareAccess], rax; Object
0x180061f3c  call    cs:__imp_ObReferenceObjectByHandle
0x180061f43  nop     dword ptr [rax+rax+00h]
0x180061f48  mov     ebx, eax
0x180061f4a  test    eax, eax
0x180061f4c  js      loc_18006206B
0x180061f52  mov     rcx, [rbp+4Fh+Object]; Object
0x180061f56  mov     rax, [rcx+8]
0x180061f5a  mov     ebx, [rax+30h]
0x180061f5d  call    cs:__imp_ObfDereferenceObject
0x180061f64  nop     dword ptr [rax+rax+00h]
0x180061f69  bt      ebx, 8
0x180061f6d  jb      short loc_180061F79
0x180061f6f  mov     ebx, 0C0000143h
0x180061f74  jmp     loc_18006206B
0x180061f79  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x180061f7d  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x180061f81  mov     r9d, 18h; Length
0x180061f87  mov     [rsp+0E0h+ShareAccess], 5; FileInformationClass
0x180061f8f  lea     rdx, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x180061f93  call    cs:__imp_ZwQueryInformationFile
0x180061f9a  nop     dword ptr [rax+rax+00h]
0x180061f9f  mov     ebx, eax
0x180061fa1  test    eax, eax
0x180061fa3  js      loc_18006206B
0x180061fa9  mov     rcx, qword ptr [rbp+4Fh+FileInformation+8]
0x180061fad  test    rcx, rcx
0x180061fb0  jnz     short loc_180061FBC
0x180061fb2  mov     ebx, 0C000011Eh
0x180061fb7  jmp     loc_18006206B
0x180061fbc  cmp     dword ptr [rbp+4Fh+FileInformation+0Ch], 0
0x180061fc0  jnz     loc_180062066
0x180061fc6  cmp     rcx, rsi
0x180061fc9  jg      loc_180062066
0x180061fcf  mov     edx, ecx
0x180061fd1  and     edi, 10h
0x180061fd4  or      edi, 1020h
0x180061fda  mov     esi, 63734943h
0x180061fdf  mov     ecx, edi
0x180061fe1  mov     r8d, esi
0x180061fe4  shr     rcx, 4
0x180061fe8  call    cs:__imp_ExAllocatePool2
0x180061fef  nop     dword ptr [rax+rax+00h]
0x180061ff4  mov     rdi, rax
0x180061ff7  test    rax, rax
0x180061ffa  jnz     short loc_180062003
0x180061ffc  mov     ebx, 0C0000017h
0x180062001  jmp     short loc_18006206B
0x180062003  mov     eax, dword ptr [rbp+4Fh+FileInformation+8]
0x180062006  xor     r9d, r9d; ApcContext
0x180062009  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x18006200d  xor     r8d, r8d; ApcRoutine
0x180062010  mov     [rsp+0E0h+Key], 0; Key
0x180062019  xor     edx, edx; Event
0x18006201b  mov     [rsp+0E0h+ByteOffset], 0; ByteOffset
0x180062024  mov     [rsp+0E0h+Length], eax; Length
0x180062028  lea     rax, [rbp+4Fh+IoStatusBlock]
0x18006202c  mov     qword ptr [rsp+0E0h+OpenOptions], rdi; Buffer
0x180062031  mov     qword ptr [rsp+0E0h+ShareAccess], rax; IoStatusBlock
0x180062036  call    cs:__imp_ZwReadFile
0x18006203d  nop     dword ptr [rax+rax+00h]
0x180062042  mov     ebx, eax
0x180062044  test    eax, eax
0x180062046  js      short loc_180062053
0x180062048  mov     eax, dword ptr [rbp+4Fh+FileInformation+8]
0x18006204b  mov     [r15], eax
0x18006204e  mov     [r14], rdi
0x180062051  jmp     short loc_18006206B
0x180062053  mov     edx, esi; Tag
0x180062055  mov     rcx, rdi; P
0x180062058  call    cs:__imp_ExFreePoolWithTag
0x18006205f  nop     dword ptr [rax+rax+00h]
0x180062064  jmp     short loc_18006206B
0x180062066  mov     ebx, 0C0000904h
0x18006206b  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x18006206f  test    rcx, rcx
0x180062072  jz      short loc_180062080
0x180062074  call    cs:__imp_ZwClose
0x18006207b  nop     dword ptr [rax+rax+00h]
0x180062080  mov     eax, ebx
0x180062082  mov     rcx, [rbp+4Fh+var_28]
0x180062086  xor     rcx, rsp; StackCookie
0x180062089  call    __security_check_cookie
0x18006208e  mov     rbx, [rsp+0E0h+arg_8]
0x180062096  add     rsp, 0C0h
0x18006209d  pop     r15
0x18006209f  pop     r14
0x1800620a1  pop     rdi
0x1800620a2  pop     rsi
0x1800620a3  pop     rbp
0x1800620a4  retn
```
