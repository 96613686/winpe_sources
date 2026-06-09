# FCpRetrieveAppPairingId

- ea: `0x1400127b0`
- end: `0x140012a2c`
- name: `FCpRetrieveAppPairingId`
- size: `636`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140012310`

## callees

- `0x140003540`
- `0x1400127b0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140012a02`
- `ntoskrnl!ObfDereferenceObject` at `0x140012a02`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400128f7`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400128f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012875`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012875`
- `ntoskrnl!ExAllocatePool2` at `0x14001284e`
- `ntoskrnl!ExAllocatePool2` at `0x14001284e`
- `FLTMGR!FltCreateFileEx` at `0x14001298f`
- `FLTMGR!FltCreateFileEx` at `0x14001298f`
- `FLTMGR!FltClose` at `0x140012a1b`
- `FLTMGR!FltClose` at `0x140012a1b`
- `FLTMGR!FltReadFile` at `0x1400129db`
- `FLTMGR!FltReadFile` at `0x1400129db`
- `FLTMGR!FltGetVolumeName` at `0x14001281f`
- `FLTMGR!FltGetVolumeName` at `0x1400128da`
- `FLTMGR!FltGetVolumeName` at `0x14001281f`
- `FLTMGR!FltGetVolumeName` at `0x1400128da`

## pseudocode

```c
__int64 __fastcall FCpRetrieveAppPairingId(_QWORD *a1)
{
  struct _FLT_VOLUME *v2; // rcx
  char v3; // di
  NTSTATUS appended; // ebx
  WCHAR *Pool2; // rax
  struct _FLT_VOLUME *v7; // rcx
  struct _FLT_INSTANCE *v8; // rdx
  struct _FLT_FILTER *v9; // rcx
  struct _FLT_INSTANCE *v10; // rcx
  ULONG BufferSizeNeeded; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING VolumeName; // [rsp+88h] [rbp-78h] BYREF
  PFILE_OBJECT FileObject; // [rsp+98h] [rbp-68h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+A0h] [rbp-60h] BYREF
  void *FileHandle; // [rsp+A8h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp-20h] BYREF
  __int128 Buffer; // [rsp+F0h] [rbp-10h] BYREF
  int v19; // [rsp+100h] [rbp+0h]

  v2 = (struct _FLT_VOLUME *)a1[2];
  v19 = 0;
  ByteOffset.QuadPart = 0;
  v3 = 0;
  Buffer = 0;
  *(_QWORD *)&VolumeName.Length = 0;
  memset(&ObjectAttributes, 0, 44);
  FileObject = 0;
  IoStatusBlock = 0;
  FileHandle = 0;
  BufferSizeNeeded = 0;
  VolumeName.Buffer = 0;
  appended = FltGetVolumeName(v2, 0, &BufferSizeNeeded);
  if ( appended == -1073741789 )
  {
    BufferSizeNeeded += 92;
    Pool2 = (WCHAR *)ExAllocatePool2(256, BufferSizeNeeded, 1986937670);
    VolumeName.Buffer = Pool2;
    if ( !Pool2 )
    {
      appended = -1073741670;
      goto LABEL_4;
    }
    v7 = (struct _FLT_VOLUME *)a1[2];
    VolumeName.MaximumLength = BufferSizeNeeded;
    VolumeName.Length = 0;
    appended = FltGetVolumeName(v7, &VolumeName, 0);
    if ( appended >= 0 )
    {
      appended = RtlAppendUnicodeToString(&VolumeName, L"\\System Volume Information\\WPAppSettings.dat");
      if ( appended >= 0 )
      {
        v8 = (struct _FLT_INSTANCE *)a1[3];
        v9 = (struct _FLT_FILTER *)a1[1];
        ObjectAttributes.ObjectName = &VolumeName;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        appended = FltCreateFileEx(
                     v9,
                     v8,
                     &FileHandle,
                     &FileObject,
                     0x120089u,
                     &ObjectAttributes,
                     &IoStatusBlock,
                     0,
                     0,
                     7u,
                     1u,
                     0x40u,
                     0,
                     0,
                     0);
        if ( appended >= 0 )
        {
          v10 = (struct _FLT_INSTANCE *)a1[3];
          v3 = 1;
          ByteOffset.QuadPart = 0;
          appended = FltReadFile(v10, FileObject, &ByteOffset, 0x14u, &Buffer, 0, 0, 0, 0);
          if ( appended >= 0 && (_DWORD)Buffer != 20 )
            appended = -1073741811;
        }
      }
    }
  }
  Pool2 = VolumeName.Buffer;
LABEL_4:
  if ( Pool2 )
  {
    ExFreePoolWithTag(Pool2, 0x766E4346u);
    VolumeName.Buffer = 0;
  }
  if ( FileObject )
  {
    ObfDereferenceObject(FileObject);
    FileObject = 0;
  }
  if ( v3 )
    FltClose(FileHandle);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1400127b0  mov     [rsp-8+arg_8], rbx
0x1400127b5  mov     [rsp-8+arg_10], rsi
0x1400127ba  push    rbp
0x1400127bb  push    rdi
0x1400127bc  push    r14
0x1400127be  lea     rbp, [rsp-10h]
0x1400127c3  sub     rsp, 110h
0x1400127ca  mov     rax, cs:__security_cookie
0x1400127d1  xor     rax, rsp
0x1400127d4  mov     [rbp+20h+var_18], rax
0x1400127d8  xorps   xmm0, xmm0
0x1400127db  lea     r8, [rbp+20h+BufferSizeNeeded]; BufferSizeNeeded
0x1400127df  xor     r14d, r14d
0x1400127e2  mov     rsi, rcx
0x1400127e5  mov     rcx, [rcx+10h]; Volume
0x1400127e9  xor     eax, eax
0x1400127eb  movups  xmmword ptr [rbp+20h+var_70.ObjectName], xmm0
0x1400127ef  xor     edx, edx; VolumeName
0x1400127f1  mov     [rbp+20h+var_20], eax
0x1400127f4  movups  xmmword ptr [rbp+20h+var_70+1Ch], xmm0
0x1400127f8  mov     qword ptr [rbp+20h+ByteOffset], r14
0x1400127fc  xor     dil, dil
0x1400127ff  movups  [rbp+20h+Buffer], xmm0
0x140012803  mov     qword ptr [rbp+20h+VolumeName.Length], r14
0x140012807  movups  xmmword ptr [rbp+20h+var_70.Length], xmm0
0x14001280b  mov     [rbp+20h+FileObject], r14
0x14001280f  movups  xmmword ptr [rbp+20h+var_40], xmm0
0x140012813  mov     [rbp+20h+FileHandle], r14
0x140012817  mov     [rbp+20h+BufferSizeNeeded], r14d
0x14001281b  mov     [rbp+20h+VolumeName.Buffer], r14
0x14001281f  call    cs:__imp_FltGetVolumeName
0x140012826  nop     dword ptr [rax+rax+00h]
0x14001282b  mov     ebx, eax
0x14001282d  cmp     eax, 0C0000023h
0x140012832  jnz     loc_140012909
0x140012838  mov     eax, [rbp+20h+BufferSizeNeeded]
0x14001283b  mov     ecx, 100h
0x140012840  add     eax, 5Ch ; '\'
0x140012843  mov     r8d, 766E4346h
0x140012849  mov     edx, eax
0x14001284b  mov     [rbp+20h+BufferSizeNeeded], eax
0x14001284e  call    cs:__imp_ExAllocatePool2
0x140012855  nop     dword ptr [rax+rax+00h]
0x14001285a  mov     [rbp+20h+VolumeName.Buffer], rax
0x14001285e  test    rax, rax
0x140012861  jnz     short loc_1400128C2
0x140012863  mov     ebx, 0C000009Ah
0x140012868  test    rax, rax
0x14001286b  jz      short loc_140012885
0x14001286d  mov     edx, 766E4346h; Tag
0x140012872  mov     rcx, rax; P
0x140012875  call    cs:__imp_ExFreePoolWithTag
0x14001287c  nop     dword ptr [rax+rax+00h]
0x140012881  mov     [rbp+20h+VolumeName.Buffer], r14
0x140012885  mov     rcx, [rbp+20h+FileObject]; Object
0x140012889  test    rcx, rcx
0x14001288c  jnz     loc_140012A02
0x140012892  test    dil, dil
0x140012895  jnz     loc_140012A17
0x14001289b  mov     eax, ebx
0x14001289d  mov     rcx, [rbp+20h+var_18]
0x1400128a1  xor     rcx, rsp; StackCookie
0x1400128a4  call    __security_check_cookie
0x1400128a9  lea     r11, [rsp+120h+var_10]
0x1400128b1  mov     rbx, [r11+28h]
0x1400128b5  mov     rsi, [r11+30h]
0x1400128b9  mov     rsp, r11
0x1400128bc  pop     r14
0x1400128be  pop     rdi
0x1400128bf  pop     rbp
0x1400128c0  retn
0x1400128c2  movzx   eax, word ptr [rbp+20h+BufferSizeNeeded]
0x1400128c6  lea     rdx, [rbp+20h+VolumeName]; VolumeName
0x1400128ca  mov     rcx, [rsi+10h]; Volume
0x1400128ce  xor     r8d, r8d; BufferSizeNeeded
0x1400128d1  mov     [rbp+20h+VolumeName.MaximumLength], ax
0x1400128d5  mov     [rbp+20h+VolumeName.Length], r14w
0x1400128da  call    cs:__imp_FltGetVolumeName
0x1400128e1  nop     dword ptr [rax+rax+00h]
0x1400128e6  mov     ebx, eax
0x1400128e8  test    eax, eax
0x1400128ea  js      short loc_140012909
0x1400128ec  lea     rdx, aSystemVolumeIn; "\\System Volume Information\\WPAppSetti"...
0x1400128f3  lea     rcx, [rbp+20h+VolumeName]; Destination
0x1400128f7  call    cs:__imp_RtlAppendUnicodeToString
0x1400128fe  nop     dword ptr [rax+rax+00h]
0x140012903  mov     ebx, eax
0x140012905  test    eax, eax
0x140012907  jns     short loc_140012912
0x140012909  mov     rax, [rbp+20h+VolumeName.Buffer]
0x14001290d  jmp     loc_140012868
0x140012912  mov     rdx, [rsi+18h]; Instance
0x140012916  lea     rax, [rbp+20h+VolumeName]
0x14001291a  mov     rcx, [rsi+8]; Filter
0x14001291e  lea     r9, [rbp+20h+FileObject]; FileObject
0x140012922  mov     [rsp+120h+Flags], r14d; Flags
0x140012927  lea     r8, [rbp+20h+FileHandle]; FileHandle
0x14001292b  mov     [rsp+120h+EaLength], r14d; EaLength
0x140012930  xorps   xmm0, xmm0
0x140012933  mov     [rsp+120h+EaBuffer], r14; EaBuffer
0x140012938  mov     [rsp+120h+CreateOptions], 40h ; '@'; CreateOptions
0x140012940  mov     [rsp+120h+CreateDisposition], 1; CreateDisposition
0x140012948  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x140012950  mov     [rsp+120h+FileAttributes], r14d; FileAttributes
0x140012955  mov     [rbp+20h+var_70.ObjectName], rax
0x140012959  lea     rax, [rbp+20h+var_40]
0x14001295d  mov     [rsp+120h+AllocationSize], r14; AllocationSize
0x140012962  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x140012967  lea     rax, [rbp+20h+var_70]
0x14001296b  mov     [rsp+120h+ObjectAttributes], rax; ObjectAttributes
0x140012970  mov     [rsp+120h+DesiredAccess], 120089h; DesiredAccess
0x140012978  mov     [rbp+20h+var_70.Length], 30h ; '0'
0x14001297f  mov     [rbp+20h+var_70.RootDirectory], r14
0x140012983  mov     [rbp+20h+var_70.Attributes], 240h
0x14001298a  movdqu  xmmword ptr [rbp+20h+var_70.SecurityDescriptor], xmm0
0x14001298f  call    cs:__imp_FltCreateFileEx
0x140012996  nop     dword ptr [rax+rax+00h]
0x14001299b  mov     ebx, eax
0x14001299d  test    eax, eax
0x14001299f  js      loc_140012909
0x1400129a5  mov     rdx, [rbp+20h+FileObject]; FileObject
0x1400129a9  lea     rax, [rbp+20h+Buffer]
0x1400129ad  mov     rcx, [rsi+18h]; InitiatingInstance
0x1400129b1  lea     r8, [rbp+20h+ByteOffset]; ByteOffset
0x1400129b5  mov     qword ptr [rsp+120h+FileAttributes], r14; CallbackContext
0x1400129ba  mov     r9d, 14h; Length
0x1400129c0  mov     [rsp+120h+AllocationSize], r14; CallbackRoutine
0x1400129c5  mov     dil, 1
0x1400129c8  mov     [rsp+120h+IoStatusBlock], r14; BytesRead
0x1400129cd  mov     dword ptr [rsp+120h+ObjectAttributes], r14d; Flags
0x1400129d2  mov     qword ptr [rsp+120h+DesiredAccess], rax; Buffer
0x1400129d7  mov     qword ptr [rbp+20h+ByteOffset], r14
0x1400129db  call    cs:__imp_FltReadFile
0x1400129e2  nop     dword ptr [rax+rax+00h]
0x1400129e7  mov     ebx, eax
0x1400129e9  test    eax, eax
0x1400129eb  js      loc_140012909
0x1400129f1  cmp     dword ptr [rbp+20h+Buffer], 14h
0x1400129f5  mov     eax, 0C000000Dh
0x1400129fa  cmovnz  ebx, eax
0x1400129fd  jmp     loc_140012909
0x140012a02  call    cs:__imp_ObfDereferenceObject
0x140012a09  nop     dword ptr [rax+rax+00h]
0x140012a0e  mov     [rbp+20h+FileObject], r14
0x140012a12  jmp     loc_140012892
0x140012a17  mov     rcx, [rbp+20h+FileHandle]; FileHandle
0x140012a1b  call    cs:__imp_FltClose
0x140012a22  nop     dword ptr [rax+rax+00h]
0x140012a27  jmp     loc_14001289B
```
