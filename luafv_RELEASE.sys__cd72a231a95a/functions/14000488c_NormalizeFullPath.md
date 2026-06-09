# NormalizeFullPath

- ea: `0x14000488c`
- end: `0x140004b6f`
- name: `NormalizeFullPath`
- size: `739`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140003b6c`

## callees

- `0x14000488c`
- `0x140005d00`
- `0x14001b650`
- `0x14001dd40`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140004b23`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140004b23`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140004b0f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140004b0f`
- `ntoskrnl!ObfDereferenceObject` at `0x140004a7a`
- `ntoskrnl!ObfDereferenceObject` at `0x140004a7a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140004ae0`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140004b33`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140004ae0`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140004b33`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140004a58`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140004a58`
- `FLTMGR!FltClose` at `0x140004a6a`
- `FLTMGR!FltClose` at `0x140004a6a`
- `FLTMGR!FltCreateFileEx2` at `0x140004a28`
- `FLTMGR!FltCreateFileEx2` at `0x140004a28`

## pseudocode

```c
__int64 __fastcall NormalizeFullPath(__int64 a1, unsigned __int16 a2, unsigned __int16 *a3, __int64 a4)
{
  unsigned __int16 v4; // di
  unsigned int v5; // esi
  __int64 v9; // rax
  unsigned __int16 v10; // di
  __int64 v11; // r8
  unsigned __int16 v12; // dx
  unsigned __int16 v13; // cx
  const void *v15; // rdx
  struct _FLT_INSTANCE *v16; // rdx
  NTSTATUS FileNameInformationUnsafe; // ebx
  __int64 v18; // r8
  unsigned int v19; // ebx
  __int64 v20; // rax
  void *FileHandle; // [rsp+80h] [rbp-59h] BYREF
  __int128 v22; // [rsp+88h] [rbp-51h] BYREF
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
  v22 = 0;
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
  LOBYTE(v11) = 2;
  WORD1(v22) = v5 + v10 + 2;
  *((_QWORD *)&v22 + 1) = LuafvAllocatePool(1, WORD1(v22), v11);
  if ( !*((_QWORD *)&v22 + 1) )
    return 3221225626LL;
  v15 = (const void *)*((_QWORD *)a3 + 1);
  LOWORD(v22) = v5 + v10;
  memmove(*((void **)&v22 + 1), v15, (unsigned __int16)(v5 + v10));
  v16 = *(struct _FLT_INSTANCE **)(a1 + 24);
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v22;
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
      v20 = *((_QWORD *)a3 + 1);
      LOBYTE(v18) = 2;
      Source.Length = *a3 - v10 - v5;
      Source.MaximumLength = Source.Length;
      Source.Buffer = (PWSTR)(v20 + 2 * ((unsigned __int64)(v5 + v10) >> 1));
      DestinationString.MaximumLength = FileNameInformation->Name.Length + Source.Length + 2;
      DestinationString.Buffer = (PWSTR)LuafvAllocatePool(1, DestinationString.MaximumLength, v18);
      if ( DestinationString.Buffer )
      {
        DestinationString.Length = 0;
        RtlCopyUnicodeString(&DestinationString, &FileNameInformation->Name);
        RtlAppendUnicodeStringToString(&DestinationString, &Source);
        FltReleaseFileNameInformation(FileNameInformation);
        LuafvFreePool(*((_QWORD *)&v22 + 1));
        *(struct _UNICODE_STRING *)a4 = DestinationString;
        return 0;
      }
      FltReleaseFileNameInformation(FileNameInformation);
      v19 = -1073741670;
    }
    else
    {
      v19 = 0;
    }
    LuafvFreePool(*((_QWORD *)&v22 + 1));
    return v19;
  }
  LuafvFreePool(*((_QWORD *)&v22 + 1));
  return 0;
}

```

## disassembly

```asm
0x14000488c  mov     [rsp-8+arg_0], rbx
0x140004891  push    rbp
0x140004892  push    rsi
0x140004893  push    rdi
0x140004894  push    r12
0x140004896  push    r13
0x140004898  push    r14
0x14000489a  push    r15
0x14000489c  lea     rbp, [rsp-27h]
0x1400048a1  sub     rsp, 100h
0x1400048a8  movzx   edi, word ptr [r8]
0x1400048ac  xor     r13d, r13d
0x1400048af  xorps   xmm0, xmm0
0x1400048b2  movzx   esi, dx
0x1400048b5  xorps   xmm1, xmm1
0x1400048b8  mov     [rbp+57h+FileHandle], r13
0x1400048bc  xor     eax, eax
0x1400048be  mov     [rbp+57h+FileObject], r13
0x1400048c2  mov     [rbp+57h+FileNameInformation], r13
0x1400048c6  mov     r14, r9
0x1400048c9  mov     [r9+8], r13
0x1400048cd  mov     r15, r8
0x1400048d0  mov     [r9], r13d
0x1400048d3  mov     rbx, rcx
0x1400048d6  movups  xmmword ptr [rbp+57h+var_68.ObjectName], xmm0
0x1400048da  movups  xmmword ptr [rbp+57h+var_68+1Ch], xmm0
0x1400048de  movups  [rbp+57h+var_A8], xmm0
0x1400048e2  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x1400048e6  movups  xmmword ptr [rbp+57h+var_68.Length], xmm0
0x1400048ea  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x1400048ee  movups  xmmword ptr [rbp+57h+Source.Length], xmm1
0x1400048f2  cmp     di, si
0x1400048f5  jbe     loc_140004B51
0x1400048fb  mov     rax, [r15+8]
0x1400048ff  lea     r10d, [r13+1]
0x140004903  mov     ecx, esi
0x140004905  sub     di, si
0x140004908  shr     rcx, 1
0x14000490b  mov     r8d, r13d
0x14000490e  mov     edx, r13d
0x140004911  lea     r9, [rax+rcx*2]
0x140004915  mov     ecx, r13d
0x140004918  cmp     r13w, di
0x14000491c  jnb     short loc_140004945
0x14000491e  movzx   eax, cx
0x140004921  shr     rax, 1
0x140004924  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x14000492a  jnz     short loc_140004936
0x14000492c  add     dx, r10w
0x140004930  cmp     dx, 3
0x140004934  jz      short loc_140004941
0x140004936  add     cx, 2
0x14000493a  cmp     cx, di
0x14000493d  jb      short loc_14000491E
0x14000493f  jmp     short loc_140004945
0x140004941  movzx   r8d, cx
0x140004945  cmp     dx, 3
0x140004949  cmovnb  di, r8w
0x14000494e  test    di, di
0x140004951  jz      loc_140004B51
0x140004957  movzx   r12d, di
0x14000495b  mov     r8b, 2
0x14000495e  add     r12d, esi
0x140004961  mov     ecx, r10d
0x140004964  lea     eax, [r12+2]
0x140004969  movzx   edx, ax
0x14000496c  mov     word ptr [rbp+57h+var_A8+2], dx
0x140004970  call    LuafvAllocatePool
0x140004975  mov     qword ptr [rbp+57h+var_A8+8], rax
0x140004979  mov     rcx, rax; void *
0x14000497c  test    rax, rax
0x14000497f  jnz     short loc_14000498B
0x140004981  mov     eax, 0C000009Ah
0x140004986  jmp     loc_140004B53
0x14000498b  mov     rdx, [r15+8]; Src
0x14000498f  lea     eax, [rsi+rdi]
0x140004992  movzx   r8d, ax; Size
0x140004996  mov     word ptr [rbp+57h+var_A8], r8w
0x14000499b  call    memmove
0x1400049a0  mov     rdx, [rbx+18h]; Instance
0x1400049a4  lea     rax, [rbp+57h+var_A8]
0x1400049a8  mov     rcx, cs:LuafvDriverData; Filter
0x1400049af  lea     r9, [rbp+57h+FileObject]; FileObject
0x1400049b3  mov     [rsp+130h+DriverContext], r13; DriverContext
0x1400049b8  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x1400049bc  mov     [rbp+57h+var_68.ObjectName], rax
0x1400049c0  xorps   xmm0, xmm0
0x1400049c3  mov     eax, 1
0x1400049c8  mov     [rbp+57h+var_68.Length], 30h ; '0'
0x1400049cf  mov     [rsp+130h+Flags], eax; Flags
0x1400049d3  mov     [rsp+130h+EaLength], r13d; EaLength
0x1400049d8  mov     [rsp+130h+EaBuffer], r13; EaBuffer
0x1400049dd  mov     [rsp+130h+CreateOptions], 21h ; '!'; CreateOptions
0x1400049e5  mov     [rsp+130h+CreateDisposition], eax; CreateDisposition
0x1400049e9  lea     rax, [rbp+57h+var_78]
0x1400049ed  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x1400049f5  mov     [rsp+130h+FileAttributes], 10h; FileAttributes
0x1400049fd  mov     [rsp+130h+AllocationSize], r13; AllocationSize
0x140004a02  mov     [rsp+130h+IoStatusBlock], rax; IoStatusBlock
0x140004a07  lea     rax, [rbp+57h+var_68]
0x140004a0b  mov     [rsp+130h+ObjectAttributes], rax; ObjectAttributes
0x140004a10  mov     [rsp+130h+DesiredAccess], 100001h; DesiredAccess
0x140004a18  mov     [rbp+57h+var_68.RootDirectory], r13
0x140004a1c  mov     [rbp+57h+var_68.Attributes], 240h
0x140004a23  movdqu  xmmword ptr [rbp+57h+var_68.SecurityDescriptor], xmm0
0x140004a28  call    cs:__imp_FltCreateFileEx2
0x140004a2f  nop     dword ptr [rax+rax+00h]
0x140004a34  test    eax, eax
0x140004a36  jns     short loc_140004A46
0x140004a38  mov     rcx, qword ptr [rbp+57h+var_A8+8]
0x140004a3c  call    LuafvFreePool
0x140004a41  jmp     loc_140004B51
0x140004a46  mov     rdx, [rbx+18h]; Instance
0x140004a4a  lea     r9, [rbp+57h+FileNameInformation]; FileNameInformation
0x140004a4e  mov     rcx, [rbp+57h+FileObject]; FileObject
0x140004a52  mov     r8d, 101h; NameOptions
0x140004a58  call    cs:__imp_FltGetFileNameInformationUnsafe
0x140004a5f  nop     dword ptr [rax+rax+00h]
0x140004a64  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140004a68  mov     ebx, eax
0x140004a6a  call    cs:__imp_FltClose
0x140004a71  nop     dword ptr [rax+rax+00h]
0x140004a76  mov     rcx, [rbp+57h+FileObject]; Object
0x140004a7a  call    cs:__imp_ObfDereferenceObject
0x140004a81  nop     dword ptr [rax+rax+00h]
0x140004a86  test    ebx, ebx
0x140004a88  jns     short loc_140004A8F
0x140004a8a  mov     ebx, r13d
0x140004a8d  jmp     short loc_140004AF1
0x140004a8f  mov     rax, [r15+8]
0x140004a93  mov     r8b, 2
0x140004a96  movzx   edx, word ptr [r15]
0x140004a9a  sub     dx, di
0x140004a9d  mov     ecx, r12d
0x140004aa0  sub     dx, si
0x140004aa3  shr     rcx, 1
0x140004aa6  mov     [rbp+57h+Source.Length], dx
0x140004aaa  mov     [rbp+57h+Source.MaximumLength], dx
0x140004aae  add     dx, 2
0x140004ab2  lea     rcx, [rax+rcx*2]
0x140004ab6  mov     rax, [rbp+57h+FileNameInformation]
0x140004aba  mov     [rbp+57h+Source.Buffer], rcx
0x140004abe  mov     ecx, 1
0x140004ac3  add     dx, [rax+8]
0x140004ac7  movzx   edx, dx
0x140004aca  mov     [rbp+57h+DestinationString.MaximumLength], dx
0x140004ace  call    LuafvAllocatePool
0x140004ad3  mov     [rbp+57h+DestinationString.Buffer], rax
0x140004ad7  test    rax, rax
0x140004ada  jnz     short loc_140004AFE
0x140004adc  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140004ae0  call    cs:__imp_FltReleaseFileNameInformation
0x140004ae7  nop     dword ptr [rax+rax+00h]
0x140004aec  mov     ebx, 0C000009Ah
0x140004af1  mov     rcx, qword ptr [rbp+57h+var_A8+8]
0x140004af5  call    LuafvFreePool
0x140004afa  mov     eax, ebx
0x140004afc  jmp     short loc_140004B53
0x140004afe  mov     rdx, [rbp+57h+FileNameInformation]
0x140004b02  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140004b06  add     rdx, 8; SourceString
0x140004b0a  mov     [rbp+57h+DestinationString.Length], r13w
0x140004b0f  call    cs:__imp_RtlCopyUnicodeString
0x140004b16  nop     dword ptr [rax+rax+00h]
0x140004b1b  lea     rdx, [rbp+57h+Source]; Source
0x140004b1f  lea     rcx, [rbp+57h+DestinationString]; Destination
0x140004b23  call    cs:__imp_RtlAppendUnicodeStringToString
0x140004b2a  nop     dword ptr [rax+rax+00h]
0x140004b2f  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140004b33  call    cs:__imp_FltReleaseFileNameInformation
0x140004b3a  nop     dword ptr [rax+rax+00h]
0x140004b3f  mov     rcx, qword ptr [rbp+57h+var_A8+8]
0x140004b43  call    LuafvFreePool
0x140004b48  movups  xmm0, xmmword ptr [rbp+57h+DestinationString.Length]
0x140004b4c  movdqu  xmmword ptr [r14], xmm0
0x140004b51  xor     eax, eax
0x140004b53  mov     rbx, [rsp+130h+arg_0]
0x140004b5b  add     rsp, 100h
0x140004b62  pop     r15
0x140004b64  pop     r14
0x140004b66  pop     r13
0x140004b68  pop     r12
0x140004b6a  pop     rdi
0x140004b6b  pop     rsi
0x140004b6c  pop     rbp
0x140004b6d  retn
```
