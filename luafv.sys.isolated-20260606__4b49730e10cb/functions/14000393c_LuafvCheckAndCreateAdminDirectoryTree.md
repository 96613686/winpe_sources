# LuafvCheckAndCreateAdminDirectoryTree

- ea: `0x14000393c`
- end: `0x140003d29`
- name: `LuafvCheckAndCreateAdminDirectoryTree`
- size: `1005`
- prototype: `NTSTATUS __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400258a0`

## callees

- `0x1400033c0`
- `0x14000393c`
- `0x140003d30`
- `0x140004390`
- `0x1400046c4`
- `0x1400049b0`
- `0x14001b6a0`
- `0x14001dd90`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140003b4e`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140003b4e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140003a89`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140003a89`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140003a71`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140003a71`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003a5a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003a5a`
- `ntoskrnl!ObfDereferenceObject` at `0x140003b87`
- `ntoskrnl!ObfDereferenceObject` at `0x140003cef`
- `ntoskrnl!ObfDereferenceObject` at `0x140003b87`
- `ntoskrnl!ObfDereferenceObject` at `0x140003cef`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003a23`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003a99`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003a23`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003a99`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400039d9`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400039d9`
- `FLTMGR!FltReleaseContext` at `0x140003a38`
- `FLTMGR!FltReleaseContext` at `0x140003acb`
- `FLTMGR!FltReleaseContext` at `0x140003b1e`
- `FLTMGR!FltReleaseContext` at `0x140003a38`
- `FLTMGR!FltReleaseContext` at `0x140003acb`
- `FLTMGR!FltReleaseContext` at `0x140003b1e`
- `FLTMGR!FltGetInstanceContext` at `0x1400039a6`
- `FLTMGR!FltGetInstanceContext` at `0x1400039a6`
- `FLTMGR!FltClose` at `0x140003b97`
- `FLTMGR!FltClose` at `0x140003cff`
- `FLTMGR!FltClose` at `0x140003b97`
- `FLTMGR!FltClose` at `0x140003cff`
- `FLTMGR!FltCreateFileEx2` at `0x140003cd7`
- `FLTMGR!FltCreateFileEx2` at `0x140003cd7`

## pseudocode

```c
NTSTATUS __fastcall LuafvCheckAndCreateAdminDirectoryTree(__int64 a1, __int64 a2, int a3)
{
  struct _FLT_INSTANCE *v5; // rcx
  NTSTATUS result; // eax
  struct _FILE_OBJECT *v8; // rcx
  NTSTATUS FileNameInformationUnsafe; // ebx
  __int64 v10; // r8
  PWSTR Buffer; // rcx
  PWSTR v12; // rsi
  int v13; // r9d
  __int64 v14; // rdi
  HANDLE v15; // rcx
  unsigned __int16 v16; // cx
  unsigned __int64 v17; // xmm0_8
  struct _FLT_INSTANCE *v18; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  HANDLE FileHandle; // [rsp+90h] [rbp-70h] BYREF
  PVOID Object; // [rsp+98h] [rbp-68h] BYREF
  __m128i v22; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING v23; // [rsp+B0h] [rbp-50h] BYREF
  __m128i v24; // [rsp+C0h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp+0h] BYREF
  PFLT_CONTEXT Context; // [rsp+140h] [rbp+40h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+158h] [rbp+58h] BYREF

  Context = 0;
  FileNameInformation = 0;
  FileHandle = 0;
  v5 = *(struct _FLT_INSTANCE **)(a1 + 24);
  Object = 0;
  DestinationString = 0;
  v23 = 0;
  v22 = 0;
  v24 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  result = FltGetInstanceContext(v5, &Context);
  if ( result >= 0 )
  {
    v8 = *(struct _FILE_OBJECT **)(*(_QWORD *)(a1 + 32) + 64LL);
    if ( v8 )
    {
      FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(
                                    v8,
                                    *(PFLT_INSTANCE *)(a1 + 24),
                                    0x101u,
                                    &FileNameInformation);
      if ( FileNameInformationUnsafe < 0 )
      {
LABEL_6:
        FltReleaseContext(Context);
        return FileNameInformationUnsafe;
      }
      LOBYTE(v10) = 2;
      DestinationString.MaximumLength = *(_WORD *)(*(_QWORD *)(a1 + 32) + 88LL) + FileNameInformation->Name.Length + 4;
      DestinationString.Buffer = (PWSTR)LuafvAllocatePool(1, DestinationString.MaximumLength, v10);
      if ( !DestinationString.Buffer )
      {
        FltReleaseFileNameInformation(FileNameInformation);
        FileNameInformationUnsafe = -1073741670;
        goto LABEL_6;
      }
      DestinationString.Length = 0;
      RtlCopyUnicodeString(&DestinationString, &FileNameInformation->Name);
      RtlAppendUnicodeToString(&DestinationString, L"\\");
      RtlAppendUnicodeStringToString(&DestinationString, (PCUNICODE_STRING)(*(_QWORD *)(a1 + 32) + 88LL));
      FltReleaseFileNameInformation(FileNameInformation);
      FileNameInformation = 0;
      FileNameInformationUnsafe = NormalizeFullPath(
                                    a1,
                                    *(unsigned __int16 *)(*((_QWORD *)Context + 3) + 56LL),
                                    &DestinationString,
                                    &v23);
      FltReleaseContext(Context);
      Context = 0;
      if ( FileNameInformationUnsafe < 0 )
      {
        Buffer = DestinationString.Buffer;
LABEL_25:
        LuafvFreePool(Buffer);
        return FileNameInformationUnsafe;
      }
      v12 = v23.Buffer;
      if ( v23.Buffer )
      {
        LuafvFreePool(DestinationString.Buffer);
        v12 = 0;
        DestinationString = v23;
      }
    }
    else
    {
      FileNameInformationUnsafe = BuildNormalizedPathFromFileName(a1, Context, &DestinationString);
      FltReleaseContext(Context);
      Context = 0;
      if ( FileNameInformationUnsafe < 0 )
        return FileNameInformationUnsafe;
      v12 = v23.Buffer;
    }
    TrimTrailingBackslash(&DestinationString);
    if ( RtlPrefixUnicodeString((PCUNICODE_STRING)(a2 + 120), &DestinationString, 1u) )
    {
      FileNameInformationUnsafe = LuafvGetMirrorFileName(a2, a3, (unsigned int)&DestinationString, v13, (__int64)&v22);
      if ( FileNameInformationUnsafe >= 0 )
      {
        TrimTrailingBackslash(&v22);
        v24 = v22;
        v16 = _mm_cvtsi128_si32(v22);
        v17 = _mm_srli_si128(v22, 8).m128i_u64[0];
        v14 = v17;
        do
        {
          if ( !v16 )
            break;
          v16 -= 2;
        }
        while ( *(_WORD *)(v17 + 2 * ((unsigned __int64)v16 >> 1)) != 92 );
        if ( v16
          && (v18 = *(struct _FLT_INSTANCE **)(a1 + 24),
              ObjectAttributes.ObjectName = (PUNICODE_STRING)&v24,
              v24.m128i_i16[0] = v16,
              ObjectAttributes.Length = 48,
              ObjectAttributes.RootDirectory = 0,
              ObjectAttributes.Attributes = 576,
              *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0,
              FltCreateFileEx2(
                LuafvDriverData,
                v18,
                &FileHandle,
                (PFILE_OBJECT *)&Object,
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
                0) >= 0) )
        {
          ObfDereferenceObject(Object);
          FltClose(FileHandle);
          FileHandle = 0;
          Object = 0;
          FileNameInformationUnsafe = LuafvCreateAdminDirectoryTree(a1, a2, &DestinationString);
        }
        else
        {
          FileNameInformationUnsafe = 0;
        }
LABEL_16:
        if ( v12 )
          LuafvFreePool(v12);
        v15 = FileHandle;
        if ( FileHandle )
        {
          if ( Object )
          {
            ObfDereferenceObject(Object);
            v15 = FileHandle;
          }
          FltClose(v15);
        }
        if ( v14 )
          LuafvFreePool(v14);
        Buffer = DestinationString.Buffer;
        if ( !DestinationString.Buffer )
          return FileNameInformationUnsafe;
        goto LABEL_25;
      }
    }
    else
    {
      FileNameInformationUnsafe = 0;
    }
    v14 = v22.m128i_i64[1];
    goto LABEL_16;
  }
  return result;
}

```

## disassembly

```asm
0x14000393c  mov     [rsp-8+arg_8], rbx
0x140003941  mov     [rsp-8+arg_10], rsi
0x140003946  push    rbp
0x140003947  push    rdi
0x140003948  push    r12
0x14000394a  push    r14
0x14000394c  push    r15
0x14000394e  lea     rbp, [rsp-10h]
0x140003953  sub     rsp, 110h
0x14000395a  xorps   xmm0, xmm0
0x14000395d  xor     r12d, r12d
0x140003960  xorps   xmm1, xmm1
0x140003963  mov     [rbp+30h+Context], r12
0x140003967  mov     r15, rdx
0x14000396a  mov     [rbp+30h+FileNameInformation], r12
0x14000396e  mov     r14, rcx
0x140003971  mov     [rbp+30h+FileHandle], r12
0x140003975  mov     rcx, [rcx+18h]; Instance
0x140003979  lea     rdx, [rbp+30h+Context]; Context
0x14000397d  movups  xmmword ptr [rbp+30h+var_60.ObjectName], xmm0
0x140003981  xor     eax, eax
0x140003983  mov     [rbp+30h+Object], r12
0x140003987  movups  xmmword ptr [rbp+30h+var_60+1Ch], xmm0
0x14000398b  mov     rdi, r8
0x14000398e  movups  xmmword ptr [rbp+30h+DestinationString.Length], xmm0
0x140003992  movups  [rbp+30h+var_80], xmm1
0x140003996  movups  [rbp+30h+var_90], xmm0
0x14000399a  movups  [rbp+30h+var_70], xmm1
0x14000399e  movups  xmmword ptr [rbp+30h+var_60.Length], xmm0
0x1400039a2  movups  xmmword ptr [rbp+30h+var_30], xmm0
0x1400039a6  call    cs:__imp_FltGetInstanceContext
0x1400039ad  nop     dword ptr [rax+rax+00h]
0x1400039b2  test    eax, eax
0x1400039b4  js      loc_140003BC0
0x1400039ba  mov     rax, [r14+20h]
0x1400039be  mov     rcx, [rax+40h]; FileObject
0x1400039c2  test    rcx, rcx
0x1400039c5  jz      loc_140003B08
0x1400039cb  mov     rdx, [r14+18h]; Instance
0x1400039cf  lea     r9, [rbp+30h+FileNameInformation]; FileNameInformation
0x1400039d3  mov     r8d, 101h; NameOptions
0x1400039d9  call    cs:__imp_FltGetFileNameInformationUnsafe
0x1400039e0  nop     dword ptr [rax+rax+00h]
0x1400039e5  mov     ebx, eax
0x1400039e7  test    eax, eax
0x1400039e9  js      short loc_140003A34
0x1400039eb  mov     rax, [r14+20h]
0x1400039ef  mov     r8b, 2
0x1400039f2  movzx   ecx, word ptr [rax+58h]
0x1400039f6  mov     rax, [rbp+30h+FileNameInformation]
0x1400039fa  movzx   edx, word ptr [rax+8]
0x1400039fe  add     dx, 4
0x140003a02  add     dx, cx
0x140003a05  lea     ecx, [r12+1]
0x140003a0a  movzx   edx, dx
0x140003a0d  mov     [rbp+30h+DestinationString.MaximumLength], dx
0x140003a11  call    LuafvAllocatePool
0x140003a16  mov     [rbp+30h+DestinationString.Buffer], rax
0x140003a1a  test    rax, rax
0x140003a1d  jnz     short loc_140003A49
0x140003a1f  mov     rcx, [rbp+30h+FileNameInformation]; FileNameInformation
0x140003a23  call    cs:__imp_FltReleaseFileNameInformation
0x140003a2a  nop     dword ptr [rax+rax+00h]
0x140003a2f  mov     ebx, 0C000009Ah
0x140003a34  mov     rcx, [rbp+30h+Context]; Context
0x140003a38  call    cs:__imp_FltReleaseContext
0x140003a3f  nop     dword ptr [rax+rax+00h]
0x140003a44  jmp     loc_140003BBE
0x140003a49  mov     rdx, [rbp+30h+FileNameInformation]
0x140003a4d  lea     rcx, [rbp+30h+DestinationString]; DestinationString
0x140003a51  add     rdx, 8; SourceString
0x140003a55  mov     [rbp+30h+DestinationString.Length], r12w
0x140003a5a  call    cs:__imp_RtlCopyUnicodeString
0x140003a61  nop     dword ptr [rax+rax+00h]
0x140003a66  lea     rdx, Source; "\\"
0x140003a6d  lea     rcx, [rbp+30h+DestinationString]; Destination
0x140003a71  call    cs:__imp_RtlAppendUnicodeToString
0x140003a78  nop     dword ptr [rax+rax+00h]
0x140003a7d  mov     rdx, [r14+20h]
0x140003a81  lea     rcx, [rbp+30h+DestinationString]; Destination
0x140003a85  add     rdx, 58h ; 'X'; Source
0x140003a89  call    cs:__imp_RtlAppendUnicodeStringToString
0x140003a90  nop     dword ptr [rax+rax+00h]
0x140003a95  mov     rcx, [rbp+30h+FileNameInformation]; FileNameInformation
0x140003a99  call    cs:__imp_FltReleaseFileNameInformation
0x140003aa0  nop     dword ptr [rax+rax+00h]
0x140003aa5  mov     rax, [rbp+30h+Context]
0x140003aa9  lea     r9, [rbp+30h+var_80]
0x140003aad  mov     [rbp+30h+FileNameInformation], r12
0x140003ab1  lea     r8, [rbp+30h+DestinationString]
0x140003ab5  mov     rcx, r14
0x140003ab8  mov     rdx, [rax+18h]
0x140003abc  movzx   edx, word ptr [rdx+38h]
0x140003ac0  call    NormalizeFullPath
0x140003ac5  mov     rcx, [rbp+30h+Context]; Context
0x140003ac9  mov     ebx, eax
0x140003acb  call    cs:__imp_FltReleaseContext
0x140003ad2  nop     dword ptr [rax+rax+00h]
0x140003ad7  mov     [rbp+30h+Context], r12
0x140003adb  test    ebx, ebx
0x140003add  jns     short loc_140003AE8
0x140003adf  mov     rcx, [rbp+30h+DestinationString.Buffer]
0x140003ae3  jmp     loc_140003BB9
0x140003ae8  mov     rsi, qword ptr [rbp+30h+var_80+8]
0x140003aec  test    rsi, rsi
0x140003aef  jz      short loc_140003B3A
0x140003af1  mov     rcx, [rbp+30h+DestinationString.Buffer]
0x140003af5  call    LuafvFreePool
0x140003afa  movaps  xmm0, [rbp+30h+var_80]
0x140003afe  mov     rsi, r12
0x140003b01  movdqa  xmmword ptr [rbp+30h+DestinationString.Length], xmm0
0x140003b06  jmp     short loc_140003B3A
0x140003b08  mov     rdx, [rbp+30h+Context]
0x140003b0c  lea     r8, [rbp+30h+DestinationString]
0x140003b10  mov     rcx, r14
0x140003b13  call    BuildNormalizedPathFromFileName
0x140003b18  mov     rcx, [rbp+30h+Context]; Context
0x140003b1c  mov     ebx, eax
0x140003b1e  call    cs:__imp_FltReleaseContext
0x140003b25  nop     dword ptr [rax+rax+00h]
0x140003b2a  mov     [rbp+30h+Context], r12
0x140003b2e  test    ebx, ebx
0x140003b30  js      loc_140003BBE
0x140003b36  mov     rsi, qword ptr [rbp+30h+var_80+8]
0x140003b3a  lea     rcx, [rbp+30h+DestinationString]
0x140003b3e  call    TrimTrailingBackslash
0x140003b43  mov     r8b, 1; CaseInSensitive
0x140003b46  lea     rdx, [rbp+30h+DestinationString]; String2
0x140003b4a  lea     rcx, [r15+78h]; String1
0x140003b4e  call    cs:__imp_RtlPrefixUnicodeString
0x140003b55  nop     dword ptr [rax+rax+00h]
0x140003b5a  test    al, al
0x140003b5c  jnz     short loc_140003BDD
0x140003b5e  mov     ebx, r12d
0x140003b61  mov     rdi, qword ptr [rbp+30h+var_90+8]
0x140003b65  test    rsi, rsi
0x140003b68  jz      short loc_140003B72
0x140003b6a  mov     rcx, rsi
0x140003b6d  call    LuafvFreePool
0x140003b72  mov     rcx, [rbp+30h+FileHandle]
0x140003b76  test    rcx, rcx
0x140003b79  jz      short loc_140003BA3
0x140003b7b  mov     rax, [rbp+30h+Object]
0x140003b7f  test    rax, rax
0x140003b82  jz      short loc_140003B97
0x140003b84  mov     rcx, rax; Object
0x140003b87  call    cs:__imp_ObfDereferenceObject
0x140003b8e  nop     dword ptr [rax+rax+00h]
0x140003b93  mov     rcx, [rbp+30h+FileHandle]; FileHandle
0x140003b97  call    cs:__imp_FltClose
0x140003b9e  nop     dword ptr [rax+rax+00h]
0x140003ba3  test    rdi, rdi
0x140003ba6  jz      short loc_140003BB0
0x140003ba8  mov     rcx, rdi
0x140003bab  call    LuafvFreePool
0x140003bb0  mov     rcx, [rbp+30h+DestinationString.Buffer]
0x140003bb4  test    rcx, rcx
0x140003bb7  jz      short loc_140003BBE
0x140003bb9  call    LuafvFreePool
0x140003bbe  mov     eax, ebx
0x140003bc0  lea     r11, [rsp+130h+var_20]
0x140003bc8  mov     rbx, [r11+38h]
0x140003bcc  mov     rsi, [r11+40h]
0x140003bd0  mov     rsp, r11
0x140003bd3  pop     r15
0x140003bd5  pop     r14
0x140003bd7  pop     r12
0x140003bd9  pop     rdi
0x140003bda  pop     rbp
0x140003bdb  retn
0x140003bdd  lea     rax, [rbp+30h+var_90]
0x140003be1  mov     rdx, rdi
0x140003be4  lea     r8, [rbp+30h+DestinationString]
0x140003be8  mov     qword ptr [rsp+130h+DesiredAccess], rax
0x140003bed  mov     rcx, r15
0x140003bf0  call    LuafvGetMirrorFileName
0x140003bf5  mov     ebx, eax
0x140003bf7  test    eax, eax
0x140003bf9  js      loc_140003B61
0x140003bff  lea     rcx, [rbp+30h+var_90]
0x140003c03  call    TrimTrailingBackslash
0x140003c08  movaps  xmm0, [rbp+30h+var_90]
0x140003c0c  movdqa  [rbp+30h+var_70], xmm0
0x140003c11  movd    ecx, xmm0
0x140003c15  psrldq  xmm0, 8
0x140003c1a  movq    rdi, xmm0
0x140003c1f  jmp     short loc_140003C36
0x140003c21  mov     eax, 0FFFEh
0x140003c26  add     cx, ax
0x140003c29  movzx   eax, cx
0x140003c2c  shr     rax, 1
0x140003c2f  cmp     word ptr [rdi+rax*2], 5Ch ; '\'
0x140003c34  jz      short loc_140003C3B
0x140003c36  test    cx, cx
0x140003c39  jnz     short loc_140003C21
0x140003c3b  test    cx, cx
0x140003c3e  jnz     short loc_140003C48
0x140003c40  mov     ebx, r12d
0x140003c43  jmp     loc_140003B65
0x140003c48  mov     rdx, [r14+18h]; Instance
0x140003c4c  lea     rax, [rbp+30h+var_70]
0x140003c50  mov     [rsp+130h+DriverContext], r12; DriverContext
0x140003c55  lea     r9, [rbp+30h+Object]; FileObject
0x140003c59  mov     [rsp+130h+Flags], 1; Flags
0x140003c61  lea     r8, [rbp+30h+FileHandle]; FileHandle
0x140003c65  mov     [rsp+130h+EaLength], r12d; EaLength
0x140003c6a  xorps   xmm0, xmm0
0x140003c6d  mov     [rsp+130h+EaBuffer], r12; EaBuffer
0x140003c72  mov     [rsp+130h+CreateOptions], 21h ; '!'; CreateOptions
0x140003c7a  mov     [rsp+130h+CreateDisposition], 1; CreateDisposition
0x140003c82  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x140003c8a  mov     [rsp+130h+FileAttributes], 10h; FileAttributes
0x140003c92  mov     [rbp+30h+var_60.ObjectName], rax
0x140003c96  lea     rax, [rbp+30h+var_30]
0x140003c9a  mov     [rsp+130h+AllocationSize], r12; AllocationSize
0x140003c9f  mov     [rsp+130h+IoStatusBlock], rax; IoStatusBlock
0x140003ca4  lea     rax, [rbp+30h+var_60]
0x140003ca8  mov     word ptr [rbp+30h+var_70], cx
0x140003cac  mov     rcx, cs:LuafvDriverData; Filter
0x140003cb3  mov     [rsp+130h+ObjectAttributes], rax; ObjectAttributes
0x140003cb8  mov     [rsp+130h+DesiredAccess], 100001h; DesiredAccess
0x140003cc0  mov     [rbp+30h+var_60.Length], 30h ; '0'
0x140003cc7  mov     [rbp+30h+var_60.RootDirectory], r12
0x140003ccb  mov     [rbp+30h+var_60.Attributes], 240h
0x140003cd2  movdqu  xmmword ptr [rbp+30h+var_60.SecurityDescriptor], xmm0
0x140003cd7  call    cs:__imp_FltCreateFileEx2
0x140003cde  nop     dword ptr [rax+rax+00h]
0x140003ce3  test    eax, eax
0x140003ce5  js      loc_140003C40
0x140003ceb  mov     rcx, [rbp+30h+Object]; Object
0x140003cef  call    cs:__imp_ObfDereferenceObject
0x140003cf6  nop     dword ptr [rax+rax+00h]
0x140003cfb  mov     rcx, [rbp+30h+FileHandle]; FileHandle
0x140003cff  call    cs:__imp_FltClose
0x140003d06  nop     dword ptr [rax+rax+00h]
0x140003d0b  lea     r8, [rbp+30h+DestinationString]
0x140003d0f  mov     [rbp+30h+FileHandle], r12
0x140003d13  mov     rdx, r15
0x140003d16  mov     [rbp+30h+Object], r12
0x140003d1a  mov     rcx, r14
0x140003d1d  call    LuafvCreateAdminDirectoryTree
0x140003d22  mov     ebx, eax
0x140003d24  jmp     loc_140003B65
```
