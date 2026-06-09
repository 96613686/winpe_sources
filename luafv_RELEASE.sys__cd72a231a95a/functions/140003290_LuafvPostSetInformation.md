# LuafvPostSetInformation

- ea: `0x140003290`
- end: `0x1400033ca`
- name: `LuafvPostSetInformation`
- size: `314`
- prototype: `__int64 __fastcall(struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, __int64, FLT_POST_OPERATION_FLAGS)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001adc`
- `0x140003290`
- `0x1400045f4`
- `0x14001dd40`

## import_xrefs

- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x1400032d2`
- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x1400032d2`
- `FLTMGR!FltReleaseContext` at `0x1400033ab`
- `FLTMGR!FltReleaseContext` at `0x1400033ab`
- `FLTMGR!FltSetInformationFile` at `0x14000335a`
- `FLTMGR!FltSetInformationFile` at `0x14000339c`
- `FLTMGR!FltSetInformationFile` at `0x14000335a`
- `FLTMGR!FltSetInformationFile` at `0x14000339c`

## pseudocode

```c
__int64 __fastcall LuafvPostSetInformation(
        struct _FLT_CALLBACK_DATA *a1,
        const struct _FLT_RELATED_OBJECTS *a2,
        __int64 a3,
        FLT_POST_OPERATION_FLAGS a4)
{
  bool v4; // sf
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  FILE_INFORMATION_CLASS FileInformationClass; // ecx
  PVOID EaBuffer; // rdx
  ULONG Length; // [rsp+30h] [rbp-18h] BYREF
  PVOID FileInformation[2]; // [rsp+38h] [rbp-10h] BYREF
  unsigned int RetPostOperationStatus; // [rsp+50h] [rbp+8h] BYREF

  v4 = a1->IoStatus.Status < 0;
  RetPostOperationStatus = 0;
  Length = 0;
  if ( !v4
    && FltDoCompletionProcessingWhenSafe(
         a1,
         a2,
         (PVOID)a3,
         a4,
         LuafvPostSetInformationSafe,
         (PFLT_POSTOP_CALLBACK_STATUS)&RetPostOperationStatus) )
  {
    return RetPostOperationStatus;
  }
  if ( (unsigned int)Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline() )
  {
    Iopb = a1->Iopb;
    FileInformationClass = Iopb->Parameters.QueryFileInformation.FileInformationClass;
    if ( FileInformationClass != FileRenameInformation && FileInformationClass != 65 )
      goto LABEL_13;
    if ( (*(_BYTE *)(a3 + 53) & 0x10) != 0 )
    {
      if ( *(_QWORD *)(a3 + 32) )
      {
        EaBuffer = Iopb->Parameters.Create.EaBuffer;
        FileInformation[0] = 0;
        if ( (int)LuafvGetMirrorRenameInformation(a3, EaBuffer, FileInformation, &Length) >= 0 )
          FltSetInformationFile(
            a2->Instance,
            *(PFILE_OBJECT *)(a3 + 32),
            FileInformation[0],
            Length,
            a1->Iopb->Parameters.QueryFileInformation.FileInformationClass);
        if ( FileInformation[0] )
          LuafvFreePool(FileInformation[0]);
        goto LABEL_16;
      }
LABEL_13:
      if ( (*(_BYTE *)(a3 + 53) & 0x10) != 0 && *(_QWORD *)(a3 + 32) )
        FltSetInformationFile(
          a2->Instance,
          *(PFILE_OBJECT *)(a3 + 32),
          Iopb->Parameters.Create.EaBuffer,
          Iopb->Parameters.Read.Length,
          FileInformationClass);
    }
  }
LABEL_16:
  FltReleaseContext((PFLT_CONTEXT)a3);
  return 0;
}

```

## disassembly

```asm
0x140003290  mov     rax, rsp
0x140003293  mov     [rax+10h], rbx
0x140003297  mov     [rax+18h], rbp
0x14000329b  push    rsi
0x14000329c  sub     rsp, 40h
0x1400032a0  cmp     dword ptr [rcx+18h], 0
0x1400032a4  mov     rbx, r8
0x1400032a7  mov     rbp, rdx
0x1400032aa  mov     dword ptr [rax+8], 0
0x1400032b1  mov     rsi, rcx
0x1400032b4  mov     dword ptr [rax-18h], 0
0x1400032bb  jl      short loc_1400032EB
0x1400032bd  lea     rax, [rax+8]
0x1400032c1  mov     [rsp+48h+RetPostOperationStatus], rax; RetPostOperationStatus
0x1400032c6  lea     rax, LuafvPostSetInformationSafe
0x1400032cd  mov     [rsp+48h+SafePostCallback], rax; SafePostCallback
0x1400032d2  call    cs:__imp_FltDoCompletionProcessingWhenSafe
0x1400032d9  nop     dword ptr [rax+rax+00h]
0x1400032de  test    al, al
0x1400032e0  jz      short loc_1400032EB
0x1400032e2  mov     eax, [rsp+48h+arg_0]
0x1400032e6  jmp     loc_1400033B9
0x1400032eb  call    Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline
0x1400032f0  test    eax, eax
0x1400032f2  jz      loc_1400033A8
0x1400032f8  mov     rdx, [rsi+10h]
0x1400032fc  mov     ecx, [rdx+20h]
0x1400032ff  cmp     ecx, 0Ah
0x140003302  jz      short loc_140003309
0x140003304  cmp     ecx, 41h ; 'A'
0x140003307  jnz     short loc_14000337A
0x140003309  test    byte ptr [rbx+35h], 10h
0x14000330d  jz      loc_1400033A8
0x140003313  cmp     qword ptr [rbx+20h], 0
0x140003318  jz      short loc_14000337A
0x14000331a  mov     rdx, [rdx+38h]
0x14000331e  lea     r9, [rsp+48h+Length]
0x140003323  lea     r8, [rsp+48h+FileInformation]
0x140003328  mov     [rsp+48h+FileInformation], 0
0x140003331  mov     rcx, rbx
0x140003334  call    LuafvGetMirrorRenameInformation
0x140003339  test    eax, eax
0x14000333b  js      short loc_140003366
0x14000333d  mov     rax, [rsi+10h]
0x140003341  mov     r9d, [rsp+48h+Length]; Length
0x140003346  mov     r8, [rsp+48h+FileInformation]; FileInformation
0x14000334b  mov     rcx, [rbp+18h]; Instance
0x14000334f  mov     edx, [rax+20h]
0x140003352  mov     dword ptr [rsp+48h+SafePostCallback], edx; FileInformationClass
0x140003356  mov     rdx, [rbx+20h]; FileObject
0x14000335a  call    cs:__imp_FltSetInformationFile
0x140003361  nop     dword ptr [rax+rax+00h]
0x140003366  cmp     [rsp+48h+FileInformation], 0
0x14000336c  jz      short loc_1400033A8
0x14000336e  mov     rcx, [rsp+48h+FileInformation]
0x140003373  call    LuafvFreePool
0x140003378  jmp     short loc_1400033A8
0x14000337a  test    byte ptr [rbx+35h], 10h
0x14000337e  jz      short loc_1400033A8
0x140003380  mov     rax, [rbx+20h]
0x140003384  test    rax, rax
0x140003387  jz      short loc_1400033A8
0x140003389  mov     r9d, [rdx+18h]; Length
0x14000338d  mov     r8, [rdx+38h]; FileInformation
0x140003391  mov     rdx, rax; FileObject
0x140003394  mov     dword ptr [rsp+48h+SafePostCallback], ecx; FileInformationClass
0x140003398  mov     rcx, [rbp+18h]; Instance
0x14000339c  call    cs:__imp_FltSetInformationFile
0x1400033a3  nop     dword ptr [rax+rax+00h]
0x1400033a8  mov     rcx, rbx; Context
0x1400033ab  call    cs:__imp_FltReleaseContext
0x1400033b2  nop     dword ptr [rax+rax+00h]
0x1400033b7  xor     eax, eax
0x1400033b9  mov     rbx, [rsp+48h+arg_8]
0x1400033be  mov     rbp, [rsp+48h+arg_10]
0x1400033c3  add     rsp, 40h
0x1400033c7  pop     rsi
0x1400033c8  retn
```
