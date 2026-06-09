# CipAuthRootLoadCTLsFromCrypt32Dll

- ea: `0x18005fac8`
- end: `0x18005fd84`
- name: `CipAuthRootLoadCTLsFromCrypt32Dll`
- size: `700`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800dc034`

## callees

- `0x18002bef0`
- `0x18002c040`
- `0x18005fac8`
- `0x180099ce4`
- `0x18009a180`

## import_xrefs

- `ntoskrnl!FsRtlGetFileSize` at `0x18005fbfb`
- `ntoskrnl!FsRtlGetFileSize` at `0x18005fbfb`
- `ntoskrnl!ExAllocatePool2` at `0x18005fcd9`
- `ntoskrnl!ExAllocatePool2` at `0x18005fcd9`
- `ntoskrnl!ZwClose` at `0x18005fd1e`
- `ntoskrnl!ZwClose` at `0x18005fd1e`
- `ntoskrnl!ObfDereferenceObject` at `0x18005fd08`
- `ntoskrnl!ObfDereferenceObject` at `0x18005fd08`
- `ntoskrnl!ZwCreateFile` at `0x18005fb9b`
- `ntoskrnl!ZwCreateFile` at `0x18005fb9b`
- `ntoskrnl!IoFileObjectType` at `0x18005fbb1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18005fbda`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18005fbda`
- `ntoskrnl!LdrResSearchResource` at `0x18005fca3`
- `ntoskrnl!LdrResSearchResource` at `0x18005fca3`

## string_xrefs

- `0x18005fb04`: `\SystemRoot\SystemResources\crypt32.dll.mun`

## pseudocode

```c
__int64 __fastcall CipAuthRootLoadCTLsFromCrypt32Dll(_QWORD *a1, _DWORD *a2)
{
  __int64 v4; // rsi
  NTSTATUS v5; // ebx
  NTSTATUS v6; // eax
  PVOID v7; // rdi
  int v8; // r9d
  int FileOpen; // eax
  void *Pool2; // rax
  size_t Size; // [rsp+60h] [rbp-A0h] BYREF
  void *Src; // [rsp+68h] [rbp-98h] BYREF
  __int64 v14; // [rsp+70h] [rbp-90h] BYREF
  void *FileHandle; // [rsp+78h] [rbp-88h] BYREF
  PVOID Object; // [rsp+80h] [rbp-80h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v18[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp-30h] BYREF
  void *v21[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v22; // [rsp+F0h] [rbp-10h]
  __int128 v23; // [rsp+100h] [rbp+0h]
  _QWORD v24[3]; // [rsp+110h] [rbp+10h] BYREF

  v18[0] = 5767254;
  v18[1] = L"\\SystemRoot\\SystemResources\\crypt32.dll.mun";
  v14 = 0;
  v4 = 0;
  FileHandle = 0;
  FileSize.QuadPart = 0;
  IoStatusBlock = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)v21 = 0;
  Src = 0;
  v22 = 0;
  ObjectAttributes.RootDirectory = 0;
  v23 = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v18;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwCreateFile(&FileHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 1u, 0x40u, 0, 0);
  if ( v5 < 0 )
    goto LABEL_14;
  Object = 0;
  v6 = ObReferenceObjectByHandle(FileHandle, 1u, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
  v7 = Object;
  v5 = v6;
  if ( v6 < 0 )
    goto LABEL_10;
  v5 = FsRtlGetFileSize((PFILE_OBJECT)Object, &FileSize);
  if ( v5 >= 0 )
  {
    if ( FileSize.QuadPart <= 0xFFFFFFFFuLL )
    {
      LOBYTE(v8) = 1;
      FileOpen = CiReadFileOpen((int)v7, 0, FileSize.LowPart, v8, v21, (__int64)&v14);
      v4 = v14;
      v5 = FileOpen;
      if ( FileOpen >= 0 )
      {
        v24[0] = L"AUTHROOTSTL";
        v24[1] = 1020;
        v24[2] = 0;
        Src = 0;
        Size = 0;
        v5 = LdrResSearchResource(v14, v24, 3, 4624, &Src, &Size, 0, 0);
        if ( v5 >= 0 )
        {
          if ( Size - 1 > 0xFFFFFFFE )
          {
            v5 = -1073741701;
          }
          else
          {
            Pool2 = (void *)ExAllocatePool2(258, (unsigned int)Size, 1668499779);
            *a1 = Pool2;
            if ( Pool2 )
            {
              memmove(Pool2, Src, (unsigned int)Size);
              *a2 = Size;
            }
            else
            {
              v5 = -1073741801;
            }
          }
        }
      }
LABEL_10:
      if ( v4 )
        CiReadFileClose(v21);
      goto LABEL_12;
    }
    v5 = -1073741701;
  }
LABEL_12:
  if ( v7 )
    ObfDereferenceObject(v7);
LABEL_14:
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18005fac8  mov     [rsp-8+arg_10], rbx
0x18005facd  mov     [rsp-8+arg_18], rsi
0x18005fad2  push    rbp
0x18005fad3  push    rdi
0x18005fad4  push    r12
0x18005fad6  push    r14
0x18005fad8  push    r15
0x18005fada  lea     rbp, [rsp-30h]
0x18005fadf  sub     rsp, 130h
0x18005fae6  mov     rax, cs:__security_cookie
0x18005faed  xor     rax, rsp
0x18005faf0  mov     [rbp+50h+var_28], rax
0x18005faf4  xor     r12d, r12d
0x18005faf7  mov     [rbp+50h+var_C0], 580056h
0x18005faff  mov     [rsp+150h+EaLength], r12d; EaLength
0x18005fb04  lea     rax, aSystemrootSyst_4; "\\SystemRoot\\SystemResources\\crypt32."...
0x18005fb0b  xorps   xmm0, xmm0
0x18005fb0e  mov     [rsp+150h+EaBuffer], r12; EaBuffer
0x18005fb13  mov     [rsp+150h+CreateOptions], 40h ; '@'; CreateOptions
0x18005fb1b  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x18005fb1f  mov     [rsp+150h+CreateDisposition], 1; CreateDisposition
0x18005fb27  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x18005fb2b  mov     [rbp+50h+var_B8], rax
0x18005fb2f  mov     r14, rdx
0x18005fb32  mov     [rsp+150h+ShareAccess], 1; ShareAccess
0x18005fb3a  lea     rax, [rbp+50h+var_C0]
0x18005fb3e  mov     r15, rcx
0x18005fb41  mov     [rsp+150h+FileAttributes], 80h; FileAttributes
0x18005fb49  mov     edx, 80000000h; DesiredAccess
0x18005fb4e  mov     [rsp+150h+AllocationSize], r12; AllocationSize
0x18005fb53  lea     rcx, [rsp+150h+FileHandle]; FileHandle
0x18005fb58  mov     [rsp+150h+var_E0], r12
0x18005fb5d  mov     esi, r12d
0x18005fb60  mov     [rsp+150h+FileHandle], r12
0x18005fb65  mov     qword ptr [rbp+50h+FileSize], r12
0x18005fb69  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x18005fb6d  mov     qword ptr [rbp+50h+ObjectAttributes.Length], 30h ; '0'
0x18005fb75  mov     qword ptr [rbp+50h+ObjectAttributes.Attributes], 240h
0x18005fb7d  movups  xmmword ptr [rbp+50h+var_70], xmm0
0x18005fb81  mov     [rsp+150h+Src], r12
0x18005fb86  movups  [rbp+50h+var_60], xmm0
0x18005fb8a  mov     [rbp+50h+ObjectAttributes.RootDirectory], r12
0x18005fb8e  movups  [rbp+50h+var_50], xmm0
0x18005fb92  mov     [rbp+50h+ObjectAttributes.ObjectName], rax
0x18005fb96  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005fb9b  call    cs:__imp_ZwCreateFile
0x18005fba2  nop     dword ptr [rax+rax+00h]
0x18005fba7  mov     ebx, eax
0x18005fba9  test    eax, eax
0x18005fbab  js      loc_18005FD14
0x18005fbb1  mov     r8, cs:__imp_IoFileObjectType
0x18005fbb8  lea     rax, [rbp+50h+Object]
0x18005fbbc  mov     rcx, [rsp+150h+FileHandle]; Handle
0x18005fbc1  lea     edx, [r12+1]; DesiredAccess
0x18005fbc6  mov     qword ptr [rsp+150h+FileAttributes], r12; HandleInformation
0x18005fbcb  xor     r9d, r9d; AccessMode
0x18005fbce  mov     [rbp+50h+Object], r12
0x18005fbd2  mov     r8, [r8]; ObjectType
0x18005fbd5  mov     [rsp+150h+AllocationSize], rax; Object
0x18005fbda  call    cs:__imp_ObReferenceObjectByHandle
0x18005fbe1  nop     dword ptr [rax+rax+00h]
0x18005fbe6  mov     rdi, [rbp+50h+Object]
0x18005fbea  mov     ebx, eax
0x18005fbec  test    eax, eax
0x18005fbee  js      loc_18005FCF2
0x18005fbf4  lea     rdx, [rbp+50h+FileSize]; FileSize
0x18005fbf8  mov     rcx, rdi; FileObject
0x18005fbfb  call    cs:__imp_FsRtlGetFileSize
0x18005fc02  nop     dword ptr [rax+rax+00h]
0x18005fc07  mov     ebx, eax
0x18005fc09  test    eax, eax
0x18005fc0b  js      loc_18005FD00
0x18005fc11  mov     r8, qword ptr [rbp+50h+FileSize]; int
0x18005fc15  mov     eax, 0FFFFFFFFh
0x18005fc1a  cmp     r8, rax
0x18005fc1d  ja      loc_18005FD7A
0x18005fc23  lea     rax, [rsp+150h+var_E0]
0x18005fc28  mov     r9b, 1; int
0x18005fc2b  mov     qword ptr [rsp+150h+FileAttributes], rax; __int64
0x18005fc30  xor     edx, edx; int
0x18005fc32  lea     rax, [rbp+50h+var_70]
0x18005fc36  mov     rcx, rdi; int
0x18005fc39  mov     [rsp+150h+AllocationSize], rax; PHANDLE
0x18005fc3e  call    CiReadFileOpen
0x18005fc43  mov     rsi, [rsp+150h+var_E0]
0x18005fc48  mov     ebx, eax
0x18005fc4a  test    eax, eax
0x18005fc4c  js      loc_18005FCF2
0x18005fc52  mov     qword ptr [rsp+150h+CreateDisposition], r12
0x18005fc57  lea     rax, aAuthrootstl; "AUTHROOTSTL"
0x18005fc5e  mov     [rbp+50h+var_40], rax
0x18005fc62  lea     r8d, [r12+3]
0x18005fc67  lea     rax, [rsp+150h+Size]
0x18005fc6c  mov     qword ptr [rsp+150h+ShareAccess], r12
0x18005fc71  mov     qword ptr [rsp+150h+FileAttributes], rax
0x18005fc76  lea     rdx, [rbp+50h+var_40]
0x18005fc7a  lea     rax, [rsp+150h+Src]
0x18005fc7f  mov     [rbp+50h+var_38], 3FCh
0x18005fc87  mov     r9d, 1210h
0x18005fc8d  mov     [rsp+150h+AllocationSize], rax
0x18005fc92  mov     rcx, rsi
0x18005fc95  mov     [rbp+50h+var_30], r12
0x18005fc99  mov     [rsp+150h+Src], r12
0x18005fc9e  mov     [rsp+150h+Size], r12
0x18005fca3  call    cs:__imp_LdrResSearchResource
0x18005fcaa  nop     dword ptr [rax+rax+00h]
0x18005fcaf  mov     ebx, eax
0x18005fcb1  test    eax, eax
0x18005fcb3  js      short loc_18005FCF2
0x18005fcb5  mov     rcx, [rsp+150h+Size]
0x18005fcba  mov     edx, 0FFFFFFFEh
0x18005fcbf  lea     rax, [rcx-1]
0x18005fcc3  cmp     rax, rdx
0x18005fcc6  ja      loc_18005FD70
0x18005fccc  mov     edx, ecx
0x18005fcce  mov     r8d, 63734943h
0x18005fcd4  mov     ecx, 102h
0x18005fcd9  call    cs:__imp_ExAllocatePool2
0x18005fce0  nop     dword ptr [rax+rax+00h]
0x18005fce5  mov     [r15], rax
0x18005fce8  test    rax, rax
0x18005fceb  jnz     short loc_18005FD55
0x18005fced  mov     ebx, 0C0000017h
0x18005fcf2  test    rsi, rsi
0x18005fcf5  jz      short loc_18005FD00
0x18005fcf7  lea     rcx, [rbp+50h+var_70]
0x18005fcfb  call    CiReadFileClose
0x18005fd00  test    rdi, rdi
0x18005fd03  jz      short loc_18005FD14
0x18005fd05  mov     rcx, rdi; Object
0x18005fd08  call    cs:__imp_ObfDereferenceObject
0x18005fd0f  nop     dword ptr [rax+rax+00h]
0x18005fd14  mov     rcx, [rsp+150h+FileHandle]; Handle
0x18005fd19  test    rcx, rcx
0x18005fd1c  jz      short loc_18005FD2A
0x18005fd1e  call    cs:__imp_ZwClose
0x18005fd25  nop     dword ptr [rax+rax+00h]
0x18005fd2a  mov     eax, ebx
0x18005fd2c  mov     rcx, [rbp+50h+var_28]
0x18005fd30  xor     rcx, rsp; StackCookie
0x18005fd33  call    __security_check_cookie
0x18005fd38  lea     r11, [rsp+150h+var_20]
0x18005fd40  mov     rbx, [r11+40h]
0x18005fd44  mov     rsi, [r11+48h]
0x18005fd48  mov     rsp, r11
0x18005fd4b  pop     r15
0x18005fd4d  pop     r14
0x18005fd4f  pop     r12
0x18005fd51  pop     rdi
0x18005fd52  pop     rbp
0x18005fd53  retn
0x18005fd55  mov     r8d, dword ptr [rsp+150h+Size]; Size
0x18005fd5a  mov     rcx, rax; void *
0x18005fd5d  mov     rdx, [rsp+150h+Src]; Src
0x18005fd62  call    memmove
0x18005fd67  mov     eax, dword ptr [rsp+150h+Size]
0x18005fd6b  mov     [r14], eax
0x18005fd6e  jmp     short loc_18005FCF2
0x18005fd70  mov     ebx, 0C000007Bh
0x18005fd75  jmp     loc_18005FCF2
0x18005fd7a  mov     ebx, 0C000007Bh
0x18005fd7f  jmp     loc_18005FD00
```
