# NormalizeFullPath

- ea: `0x1400046c4`
- end: `0x1400049a7`
- name: `NormalizeFullPath`
- size: `739`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000393c`

## callees

- `0x1400046c4`
- `0x140006080`
- `0x14001b6a0`
- `0x14001dd90`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000495b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000495b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140004947`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140004947`
- `ntoskrnl!ObfDereferenceObject` at `0x1400048b2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400048b2`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140004918`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000496b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140004918`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000496b`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140004890`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140004890`
- `FLTMGR!FltClose` at `0x1400048a2`
- `FLTMGR!FltClose` at `0x1400048a2`
- `FLTMGR!FltCreateFileEx2` at `0x140004860`
- `FLTMGR!FltCreateFileEx2` at `0x140004860`

## pseudocode

```c
__int64 __fastcall NormalizeFullPath(__int64 a1, unsigned __int16 a2, unsigned __int16 *a3, __int64 a4)
{
  unsigned __int16 v4; // di
  unsigned int v5; // esi
  __int64 v9; // rax
  unsigned __int16 v10; // di
  unsigned __int16 v11; // r8
  unsigned __int16 v12; // dx
  unsigned __int16 v13; // cx
  const void *v15; // rdx
  struct _FLT_INSTANCE *v16; // rdx
  NTSTATUS FileNameInformationUnsafe; // ebx
  unsigned int v18; // ebx
  __int64 v19; // rax
  void *FileHandle; // [rsp+80h] [rbp-59h] BYREF
  __int128 v21; // [rsp+88h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-41h] BYREF
  UNICODE_STRING Source; // [rsp+A8h] [rbp-31h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-11h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+150h] [rbp+77h] BYREF
  PFILE_OBJECT FileObject; // [rsp+158h] [rbp+7Fh] BYREF

  v4 = *a3;
  v5 = a2;
  FileHandle = 0;
  FileObject = 0;
  FileNameInformation = 0;
  *(_QWORD *)(a4 + 8) = 0;
  *(_DWORD *)a4 = 0;
  v21 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  Source = 0;
  if ( v4 <= a2 )
    return 0;
  v9 = *((_QWORD *)a3 + 1);
  v10 = v4 - a2;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  if ( v10 )
  {
    while ( *(_WORD *)(v9 + 2 * ((unsigned __int64)v5 >> 1) + 2 * ((unsigned __int64)v13 >> 1)) != 92 || ++v12 != 3 )
    {
      v13 += 2;
      if ( v13 >= v10 )
        goto LABEL_8;
    }
    v11 = v13;
  }
LABEL_8:
  if ( v12 >= 3u )
    v10 = v11;
  if ( !v10 )
    return 0;
  WORD1(v21) = v5 + v10 + 2;
  *((_QWORD *)&v21 + 1) = LuafvAllocatePool(1, WORD1(v21), 2);
  if ( !*((_QWORD *)&v21 + 1) )
    return 3221225626LL;
  v15 = (const void *)*((_QWORD *)a3 + 1);
  LOWORD(v21) = v5 + v10;
  memmove(*((void **)&v21 + 1), v15, (unsigned __int16)(v5 + v10));
  v16 = *(struct _FLT_INSTANCE **)(a1 + 24);
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v21;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( FltCreateFileEx2(
         LuafvDriverData,
         v16,
         &FileHandle,
         &FileObject,
         0x100001u,
         &ObjectAttributes,
         &IoStatusBlock,
         0,
         0x10u,
         7u,
         1u,
         0x21u,
         0,
         0,
         1u,
         0) >= 0 )
  {
    FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(
                                  FileObject,
                                  *(PFLT_INSTANCE *)(a1 + 24),
                                  0x101u,
                                  &FileNameInformation);
    FltClose(FileHandle);
    ObfDereferenceObject(FileObject);
    if ( FileNameInformationUnsafe >= 0 )
    {
      v19 = *((_QWORD *)a3 + 1);
      Source.Length = *a3 - v10 - v5;
      Source.MaximumLength = Source.Length;
      Source.Buffer = (PWSTR)(v19 + 2 * ((unsigned __int64)(v5 + v10) >> 1));
      DestinationString.MaximumLength = FileNameInformation->Name.Length + Source.Length + 2;
      DestinationString.Buffer = (PWSTR)LuafvAllocatePool(1, DestinationString.MaximumLength, 2);
      if ( DestinationString.Buffer )
      {
        DestinationString.Length = 0;
        RtlCopyUnicodeString(&DestinationString, &FileNameInformation->Name);
        RtlAppendUnicodeStringToString(&DestinationString, &Source);
        FltReleaseFileNameInformation(FileNameInformation);
        LuafvFreePool(*((_QWORD *)&v21 + 1));
        *(struct _UNICODE_STRING *)a4 = DestinationString;
        return 0;
      }
      FltReleaseFileNameInformation(FileNameInformation);
      v18 = -1073741670;
    }
    else
    {
      v18 = 0;
    }
    LuafvFreePool(*((_QWORD *)&v21 + 1));
    return v18;
  }
  LuafvFreePool(*((_QWORD *)&v21 + 1));
  return 0;
}

```

## disassembly

```asm
0x1400046c4  mov     [rsp-8+arg_0], rbx
0x1400046c9  push    rbp
0x1400046ca  push    rsi
0x1400046cb  push    rdi
0x1400046cc  push    r12
0x1400046ce  push    r13
0x1400046d0  push    r14
0x1400046d2  push    r15
0x1400046d4  lea     rbp, [rsp-27h]
0x1400046d9  sub     rsp, 100h
0x1400046e0  movzx   edi, word ptr [r8]
0x1400046e4  xor     r13d, r13d
0x1400046e7  xorps   xmm0, xmm0
0x1400046ea  movzx   esi, dx
0x1400046ed  xorps   xmm1, xmm1
0x1400046f0  mov     [rbp+57h+FileHandle], r13
0x1400046f4  xor     eax, eax
0x1400046f6  mov     [rbp+57h+FileObject], r13
0x1400046fa  mov     [rbp+57h+FileNameInformation], r13
0x1400046fe  mov     r14, r9
0x140004701  mov     [r9+8], r13
0x140004705  mov     r15, r8
0x140004708  mov     [r9], r13d
0x14000470b  mov     rbx, rcx
0x14000470e  movups  xmmword ptr [rbp+57h+var_68.ObjectName], xmm0
0x140004712  movups  xmmword ptr [rbp+57h+var_68+1Ch], xmm0
0x140004716  movups  [rbp+57h+var_A8], xmm0
0x14000471a  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x14000471e  movups  xmmword ptr [rbp+57h+var_68.Length], xmm0
0x140004722  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x140004726  movups  xmmword ptr [rbp+57h+Source.Length], xmm1
0x14000472a  cmp     di, si
0x14000472d  jbe     loc_140004989
0x140004733  mov     rax, [r15+8]
0x140004737  lea     r10d, [r13+1]
0x14000473b  mov     ecx, esi
0x14000473d  sub     di, si
0x140004740  shr     rcx, 1
0x140004743  mov     r8d, r13d
0x140004746  mov     edx, r13d
0x140004749  lea     r9, [rax+rcx*2]
0x14000474d  mov     ecx, r13d
0x140004750  cmp     r13w, di
0x140004754  jnb     short loc_14000477D
0x140004756  movzx   eax, cx
0x140004759  shr     rax, 1
0x14000475c  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x140004762  jnz     short loc_14000476E
0x140004764  add     dx, r10w
0x140004768  cmp     dx, 3
0x14000476c  jz      short loc_140004779
0x14000476e  add     cx, 2
0x140004772  cmp     cx, di
0x140004775  jb      short loc_140004756
0x140004777  jmp     short loc_14000477D
0x140004779  movzx   r8d, cx
0x14000477d  cmp     dx, 3
0x140004781  cmovnb  di, r8w
0x140004786  test    di, di
0x140004789  jz      loc_140004989
0x14000478f  movzx   r12d, di
0x140004793  mov     r8b, 2
0x140004796  add     r12d, esi
0x140004799  mov     ecx, r10d
0x14000479c  lea     eax, [r12+2]
0x1400047a1  movzx   edx, ax
0x1400047a4  mov     word ptr [rbp+57h+var_A8+2], dx
0x1400047a8  call    LuafvAllocatePool
0x1400047ad  mov     qword ptr [rbp+57h+var_A8+8], rax
0x1400047b1  mov     rcx, rax; void *
0x1400047b4  test    rax, rax
0x1400047b7  jnz     short loc_1400047C3
0x1400047b9  mov     eax, 0C000009Ah
0x1400047be  jmp     loc_14000498B
0x1400047c3  mov     rdx, [r15+8]; Src
0x1400047c7  lea     eax, [rsi+rdi]
0x1400047ca  movzx   r8d, ax; Size
0x1400047ce  mov     word ptr [rbp+57h+var_A8], r8w
0x1400047d3  call    memmove
0x1400047d8  mov     rdx, [rbx+18h]; Instance
0x1400047dc  lea     rax, [rbp+57h+var_A8]
0x1400047e0  mov     rcx, cs:LuafvDriverData; Filter
0x1400047e7  lea     r9, [rbp+57h+FileObject]; FileObject
0x1400047eb  mov     [rsp+130h+DriverContext], r13; DriverContext
0x1400047f0  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x1400047f4  mov     [rbp+57h+var_68.ObjectName], rax
0x1400047f8  xorps   xmm0, xmm0
0x1400047fb  mov     eax, 1
0x140004800  mov     [rbp+57h+var_68.Length], 30h ; '0'
0x140004807  mov     [rsp+130h+Flags], eax; Flags
0x14000480b  mov     [rsp+130h+EaLength], r13d; EaLength
0x140004810  mov     [rsp+130h+EaBuffer], r13; EaBuffer
0x140004815  mov     [rsp+130h+CreateOptions], 21h ; '!'; CreateOptions
0x14000481d  mov     [rsp+130h+CreateDisposition], eax; CreateDisposition
0x140004821  lea     rax, [rbp+57h+var_78]
0x140004825  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x14000482d  mov     [rsp+130h+FileAttributes], 10h; FileAttributes
0x140004835  mov     [rsp+130h+AllocationSize], r13; AllocationSize
0x14000483a  mov     [rsp+130h+IoStatusBlock], rax; IoStatusBlock
0x14000483f  lea     rax, [rbp+57h+var_68]
0x140004843  mov     [rsp+130h+ObjectAttributes], rax; ObjectAttributes
0x140004848  mov     [rsp+130h+DesiredAccess], 100001h; DesiredAccess
0x140004850  mov     [rbp+57h+var_68.RootDirectory], r13
0x140004854  mov     [rbp+57h+var_68.Attributes], 240h
0x14000485b  movdqu  xmmword ptr [rbp+57h+var_68.SecurityDescriptor], xmm0
0x140004860  call    cs:__imp_FltCreateFileEx2
0x140004867  nop     dword ptr [rax+rax+00h]
0x14000486c  test    eax, eax
0x14000486e  jns     short loc_14000487E
0x140004870  mov     rcx, qword ptr [rbp+57h+var_A8+8]
0x140004874  call    LuafvFreePool
0x140004879  jmp     loc_140004989
0x14000487e  mov     rdx, [rbx+18h]; Instance
0x140004882  lea     r9, [rbp+57h+FileNameInformation]; FileNameInformation
0x140004886  mov     rcx, [rbp+57h+FileObject]; FileObject
0x14000488a  mov     r8d, 101h; NameOptions
0x140004890  call    cs:__imp_FltGetFileNameInformationUnsafe
0x140004897  nop     dword ptr [rax+rax+00h]
0x14000489c  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400048a0  mov     ebx, eax
0x1400048a2  call    cs:__imp_FltClose
0x1400048a9  nop     dword ptr [rax+rax+00h]
0x1400048ae  mov     rcx, [rbp+57h+FileObject]; Object
0x1400048b2  call    cs:__imp_ObfDereferenceObject
0x1400048b9  nop     dword ptr [rax+rax+00h]
0x1400048be  test    ebx, ebx
0x1400048c0  jns     short loc_1400048C7
0x1400048c2  mov     ebx, r13d
0x1400048c5  jmp     short loc_140004929
0x1400048c7  mov     rax, [r15+8]
0x1400048cb  mov     r8b, 2
0x1400048ce  movzx   edx, word ptr [r15]
0x1400048d2  sub     dx, di
0x1400048d5  mov     ecx, r12d
0x1400048d8  sub     dx, si
0x1400048db  shr     rcx, 1
0x1400048de  mov     [rbp+57h+Source.Length], dx
0x1400048e2  mov     [rbp+57h+Source.MaximumLength], dx
0x1400048e6  add     dx, 2
0x1400048ea  lea     rcx, [rax+rcx*2]
0x1400048ee  mov     rax, [rbp+57h+FileNameInformation]
0x1400048f2  mov     [rbp+57h+Source.Buffer], rcx
0x1400048f6  mov     ecx, 1
0x1400048fb  add     dx, [rax+8]
0x1400048ff  movzx   edx, dx
0x140004902  mov     [rbp+57h+DestinationString.MaximumLength], dx
0x140004906  call    LuafvAllocatePool
0x14000490b  mov     [rbp+57h+DestinationString.Buffer], rax
0x14000490f  test    rax, rax
0x140004912  jnz     short loc_140004936
0x140004914  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140004918  call    cs:__imp_FltReleaseFileNameInformation
0x14000491f  nop     dword ptr [rax+rax+00h]
0x140004924  mov     ebx, 0C000009Ah
0x140004929  mov     rcx, qword ptr [rbp+57h+var_A8+8]
0x14000492d  call    LuafvFreePool
0x140004932  mov     eax, ebx
0x140004934  jmp     short loc_14000498B
0x140004936  mov     rdx, [rbp+57h+FileNameInformation]
0x14000493a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000493e  add     rdx, 8; SourceString
0x140004942  mov     [rbp+57h+DestinationString.Length], r13w
0x140004947  call    cs:__imp_RtlCopyUnicodeString
0x14000494e  nop     dword ptr [rax+rax+00h]
0x140004953  lea     rdx, [rbp+57h+Source]; Source
0x140004957  lea     rcx, [rbp+57h+DestinationString]; Destination
0x14000495b  call    cs:__imp_RtlAppendUnicodeStringToString
0x140004962  nop     dword ptr [rax+rax+00h]
0x140004967  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x14000496b  call    cs:__imp_FltReleaseFileNameInformation
0x140004972  nop     dword ptr [rax+rax+00h]
0x140004977  mov     rcx, qword ptr [rbp+57h+var_A8+8]
0x14000497b  call    LuafvFreePool
0x140004980  movups  xmm0, xmmword ptr [rbp+57h+DestinationString.Length]
0x140004984  movdqu  xmmword ptr [r14], xmm0
0x140004989  xor     eax, eax
0x14000498b  mov     rbx, [rsp+130h+arg_0]
0x140004993  add     rsp, 100h
0x14000499a  pop     r15
0x14000499c  pop     r14
0x14000499e  pop     r13
0x1400049a0  pop     r12
0x1400049a2  pop     rdi
0x1400049a3  pop     rsi
0x1400049a4  pop     rbp
0x1400049a5  retn
```
