# LuafvPostSetInformation

- ea: `0x140003060`
- end: `0x14000319a`
- name: `LuafvPostSetInformation`
- size: `314`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001adc`
- `0x140003060`
- `0x1400043c4`
- `0x14001dd90`

## import_xrefs

- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x1400030a2`
- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x1400030a2`
- `FLTMGR!FltReleaseContext` at `0x14000317b`
- `FLTMGR!FltReleaseContext` at `0x14000317b`
- `FLTMGR!FltSetInformationFile` at `0x14000312a`
- `FLTMGR!FltSetInformationFile` at `0x14000316c`
- `FLTMGR!FltSetInformationFile` at `0x14000312a`
- `FLTMGR!FltSetInformationFile` at `0x14000316c`

## pseudocode

```c
__int64 __fastcall LuafvPostSetInformation(
        struct _FLT_CALLBACK_DATA *a1,
        const struct _FLT_RELATED_OBJECTS *a2,
        __int64 a3,
        __int64 a4)
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
  if ( (unsigned int)Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline(a1, a2, a3, a4) )
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
          LuafvFreePool((__int64)FileInformation[0]);
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
0x140003060  mov     rax, rsp
0x140003063  mov     [rax+10h], rbx
0x140003067  mov     [rax+18h], rbp
0x14000306b  push    rsi
0x14000306c  sub     rsp, 40h
0x140003070  cmp     dword ptr [rcx+18h], 0
0x140003074  mov     rbx, r8
0x140003077  mov     rbp, rdx
0x14000307a  mov     dword ptr [rax+8], 0
0x140003081  mov     rsi, rcx
0x140003084  mov     dword ptr [rax-18h], 0
0x14000308b  jl      short loc_1400030BB
0x14000308d  lea     rax, [rax+8]
0x140003091  mov     [rsp+48h+RetPostOperationStatus], rax; RetPostOperationStatus
0x140003096  lea     rax, LuafvPostSetInformationSafe
0x14000309d  mov     [rsp+48h+SafePostCallback], rax; SafePostCallback
0x1400030a2  call    cs:__imp_FltDoCompletionProcessingWhenSafe
0x1400030a9  nop     dword ptr [rax+rax+00h]
0x1400030ae  test    al, al
0x1400030b0  jz      short loc_1400030BB
0x1400030b2  mov     eax, [rsp+48h+arg_0]
0x1400030b6  jmp     loc_140003189
0x1400030bb  call    Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline
0x1400030c0  test    eax, eax
0x1400030c2  jz      loc_140003178
0x1400030c8  mov     rdx, [rsi+10h]
0x1400030cc  mov     ecx, [rdx+20h]
0x1400030cf  cmp     ecx, 0Ah
0x1400030d2  jz      short loc_1400030D9
0x1400030d4  cmp     ecx, 41h ; 'A'
0x1400030d7  jnz     short loc_14000314A
0x1400030d9  test    byte ptr [rbx+35h], 10h
0x1400030dd  jz      loc_140003178
0x1400030e3  cmp     qword ptr [rbx+20h], 0
0x1400030e8  jz      short loc_14000314A
0x1400030ea  mov     rdx, [rdx+38h]
0x1400030ee  lea     r9, [rsp+48h+Length]
0x1400030f3  lea     r8, [rsp+48h+FileInformation]
0x1400030f8  mov     [rsp+48h+FileInformation], 0
0x140003101  mov     rcx, rbx
0x140003104  call    LuafvGetMirrorRenameInformation
0x140003109  test    eax, eax
0x14000310b  js      short loc_140003136
0x14000310d  mov     rax, [rsi+10h]
0x140003111  mov     r9d, [rsp+48h+Length]; Length
0x140003116  mov     r8, [rsp+48h+FileInformation]; FileInformation
0x14000311b  mov     rcx, [rbp+18h]; Instance
0x14000311f  mov     edx, [rax+20h]
0x140003122  mov     dword ptr [rsp+48h+SafePostCallback], edx; FileInformationClass
0x140003126  mov     rdx, [rbx+20h]; FileObject
0x14000312a  call    cs:__imp_FltSetInformationFile
0x140003131  nop     dword ptr [rax+rax+00h]
0x140003136  cmp     [rsp+48h+FileInformation], 0
0x14000313c  jz      short loc_140003178
0x14000313e  mov     rcx, [rsp+48h+FileInformation]
0x140003143  call    LuafvFreePool
0x140003148  jmp     short loc_140003178
0x14000314a  test    byte ptr [rbx+35h], 10h
0x14000314e  jz      short loc_140003178
0x140003150  mov     rax, [rbx+20h]
0x140003154  test    rax, rax
0x140003157  jz      short loc_140003178
0x140003159  mov     r9d, [rdx+18h]; Length
0x14000315d  mov     r8, [rdx+38h]; FileInformation
0x140003161  mov     rdx, rax; FileObject
0x140003164  mov     dword ptr [rsp+48h+SafePostCallback], ecx; FileInformationClass
0x140003168  mov     rcx, [rbp+18h]; Instance
0x14000316c  call    cs:__imp_FltSetInformationFile
0x140003173  nop     dword ptr [rax+rax+00h]
0x140003178  mov     rcx, rbx; Context
0x14000317b  call    cs:__imp_FltReleaseContext
0x140003182  nop     dword ptr [rax+rax+00h]
0x140003187  xor     eax, eax
0x140003189  mov     rbx, [rsp+48h+arg_8]
0x14000318e  mov     rbp, [rsp+48h+arg_10]
0x140003193  add     rsp, 40h
0x140003197  pop     rsi
0x140003198  retn
```
