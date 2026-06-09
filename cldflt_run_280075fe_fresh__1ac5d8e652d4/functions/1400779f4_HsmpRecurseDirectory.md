# HsmpRecurseDirectory

- ea: `0x1400779f4`
- end: `0x140077f36`
- name: `HsmpRecurseDirectory`
- size: `1346`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140050d70`
- `0x140054a9c`
- `0x14005599c`
- `0x140077990`

## callees

- `0x140003c50`
- `0x140008b74`
- `0x140009300`
- `0x14000d95c`
- `0x14001e220`
- `0x1400779f4`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140077c22`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140077c41`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140077c22`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140077c41`
- `ntoskrnl!ObfDereferenceObject` at `0x140077da6`
- `ntoskrnl!ObfDereferenceObject` at `0x140077f14`
- `ntoskrnl!ObfDereferenceObject` at `0x140077da6`
- `ntoskrnl!ObfDereferenceObject` at `0x140077f14`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077b0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077b0a`
- `ntoskrnl!ExAllocatePool2` at `0x140077b5e`
- `ntoskrnl!ExAllocatePool2` at `0x140077b5e`
- `FLTMGR!FltCreateFileEx` at `0x140077cea`
- `FLTMGR!FltCreateFileEx` at `0x140077cea`
- `FLTMGR!FltClose` at `0x140077d89`
- `FLTMGR!FltClose` at `0x140077f25`
- `FLTMGR!FltClose` at `0x140077d89`
- `FLTMGR!FltClose` at `0x140077f25`
- `FLTMGR!FltQueryDirectoryFile` at `0x140077ba9`
- `FLTMGR!FltQueryDirectoryFile` at `0x140077ba9`

## pseudocode

```c
__int64 __fastcall HsmpRecurseDirectory(
        __int64 a1,
        void *a2,
        struct _FILE_OBJECT *a3,
        unsigned int a4,
        char a5,
        char a6,
        __int64 (__fastcall *a7)(__int64, struct _FILE_OBJECT *, _QWORD, __int64),
        __int64 (__fastcall *a8)(_QWORD, _QWORD, _QWORD, _QWORD),
        __int64 a9)
{
  struct _FLT_INSTANCE *v9; // r13
  int v10; // ebx
  int v11; // edi
  __int64 v13; // r14
  unsigned int *Pool2; // rsi
  int v15; // eax
  __int64 v17; // rdi
  unsigned int *RestartScan; // rdi
  unsigned int v19; // r14d
  NTSTATUS v20; // r14d
  __int64 v21; // rax
  PDEVICE_OBJECT v22; // rcx
  __int64 v23; // rdx
  PFILE_OBJECT FileObject; // [rsp+80h] [rbp-80h] BYREF
  void *FileHandle; // [rsp+88h] [rbp-78h] BYREF
  ULONG LengthReturned; // [rsp+90h] [rbp-70h] BYREF
  UNICODE_STRING String1; // [rsp+98h] [rbp-68h] BYREF
  UNICODE_STRING String2; // [rsp+A8h] [rbp-58h] BYREF
  UNICODE_STRING v29; // [rsp+B8h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v31; // [rsp+100h] [rbp+0h]
  void *v32; // [rsp+108h] [rbp+8h]
  PFILE_OBJECT v33; // [rsp+110h] [rbp+10h]
  unsigned int v34; // [rsp+118h] [rbp+18h]
  char v35; // [rsp+11Ch] [rbp+1Ch]
  char v36; // [rsp+11Dh] [rbp+1Dh]
  __int16 v37; // [rsp+11Eh] [rbp+1Eh]
  __int64 (__fastcall *v38)(_QWORD, _QWORD, _QWORD, _QWORD); // [rsp+120h] [rbp+20h]
  __int64 (__fastcall *v39)(_QWORD, _QWORD, _QWORD, _QWORD); // [rsp+128h] [rbp+28h]
  __int64 v40; // [rsp+130h] [rbp+30h]
  __int64 Parameter; // [rsp+138h] [rbp+38h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+140h] [rbp+40h] BYREF

  v9 = *(struct _FLT_INSTANCE **)(a1 + 32);
  v10 = 0;
  String2.Buffer = L".";
  *(_QWORD *)&String2.Length = 262146;
  v29.Buffer = L"..";
  v11 = a4 & 0x10;
  *(_QWORD *)&v29.Length = 393220;
  FileHandle = 0;
  v13 = a1;
  FileObject = 0;
  if ( a7 )
  {
    v10 = a7(a1, a3, a4, a9);
    if ( v10 < 0 )
    {
      if ( a5 )
      {
        Pool2 = 0;
        if ( !v11 )
          goto LABEL_10;
LABEL_9:
        if ( a6 )
          goto LABEL_10;
        goto LABEL_3;
      }
    }
  }
  Pool2 = 0;
  if ( v11 )
  {
    LOBYTE(RestartScan) = 1;
LABEL_20:
    LengthReturned = 0;
    if ( !Pool2 )
    {
      Pool2 = (unsigned int *)ExAllocatePool2(256, 1024, 1683125064);
      if ( !Pool2 )
      {
        HsmDbgBreakOnStatus(3221225626LL);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqd(
            WPP_GLOBAL_Control->AttachedDevice,
            41,
            WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids,
            v9,
            a3,
            -1073741670);
        }
        v13 = a1;
        if ( v10 >= 0 )
          v10 = -1073741670;
        goto LABEL_9;
      }
    }
    v17 = (unsigned int)FltQueryDirectoryFile(
                          v9,
                          a3,
                          Pool2,
                          0x400u,
                          FileDirectoryInformation,
                          0,
                          0,
                          (BOOLEAN)RestartScan,
                          &LengthReturned);
    HsmDbgBreakOnStatus(v17);
    if ( (_DWORD)v17 != -2147483642 )
    {
      if ( (int)v17 >= 0 )
      {
        RestartScan = Pool2;
        while ( 1 )
        {
          if ( !RestartScan )
            goto LABEL_20;
          *(_QWORD *)&String1.Length = 0;
          memset(&ObjectAttributes, 0, 44);
          String1.Buffer = (PWSTR)(RestartScan + 16);
          IoStatusBlock = 0;
          String1.Length = *((_WORD *)RestartScan + 30);
          String1.MaximumLength = *((_WORD *)RestartScan + 30);
          v19 = RestartScan[14];
          if ( !RtlEqualUnicodeString(&String1, &String2, 0) && !RtlEqualUnicodeString(&String1, &v29, 0) )
            break;
LABEL_30:
          if ( FileHandle )
          {
            FltClose(FileHandle);
            FileHandle = 0;
          }
          if ( FileObject )
          {
            ObfDereferenceObject(FileObject);
            FileObject = 0;
          }
          v21 = *RestartScan;
          if ( (_DWORD)v21 )
            RestartScan = (unsigned int *)((char *)RestartScan + v21);
          else
            RestartScan = 0;
        }
        ObjectAttributes.RootDirectory = a2;
        ObjectAttributes.ObjectName = &String1;
        ObjectAttributes.Length = 48;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v20 = FltCreateFileEx(
                Filter,
                v9,
                &FileHandle,
                &FileObject,
                (v19 & 0x10 | 0x1001800) >> 4,
                &ObjectAttributes,
                &IoStatusBlock,
                0,
                0,
                7u,
                1u,
                0x200020u,
                0,
                0,
                0x800u);
        HsmDbgBreakOnStatus((unsigned int)v20);
        if ( v20 < 0 )
        {
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
LABEL_48:
            if ( v10 >= 0 )
              v10 = v20;
            if ( a5 )
              goto LABEL_64;
            goto LABEL_30;
          }
          v23 = 43;
        }
        else
        {
          v35 = a5;
          v37 = 0;
          Parameter = 0;
          v31 = a1;
          v32 = FileHandle;
          v33 = FileObject;
          v34 = RestartScan[14];
          v38 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))a7;
          v39 = a8;
          v40 = a9;
          v36 = 0;
          v20 = HsmExpandKernelStackAndCallout(HsmpRecurseDirectoryCallout, &Parameter);
          HsmDbgBreakOnStatus((unsigned int)v20);
          if ( v20 >= 0 )
            goto LABEL_30;
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_48;
          }
          v23 = 44;
        }
        WPP_SF_d(v22->AttachedDevice, v23, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, (unsigned int)v20);
        goto LABEL_48;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, v9, a3, v17);
      }
      if ( v10 >= 0 )
        v10 = v17;
    }
LABEL_64:
    v13 = a1;
    goto LABEL_9;
  }
LABEL_3:
  if ( v10 >= 0 || !a5 )
  {
    if ( a8 )
    {
      v15 = a8(v13, a3, a4, a9);
      if ( v10 >= 0 )
        v10 = v15;
    }
  }
LABEL_10:
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x64527348u);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400779f4  mov     rax, rsp
0x1400779f7  mov     [rax+18h], rbx
0x1400779fb  mov     [rax+20h], r9d
0x1400779ff  mov     [rax+10h], rdx
0x140077a03  mov     [rax+8], rcx
0x140077a07  push    rbp
0x140077a08  push    rsi
0x140077a09  push    rdi
0x140077a0a  push    r12
0x140077a0c  push    r13
0x140077a0e  push    r14
0x140077a10  push    r15
0x140077a12  lea     rbp, [rsp-50h]
0x140077a17  sub     rsp, 150h
0x140077a1e  mov     r13, [rcx+20h]
0x140077a22  lea     rax, asc_1400208B8; "."
0x140077a29  mov     r15b, [rbp+80h+arg_20]
0x140077a30  xor     ebx, ebx
0x140077a32  mov     [rbp+80h+String2.Buffer], rax
0x140077a36  mov     edi, r9d
0x140077a39  lea     rax, asc_1400208B0; ".."
0x140077a40  mov     qword ptr [rbp+80h+String2.Length], 40002h
0x140077a48  mov     [rbp+80h+var_C8.Buffer], rax
0x140077a4c  and     edi, 10h
0x140077a4f  mov     rax, [rbp+80h+arg_30]
0x140077a56  mov     r10d, r9d
0x140077a59  mov     qword ptr [rbp+80h+var_C8.Length], 60004h
0x140077a61  mov     r12, r8
0x140077a64  mov     [rbp+80h+FileHandle], rbx
0x140077a68  mov     r14, rcx
0x140077a6b  mov     [rbp+80h+FileObject], rbx
0x140077a6f  test    rax, rax
0x140077a72  jnz     loc_140077B18
0x140077a78  xor     esi, esi
0x140077a7a  test    edi, edi
0x140077a7c  jnz     loc_140077DD4
0x140077a82  test    ebx, ebx
0x140077a84  js      loc_140077F06
0x140077a8a  mov     rax, [rbp+80h+arg_38]
0x140077a91  test    rax, rax
0x140077a94  jz      short loc_140077AC5
0x140077a96  mov     r9, [rbp+80h+arg_40]
0x140077a9d  mov     rdx, r12
0x140077aa0  mov     r8d, [rbp+80h+arg_18]
0x140077aa7  mov     rcx, r14
0x140077aaa  call    _guard_dispatch_icall
0x140077aaf  test    ebx, ebx
0x140077ab1  cmovns  ebx, eax
0x140077ab4  jmp     short loc_140077AC5
0x140077ab6  xor     esi, esi
0x140077ab8  test    edi, edi
0x140077aba  jz      short loc_140077AC5
0x140077abc  cmp     [rbp+80h+arg_28], 0
0x140077ac3  jz      short loc_140077A82
0x140077ac5  mov     rcx, [rbp+80h+FileObject]; Object
0x140077ac9  test    rcx, rcx
0x140077acc  jnz     loc_140077F14
0x140077ad2  mov     rcx, [rbp+80h+FileHandle]; FileHandle
0x140077ad6  test    rcx, rcx
0x140077ad9  jnz     loc_140077F25
0x140077adf  test    rsi, rsi
0x140077ae2  jnz     short loc_140077B02
0x140077ae4  mov     eax, ebx
0x140077ae6  mov     rbx, [rsp+180h+arg_10]
0x140077aee  add     rsp, 150h
0x140077af5  pop     r15
0x140077af7  pop     r14
0x140077af9  pop     r13
0x140077afb  pop     r12
0x140077afd  pop     rdi
0x140077afe  pop     rsi
0x140077aff  pop     rbp
0x140077b00  retn
0x140077b02  mov     edx, 64527348h; Tag
0x140077b07  mov     rcx, rsi; P
0x140077b0a  call    cs:__imp_ExFreePoolWithTag
0x140077b11  nop     dword ptr [rax+rax+00h]
0x140077b16  jmp     short loc_140077AE4
0x140077b18  mov     r9, [rbp+80h+arg_40]
0x140077b1f  mov     r8d, r10d
0x140077b22  mov     rdx, r12
0x140077b25  call    _guard_dispatch_icall
0x140077b2a  mov     ebx, eax
0x140077b2c  test    eax, eax
0x140077b2e  jns     loc_140077A78
0x140077b34  test    r15b, r15b
0x140077b37  jz      loc_140077A78
0x140077b3d  jmp     loc_140077AB6
0x140077b42  mov     [rbp+80h+var_F0], 0
0x140077b49  test    rsi, rsi
0x140077b4c  jnz     short loc_140077B76
0x140077b4e  mov     edx, 400h
0x140077b53  mov     ecx, 100h
0x140077b58  mov     r8d, 64527348h
0x140077b5e  call    cs:__imp_ExAllocatePool2
0x140077b65  nop     dword ptr [rax+rax+00h]
0x140077b6a  mov     rsi, rax
0x140077b6d  test    rax, rax
0x140077b70  jz      loc_140077E51
0x140077b76  lea     rax, [rbp+80h+var_F0]
0x140077b7a  mov     r9d, 400h; Length
0x140077b80  mov     [rsp+180h+LengthReturned], rax; LengthReturned
0x140077b85  mov     r8, rsi; FileInformation
0x140077b88  mov     [rsp+180h+RestartScan], dil; RestartScan
0x140077b8d  mov     rdx, r12; FileObject
0x140077b90  mov     [rsp+180h+FileName], 0; FileName
0x140077b99  mov     rcx, r13; Instance
0x140077b9c  mov     [rsp+180h+ReturnSingleEntry], 0; ReturnSingleEntry
0x140077ba1  mov     [rsp+180h+FileInformationClass], 1; FileInformationClass
0x140077ba9  call    cs:__imp_FltQueryDirectoryFile
0x140077bb0  nop     dword ptr [rax+rax+00h]
0x140077bb5  mov     ecx, eax
0x140077bb7  mov     edi, eax
0x140077bb9  call    HsmDbgBreakOnStatus
0x140077bbe  cmp     edi, 80000006h
0x140077bc4  jz      loc_140077EFA
0x140077bca  test    edi, edi
0x140077bcc  js      loc_140077EB4
0x140077bd2  mov     rdi, rsi
0x140077bd5  test    rdi, rdi
0x140077bd8  jz      loc_140077DCF
0x140077bde  mov     qword ptr [rbp+80h+String1.Length], 0
0x140077be6  lea     rdx, [rbp+80h+String2]; String2
0x140077bea  xorps   xmm0, xmm0
0x140077bed  lea     rcx, [rbp+80h+String1]; String1
0x140077bf1  movups  xmmword ptr [rbp+80h+ObjectAttributes.ObjectName], xmm0
0x140077bf5  xor     eax, eax
0x140077bf7  xor     r8d, r8d; CaseInSensitive
0x140077bfa  movups  xmmword ptr [rbp+80h+ObjectAttributes.Length], xmm0
0x140077bfe  lea     rax, [rdi+40h]
0x140077c02  mov     [rbp+80h+String1.Buffer], rax
0x140077c06  movups  xmmword ptr [rbp+80h+ObjectAttributes+1Ch], xmm0
0x140077c0a  movups  xmmword ptr [rbp+80h+IoStatusBlock], xmm0
0x140077c0e  movzx   eax, word ptr [rdi+3Ch]
0x140077c12  mov     [rbp+80h+String1.Length], ax
0x140077c16  movzx   eax, word ptr [rdi+3Ch]
0x140077c1a  mov     [rbp+80h+String1.MaximumLength], ax
0x140077c1e  mov     r14d, [rdi+38h]
0x140077c22  call    cs:__imp_RtlEqualUnicodeString
0x140077c29  nop     dword ptr [rax+rax+00h]
0x140077c2e  test    al, al
0x140077c30  jnz     loc_140077D80
0x140077c36  xor     r8d, r8d; CaseInSensitive
0x140077c39  lea     rdx, [rbp+80h+var_C8]; String2
0x140077c3d  lea     rcx, [rbp+80h+String1]; String1
0x140077c41  call    cs:__imp_RtlEqualUnicodeString
0x140077c48  nop     dword ptr [rax+rax+00h]
0x140077c4d  xor     ecx, ecx
0x140077c4f  test    al, al
0x140077c51  jnz     loc_140077D80
0x140077c57  mov     rax, [rbp+80h+arg_8]
0x140077c5e  lea     r9, [rbp+80h+FileObject]; FileObject
0x140077c62  mov     [rsp+180h+Flags], 800h; Flags
0x140077c6a  lea     r8, [rbp+80h+FileHandle]; FileHandle
0x140077c6e  mov     [rsp+180h+EaLength], ecx; EaLength
0x140077c72  and     r14d, 10h
0x140077c76  mov     [rsp+180h+EaBuffer], rcx; EaBuffer
0x140077c7b  xorps   xmm0, xmm0
0x140077c7e  mov     [rsp+180h+CreateOptions], 200020h; CreateOptions
0x140077c86  or      r14d, 1001800h
0x140077c8d  mov     [rsp+180h+CreateDisposition], 1; CreateDisposition
0x140077c95  mov     rdx, r13; Instance
0x140077c98  mov     [rsp+180h+ShareAccess], 7; ShareAccess
0x140077ca0  mov     dword ptr [rsp+180h+LengthReturned], ecx; FileAttributes
0x140077ca4  mov     qword ptr [rsp+180h+RestartScan], rcx; AllocationSize
0x140077ca9  mov     rcx, cs:Filter; Filter
0x140077cb0  mov     [rbp+80h+ObjectAttributes.RootDirectory], rax
0x140077cb4  lea     rax, [rbp+80h+String1]
0x140077cb8  mov     [rbp+80h+ObjectAttributes.ObjectName], rax
0x140077cbc  lea     rax, [rbp+80h+IoStatusBlock]
0x140077cc0  mov     [rsp+180h+FileName], rax; IoStatusBlock
0x140077cc5  lea     rax, [rbp+80h+ObjectAttributes]
0x140077cc9  mov     qword ptr [rsp+180h+ReturnSingleEntry], rax; ObjectAttributes
0x140077cce  shr     r14d, 4
0x140077cd2  mov     [rsp+180h+FileInformationClass], r14d; DesiredAccess
0x140077cd7  mov     [rbp+80h+ObjectAttributes.Length], 30h ; '0'
0x140077cde  mov     [rbp+80h+ObjectAttributes.Attributes], 240h
0x140077ce5  movdqu  xmmword ptr [rbp+80h+ObjectAttributes.SecurityDescriptor], xmm0
0x140077cea  call    cs:__imp_FltCreateFileEx
0x140077cf1  nop     dword ptr [rax+rax+00h]
0x140077cf6  mov     ecx, eax
0x140077cf8  mov     r14d, eax
0x140077cfb  call    HsmDbgBreakOnStatus
0x140077d00  test    r14d, r14d
0x140077d03  js      loc_140077DDC
0x140077d09  xor     eax, eax
0x140077d0b  mov     [rbp+80h+var_64], r15b
0x140077d0f  mov     [rbp+80h+var_62], ax
0x140077d13  lea     rdx, [rbp+80h+Parameter]; Parameter
0x140077d17  mov     [rbp+80h+Parameter], rax
0x140077d1b  lea     rcx, HsmpRecurseDirectoryCallout; Callout
0x140077d22  mov     rax, [rbp+80h+arg_0]
0x140077d29  mov     [rbp+80h+var_80], rax
0x140077d2d  mov     rax, [rbp+80h+FileHandle]
0x140077d31  mov     [rbp+80h+var_78], rax
0x140077d35  mov     rax, [rbp+80h+FileObject]
0x140077d39  mov     [rbp+80h+var_70], rax
0x140077d3d  mov     eax, [rdi+38h]
0x140077d40  mov     [rbp+80h+var_68], eax
0x140077d43  mov     rax, [rbp+80h+arg_30]
0x140077d4a  mov     [rbp+80h+var_60], rax
0x140077d4e  mov     rax, [rbp+80h+arg_38]
0x140077d55  mov     [rbp+80h+var_58], rax
0x140077d59  mov     rax, [rbp+80h+arg_40]
0x140077d60  mov     [rbp+80h+var_50], rax
0x140077d64  mov     [rbp+80h+var_63], 0
0x140077d68  call    HsmExpandKernelStackAndCallout
0x140077d6d  mov     ecx, eax
0x140077d6f  mov     r14d, eax
0x140077d72  call    HsmDbgBreakOnStatus
0x140077d77  test    r14d, r14d
0x140077d7a  js      loc_140077E04
0x140077d80  mov     rcx, [rbp+80h+FileHandle]; FileHandle
0x140077d84  test    rcx, rcx
0x140077d87  jz      short loc_140077D9D
0x140077d89  call    cs:__imp_FltClose
0x140077d90  nop     dword ptr [rax+rax+00h]
0x140077d95  mov     [rbp+80h+FileHandle], 0
0x140077d9d  mov     rcx, [rbp+80h+FileObject]; Object
0x140077da1  test    rcx, rcx
0x140077da4  jz      short loc_140077DBA
0x140077da6  call    cs:__imp_ObfDereferenceObject
0x140077dad  nop     dword ptr [rax+rax+00h]
0x140077db2  mov     [rbp+80h+FileObject], 0
0x140077dba  mov     eax, [rdi]
0x140077dbc  test    eax, eax
0x140077dbe  jz      short loc_140077DC8
0x140077dc0  add     rdi, rax
0x140077dc3  jmp     loc_140077BD5
0x140077dc8  xor     edi, edi
0x140077dca  jmp     loc_140077BD5
0x140077dcf  jmp     loc_140077B42
0x140077dd4  mov     dil, 1
0x140077dd7  jmp     loc_140077B42
0x140077ddc  mov     rcx, cs:WPP_GLOBAL_Control
0x140077de3  lea     rax, WPP_GLOBAL_Control
0x140077dea  cmp     rcx, rax
0x140077ded  jz      short loc_140077E3D
0x140077def  mov     edx, [rcx+2Ch]
0x140077df2  test    dl, 8
0x140077df5  jz      short loc_140077E3D
0x140077df7  cmp     byte ptr [rcx+29h], 2
0x140077dfb  jb      short loc_140077E3D
0x140077dfd  mov     edx, 2Bh ; '+'
0x140077e02  jmp     short loc_140077E2A
0x140077e04  mov     rcx, cs:WPP_GLOBAL_Control
0x140077e0b  lea     rax, WPP_GLOBAL_Control
0x140077e12  cmp     rcx, rax
0x140077e15  jz      short loc_140077E3D
0x140077e17  mov     edx, [rcx+2Ch]
0x140077e1a  test    dl, 8
0x140077e1d  jz      short loc_140077E3D
0x140077e1f  cmp     byte ptr [rcx+29h], 2
0x140077e23  jb      short loc_140077E3D
0x140077e25  mov     edx, 2Ch ; ','
0x140077e2a  mov     rcx, [rcx+18h]
0x140077e2e  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x140077e35  mov     r9d, r14d
0x140077e38  call    WPP_SF_d
0x140077e3d  test    ebx, ebx
0x140077e3f  cmovns  ebx, r14d
0x140077e43  test    r15b, r15b
0x140077e46  jnz     loc_140077EFA
0x140077e4c  jmp     loc_140077D80
0x140077e51  mov     edi, 0C000009Ah
0x140077e56  mov     ecx, edi
0x140077e58  call    HsmDbgBreakOnStatus
0x140077e5d  mov     rcx, cs:WPP_GLOBAL_Control
0x140077e64  lea     rax, WPP_GLOBAL_Control
0x140077e6b  cmp     rcx, rax
0x140077e6e  jz      short loc_140077E9E
0x140077e70  mov     eax, [rcx+2Ch]
0x140077e73  test    al, 8
0x140077e75  jz      short loc_140077E9E
0x140077e77  cmp     byte ptr [rcx+29h], 2
0x140077e7b  jb      short loc_140077E9E
0x140077e7d  mov     rcx, [rcx+18h]
0x140077e81  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x140077e88  mov     edx, 29h ; ')'
0x140077e8d  mov     dword ptr [rsp+180h+ReturnSingleEntry], edi
0x140077e91  mov     r9, r13
0x140077e94  mov     qword ptr [rsp+180h+FileInformationClass], r12
0x140077e99  call    WPP_SF_qqd
0x140077e9e  mov     r14, [rbp+80h+arg_0]
0x140077ea5  test    ebx, ebx
0x140077ea7  js      loc_140077ABC
0x140077ead  mov     ebx, edi
0x140077eaf  jmp     loc_140077ABC
0x140077eb4  mov     rcx, cs:WPP_GLOBAL_Control
0x140077ebb  lea     rax, WPP_GLOBAL_Control
0x140077ec2  cmp     rcx, rax
0x140077ec5  jz      short loc_140077EF5
0x140077ec7  mov     eax, [rcx+2Ch]
0x140077eca  test    al, 8
0x140077ecc  jz      short loc_140077EF5
0x140077ece  cmp     byte ptr [rcx+29h], 2
0x140077ed2  jb      short loc_140077EF5
0x140077ed4  mov     rcx, [rcx+18h]
0x140077ed8  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x140077edf  mov     edx, 2Ah ; '*'
  ... truncated ...
```
