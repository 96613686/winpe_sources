# BuildNormalizedPathFromFileName

- ea: `0x1400035f0`
- end: `0x1400039af`
- name: `BuildNormalizedPathFromFileName`
- size: `959`
- prototype: `__int64 __fastcall(__int64, __int64, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140003b6c`

## callees

- `0x1400035f0`
- `0x14001b650`
- `0x14001dd40`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400036ea`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140003765`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400038d9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140003975`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400036ea`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140003765`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400038d9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140003975`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400036d3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003734`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400038c2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003962`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400036d3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003734`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400038c2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003962`
- `ntoskrnl!ObfDereferenceObject` at `0x140003877`
- `ntoskrnl!ObfDereferenceObject` at `0x140003877`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003942`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003985`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003942`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003985`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140003855`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140003855`
- `FLTMGR!FltClose` at `0x140003867`
- `FLTMGR!FltClose` at `0x140003867`
- `FLTMGR!FltCreateFileEx2` at `0x1400037f4`
- `FLTMGR!FltCreateFileEx2` at `0x1400037f4`

## pseudocode

```c
__int64 __fastcall BuildNormalizedPathFromFileName(__int64 a1, __int64 a2, struct _UNICODE_STRING *a3)
{
  __int64 v5; // rax
  USHORT v7; // r9
  __int64 v8; // r8
  USHORT v9; // dx
  unsigned __int16 v10; // cx
  bool v11; // cf
  USHORT v12; // r14
  __int16 v13; // dx
  __int64 v14; // rdx
  __int64 v15; // rax
  const UNICODE_STRING *v17; // rdx
  __int64 v18; // rax
  struct _FLT_INSTANCE *v19; // rdx
  __int64 v20; // r8
  USHORT v21; // ax
  __int64 v22; // rax
  NTSTATUS FileNameInformationUnsafe; // ebx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 Pool; // rax
  UNICODE_STRING *p_Name; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-39h] BYREF
  UNICODE_STRING Source; // [rsp+90h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-9h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+120h] [rbp+67h] BYREF
  PFILE_OBJECT FileObject; // [rsp+130h] [rbp+77h] BYREF
  void *FileHandle; // [rsp+138h] [rbp+7Fh] BYREF

  FileHandle = 0;
  *(_OWORD *)&ObjectAttributes.ObjectName = 0;
  FileObject = 0;
  DestinationString = 0;
  a3->Buffer = 0;
  *(_DWORD *)&a3->Length = 0;
  v5 = *(_QWORD *)(a1 + 32);
  FileNameInformation = 0;
  v7 = 0;
  *(_OWORD *)&ObjectAttributes.Length = 0;
  v8 = 0;
  v9 = 0;
  *(_OWORD *)(&ObjectAttributes.Attributes + 1) = 0;
  IoStatusBlock = 0;
  v10 = *(_WORD *)(v5 + 88);
  if ( v10 )
  {
    while ( 1 )
    {
      if ( *(_WORD *)(*(_QWORD *)(v5 + 96) + 2 * ((unsigned __int64)v9 >> 1)) == 92 )
      {
        LOWORD(v8) = v8 + 1;
        if ( (_WORD)v8 == 3 )
          break;
      }
      v9 += 2;
      if ( v9 >= v10 )
        goto LABEL_7;
    }
    v7 = v9;
  }
LABEL_7:
  v11 = (unsigned __int16)v8 < 3u;
  v12 = *(_WORD *)(v5 + 88);
  LOBYTE(v8) = 2;
  if ( !v11 )
    v12 = v7;
  v13 = *(_WORD *)(*(_QWORD *)(a2 + 24) + 56LL);
  if ( v12 )
  {
    DestinationString.MaximumLength = v13 + v12 + 2;
    DestinationString.Buffer = (PWSTR)LuafvAllocatePool(1, DestinationString.MaximumLength, v8);
    if ( !DestinationString.Buffer )
      return 3221225626LL;
    v17 = (const UNICODE_STRING *)(*(_QWORD *)(a2 + 24) + 56LL);
    DestinationString.Length = 0;
    RtlCopyUnicodeString(&DestinationString, v17);
    v18 = *(_QWORD *)(a1 + 32);
    Source = 0;
    Source.Buffer = *(PWSTR *)(v18 + 96);
    Source.Length = v12;
    Source.MaximumLength = v12;
    RtlAppendUnicodeStringToString(&DestinationString, &Source);
    v19 = *(struct _FLT_INSTANCE **)(a1 + 24);
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( FltCreateFileEx2(
           LuafvDriverData,
           v19,
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
      FileHandle = 0;
      LOBYTE(v20) = 2;
      FileObject = 0;
      if ( FileNameInformationUnsafe >= 0 )
      {
        v24 = *(_QWORD *)(a1 + 32);
        Source = 0;
        Source.Buffer = (PWSTR)(*(_QWORD *)(v24 + 96) + 2 * ((unsigned __int64)v12 >> 1));
        Source.Length = *(_WORD *)(v24 + 88) - v12;
        Source.MaximumLength = Source.Length;
        v25 = (unsigned __int16)(FileNameInformation->Name.Length + Source.Length + 2);
        a3->MaximumLength = v25;
        Pool = LuafvAllocatePool(1, v25, v20);
        a3->Buffer = (PWSTR)Pool;
        if ( !Pool )
        {
          FltReleaseFileNameInformation(FileNameInformation);
          goto LABEL_17;
        }
        p_Name = &FileNameInformation->Name;
        a3->Length = 0;
        RtlCopyUnicodeString(a3, p_Name);
        RtlAppendUnicodeStringToString(a3, &Source);
        FltReleaseFileNameInformation(FileNameInformation);
LABEL_24:
        LuafvFreePool(DestinationString.Buffer);
        return 0;
      }
      v21 = *(_WORD *)(*(_QWORD *)(a1 + 32) + 88LL) + 2 + *(_WORD *)(*(_QWORD *)(a2 + 24) + 56LL);
    }
    else
    {
      LOBYTE(v20) = 2;
      v21 = *(_WORD *)(*(_QWORD *)(a1 + 32) + 88LL) + 2 + *(_WORD *)(*(_QWORD *)(a2 + 24) + 56LL);
    }
    a3->MaximumLength = v21;
    v22 = LuafvAllocatePool(1, v21, v20);
    a3->Buffer = (PWSTR)v22;
    if ( !v22 )
    {
LABEL_17:
      LuafvFreePool(DestinationString.Buffer);
      return 3221225626LL;
    }
    a3->Length = 0;
    RtlCopyUnicodeString(a3, (PCUNICODE_STRING)(*(_QWORD *)(a2 + 24) + 56LL));
    RtlAppendUnicodeStringToString(a3, (PCUNICODE_STRING)(*(_QWORD *)(a1 + 32) + 88LL));
    goto LABEL_24;
  }
  v14 = (unsigned __int16)(v13 + 2 + v10);
  a3->MaximumLength = v14;
  v15 = LuafvAllocatePool(1, v14, v8);
  a3->Buffer = (PWSTR)v15;
  if ( !v15 )
    return 3221225626LL;
  a3->Length = 0;
  RtlCopyUnicodeString(a3, (PCUNICODE_STRING)(*(_QWORD *)(a2 + 24) + 56LL));
  RtlAppendUnicodeStringToString(a3, (PCUNICODE_STRING)(*(_QWORD *)(a1 + 32) + 88LL));
  return 0;
}

```

## disassembly

```asm
0x1400035f0  push    rbp
0x1400035f2  push    rbx
0x1400035f3  push    rsi
0x1400035f4  push    rdi
0x1400035f5  push    r12
0x1400035f7  push    r14
0x1400035f9  push    r15
0x1400035fb  lea     rbp, [rsp-27h]
0x140003600  sub     rsp, 0E0h
0x140003607  xor     r12d, r12d
0x14000360a  xorps   xmm0, xmm0
0x14000360d  mov     rdi, r8
0x140003610  mov     [rbp+57h+FileHandle], r12
0x140003614  movups  xmmword ptr [rbp+57h+var_60.ObjectName], xmm0
0x140003618  xor     eax, eax
0x14000361a  mov     [rbp+57h+FileObject], r12
0x14000361e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140003622  mov     [rdi+8], r12
0x140003626  lea     ebx, [r12+1]
0x14000362b  mov     [rdi], r12d
0x14000362e  mov     rsi, rcx
0x140003631  mov     rax, [rcx+20h]
0x140003635  mov     r15, rdx
0x140003638  mov     [rbp+57h+FileNameInformation], r12
0x14000363c  mov     r9d, r12d
0x14000363f  movups  xmmword ptr [rbp+57h+var_60.Length], xmm0
0x140003643  mov     r8d, r12d
0x140003646  mov     edx, r12d
0x140003649  movups  xmmword ptr [rbp+57h+var_60+1Ch], xmm0
0x14000364d  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x140003651  movzx   ecx, word ptr [rax+58h]
0x140003655  mov     r10, [rax+60h]
0x140003659  cmp     r12w, cx
0x14000365d  jnb     short loc_140003687
0x14000365f  movzx   eax, dx
0x140003662  shr     rax, 1
0x140003665  cmp     word ptr [r10+rax*2], 5Ch ; '\'
0x14000366b  jnz     short loc_140003678
0x14000366d  add     r8w, bx
0x140003671  cmp     r8w, 3
0x140003676  jz      short loc_140003683
0x140003678  add     dx, 2
0x14000367c  cmp     dx, cx
0x14000367f  jb      short loc_14000365F
0x140003681  jmp     short loc_140003687
0x140003683  movzx   r9d, dx
0x140003687  mov     rax, [r15+18h]
0x14000368b  cmp     r8w, 3
0x140003690  movzx   r14d, cx
0x140003694  mov     r8b, 2
0x140003697  cmovnb  r14w, r9w
0x14000369c  movzx   edx, word ptr [rax+38h]
0x1400036a0  test    r14w, r14w
0x1400036a4  jnz     short loc_1400036FB
0x1400036a6  add     dx, 2
0x1400036aa  add     cx, dx
0x1400036ad  movzx   edx, cx
0x1400036b0  mov     ecx, ebx
0x1400036b2  mov     [rdi+2], dx
0x1400036b6  call    LuafvAllocatePool
0x1400036bb  mov     [rdi+8], rax
0x1400036bf  test    rax, rax
0x1400036c2  jz      short loc_140003719
0x1400036c4  mov     [rdi], r12w
0x1400036c8  mov     rcx, rdi; DestinationString
0x1400036cb  mov     rdx, [r15+18h]
0x1400036cf  add     rdx, 38h ; '8'; SourceString
0x1400036d3  call    cs:__imp_RtlCopyUnicodeString
0x1400036da  nop     dword ptr [rax+rax+00h]
0x1400036df  mov     rdx, [rsi+20h]
0x1400036e3  mov     rcx, rdi; Destination
0x1400036e6  add     rdx, 58h ; 'X'; Source
0x1400036ea  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400036f1  nop     dword ptr [rax+rax+00h]
0x1400036f6  jmp     loc_14000399A
0x1400036fb  lea     eax, [r14+2]
0x1400036ff  mov     ecx, ebx
0x140003701  add     ax, dx
0x140003704  movzx   edx, ax
0x140003707  mov     [rbp+57h+DestinationString.MaximumLength], dx
0x14000370b  call    LuafvAllocatePool
0x140003710  mov     [rbp+57h+DestinationString.Buffer], rax
0x140003714  test    rax, rax
0x140003717  jnz     short loc_140003723
0x140003719  mov     eax, 0C000009Ah
0x14000371e  jmp     loc_14000399C
0x140003723  mov     rdx, [r15+18h]
0x140003727  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000372b  add     rdx, 38h ; '8'; SourceString
0x14000372f  mov     [rbp+57h+DestinationString.Length], r12w
0x140003734  call    cs:__imp_RtlCopyUnicodeString
0x14000373b  nop     dword ptr [rax+rax+00h]
0x140003740  mov     rax, [rsi+20h]
0x140003744  lea     rdx, [rbp+57h+Source]; Source
0x140003748  xorps   xmm0, xmm0
0x14000374b  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x14000374f  mov     rcx, [rax+60h]
0x140003753  mov     [rbp+57h+Source.Buffer], rcx
0x140003757  lea     rcx, [rbp+57h+DestinationString]; Destination
0x14000375b  mov     [rbp+57h+Source.Length], r14w
0x140003760  mov     [rbp+57h+Source.MaximumLength], r14w
0x140003765  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000376c  nop     dword ptr [rax+rax+00h]
0x140003771  mov     rdx, [rsi+18h]; Instance
0x140003775  lea     rax, [rbp+57h+DestinationString]
0x140003779  mov     rcx, cs:LuafvDriverData; Filter
0x140003780  lea     r9, [rbp+57h+FileObject]; FileObject
0x140003784  mov     [rsp+110h+DriverContext], r12; DriverContext
0x140003789  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x14000378d  mov     [rsp+110h+Flags], ebx; Flags
0x140003791  xorps   xmm0, xmm0
0x140003794  mov     [rsp+110h+EaLength], r12d; EaLength
0x140003799  mov     [rsp+110h+EaBuffer], r12; EaBuffer
0x14000379e  mov     [rsp+110h+CreateOptions], 21h ; '!'; CreateOptions
0x1400037a6  mov     [rsp+110h+CreateDisposition], ebx; CreateDisposition
0x1400037aa  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x1400037b2  mov     [rsp+110h+FileAttributes], 10h; FileAttributes
0x1400037ba  mov     [rbp+57h+var_60.ObjectName], rax
0x1400037be  lea     rax, [rbp+57h+var_70]
0x1400037c2  mov     [rsp+110h+AllocationSize], r12; AllocationSize
0x1400037c7  mov     [rsp+110h+IoStatusBlock], rax; IoStatusBlock
0x1400037cc  lea     rax, [rbp+57h+var_60]
0x1400037d0  mov     [rsp+110h+ObjectAttributes], rax; ObjectAttributes
0x1400037d5  mov     [rsp+110h+DesiredAccess], 100001h; DesiredAccess
0x1400037dd  mov     [rbp+57h+var_60.Length], 30h ; '0'
0x1400037e4  mov     [rbp+57h+var_60.RootDirectory], r12
0x1400037e8  mov     [rbp+57h+var_60.Attributes], 240h
0x1400037ef  movdqu  xmmword ptr [rbp+57h+var_60.SecurityDescriptor], xmm0
0x1400037f4  call    cs:__imp_FltCreateFileEx2
0x1400037fb  nop     dword ptr [rax+rax+00h]
0x140003800  test    eax, eax
0x140003802  jns     short loc_140003843
0x140003804  mov     rax, [rsi+20h]
0x140003808  mov     r8b, 2
0x14000380b  mov     rdx, [r15+18h]
0x14000380f  movzx   ecx, word ptr [rax+58h]
0x140003813  movzx   eax, word ptr [rdx+38h]
0x140003817  add     cx, 2
0x14000381b  add     ax, cx
0x14000381e  mov     ecx, ebx
0x140003820  movzx   edx, ax
0x140003823  mov     [rdi+2], dx
0x140003827  call    LuafvAllocatePool
0x14000382c  mov     [rdi+8], rax
0x140003830  test    rax, rax
0x140003833  jnz     short loc_1400038B3
0x140003835  mov     rcx, [rbp+57h+DestinationString.Buffer]
0x140003839  call    LuafvFreePool
0x14000383e  jmp     loc_140003719
0x140003843  mov     rdx, [rsi+18h]; Instance
0x140003847  lea     r9, [rbp+57h+FileNameInformation]; FileNameInformation
0x14000384b  mov     rcx, [rbp+57h+FileObject]; FileObject
0x14000384f  mov     r8d, 101h; NameOptions
0x140003855  call    cs:__imp_FltGetFileNameInformationUnsafe
0x14000385c  nop     dword ptr [rax+rax+00h]
0x140003861  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140003865  mov     ebx, eax
0x140003867  call    cs:__imp_FltClose
0x14000386e  nop     dword ptr [rax+rax+00h]
0x140003873  mov     rcx, [rbp+57h+FileObject]; Object
0x140003877  call    cs:__imp_ObfDereferenceObject
0x14000387e  nop     dword ptr [rax+rax+00h]
0x140003883  mov     [rbp+57h+FileHandle], r12
0x140003887  mov     r8b, 2
0x14000388a  mov     [rbp+57h+FileObject], r12
0x14000388e  test    ebx, ebx
0x140003890  jns     short loc_1400038EA
0x140003892  mov     rax, [rsi+20h]
0x140003896  mov     rdx, [r15+18h]
0x14000389a  movzx   ecx, word ptr [rax+58h]
0x14000389e  movzx   eax, word ptr [rdx+38h]
0x1400038a2  add     cx, 2
0x1400038a6  add     ax, cx
0x1400038a9  mov     ecx, 1
0x1400038ae  jmp     loc_140003820
0x1400038b3  mov     [rdi], r12w
0x1400038b7  mov     rcx, rdi; DestinationString
0x1400038ba  mov     rdx, [r15+18h]
0x1400038be  add     rdx, 38h ; '8'; SourceString
0x1400038c2  call    cs:__imp_RtlCopyUnicodeString
0x1400038c9  nop     dword ptr [rax+rax+00h]
0x1400038ce  mov     rdx, [rsi+20h]
0x1400038d2  mov     rcx, rdi; Destination
0x1400038d5  add     rdx, 58h ; 'X'; Source
0x1400038d9  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400038e0  nop     dword ptr [rax+rax+00h]
0x1400038e5  jmp     loc_140003991
0x1400038ea  mov     rdx, [rsi+20h]
0x1400038ee  xorps   xmm0, xmm0
0x1400038f1  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x1400038f5  movzx   ecx, r14w
0x1400038f9  shr     rcx, 1
0x1400038fc  mov     rax, [rdx+60h]
0x140003900  lea     rcx, [rax+rcx*2]
0x140003904  mov     rax, [rbp+57h+FileNameInformation]
0x140003908  mov     [rbp+57h+Source.Buffer], rcx
0x14000390c  movzx   ecx, word ptr [rdx+58h]
0x140003910  sub     cx, r14w
0x140003914  mov     [rbp+57h+Source.Length], cx
0x140003918  mov     [rbp+57h+Source.MaximumLength], cx
0x14000391c  add     cx, 2
0x140003920  add     cx, [rax+8]
0x140003924  movzx   edx, cx
0x140003927  mov     ecx, 1
0x14000392c  mov     [rdi+2], dx
0x140003930  call    LuafvAllocatePool
0x140003935  mov     [rdi+8], rax
0x140003939  test    rax, rax
0x14000393c  jnz     short loc_140003953
0x14000393e  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140003942  call    cs:__imp_FltReleaseFileNameInformation
0x140003949  nop     dword ptr [rax+rax+00h]
0x14000394e  jmp     loc_140003835
0x140003953  mov     rdx, [rbp+57h+FileNameInformation]
0x140003957  mov     rcx, rdi; DestinationString
0x14000395a  add     rdx, 8; SourceString
0x14000395e  mov     [rdi], r12w
0x140003962  call    cs:__imp_RtlCopyUnicodeString
0x140003969  nop     dword ptr [rax+rax+00h]
0x14000396e  lea     rdx, [rbp+57h+Source]; Source
0x140003972  mov     rcx, rdi; Destination
0x140003975  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000397c  nop     dword ptr [rax+rax+00h]
0x140003981  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140003985  call    cs:__imp_FltReleaseFileNameInformation
0x14000398c  nop     dword ptr [rax+rax+00h]
0x140003991  mov     rcx, [rbp+57h+DestinationString.Buffer]
0x140003995  call    LuafvFreePool
0x14000399a  xor     eax, eax
0x14000399c  add     rsp, 0E0h
0x1400039a3  pop     r15
0x1400039a5  pop     r14
0x1400039a7  pop     r12
0x1400039a9  pop     rdi
0x1400039aa  pop     rsi
0x1400039ab  pop     rbx
0x1400039ac  pop     rbp
0x1400039ad  retn
```
