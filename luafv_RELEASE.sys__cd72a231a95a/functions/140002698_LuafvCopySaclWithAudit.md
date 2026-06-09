# LuafvCopySaclWithAudit

- ea: `0x140002698`
- end: `0x1400028d9`
- name: `LuafvCopySaclWithAudit`
- size: `577`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFLT_CALLBACK_DATA CallbackData, PFILE_OBJECT FileObject, void *, PVOID Data, PVOID)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140023058`

## callees

- `0x140002698`
- `0x140016e78`
- `0x14001b650`
- `0x14001dd40`

## import_xrefs

- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x14000283a`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x14000283a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400026fc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400026fc`
- `ntoskrnl!ObfDereferenceObject` at `0x140002899`
- `ntoskrnl!ObfDereferenceObject` at `0x140002899`
- `FLTMGR!FltSetSecurityObject` at `0x140002862`
- `FLTMGR!FltSetSecurityObject` at `0x140002862`
- `FLTMGR!FltQuerySecurityObject` at `0x1400027c2`
- `FLTMGR!FltQuerySecurityObject` at `0x140002819`
- `FLTMGR!FltQuerySecurityObject` at `0x1400027c2`
- `FLTMGR!FltQuerySecurityObject` at `0x140002819`
- `FLTMGR!FltClose` at `0x1400028ae`
- `FLTMGR!FltClose` at `0x1400028ae`
- `FLTMGR!FltCreateFileEx2` at `0x140002790`
- `FLTMGR!FltCreateFileEx2` at `0x140002790`

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
0x140002698  mov     [rsp-8+arg_0], rbx
0x14000269d  mov     [rsp-8+arg_8], rsi
0x1400026a2  push    rbp
0x1400026a3  push    rdi
0x1400026a4  push    r12
0x1400026a6  push    r14
0x1400026a8  push    r15
0x1400026aa  lea     rbp, [rsp-27h]
0x1400026af  sub     rsp, 0F0h
0x1400026b6  xorps   xmm0, xmm0
0x1400026b9  xor     r12d, r12d
0x1400026bc  mov     r15, rdx
0x1400026bf  mov     [rbp+47h+LengthNeeded], r12d
0x1400026c3  mov     rsi, rcx
0x1400026c6  mov     [rbp+47h+SaclPresent], r12b
0x1400026ca  movups  xmmword ptr [rbp+47h+var_70.ObjectName], xmm0
0x1400026ce  xor     eax, eax
0x1400026d0  mov     [rbp+47h+Sacl], r12
0x1400026d4  xor     edx, edx; SourceString
0x1400026d6  mov     [rbp+47h+SaclDefaulted], r12b
0x1400026da  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x1400026de  mov     [rbp+47h+FileHandle], r12
0x1400026e2  movups  xmmword ptr [rbp+47h+var_70+1Ch], xmm0
0x1400026e6  mov     rbx, r9
0x1400026e9  mov     [rbp+47h+FileObject], r12
0x1400026ed  mov     r14, r8
0x1400026f0  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x1400026f4  movups  xmmword ptr [rbp+47h+var_70.Length], xmm0
0x1400026f8  movups  xmmword ptr [rbp+47h+var_30], xmm0
0x1400026fc  call    cs:__imp_RtlInitUnicodeString
0x140002703  nop     dword ptr [rax+rax+00h]
0x140002708  mov     rcx, cs:LuafvDriverData; Filter
0x14000270f  lea     rax, [rbp+47h+DestinationString]
0x140002713  mov     [rsp+110h+DriverContext], r12; DriverContext
0x140002718  lea     edi, [r12+1]
0x14000271d  mov     [rsp+110h+Flags], 100h; Flags
0x140002725  lea     r9, [rbp+47h+FileObject]; FileObject
0x140002729  mov     [rsp+110h+EaLength], r12d; EaLength
0x14000272e  lea     r8, [rbp+47h+FileHandle]; FileHandle
0x140002732  mov     [rsp+110h+EaBuffer], r12; EaBuffer
0x140002737  xorps   xmm0, xmm0
0x14000273a  mov     [rsp+110h+CreateOptions], 4020h; CreateOptions
0x140002742  mov     rdx, rsi; Instance
0x140002745  mov     [rsp+110h+CreateDisposition], edi; CreateDisposition
0x140002749  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x140002751  mov     [rsp+110h+FileAttributes], r12d; FileAttributes
0x140002756  mov     [rbp+47h+var_70.ObjectName], rax
0x14000275a  lea     rax, [rbp+47h+var_30]
0x14000275e  mov     [rsp+110h+AllocationSize], r12; AllocationSize
0x140002763  mov     [rsp+110h+IoStatusBlock], rax; IoStatusBlock
0x140002768  lea     rax, [rbp+47h+var_70]
0x14000276c  mov     [rsp+110h+ObjectAttributes], rax; ObjectAttributes
0x140002771  mov     [rsp+110h+DesiredAccess], 140000h; DesiredAccess
0x140002779  mov     [rbp+47h+var_70.Length], 30h ; '0'
0x140002780  mov     [rbp+47h+var_70.RootDirectory], rbx
0x140002784  mov     [rbp+47h+var_70.Attributes], 240h
0x14000278b  movdqu  xmmword ptr [rbp+47h+var_70.SecurityDescriptor], xmm0
0x140002790  call    cs:__imp_FltCreateFileEx2
0x140002797  nop     dword ptr [rax+rax+00h]
0x14000279c  mov     ebx, eax
0x14000279e  test    eax, eax
0x1400027a0  js      loc_140002890
0x1400027a6  lea     rax, [rbp+47h+LengthNeeded]
0x1400027aa  xor     r9d, r9d; SecurityDescriptor
0x1400027ad  mov     [rsp+110h+ObjectAttributes], rax; LengthNeeded
0x1400027b2  lea     r8d, [r12+8]; SecurityInformation
0x1400027b7  mov     rdx, r14; FileObject
0x1400027ba  mov     [rsp+110h+DesiredAccess], r12d; Length
0x1400027bf  mov     rcx, rsi; Instance
0x1400027c2  call    cs:__imp_FltQuerySecurityObject
0x1400027c9  nop     dword ptr [rax+rax+00h]
0x1400027ce  mov     ebx, eax
0x1400027d0  cmp     eax, 0C0000023h
0x1400027d5  jnz     loc_140002890
0x1400027db  mov     edx, [rbp+47h+LengthNeeded]
0x1400027de  mov     r8b, 4
0x1400027e1  mov     ecx, edi
0x1400027e3  call    LuafvAllocatePool
0x1400027e8  mov     rdi, rax
0x1400027eb  test    rax, rax
0x1400027ee  jnz     short loc_1400027FA
0x1400027f0  mov     ebx, 0C000009Ah
0x1400027f5  jmp     loc_140002890
0x1400027fa  lea     rax, [rbp+47h+LengthNeeded]
0x1400027fe  mov     r9, rdi; SecurityDescriptor
0x140002801  mov     [rsp+110h+ObjectAttributes], rax; LengthNeeded
0x140002806  mov     r8d, 8; SecurityInformation
0x14000280c  mov     eax, [rbp+47h+LengthNeeded]
0x14000280f  mov     rdx, r14; FileObject
0x140002812  mov     rcx, rsi; Instance
0x140002815  mov     [rsp+110h+DesiredAccess], eax; Length
0x140002819  call    cs:__imp_FltQuerySecurityObject
0x140002820  nop     dword ptr [rax+rax+00h]
0x140002825  mov     ebx, eax
0x140002827  test    eax, eax
0x140002829  js      short loc_140002888
0x14000282b  lea     r9, [rbp+47h+SaclDefaulted]; SaclDefaulted
0x14000282f  mov     rcx, rdi; SecurityDescriptor
0x140002832  lea     r8, [rbp+47h+Sacl]; Sacl
0x140002836  lea     rdx, [rbp+47h+SaclPresent]; SaclPresent
0x14000283a  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x140002841  nop     dword ptr [rax+rax+00h]
0x140002846  mov     ebx, eax
0x140002848  test    eax, eax
0x14000284a  js      short loc_140002888
0x14000284c  cmp     [rbp+47h+SaclPresent], r12b
0x140002850  jz      short loc_140002888
0x140002852  mov     rdx, [rbp+47h+FileObject]; FileObject
0x140002856  mov     r9, rdi; SecurityDescriptor
0x140002859  mov     r8d, 8; SecurityInformation
0x14000285f  mov     rcx, rsi; Instance
0x140002862  call    cs:__imp_FltSetSecurityObject
0x140002869  nop     dword ptr [rax+rax+00h]
0x14000286e  mov     ebx, eax
0x140002870  test    eax, eax
0x140002872  js      short loc_140002888
0x140002874  mov     r9, [rbp+47h+arg_28]; PVOID
0x140002878  mov     rdx, r15; CallbackData
0x14000287b  mov     r8, [rbp+47h+Data]; Data
0x14000287f  mov     rcx, [rbp+47h+Sacl]; ResourceSacl
0x140002883  call    LuafvReportAuditVirtualizationEvent
0x140002888  mov     rcx, rdi
0x14000288b  call    LuafvFreePool
0x140002890  mov     rcx, [rbp+47h+FileObject]; Object
0x140002894  test    rcx, rcx
0x140002897  jz      short loc_1400028A5
0x140002899  call    cs:__imp_ObfDereferenceObject
0x1400028a0  nop     dword ptr [rax+rax+00h]
0x1400028a5  mov     rcx, [rbp+47h+FileHandle]; FileHandle
0x1400028a9  test    rcx, rcx
0x1400028ac  jz      short loc_1400028BA
0x1400028ae  call    cs:__imp_FltClose
0x1400028b5  nop     dword ptr [rax+rax+00h]
0x1400028ba  lea     r11, [rsp+110h+var_20]
0x1400028c2  mov     eax, ebx
0x1400028c4  mov     rbx, [r11+30h]
0x1400028c8  mov     rsi, [r11+38h]
0x1400028cc  mov     rsp, r11
0x1400028cf  pop     r15
0x1400028d1  pop     r14
0x1400028d3  pop     r12
0x1400028d5  pop     rdi
0x1400028d6  pop     rbp
0x1400028d7  retn
```
