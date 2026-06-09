# CiReadFileAtPath

- ea: `0x1800626ac`
- end: `0x1800628ea`
- name: `CiReadFileAtPath`
- size: `574`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180063878`
- `0x180076158`

## callees

- `0x18002bf20`
- `0x1800626ac`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18006282c`
- `ntoskrnl!ExAllocatePool2` at `0x18006282c`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006289c`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006289c`
- `ntoskrnl!ZwOpenFile` at `0x180062735`
- `ntoskrnl!ZwOpenFile` at `0x180062735`
- `ntoskrnl!ZwClose` at `0x1800628b8`
- `ntoskrnl!ZwClose` at `0x1800628b8`
- `ntoskrnl!ObfDereferenceObject` at `0x1800627a1`
- `ntoskrnl!ObfDereferenceObject` at `0x1800627a1`
- `ntoskrnl!IoFileObjectType` at `0x180062751`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180062780`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180062780`
- `ntoskrnl!ZwQueryInformationFile` at `0x1800627d7`
- `ntoskrnl!ZwQueryInformationFile` at `0x1800627d7`
- `ntoskrnl!ZwReadFile` at `0x18006287a`
- `ntoskrnl!ZwReadFile` at `0x18006287a`

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
0x1800626ac  mov     [rsp-8+arg_8], rbx
0x1800626b1  push    rbp
0x1800626b2  push    rsi
0x1800626b3  push    rdi
0x1800626b4  push    r14
0x1800626b6  push    r15
0x1800626b8  lea     rbp, [rsp-2Fh]
0x1800626bd  sub     rsp, 0C0h
0x1800626c4  mov     rax, cs:__security_cookie
0x1800626cb  xor     rax, rsp
0x1800626ce  mov     [rbp+4Fh+var_28], rax
0x1800626d2  mov     r15, [rbp+4Fh+arg_20]
0x1800626d6  xorps   xmm0, xmm0
0x1800626d9  xor     eax, eax
0x1800626db  mov     esi, r8d
0x1800626de  mov     r14, r9
0x1800626e1  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rcx
0x1800626e5  mov     edi, edx
0x1800626e7  mov     [rsp+0E0h+OpenOptions], 60h ; '`'; OpenOptions
0x1800626ef  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1800626f3  mov     [rbp+4Fh+var_30], rax
0x1800626f7  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1800626fb  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rax
0x1800626ff  mov     edx, 120089h; DesiredAccess
0x180062704  mov     [rbp+4Fh+FileHandle], 0
0x18006270c  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x180062710  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x180062718  movups  [rbp+4Fh+FileInformation], xmm0
0x18006271c  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x180062724  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x180062728  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x180062730  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180062735  call    cs:__imp_ZwOpenFile
0x18006273c  nop     dword ptr [rax+rax+00h]
0x180062741  mov     ebx, eax
0x180062743  test    eax, eax
0x180062745  js      loc_1800628AF
0x18006274b  test    dil, 8
0x18006274f  jz      short loc_1800627BD
0x180062751  mov     r8, cs:__imp_IoFileObjectType
0x180062758  lea     rax, [rbp+4Fh+Object]
0x18006275c  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x180062760  xor     r9d, r9d; AccessMode
0x180062763  mov     qword ptr [rsp+0E0h+OpenOptions], 0; HandleInformation
0x18006276c  mov     [rbp+4Fh+Object], 0
0x180062774  mov     r8, [r8]; ObjectType
0x180062777  lea     edx, [r9+1]; DesiredAccess
0x18006277b  mov     qword ptr [rsp+0E0h+ShareAccess], rax; Object
0x180062780  call    cs:__imp_ObReferenceObjectByHandle
0x180062787  nop     dword ptr [rax+rax+00h]
0x18006278c  mov     ebx, eax
0x18006278e  test    eax, eax
0x180062790  js      loc_1800628AF
0x180062796  mov     rcx, [rbp+4Fh+Object]; Object
0x18006279a  mov     rax, [rcx+8]
0x18006279e  mov     ebx, [rax+30h]
0x1800627a1  call    cs:__imp_ObfDereferenceObject
0x1800627a8  nop     dword ptr [rax+rax+00h]
0x1800627ad  bt      ebx, 8
0x1800627b1  jb      short loc_1800627BD
0x1800627b3  mov     ebx, 0C0000143h
0x1800627b8  jmp     loc_1800628AF
0x1800627bd  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1800627c1  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x1800627c5  mov     r9d, 18h; Length
0x1800627cb  mov     [rsp+0E0h+ShareAccess], 5; FileInformationClass
0x1800627d3  lea     rdx, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1800627d7  call    cs:__imp_ZwQueryInformationFile
0x1800627de  nop     dword ptr [rax+rax+00h]
0x1800627e3  mov     ebx, eax
0x1800627e5  test    eax, eax
0x1800627e7  js      loc_1800628AF
0x1800627ed  mov     rcx, qword ptr [rbp+4Fh+FileInformation+8]
0x1800627f1  test    rcx, rcx
0x1800627f4  jnz     short loc_180062800
0x1800627f6  mov     ebx, 0C000011Eh
0x1800627fb  jmp     loc_1800628AF
0x180062800  cmp     dword ptr [rbp+4Fh+FileInformation+0Ch], 0
0x180062804  jnz     loc_1800628AA
0x18006280a  cmp     rcx, rsi
0x18006280d  jg      loc_1800628AA
0x180062813  mov     edx, ecx
0x180062815  and     edi, 10h
0x180062818  or      edi, 1020h
0x18006281e  mov     esi, 63734943h
0x180062823  mov     ecx, edi
0x180062825  mov     r8d, esi
0x180062828  shr     rcx, 4
0x18006282c  call    cs:__imp_ExAllocatePool2
0x180062833  nop     dword ptr [rax+rax+00h]
0x180062838  mov     rdi, rax
0x18006283b  test    rax, rax
0x18006283e  jnz     short loc_180062847
0x180062840  mov     ebx, 0C0000017h
0x180062845  jmp     short loc_1800628AF
0x180062847  mov     eax, dword ptr [rbp+4Fh+FileInformation+8]
0x18006284a  xor     r9d, r9d; ApcContext
0x18006284d  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x180062851  xor     r8d, r8d; ApcRoutine
0x180062854  mov     [rsp+0E0h+Key], 0; Key
0x18006285d  xor     edx, edx; Event
0x18006285f  mov     [rsp+0E0h+ByteOffset], 0; ByteOffset
0x180062868  mov     [rsp+0E0h+Length], eax; Length
0x18006286c  lea     rax, [rbp+4Fh+IoStatusBlock]
0x180062870  mov     qword ptr [rsp+0E0h+OpenOptions], rdi; Buffer
0x180062875  mov     qword ptr [rsp+0E0h+ShareAccess], rax; IoStatusBlock
0x18006287a  call    cs:__imp_ZwReadFile
0x180062881  nop     dword ptr [rax+rax+00h]
0x180062886  mov     ebx, eax
0x180062888  test    eax, eax
0x18006288a  js      short loc_180062897
0x18006288c  mov     eax, dword ptr [rbp+4Fh+FileInformation+8]
0x18006288f  mov     [r15], eax
0x180062892  mov     [r14], rdi
0x180062895  jmp     short loc_1800628AF
0x180062897  mov     edx, esi; Tag
0x180062899  mov     rcx, rdi; P
0x18006289c  call    cs:__imp_ExFreePoolWithTag
0x1800628a3  nop     dword ptr [rax+rax+00h]
0x1800628a8  jmp     short loc_1800628AF
0x1800628aa  mov     ebx, 0C0000904h
0x1800628af  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x1800628b3  test    rcx, rcx
0x1800628b6  jz      short loc_1800628C4
0x1800628b8  call    cs:__imp_ZwClose
0x1800628bf  nop     dword ptr [rax+rax+00h]
0x1800628c4  mov     eax, ebx
0x1800628c6  mov     rcx, [rbp+4Fh+var_28]
0x1800628ca  xor     rcx, rsp; StackCookie
0x1800628cd  call    __security_check_cookie
0x1800628d2  mov     rbx, [rsp+0E0h+arg_8]
0x1800628da  add     rsp, 0C0h
0x1800628e1  pop     r15
0x1800628e3  pop     r14
0x1800628e5  pop     rdi
0x1800628e6  pop     rsi
0x1800628e7  pop     rbp
0x1800628e8  retn
```
