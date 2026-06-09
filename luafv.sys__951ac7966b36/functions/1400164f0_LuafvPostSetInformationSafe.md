# LuafvPostSetInformationSafe

- ea: `0x1400164f0`
- end: `0x14001665e`
- name: `LuafvPostSetInformationSafe`
- size: `366`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, PCFLT_RELATED_OBJECTS FltObjects, __int64 CompletionContext, FLT_POST_OPERATION_FLAGS Flags)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140001adc`
- `0x1400043c4`
- `0x1400162cc`
- `0x1400164f0`
- `0x14001dd90`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x140016642`
- `FLTMGR!FltReleaseContext` at `0x140016642`
- `FLTMGR!FltSetInformationFile` at `0x1400165ba`
- `FLTMGR!FltSetInformationFile` at `0x140016633`
- `FLTMGR!FltSetInformationFile` at `0x1400165ba`
- `FLTMGR!FltSetInformationFile` at `0x140016633`

## pseudocode

```c
__int64 __fastcall LuafvPostSetInformationSafe(
        PFLT_CALLBACK_DATA Data,
        PCFLT_RELATED_OBJECTS FltObjects,
        __int64 CompletionContext,
        FLT_POST_OPERATION_FLAGS Flags)
{
  int v5; // edi
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  PFLT_IO_PARAMETER_BLOCK v9; // rdx
  int MirrorRenameInformation; // eax
  PVOID v11; // rdi
  struct _FILE_OBJECT *v12; // rdx
  ULONG Length; // [rsp+50h] [rbp+8h] BYREF
  PVOID FileInformation; // [rsp+60h] [rbp+18h] BYREF

  v5 = 0;
  Length = 0;
  Iopb = Data->Iopb;
  switch ( Iopb->Parameters.Create.Options )
  {
    case 0xAu:
LABEL_5:
      v5 = 1;
      LuafvLogVirtualRename(Data, (UNICODE_STRING **)CompletionContext, 1, 0);
      break;
    case 0xDu:
      *(_BYTE *)(CompletionContext + 53) = *(_BYTE *)(CompletionContext + 53) & 0xF7
                                         | (*(_BYTE *)Iopb->Parameters.Create.EaBuffer != 0 ? 8 : 0);
      break;
    case 0x40u:
      *(_BYTE *)(CompletionContext + 53) = *(_BYTE *)(CompletionContext + 53) & 0xF7
                                         | (8 * (*(_BYTE *)Iopb->Parameters.Create.EaBuffer & 1));
      break;
    case 0x41u:
      goto LABEL_5;
    default:
      break;
  }
  if ( (unsigned int)Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( !v5 )
      goto LABEL_22;
    if ( (*(_BYTE *)(CompletionContext + 53) & 0x10) == 0 )
      goto LABEL_19;
    if ( *(_QWORD *)(CompletionContext + 32) )
    {
      v9 = Data->Iopb;
      FileInformation = 0;
      MirrorRenameInformation = LuafvGetMirrorRenameInformation(
                                  CompletionContext,
                                  (__int64)v9->Parameters.Create.EaBuffer,
                                  (char **)&FileInformation,
                                  &Length);
      v11 = FileInformation;
      if ( MirrorRenameInformation >= 0 )
        FltSetInformationFile(
          FltObjects->Instance,
          *(PFILE_OBJECT *)(CompletionContext + 32),
          FileInformation,
          Length,
          Data->Iopb->Parameters.QueryFileInformation.FileInformationClass);
      if ( v11 )
        LuafvFreePool((__int64)v11);
    }
    else
    {
LABEL_22:
      if ( (*(_BYTE *)(CompletionContext + 53) & 0x10) != 0 )
      {
        v12 = *(struct _FILE_OBJECT **)(CompletionContext + 32);
        if ( v12 )
          FltSetInformationFile(
            FltObjects->Instance,
            v12,
            Data->Iopb->Parameters.Create.EaBuffer,
            Data->Iopb->Parameters.Read.Length,
            Data->Iopb->Parameters.QueryFileInformation.FileInformationClass);
      }
    }
  }
LABEL_19:
  FltReleaseContext((PFLT_CONTEXT)CompletionContext);
  return 0;
}

```

## disassembly

```asm
0x1400164f0  mov     [rsp+arg_8], rbx
0x1400164f5  push    rbp
0x1400164f6  push    rsi
0x1400164f7  push    rdi
0x1400164f8  sub     rsp, 30h
0x1400164fc  mov     rbx, r8
0x1400164ff  xor     edi, edi
0x140016501  mov     rsi, rcx
0x140016504  mov     [rsp+48h+Length], edi
0x140016508  mov     rcx, [rcx+10h]
0x14001650c  mov     rbp, rdx
0x14001650f  mov     r8d, [rcx+20h]
0x140016513  sub     r8d, 0Ah
0x140016517  jz      short loc_140016533
0x140016519  sub     r8d, 3
0x14001651d  jz      loc_1400165F0
0x140016523  sub     r8d, 33h ; '3'
0x140016527  jz      loc_1400165D5
0x14001652d  cmp     r8d, 1
0x140016531  jnz     short loc_140016549
0x140016533  mov     edi, 1
0x140016538  xor     r9d, r9d
0x14001653b  mov     r8b, dil
0x14001653e  mov     rdx, rbx
0x140016541  mov     rcx, rsi
0x140016544  call    LuafvLogVirtualRename
0x140016549  call    Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline
0x14001654e  test    eax, eax
0x140016550  jz      loc_14001663F
0x140016556  test    edi, edi
0x140016558  jz      loc_14001660C
0x14001655e  test    byte ptr [rbx+35h], 10h
0x140016562  jz      loc_14001663F
0x140016568  cmp     qword ptr [rbx+20h], 0
0x14001656d  jz      loc_14001660C
0x140016573  mov     rdx, [rsi+10h]
0x140016577  lea     r9, [rsp+48h+Length]
0x14001657c  lea     r8, [rsp+48h+FileInformation]
0x140016581  mov     [rsp+48h+FileInformation], 0
0x14001658a  mov     rcx, rbx
0x14001658d  mov     rdx, [rdx+38h]
0x140016591  call    LuafvGetMirrorRenameInformation
0x140016596  mov     rdi, [rsp+48h+FileInformation]
0x14001659b  test    eax, eax
0x14001659d  js      short loc_1400165C6
0x14001659f  mov     rax, [rsi+10h]
0x1400165a3  mov     r8, rdi; FileInformation
0x1400165a6  mov     r9d, [rsp+48h+Length]; Length
0x1400165ab  mov     rcx, [rbp+18h]; Instance
0x1400165af  mov     edx, [rax+20h]
0x1400165b2  mov     [rsp+48h+FileInformationClass], edx; FileInformationClass
0x1400165b6  mov     rdx, [rbx+20h]; FileObject
0x1400165ba  call    cs:__imp_FltSetInformationFile
0x1400165c1  nop     dword ptr [rax+rax+00h]
0x1400165c6  test    rdi, rdi
0x1400165c9  jz      short loc_14001663F
0x1400165cb  mov     rcx, rdi
0x1400165ce  call    LuafvFreePool
0x1400165d3  jmp     short loc_14001663F
0x1400165d5  mov     rax, [rcx+38h]
0x1400165d9  mov     cl, [rax]
0x1400165db  mov     al, [rbx+35h]
0x1400165de  and     cl, 1
0x1400165e1  shl     cl, 3
0x1400165e4  and     al, 0F7h
0x1400165e6  or      cl, al
0x1400165e8  mov     [rbx+35h], cl
0x1400165eb  jmp     loc_140016549
0x1400165f0  mov     rax, [rcx+38h]
0x1400165f4  mov     cl, [rax]
0x1400165f6  mov     al, [rbx+35h]
0x1400165f9  neg     cl
0x1400165fb  sbb     dl, dl
0x1400165fd  and     al, 0F7h
0x1400165ff  and     dl, 8
0x140016602  or      dl, al
0x140016604  mov     [rbx+35h], dl
0x140016607  jmp     loc_140016549
0x14001660c  test    byte ptr [rbx+35h], 10h
0x140016610  jz      short loc_14001663F
0x140016612  mov     rdx, [rbx+20h]; FileObject
0x140016616  test    rdx, rdx
0x140016619  jz      short loc_14001663F
0x14001661b  mov     r8, [rsi+10h]
0x14001661f  mov     rcx, [rbp+18h]; Instance
0x140016623  mov     eax, [r8+20h]
0x140016627  mov     r9d, [r8+18h]; Length
0x14001662b  mov     r8, [r8+38h]; FileInformation
0x14001662f  mov     [rsp+48h+FileInformationClass], eax; FileInformationClass
0x140016633  call    cs:__imp_FltSetInformationFile
0x14001663a  nop     dword ptr [rax+rax+00h]
0x14001663f  mov     rcx, rbx; Context
0x140016642  call    cs:__imp_FltReleaseContext
0x140016649  nop     dword ptr [rax+rax+00h]
0x14001664e  mov     rbx, [rsp+48h+arg_8]
0x140016653  xor     eax, eax
0x140016655  add     rsp, 30h
0x140016659  pop     rdi
0x14001665a  pop     rsi
0x14001665b  pop     rbp
0x14001665c  retn
```
