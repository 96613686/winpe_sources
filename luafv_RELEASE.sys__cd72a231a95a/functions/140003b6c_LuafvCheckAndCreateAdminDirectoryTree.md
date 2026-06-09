# LuafvCheckAndCreateAdminDirectoryTree

- ea: `0x140003b6c`
- end: `0x140003f59`
- name: `LuafvCheckAndCreateAdminDirectoryTree`
- size: `1005`
- prototype: `NTSTATUS __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140025820`

## callees

- `0x1400035f0`
- `0x140003b6c`
- `0x140003f60`
- `0x1400045c0`
- `0x14000488c`
- `0x140004b78`
- `0x14001b650`
- `0x14001dd40`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140003d7e`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140003d7e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140003cb9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140003cb9`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140003ca1`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140003ca1`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003c8a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003c8a`
- `ntoskrnl!ObfDereferenceObject` at `0x140003db7`
- `ntoskrnl!ObfDereferenceObject` at `0x140003f1f`
- `ntoskrnl!ObfDereferenceObject` at `0x140003db7`
- `ntoskrnl!ObfDereferenceObject` at `0x140003f1f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003c53`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003cc9`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003c53`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003cc9`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140003c09`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140003c09`
- `FLTMGR!FltReleaseContext` at `0x140003c68`
- `FLTMGR!FltReleaseContext` at `0x140003cfb`
- `FLTMGR!FltReleaseContext` at `0x140003d4e`
- `FLTMGR!FltReleaseContext` at `0x140003c68`
- `FLTMGR!FltReleaseContext` at `0x140003cfb`
- `FLTMGR!FltReleaseContext` at `0x140003d4e`
- `FLTMGR!FltGetInstanceContext` at `0x140003bd6`
- `FLTMGR!FltGetInstanceContext` at `0x140003bd6`
- `FLTMGR!FltClose` at `0x140003dc7`
- `FLTMGR!FltClose` at `0x140003f2f`
- `FLTMGR!FltClose` at `0x140003dc7`
- `FLTMGR!FltClose` at `0x140003f2f`
- `FLTMGR!FltCreateFileEx2` at `0x140003f07`
- `FLTMGR!FltCreateFileEx2` at `0x140003f07`

## pseudocode

```c
NTSTATUS __fastcall LuafvCheckAndCreateAdminDirectoryTree(__int64 a1, __int64 a2, __int64 a3)
{
  struct _FLT_INSTANCE *v5; // rcx
  NTSTATUS result; // eax
  struct _FILE_OBJECT *v8; // rcx
  int FileNameInformationUnsafe; // ebx
  __int64 v10; // r8
  PWSTR Buffer; // rcx
  PWSTR v12; // rsi
  __int64 v13; // r9
  PWSTR v14; // rdi
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
      FileNameInformationUnsafe = BuildNormalizedPathFromFileName(a1, (__int64)Context, &DestinationString);
      FltReleaseContext(Context);
      Context = 0;
      if ( FileNameInformationUnsafe < 0 )
        return FileNameInformationUnsafe;
      v12 = v23.Buffer;
    }
    TrimTrailingBackslash(&DestinationString);
    if ( RtlPrefixUnicodeString((PCUNICODE_STRING)(a2 + 120), &DestinationString, 1u) )
    {
      FileNameInformationUnsafe = LuafvGetMirrorFileName(
                                    a2,
                                    a3,
                                    &DestinationString,
                                    v13,
                                    (struct _UNICODE_STRING *)&v22);
      if ( FileNameInformationUnsafe >= 0 )
      {
        TrimTrailingBackslash(&v22);
        v24 = v22;
        v16 = _mm_cvtsi128_si32(v22);
        v17 = _mm_srli_si128(v22, 8).m128i_u64[0];
        v14 = (PWSTR)v17;
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
    v14 = (PWSTR)v22.m128i_i64[1];
    goto LABEL_16;
  }
  return result;
}

```

## disassembly

```asm
0x140003b6c  mov     [rsp-8+arg_8], rbx
0x140003b71  mov     [rsp-8+arg_10], rsi
0x140003b76  push    rbp
0x140003b77  push    rdi
0x140003b78  push    r12
0x140003b7a  push    r14
0x140003b7c  push    r15
0x140003b7e  lea     rbp, [rsp-10h]
0x140003b83  sub     rsp, 110h
0x140003b8a  xorps   xmm0, xmm0
0x140003b8d  xor     r12d, r12d
0x140003b90  xorps   xmm1, xmm1
0x140003b93  mov     [rbp+30h+Context], r12
0x140003b97  mov     r15, rdx
0x140003b9a  mov     [rbp+30h+FileNameInformation], r12
0x140003b9e  mov     r14, rcx
0x140003ba1  mov     [rbp+30h+FileHandle], r12
0x140003ba5  mov     rcx, [rcx+18h]; Instance
0x140003ba9  lea     rdx, [rbp+30h+Context]; Context
0x140003bad  movups  xmmword ptr [rbp+30h+var_60.ObjectName], xmm0
0x140003bb1  xor     eax, eax
0x140003bb3  mov     [rbp+30h+Object], r12
0x140003bb7  movups  xmmword ptr [rbp+30h+var_60+1Ch], xmm0
0x140003bbb  mov     rdi, r8
0x140003bbe  movups  xmmword ptr [rbp+30h+DestinationString.Length], xmm0
0x140003bc2  movups  [rbp+30h+var_80], xmm1
0x140003bc6  movups  [rbp+30h+var_90], xmm0
0x140003bca  movups  [rbp+30h+var_70], xmm1
0x140003bce  movups  xmmword ptr [rbp+30h+var_60.Length], xmm0
0x140003bd2  movups  xmmword ptr [rbp+30h+var_30], xmm0
0x140003bd6  call    cs:__imp_FltGetInstanceContext
0x140003bdd  nop     dword ptr [rax+rax+00h]
0x140003be2  test    eax, eax
0x140003be4  js      loc_140003DF0
0x140003bea  mov     rax, [r14+20h]
0x140003bee  mov     rcx, [rax+40h]; FileObject
0x140003bf2  test    rcx, rcx
0x140003bf5  jz      loc_140003D38
0x140003bfb  mov     rdx, [r14+18h]; Instance
0x140003bff  lea     r9, [rbp+30h+FileNameInformation]; FileNameInformation
0x140003c03  mov     r8d, 101h; NameOptions
0x140003c09  call    cs:__imp_FltGetFileNameInformationUnsafe
0x140003c10  nop     dword ptr [rax+rax+00h]
0x140003c15  mov     ebx, eax
0x140003c17  test    eax, eax
0x140003c19  js      short loc_140003C64
0x140003c1b  mov     rax, [r14+20h]
0x140003c1f  mov     r8b, 2
0x140003c22  movzx   ecx, word ptr [rax+58h]
0x140003c26  mov     rax, [rbp+30h+FileNameInformation]
0x140003c2a  movzx   edx, word ptr [rax+8]
0x140003c2e  add     dx, 4
0x140003c32  add     dx, cx
0x140003c35  lea     ecx, [r12+1]
0x140003c3a  movzx   edx, dx
0x140003c3d  mov     [rbp+30h+DestinationString.MaximumLength], dx
0x140003c41  call    LuafvAllocatePool
0x140003c46  mov     [rbp+30h+DestinationString.Buffer], rax
0x140003c4a  test    rax, rax
0x140003c4d  jnz     short loc_140003C79
0x140003c4f  mov     rcx, [rbp+30h+FileNameInformation]; FileNameInformation
0x140003c53  call    cs:__imp_FltReleaseFileNameInformation
0x140003c5a  nop     dword ptr [rax+rax+00h]
0x140003c5f  mov     ebx, 0C000009Ah
0x140003c64  mov     rcx, [rbp+30h+Context]; Context
0x140003c68  call    cs:__imp_FltReleaseContext
0x140003c6f  nop     dword ptr [rax+rax+00h]
0x140003c74  jmp     loc_140003DEE
0x140003c79  mov     rdx, [rbp+30h+FileNameInformation]
0x140003c7d  lea     rcx, [rbp+30h+DestinationString]; DestinationString
0x140003c81  add     rdx, 8; SourceString
0x140003c85  mov     [rbp+30h+DestinationString.Length], r12w
0x140003c8a  call    cs:__imp_RtlCopyUnicodeString
0x140003c91  nop     dword ptr [rax+rax+00h]
0x140003c96  lea     rdx, Source; "\\"
0x140003c9d  lea     rcx, [rbp+30h+DestinationString]; Destination
0x140003ca1  call    cs:__imp_RtlAppendUnicodeToString
0x140003ca8  nop     dword ptr [rax+rax+00h]
0x140003cad  mov     rdx, [r14+20h]
0x140003cb1  lea     rcx, [rbp+30h+DestinationString]; Destination
0x140003cb5  add     rdx, 58h ; 'X'; Source
0x140003cb9  call    cs:__imp_RtlAppendUnicodeStringToString
0x140003cc0  nop     dword ptr [rax+rax+00h]
0x140003cc5  mov     rcx, [rbp+30h+FileNameInformation]; FileNameInformation
0x140003cc9  call    cs:__imp_FltReleaseFileNameInformation
0x140003cd0  nop     dword ptr [rax+rax+00h]
0x140003cd5  mov     rax, [rbp+30h+Context]
0x140003cd9  lea     r9, [rbp+30h+var_80]
0x140003cdd  mov     [rbp+30h+FileNameInformation], r12
0x140003ce1  lea     r8, [rbp+30h+DestinationString]
0x140003ce5  mov     rcx, r14
0x140003ce8  mov     rdx, [rax+18h]
0x140003cec  movzx   edx, word ptr [rdx+38h]
0x140003cf0  call    NormalizeFullPath
0x140003cf5  mov     rcx, [rbp+30h+Context]; Context
0x140003cf9  mov     ebx, eax
0x140003cfb  call    cs:__imp_FltReleaseContext
0x140003d02  nop     dword ptr [rax+rax+00h]
0x140003d07  mov     [rbp+30h+Context], r12
0x140003d0b  test    ebx, ebx
0x140003d0d  jns     short loc_140003D18
0x140003d0f  mov     rcx, [rbp+30h+DestinationString.Buffer]
0x140003d13  jmp     loc_140003DE9
0x140003d18  mov     rsi, qword ptr [rbp+30h+var_80+8]
0x140003d1c  test    rsi, rsi
0x140003d1f  jz      short loc_140003D6A
0x140003d21  mov     rcx, [rbp+30h+DestinationString.Buffer]
0x140003d25  call    LuafvFreePool
0x140003d2a  movaps  xmm0, [rbp+30h+var_80]
0x140003d2e  mov     rsi, r12
0x140003d31  movdqa  xmmword ptr [rbp+30h+DestinationString.Length], xmm0
0x140003d36  jmp     short loc_140003D6A
0x140003d38  mov     rdx, [rbp+30h+Context]
0x140003d3c  lea     r8, [rbp+30h+DestinationString]
0x140003d40  mov     rcx, r14
0x140003d43  call    BuildNormalizedPathFromFileName
0x140003d48  mov     rcx, [rbp+30h+Context]; Context
0x140003d4c  mov     ebx, eax
0x140003d4e  call    cs:__imp_FltReleaseContext
0x140003d55  nop     dword ptr [rax+rax+00h]
0x140003d5a  mov     [rbp+30h+Context], r12
0x140003d5e  test    ebx, ebx
0x140003d60  js      loc_140003DEE
0x140003d66  mov     rsi, qword ptr [rbp+30h+var_80+8]
0x140003d6a  lea     rcx, [rbp+30h+DestinationString]
0x140003d6e  call    TrimTrailingBackslash
0x140003d73  mov     r8b, 1; CaseInSensitive
0x140003d76  lea     rdx, [rbp+30h+DestinationString]; String2
0x140003d7a  lea     rcx, [r15+78h]; String1
0x140003d7e  call    cs:__imp_RtlPrefixUnicodeString
0x140003d85  nop     dword ptr [rax+rax+00h]
0x140003d8a  test    al, al
0x140003d8c  jnz     short loc_140003E0D
0x140003d8e  mov     ebx, r12d
0x140003d91  mov     rdi, qword ptr [rbp+30h+var_90+8]
0x140003d95  test    rsi, rsi
0x140003d98  jz      short loc_140003DA2
0x140003d9a  mov     rcx, rsi
0x140003d9d  call    LuafvFreePool
0x140003da2  mov     rcx, [rbp+30h+FileHandle]
0x140003da6  test    rcx, rcx
0x140003da9  jz      short loc_140003DD3
0x140003dab  mov     rax, [rbp+30h+Object]
0x140003daf  test    rax, rax
0x140003db2  jz      short loc_140003DC7
0x140003db4  mov     rcx, rax; Object
0x140003db7  call    cs:__imp_ObfDereferenceObject
0x140003dbe  nop     dword ptr [rax+rax+00h]
0x140003dc3  mov     rcx, [rbp+30h+FileHandle]; FileHandle
0x140003dc7  call    cs:__imp_FltClose
0x140003dce  nop     dword ptr [rax+rax+00h]
0x140003dd3  test    rdi, rdi
0x140003dd6  jz      short loc_140003DE0
0x140003dd8  mov     rcx, rdi
0x140003ddb  call    LuafvFreePool
0x140003de0  mov     rcx, [rbp+30h+DestinationString.Buffer]
0x140003de4  test    rcx, rcx
0x140003de7  jz      short loc_140003DEE
0x140003de9  call    LuafvFreePool
0x140003dee  mov     eax, ebx
0x140003df0  lea     r11, [rsp+130h+var_20]
0x140003df8  mov     rbx, [r11+38h]
0x140003dfc  mov     rsi, [r11+40h]
0x140003e00  mov     rsp, r11
0x140003e03  pop     r15
0x140003e05  pop     r14
0x140003e07  pop     r12
0x140003e09  pop     rdi
0x140003e0a  pop     rbp
0x140003e0b  retn
0x140003e0d  lea     rax, [rbp+30h+var_90]
0x140003e11  mov     rdx, rdi
0x140003e14  lea     r8, [rbp+30h+DestinationString]
0x140003e18  mov     qword ptr [rsp+130h+DesiredAccess], rax
0x140003e1d  mov     rcx, r15
0x140003e20  call    LuafvGetMirrorFileName
0x140003e25  mov     ebx, eax
0x140003e27  test    eax, eax
0x140003e29  js      loc_140003D91
0x140003e2f  lea     rcx, [rbp+30h+var_90]
0x140003e33  call    TrimTrailingBackslash
0x140003e38  movaps  xmm0, [rbp+30h+var_90]
0x140003e3c  movdqa  [rbp+30h+var_70], xmm0
0x140003e41  movd    ecx, xmm0
0x140003e45  psrldq  xmm0, 8
0x140003e4a  movq    rdi, xmm0
0x140003e4f  jmp     short loc_140003E66
0x140003e51  mov     eax, 0FFFEh
0x140003e56  add     cx, ax
0x140003e59  movzx   eax, cx
0x140003e5c  shr     rax, 1
0x140003e5f  cmp     word ptr [rdi+rax*2], 5Ch ; '\'
0x140003e64  jz      short loc_140003E6B
0x140003e66  test    cx, cx
0x140003e69  jnz     short loc_140003E51
0x140003e6b  test    cx, cx
0x140003e6e  jnz     short loc_140003E78
0x140003e70  mov     ebx, r12d
0x140003e73  jmp     loc_140003D95
0x140003e78  mov     rdx, [r14+18h]; Instance
0x140003e7c  lea     rax, [rbp+30h+var_70]
0x140003e80  mov     [rsp+130h+DriverContext], r12; DriverContext
0x140003e85  lea     r9, [rbp+30h+Object]; FileObject
0x140003e89  mov     [rsp+130h+Flags], 1; Flags
0x140003e91  lea     r8, [rbp+30h+FileHandle]; FileHandle
0x140003e95  mov     [rsp+130h+EaLength], r12d; EaLength
0x140003e9a  xorps   xmm0, xmm0
0x140003e9d  mov     [rsp+130h+EaBuffer], r12; EaBuffer
0x140003ea2  mov     [rsp+130h+CreateOptions], 21h ; '!'; CreateOptions
0x140003eaa  mov     [rsp+130h+CreateDisposition], 1; CreateDisposition
0x140003eb2  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x140003eba  mov     [rsp+130h+FileAttributes], 10h; FileAttributes
0x140003ec2  mov     [rbp+30h+var_60.ObjectName], rax
0x140003ec6  lea     rax, [rbp+30h+var_30]
0x140003eca  mov     [rsp+130h+AllocationSize], r12; AllocationSize
0x140003ecf  mov     [rsp+130h+IoStatusBlock], rax; IoStatusBlock
0x140003ed4  lea     rax, [rbp+30h+var_60]
0x140003ed8  mov     word ptr [rbp+30h+var_70], cx
0x140003edc  mov     rcx, cs:LuafvDriverData; Filter
0x140003ee3  mov     [rsp+130h+ObjectAttributes], rax; ObjectAttributes
0x140003ee8  mov     [rsp+130h+DesiredAccess], 100001h; DesiredAccess
0x140003ef0  mov     [rbp+30h+var_60.Length], 30h ; '0'
0x140003ef7  mov     [rbp+30h+var_60.RootDirectory], r12
0x140003efb  mov     [rbp+30h+var_60.Attributes], 240h
0x140003f02  movdqu  xmmword ptr [rbp+30h+var_60.SecurityDescriptor], xmm0
0x140003f07  call    cs:__imp_FltCreateFileEx2
0x140003f0e  nop     dword ptr [rax+rax+00h]
0x140003f13  test    eax, eax
0x140003f15  js      loc_140003E70
0x140003f1b  mov     rcx, [rbp+30h+Object]; Object
0x140003f1f  call    cs:__imp_ObfDereferenceObject
0x140003f26  nop     dword ptr [rax+rax+00h]
0x140003f2b  mov     rcx, [rbp+30h+FileHandle]; FileHandle
0x140003f2f  call    cs:__imp_FltClose
0x140003f36  nop     dword ptr [rax+rax+00h]
0x140003f3b  lea     r8, [rbp+30h+DestinationString]
0x140003f3f  mov     [rbp+30h+FileHandle], r12
0x140003f43  mov     rdx, r15
0x140003f46  mov     [rbp+30h+Object], r12
0x140003f4a  mov     rcx, r14
0x140003f4d  call    LuafvCreateAdminDirectoryTree
0x140003f52  mov     ebx, eax
0x140003f54  jmp     loc_140003D95
```
