# CiReadFileAtPath

- ea: `0x180062810`
- end: `0x180062a4e`
- name: `CiReadFileAtPath`
- size: `574`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800639e8`
- `0x180076438`

## callees

- `0x18002c0d0`
- `0x180062810`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180062990`
- `ntoskrnl!ExAllocatePool2` at `0x180062990`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062a00`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062a00`
- `ntoskrnl!ZwOpenFile` at `0x180062899`
- `ntoskrnl!ZwOpenFile` at `0x180062899`
- `ntoskrnl!ZwClose` at `0x180062a1c`
- `ntoskrnl!ZwClose` at `0x180062a1c`
- `ntoskrnl!ObfDereferenceObject` at `0x180062905`
- `ntoskrnl!ObfDereferenceObject` at `0x180062905`
- `ntoskrnl!IoFileObjectType` at `0x1800628b5`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1800628e4`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1800628e4`
- `ntoskrnl!ZwQueryInformationFile` at `0x18006293b`
- `ntoskrnl!ZwQueryInformationFile` at `0x18006293b`
- `ntoskrnl!ZwReadFile` at `0x1800629de`
- `ntoskrnl!ZwReadFile` at `0x1800629de`

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
0x180062810  mov     [rsp-8+arg_8], rbx
0x180062815  push    rbp
0x180062816  push    rsi
0x180062817  push    rdi
0x180062818  push    r14
0x18006281a  push    r15
0x18006281c  lea     rbp, [rsp-2Fh]
0x180062821  sub     rsp, 0C0h
0x180062828  mov     rax, cs:__security_cookie
0x18006282f  xor     rax, rsp
0x180062832  mov     [rbp+4Fh+var_28], rax
0x180062836  mov     r15, [rbp+4Fh+arg_20]
0x18006283a  xorps   xmm0, xmm0
0x18006283d  xor     eax, eax
0x18006283f  mov     esi, r8d
0x180062842  mov     r14, r9
0x180062845  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rcx
0x180062849  mov     edi, edx
0x18006284b  mov     [rsp+0E0h+OpenOptions], 60h ; '`'; OpenOptions
0x180062853  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x180062857  mov     [rbp+4Fh+var_30], rax
0x18006285b  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18006285f  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rax
0x180062863  mov     edx, 120089h; DesiredAccess
0x180062868  mov     [rbp+4Fh+FileHandle], 0
0x180062870  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x180062874  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18006287c  movups  [rbp+4Fh+FileInformation], xmm0
0x180062880  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x180062888  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x18006288c  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x180062894  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180062899  call    cs:__imp_ZwOpenFile
0x1800628a0  nop     dword ptr [rax+rax+00h]
0x1800628a5  mov     ebx, eax
0x1800628a7  test    eax, eax
0x1800628a9  js      loc_180062A13
0x1800628af  test    dil, 8
0x1800628b3  jz      short loc_180062921
0x1800628b5  mov     r8, cs:__imp_IoFileObjectType
0x1800628bc  lea     rax, [rbp+4Fh+Object]
0x1800628c0  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x1800628c4  xor     r9d, r9d; AccessMode
0x1800628c7  mov     qword ptr [rsp+0E0h+OpenOptions], 0; HandleInformation
0x1800628d0  mov     [rbp+4Fh+Object], 0
0x1800628d8  mov     r8, [r8]; ObjectType
0x1800628db  lea     edx, [r9+1]; DesiredAccess
0x1800628df  mov     qword ptr [rsp+0E0h+ShareAccess], rax; Object
0x1800628e4  call    cs:__imp_ObReferenceObjectByHandle
0x1800628eb  nop     dword ptr [rax+rax+00h]
0x1800628f0  mov     ebx, eax
0x1800628f2  test    eax, eax
0x1800628f4  js      loc_180062A13
0x1800628fa  mov     rcx, [rbp+4Fh+Object]; Object
0x1800628fe  mov     rax, [rcx+8]
0x180062902  mov     ebx, [rax+30h]
0x180062905  call    cs:__imp_ObfDereferenceObject
0x18006290c  nop     dword ptr [rax+rax+00h]
0x180062911  bt      ebx, 8
0x180062915  jb      short loc_180062921
0x180062917  mov     ebx, 0C0000143h
0x18006291c  jmp     loc_180062A13
0x180062921  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x180062925  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x180062929  mov     r9d, 18h; Length
0x18006292f  mov     [rsp+0E0h+ShareAccess], 5; FileInformationClass
0x180062937  lea     rdx, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x18006293b  call    cs:__imp_ZwQueryInformationFile
0x180062942  nop     dword ptr [rax+rax+00h]
0x180062947  mov     ebx, eax
0x180062949  test    eax, eax
0x18006294b  js      loc_180062A13
0x180062951  mov     rcx, qword ptr [rbp+4Fh+FileInformation+8]
0x180062955  test    rcx, rcx
0x180062958  jnz     short loc_180062964
0x18006295a  mov     ebx, 0C000011Eh
0x18006295f  jmp     loc_180062A13
0x180062964  cmp     dword ptr [rbp+4Fh+FileInformation+0Ch], 0
0x180062968  jnz     loc_180062A0E
0x18006296e  cmp     rcx, rsi
0x180062971  jg      loc_180062A0E
0x180062977  mov     edx, ecx
0x180062979  and     edi, 10h
0x18006297c  or      edi, 1020h
0x180062982  mov     esi, 63734943h
0x180062987  mov     ecx, edi
0x180062989  mov     r8d, esi
0x18006298c  shr     rcx, 4
0x180062990  call    cs:__imp_ExAllocatePool2
0x180062997  nop     dword ptr [rax+rax+00h]
0x18006299c  mov     rdi, rax
0x18006299f  test    rax, rax
0x1800629a2  jnz     short loc_1800629AB
0x1800629a4  mov     ebx, 0C0000017h
0x1800629a9  jmp     short loc_180062A13
0x1800629ab  mov     eax, dword ptr [rbp+4Fh+FileInformation+8]
0x1800629ae  xor     r9d, r9d; ApcContext
0x1800629b1  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1800629b5  xor     r8d, r8d; ApcRoutine
0x1800629b8  mov     [rsp+0E0h+Key], 0; Key
0x1800629c1  xor     edx, edx; Event
0x1800629c3  mov     [rsp+0E0h+ByteOffset], 0; ByteOffset
0x1800629cc  mov     [rsp+0E0h+Length], eax; Length
0x1800629d0  lea     rax, [rbp+4Fh+IoStatusBlock]
0x1800629d4  mov     qword ptr [rsp+0E0h+OpenOptions], rdi; Buffer
0x1800629d9  mov     qword ptr [rsp+0E0h+ShareAccess], rax; IoStatusBlock
0x1800629de  call    cs:__imp_ZwReadFile
0x1800629e5  nop     dword ptr [rax+rax+00h]
0x1800629ea  mov     ebx, eax
0x1800629ec  test    eax, eax
0x1800629ee  js      short loc_1800629FB
0x1800629f0  mov     eax, dword ptr [rbp+4Fh+FileInformation+8]
0x1800629f3  mov     [r15], eax
0x1800629f6  mov     [r14], rdi
0x1800629f9  jmp     short loc_180062A13
0x1800629fb  mov     edx, esi; Tag
0x1800629fd  mov     rcx, rdi; P
0x180062a00  call    cs:__imp_ExFreePoolWithTag
0x180062a07  nop     dword ptr [rax+rax+00h]
0x180062a0c  jmp     short loc_180062A13
0x180062a0e  mov     ebx, 0C0000904h
0x180062a13  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x180062a17  test    rcx, rcx
0x180062a1a  jz      short loc_180062A28
0x180062a1c  call    cs:__imp_ZwClose
0x180062a23  nop     dword ptr [rax+rax+00h]
0x180062a28  mov     eax, ebx
0x180062a2a  mov     rcx, [rbp+4Fh+var_28]
0x180062a2e  xor     rcx, rsp; StackCookie
0x180062a31  call    __security_check_cookie
0x180062a36  mov     rbx, [rsp+0E0h+arg_8]
0x180062a3e  add     rsp, 0C0h
0x180062a45  pop     r15
0x180062a47  pop     r14
0x180062a49  pop     rdi
0x180062a4a  pop     rsi
0x180062a4b  pop     rbp
0x180062a4c  retn
```
