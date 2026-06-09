# HsmpRecurseDirectory

- ea: `0x140077b34`
- end: `0x140078076`
- name: `HsmpRecurseDirectory`
- size: `1346`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140050e90`
- `0x140054bbc`
- `0x140055abc`
- `0x140077ad0`

## callees

- `0x140003c50`
- `0x140008b74`
- `0x140009300`
- `0x14000d95c`
- `0x14001e2a0`
- `0x140077b34`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140077d62`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140077d81`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140077d62`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140077d81`
- `ntoskrnl!ObfDereferenceObject` at `0x140077ee6`
- `ntoskrnl!ObfDereferenceObject` at `0x140078054`
- `ntoskrnl!ObfDereferenceObject` at `0x140077ee6`
- `ntoskrnl!ObfDereferenceObject` at `0x140078054`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077c4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077c4a`
- `ntoskrnl!ExAllocatePool2` at `0x140077c9e`
- `ntoskrnl!ExAllocatePool2` at `0x140077c9e`
- `FLTMGR!FltCreateFileEx` at `0x140077e2a`
- `FLTMGR!FltCreateFileEx` at `0x140077e2a`
- `FLTMGR!FltClose` at `0x140077ec9`
- `FLTMGR!FltClose` at `0x140078065`
- `FLTMGR!FltClose` at `0x140077ec9`
- `FLTMGR!FltClose` at `0x140078065`
- `FLTMGR!FltQueryDirectoryFile` at `0x140077ce9`
- `FLTMGR!FltQueryDirectoryFile` at `0x140077ce9`

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
  NTSTATUS v17; // edi
  unsigned int *RestartScan; // rdi
  unsigned int v19; // r14d
  int v20; // r14d
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
        HsmDbgBreakOnStatus(-1073741670);
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
    v17 = FltQueryDirectoryFile(
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
    if ( v17 != -2147483642 )
    {
      if ( v17 >= 0 )
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
        HsmDbgBreakOnStatus(v20);
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
          v20 = HsmExpandKernelStackAndCallout(HsmpRecurseDirectoryCallout, (NTSTATUS *)&Parameter);
          HsmDbgBreakOnStatus(v20);
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
0x140077b34  mov     rax, rsp
0x140077b37  mov     [rax+18h], rbx
0x140077b3b  mov     [rax+20h], r9d
0x140077b3f  mov     [rax+10h], rdx
0x140077b43  mov     [rax+8], rcx
0x140077b47  push    rbp
0x140077b48  push    rsi
0x140077b49  push    rdi
0x140077b4a  push    r12
0x140077b4c  push    r13
0x140077b4e  push    r14
0x140077b50  push    r15
0x140077b52  lea     rbp, [rsp-50h]
0x140077b57  sub     rsp, 150h
0x140077b5e  mov     r13, [rcx+20h]
0x140077b62  lea     rax, asc_1400208B8; "."
0x140077b69  mov     r15b, [rbp+80h+arg_20]
0x140077b70  xor     ebx, ebx
0x140077b72  mov     [rbp+80h+String2.Buffer], rax
0x140077b76  mov     edi, r9d
0x140077b79  lea     rax, asc_1400208B0; ".."
0x140077b80  mov     qword ptr [rbp+80h+String2.Length], 40002h
0x140077b88  mov     [rbp+80h+var_C8.Buffer], rax
0x140077b8c  and     edi, 10h
0x140077b8f  mov     rax, [rbp+80h+arg_30]
0x140077b96  mov     r10d, r9d
0x140077b99  mov     qword ptr [rbp+80h+var_C8.Length], 60004h
0x140077ba1  mov     r12, r8
0x140077ba4  mov     [rbp+80h+FileHandle], rbx
0x140077ba8  mov     r14, rcx
0x140077bab  mov     [rbp+80h+FileObject], rbx
0x140077baf  test    rax, rax
0x140077bb2  jnz     loc_140077C58
0x140077bb8  xor     esi, esi
0x140077bba  test    edi, edi
0x140077bbc  jnz     loc_140077F14
0x140077bc2  test    ebx, ebx
0x140077bc4  js      loc_140078046
0x140077bca  mov     rax, [rbp+80h+arg_38]
0x140077bd1  test    rax, rax
0x140077bd4  jz      short loc_140077C05
0x140077bd6  mov     r9, [rbp+80h+arg_40]
0x140077bdd  mov     rdx, r12
0x140077be0  mov     r8d, [rbp+80h+arg_18]
0x140077be7  mov     rcx, r14
0x140077bea  call    _guard_dispatch_icall
0x140077bef  test    ebx, ebx
0x140077bf1  cmovns  ebx, eax
0x140077bf4  jmp     short loc_140077C05
0x140077bf6  xor     esi, esi
0x140077bf8  test    edi, edi
0x140077bfa  jz      short loc_140077C05
0x140077bfc  cmp     [rbp+80h+arg_28], 0
0x140077c03  jz      short loc_140077BC2
0x140077c05  mov     rcx, [rbp+80h+FileObject]; Object
0x140077c09  test    rcx, rcx
0x140077c0c  jnz     loc_140078054
0x140077c12  mov     rcx, [rbp+80h+FileHandle]; FileHandle
0x140077c16  test    rcx, rcx
0x140077c19  jnz     loc_140078065
0x140077c1f  test    rsi, rsi
0x140077c22  jnz     short loc_140077C42
0x140077c24  mov     eax, ebx
0x140077c26  mov     rbx, [rsp+180h+arg_10]
0x140077c2e  add     rsp, 150h
0x140077c35  pop     r15
0x140077c37  pop     r14
0x140077c39  pop     r13
0x140077c3b  pop     r12
0x140077c3d  pop     rdi
0x140077c3e  pop     rsi
0x140077c3f  pop     rbp
0x140077c40  retn
0x140077c42  mov     edx, 64527348h; Tag
0x140077c47  mov     rcx, rsi; P
0x140077c4a  call    cs:__imp_ExFreePoolWithTag
0x140077c51  nop     dword ptr [rax+rax+00h]
0x140077c56  jmp     short loc_140077C24
0x140077c58  mov     r9, [rbp+80h+arg_40]
0x140077c5f  mov     r8d, r10d
0x140077c62  mov     rdx, r12
0x140077c65  call    _guard_dispatch_icall
0x140077c6a  mov     ebx, eax
0x140077c6c  test    eax, eax
0x140077c6e  jns     loc_140077BB8
0x140077c74  test    r15b, r15b
0x140077c77  jz      loc_140077BB8
0x140077c7d  jmp     loc_140077BF6
0x140077c82  mov     [rbp+80h+var_F0], 0
0x140077c89  test    rsi, rsi
0x140077c8c  jnz     short loc_140077CB6
0x140077c8e  mov     edx, 400h
0x140077c93  mov     ecx, 100h
0x140077c98  mov     r8d, 64527348h
0x140077c9e  call    cs:__imp_ExAllocatePool2
0x140077ca5  nop     dword ptr [rax+rax+00h]
0x140077caa  mov     rsi, rax
0x140077cad  test    rax, rax
0x140077cb0  jz      loc_140077F91
0x140077cb6  lea     rax, [rbp+80h+var_F0]
0x140077cba  mov     r9d, 400h; Length
0x140077cc0  mov     [rsp+180h+LengthReturned], rax; LengthReturned
0x140077cc5  mov     r8, rsi; FileInformation
0x140077cc8  mov     [rsp+180h+RestartScan], dil; RestartScan
0x140077ccd  mov     rdx, r12; FileObject
0x140077cd0  mov     [rsp+180h+FileName], 0; FileName
0x140077cd9  mov     rcx, r13; Instance
0x140077cdc  mov     [rsp+180h+ReturnSingleEntry], 0; ReturnSingleEntry
0x140077ce1  mov     [rsp+180h+FileInformationClass], 1; FileInformationClass
0x140077ce9  call    cs:__imp_FltQueryDirectoryFile
0x140077cf0  nop     dword ptr [rax+rax+00h]
0x140077cf5  mov     ecx, eax
0x140077cf7  mov     edi, eax
0x140077cf9  call    HsmDbgBreakOnStatus
0x140077cfe  cmp     edi, 80000006h
0x140077d04  jz      loc_14007803A
0x140077d0a  test    edi, edi
0x140077d0c  js      loc_140077FF4
0x140077d12  mov     rdi, rsi
0x140077d15  test    rdi, rdi
0x140077d18  jz      loc_140077F0F
0x140077d1e  mov     qword ptr [rbp+80h+String1.Length], 0
0x140077d26  lea     rdx, [rbp+80h+String2]; String2
0x140077d2a  xorps   xmm0, xmm0
0x140077d2d  lea     rcx, [rbp+80h+String1]; String1
0x140077d31  movups  xmmword ptr [rbp+80h+ObjectAttributes.ObjectName], xmm0
0x140077d35  xor     eax, eax
0x140077d37  xor     r8d, r8d; CaseInSensitive
0x140077d3a  movups  xmmword ptr [rbp+80h+ObjectAttributes.Length], xmm0
0x140077d3e  lea     rax, [rdi+40h]
0x140077d42  mov     [rbp+80h+String1.Buffer], rax
0x140077d46  movups  xmmword ptr [rbp+80h+ObjectAttributes+1Ch], xmm0
0x140077d4a  movups  xmmword ptr [rbp+80h+IoStatusBlock], xmm0
0x140077d4e  movzx   eax, word ptr [rdi+3Ch]
0x140077d52  mov     [rbp+80h+String1.Length], ax
0x140077d56  movzx   eax, word ptr [rdi+3Ch]
0x140077d5a  mov     [rbp+80h+String1.MaximumLength], ax
0x140077d5e  mov     r14d, [rdi+38h]
0x140077d62  call    cs:__imp_RtlEqualUnicodeString
0x140077d69  nop     dword ptr [rax+rax+00h]
0x140077d6e  test    al, al
0x140077d70  jnz     loc_140077EC0
0x140077d76  xor     r8d, r8d; CaseInSensitive
0x140077d79  lea     rdx, [rbp+80h+var_C8]; String2
0x140077d7d  lea     rcx, [rbp+80h+String1]; String1
0x140077d81  call    cs:__imp_RtlEqualUnicodeString
0x140077d88  nop     dword ptr [rax+rax+00h]
0x140077d8d  xor     ecx, ecx
0x140077d8f  test    al, al
0x140077d91  jnz     loc_140077EC0
0x140077d97  mov     rax, [rbp+80h+arg_8]
0x140077d9e  lea     r9, [rbp+80h+FileObject]; FileObject
0x140077da2  mov     [rsp+180h+Flags], 800h; Flags
0x140077daa  lea     r8, [rbp+80h+FileHandle]; FileHandle
0x140077dae  mov     [rsp+180h+EaLength], ecx; EaLength
0x140077db2  and     r14d, 10h
0x140077db6  mov     [rsp+180h+EaBuffer], rcx; EaBuffer
0x140077dbb  xorps   xmm0, xmm0
0x140077dbe  mov     [rsp+180h+CreateOptions], 200020h; CreateOptions
0x140077dc6  or      r14d, 1001800h
0x140077dcd  mov     [rsp+180h+CreateDisposition], 1; CreateDisposition
0x140077dd5  mov     rdx, r13; Instance
0x140077dd8  mov     [rsp+180h+ShareAccess], 7; ShareAccess
0x140077de0  mov     dword ptr [rsp+180h+LengthReturned], ecx; FileAttributes
0x140077de4  mov     qword ptr [rsp+180h+RestartScan], rcx; AllocationSize
0x140077de9  mov     rcx, cs:Filter; Filter
0x140077df0  mov     [rbp+80h+ObjectAttributes.RootDirectory], rax
0x140077df4  lea     rax, [rbp+80h+String1]
0x140077df8  mov     [rbp+80h+ObjectAttributes.ObjectName], rax
0x140077dfc  lea     rax, [rbp+80h+IoStatusBlock]
0x140077e00  mov     [rsp+180h+FileName], rax; IoStatusBlock
0x140077e05  lea     rax, [rbp+80h+ObjectAttributes]
0x140077e09  mov     qword ptr [rsp+180h+ReturnSingleEntry], rax; ObjectAttributes
0x140077e0e  shr     r14d, 4
0x140077e12  mov     [rsp+180h+FileInformationClass], r14d; DesiredAccess
0x140077e17  mov     [rbp+80h+ObjectAttributes.Length], 30h ; '0'
0x140077e1e  mov     [rbp+80h+ObjectAttributes.Attributes], 240h
0x140077e25  movdqu  xmmword ptr [rbp+80h+ObjectAttributes.SecurityDescriptor], xmm0
0x140077e2a  call    cs:__imp_FltCreateFileEx
0x140077e31  nop     dword ptr [rax+rax+00h]
0x140077e36  mov     ecx, eax
0x140077e38  mov     r14d, eax
0x140077e3b  call    HsmDbgBreakOnStatus
0x140077e40  test    r14d, r14d
0x140077e43  js      loc_140077F1C
0x140077e49  xor     eax, eax
0x140077e4b  mov     [rbp+80h+var_64], r15b
0x140077e4f  mov     [rbp+80h+var_62], ax
0x140077e53  lea     rdx, [rbp+80h+Parameter]; Parameter
0x140077e57  mov     [rbp+80h+Parameter], rax
0x140077e5b  lea     rcx, HsmpRecurseDirectoryCallout; Callout
0x140077e62  mov     rax, [rbp+80h+arg_0]
0x140077e69  mov     [rbp+80h+var_80], rax
0x140077e6d  mov     rax, [rbp+80h+FileHandle]
0x140077e71  mov     [rbp+80h+var_78], rax
0x140077e75  mov     rax, [rbp+80h+FileObject]
0x140077e79  mov     [rbp+80h+var_70], rax
0x140077e7d  mov     eax, [rdi+38h]
0x140077e80  mov     [rbp+80h+var_68], eax
0x140077e83  mov     rax, [rbp+80h+arg_30]
0x140077e8a  mov     [rbp+80h+var_60], rax
0x140077e8e  mov     rax, [rbp+80h+arg_38]
0x140077e95  mov     [rbp+80h+var_58], rax
0x140077e99  mov     rax, [rbp+80h+arg_40]
0x140077ea0  mov     [rbp+80h+var_50], rax
0x140077ea4  mov     [rbp+80h+var_63], 0
0x140077ea8  call    HsmExpandKernelStackAndCallout
0x140077ead  mov     ecx, eax
0x140077eaf  mov     r14d, eax
0x140077eb2  call    HsmDbgBreakOnStatus
0x140077eb7  test    r14d, r14d
0x140077eba  js      loc_140077F44
0x140077ec0  mov     rcx, [rbp+80h+FileHandle]; FileHandle
0x140077ec4  test    rcx, rcx
0x140077ec7  jz      short loc_140077EDD
0x140077ec9  call    cs:__imp_FltClose
0x140077ed0  nop     dword ptr [rax+rax+00h]
0x140077ed5  mov     [rbp+80h+FileHandle], 0
0x140077edd  mov     rcx, [rbp+80h+FileObject]; Object
0x140077ee1  test    rcx, rcx
0x140077ee4  jz      short loc_140077EFA
0x140077ee6  call    cs:__imp_ObfDereferenceObject
0x140077eed  nop     dword ptr [rax+rax+00h]
0x140077ef2  mov     [rbp+80h+FileObject], 0
0x140077efa  mov     eax, [rdi]
0x140077efc  test    eax, eax
0x140077efe  jz      short loc_140077F08
0x140077f00  add     rdi, rax
0x140077f03  jmp     loc_140077D15
0x140077f08  xor     edi, edi
0x140077f0a  jmp     loc_140077D15
0x140077f0f  jmp     loc_140077C82
0x140077f14  mov     dil, 1
0x140077f17  jmp     loc_140077C82
0x140077f1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140077f23  lea     rax, WPP_GLOBAL_Control
0x140077f2a  cmp     rcx, rax
0x140077f2d  jz      short loc_140077F7D
0x140077f2f  mov     edx, [rcx+2Ch]
0x140077f32  test    dl, 8
0x140077f35  jz      short loc_140077F7D
0x140077f37  cmp     byte ptr [rcx+29h], 2
0x140077f3b  jb      short loc_140077F7D
0x140077f3d  mov     edx, 2Bh ; '+'
0x140077f42  jmp     short loc_140077F6A
0x140077f44  mov     rcx, cs:WPP_GLOBAL_Control
0x140077f4b  lea     rax, WPP_GLOBAL_Control
0x140077f52  cmp     rcx, rax
0x140077f55  jz      short loc_140077F7D
0x140077f57  mov     edx, [rcx+2Ch]
0x140077f5a  test    dl, 8
0x140077f5d  jz      short loc_140077F7D
0x140077f5f  cmp     byte ptr [rcx+29h], 2
0x140077f63  jb      short loc_140077F7D
0x140077f65  mov     edx, 2Ch ; ','
0x140077f6a  mov     rcx, [rcx+18h]
0x140077f6e  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x140077f75  mov     r9d, r14d
0x140077f78  call    WPP_SF_d
0x140077f7d  test    ebx, ebx
0x140077f7f  cmovns  ebx, r14d
0x140077f83  test    r15b, r15b
0x140077f86  jnz     loc_14007803A
0x140077f8c  jmp     loc_140077EC0
0x140077f91  mov     edi, 0C000009Ah
0x140077f96  mov     ecx, edi
0x140077f98  call    HsmDbgBreakOnStatus
0x140077f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140077fa4  lea     rax, WPP_GLOBAL_Control
0x140077fab  cmp     rcx, rax
0x140077fae  jz      short loc_140077FDE
0x140077fb0  mov     eax, [rcx+2Ch]
0x140077fb3  test    al, 8
0x140077fb5  jz      short loc_140077FDE
0x140077fb7  cmp     byte ptr [rcx+29h], 2
0x140077fbb  jb      short loc_140077FDE
0x140077fbd  mov     rcx, [rcx+18h]
0x140077fc1  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x140077fc8  mov     edx, 29h ; ')'
0x140077fcd  mov     dword ptr [rsp+180h+ReturnSingleEntry], edi
0x140077fd1  mov     r9, r13
0x140077fd4  mov     qword ptr [rsp+180h+FileInformationClass], r12
0x140077fd9  call    WPP_SF_qqd
0x140077fde  mov     r14, [rbp+80h+arg_0]
0x140077fe5  test    ebx, ebx
0x140077fe7  js      loc_140077BFC
0x140077fed  mov     ebx, edi
0x140077fef  jmp     loc_140077BFC
0x140077ff4  mov     rcx, cs:WPP_GLOBAL_Control
0x140077ffb  lea     rax, WPP_GLOBAL_Control
0x140078002  cmp     rcx, rax
0x140078005  jz      short loc_140078035
0x140078007  mov     eax, [rcx+2Ch]
0x14007800a  test    al, 8
0x14007800c  jz      short loc_140078035
0x14007800e  cmp     byte ptr [rcx+29h], 2
0x140078012  jb      short loc_140078035
0x140078014  mov     rcx, [rcx+18h]
0x140078018  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14007801f  mov     edx, 2Ah ; '*'
  ... truncated ...
```
