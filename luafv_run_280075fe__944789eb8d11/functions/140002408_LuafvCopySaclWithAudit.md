# LuafvCopySaclWithAudit

- ea: `0x140002408`
- end: `0x140002649`
- name: `LuafvCopySaclWithAudit`
- size: `577`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFLT_CALLBACK_DATA CallbackData@<rdx>, PFILE_OBJECT FileObject@<r8>, PVOID Data, PVOID)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400230a8`

## callees

- `0x140002408`
- `0x140016ec8`
- `0x14001b6a0`
- `0x14001dd90`

## import_xrefs

- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1400025aa`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1400025aa`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000246c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000246c`
- `ntoskrnl!ObfDereferenceObject` at `0x140002609`
- `ntoskrnl!ObfDereferenceObject` at `0x140002609`
- `FLTMGR!FltSetSecurityObject` at `0x1400025d2`
- `FLTMGR!FltSetSecurityObject` at `0x1400025d2`
- `FLTMGR!FltQuerySecurityObject` at `0x140002532`
- `FLTMGR!FltQuerySecurityObject` at `0x140002589`
- `FLTMGR!FltQuerySecurityObject` at `0x140002532`
- `FLTMGR!FltQuerySecurityObject` at `0x140002589`
- `FLTMGR!FltClose` at `0x14000261e`
- `FLTMGR!FltClose` at `0x14000261e`
- `FLTMGR!FltCreateFileEx2` at `0x140002500`
- `FLTMGR!FltCreateFileEx2` at `0x140002500`

## pseudocode

```c
__int64 __fastcall LuafvCopySaclWithAudit(
        PFLT_INSTANCE Instance,
        PFLT_CALLBACK_DATA CallbackData,
        PFILE_OBJECT FileObject,
        void *a4,
        PVOID Data,
        PVOID a6)
{
  NTSTATUS SaclSecurityDescriptor; // ebx
  __int64 v11; // r8
  void *Pool; // rax
  void *v13; // rdi
  unsigned __int8 SaclDefaulted[4]; // [rsp+80h] [rbp-49h] BYREF
  ULONG LengthNeeded; // [rsp+84h] [rbp-45h] BYREF
  PFILE_OBJECT FileObjecta; // [rsp+88h] [rbp-41h] BYREF
  PACL Sacl; // [rsp+90h] [rbp-39h] BYREF
  void *FileHandle; // [rsp+98h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+D0h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp+17h] BYREF
  unsigned __int8 SaclPresent; // [rsp+138h] [rbp+6Fh] BYREF

  LengthNeeded = 0;
  SaclPresent = 0;
  Sacl = 0;
  SaclDefaulted[0] = 0;
  FileHandle = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  FileObjecta = 0;
  DestinationString = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = a4;
  ObjectAttributes.Attributes = 576;
  SaclSecurityDescriptor = FltCreateFileEx2(
                             LuafvDriverData,
                             Instance,
                             &FileHandle,
                             &FileObjecta,
                             0x140000u,
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
  if ( SaclSecurityDescriptor >= 0 )
  {
    SaclSecurityDescriptor = FltQuerySecurityObject(Instance, FileObject, 8u, 0, 0, &LengthNeeded);
    if ( SaclSecurityDescriptor == -1073741789 )
    {
      LOBYTE(v11) = 4;
      Pool = (void *)LuafvAllocatePool(1, LengthNeeded, v11);
      v13 = Pool;
      if ( Pool )
      {
        SaclSecurityDescriptor = FltQuerySecurityObject(Instance, FileObject, 8u, Pool, LengthNeeded, &LengthNeeded);
        if ( SaclSecurityDescriptor >= 0 )
        {
          SaclSecurityDescriptor = RtlGetSaclSecurityDescriptor(v13, &SaclPresent, &Sacl, SaclDefaulted);
          if ( SaclSecurityDescriptor >= 0 )
          {
            if ( SaclPresent )
            {
              SaclSecurityDescriptor = FltSetSecurityObject(Instance, FileObjecta, 8u, v13);
              if ( SaclSecurityDescriptor >= 0 )
                LuafvReportAuditVirtualizationEvent(Sacl, CallbackData, Data, a6);
            }
          }
        }
        LuafvFreePool(v13);
      }
      else
      {
        SaclSecurityDescriptor = -1073741670;
      }
    }
  }
  if ( FileObjecta )
    ObfDereferenceObject(FileObjecta);
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)SaclSecurityDescriptor;
}

```

## disassembly

```asm
0x140002408  mov     [rsp-8+arg_0], rbx
0x14000240d  mov     [rsp-8+arg_8], rsi
0x140002412  push    rbp
0x140002413  push    rdi
0x140002414  push    r12
0x140002416  push    r14
0x140002418  push    r15
0x14000241a  lea     rbp, [rsp-27h]
0x14000241f  sub     rsp, 0F0h
0x140002426  xorps   xmm0, xmm0
0x140002429  xor     r12d, r12d
0x14000242c  mov     r15, rdx
0x14000242f  mov     [rbp+47h+LengthNeeded], r12d
0x140002433  mov     rsi, rcx
0x140002436  mov     [rbp+47h+SaclPresent], r12b
0x14000243a  movups  xmmword ptr [rbp+47h+var_70.ObjectName], xmm0
0x14000243e  xor     eax, eax
0x140002440  mov     [rbp+47h+Sacl], r12
0x140002444  xor     edx, edx; SourceString
0x140002446  mov     [rbp+47h+SaclDefaulted], r12b
0x14000244a  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x14000244e  mov     [rbp+47h+FileHandle], r12
0x140002452  movups  xmmword ptr [rbp+47h+var_70+1Ch], xmm0
0x140002456  mov     rbx, r9
0x140002459  mov     [rbp+47h+FileObject], r12
0x14000245d  mov     r14, r8
0x140002460  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x140002464  movups  xmmword ptr [rbp+47h+var_70.Length], xmm0
0x140002468  movups  xmmword ptr [rbp+47h+var_30], xmm0
0x14000246c  call    cs:__imp_RtlInitUnicodeString
0x140002473  nop     dword ptr [rax+rax+00h]
0x140002478  mov     rcx, cs:LuafvDriverData; Filter
0x14000247f  lea     rax, [rbp+47h+DestinationString]
0x140002483  mov     [rsp+110h+DriverContext], r12; DriverContext
0x140002488  lea     edi, [r12+1]
0x14000248d  mov     [rsp+110h+Flags], 100h; Flags
0x140002495  lea     r9, [rbp+47h+FileObject]; FileObject
0x140002499  mov     [rsp+110h+EaLength], r12d; EaLength
0x14000249e  lea     r8, [rbp+47h+FileHandle]; FileHandle
0x1400024a2  mov     [rsp+110h+EaBuffer], r12; EaBuffer
0x1400024a7  xorps   xmm0, xmm0
0x1400024aa  mov     [rsp+110h+CreateOptions], 4020h; CreateOptions
0x1400024b2  mov     rdx, rsi; Instance
0x1400024b5  mov     [rsp+110h+CreateDisposition], edi; CreateDisposition
0x1400024b9  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x1400024c1  mov     [rsp+110h+FileAttributes], r12d; FileAttributes
0x1400024c6  mov     [rbp+47h+var_70.ObjectName], rax
0x1400024ca  lea     rax, [rbp+47h+var_30]
0x1400024ce  mov     [rsp+110h+AllocationSize], r12; AllocationSize
0x1400024d3  mov     [rsp+110h+IoStatusBlock], rax; IoStatusBlock
0x1400024d8  lea     rax, [rbp+47h+var_70]
0x1400024dc  mov     [rsp+110h+ObjectAttributes], rax; ObjectAttributes
0x1400024e1  mov     [rsp+110h+DesiredAccess], 140000h; DesiredAccess
0x1400024e9  mov     [rbp+47h+var_70.Length], 30h ; '0'
0x1400024f0  mov     [rbp+47h+var_70.RootDirectory], rbx
0x1400024f4  mov     [rbp+47h+var_70.Attributes], 240h
0x1400024fb  movdqu  xmmword ptr [rbp+47h+var_70.SecurityDescriptor], xmm0
0x140002500  call    cs:__imp_FltCreateFileEx2
0x140002507  nop     dword ptr [rax+rax+00h]
0x14000250c  mov     ebx, eax
0x14000250e  test    eax, eax
0x140002510  js      loc_140002600
0x140002516  lea     rax, [rbp+47h+LengthNeeded]
0x14000251a  xor     r9d, r9d; SecurityDescriptor
0x14000251d  mov     [rsp+110h+ObjectAttributes], rax; LengthNeeded
0x140002522  lea     r8d, [r12+8]; SecurityInformation
0x140002527  mov     rdx, r14; FileObject
0x14000252a  mov     [rsp+110h+DesiredAccess], r12d; Length
0x14000252f  mov     rcx, rsi; Instance
0x140002532  call    cs:__imp_FltQuerySecurityObject
0x140002539  nop     dword ptr [rax+rax+00h]
0x14000253e  mov     ebx, eax
0x140002540  cmp     eax, 0C0000023h
0x140002545  jnz     loc_140002600
0x14000254b  mov     edx, [rbp+47h+LengthNeeded]
0x14000254e  mov     r8b, 4
0x140002551  mov     ecx, edi
0x140002553  call    LuafvAllocatePool
0x140002558  mov     rdi, rax
0x14000255b  test    rax, rax
0x14000255e  jnz     short loc_14000256A
0x140002560  mov     ebx, 0C000009Ah
0x140002565  jmp     loc_140002600
0x14000256a  lea     rax, [rbp+47h+LengthNeeded]
0x14000256e  mov     r9, rdi; SecurityDescriptor
0x140002571  mov     [rsp+110h+ObjectAttributes], rax; LengthNeeded
0x140002576  mov     r8d, 8; SecurityInformation
0x14000257c  mov     eax, [rbp+47h+LengthNeeded]
0x14000257f  mov     rdx, r14; FileObject
0x140002582  mov     rcx, rsi; Instance
0x140002585  mov     [rsp+110h+DesiredAccess], eax; Length
0x140002589  call    cs:__imp_FltQuerySecurityObject
0x140002590  nop     dword ptr [rax+rax+00h]
0x140002595  mov     ebx, eax
0x140002597  test    eax, eax
0x140002599  js      short loc_1400025F8
0x14000259b  lea     r9, [rbp+47h+SaclDefaulted]; SaclDefaulted
0x14000259f  mov     rcx, rdi; SecurityDescriptor
0x1400025a2  lea     r8, [rbp+47h+Sacl]; Sacl
0x1400025a6  lea     rdx, [rbp+47h+SaclPresent]; SaclPresent
0x1400025aa  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x1400025b1  nop     dword ptr [rax+rax+00h]
0x1400025b6  mov     ebx, eax
0x1400025b8  test    eax, eax
0x1400025ba  js      short loc_1400025F8
0x1400025bc  cmp     [rbp+47h+SaclPresent], r12b
0x1400025c0  jz      short loc_1400025F8
0x1400025c2  mov     rdx, [rbp+47h+FileObject]; FileObject
0x1400025c6  mov     r9, rdi; SecurityDescriptor
0x1400025c9  mov     r8d, 8; SecurityInformation
0x1400025cf  mov     rcx, rsi; Instance
0x1400025d2  call    cs:__imp_FltSetSecurityObject
0x1400025d9  nop     dword ptr [rax+rax+00h]
0x1400025de  mov     ebx, eax
0x1400025e0  test    eax, eax
0x1400025e2  js      short loc_1400025F8
0x1400025e4  mov     r9, [rbp+47h+arg_28]; PVOID
0x1400025e8  mov     rdx, r15; CallbackData
0x1400025eb  mov     r8, [rbp+47h+Data]; Data
0x1400025ef  mov     rcx, [rbp+47h+Sacl]; ResourceSacl
0x1400025f3  call    LuafvReportAuditVirtualizationEvent
0x1400025f8  mov     rcx, rdi
0x1400025fb  call    LuafvFreePool
0x140002600  mov     rcx, [rbp+47h+FileObject]; Object
0x140002604  test    rcx, rcx
0x140002607  jz      short loc_140002615
0x140002609  call    cs:__imp_ObfDereferenceObject
0x140002610  nop     dword ptr [rax+rax+00h]
0x140002615  mov     rcx, [rbp+47h+FileHandle]; FileHandle
0x140002619  test    rcx, rcx
0x14000261c  jz      short loc_14000262A
0x14000261e  call    cs:__imp_FltClose
0x140002625  nop     dword ptr [rax+rax+00h]
0x14000262a  lea     r11, [rsp+110h+var_20]
0x140002632  mov     eax, ebx
0x140002634  mov     rbx, [r11+30h]
0x140002638  mov     rsi, [r11+38h]
0x14000263c  mov     rsp, r11
0x14000263f  pop     r15
0x140002641  pop     r14
0x140002643  pop     r12
0x140002645  pop     rdi
0x140002646  pop     rbp
0x140002647  retn
```
