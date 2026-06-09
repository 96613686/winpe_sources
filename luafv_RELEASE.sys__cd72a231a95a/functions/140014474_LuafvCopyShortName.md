# LuafvCopyShortName

- ea: `0x140014474`
- end: `0x1400147ff`
- name: `LuafvCopyShortName`
- size: `907`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, UNICODE_STRING *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140023058`

## callees

- `0x140005bb0`
- `0x140005d00`
- `0x140014474`
- `0x14001ba60`
- `0x14001d8e0`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140014545`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001457c`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400145f5`
- `ntoskrnl!ExReleaseFastMutex` at `0x140014545`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001457c`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400145f5`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001451e`
- `ntoskrnl!ExAcquireFastMutex` at `0x140014569`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400145b8`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001451e`
- `ntoskrnl!ExAcquireFastMutex` at `0x140014569`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400145b8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140014777`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140014777`
- `ntoskrnl!RtlInitUnicodeString` at `0x140014626`
- `ntoskrnl!RtlInitUnicodeString` at `0x140014626`
- `ntoskrnl!ObfDereferenceObject` at `0x1400147b9`
- `ntoskrnl!ObfDereferenceObject` at `0x1400147b9`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x140014556`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x140014556`
- `FLTMGR!FltReleasePushLockEx` at `0x1400145e2`
- `FLTMGR!FltReleasePushLockEx` at `0x1400145e2`
- `FLTMGR!FltSetInformationFile` at `0x1400147a0`
- `FLTMGR!FltSetInformationFile` at `0x1400147a0`
- `FLTMGR!FltClose` at `0x1400147c9`
- `FLTMGR!FltClose` at `0x1400147c9`
- `FLTMGR!FltCreateFileEx2` at `0x1400146bd`
- `FLTMGR!FltCreateFileEx2` at `0x1400146bd`

## pseudocode

```c
__int64 __fastcall LuafvCopyShortName(PFLT_INSTANCE Instance, UNICODE_STRING *a2, void *a3)
{
  __int64 result; // rax
  int v7; // esi
  __int64 v8; // rbx
  unsigned int v9; // eax
  NTSTATUS v11; // ebx
  USHORT Length; // dx
  unsigned __int16 v13; // cx
  __int64 v14; // r8
  unsigned __int16 v15; // cx
  __int64 v16; // rdx
  PFILE_OBJECT FileObject; // [rsp+80h] [rbp-80h] BYREF
  UNICODE_STRING String2; // [rsp+88h] [rbp-78h] BYREF
  UNICODE_STRING String1; // [rsp+98h] [rbp-68h] BYREF
  void *FileHandle; // [rsp+A8h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v23; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v24; // [rsp+118h] [rbp+18h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+120h] [rbp+20h] BYREF
  _OWORD FileInformation[2]; // [rsp+130h] [rbp+30h] BYREF

  v24 = 0;
  FileHandle = 0;
  FileObject = 0;
  v23 = 0;
  String1 = 0;
  String2 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  result = LuafvFindTableNode(0, a2, 1, &v23);
  v7 = result;
  if ( (int)result < 0 )
    return result;
  v8 = v23;
  if ( (_BYTE)v24 && (*(_BYTE *)(v23 + 30) & 8) != 0 )
  {
    ExAcquireFastMutex(&FastMutex);
    if ( *(struct _KTHREAD **)(v8 + 8) == KeGetCurrentThread() )
    {
      ++*(_DWORD *)(v8 + 16);
    }
    else
    {
      ExReleaseFastMutex(&FastMutex);
      FltAcquirePushLockSharedEx(v8, 0);
      ExAcquireFastMutex(&FastMutex);
    }
    ExReleaseFastMutex(&FastMutex);
    v9 = *(unsigned __int16 *)(v8 + 128);
    LODWORD(FileInformation[0]) = v9;
    if ( v9 > 0x1C )
      v7 = -1073741823;
    else
      memmove((char *)FileInformation + 4, *(const void **)(v8 + 136), v9);
    ExAcquireFastMutex(&FastMutex);
    if ( *(struct _KTHREAD **)(v8 + 8) == KeGetCurrentThread() )
    {
      if ( (*(_DWORD *)(v8 + 16))-- != 1 )
      {
LABEL_14:
        ExReleaseFastMutex(&FastMutex);
        goto LABEL_16;
      }
      *(_QWORD *)(v8 + 8) = 0;
    }
    FltReleasePushLockEx(v8, 0);
    goto LABEL_14;
  }
  v7 = -1073741772;
LABEL_16:
  LuafvDereferenceTableNodeEx(v8, 0, 0);
  if ( v7 < 0 )
    return (unsigned int)v7;
  RtlInitUnicodeString(&DestinationString, 0);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = a3;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  FileObject = 0;
  v11 = FltCreateFileEx2(
          LuafvDriverData,
          Instance,
          &FileHandle,
          &FileObject,
          0x100100u,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          0,
          7u,
          1u,
          0x4020u,
          0,
          0,
          0x100u,
          0);
  if ( v11 >= 0 )
  {
    String1 = *a2;
    Length = String1.Length;
    v13 = String1.Length >> 1;
    do
    {
      v14 = v13;
      if ( !v13 )
        break;
      --v13;
    }
    while ( String1.Buffer[v13] != 92 );
    String1.Buffer += v14;
    String1.Length -= 2 * v14;
    String1.MaximumLength = Length - 2 * v14;
    String2 = FileObject->FileName;
    v15 = FileObject->FileName.Length >> 1;
    do
    {
      v16 = v15;
      if ( !v15 )
        break;
      --v15;
    }
    while ( String2.Buffer[v15] != 92 );
    String2.Buffer += v16;
    String2.Length = FileObject->FileName.Length - 2 * v16;
    String2.MaximumLength = String2.Length;
    if ( RtlEqualUnicodeString(&String1, &String2, 1u) )
      v11 = FltSetInformationFile(Instance, FileObject, FileInformation, 0x20u, FileShortNameInformation);
    else
      v11 = -1073741823;
    ObfDereferenceObject(FileObject);
    FltClose(FileHandle);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140014474  mov     [rsp-8+arg_18], rbx
0x140014479  push    rbp
0x14001447a  push    rsi
0x14001447b  push    rdi
0x14001447c  push    r12
0x14001447e  push    r13
0x140014480  push    r14
0x140014482  push    r15
0x140014484  lea     rbp, [rsp-60h]
0x140014489  sub     rsp, 160h
0x140014490  mov     rax, cs:__security_cookie
0x140014497  xor     rax, rsp
0x14001449a  mov     [rbp+90h+var_40], rax
0x14001449e  xorps   xmm0, xmm0
0x1400144a1  lea     r9, [rbp+90h+var_98]
0x1400144a5  xor     eax, eax
0x1400144a7  mov     r12, r8
0x1400144aa  mov     r15, rcx
0x1400144ad  mov     [rbp+90h+var_78], rax
0x1400144b1  xorps   xmm1, xmm1
0x1400144b4  xor     r13d, r13d
0x1400144b7  movups  xmmword ptr [rbp+90h+var_D8.ObjectName], xmm0
0x1400144bb  lea     r8d, [rax+1]
0x1400144bf  mov     [rbp+90h+FileHandle], r13
0x1400144c3  xor     ecx, ecx
0x1400144c5  mov     [rbp+90h+FileObject], r13
0x1400144c9  mov     r14, rdx
0x1400144cc  movups  [rbp+90h+var_98], xmm0
0x1400144d0  movups  xmmword ptr [rbp+90h+String1.Length], xmm0
0x1400144d4  movups  xmmword ptr [rbp+90h+String2.Length], xmm1
0x1400144d8  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm0
0x1400144dc  movups  xmmword ptr [rbp+90h+var_D8.Length], xmm0
0x1400144e0  movups  xmmword ptr [rbp+90h+var_D8+1Ch], xmm0
0x1400144e4  movups  xmmword ptr [rbp+90h+var_70], xmm0
0x1400144e8  movups  [rbp+90h+FileInformation], xmm0
0x1400144ec  movups  [rbp+90h+var_50], xmm0
0x1400144f0  call    LuafvFindTableNode
0x1400144f5  mov     esi, eax
0x1400144f7  test    eax, eax
0x1400144f9  js      loc_1400147D7
0x1400144ff  mov     rbx, qword ptr [rbp+90h+var_98]
0x140014503  cmp     byte ptr [rbp+90h+var_78], r13b
0x140014507  jz      loc_140014603
0x14001450d  test    byte ptr [rbx+1Eh], 8
0x140014511  jz      loc_140014603
0x140014517  lea     rcx, FastMutex; FastMutex
0x14001451e  call    cs:__imp_ExAcquireFastMutex
0x140014525  nop     dword ptr [rax+rax+00h]
0x14001452a  mov     rax, gs:188h
0x140014533  cmp     [rbx+8], rax
0x140014537  jnz     short loc_14001453E
0x140014539  inc     dword ptr [rbx+10h]
0x14001453c  jmp     short loc_140014575
0x14001453e  lea     rcx, FastMutex; FastMutex
0x140014545  call    cs:__imp_ExReleaseFastMutex
0x14001454c  nop     dword ptr [rax+rax+00h]
0x140014551  xor     edx, edx
0x140014553  mov     rcx, rbx
0x140014556  call    cs:__imp_FltAcquirePushLockSharedEx
0x14001455d  nop     dword ptr [rax+rax+00h]
0x140014562  lea     rcx, FastMutex; FastMutex
0x140014569  call    cs:__imp_ExAcquireFastMutex
0x140014570  nop     dword ptr [rax+rax+00h]
0x140014575  lea     rcx, FastMutex; FastMutex
0x14001457c  call    cs:__imp_ExReleaseFastMutex
0x140014583  nop     dword ptr [rax+rax+00h]
0x140014588  movzx   eax, word ptr [rbx+80h]
0x14001458f  mov     dword ptr [rbp+90h+FileInformation], eax
0x140014592  cmp     eax, 1Ch
0x140014595  ja      short loc_1400145AC
0x140014597  mov     rdx, [rbx+88h]; Src
0x14001459e  lea     rcx, [rbp+90h+FileInformation+4]; void *
0x1400145a2  mov     r8d, eax; Size
0x1400145a5  call    memmove
0x1400145aa  jmp     short loc_1400145B1
0x1400145ac  mov     esi, 0C0000001h
0x1400145b1  lea     rcx, FastMutex; FastMutex
0x1400145b8  call    cs:__imp_ExAcquireFastMutex
0x1400145bf  nop     dword ptr [rax+rax+00h]
0x1400145c4  mov     rax, gs:188h
0x1400145cd  cmp     [rbx+8], rax
0x1400145d1  jnz     short loc_1400145DD
0x1400145d3  sub     dword ptr [rbx+10h], 1
0x1400145d7  jnz     short loc_1400145EE
0x1400145d9  mov     [rbx+8], r13
0x1400145dd  xor     edx, edx
0x1400145df  mov     rcx, rbx
0x1400145e2  call    cs:__imp_FltReleasePushLockEx
0x1400145e9  nop     dword ptr [rax+rax+00h]
0x1400145ee  lea     rcx, FastMutex; FastMutex
0x1400145f5  call    cs:__imp_ExReleaseFastMutex
0x1400145fc  nop     dword ptr [rax+rax+00h]
0x140014601  jmp     short loc_140014608
0x140014603  mov     esi, 0C0000034h
0x140014608  xor     r8d, r8d
0x14001460b  xor     edx, edx
0x14001460d  mov     rcx, rbx
0x140014610  call    LuafvDereferenceTableNodeEx
0x140014615  test    esi, esi
0x140014617  jns     short loc_140014620
0x140014619  mov     eax, esi
0x14001461b  jmp     loc_1400147D7
0x140014620  xor     edx, edx; SourceString
0x140014622  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x140014626  call    cs:__imp_RtlInitUnicodeString
0x14001462d  nop     dword ptr [rax+rax+00h]
0x140014632  mov     rcx, cs:LuafvDriverData; Filter
0x140014639  lea     rax, [rbp+90h+DestinationString]
0x14001463d  mov     [rsp+190h+DriverContext], r13; DriverContext
0x140014642  lea     r9, [rbp+90h+FileObject]; FileObject
0x140014646  mov     [rsp+190h+Flags], 100h; Flags
0x14001464e  lea     r8, [rbp+90h+FileHandle]; FileHandle
0x140014652  mov     [rsp+190h+EaLength], r13d; EaLength
0x140014657  xorps   xmm0, xmm0
0x14001465a  mov     [rsp+190h+EaBuffer], r13; EaBuffer
0x14001465f  mov     rdx, r15; Instance
0x140014662  mov     [rsp+190h+CreateOptions], 4020h; CreateOptions
0x14001466a  mov     [rsp+190h+CreateDisposition], 1; CreateDisposition
0x140014672  mov     [rsp+190h+ShareAccess], 7; ShareAccess
0x14001467a  mov     [rsp+190h+FileAttributes], r13d; FileAttributes
0x14001467f  mov     [rbp+90h+var_D8.ObjectName], rax
0x140014683  lea     rax, [rbp+90h+var_70]
0x140014687  mov     [rsp+190h+AllocationSize], r13; AllocationSize
0x14001468c  mov     [rsp+190h+IoStatusBlock], rax; IoStatusBlock
0x140014691  lea     rax, [rbp+90h+var_D8]
0x140014695  mov     [rsp+190h+ObjectAttributes], rax; ObjectAttributes
0x14001469a  mov     [rsp+190h+DesiredAccess], 100100h; DesiredAccess
0x1400146a2  mov     [rbp+90h+var_D8.Length], 30h ; '0'
0x1400146a9  mov     [rbp+90h+var_D8.RootDirectory], r12
0x1400146ad  mov     [rbp+90h+var_D8.Attributes], 240h
0x1400146b4  movdqu  xmmword ptr [rbp+90h+var_D8.SecurityDescriptor], xmm0
0x1400146b9  mov     [rbp+90h+FileObject], r13
0x1400146bd  call    cs:__imp_FltCreateFileEx2
0x1400146c4  nop     dword ptr [rax+rax+00h]
0x1400146c9  mov     ebx, eax
0x1400146cb  test    eax, eax
0x1400146cd  js      loc_1400147D5
0x1400146d3  movups  xmm0, xmmword ptr [r14]
0x1400146d7  movzx   edx, word ptr [r14]
0x1400146db  mov     r11d, 0FFFFh
0x1400146e1  movzx   ecx, dx
0x1400146e4  movdqu  xmmword ptr [rbp+90h+String1.Length], xmm0
0x1400146e9  mov     r9, [rbp+90h+String1.Buffer]
0x1400146ed  shr     cx, 1
0x1400146f0  movzx   r8d, cx
0x1400146f4  test    cx, cx
0x1400146f7  jz      short loc_140014708
0x1400146f9  add     cx, r11w
0x1400146fd  movzx   eax, cx
0x140014700  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x140014706  jnz     short loc_1400146F0
0x140014708  lea     rcx, [r9+r8*2]
0x14001470c  mov     r9, [rbp+90h+FileObject]
0x140014710  mov     [rbp+90h+String1.Buffer], rcx
0x140014714  add     r8w, r8w
0x140014718  sub     dx, r8w
0x14001471c  mov     [rbp+90h+String1.Length], dx
0x140014720  mov     [rbp+90h+String1.MaximumLength], dx
0x140014724  movups  xmm0, xmmword ptr [r9+58h]
0x140014729  movdqu  xmmword ptr [rbp+90h+String2.Length], xmm0
0x14001472e  movzx   ecx, word ptr [r9+58h]
0x140014733  mov     r10, [rbp+90h+String2.Buffer]
0x140014737  shr     cx, 1
0x14001473a  movzx   edx, cx
0x14001473d  test    cx, cx
0x140014740  jz      short loc_140014751
0x140014742  add     cx, r11w
0x140014746  movzx   eax, cx
0x140014749  cmp     word ptr [r10+rax*2], 5Ch ; '\'
0x14001474f  jnz     short loc_14001473A
0x140014751  lea     rcx, [r10+rdx*2]
0x140014755  mov     r8b, 1; CaseInSensitive
0x140014758  mov     [rbp+90h+String2.Buffer], rcx
0x14001475c  add     dx, dx
0x14001475f  movzx   eax, word ptr [r9+58h]
0x140014764  lea     rcx, [rbp+90h+String1]; String1
0x140014768  sub     ax, dx
0x14001476b  lea     rdx, [rbp+90h+String2]; String2
0x14001476f  mov     [rbp+90h+String2.Length], ax
0x140014773  mov     [rbp+90h+String2.MaximumLength], ax
0x140014777  call    cs:__imp_RtlEqualUnicodeString
0x14001477e  nop     dword ptr [rax+rax+00h]
0x140014783  test    al, al
0x140014785  jz      short loc_1400147B0
0x140014787  mov     rdx, [rbp+90h+FileObject]; FileObject
0x14001478b  lea     r8, [rbp+90h+FileInformation]; FileInformation
0x14001478f  mov     r9d, 20h ; ' '; Length
0x140014795  mov     [rsp+190h+DesiredAccess], 28h ; '('; FileInformationClass
0x14001479d  mov     rcx, r15; Instance
0x1400147a0  call    cs:__imp_FltSetInformationFile
0x1400147a7  nop     dword ptr [rax+rax+00h]
0x1400147ac  mov     ebx, eax
0x1400147ae  jmp     short loc_1400147B5
0x1400147b0  mov     ebx, 0C0000001h
0x1400147b5  mov     rcx, [rbp+90h+FileObject]; Object
0x1400147b9  call    cs:__imp_ObfDereferenceObject
0x1400147c0  nop     dword ptr [rax+rax+00h]
0x1400147c5  mov     rcx, [rbp+90h+FileHandle]; FileHandle
0x1400147c9  call    cs:__imp_FltClose
0x1400147d0  nop     dword ptr [rax+rax+00h]
0x1400147d5  mov     eax, ebx
0x1400147d7  mov     rcx, [rbp+90h+var_40]
0x1400147db  xor     rcx, rsp; StackCookie
0x1400147de  call    __security_check_cookie
0x1400147e3  mov     rbx, [rsp+190h+arg_18]
0x1400147eb  add     rsp, 160h
0x1400147f2  pop     r15
0x1400147f4  pop     r14
0x1400147f6  pop     r13
0x1400147f8  pop     r12
0x1400147fa  pop     rdi
0x1400147fb  pop     rsi
0x1400147fc  pop     rbp
0x1400147fd  retn
```
