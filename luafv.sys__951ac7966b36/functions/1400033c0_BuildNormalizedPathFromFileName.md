# BuildNormalizedPathFromFileName

- ea: `0x1400033c0`
- end: `0x14000377f`
- name: `BuildNormalizedPathFromFileName`
- size: `959`
- prototype: `__int64 __fastcall(__int64, __int64, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000393c`

## callees

- `0x1400033c0`
- `0x14001b6a0`
- `0x14001dd90`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400034ba`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140003535`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400036a9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140003745`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400034ba`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140003535`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400036a9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140003745`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400034a3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003504`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003692`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003732`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400034a3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003504`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003692`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003732`
- `ntoskrnl!ObfDereferenceObject` at `0x140003647`
- `ntoskrnl!ObfDereferenceObject` at `0x140003647`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003712`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003755`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003712`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003755`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140003625`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140003625`
- `FLTMGR!FltClose` at `0x140003637`
- `FLTMGR!FltClose` at `0x140003637`
- `FLTMGR!FltCreateFileEx2` at `0x1400035c4`
- `FLTMGR!FltCreateFileEx2` at `0x1400035c4`

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
0x1400033c0  push    rbp
0x1400033c2  push    rbx
0x1400033c3  push    rsi
0x1400033c4  push    rdi
0x1400033c5  push    r12
0x1400033c7  push    r14
0x1400033c9  push    r15
0x1400033cb  lea     rbp, [rsp-27h]
0x1400033d0  sub     rsp, 0E0h
0x1400033d7  xor     r12d, r12d
0x1400033da  xorps   xmm0, xmm0
0x1400033dd  mov     rdi, r8
0x1400033e0  mov     [rbp+57h+FileHandle], r12
0x1400033e4  movups  xmmword ptr [rbp+57h+var_60.ObjectName], xmm0
0x1400033e8  xor     eax, eax
0x1400033ea  mov     [rbp+57h+FileObject], r12
0x1400033ee  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400033f2  mov     [rdi+8], r12
0x1400033f6  lea     ebx, [r12+1]
0x1400033fb  mov     [rdi], r12d
0x1400033fe  mov     rsi, rcx
0x140003401  mov     rax, [rcx+20h]
0x140003405  mov     r15, rdx
0x140003408  mov     [rbp+57h+FileNameInformation], r12
0x14000340c  mov     r9d, r12d
0x14000340f  movups  xmmword ptr [rbp+57h+var_60.Length], xmm0
0x140003413  mov     r8d, r12d
0x140003416  mov     edx, r12d
0x140003419  movups  xmmword ptr [rbp+57h+var_60+1Ch], xmm0
0x14000341d  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x140003421  movzx   ecx, word ptr [rax+58h]
0x140003425  mov     r10, [rax+60h]
0x140003429  cmp     r12w, cx
0x14000342d  jnb     short loc_140003457
0x14000342f  movzx   eax, dx
0x140003432  shr     rax, 1
0x140003435  cmp     word ptr [r10+rax*2], 5Ch ; '\'
0x14000343b  jnz     short loc_140003448
0x14000343d  add     r8w, bx
0x140003441  cmp     r8w, 3
0x140003446  jz      short loc_140003453
0x140003448  add     dx, 2
0x14000344c  cmp     dx, cx
0x14000344f  jb      short loc_14000342F
0x140003451  jmp     short loc_140003457
0x140003453  movzx   r9d, dx
0x140003457  mov     rax, [r15+18h]
0x14000345b  cmp     r8w, 3
0x140003460  movzx   r14d, cx
0x140003464  mov     r8b, 2
0x140003467  cmovnb  r14w, r9w
0x14000346c  movzx   edx, word ptr [rax+38h]
0x140003470  test    r14w, r14w
0x140003474  jnz     short loc_1400034CB
0x140003476  add     dx, 2
0x14000347a  add     cx, dx
0x14000347d  movzx   edx, cx
0x140003480  mov     ecx, ebx
0x140003482  mov     [rdi+2], dx
0x140003486  call    LuafvAllocatePool
0x14000348b  mov     [rdi+8], rax
0x14000348f  test    rax, rax
0x140003492  jz      short loc_1400034E9
0x140003494  mov     [rdi], r12w
0x140003498  mov     rcx, rdi; DestinationString
0x14000349b  mov     rdx, [r15+18h]
0x14000349f  add     rdx, 38h ; '8'; SourceString
0x1400034a3  call    cs:__imp_RtlCopyUnicodeString
0x1400034aa  nop     dword ptr [rax+rax+00h]
0x1400034af  mov     rdx, [rsi+20h]
0x1400034b3  mov     rcx, rdi; Destination
0x1400034b6  add     rdx, 58h ; 'X'; Source
0x1400034ba  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400034c1  nop     dword ptr [rax+rax+00h]
0x1400034c6  jmp     loc_14000376A
0x1400034cb  lea     eax, [r14+2]
0x1400034cf  mov     ecx, ebx
0x1400034d1  add     ax, dx
0x1400034d4  movzx   edx, ax
0x1400034d7  mov     [rbp+57h+DestinationString.MaximumLength], dx
0x1400034db  call    LuafvAllocatePool
0x1400034e0  mov     [rbp+57h+DestinationString.Buffer], rax
0x1400034e4  test    rax, rax
0x1400034e7  jnz     short loc_1400034F3
0x1400034e9  mov     eax, 0C000009Ah
0x1400034ee  jmp     loc_14000376C
0x1400034f3  mov     rdx, [r15+18h]
0x1400034f7  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400034fb  add     rdx, 38h ; '8'; SourceString
0x1400034ff  mov     [rbp+57h+DestinationString.Length], r12w
0x140003504  call    cs:__imp_RtlCopyUnicodeString
0x14000350b  nop     dword ptr [rax+rax+00h]
0x140003510  mov     rax, [rsi+20h]
0x140003514  lea     rdx, [rbp+57h+Source]; Source
0x140003518  xorps   xmm0, xmm0
0x14000351b  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x14000351f  mov     rcx, [rax+60h]
0x140003523  mov     [rbp+57h+Source.Buffer], rcx
0x140003527  lea     rcx, [rbp+57h+DestinationString]; Destination
0x14000352b  mov     [rbp+57h+Source.Length], r14w
0x140003530  mov     [rbp+57h+Source.MaximumLength], r14w
0x140003535  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000353c  nop     dword ptr [rax+rax+00h]
0x140003541  mov     rdx, [rsi+18h]; Instance
0x140003545  lea     rax, [rbp+57h+DestinationString]
0x140003549  mov     rcx, cs:LuafvDriverData; Filter
0x140003550  lea     r9, [rbp+57h+FileObject]; FileObject
0x140003554  mov     [rsp+110h+DriverContext], r12; DriverContext
0x140003559  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x14000355d  mov     [rsp+110h+Flags], ebx; Flags
0x140003561  xorps   xmm0, xmm0
0x140003564  mov     [rsp+110h+EaLength], r12d; EaLength
0x140003569  mov     [rsp+110h+EaBuffer], r12; EaBuffer
0x14000356e  mov     [rsp+110h+CreateOptions], 21h ; '!'; CreateOptions
0x140003576  mov     [rsp+110h+CreateDisposition], ebx; CreateDisposition
0x14000357a  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x140003582  mov     [rsp+110h+FileAttributes], 10h; FileAttributes
0x14000358a  mov     [rbp+57h+var_60.ObjectName], rax
0x14000358e  lea     rax, [rbp+57h+var_70]
0x140003592  mov     [rsp+110h+AllocationSize], r12; AllocationSize
0x140003597  mov     [rsp+110h+IoStatusBlock], rax; IoStatusBlock
0x14000359c  lea     rax, [rbp+57h+var_60]
0x1400035a0  mov     [rsp+110h+ObjectAttributes], rax; ObjectAttributes
0x1400035a5  mov     [rsp+110h+DesiredAccess], 100001h; DesiredAccess
0x1400035ad  mov     [rbp+57h+var_60.Length], 30h ; '0'
0x1400035b4  mov     [rbp+57h+var_60.RootDirectory], r12
0x1400035b8  mov     [rbp+57h+var_60.Attributes], 240h
0x1400035bf  movdqu  xmmword ptr [rbp+57h+var_60.SecurityDescriptor], xmm0
0x1400035c4  call    cs:__imp_FltCreateFileEx2
0x1400035cb  nop     dword ptr [rax+rax+00h]
0x1400035d0  test    eax, eax
0x1400035d2  jns     short loc_140003613
0x1400035d4  mov     rax, [rsi+20h]
0x1400035d8  mov     r8b, 2
0x1400035db  mov     rdx, [r15+18h]
0x1400035df  movzx   ecx, word ptr [rax+58h]
0x1400035e3  movzx   eax, word ptr [rdx+38h]
0x1400035e7  add     cx, 2
0x1400035eb  add     ax, cx
0x1400035ee  mov     ecx, ebx
0x1400035f0  movzx   edx, ax
0x1400035f3  mov     [rdi+2], dx
0x1400035f7  call    LuafvAllocatePool
0x1400035fc  mov     [rdi+8], rax
0x140003600  test    rax, rax
0x140003603  jnz     short loc_140003683
0x140003605  mov     rcx, [rbp+57h+DestinationString.Buffer]
0x140003609  call    LuafvFreePool
0x14000360e  jmp     loc_1400034E9
0x140003613  mov     rdx, [rsi+18h]; Instance
0x140003617  lea     r9, [rbp+57h+FileNameInformation]; FileNameInformation
0x14000361b  mov     rcx, [rbp+57h+FileObject]; FileObject
0x14000361f  mov     r8d, 101h; NameOptions
0x140003625  call    cs:__imp_FltGetFileNameInformationUnsafe
0x14000362c  nop     dword ptr [rax+rax+00h]
0x140003631  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140003635  mov     ebx, eax
0x140003637  call    cs:__imp_FltClose
0x14000363e  nop     dword ptr [rax+rax+00h]
0x140003643  mov     rcx, [rbp+57h+FileObject]; Object
0x140003647  call    cs:__imp_ObfDereferenceObject
0x14000364e  nop     dword ptr [rax+rax+00h]
0x140003653  mov     [rbp+57h+FileHandle], r12
0x140003657  mov     r8b, 2
0x14000365a  mov     [rbp+57h+FileObject], r12
0x14000365e  test    ebx, ebx
0x140003660  jns     short loc_1400036BA
0x140003662  mov     rax, [rsi+20h]
0x140003666  mov     rdx, [r15+18h]
0x14000366a  movzx   ecx, word ptr [rax+58h]
0x14000366e  movzx   eax, word ptr [rdx+38h]
0x140003672  add     cx, 2
0x140003676  add     ax, cx
0x140003679  mov     ecx, 1
0x14000367e  jmp     loc_1400035F0
0x140003683  mov     [rdi], r12w
0x140003687  mov     rcx, rdi; DestinationString
0x14000368a  mov     rdx, [r15+18h]
0x14000368e  add     rdx, 38h ; '8'; SourceString
0x140003692  call    cs:__imp_RtlCopyUnicodeString
0x140003699  nop     dword ptr [rax+rax+00h]
0x14000369e  mov     rdx, [rsi+20h]
0x1400036a2  mov     rcx, rdi; Destination
0x1400036a5  add     rdx, 58h ; 'X'; Source
0x1400036a9  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400036b0  nop     dword ptr [rax+rax+00h]
0x1400036b5  jmp     loc_140003761
0x1400036ba  mov     rdx, [rsi+20h]
0x1400036be  xorps   xmm0, xmm0
0x1400036c1  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x1400036c5  movzx   ecx, r14w
0x1400036c9  shr     rcx, 1
0x1400036cc  mov     rax, [rdx+60h]
0x1400036d0  lea     rcx, [rax+rcx*2]
0x1400036d4  mov     rax, [rbp+57h+FileNameInformation]
0x1400036d8  mov     [rbp+57h+Source.Buffer], rcx
0x1400036dc  movzx   ecx, word ptr [rdx+58h]
0x1400036e0  sub     cx, r14w
0x1400036e4  mov     [rbp+57h+Source.Length], cx
0x1400036e8  mov     [rbp+57h+Source.MaximumLength], cx
0x1400036ec  add     cx, 2
0x1400036f0  add     cx, [rax+8]
0x1400036f4  movzx   edx, cx
0x1400036f7  mov     ecx, 1
0x1400036fc  mov     [rdi+2], dx
0x140003700  call    LuafvAllocatePool
0x140003705  mov     [rdi+8], rax
0x140003709  test    rax, rax
0x14000370c  jnz     short loc_140003723
0x14000370e  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140003712  call    cs:__imp_FltReleaseFileNameInformation
0x140003719  nop     dword ptr [rax+rax+00h]
0x14000371e  jmp     loc_140003605
0x140003723  mov     rdx, [rbp+57h+FileNameInformation]
0x140003727  mov     rcx, rdi; DestinationString
0x14000372a  add     rdx, 8; SourceString
0x14000372e  mov     [rdi], r12w
0x140003732  call    cs:__imp_RtlCopyUnicodeString
0x140003739  nop     dword ptr [rax+rax+00h]
0x14000373e  lea     rdx, [rbp+57h+Source]; Source
0x140003742  mov     rcx, rdi; Destination
0x140003745  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000374c  nop     dword ptr [rax+rax+00h]
0x140003751  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140003755  call    cs:__imp_FltReleaseFileNameInformation
0x14000375c  nop     dword ptr [rax+rax+00h]
0x140003761  mov     rcx, [rbp+57h+DestinationString.Buffer]
0x140003765  call    LuafvFreePool
0x14000376a  xor     eax, eax
0x14000376c  add     rsp, 0E0h
0x140003773  pop     r15
0x140003775  pop     r14
0x140003777  pop     r12
0x140003779  pop     rdi
0x14000377a  pop     rsi
0x14000377b  pop     rbx
0x14000377c  pop     rbp
0x14000377d  retn
```
